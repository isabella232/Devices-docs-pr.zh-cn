---
title: 本地部署多林 (Surface Hub)
description: 本主题介绍如何在具有多林的本地部署时为 Microsoft Surface Hub 添加设备帐户。
keywords: 多林部署, 本地部署, 设备帐户, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831795"
---
# 多林环境中的 Surface Hub 的本地部署


本主题介绍如何在具有多林的本地部署时为 Microsoft Surface Hub 添加设备帐户。

如果具有带 Microsoft Exchange 2013 或更高版本和 Skype for Business 2013 或更高版本的多林本地部署，则可以[使用提供的 PowerShell 脚本](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts)创建设备帐户。 如果使用的是单林部署，请参阅[单林环境中 Surface Hub 的本地部署](on-premises-deployment-surface-hub-device-accounts.md)。

1.  在电脑上启动远程 PowerShell 会话，并连接到 Exchange。

    请确保已设置正确的权限来运行关联的 cmdlet。

    请注意下面，`$strExchangeServer` 是你的 Exchange Server 的完全限定的域名 (FQDN)，而 `$strLyncFQDN` 是你的 Skype for Business Server 的 FQDN。

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  建立会话后，在资源林中创建新的邮箱。 这将允许帐户在 Surface Hub 中进行身份验证。

    如果要更改现有资源邮箱：

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用现有兼容的策略。

    Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 **False**）兼容。 如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。

    如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。 完成创建后，你可以对其他设备帐户应用相同的策略。

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    具有兼容的策略后，需要将该策略应用于设备帐户。 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  可在设备帐户上设置各种 Exchange 属性，以改进用户的会议体验。 你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)部分中查看需要设置哪些属性。

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。 有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。 这应该在用户林中设置。

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  在 Active Directory 中启用帐户，以便它对 Surface Hub 进行身份验证。 这应该在用户林中设置。

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. 你现在需要将会议室邮箱更改为已链接的邮箱：

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  通过在 Skype for Business Server 池上启用 Surface Hub AD 帐户，启用带 Skype for Business 的设备帐户：

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    你将需要针对 Surface Hub 使用会话初始协议 (SIP) 地址和域控制器，以及你自己的 Skype for Business Server 池标识符和用户身份。


## 禁用匿名电子邮件和即时消息



Surface Hub 使用设备帐户提供电子邮件和协作服务（IM、视频和语音）。 此设备帐户在发送电子邮件、即时消息和呼叫时用作源标识（"发件人" 一方）。 由于此帐户不是来自个人可标识的用户，因此它被视为 "匿名"，因为它来源于 Surface Hub 的设备帐户。  

假设你有一个每用户客户端策略，该策略分配给每个具有**SurfaceHubPolicy**标识的会议室设备。 若要禁用匿名电子邮件和消息，请使用以下命令将 clientPolicyEntry 添加到此客户端策略。

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

若要验证是否已设置策略，请执行以下操作：

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

输出应为：

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
若要更改策略条目，请执行以下操作：

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
要删除策略条目，请执行以下操作：

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 






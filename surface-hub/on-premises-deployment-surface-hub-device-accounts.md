---
title: 本地部署单林 (Surface Hub)
description: 本主题介绍如何在具有单林的本地部署时为 Microsoft Surface Hub 添加设备帐户。
ms.assetid: 80E12195-A65B-42D1-8B84-ECC3FCBAAFC6
ms.reviewer: ''
manager: laurawi
keywords: 单林部署, 本地部署, 设备帐户, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.localizationpriority: medium
ms.openlocfilehash: 37b157268769ddcdeaef67b7e19cc7260cd392b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831811"
---
# 单林环境中 Surface Hub 的本地部署


本主题介绍如何在具有单林的本地部署时为 Microsoft Surface Hub 添加设备帐户。

如果具有带 Microsoft Exchange 2013 或更高版本和 Skype for Business 2013 或更高版本的单林本地部署，则可以[使用提供的 PowerShell 脚本](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts)创建设备帐户。 如果使用的是多林部署，请参阅[多林环境中 Surface Hub 的本地部署](on-premises-deployment-surface-hub-multi-forest.md)。

1. 在电脑上启动远程 PowerShell 会话，并连接到 Exchange。

   请确保已设置正确的权限来运行关联的 cmdlet。

   请注意下面，`$strExchangeServer` 是你的 Exchange Server 的完全限定的域名 (FQDN)，而 `$strLyncFQDN` 是你的 Skype for Business 服务器的 FQDN。

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. 建立会话后，你将创建一个新邮箱并启用它作为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许在 Surface Hub 中对帐户进行身份验证。

   如果要更改现有资源邮箱：

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   如果要创建新的资源邮箱：

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> 需要启用 ActiveSync 虚拟目录基本身份验证，因为 Surface Hub 无法使用其他身份验证方法进行身份验证。

3. 设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。

   Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 False）兼容。 如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。

   如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。 完成创建后，你可以对其他设备帐户应用相同的策略。

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   具有兼容的策略后，你需要将该策略应用于设备帐户。 但是，仅可以将策略应用到用户帐户，而非资源邮箱。 你需要将邮箱转换为用户类型、应用策略，然后将其转换回邮箱 — 你可能需要重新启用它并重新设置密码。

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. 可在设备帐户上设置各种 Exchange 属性以改进用户的会议体验。 你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)部分中查看需要设置哪些属性。

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. 如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。 有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. 启用 Active Directory 中的帐户，以便它将在 Surface Hub 中进行身份验证。

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. 通过在 Skype for Business Server 池上启用你的 Surface Hub AD 帐户，使用 Skype for Business 启用设备帐户：

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   你将需要针对 Surface Hub 使用会话初始协议 (SIP) 地址和域控制器，以及你自己的 Skype for Business Server 池标识符和用户身份。

8. 可选：你还可以通过为你的帐户启用企业语音，从而让你的 Surface Hub 可以接打公用电话交换网 (PSTN) 电话。 Surface Hub 不要求企业语音，但是如果你想要使用 Surface Hub 客户端的 PSTN 拨号功能，下面是启用它的方法：

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   同样，您需要将所提供的域控制器和电话号码示例替换为您自己的信息。 参数值 `$true` 保持不变。
    

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

 






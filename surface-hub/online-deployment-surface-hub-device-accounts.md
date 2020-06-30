---
title: 使用 Office 365 的联机部署 (Surface Hub)
description: 本主题提供有关在具有纯联机部署时为 Microsoft Surface Hub 添加设备帐户的说明。
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 的设备帐户, 联机部署
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831792"
---
# 使用 Office 365 的联机部署 (Surface Hub)


本主题提供有关在具有纯联机部署时为 Microsoft Surface Hub 添加设备帐户的说明。

如果具有纯联机 (O365) 部署，可[使用提供的 PowerShell 脚本](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts)创建设备帐户。 

1. 在电脑上启动远程 PowerShell 会话，并连接到 Exchange。

   请确保已设置正确的权限来运行关联的 cmdlet。

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. 建立会话后，你将创建一个新邮箱并启用它作为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许在 Surface Hub 中对帐户进行身份验证。

   如果要更改现有资源邮箱：

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   如果要创建新的资源邮箱：

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。

   Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 False）兼容。 如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。

   如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。 完成创建后，你可以对其他设备帐户应用相同的策略。

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   具有兼容的策略后，你需要将该策略应用于设备帐户。

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. 必须在设备帐户上设置各种 Exchange 属性才能改进会议体验。 你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md) 部分中查看需要设置哪些属性。

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. 连接到 Azure AD。
    
   首先需要安装 PowerShell 版本 2 的 Azure AD 模块。 在提升的命令提示符处运行以下命令:
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   需要连接到 Azure AD 才能应用某些帐户设置。 你可以运行此 cmdlet 来进行连接。

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. 如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。 有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. Surface Hub 需要许可证以使用 Skype for Business 功能。 为了启用 Skype for Business，你的环境将需要满足 [Skype for Business Online 的必备条件](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online)。
   
   接下来，可使用 `Get-AzureADSubscribedSku` 检索可供 O365 租户使用的 SKU 列表。

   列出 SKU 后，需要将所需的 SkuId 分配给 `$License.SkuId` 变量。

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"
    
   Get-AzureADSubscribedSku | Select Sku*,*Units
   $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
   $License.SkuId = SkuId You selected 
    
   $AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
   $AssignedLicenses.AddLicenses = $License
   $AssignedLicenses.RemoveLicenses = @()
    
   Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
   ```

8. 使用 Skype for Business 启用设备帐户。
   如果未安装 Skype for Business PowerShell 模块，请[下载 Skype for Business Online Windows PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)。 

   - 首先在电脑上创建一个远程 PowerShell 会话。

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - 接着，如果你不确定将哪个值用于环境中的 `RegistrarPool` 参数，则可以使用此 cmdlet（例如，<em>alice@contoso.com</em>），从现有的 Skype for Business 用户中获取值：

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       或通过设置变量获取值
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - 使用以下 cmdlet 启用 Surface Hub 帐户：
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       或使用上文中的 $strRegistarPool 变量
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

为了进行验证，你应该能使用任一 Skype for Business 客户端（电脑、Android 等）登录此帐户。






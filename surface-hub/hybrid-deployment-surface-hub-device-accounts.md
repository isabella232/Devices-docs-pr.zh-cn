---
title: 混合部署 (Surface Hub)
description: 混合部署需要特殊处理，才能为 Microsoft Surface Hub 设置设备帐户。
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: 混合部署, Surface Hub 的设备帐户, 本地托管的 Exchange, 联机托管的 Exchange
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831828"
---
# 混合部署 (Surface Hub)

混合部署需要特殊处理，才能为 Microsoft Surface Hub 设置设备帐户。 如果使用的是混合部署（即组织中混合服务的一部分是本地托管的，另一部分是联机托管的），你的配置将取决于每个服务的托管位置。 本主题涵盖[本地托管的 Exchange](#exchange-on-premises)、[联机托管的 Exchange](#exchange-online)、本地 Skype for Business、Skype for Business Online 和混合 Skype for Business 的混合部署。 由于这种类型的部署有很多不同的变体，因此无法针对所有部署提供详细说明。 以下过程将适用于许多配置。 如果该过程不适合你的设置，我们建议你使用 PowerShell（请参阅[附录：PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)）以针对其他部署选项获得相同的最终结果，如此处所述。 然后，应使用提供的 Powershell 脚本验证 Surface Hub 设置。 （请参阅[帐户验证脚本](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)。）

> [!NOTE]
> 在 Exchange 混合环境中，按照[本地 exchange](#exchange-on-premises)的步骤进行操作。 若要将 Exchange 对象移动到 Office 365，请使用[MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet。

## 本地 Exchange

如果你使用本地 Exchange，请使用此过程。

1. 在此过程中，你将使用 AD 管理员工具为你的本地域帐户添加电子邮件地址。 此帐户将同步到 Office 365。

- 在 **Active Directory 用户和计算机** AD 工具中，右键单击将在其中创建 Surface Hub 帐户的文件夹或组织单位，然后依次单击**新建**和**用户**。
- 将上一 cmdlet 的显示名称键入到**全名**框中，而将别名键入到**用户登录名称**框中。 单击**下一步**。<p>

![用于在 Active Directory 中创建新用户的新对象框。](images/hybriddeployment-01a.png)

- 键入此帐户的密码。 你将需要重新键入它以供验证。 请确保**密码永不过期**复选框是唯一处于选中状态的选项。

> **重要提示** Surface Hub 上的 Skype for Business 要求选择**密码永不过期**。 域规则可能会禁止未过期的密码。 如果是这样，你将需要针对每个 Surface Hub 设备帐户创建例外。

![显示密码对话框的图像。](images/hybriddeployment-02a.png)

-   单击**完成**以创建帐户。

![具有新用户的帐户名称、登录名称和密码选项的图像。](images/hybriddeployment-03a.png)

2. 启用远程邮箱。

使用管理员权限打开你的本地 Exchange 命令行管理程序，并运行此 cmdlet。

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> 如果没有本地 Exchange 环境来运行此 cmdlet，则你可以直接对此帐户的 Active Directory 对象进行相同的更改。
>
> msExchRemoteRecipientType = 33
>
> msExchRecipientDisplayType = -2147481850
>
> msExchRecipientTypeDetails = 8589934592

3. 创建完帐户后，运行目录同步。 完成后，转到 Microsoft 365 管理中心中的 "用户" 页面，并验证在先前步骤中创建的帐户是否已合并到 "联机"。

4. 连接到 Microsoft Exchange Online 并在 Office 365 中设置帐户的某些属性。

在电脑上启动远程 PowerShell 会话，并连接到 Microsoft Exchange。 请确保已设置正确的权限来运行关联的 cmdlet。

后续步骤将在你的 Office 365 租户上运行。

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. 创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。

设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。

Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 False）兼容。 如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。

如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。 完成创建后，你可以对其他设备帐户应用相同的策略。

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

一旦你有兼容的策略，你将需要将策略应用到设备帐户。 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. 设置 Exchange 属性。

可通过设置设备帐户上的 Exchange 属性来改进会议体验。 你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md) 部分中查看需要设置哪些属性。

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. 连接到 Azure AD。

首先需要安装 PowerShell 版本 2 的 Azure AD 模块。 在提升的 PowerShell 提示符下，运行以下命令：

```PowerShell
Install-Module -Name AzureAD
```

需要连接到 Azure AD 才能应用某些帐户设置。 你可以运行此 cmdlet 来进行连接。

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. 分配 Office 365 许可证。

设备帐户需要有一个有效的 Office 365 (O365) 许可证，否则 Exchange 和 Skype for Business 将不可用。 如果已拥有许可证，则需要将使用位置分配给设备帐户，以便确定适用于你的帐户的许可证 SKU。

可使用 `Get-AzureADSubscribedSku` 检索可供 O365 租户使用的 SKU 列表。

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

接下来，使用 [Skype for Business Online](#skype-for-business-online)、[本地 Skype for Business](#skype-for-business-on-premises) 或[混合 Skype for Business](#skype-for-business-hybrid) 启用设备帐户。

### Skype for Business Online

若要启用 Skype for Business Online，租户用户必须具有 Exchange 邮箱（至少需要租户中的一个 Exchange 邮箱）。 下表说明了你需要的计划或附加服务。

| Skype 房间系统方案 | 如果您有 Office 365 Premium、Microsoft 365 适用的企业版或 Skype for business 独立计划2，您需要： | 如果你有基于企业版的计划，则需要： | 如果您有 Skype for business Server 2015 （本地或混合版），您需要： |
| --- | --- | --- | --- |
| 加入计划的会议 | Skype for Business 独立计划 1 | E1、3、4 或 5 | Skype for Business Server 标准 CAL |
| 启动临时安排的会议 | Skype for Business 独立计划 2 | E 1、3、4 或 5 | Skype for Business Server 标准 CAL 或企业 CAL |
| 启动临时安排的会议并在会议中拨出电话号码 | 带有音频会议的 Skype for business 独立计划2</br></br>**注意** PSTN 用量计费为可选项 | 具有音频会议或 E5 的 E1 或 E3| Skype for Business Server 标准 CAL 或企业 CAL |
| 为房间提供电话号码，并从房间拨打或接听电话或者使用电话号码加入电话拨入式会议 | Skype for business 独立计划2，带有电话系统和 PSTN 语音呼叫计划 | 与电话系统和 PSTN 语音呼叫计划（即 E5）的 E1 或 E3 | Skype for Business Server 标准 CAL 或 Plus CAL |

下表列出了 Office 365 计划和 Skype for Business 选项。

| O365 计划 | Skype for Business | 电话系统 | 音频会议 | 通话计划 |
| --- | --- | --- | --- | --- |
| O365 商业协作版 | 已包含 |  |  |  |
| O365 商业高级版 | 已包含 |  |  |  |
| E1 | 已包含 | 加载项 | 加载项 | 加载项（需要电话系统加载项） |
| E3 | 已包含 | 加载项 | 加载项 | 加载项（需要电话系统加载项） |
| E5 | 已包含 | 已包含 | 已包含 | 加载项  |

1. 首先，创建从电脑到 Skype for Business Online 环境的远程 PowerShell 会话。

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. 若要为 Skype for Business Server 启用你的 Surface Hub 帐户，请运行此 cmdlet：

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

如果你不确定在你的环境中要用于 `RegistrarPool` 参数的值，你可以使用此 cmdlet 从现有 Skype for Business 用户获取值：

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. 将 Skype for Business 许可证分配给你的 Surface Hub 帐户。

 在完成上述用来在 Skype for Business Online 中启用 Surface Hub 帐户的步骤后，你需要将许可证分配给 Surface Hub。 使用 O365 管理门户，为设备分配 Skype for business Online （计划2）或 Skype for business Online （计划3）许可证。

- 以租户管理员身份登录、打开 O365 管理门户，然后单击管理员应用。

- 单击**用户和组**，然后单击**添加用户、重置密码等**。

- 单击 Surface Hub 帐户，然后单击笔图标以编辑帐户信息。

- 单击**许可证**。

- 在 "**分配许可证**" 中，选择 "skype for Business （计划1）" 或 "skype for business" （计划2），具体取决于你的许可和企业语音要求。 如果要在 Surface Hub 上使用企业语音，则必须使用计划2许可证。

- 单击**保存**。

> [!NOTE]
> 还可以使用适用于 Windows Powershell 的 Windows Azure Active Directory 模块，运行分配这些许可证之一所需的 cmdlet，但此处未做介绍。

为了进行验证，你应该能使用任一 Skype for Business Client（电脑、Android 等）登录此帐户。

### 本地 Skype for Business

若要运行此 cmdlet，你将需要连接到 Skype 前端之一。 打开 Skype PowerShell 并运行：

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### 混合 Skype for Business

如果你的组织已设置 [Skype for Business Server 和 Skype for Business Online ](https://technet.microsoft.com/library/jj205403.aspx)之间的混合连接，创建帐户的指南与标准 Surface Hub 部署不同。

Surface Hub 需要类型为 `meetingroom` 的 Skype 帐户，而普通用户将在 Skype 中使用用户类型帐户。 如果针对一些用户在本地 Skype 服务器上，而一些用户托管在 Office 365 上的混合环境设置你的 Skype 服务器，你可能在尝试创建 Surface Hub 帐户时遇到几个问题。

在 Skype for Business Server 2015 混合环境中，你希望在 Skype for Business Online 中使用的任何用户都必须先在本地部署中创建，以便在 Active Directory 域服务中创建用户帐户。 然后，您可以将用户移动到 Skype for business Online。 从本地到联机的用户帐户的移动通过[move-csuser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet 完成。 若要移动 Csmeetingroom 对象，请使用[Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet。

> [!NOTE]
> 若要使用 CsMeetingRoom cmdlet，你必须已安装适用于[Skype For Business Server 2015 的2017累积更新 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)或[Lync Server 2013 的7月2017累积更新 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)。


## Exchange Online

如果你使用 Exchange Online，请使用此过程。

1. 在 Office 365 中创建电子邮件帐户。

在电脑上启动远程 PowerShell 会话，并连接到 Exchange。 请确保已设置正确的权限来运行关联的 cmdlet。

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. 设置邮箱。

建立会话后，你将创建一个新邮箱并启用它作为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许在 Surface Hub 中对帐户进行身份验证。

如果要更改现有资源邮箱：

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

如果要创建新的资源邮箱：

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. 创建 Exchange ActiveSync 策略。

设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。

Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 False）兼容。 如果未正确设置，Surface Hub （"邮件"、"日历" 和 "加入会议"）上的 Exchange 服务将不会启用。

如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。 完成创建后，你可以对其他设备帐户应用相同的策略。

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

一旦你有兼容的策略，你将需要将策略应用到设备帐户。 但是，仅可以将策略应用到用户帐户，而非资源邮箱。 你需要将邮箱转换为用户类型、应用策略，然后将其转换回邮箱 — 你可能需要重新启用它并重新设置密码。

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. 设置 Exchange 属性。

必须在设备帐户上设置各种 Exchange 属性才能改进会议体验。 你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md) 部分中查看需要设置哪些属性。

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. 为您的本地域帐户添加电子邮件地址。

在此过程中，你将使用 AD 管理员工具为你的本地域帐户添加电子邮件地址。

- 在 **Active Directory 用户和计算机** AD 工具中，右键单击将在其中创建 Surface Hub 帐户的文件夹或组织单位，然后依次单击**新建**和**用户**。
- 将上一 cmdlet 的显示名称键入到**全名**框中，而将别名键入到**用户登录名称**框中。 单击**下一步**。

![用于在 Active Directory 中创建新用户的新对象框。](images/hybriddeployment-01a.png)

- 键入此帐户的密码。 你将需要重新键入它以供验证。 请确保**密码永不过期**复选框是唯一处于选中状态的选项。

> [!IMPORTANT]
> 选择 "**密码永不过期**" 是对 Surface Hub 上的 Skype for business 的要求。 域规则可能会禁止未过期的密码。 如果是这样，你将需要针对每个 Surface Hub 设备帐户创建例外。

![显示密码对话框的图像。](images/hybriddeployment-02a.png)

- 单击**完成**以创建帐户。

![具有新用户的帐户名称、登录名称和密码选项的图像。](images/hybriddeployment-03a.png)

6. 运行目录同步。

创建完帐户后，运行目录同步。 完成后，请转到用户页，并验证前面步骤中创建的两个帐户是否已合并。

7. 连接到 Azure AD。

首先需要安装 PowerShell 版本 2 的 Azure AD 模块。 在提升的 PowerShell 提示符下，运行以下命令：

```PowerShell
Install-Module -Name AzureAD
```

需要连接到 Azure AD 才能应用某些帐户设置。 你可以运行此 cmdlet 连接到：

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. 分配 Office 365 许可证。

设备帐户需要有一个有效的 Office 365 (O365) 许可证，否则 Exchange 和 Skype for Business 将不可用。 如果已拥有许可证，则需要将使用位置分配给设备帐户，以便确定适用于你的帐户的许可证 SKU。

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

接下来，使用 [Skype for Business Online](#skype-for-business-online)、[本地 Skype for Business](#skype-for-business-on-premises) 或[混合 Skype for Business](#skype-for-business-hybrid) 启用设备帐户。

### Skype for Business Online

为了启用 Skype for Business，你的环境将需要满足 [Skype for Business Online 的必备条件](#skype-for-business-online)。

1. 首先，创建从电脑到 Skype for Business Online 环境的远程 PowerShell 会话。

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. 若要为 Skype for Business Server 启用你的 Surface Hub 帐户，请运行此 cmdlet：

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   如果你不确定在你的环境中要用于 `RegistrarPool` 参数的值，你可以使用此 cmdlet 从现有 Skype for Business 用户获取值：

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. 将 Skype for Business 许可证分配给你的 Surface Hub 帐户

在完成上述用来在 Skype for Business Online 中启用 Surface Hub 帐户的步骤后，你需要将许可证分配给 Surface Hub。 使用 O365 管理门户，为设备分配 Skype for business Online （计划2）或 Skype for business Online （计划3）许可证。

- 以租户管理员身份登录、打开 O365 管理门户，然后单击管理员应用。

- 单击**用户和组**，然后单击**添加用户、重置密码等**。

- 单击 Surface Hub 帐户，然后单击笔图标以编辑帐户信息。

- 单击**许可证**。

- 在**分配许可证**中，选择 Skype for Business（计划 2）或 Skype for Business（计划 3），具体取决于你的许可和企业语音要求。 如果你想要在 Surface Hub 上使用企业语音，你将需要使用计划 3 许可证。

- 单击**保存**。

> [!NOTE]
> 你还可以使用适用于 Windows PowerShell 的 Windows Azure Active Directory 模块，运行分配这些许可证之一所需的 cmdlet，但此处未做介绍。

为了进行验证，你应该能使用任一 Skype for Business Client（电脑、Android 等）登录此帐户。

### 本地 Skype for Business

若要运行此 cmdlet，你将需要连接到 Skype 前端之一。 打开 Skype PowerShell 并运行：

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### 混合 Skype for Business

如果你的组织已设置 [Skype for Business Server 和 Skype for Business Online ](https://technet.microsoft.com/library/jj205403.aspx)之间的混合连接，创建帐户的指南与标准 Surface Hub 部署不同。

Surface Hub 需要类型为*会议室*的 Skype 帐户，而普通用户将在 Skype 中使用*用户*类型帐户。 如果针对一些用户在本地 Skype 服务器上，而一些用户托管在 Office 365 上的混合环境设置你的 Skype 服务器，你可能在尝试创建 Surface Hub 帐户时遇到几个问题。

在 Skype for Business Server 2015 混合环境中，你希望在 Skype for Business Online 中使用的任何用户都必须先在本地部署中创建，以便在 Active Directory 域服务中创建用户帐户。 然后，您可以将用户移动到 Skype for business Online。 从本地到联机的用户帐户的移动通过[move-csuser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet 完成。 若要移动 Csmeetingroom 对象，请使用[Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet。

> [!NOTE]
> 若要使用 CsMeetingRoom cmdlet，你必须已安装适用于[Skype For Business Server 2015 的2017累积更新 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)或[Lync Server 2013 的7月2017累积更新 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)。

---
title: 创建 Surface Hub 2S 设备帐户
description: 本页介绍创建 Surface Hub 2 设备帐户的过程。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196725"
---
# 创建 Surface Hub 2S 设备帐户

创建 Surface Hub 设备帐户 (也称为会议室邮箱) 允许 Surface Hub 2 使用 Microsoft 团队或 Skype for business 接收、批准或拒绝会议请求并加入会议。  (OOBE) 安装程序时在全新体验期间配置设备帐户。 如果需要，您可以在以后 (更改它，而无需通过 OOBE 设置) 。

与默认情况下处于禁用状态的标准会议室邮箱不同，你需要启用 Surface Hub 2 设备帐户以登录到 Microsoft 团队和 Skype for business。 Surface Hub 2 依赖 Exchange ActiveSync，这需要设备帐户上的 ActiveSync 邮箱策略。 应用 Exchange Online 附带的默认 ActiveSync 邮箱策略。

使用 Microsoft 365 管理中心或使用 PowerShell 创建帐户。 你可以使用 Exchange Online PowerShell 配置特定功能，包括：

- 每个 Surface Hub 设备帐户的日历处理。
- 自定义自动答复日程安排请求。
- 如果默认的 ActiveSync 邮箱策略已由其他人或另一个进程修改，则可能需要创建并分配新的 ActiveSync 邮箱策略。

> [!NOTE]  
> Surface Hub 设备帐户不支持 (FIPs) 的第三方联合身份提供程序，并且必须是标准 Active Directory 或 Azure Active Directory 帐户。

## 使用 Microsoft 365 管理中心创建帐户

1. 在 Microsoft 365 管理中心中，转到 " **资源** " 并选择 " **会议室" & 设备** ，然后选择 " **+ 会议室**"。

2. 提供设备帐户的名称和电子邮件地址。 保留默认状态中的 "剩余设置" 不变。

   ![提供姓名和电子邮件地址](images/sh2-account2.png)

   ![保留默认状态中的 "剩余设置" 不变](images/sh2-account3.png)

3. 设置设备帐户的密码。 若要设置密码，请选择 " **用户** "，然后选择 " **活动用户**"。 现在，搜索新创建的用户以设置密码。 确保**未**选中 "将**此用户首次登录时，使此用户更改其密码**" 选项。

   ![设置设备帐户的密码](images/sh2-account4.png)

4. 使用 Office 365 许可证分配会议室。 建议分配 Office 365 **会议室** 许可证，这是一个新选项，可自动为 Skype For business Online 和 Microsoft 团队启用帐户。

   ![分配 Office 365 许可证](images/sh2-account5.png)

### 通过 PowerShell 完成安装

- **Microsoft 团队和 Skype for Business 日历：** 为此帐户设置 [**日历自动处理**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) 。

## 使用 PowerShell 创建帐户

你可以使用 PowerShell 创建帐户，而不是使用 Microsoft 管理中心门户。

### 连接到 Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### 创建邮箱

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### 设置日历自动处理

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### 如果需要使用电子邮件应用，请启用 "动态同步"

 如果 unchnaged，则默认 ActiveSync 策略将正常工作。 否则，创建新策略并分配。

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### 连接到 Azure AD

```powershell
Connect-AzureAD
```

### 分配许可证

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### 检查可用的许可证

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```
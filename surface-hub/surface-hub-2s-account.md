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
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831916"
---
# 创建 Surface Hub 2S 设备帐户

创建 Surface Hub 设备帐户（也称为会议室邮箱）允许 Surface Hub 2 接收、批准或拒绝会议请求，并使用 Microsoft 团队或 Skype for business 加入会议。 在全新体验设置期间配置设备帐户（OOBE）。 如果需要，您可以稍后更改它（无需通过 OOBE 设置）。

与默认情况下处于禁用状态的标准会议室邮箱不同，你需要启用 Surface Hub 2 设备帐户以登录到 Microsoft 团队和 Skype for business。 Surface Hub 2 依赖 Exchange ActiveSync，这需要设备帐户上的 ActiveSync 邮箱策略。 应用 Exchange Online 附带的默认 ActiveSync 邮箱策略。

使用 Microsoft 365 管理中心或使用 PowerShell 创建帐户。 你可以使用 Exchange Online PowerShell 配置特定功能，包括：

- 每个 Surface Hub 设备帐户的日历处理。
- 自定义自动答复日程安排请求。
- 如果默认的 ActiveSync 邮箱策略已由其他人或另一个进程修改，则可能需要创建并分配新的 ActiveSync 邮箱策略。

> [!NOTE]  
> Surface Hub 设备帐户不支持第三方联合身份提供程序（FIPs），并且必须是标准的 Active Directory 或 Azure Active Directory 帐户。

## 使用 Microsoft 365 管理中心创建帐户

1. 在 Microsoft 365 管理中心中，转到 "**资源**" 并选择 "**会议室" & 设备**，然后选择 " **+ 会议室**"。

2. 提供设备帐户的名称和电子邮件地址。 保留默认状态中的 "剩余设置" 不变。

   ![提供姓名和电子邮件地址](images/sh2-account2.png)

   ![保留默认状态中的 "剩余设置" 不变](images/sh2-account3.png)

3. 设置设备帐户的密码。 若要设置密码，请选择 "**用户**"，然后选择 "**活动用户**"。 现在，搜索新创建的用户以设置密码。 确保**未**选中 "将**此用户首次登录时，使此用户更改其密码**" 选项。

   ![设置设备帐户的密码](images/sh2-account4.png)

4. 使用 Office 365 许可证分配会议室。 建议分配 Office 365**会议室**许可证，这是一个新选项，可自动为 Skype For business Online 和 Microsoft 团队启用帐户。

   ![分配 Office 365 许可证](images/sh2-account5.png)

### 通过 PowerShell 完成安装

- **Skype For business：** 对于仅限 Skype for business （本地版或联机版），您可以通过运行**enable-CsMeetingRoom**启用 skype for business 对象来启用音频和会议厅保留的会议室提示功能。

- **Microsoft 团队和 Skype for Business 日历：** 为此帐户设置[**日历自动处理**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing)。

## 使用 PowerShell 创建帐户

你可以使用 PowerShell 创建帐户，而不是使用 Microsoft 管理中心门户。

### 连接到 Exchange Online PowerShell

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### 创建新的会议室邮箱

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### 设置日历自动处理

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### 分配许可证

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## 使用 PowerShell 连接到 Skype for Business Online

### 安装先决条件

- [Visual c + + 2017 可再发行组件](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [Skype for Business Online PowerShell 模块](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```

---
title: 配置 PowerShell 的 Surface Hub 2 本地帐户
description: 了解如何通过 PowerShell 配置本地帐户的 Surface Hub 2
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
ms.openlocfilehash: 6832f4e4b5bc307746ec5838c0f80d043a22021a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832048"
---
# 配置 PowerShell 的 Surface Hub 2 本地帐户

## 连接到 Exchange Server PowerShell

> [!IMPORTANT]
> 对于某些 cmdlet，你需要本地 Exchange server 的客户端访问服务的完全限定的域名（FQDN）。

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## 创建设备帐户

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## 设置自动日历处理

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## 启用 Skype for Business 对象

> [!NOTE]
> 了解 Skype for business 注册机构池的 FQDN 非常重要。

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## 移动设备邮箱策略

你可能需要创建移动设备邮箱策略（也称为 ActiveSync 策略），以允许 Surface Hub 连接到你的联机或本地环境。

## 创建 Surface Hub 移动设备邮箱策略

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## 其他设置

建议将邮件提醒添加到 Surface Hub 房间，以便用户记得让会议成为 Skype for Business 或团队会议：

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```

---
title: 适用于 Surface Pro 3 (Surface) 的高级 UEFI 安全功能
description: 本文介绍了如何安装和配置 v3.11.760.0 UEFI 更新，以便针对 Surface Pro 3 设备启用其他安全选项。
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: 安全, 功能, 配置, 硬件, 设备, 自定义, 脚本, 更新
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 6a5c53c3e161bd4c49069a0665896762ce587618
ms.sourcegitcommit: e9190a6fe68b8a7cd9b024aea4be9f885f0de388
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163185"
---
# 适用于 Surface Pro 3 的高级 UEFI 安全功能


本文介绍了如何安装和配置 v3.11.760.0 UEFI 更新，以便针对 Surface Pro 3 设备启用其他安全选项。

为了解决对 Surface 设备安全的更细化的控制，v3.11.760.0 UEF 更新提供了其他安全选项，可使你禁用特定的硬件设备或阻止这些设备启动。 在设备上安装 UEFI 更新后，你可以手动配置它，也可以通过运行脚本自动进行配置。

## 手动安装 UEFI 更新


必须先安装 v3.11.760.0 UEFI 更新，然后你才可以配置你的 Surface 设备的高级安全功能。 如果你从 Windows 更新接收更新，此更新将自动安装。 有关如何将 Windows 配置为使用 Windows 更新自动更新的详细信息，请参阅[如何配置和使用 Windows 中的自动更新](https://support.microsoft.com/kb/306525)。

若要更新 Surface Pro 3 上的 UEFI，你可以下载并安装作为 Surface Pro 3 固件和驱动程序包一部分的 Surface UEFI 更新。 可以从 Microsoft 下载中心上的[Surface Pro 3 页面](https://www.microsoft.com/download/details.aspx?id=38826)获取这些固件和驱动程序包。 你可以在[为 Surface 设备下载最新的固件和驱动程序](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)中了解有关固件和驱动程序包的详细信息。 将以独立的 Windows Installer (.msi) 和存档 (.zip) 格式提供这些固件和驱动程序包。 你可以在[管理 Surface 驱动程序和固件更新](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates)中了解有关这两种格式的详细信息以及如何使用它们更新驱动程序。

## 手动配置其他安全设置


>[!NOTE]
>若要进入 Surface 设备上的固件设置，请先关闭设备电源、长按“提高音量”**** 按钮、按下并释放“电源”**** 按钮，然后在设备开始启动后释放“提高音量”**** 按钮。

在 Surface 设备上安装 v3.11.760.0 UEFI 更新后，一个名为“高级设备安全”**** 的附加 UEFI 菜单将变为可用。 如果你单击此菜单，将显示以下选项：

| 选项         | 描述                                                                                                                                                                          | 可用设置（默认设置以粗体列出） |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| 网络启动   | 启用或禁用从网络启动 Surface 设备的能力（也称为 PXE 启动）。                                                                            | **已启用**、不可启动                   |
| 侧 USB       | 启用或禁用 Surface 设备一侧的 USB 端口。 此外，USB 端口可启用，但不允许启动。                                                | **已启用**、不可启动、已禁用         |
| 插接端口   | 启用或禁用 Surface 扩展坞上的端口。 此外，插接端口可启用，但阻止从扩展坞中的任何 USB 或以太网端口启动。 | **已启用**、不可启动、已禁用         |
| 前置摄像头   | 启用或禁用 Surface 设备前端的摄像头。                                                                                                                   | **已启用**、已禁用                       |
| 后置摄像头    | 启用或禁用 Surface 设备后端的摄像头。                                                                                                                    | **已启用**、已禁用                       |
| 板载音频 | 启用或禁用 Surface 设备上的音频。                                                                                                                                     | **已启用**、已禁用                       |
| microSD        | 启用或禁用 Surface 设备上的 microSD 卡槽。                                                                                                                          | **已启用**、已禁用                       |
| WLAN           | 启用或禁用 Surface 设备中的内置 WLAN 收发器。 这也将禁用蓝牙。                                                                              | **已启用**、已禁用                       |
| 蓝牙      | 启用或禁用 Surface 设备中的内置蓝牙无线收发器。                                                                                                        | **已启用**、已禁用                       |

 

## 自动化其他安全设置


作为一名具有管理权限的 IT 专业人员，你可以通过利用 Microsoft 下载中心中提供的 [Surface Pro 3 固件工具 (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) 来自动化 UEFI 设置的配置。 这些工具将安装可从任何自定义应用程序或脚本调用的 .NET 程序集。

**先决条件**

-   下面的示例脚本利用前面提到的扩展，因此假定工具已安装在正在管理的设备上。
-   这些脚本必须使用管理权限进行运行。
-   必须先调用 Windows PowerShell 命令 [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx)，然后再运行示例脚本（如果未对它们进行数字签名）。

**示例脚本**

> [!NOTE]
> 以下示例脚本中使用的 UEFI 密码将以明文形式提供。 我们强烈建议将脚本保存在受保护的位置中并在受控环境中运行它们。


显示所有可配置选项：

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

设置或更改 UEFI 密码：

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

检查建议的更改的状态：

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

将 UEFI 还原为默认值：

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

状态代码解释

-   00 - 建议的更新成功
-   02 - 其中一个建议的值具有无效的值
-   03 - 有一个无法识别的建议值集
-   0F - 解锁密码与当前设置密码不匹配

 

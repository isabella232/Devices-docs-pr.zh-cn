---
title: 电池限制设置（Surface）
description: 电池限制是一种 UEFI 设置，可更改 Surface 设备电池的充电方式，并可能延长其寿命。
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831720"
---
# 电池限制设置

电池限制选项是一项 UEFI 设置，可更改 Surface 设备电池的充电方式，并可能延长其寿命。 如果设备持续连接到电源，例如设备已集成到展台解决方案中，则建议使用此设置。  

## 电池限制的工作原理

设置电池限制的设备将更改用于对设备电池充电的协议。 启用电池限制后，电池电量将限制为其最大容量的50%。 Windows 中报告的费用级别将反映此限制。 因此，它将显示将电池费用最高达50%，并且不会超出此限制。 如果在设备超过50% 时启用电池限制，电池图标将显示设备已插入但正在放电，直到设备达到其最大收费容量的50%。  

## 支持的设备
电池限制 UEFI 设置内置于最新的 Surface 设备中，包括 Surface Pro 7 和 Surface 笔记本3。 以前的设备需要[SURFACE UEFI 固件更新](manage-surface-driver-and-firmware-updates.md)，可通过 Windows 更新或通过[Surface 支持网站](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)上的 MSI 驱动程序和固件程序包进行更新。 对于每个受支持的设备所需的特定 Surface UEFI 版本，请选中["为必须插入长时间的 surface 设备启用" 电池限制 "](https://support.microsoft.com/help/4464941) 。 

## 在 Surface UEFI 中启用电池限制（Surface Pro 4 及更高版本）

"Surface UEFI 电池限制" 设置可通过启动到 Surface UEFI （打开设备时为**电源 + 音量**）进行配置。 选择 "**启动配置**"，然后在 "**高级选项**" 下，将 "**启用电池限制模式**" 切换为 **"开"**。  

![高级选项的屏幕截图](images/enable-bl.png) 

## 在 Surface Go 和 Surface Go 2 上启用电池限制
图面电池限制设置可通过启动到 Surface UEFI （打开设备时为**电源 + 音量**）进行配置。 选择 "**启动配置**"，然后在 "**展台模式**" 下，向右移动滑块以将电池限制设置为 "**已启用**"。  

![表面上的展台模式电池电量限制的屏幕截图](images/go-batterylimit.png) 

## 在 Surface UEFI 中启用电池限制（Surface Pro 3）

"Surface UEFI 电池限制" 设置可通过启动到 Surface UEFI （打开设备时为**电源 + 音量**）进行配置。 选择 "**展台模式**"，选择 "**电池限制**"，然后选择 "**已启用**"。

![高级选项的屏幕截图](images/enable-bl-sp3.png) 

![高级选项的屏幕截图](images/enable-bl-sp3-2.png) 

## 使用 Surface Enterprise 管理模式（SEMM）或 Surface Pro 3 固件 PowerShell 脚本启用电池限制

还可通过以下方法配置图面 UEFI 电池限额：

- Surface Pro 4 及更高版本 
    - [Microsoft Surface UEFI 配置器](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Surface UEFI 管理器 Powershell 脚本（SEMM_Powershell.zip）在[IT 下载的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)中
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### 使用 Microsoft Surface UEFI 配置器

要配置电池限制模式，请在 SEMM （Surface Pro 4 及更高版本）中的 "**高级设置**" 配置页面上设置**展台覆盖**设置。

![高级设置的屏幕截图](images/semm-bl.png)

### 使用 Surface UEFI 管理器 PowerShell 脚本

电池限制功能通过以下设置进行控制：  

`407 = Battery Profile`

**说明**：电池使用模式的活动管理方案

**默认**：  `0` 

将此设置为 `1` 以启用电池限制。

### 使用 Surface Pro 3 固件工具

电池限制功能通过以下设置进行控制：  

**名称**： BatteryLimitEnable

**说明**： BatteryLimit

**当前值**：  `0` 

**默认值**： `0`

**建议的值**： `0` 

将此设置为 `1` 以启用电池限制。

>[!NOTE]
>若要配置此设置，必须使用[SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)。 


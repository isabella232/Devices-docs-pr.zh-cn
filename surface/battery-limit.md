---
title: 'Surface (的电池) '
description: 电池限制是 UEFI 设置，可更改 Surface 设备电池的充电情况，并延长其使用时间。
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
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271139"
---
# 电池限制设置

电池限制选项是 UEFI 设置，可更改 Surface 设备电池的充电方式并延长其使用时间。 当设备连续连接到电源时（例如，当设备集成到展台解决方案中时）建议使用此设置。  

## 电池限制的工作原理

在"电池限制"上设置设备会更改用于为设备电池充电的协议。 启用电池限制后，电池电量将限制为最大容量的 50%。 Windows 中报告的费用级别将反映此限制。 因此，它将显示电池的充电率最高为 50%，并且不会超出此限制。 如果在设备充电超过 50% 时启用电池限制，电池图标将显示设备已接通电源，但正在等待，直到设备达到最大充电容量的 50%。  

## 支持的设备

电池限制 UEFI 设置内置于最新的 Surface 设备中，包括 Surface Pro 7+、Surface Pro 7 和 Surface Laptop 3。 较早的设备需要 [Surface UEFI](manage-surface-driver-and-firmware-updates.md)固件更新，可通过 Windows 更新或通过 Surface 支持站点上的 MSI 驱动程序和固件 [包获取](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)。 选中 ["为必须](https://support.microsoft.com/help/4464941) 长时间插入的 Surface 设备启用"电池限制"，以针对每个受支持的设备所需的特定 Surface UEFI 版本。 

## 在 Surface UEFI (Surface Pro 4 及更高版本中启用电池) 

Surface UEFI 电池限制设置可通过在打开设备时启动到 Surface UEFI (**Power + Vol Up** 来) 。 选择**启动配置**，然后在"**高级**选项"下，将"**启用电池限制模式"** 切换为 **"打开"。**  

![电池限制高级选项](images/enable-bl.png) 

## 在 Surface Go 和 Surface Go 2 上启用电池限制
Surface 电池限制设置可通过在打开设备时启动到 Surface UEFI (**Power + Vol Up** 进行) 。 选择**启动配置**，然后在展台**模式下**，将滑块向右移动以将电池限制设置为 **"已启用"。**  

![Surface Go 中的展台模式电池限制](images/go-batterylimit.png) 

## 在 Surface UEFI 中启用 Surface Pro 3 (电池) 

Surface UEFI 电池限制设置可通过在打开设备时启动到 Surface UEFI (**Power + Vol Up** 来) 。 选择**展台模式**，选择**电池限制**，**然后选择启用。**

![高级选项的屏幕截图](images/enable-bl-sp3.png) 

![高级选项](images/enable-bl-sp3-2.png) 

## 使用 Surface Enterprise Management Mode (SEMM) Surface Pro 3 固件 PowerShell 脚本启用电池限制

Surface UEFI 电池限制也可通过以下方法进行配置：

- Surface Pro 4 及更高版本 
    - [Microsoft Surface UEFI 配置程序](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Surface UEFI 管理器 Powershell 脚本 (SEMM_Powershell.zip) [适用于 IT 的 Surface Tools 下载](https://www.microsoft.com/download/details.aspx?id=46703)
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### 使用 Microsoft Surface UEFI 配置器

若要配置电池限制模式，请设置**** SEMM Surface **** Pro 4 及更高版本中"高级设置"配置 ("展台覆盖) 。

![高级设置的屏幕截图](images/semm-bl.png)

### 使用 Surface UEFI 管理器 PowerShell 脚本

电池限制功能通过以下设置进行控制：  

`407 = Battery Profile`

**说明**：电池使用模式的活动管理方案

**默认**：  `0` 

设置此选项 `1` 以启用电池限制。

### 使用 Surface Pro 3 固件工具

电池限制功能通过以下设置进行控制：  

**名称**：BatteryLimitEnable

**说明**：BatteryLimit

**当前值**：  `0` 

**默认值：** `0`

**建议的值**： `0` 

设置此选项 `1` 以启用电池限制。

>[!NOTE]
>若要配置此设置，必须使用[SP3_Firmware_Powershell_Scripts.zip。 ](https://www.microsoft.com/download/details.aspx?id=46703) 


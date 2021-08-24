---
title: 'Surface 设备 (电池) '
description: 电池限制是 UEFI 设置，可更改 Surface 设备电池的充电情况，并可能延长其使用时间。
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
ms.openlocfilehash: 52e43a1ac14f89f5671b6fad8fc2e1ef49480470
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911837"
---
# <a name="battery-limit-setting"></a>电池限制设置

电池限制选项是 UEFI 设置，可更改 Surface 设备电池的充电方式，并可能延长其使用时间。 当设备持续连接到电源时（例如，当设备集成到展台解决方案中时）建议使用此设置。  

## <a name="how-battery-limit-works"></a>电池限制的工作原理

将设备设置为电池限制将更改用于为设备电池充电的协议。 启用电池限制后，电池电量将限制为最大容量的 50%。 报告的费用级别Windows反映此限制。 因此，它将显示电池的充电率高达 50%，并且不会超出此限制。 如果在设备超过 50% 的电量时启用电池限制，电池图标将显示设备已接通电源但正在充电，直到设备达到最大充电容量的 50%。  

## <a name="supported-devices"></a>支持的设备

电池限制 UEFI 设置内置于最新的 Surface 设备中，Surface Pro 7+、Surface Pro 7 和 Surface Laptop 3。 早期设备需要[Surface UEFI](manage-surface-driver-and-firmware-updates.md)固件更新，可通过 Windows 更新或通过 Surface 支持站点上的 MSI 驱动程序和固件[包获取](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)。 选中 ["为](https://support.microsoft.com/help/4464941) 每台受支持的设备所需的特定 Surface UEFI 版本必须长时间插入的 Surface 设备启用"电池限制"。

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-4-and-later"></a>在 Surface UEFI (Surface Pro 4及更高版本中启用电池) 

Surface UEFI 电池限制设置可通过在打开设备时启动到 Surface UEFI (**Power + Vol Up** 进行) 。 选择**启动配置**，然后在"高级选项"**下**，将 **"启用电池限制模式"切换为****"打开"。**  

![电池限制 高级选项。](images/enable-bl.png)

## <a name="enabling-battery-limit-on-surface-go-and-surface-go-2"></a>在 Surface Go 和 Surface Go 2 上启用电池限制

Surface 电池限制设置可通过在打开设备时启动到 Surface UEFI (**Power + Vol Up** 进行) 。 选择**启动配置**，然后在展台模式下****，将滑块向右移动以将电池限制设置为**已启用**。  

![Surface Go 中的展台模式电池限制。](images/go-batterylimit.png)

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-3"></a>在 Surface UEFI 中启用电池 (Surface Pro 3) 

Surface UEFI 电池限制设置可通过在打开设备时启动到 Surface UEFI (**Power + Vol Up** 进行) 。 选择**展台模式**，选择**电池限制**，**然后选择启用。**

![高级选项的屏幕截图。](images/enable-bl-sp3.png)

![“高级选项”。](images/enable-bl-sp3-2.png)

## <a name="enabling-battery-limit-using-surface-enterprise-management-mode-semm-or-surface-pro-3-firmware-powershell-scripts"></a>使用 Surface Enterprise 管理模式启用电池 (SEMM) 或 Surface Pro 3 固件 PowerShell 脚本

Surface UEFI 电池限制也可通过以下方法进行配置：

- Surface Pro 4及更高版本
  - [Microsoft Surface UEFI 配置器](surface-enterprise-management-mode.md)  
    - Surface UEFI 管理器 Powershell 脚本 (SEMM_Powershell.zip) [适用于 IT 的 Surface 工具下载](https://www.microsoft.com/download/details.aspx?id=46703)

### <a name="using-microsoft-surface-uefi-configurator"></a>使用 Microsoft Surface UEFI 配置器

若要配置电池限制模式，请设置**** SEMM 设置及**** 更高版本中"高级设备配置" (Surface Pro 4"展台) 。

![高级设置的屏幕截图。](images/semm-bl.png)

### <a name="using-surface-uefi-manager-powershell-scripts"></a>使用 Surface UEFI 管理器 PowerShell 脚本

电池限制功能通过以下设置进行控制：  

`407 = Battery Profile`

**说明**：电池使用模式的活动管理方案

**默认**：  `0`

将此选项设置为 `1` 启用电池限制。

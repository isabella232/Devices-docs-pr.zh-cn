---
title: 优化 Surface 设备上视频会议
description: 此页面提供在 Surface 设备上Microsoft Teams会议解决方案和其他视频会议解决方案的最佳实践
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/10/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
ms.openlocfilehash: dd72bf940309fe9f3d7b4bf334a94a557cffe016
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338600"
---
# <a name="optimize-video-conferencing-on-surface-devices"></a>优化 Surface 设备上视频会议

Surface 设备利用移动设备能耗的最新进展，提供跨工作负载优化的简化体验。 对于大多数工作负载，这将提供出色的体验。 对于使用 Microsoft Teams或其他视频会议应用程序的一些工作负载，您应该遵循这些建议以确保获得最佳体验。

## <a name="surface-drivers-and-firmware"></a>Surface 驱动程序和固件

Microsoft 定期发布 Surface 设备的更新，并发布了多个面向视频会议工作负载的 Surface 更新，包括：

- 系统性能改进
- 相机驱动程序中的电源消耗改进
- 图形驱动程序更新
- 电源设置优化

### <a name="get-updates-to-all-devices"></a>获取所有设备的更新

确保你的组织有一个过程，你的设备可以接收这些更新。 如果你使用的是适用于Windows更新Windows[更新](/windows/deployment/update/waas-manage-updates-wufb)，则你已在发布最新 Surface 更新时收到它们。 使用 surface 更新Windows检查更新，并验证已安装最新的 Surface 更新。 若要了解更多，请参阅：

- [Surface 更新历史记录](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)
- [安装 Surface 和 Windows 更新](https://www.microsoft.com/surface/support/performance-and-maintenance/install-software-updates-for-surface?)

如果你正在使用其他选项来安装 Surface 驱动程序和固件更新，你将需要使用发布的 MSI 文件手动安装最新的 Surface 更新，或者使用 Configuration Manager 安装更新。 若要了解更多，请参阅：

- [下载 Surface 的驱动程序和固件](https://support.microsoft.com/help/4023482)
- [管理和部署 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)
- [如何在 Configuration Manager 中管理 Surface 驱动程序更新](https://support.microsoft.com/help/4098906)

### <a name="graphics-driver-updates-for-microsoft-teams"></a>适用于应用的图形驱动程序Microsoft Teams

具有第 10 代和 11 代 Intel 处理器的较新的 Surface 设备型号已收到图形驱动程序更新，这些更新可帮助处理视频会议工作负载。 若要启用这些改进，请确保安装以下内容：

- Microsoft Teams**版本 1.4.00.22472** 或更高版本。
- Intel 图形驱动程序 **27.20.100.9621** 或更高版本。

### <a name="power-settings-optimizations"></a>电源设置优化

Surface 设备可以通过更改 Windows 性能电源滑块的位置来调整与性能相关的电源Windows 10，也称为Windows 11。

某些 Surface 设备已收到更新，其中包括基于电源滑块位置或电源模式对视频会议工作负载的电源设置优化。 但是，由于Windows 10和Windows 11对视频会议工作负载使用建议电源滑块**** 位置和电源模式位置，因此你需要调整电源滑块以启用这些优化：

1. 连接交流电源 (使用电池电源时，不会运行) 。  
2. 调整电源滑块或电源模式位置以使用 **更好的性能** 或 **最佳性能。**

## <a name="learn-more"></a>了解详细信息

- [Surface 设备电源设置的最佳做法](maintain-optimal-power-settings-on-surface-devices.md)
- [最大程度地延长 Surface 电池使用时间](https://support.microsoft.com/surface/maximize-your-surface-battery-life-45479867-a7fa-33dd-fc4d-6762e9b3b11a)

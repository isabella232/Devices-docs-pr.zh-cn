---
title: LAN 唤醒 Surface 扩展坞 2
description: Surface Dock 2 为 LAN 上的唤醒和 WOL (最佳) 使管理员能够远程唤醒设备并自动执行管理任务。
keywords: 更新， 部署， 驱动程序， wol， lan 上唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 6/03/2021
ms.openlocfilehash: 74b36b60cb58ecb9042b73b8cdba7271d0af8c80
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614043"
---
# <a name="wake-on-lan-with-surface-dock-2"></a>LAN 唤醒 Surface 扩展坞 2

若要使设备完全保持最新，IT 管理员需要能够在设备不使用时（通常是夜间维护时段）管理设备。 Surface Dock 2 为 LAN (WOL 上的唤醒提供最佳支持) 使管理员能够远程唤醒设备，并自动使用 Microsoft Endpoint Manager 或其他第三方解决方案执行管理任务。

## <a name="requirements"></a>要求

设备必须与 Surface 扩展坞 2 建立有线连接，并持续连接到交流电源。

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a>支持的 Surface 设备

- Surface Laptop 4 (Intel 处理器) 
- Surface Laptop 4 (AMD 处理器) 
- Surface Laptop 3 (Intel 处理器) 
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop转到
- Surface Book 3

Surface Dock 2 为以下电源状态中的设备提供 WOL 支持：

- 连接待机
- 休眠 (S4 电源状态) 
- 休眠 (S5"软关闭"电源状态) 

若要详细了解电源状态，请参阅 [系统电源状态](/windows/win32/power/system-power-states)。

## <a name="how-it-works"></a>工作原理

不使用时，Surface 设备将进入空闲的低电源状态，称为现代待机或连接待机。 IT 管理员可以使用唤醒请求远程触发设备 (包含目标 Surface 设备的媒体访问控制 (MAC) 地址的神奇数据包) 。 许多管理解决方案（Microsoft Endpoint Configuration Manager第三方Microsoft Store应用）都提供对 WOL 的内置支持。

若要在没有 Surface 扩展坞 2 的设备上启用 WOL，请参阅 [Surface 设备的 LAN 唤醒](wake-on-lan-for-surface-devices.md)。

## <a name="learn-more"></a>了解详细信息

- [Surface Dock 2](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [Surface 设备的 LAN 唤醒](wake-on-lan-for-surface-devices.md)
- [系统电源状态](/windows/win32/power/system-power-states)
- [在 LAN 上配置唤醒 - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)

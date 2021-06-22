---
title: Surface 设备的 LAN 唤醒
description: 了解如何使用 LAN 唤醒远程唤醒设备以自动执行管理任务。
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
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613793"
---
# <a name="wake-on-lan-for-surface-devices"></a>Surface 设备的 LAN 唤醒

若要使设备完全保持最新，IT 管理员需要能够在设备不使用时（通常是夜间维护时段）管理设备。 LAN 唤醒 (WOL) 使管理员能够远程唤醒设备，并自动使用 Microsoft Endpoint Manager 或第三方解决方案执行管理任务。

## <a name="requirements"></a>要求

设备必须连接到交流电源，并且具有与以下兼容的以太网适配器之一的有线连接：

- Surface USB 3.0 千兆位以太网适配器
- Surface 以太网适配器
- Surface USB-C 到以太网和 USB 适配器
- Microsoft USB-C 旅行适配器中心
- Surface 扩展坞
- Surface Dock 2

> [!NOTE]
> Surface Dock 2 提供了对 LAN 唤醒的最佳支持，无需任何其他 IT 配置。 若要了解更多信息，请参阅 [Surface Dock 2 的 LAN 唤醒](wake-on-lan-surface-dock2.md)

## <a name="how-it-works"></a>工作原理

不使用时，Surface 设备将进入空闲的低电源状态，称为现代待机或连接待机。 IT 管理员可以使用唤醒请求远程触发设备 (包含目标 Surface 设备的媒体访问控制 (MAC) 地址的神奇数据包) 。 许多管理解决方案（Microsoft Endpoint Configuration Manager第三方Microsoft Store应用）都提供对 WOL 的内置支持。 若要了解有关使用 Endpoint Configuration Manager 唤醒设备的信息，请参阅[Configure Wake on LAN - Configuration Manager。](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)

对 LAN 唤醒的支持因睡眠状态而异：连接待机或休眠 (S4 电源状态) 。

## <a name="connected-standby"></a>连接待机

默认情况下，Windows 10待机时支持 Surface 设备在 LAN 上唤醒。

### <a name="supported-surface-devices---connected-standby"></a>受支持的 Surface 设备 - 连接待机

- Surface Laptop 4 (Intel 处理器) 
- Surface Laptop 3 (Intel 处理器) 
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop转到
- Surface Book 3

## <a name="hibernation"></a>休眠

若要将设备从休眠状态中唤醒，需要为连接到 Surface Dock 2) 的设备启用[Surface Enterprise](surface-enterprise-management-mode.md)管理模式 (SEMM)  (UEFI 策略设置。

### <a name="supported-surface-devices---hibernation"></a>受支持的 Surface 设备 - 休眠

- Surface Laptop 4 (Intel 处理器) 
- Surface Laptop 3 (Intel 处理器) 
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop转到
- Surface Book 3

### <a name="to-enable-wake-on-lan-uefi-setting"></a>启用 LAN UEFI 唤醒设置

若要启用 LAN UEFI 唤醒设置，你需要将目标设备注册到 SEMM，创建配置包，然后应用该包到设备。 有关详细信息，请参阅：

- [Surface 企业管理模式](surface-enterprise-management-mode.md)
- [使用 SEMM 注册并配置 Surface 设备](enroll-and-configure-surface-devices-with-semm.md)

1. 下载并安装 [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703)。
2. 选择 **"启动**  >  **配置包**  >  **创建**  > **+ 证书保护"。**
3. 转到高级**设置，** 将 LAN**上的唤醒切换到****开**。
4. 将程序包应用到目标设备。

    > [!div class="mx-imgBorder"]
    > ![启用 LAN UEFI 策略设置唤醒](images/wol-uefi.png)

## <a name="learn-more"></a>了解详细信息

- [Surface 扩展坞 2 的 LAN 唤醒](wake-on-lan-surface-dock2.md)
- [Microsoft Surface USB-C 到以太网和 USB 适配器](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [Surface USB 3.0 千兆位以太网适配器](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)

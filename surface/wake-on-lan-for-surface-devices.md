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
ms.date: 3/19/2021
ms.openlocfilehash: 9c3302616de97cf60b7d750948fed653456a7cba
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442886"
---
# <a name="wake-on-lan-for-surface-devices"></a>Surface 设备的 LAN 唤醒

使用 Surface 以太网适配器连接到有线网络的 Surface 设备可以利用连接待机LAN 唤醒 (WOL) 连接。 借助 WOL，你可以远程唤醒设备，并自动使用管理解决方案（如 Microsoft Endpoint Manager/Microsoft Intune）执行管理任务。

## <a name="wol-supported-devices"></a>支持 WOL 的设备

- Surface 以太网适配器
- Surface USB-C 到以太网和 USB 适配器
- Surface Dock 2
- Surface Pro 6 及更高版本
- Surface Book (代) 
- Surface Laptop (所有代) 
- Surface Go (代) 
- Surface Studio 2 (请参阅附录) 


## <a name="using-surface-wol"></a>使用 Surface WOL

IT 管理员可以使用 LAN 请求唤醒 (包含目标计算机的 MAC 地址的) 数据包来触发设备。 若要发送神奇数据包，然后使用 WOL 唤醒设备，必须知道目标设备和以太网适配器的 MAC 地址。 由于神奇数据包不使用 IP 网络协议，因此不可能使用设备的 IP 地址或 DNS 名称。

许多管理解决方案（如 Microsoft Endpoint Configuration Manager 和第三方 Microsoft Store 应用）都提供对 WOL 的内置支持。 请注意，设备需要处于连接待机模式 (睡眠) 并连接到交流电源。 若要了解有关使用 Endpoint Configuration Manager 唤醒设备的信息，请参阅[Configure Wake on LAN - Configuration Manager。](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan)


### <a name="to-check-wol-is-enabled-on-your-device"></a>检查设备上是否已启用 WOL

1. 在已连接以太网的设备上，选择网络适配器，然后选择"属性 **"。**

   > [!div class="mx-imgBorder"]
   > ![Surface 以太网适配器](images/surface-ethernet.png)

2. 选择 **"配置**  >  **高级"。**
3. 滚动到 **"新式待机 WoL 神奇数据包** "，并确保 **选中"** 已启用"。

     ![检查设备上是否已启用 WOL](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a>附录：Surface Studio 2

若要在 Surface Studio 2 上启用 WOL，请使用以下过程。

1. 创建以下注册表项：

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. 运行以下命令

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a>了解详细信息

- [Microsoft Surface USB-C 到以太网和 USB 适配器](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [Surface USB 3.0 千兆位以太网适配器](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)

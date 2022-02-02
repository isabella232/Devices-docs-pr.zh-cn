---
title: Surface 设备的 LAN 唤醒
description: 运行 Windows 10 版本 1607 或更高版本并使用 Surface 以太网适配器连接到有线网络的 Surface 设备能够从现代待机LAN 唤醒 (WOL) WOL。
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
ms.date: 11/30/2021
ms.openlocfilehash: eed1cbedea2a39207846301fa6b4f6c2b2f6dd56
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "12337905"
---
# <a name="wake-on-lan-for-surface-devices"></a>Surface 设备的 LAN 唤醒 

运行 1607 Windows 10更高版本的 Surface 设备能够从现代待机LAN 唤醒 (W) OL (也称为连接待机) 。 借助 WOL，IT 管理员可以远程唤醒设备，并自动使用 Microsoft Endpoint Manager 或第三方解决方案执行管理任务。

>[!NOTE]
>若要支持 WOL，Surface 设备必须插入交流电源并使用连接到有线网络的 Surface 以太网适配器。

## <a name="supported-devices"></a>支持的设备

支持 WOL 的以太网适配器：

- Surface USB 3.0 千兆位以太网适配器 
- Surface 以太网适配器
- Surface USB-C 到以太网和 USB 适配器
- Surface 扩展坞
- Surface 扩展坞 2
- 适用于 Surface Pro 3 的 Surface 扩展坞

支持 WOL 的 Surface 设备：

- Surface 3
- Surface Pro 3
- Surface Pro 4
- Surface Pro (第五代) 
- Surface Pro (LTE 高级) 第五代
- Surface Book (所有代) 
- Surface Laptop (所有代) 
- Surface Pro 6
- Surface Book 2
- Surface Go (代) 
- Surface Studio 2 (请参阅Surface Studio 2 说明) 
- Surface Pro 7
- Surface Pro 7+
- Surface Pro 8
- Surface Laptop Go
- Surface Laptop Studio


## <a name="using-wol"></a>使用 WOL 

不使用时，Surface 设备会进入空闲的低电源状态，称为现代待机或连接待机。 IT 管理员可以使用唤醒请求或神奇数据包 (远程触发设备) 包含目标 Surface 设备的媒体访问控制 (MAC) 地址。 目标网络接口卡 (NIC) 在启动设备之前将 MAC 地址与其自身的地址进行比较。 如果神奇数据包唤醒请求中的 MAC 地址与目标 NIC 上的 MAC 地址不匹配，则 NIC 不会唤醒设备。 若要了解更多信息，请参阅 [唤醒源文档](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## <a name="modern-standby"></a>现代待机

当用户使系统进入睡眠状态或设备根据用户设置的电源设置Windows进入睡眠状态时，将启动现代待机。 例如，用户按下电源按钮、关闭灯盖，或者从电源按钮中选择睡眠Windows "开始"菜单。 默认情况下，WOL 适用于在版本 1607 或更高版本Windows 10待机模式下的 Surface 设备。 不需要其他 IT 配置，第 2 Surface Studio除外。

## <a name="surface-studio-2-instructions"></a>Surface Studio 2 条说明

若要在 Surface Studio 2 上启用 WOL，您必须使用以下过程

1. 打开"** ** 注册表编辑器 (**StartSearch** > **** > regedit.exe) 并创建以下注册表项：

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   ```

2. 运行以下命令

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

> [!NOTE]
> 例如，如果在 Surface Studio 2 (上升级 Windows 10 版本，从 Windows 10 20H2 升级到 21H1) ，则需要再次按照这些说明启用 WOL。


### <a name="to-wake-from-hibernation-s4-or-shutdown-s5"></a>若要从休眠状态 (S4) 或 (S5)  

- 对于连接到 Surface Dock 2 的设备，请参阅 [Surface Dock 2 的 LAN 唤醒](wake-on-lan-surface-dock2.md)

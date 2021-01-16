---
title: 'LAN 唤醒 Surface 设备 (Surface) '
description: 了解如何使用 LAN 唤醒 远程唤醒设备以执行管理或维护任务，或自动启用管理解决方案 ，即使设备已断电。
keywords: 更新， 部署， 驱动程序， wol， lan 唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271119"
---
# Surface 设备的 LAN 唤醒

运行 Windows 10 版本 1607 (也称为 Windows 10 周年更新) 或更高版本并使用 Surface 以太网适配器连接到有线网络的 Surface 设备能够从连接待机状态LAN 唤醒 (WOL) 。 使用 WOL，你可以远程唤醒设备以执行管理或维护任务，或启用管理解决方案 (如 Microsoft Endpoint Configuration Manager) 自动。 例如，你可以将应用程序部署到与 Surface 扩展坞或 Surface Pro 3 扩展坞一起停靠的 Surface 设备，通过使用 Microsoft Endpoint Configuration Manager 在夜间窗口（当办公室为空时）使用 Microsoft Endpoint Configuration Manager。

>[!NOTE]
>Surface 设备必须连接到交流电源，并且处于连接待机模式 (睡眠) WOL。 在休眠或关机的设备中无法使用 WOL。

## 支持的设备

WOL 支持以下设备：

* Surface 以太网适配器
* Surface USB-C 到以太网和 USB 适配器
* Surface 扩展坞
* Surface Pro 3 的 Surface 扩展坞
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface Pro (第五代) 
* Surface Pro (第五代) LTE Advanced
* Surface Book
* Surface Laptop (第一代) 
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* 带有 LTE Advanced 的 Surface Go
* Surface Studio 2 (请参阅下面的 Surface Studio 2) 
* Surface Pro 7
* Surface Laptop 3
* Surface Laptop Go
* Surface Pro 7+

## WOL 驱动程序

若要在 Surface 设备上启用 WOL 支持，需要 Surface 以太网适配器的特定驱动程序。 此驱动程序不包含在 Surface 设备的标准驱动程序和固件包中 ， 你必须单独下载并安装它。 你可以从 Microsoft 下载中心的 Surface Tools (SurfaceWOL.msi) [下载 Surface](https://www.microsoft.com/download/details.aspx?id=46703) WOL 驱动程序。

可以在 Surface 设备上运行此 Microsoft Windows Installer (.msi) 文件以安装 Surface WOL 驱动程序，或者可以使用应用程序部署解决方案（如 Microsoft Endpoint Configuration Manager）将其分发到 Surface 设备。 若要在部署过程中包括 Surface WOL 驱动程序，可以在部署过程中将 .msi 文件安装为应用程序。 还可以提取 Surface WOL 驱动程序文件，以将其包括在部署过程中。 例如，你可以将它们包括在 Microsoft Deployment Toolkit (MDT) 共享中。 你可以阅读有关 Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit。](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)

> [!NOTE]
> 在安装 SurfaceWOL.msi 时，以下注册表项设置为值 1，这便于识别已安装 WOL 驱动程序的系统。 如果选择在部署过程中单独提取和安装这些驱动程序，将不会配置此注册表项，并且必须手动或使用脚本进行配置。
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

若要提取 SurfaceWOL.msi 的内容，请使用 MSIExec 管理安装选项 (**/a**) ，如以下示例所示，将内容提取到 C：\WOL\ 文件夹：

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Surface Studio 2 说明

若要在 Surface Studio 2 上启用 WOL，你必须使用以下过程

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

## 使用 Surface WOL

Surface WOL 驱动程序符合 WOL 标准，即设备由称为神奇数据包的特殊网络通信所驱动。 神奇数据包包含 6 个字节（255 (或 FF，以十六进制) 后跟目标计算机的 MAC 地址的 16 个重复。 可以在 Wikipedia 上阅读有关神奇数据包和 WOL 标准 [的内容](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)。

>[!NOTE]
>若要发送一个神奇数据包，然后使用 WOL 唤醒设备，必须知道目标设备和以太网适配器的 MAC 地址。 由于神奇数据包不使用 IP 网络协议，因此不可能使用设备的 IP 地址或 DNS 名称。

许多管理解决方案（如 Configuration Manager）都提供对 WOL 的内置支持。 还有许多解决方案，包括 Microsoft Store 应用、PowerShell 模块、第三方应用程序和第三方管理解决方案，它们允许你发送神奇数据包来唤醒设备。 例如，可以从 [TechNet 脚本LAN 唤醒 PowerShell](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) 模块。 

>[!NOTE]
>在设备被一个神奇数据包丢弃后，如果应用程序未主动阻止系统睡眠，或者 AllowSystemRequiredPowerRequests 注册表项未配置为 1，则设备将返回到睡眠状态，这将允许应用程序阻止睡眠。 有关此注册表项详细信息，请参阅本文的 [WOL](#wol-driver) 驱动程序部分。

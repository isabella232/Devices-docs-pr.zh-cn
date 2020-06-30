---
title: 用于 Surface 设备（Surface）的 LAN 唤醒
description: 了解如何使用 LAN 唤醒远程唤醒设备以执行管理或维护任务，或自动启用管理解决方案-即使设备已断电。
keywords: 更新、部署、驱动程序、wol、lan 唤醒
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
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830990"
---
# Surface 设备的 LAN 唤醒

运行 Windows 10 版本1607（也称为 Windows 10 周年更新）或更高版本的 surface 设备，并使用 Surface 以太网适配器连接到有线网络，可从连接备用设备上从 LAN （WOL）唤醒。 使用 WOL，您可以远程唤醒设备以执行管理或维护任务，或自动启用管理解决方案（如 Microsoft 终结点配置管理器）。 例如，当 office 为空时，你可以使用 Microsoft 终结点配置管理器将应用程序部署到与 Surface Dock 或 Surface Pro 3 扩展坞一起停靠的 Surface 设备。

>[!NOTE]
>Surface 设备必须连接到交流电源和连接待机（睡眠）才能支持 WOL。 在休眠或关闭电源的设备中不能进行 WOL。

## 支持的设备

WOL 支持以下设备：

* Surface 以太网适配器
* Surface USB-C 至以太网和 USB 适配器
* Surface 扩展坞
* Surface Pro 的 surface 插接站 Pro 3
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface Pro （第五代）
* 具有 LTE 高级版的 Surface Pro （第5代）
* Surface Book
* Surface 笔记本电脑（第1代）
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* 带有 LTE Advanced 的 Surface Go
* Surface Studio 2 （请参阅下面的 Surface Studio 2 说明）
* Surface Pro 7
* Surface 笔记本电脑3

## WOL 驱动程序

要在 Surface 设备上启用 WOL 支持，需要使用 Surface 以太网适配器的特定驱动程序。 此驱动程序未包含在 Surface 设备的标准驱动程序和固件包中-必须单独下载并安装。 您可以从 Microsoft 下载中心的 " [Surface Tools FOR IT](https://www.microsoft.com/download/details.aspx?id=46703) " 页面下载 surface WOL 驱动程序（SurfaceWOL.msi）。

你可以在 Surface 设备上运行此 Microsoft Windows Installer （.msi）文件以安装 Surface WOL 驱动程序，也可以使用应用程序部署解决方案（如 Microsoft 终结点配置管理器）将其分发到 Surface 设备。 若要在部署期间包括 Surface WOL 驱动程序，你可以在部署过程中将 .msi 文件作为应用程序进行安装。 你还可以提取 Surface WOL 驱动程序文件以将它们包含在部署过程中。 例如，你可以将它们包含在 Microsoft 部署工具包（MDT）部署共享中。 在[将 Windows 10 部署到 surface 设备（包含 Microsoft 部署工具包](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)）时，你可以通过 MDT 阅读有关 surface 部署的详细信息。

> [!NOTE]
> 在 SurfaceWOL.msi 安装期间，将以下注册表项设置为值1，这样就可以轻松地识别已安装 WOL 驱动程序的系统。 如果你选择在部署期间单独提取和安装这些驱动程序，则不会配置此注册表项，并且必须手动配置或使用脚本进行配置。
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

若要提取 SurfaceWOL.msi 的内容，请使用 MSIExec 管理员安装选项（**/a**），如以下示例所示，将内容提取到 C:\WOL\ 文件夹：

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Surface Studio 2 说明

若要在 Surface Studio 2 上启用 WOL，必须使用以下过程

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

Surface WOL 驱动程序符合 WOL 标准，由此设备通过称为幻数据包的特殊网络通信 woken。 幻数据包由255的6个字节（或十六进制的 FF）组成，后跟目标计算机的 MAC 地址的16个重复项。 你可以在[维基百科](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)上阅读有关幻数据包和 WOL 标准的详细信息。

>[!NOTE]
>若要通过使用 WOL 发送幻数据包并唤醒设备，您必须知道目标设备和以太网适配器的 MAC 地址。 由于幻数据包不使用 IP 网络协议，因此不能使用设备的 IP 地址或 DNS 名称。

许多管理解决方案（如配置管理器）提供对 WOL 的内置支持。 还有许多解决方案，包括 Microsoft Store 应用、PowerShell 模块、第三方应用程序和第三方管理解决方案，这些解决方案允许你发送幻数据包以唤醒设备。 例如，您可以使用 TechNet 脚本中心的[LAN 上的唤醒模块](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4)。 

>[!NOTE]
>使用幻数据包 woken 设备后，如果应用程序未在系统上主动阻止睡眠，或者 AllowSystemRequiredPowerRequests 注册表项未配置为1，则设备将返回睡眠状态，从而允许应用程序阻止睡眠。 有关此注册表项的详细信息，请参阅本文的[WOL 驱动程序](#wol-driver)部分。

---
title: Surface Hub 上的 Miracast 疑难解答
description: 了解如何解决 Surface Hub 上的 Miracast 问题。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 96c7c42fe0176f275a8657165d88bf447e57772b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832190"
---
# Surface Hub 上的 Miracast 疑难解答

Surface Hub 通过 Miracast 协议支持无线投影。 目前可用的大多数无线监视器和适配器都使用 Miracast 的原始实现方式。 Surface Hub 使用稍微不同的 Miracast 版本，此版本称为 **Miracast 自治组所有者 (AGO)**。 无线投影到 Surface Hub 失败时常见故障排除步骤是测试投影到另一个无线监视器或适配器。 然而，在大多数情况下，这些设备不使用 Miracast AGO，并且不使用 Surface Hub 的处理方式来处理无线投影。

在传统的 Miracast 中，投影设备将连接由支持 Miracast 的监视器设置的接入点，然后此监视器将使用投影设备的网络通道将流量发送回投影设备。 Miracast AGO 是一个两步连接过程：

- 第一步是使用 2.4GHz 的带宽进行初始连接。 
- 在初次握手之后，投影设备使用监视器上的无线通道设置将流量发送到监视器。 如果 Surface Hub 连接到 WLAN 网络（接入点），则它将使用已连接网络所使用的相同通道，否则将使用“设置”中的 Miracast 通道。

Surface Hub 的 Miracast 通常存在以下两种类型的问题：[连接](#connect-issues)和[性能](#performance-issues)。 在任何一种情况下，最好在 Surface Hub 的位置获取无线网络活动的一般图片。 如果运行网络扫描工具，则将向你显示环境中可用的网络和通道使用情况。

## 连接问题

确保在 Surface Hub 上的“设置”中启用了 WLAN 和 Miracast。 

如果你运行了网络扫描，则应该会看到列为接入点的 Surface Hub Miracast。 如果在扫描中显示 Surface Hub 的 Miracast 网络，但不能将其视为可用设备，则可以尝试调整 Surface Hub 使用的 Miracast 通道。 

当 Surface Hub 连接到 WLAN 网络时，它将对其 Miracast 接入点使用 WLAN 接入点所使用的相同通道设置。 为了进行故障排除，请从任何 WLAN 网络中断开 Surface Hub（但保持启用 WLAN），以便你可以控制用于 Miracast 的通道。 你可以在“设置”中手动选择 Miracast 通道。 每次更改后，你将需要重启 Surface Hub。 一般来说，你将希望使用网络扫描中所显示的利用率不高的通道。

连接问题也可能是连接设备问题所造成的。 如果投影设备要运行 Windows，则应该运行 Windows 8.1 或更高版本以获得全面的 Miracast 支持。 同样，为了进行排除故障，请从任何 WLAN 网络中断开投影设备。 这将消除接入点通道与 Surface Hub 上设置的 Miracast 通道之间的任何通道切换。 此外，某些组策略和防火墙设置可能与 WLAN 网络相关联。

### 检查驱动程序

确保在投影设备上安装最新的驱动程序和更新也是一个好主意。 在设备管理器中，打开 WLAN 适配器和视频适配器，并检查是否有更新的驱动程序版本。 如果 Surface Pro 3 和 Surface Pro 4 使用的是较旧的 WLAN 驱动程序，则强烈建议对它们使用[修补程序 3120232](https://support.microsoft.com/help/3120232/poor-wireless-performance-on-5-ghz-connections-on-surface-pro-3-and-surface-3)。 

### 检查 Miracast 支持

接下来，确保设备支持 Miracast。 

1. 按 Windows 键 + R 并键入 `dxdiag`。 
2. 单击 "保存所有信息"。 
3. 打开保存的 dxdiag.txt 并查找 **Miracast**。 它应该显示 **Available, with HDCP**。 
    
### 检查防火墙
    
Windows 防火墙可能会阻止 Miracast 流量。 最简单的测试是禁用防火墙并测试投影。 如果禁用防火墙后 Miracast 正常工作，则为以下项添加例外

    C:\Windows\System32\WUDFHost.exe
    Allow In/Out connections for TCP and UDP, Ports: All.

### 检查组策略设置

在加入域的设备上，组策略也可能会阻止 Miracast。 

1. 使用 Windows 键 + R 并键入 `rsop.msc` 来执行**策略的结果集**管理单元。 这将显示应用于电脑的当前策略。 
2. 查看**计算机配置** > **Windows 设置** > **安全设置** > **无线网络(IEEE 802.11)策略**。 那里应该有无线策略的设置。 
3. 双击无线策略的设置，随即将出现一个对话框。 
4. 打开**网络权限**选项卡，并选择**允许所有人创建所有用户配置文件**。

### 检查事件日志

最后一项检查是检查事件日志。 Miracast 事件将记录到 **Wlanautoconfig** 中。 这适用于 Surface Hub 和投影设备。 如果您导出 Surface Hub 日志，则可以在**WindowsEventLog**文件夹中查看 surface Hub 的 Wlanautoconfig。 事件日志中的错误可以提供关于连接失败位置的一些附加详细信息。

## 性能问题

连接无线投影后，可能会遇到导致延迟的性能问题。 这通常是整体通道饱和或导致通道切换的情况所造成的。 

对于通道饱和，请参阅网络扫描，并尝试使用流量较少的通道。

当 WLAN 适配器需要向多个通道发送流量时，会导致通道切换。 某些通道支持动态频率选择 (DFS)。 DFS 用于通道 49 至 148。 连接到 DFS 通道后，某些 WLAN 驱动程序将表现出性能不佳。 如果在连接到 DFS 通道后发现 Miracast 性能不佳，请尝试利用非 DFS 通道进行投影。 Surface Hub 和投影设备都应该使用非 DFS 通道。

如果 Surface Hub 和投影设备都已连接到 WLAN，但将不同接入点与不同通道配合使用，那么这将在连接 Miracast 时强制 Surface Hub 和投影设备进行通道切换。 这将导致无线投影性能差，并且 WLAN 网络性能差。 通道切换将影响所有无线流量的性能，而不仅仅是无线投影。 

如果投影设备连接到 WLAN 网络时使用的通道不同于 Surface Hub 对 Miracast 所使用的通道，则也将发生通道切换。 因此，最佳做法是将 Surface Hub 的 Miracast 通道设置为与最常使用的访问点相同的信道。 

如果环境中存在多个 WLAN 网络或接入点，则无法避免某些通道切换。 通过确保所有 WLAN 驱动程序是最新版本，可以最好地解决此问题。

##  <a name="contact-support"></a>联系支持人员

如果有疑问或需要帮助，您可以[创建支持请求](https://support.microsoft.com/supportforbusiness/productselection)。

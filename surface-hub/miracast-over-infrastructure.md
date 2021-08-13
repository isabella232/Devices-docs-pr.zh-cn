---
title: 现有无线网络或 LAN 上的 Miracast
description: Windows 10 允许你通过本地网络发送 Miracast 流。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/24/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 26cfffe74c64c786e11dd573b01ad0c025bfc4b0
ms.sourcegitcommit: 21fcd329a7b0c82c69e2a65c423d47c5b23b4e7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "11883009"
---
# <a name="miracast-over-infrastructure"></a>Miracast基础结构

在 Windows 10 版本 1703 上，Microsoft 的功能经过扩展，可以通过本地网络而不是直接无线链接发送 Miracast 流。 此功能基于[基础结构上的 Miracast 连接建立协议 (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx)。

基础结构上的 Miracast 具有以下多项优势：

- Windows 可以自动检测通过此路径发送视频流的合适时间。
- 仅当通过以太网或安全的 WLAN 网络进行连接时，Windows 才将选择此路径。
- 用户无需更改其与 Miracast 接收器的连接方式。 他们使用用于标准 Miracast 连接的相同 UX。
- 无需更改当前无线驱动程序或电脑硬件。
- 它非常适用于未针对 WLAN Direct 上的 Miracast 进行优化的旧版无线硬件。
- 它利用了现有连接，这既缩短了连接时间，也提供了非常稳定的流。


## <a name="how-it-works"></a>工作原理

用户尝试像以前Miracast一样Wi-Fi客户端接收器。 填充 Miracast 接收器列表时，Windows 10 将确认接收器是否能够支持通过基础结构进行连接。 当用户选择 Miracast 接收器时，Windows 10 将尝试通过标准 DNS 以及多播 DNS (mDNS) 解析设备的主机名。 如果名称无法通过任何一种 DNS 方法解析，则 Windows 10 将回退到使用标准 WLAN Direct 连接建立 Miracast 会话。

> [!NOTE]
> 有关连接协商序列详细信息，请参阅 Miracast [OVER Infrastructure Connection Establishment Protocol (MS-MICE) ](https://msdn.microsoft.com/library/mt796768.aspx)




## <a name="enabling-miracast-over-infrastructure"></a>启用基础结构上的 Miracast 

如果你的 Surface Hub 或其他 Windows 10 设备已更新至 Windows 10 版本 1703，则你将自动具有此新功能。 若要在你的环境中充分利用此功能，你需要确保部署中以下条件成立：

- Surface Hub 或设备（Windows 电脑或手机）需要运行 Windows 10 版本 1703。
- 打开 TCP 端口 **：7250**。
- Surface Hub 或 Windows 电脑可充当基础结构上的 Miracast 的*接收器*。 Windows 电脑或手机可充当基础结构上的 Miracast 的*源*。
    - 作为 Miracast 接收器，Surface Hub 或设备必须通过以太网或安全的 WLAN 连接（如使用 WPA2-PSK 或 WPA2-企业安全功能）连接至企业网络。 如果Surface Hub设备连接到打开的 Wi-Fi 连接，Miracast基础结构将自行禁用。
    - 作为 Miracast 源，Windows 电脑或手机必须通过以太网或安全的 WLAN 连接来连接至相同的企业网络。
- DNS 主机名 (DNS) 设备名称Surface Hub或设备的名称需要通过 DNS 服务器解析。 通过允许 Surface Hub 通过动态 DNS 自动注册，或者通过为 Surface Hub 主机名手动创建 A 或 AAAA 记录，你可以达到此目的。 
- Windows 10 电脑必须通过以太网或安全的 WLAN 连接来连接至相同的企业网络。 


请务必注意，基础结构上的 Miracast 并不能替代标准 Miracast。 相反，此功能可作为补充，并且可以为企业网络中的用户带来优势。 作为特定位置的来宾且无企业网络访问权限的用户将继续使用 WLAN Direct 连接方法进行连接。

基础结构上的 Miracast 不需要 [SurfaceHub 配置服务提供程序 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) 中的 **InBoxApps/WirelessProjection/PinRequired** 设置。 这是因为仅当两台设备连接到同一企业网络时，基础结构上的 Miracast 才能工作。 这将删除 Miracast 以前缺少的安全限制。 我们建议你继续使用此设置（如果你之前使用过它），因为在基础结构连接不起作用的情况下 Miracast 将恢复为常规 Miracast。 

## <a name="faq"></a>常见问题
**为什么仍需要Wi-Fi基础结构Miracast基础结构？**<br>
识别接收器Miracast发现请求只能通过 Wi-Fi 适配器发生。 确定接收器后，Windows 10可以尝试连接到网络。

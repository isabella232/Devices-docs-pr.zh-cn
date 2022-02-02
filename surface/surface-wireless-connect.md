---
title: 优化 Surface 设备的 WLAN 连接
description: 本主题介绍推荐的Wi-Fi设置，以确保 Surface 设备在交通塞塞的网络环境和移动方案中保持连接。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.audience: itpro
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.reviewer: tokatz
manager: laurawi
ms.date: 11/30/2021
ms.openlocfilehash: e031b485979b20d6206398840466d553772b6f1d
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338245"
---
# <a name="optimize-wi-fi-connectivity-on-surface-devices"></a>优化Wi-Fi Surface 设备的连接性

为了与全天的电池使用时间保持连接，Surface 设备实现了可平衡性能和电源消耗的无线连接设置。 在要求最严格的移动工作负载之外，用户可以保持足够的无线连接，而无需修改默认网络适配器或相关设置。 本页重点介绍使用 Surface 设备的移动方案中的关键无线连接注意事项。

## <a name="prerequisites"></a>必备条件

本文档假定你已成功部署支持 802.11n (Wi-Fi 4) 或更高版本的无线网络) 遵循来自领先设备供应商的建议。

## <a name="configuring-access-points-for-optimal-roaming-capabilities"></a>配置访问点以实现最佳漫游功能

假设您正在管理通常由许多不同类型的客户端设备访问的无线网络。 在这种情况下，建议在 WLAN 中的接入点 (AP) 上启用特定协议，如使用 [802.11k、802.11v 和 802.11r](/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r) 快速漫游中所述。 Surface 设备可以利用以下无线协议：

- **802.11r。** "**快速 BSS 转换** "通过减少设备在设备四处移动时访问其他 AP 所需的帧数来加速连接到新的无线接入点。 在自 2019 年发布的新一代 Surface 设备中，最终用户可能会访问其设备上漫游的主动性设置。 尽管不建议修改默认设置，但用户应了解此功能并了解特定设置如何影响其保持连接能力。
- **802.11k.** **"邻接** 报告"为设备提供有关相邻接入点的当前条件的信息。 它可以帮助你的 Surface 设备使用除信号强度外的其他条件（如 AP 使用率）选择最佳 AP。

特定 Surface 设备还可使用 802.11v"BSS 转换管理帧"，其功能与 802.11k 非常类似，提供有关附近候选 AP 的信息。 其中包括 Surface Pro 8、Surface Pro 7+、Surface Laptop Studio、Surface Go 3、Surface Go 2、Surface Go、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。

## <a name="managing-user-settings"></a>管理用户设置

可以通过设计良好的网络（在所有接入点支持 802.11r 和 802.11k）实现最佳漫游功能。 与在单个设备上管理用户设置相比，建议采用确保网络配置得当以为用户提供最佳无线体验的方法。

### <a name="recommended-user-settings-and-best-practices"></a>建议的用户设置和最佳做法

在某些情况下，修改内置于 Surface 设备的高级网络适配器设置可能会促进更可靠的连接。 但是，请记住，由于接入点问题、网络设计缺陷或环境站点问题，无法连接到无线资源更为频繁。

> [!TIP]
> 如何保持你的Surface Pro Surface Go 也会影响信号强度。 如果遇到带宽损失，请检查是否未保持屏幕顶部（无线Wi-Fi的位置）。 尽管保持屏幕顶部不会阻止无线信号，但它可触发设备驱动程序以启动更改，以减少连接。

### <a name="keep-default-auto-setting-for-dual-bandwidth-capability"></a>保留双带宽功能的默认自动设置

在大多数 Surface 设备上，你可以将客户端网络适配器设置配置为仅连接到 5 GHz (GHz) 上的无线 AP、仅连接 2.4 GHz 或让操作系统选择最佳选项 (默认自动设置) 。

**若要访问网络适配器设置，请转到：**

- **Start** > **控制面板** > **网络和共享中心** > **你的Wi-Fi适配器** > **属性** > **配置** > **高级**。

![* wifi-band settings*.](images/wifi-band.png) <br>

请记住，2.4 GHz 在 5 GHz 上具有一些优势：它通过墙壁或其他实心对象进一步且更轻松地延伸。 除非你有一个明确用例可以保证连接到 5 GHz，否则建议将频带设置保留为默认状态以避免可能出现的负面影响。 例如：

- 在机场、咖啡店和机场发现的许多热点仍只能使用 2.4 GHz，如果仅将 Band 设置为 5 GHz，则有效地阻止对设备的访问。
- 由于Miracast要求在 2.4 GHz 通道上完成初始握手，因此设备无法仅以 5 GHz 进行连接。

> [!NOTE]
> 默认情况下，Surface 设备首选连接到 5 GHz（如果可用）。 但是，Surface 将首先查找 2.4 GHz 连接，以在电池不足时保持电源。

还可以根据需要切换区段设置以适合您的环境。 例如，居住在具有多个 Wi-Fi 热点的高密度单元建筑物的用户（通过 2.4 GHz 广播的所有消费者设备的存在）可能受益于以下操作：将其 Surface 设备设置为仅连接 5 GHz，然后根据需要恢复为自动。

### <a name="roaming-aggressiveness-settings-on-surface-devices-with-intel-adapters"></a>使用 Intel 适配器的 Surface 设备上漫游主动性设置

用户可能希望选择一个信号强度阈值，该阈值在信号降低时提示设备搜索新的接入点 (漫游攻击) 。 默认情况下，如果信号强度下降至中等 (72% 的信号强度，则带 Intel 适配器的 Surface 设备将尝试**** 漫游到新的) 。 组织还可以跨多个网络访问点实施旨在构建的无线协议，以促进漫游的塞塞网络环境，如本页前面所述。

虽然增加高于 **中等** 的漫游攻击性可能会改善高度交通状况的办公环境或居住环境中的连接性，但当单步超出这些环境时，可能会导致连接降级。

除非在特定的移动方案中遇到连接问题（例如，在会议期间维护语音和视频连接，同时执行环境站点检查）时，将漫游主动性设置保留为默认状态。 如果没有注意到任何改进，请恢复为默认的"中等"状态。 请注意，如果你增加漫游的主动性，也会加快电池电源消耗。

**若要在 Surface 上启用漫游主动性：**

1. 转到 **"****StartDevice** >  管理器"。
2. 在 **"网络适配器"** 下，选择 **"intel Wi-Fi 6"** ，然后右键单击"属性 **"**。
3. 选择" **高级"** 选项卡。
4. 选择 **"漫游主动性** "，然后从下拉菜单中选择你的首选值。

![* 漫游主动性设置-Intel *。](images/wifi-roaming-int.png) <br>

### <a name="roaming-aggressiveness-settings-on-surface-go-and-surface-pro-x"></a>Surface Go 和 X 上的漫游Surface Pro设置

使用 Surface Go 的前端工作人员可能希望选择一个信号强度阈值，该阈值在信号强度降低时提示设备搜索新的接入点 (漫游攻击) 。 默认情况下，如果信号强度下降至中等信号强度低于中等 (50% 的信号强度，Surface **** 设备将尝试漫游到) 。 请注意，只要增加漫游的主动性，就会加快电池电源消耗。

除非在特定的移动方案中遇到连接问题（例如，在会议期间维护语音和视频连接，同时执行环境站点检查）时，将漫游主动性设置保留为默认状态。 如果没有注意到任何改进，则还原为默认的"中等 **"** 状态。

**若要在 Surface Go 上启用漫游主动性：**

1. 转到"**开始>控制面板** > **""网络"和"InternetNetwork** >  **和共享中心"。**
2. 在 **"连接**"下 **，选择"WLAN"** ，然后选择"属性 **"。**
3. 选择 **"Microsoft 网络的客户端"** ，然后选择"配置 **"**
4. 选择 **"** > **高级攻击性"** ，然后从下拉菜单中选择首选值。

![* 漫游主动性设置-QualComm *。](images/wifi-roaming.png) <br>

## <a name="conclusion"></a>总结

Surface 设备使用默认设置进行设计，以在保持电池使用时间需求时实现最佳无线连接。 为 Surface 设备实现可靠连接的最有效方式是通过支持 802.11r 和 802.11k 的精心设计的网络。 用户可以调整网络适配器设置或漫游主动性，但应仅为响应特定的环境因素而这样做，如果没有明显的改进，则恢复到默认状态。

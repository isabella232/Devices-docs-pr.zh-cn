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
ms.date: 01/15/2021
ms.openlocfilehash: 69ca7bc7383a122dfd4f069135319b92ff7edfb0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271376"
---
# 优化 Surface 设备的 WLAN 连接


为了与全天的电池使用时间保持联系，Surface 设备实现了在性能和电源消耗之间平衡的无线连接设置。 在最严格的移动方案之外，用户可以保持足够的无线连接，而无需修改默认网络适配器或相关设置。 此页面重点介绍使用最新 Surface 设备（包括 Surface Pro 7+、Surface Laptop Go、Surface Go 2、Surface Pro X、Surface Laptop 3、Surface Book 3 和 Surface Pro 7）的移动方案中的关键无线连接注意事项。

##  <a name="prerequisites"></a>必备条件

本文档假定你已根据来自主要设备供应商的最佳方案建议成功部署支持 802.11n (WI-Fi 4) 或更高版本的无线网络。

##  <a name="configuring-access-points-for-optimal-roaming-capabilities"></a>配置访问点以实现最佳漫游功能

如果要管理通常由许多不同类型的客户端设备访问的无线网络，建议在 WLAN 中的接入点 (AP) 上启用特定协议，如 [使用 802.11k、802.11v 和 802.11r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)的快速漫游中所述。 Surface 设备可以利用以下无线协议：

- **802.11r。** "**快速 BSS** 转换"通过减少设备在设备四处移动时访问其他 AP 所需的帧数来加速连接到新的无线接入点。 在自 2019 年发布的新一代 Surface 设备中，最终用户可能会访问其设备上漫游的主动性设置。 尽管不建议修改默认设置，但用户应了解此功能并了解特定设置如何影响其保持连接的能力。
- **802.11k.** **"邻接** 报告"为设备提供有关相邻接入点的当前条件的信息。 它可以帮助你的 Surface 设备使用信号强度（如 AP 利用率）标准选择最佳 AP。

特定 Surface 设备还可使用 802.11v"BSS 转换管理帧"，其功能与提供有关附近候选 AP 的信息的 802.11k 非常类似。 其中包括 Surface Pro 7+、Surface Go、Surface Go 2、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。 

##  <a name="managing-user-settings"></a>管理用户设置

可以通过设计良好的网络实现最佳漫游功能，该网络在所有接入点中支持 802.11r 和 802.11k。 与尝试在单个设备上管理用户设置相比，建议采用确保网络正确配置为为用户提供最佳无线体验的方法。 

###  <a name="recommended-user-settings-and-best-practices"></a>建议的用户设置和最佳做法

在某些情况下，修改内置于 Surface 设备的高级网络适配器设置可能会促进更可靠的连接。 但请记住，无法连接到无线资源通常是由于接入点问题、网络设计缺陷或环境站点问题。

> [!NOTE]
> 如何保持 Surface Pro 或 Surface Go 也会影响信号强度。 如果遇到带宽损失，请检查是否未保持屏幕顶部，该屏幕Wi-Fi接收器所在的位置。 尽管保持屏幕顶部不会阻止无线信号，但它可以触发设备驱动程序以启动更改，以减少连接。

###  <a name="keep-default-auto-setting-for-dual-bandwidth-capability"></a>保留双带宽功能的默认自动设置

在大多数 Surface 设备上，你可以将客户端网络适配器设置配置为仅连接到 5 GHz (GHz) 上的无线 AP、仅连接 2.4 GHz 或让操作系统选择最佳选项 (默认自动设置) 。

**若要访问网络适配器设置，请转到：**

- **开始**  > **控制面板**  > **网络和共享中心**  > **你的Wi-Fi适配器**  > **属性**  > **配置**  > **高级**。

![* wifi-band settings*](images/wifi-band.png) <br>

请记住，2.4 GHz 在 5 GHz 上具有一些优势：它通过墙壁或其他实心对象进一步且更轻松地延伸。 除非你有一个明确用例需要连接到 5 GHz，否则建议将带设置保留为默认状态，以避免可能出现的负面影响。 例如：


- 许多在餐厅、咖啡店和机场找到的热点仍使用 2.4 GHz，如果仅将频带设置为 5 GHz，则有效地阻止设备访问。
- 由于 Miracast 无线显示连接要求通过 2.4 GHz 通道完成初始握手，因此设备无法仅以 5 GHz 进行连接。

> [!NOTE]
> 默认情况下，Surface 设备首选连接到 5 GHz（如果可用）。 但是，若要在低电池状态中保持电源，Surface 将首先查找 2.4 GHz 连接。

还可以根据需要切换区段设置以适合您的环境。 例如，居住在具有多个 Wi-Fi 热点的高密度单元大楼的用户（通过 2.4 GHz 广播的消费者设备的存在）可能会受益，只需将其 Surface 设备设置为仅在 5 GHz 上连接，然后根据需要恢复为自动。

###  <a name="roaming-aggressiveness-settings-on-surface-devices-with-intel-adapters"></a>使用 Intel 适配器的 Surface 设备上漫游主动性设置 

用户可能希望选择一个信号强度阈值，该阈值在信号下降时提示设备搜索新的接入点 (漫游主动性) 。 默认情况下，如果信号强度低于中等值 (72% 的信号强度，则具有 Intel**** 适配器的 Surface 设备将尝试漫游到新的接入点) 。 另请注意，组织可以跨多个网络访问点实现用途构建的无线协议，以简化漫游的塞塞网络环境，如本页前面所述。 

虽然提高高于 **中等** 的漫游主动性可能会改善高度交通塞塞的办公或住宅环境中的连接性，但当单步执行这些环境外操作时，可能会导致连接降级。 

建议将漫游主动性设置保留为默认状态，除非你在特定的移动方案中遇到连接问题，例如执行环境站点检查，同时在会议期间维护语音和视频连接。 如果没有注意到任何改进，请恢复为默认的"中等"状态。 请注意，如果你增加漫游主动性，也会加快电池电源消耗。 

**若要在 Surface 上启用漫游主动性：**

1. 转到"**启动**  >  **设备管理器"。**
2. 在 **"网络适配器"****下，选择 Intel Wi-Fi 6，** 然后右键单击 **"属性"。**
3. 选择 **"高级"** 选项卡。
4. 选择 **"漫游主动性** "，然后从下拉菜单中选择首选值。

![* 漫游主动性设置-Intel *](images/wifi-roaming-int.png) <br>

###  <a name="roaming-aggressiveness-settings-on-surface-go-and-surface-pro-x"></a>Surface Go 和 Surface Pro X 上的漫游主动性设置

使用 Surface Go 的前端工作人员可能希望选择一个信号强度阈值，该阈值在信号强度下降时提示设备搜索新的接入点 (漫游主动) 。 默认情况下，如果信号强度低于中等值，则 Surface 设备会尝试漫游到新接入点**** (信号强度低于 50%) 。 请注意，只要增加漫游的主动性，就会加快电池电源消耗。

将漫游主动性设置保留为默认状态，除非你在特定的移动方案中遇到连接问题，例如执行环境站点检查，同时在会议期间维护语音和视频连接。 如果你未注意到任何改进，请恢复为默认的"中等 **"** 状态。

**若要在 Surface Go 上启用漫游主动性：**

1. 转到 **">控制面板**  >  **网络和 Internet**  >  **网络和共享中心"。**
2. 在 **"连接****"下，选择 WLAN，** 然后选择 **"属性"。**
3. 选择 **Microsoft 网络的客户端** ，然后选择" **配置"**
4. 选择****  >  **"高级漫游主动性**"，然后从下拉菜单中选择首选值。

![* 漫游主动性设置-QualComm *](images/wifi-roaming.png) <br>


##  <a name="conclusion"></a>总结

Surface 设备使用默认设置进行设计，以在保持电池使用时间需求时实现最佳无线连接平衡。 为 Surface 设备实现可靠连接的最有效方式是通过支持 802.11r 和 802.11k 的精心设计的网络。 用户可以调整网络适配器设置或漫游的主动性，但应仅为响应特定环境因素而这样做，如果没有明显的改进，则恢复为默认状态。

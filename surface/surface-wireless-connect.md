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
# <span data-ttu-id="167f0-103">优化 Surface 设备的 WLAN 连接</span><span class="sxs-lookup"><span data-stu-id="167f0-103">Optimize Wi-Fi connectivity for Surface devices</span></span>


<span data-ttu-id="167f0-104">为了与全天的电池使用时间保持联系，Surface 设备实现了在性能和电源消耗之间平衡的无线连接设置。</span><span class="sxs-lookup"><span data-stu-id="167f0-104">To stay connected with all-day battery life, Surface devices implement wireless connectivity settings that balance performance and power conservation.</span></span> <span data-ttu-id="167f0-105">在最严格的移动方案之外，用户可以保持足够的无线连接，而无需修改默认网络适配器或相关设置。</span><span class="sxs-lookup"><span data-stu-id="167f0-105">Outside of the most demanding mobility scenarios, users can maintain sufficient wireless connectivity without modifying default network adapter or related settings.</span></span> <span data-ttu-id="167f0-106">此页面重点介绍使用最新 Surface 设备（包括 Surface Pro 7+、Surface Laptop Go、Surface Go 2、Surface Pro X、Surface Laptop 3、Surface Book 3 和 Surface Pro 7）的移动方案中的关键无线连接注意事项。</span><span class="sxs-lookup"><span data-stu-id="167f0-106">This page highlights key wireless connectivity considerations in mobile scenarios using the latest Surface devices including Surface Pro 7+, Surface Laptop Go, Surface Go 2, Surface Pro X, Surface Laptop 3, Surface Book 3, and Surface Pro 7.</span></span>

## <span data-ttu-id="167f0-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="167f0-107">Prerequisites</span></span>

<span data-ttu-id="167f0-108">本文档假定你已根据来自主要设备供应商的最佳方案建议成功部署支持 802.11n (WI-Fi 4) 或更高版本的无线网络。</span><span class="sxs-lookup"><span data-stu-id="167f0-108">This document assumes you have successfully deployed a wireless network that supports 802.11n (Wi-Fi 4) or later in accordance with best practice recommendations from leading equipment vendors.</span></span>

## <span data-ttu-id="167f0-109">配置访问点以实现最佳漫游功能</span><span class="sxs-lookup"><span data-stu-id="167f0-109">Configuring access points for optimal roaming capabilities</span></span>

<span data-ttu-id="167f0-110">如果要管理通常由许多不同类型的客户端设备访问的无线网络，建议在 WLAN 中的接入点 (AP) 上启用特定协议，如 [使用 802.11k、802.11v 和 802.11r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)的快速漫游中所述。</span><span class="sxs-lookup"><span data-stu-id="167f0-110">If you’re managing a wireless network that’s typically accessed by many different types of client devices, it’s recommended to enable specific protocols on access points (APs) in your WLAN, as described in [Fast Roaming with 802.11k, 802.11v, and 802.11r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r).</span></span> <span data-ttu-id="167f0-111">Surface 设备可以利用以下无线协议：</span><span class="sxs-lookup"><span data-stu-id="167f0-111">Surface devices can take advantage of the following wireless protocols:</span></span>

- **<span data-ttu-id="167f0-112">802.11r。</span><span class="sxs-lookup"><span data-stu-id="167f0-112">802.11r.</span></span>** <span data-ttu-id="167f0-113">"**快速 BSS** 转换"通过减少设备在设备四处移动时访问其他 AP 所需的帧数来加速连接到新的无线接入点。</span><span class="sxs-lookup"><span data-stu-id="167f0-113">“**Fast BSS Transition”** accelerates connecting to new wireless access points by reducing the number of frames required before your device can access another AP as you move around with your device.</span></span> <span data-ttu-id="167f0-114">在自 2019 年发布的新一代 Surface 设备中，最终用户可能会访问其设备上漫游的主动性设置。</span><span class="sxs-lookup"><span data-stu-id="167f0-114">In the new generation of Surface devices released since 2019, end users may gain access to roaming aggressiveness settings on their device.</span></span> <span data-ttu-id="167f0-115">尽管不建议修改默认设置，但用户应了解此功能并了解特定设置如何影响其保持连接的能力。</span><span class="sxs-lookup"><span data-stu-id="167f0-115">Although modifying default settings is not recommended, users should be aware of this capability and understand how specific settings can impact their ability to remain connected.</span></span>
- **<span data-ttu-id="167f0-116">802.11k.</span><span class="sxs-lookup"><span data-stu-id="167f0-116">802.11k.</span></span>** <span data-ttu-id="167f0-117">**"邻接** 报告"为设备提供有关相邻接入点的当前条件的信息。</span><span class="sxs-lookup"><span data-stu-id="167f0-117">**“Neighbor Reports”** provides devices with information on current conditions at neighboring access points.</span></span> <span data-ttu-id="167f0-118">它可以帮助你的 Surface 设备使用信号强度（如 AP 利用率）标准选择最佳 AP。</span><span class="sxs-lookup"><span data-stu-id="167f0-118">It can help your Surface device choose the best AP using criteria other than signal strength such as AP utilization.</span></span>

<span data-ttu-id="167f0-119">特定 Surface 设备还可使用 802.11v"BSS 转换管理帧"，其功能与提供有关附近候选 AP 的信息的 802.11k 非常类似。</span><span class="sxs-lookup"><span data-stu-id="167f0-119">Specific Surface devices can also use 802.11v “BSS Transition Management Frames,” which functions much like 802.11k in providing information on nearby candidate APs.</span></span> <span data-ttu-id="167f0-120">其中包括 Surface Pro 7+、Surface Go、Surface Go 2、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。</span><span class="sxs-lookup"><span data-stu-id="167f0-120">These include Surface Pro 7+, Surface Go, Surface Go 2, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

## <span data-ttu-id="167f0-121">管理用户设置</span><span class="sxs-lookup"><span data-stu-id="167f0-121">Managing user settings</span></span>

<span data-ttu-id="167f0-122">可以通过设计良好的网络实现最佳漫游功能，该网络在所有接入点中支持 802.11r 和 802.11k。</span><span class="sxs-lookup"><span data-stu-id="167f0-122">You can achieve optimal roaming capabilities through a well-designed network that supports  802.11r and 802.11k across all access points.</span></span> <span data-ttu-id="167f0-123">与尝试在单个设备上管理用户设置相比，建议采用确保网络正确配置为为用户提供最佳无线体验的方法。</span><span class="sxs-lookup"><span data-stu-id="167f0-123">Ensuring that your network is properly configured to provide users with the best wireless experience is the recommended approach versus attempting to manage user settings on individual devices.</span></span> 

### <span data-ttu-id="167f0-124">建议的用户设置和最佳做法</span><span class="sxs-lookup"><span data-stu-id="167f0-124">Recommended user settings and best practices</span></span>

<span data-ttu-id="167f0-125">在某些情况下，修改内置于 Surface 设备的高级网络适配器设置可能会促进更可靠的连接。</span><span class="sxs-lookup"><span data-stu-id="167f0-125">In certain situations, modifying advanced network adapter settings built into Surface devices may facilitate a more reliable connection.</span></span> <span data-ttu-id="167f0-126">但请记住，无法连接到无线资源通常是由于接入点问题、网络设计缺陷或环境站点问题。</span><span class="sxs-lookup"><span data-stu-id="167f0-126">Keep in mind however that an inability to connect to wireless resources is more often due to an access point issue, networking design flaw, or environmental site issue.</span></span>

> [!NOTE]
> <span data-ttu-id="167f0-127">如何保持 Surface Pro 或 Surface Go 也会影响信号强度。</span><span class="sxs-lookup"><span data-stu-id="167f0-127">How you hold your Surface Pro or Surface Go can also affect signal strength.</span></span> <span data-ttu-id="167f0-128">如果遇到带宽损失，请检查是否未保持屏幕顶部，该屏幕Wi-Fi接收器所在的位置。</span><span class="sxs-lookup"><span data-stu-id="167f0-128">If you’re experiencing a loss of bandwidth, check that you’re not holding the top of the display, where the Wi-Fi radio receiver is located.</span></span> <span data-ttu-id="167f0-129">尽管保持屏幕顶部不会阻止无线信号，但它可以触发设备驱动程序以启动更改，以减少连接。</span><span class="sxs-lookup"><span data-stu-id="167f0-129">Although holding the top of the display does not block wireless signals, it can trigger the device driver to initiate changes that reduce connectivity.</span></span>

### <span data-ttu-id="167f0-130">保留双带宽功能的默认自动设置</span><span class="sxs-lookup"><span data-stu-id="167f0-130">Keep default Auto setting for dual bandwidth capability</span></span>

<span data-ttu-id="167f0-131">在大多数 Surface 设备上，你可以将客户端网络适配器设置配置为仅连接到 5 GHz (GHz) 上的无线 AP、仅连接 2.4 GHz 或让操作系统选择最佳选项 (默认自动设置) 。</span><span class="sxs-lookup"><span data-stu-id="167f0-131">On most Surface devices, you can configure client network adapter settings to only connect to wireless APs over 5 gigahertz (GHz), only connect over 2.4 GHz, or let the operating system choose the best option (default Auto setting).</span></span>

**<span data-ttu-id="167f0-132">若要访问网络适配器设置，请转到：</span><span class="sxs-lookup"><span data-stu-id="167f0-132">To access network adapter settings go to:</span></span>**

- <span data-ttu-id="167f0-133">**开始**  > **控制面板**  > **网络和共享中心**  > **你的Wi-Fi适配器**  > **属性**  > **配置**  > **高级**。</span><span class="sxs-lookup"><span data-stu-id="167f0-133">**Start** > **Control panel** > **Network and Sharing Center** > **your Wi-Fi adapter** > **Properties** > **Configure** > **Advanced**.</span></span>

![\* wifi-band settings\*](images/wifi-band.png) <br>

<span data-ttu-id="167f0-135">请记住，2.4 GHz 在 5 GHz 上具有一些优势：它通过墙壁或其他实心对象进一步且更轻松地延伸。</span><span class="sxs-lookup"><span data-stu-id="167f0-135">Keep in mind that 2.4 GHz has some advantages over 5 GHz: It extends further and more easily penetrates through walls or other solid objects.</span></span> <span data-ttu-id="167f0-136">除非你有一个明确用例需要连接到 5 GHz，否则建议将带设置保留为默认状态，以避免可能出现的负面影响。</span><span class="sxs-lookup"><span data-stu-id="167f0-136">Unless you have a clear use case that warrants connecting to 5 GHz, it’s recommended to leave the Band setting in the default state to avoid possible adverse consequences.</span></span> <span data-ttu-id="167f0-137">例如：</span><span class="sxs-lookup"><span data-stu-id="167f0-137">For example:</span></span>


- <span data-ttu-id="167f0-138">许多在餐厅、咖啡店和机场找到的热点仍使用 2.4 GHz，如果仅将频带设置为 5 GHz，则有效地阻止设备访问。</span><span class="sxs-lookup"><span data-stu-id="167f0-138">Many hotspots found in hotels, coffee shops, and airports still only use 2.4 GHz, effectively blocking access to devices if Band is set to 5 GHz Only.</span></span>
- <span data-ttu-id="167f0-139">由于 Miracast 无线显示连接要求通过 2.4 GHz 通道完成初始握手，因此设备无法仅以 5 GHz 进行连接。</span><span class="sxs-lookup"><span data-stu-id="167f0-139">Since Miracast wireless display connections require the initial handshake to be completed over 2.4 GHz channels, devices won’t be able to connect at 5 GHz Only.</span></span>

> [!NOTE]
> <span data-ttu-id="167f0-140">默认情况下，Surface 设备首选连接到 5 GHz（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="167f0-140">By default Surface devices will prefer connecting to 5 GHz if available.</span></span> <span data-ttu-id="167f0-141">但是，若要在低电池状态中保持电源，Surface 将首先查找 2.4 GHz 连接。</span><span class="sxs-lookup"><span data-stu-id="167f0-141">However, to preserve power  in a low battery state, Surface will first look for a 2.4 GHz connection.</span></span>

<span data-ttu-id="167f0-142">还可以根据需要切换区段设置以适合您的环境。</span><span class="sxs-lookup"><span data-stu-id="167f0-142">You can also toggle the band setting as needed to suit your environment.</span></span> <span data-ttu-id="167f0-143">例如，居住在具有多个 Wi-Fi 热点的高密度单元大楼的用户（通过 2.4 GHz 广播的消费者设备的存在）可能会受益，只需将其 Surface 设备设置为仅在 5 GHz 上连接，然后根据需要恢复为自动。</span><span class="sxs-lookup"><span data-stu-id="167f0-143">For example, users living in high density apartment buildings with multiple Wi-Fi hotspots  —  amid the presence of consumer devices all broadcasting via 2.4 GHz  —  will likely benefit by setting their Surface device to connect on 5 GHz only and then revert to Auto when needed.</span></span>

### <span data-ttu-id="167f0-144">使用 Intel 适配器的 Surface 设备上漫游主动性设置</span><span class="sxs-lookup"><span data-stu-id="167f0-144">Roaming aggressiveness settings on Surface devices with Intel adapters</span></span> 

<span data-ttu-id="167f0-145">用户可能希望选择一个信号强度阈值，该阈值在信号下降时提示设备搜索新的接入点 (漫游主动性) 。</span><span class="sxs-lookup"><span data-stu-id="167f0-145">Users may wish to select a signal strength threshold that prompts the device to search for a new access point when the signal drops (roaming aggressiveness).</span></span> <span data-ttu-id="167f0-146">默认情况下，如果信号强度低于中等值 (72% 的信号强度，则具有 Intel\*\*\*\* 适配器的 Surface 设备将尝试漫游到新的接入点) 。</span><span class="sxs-lookup"><span data-stu-id="167f0-146">By default, Surface devices with Intel adapters attempt to roam to a new access point if the signal strength drops below **Medium** (72 percent signal strength).</span></span> <span data-ttu-id="167f0-147">另请注意，组织可以跨多个网络访问点实现用途构建的无线协议，以简化漫游的塞塞网络环境，如本页前面所述。</span><span class="sxs-lookup"><span data-stu-id="167f0-147">Note also that organizations can implement purpose-built wireless protocols across multiple network access points to facilitate roaming congested network environments, as explained earlier on this page.</span></span> 

<span data-ttu-id="167f0-148">虽然提高高于 **中等** 的漫游主动性可能会改善高度交通塞塞的办公或住宅环境中的连接性，但当单步执行这些环境外操作时，可能会导致连接降级。</span><span class="sxs-lookup"><span data-stu-id="167f0-148">While increasing roaming aggressiveness above **Medium** may yield improved connectivity in highly congested office or residential environments, it can result in degraded connectivity when stepping outside of these environments.</span></span> 

<span data-ttu-id="167f0-149">建议将漫游主动性设置保留为默认状态，除非你在特定的移动方案中遇到连接问题，例如执行环境站点检查，同时在会议期间维护语音和视频连接。</span><span class="sxs-lookup"><span data-stu-id="167f0-149">It’s recommended to leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="167f0-150">如果没有注意到任何改进，请恢复为默认的"中等"状态。</span><span class="sxs-lookup"><span data-stu-id="167f0-150">If you don’t notice any improvement, revert to the default Medium state.</span></span> <span data-ttu-id="167f0-151">请注意，如果你增加漫游主动性，也会加快电池电源消耗。</span><span class="sxs-lookup"><span data-stu-id="167f0-151">Note that if you increase roaming aggressiveness, you also accelerate battery power consumption.</span></span> 

**<span data-ttu-id="167f0-152">若要在 Surface 上启用漫游主动性：</span><span class="sxs-lookup"><span data-stu-id="167f0-152">To enable roaming aggressiveness on Surface:</span></span>**

1. <span data-ttu-id="167f0-153">转到"**启动**  >  **设备管理器"。**</span><span class="sxs-lookup"><span data-stu-id="167f0-153">Go to **Start** > **Device Manager**.</span></span>
2. <span data-ttu-id="167f0-154">在 **"网络适配器"\*\*\*\*下，选择 Intel Wi-Fi 6，** 然后右键单击 **"属性"。**</span><span class="sxs-lookup"><span data-stu-id="167f0-154">Under **Network adapters** select **Intel Wi-Fi 6** and then right click **Properties**.</span></span>
3. <span data-ttu-id="167f0-155">选择 **"高级"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="167f0-155">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="167f0-156">选择 **"漫游主动性** "，然后从下拉菜单中选择首选值。</span><span class="sxs-lookup"><span data-stu-id="167f0-156">Select **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 漫游主动性设置-Intel \*](images/wifi-roaming-int.png) <br>

### <span data-ttu-id="167f0-158">Surface Go 和 Surface Pro X 上的漫游主动性设置</span><span class="sxs-lookup"><span data-stu-id="167f0-158">Roaming aggressiveness settings on Surface Go and Surface Pro X</span></span>

<span data-ttu-id="167f0-159">使用 Surface Go 的前端工作人员可能希望选择一个信号强度阈值，该阈值在信号强度下降时提示设备搜索新的接入点 (漫游主动) 。</span><span class="sxs-lookup"><span data-stu-id="167f0-159">Front-line workers using Surface Go may wish to select a signal strength threshold that prompts the device to search for a new access point when signal strength drops (roaming aggressiveness).</span></span> <span data-ttu-id="167f0-160">默认情况下，如果信号强度低于中等值，则 Surface 设备会尝试漫游到新接入点\*\*\*\* (信号强度低于 50%) 。</span><span class="sxs-lookup"><span data-stu-id="167f0-160">By default, Surface devices attempt to roam to a new access point if the signal strength drops below **Medium** (50 percent signal strength).</span></span> <span data-ttu-id="167f0-161">请注意，只要增加漫游的主动性，就会加快电池电源消耗。</span><span class="sxs-lookup"><span data-stu-id="167f0-161">Note that whenever you increase roaming aggressiveness, you accelerate battery power consumption.</span></span>

<span data-ttu-id="167f0-162">将漫游主动性设置保留为默认状态，除非你在特定的移动方案中遇到连接问题，例如执行环境站点检查，同时在会议期间维护语音和视频连接。</span><span class="sxs-lookup"><span data-stu-id="167f0-162">Leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="167f0-163">如果你未注意到任何改进，请恢复为默认的"中等 **"** 状态。</span><span class="sxs-lookup"><span data-stu-id="167f0-163">If you don’t notice any improvement revert to the default **Medium** state.</span></span>

**<span data-ttu-id="167f0-164">若要在 Surface Go 上启用漫游主动性：</span><span class="sxs-lookup"><span data-stu-id="167f0-164">To enable roaming aggressiveness on Surface Go:</span></span>**

1. <span data-ttu-id="167f0-165">转到 **">控制面板**  >  **网络和 Internet**  >  **网络和共享中心"。**</span><span class="sxs-lookup"><span data-stu-id="167f0-165">Go to **Start > Control Panel** > **Network and Internet** > **Network and Sharing Center.**</span></span>
2. <span data-ttu-id="167f0-166">在 **"连接\*\*\*\*"下，选择 WLAN，** 然后选择 **"属性"。**</span><span class="sxs-lookup"><span data-stu-id="167f0-166">Under **Connections** select **Wi-Fi** and then select **Properties.**</span></span>
3. <span data-ttu-id="167f0-167">选择 **Microsoft 网络的客户端** ，然后选择" **配置"**</span><span class="sxs-lookup"><span data-stu-id="167f0-167">Select **Client for Microsoft Networks** and then select **Configure**</span></span>
4. <span data-ttu-id="167f0-168">选择\*\*\*\*  >  **"高级漫游主动性**"，然后从下拉菜单中选择首选值。</span><span class="sxs-lookup"><span data-stu-id="167f0-168">Select **Advanced** > **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 漫游主动性设置-QualComm \*](images/wifi-roaming.png) <br>


## <span data-ttu-id="167f0-170">总结</span><span class="sxs-lookup"><span data-stu-id="167f0-170">Conclusion</span></span>

<span data-ttu-id="167f0-171">Surface 设备使用默认设置进行设计，以在保持电池使用时间需求时实现最佳无线连接平衡。</span><span class="sxs-lookup"><span data-stu-id="167f0-171">Surface devices are designed with default settings for optimal wireless connectivity balanced alongside the need to preserve battery life.</span></span> <span data-ttu-id="167f0-172">为 Surface 设备实现可靠连接的最有效方式是通过支持 802.11r 和 802.11k 的精心设计的网络。</span><span class="sxs-lookup"><span data-stu-id="167f0-172">The most effective way of enabling reliable connectivity for Surface devices is through a well-designed network that supports 802.11r and 802.11k.</span></span> <span data-ttu-id="167f0-173">用户可以调整网络适配器设置或漫游的主动性，但应仅为响应特定环境因素而这样做，如果没有明显的改进，则恢复为默认状态。</span><span class="sxs-lookup"><span data-stu-id="167f0-173">Users can adjust network adapter settings or roaming aggressiveness but should only do so in response to specific environmental factors and revert to default state if there’s no noticeable improvement.</span></span>

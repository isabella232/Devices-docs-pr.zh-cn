---
title: 优化 Surface 设备的 WLAN 连接
description: 本主题介绍了推荐的 Wi-Fi 设置，以确保 Surface 设备在拥挤的网络环境和移动方案中保持连接。
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
ms.date: 10/26/2020
ms.openlocfilehash: d211ceea20b89824d45e433cf9670abe137130a0
ms.sourcegitcommit: 07ac65bf70c8c6efcda28eecc3013983fc386e0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "11136138"
---
# <span data-ttu-id="3f498-103">优化 Surface 设备的 WLAN 连接</span><span class="sxs-lookup"><span data-stu-id="3f498-103">Optimize Wi-Fi connectivity for Surface devices</span></span>


<span data-ttu-id="3f498-104">为了保持全天的电池使用时间，Surface 设备实现可平衡性能和节能的无线连接设置。</span><span class="sxs-lookup"><span data-stu-id="3f498-104">To stay connected with all-day battery life, Surface devices implement wireless connectivity settings that balance performance and power conservation.</span></span> <span data-ttu-id="3f498-105">在最苛刻的移动方案之外，用户可以保持足够的无线连接，而无需修改默认网络适配器或相关设置。</span><span class="sxs-lookup"><span data-stu-id="3f498-105">Outside of the most demanding mobility scenarios, users can maintain sufficient wireless connectivity without modifying default network adapter or related settings.</span></span> <span data-ttu-id="3f498-106">本页重点介绍了移动方案中使用最新 Surface 设备（包括 Surface Pro 7、Surface Pro X、Surface 笔记本3、Surface Book 3、Surface Go 2 和 Surface 笔记本电脑）的关键无线连接注意事项。</span><span class="sxs-lookup"><span data-stu-id="3f498-106">This page highlights key wireless connectivity considerations in mobile scenarios using the latest Surface devices including Surface Pro 7, Surface Pro X, Surface Laptop 3, Surface Book 3,  Surface Go 2, and Surface Laptop Go.</span></span>  

## <span data-ttu-id="3f498-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="3f498-107">Prerequisites</span></span>

<span data-ttu-id="3f498-108">本文档假设你已成功部署支持 802.11 n (Wi-fi 4) 或更高版本的无线网络，根据主要设备供应商提供的最佳做法建议。</span><span class="sxs-lookup"><span data-stu-id="3f498-108">This document assumes you have successfully deployed a wireless network that supports 802.11n (Wi-Fi 4) or later in accordance with best practice recommendations from leading equipment vendors.</span></span>

## <span data-ttu-id="3f498-109">为最佳漫游功能配置接入点</span><span class="sxs-lookup"><span data-stu-id="3f498-109">Configuring access points for optimal roaming capabilities</span></span>

<span data-ttu-id="3f498-110">如果你管理通常由许多不同类型的客户端设备访问的无线网络，建议在你的 WLAN 中 (Ap) 的接入点上启用特定协议，如 [使用 802.11 k、802.11 v 和 802.11 r 进行快速漫游](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)中所述。</span><span class="sxs-lookup"><span data-stu-id="3f498-110">If you’re managing a wireless network that’s typically accessed by many different types of client devices, it’s recommended to enable specific protocols on access points (APs) in your WLAN, as described in [Fast Roaming with 802.11k, 802.11v, and 802.11r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r).</span></span> <span data-ttu-id="3f498-111">Surface 设备可以利用下列无线协议：</span><span class="sxs-lookup"><span data-stu-id="3f498-111">Surface devices can take advantage of the following wireless protocols:</span></span>

- **<span data-ttu-id="3f498-112">802.11 r。</span><span class="sxs-lookup"><span data-stu-id="3f498-112">802.11r.</span></span>** <span data-ttu-id="3f498-113">"**快速 BSS 过渡"** 通过减少在使用设备移动设备时设备可以访问其他 AP 所需的帧数，加速连接到新的无线访问点。</span><span class="sxs-lookup"><span data-stu-id="3f498-113">“**Fast BSS Transition”** accelerates connecting to new wireless access points by reducing the number of frames required before your device can access another AP as you move around with your device.</span></span> <span data-ttu-id="3f498-114">在自2019以来发布的新一代 Surface 设备中，最终用户可能会在其设备上获得漫游入侵设置的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3f498-114">In the new generation of Surface devices released since 2019, end users may gain access to roaming aggressiveness settings on their device.</span></span> <span data-ttu-id="3f498-115">尽管不推荐修改默认设置，但用户应了解此功能，并了解特定设置对保持连接的能力有何影响。</span><span class="sxs-lookup"><span data-stu-id="3f498-115">Although modifying default settings is not recommended, users should be aware of this capability and understand how specific settings can impact their ability to remain connected.</span></span>
- **<span data-ttu-id="3f498-116">802.11 k。</span><span class="sxs-lookup"><span data-stu-id="3f498-116">802.11k.</span></span>** <span data-ttu-id="3f498-117">**"邻居报告"** 为设备提供有关邻近访问点上的当前条件的信息。</span><span class="sxs-lookup"><span data-stu-id="3f498-117">**“Neighbor Reports”** provides devices with information on current conditions at neighboring access points.</span></span> <span data-ttu-id="3f498-118">它可以帮助 Surface 设备使用信号强度（如 AP 利用率）以外的其他条件选择最佳 AP。</span><span class="sxs-lookup"><span data-stu-id="3f498-118">It can help your Surface device choose the best AP using criteria other than signal strength such as AP utilization.</span></span>

<span data-ttu-id="3f498-119">特定的 Surface 设备还可以使用 802.11 v "BSS 转换管理帧"，这与在提供附近的候选 Ap 相关信息的 802.11 k 非常类似。</span><span class="sxs-lookup"><span data-stu-id="3f498-119">Specific Surface devices can also use 802.11v “BSS Transition Management Frames,” which functions much like 802.11k in providing information on nearby candidate APs.</span></span> <span data-ttu-id="3f498-120">其中包括 Surface Go、Surface Pro 7、Surface Pro X 和 Surface 膝上型电脑3。</span><span class="sxs-lookup"><span data-stu-id="3f498-120">These include Surface Go, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

## <span data-ttu-id="3f498-121">管理用户设置</span><span class="sxs-lookup"><span data-stu-id="3f498-121">Managing user settings</span></span>

<span data-ttu-id="3f498-122">你可以通过在所有访问点上支持 802.11 r 和 802.11 k 的精心设计的网络实现最佳漫游功能。</span><span class="sxs-lookup"><span data-stu-id="3f498-122">You can achieve optimal roaming capabilities through a well-designed network that supports  802.11r and 802.11k across all access points.</span></span> <span data-ttu-id="3f498-123">确保您的网络正确配置为为用户提供最佳无线体验是推荐的方法，与尝试管理单个设备上的用户设置相比。</span><span class="sxs-lookup"><span data-stu-id="3f498-123">Ensuring that your network is properly configured to provide users with the best wireless experience is the recommended approach versus attempting to manage user settings on individual devices.</span></span> 

### <span data-ttu-id="3f498-124">推荐的用户设置和最佳做法</span><span class="sxs-lookup"><span data-stu-id="3f498-124">Recommended user settings and best practices</span></span>

<span data-ttu-id="3f498-125">在某些情况下，修改内置于 Surface 设备的高级网络适配器设置有助于实现更可靠的连接。</span><span class="sxs-lookup"><span data-stu-id="3f498-125">In certain situations, modifying advanced network adapter settings built into Surface devices may facilitate a more reliable connection.</span></span> <span data-ttu-id="3f498-126">请记住，由于访问点问题、网络设计缺陷或环境网站问题，无法连接到无线资源会更频繁。</span><span class="sxs-lookup"><span data-stu-id="3f498-126">Keep in mind however that an inability to connect to wireless resources is more often due to an access point issue, networking design flaw, or environmental site issue.</span></span>

> [!NOTE]
> <span data-ttu-id="3f498-127">保持 Surface Pro 或 Surface Go 的方式也会影响信号强度。</span><span class="sxs-lookup"><span data-stu-id="3f498-127">How you hold your Surface Pro or Surface Go can also affect signal strength.</span></span> <span data-ttu-id="3f498-128">如果您遇到带宽丢失的情况，请检查您是否没有在屏幕顶部显示 Wi-Fi 无线电接收器所在的位置。</span><span class="sxs-lookup"><span data-stu-id="3f498-128">If you’re experiencing a loss of bandwidth, check that you’re not holding the top of the display, where the Wi-Fi radio receiver is located.</span></span> <span data-ttu-id="3f498-129">尽管保持显示屏顶部不会阻止无线信号，但它可以触发设备驱动程序以启动减少连接的更改。</span><span class="sxs-lookup"><span data-stu-id="3f498-129">Although holding the top of the display does not block wireless signals, it can trigger the device driver to initiate changes that reduce connectivity.</span></span>

### <span data-ttu-id="3f498-130">保留双带宽功能的默认自动设置</span><span class="sxs-lookup"><span data-stu-id="3f498-130">Keep default Auto setting for dual bandwidth capability</span></span>

<span data-ttu-id="3f498-131">在大多数 Surface 设备上，你可以将客户端网络适配器设置配置为仅连接到5千赫兹 (GHz) 的无线 Ap，仅通过 2.4 GHz 连接，或者让操作系统选择最佳选项 (默认自动设置) 。</span><span class="sxs-lookup"><span data-stu-id="3f498-131">On most Surface devices, you can configure client network adapter settings to only connect to wireless APs over 5 gigahertz (GHz), only connect over 2.4 GHz, or let the operating system choose the best option (default Auto setting).</span></span>

**<span data-ttu-id="3f498-132">若要访问网络适配器设置，请转到：</span><span class="sxs-lookup"><span data-stu-id="3f498-132">To access network adapter settings go to:</span></span>**

- <span data-ttu-id="3f498-133">**开始**  > **"控制面板"**  > **网络和共享中心**  > **您的 Wi-Fi 适配器**  > **属性**  > **配置**  > **高级**。</span><span class="sxs-lookup"><span data-stu-id="3f498-133">**Start** > **Control panel** > **Network and Sharing Center** > **your Wi-Fi adapter** > **Properties** > **Configure** > **Advanced**.</span></span>

![\* wifi 频带设置 \*](images/wifi-band.png) <br>

<span data-ttu-id="3f498-135">请记住，2.4 GHz 有比 5 GHz 更多的优势：它通过墙壁或其他实体对象进一步、更轻松地 penetrates 扩展。</span><span class="sxs-lookup"><span data-stu-id="3f498-135">Keep in mind that 2.4 GHz has some advantages over 5 GHz: It extends further and more easily penetrates through walls or other solid objects.</span></span> <span data-ttu-id="3f498-136">除非你有一个明确的用例需要连接到 5 GHz，否则建议将波段设置保留为默认状态，以避免潜在的不利后果。</span><span class="sxs-lookup"><span data-stu-id="3f498-136">Unless you have a clear use case that warrants connecting to 5 GHz, it’s recommended to leave the Band setting in the default state to avoid possible adverse consequences.</span></span> <span data-ttu-id="3f498-137">例如：</span><span class="sxs-lookup"><span data-stu-id="3f498-137">For example:</span></span>


- <span data-ttu-id="3f498-138">在酒店、咖啡店和机场中发现的很多热点仍仅使用 2.4 GHz，如果带区仅设置为 5 GHz，则可以有效地阻止对设备的访问。</span><span class="sxs-lookup"><span data-stu-id="3f498-138">Many hotspots found in hotels, coffee shops, and airports still only use 2.4 GHz, effectively blocking access to devices if Band is set to 5 GHz Only.</span></span>
- <span data-ttu-id="3f498-139">由于 Miracast 无线显示器连接要求通过 2.4 GHz 通道完成初始握手，因此设备将无法仅以 5 GHz 的方式连接。</span><span class="sxs-lookup"><span data-stu-id="3f498-139">Since Miracast wireless display connections require the initial handshake to be completed over 2.4 GHz channels, devices won’t be able to connect at 5 GHz Only.</span></span>

> [!NOTE]
> <span data-ttu-id="3f498-140">默认情况下，Surface 设备将首选连接到 5 GHz （如果可用）。</span><span class="sxs-lookup"><span data-stu-id="3f498-140">By default Surface devices will prefer connecting to 5 GHz if available.</span></span> <span data-ttu-id="3f498-141">但是，为了在电池电量不足的情况下保持通电，Surface 将首先查找 2.4 GHz 连接。</span><span class="sxs-lookup"><span data-stu-id="3f498-141">However, to preserve power  in a low battery state, Surface will first look for a 2.4 GHz connection.</span></span>

<span data-ttu-id="3f498-142">您也可以根据需要切换带区设置以适合您的环境。</span><span class="sxs-lookup"><span data-stu-id="3f498-142">You can also toggle the band setting as needed to suit your environment.</span></span> <span data-ttu-id="3f498-143">例如，生活在具有多个 Wi-Fi 热点的高密度公寓建筑中的用户（使用 2.4 GHz 的所有广播），将其 Surface 设备设置为仅 5 GHz 的连接，并在需要时恢复为自动，这可能会带来好处。</span><span class="sxs-lookup"><span data-stu-id="3f498-143">For example, users living in high density apartment buildings with multiple Wi-Fi hotspots  —  amid the presence of consumer devices all broadcasting via 2.4 GHz  —  will likely benefit by setting their Surface device to connect on 5 GHz only and then revert to Auto when needed.</span></span>

### <span data-ttu-id="3f498-144">带有英特尔适配器的 Surface 设备上的漫游入侵设置</span><span class="sxs-lookup"><span data-stu-id="3f498-144">Roaming aggressiveness settings on Surface devices with Intel adapters</span></span> 

<span data-ttu-id="3f498-145">用户可能希望选择 "信号强度阈值"，以提示设备在信号丢弃 (漫游入侵) 时搜索新接入点。</span><span class="sxs-lookup"><span data-stu-id="3f498-145">Users may wish to select a signal strength threshold that prompts the device to search for a new access point when the signal drops (roaming aggressiveness).</span></span> <span data-ttu-id="3f498-146">默认情况下，带有 Intel 适配器的 Surface 设备尝试漫游到新的接入点，前提是信号强度降至 **中等** (72% 的信号强度) 。</span><span class="sxs-lookup"><span data-stu-id="3f498-146">By default, Surface devices with Intel adapters attempt to roam to a new access point if the signal strength drops below **Medium** (72 percent signal strength).</span></span> <span data-ttu-id="3f498-147">另请注意，组织可以跨多个网络访问点实现专门构建的无线协议，以方便漫游网络环境，如本页面前面所述。</span><span class="sxs-lookup"><span data-stu-id="3f498-147">Note also that organizations can implement purpose-built wireless protocols across multiple network access points to facilitate roaming congested network environments, as explained earlier on this page.</span></span> 

<span data-ttu-id="3f498-148">在高拥挤的 office 或家庭环境中提高漫游入侵的同时 **，可能会** 导致在这些环境外进行步进时的连接性下降。</span><span class="sxs-lookup"><span data-stu-id="3f498-148">While increasing roaming aggressiveness above **Medium** may yield improved connectivity in highly congested office or residential environments, it can result in degraded connectivity when stepping outside of these environments.</span></span> 

<span data-ttu-id="3f498-149">建议在默认状态下保留漫游入侵设置，除非在特定移动方案中遇到连接问题，例如，在会议会议期间执行环境网站检查，同时保持语音和视频连接。</span><span class="sxs-lookup"><span data-stu-id="3f498-149">It’s recommended to leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="3f498-150">如果未注意到任何改进，请还原到默认介质状态。</span><span class="sxs-lookup"><span data-stu-id="3f498-150">If you don’t notice any improvement, revert to the default Medium state.</span></span> <span data-ttu-id="3f498-151">请注意，如果增加漫游入侵，还可以提高电池能耗。</span><span class="sxs-lookup"><span data-stu-id="3f498-151">Note that if you increase roaming aggressiveness, you also accelerate battery power consumption.</span></span> 

**<span data-ttu-id="3f498-152">要在 Surface 上启用漫游入侵，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3f498-152">To enable roaming aggressiveness on Surface:</span></span>**

1. <span data-ttu-id="3f498-153">转到 "**开始**  >  **设备管理器**"。</span><span class="sxs-lookup"><span data-stu-id="3f498-153">Go to **Start** > **Device Manager**.</span></span>
2. <span data-ttu-id="3f498-154">在 " **网络适配器** " 下选择 " **英特尔 Wi-Fi 6** "，然后右键单击 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="3f498-154">Under **Network adapters** select **Intel Wi-Fi 6** and then right click **Properties**.</span></span>
3. <span data-ttu-id="3f498-155">选择 " **高级** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3f498-155">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="3f498-156">选择 " **漫游入侵** "，然后从下拉菜单中选择您的首选值。</span><span class="sxs-lookup"><span data-stu-id="3f498-156">Select **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 漫游入侵设置-英特尔 \*](images/wifi-roaming-int.png) <br>

### <span data-ttu-id="3f498-158">Surface Go 和 Surface Pro X 上的漫游入侵设置</span><span class="sxs-lookup"><span data-stu-id="3f498-158">Roaming aggressiveness settings on Surface Go and Surface Pro X</span></span>

<span data-ttu-id="3f498-159">使用 Surface Go 的前线工作者可能希望选择信号强度阈值，当信号强度下降 (漫游入侵) 时，该阈值会提示设备搜索新接入点。</span><span class="sxs-lookup"><span data-stu-id="3f498-159">Front-line workers using Surface Go may wish to select a signal strength threshold that prompts the device to search for a new access point when signal strength drops (roaming aggressiveness).</span></span> <span data-ttu-id="3f498-160">默认情况下，如果信号强度低于 **中等** (50% 的信号) 强度，则 Surface 设备将尝试漫游到新的接入点。</span><span class="sxs-lookup"><span data-stu-id="3f498-160">By default, Surface devices attempt to roam to a new access point if the signal strength drops below **Medium** (50 percent signal strength).</span></span> <span data-ttu-id="3f498-161">请注意，无论何时增加漫游入侵，都可以加速电池电量消耗。</span><span class="sxs-lookup"><span data-stu-id="3f498-161">Note that whenever you increase roaming aggressiveness, you accelerate battery power consumption.</span></span>

<span data-ttu-id="3f498-162">除非在特定移动方案中遇到连接问题（例如，在会议会议期间执行环境网站检查，同时保持语音和视频连接），否则将漫游入侵设置保留为默认状态。</span><span class="sxs-lookup"><span data-stu-id="3f498-162">Leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="3f498-163">如果你没有注意到任何改进将还原为默认 **介质** 状态。</span><span class="sxs-lookup"><span data-stu-id="3f498-163">If you don’t notice any improvement revert to the default **Medium** state.</span></span>

**<span data-ttu-id="3f498-164">要在表面上启用漫游入侵，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3f498-164">To enable roaming aggressiveness on Surface Go:</span></span>**

1. <span data-ttu-id="3f498-165">转到 **"开始" > 控制面板**  >  **网络和 Internet**  >  **网络以及 "共享中心"。**</span><span class="sxs-lookup"><span data-stu-id="3f498-165">Go to **Start > Control Panel** > **Network and Internet** > **Network and Sharing Center.**</span></span>
2. <span data-ttu-id="3f498-166">在 " **连接** " 下，选择 " **wi-fi** "，然后选择 " **属性"。**</span><span class="sxs-lookup"><span data-stu-id="3f498-166">Under **Connections** select **Wi-Fi** and then select **Properties.**</span></span>
3. <span data-ttu-id="3f498-167">**为 Microsoft 网络选择 "客户端**"，然后选择 "**配置**"</span><span class="sxs-lookup"><span data-stu-id="3f498-167">Select **Client for Microsoft Networks** and then select **Configure**</span></span>
4. <span data-ttu-id="3f498-168">选择 "**高级**  >  **漫游入侵**"，然后从下拉菜单中选择您的首选值。</span><span class="sxs-lookup"><span data-stu-id="3f498-168">Select **Advanced** > **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 漫游入侵设置-QualComm \*](images/wifi-roaming.png) <br>


## <span data-ttu-id="3f498-170">总结</span><span class="sxs-lookup"><span data-stu-id="3f498-170">Conclusion</span></span>

<span data-ttu-id="3f498-171">Surface 设备设计了默认设置以实现最佳无线连接平衡，并且需要保留电池寿命。</span><span class="sxs-lookup"><span data-stu-id="3f498-171">Surface devices are designed with default settings for optimal wireless connectivity balanced alongside the need to preserve battery life.</span></span> <span data-ttu-id="3f498-172">为 Surface 设备启用可靠连接的最有效方式是使用支持 802.11 r 和 802.11 k 的精心设计的网络。</span><span class="sxs-lookup"><span data-stu-id="3f498-172">The most effective way of enabling reliable connectivity for Surface devices is through a well-designed network that supports 802.11r and 802.11k.</span></span> <span data-ttu-id="3f498-173">用户可以调整网络适配器设置或漫游入侵，但应仅针对特定的环境因素执行此操作，如果没有显著改进，则还原为默认状态。</span><span class="sxs-lookup"><span data-stu-id="3f498-173">Users can adjust network adapter settings or roaming aggressiveness but should only do so in response to specific environmental factors and revert to default state if there’s no noticeable improvement.</span></span>

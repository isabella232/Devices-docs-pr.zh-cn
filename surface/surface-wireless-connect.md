---
title: 优化 Surface 设备的 WLAN 连接
description: 本主题介绍了建议的 Wi-fi 设置，以确保 Surface 设备在网络环境和移动方案中的拥挤保持连接。
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
ms.openlocfilehash: 2fb64f86e3c1da0e4ba3834877548898e98fd893
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830999"
---
# <span data-ttu-id="05b6e-103">优化 Surface 设备的 WLAN 连接</span><span class="sxs-lookup"><span data-stu-id="05b6e-103">Optimize Wi-Fi connectivity for Surface devices</span></span>


<span data-ttu-id="05b6e-104">为了保持全天的电池使用时间，Surface 设备实现可平衡性能和节能的无线连接设置。</span><span class="sxs-lookup"><span data-stu-id="05b6e-104">To stay connected with all-day battery life, Surface devices implement wireless connectivity settings that balance performance and power conservation.</span></span> <span data-ttu-id="05b6e-105">在最苛刻的移动方案之外，用户可以保持足够的无线连接，而无需修改默认网络适配器或相关设置。</span><span class="sxs-lookup"><span data-stu-id="05b6e-105">Outside of the most demanding mobility scenarios, users can maintain sufficient wireless connectivity without modifying default network adapter or related settings.</span></span> 

<span data-ttu-id="05b6e-106">在拥挤的网络环境中，组织可以跨多个网络访问点实现专门构建的无线协议，以便于漫游。</span><span class="sxs-lookup"><span data-stu-id="05b6e-106">In congested network environments, organizations can implement purpose-built wireless protocols across multiple network access points to facilitate roaming.</span></span> <span data-ttu-id="05b6e-107">本页重点介绍了使用 Surface Pro 3 及更高版本、Surface Book、Surface 笔记本电脑和 Surface Go 的移动方案中的关键无线连接注意事项。</span><span class="sxs-lookup"><span data-stu-id="05b6e-107">This page highlights key wireless connectivity considerations in mobile scenarios utilizing Surface Pro 3 and later, Surface Book, Surface Laptop, and Surface Go.</span></span>

## <span data-ttu-id="05b6e-108">必备条件</span><span class="sxs-lookup"><span data-stu-id="05b6e-108">Prerequisites</span></span>

<span data-ttu-id="05b6e-109">本文档假设你已成功部署支持 802.11 n （Wi-fi 4）或更高版本的无线网络，符合来自主要设备供应商的最佳做法建议。</span><span class="sxs-lookup"><span data-stu-id="05b6e-109">This document assumes you have successfully deployed a wireless network that supports 802.11n (Wi-Fi 4) or later in accordance with best practice recommendations from leading equipment vendors.</span></span>

## <span data-ttu-id="05b6e-110">为最佳漫游功能配置接入点</span><span class="sxs-lookup"><span data-stu-id="05b6e-110">Configuring access points for optimal roaming capabilities</span></span>

<span data-ttu-id="05b6e-111">如果你管理的无线网络通常由许多不同类型的客户端设备进行访问，建议在你的 WLAN 中启用接入点（Ap）上的特定协议，如[使用 802.11 k、802.11 v 和 802.11 r 进行快速漫游](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)中所述。</span><span class="sxs-lookup"><span data-stu-id="05b6e-111">If you’re managing a wireless network that’s typically accessed by many different types of client devices, it’s recommended to enable specific protocols on access points (APs) in your WLAN, as described in [Fast Roaming with 802.11k, 802.11v, and 802.11r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r).</span></span> <span data-ttu-id="05b6e-112">Surface 设备可以利用下列无线协议：</span><span class="sxs-lookup"><span data-stu-id="05b6e-112">Surface devices can take advantage of the following wireless protocols:</span></span>

- **<span data-ttu-id="05b6e-113">802.11 r。</span><span class="sxs-lookup"><span data-stu-id="05b6e-113">802.11r.</span></span>** <span data-ttu-id="05b6e-114">"**快速 BSS 过渡"** 通过减少在使用设备移动设备时设备可以访问其他 AP 所需的帧数，加速连接到新的无线访问点。</span><span class="sxs-lookup"><span data-stu-id="05b6e-114">“**Fast BSS Transition”** accelerates connecting to new wireless access points by reducing the number of frames required before your device can access another AP as you move around with your device.</span></span>
- **<span data-ttu-id="05b6e-115">802.11 k。</span><span class="sxs-lookup"><span data-stu-id="05b6e-115">802.11k.</span></span>** <span data-ttu-id="05b6e-116">**"邻居报告"** 为设备提供有关邻近访问点上的当前条件的信息。</span><span class="sxs-lookup"><span data-stu-id="05b6e-116">**“Neighbor Reports”** provides devices with information on current conditions at neighboring access points.</span></span> <span data-ttu-id="05b6e-117">它可以帮助 Surface 设备使用信号强度（如 AP 利用率）以外的其他条件选择最佳 AP。</span><span class="sxs-lookup"><span data-stu-id="05b6e-117">It can help your Surface device choose the best AP using criteria other than signal strength such as AP utilization.</span></span>

<span data-ttu-id="05b6e-118">特定的 Surface 设备还可以使用 802.11 v "BSS 转换管理帧"，这与在提供附近的候选 Ap 相关信息的 802.11 k 非常类似。</span><span class="sxs-lookup"><span data-stu-id="05b6e-118">Specific Surface devices can also use 802.11v “BSS Transition Management Frames,” which functions much like 802.11k in providing information on nearby candidate APs.</span></span> <span data-ttu-id="05b6e-119">其中包括 Surface Go、Surface Pro 7、Surface Pro X 和 Surface 膝上型电脑3。</span><span class="sxs-lookup"><span data-stu-id="05b6e-119">These include Surface Go, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

## <span data-ttu-id="05b6e-120">管理用户设置</span><span class="sxs-lookup"><span data-stu-id="05b6e-120">Managing user settings</span></span>

<span data-ttu-id="05b6e-121">你可以通过在所有访问点上支持 802.11 r 和 802.11 k 的精心设计的网络实现最佳漫游功能。</span><span class="sxs-lookup"><span data-stu-id="05b6e-121">You can achieve optimal roaming capabilities through a well-designed network that supports  802.11r and 802.11k across all access points.</span></span> <span data-ttu-id="05b6e-122">确保您的网络正确配置为为用户提供最佳无线体验是推荐的方法，与尝试管理单个设备上的用户设置相比。</span><span class="sxs-lookup"><span data-stu-id="05b6e-122">Ensuring that your network is properly configured to provide users with the best wireless experience is the recommended approach versus attempting to manage user settings on individual devices.</span></span> <span data-ttu-id="05b6e-123">此外，在许多公司环境中，设备用户无法在没有显式权限或本地管理员权限的情况下访问高级网络适配器设置。</span><span class="sxs-lookup"><span data-stu-id="05b6e-123">Moreover, in many corporate environments Surface device users won’t be able to access advanced network adapter settings without explicit permissions or local admin rights.</span></span> <span data-ttu-id="05b6e-124">在其他较轻的托管网络中，用户可以通过了解特定设置对保持连接的能力有何影响来获得好处。</span><span class="sxs-lookup"><span data-stu-id="05b6e-124">In other lightly managed networks, users can benefit by knowing how specific settings can impact their ability to remain connected.</span></span>

### <span data-ttu-id="05b6e-125">推荐的用户设置和最佳做法</span><span class="sxs-lookup"><span data-stu-id="05b6e-125">Recommended user settings and best practices</span></span>

<span data-ttu-id="05b6e-126">在某些情况下，修改内置于 Surface 设备的高级网络适配器设置有助于实现更可靠的连接。</span><span class="sxs-lookup"><span data-stu-id="05b6e-126">In certain situations, modifying advanced network adapter settings built into Surface devices may facilitate a more reliable connection.</span></span> <span data-ttu-id="05b6e-127">请记住，由于访问点问题、网络设计缺陷或环境网站问题，无法连接到无线资源会更频繁。</span><span class="sxs-lookup"><span data-stu-id="05b6e-127">Keep in mind however that an inability to connect to wireless resources is more often due to an access point issue, networking design flaw, or environmental site issue.</span></span>

> [!NOTE]
> <span data-ttu-id="05b6e-128">保持 Surface Pro 或 Surface Go 的方式也会影响信号强度。</span><span class="sxs-lookup"><span data-stu-id="05b6e-128">How you hold your Surface Pro or Surface Go can also affect signal strength.</span></span> <span data-ttu-id="05b6e-129">如果您遇到带宽丢失的情况，请检查您不在屏幕顶部的位置（Wi-fi 无线电接收器所在的位置）。</span><span class="sxs-lookup"><span data-stu-id="05b6e-129">If you’re experiencing a loss of bandwidth, check that you’re not holding the top of the display, where the Wi-Fi radio receiver is located.</span></span> <span data-ttu-id="05b6e-130">尽管保持显示屏顶部不会阻止无线信号，但它可以触发设备驱动程序以启动减少连接的更改。</span><span class="sxs-lookup"><span data-stu-id="05b6e-130">Although holding the top of the display does not block wireless signals, it can trigger the device driver to initiate changes that reduce connectivity.</span></span>

### <span data-ttu-id="05b6e-131">保留双带宽功能的默认自动设置</span><span class="sxs-lookup"><span data-stu-id="05b6e-131">Keep default Auto setting for dual bandwidth capability</span></span>
<span data-ttu-id="05b6e-132">在大多数 Surface 设备上，你可以将客户端网络适配器设置配置为仅连接到超过5千赫兹（GHz）的无线 Ap，仅通过 2.4 GHz 连接，或者让操作系统选择最佳选项（默认自动设置）。</span><span class="sxs-lookup"><span data-stu-id="05b6e-132">On most Surface devices, you can configure client network adapter settings to only connect to wireless APs over 5 gigahertz (GHz), only connect over 2.4 GHz, or let the operating system choose the best option (default Auto setting).</span></span>

**<span data-ttu-id="05b6e-133">若要访问网络适配器设置，请转到：</span><span class="sxs-lookup"><span data-stu-id="05b6e-133">To access network adapter settings go to:</span></span>**

- <span data-ttu-id="05b6e-134">**开始**  > **"控制面板"**  > **网络和共享中心**  > **wi-fi 适配器**  > **属性**  > **配置**  > **高级**。</span><span class="sxs-lookup"><span data-stu-id="05b6e-134">**Start** > **Control panel** > **Network and Sharing Center** > **your Wi-Fi adapter** > **Properties** > **Configure** > **Advanced**.</span></span>

![\* wifi 频带设置 \*](images/wifi-band.png) <br>

<span data-ttu-id="05b6e-136">请记住，2.4 GHz 有比 5 GHz 更多的优势：它通过墙壁或其他实体对象进一步、更轻松地 penetrates 扩展。</span><span class="sxs-lookup"><span data-stu-id="05b6e-136">Keep in mind that 2.4 GHz has some advantages over 5 GHz: It extends further and more easily penetrates through walls or other solid objects.</span></span> <span data-ttu-id="05b6e-137">除非你有一个明确的用例需要连接到 5 GHz，否则建议将波段设置保留为默认状态，以避免潜在的不利后果。</span><span class="sxs-lookup"><span data-stu-id="05b6e-137">Unless you have a clear use case that warrants connecting to 5 GHz, it’s recommended to leave the Band setting in the default state to avoid possible adverse consequences.</span></span> <span data-ttu-id="05b6e-138">例如：</span><span class="sxs-lookup"><span data-stu-id="05b6e-138">For example:</span></span>


- <span data-ttu-id="05b6e-139">在酒店、咖啡店和机场中发现的很多热点仍仅使用 2.4 GHz，如果带区仅设置为 5 GHz，则可以有效地阻止对设备的访问。</span><span class="sxs-lookup"><span data-stu-id="05b6e-139">Many hotspots found in hotels, coffee shops, and airports still only use 2.4 GHz, effectively blocking access to devices if Band is set to 5 GHz Only.</span></span>
- <span data-ttu-id="05b6e-140">由于 Miracast 无线显示器连接要求通过 2.4 GHz 通道完成初始握手，因此设备将无法仅以 5 GHz 的方式连接。</span><span class="sxs-lookup"><span data-stu-id="05b6e-140">Since Miracast wireless display connections require the initial handshake to be completed over 2.4 GHz channels, devices won’t be able to connect at 5 GHz Only.</span></span>

> [!NOTE]
> <span data-ttu-id="05b6e-141">默认情况下，Surface 设备将首选连接到 5 GHz （如果可用）。</span><span class="sxs-lookup"><span data-stu-id="05b6e-141">By default Surface devices will prefer connecting to 5 GHz if available.</span></span> <span data-ttu-id="05b6e-142">但是，为了在电池电量不足的情况下保持通电，Surface 将首先查找 2.4 GHz 连接。</span><span class="sxs-lookup"><span data-stu-id="05b6e-142">However, to preserve power  in a low battery state, Surface will first look for a 2.4 GHz connection.</span></span>

<span data-ttu-id="05b6e-143">您也可以根据需要切换带区设置以适合您的环境。</span><span class="sxs-lookup"><span data-stu-id="05b6e-143">You can also toggle the band setting as needed to suit your environment.</span></span> <span data-ttu-id="05b6e-144">例如，居住在具有多个 Wi-fi 热点的高密度单元建筑物（使用所有客户设备通过 2.4 GHz 进行广播）中的用户将有可能受益，只需将其 Surface 设备设置为仅 5 GHz 连接，然后在需要时恢复为自动。</span><span class="sxs-lookup"><span data-stu-id="05b6e-144">For example, users living in high density apartment buildings with multiple Wi-Fi hotspots  —  amid the presence of consumer devices all broadcasting via 2.4 GHz  —  will likely benefit by setting their Surface device to connect on 5 GHz only and then revert to Auto when needed.</span></span>

### <span data-ttu-id="05b6e-145">Surface Go 上的漫游入侵设置</span><span class="sxs-lookup"><span data-stu-id="05b6e-145">Roaming aggressiveness settings on Surface Go</span></span>

<span data-ttu-id="05b6e-146">使用 Surface Go 的前线工作者可能希望选择信号强度阈值，当信号强度下降（漫游入侵）时，系统会提示设备搜索新接入点。</span><span class="sxs-lookup"><span data-stu-id="05b6e-146">Front-line workers using Surface Go may wish to select a signal strength threshold that prompts the device to search for a new access point when signal strength drops (roaming aggressiveness).</span></span> <span data-ttu-id="05b6e-147">默认情况下，如果信号强度降到 "**中**" （50% 信号强度）以下，则 Surface 设备会尝试漫游到新的接入点。</span><span class="sxs-lookup"><span data-stu-id="05b6e-147">By default, Surface devices attempt to roam to a new access point if the signal strength drops below **Medium** (50 percent signal strength).</span></span> <span data-ttu-id="05b6e-148">请注意，无论何时增加漫游入侵，都可以加速电池电量消耗。</span><span class="sxs-lookup"><span data-stu-id="05b6e-148">Note that whenever you increase roaming aggressiveness, you accelerate battery power consumption.</span></span>

<span data-ttu-id="05b6e-149">除非在特定移动方案中遇到连接问题（例如，在会议会议期间执行环境网站检查，同时保持语音和视频连接），否则将漫游入侵设置保留为默认状态。</span><span class="sxs-lookup"><span data-stu-id="05b6e-149">Leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="05b6e-150">如果你没有注意到任何改进将还原为默认**介质**状态。</span><span class="sxs-lookup"><span data-stu-id="05b6e-150">If you don’t notice any improvement revert to the default **Medium** state.</span></span>

**<span data-ttu-id="05b6e-151">要在表面上启用漫游入侵，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="05b6e-151">To enable roaming aggressiveness on Surface Go:</span></span>**

1. <span data-ttu-id="05b6e-152">转到 **"开始" > 控制面板**  >  **网络和 Internet**  >  **网络以及 "共享中心"。**</span><span class="sxs-lookup"><span data-stu-id="05b6e-152">Go to **Start > Control Panel** > **Network and Internet** > **Network and Sharing Center.**</span></span>
2. <span data-ttu-id="05b6e-153">在 "**连接**" 下，选择 " **wi-fi** "，然后选择 "**属性"。**</span><span class="sxs-lookup"><span data-stu-id="05b6e-153">Under **Connections** select **Wi-Fi** and then select **Properties.**</span></span>
3. <span data-ttu-id="05b6e-154">**为 Microsoft 网络选择 "客户端**"，然后选择 "**配置**"</span><span class="sxs-lookup"><span data-stu-id="05b6e-154">Select **Client for Microsoft Networks** and then select **Configure**</span></span>
4. <span data-ttu-id="05b6e-155">选择 "**高级**  >  **漫游入侵**"，然后从下拉菜单中选择您的首选值。</span><span class="sxs-lookup"><span data-stu-id="05b6e-155">Select **Advanced** > **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 漫游入侵设置 \*](images/wifi-roaming.png) <br>

## <span data-ttu-id="05b6e-157">总结</span><span class="sxs-lookup"><span data-stu-id="05b6e-157">Conclusion</span></span>

<span data-ttu-id="05b6e-158">Surface 设备设计了默认设置以实现最佳无线连接平衡，并且需要保留电池寿命。</span><span class="sxs-lookup"><span data-stu-id="05b6e-158">Surface devices are designed with default settings for optimal wireless connectivity balanced alongside the need to preserve battery life.</span></span> <span data-ttu-id="05b6e-159">为 Surface 设备启用可靠连接的最有效方式是使用支持 802.11 r 和 802.11 k 的精心设计的网络。</span><span class="sxs-lookup"><span data-stu-id="05b6e-159">The most effective way of enabling reliable connectivity for Surface devices is through a well-designed network that supports 802.11r and 802.11k.</span></span> <span data-ttu-id="05b6e-160">用户可以调整网络适配器设置或漫游入侵，但应仅针对特定的环境因素执行此操作，如果没有显著改进，则还原为默认状态。</span><span class="sxs-lookup"><span data-stu-id="05b6e-160">Users can adjust network adapter settings or roaming aggressiveness but should only do so in response to specific environmental factors and revert to default state if there’s no noticeable improvement.</span></span>

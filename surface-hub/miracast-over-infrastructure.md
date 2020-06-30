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
ms.openlocfilehash: d63b3de0f76cb70fe86fff246d82cbe166278461
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832195"
---
# <span data-ttu-id="6d251-103">基础架构上的 Miracast</span><span class="sxs-lookup"><span data-stu-id="6d251-103">Miracast over infrastructure</span></span>

<span data-ttu-id="6d251-104">在 Windows 10 版本 1703 上，Microsoft 的功能经过扩展，可以通过本地网络而不是直接无线链接发送 Miracast 流。</span><span class="sxs-lookup"><span data-stu-id="6d251-104">In the Windows 10, version 1703, Microsoft has extended the ability to send a Miracast stream over a local network rather than over a direct wireless link.</span></span> <span data-ttu-id="6d251-105">此功能基于[基础结构上的 Miracast 连接建立协议 (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6d251-105">This functionality is based on the [Miracast over Infrastructure Connection Establishment Protocol (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx).</span></span>

<span data-ttu-id="6d251-106">基础结构上的 Miracast 具有以下多项优势：</span><span class="sxs-lookup"><span data-stu-id="6d251-106">Miracast over Infrastructure offers a number of benefits:</span></span>

- <span data-ttu-id="6d251-107">Windows 可以自动检测通过此路径发送视频流的合适时间。</span><span class="sxs-lookup"><span data-stu-id="6d251-107">Windows automatically detects when sending the video stream over this path is applicable.</span></span>
- <span data-ttu-id="6d251-108">仅当通过以太网或安全的 WLAN 网络进行连接时，Windows 才将选择此路径。</span><span class="sxs-lookup"><span data-stu-id="6d251-108">Windows will only choose this route if the connection is over Ethernet or a secure Wi-Fi network.</span></span>
- <span data-ttu-id="6d251-109">用户无需更改其与 Miracast 接收器的连接方式。</span><span class="sxs-lookup"><span data-stu-id="6d251-109">Users do not have to change how they connect to a Miracast receiver.</span></span> <span data-ttu-id="6d251-110">他们使用用于标准 Miracast 连接的相同 UX。</span><span class="sxs-lookup"><span data-stu-id="6d251-110">They use the same UX as for standard Miracast connections.</span></span>
- <span data-ttu-id="6d251-111">无需更改当前无线驱动程序或电脑硬件。</span><span class="sxs-lookup"><span data-stu-id="6d251-111">No changes to current wireless drivers or PC hardware are required.</span></span>
- <span data-ttu-id="6d251-112">它非常适用于未针对 WLAN Direct 上的 Miracast 进行优化的旧版无线硬件。</span><span class="sxs-lookup"><span data-stu-id="6d251-112">It works well with older wireless hardware that is not optimized for Miracast over Wi-Fi Direct.</span></span>
- <span data-ttu-id="6d251-113">它利用了现有连接，这既缩短了连接时间，也提供了非常稳定的流。</span><span class="sxs-lookup"><span data-stu-id="6d251-113">It leverages an existing connection which both reduces the time to connect and provides a very stable stream.</span></span>


## <span data-ttu-id="6d251-114">工作原理</span><span class="sxs-lookup"><span data-stu-id="6d251-114">How it works</span></span>

<span data-ttu-id="6d251-115">用户尝试通过其 Wi-fi 适配器连接到 Miracast 接收器，就像以前一样。</span><span class="sxs-lookup"><span data-stu-id="6d251-115">Users attempt to connect to a Miracast receiver through their Wi-Fi adapter as they did previously.</span></span> <span data-ttu-id="6d251-116">填充 Miracast 接收器列表时，Windows 10 将确认接收器是否能够支持通过基础结构进行连接。</span><span class="sxs-lookup"><span data-stu-id="6d251-116">When the list of Miracast receivers is populated, Windows 10 will identify that the receiver is capable of supporting a connection over the infrastructure.</span></span> <span data-ttu-id="6d251-117">当用户选择 Miracast 接收器时，Windows 10 将尝试通过标准 DNS 以及多播 DNS (mDNS) 解析设备的主机名。</span><span class="sxs-lookup"><span data-stu-id="6d251-117">When the user selects a Miracast receiver, Windows 10 will attempt to resolve the device's hostname via standard DNS, as well as via multicast DNS (mDNS).</span></span> <span data-ttu-id="6d251-118">如果名称无法通过任何一种 DNS 方法解析，则 Windows 10 将回退到使用标准 WLAN Direct 连接建立 Miracast 会话。</span><span class="sxs-lookup"><span data-stu-id="6d251-118">If the name is not resolvable via either DNS method, Windows 10 will fall back to establishing the Miracast session using the standard Wi-Fi direct connection.</span></span>

> [!NOTE]
> <span data-ttu-id="6d251-119">有关连接协商顺序的详细信息，请参阅[基础结构连接建立协议（MS-鼠标）](https://msdn.microsoft.com/library/mt796768.aspx)上的 Miracast</span><span class="sxs-lookup"><span data-stu-id="6d251-119">For more information on the connection negotiation sequence, see [Miracast over Infrastructure Connection Establishment Protocol (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx)</span></span>




## <span data-ttu-id="6d251-120">启用基础结构上的 Miracast</span><span class="sxs-lookup"><span data-stu-id="6d251-120">Enabling Miracast over Infrastructure</span></span> 

<span data-ttu-id="6d251-121">如果你的 Surface Hub 或其他 Windows 10 设备已更新至 Windows 10 版本 1703，则你将自动具有此新功能。</span><span class="sxs-lookup"><span data-stu-id="6d251-121">If you have a Surface Hub or other Windows 10 device that has been updated to Windows 10, version 1703, then you automatically have this new feature.</span></span> <span data-ttu-id="6d251-122">若要在你的环境中充分利用此功能，你需要确保部署中以下条件成立：</span><span class="sxs-lookup"><span data-stu-id="6d251-122">To take advantage of it in your environment, you need to ensure the following is true within your deployment:</span></span>

- <span data-ttu-id="6d251-123">Surface Hub 或设备（Windows 电脑或手机）需要运行 Windows 10 版本 1703。</span><span class="sxs-lookup"><span data-stu-id="6d251-123">The Surface Hub or device (Windows PC or phone) needs to be running Windows 10, version 1703.</span></span>
- <span data-ttu-id="6d251-124">打开 TCP 端口： **7250**。</span><span class="sxs-lookup"><span data-stu-id="6d251-124">Open TCP port: **7250**.</span></span>
- <span data-ttu-id="6d251-125">Surface Hub 或 Windows 电脑可充当基础结构上的 Miracast 的*接收器*。</span><span class="sxs-lookup"><span data-stu-id="6d251-125">A Surface Hub or Windows PC can act as a Miracast over Infrastructure *receiver*.</span></span> <span data-ttu-id="6d251-126">Windows 电脑或手机可充当基础结构上的 Miracast 的*源*。</span><span class="sxs-lookup"><span data-stu-id="6d251-126">A Windows PC or phone can act as a Miracast over Infrastructure *source*.</span></span>
    - <span data-ttu-id="6d251-127">作为 Miracast 接收器，Surface Hub 或设备必须通过以太网或安全的 WLAN 连接（如使用 WPA2-PSK 或 WPA2-企业安全功能）连接至企业网络。</span><span class="sxs-lookup"><span data-stu-id="6d251-127">As a Miracast receiver, the Surface Hub or device must be connected to your enterprise network via either Ethernet or a secure Wi-Fi connection (e.g. using either WPA2-PSK or WPA2-Enterprise security).</span></span> <span data-ttu-id="6d251-128">如果 Surface Hub 或设备连接到打开的 Wlan 连接，则基础结构上的 Miracast 将禁用自身。</span><span class="sxs-lookup"><span data-stu-id="6d251-128">If the Surface Hub or device is connected to an open Wi-Fi connection, Miracast over Infrastructure will disable itself.</span></span>
    - <span data-ttu-id="6d251-129">作为 Miracast 源，Windows 电脑或手机必须通过以太网或安全的 WLAN 连接来连接至相同的企业网络。</span><span class="sxs-lookup"><span data-stu-id="6d251-129">As a Miracast source, the Windows PC or phone must be connected to the same enterprise network via Ethernet or a secure Wi-Fi connection.</span></span>
- <span data-ttu-id="6d251-130">Surface Hub 或设备的 DNS 主机名（设备名称）需要可通过 DNS 服务器解析。</span><span class="sxs-lookup"><span data-stu-id="6d251-130">The DNS Hostname (device name) of the Surface Hub or device needs to be resolvable via your DNS servers.</span></span> <span data-ttu-id="6d251-131">通过允许 Surface Hub 通过动态 DNS 自动注册，或者通过为 Surface Hub 主机名手动创建 A 或 AAAA 记录，你可以达到此目的。</span><span class="sxs-lookup"><span data-stu-id="6d251-131">You can achieve this by either allowing your Surface Hub to register automatically via Dynamic DNS, or by manually creating an A or AAAA record for the Surface Hub's hostname.</span></span> 
- <span data-ttu-id="6d251-132">Windows 10 电脑必须通过以太网或安全的 WLAN 连接来连接至相同的企业网络。</span><span class="sxs-lookup"><span data-stu-id="6d251-132">Windows 10 PCs must be connected to the same enterprise network via Ethernet or a secure Wi-Fi connection.</span></span> 
-   <span data-ttu-id="6d251-133">在 Windows 10 Pc 上，必须在 "系统设置" 中启用 "**投影到这台电脑**" 功能，并且设备必须启用 wi-fi 界面才能响应仅通过 wi-fi 适配器发生的发现请求。</span><span class="sxs-lookup"><span data-stu-id="6d251-133">On Windows 10 PCs, the **Projecting to this PC** feature must be enabled in System Settings, and the device must have a Wi-Fi interface enabled in order to respond to discovery requests that only occur through the Wi-Fi adapter.</span></span>


<span data-ttu-id="6d251-134">请务必注意，基础结构上的 Miracast 并不能替代标准 Miracast。</span><span class="sxs-lookup"><span data-stu-id="6d251-134">It is important to note that Miracast over Infrastructure is not a replacement for standard Miracast.</span></span> <span data-ttu-id="6d251-135">相反，此功能可作为补充，并且可以为企业网络中的用户带来优势。</span><span class="sxs-lookup"><span data-stu-id="6d251-135">Instead, the functionality is complementary, and provides an advantage to users who are part of the enterprise network.</span></span> <span data-ttu-id="6d251-136">作为特定位置的来宾且无企业网络访问权限的用户将继续使用 WLAN Direct 连接方法进行连接。</span><span class="sxs-lookup"><span data-stu-id="6d251-136">Users who are guests to a particular location and don’t have access to the enterprise network will continue to connect using the Wi-Fi Direct connection method.</span></span>

<span data-ttu-id="6d251-137">基础结构上的 Miracast 不需要 [SurfaceHub 配置服务提供程序 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) 中的 **InBoxApps/WirelessProjection/PinRequired** 设置。</span><span class="sxs-lookup"><span data-stu-id="6d251-137">The **InBoxApps/WirelessProjection/PinRequired** setting in the [SurfaceHub configuration service provider (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) is not required for Miracast over Infrastructure.</span></span> <span data-ttu-id="6d251-138">这是因为仅当两台设备连接到同一企业网络时，基础结构上的 Miracast 才能工作。</span><span class="sxs-lookup"><span data-stu-id="6d251-138">This is because Miracast over Infrastructure only works when both devices are connected to the same enterprise network.</span></span> <span data-ttu-id="6d251-139">这将删除 Miracast 以前缺少的安全限制。</span><span class="sxs-lookup"><span data-stu-id="6d251-139">This removes the security restriction that was previously missing from Miracast.</span></span> <span data-ttu-id="6d251-140">我们建议你继续使用此设置（如果你之前使用过它），因为在基础结构连接不起作用的情况下 Miracast 将恢复为常规 Miracast。</span><span class="sxs-lookup"><span data-stu-id="6d251-140">We recommend that you continue using this setting (if you used it previously) as Miracast will fall back to regular Miracast if the infrastructure connection does not work.</span></span> 

## <span data-ttu-id="6d251-141">常见问题</span><span class="sxs-lookup"><span data-stu-id="6d251-141">FAQ</span></span>
**<span data-ttu-id="6d251-142">为什么仍需要 Wi-fi 才能通过基础架构使用 Miracast？</span><span class="sxs-lookup"><span data-stu-id="6d251-142">Why do I still need Wi-Fi to use Miracast over infrastructure?</span></span>**<br>
<span data-ttu-id="6d251-143">确定 Miracast 接收器的发现请求只能通过 Wi-fi 适配器进行。</span><span class="sxs-lookup"><span data-stu-id="6d251-143">Discovery requests to identify Miracast receivers can only occur through the Wi-Fi adapter.</span></span> <span data-ttu-id="6d251-144">一旦接收器已确定，Windows 10 就可以尝试连接到网络。</span><span class="sxs-lookup"><span data-stu-id="6d251-144">Once the receivers have been identified, Windows 10 can then attempt the connection to the network.</span></span>

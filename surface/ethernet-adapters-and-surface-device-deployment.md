---
title: 以太网适配器和 Surface 部署 (Surface)
description: 本文提供了可帮助你执行到 Surface 设备的网络部署的指南和方法。
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: ''
manager: laurawi
keywords: 以太网, 部署, 可移动, 网络, 连接性, 启动, 固件, 设备, 适配器, PXE 启动, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 4b0cfd9cadab33d82ae3d0acaa83e007229c6fb8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830789"
---
# <span data-ttu-id="58c24-104">以太网适配器和 Surface 部署</span><span class="sxs-lookup"><span data-stu-id="58c24-104">Ethernet adapters and Surface deployment</span></span>


<span data-ttu-id="58c24-105">本文提供了指导和解答，可帮助你对包括 Surface Pro 3 和更高版本的 Surface 设备执行网络部署。</span><span class="sxs-lookup"><span data-stu-id="58c24-105">This article provides guidance and answers to help you perform a network deployment to Surface devices including Surface Pro 3 and later.</span></span>

<span data-ttu-id="58c24-106">到 Surface 设备的网络部署可能会给系统管理员带来一些独特的挑战。</span><span class="sxs-lookup"><span data-stu-id="58c24-106">Network deployment to Surface devices can pose some unique challenges for system administrators.</span></span> <span data-ttu-id="58c24-107">由于缺少本机有线以太网适配器，因此管理员必须通过可移动以太网适配器提供连接。</span><span class="sxs-lookup"><span data-stu-id="58c24-107">Due to the lack of a native wired Ethernet adapter, administrators must provide connectivity through a removable Ethernet adapter.</span></span>

## <span data-ttu-id="58c24-108">针对 Surface 设备选择以太网适配器</span><span class="sxs-lookup"><span data-stu-id="58c24-108">Select an Ethernet adapter for Surface devices</span></span>


<span data-ttu-id="58c24-109">在解决将如何启动到部署环境或者设备将如何由部署解决方案标识方面的问题前，必须使用有线网络适配器。</span><span class="sxs-lookup"><span data-stu-id="58c24-109">Before you can address the concerns of how you will boot to your deployment environment or how devices will be recognized by your deployment solution, you have to use a wired network adapter.</span></span>

<span data-ttu-id="58c24-110">当选择以太网适配器时，主要问题在于该适配器将如何从网络启动 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="58c24-110">The primary concern when selecting an Ethernet adapter is how that adapter will boot your Surface device from the network.</span></span> <span data-ttu-id="58c24-111">如果你使用 Windows 部署服务（WDS）预暂存客户端，或者如果你使用的是 Microsoft 终结点配置管理器，你可能还需要考虑可移除的以太网适配器是否专用于特定的 Surface 设备或在多个设备之间共享。</span><span class="sxs-lookup"><span data-stu-id="58c24-111">If you are pre-staging clients with Windows Deployment Services (WDS) or if you are using Microsoft Endpoint Configuration Manager, you may also want to consider whether the removable Ethernet adapters will be dedicated to a specific Surface device or shared among multiple devices.</span></span> <span data-ttu-id="58c24-112">有关与共享适配器的潜在冲突的详细信息，请参阅本文后面的[管理可移动以太网适配器的 MAC 地址](#manage-mac-addresses)。</span><span class="sxs-lookup"><span data-stu-id="58c24-112">For more information on potential conflicts with shared adapters, see [Manage MAC addresses with removable Ethernet adapters](#manage-mac-addresses) later in this article.</span></span>

<span data-ttu-id="58c24-113">仅当使用 Microsoft 提供的以太网适配器或扩展坞时，才支持从网络启动（PXE 启动）。</span><span class="sxs-lookup"><span data-stu-id="58c24-113">Booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="58c24-114">若要从网络启动，必须检测以太网适配器或扩展坞中的芯片集并将其配置为 Surface 设备的固件中的启动设备。</span><span class="sxs-lookup"><span data-stu-id="58c24-114">To boot from the network, the chipset in the Ethernet adapter or dock must be detected and configured as a boot device in the firmware of the Surface device.</span></span> <span data-ttu-id="58c24-115">Microsoft 以太网适配器（如 Surface 以太网适配器和 [Surface 扩展坞](https://www.microsoft.com/surface/accessories/surface-dock)）使用与 Surface 固件兼容的芯片集。</span><span class="sxs-lookup"><span data-stu-id="58c24-115">Microsoft Ethernet adapters, such as the Surface Ethernet Adapter and the [Surface Dock](https://www.microsoft.com/surface/accessories/surface-dock) use a chipset that is compatible with the Surface firmware.</span></span>

<span data-ttu-id="58c24-116">Surface 设备的网络启动支持以下以太网设备：</span><span class="sxs-lookup"><span data-stu-id="58c24-116">The following Ethernet devices are supported for network boot with Surface devices:</span></span>

-   <span data-ttu-id="58c24-117">Surface USB-C 至以太网和 USB 3.0 适配器</span><span class="sxs-lookup"><span data-stu-id="58c24-117">Surface USB-C to Ethernet and USB 3.0 Adapter</span></span>

-   <span data-ttu-id="58c24-118">Surface USB 3.0 至千兆以太网适配器</span><span class="sxs-lookup"><span data-stu-id="58c24-118">Surface USB 3.0 to Gigabit Ethernet Adapter</span></span>

-   <span data-ttu-id="58c24-119">Surface 扩展坞</span><span class="sxs-lookup"><span data-stu-id="58c24-119">Surface Dock</span></span>

-   <span data-ttu-id="58c24-120">Surface 3 扩展坞</span><span class="sxs-lookup"><span data-stu-id="58c24-120">Surface 3 Docking Station</span></span>

-   <span data-ttu-id="58c24-121">Surface Pro 3 扩展坞</span><span class="sxs-lookup"><span data-stu-id="58c24-121">Surface Pro 3 Docking Station</span></span>

-   <span data-ttu-id="58c24-122">适用于 Surface Pro 和 Surface Pro 2 的扩展坞</span><span class="sxs-lookup"><span data-stu-id="58c24-122">Docking Station for Surface Pro and Surface Pro 2</span></span>

<span data-ttu-id="58c24-123">第三方以太网适配器还受网络部署支持，尽管它们不支持 PXE 启动。</span><span class="sxs-lookup"><span data-stu-id="58c24-123">Third-party Ethernet adapters are also supported for network deployment, although they do not support PXE boot.</span></span> <span data-ttu-id="58c24-124">若要使用第三方以太网适配器，必须将驱动程序加载到部署启动映像中，并且必须从单独的存储设备（如 U 盘）启动该启动映像。</span><span class="sxs-lookup"><span data-stu-id="58c24-124">To use a third-party Ethernet adapter, you must load the drivers into the deployment boot image and you must launch that boot image from a separate storage device, such as a USB stick.</span></span>

## <span data-ttu-id="58c24-125">从网络启动 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="58c24-125">Boot Surface devices from the network</span></span>

<span data-ttu-id="58c24-126">若要从网络或连接的 U 盘启动，必须指示 Surface 设备从备用启动设备中启动。</span><span class="sxs-lookup"><span data-stu-id="58c24-126">To boot from the network or a connected USB stick, you must instruct the Surface device to boot from an alternate boot device.</span></span> <span data-ttu-id="58c24-127">你可以更改系统固件中的启动顺序以设置 USB 启动设备的优先级，也可以指示它在启动过程中从备用启动设备中启动。</span><span class="sxs-lookup"><span data-stu-id="58c24-127">You can alter the boot order in the system firmware to prioritize USB boot devices, or you can instruct it to boot from an alternate boot device during the boot up process.</span></span>

<span data-ttu-id="58c24-128">若要从备用启动设备中启动 Surface 设备，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="58c24-128">To boot a Surface device from an alternative boot device, follow these steps:</span></span>

1.  <span data-ttu-id="58c24-129">确保 Surface 设备的电源已关闭。</span><span class="sxs-lookup"><span data-stu-id="58c24-129">Ensure the Surface device is powered off.</span></span>
2.  <span data-ttu-id="58c24-130">长按**降低音量**按钮。</span><span class="sxs-lookup"><span data-stu-id="58c24-130">Press and hold the **Volume Down** button.</span></span>
3.  <span data-ttu-id="58c24-131">按下并释放“电源”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="58c24-131">Press and release the **Power** button.</span></span>
4.  <span data-ttu-id="58c24-132">在系统开始从 U 盘或以太网适配器启动后，释放**降低音量**按钮。</span><span class="sxs-lookup"><span data-stu-id="58c24-132">After the system begins to boot from the USB stick or Ethernet adapter, release the **Volume Down** button.</span></span>

>[!NOTE]
><span data-ttu-id="58c24-133">除了以太网适配器外，键盘也必须连接到 Surface 设备，以便进入预安装环境并导航部署向导。</span><span class="sxs-lookup"><span data-stu-id="58c24-133">In addition to an Ethernet adapter, a keyboard must also be connected to the Surface device to enter the preinstallation environment and navigate the deployment wizard.</span></span>

 
<span data-ttu-id="58c24-134">对于 Windows 10 版本 1511 和更高版本（包括适用于 Windows 10 版本 1511 的 Windows 评估和部署工具包 (Windows ADK)），默认情况下存在适用于 Microsoft Surface 以太网适配器的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="58c24-134">For Windows 10, version 1511 and later – including the Windows Assessment and Deployment Kit (Windows ADK) for Windows 10, version 1511 – the drivers for Microsoft Surface Ethernet Adapters are present by default.</span></span> <span data-ttu-id="58c24-135">如果你使用的是使用 Windows 预安装环境 (WinPE) 的部署解决方案（如 Microsoft 部署工具包）并且通过 PXE 从网络启动，请确保你的部署解决方案使用最新版本的 Windows ADK。</span><span class="sxs-lookup"><span data-stu-id="58c24-135">If you are using a deployment solution that uses Windows Preinstallation Environment (WinPE), like the Microsoft Deployment Toolkit, and booting from the network with PXE, ensure that your deployment solution is using the latest version of the Windows ADK.</span></span>

## <a href="" id="manage-mac-addresses"></a><span data-ttu-id="58c24-136">使用可移动以太网适配器管理 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="58c24-136">Manage MAC addresses with removable Ethernet adapters</span></span>

<span data-ttu-id="58c24-137">对于通过网络执行 Windows 部署的管理员而言，另一注意事项是如何在将相同的以太网适配器用于部署到多台计算机时标识计算机。</span><span class="sxs-lookup"><span data-stu-id="58c24-137">Another consideration for administrators performing Windows deployment over the network is how you will identify computers when you use the same Ethernet adapter to deploy to more than one computer.</span></span> <span data-ttu-id="58c24-138">部署技术所使用的常见标识符是与每个以太网适配器关联的媒体访问控制 (MAC) 地址。</span><span class="sxs-lookup"><span data-stu-id="58c24-138">A common identifier used by deployment technologies is the Media Access Control (MAC) address that is associated with each Ethernet adapter.</span></span> <span data-ttu-id="58c24-139">但在将同一以太网适配器用于部署到多台计算机时，你将无法使用可检查 MAC 地址的部署技术，因为在可移动适配器用于不同的计算机时无法区分其 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="58c24-139">However, when you use the same Ethernet adapter to deploy to multiple computers, you cannot use a deployment technology that inspects MAC addresses because there is no way to differentiate the MAC address of the removable adapter when used on the different computers.</span></span>

<span data-ttu-id="58c24-140">避免 MAC 地址冲突的最简单解决方案是为每台 Surface 设备提供专用的可移动以太网适配器。</span><span class="sxs-lookup"><span data-stu-id="58c24-140">The simplest solution to avoid MAC address conflicts is to provide a dedicated removable Ethernet adapter for each Surface device.</span></span> <span data-ttu-id="58c24-141">这在将定期使用以太网适配器或扩展坞的附加功能的大多数情况下可能会有意义。</span><span class="sxs-lookup"><span data-stu-id="58c24-141">This can make sense in many scenarios where the Ethernet adapter or the additional functionality of the docking station will be used regularly.</span></span> <span data-ttu-id="58c24-142">但是，并非所有方案都要求扩展坞的其他连接或对有线网络的支持。</span><span class="sxs-lookup"><span data-stu-id="58c24-142">However, not all scenarios call for the additional connectivity of a docking station or support for wired networks.</span></span>

<span data-ttu-id="58c24-143">避免共享适配器时发生冲突的另一可能的解决方案是使用 [Microsoft Deployment Toolkit (MDT)](https://technet.microsoft.com/windows/dn475741) 执行到 Surface 设备的部署。</span><span class="sxs-lookup"><span data-stu-id="58c24-143">Another potential solution to avoid conflict when adapters are shared is to use the [Microsoft Deployment Toolkit (MDT)](https://technet.microsoft.com/windows/dn475741) to perform deployment to Surface devices.</span></span> <span data-ttu-id="58c24-144">MDT 不使用 MAC 地址来标识个别计算机，因此不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="58c24-144">MDT does not use the MAC address to identify individual computers and thus is not subject to this limitation.</span></span> <span data-ttu-id="58c24-145">但是，MDT 会使用 Windows 部署服务来提供 PXE 启动功能，因此受预暂存的客户端方面的限制，这将在本部分的后面部分中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="58c24-145">However, MDT does use Windows Deployment Services to provide PXE boot functionality, and is subject to the limitations regarding pre-staged clients which is covered later in this section.</span></span>

<span data-ttu-id="58c24-146">当你将共享的适配器用于部署时，受影响的部署技术的解决方案是使用其他方法来标识唯一系统。</span><span class="sxs-lookup"><span data-stu-id="58c24-146">When you use a shared adapter for deployment, the solution for affected deployment technologies is to use another means to identify unique systems.</span></span> <span data-ttu-id="58c24-147">对于可能受此问题影响的配置管理器和 WDS，解决方案是使用由计算机制造商嵌入在计算机固件中的系统通用唯一标识符（系统 UUID）。</span><span class="sxs-lookup"><span data-stu-id="58c24-147">For Configuration Manager and WDS, both of which can be affected by this issue, the solution is to use the System Universal Unique Identifier (System UUID) that is embedded in the computer firmware by the computer manufacturer.</span></span> <span data-ttu-id="58c24-148">对于 Surface 设备，你可以在计算机固件的**设备信息**下看到此项。</span><span class="sxs-lookup"><span data-stu-id="58c24-148">For Surface devices, you can see this entry in the computer firmware under **Device Information**.</span></span>

<span data-ttu-id="58c24-149">若要访问 Surface 设备的固件，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="58c24-149">To access the firmware of a Surface device, follow these steps:</span></span>

1.  <span data-ttu-id="58c24-150">确保 Surface 设备的电源已关闭。</span><span class="sxs-lookup"><span data-stu-id="58c24-150">Ensure the Surface device is powered off.</span></span>
2.  <span data-ttu-id="58c24-151">长按**调高音量**按钮。</span><span class="sxs-lookup"><span data-stu-id="58c24-151">Press and hold the **Volume Up** button.</span></span>
3.  <span data-ttu-id="58c24-152">按下并释放**电源**按钮。</span><span class="sxs-lookup"><span data-stu-id="58c24-152">Press and release the **Power** button.</span></span>
4.  <span data-ttu-id="58c24-153">在设备开始启动后，释放**调高音量**按钮。</span><span class="sxs-lookup"><span data-stu-id="58c24-153">After the device begins to boot, release the **Volume Up** button.</span></span>

<span data-ttu-id="58c24-154">如果使用 WDS 部署，MAC 地址将仅用于在部署服务器配置为仅响应已知且预暂存的客户端时标识计算机。</span><span class="sxs-lookup"><span data-stu-id="58c24-154">When deploying with WDS, the MAC address is only used to identify a computer when the deployment server is configured to respond only to known, pre-staged clients.</span></span> <span data-ttu-id="58c24-155">当预暂存客户端时，管理员将在 Active Directory 中创建计算机帐户，并根据 MAC 地址或系统 UUID 定义该计算机。</span><span class="sxs-lookup"><span data-stu-id="58c24-155">When pre-staging a client, an administrator creates a computer account in Active Directory and defines that computer by the MAC address or the System UUID.</span></span> <span data-ttu-id="58c24-156">若要避免由共享的以太网适配器引起的标识冲突，应使用[系统 UUID 定义预暂存的客户端](https://technet.microsoft.com/library/cc742034)。</span><span class="sxs-lookup"><span data-stu-id="58c24-156">To avoid the identity conflicts caused by shared Ethernet adapters, you should use [System UUID to define pre-staged clients](https://technet.microsoft.com/library/cc742034).</span></span> <span data-ttu-id="58c24-157">或者，可以将 WDS 配置为响应未知客户端，而无需由 MAC 地址或系统 UUID 进行定义，方法是在 **Windows 部署服务器属性**的[**PXE 响应**选项卡](https://technet.microsoft.com/library/cc732360)上选择**响应所有客户端计算机(已知和未知)** 选项。</span><span class="sxs-lookup"><span data-stu-id="58c24-157">Alternatively, you can configure WDS to respond to unknown clients that do not require definition by either MAC address or System UUID by selecting the **Respond to all client computers (known and unknown)** option on the [**PXE Response** tab](https://technet.microsoft.com/library/cc732360) in **Windows Deployment Server Properties**.</span></span>

<span data-ttu-id="58c24-158">与配置管理器相比，与共享的以太网适配发生冲突的可能性要高很多。</span><span class="sxs-lookup"><span data-stu-id="58c24-158">The potential for conflicts with shared Ethernet adapters is much higher with Configuration Manager.</span></span> <span data-ttu-id="58c24-159">在 WDS 仅使用 MAC 地址来定义各个系统（如果将其这样配置）的情况下，只要执行到新的或未知计算机的部署，配置管理器便会使用 MAC 地址来定义各个系统。</span><span class="sxs-lookup"><span data-stu-id="58c24-159">Where WDS only uses MAC addresses to define individual systems when configured to do so, Configuration Manager uses the MAC address to define individual systems whenever performing a deployment to new or unknown computers.</span></span> <span data-ttu-id="58c24-160">这可能导致未正确配置设备，甚至无法使用共享的以太网适配器部署多个系统。</span><span class="sxs-lookup"><span data-stu-id="58c24-160">This can result in improperly configured devices or even the inability to deploy more than one system with a shared Ethernet adapter.</span></span> <span data-ttu-id="58c24-161">有关[如何对多个 SCCM OSD 使用同一外部以太网适配器](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374)的多个潜在解决方案，详细介绍了如何在核心基础结构和安全博客上使用一个博客文章。</span><span class="sxs-lookup"><span data-stu-id="58c24-161">There are several potential solutions for this situation that are described in detail in [How to Use The Same External Ethernet Adapter For Multiple SCCM OSD](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374), a blog post on the Core Infrastructure and Security Blog.</span></span>

 

 






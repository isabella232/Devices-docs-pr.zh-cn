---
title: Windows Autopilot 和 Surface 设备
ms.reviewer: ''
manager: laurawi
description: 了解适用于 Surface 设备的 Windows Autopilot 部署选项。
keywords: autopilot， windows 10， 图面， 部署
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 9/14/2020
ms.openlocfilehash: 31f11db8c3ab12d1af754267022d9060d3a8c026
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271098"
---
# <span data-ttu-id="54108-104">Windows Autopilot 和 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="54108-104">Windows Autopilot and Surface devices</span></span>

<span data-ttu-id="54108-105">Windows Autopilot 是 Windows 10 中的一种基于云的部署技术。</span><span class="sxs-lookup"><span data-stu-id="54108-105">Windows Autopilot is a cloud-based deployment technology in Windows 10.</span></span> <span data-ttu-id="54108-106">你可以立即使用 Windows Autopilot 在零接触进程中远程部署和配置设备。</span><span class="sxs-lookup"><span data-stu-id="54108-106">You can use Windows Autopilot to remotely deploy and configure devices in a zero-touch process right out of the box.</span></span>

<span data-ttu-id="54108-107">从传统来看，IT 专业人员花费大量时间构建和自定义映像，这些映像稍后将部署到已经安装了良好操作系统的设备。</span><span class="sxs-lookup"><span data-stu-id="54108-107">Traditionally, IT pros spend a lot of time building and customizing images that will later be deployed to devices that already come with a perfectly good OS already installed on them.</span></span> <span data-ttu-id="54108-108">Windows Autopilot 引入了一种新的零接触部署方法，该方法使用一组技术来设置和配置 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="54108-108">Windows Autopilot introduces a new zero-touch deployment approach using a collection of technologies to set up and configure Windows devices.</span></span> <span data-ttu-id="54108-109">这使 IT 部门能够配置/自定义映像，几乎无需管理基础结构，且过程简单明了。</span><span class="sxs-lookup"><span data-stu-id="54108-109">This enables an IT department to configure/customize images with little to no infrastructure to manage and a process that is easy and simple.</span></span> <span data-ttu-id="54108-110">从用户的角度来看，只需几个简单的步骤，Surface 就进入高效状态。</span><span class="sxs-lookup"><span data-stu-id="54108-110">From the user’s perspective, it only takes a few simple steps to get Surface to a productive state.</span></span> <span data-ttu-id="54108-111">实际上，最终用户所需的唯一交互是连接到网络并验证其凭据。</span><span class="sxs-lookup"><span data-stu-id="54108-111">In fact, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span> <span data-ttu-id="54108-112">之后的所有内容都完全自动化。</span><span class="sxs-lookup"><span data-stu-id="54108-112">Everything after that is fully automated.</span></span>

<span data-ttu-id="54108-113">Windows Autopilot 允许你：</span><span class="sxs-lookup"><span data-stu-id="54108-113">Windows Autopilot allows you to:</span></span>

- <span data-ttu-id="54108-114">自动将设备加入 Azure Active Directory (Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="54108-114">Automatically join devices to Azure Active Directory (Azure AD).</span></span>
- <span data-ttu-id="54108-115">将设备自动注册到 MDM 服务（如 Microsoft Intune (）需要 Azure AD Premium 订阅) 。</span><span class="sxs-lookup"><span data-stu-id="54108-115">Auto-enroll devices into MDM services, such as Microsoft Intune (requires an Azure AD Premium subscription).</span></span>
- <span data-ttu-id="54108-116">限制管理员帐户的创建。</span><span class="sxs-lookup"><span data-stu-id="54108-116">Restrict the Administrator account creation.</span></span> <span data-ttu-id="54108-117">Autopilot 是让第一个登录 Windows 的人以标准用户输入的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="54108-117">Autopilot is the only way to have the first person who logs into Windows enter as a standard user.</span></span>
- <span data-ttu-id="54108-118">根据设备配置文件创建设备并将其自动分配给配置组。</span><span class="sxs-lookup"><span data-stu-id="54108-118">Create and auto-assign devices to configuration groups based on device profiles.</span></span>
- <span data-ttu-id="54108-119">自定义 OOBE (全新体验) 内容和品牌，以满足组织要求。</span><span class="sxs-lookup"><span data-stu-id="54108-119">Customize OOBE (Out of Box Experience) content and branding to meet organizational requirements.</span></span>
- <span data-ttu-id="54108-120">使用 Intune 启用完整的设备配置。</span><span class="sxs-lookup"><span data-stu-id="54108-120">Enable full device configuration with Intune.</span></span>
- <span data-ttu-id="54108-121">远程重置或重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="54108-121">Reset or restart devices remotely.</span></span>

## <span data-ttu-id="54108-122">工作原理</span><span class="sxs-lookup"><span data-stu-id="54108-122">How it works</span></span>

<span data-ttu-id="54108-123">Windows Autopilot 注册的设备在首次启动时通过称为硬件哈希的唯一设备签名通过 Internet *进行标识*。</span><span class="sxs-lookup"><span data-stu-id="54108-123">Windows Autopilot-registered devices are identified over the Internet at first startup through a unique device signature that's called a *hardware hash*.</span></span> <span data-ttu-id="54108-124">通过使用现代管理解决方案（如 Azure Active Directory (Azure AD) 移动设备管理）自动注册和配置它们。</span><span class="sxs-lookup"><span data-stu-id="54108-124">They're automatically enrolled and configured by using modern management solutions such as Azure Active Directory (Azure AD) and mobile device management.</span></span>

<span data-ttu-id="54108-125">你可以从为 Windows Autopilot 启用的 Surface 合作伙伴购买时注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="54108-125">You can register Surface devices at the time of purchase from a Surface partner that's enabled for Windows Autopilot.</span></span> <span data-ttu-id="54108-126">这些合作伙伴可以直接将新设备发货给用户。</span><span class="sxs-lookup"><span data-stu-id="54108-126">These partners can ship new devices directly to your users.</span></span> <span data-ttu-id="54108-127">设备将在首次打开时自动注册和配置。</span><span class="sxs-lookup"><span data-stu-id="54108-127">The devices will be automatically enrolled and configured when they are first turned on.</span></span> <span data-ttu-id="54108-128">此过程在部署过程中消除了重新映像，从而允许你实现新的敏捷的设备管理和分发方法。</span><span class="sxs-lookup"><span data-stu-id="54108-128">This process eliminates reimaging during deployment, which lets you implement new, agile methods of device management and distribution.</span></span>

## <span data-ttu-id="54108-129">现代管理</span><span class="sxs-lookup"><span data-stu-id="54108-129">Modern management</span></span>

<span data-ttu-id="54108-130">Autopilot 是 Surface 设备（包括 Surface Pro 7+、Surface Laptop 3、Surface Pro 7 和 Surface Pro X）的推荐部署选项，专用于通过 Autopilot 进行部署。</span><span class="sxs-lookup"><span data-stu-id="54108-130">Autopilot is the recommended deployment option for Surface devices, including Surface Pro 7+, Surface Laptop 3, Surface Pro 7, and Surface Pro X, which is specifically designed for deployment through Autopilot.</span></span>

 <span data-ttu-id="54108-131">最好在 Microsoft 云解决方案提供商的帮助下注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="54108-131">It's best to enroll your Surface devices with the help of a Microsoft Cloud Solution Provider.</span></span> <span data-ttu-id="54108-132">此步骤允许你直接从 Intune 管理 Surface 上的 UEFI 固件设置。</span><span class="sxs-lookup"><span data-stu-id="54108-132">This step allows you to manage UEFI firmware settings on Surface directly from Intune.</span></span> <span data-ttu-id="54108-133">它无需以物理方式触摸设备进行证书管理。</span><span class="sxs-lookup"><span data-stu-id="54108-133">It eliminates the need to physically touch devices for certificate management.</span></span> <span data-ttu-id="54108-134">有关详细信息 [，请参阅 Surface UEFI 设置的 Intune](surface-manage-dfci-guide.md) 管理。</span><span class="sxs-lookup"><span data-stu-id="54108-134">See [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md) for details.</span></span>

## <span data-ttu-id="54108-135">Windows 版本注意事项</span><span class="sxs-lookup"><span data-stu-id="54108-135">Windows version considerations</span></span>

<span data-ttu-id="54108-136">通过 Windows Autopilot 广泛部署 Surface 设备（包括在购买时由 Surface 合作伙伴注册）需要 Windows 10 版本 1709 (Fall Creators Update) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="54108-136">Broad deployment of Surface devices through Windows Autopilot, including enrollment by Surface partners at the time of purchase, requires Windows 10 Version 1709 (Fall Creators Update) or later.</span></span>

<span data-ttu-id="54108-137">这些 Windows 版本支持 4，000 字节 (4k) 哈希值，它唯一标识 Windows Autopilot 的设备，这是大规模部署所必需的。</span><span class="sxs-lookup"><span data-stu-id="54108-137">These Windows versions support a 4,000-byte (4k) hash value that uniquely identifies devices for Windows Autopilot, which is necessary for deployments at scale.</span></span> <span data-ttu-id="54108-138">所有新的 Surface 设备（包括 Surface Pro 7+、Surface Pro X 和 Surface Laptop 3）随 Windows 10 版本 1903 或更高版本一起提供。</span><span class="sxs-lookup"><span data-stu-id="54108-138">All new Surface devices, including Surface Pro 7+, Surface Pro X, and Surface Laptop 3 ship with Windows 10 Version 1903 or later.</span></span>

## <span data-ttu-id="54108-139">需要修复或更换的 Surface 设备的 Exchange 体验</span><span class="sxs-lookup"><span data-stu-id="54108-139">Exchange experience on Surface devices in need of repair or replacement</span></span>

<span data-ttu-id="54108-140">Microsoft 会自动检查每个 Surface 的 Autopilot 注册，并取消客户租户中的设备注册。</span><span class="sxs-lookup"><span data-stu-id="54108-140">Microsoft automatically checks every Surface for Autopilot enrollment and will deregister the device from the customer's tenant.</span></span>  <span data-ttu-id="54108-141">Microsoft 确保在将替换设备交付回客户后注册到 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="54108-141">Microsoft ensures the replacement device is enrolled into Windows Autopilot once a replacement is shipped back to the customer.</span></span> <span data-ttu-id="54108-142">此服务可在所有设备直接与 Microsoft 交换服务订单上提供。</span><span class="sxs-lookup"><span data-stu-id="54108-142">This service is available on all device exchange service orders directly with Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="54108-143">当客户使用合作伙伴返回设备时，合作伙伴负责管理交换过程，包括注销设备以及将设备注册到 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="54108-143">When customers use a Partner to return devices, the Partner is responsible for managing the exchange process including deregistering and enrolling devices into Windows Autopilot.</span></span>

## <span data-ttu-id="54108-144">Microsoft 支持注册</span><span class="sxs-lookup"><span data-stu-id="54108-144">Microsoft Support registration</span></span>

<span data-ttu-id="54108-145">客户和 Microsoft 云解决方案提供商 (服务提供商) 通过向 Microsoft 支持提交请求来注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="54108-145">Customers and Microsoft Cloud Solution Providers (CSPs) have the option of registering Surface devices by submitting requests to Microsoft Support.</span></span> <span data-ttu-id="54108-146">若要了解更多信息，请参阅 [Windows Autopilot](surface-autopilot-registration-support.md)的 Surface 注册支持。</span><span class="sxs-lookup"><span data-stu-id="54108-146">To learn more, see [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md).</span></span>

## <span data-ttu-id="54108-147">为 Windows Autopilot 启用的 Surface 合作伙伴</span><span class="sxs-lookup"><span data-stu-id="54108-147">Surface partners enabled for Windows Autopilot</span></span>

<span data-ttu-id="54108-148">选择 Surface 合作伙伴可在购买时在 Windows Autopilot 中注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="54108-148">Select Surface partners can enroll Surface devices in Windows Autopilot for you at the time of purchase.</span></span> <span data-ttu-id="54108-149">他们还可以将已注册的设备直接发货给用户。</span><span class="sxs-lookup"><span data-stu-id="54108-149">They can also ship enrolled devices directly to your users.</span></span> <span data-ttu-id="54108-150">可以使用 Windows Autopilot、Azure AD 和移动设备管理，通过零接触过程完全配置设备。</span><span class="sxs-lookup"><span data-stu-id="54108-150">The devices can be configured entirely through a zero-touch process by using Windows Autopilot, Azure AD, and mobile device management.</span></span>

<span data-ttu-id="54108-151">为 Windows Autopilot 启用的 Surface 合作伙伴包括：</span><span class="sxs-lookup"><span data-stu-id="54108-151">Surface partners that are enabled for Windows Autopilot include:</span></span>

| <span data-ttu-id="54108-152">美国合作伙伴</span><span class="sxs-lookup"><span data-stu-id="54108-152">US partners</span></span> | <span data-ttu-id="54108-153">全球合作伙伴</span><span class="sxs-lookup"><span data-stu-id="54108-153">Global partners</span></span> | <span data-ttu-id="54108-154">美国分销商</span><span class="sxs-lookup"><span data-stu-id="54108-154">US distributors</span></span> |
|--------------|---------------|-------------------|
| <span data-ttu-id="54108-155">\* [CDW](https://www.cdw.com/)</span><span class="sxs-lookup"><span data-stu-id="54108-155">\* [CDW](https://www.cdw.com/)</span></span> | <span data-ttu-id="54108-156">\* [Also](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="54108-156">\* [ALSO](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span></span> | <span data-ttu-id="54108-157">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span><span class="sxs-lookup"><span data-stu-id="54108-157">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span></span>  |
| <span data-ttu-id="54108-158">\* [连接](https://www.connection.com/brand/microsoft/microsoft-surface)</span><span class="sxs-lookup"><span data-stu-id="54108-158">\* [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)</span></span>   | <span data-ttu-id="54108-159">\* [ATEA](https://www.atea.com/)</span><span class="sxs-lookup"><span data-stu-id="54108-159">\* [ATEA](https://www.atea.com/)</span></span> | <span data-ttu-id="54108-160">\* [Techdata](https://www.techdata.com/)</span><span class="sxs-lookup"><span data-stu-id="54108-160">\* [Techdata](https://www.techdata.com/)</span></span>  |
| <span data-ttu-id="54108-161">\* [见解](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span><span class="sxs-lookup"><span data-stu-id="54108-161">\* [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span></span>  | <span data-ttu-id="54108-162">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="54108-162">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span></span> | <span data-ttu-id="54108-163">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span><span class="sxs-lookup"><span data-stu-id="54108-163">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span></span>   |
| <span data-ttu-id="54108-164">\* [一名](https://www.shi.com/Surface)</span><span class="sxs-lookup"><span data-stu-id="54108-164">\* [SHI](https://www.shi.com/Surface)</span></span> | <span data-ttu-id="54108-165">\* [Cancom](https://www.cancom.de/)</span><span class="sxs-lookup"><span data-stu-id="54108-165">\* [Cancom](https://www.cancom.de/)</span></span> |    |
| <span data-ttu-id="54108-166">\* [LDI Connect](https://www.myldi.com/managed-it/)</span><span class="sxs-lookup"><span data-stu-id="54108-166">\* [LDI Connect](https://www.myldi.com/managed-it/)</span></span>  | <span data-ttu-id="54108-167">\* [Computacenter](https://www.computacenter.com/uk)</span><span class="sxs-lookup"><span data-stu-id="54108-167">\* [Computacenter](https://www.computacenter.com/uk)</span></span> |    |
| <span data-ttu-id="54108-168">\* [F1](https://www.functiononeit.com/#empower)</span><span class="sxs-lookup"><span data-stu-id="54108-168">\* [F1](https://www.functiononeit.com/#empower)</span></span>  |   |  |
| <span data-ttu-id="54108-169">\* [受保护的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span><span class="sxs-lookup"><span data-stu-id="54108-169">\* [Protected Trust](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span></span> | | | 

## <span data-ttu-id="54108-170">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="54108-170">Learn more</span></span>

<span data-ttu-id="54108-171">有关 Windows Autopilot 详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="54108-171">For more information about Windows Autopilot, see:</span></span>
- [<span data-ttu-id="54108-172">Windows Autopilot 概述</span><span class="sxs-lookup"><span data-stu-id="54108-172">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [<span data-ttu-id="54108-173">Windows Autopilot 要求</span><span class="sxs-lookup"><span data-stu-id="54108-173">Windows Autopilot requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [<span data-ttu-id="54108-174">适用于 Windows Autopilot 的 Surface 注册支持</span><span class="sxs-lookup"><span data-stu-id="54108-174">Surface Registration Support for Windows Autopilot</span></span>](surface-autopilot-registration-support.md)
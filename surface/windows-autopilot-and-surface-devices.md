---
title: Windows Autopilot 和 Surface 设备
ms.reviewer: ''
manager: laurawi
description: 了解有关面向 Surface 设备的 Windows Autopilot 部署选项的信息。
keywords: autopilot、windows 10、surface、部署
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
ms.openlocfilehash: d2a948d236ffa286192937cc5ca71099b6eeeafb
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016421"
---
# <span data-ttu-id="7d4b4-104">Windows Autopilot 和 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="7d4b4-104">Windows Autopilot and Surface devices</span></span>

<span data-ttu-id="7d4b4-105">Windows Autopilot 是 Windows 10 中基于云的部署技术。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-105">Windows Autopilot is a cloud-based deployment technology in Windows 10.</span></span> <span data-ttu-id="7d4b4-106">你可以使用 Windows Autopilot 远程部署和配置设备，只需要一个零接触过程即可。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-106">You can use Windows Autopilot to remotely deploy and configure devices in a zero-touch process right out of the box.</span></span>

<span data-ttu-id="7d4b4-107">传统上，IT 专业人员花费大量时间构建和自定义映像，这些映像稍后将部署到已安装好良好操作系统的设备。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-107">Traditionally, IT pros spend a lot of time building and customizing images that will later be deployed to devices that already come with a perfectly good OS already installed on them.</span></span> <span data-ttu-id="7d4b4-108">Windows Autopilot 使用用于设置和配置 Windows 设备的技术集合引入了新的零接触部署方法。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-108">Windows Autopilot introduces a new zero-touch deployment approach using a collection of technologies to set up and configure Windows devices.</span></span> <span data-ttu-id="7d4b4-109">这使 IT 部门能够配置/自定义图像，几乎不需要管理基础结构，而且简单明了。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-109">This enables an IT department to configure/customize images with little to no infrastructure to manage and a process that is easy and simple.</span></span> <span data-ttu-id="7d4b4-110">从用户的角度来看，只需执行几个简单的步骤即可获取生产状态的图面。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-110">From the user’s perspective, it only takes a few simple steps to get Surface to a productive state.</span></span> <span data-ttu-id="7d4b4-111">实际上，最终用户所需的唯一交互是连接到网络并验证其凭据。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-111">In fact, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span> <span data-ttu-id="7d4b4-112">所有内容将完全自动化。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-112">Everything after that is fully automated.</span></span>

<span data-ttu-id="7d4b4-113">Windows Autopilot 允许你：</span><span class="sxs-lookup"><span data-stu-id="7d4b4-113">Windows Autopilot allows you to:</span></span>

- <span data-ttu-id="7d4b4-114">将设备自动加入到 Azure Active Directory (Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-114">Automatically join devices to Azure Active Directory (Azure AD).</span></span>
- <span data-ttu-id="7d4b4-115">将设备自动注册到 MDM 服务（如 Microsoft Intune (需要 Azure AD Premium 订阅) 。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-115">Auto-enroll devices into MDM services, such as Microsoft Intune (requires an Azure AD Premium subscription).</span></span>
- <span data-ttu-id="7d4b4-116">限制管理员帐户的创建。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-116">Restrict the Administrator account creation.</span></span> <span data-ttu-id="7d4b4-117">Autopilot 是让登录 Windows 的第一个用户输入标准用户的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-117">Autopilot is the only way to have the first person who logs into Windows enter as a standard user.</span></span>
- <span data-ttu-id="7d4b4-118">根据设备配置文件创建设备并自动将其分配到配置组。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-118">Create and auto-assign devices to configuration groups based on device profiles.</span></span>
- <span data-ttu-id="7d4b4-119">自定义 OOBE (现成的体验) 内容和品牌，以满足组织的要求。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-119">Customize OOBE (Out of Box Experience) content and branding to meet organizational requirements.</span></span>
- <span data-ttu-id="7d4b4-120">使用 Intune 启用完整设备配置。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-120">Enable full device configuration with Intune.</span></span>
- <span data-ttu-id="7d4b4-121">远程重置或重启设备。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-121">Reset or restart devices remotely.</span></span>

## <span data-ttu-id="7d4b4-122">工作原理</span><span class="sxs-lookup"><span data-stu-id="7d4b4-122">How it works</span></span>

<span data-ttu-id="7d4b4-123">Windows Autopilot 注册的设备将在首次启动时通过 Internet 标识，该设备签名是一个称为 *硬件哈希*的唯一设备签名。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-123">Windows Autopilot-registered devices are identified over the Internet at first startup through a unique device signature that's called a *hardware hash*.</span></span> <span data-ttu-id="7d4b4-124">它们通过使用新式管理解决方案（如 Azure Active Directory (Azure AD) 和移动设备管理）自动注册和配置。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-124">They're automatically enrolled and configured by using modern management solutions such as Azure Active Directory (Azure AD) and mobile device management.</span></span>

<span data-ttu-id="7d4b4-125">您可以在从支持 Windows Autopilot 的 Surface 合作伙伴处购买时注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-125">You can register Surface devices at the time of purchase from a Surface partner that's enabled for Windows Autopilot.</span></span> <span data-ttu-id="7d4b4-126">这些合作伙伴可以将新设备直接发送给你的用户。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-126">These partners can ship new devices directly to your users.</span></span> <span data-ttu-id="7d4b4-127">这些设备将在首次打开时自动注册和配置。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-127">The devices will be automatically enrolled and configured when they are first turned on.</span></span> <span data-ttu-id="7d4b4-128">此过程消除了部署期间的映像，使你可以实现设备管理和分发的全新敏捷方法。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-128">This process eliminates reimaging during deployment, which lets you implement new, agile methods of device management and distribution.</span></span>

## <span data-ttu-id="7d4b4-129">现代管理</span><span class="sxs-lookup"><span data-stu-id="7d4b4-129">Modern management</span></span>

<span data-ttu-id="7d4b4-130">Autopilot 是适用于 Surface 设备的推荐部署选项，包括 Surface Pro 7、Surface 笔记本3和 Surface Pro X，后者专为通过 Autopilot 进行部署而设计。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-130">Autopilot is the recommended deployment option for Surface devices, including Surface Pro 7, Surface Laptop 3, and Surface Pro X, which is specifically designed for deployment through Autopilot.</span></span>

 <span data-ttu-id="7d4b4-131">最好使用 Microsoft 云解决方案提供商的帮助注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-131">It's best to enroll your Surface devices with the help of a Microsoft Cloud Solution Provider.</span></span> <span data-ttu-id="7d4b4-132">此步骤允许你直接从 Intune 管理 Surface 固件设置。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-132">This step allows you to manage UEFI firmware settings on Surface directly from Intune.</span></span> <span data-ttu-id="7d4b4-133">它消除了针对证书管理的物理触控设备的需要。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-133">It eliminates the need to physically touch devices for certificate management.</span></span> <span data-ttu-id="7d4b4-134">有关详细信息，请参阅 [SURFACE UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md) 。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-134">See [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md) for details.</span></span>

## <span data-ttu-id="7d4b4-135">Windows 版本注意事项</span><span class="sxs-lookup"><span data-stu-id="7d4b4-135">Windows version considerations</span></span>

<span data-ttu-id="7d4b4-136">通过 Windows Autopilot 广泛部署 Surface 设备（包括购买时 Surface 合作伙伴的注册）需要 Windows 10 版本 1709 (秋季创建者更新) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-136">Broad deployment of Surface devices through Windows Autopilot, including enrollment by Surface partners at the time of purchase, requires Windows 10 Version 1709 (Fall Creators Update) or later.</span></span>

<span data-ttu-id="7d4b4-137">这些 Windows 版本支持4000字节 (4k) 哈希值，该哈希值唯一地标识 Windows Autopilot 的设备，这对于部署规模很有必要。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-137">These Windows versions support a 4,000-byte (4k) hash value that uniquely identifies devices for Windows Autopilot, which is necessary for deployments at scale.</span></span> <span data-ttu-id="7d4b4-138">所有新的 Surface 设备（包括 Surface Pro 7、Surface Pro X 和 Surface 笔记本3）随 Windows 10 版本1903或更高版本一起提供。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-138">All new Surface devices, including Surface Pro 7, Surface Pro X, and Surface Laptop 3, ship with Windows 10 Version 1903 or later.</span></span>

## <span data-ttu-id="7d4b4-139">需要维修或更换的 Surface 设备上的 Exchange 体验</span><span class="sxs-lookup"><span data-stu-id="7d4b4-139">Exchange experience on Surface devices in need of repair or replacement</span></span>

<span data-ttu-id="7d4b4-140">Microsoft 会自动检查每个 Surface 的 Autopilot 注册，并将该设备从客户的租户中注销。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-140">Microsoft automatically checks every Surface for Autopilot enrollment and will deregister the device from the customer's tenant.</span></span>  <span data-ttu-id="7d4b4-141">Microsoft 可确保一旦向客户推出更换设备，即可将替换设备注册到 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-141">Microsoft ensures the replacement device is enrolled into Windows Autopilot once a replacement is shipped back to the customer.</span></span> <span data-ttu-id="7d4b4-142">此服务在所有设备 exchange 服务订单上通过 Microsoft 直接提供。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-142">This service is available on all device exchange service orders directly with Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="7d4b4-143">当客户使用合作伙伴返回设备时，合作伙伴负责管理 exchange 流程，包括将设备注销和注册到 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-143">When customers use a Partner to return devices, the Partner is responsible for managing the exchange process including deregistering and enrolling devices into Windows Autopilot.</span></span>

## <span data-ttu-id="7d4b4-144">Microsoft 支持注册</span><span class="sxs-lookup"><span data-stu-id="7d4b4-144">Microsoft Support registration</span></span>

<span data-ttu-id="7d4b4-145"> (Csp) 的客户和 Microsoft 云解决方案提供商可以通过向 Microsoft 支持人员提交请求来选择注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-145">Customers and Microsoft Cloud Solution Providers (CSPs) have the option of registering Surface devices by submitting requests to Microsoft Support.</span></span> <span data-ttu-id="7d4b4-146">若要了解详细信息，请参阅 [Windows Autopilot 的 Surface Registration 支持](surface-autopilot-registration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-146">To learn more, see [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md).</span></span>

## <span data-ttu-id="7d4b4-147">为 Windows Autopilot 启用的 Surface 合作伙伴</span><span class="sxs-lookup"><span data-stu-id="7d4b4-147">Surface partners enabled for Windows Autopilot</span></span>

<span data-ttu-id="7d4b4-148">选择 "Surface 合作伙伴" 可在购买时为您在 Windows Autopilot 中注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-148">Select Surface partners can enroll Surface devices in Windows Autopilot for you at the time of purchase.</span></span> <span data-ttu-id="7d4b4-149">他们还可以直接将注册的设备发运给你的用户。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-149">They can also ship enrolled devices directly to your users.</span></span> <span data-ttu-id="7d4b4-150">通过使用 Windows Autopilot、Azure AD 和移动设备管理，可以完全通过零接触过程来配置设备。</span><span class="sxs-lookup"><span data-stu-id="7d4b4-150">The devices can be configured entirely through a zero-touch process by using Windows Autopilot, Azure AD, and mobile device management.</span></span>

<span data-ttu-id="7d4b4-151">为 Windows Autopilot 启用的 Surface 合作伙伴包括：</span><span class="sxs-lookup"><span data-stu-id="7d4b4-151">Surface partners that are enabled for Windows Autopilot include:</span></span>

| <span data-ttu-id="7d4b4-152">美国合作伙伴</span><span class="sxs-lookup"><span data-stu-id="7d4b4-152">US partners</span></span> | <span data-ttu-id="7d4b4-153">全球合作伙伴</span><span class="sxs-lookup"><span data-stu-id="7d4b4-153">Global partners</span></span> | <span data-ttu-id="7d4b4-154">美国分销商</span><span class="sxs-lookup"><span data-stu-id="7d4b4-154">US distributors</span></span> |
|--------------|---------------|-------------------|
| <span data-ttu-id="7d4b4-155">\* [CDW](https://www.cdw.com/)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-155">\* [CDW](https://www.cdw.com/)</span></span> | <span data-ttu-id="7d4b4-156">\* [而且](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-156">\* [ALSO](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span></span> | <span data-ttu-id="7d4b4-157">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-157">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span></span>  |
| <span data-ttu-id="7d4b4-158">\* [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-158">\* [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)</span></span>   | <span data-ttu-id="7d4b4-159">\* [ATEA](https://www.atea.com/)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-159">\* [ATEA](https://www.atea.com/)</span></span> | <span data-ttu-id="7d4b4-160">\* [Techdata](https://www.techdata.com/)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-160">\* [Techdata](https://www.techdata.com/)</span></span>  |
| <span data-ttu-id="7d4b4-161">\* [知识](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-161">\* [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span></span>  | <span data-ttu-id="7d4b4-162">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-162">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span></span> | <span data-ttu-id="7d4b4-163">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-163">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span></span>   |
| <span data-ttu-id="7d4b4-164">\* [SHI](https://www.shi.com/Surface)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-164">\* [SHI](https://www.shi.com/Surface)</span></span> | <span data-ttu-id="7d4b4-165">\* [Cancom](https://www.cancom.de/)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-165">\* [Cancom](https://www.cancom.de/)</span></span> |    |
| <span data-ttu-id="7d4b4-166">\* [LDI 连接](https://www.myldi.com/managed-it/)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-166">\* [LDI Connect](https://www.myldi.com/managed-it/)</span></span>  | <span data-ttu-id="7d4b4-167">\* [Computacenter](https://www.computacenter.com/uk)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-167">\* [Computacenter](https://www.computacenter.com/uk)</span></span> |    |
| <span data-ttu-id="7d4b4-168">\* [了解](https://www.functiononeit.com/#empower)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-168">\* [F1](https://www.functiononeit.com/#empower)</span></span>  |   |  |
| <span data-ttu-id="7d4b4-169">\* [受保护的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span><span class="sxs-lookup"><span data-stu-id="7d4b4-169">\* [Protected Trust](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span></span> | | | 

## <span data-ttu-id="7d4b4-170">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="7d4b4-170">Learn more</span></span>

<span data-ttu-id="7d4b4-171">有关 Windows Autopilot 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="7d4b4-171">For more information about Windows Autopilot, see:</span></span>
- [<span data-ttu-id="7d4b4-172">Windows Autopilot 概述</span><span class="sxs-lookup"><span data-stu-id="7d4b4-172">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [<span data-ttu-id="7d4b4-173">Windows Autopilot 要求</span><span class="sxs-lookup"><span data-stu-id="7d4b4-173">Windows Autopilot requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [<span data-ttu-id="7d4b4-174">适用于 Windows 的 Surface 注册支持 Autopilot</span><span class="sxs-lookup"><span data-stu-id="7d4b4-174">Surface Registration Support for Windows Autopilot</span></span>](surface-autopilot-registration-support.md)
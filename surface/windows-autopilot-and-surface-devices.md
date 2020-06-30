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
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830767"
---
# <span data-ttu-id="242f1-104">Windows Autopilot 和 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="242f1-104">Windows Autopilot and Surface devices</span></span>

<span data-ttu-id="242f1-105">Windows Autopilot 是 Windows 10 中基于云的部署技术。</span><span class="sxs-lookup"><span data-stu-id="242f1-105">Windows Autopilot is a cloud-based deployment technology in Windows 10.</span></span> <span data-ttu-id="242f1-106">你可以使用 Windows Autopilot 远程部署和配置设备，只需要一个零接触过程即可。</span><span class="sxs-lookup"><span data-stu-id="242f1-106">You can use Windows Autopilot to remotely deploy and configure devices in a zero-touch process right out of the box.</span></span>

<span data-ttu-id="242f1-107">Windows Autopilot 注册的设备将在首次启动时通过 Internet 标识，该设备签名是一个称为*硬件哈希*的唯一设备签名。</span><span class="sxs-lookup"><span data-stu-id="242f1-107">Windows Autopilot-registered devices are identified over the Internet at first startup through a unique device signature that's called a *hardware hash*.</span></span> <span data-ttu-id="242f1-108">它们通过使用新式管理解决方案（如 Azure Active Directory （Azure AD）和移动设备管理）自动注册和配置。</span><span class="sxs-lookup"><span data-stu-id="242f1-108">They're automatically enrolled and configured by using modern management solutions such as Azure Active Directory (Azure AD) and mobile device management.</span></span>

<span data-ttu-id="242f1-109">您可以在从支持 Windows Autopilot 的 Surface 合作伙伴处购买时注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="242f1-109">You can register Surface devices at the time of purchase from a Surface partner that's enabled for Windows Autopilot.</span></span> <span data-ttu-id="242f1-110">这些合作伙伴可以将新设备直接发送给你的用户。</span><span class="sxs-lookup"><span data-stu-id="242f1-110">These partners can ship new devices directly to your users.</span></span> <span data-ttu-id="242f1-111">这些设备将在首次打开时自动注册和配置。</span><span class="sxs-lookup"><span data-stu-id="242f1-111">The devices will be automatically enrolled and configured when they are first turned on.</span></span> <span data-ttu-id="242f1-112">此过程消除了部署期间的映像，使你可以实现设备管理和分发的全新敏捷方法。</span><span class="sxs-lookup"><span data-stu-id="242f1-112">This process eliminates reimaging during deployment, which lets you implement new, agile methods of device management and distribution.</span></span>

## <span data-ttu-id="242f1-113">现代管理</span><span class="sxs-lookup"><span data-stu-id="242f1-113">Modern management</span></span>

<span data-ttu-id="242f1-114">Autopilot 是适用于 Surface 设备的推荐部署选项，包括 Surface Pro 7、Surface 笔记本3和 Surface Pro X，后者专为通过 Autopilot 进行部署而设计。</span><span class="sxs-lookup"><span data-stu-id="242f1-114">Autopilot is the recommended deployment option for Surface devices, including Surface Pro 7, Surface Laptop 3, and Surface Pro X, which is specifically designed for deployment through Autopilot.</span></span>

 <span data-ttu-id="242f1-115">最好使用 Microsoft 云解决方案提供商的帮助注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="242f1-115">It's best to enroll your Surface devices with the help of a Microsoft Cloud Solution Provider.</span></span> <span data-ttu-id="242f1-116">此步骤允许你直接从 Intune 管理 Surface 固件设置。</span><span class="sxs-lookup"><span data-stu-id="242f1-116">This step allows you to manage UEFI firmware settings on Surface directly from Intune.</span></span> <span data-ttu-id="242f1-117">它消除了针对证书管理的物理触控设备的需要。</span><span class="sxs-lookup"><span data-stu-id="242f1-117">It eliminates the need to physically touch devices for certificate management.</span></span> <span data-ttu-id="242f1-118">有关详细信息，请参阅[SURFACE UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="242f1-118">See [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md) for details.</span></span>

## <span data-ttu-id="242f1-119">Windows 版本注意事项</span><span class="sxs-lookup"><span data-stu-id="242f1-119">Windows version considerations</span></span>

<span data-ttu-id="242f1-120">通过 Windows Autopilot 广泛部署 Surface 设备（包括购买时 Surface 合作伙伴的注册）需要 Windows 10 版本1709（秋季创意者更新）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="242f1-120">Broad deployment of Surface devices through Windows Autopilot, including enrollment by Surface partners at the time of purchase, requires Windows 10 Version 1709 (Fall Creators Update) or later.</span></span>

<span data-ttu-id="242f1-121">这些 Windows 版本支持一个4000字节（4k）哈希值，该哈希值唯一标识 Windows Autopilot 的设备，这对于部署规模很有必要。</span><span class="sxs-lookup"><span data-stu-id="242f1-121">These Windows versions support a 4,000-byte (4k) hash value that uniquely identifies devices for Windows Autopilot, which is necessary for deployments at scale.</span></span> <span data-ttu-id="242f1-122">所有新的 Surface 设备（包括 Surface Pro 7、Surface Pro X 和 Surface 笔记本3）随 Windows 10 版本1903或更高版本一起提供。</span><span class="sxs-lookup"><span data-stu-id="242f1-122">All new Surface devices, including Surface Pro 7, Surface Pro X, and Surface Laptop 3, ship with Windows 10 Version 1903 or later.</span></span>

## <span data-ttu-id="242f1-123">需要维修或更换的 Surface 设备上的 Exchange 体验</span><span class="sxs-lookup"><span data-stu-id="242f1-123">Exchange experience on Surface devices in need of repair or replacement</span></span>

<span data-ttu-id="242f1-124">Microsoft 会自动检查每个 Surface 的 Autopilot 注册，并将该设备从客户的租户中注销。</span><span class="sxs-lookup"><span data-stu-id="242f1-124">Microsoft automatically checks every Surface for Autopilot enrollment and will deregister the device from the customer's tenant.</span></span>  <span data-ttu-id="242f1-125">Microsoft 可确保一旦向客户推出更换设备，即可将替换设备注册到 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="242f1-125">Microsoft ensures the replacement device is enrolled into Windows Autopilot once a replacement is shipped back to the customer.</span></span> <span data-ttu-id="242f1-126">此服务在所有设备 exchange 服务订单上通过 Microsoft 直接提供。</span><span class="sxs-lookup"><span data-stu-id="242f1-126">This service is available on all device exchange service orders directly with Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="242f1-127">当客户使用合作伙伴返回设备时，合作伙伴负责管理 exchange 流程，包括将设备注销和注册到 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="242f1-127">When customers use a Partner to return devices, the Partner is responsible for managing the exchange process including deregistering and enrolling devices into Windows Autopilot.</span></span>

## <span data-ttu-id="242f1-128">为 Windows Autopilot 启用的 Surface 合作伙伴</span><span class="sxs-lookup"><span data-stu-id="242f1-128">Surface partners enabled for Windows Autopilot</span></span>

<span data-ttu-id="242f1-129">选择 "Surface 合作伙伴" 可在购买时为您在 Windows Autopilot 中注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="242f1-129">Select Surface partners can enroll Surface devices in Windows Autopilot for you at the time of purchase.</span></span> <span data-ttu-id="242f1-130">他们还可以直接将注册的设备发运给你的用户。</span><span class="sxs-lookup"><span data-stu-id="242f1-130">They can also ship enrolled devices directly to your users.</span></span> <span data-ttu-id="242f1-131">通过使用 Windows Autopilot、Azure AD 和移动设备管理，可以完全通过零接触过程来配置设备。</span><span class="sxs-lookup"><span data-stu-id="242f1-131">The devices can be configured entirely through a zero-touch process by using Windows Autopilot, Azure AD, and mobile device management.</span></span>

<span data-ttu-id="242f1-132">为 Windows Autopilot 启用的 Surface 合作伙伴包括：</span><span class="sxs-lookup"><span data-stu-id="242f1-132">Surface partners that are enabled for Windows Autopilot include:</span></span>

| <span data-ttu-id="242f1-133">美国合作伙伴</span><span class="sxs-lookup"><span data-stu-id="242f1-133">US partners</span></span> | <span data-ttu-id="242f1-134">全球合作伙伴</span><span class="sxs-lookup"><span data-stu-id="242f1-134">Global partners</span></span> | <span data-ttu-id="242f1-135">美国分销商</span><span class="sxs-lookup"><span data-stu-id="242f1-135">US distributors</span></span> |
|--------------|---------------|-------------------|
| <span data-ttu-id="242f1-136">\* [CDW](https://www.cdw.com/)</span><span class="sxs-lookup"><span data-stu-id="242f1-136">\* [CDW](https://www.cdw.com/)</span></span> | <span data-ttu-id="242f1-137">\* [而且](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="242f1-137">\* [ALSO](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span></span> | <span data-ttu-id="242f1-138">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span><span class="sxs-lookup"><span data-stu-id="242f1-138">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span></span>  |
| <span data-ttu-id="242f1-139">\* [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)</span><span class="sxs-lookup"><span data-stu-id="242f1-139">\* [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)</span></span>   | <span data-ttu-id="242f1-140">\* [ATEA](https://www.atea.com/)</span><span class="sxs-lookup"><span data-stu-id="242f1-140">\* [ATEA](https://www.atea.com/)</span></span> | <span data-ttu-id="242f1-141">\* [Techdata](https://www.techdata.com/)</span><span class="sxs-lookup"><span data-stu-id="242f1-141">\* [Techdata](https://www.techdata.com/)</span></span>  |
| <span data-ttu-id="242f1-142">\* [知识](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span><span class="sxs-lookup"><span data-stu-id="242f1-142">\* [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span></span>  | <span data-ttu-id="242f1-143">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="242f1-143">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span></span> | <span data-ttu-id="242f1-144">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span><span class="sxs-lookup"><span data-stu-id="242f1-144">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span></span>   |
| <span data-ttu-id="242f1-145">\* [SHI](https://www.shi.com/Surface)</span><span class="sxs-lookup"><span data-stu-id="242f1-145">\* [SHI](https://www.shi.com/Surface)</span></span> | <span data-ttu-id="242f1-146">\* [Cancom](https://www.cancom.de/)</span><span class="sxs-lookup"><span data-stu-id="242f1-146">\* [Cancom](https://www.cancom.de/)</span></span> |    |
| <span data-ttu-id="242f1-147">\* [LDI 连接](https://www.myldi.com/managed-it/)</span><span class="sxs-lookup"><span data-stu-id="242f1-147">\* [LDI Connect](https://www.myldi.com/managed-it/)</span></span>  | <span data-ttu-id="242f1-148">\* [Computacenter](https://www.computacenter.com/uk)</span><span class="sxs-lookup"><span data-stu-id="242f1-148">\* [Computacenter](https://www.computacenter.com/uk)</span></span> |    |
| <span data-ttu-id="242f1-149">\* [了解](https://www.functiononeit.com/#empower)</span><span class="sxs-lookup"><span data-stu-id="242f1-149">\* [F1](https://www.functiononeit.com/#empower)</span></span>  |   |  |
| <span data-ttu-id="242f1-150">\* [受保护的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span><span class="sxs-lookup"><span data-stu-id="242f1-150">\* [Protected Trust](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span></span> | | | 

## <span data-ttu-id="242f1-151">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="242f1-151">Learn more</span></span>

<span data-ttu-id="242f1-152">有关 Windows Autopilot 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="242f1-152">For more information about Windows Autopilot, see:</span></span>
- [<span data-ttu-id="242f1-153">Windows Autopilot 概述</span><span class="sxs-lookup"><span data-stu-id="242f1-153">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [<span data-ttu-id="242f1-154">Windows Autopilot 要求</span><span class="sxs-lookup"><span data-stu-id="242f1-154">Windows Autopilot requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
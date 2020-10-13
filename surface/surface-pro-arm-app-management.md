---
title: 部署、管理和维护 Surface Pro X
description: 本文概述了部署、管理和维护 Surface Pro X 的主要注意事项。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 7d82a24126798c20f11c51074f6099e1363c257f
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114620"
---
# <span data-ttu-id="0b1ee-103">部署、管理和维护 Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="0b1ee-103">Deploying, managing, and servicing Surface Pro X</span></span>

## <span data-ttu-id="0b1ee-104">简介</span><span class="sxs-lookup"><span data-stu-id="0b1ee-104">Introduction</span></span>

<span data-ttu-id="0b1ee-105">Surface Pro X 专为满足高性能商业要求而构建，集成了在同类中功能最强大的处理器（即 Microsoft SQ1 和 Microsoft SQ1 ARM 芯片集），实现了新的突破。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-105">Built to handle high performance commercial requirements, Surface Pro X breaks new ground by incorporating the most powerful processors in its class, the Microsoft SQ1 and Microsoft SQ1 ARM chipsets.</span></span>

<span data-ttu-id="0b1ee-106">Surface Pro X 由 3 GHz CPU 和 2.1 万亿次浮点运算 GPU 提供支持，可提供完整的 Windows 体验。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-106">Powered by a 3GHz CPU and a 2.1 teraflop GPU, Surface Pro X provides a full Windows experience.</span></span> <span data-ttu-id="0b1ee-107">其具有 15 小时的电池使用时间、内置千兆 LTE 并兼有触控、手写笔、平板电脑和笔记本电脑功能，非常适合金融、法律和医疗领域的移动一线工作人员和专业人员，或者需要更长的电池使用时间和连续连接能力的任何角色。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-107">Its 15-hour battery life built-in Gigabit LTE and the versatility of touch, pen, tablet, and laptop make it ideally suited for mobile first-line workers and professionals across the financial, legal, and medical fields or any role demanding extended battery life and continuous connectivity capabilities.</span></span>

<span data-ttu-id="0b1ee-108">Surface Pro X 几乎专为基于云的现代环境而设计，搭配 Microsoft 365、Intune 和 Windows Autopilot 时效果最佳。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-108">Surface Pro X is designed almost exclusively for a modern, cloud-based environment and works best when paired with Microsoft 365, Intune and Windows Autopilot.</span></span> <span data-ttu-id="0b1ee-109">本文重点介绍了 Surface Pro X 的外观，并概述了部署、管理和维护 Surface Pro X 的主要注意事项。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-109">This article highlights what that looks like and outlines key considerations for deploying, managing, and servicing Surface Pro X.</span></span>

## <span data-ttu-id="0b1ee-110">部署 Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="0b1ee-110">Deploying Surface Pro X</span></span>

<span data-ttu-id="0b1ee-111">为了获得出色体验，请使用 Windows Autopilot 部署 Surface Pro X，可以依靠 Microsoft 云解决方案提供商的帮助，也可以使用 Autopilot 部署配置文件和相关功能自行设置。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-111">For the best experience, deploy Surface Pro X using Windows Autopilot either with the assistance of a Microsoft Cloud Solution Provider or self-provisioned using Autopilot deployment profiles and related features.</span></span> <span data-ttu-id="0b1ee-112">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="0b1ee-112">For more information, refer to:</span></span>

- [<span data-ttu-id="0b1ee-113">Windows Autopilot 和 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="0b1ee-113">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md)
- [<span data-ttu-id="0b1ee-114">Windows Autopilot 概述</span><span class="sxs-lookup"><span data-stu-id="0b1ee-114">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)

<span data-ttu-id="0b1ee-115">Autopilot 部署具有以下几个优点：为你提供出厂设置好的操作系统，针对零接触部署进行了优化，并预安装 Office 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-115">Autopilot deployment has several advantages: It allows you to use the factory provisioned operating system, streamlined for zero-touch deployment, to include pre-installation of Office Pro Plus.</span></span>

<span data-ttu-id="0b1ee-116">已经在使用现代管理、安全和工作效率解决方案的组织可充分利用 Surface Pro X 中独特的性能功能。使用现代化业务线应用、Microsoft Store (UWP) 应用或远程桌面解决方案的客户也可从中受益。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-116">Organizations already using modern management, security, and productivity solutions are well positioned to take advantage of the unique performance features in Surface Pro X. Customers using modernized line of business apps, Microsoft store (UWP) apps, or remote desktop solutions also stand to benefit.</span></span>

## <span data-ttu-id="0b1ee-117">基于映像的部署注意事项</span><span class="sxs-lookup"><span data-stu-id="0b1ee-117">Image-based deployment considerations</span></span>

<span data-ttu-id="0b1ee-118">Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager（以前称为 System Center Configuration Manager）当前不支持 Surface Pro X 的操作系统部署。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-118">Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager (formerly System Center Configuration Manager) currently do not support Surface Pro X for operating system deployment.</span></span> <span data-ttu-id="0b1ee-119">依赖基于映像的部署的客户在评估过渡到现代部署解决方案的正确时间时，应考虑采用 Surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-119">Customers relying on image-based deployment should consider Surface Pro 7 while they continue to evaluate the right time to transition to modern deployment solutions.</span></span> 

## <span data-ttu-id="0b1ee-120">管理 Surface Pro X 设备</span><span class="sxs-lookup"><span data-stu-id="0b1ee-120">Managing Surface Pro X devices</span></span>

### <span data-ttu-id="0b1ee-121">Intune</span><span class="sxs-lookup"><span data-stu-id="0b1ee-121">Intune</span></span>

<span data-ttu-id="0b1ee-122">作为 Microsoft 企业移动性 + 安全性的一个组成部分，Intune 与 Azure Active Directory 相集成，可实现身份和访问控制，并提供对已注册 Surface Pro X 设备的精细管理。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-122">A component of Microsoft Enterprise Mobility + Security, Intune integrates with Azure Active Directory for identity and access control and provides granular management of enrolled Surface Pro X devices.</span></span> <span data-ttu-id="0b1ee-123">与旧的本地工具（如 Windows 组策略）相比，Intune 移动设备管理 (MDM) 策略具有许多优点。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-123">Intune mobile device management (MDM) policies have a number of advantages over older on-premises tools such as Windows Group Policy.</span></span> <span data-ttu-id="0b1ee-124">其中包括设备登录时间缩短，策略目录更为简化，因此支持在云端进行全面设备管理。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-124">This includes faster device login times and a more streamlined catalog of policies enabling full device management from the cloud.</span></span> <span data-ttu-id="0b1ee-125">例如，你可以使用 eSIM 配置文件管理 LTE，以配置流量套餐并将激活代码部署到多台设备。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-125">For example, you can manage LTE using eSIM profiles to configure data plans and deploy activation codes to multiple devices.</span></span><br> 

<span data-ttu-id="0b1ee-126">有关使用 Intune 的详细信息，请参阅 [Intune 文档](https://docs.microsoft.com/intune/)。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-126">For more information about using Intune, refer to the [Intune documentation](https://docs.microsoft.com/intune/).</span></span>

### <span data-ttu-id="0b1ee-127">联合管理</span><span class="sxs-lookup"><span data-stu-id="0b1ee-127">Co-management</span></span>

<span data-ttu-id="0b1ee-128">在 Autopilot 中部署 Surface Pro X 设备后，你可以将其加入到 Azure AD 或 Active Directory（混合 Azure AD 联接），通过此服务你将能够使用 Intune 管理设备，或使用 Endpoint Configuration Manager 对设备进行联合管理（将会安装 32 位 x86 ConfigMgr 客户端）。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-128">Once deployed in Autopilot, you can join Surface Pro X devices to Azure AD or Active Directory (Hybrid Azure AD Join) where you will be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which will install the 32-bit x86 ConfigMgr client.</span></span>

### <span data-ttu-id="0b1ee-129">第三方 MDM 解决方案</span><span class="sxs-lookup"><span data-stu-id="0b1ee-129">Third party MDM solutions</span></span>

<span data-ttu-id="0b1ee-130">你可以使用第三方 MDM 工具管理 Surface Pro X 设备。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-130">You may be able to use third-party MDM tools to manage Surface Pro X devices.</span></span> <span data-ttu-id="0b1ee-131">有关详细信息，请联系 MDM 提供商。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-131">For details, contact your MDM provider.</span></span>

### <span data-ttu-id="0b1ee-132">防病毒软件</span><span class="sxs-lookup"><span data-stu-id="0b1ee-132">Antivirus software</span></span>

<span data-ttu-id="0b1ee-133">在 Windows 10 设备受支持的生命周期内，Windows Defender 将保护基于 ARM 的电脑上的 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-133">Windows Defender will help protect Windows 10 on ARM-based PCs for the supported lifetime of the Windows 10 device.</span></span> 

<span data-ttu-id="0b1ee-134">某些第三方防病毒软件无法安装到采用 ARM 处理器的 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-134">Some third-party antivirus software cannot be installed on a Windows 10 PC running on an ARM-based processor.</span></span> <span data-ttu-id="0b1ee-135">与第三方防病毒软件提供商的协作仍在继续，以确保 AV 应用在基于 ARM 的电脑上的就绪度。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-135">Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs.</span></span> <span data-ttu-id="0b1ee-136">请联系你的防病毒软件提供商，了解其应用何时可用。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-136">Contact your antivirus software provider to understand when their apps will be available.</span></span>

## <span data-ttu-id="0b1ee-137">维护 Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="0b1ee-137">Servicing Surface Pro X</span></span>

<span data-ttu-id="0b1ee-138">Surface Pro X 随附 Windows 10 版本 2004 并支持 Windows 10 版本 1903 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-138">Surface Pro X ships with Windows 10 version 2004 and supports Windows 10, version 1903 and later.</span></span> <span data-ttu-id="0b1ee-139">作为一台基于 ARM 的设备，它对于保持最新的驱动程序和固件有着特定要求。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-139">As an ARM-based device, it has specific requirements for maintaining the latest drivers and firmware.</span></span> 

<span data-ttu-id="0b1ee-140">Surface Pro X 可使用 Windows 更新来简化将驱动程序和固件保持最新的过程，这对家庭用户和小型企业用户均适用。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-140">Surface Pro X was designed to use Windows Update to simplify the process of keeping drivers and firmware up to date for both home users and small business users.</span></span> <span data-ttu-id="0b1ee-141">使用默认设置接收自动更新。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-141">Use the default settings to receive Automatic updates.</span></span>  <span data-ttu-id="0b1ee-142">如需进行验证，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0b1ee-142">To verify:</span></span>

1. <span data-ttu-id="0b1ee-143">转到**开始** > **设置 > 更新和安全 > Windows 更新** > **高级选项**。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-143">Go to **Start** > **Settings > Update & Security > Windows Update** > **Advanced Options.**</span></span>
2. <span data-ttu-id="0b1ee-144">在**选择安装更新的方式**下，选择**自动(建议)**。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-144">Under **Choose how updates are installed,** select **Automatic (recommended)**.</span></span>

### <span data-ttu-id="0b1ee-145">针对商业客户的建议</span><span class="sxs-lookup"><span data-stu-id="0b1ee-145">Recommendations for commercial customers</span></span>

- <span data-ttu-id="0b1ee-146">使用 Windows 更新或适用于企业的 Windows 更新来维护最新的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-146">Use Windows Update or Windows Update for Business for maintaining the latest drivers and firmware.</span></span> <span data-ttu-id="0b1ee-147">有关详细信息，请参阅[使用适用于企业的 Windows 更新部署更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-147">For more information, see [Deploy Updates using Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).</span></span>
- <span data-ttu-id="0b1ee-148">有关部署和管理 Surface 设备更新的更多信息，参见“[管理和部署 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)”。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-148">For more information about deploying and managing updates on Surface devices, see [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span>
- <span data-ttu-id="0b1ee-149">请注意，Windows Server Update Services (WSUS) 不支持向 Surface Pro X 提供驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-149">Note that Windows Server Update Services (WSUS) does not support the ability to deliver drivers and firmware to Surface Pro X.</span></span>

## <span data-ttu-id="0b1ee-150">在 Surface Pro X 上运行应用</span><span class="sxs-lookup"><span data-stu-id="0b1ee-150">Running apps on Surface Pro X</span></span>

<span data-ttu-id="0b1ee-151">大多数应用在基于 ARM 的 Windows 10 电脑上运行，少数应用除外。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-151">Most apps run on ARM-based Windows 10 PCs with limited exclusions.</span></span>

### <span data-ttu-id="0b1ee-152">支持的应用</span><span class="sxs-lookup"><span data-stu-id="0b1ee-152">Supported apps</span></span>

- <span data-ttu-id="0b1ee-153">大多数 x86 Win32 应用都能在 Surface Pro X 上运行。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-153">Most x86 Win32 apps run on Surface Pro X.</span></span>
- <span data-ttu-id="0b1ee-154">本机 ARM64 和 Microsoft Store UWP 应用充分发挥了基于 ARM 的处理器的本机速度，同时优化了电池使用时间，从而提供了出色的用户体验。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-154">Native ARM64 and Microsoft Store UWP apps provide an excellent user experience utilizing the full native speed of the ARM-based processor while optimizing battery life.</span></span>
- <span data-ttu-id="0b1ee-155">使用专为采用 ARM 处理器的 Windows 10 电脑设计的驱动程序的应用。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-155">Apps that use drivers designed for a Windows 10 PC running on an ARM-based processor.</span></span>

> [!NOTE]
> <span data-ttu-id="0b1ee-156">通过 Windows 预览体验计划即将在预览版中提供 64 位仿真功能，你将能够在 Surface Pro X 上运行 64 位 (x64) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-156">With 64-bit emulation coming soon in Preview via the Windows Insider program, you'll be able to run 64-bit (x64) apps on Surface Pro X.</span></span>

### <span data-ttu-id="0b1ee-157">FastTrack 应用保证</span><span class="sxs-lookup"><span data-stu-id="0b1ee-157">FastTrack App Assure</span></span> 

<span data-ttu-id="0b1ee-158">应用保证计划适用于商业客户的 LOB、ISV 和面向基于 ARM 的 Windows 10 的 Microsoft 第一方应用。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-158">The App Assure program is available to commercial customers for their LOB, ISV and Microsoft first-party apps targeting Windows 10 on ARM.</span></span> <span data-ttu-id="0b1ee-159">如果商业客户使用基于 ARM 的 Windows 10 时遇到应用兼容性问题，Microsoft 将提供开发人员资源，无需额外付费即可对应用修正进行疑难解答并提供帮助。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-159">If commercial customers encounter an app compatibility issue using Windows 10 on ARM, Microsoft will provide developer resources to troubleshoot and assist with app remediations, at no additional cost.</span></span> <span data-ttu-id="0b1ee-160">若要了解详细信息，请访问 [aka.ms/AppAssure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure)。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-160">To learn more,visit [aka.ms/AppAssure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure).</span></span>

<span data-ttu-id="0b1ee-161">有关在 Surface Pro X 上运行应用的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="0b1ee-161">For more information about running apps on Surface Pro X, refer to:</span></span>

- [<span data-ttu-id="0b1ee-162">基于 ARM 的 Windows 10 电脑支持常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0b1ee-162">Windows 10 ARM-based PCs Support FAQ</span></span>](https://support.microsoft.com/help/4521606)
- [<span data-ttu-id="0b1ee-163">基于 ARM 的 Windows 10 文档</span><span class="sxs-lookup"><span data-stu-id="0b1ee-163">Windows 10 on ARM documentation</span></span>](https://docs.microsoft.com/windows/arm)

## <span data-ttu-id="0b1ee-164">虚拟桌面 (VDI)</span><span class="sxs-lookup"><span data-stu-id="0b1ee-164">Virtual Desktops (VDI)</span></span>

<span data-ttu-id="0b1ee-165">Windows 虚拟桌面允许从任何位置访问 Windows 桌面、应用程序和任何计算设备或平台上的数据。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-165">Windows Virtual Desktop enables access to Windows desktops,applications, and data on any computing device or platform, from any location.</span></span> <span data-ttu-id="0b1ee-166">如需了解详细信息，请参阅 [Windows 虚拟桌面站点](https://aka.ms/wvd)。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-166">To learn more, refer to the [Windows Virtual Desktop site](https://aka.ms/wvd).</span></span> 

## <span data-ttu-id="0b1ee-167">使用 Surface Pro X 浏览</span><span class="sxs-lookup"><span data-stu-id="0b1ee-167">Browsing with Surface Pro X</span></span>

<span data-ttu-id="0b1ee-168">很多热门浏览器在 Surface Pro X 上运行：</span><span class="sxs-lookup"><span data-stu-id="0b1ee-168">Popular browsers run on Surface Pro X:</span></span>

- <span data-ttu-id="0b1ee-169">设备自带的 Edge、Firefox、Chrome 和 Internet Explorer 均可在 Surface Pro X 上运行。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-169">In-box Edge, Firefox, Chrome, and Internet Explorer all run on Surface Pro X.</span></span>
- <span data-ttu-id="0b1ee-170">基于 Chromium 的 Firefox 和 Microsoft Edge 均在本机运行，因此在采用 ARM 处理器的 Windows 10 电脑上性能有所增强。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-170">Firefox and Microsoft Edge based on Chromium run natively and therefore have enhanced performance on a Windows 10 PC on an ARM-based processor.</span></span>

## <span data-ttu-id="0b1ee-171">安装和使用 Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="0b1ee-171">Installing and using Microsoft Office</span></span>

- <span data-ttu-id="0b1ee-172">在采用 ARM 处理器的 Windows 10 电脑上，使用 Office 365 获得出色体验。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-172">Use Office 365 for the best experience on a Windows 10 PC on an ARM-based processor.</span></span>
- <span data-ttu-id="0b1ee-173">Office 365“即点即用”安装了 Outlook、Word、Excel 和 PowerPoint，这些程序已进行优化，可在采用 ARM 处理器的 Windows 10 电脑上运行。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-173">Office 365 "click-to-run" installs Outlook, Word, Excel, and PowerPoint, optimized to run on a Windows 10 PC on an ARM-based processor.</span></span>
- <span data-ttu-id="0b1ee-174">Microsoft Teams 在 Surface Pro X 上的运行效果出色。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-174">Microsoft Teams runs great on Surface Pro X.</span></span>
- <span data-ttu-id="0b1ee-175">对于 Office 的“永久版本”（例如 Office 2019），请安装 32 位版本。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-175">For "perpetual versions" of Office such as Office 2019, install the 32-bit version.</span></span>

## <span data-ttu-id="0b1ee-176">VPN</span><span class="sxs-lookup"><span data-stu-id="0b1ee-176">VPN</span></span>

<span data-ttu-id="0b1ee-177">如需确认特定的第三方 VPN 是否支持采用 ARM 处理器的 Windows 10 电脑，请联系 VPN 提供商。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-177">To confirm if a specific third-party VPN supports a Windows 10 PC on an ARM-based processor, contact the VPN provider.</span></span>

## <span data-ttu-id="0b1ee-178">功能摘要</span><span class="sxs-lookup"><span data-stu-id="0b1ee-178">Feature summary</span></span>

<span data-ttu-id="0b1ee-179">下表展示了所选关键功能在 Surface Pro X（采用基于 ARM 的 Windows 10 系统）上的可用性。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-179">The following tables show the availability of selected key features on Surface Pro X with Windows 10 on ARM.</span></span>


**<span data-ttu-id="0b1ee-180">部署</span><span class="sxs-lookup"><span data-stu-id="0b1ee-180">Deployment</span></span>**

| <span data-ttu-id="0b1ee-181">功能</span><span class="sxs-lookup"><span data-stu-id="0b1ee-181">Feature</span></span>                                                           | <span data-ttu-id="0b1ee-182">是/否</span><span class="sxs-lookup"><span data-stu-id="0b1ee-182">Y/N</span></span> | <span data-ttu-id="0b1ee-183">注释</span><span class="sxs-lookup"><span data-stu-id="0b1ee-183">Notes</span></span>                                                                                                                             |
| ----------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="0b1ee-184">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="0b1ee-184">Windows Autopilot</span></span>                                                 | <span data-ttu-id="0b1ee-185">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-185">Yes</span></span> |                                                                                                                                   |
| <span data-ttu-id="0b1ee-186">支持网络启动 (PXE)</span><span class="sxs-lookup"><span data-stu-id="0b1ee-186">Support for Network Boot (PXE)</span></span>                                    | <span data-ttu-id="0b1ee-187">否</span><span class="sxs-lookup"><span data-stu-id="0b1ee-187">No</span></span>  |                                                                                                                                   |
| <span data-ttu-id="0b1ee-188">Windows 配置设计器</span><span class="sxs-lookup"><span data-stu-id="0b1ee-188">Windows Configuration Designer</span></span>                                    | <span data-ttu-id="0b1ee-189">否</span><span class="sxs-lookup"><span data-stu-id="0b1ee-189">No</span></span>  | <span data-ttu-id="0b1ee-190">不建议用于 Surface Pro X。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-190">Not recommended for Surface Pro X.</span></span>                                                                                                |
| <span data-ttu-id="0b1ee-191">WinPE</span><span class="sxs-lookup"><span data-stu-id="0b1ee-191">WinPE</span></span>                                                             | <span data-ttu-id="0b1ee-192">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-192">Yes</span></span> | <span data-ttu-id="0b1ee-193">不建议用于 Surface Pro X。Microsoft 不提供 Surface Pro X 支持 WinPE 所需的 .ISO 和驱动程序。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-193">Not recommended for Surface Pro X. Microsoft does not provide the necessary .ISO and drivers to support WinPE with Surface Pro X.</span></span> |
| <span data-ttu-id="0b1ee-194">Endpoint Configuration Manager：操作系统部署 (OSD)</span><span class="sxs-lookup"><span data-stu-id="0b1ee-194">Endpoint Configuration Manager: Operating System Deployment (OSD)</span></span> | <span data-ttu-id="0b1ee-195">否</span><span class="sxs-lookup"><span data-stu-id="0b1ee-195">No</span></span>  | <span data-ttu-id="0b1ee-196">在 Surface Pro X 上不支持。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-196">Not supported on Surface Pro X.</span></span>                                                                                                   |
| <span data-ttu-id="0b1ee-197">MDT</span><span class="sxs-lookup"><span data-stu-id="0b1ee-197">MDT</span></span>                                                               | <span data-ttu-id="0b1ee-198">否</span><span class="sxs-lookup"><span data-stu-id="0b1ee-198">No</span></span>  | <span data-ttu-id="0b1ee-199">在 Surface Pro X 上不支持。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-199">Not supported on Surface Pro X.</span></span>                                                                                                   |

 
 
 **<span data-ttu-id="0b1ee-200">管理</span><span class="sxs-lookup"><span data-stu-id="0b1ee-200">Management</span></span>**
 

| <span data-ttu-id="0b1ee-201">功能</span><span class="sxs-lookup"><span data-stu-id="0b1ee-201">Feature</span></span>                                       | <span data-ttu-id="0b1ee-202">是/否</span><span class="sxs-lookup"><span data-stu-id="0b1ee-202">Y/N</span></span>     | <span data-ttu-id="0b1ee-203">注释</span><span class="sxs-lookup"><span data-stu-id="0b1ee-203">Notes</span></span>                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="0b1ee-204">Intune</span><span class="sxs-lookup"><span data-stu-id="0b1ee-204">Intune</span></span>                                        | <span data-ttu-id="0b1ee-205">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-205">Yes</span></span>     | <span data-ttu-id="0b1ee-206">使用 eSIM 配置文件管理 LTE。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-206">Manage LTE with eSIM profiles.</span></span>                                                        |
| <span data-ttu-id="0b1ee-207">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="0b1ee-207">Windows Autopilot</span></span>                             | <span data-ttu-id="0b1ee-208">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-208">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="0b1ee-209">Azure AD（联合管理）</span><span class="sxs-lookup"><span data-stu-id="0b1ee-209">Azure AD (co-management)</span></span>                      | <span data-ttu-id="0b1ee-210">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-210">Yes</span></span>     | <span data-ttu-id="0b1ee-211">将 Surface Pro X 加入到 Azure AD 或 Active Directory（混合 Azure AD 联接）的功能。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-211">Ability to join Surface Pro X to Azure AD or Active Directory (Hybrid Azure AD Join).</span></span> |
| <span data-ttu-id="0b1ee-212">Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0b1ee-212">Endpoint Configuration Manager</span></span>                | <span data-ttu-id="0b1ee-213">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-213">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="0b1ee-214">当 AC 恢复时开机</span><span class="sxs-lookup"><span data-stu-id="0b1ee-214">Power on When AC Restore</span></span>                      | <span data-ttu-id="0b1ee-215">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-215">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="0b1ee-216">适用于企业的 Surface 诊断工具包 (SDT)</span><span class="sxs-lookup"><span data-stu-id="0b1ee-216">Surface Diagnostic Toolkit (SDT) for Business</span></span> | <span data-ttu-id="0b1ee-217">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-217">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="0b1ee-218">Surface 资产标记工具</span><span class="sxs-lookup"><span data-stu-id="0b1ee-218">Surface Asset Tag tool</span></span>                        | <span data-ttu-id="0b1ee-219">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-219">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="0b1ee-220">Surface 企业管理模式 (SEMM)</span><span class="sxs-lookup"><span data-stu-id="0b1ee-220">Surface Enterprise management Mode (SEMM)</span></span>     | <span data-ttu-id="0b1ee-221">部分</span><span class="sxs-lookup"><span data-stu-id="0b1ee-221">Partial</span></span> | <span data-ttu-id="0b1ee-222">不支持在固件级别禁用 Surface Pro X 上的硬件。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-222">No option to disable hardware on Surface Pro X at the firmware level.</span></span>                 |
| <span data-ttu-id="0b1ee-223">Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="0b1ee-223">Surface UEFI Configurator</span></span>                     | <span data-ttu-id="0b1ee-224">否</span><span class="sxs-lookup"><span data-stu-id="0b1ee-224">No</span></span>      | <span data-ttu-id="0b1ee-225">不支持在固件级别</span><span class="sxs-lookup"><span data-stu-id="0b1ee-225">No option to disable hardware.</span></span> <span data-ttu-id="0b1ee-226">禁用 Surface Pro X 上的硬件。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-226">on Surface Pro X at the firmware level.</span></span>                |
| <span data-ttu-id="0b1ee-227">Surface UEFI 管理器</span><span class="sxs-lookup"><span data-stu-id="0b1ee-227">Surface UEFI Manager</span></span>                          | <span data-ttu-id="0b1ee-228">部分</span><span class="sxs-lookup"><span data-stu-id="0b1ee-228">Partial</span></span> | <span data-ttu-id="0b1ee-229">不支持在固件级别禁用 Surface Pro X 上的硬件。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-229">No option to disable hardware on Surface Pro X at the firmware level.</span></span>                 |

 

**<span data-ttu-id="0b1ee-230">安全性</span><span class="sxs-lookup"><span data-stu-id="0b1ee-230">Security</span></span>**
 

 <span data-ttu-id="0b1ee-231">功能</span><span class="sxs-lookup"><span data-stu-id="0b1ee-231">Feature</span></span>                                       | <span data-ttu-id="0b1ee-232">是/否</span><span class="sxs-lookup"><span data-stu-id="0b1ee-232">Y/N</span></span>     | <span data-ttu-id="0b1ee-233">注释</span><span class="sxs-lookup"><span data-stu-id="0b1ee-233">Notes</span></span>                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="0b1ee-234">BitLocker</span><span class="sxs-lookup"><span data-stu-id="0b1ee-234">BitLocker</span></span>                                     | <span data-ttu-id="0b1ee-235">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-235">Yes</span></span>     |                                                       |
| <span data-ttu-id="0b1ee-236">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="0b1ee-236">Windows Defender</span></span>                              | <span data-ttu-id="0b1ee-237">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-237">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="0b1ee-238">支持第三方防病毒程序</span><span class="sxs-lookup"><span data-stu-id="0b1ee-238">Support for third-party antivirus</span></span>             | <span data-ttu-id="0b1ee-239">查看说明</span><span class="sxs-lookup"><span data-stu-id="0b1ee-239">See note</span></span>| <span data-ttu-id="0b1ee-240">某些第三方防病毒软件无法安装到采用 ARM 处理器的 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-240">Some third-party antivirus software cannot be installed on a Windows 10 PC running on an ARM-based processor.</span></span> <span data-ttu-id="0b1ee-241">与第三方防病毒软件提供商的协作仍在继续，以确保 AV 应用在基于 ARM 的电脑上的就绪度。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-241">Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs.</span></span> <span data-ttu-id="0b1ee-242">请联系你的防病毒软件提供商，了解其应用何时可用。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-242">Contact your antivirus software provider to understand when their apps will be available.</span></span> |
| <span data-ttu-id="0b1ee-243">安全启动</span><span class="sxs-lookup"><span data-stu-id="0b1ee-243">Secure Boot</span></span>               | <span data-ttu-id="0b1ee-244">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-244">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="0b1ee-245">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="0b1ee-245">Windows Information Protection</span></span>                      | <span data-ttu-id="0b1ee-246">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-246">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="0b1ee-247">Surface Data Eraser (SDE)</span><span class="sxs-lookup"><span data-stu-id="0b1ee-247">Surface Data Eraser (SDE)</span></span>     | <span data-ttu-id="0b1ee-248">是</span><span class="sxs-lookup"><span data-stu-id="0b1ee-248">Yes</span></span>     |                                                                                       |




## <span data-ttu-id="0b1ee-249">常见问题</span><span class="sxs-lookup"><span data-stu-id="0b1ee-249">FAQ</span></span>

### <span data-ttu-id="0b1ee-250">我能否使用 MDT 或 Endpoint Configuration Manager 部署 Surface Pro X？</span><span class="sxs-lookup"><span data-stu-id="0b1ee-250">Can I deploy Surface Pro X with MDT or Endpoint Configuration Manager?</span></span>

<span data-ttu-id="0b1ee-251">Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager 当前不支持 Surface Pro X 的操作系统部署。依赖基于映像的部署的客户在评估过渡到云的正确时间时，应考虑采用 Surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-251">The Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager  currently do not support Surface Pro X for operating system deployment.Customers relying on image-based deployment should consider Surface Pro 7 while they continue to evaluate the right time to transition to the cloud.</span></span>

### <span data-ttu-id="0b1ee-252">我可以如何部署 Surface Pro X？</span><span class="sxs-lookup"><span data-stu-id="0b1ee-252">How can I deploy Surface Pro X?</span></span>

<span data-ttu-id="0b1ee-253">使用 Windows Autopilot 部署 Surface Pro X。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-253">Deploy Surface Pro X using Windows Autopilot.</span></span>

### <span data-ttu-id="0b1ee-254">BMR 是否可用？</span><span class="sxs-lookup"><span data-stu-id="0b1ee-254">Is a BMR available?</span></span>

<span data-ttu-id="0b1ee-255">是的，请参阅 [为 Surface 下载恢复映像](https://support.microsoft.com/surfacerecoveryimage)。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-255">Yes, refer to [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).</span></span>

### <span data-ttu-id="0b1ee-256">是否必须使用 Intune 来管理 Surface Pro X？</span><span class="sxs-lookup"><span data-stu-id="0b1ee-256">Is Intune required to manage Surface Pro X?</span></span>

<span data-ttu-id="0b1ee-257">建议使用 Intune，但并非强制要求。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-257">Intune is recommended but not required.</span></span> <span data-ttu-id="0b1ee-258">在 Autopilot 中部署 Surface Pro X 设备后，你可以将其加入到 Azure AD 或 Active Directory（混合 Azure AD 联接），通过此服务你将能够使用 Intune 管理设备，或使用 Endpoint Configuration Manager 对设备进行联合管理（将会安装 32 位 x86 ConfigMgr 客户端）。</span><span class="sxs-lookup"><span data-stu-id="0b1ee-258">Once deployed in Autopilot, you can join Surface Pro X devices to Azure AD or Active Directory (Hybrid Azure AD Join) where you will be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which will install the 32-bit x86 ConfigMgr client.</span></span>

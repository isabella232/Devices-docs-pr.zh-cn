---
title: 管理和部署 Surface 驱动程序和固件更新
description: 本文介绍用于管理和部署 Surface 设备的固件和驱动程序更新的可用选项。
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, 固件, 更新, 设备, 管理, 部署, 驱动程序, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: f41974193d62e4c0cbc1e286976105c20534d906
ms.sourcegitcommit: ed4478dd3c6116a25b1e01a3a0f5ff6c1f940013
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "10897060"
---
# <span data-ttu-id="84d02-104">管理和部署 Surface 驱动程序和固件更新</span><span class="sxs-lookup"><span data-stu-id="84d02-104">Manage and deploy Surface driver and firmware updates</span></span>

<span data-ttu-id="84d02-105">管理图面驱动程序和固件更新的方式取决于你的环境和组织要求。</span><span class="sxs-lookup"><span data-stu-id="84d02-105">How you manage Surface driver and firmware updates varies depending on your environment and organizational requirements.</span></span> <span data-ttu-id="84d02-106">在 Surface 设备上，固件作为驱动程序公开给操作系统，并且在设备管理器中可见。</span><span class="sxs-lookup"><span data-stu-id="84d02-106">On Surface devices, firmware is exposed to the operating system as a driver and is visible in Device Manager.</span></span> <span data-ttu-id="84d02-107">这使设备固件和驱动程序能够使用 Windows 更新或 Windows 更新企业版自动更新。</span><span class="sxs-lookup"><span data-stu-id="84d02-107">This enables device firmware and drivers to be automatically updated using Windows Update or Windows Update for Business.</span></span> <span data-ttu-id="84d02-108">虽然这种简化的方法对于启动和小型企业或中型企业来说可能是可行的，但是大型组织通常需要 IT 管理员在内部分发更新。</span><span class="sxs-lookup"><span data-stu-id="84d02-108">Although this simplified approach may be feasible for startups and small or medium-sized businesses, larger organizations typically need IT admins to distribute updates internally.</span></span> <span data-ttu-id="84d02-109">这可能涉及全面规划、应用程序兼容性测试、试验和验证更新，然后再通过网络进行最终批准和分发。</span><span class="sxs-lookup"><span data-stu-id="84d02-109">This may involve comprehensive planning, application compatibility testing, and piloting and validating updates before final approval and distribution across the network.</span></span>

> [!NOTE]
> <span data-ttu-id="84d02-110">本文面向技术支持工程师和 IT 专业人士，仅适用于 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="84d02-110">This article is intended for technical support agents and IT professionals and applies to Surface devices only.</span></span> <span data-ttu-id="84d02-111">如果在家庭设备上查找有关安装 Surface 更新或固件的帮助，请参阅[更新 Surface 固件和 Windows 10](https://support.microsoft.com/help/4023505)。</span><span class="sxs-lookup"><span data-stu-id="84d02-111">If you're looking for help to install Surface updates or firmware on a home device, see [Update Surface firmware and Windows 10](https://support.microsoft.com/help/4023505).</span></span>

<span data-ttu-id="84d02-112">虽然企业级软件分发解决方案继续发展，但集中管理更新的业务基本原理仍保持不变：维护 Surface 设备的安全，并使其在最新操作系统和功能改进中保持更新。</span><span class="sxs-lookup"><span data-stu-id="84d02-112">While enterprise-grade software distribution solutions continue to evolve, the business rationale for centrally managing  updates remains the same: Maintain the security of Surface devices and keep them updated with the latest operating system and feature improvements.</span></span> <span data-ttu-id="84d02-113">这对于维持稳定的生产环境非常重要，并且确保用户不会被阻止，从而提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="84d02-113">This is essential for sustaining a stable production environment and making sure that users aren't blocked from being productive.</span></span> <span data-ttu-id="84d02-114">本文概述了针对大型组织实现这些目标所推荐的工具和流程。</span><span class="sxs-lookup"><span data-stu-id="84d02-114">This article provides an overview of recommended tools and processes for larger organizations to accomplish these goals.</span></span>

## <span data-ttu-id="84d02-115">商业环境中的中央更新管理</span><span class="sxs-lookup"><span data-stu-id="84d02-115">Central update management in commercial environments</span></span>

<span data-ttu-id="84d02-116">Microsoft 具有用于管理设备（包括驱动程序和固件更新）的优化工具，以名为[Microsoft 终结点管理器管理中心](https://devicemanagement.microsoft.com/)并从[devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home)访问的单个统一体验。</span><span class="sxs-lookup"><span data-stu-id="84d02-116">Microsoft has streamlined tools for managing devices – including driver and firmware updates -- into a single unified experience that is named [Microsoft Endpoint Manager admin center](https://devicemanagement.microsoft.com/) and is accessed from [devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home).</span></span>

### <span data-ttu-id="84d02-117">管理配置管理器和 Intune 的更新</span><span class="sxs-lookup"><span data-stu-id="84d02-117">Manage updates with Configuration Manager and Intune</span></span>

<span data-ttu-id="84d02-118">Microsoft 终结点配置管理器允许你通过 Configuration Manager 客户端同步和部署 Surface 固件和驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="84d02-118">Microsoft Endpoint Configuration Manager allows you to synchronize and deploy Surface firmware and driver updates with the Configuration Manager client.</span></span> <span data-ttu-id="84d02-119">通过与 Microsoft Intune 的集成，你可以在一个位置查看所有托管、共同管理和合作伙伴管理的设备。</span><span class="sxs-lookup"><span data-stu-id="84d02-119">Integration with Microsoft Intune lets you see all your managed, co-managed, and partner-managed devices in one place.</span></span> <span data-ttu-id="84d02-120">这是适用于大型组织管理图面更新的推荐解决方案。</span><span class="sxs-lookup"><span data-stu-id="84d02-120">This is the recommended solution for large organizations to manage Surface updates.</span></span>

<span data-ttu-id="84d02-121">有关详细步骤，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="84d02-121">For detailed steps, see the following resources:</span></span>

- [<span data-ttu-id="84d02-122">管理 Configuration Manager 中的 Surface 更新</span><span class="sxs-lookup"><span data-stu-id="84d02-122">Manage Surface driver updates in Configuration Manager</span></span>](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [<span data-ttu-id="84d02-123">通过 Configuration Manager 部署应用程序</span><span class="sxs-lookup"><span data-stu-id="84d02-123">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [<span data-ttu-id="84d02-124">终结点配置管理器文档</span><span class="sxs-lookup"><span data-stu-id="84d02-124">Endpoint Configuration Manager documentation</span></span>](https://docs.microsoft.com/configmgr/)

### <span data-ttu-id="84d02-125">通过 Microsoft 部署工具包管理更新</span><span class="sxs-lookup"><span data-stu-id="84d02-125">Manage updates with Microsoft Deployment Toolkit</span></span>

<span data-ttu-id="84d02-126">Microsoft 部署工具包（MDT）包含在终结点配置管理器中。</span><span class="sxs-lookup"><span data-stu-id="84d02-126">The Microsoft Deployment Toolkit (MDT) is included in Endpoint Configuration Manager.</span></span> <span data-ttu-id="84d02-127">它包含你可能希望使用的可选部署工具，具体取决于你的环境。</span><span class="sxs-lookup"><span data-stu-id="84d02-127">It contains optional deployment tools that you may want to use, depending on your environment.</span></span> <span data-ttu-id="84d02-128">其中包括 Windows 评估和部署工具包（Windows ADK）、Windows 系统映像管理器（Windows SIM）、部署映像服务和管理（DISM）和用户状态迁移工具（USMT）。</span><span class="sxs-lookup"><span data-stu-id="84d02-128">These include the Windows Assessment and Deployment Kit (Windows ADK), Windows System Image Manager (Windows SIM), Deployment Image Servicing and Management (DISM), and User State Migration Tool (USMT).</span></span> <span data-ttu-id="84d02-129">您可以从 " [Microsoft 部署工具包下载" 页面](https://www.microsoft.com/download/details.aspx?id=54259)下载最新版本的 MDT。</span><span class="sxs-lookup"><span data-stu-id="84d02-129">You can download the latest version of MDT from the [Microsoft Deployment Toolkit download page](https://www.microsoft.com/download/details.aspx?id=54259).</span></span>

<span data-ttu-id="84d02-130">有关详细步骤，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="84d02-130">For detailed steps, see the following resources:</span></span>

- [<span data-ttu-id="84d02-131">Microsoft 部署工具包文档</span><span class="sxs-lookup"><span data-stu-id="84d02-131">Microsoft Deployment Toolkit documentation</span></span>](https://docs.microsoft.com/configmgr/mdt/)
- [<span data-ttu-id="84d02-132">使用 Microsoft 部署工具包部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="84d02-132">Deploy Windows 10 with the Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [<span data-ttu-id="84d02-133">通过 Microsoft 部署工具包将 Windows 10 部署到 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="84d02-133">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

<span data-ttu-id="84d02-134">Surface driver 和固件更新打包为 Windows Installer （\* .msi）文件。</span><span class="sxs-lookup"><span data-stu-id="84d02-134">Surface driver and firmware updates are packaged as Windows Installer (\*.msi) files.</span></span> <span data-ttu-id="84d02-135">若要部署这些 Windows Installer 程序包，可以使用终结点配置管理器或 MDT。</span><span class="sxs-lookup"><span data-stu-id="84d02-135">To deploy these Windows Installer packages, you can use Endpoint Configuration Manager or MDT.</span></span> <span data-ttu-id="84d02-136">有关如何为设备和操作系统选择正确的 .msi 文件的信息，请参阅以下部分中有关下载 .msi 文件的指南。</span><span class="sxs-lookup"><span data-stu-id="84d02-136">For information about how to select the correct .msi file for a device and operating system, refer to the guidance in the following sections about downloading .msi files.</span></span>

<span data-ttu-id="84d02-137">有关如何使用终结点配置管理器部署更新的说明，请参阅使用[Configuration Manager 部署应用程序](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)。</span><span class="sxs-lookup"><span data-stu-id="84d02-137">For instructions about how to deploy updates by using Endpoint Configuration Manager, see [Deploy applications with Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications).</span></span> <span data-ttu-id="84d02-138">有关如何使用 MDT 部署更新的说明，请参阅[使用 Mdt 部署 Windows 10 映像](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)。</span><span class="sxs-lookup"><span data-stu-id="84d02-138">For instructions about how to deploy updates by using MDT, see [Deploy a Windows 10 image using MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).</span></span>

**<span data-ttu-id="84d02-139">WindowsPE 和 Surface 固件和驱动程序</span><span class="sxs-lookup"><span data-stu-id="84d02-139">WindowsPE and Surface firmware and drivers</span></span>**

<span data-ttu-id="84d02-140">终结点配置管理器和 MDT 在部署过程中均使用 Windows 预安装环境（WindowsPE）。</span><span class="sxs-lookup"><span data-stu-id="84d02-140">Endpoint Configuration Manager and MDT both use the Windows Preinstallation Environment (WindowsPE) during the deployment process.</span></span> <span data-ttu-id="84d02-141">WindowsPE 仅支持一组有限的基本驱动程序，例如用于网络适配器和存储控制器的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="84d02-141">WindowsPE supports only a limited set of basic drivers such as those for network adapters and storage controllers.</span></span> <span data-ttu-id="84d02-142">不属于 WindowsPE 的 Windows 组件的驱动程序可能会产生错误。</span><span class="sxs-lookup"><span data-stu-id="84d02-142">Drivers for Windows components that are not part of WindowsPE might produce errors.</span></span> <span data-ttu-id="84d02-143">最佳做法是将部署过程配置为仅在 WindowsPE 阶段使用所需的驱动程序，从而阻止此类错误。</span><span class="sxs-lookup"><span data-stu-id="84d02-143">As a best practice, you can prevent such errors by configuring the deployment process to use only the required drivers during the WindowsPE phase.</span></span>

### <span data-ttu-id="84d02-144">Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="84d02-144">Endpoint Configuration Manager</span></span>

<span data-ttu-id="84d02-145">从终结点配置管理器开始，你可以使用 Configuration Manager 客户端同步和部署 Microsoft Surface 固件和驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="84d02-145">Starting in Endpoint Configuration Manager, you can synchronize and deploy Microsoft Surface firmware and driver updates by using the Configuration Manager client.</span></span> <span data-ttu-id="84d02-146">有关其他信息，请参阅 KB 4098906，[如何在 Configuration Manager 中管理 Surface driver 更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)。</span><span class="sxs-lookup"><span data-stu-id="84d02-146">For additional information, see KB 4098906, [How to manage Surface driver updates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).</span></span>

## <span data-ttu-id="84d02-147">支持的设备</span><span class="sxs-lookup"><span data-stu-id="84d02-147">Supported devices</span></span>

<span data-ttu-id="84d02-148">可下载的 .msi 文件可用于 Surface Pro 2 和更高版本的设备。</span><span class="sxs-lookup"><span data-stu-id="84d02-148">Downloadable .msi files are available for the Surface Pro 2 and later devices.</span></span> <span data-ttu-id="84d02-149">有关所有 Surface 设备（如 Surface Pro 7 和 Surface 笔记本电脑3）的 .msi 文件的信息将在此页发布时提供。</span><span class="sxs-lookup"><span data-stu-id="84d02-149">Information about .msi files for the newest Surface devices, such as Surface Pro 7 and Surface Laptop 3, will be available from this page upon release.</span></span>

## <span data-ttu-id="84d02-150">通过 DFCI 管理固件</span><span class="sxs-lookup"><span data-stu-id="84d02-150">Managing firmware with DFCI</span></span>

<span data-ttu-id="84d02-151">通过在 Intune 中内置设备固件配置接口（DFCI）配置文件（现在在[公共预览版](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)中可用），Surface UEFI 管理将新式管理堆栈扩展到 UEFI 硬件级别。</span><span class="sxs-lookup"><span data-stu-id="84d02-151">By having Device Firmware Configuration Interface (DFCI) profiles built into Intune (now available in [public preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="84d02-152">DFCI 支持零接触预配，消除了 BIOS 密码，提供了安全设置（包括启动选项和内置外围设备）的控制权，并为将来的高级安全方案奠定了基础。</span><span class="sxs-lookup"><span data-stu-id="84d02-152">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings (including startup options and built-in peripherals), and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="84d02-153">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="84d02-153">For more information, see the following articles:</span></span>

- [<span data-ttu-id="84d02-154">Surface UEFI 设置的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="84d02-154">Intune management of Surface UEFI settings</span></span>](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- <span data-ttu-id="84d02-155">[Ignite 2019：宣布从 Intune 进行 SURFACE UEFI 设置的远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。</span><span class="sxs-lookup"><span data-stu-id="84d02-155">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

## <span data-ttu-id="84d02-156">更新部署过程的最佳做法</span><span class="sxs-lookup"><span data-stu-id="84d02-156">Best practices for update deployment processes</span></span>

<span data-ttu-id="84d02-157">为了保持环境稳定，我们强烈建议你使用最新版本的 Windows 10 保持奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="84d02-157">To maintain a stable environment, we strongly recommend that you maintain parity with the most recent version of Windows 10.</span></span>  <span data-ttu-id="84d02-158">有关最佳做法建议，请参阅[Windows 10 更新的构建部署环](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)。</span><span class="sxs-lookup"><span data-stu-id="84d02-158">For best practice recommendations, see [Build deployment rings for Windows 10 updates](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates).</span></span>

## <span data-ttu-id="84d02-159">可下载的 Surface 更新程序包</span><span class="sxs-lookup"><span data-stu-id="84d02-159">Downloadable Surface update packages</span></span>

<span data-ttu-id="84d02-160">Windows 10 的特定版本具有单独的 .msi 文件，每个文件包含 Surface 设备的所有必需的累积驱动程序和固件更新。</span><span class="sxs-lookup"><span data-stu-id="84d02-160">Specific versions of Windows 10 have separate .msi files, each containing all the required cumulative driver and firmware updates for Surface devices.</span></span> <span data-ttu-id="84d02-161">更新程序包可能包含以下部分或所有组件：</span><span class="sxs-lookup"><span data-stu-id="84d02-161">Update packages may include some or all the following components:</span></span>

- <span data-ttu-id="84d02-162">Wi-fi 和 LTE</span><span class="sxs-lookup"><span data-stu-id="84d02-162">Wi-Fi and LTE</span></span>
- <span data-ttu-id="84d02-163">视频</span><span class="sxs-lookup"><span data-stu-id="84d02-163">Video</span></span>
- <span data-ttu-id="84d02-164">固态驱动器</span><span class="sxs-lookup"><span data-stu-id="84d02-164">Solid state drive</span></span>
- <span data-ttu-id="84d02-165">系统聚合器模块（SAM）</span><span class="sxs-lookup"><span data-stu-id="84d02-165">System aggregator module (SAM)</span></span>
- <span data-ttu-id="84d02-166">电池</span><span class="sxs-lookup"><span data-stu-id="84d02-166">Battery</span></span>
- <span data-ttu-id="84d02-167">键盘控制器</span><span class="sxs-lookup"><span data-stu-id="84d02-167">Keyboard controller</span></span>
- <span data-ttu-id="84d02-168">嵌入式控制器（EC）</span><span class="sxs-lookup"><span data-stu-id="84d02-168">Embedded controller (EC)</span></span>
- <span data-ttu-id="84d02-169">管理引擎（ME）</span><span class="sxs-lookup"><span data-stu-id="84d02-169">Management engine (ME)</span></span>
- <span data-ttu-id="84d02-170">统一可扩展固件接口（UEFI）</span><span class="sxs-lookup"><span data-stu-id="84d02-170">Unified extensible firmware interface (UEFI)</span></span>

### <span data-ttu-id="84d02-171">下载 .msi 文件</span><span class="sxs-lookup"><span data-stu-id="84d02-171">Downloading .msi files</span></span>

1. <span data-ttu-id="84d02-172">浏览以下载适用于 Microsoft 下载中心的[驱动程序和固件](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)。</span><span class="sxs-lookup"><span data-stu-id="84d02-172">Browse to [Download drivers and firmware for Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) on the Microsoft Download Center.</span></span>
2. <span data-ttu-id="84d02-173">选择与 Surface 模型和 Windows 版本相匹配的 .msi 文件名。</span><span class="sxs-lookup"><span data-stu-id="84d02-173">Select the .msi file name that matches the Surface model and version of Windows.</span></span> <span data-ttu-id="84d02-174">.Msi 文件名包含安装驱动程序和固件所需的最低支持的 Windows 内部版本号。</span><span class="sxs-lookup"><span data-stu-id="84d02-174">The .msi file name includes the minimum supported Windows build number that's required to install the drivers and firmware.</span></span> <span data-ttu-id="84d02-175">例如，请参考下图。</span><span class="sxs-lookup"><span data-stu-id="84d02-175">For example, refer to the following figure.</span></span> <span data-ttu-id="84d02-176">若要更新具有 Windows 10 版本18362的 Surface Book 2，请选择 " **SurfaceBook2_Win10_18362_19.101.13994.msi"。**</span><span class="sxs-lookup"><span data-stu-id="84d02-176">To update a Surface Book 2 that has build 18362 of Windows 10, choose **SurfaceBook2_Win10_18362_19.101.13994.msi.**</span></span> <span data-ttu-id="84d02-177">对于具有 Windows 10 版本16299的 Surface Book 2，请选择 " **SurfaceBook2_Win10_16299_1803509_3.msi**"。</span><span class="sxs-lookup"><span data-stu-id="84d02-177">For a Surface Book 2 that has build 16299 of Windows 10, choose **SurfaceBook2_Win10_16299_1803509_3.msi**.</span></span>

    ![图 1.](images/fig1-downloads-msi.png)

    *<span data-ttu-id="84d02-180">图 1.</span><span class="sxs-lookup"><span data-stu-id="84d02-180">Figure 1.</span></span> <span data-ttu-id="84d02-181">下载图面更新</span><span class="sxs-lookup"><span data-stu-id="84d02-181">Downloading Surface updates</span></span>*

### <span data-ttu-id="84d02-182">Surface 命名约定</span><span class="sxs-lookup"><span data-stu-id="84d02-182">Surface .msi naming convention</span></span>

<span data-ttu-id="84d02-183">自2019年8月起，.msi 文件使用以下命名约定：</span><span class="sxs-lookup"><span data-stu-id="84d02-183">Since August 2019, .msi files are using the following naming convention:</span></span>

- <span data-ttu-id="84d02-184">*产品*_*windows 版本*_*windows 内部*_*Version number*_ 版本号版本版本号 *（通常为零）的版本号修订版*。</span><span class="sxs-lookup"><span data-stu-id="84d02-184">*Product*_*Windows release*_*Windows build number*_*Version number*_*Revision of version number (typically zero)*.</span></span>

**<span data-ttu-id="84d02-185">示例</span><span class="sxs-lookup"><span data-stu-id="84d02-185">Example</span></span>**

- <span data-ttu-id="84d02-186">SurfacePro6_Win10_18362_19.073.44195_0.msi</span><span class="sxs-lookup"><span data-stu-id="84d02-186">SurfacePro6_Win10_18362_19.073.44195_0.msi</span></span>

<span data-ttu-id="84d02-187">此文件名提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="84d02-187">This file name provides the following information:</span></span>

- <span data-ttu-id="84d02-188">**产品：** SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="84d02-188">**Product:** SurfacePro6</span></span>
- <span data-ttu-id="84d02-189">**Windows 版本：** Win10</span><span class="sxs-lookup"><span data-stu-id="84d02-189">**Windows release:** Win10</span></span>
- <span data-ttu-id="84d02-190">**内部版本：** 18362</span><span class="sxs-lookup"><span data-stu-id="84d02-190">**Build:** 18362</span></span>
- <span data-ttu-id="84d02-191">**版本：** 19.073.44195-这将显示创建文件的日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="84d02-191">**Version:** 19.073.44195 – This shows the date and time that the file was created, as follows:</span></span>
  - <span data-ttu-id="84d02-192">**年份：** 19 （2019）</span><span class="sxs-lookup"><span data-stu-id="84d02-192">**Year:** 19 (2019)</span></span>
  - <span data-ttu-id="84d02-193">**月份和星期：** 073 （七月的第三周）</span><span class="sxs-lookup"><span data-stu-id="84d02-193">**Month and week:** 073 (third week of July)</span></span>
  - <span data-ttu-id="84d02-194">**月份的分钟数：** 44195</span><span class="sxs-lookup"><span data-stu-id="84d02-194">**Minute of the month:** 44195</span></span>
- <span data-ttu-id="84d02-195">**版本：0的版本：** 0 （此版本的首次发布）</span><span class="sxs-lookup"><span data-stu-id="84d02-195">**Revision of version:** 0 (first release of this version)</span></span>

### <span data-ttu-id="84d02-196">旧式图面。 msi 命名约定</span><span class="sxs-lookup"><span data-stu-id="84d02-196">Legacy Surface .msi naming convention</span></span>

<span data-ttu-id="84d02-197">旧版 .msi 文件（在2019年8月之前生成的文件）使用相同的总命名公式，但使用不同的方法派生版本号。</span><span class="sxs-lookup"><span data-stu-id="84d02-197">Legacy .msi files (files that were built before August 2019) followed the same overall naming formula but used a different method to derive the version number.</span></span>

**<span data-ttu-id="84d02-198">示例</span><span class="sxs-lookup"><span data-stu-id="84d02-198">Example</span></span>**

- <span data-ttu-id="84d02-199">SurfacePro6_Win10_16299_1900307_0.msi</span><span class="sxs-lookup"><span data-stu-id="84d02-199">SurfacePro6_Win10_16299_1900307_0.msi</span></span>

<span data-ttu-id="84d02-200">此文件名提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="84d02-200">This file name provides the following information:</span></span>

- <span data-ttu-id="84d02-201">**产品：** SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="84d02-201">**Product:** SurfacePro6</span></span>
- <span data-ttu-id="84d02-202">**Windows 版本：** Win10</span><span class="sxs-lookup"><span data-stu-id="84d02-202">**Windows release:** Win10</span></span>
- <span data-ttu-id="84d02-203">**内部版本：** 16299</span><span class="sxs-lookup"><span data-stu-id="84d02-203">**Build:** 16299</span></span>
- <span data-ttu-id="84d02-204">**版本：** 1900307-这将显示文件的创建日期及其在发布序列中的位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="84d02-204">**Version:** 1900307 – This shows the date that the file was created and its position in the release sequence, as follows:</span></span>
  - <span data-ttu-id="84d02-205">**年份：** 19 （2019）</span><span class="sxs-lookup"><span data-stu-id="84d02-205">**Year:** 19 (2019)</span></span>
  - <span data-ttu-id="84d02-206">**发布数：** 003 （年份的第三个版本）</span><span class="sxs-lookup"><span data-stu-id="84d02-206">**Number of release:** 003 (third release of the year)</span></span>
  - <span data-ttu-id="84d02-207">**产品版本号：** 07 （surface pro 6 正式是 surface pro 的第7个版本）</span><span class="sxs-lookup"><span data-stu-id="84d02-207">**Product version number:** 07 (Surface Pro 6 is officially the seventh version of Surface Pro)</span></span>
- <span data-ttu-id="84d02-208">**版本：0的版本：** 0 （此版本的首次发布）</span><span class="sxs-lookup"><span data-stu-id="84d02-208">**Revision of version:** 0 (first release of this version)</span></span>

## <span data-ttu-id="84d02-209">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="84d02-209">Learn more</span></span>

- [<span data-ttu-id="84d02-210">下载用于 Surface 的驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="84d02-210">Download drivers and firmware for Surface</span></span>](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [<span data-ttu-id="84d02-211">如何在 Configuration Manager 中管理 Surface driver 更新</span><span class="sxs-lookup"><span data-stu-id="84d02-211">How to manage Surface driver updates in Configuration Manager</span></span>](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [<span data-ttu-id="84d02-212">通过 Configuration Manager 部署应用程序</span><span class="sxs-lookup"><span data-stu-id="84d02-212">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [<span data-ttu-id="84d02-213">终结点配置管理器文档</span><span class="sxs-lookup"><span data-stu-id="84d02-213">Endpoint Configuration Manager documentation</span></span>](https://docs.microsoft.com/configmgr/)
- [<span data-ttu-id="84d02-214">Microsoft 部署工具包文档</span><span class="sxs-lookup"><span data-stu-id="84d02-214">Microsoft Deployment Toolkit documentation</span></span>](https://docs.microsoft.com/configmgr/mdt/)
- [<span data-ttu-id="84d02-215">使用 Microsoft 部署工具包部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="84d02-215">Deploy Windows 10 with the Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [<span data-ttu-id="84d02-216">通过 Microsoft 部署工具包将 Windows 10 部署到 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="84d02-216">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [<span data-ttu-id="84d02-217">Surface UEFI 设置的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="84d02-217">Intune management of Surface UEFI settings</span></span>](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- <span data-ttu-id="84d02-218">[Ignite 2019：宣布从 Intune 进行 SURFACE UEFI 设置的远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。</span><span class="sxs-lookup"><span data-stu-id="84d02-218">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>
- [<span data-ttu-id="84d02-219">生成 Windows 10 更新的部署圈</span><span class="sxs-lookup"><span data-stu-id="84d02-219">Build deployment rings for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)

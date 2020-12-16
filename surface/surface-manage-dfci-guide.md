---
title: Surface UEFI 设置的 Intune 管理
description: 本文介绍了如何在 Microsoft Intune 中配置 DFCI 环境并管理目标 Surface 设备的固件设置。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
ms.openlocfilehash: e984741a8367935eab18351815c5f00d9f8a72b7
ms.sourcegitcommit: efc38524f81238e0c36371f462eb57123e46d09b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "11228543"
---
# <span data-ttu-id="19c5e-103">Surface UEFI 设置的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="19c5e-103">Intune management of Surface UEFI settings</span></span>

## <span data-ttu-id="19c5e-104">简介</span><span class="sxs-lookup"><span data-stu-id="19c5e-104">Introduction</span></span>

<span data-ttu-id="19c5e-105">从云管理设备的能力极大地简化了整个生命周期中的 IT 部署和预配。</span><span class="sxs-lookup"><span data-stu-id="19c5e-105">The ability to manage devices from the cloud has dramatically simplified IT deployment and provisioning across the lifecycle.</span></span> <span data-ttu-id="19c5e-106">借助内置于 [Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows) (DFCI) 配置文件的设备固件配置接口，Surface UEFI 管理将新式管理堆栈向下扩展到 UEFI 硬件级别。</span><span class="sxs-lookup"><span data-stu-id="19c5e-106">With Device Firmware Configuration Interface (DFCI) profiles built into [Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="19c5e-107">DFCI 支持零接触预配、消除 BIOS 密码、控制安全设置（包括启动选项和内置外设）并在将来为高级安全方案打下基础。</span><span class="sxs-lookup"><span data-stu-id="19c5e-107">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="19c5e-108">有关常见问题的解答，请参阅 [Ignite 2019：宣布从 Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)远程管理 Surface UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="19c5e-108">For answers to frequently asked questions, see [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

### <span data-ttu-id="19c5e-109">Background</span><span class="sxs-lookup"><span data-stu-id="19c5e-109">Background</span></span>

<span data-ttu-id="19c5e-110">与运行 Windows 10 的任何计算机一样，Surface 设备依赖于 SoC 中存储的代码，该代码使 CPU 能够与硬盘驱动器、显示设备、USB 端口和其他设备交互。</span><span class="sxs-lookup"><span data-stu-id="19c5e-110">Like any computer running Windows 10, Surface devices rely on code stored in the SoC that enables the CPU to interface with hard drives, display devices, USB ports, and other devices.</span></span> <span data-ttu-id="19c5e-111">此只读内存中存储的程序 (ROM) 称为固件 (而存储在动态媒体中的程序称为软件) 。</span><span class="sxs-lookup"><span data-stu-id="19c5e-111">The programs stored in this read-only memory (ROM) are known as firmware (while programs stored in dynamic media are known as software).</span></span>

<span data-ttu-id="19c5e-112">与当今市场中提供的其他 Windows 10 设备不同，Surface 为 IT 管理员提供了通过一组丰富的 UEFI 配置设置配置和管理固件的能力。</span><span class="sxs-lookup"><span data-stu-id="19c5e-112">In contrast to other Windows 10 devices available in the market today, Surface provides IT admins with the ability to configure and manage firmware through a rich set of UEFI configuration settings.</span></span> <span data-ttu-id="19c5e-113">这将在基于软件的策略管理的基础上提供硬件控制层，通过移动设备管理、MDM (策略、Configuration Manager 或组) 实现。</span><span class="sxs-lookup"><span data-stu-id="19c5e-113">This provides a layer of hardware control on top of software-based policy management as implemented via mobile device management (MDM) policies, Configuration Manager or Group Policy.</span></span> <span data-ttu-id="19c5e-114">例如，在具有敏感信息的高度安全区域部署设备的组织可以通过删除硬件级别的功能来阻止使用相机。</span><span class="sxs-lookup"><span data-stu-id="19c5e-114">For example, organizations deploying devices in highly secure areas with sensitive information can prevent camera use by removing functionality at the hardware level.</span></span> <span data-ttu-id="19c5e-115">从设备的角度来看，通过固件设置关闭相机等效于以物理方式删除相机。</span><span class="sxs-lookup"><span data-stu-id="19c5e-115">From a device standpoint, turning the camera off via a firmware setting is equivalent to physically removing the camera.</span></span> <span data-ttu-id="19c5e-116">将固件级别管理的新增安全性与仅依赖操作系统软件设置进行比较。</span><span class="sxs-lookup"><span data-stu-id="19c5e-116">Compare the added security of managing at the firmware level to relying only on operating system software settings.</span></span> <span data-ttu-id="19c5e-117">例如，如果在域环境中通过策略设置禁用 Windows 音频服务，本地管理员仍可重新启用该服务。</span><span class="sxs-lookup"><span data-stu-id="19c5e-117">For example, if you disable the Windows audio service via a policy setting in a domain environment, a local admin could still re-enable the service.</span></span>

### <span data-ttu-id="19c5e-118">DFCI 与 SEMM</span><span class="sxs-lookup"><span data-stu-id="19c5e-118">DFCI versus SEMM</span></span>

<span data-ttu-id="19c5e-119">以前，管理需要将设备注册到 Surface Enterprise Management Mode (SEMM) 具有正在进行的手动 IT 密集型任务的开销。</span><span class="sxs-lookup"><span data-stu-id="19c5e-119">Previously, managing firmware required enrolling devices into Surface Enterprise Management Mode (SEMM) with the overhead of ongoing manual IT-intensive tasks.</span></span> <span data-ttu-id="19c5e-120">例如，SEMM 要求 IT 人员在物理上访问每台电脑，以在证书管理过程中输入两位数的引脚。</span><span class="sxs-lookup"><span data-stu-id="19c5e-120">As an example, SEMM requires IT staff to physically access each PC to enter a two-digit pin as part of the certificate management process.</span></span> <span data-ttu-id="19c5e-121">虽然 SEMM 对于严格位于本地环境中的组织仍然是一个很好的解决方案，但它的复杂性和 IT 密集型要求使使用成本高。</span><span class="sxs-lookup"><span data-stu-id="19c5e-121">Although SEMM remains a good solution for organizations in a strictly on-premises environment, its complexity and IT-intensive requirements make it costly to use.</span></span>

 <span data-ttu-id="19c5e-122">借助 Microsoft Intune 中的集成 UEFI 固件管理功能，锁定硬件的功能已简化，并且更易于与预配、安全性和简化更新的新功能一同使用，现在统一为[Microsoft Endpoint Manager。](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)</span><span class="sxs-lookup"><span data-stu-id="19c5e-122">With integrated UEFI firmware management capabilities in Microsoft Intune, the ability to lock down hardware is simplified and easier to use with new features for provisioning, security, and streamlined updating all in a single console, now unified as [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span> <span data-ttu-id="19c5e-123">下图显示了直接在设备左侧 (查看的 UEFI 设置) 在终结点管理器控制台中 (右) 。</span><span class="sxs-lookup"><span data-stu-id="19c5e-123">The following figure shows UEFI settings viewed directly on the device (left) and viewed in the Endpoint Manager console (right).</span></span>

![设备左侧和 (控制台) 的 UEFI 设置 (右) ](images/uefidfci.png)

<span data-ttu-id="19c5e-125">重要的是，DFCI 支持零接触管理，无需 IT 管理员进行手动交互。</span><span class="sxs-lookup"><span data-stu-id="19c5e-125">Crucially, DFCI enables zero touch management, eliminating the need for manual interaction by IT admins.</span></span> <span data-ttu-id="19c5e-126">DFCI 使用 Intune 中的设备配置文件功能通过 Windows Autopilot 部署。</span><span class="sxs-lookup"><span data-stu-id="19c5e-126">DFCI is deployed via Windows Autopilot using the device profiles capability in Intune.</span></span> <span data-ttu-id="19c5e-127">设备配置文件允许你添加和配置设置，这些设置随后可部署到在组织管理中注册的设备。</span><span class="sxs-lookup"><span data-stu-id="19c5e-127">A device profile allows you to add and configure settings which can then be deployed to devices enrolled in management within your organization.</span></span> <span data-ttu-id="19c5e-128">设备收到设备配置文件后，将自动应用功能和设置。</span><span class="sxs-lookup"><span data-stu-id="19c5e-128">Once the device receives the device profile, the features and settings are applied automatically.</span></span> <span data-ttu-id="19c5e-129">常见设备配置文件的示例包括电子邮件、设备限制、VPN、WLAN 和管理模板。</span><span class="sxs-lookup"><span data-stu-id="19c5e-129">Examples of common device profiles include Email, Device restrictions, VPN, Wi-Fi, and Administrative templates.</span></span> <span data-ttu-id="19c5e-130">DFCI 只是一个额外的设备配置文件，使你能够管理云中的 UEFI 配置设置，而无需维护本地基础结构。</span><span class="sxs-lookup"><span data-stu-id="19c5e-130">DFCI is simply an additional device profile that enables you to manage UEFI configuration settings from the cloud without having to maintain on-premises infrastructure.</span></span>  

## <span data-ttu-id="19c5e-131">支持的设备</span><span class="sxs-lookup"><span data-stu-id="19c5e-131">Supported devices</span></span>

<span data-ttu-id="19c5e-132">以下设备支持 DFCI：</span><span class="sxs-lookup"><span data-stu-id="19c5e-132">DFCI is supported in the following devices:</span></span>

- <span data-ttu-id="19c5e-133">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="19c5e-133">Surface Pro 7</span></span>
- <span data-ttu-id="19c5e-134">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="19c5e-134">Surface Pro X</span></span>
- <span data-ttu-id="19c5e-135">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="19c5e-135">Surface Laptop 3</span></span>
- <span data-ttu-id="19c5e-136">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="19c5e-136">Surface Book 3</span></span>
- <span data-ttu-id="19c5e-137">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="19c5e-137">Surface Laptop Go</span></span>

> [!NOTE]
> <span data-ttu-id="19c5e-138">Surface Pro X 不支持内置相机、音频和 WI-Fi/Bluetooth。</span><span class="sxs-lookup"><span data-stu-id="19c5e-138">Surface Pro X does not support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth.</span></span>

## <span data-ttu-id="19c5e-139">必备条件</span><span class="sxs-lookup"><span data-stu-id="19c5e-139">Prerequisites</span></span>

- <span data-ttu-id="19c5e-140">设备必须由 Microsoft 云解决方案提供商或 OEM ([云](https://partner.microsoft.com/membership/cloud-solution-provider) 解决方案提供商) Windows Autopilot 注册。</span><span class="sxs-lookup"><span data-stu-id="19c5e-140">Devices must be registered with Windows Autopilot by a [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider) or OEM distributor.</span></span>

- <span data-ttu-id="19c5e-141">为 Surface 配置 DFCI 之前，你应该熟悉  [Microsoft Intune](https://docs.microsoft.com/intune/) 和 Azure [Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="19c5e-141">Before configuring DFCI for Surface, you should be familiar with Autopilot configuration requirements in  [Microsoft Intune](https://docs.microsoft.com/intune/) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).</span></span>

## <span data-ttu-id="19c5e-142">开始之前</span><span class="sxs-lookup"><span data-stu-id="19c5e-142">Before you begin</span></span>

<span data-ttu-id="19c5e-143">将目标 Surface 设备添加到 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="19c5e-143">Add your target Surface devices to an Azure AD security group.</span></span> <span data-ttu-id="19c5e-144">有关创建和管理安全组的信息，请参阅 [Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="19c5e-144">For more information about creating and managing security groups, refer to [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).</span></span>

## <span data-ttu-id="19c5e-145">为 Surface 设备配置 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="19c5e-145">Configure DFCI management for Surface devices</span></span>

<span data-ttu-id="19c5e-146">DFCI 环境需要设置包含设置的 DFCI 配置文件和 Autopilot 配置文件，以将设置应用于注册的设备。</span><span class="sxs-lookup"><span data-stu-id="19c5e-146">A DFCI environment requires setting up a DFCI profile that contains  the settings and an Autopilot profile to apply the settings to registered devices.</span></span> <span data-ttu-id="19c5e-147">还建议注册状态配置文件，以确保在用户首次启动设备时在 OOBE 安装期间将设置向下推送。</span><span class="sxs-lookup"><span data-stu-id="19c5e-147">An enrollment status profile is also recommended to ensure settings are pushed down during OOBE setup when users first start the device.</span></span> <span data-ttu-id="19c5e-148">本指南介绍如何配置 DFCI 环境和管理目标 Surface 设备的 UEFI 配置设置。</span><span class="sxs-lookup"><span data-stu-id="19c5e-148">This guide explains how to configure the DFCI environment and manage UEFI configuration settings for targeted Surface devices.</span></span>

## <span data-ttu-id="19c5e-149">创建 DFCI 配置文件</span><span class="sxs-lookup"><span data-stu-id="19c5e-149">Create DFCI profile</span></span>

<span data-ttu-id="19c5e-150">在配置 DFCI 策略设置之前，首先创建一个 DFCI 配置文件并将其分配给包含目标设备的 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="19c5e-150">Before configuring DFCI policy settings, first create a DFCI profile and assign it to the Azure AD security group that contains your target devices.</span></span>

1. <span data-ttu-id="19c5e-151">在租户中登录devicemanagement.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="19c5e-151">Sign into your tenant at  devicemanagement.microsoft.com.</span></span>
2. <span data-ttu-id="19c5e-152">在 Microsoft Endpoint Manager 管理中心中，> **配置文件>设备** 并输入名称;例如 **，DFCI 配置策略。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-152">In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile** and enter a name; for example, **DFCI Configuration Policy.**</span></span>
3. <span data-ttu-id="19c5e-153">为 **平台类型选择 Windows 10** 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="19c5e-153">Select **Windows 10 and later** for platform type.</span></span>
4. <span data-ttu-id="19c5e-154">在"配置文件类型"下拉列表中，选择 **"设备固件配置接口** "以打开包含所有可用策略设置的 DFCI 边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="19c5e-154">In the Profile type drop down list, select **Device Firmware Configuration Interface** to open the DFCI blade containing all available policy settings.</span></span> <span data-ttu-id="19c5e-155">有关 DFCI 设置的信息，请参阅此页上的表 1 或 [Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="19c5e-155">For information on DFCI settings, refer to Table 1 on this page or the [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span> <span data-ttu-id="19c5e-156">可以在初始设置过程中或稍后通过编辑 DFCI 配置文件来配置 DFCI 设置。</span><span class="sxs-lookup"><span data-stu-id="19c5e-156">You can configure DFCI settings during the initial setup process or later by editing the DFCI profile.</span></span>

    ![创建 DFCI 配置文件](images/df1.png)

5. <span data-ttu-id="19c5e-158">单击 **"** 确定"，然后选择"**创建"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-158">Click **OK** and then select **Create**.</span></span>
6. <span data-ttu-id="19c5e-159">选择**分配\*\*\*\*，在**"选择要包括的组"下选择包含目标设备的 Azure AD 安全组，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="19c5e-159">Select **Assignments** and under **Select groups to include** select the Azure AD security group that contains your target devices, as shown in the following figure.</span></span> <span data-ttu-id="19c5e-160">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="19c5e-160">Click **Save**.</span></span>

    ![分配安全组](images/df2a.png)

## <span data-ttu-id="19c5e-162">创建 Autopilot 配置文件</span><span class="sxs-lookup"><span data-stu-id="19c5e-162">Create Autopilot profile</span></span>

1. <span data-ttu-id="19c5e-163">在终结点管理器devicemanagement.microsoft.com，> **Windows** 注册的设备，然后向下滚动到 **部署配置文件**。</span><span class="sxs-lookup"><span data-stu-id="19c5e-163">In Endpoint Manager at  devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles**.</span></span>
2. <span data-ttu-id="19c5e-164">选择 **"创建配置文件**"并输入名称;例如 **，My Autopilot 配置文件**，然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-164">Select **Create profile** and enter a name; for example, **My Autopilot profile**, and select **Next**.</span></span>
3. <span data-ttu-id="19c5e-165">选择以下设置：</span><span class="sxs-lookup"><span data-stu-id="19c5e-165">Select the following settings:</span></span>

    - <span data-ttu-id="19c5e-166">部署模式： **用户驱动**。</span><span class="sxs-lookup"><span data-stu-id="19c5e-166">Deployment mode: **User-Driven**.</span></span>
    - <span data-ttu-id="19c5e-167">加入类型：已加入 Azure **AD。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-167">Join type: Azure **AD joined**.</span></span>

4. <span data-ttu-id="19c5e-168">保留其余默认设置不变，然后选择" **下**一步"，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="19c5e-168">Leave the remaining default settings unchanged and select **Next**, as shown in the following figure.</span></span>

    ![创建 Autopilot 配置文件](images/df3b.png)

5. <span data-ttu-id="19c5e-170">在"分配"页上， **选择"选择要包含** 的组"，然后单击 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="19c5e-170">On the Assignments page, choose **Select groups to include** and click your Azure AD security group.</span></span> <span data-ttu-id="19c5e-171">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="19c5e-171">Select **Next**.</span></span>
6. <span data-ttu-id="19c5e-172">接受摘要，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-172">Accept the summary and then select **Create**.</span></span> <span data-ttu-id="19c5e-173">Autopilot 配置文件现已创建并分配给组。</span><span class="sxs-lookup"><span data-stu-id="19c5e-173">The Autopilot profile is now created and assigned to the group.</span></span>

## <span data-ttu-id="19c5e-174">配置注册状态页</span><span class="sxs-lookup"><span data-stu-id="19c5e-174">Configure Enrollment Status Page</span></span>

<span data-ttu-id="19c5e-175">若要确保设备在用户登录之前在 OOBE 期间应用 DFCI 配置，需要配置注册状态。</span><span class="sxs-lookup"><span data-stu-id="19c5e-175">To ensure that devices apply the DFCI configuration during OOBE before users sign in, you need to configure enrollment status.</span></span>

<span data-ttu-id="19c5e-176">有关详细信息，请参阅" [设置注册状态"页](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="19c5e-176">For more information, refer to [Set up an enrollment status page](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).</span></span>


## <span data-ttu-id="19c5e-177">在 Surface 设备上配置 DFCI 设置</span><span class="sxs-lookup"><span data-stu-id="19c5e-177">Configure DFCI settings on Surface devices</span></span>

<span data-ttu-id="19c5e-178">DFCI 包括一组简化的 UEFI 配置策略，这些策略通过锁定硬件级别的设备来提供额外的安全级别。</span><span class="sxs-lookup"><span data-stu-id="19c5e-178">DFCI includes a streamlined set of UEFI configuration policies that provide an extra level of security by locking down devices at the hardware level.</span></span> <span data-ttu-id="19c5e-179">DFCI 设计为与软件级别的移动设备管理设置结合使用。</span><span class="sxs-lookup"><span data-stu-id="19c5e-179">DFCI is designed to be used in conjunction with mobile device management settings at the software level.</span></span> <span data-ttu-id="19c5e-180">请注意，DFCI 设置仅影响内置于 Surface 设备的硬件组件，不会扩展到连接的外围设备（如 USB 摄像头）。</span><span class="sxs-lookup"><span data-stu-id="19c5e-180">Note that DFCI settings only affect hardware components built into Surface devices and do not extend to attached peripherals such as USB webcams.</span></span> <span data-ttu-id="19c5e-181"> (但是，可以使用 Intune 中的设备限制策略在软件级别关闭对已连接的外围设备) 。</span><span class="sxs-lookup"><span data-stu-id="19c5e-181">(However, you can use Device restriction policies in Intune to turn off access to attached peripherals at the software level).</span></span>

<span data-ttu-id="19c5e-182">通过从终结点管理器编辑 DFCI 配置文件来配置 DFCI 策略设置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="19c5e-182">You configure DFCI policy settings by editing the DFCI profile from Endpoint Manager, as shown in the figure below.</span></span> 

- <span data-ttu-id="19c5e-183">在终结点管理器devicemanagement.microsoft.com，> **Windows > 配置文件>"DFCI 配置文件名称">属性>设置**。</span><span class="sxs-lookup"><span data-stu-id="19c5e-183">In Endpoint Manager at  devicemanagement.microsoft.com, select **Devices > Windows > Configuration Profiles > “DFCI profile name” > Properties > Settings**.</span></span>

    ![配置 DFCI 设置](images/dfciconfig.png)

### <span data-ttu-id="19c5e-185">阻止用户访问 UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="19c5e-185">Block user access to UEFI settings</span></span>

<span data-ttu-id="19c5e-186">对于许多客户来说，阻止用户更改 UEFI 设置的能力至关重要，也是使用 DFCI 的主要原因。</span><span class="sxs-lookup"><span data-stu-id="19c5e-186">For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI.</span></span> <span data-ttu-id="19c5e-187">如表 1 所示，这是通过设置"允许本地用户更改 **UEFI 设置"进行管理的**。</span><span class="sxs-lookup"><span data-stu-id="19c5e-187">As listed in Table 1, this is managed via the setting **Allow local user to change UEFI settings**.</span></span> <span data-ttu-id="19c5e-188">如果未编辑或配置此设置，本地用户将能够更改任何未由 Intune 管理的 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="19c5e-188">If you do not edit or configure this setting, local users will be able to change any UEFI setting not managed by Intune.</span></span> <span data-ttu-id="19c5e-189">因此，强烈建议禁用"允许本地用户 **更改 UEFI 设置"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-189">Therefore, it’s highly recommended to disable **Allow local user to change UEFI settings.**</span></span>
<span data-ttu-id="19c5e-190">其余 DFCI 设置使你可以关闭原本可供用户使用的功能。</span><span class="sxs-lookup"><span data-stu-id="19c5e-190">The rest of the DFCI settings enable you to turn off functionality that would otherwise be available to users.</span></span> <span data-ttu-id="19c5e-191">例如，如果需要保护高度安全的区域中的敏感信息，可以禁用相机，如果不希望用户从 USB 驱动器启动，也可以禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="19c5e-191">For example, if you need to protect sensitive information in highly secure areas, you can disable the camera, and if you don’t want users booting from USB drives, you can disable that also.</span></span>

### <span data-ttu-id="19c5e-192">表 1. </span><span class="sxs-lookup"><span data-stu-id="19c5e-192">Table 1.</span></span> <span data-ttu-id="19c5e-193">DFCI 方案</span><span class="sxs-lookup"><span data-stu-id="19c5e-193">DFCI scenarios</span></span>

| <span data-ttu-id="19c5e-194">设备管理目标</span><span class="sxs-lookup"><span data-stu-id="19c5e-194">Device management goal</span></span>                        | <span data-ttu-id="19c5e-195">配置步骤</span><span class="sxs-lookup"><span data-stu-id="19c5e-195">Configuration steps</span></span>                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="19c5e-196">阻止本地用户更改 UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="19c5e-196">Block local users from changing UEFI settings</span></span> | <span data-ttu-id="19c5e-197">在 **"安全功能>允许本地用户更改 UEFI 设置"** 下，选择"**无"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-197">Under **Security Features > Allow local user to change UEFI settings**, select **None**.</span></span>              |
| <span data-ttu-id="19c5e-198">禁用相机</span><span class="sxs-lookup"><span data-stu-id="19c5e-198">Disable cameras</span></span>                               | <span data-ttu-id="19c5e-199">在 **"内置硬件>相机"下**，选择 **"已禁用"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-199">Under **Built in Hardware > Cameras**, select **Disabled**.</span></span>                                       |
| <span data-ttu-id="19c5e-200">禁用麦克风和扬声器</span><span class="sxs-lookup"><span data-stu-id="19c5e-200">Disable Microphones and speakers</span></span>              | <span data-ttu-id="19c5e-201">在 **"内置硬件>麦克风和扬声器"下**，选择 **"已禁用"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-201">Under **Built in Hardware > Microphones and speakers**, select **Disabled**.</span></span>                      |
| <span data-ttu-id="19c5e-202">禁用无线 (Bluetooth、WI-Fi) </span><span class="sxs-lookup"><span data-stu-id="19c5e-202">Disable radios (Bluetooth, Wi-Fi)</span></span>             | <span data-ttu-id="19c5e-203">Under \*\*Built in Hardware > Radios (Bluetooth， Wi-Fi， etc...) ， \*\*select **Disabled**.</span><span class="sxs-lookup"><span data-stu-id="19c5e-203">Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc…)**, select **Disabled**.</span></span>                   |
| <span data-ttu-id="19c5e-204">禁用从外部媒体启动 (USB、SD) </span><span class="sxs-lookup"><span data-stu-id="19c5e-204">Disable Boot from external media (USB, SD)</span></span>    | <span data-ttu-id="19c5e-205">Under \*\*Built in Hardware > Boot Options > Boot from external media (USB， SD) ， \*\*select **Disabled.**</span><span class="sxs-lookup"><span data-stu-id="19c5e-205">Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**.</span></span> |

> [!CAUTION]
> <span data-ttu-id="19c5e-206">\*\*"禁用 (Bluetooth WI-Fi) \*\*设置应仅在具有有线以太网连接的设备上使用。</span><span class="sxs-lookup"><span data-stu-id="19c5e-206">The **Disable radios (Bluetooth, Wi-Fi)** setting should only be used on devices that have a wired Ethernet connection.</span></span>
 
> [!NOTE]
>  <span data-ttu-id="19c5e-207">Intune 中的 DFCI 包括两个当前不适用于 Surface 设备的设置： (1) CPU 和 IO 虚拟化以及 (2) 从网络适配器禁用启动。</span><span class="sxs-lookup"><span data-stu-id="19c5e-207">DFCI in Intune includes two settings that do not currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.</span></span>
 
<span data-ttu-id="19c5e-208">Intune 提供范围标记以委派管理权限和适用性规则来管理设备类型。</span><span class="sxs-lookup"><span data-stu-id="19c5e-208">Intune provides Scope tags to delegate administrative rights and Applicability Rules to manage device types.</span></span> <span data-ttu-id="19c5e-209">有关策略管理支持和有关所有 DFCI 设置的完整详细信息的详细信息，请参阅 [Microsoft Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="19c5e-209">For more information about policy management support and full details on all DFCI settings, refer to [Microsoft Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span>

## <span data-ttu-id="19c5e-210">在 Autopilot 中注册设备</span><span class="sxs-lookup"><span data-stu-id="19c5e-210">Register devices in Autopilot</span></span>

<span data-ttu-id="19c5e-211">如上所述，DFCI 只能应用于由经销商或分销商在 Windows Autopilot 中注册的设备，并且目前仅在 Surface Pro 7、Surface Pro X 和 Surface Laptop 3 上受支持。</span><span class="sxs-lookup"><span data-stu-id="19c5e-211">As stated above, DFCI can only be applied on devices registered in Windows Autopilot by your reseller or distributor and is only supported, at this time, on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="19c5e-212">出于安全考虑，无法将设备"自行预配"到 Autopilot 中。</span><span class="sxs-lookup"><span data-stu-id="19c5e-212">For security reasons, it’s not possible to “self-provision” your devices into Autopilot.</span></span>

## <span data-ttu-id="19c5e-213">手动同步 Autopilot 设备</span><span class="sxs-lookup"><span data-stu-id="19c5e-213">Manually Sync Autopilot devices</span></span>

<span data-ttu-id="19c5e-214">尽管通常几乎会立即应用 Intune 策略设置，但设置在目标设备上生效之前可能有 10 分钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="19c5e-214">Although Intune policy settings typically get applied almost immediately, there may be a delay of 10 minutes before the settings take effect on targeted devices.</span></span> <span data-ttu-id="19c5e-215">在极少数情况下，最多延迟 8 小时。</span><span class="sxs-lookup"><span data-stu-id="19c5e-215">In rare circumstances, delays of up to 8 hours are possible.</span></span> <span data-ttu-id="19c5e-216">若要确保设置尽快应用， (如在测试方案中) ，可以手动同步目标设备。</span><span class="sxs-lookup"><span data-stu-id="19c5e-216">To ensure settings apply as soon as possible, (such as in test scenarios), you can manually sync the target devices.</span></span>

- <span data-ttu-id="19c5e-217">在终结点管理器devicemanagement.microsoft.com，转到 Windows **Autopilot** > Windows 注册>设备注册>，然后选择"**同步"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-217">In Endpoint Manager at  devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync**.</span></span>

 <span data-ttu-id="19c5e-218">有关详细信息，请参阅手动同步 [Windows 设备](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。</span><span class="sxs-lookup"><span data-stu-id="19c5e-218">For more information, refer to [Sync your Windows device manually](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).</span></span>

> [!NOTE]
> <span data-ttu-id="19c5e-219">直接在 UEFI 中调整设置时，需要确保设备完全重启到标准 Windows 登录。</span><span class="sxs-lookup"><span data-stu-id="19c5e-219">When adjusting settings directly in UEFI, you need to ensure the device fully restarts to the standard Windows login.</span></span>

## <span data-ttu-id="19c5e-220">验证 DFCI 托管的设备的 UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="19c5e-220">Verifying UEFI settings on DFCI-managed devices</span></span>

<span data-ttu-id="19c5e-221">在测试环境中，你可以验证 Surface UEFI 接口中的设置。</span><span class="sxs-lookup"><span data-stu-id="19c5e-221">In a test environment, you can verify settings in the Surface UEFI interface.</span></span>

1. <span data-ttu-id="19c5e-222">打开 Surface UEFI，这涉及同时按音量 **+** 和 **电源** 按钮。</span><span class="sxs-lookup"><span data-stu-id="19c5e-222">Open Surface UEFI, which involves pressing the **Volume +** and **Power** buttons at the same time.</span></span>
2. <span data-ttu-id="19c5e-223">选择 **设备**。</span><span class="sxs-lookup"><span data-stu-id="19c5e-223">Select **Devices**.</span></span> <span data-ttu-id="19c5e-224">UEFI 菜单将反映配置的设置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="19c5e-224">The UEFI menu will reflect configured settings, as shown in the following figure.</span></span>

    ![Surface UEFI](images/df3.png)

    <span data-ttu-id="19c5e-226">请注意如何：</span><span class="sxs-lookup"><span data-stu-id="19c5e-226">Note how:</span></span>

      - <span data-ttu-id="19c5e-227">由于"允许本地用户更改 **UEFI"** 设置设置为"无"，因此设置灰化。</span><span class="sxs-lookup"><span data-stu-id="19c5e-227">The settings are greyed out because **Allow local user to change UEFI setting** is set to None.</span></span>
      - <span data-ttu-id="19c5e-228">音频设置为关闭， **因为麦克风和扬声器** 设置为 **禁用**。</span><span class="sxs-lookup"><span data-stu-id="19c5e-228">Audio is set to off because **Microphones and speakers** are set to **Disabled**.</span></span>

## <span data-ttu-id="19c5e-229">删除 DFCI 策略设置</span><span class="sxs-lookup"><span data-stu-id="19c5e-229">Removing DFCI policy settings</span></span>

<span data-ttu-id="19c5e-230">创建 DFCI 配置文件时，所有配置的设置将在配置文件的管理作用域内的所有设备中保持有效。</span><span class="sxs-lookup"><span data-stu-id="19c5e-230">When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile’s scope of management.</span></span> <span data-ttu-id="19c5e-231">你仅可以通过直接编辑 DFCI 配置文件来删除 DFCI 策略设置。</span><span class="sxs-lookup"><span data-stu-id="19c5e-231">You can only remove DFCI policy settings by editing the DFCI profile directly.</span></span>

<span data-ttu-id="19c5e-232">如果原始 DFCI 配置文件已删除，则可以通过创建新配置文件，然后编辑相应设置来删除策略设置。</span><span class="sxs-lookup"><span data-stu-id="19c5e-232">If the original DFCI profile has been deleted, you can remove policy settings by creating a new profile and then editing the settings, as appropriate.</span></span>

## <span data-ttu-id="19c5e-233">删除 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="19c5e-233">Removing DFCI management</span></span>

**<span data-ttu-id="19c5e-234">若要删除 DFCI 管理，将设备返回到出厂新状态：</span><span class="sxs-lookup"><span data-stu-id="19c5e-234">To remove DFCI management and return device to factory new state:</span></span>**

1. <span data-ttu-id="19c5e-235">从 Intune 停用设备：</span><span class="sxs-lookup"><span data-stu-id="19c5e-235">Retire the device from Intune:</span></span>
    1. <span data-ttu-id="19c5e-236">在终结点管理器devicemanagement.microsoft.com，选择> **所有设备的组**。</span><span class="sxs-lookup"><span data-stu-id="19c5e-236">In Endpoint Manager at  devicemanagement.microsoft.com, choose **Groups > All Devices**.</span></span> <span data-ttu-id="19c5e-237">选择要停用的设备，然后选择"停用 **/擦除"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-237">Select the devices you want to retire, and then choose **Retire/Wipe.**</span></span> <span data-ttu-id="19c5e-238">若要了解详情，请参阅使用擦除、停用或 [手动注销设备来删除设备](https://docs.microsoft.com/intune/remote-actions/devices-wipe)。</span><span class="sxs-lookup"><span data-stu-id="19c5e-238">To learn more refer to [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/remote-actions/devices-wipe).</span></span> 
2. <span data-ttu-id="19c5e-239">从 Intune 中删除 Autopilot 注册：</span><span class="sxs-lookup"><span data-stu-id="19c5e-239">Delete the Autopilot registration from Intune:</span></span>
    1.  <span data-ttu-id="19c5e-240">Choose **Device enrollment > Windows enrollment > Devices.**</span><span class="sxs-lookup"><span data-stu-id="19c5e-240">Choose **Device enrollment > Windows enrollment > Devices**.</span></span>
    2. <span data-ttu-id="19c5e-241">在 Windows Autopilot 设备下，选择要删除的设备，然后选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="19c5e-241">Under Windows Autopilot devices, choose the devices you want to delete, and then choose **Delete**.</span></span>
3. <span data-ttu-id="19c5e-242">使用 Surface 品牌以太网适配器将设备连接到有线 Internet。</span><span class="sxs-lookup"><span data-stu-id="19c5e-242">Connect device to wired internet with Surface-branded ethernet adapter.</span></span> <span data-ttu-id="19c5e-243">重新启动设备并打开 UEFI 菜单 (长按调高按钮，同时按下并释放电源按钮) 。</span><span class="sxs-lookup"><span data-stu-id="19c5e-243">Restart device and open the UEFI menu (press and hold the volume-up button while also pressing and releasing the power button).</span></span>
4. <span data-ttu-id="19c5e-244">Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**</span><span class="sxs-lookup"><span data-stu-id="19c5e-244">Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**</span></span>

<span data-ttu-id="19c5e-245">若要使用 Intune 继续管理设备，但不进行 DFCI 管理，请自行将设备注册到 Autopilot，然后注册到 Intune。</span><span class="sxs-lookup"><span data-stu-id="19c5e-245">To keep managing the device with Intune, but without DFCI management, self-register the device to Autopilot and enroll it to Intune.</span></span> <span data-ttu-id="19c5e-246">DFCI 不会应用于自注册设备。</span><span class="sxs-lookup"><span data-stu-id="19c5e-246">DFCI will not be applied to self-registered devices.</span></span>

## <span data-ttu-id="19c5e-247">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="19c5e-247">Learn more</span></span>
- <span data-ttu-id="19c5e-248">[Ignite 2019：宣布从 Intune 远程管理 Surface UEFI 设置](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="19c5e-248">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span></span>
- [<span data-ttu-id="19c5e-249">Windows Autopilot 和 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="19c5e-249">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md) 
- [<span data-ttu-id="19c5e-250">在 Microsoft Intune 中的 Windows 设备上使用 DFCI 配置文件</span><span class="sxs-lookup"><span data-stu-id="19c5e-250">Use DFCI profiles on Windows devices in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

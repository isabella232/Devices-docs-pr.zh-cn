---
title: Surface UEFI 设置的 Intune 管理
description: 本文介绍如何在 Microsoft Intune 中配置 DFCI 环境和管理目标 Surface 设备的固件设置。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 11/13/2019
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 0aa69bb229f0d76972620bc58f236e43e03075b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831008"
---
# <span data-ttu-id="ae2eb-103">Surface UEFI 设置的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="ae2eb-103">Intune management of Surface UEFI settings</span></span>

## <span data-ttu-id="ae2eb-104">简介</span><span class="sxs-lookup"><span data-stu-id="ae2eb-104">Introduction</span></span>

<span data-ttu-id="ae2eb-105">从云管理设备的能力大大简化了 IT 部署和在生命周期中的预配。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-105">The ability to manage devices from the cloud has dramatically simplified IT deployment and provisioning across the lifecycle.</span></span> <span data-ttu-id="ae2eb-106">使用内置于 Microsoft Intune 的设备固件配置接口（DFCI）配置文件（现在在[公共预览版](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)中可用），Surface UEFI 管理将新式管理堆栈扩展到 UEFI 硬件级别。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-106">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in [public preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="ae2eb-107">DFCI 支持零接触预配，消除了 BIOS 密码，提供了安全设置（包括启动选项和内置外围设备）的控制权，并为将来的高级安全方案奠定了基础。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-107">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="ae2eb-108">有关常见问题的解答，请参阅[Ignite 2019：宣布从 Intune 进行 SURFACE UEFI 设置的远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-108">For answers to frequently asked questions, see [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

### <span data-ttu-id="ae2eb-109">Background</span><span class="sxs-lookup"><span data-stu-id="ae2eb-109">Background</span></span>

<span data-ttu-id="ae2eb-110">与运行 Windows 10 的任何计算机一样，Surface 设备依赖于 SoC 中存储的代码，使 CPU 能够与硬盘驱动器、显示器设备、USB 端口和其他设备进行接口。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-110">Like any computer running Windows 10, Surface devices rely on code stored in the SoC that enables the CPU to interface with hard drives, display devices, USB ports, and other devices.</span></span> <span data-ttu-id="ae2eb-111">存储在此只读内存（ROM）中的程序称为固件（虽然存储在动态媒体中的程序称为软件）。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-111">The programs stored in this read-only memory (ROM) are known as firmware (while programs stored in dynamic media are known as software).</span></span>

<span data-ttu-id="ae2eb-112">与目前市场上提供的其他 Windows 10 设备相比，Surface 为 IT 管理员提供通过一组丰富的 UEFI 配置设置配置和管理固件的能力。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-112">In contrast to other Windows 10 devices available in the market today, Surface provides IT admins with the ability to configure and manage firmware through a rich set of UEFI configuration settings.</span></span> <span data-ttu-id="ae2eb-113">这在基于软件的策略管理（通过移动设备管理（MDM）策略、配置管理器或组策略实现）的基础上提供了一层硬件控制。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-113">This provides a layer of hardware control on top of software-based policy management as implemented via mobile device management (MDM) policies, Configuration Manager or Group Policy.</span></span> <span data-ttu-id="ae2eb-114">例如，在具有敏感信息的高度安全的区域中部署设备的组织可通过在硬件级别删除功能来阻止相机使用。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-114">For example, organizations deploying devices in highly secure areas with sensitive information can prevent camera use by removing functionality at the hardware level.</span></span> <span data-ttu-id="ae2eb-115">从设备角度看，通过固件设置关闭摄像头相当于实际删除摄像头。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-115">From a device standpoint, turning the camera off via a firmware setting is equivalent to physically removing the camera.</span></span> <span data-ttu-id="ae2eb-116">比较在固件级别管理的增加的安全性，仅依赖于操作系统软件设置。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-116">Compare the added security of managing at the firmware level to relying only on operating system software settings.</span></span> <span data-ttu-id="ae2eb-117">例如，如果通过域环境中的策略设置禁用 Windows 音频服务，本地管理员仍然可以重新启用该服务。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-117">For example, if you disable the Windows audio service via a policy setting in a domain environment, a local admin could still re-enable the service.</span></span>

### <span data-ttu-id="ae2eb-118">DFCI 与 SEMM</span><span class="sxs-lookup"><span data-stu-id="ae2eb-118">DFCI versus SEMM</span></span>

<span data-ttu-id="ae2eb-119">到目前为止，管理固件需要将设备注册到 Surface Enterprise 管理模式（SEMM），并具有持续手动 IT 密集型任务的开销。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-119">Until now, managing firmware required enrolling devices into Surface Enterprise Management Mode (SEMM) with the overhead of ongoing manual IT-intensive tasks.</span></span> <span data-ttu-id="ae2eb-120">例如，SEMM 要求 IT 员工以物理方式访问每台电脑以在证书管理过程中输入两位数的 pin 码。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-120">As an example, SEMM requires IT staff to physically access each PC to enter a two-digit pin as part of the certificate management process.</span></span> <span data-ttu-id="ae2eb-121">尽管 SEMM 在严格的本地环境中为组织提供了良好的解决方案，但其复杂性和 IT 密集型要求使其使用成本很高。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-121">Although SEMM remains a good solution for organizations in a strictly on-premises environment, its complexity and IT-intensive requirements make it costly to use.</span></span>

<span data-ttu-id="ae2eb-122">现在，使用 Microsoft Intune 中的新集成的 UEFI 固件管理功能，锁定硬件的功能在单个控制台中预配、安全和优化更新的新功能更易于使用，现在统一为[Microsoft 终结点管理器](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-122">Now with newly integrated UEFI firmware management capabilities in Microsoft Intune, the ability to lock down hardware is simplified and easier to use with new features for provisioning, security, and streamlined updating all in a single console, now unified as [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span> <span data-ttu-id="ae2eb-123">下图显示了在设备上直接查看的 UEFI 设置（左图），并在终结点管理器控制台中查看（右）。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-123">The following figure shows UEFI settings viewed directly on the device (left) and viewed in the Endpoint Manager console (right).</span></span>

![在设备（左侧）和终结点管理器控制台（右）中显示的 UEFI 设置](images/uefidfci.png)

<span data-ttu-id="ae2eb-125">Crucially，DFCI 支持零接触管理，消除 IT 管理员对手动交互的需要。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-125">Crucially, DFCI enables zero touch management, eliminating the need for manual interaction by IT admins.</span></span> <span data-ttu-id="ae2eb-126">DFCI 通过 Windows Autopilot 使用 Intune 中的设备配置文件功能进行部署。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-126">DFCI is deployed via Windows Autopilot using the device profiles capability in Intune.</span></span> <span data-ttu-id="ae2eb-127">设备配置文件允许你添加和配置设置，然后可将这些设置部署到在你的组织中注册管理的设备。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-127">A device profile allows you to add and configure settings which can then be deployed to devices enrolled in management within your organization.</span></span> <span data-ttu-id="ae2eb-128">设备收到设备配置文件后，将自动应用功能和设置。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-128">Once the device receives the device profile, the features and settings are applied automatically.</span></span> <span data-ttu-id="ae2eb-129">常见设备配置文件的示例包括电子邮件、设备限制、VPN、Wi-fi 和管理模板。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-129">Examples of common device profiles include Email, Device restrictions, VPN, Wi-Fi, and Administrative templates.</span></span> <span data-ttu-id="ae2eb-130">DFCI 只是一个附加的设备配置文件，使你能够从云管理 UEFI 配置设置，而无需维护本地基础结构。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-130">DFCI is simply an additional device profile that enables you to manage UEFI configuration settings from the cloud without having to maintain on-premises infrastructure.</span></span>  

## <span data-ttu-id="ae2eb-131">支持的设备</span><span class="sxs-lookup"><span data-stu-id="ae2eb-131">Supported devices</span></span>

<span data-ttu-id="ae2eb-132">目前，DFCI 在以下设备中受支持：</span><span class="sxs-lookup"><span data-stu-id="ae2eb-132">At this time, DFCI is supported in the following devices:</span></span>

- <span data-ttu-id="ae2eb-133">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="ae2eb-133">Surface Pro 7</span></span>
- <span data-ttu-id="ae2eb-134">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="ae2eb-134">Surface Pro X</span></span>
- <span data-ttu-id="ae2eb-135">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="ae2eb-135">Surface Laptop 3</span></span>

> [!NOTE]
> <span data-ttu-id="ae2eb-136">Surface Pro X 不支持内置摄像头、音频和 Wi-fi/蓝牙的 DFCI 设置管理。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-136">Surface Pro X does not support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth.</span></span>

## <span data-ttu-id="ae2eb-137">必备条件</span><span class="sxs-lookup"><span data-stu-id="ae2eb-137">Prerequisites</span></span>

- <span data-ttu-id="ae2eb-138">设备必须由[Microsoft 云解决方案提供商（CSP）合作伙伴](https://partner.microsoft.com/membership/cloud-solution-provider)或 OEM 分发服务器通过 Windows Autopilot 注册。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-138">Devices must be registered with Windows Autopilot by a [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider) or OEM distributor.</span></span>

- <span data-ttu-id="ae2eb-139">在为 Surface 配置 DFCI 之前，你应该熟悉[Microsoft Intune](https://docs.microsoft.com/intune/)和[azure Active DIRECTORY](https://docs.microsoft.com/azure/active-directory/) （azure AD）中的 Autopilot 配置要求。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-139">Before configuring DFCI for Surface, you should be familiar with Autopilot configuration requirements in  [Microsoft Intune](https://docs.microsoft.com/intune/) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).</span></span>

## <span data-ttu-id="ae2eb-140">开始之前</span><span class="sxs-lookup"><span data-stu-id="ae2eb-140">Before you begin</span></span>

<span data-ttu-id="ae2eb-141">将目标 Surface 设备添加到 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-141">Add your target Surface devices to an Azure AD security group.</span></span> <span data-ttu-id="ae2eb-142">有关创建和管理安全组的详细信息，请参阅[Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-142">For more information about creating and managing security groups, refer to [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).</span></span>

## <span data-ttu-id="ae2eb-143">为 Surface 设备配置 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="ae2eb-143">Configure DFCI management for Surface devices</span></span>

<span data-ttu-id="ae2eb-144">DFCI 环境需要设置包含设置和 Autopilot 配置文件的 DFCI 配置文件，以便将设置应用于已注册的设备。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-144">A DFCI environment requires setting up a DFCI profile that contains  the settings and an Autopilot profile to apply the settings to registered devices.</span></span> <span data-ttu-id="ae2eb-145">还建议使用注册状态配置文件，以确保在用户第一次启动设备时，在 OOBE 设置期间将设置推送到运行状态。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-145">An enrollment status profile is also recommended to ensure settings are pushed down during OOBE setup when users first start the device.</span></span> <span data-ttu-id="ae2eb-146">本指南介绍如何配置 DFCI 环境和管理目标 Surface 设备的 UEFI 配置设置。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-146">This guide explains how to configure the DFCI environment and manage UEFI configuration settings for targeted Surface devices.</span></span>

## <span data-ttu-id="ae2eb-147">创建 DFCI 配置文件</span><span class="sxs-lookup"><span data-stu-id="ae2eb-147">Create DFCI profile</span></span>

<span data-ttu-id="ae2eb-148">在配置 DFCI 策略设置之前，请先创建一个 DFCI 配置文件，然后将其分配给包含你的目标设备的 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-148">Before configuring DFCI policy settings, first create a DFCI profile and assign it to the Azure AD security group that contains your target devices.</span></span>

1. <span data-ttu-id="ae2eb-149">在 devicemanagement.microsoft.com 登录到你的租户。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-149">Sign into your tenant at  devicemanagement.microsoft.com.</span></span>
2. <span data-ttu-id="ae2eb-150">在 Microsoft 终结点管理器管理中心，选择 "**设备" > 配置文件 > "创建配置文件**"，然后输入名称;例如， **DFCI 配置策略。**</span><span class="sxs-lookup"><span data-stu-id="ae2eb-150">In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile** and enter a name; for example, **DFCI Configuration Policy.**</span></span>
3. <span data-ttu-id="ae2eb-151">为 "平台类型" 选择**Windows 10 和更高版本**。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-151">Select **Windows 10 and later** for platform type.</span></span>
4. <span data-ttu-id="ae2eb-152">在 "配置文件类型" 下拉列表中，选择 "**设备固件配置" 界面**以打开包含所有可用策略设置的 DFCI 刀片。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-152">In the Profile type drop down list, select **Device Firmware Configuration Interface** to open the DFCI blade containing all available policy settings.</span></span> <span data-ttu-id="ae2eb-153">有关 DFCI 设置的信息，请参阅此页面上的表1或[Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-153">For information on DFCI settings, refer to Table 1 on this page or the [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span> <span data-ttu-id="ae2eb-154">你可以在初始设置过程中或在稍后通过编辑 DFCI 配置文件来配置 DFCI 设置。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-154">You can configure DFCI settings during the initial setup process or later by editing the DFCI profile.</span></span>

    ![创建 DFCI 配置文件](images/df1.png)

5. <span data-ttu-id="ae2eb-156">单击 **"确定"** ，然后选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-156">Click **OK** and then select **Create**.</span></span>
6. <span data-ttu-id="ae2eb-157">选择 "**作业**"，然后在 "**选择要包括的组**" 下，选择包含目标设备的 Azure AD 安全组，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-157">Select **Assignments** and under **Select groups to include** select the Azure AD security group that contains your target devices, as shown in the following figure.</span></span> <span data-ttu-id="ae2eb-158">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-158">Click **Save**.</span></span>

    ![分配安全组](images/df2a.png)

## <span data-ttu-id="ae2eb-160">创建 Autopilot 配置文件</span><span class="sxs-lookup"><span data-stu-id="ae2eb-160">Create Autopilot profile</span></span>

1. <span data-ttu-id="ae2eb-161">在 devicemanagement.microsoft.com 的终结点管理器中，选择 "**设备" > Windows 注册**并向下滚动到 "**部署配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-161">In Endpoint Manager at  devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles**.</span></span>
2. <span data-ttu-id="ae2eb-162">选择 "**创建配置文件**"，然后输入名称;例如， **"我的 Autopilot" 配置文件**，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-162">Select **Create profile** and enter a name; for example, **My Autopilot profile**, and select **Next**.</span></span>
3. <span data-ttu-id="ae2eb-163">选择以下设置：</span><span class="sxs-lookup"><span data-stu-id="ae2eb-163">Select the following settings:</span></span>

    - <span data-ttu-id="ae2eb-164">部署模式：**用户驱动**的。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-164">Deployment mode: **User-Driven**.</span></span>
    - <span data-ttu-id="ae2eb-165">加入类型： Azure **AD 已加入**。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-165">Join type: Azure **AD joined**.</span></span>

4. <span data-ttu-id="ae2eb-166">保留其余默认设置不变，然后选择 "**下一步**"，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-166">Leave the remaining default settings unchanged and select **Next**, as shown in the following figure.</span></span>

    ![创建 Autopilot 配置文件](images/df3b.png)

5. <span data-ttu-id="ae2eb-168">在 "作业" 页面上，选择 "**选择要包含的组**"，然后单击您的 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-168">On the Assignments page, choose **Select groups to include** and click your Azure AD security group.</span></span> <span data-ttu-id="ae2eb-169">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-169">Select **Next**.</span></span>
6. <span data-ttu-id="ae2eb-170">接受摘要，然后选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-170">Accept the summary and then select **Create**.</span></span> <span data-ttu-id="ae2eb-171">此时将创建 Autopilot 配置文件，并将其分配给该组。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-171">The Autopilot profile is now created and assigned to the group.</span></span>

## <span data-ttu-id="ae2eb-172">"配置注册状态" 页面</span><span class="sxs-lookup"><span data-stu-id="ae2eb-172">Configure Enrollment Status Page</span></span>

<span data-ttu-id="ae2eb-173">若要确保设备在用户登录之前在 OOBE 期间应用 DFCI 配置，你需要配置注册状态。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-173">To ensure that devices apply the DFCI configuration during OOBE before users sign in, you need to configure enrollment status.</span></span>

<span data-ttu-id="ae2eb-174">有关详细信息，请参阅[设置注册状态页面](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-174">For more information, refer to [Set up an enrollment status page](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).</span></span>


## <span data-ttu-id="ae2eb-175">在 Surface 设备上配置 DFCI 设置</span><span class="sxs-lookup"><span data-stu-id="ae2eb-175">Configure DFCI settings on Surface devices</span></span>

<span data-ttu-id="ae2eb-176">DFCI 包括一组简化的 UEFI 配置策略，可通过在硬件级别锁定设备来提供额外的安全级别。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-176">DFCI includes a streamlined set of UEFI configuration policies that provide an extra level of security by locking down devices at the hardware level.</span></span> <span data-ttu-id="ae2eb-177">DFCI 设计为与软件级别的移动设备管理设置结合使用。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-177">DFCI is designed to be used in conjunction with mobile device management settings at the software level.</span></span> <span data-ttu-id="ae2eb-178">请注意，DFCI 设置仅影响内置于 Surface 设备中的硬件组件，并且不会扩展到连接的外围设备（如 USB 网络摄像头）。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-178">Note that DFCI settings only affect hardware components built into Surface devices and do not extend to attached peripherals such as USB webcams.</span></span> <span data-ttu-id="ae2eb-179">（但是，你可以使用 Intune 中的设备限制策略关闭对连接到软件级别的外围设备的访问。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-179">(However, you can use Device restriction policies in Intune to turn off access to attached peripherals at the software level).</span></span>

<span data-ttu-id="ae2eb-180">通过从终结点管理器编辑 DFCI 配置文件来配置 DFCI 策略设置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-180">You configure DFCI policy settings by editing the DFCI profile from Endpoint Manager, as shown in the figure below.</span></span> 

- <span data-ttu-id="ae2eb-181">在 devicemanagement.microsoft.com 的终结点管理器中，选择 **"设备" > Windows > 配置文件 > "DFCI 配置文件名称" > 属性 > 设置**。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-181">In Endpoint Manager at  devicemanagement.microsoft.com, select **Devices > Windows > Configuration Profiles > “DFCI profile name” > Properties > Settings**.</span></span>

    ![配置 DFCI 设置](images/dfciconfig.png)

### <span data-ttu-id="ae2eb-183">阻止用户访问 UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="ae2eb-183">Block user access to UEFI settings</span></span>

<span data-ttu-id="ae2eb-184">对于许多客户，阻止用户更改 UEFI 设置的功能至关重要，并且是使用 DFCI 的主要原因。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-184">For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI.</span></span> <span data-ttu-id="ae2eb-185">如表1所示，通过设置进行管理，**允许本地用户更改 UEFI 设置**。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-185">As listed in Table 1, this is managed via the setting **Allow local user to change UEFI settings**.</span></span> <span data-ttu-id="ae2eb-186">如果不编辑或配置此设置，本地用户将能够更改不由 Intune 管理的任何 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-186">If you do not edit or configure this setting, local users will be able to change any UEFI setting not managed by Intune.</span></span> <span data-ttu-id="ae2eb-187">因此，强烈建议禁用 "**允许本地用户更改 UEFI 设置"。**</span><span class="sxs-lookup"><span data-stu-id="ae2eb-187">Therefore, it’s highly recommended to disable **Allow local user to change UEFI settings.**</span></span>
<span data-ttu-id="ae2eb-188">其余的 DFCI 设置使你能够关闭其他用户可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-188">The rest of the DFCI settings enable you to turn off functionality that would otherwise be available to users.</span></span> <span data-ttu-id="ae2eb-189">例如，如果您需要保护高度安全的区域中的敏感信息，则可以禁用摄像头，如果不希望用户从 USB 驱动器启动，也可以将其禁用。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-189">For example, if you need to protect sensitive information in highly secure areas, you can disable the camera, and if you don’t want users booting from USB drives, you can disable that also.</span></span>

### <span data-ttu-id="ae2eb-190">表 1. </span><span class="sxs-lookup"><span data-stu-id="ae2eb-190">Table 1.</span></span> <span data-ttu-id="ae2eb-191">DFCI 方案</span><span class="sxs-lookup"><span data-stu-id="ae2eb-191">DFCI scenarios</span></span>

| <span data-ttu-id="ae2eb-192">设备管理目标</span><span class="sxs-lookup"><span data-stu-id="ae2eb-192">Device management goal</span></span>                        | <span data-ttu-id="ae2eb-193">配置步骤</span><span class="sxs-lookup"><span data-stu-id="ae2eb-193">Configuration steps</span></span>                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ae2eb-194">阻止本地用户更改 UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="ae2eb-194">Block local users from changing UEFI settings</span></span> | <span data-ttu-id="ae2eb-195">在 "**安全功能" 下 > 允许本地用户更改 UEFI 设置**"下，选择"**无**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-195">Under **Security Features > Allow local user to change UEFI settings**, select **None**.</span></span>              |
| <span data-ttu-id="ae2eb-196">禁用相机</span><span class="sxs-lookup"><span data-stu-id="ae2eb-196">Disable cameras</span></span>                               | <span data-ttu-id="ae2eb-197">在 "**内置硬件 > 照相机**" 下，选择 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-197">Under **Built in Hardware > Cameras**, select **Disabled**.</span></span>                                       |
| <span data-ttu-id="ae2eb-198">禁用麦克风和扬声器</span><span class="sxs-lookup"><span data-stu-id="ae2eb-198">Disable Microphones and speakers</span></span>              | <span data-ttu-id="ae2eb-199">在 "**内置硬件 > 麦克风和扬声器**" 下，选择 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-199">Under **Built in Hardware > Microphones and speakers**, select **Disabled**.</span></span>                      |
| <span data-ttu-id="ae2eb-200">禁用无线电收发器（蓝牙、Wi-fi）</span><span class="sxs-lookup"><span data-stu-id="ae2eb-200">Disable radios (Bluetooth, Wi-Fi)</span></span>             | <span data-ttu-id="ae2eb-201">在 "**内置硬件 > 无线收发器（蓝牙、wi-fi 等）**" 下，选择 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-201">Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc…)**, select **Disabled**.</span></span>                   |
| <span data-ttu-id="ae2eb-202">禁止从外部媒体（USB、SD）启动</span><span class="sxs-lookup"><span data-stu-id="ae2eb-202">Disable Boot from external media (USB, SD)</span></span>    | <span data-ttu-id="ae2eb-203">在 "**内置硬件 > 启动选项" 下 > 从外部媒体（USB、SD）启动**"，选择"**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-203">Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**.</span></span> |

> [!CAUTION]
> <span data-ttu-id="ae2eb-204">仅应在具有有线以太网连接的设备上使用 "**禁用无线收发器（蓝牙、wi-fi）** " 设置。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-204">The **Disable radios (Bluetooth, Wi-Fi)** setting should only be used on devices that have a wired Ethernet connection.</span></span>
 
> [!NOTE]
>  <span data-ttu-id="ae2eb-205">Intune 中的 DFCI 包括两个目前不适用于 Surface 设备的设置：（1） CPU 和 IO 虚拟化，（2）禁用从网络适配器启动。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-205">DFCI in Intune includes two settings that do not currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.</span></span>
 
<span data-ttu-id="ae2eb-206">Intune 提供用于委派管理权限和适用规则以管理设备类型的作用域标记。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-206">Intune provides Scope tags to delegate administrative rights and Applicability Rules to manage device types.</span></span> <span data-ttu-id="ae2eb-207">有关策略管理支持的详细信息以及所有 DFCI 设置的完整详细信息，请参阅[Microsoft Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-207">For more information about policy management support and full details on all DFCI settings, refer to [Microsoft Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span>

## <span data-ttu-id="ae2eb-208">在 Autopilot 中注册设备</span><span class="sxs-lookup"><span data-stu-id="ae2eb-208">Register devices in Autopilot</span></span>

<span data-ttu-id="ae2eb-209">如上所述，DFCI 只能应用于经销商或分销商在 Windows Autopilot 中注册的设备，此时仅支持 Surface Pro 7、Surface Pro X 和 Surface 笔记本电脑3。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-209">As stated above, DFCI can only be applied on devices registered in Windows Autopilot by your reseller or distributor and is only supported, at this time, on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="ae2eb-210">出于安全考虑，不能将设备 "自设置" 到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-210">For security reasons, it’s not possible to “self-provision” your devices into Autopilot.</span></span>

## <span data-ttu-id="ae2eb-211">手动同步 Autopilot 设备</span><span class="sxs-lookup"><span data-stu-id="ae2eb-211">Manually Sync Autopilot devices</span></span>

<span data-ttu-id="ae2eb-212">尽管 Intune 策略设置通常几乎会立即应用，但可能会有10分钟的延迟，然后设置才会在目标设备上生效。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-212">Although Intune policy settings typically get applied almost immediately, there may be a delay of 10 minutes before the settings take effect on targeted devices.</span></span> <span data-ttu-id="ae2eb-213">在极少数情况下，可能需要最多8小时的延迟。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-213">In rare circumstances, delays of up to 8 hours are possible.</span></span> <span data-ttu-id="ae2eb-214">若要确保尽快应用 "设置" （例如在测试方案中），可以手动同步目标设备。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-214">To ensure settings apply as soon as possible, (such as in test scenarios), you can manually sync the target devices.</span></span>

- <span data-ttu-id="ae2eb-215">在 devicemanagement.microsoft.com 的终结点管理器中，转到 "设备" **> 设备注册 > windows 注册 > Windows Autopilot 设备**，然后选择 "**同步**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-215">In Endpoint Manager at  devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync**.</span></span>

 <span data-ttu-id="ae2eb-216">有关详细信息，请参阅[手动同步你的 Windows 设备](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-216">For more information, refer to [Sync your Windows device manually](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).</span></span>

> [!NOTE]
> <span data-ttu-id="ae2eb-217">当直接在 UEFI 中调整设置时，你需要确保设备完全重启到标准 Windows 登录。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-217">When adjusting settings directly in UEFI, you need to ensure the device fully restarts to the standard Windows login.</span></span>

## <span data-ttu-id="ae2eb-218">在 DFCI 托管设备上验证 UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="ae2eb-218">Verifying UEFI settings on DFCI-managed devices</span></span>

<span data-ttu-id="ae2eb-219">在测试环境中，可以验证 Surface UEFI 界面中的设置。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-219">In a test environment, you can verify settings in the Surface UEFI interface.</span></span>

1. <span data-ttu-id="ae2eb-220">打开 Surface UEFI，其中包括同时按下 "**音量 +** " 和 "**电源**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-220">Open Surface UEFI, which involves pressing the **Volume +** and **Power** buttons at the same time.</span></span>
2. <span data-ttu-id="ae2eb-221">选择 "**设备**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-221">Select **Devices**.</span></span> <span data-ttu-id="ae2eb-222">UEFI 菜单将反映已配置的设置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-222">The UEFI menu will reflect configured settings, as shown in the following figure.</span></span>

    ![Surface UEFI](images/df3.png)

    <span data-ttu-id="ae2eb-224">注意操作方法：</span><span class="sxs-lookup"><span data-stu-id="ae2eb-224">Note how:</span></span>

      - <span data-ttu-id="ae2eb-225">设置将灰显，因为 "**允许本地用户更改 UEFI" 设置**将设置为 "无"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-225">The settings are greyed out because **Allow local user to change UEFI setting** is set to None.</span></span>
      - <span data-ttu-id="ae2eb-226">将音频设置为 "关闭" **，因为麦克风和扬声器**设置为 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-226">Audio is set to off because **Microphones and speakers** are set to **Disabled**.</span></span>

## <span data-ttu-id="ae2eb-227">删除 DFCI 策略设置</span><span class="sxs-lookup"><span data-stu-id="ae2eb-227">Removing DFCI policy settings</span></span>

<span data-ttu-id="ae2eb-228">创建 DFCI 配置文件时，所有配置的设置将在配置文件的管理范围内的所有设备上保持有效。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-228">When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile’s scope of management.</span></span> <span data-ttu-id="ae2eb-229">仅可通过直接编辑 DFCI 配置文件来删除 DFCI 策略设置。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-229">You can only remove DFCI policy settings by editing the DFCI profile directly.</span></span>

<span data-ttu-id="ae2eb-230">如果已删除原始 DFCI 配置文件，则可以通过创建新的配置文件，然后根据需要编辑设置来删除策略设置。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-230">If the original DFCI profile has been deleted, you can remove policy settings by creating a new profile and then editing the settings, as appropriate.</span></span>

## <span data-ttu-id="ae2eb-231">删除 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="ae2eb-231">Removing DFCI management</span></span>

**<span data-ttu-id="ae2eb-232">要删除 DFCI 管理并将设备返回到出厂新状态，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae2eb-232">To remove DFCI management and return device to factory new state:</span></span>**

1. <span data-ttu-id="ae2eb-233">从 Intune 中停用设备：</span><span class="sxs-lookup"><span data-stu-id="ae2eb-233">Retire the device from Intune:</span></span>
    1. <span data-ttu-id="ae2eb-234">在 devicemanagement.microsoft.com 的终结点管理器中，选择 "**组 > 所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-234">In Endpoint Manager at  devicemanagement.microsoft.com, choose **Groups > All Devices**.</span></span> <span data-ttu-id="ae2eb-235">选择要停用的设备，然后选择 "**停用/擦除"。**</span><span class="sxs-lookup"><span data-stu-id="ae2eb-235">Select the devices you want to retire, and then choose **Retire/Wipe.**</span></span> <span data-ttu-id="ae2eb-236">若要了解详细信息，请参阅[使用擦除、停用或手动通过设备删除设备](https://docs.microsoft.com/intune/remote-actions/devices-wipe)。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-236">To learn more refer to [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/remote-actions/devices-wipe).</span></span> 
2. <span data-ttu-id="ae2eb-237">从 Intune 中删除 Autopilot 注册：</span><span class="sxs-lookup"><span data-stu-id="ae2eb-237">Delete the Autopilot registration from Intune:</span></span>
    1.  <span data-ttu-id="ae2eb-238">选择 "**设备注册" > Windows 注册 > 设备**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-238">Choose **Device enrollment > Windows enrollment > Devices**.</span></span>
    2. <span data-ttu-id="ae2eb-239">在 "Windows Autopilot 设备" 下，选择要删除的设备，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-239">Under Windows Autopilot devices, choose the devices you want to delete, and then choose **Delete**.</span></span>
3. <span data-ttu-id="ae2eb-240">将设备连接到带 Surface 品牌以太网适配器的有线互联网。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-240">Connect device to wired internet with Surface-branded ethernet adapter.</span></span> <span data-ttu-id="ae2eb-241">重启设备并打开 UEFI 菜单（按住音量键，同时按下并释放电源按钮）。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-241">Restart device and open the UEFI menu (press and hold the volume-up button while also pressing and releasing the power button).</span></span>
4. <span data-ttu-id="ae2eb-242">选择 "**管理 > 配置" 从网络 > 刷新**"，然后选择"**退出 "。**</span><span class="sxs-lookup"><span data-stu-id="ae2eb-242">Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**</span></span>

<span data-ttu-id="ae2eb-243">若要继续通过 Intune 管理设备，但没有 DFCI 管理，请自行注册设备以 Autopilot 并将其注册到 Intune。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-243">To keep managing the device with Intune, but without DFCI management, self-register the device to Autopilot and enroll it to Intune.</span></span> <span data-ttu-id="ae2eb-244">DFCI 将不会应用于自注册设备。</span><span class="sxs-lookup"><span data-stu-id="ae2eb-244">DFCI will not be applied to self-registered devices.</span></span>

## <span data-ttu-id="ae2eb-245">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="ae2eb-245">Learn more</span></span>
- <span data-ttu-id="ae2eb-246">[Ignite 2019：宣布从 Intune 进行 SURFACE UEFI 设置的远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="ae2eb-246">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span></span>
- [<span data-ttu-id="ae2eb-247">Windows Autopilot 和 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="ae2eb-247">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md) 
- [<span data-ttu-id="ae2eb-248">在 Microsoft Intune 中的 Windows 设备上使用 DFCI 配置文件</span><span class="sxs-lookup"><span data-stu-id="ae2eb-248">Use DFCI profiles on Windows devices in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

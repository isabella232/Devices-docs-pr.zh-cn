---
title: Surface UEFI 设置的 Intune 管理
description: 本文介绍如何在 Microsoft Intune 中配置 DFCI 环境，以及如何管理目标 Surface 设备的固件设置。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 08/19/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
ms.openlocfilehash: 9d83fe9b7febf996d2cb314399505ed050a69a92
ms.sourcegitcommit: b94832cba98e01014f7d184c85d79f8339e046c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941661"
---
# <span data-ttu-id="81605-103">Surface UEFI 设置的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="81605-103">Intune management of Surface UEFI settings</span></span>

## <span data-ttu-id="81605-104">简介</span><span class="sxs-lookup"><span data-stu-id="81605-104">Introduction</span></span>

<span data-ttu-id="81605-105">管理云中的设备的功能在整个生命周期中进行了重大化。</span><span class="sxs-lookup"><span data-stu-id="81605-105">The ability to manage devices from the cloud has dramatically simplified IT deployment and provisioning across the lifecycle.</span></span> <span data-ttu-id="81605-106">借助 Microsoft Intune (中内置的设备配置接口 (DFCI [) ](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)) 配置文件，Surface UEFI 管理层将现代管理堆叠到 UEFI 硬件级别。</span><span class="sxs-lookup"><span data-stu-id="81605-106">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in [public preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="81605-107">DFCI 支持零触控设置，消除 BIOS 密码，提供对安全设置的控制，包括启动选项和内置外围设备，并在未来为高级安全方案设置分页工作。</span><span class="sxs-lookup"><span data-stu-id="81605-107">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="81605-108">有关常见问题的解答，请参阅 [Ignite 2019：公布 Intune 的 Surface UEFI 设置远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。</span><span class="sxs-lookup"><span data-stu-id="81605-108">For answers to frequently asked questions, see [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

### <span data-ttu-id="81605-109">Background</span><span class="sxs-lookup"><span data-stu-id="81605-109">Background</span></span>

<span data-ttu-id="81605-110">与运行 Windows 10 的任何计算机类似，Surface 设备所存储在 SoC 中的代码，后续的 CPU 可将 CPU 与硬盘连接、显示设备、USB 端口以及其他设备。</span><span class="sxs-lookup"><span data-stu-id="81605-110">Like any computer running Windows 10, Surface devices rely on code stored in the SoC that enables the CPU to interface with hard drives, display devices, USB ports, and other devices.</span></span> <span data-ttu-id="81605-111">存储在此只读的 () 内存中的程序称为固件 (而存放在动态媒体中时，存储在动态媒体中的程序称为软件) 。</span><span class="sxs-lookup"><span data-stu-id="81605-111">The programs stored in this read-only memory (ROM) are known as firmware (while programs stored in dynamic media are known as software).</span></span>

<span data-ttu-id="81605-112">与当市场中可用的其他 Windows 10 设备相比，Surface 使 IT 管理员可通过一组丰富的 UEFI 配置设置来配置和管理固件。</span><span class="sxs-lookup"><span data-stu-id="81605-112">In contrast to other Windows 10 devices available in the market today, Surface provides IT admins with the ability to configure and manage firmware through a rich set of UEFI configuration settings.</span></span> <span data-ttu-id="81605-113">这在通过移动设备管理或 MDM) 策略、Configuration Manager 或组策略实施时，基于软件的策略管理提供基于软件 (的硬件控制。</span><span class="sxs-lookup"><span data-stu-id="81605-113">This provides a layer of hardware control on top of software-based policy management as implemented via mobile device management (MDM) policies, Configuration Manager or Group Policy.</span></span> <span data-ttu-id="81605-114">例如，将设备部署到高度安全性信息的区域，可能无法在硬件级别删除功能，防止相机使用。</span><span class="sxs-lookup"><span data-stu-id="81605-114">For example, organizations deploying devices in highly secure areas with sensitive information can prevent camera use by removing functionality at the hardware level.</span></span> <span data-ttu-id="81605-115">从设备角度来看，通过固件设置关闭相机以物理方式删除相机。</span><span class="sxs-lookup"><span data-stu-id="81605-115">From a device standpoint, turning the camera off via a firmware setting is equivalent to physically removing the camera.</span></span> <span data-ttu-id="81605-116">比较在固件级别管理的增强安全性，使其仅处理于操作系统软件设置。</span><span class="sxs-lookup"><span data-stu-id="81605-116">Compare the added security of managing at the firmware level to relying only on operating system software settings.</span></span> <span data-ttu-id="81605-117">例如，如果通过域环境中的策略设置禁用 Windows 音频服务，本地管理员仍然可以重新启用该服务。</span><span class="sxs-lookup"><span data-stu-id="81605-117">For example, if you disable the Windows audio service via a policy setting in a domain environment, a local admin could still re-enable the service.</span></span>

### <span data-ttu-id="81605-118">DFCI 与 SEMM</span><span class="sxs-lookup"><span data-stu-id="81605-118">DFCI versus SEMM</span></span>

<span data-ttu-id="81605-119">到目前为止，使用长期执行手动 IT 密集任务的开头，管理开发需要将设备注册到 Surface Enterprise 管理模式 (SEMM) 的固件。</span><span class="sxs-lookup"><span data-stu-id="81605-119">Until now, managing firmware required enrolling devices into Surface Enterprise Management Mode (SEMM) with the overhead of ongoing manual IT-intensive tasks.</span></span> <span data-ttu-id="81605-120">例如，SEMM 要求 IT 人员实际访问每台电脑，以在证书管理过程中输入两位数 PIN。</span><span class="sxs-lookup"><span data-stu-id="81605-120">As an example, SEMM requires IT staff to physically access each PC to enter a two-digit pin as part of the certificate management process.</span></span> <span data-ttu-id="81605-121">SEMM 在统一的本地环境中为组织保留了不错的解决方案，但其复杂性和 IT 密集性要求将充分利用费用。</span><span class="sxs-lookup"><span data-stu-id="81605-121">Although SEMM remains a good solution for organizations in a strictly on-premises environment, its complexity and IT-intensive requirements make it costly to use.</span></span>

<span data-ttu-id="81605-122">现在，借助 Microsoft Intune 中新集成的 UEFI 固件管理功能，因此锁定硬件的功能得到了简化，并且通过新功能用于在单个主机中进行配置、安全和简化更新，现在统一 [标识为 Microsoft 终结点管理器](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)。</span><span class="sxs-lookup"><span data-stu-id="81605-122">Now with newly integrated UEFI firmware management capabilities in Microsoft Intune, the ability to lock down hardware is simplified and easier to use with new features for provisioning, security, and streamlined updating all in a single console, now unified as [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span> <span data-ttu-id="81605-123">下图显示了直接在设备中查看的 UEFI 设置 (左侧) ，以及在适当的终结点 (管理员) 。</span><span class="sxs-lookup"><span data-stu-id="81605-123">The following figure shows UEFI settings viewed directly on the device (left) and viewed in the Endpoint Manager console (right).</span></span>

![设备与终结点管理器 (控制) 台的 UEFI (设置) ](images/uefidfci.png)

<span data-ttu-id="81605-125">从根本上来讲，DFCI 支持零触摸管理，不再需要 IT 管理员手动互动。</span><span class="sxs-lookup"><span data-stu-id="81605-125">Crucially, DFCI enables zero touch management, eliminating the need for manual interaction by IT admins.</span></span> <span data-ttu-id="81605-126">在 Intune 中使用设备配置文件功能通过 Windows Autopilot 部署 DFCI。</span><span class="sxs-lookup"><span data-stu-id="81605-126">DFCI is deployed via Windows Autopilot using the device profiles capability in Intune.</span></span> <span data-ttu-id="81605-127">设备配置文件让你可以添加和配置这些设置，然后可以将其部署到组织内管理中注册的设备。</span><span class="sxs-lookup"><span data-stu-id="81605-127">A device profile allows you to add and configure settings which can then be deployed to devices enrolled in management within your organization.</span></span> <span data-ttu-id="81605-128">设备收到该设备配置文件后，功能和设置将自动应用。</span><span class="sxs-lookup"><span data-stu-id="81605-128">Once the device receives the device profile, the features and settings are applied automatically.</span></span> <span data-ttu-id="81605-129">常见设备配置文件的示例包括电子邮件、设备限制、VPN、Wi-Fi 和管理模板。</span><span class="sxs-lookup"><span data-stu-id="81605-129">Examples of common device profiles include Email, Device restrictions, VPN, Wi-Fi, and Administrative templates.</span></span> <span data-ttu-id="81605-130">DFCI 只是一个附加设备配置文件，使你能够从云管理 UEFI 配置设置，而无需维护本地基础结构。</span><span class="sxs-lookup"><span data-stu-id="81605-130">DFCI is simply an additional device profile that enables you to manage UEFI configuration settings from the cloud without having to maintain on-premises infrastructure.</span></span>  

## <span data-ttu-id="81605-131">支持的设备</span><span class="sxs-lookup"><span data-stu-id="81605-131">Supported devices</span></span>

<span data-ttu-id="81605-132">以下设备支持 DFCI：</span><span class="sxs-lookup"><span data-stu-id="81605-132">DFCI is supported in the following devices:</span></span>

- <span data-ttu-id="81605-133">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="81605-133">Surface Pro 7</span></span>
- <span data-ttu-id="81605-134">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="81605-134">Surface Pro X</span></span>
- <span data-ttu-id="81605-135">Surface 笔记本电脑 3</span><span class="sxs-lookup"><span data-stu-id="81605-135">Surface Laptop 3</span></span>
- <span data-ttu-id="81605-136">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="81605-136">Surface Book 3</span></span>

> [!NOTE]
> <span data-ttu-id="81605-137">Surface Pro X 不支持针对内置相机、音频和 Wi-Fi/Bluetooth。</span><span class="sxs-lookup"><span data-stu-id="81605-137">Surface Pro X does not support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth.</span></span>

## <span data-ttu-id="81605-138">必备条件</span><span class="sxs-lookup"><span data-stu-id="81605-138">Prerequisites</span></span>

- <span data-ttu-id="81605-139">设备必须由 Microsoft 云解决方案提供商未 [面向 Windows Autopilot (CSP 或](https://partner.microsoft.com/membership/cloud-solution-provider) OEM) 分发商注册。</span><span class="sxs-lookup"><span data-stu-id="81605-139">Devices must be registered with Windows Autopilot by a [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider) or OEM distributor.</span></span>

- <span data-ttu-id="81605-140">在为 Surface 配置 DFCI 之前，你应熟悉  [Microsoft Intune](https://docs.microsoft.com/intune/) 和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) 中的 Autopilot 配置 (Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="81605-140">Before configuring DFCI for Surface, you should be familiar with Autopilot configuration requirements in  [Microsoft Intune](https://docs.microsoft.com/intune/) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).</span></span>

## <span data-ttu-id="81605-141">开始之前</span><span class="sxs-lookup"><span data-stu-id="81605-141">Before you begin</span></span>

<span data-ttu-id="81605-142">将目标 Surface 设备添加到 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="81605-142">Add your target Surface devices to an Azure AD security group.</span></span> <span data-ttu-id="81605-143">有关创建和管理安全组的详细信息，请参阅 [Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="81605-143">For more information about creating and managing security groups, refer to [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).</span></span>

## <span data-ttu-id="81605-144">为 Surface 设备配置 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="81605-144">Configure DFCI management for Surface devices</span></span>

<span data-ttu-id="81605-145">DFCI 环境要求设置一个 DFCI 配置文件，其中包含设置和 Autopilot 配置文件，以将设置应用到已注册设备。</span><span class="sxs-lookup"><span data-stu-id="81605-145">A DFCI environment requires setting up a DFCI profile that contains  the settings and an Autopilot profile to apply the settings to registered devices.</span></span> <span data-ttu-id="81605-146">还建议注册状态配置文件，以确保在用户首次启动设备时，在 OOBE 设置过程中设置已被推送。</span><span class="sxs-lookup"><span data-stu-id="81605-146">An enrollment status profile is also recommended to ensure settings are pushed down during OOBE setup when users first start the device.</span></span> <span data-ttu-id="81605-147">此指南介绍了如何配置 DFCI 环境和管理针对 Surface 设备的 UEFI 配置设置。</span><span class="sxs-lookup"><span data-stu-id="81605-147">This guide explains how to configure the DFCI environment and manage UEFI configuration settings for targeted Surface devices.</span></span>

## <span data-ttu-id="81605-148">创建 DFCI 配置文件</span><span class="sxs-lookup"><span data-stu-id="81605-148">Create DFCI profile</span></span>

<span data-ttu-id="81605-149">在配置 DFCI 策略设置之前，请首先创建一个 DFCI 配置文件并将其分配到包含目标设备的 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="81605-149">Before configuring DFCI policy settings, first create a DFCI profile and assign it to the Azure AD security group that contains your target devices.</span></span>

1. <span data-ttu-id="81605-150">在 devicemanagement.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="81605-150">Sign into your tenant at  devicemanagement.microsoft.com.</span></span>
2. <span data-ttu-id="81605-151">在 Microsoft 终结点管理器管理中心，选择 **">配置文件">并** 输入名称;例如 **，DFCI 配置策略。**</span><span class="sxs-lookup"><span data-stu-id="81605-151">In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile** and enter a name; for example, **DFCI Configuration Policy.**</span></span>
3. <span data-ttu-id="81605-152">选择 **Windows 10 和更高版本以** 获取平台类型。</span><span class="sxs-lookup"><span data-stu-id="81605-152">Select **Windows 10 and later** for platform type.</span></span>
4. <span data-ttu-id="81605-153">在配置文件类型下拉列表中， **选择"设备固件配置** 接口"以打开包含所有可用策略设置的 DFCI 蓝色。</span><span class="sxs-lookup"><span data-stu-id="81605-153">In the Profile type drop down list, select **Device Firmware Configuration Interface** to open the DFCI blade containing all available policy settings.</span></span> <span data-ttu-id="81605-154">有关 DFCI 设置的信息，请参阅此页面中的"表格 1"或 ["Intune"文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="81605-154">For information on DFCI settings, refer to Table 1 on this page or the [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span> <span data-ttu-id="81605-155">您可以在初始设置过程中或编辑 DFCI 配置文件，在初始设置过程中或更高版本中配置 DFCI 设置。</span><span class="sxs-lookup"><span data-stu-id="81605-155">You can configure DFCI settings during the initial setup process or later by editing the DFCI profile.</span></span>

    ![创建 DFCI 配置文件](images/df1.png)

5. <span data-ttu-id="81605-157">单击" **确定** "，然后选择" **创建**"。</span><span class="sxs-lookup"><span data-stu-id="81605-157">Click **OK** and then select **Create**.</span></span>
6. <span data-ttu-id="81605-158">选择 **"选择组"，** 在 **"选择组"** 下加入包含目标设备的 Azure AD 安全组，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="81605-158">Select **Assignments** and under **Select groups to include** select the Azure AD security group that contains your target devices, as shown in the following figure.</span></span> <span data-ttu-id="81605-159">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="81605-159">Click **Save**.</span></span>

    ![分配安全组](images/df2a.png)

## <span data-ttu-id="81605-161">创建 Autopilot 配置文件</span><span class="sxs-lookup"><span data-stu-id="81605-161">Create Autopilot profile</span></span>

1. <span data-ttu-id="81605-162">在支持"配置文件devicemanagement.microsoft.com的 **终结点管理 >器，然后** 滚动到 **部署配置文件**。</span><span class="sxs-lookup"><span data-stu-id="81605-162">In Endpoint Manager at  devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles**.</span></span>
2. <span data-ttu-id="81605-163">选择 **"创建配置** 文件"并输入名称;例如"我的 **自动化配置文件"，** 然后选择"下一 **步**"。</span><span class="sxs-lookup"><span data-stu-id="81605-163">Select **Create profile** and enter a name; for example, **My Autopilot profile**, and select **Next**.</span></span>
3. <span data-ttu-id="81605-164">选择以下设置：</span><span class="sxs-lookup"><span data-stu-id="81605-164">Select the following settings:</span></span>

    - <span data-ttu-id="81605-165">部署模式：**用户驱动。**</span><span class="sxs-lookup"><span data-stu-id="81605-165">Deployment mode: **User-Driven**.</span></span>
    - <span data-ttu-id="81605-166">加入类型：Azure **AD 加入**。</span><span class="sxs-lookup"><span data-stu-id="81605-166">Join type: Azure **AD joined**.</span></span>

4. <span data-ttu-id="81605-167">使其余的默认设置保持不变，然后选择 **"下**一步"，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="81605-167">Leave the remaining default settings unchanged and select **Next**, as shown in the following figure.</span></span>

    ![创建 Autopilot 配置文件](images/df3b.png)

5. <span data-ttu-id="81605-169">在"作业"页面上，选择 **"选择要包括的组"，** 并单击 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="81605-169">On the Assignments page, choose **Select groups to include** and click your Azure AD security group.</span></span> <span data-ttu-id="81605-170">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="81605-170">Select **Next**.</span></span>
6. <span data-ttu-id="81605-171">接受摘要，然后选择" **创建**"。</span><span class="sxs-lookup"><span data-stu-id="81605-171">Accept the summary and then select **Create**.</span></span> <span data-ttu-id="81605-172">现已创建 Autopilot 配置文件并将其分配给组。</span><span class="sxs-lookup"><span data-stu-id="81605-172">The Autopilot profile is now created and assigned to the group.</span></span>

## <span data-ttu-id="81605-173">"配置注册状态"页面</span><span class="sxs-lookup"><span data-stu-id="81605-173">Configure Enrollment Status Page</span></span>

<span data-ttu-id="81605-174">若要确保设备在用户登录之前在 OOBE 期间应用 DFCI 配置，您需要配置注册状态。</span><span class="sxs-lookup"><span data-stu-id="81605-174">To ensure that devices apply the DFCI configuration during OOBE before users sign in, you need to configure enrollment status.</span></span>

<span data-ttu-id="81605-175">有关详细信息，请参 [考"设置合约状态"页面](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="81605-175">For more information, refer to [Set up an enrollment status page](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).</span></span>


## <span data-ttu-id="81605-176">在 Surface 设备上配置 DFCI 设置</span><span class="sxs-lookup"><span data-stu-id="81605-176">Configure DFCI settings on Surface devices</span></span>

<span data-ttu-id="81605-177">DFCI 包含一组简化的 UEFI 配置策略，它们通过在硬件级别锁定设备来提供额外级别的安全性。</span><span class="sxs-lookup"><span data-stu-id="81605-177">DFCI includes a streamlined set of UEFI configuration policies that provide an extra level of security by locking down devices at the hardware level.</span></span> <span data-ttu-id="81605-178">DFCI 设计为与软件级别的移动设备管理设置配合使用。</span><span class="sxs-lookup"><span data-stu-id="81605-178">DFCI is designed to be used in conjunction with mobile device management settings at the software level.</span></span> <span data-ttu-id="81605-179">请注意，DFCI 设置仅影响内置于 Surface 设备的硬件组件，并且不超过连接外围设备，例如 USB 摄像头。</span><span class="sxs-lookup"><span data-stu-id="81605-179">Note that DFCI settings only affect hardware components built into Surface devices and do not extend to attached peripherals such as USB webcams.</span></span> <span data-ttu-id="81605-180"> (，您可以在 Intune 中使用设备限制策略关闭对软件级别设置的附加外围设备) 。</span><span class="sxs-lookup"><span data-stu-id="81605-180">(However, you can use Device restriction policies in Intune to turn off access to attached peripherals at the software level).</span></span>

<span data-ttu-id="81605-181">通过从终结点管理器编辑 DFCI 配置文件来配置 DFCI 策略设置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="81605-181">You configure DFCI policy settings by editing the DFCI profile from Endpoint Manager, as shown in the figure below.</span></span> 

- <span data-ttu-id="81605-182">在支持的终结devicemanagement.microsoft.com"终 **结点管理器">，> >"配置文件>"DFCI 配置文件名称"> >设置**。</span><span class="sxs-lookup"><span data-stu-id="81605-182">In Endpoint Manager at  devicemanagement.microsoft.com, select **Devices > Windows > Configuration Profiles > “DFCI profile name” > Properties > Settings**.</span></span>

    ![配置 DFCI 设置](images/dfciconfig.png)

### <span data-ttu-id="81605-184">阻止用户访问 UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="81605-184">Block user access to UEFI settings</span></span>

<span data-ttu-id="81605-185">对于许多客户而，阻止用户更改 UEFI 设置这一功能是非常重要的，这是使用 DFCI 的主要理由。</span><span class="sxs-lookup"><span data-stu-id="81605-185">For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI.</span></span> <span data-ttu-id="81605-186">如表 1 所示，通过设置"允许本地用户更改 **UEFI 设置"来进行管理**。</span><span class="sxs-lookup"><span data-stu-id="81605-186">As listed in Table 1, this is managed via the setting **Allow local user to change UEFI settings**.</span></span> <span data-ttu-id="81605-187">如果不编辑或配置此设置，本地用户将不能更改 Intune 未管理的任何 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="81605-187">If you do not edit or configure this setting, local users will be able to change any UEFI setting not managed by Intune.</span></span> <span data-ttu-id="81605-188">因此，强烈建议禁用"允许本地用户更改 **UEFI 设置"。**</span><span class="sxs-lookup"><span data-stu-id="81605-188">Therefore, it’s highly recommended to disable **Allow local user to change UEFI settings.**</span></span>
<span data-ttu-id="81605-189">使用 DFCI 设置，你可以关闭用户对其可用的功能。</span><span class="sxs-lookup"><span data-stu-id="81605-189">The rest of the DFCI settings enable you to turn off functionality that would otherwise be available to users.</span></span> <span data-ttu-id="81605-190">例如，如果需要在高度安全区域保护敏感信息，可禁用相机，如果不希望用户在 USB 驱动器的脚本中进行登录，也可以禁用该文件。</span><span class="sxs-lookup"><span data-stu-id="81605-190">For example, if you need to protect sensitive information in highly secure areas, you can disable the camera, and if you don’t want users booting from USB drives, you can disable that also.</span></span>

### <span data-ttu-id="81605-191">表 1. </span><span class="sxs-lookup"><span data-stu-id="81605-191">Table 1.</span></span> <span data-ttu-id="81605-192">DFCI 方案</span><span class="sxs-lookup"><span data-stu-id="81605-192">DFCI scenarios</span></span>

| <span data-ttu-id="81605-193">设备管理目标</span><span class="sxs-lookup"><span data-stu-id="81605-193">Device management goal</span></span>                        | <span data-ttu-id="81605-194">配置步骤</span><span class="sxs-lookup"><span data-stu-id="81605-194">Configuration steps</span></span>                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="81605-195">阻止本地用户更改 UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="81605-195">Block local users from changing UEFI settings</span></span> | <span data-ttu-id="81605-196">在 **"安全性>允许本地用户更改 UEFI 设置，** 选择 **"无**"。</span><span class="sxs-lookup"><span data-stu-id="81605-196">Under **Security Features > Allow local user to change UEFI settings**, select **None**.</span></span>              |
| <span data-ttu-id="81605-197">禁用相机</span><span class="sxs-lookup"><span data-stu-id="81605-197">Disable cameras</span></span>                               | <span data-ttu-id="81605-198">在 **"硬件内置>内置"下，** 选择" **已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="81605-198">Under **Built in Hardware > Cameras**, select **Disabled**.</span></span>                                       |
| <span data-ttu-id="81605-199">禁用麦克风和扬声器</span><span class="sxs-lookup"><span data-stu-id="81605-199">Disable Microphones and speakers</span></span>              | <span data-ttu-id="81605-200">在 **"麦克风和扬>器"** 下，选择"已 **禁用**"。</span><span class="sxs-lookup"><span data-stu-id="81605-200">Under **Built in Hardware > Microphones and speakers**, select **Disabled**.</span></span>                      |
| <span data-ttu-id="81605-201">禁用使用 WLAN 网络 (Bluetooth的无线) </span><span class="sxs-lookup"><span data-stu-id="81605-201">Disable radios (Bluetooth, Wi-Fi)</span></span>             | <span data-ttu-id="81605-202">在 \*\*硬件（> 无波版和 Wi-) Fi (Bluetooth 等 \*\*）下，选择" **已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="81605-202">Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc…)**, select **Disabled**.</span></span>                   |
| <span data-ttu-id="81605-203">从 USB、 S) D 函数通过外部 (开</span><span class="sxs-lookup"><span data-stu-id="81605-203">Disable Boot from external media (USB, SD)</span></span>    | <span data-ttu-id="81605-204">在 \*\*"内置硬件>支持"自动 > UOot（来自 USB (SD）的) \*\*按" **已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="81605-204">Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**.</span></span> |

> [!CAUTION]
> <span data-ttu-id="81605-205">" \*\*禁用 wi- (Bluetooth，"Wi-Fi) " \*\* 设置只能在具有有线以太网连接的设备上使用。</span><span class="sxs-lookup"><span data-stu-id="81605-205">The **Disable radios (Bluetooth, Wi-Fi)** setting should only be used on devices that have a wired Ethernet connection.</span></span>
 
> [!NOTE]
>  <span data-ttu-id="81605-206">Intune 中的 DFCI 包含两个当前不适用于 Surface 设备的设置： (1) CPU 和 IO 虚拟化， (2) 禁用来自网络适配器的 Boot。</span><span class="sxs-lookup"><span data-stu-id="81605-206">DFCI in Intune includes two settings that do not currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.</span></span>
 
<span data-ttu-id="81605-207">Intune 提供代理管理权限和适用性规则来管理设备类型的范围标记。</span><span class="sxs-lookup"><span data-stu-id="81605-207">Intune provides Scope tags to delegate administrative rights and Applicability Rules to manage device types.</span></span> <span data-ttu-id="81605-208">有关所有 DFCI 设置的策略管理支持和完整详细信息，请参阅 [Microsoft Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="81605-208">For more information about policy management support and full details on all DFCI settings, refer to [Microsoft Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span>

## <span data-ttu-id="81605-209">在 Autopilot 中注册设备</span><span class="sxs-lookup"><span data-stu-id="81605-209">Register devices in Autopilot</span></span>

<span data-ttu-id="81605-210">如上所述，DFCI 只能应用于经销商或分销商在 Windows Autopilot 中注册的设备，且仅在 Surface Pro 7、Surface Pro X 和 Surface 笔记本电脑 3 上受支持。</span><span class="sxs-lookup"><span data-stu-id="81605-210">As stated above, DFCI can only be applied on devices registered in Windows Autopilot by your reseller or distributor and is only supported, at this time, on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="81605-211">出于安全原因，不能将设备"自行设置"设备"连接到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="81605-211">For security reasons, it’s not possible to “self-provision” your devices into Autopilot.</span></span>

## <span data-ttu-id="81605-212">手动同步自动设备</span><span class="sxs-lookup"><span data-stu-id="81605-212">Manually Sync Autopilot devices</span></span>

<span data-ttu-id="81605-213">尽管 Intune 策略设置通常几乎立即应用，但是设置可能在目标设备上生效之前 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="81605-213">Although Intune policy settings typically get applied almost immediately, there may be a delay of 10 minutes before the settings take effect on targeted devices.</span></span> <span data-ttu-id="81605-214">在少数情况下，最多可以延迟 8 小时。</span><span class="sxs-lookup"><span data-stu-id="81605-214">In rare circumstances, delays of up to 8 hours are possible.</span></span> <span data-ttu-id="81605-215">要确保尽快应用设置（ (在测试方案) ），可以手动同步目标设备。</span><span class="sxs-lookup"><span data-stu-id="81605-215">To ensure settings apply as soon as possible, (such as in test scenarios), you can manually sync the target devices.</span></span>

- <span data-ttu-id="81605-216">在支持的 devicemanagement.microsoft.com 端点管理器中，转到 **Windows > > 注册窗口 Windows >注册** 的设备，然后选择" **同步**"。</span><span class="sxs-lookup"><span data-stu-id="81605-216">In Endpoint Manager at  devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync**.</span></span>

 <span data-ttu-id="81605-217">有关详细信息，请参阅 [手动同步 Windows 设备](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。</span><span class="sxs-lookup"><span data-stu-id="81605-217">For more information, refer to [Sync your Windows device manually](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).</span></span>

> [!NOTE]
> <span data-ttu-id="81605-218">当直接在 UEFI 中调整设置时，你需要确保设备完全重启到标准 Windows 登录。</span><span class="sxs-lookup"><span data-stu-id="81605-218">When adjusting settings directly in UEFI, you need to ensure the device fully restarts to the standard Windows login.</span></span>

## <span data-ttu-id="81605-219">验证 DFCI 托管设备上的 UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="81605-219">Verifying UEFI settings on DFCI-managed devices</span></span>

<span data-ttu-id="81605-220">在测试环境中，你可以在 Surface UEFI 接口中验证设置。</span><span class="sxs-lookup"><span data-stu-id="81605-220">In a test environment, you can verify settings in the Surface UEFI interface.</span></span>

1. <span data-ttu-id="81605-221">打开 Surface UEFI，它同时涉及同时按 **高源 +** 和 **电** 源按钮。</span><span class="sxs-lookup"><span data-stu-id="81605-221">Open Surface UEFI, which involves pressing the **Volume +** and **Power** buttons at the same time.</span></span>
2. <span data-ttu-id="81605-222">选择 **"设备**"。</span><span class="sxs-lookup"><span data-stu-id="81605-222">Select **Devices**.</span></span> <span data-ttu-id="81605-223">UEFI 菜单将反映已配置设置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="81605-223">The UEFI menu will reflect configured settings, as shown in the following figure.</span></span>

    ![Surface UEFI](images/df3.png)

    <span data-ttu-id="81605-225">请注意方法：</span><span class="sxs-lookup"><span data-stu-id="81605-225">Note how:</span></span>

      - <span data-ttu-id="81605-226">设置显示为"允许本地用户更改 **UEFI"** 设置是"无"。</span><span class="sxs-lookup"><span data-stu-id="81605-226">The settings are greyed out because **Allow local user to change UEFI setting** is set to None.</span></span>
      - <span data-ttu-id="81605-227">音频设置为"已关闭 **"，因为"麦克风和扬声** 器"已设置为 **"已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="81605-227">Audio is set to off because **Microphones and speakers** are set to **Disabled**.</span></span>

## <span data-ttu-id="81605-228">删除 DFCI 策略设置</span><span class="sxs-lookup"><span data-stu-id="81605-228">Removing DFCI policy settings</span></span>

<span data-ttu-id="81605-229">创建 DFCI 配置文件时，所有已配置设置会在配置文件管理范围内的所有设备保持有效。</span><span class="sxs-lookup"><span data-stu-id="81605-229">When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile’s scope of management.</span></span> <span data-ttu-id="81605-230">只能通过直接编辑 DFCI 配置文件来删除 DFCI 策略设置。</span><span class="sxs-lookup"><span data-stu-id="81605-230">You can only remove DFCI policy settings by editing the DFCI profile directly.</span></span>

<span data-ttu-id="81605-231">如果原始 DFCI 配置文件已被删除，可以通过创建新的配置文件，然后对其进行编辑设置来删除策略设置。</span><span class="sxs-lookup"><span data-stu-id="81605-231">If the original DFCI profile has been deleted, you can remove policy settings by creating a new profile and then editing the settings, as appropriate.</span></span>

## <span data-ttu-id="81605-232">删除 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="81605-232">Removing DFCI management</span></span>

**<span data-ttu-id="81605-233">若要删除 DFCI 管理并将设备恢复为出版新状态，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81605-233">To remove DFCI management and return device to factory new state:</span></span>**

1. <span data-ttu-id="81605-234">停用 Intune 上的设备：</span><span class="sxs-lookup"><span data-stu-id="81605-234">Retire the device from Intune:</span></span>
    1. <span data-ttu-id="81605-235">在管理"终结点devicemanagement.microsoft.com中，选择 **">"组**"。</span><span class="sxs-lookup"><span data-stu-id="81605-235">In Endpoint Manager at  devicemanagement.microsoft.com, choose **Groups > All Devices**.</span></span> <span data-ttu-id="81605-236">选择要停用的设备，然后选择" **停用/擦除"。**</span><span class="sxs-lookup"><span data-stu-id="81605-236">Select the devices you want to retire, and then choose **Retire/Wipe.**</span></span> <span data-ttu-id="81605-237">若要了解详细信息， [请参阅"删除设备"中的操作、停用设备或手动取消注册该设备](https://docs.microsoft.com/intune/remote-actions/devices-wipe)。</span><span class="sxs-lookup"><span data-stu-id="81605-237">To learn more refer to [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/remote-actions/devices-wipe).</span></span> 
2. <span data-ttu-id="81605-238">从 Intune 中删除 Autopilot 注册：</span><span class="sxs-lookup"><span data-stu-id="81605-238">Delete the Autopilot registration from Intune:</span></span>
    1.  <span data-ttu-id="81605-239">选择**设备注册窗口> >设备。**</span><span class="sxs-lookup"><span data-stu-id="81605-239">Choose **Device enrollment > Windows enrollment > Devices**.</span></span>
    2. <span data-ttu-id="81605-240">在 Windows Autopilot 设备上，选择要删除的设备，然后选择" **删除**"。</span><span class="sxs-lookup"><span data-stu-id="81605-240">Under Windows Autopilot devices, choose the devices you want to delete, and then choose **Delete**.</span></span>
3. <span data-ttu-id="81605-241">使用 Surface 品牌广告适配器将设备连接到有线 Internet。</span><span class="sxs-lookup"><span data-stu-id="81605-241">Connect device to wired internet with Surface-branded ethernet adapter.</span></span> <span data-ttu-id="81605-242">重启设备并打开 UEFI 菜单 (然后按住音量按钮，同时按下和重新放) 。</span><span class="sxs-lookup"><span data-stu-id="81605-242">Restart device and open the UEFI menu (press and hold the volume-up button while also pressing and releasing the power button).</span></span>
4. <span data-ttu-id="81605-243">从 **网络>"> 中选择"配置管理器，** 然后选择 **"选择退出"。**</span><span class="sxs-lookup"><span data-stu-id="81605-243">Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**</span></span>

<span data-ttu-id="81605-244">若要使用 Intune 管理设备，但不使用 DFCI 管理，将设备注册为 Autopilot，并将其注册到 Intune。</span><span class="sxs-lookup"><span data-stu-id="81605-244">To keep managing the device with Intune, but without DFCI management, self-register the device to Autopilot and enroll it to Intune.</span></span> <span data-ttu-id="81605-245">DFCI 将不适用于自行注册的设备。</span><span class="sxs-lookup"><span data-stu-id="81605-245">DFCI will not be applied to self-registered devices.</span></span>

## <span data-ttu-id="81605-246">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="81605-246">Learn more</span></span>
- <span data-ttu-id="81605-247">[Ignite 2019：从 Intune 通知远程管理 Surface UEFI 设置](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="81605-247">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span></span>
- [<span data-ttu-id="81605-248">Windows Autopilot 和 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="81605-248">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md) 
- [<span data-ttu-id="81605-249">在 Microsoft Intune 的 Windows 设备上使用 DFCI 配置文件</span><span class="sxs-lookup"><span data-stu-id="81605-249">Use DFCI profiles on Windows devices in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

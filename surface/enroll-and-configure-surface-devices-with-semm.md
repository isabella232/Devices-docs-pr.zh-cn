---
title: 通过 SEMM （Surface）注册和配置 Surface 设备
description: 了解如何创建 Surface UEFI 配置包以控制 Surface UEFI 的设置，以及在 SEMM 中注册 Surface 设备。
keywords: surface 企业管理
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 183eceee47eba8b8d1e794e9e7d3efffa7a9b2e0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831703"
---
# <span data-ttu-id="8acb3-104">使用 SEMM 注册并配置 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="8acb3-104">Enroll and configure Surface devices with SEMM</span></span>

<span data-ttu-id="8acb3-105">使用 Microsoft Surface Enterprise 管理模式（SEMM），你可以安全地在 Surface 设备上配置 Surface UEFI 的设置，并在你的组织中的 Surface 设备上管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="8acb3-105">With Microsoft Surface Enterprise Management Mode (SEMM), you can securely configure the settings of Surface UEFI on a Surface device and manage those settings on Surface devices in your organization.</span></span> <span data-ttu-id="8acb3-106">当 Surface 设备由 SEMM 管理时，该设备将被视为已*注册*（有时称为已激活）。</span><span class="sxs-lookup"><span data-stu-id="8acb3-106">When a Surface device is managed by SEMM, that device is considered to be *enrolled* (sometimes referred to as activated).</span></span> <span data-ttu-id="8acb3-107">本文介绍如何创建一个 Surface UEFI 配置包，该程序包不仅可以控制 Surface UEFI 的设置，还会在 SEMM 中注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="8acb3-107">This article shows you how to create a Surface UEFI configuration package that will not only control the settings of Surface UEFI, but will also enroll a Surface device in SEMM.</span></span>

<span data-ttu-id="8acb3-108">有关 SEMM 的更高级别概述，请参阅[Microsoft Surface 企业管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="8acb3-108">For a more high-level overview of SEMM, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

<span data-ttu-id="8acb3-109">管理 Surface Pro X 和 Surface 笔记本电脑3上的云中的固件的一种简化方法现在可通过公共预览版获得。</span><span class="sxs-lookup"><span data-stu-id="8acb3-109">A streamlined method of managing firmware from the cloud on Surface Pro 7,Surface Pro X and Surface Laptop 3 is now available via public preview.</span></span> <span data-ttu-id="8acb3-110">有关详细信息，请参阅[SURFACE UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="8acb3-110">For more information,refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8acb3-111">SEMM 仅通过 UEFI 管理器在 Surface Pro X 上受支持。</span><span class="sxs-lookup"><span data-stu-id="8acb3-111">SEMM is supported on Surface Pro X via the UEFI Manager only.</span></span> <span data-ttu-id="8acb3-112">有关详细信息，请参阅[部署、管理和维护 Surface Pro X](surface-pro-arm-app-management.md)。</span><span class="sxs-lookup"><span data-stu-id="8acb3-112">For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>

#### <span data-ttu-id="8acb3-113">下载并安装 Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="8acb3-113">Download and install Microsoft Surface UEFI Configurator</span></span>
<span data-ttu-id="8acb3-114">用于创建 SEMM 程序包的工具是 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="8acb3-114">The tool used to create SEMM packages is Microsoft Surface UEFI Configurator.</span></span> <span data-ttu-id="8acb3-115">你可以从 Microsoft 下载中心的[IT "Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) " 页面下载 MICROSOFT Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="8acb3-115">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>
<span data-ttu-id="8acb3-116">运行 Microsoft Surface UEFI 配置器 Windows Installer （.msi）文件以启动该工具的安装。</span><span class="sxs-lookup"><span data-stu-id="8acb3-116">Run the Microsoft Surface UEFI Configurator Windows Installer (.msi) file to start the installation of the tool.</span></span> <span data-ttu-id="8acb3-117">安装程序完成后，在 "开始" 菜单的 "所有应用" 部分中查找 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="8acb3-117">When the installer completes, find Microsoft Surface UEFI Configurator in the All Apps section of your Start menu.</span></span>

>[!NOTE]
><span data-ttu-id="8acb3-118">仅在 Windows 10 上支持 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="8acb3-118">Microsoft Surface UEFI Configurator is supported only on Windows 10.</span></span>

## <span data-ttu-id="8acb3-119">创建 Surface UEFI 配置包</span><span class="sxs-lookup"><span data-stu-id="8acb3-119">Create a Surface UEFI configuration package</span></span>

<span data-ttu-id="8acb3-120">Surface UEFI 配置包执行将 Surface UEFI 设置的新配置应用到使用 SEMM 管理的 Surface 设备和 SEMM 中注册 Surface 设备的角色的角色。</span><span class="sxs-lookup"><span data-stu-id="8acb3-120">The Surface UEFI configuration package performs both the role of applying a new configuration of Surface UEFI settings to a Surface device managed with SEMM and the role of enrolling Surface devices in SEMM.</span></span> <span data-ttu-id="8acb3-121">创建配置程序包要求你拥有与 SEMM 一起使用的签名证书，以确保每个 Surface 设备上的 UEFI 设置的配置安全。</span><span class="sxs-lookup"><span data-stu-id="8acb3-121">The creation of a configuration package requires you to have a signing certificate to be used with SEMM to secure the configuration of UEFI settings on each Surface device.</span></span> <span data-ttu-id="8acb3-122">有关 SEMM 证书的要求的详细信息，请参阅[Microsoft Surface 企业管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="8acb3-122">For more information about the requirements for the SEMM certificate, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

<span data-ttu-id="8acb3-123">若要创建 Surface UEFI 配置包，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8acb3-123">To create a Surface UEFI configuration package, follow these steps:</span></span>

1. <span data-ttu-id="8acb3-124">从 "开始" 菜单打开 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="8acb3-124">Open Microsoft Surface UEFI Configurator from the Start menu.</span></span>
2. <span data-ttu-id="8acb3-125">单击**开始**。</span><span class="sxs-lookup"><span data-stu-id="8acb3-125">Click **Start**.</span></span>
3. <span data-ttu-id="8acb3-126">单击 "**配置包**"，如图1所示。</span><span class="sxs-lookup"><span data-stu-id="8acb3-126">Click **Configuration Package**, as shown in Figure 1.</span></span>

   ![为 SEMM 注册创建程序包](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *<span data-ttu-id="8acb3-128">图 1.</span><span class="sxs-lookup"><span data-stu-id="8acb3-128">Figure 1.</span></span> <span data-ttu-id="8acb3-129">选择 "配置包" 以创建 SEMM 注册和配置的程序包</span><span class="sxs-lookup"><span data-stu-id="8acb3-129">Select Configuration Package to create a package for SEMM enrollment and configuration</span></span>*

4. <span data-ttu-id="8acb3-130">单击 "**证书保护**" 以添加导出的带有私钥（.pfx）的证书文件，如图2所示。</span><span class="sxs-lookup"><span data-stu-id="8acb3-130">Click **Certificate Protection** to add your exported certificate file with private key (.pfx), as shown in Figure 2.</span></span> <span data-ttu-id="8acb3-131">通过浏览找到您的证书文件的位置，选择该文件，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8acb3-131">Browse to the location of your certificate file, select the file, and then click **OK**.</span></span>

   ![将 SEM 证书和 Surface UEFI 密码添加到配置包](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *<span data-ttu-id="8acb3-133">图 2.</span><span class="sxs-lookup"><span data-stu-id="8acb3-133">Figure 2.</span></span> <span data-ttu-id="8acb3-134">将 SEMM 证书和 Surface UEFI 密码添加到 Surface UEFI 配置包</span><span class="sxs-lookup"><span data-stu-id="8acb3-134">Add the SEMM certificate and Surface UEFI password to a Surface UEFI configuration package</span></span>*

5. <span data-ttu-id="8acb3-135">当系统提示您确认证书密码时，请输入并确认您的证书文件的密码，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8acb3-135">When you are prompted to confirm the certificate password, enter and confirm the password for your certificate file, and then click **OK**.</span></span>
6. <span data-ttu-id="8acb3-136">单击 "**密码保护**" 以将密码添加到 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="8acb3-136">Click **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="8acb3-137">当您启动到 UEFI 时，将需要此密码。</span><span class="sxs-lookup"><span data-stu-id="8acb3-137">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="8acb3-138">如果未输入此密码，则仅显示**电脑信息**、 **"\*\*\*\*企业管理**" 和 "**退出**页面"。</span><span class="sxs-lookup"><span data-stu-id="8acb3-138">If this password is not entered, only the **PC information**, **About**, **Enterprise management**, and **Exit** pages will be displayed.</span></span> <span data-ttu-id="8acb3-139">此步骤可选。</span><span class="sxs-lookup"><span data-stu-id="8acb3-139">This step is optional.</span></span>
7. <span data-ttu-id="8acb3-140">出现提示时，请输入并确认你为 Surface UEFI 选择的密码，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8acb3-140">When you are prompted, enter and confirm your chosen password for Surface UEFI, and then click **OK**.</span></span> <span data-ttu-id="8acb3-141">如果要清除现有 Surface UEFI 密码，请将 "密码" 字段保留为空。</span><span class="sxs-lookup"><span data-stu-id="8acb3-141">If you want to clear an existing Surface UEFI password, leave the password field blank.</span></span>
8. <span data-ttu-id="8acb3-142">如果不希望将 Surface UEFI 包应用于特定设备，请在 "**选择要确定的目标图面类型**" 页面上，单击相应 surface Book 或 Surface Pro 4 图像下方的滑块，使其位于 "**关**" 位置。</span><span class="sxs-lookup"><span data-stu-id="8acb3-142">If you do not want the Surface UEFI package to apply to a particular device, on the **Choose which Surface type you want to target** page, click the slider beneath the corresponding Surface Book or Surface Pro 4 image so that it is in the **Off** position.</span></span> <span data-ttu-id="8acb3-143">（如图3所示。）</span><span class="sxs-lookup"><span data-stu-id="8acb3-143">(As shown in Figure 3.)</span></span>
   > [!NOTE] 
   > <span data-ttu-id="8acb3-144">默认情况下，选择 "无"，则必须选择设备。</span><span class="sxs-lookup"><span data-stu-id="8acb3-144">You must select a device as none are selected by default.</span></span>

   ![为程序包兼容性选择设备](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *<span data-ttu-id="8acb3-146">图 3.</span><span class="sxs-lookup"><span data-stu-id="8acb3-146">Figure 3.</span></span> <span data-ttu-id="8acb3-147">选择用于程序包兼容性的设备</span><span class="sxs-lookup"><span data-stu-id="8acb3-147">Choose the devices for package compatibility</span></span>*

9. <span data-ttu-id="8acb3-148">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8acb3-148">Click **Next**.</span></span>
10. <span data-ttu-id="8acb3-149">如果要停用托管 Surface 设备上的组件，请在 "**选择要激活或停用的组件**" 页面上，单击要停用的任何设备或设备组旁边的滑块，以使滑块位于**关闭**位置。</span><span class="sxs-lookup"><span data-stu-id="8acb3-149">If you want to deactivate a component on managed Surface devices, on the **Choose which components you want to activate or deactivate** page, click the slider next to any device or group of devices you want to deactivate so that the slider is in the **Off** position.</span></span> <span data-ttu-id="8acb3-150">（如图4所示。）每个设备的默认配置均为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="8acb3-150">(Shown in Figure 4.) The default configuration for each device is **On**.</span></span> <span data-ttu-id="8acb3-151">如果要将所有滑块恢复到默认位置，请单击 "**重置**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="8acb3-151">Click the **Reset** button if you want to return all sliders to the default position.</span></span>

    ![禁用或启用 Surface 组件](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *<span data-ttu-id="8acb3-153">图 4.</span><span class="sxs-lookup"><span data-stu-id="8acb3-153">Figure 4.</span></span> <span data-ttu-id="8acb3-154">禁用或启用单个 Surface 组件</span><span class="sxs-lookup"><span data-stu-id="8acb3-154">Disable or enable individual Surface components</span></span>*

11. <span data-ttu-id="8acb3-155">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8acb3-155">Click **Next**.</span></span>
12. <span data-ttu-id="8acb3-156">若要在 Surface UEFI 或 Surface UEFI 页面的显示中启用或禁用高级选项，请在 "**选择设备的高级设置**" 页面上，单击所需设置旁边的滑块以将该选项配置为 **"打开" 或 "** **关闭**" （如图5所示）。</span><span class="sxs-lookup"><span data-stu-id="8acb3-156">To enable or disable advanced options in Surface UEFI or the display of Surface UEFI pages, on the **Choose the advanced settings for your devices** page, click the slider beside the desired setting to configure that option to **On** or **Off** (shown in Figure 5).</span></span> <span data-ttu-id="8acb3-157">在 " **UEFI 前页**" 部分中，你可以使用 "**安全**"、"**设备**" 和 "**启动**" 滑块来控制启动到 Surface UEFI 的用户可以使用哪些页面。</span><span class="sxs-lookup"><span data-stu-id="8acb3-157">In the **UEFI Front Page** section, you can use the sliders for **Security**, **Devices**, and **Boot** to control what pages are available to users who boot into Surface UEFI.</span></span> <span data-ttu-id="8acb3-158">（有关 Surface UEFI 设置的详细信息，请参阅[管理 SURFACE uefi 设置](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)。）完成选择生成和保存程序包的选项后，单击 "**生成**"。</span><span class="sxs-lookup"><span data-stu-id="8acb3-158">(For more information about Surface UEFI settings, see [Manage Surface UEFI settings](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).) Click **Build** when you have finished selecting options to generate and save the package.</span></span>

    ![控制高级 Surface UEFI 设置和 Surface UEFI 页面](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *<span data-ttu-id="8acb3-160">图 5.</span><span class="sxs-lookup"><span data-stu-id="8acb3-160">Figure 5.</span></span> <span data-ttu-id="8acb3-161">通过 SEMM 控制高级 Surface UEFI 设置和 Surface UEFI 页面</span><span class="sxs-lookup"><span data-stu-id="8acb3-161">Control advanced Surface UEFI settings and Surface UEFI pages with SEMM</span></span>*

13. <span data-ttu-id="8acb3-162">在 "**另存为**" 对话框中，指定 Surface UEFI 配置包的名称，浏览到要保存文件的位置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="8acb3-162">In the **Save As** dialog box, specify a name for the Surface UEFI configuration package, browse to the location where you would like to save the file, and then click **Save**.</span></span>
14. <span data-ttu-id="8acb3-163">创建并保存程序包后，将显示**成功**的页面。</span><span class="sxs-lookup"><span data-stu-id="8acb3-163">When the package is created and saved, the **Successful** page is displayed.</span></span>

>[!NOTE]
><span data-ttu-id="8acb3-164">记录此页面上显示的证书指纹字符，如图6所示。</span><span class="sxs-lookup"><span data-stu-id="8acb3-164">Record the certificate thumbprint characters that are displayed on this page, as shown in Figure 6.</span></span> <span data-ttu-id="8acb3-165">你将需要这些字符来确认在 SEMM 中注册新的 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="8acb3-165">You will need these characters to confirm enrollment of new Surface devices in SEMM.</span></span> <span data-ttu-id="8acb3-166">单击 "**结束**" 以完成程序包创建并关闭 MICROSOFT Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="8acb3-166">Click **End** to complete package creation and close Microsoft Surface UEFI Configurator.</span></span>

![证书指纹字符的显示](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*<span data-ttu-id="8acb3-168">图 6.</span><span class="sxs-lookup"><span data-stu-id="8acb3-168">Figure 6.</span></span> <span data-ttu-id="8acb3-169">证书指纹的最后两个字符显示在成功的页面上</span><span class="sxs-lookup"><span data-stu-id="8acb3-169">The last two characters of the certificate thumbprint are displayed on the Successful page</span></span>*

<span data-ttu-id="8acb3-170">现在，你已创建 Surface UEFI 配置包，你可以注册或配置 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="8acb3-170">Now that you have created your Surface UEFI configuration package, you can enroll or configure Surface devices.</span></span>

>[!NOTE]
><span data-ttu-id="8acb3-171">创建 Surface UEFI 配置包时，将在桌面上创建日志文件，其中包含配置程序包设置和选项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8acb3-171">When a Surface UEFI configuration package is created, a log file is created on the desktop with details of the configuration package settings and options.</span></span>

## <span data-ttu-id="8acb3-172">在 SEMM 中注册 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="8acb3-172">Enroll a Surface device in SEMM</span></span>
<span data-ttu-id="8acb3-173">当执行 Surface UEFI 配置包时，SEMM 证书和 Surface UEFI 配置文件将暂存在 Surface 设备的固件存储中。</span><span class="sxs-lookup"><span data-stu-id="8acb3-173">When the Surface UEFI configuration package is executed, the SEMM certificate and Surface UEFI configuration files are staged in the firmware storage of the Surface device.</span></span> <span data-ttu-id="8acb3-174">当 Surface 设备重新启动时，Surface UEFI 处理这些文件，并开始在 SEMM 中应用 Surface UEFI 配置或注册 Surface 设备的过程，如图7所示。</span><span class="sxs-lookup"><span data-stu-id="8acb3-174">When the Surface device reboots, Surface UEFI processes these files and begins the process of applying the Surface UEFI configuration or enrolling the Surface device in SEMM, as shown in Figure 7.</span></span>

![用于 Surface UEFI 或注册配置的 SEMM 过程](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*<span data-ttu-id="8acb3-176">图 7.</span><span class="sxs-lookup"><span data-stu-id="8acb3-176">Figure 7.</span></span> <span data-ttu-id="8acb3-177">用于配置 Surface UEFI 或注册 Surface 设备的 SEMM 过程</span><span class="sxs-lookup"><span data-stu-id="8acb3-177">The SEMM process for configuration of Surface UEFI or enrollment of a Surface device</span></span>*

<span data-ttu-id="8acb3-178">开始在 SEMM 中注册 Surface 设备之前，请确保你有证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="8acb3-178">Before you begin the process to enroll a Surface device in SEMM, ensure that you have the last two characters of the certificate thumbprint on hand.</span></span> <span data-ttu-id="8acb3-179">你将需要这些字符来确认设备的注册（请参阅图6）。</span><span class="sxs-lookup"><span data-stu-id="8acb3-179">You will need these characters to confirm the device’s enrollment (see Figure 6).</span></span>

<span data-ttu-id="8acb3-180">若要使用 Surface UEFI 配置包在 SEMM 中注册 Surface 设备，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8acb3-180">To enroll a Surface device in SEMM with a Surface UEFI configuration package, follow these steps:</span></span>

1. <span data-ttu-id="8acb3-181">在要在 SEMM 中注册的 Surface 设备上运行 Surface UEFI 配置程序包 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="8acb3-181">Run the Surface UEFI configuration package .msi file on the Surface device you want to enroll in SEMM.</span></span> <span data-ttu-id="8acb3-182">这将在设备固件中设置 Surface UEFI 配置文件。</span><span class="sxs-lookup"><span data-stu-id="8acb3-182">This will provision the Surface UEFI configuration file in the device’s firmware.</span></span>
2. <span data-ttu-id="8acb3-183">选中 "**我接受许可协议中的条款**" 复选框以接受最终用户许可协议（EULA），然后单击 "**安装**" 以开始安装过程。</span><span class="sxs-lookup"><span data-stu-id="8acb3-183">Select the **I accept the terms in the License Agreement** check box to accept the End User License Agreement (EULA), and then click **Install** to begin the installation process.</span></span>
3. <span data-ttu-id="8acb3-184">单击 "**完成**" 以完成 surface UEFI 配置程序包安装，并在系统提示时重启 surface 设备。</span><span class="sxs-lookup"><span data-stu-id="8acb3-184">Click **Finish** to complete the Surface UEFI configuration package installation and restart the Surface device when you are prompted to do so.</span></span>
4. <span data-ttu-id="8acb3-185">Surface UEFI 将加载配置文件并确定设备上未启用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="8acb3-185">Surface UEFI will load the configuration file and determine that SEMM is not enabled on the device.</span></span> <span data-ttu-id="8acb3-186">然后，Surface UEFI 将开始 SEMM 注册过程，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8acb3-186">Surface UEFI will then begin the SEMM enrollment process, as follows:</span></span>
   * <span data-ttu-id="8acb3-187">Surface UEFI 将验证 SEMM 配置文件是否包含 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="8acb3-187">Surface UEFI will verify that the SEMM configuration file contains a SEMM certificate.</span></span>
   * <span data-ttu-id="8acb3-188">Surface UEFI 将提示你输入证书指纹的最后两个字符以确认在 SEMM 中注册 Surface 设备，如图8所示。</span><span class="sxs-lookup"><span data-stu-id="8acb3-188">Surface UEFI will prompt you to enter the last two characters of the certificate thumbprint to confirm enrollment of the Surface device in SEMM, as shown in Figure 8.</span></span>

      ![SEMM 注册需要证书指纹的最后两个字符](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *<span data-ttu-id="8acb3-190">图 8.</span><span class="sxs-lookup"><span data-stu-id="8acb3-190">Figure 8.</span></span> <span data-ttu-id="8acb3-191">SEMM 中的注册需要证书指纹的最后两个字符</span><span class="sxs-lookup"><span data-stu-id="8acb3-191">Enrollment in SEMM requires the last two characters of the certificate thumbprint</span></span>*

   * <span data-ttu-id="8acb3-192">Surface UEFI 将在固件中存储 SEMM 证书，并应用 Surface UEFI 配置文件中指定的配置设置。</span><span class="sxs-lookup"><span data-stu-id="8acb3-192">Surface UEFI will store the SEMM certificate in firmware and apply the configuration settings that are specified in the Surface UEFI configuration file.</span></span>
   
5. <span data-ttu-id="8acb3-193">Surface 设备现在已注册 SEMM 并将启动到 Windows。</span><span class="sxs-lookup"><span data-stu-id="8acb3-193">The Surface device is now enrolled in SEMM and will boot to Windows.</span></span>

<span data-ttu-id="8acb3-194">通过在 "事件查看器" 的 "**应用程序和服务日志**" 下的 "应用程序和服务日志" 下的 "应用**程序**和服务日志" 下找到的 "Microsoft surface **UEFI** **配置包**" （如图10所示），可以验证是否已在 SEMM 中成功注册了 surface 设备。</span><span class="sxs-lookup"><span data-stu-id="8acb3-194">You can verify that a Surface device has been successfully enrolled in SEMM by looking for **Microsoft Surface Configuration Package** in **Programs and Features** (as shown in Figure 9), or in the events stored in the **Microsoft Surface UEFI Configurator** log, found under **Applications and Services Logs** in Event Viewer (as shown in Figure 10).</span></span>

![验证 "程序和功能" SEMM 中的 Surface 设备注册](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*<span data-ttu-id="8acb3-196">图 9.</span><span class="sxs-lookup"><span data-stu-id="8acb3-196">Figure 9.</span></span> <span data-ttu-id="8acb3-197">验证在 SEMM 中的 "程序和功能" 中注册 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="8acb3-197">Verify the enrollment of a Surface device in SEMM in Programs and Features</span></span>*

![在事件查看器中验证 SEMM 中的 Surface 设备注册](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*<span data-ttu-id="8acb3-199">图 10.</span><span class="sxs-lookup"><span data-stu-id="8acb3-199">Figure 10.</span></span> <span data-ttu-id="8acb3-200">在事件查看器的 SEMM 中验证是否注册 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="8acb3-200">Verify the enrollment of a Surface device in SEMM in Event Viewer</span></span>*

<span data-ttu-id="8acb3-201">你还可以验证设备是否已在 SEMM 在 Surface UEFI 中注册-当设备已注册时，Surface UEFI 将包含**企业管理**页面（如图11所示）。</span><span class="sxs-lookup"><span data-stu-id="8acb3-201">You can also verify that the device is enrolled in SEMM in Surface UEFI – while the device is enrolled, Surface UEFI will contain the **Enterprise management** page (as shown in Figure 11).</span></span>

![Surface UEFI 企业版管理页面](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*<span data-ttu-id="8acb3-203">图 11.</span><span class="sxs-lookup"><span data-stu-id="8acb3-203">Figure 11.</span></span> <span data-ttu-id="8acb3-204">Surface UEFI 企业版管理页面</span><span class="sxs-lookup"><span data-stu-id="8acb3-204">The Surface UEFI Enterprise management page</span></span>*


## <span data-ttu-id="8acb3-205">通过 SEMM 配置 Surface UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="8acb3-205">Configure Surface UEFI settings with SEMM</span></span>

<span data-ttu-id="8acb3-206">在 SEMM 中注册设备后，你可以运行使用同一 SEMM 证书签名的 Surface UEFI 配置包来应用新的 Surface UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="8acb3-206">After a device is enrolled in SEMM, you can run Surface UEFI configuration packages signed with the same SEMM certificate to apply new Surface UEFI settings.</span></span> <span data-ttu-id="8acb3-207">下次启动设备时将自动应用这些设置，而不与用户进行任何交互。</span><span class="sxs-lookup"><span data-stu-id="8acb3-207">These settings are applied automatically the next time the device boots, without any interaction from the user.</span></span> <span data-ttu-id="8acb3-208">你可以使用 Microsoft 终结点配置管理器等应用程序部署解决方案将 Surface UEFI 配置包部署到 Surface 设备，以更改或管理 Surface UEFI 中的设置。</span><span class="sxs-lookup"><span data-stu-id="8acb3-208">You can use application deployment solutions like Microsoft Endpoint Configuration Manager to deploy Surface UEFI configuration packages to Surface devices to change or manage the settings in Surface UEFI.</span></span>

<span data-ttu-id="8acb3-209">有关如何通过配置管理器部署 Windows Installer （.msi）文件的详细信息，请参阅[通过 Microsoft 终结点配置管理器部署和管理应用程序](https://technet.microsoft.com/library/mt627959)。</span><span class="sxs-lookup"><span data-stu-id="8acb3-209">For more information about how to deploy Windows Installer (.msi) files with Configuration Manager, see [Deploy and manage applications with Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt627959).</span></span>

<span data-ttu-id="8acb3-210">如果您有安全的 Surface UEFI 和密码，则没有尝试启动到 Surface UEFI 的密码的用户将仅显示**PC 信息** **，包括 "\*\*\*\*企业管理**" 和 "**退出**页面"。</span><span class="sxs-lookup"><span data-stu-id="8acb3-210">If you have secured Surface UEFI with a password, users without the password who attempt to boot to Surface UEFI will only have the **PC information**, **About**, **Enterprise management**, and **Exit** pages displayed to them.</span></span>

<span data-ttu-id="8acb3-211">如果你没有安全的 Surface UEFI （使用密码或用户输入正确的密码），则使用 SEMM 配置的设置将灰显（不可用），并且您的组织管理某些设置的文本将显示在页面顶部，如图12所示。</span><span class="sxs-lookup"><span data-stu-id="8acb3-211">If you have not secured Surface UEFI with a password or a user enters the password correctly, settings that are configured with SEMM will be dimmed (unavailable) and the text Some settings are managed by your organization will be displayed at the top of the page, as shown in Figure 12.</span></span>

![由 SEMM 托管的设置在 Surface UEFI 中被禁用](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*<span data-ttu-id="8acb3-213">图 12.</span><span class="sxs-lookup"><span data-stu-id="8acb3-213">Figure 12.</span></span> <span data-ttu-id="8acb3-214">SEMM 托管的设置将在 Surface UEFI 中禁用</span><span class="sxs-lookup"><span data-stu-id="8acb3-214">Settings managed by SEMM will be disabled in Surface UEFI</span></span>*

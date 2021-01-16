---
title: '在 Surface 设备上注册和配置 SEMM (Surface) '
description: 了解如何创建 Surface UEFI 配置包以控制 Surface UEFI 的设置，以及如何在 SEMM 中注册 Surface 设备。
keywords: surface enterprise management
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: hachinda
manager: laurawi
ms.date: 1/15/2021
ms.openlocfilehash: f310b4a43a8a0fc0e77295344ac723770ce821bc
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271059"
---
# <span data-ttu-id="a3ef6-104">使用 SEMM 注册并配置 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="a3ef6-104">Enroll and configure Surface devices with SEMM</span></span>

<span data-ttu-id="a3ef6-105">借助 Microsoft Surface Enterprise Management Mode (SEMM) ，你可以安全地在 Surface 设备上配置 Surface UEFI 的设置，并管理组织中 Surface 设备的这些设置。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-105">With Microsoft Surface Enterprise Management Mode (SEMM), you can securely configure the settings of Surface UEFI on a Surface device and manage those settings on Surface devices in your organization.</span></span> <span data-ttu-id="a3ef6-106">当 Surface 设备由 SEMM 管理时，该设备被视为已\*\* 注册 (有时称为已激活) 。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-106">When a Surface device is managed by SEMM, that device is considered to be *enrolled* (sometimes referred to as activated).</span></span> <span data-ttu-id="a3ef6-107">本文介绍了如何创建 Surface UEFI 配置包，该程序包不仅将控制 Surface UEFI 的设置，还将在 SEMM 中注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-107">This article shows you how to create a Surface UEFI configuration package that will not only control the settings of Surface UEFI, but will also enroll a Surface device in SEMM.</span></span>

<span data-ttu-id="a3ef6-108">有关 SEMM 的更高级概述，请参阅 [Microsoft Surface Enterprise 管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-108">For a more high-level overview of SEMM, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

<span data-ttu-id="a3ef6-109">作为 SEMM 的替代方法，较新的 Surface 设备支持通过 Microsoft Intune 远程管理固件设置的子集。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-109">As an alternative to SEMM, newer Surface devices support remote management of a subset of firmware settings via Microsoft Intune.</span></span> <span data-ttu-id="a3ef6-110">有关详细信息，请参阅 Surface [UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-110">For more information,refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3ef6-111">仅通过 UEFI 管理器在 Surface Pro X 上支持 SEMM。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-111">SEMM is supported on Surface Pro X via the UEFI Manager only.</span></span> <span data-ttu-id="a3ef6-112">有关详细信息，请参阅[部署、管理和维护 Surface Pro X。](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="a3ef6-112">For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>

#### <span data-ttu-id="a3ef6-113">下载并安装 Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="a3ef6-113">Download and install Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="a3ef6-114">用于创建 SEMM 程序包的工具是 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-114">The tool used to create SEMM packages is Microsoft Surface UEFI Configurator.</span></span> <span data-ttu-id="a3ef6-115">你可以从 Microsoft 下载中心的 Surface Tools [for IT](https://www.microsoft.com/download/details.aspx?id=46703) 页面下载 Microsoft Surface UEFI 配置程序。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-115">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>
<span data-ttu-id="a3ef6-116">运行 Microsoft Surface UEFI Configurator Windows Installer (.msi) 文件以开始安装该工具。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-116">Run the Microsoft Surface UEFI Configurator Windows Installer (.msi) file to start the installation of the tool.</span></span> <span data-ttu-id="a3ef6-117">安装程序完成后，在"开始"菜单的"所有应用"部分查找 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-117">When the installer completes, find Microsoft Surface UEFI Configurator in the All Apps section of your Start menu.</span></span>

>[!NOTE]
><span data-ttu-id="a3ef6-118">Microsoft Surface UEFI 配置器仅在 Windows 10 上受支持。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-118">Microsoft Surface UEFI Configurator is supported only on Windows 10.</span></span>

## <span data-ttu-id="a3ef6-119">创建 Surface UEFI 配置包</span><span class="sxs-lookup"><span data-stu-id="a3ef6-119">Create a Surface UEFI configuration package</span></span>

<span data-ttu-id="a3ef6-120">Surface UEFI 配置包同时执行将 Surface UEFI 设置的新配置应用到使用 SEMM 管理的 Surface 设备的角色和在 SEMM 中注册 Surface 设备的角色。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-120">The Surface UEFI configuration package performs both the role of applying a new configuration of Surface UEFI settings to a Surface device managed with SEMM and the role of enrolling Surface devices in SEMM.</span></span> <span data-ttu-id="a3ef6-121">创建配置包需要具有签名证书以与 SEMM 一起使用，以确保在每个 Surface 设备上配置 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-121">The creation of a configuration package requires you to have a signing certificate to be used with SEMM to secure the configuration of UEFI settings on each Surface device.</span></span> <span data-ttu-id="a3ef6-122">有关 SEMM 证书的要求详细信息，请参阅 Microsoft [Surface Enterprise 管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-122">For more information about the requirements for the SEMM certificate, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

<span data-ttu-id="a3ef6-123">若要创建 Surface UEFI 配置包，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a3ef6-123">To create a Surface UEFI configuration package, follow these steps:</span></span>

1. <span data-ttu-id="a3ef6-124">从"开始"菜单打开 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-124">Open Microsoft Surface UEFI Configurator from the Start menu.</span></span>
2. <span data-ttu-id="a3ef6-125">单击**开始**。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-125">Click **Start**.</span></span>
3. <span data-ttu-id="a3ef6-126">单击 **"配置**包"，如图 1 所示。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-126">Click **Configuration Package**, as shown in Figure 1.</span></span>

   ![创建 SEMM 注册包](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *<span data-ttu-id="a3ef6-128">图 1.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-128">Figure 1.</span></span> <span data-ttu-id="a3ef6-129">选择配置包以创建用于 SEMM 注册和配置的程序包</span><span class="sxs-lookup"><span data-stu-id="a3ef6-129">Select Configuration Package to create a package for SEMM enrollment and configuration</span></span>*

4. <span data-ttu-id="a3ef6-130">单击 **"证书** 保护"以使用私钥 (.pfx) 导出的证书文件，如图 2 所示。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-130">Click **Certificate Protection** to add your exported certificate file with private key (.pfx), as shown in Figure 2.</span></span> <span data-ttu-id="a3ef6-131">浏览到证书文件的位置，选择该文件，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="a3ef6-131">Browse to the location of your certificate file, select the file, and then click **OK**.</span></span>

   ![将 SEM 证书和 Surface UEFI 密码添加到配置包](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *<span data-ttu-id="a3ef6-133">图 2.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-133">Figure 2.</span></span> <span data-ttu-id="a3ef6-134">将 SEMM 证书和 Surface UEFI 密码添加到 Surface UEFI 配置包</span><span class="sxs-lookup"><span data-stu-id="a3ef6-134">Add the SEMM certificate and Surface UEFI password to a Surface UEFI configuration package</span></span>*

5. <span data-ttu-id="a3ef6-135">当系统提示您确认证书密码时，请输入并确认证书文件的密码，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="a3ef6-135">When you are prompted to confirm the certificate password, enter and confirm the password for your certificate file, and then click **OK**.</span></span>
6. <span data-ttu-id="a3ef6-136">单击 **"密码保护** "将密码添加到 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-136">Click **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="a3ef6-137">每次启动到 UEFI 时，都需要此密码。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-137">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="a3ef6-138">如果未输入此密码，**则只\*\*\*\*显示电脑**信息、关于、企业管理\*\*\*\* 和**退出**页面。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-138">If this password is not entered, only the **PC information**, **About**, **Enterprise management**, and **Exit** pages will be displayed.</span></span> <span data-ttu-id="a3ef6-139">此步骤可选。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-139">This step is optional.</span></span>
7. <span data-ttu-id="a3ef6-140">出现提示时，输入并确认你为 Surface UEFI 选择的密码，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="a3ef6-140">When you are prompted, enter and confirm your chosen password for Surface UEFI, and then click **OK**.</span></span> <span data-ttu-id="a3ef6-141">如果要清除现有的 Surface UEFI 密码，将密码字段留空。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-141">If you want to clear an existing Surface UEFI password, leave the password field blank.</span></span>
8. <span data-ttu-id="a3ef6-142">如果不希望 Surface UEFI 程序包应用于特定设备，请在"选择要面向的**Surface**类型"页上，单击相应的 Surface Book 或 Surface Pro 4 图像下方的滑块，以便它处于关闭\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-142">If you do not want the Surface UEFI package to apply to a particular device, on the **Choose which Surface type you want to target** page, click the slider beneath the corresponding Surface Book or Surface Pro 4 image so that it is in the **Off** position.</span></span> <span data-ttu-id="a3ef6-143"> (如图 3.) </span><span class="sxs-lookup"><span data-stu-id="a3ef6-143">(As shown in Figure 3.)</span></span>
   > [!NOTE] 
   > <span data-ttu-id="a3ef6-144">你必须选择设备，因为默认情况下未选择任何设备。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-144">You must select a device as none are selected by default.</span></span>

   ![选择设备进行程序包兼容性](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *<span data-ttu-id="a3ef6-146">图 3.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-146">Figure 3.</span></span> <span data-ttu-id="a3ef6-147">选择设备进行程序包兼容性</span><span class="sxs-lookup"><span data-stu-id="a3ef6-147">Choose the devices for package compatibility</span></span>*

9. <span data-ttu-id="a3ef6-148">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-148">Click **Next**.</span></span>
10. <span data-ttu-id="a3ef6-149">如果要在托管 Surface 设备上停用组件，请在"选择要激活或停用\*\*\*\* 的组件"页上，单击要停用的任何设备或设备组旁边的滑块，以便滑块处于关闭位置。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a3ef6-149">If you want to deactivate a component on managed Surface devices, on the **Choose which components you want to activate or deactivate** page, click the slider next to any device or group of devices you want to deactivate so that the slider is in the **Off** position.</span></span> <span data-ttu-id="a3ef6-150"> (图 4.) 每个设备的默认配置为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="a3ef6-150">(Shown in Figure 4.) The default configuration for each device is **On**.</span></span> <span data-ttu-id="a3ef6-151">如果要 **将** 所有滑块返回到默认位置，请单击"重置"按钮。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-151">Click the **Reset** button if you want to return all sliders to the default position.</span></span>

    ![禁用或启用 Surface 组件](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *<span data-ttu-id="a3ef6-153">图 4.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-153">Figure 4.</span></span> <span data-ttu-id="a3ef6-154">禁用或启用单个 Surface 组件</span><span class="sxs-lookup"><span data-stu-id="a3ef6-154">Disable or enable individual Surface components</span></span>*

11. <span data-ttu-id="a3ef6-155">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-155">Click **Next**.</span></span>
12. <span data-ttu-id="a3ef6-156">若要在 Surface UEFI 中启用或禁用高级选项或显示 Surface UEFI\*\*\*\* 页面，请在"选择设备的高级设置"页上，单击所需设置旁边的滑块，将该选项配置为"\*\*\*\* 开"或"关 **" (如图**5) 所示。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-156">To enable or disable advanced options in Surface UEFI or the display of Surface UEFI pages, on the **Choose the advanced settings for your devices** page, click the slider beside the desired setting to configure that option to **On** or **Off** (shown in Figure 5).</span></span> <span data-ttu-id="a3ef6-157">在**UEFI**首页部分，可以使用安全、设备和启动的滑块来控制哪些\*\*\*\* 页面可供启动到\*\*\*\* Surface UEFI 的用户使用。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a3ef6-157">In the **UEFI Front Page** section, you can use the sliders for **Security**, **Devices**, and **Boot** to control what pages are available to users who boot into Surface UEFI.</span></span> <span data-ttu-id="a3ef6-158"> (有关 Surface UEFI 设置的详细信息，请参阅"管理[Surface UEFI](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)设置"。)\ \*\*\** 完成选择生成和保存程序包的选项后单击"生成"。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-158">(For more information about Surface UEFI settings, see [Manage Surface UEFI settings](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).) Click **Build** when you have finished selecting options to generate and save the package.</span></span>

    ![控制高级 Surface UEFI 设置和 Surface UEFI 页面](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *<span data-ttu-id="a3ef6-160">图 5.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-160">Figure 5.</span></span> <span data-ttu-id="a3ef6-161">使用 SEMM 控制高级 Surface UEFI 设置和 Surface UEFI 页面</span><span class="sxs-lookup"><span data-stu-id="a3ef6-161">Control advanced Surface UEFI settings and Surface UEFI pages with SEMM</span></span>*

13. <span data-ttu-id="a3ef6-162">在 **"另存为**"对话框中，指定 Surface UEFI 配置包的名称，浏览到要保存文件的位置，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3ef6-162">In the **Save As** dialog box, specify a name for the Surface UEFI configuration package, browse to the location where you would like to save the file, and then click **Save**.</span></span>
14. <span data-ttu-id="a3ef6-163">创建和保存程序包时，将显示 **"成功"** 页。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-163">When the package is created and saved, the **Successful** page is displayed.</span></span>

>[!NOTE]
><span data-ttu-id="a3ef6-164">记录此页上显示的证书指纹字符，如图 6 所示。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-164">Record the certificate thumbprint characters that are displayed on this page, as shown in Figure 6.</span></span> <span data-ttu-id="a3ef6-165">你将需要这些字符来确认在 SEMM 中注册新的 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-165">You will need these characters to confirm enrollment of new Surface devices in SEMM.</span></span> <span data-ttu-id="a3ef6-166">单击 **"结束** "完成程序包创建并关闭 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-166">Click **End** to complete package creation and close Microsoft Surface UEFI Configurator.</span></span>

![显示证书指纹字符](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*<span data-ttu-id="a3ef6-168">图 6.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-168">Figure 6.</span></span> <span data-ttu-id="a3ef6-169">证书指纹的最后两个字符显示在"成功"页上</span><span class="sxs-lookup"><span data-stu-id="a3ef6-169">The last two characters of the certificate thumbprint are displayed on the Successful page</span></span>*

<span data-ttu-id="a3ef6-170">现在，你已创建 Surface UEFI 配置包，你可以注册或配置 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-170">Now that you have created your Surface UEFI configuration package, you can enroll or configure Surface devices.</span></span>

>[!NOTE]
><span data-ttu-id="a3ef6-171">创建 Surface UEFI 配置包时，日志文件在桌面上创建一个配置包设置和选项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-171">When a Surface UEFI configuration package is created, a log file is created on the desktop with details of the configuration package settings and options.</span></span>

## <span data-ttu-id="a3ef6-172">在 SEMM 中注册 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="a3ef6-172">Enroll a Surface device in SEMM</span></span>
<span data-ttu-id="a3ef6-173">执行 Surface UEFI 配置包时，SEMM 证书和 Surface UEFI 配置文件将存储在 Surface 设备的固件存储中。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-173">When the Surface UEFI configuration package is executed, the SEMM certificate and Surface UEFI configuration files are staged in the firmware storage of the Surface device.</span></span> <span data-ttu-id="a3ef6-174">当 Surface 设备重新启动时，Surface UEFI 将处理这些文件，并开始在 SEMM 中应用 Surface UEFI 配置或注册 Surface 设备的过程，如图 7 所示。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-174">When the Surface device reboots, Surface UEFI processes these files and begins the process of applying the Surface UEFI configuration or enrolling the Surface device in SEMM, as shown in Figure 7.</span></span>

![用于配置 Surface UEFI 或注册的 SEMM 过程](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*<span data-ttu-id="a3ef6-176">图 7.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-176">Figure 7.</span></span> <span data-ttu-id="a3ef6-177">Surface UEFI 的配置或 Surface 设备的注册的 SEMM 过程</span><span class="sxs-lookup"><span data-stu-id="a3ef6-177">The SEMM process for configuration of Surface UEFI or enrollment of a Surface device</span></span>*

<span data-ttu-id="a3ef6-178">在开始在 SEMM 中注册 Surface 设备的过程之前，请确保你已拥有证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-178">Before you begin the process to enroll a Surface device in SEMM, ensure that you have the last two characters of the certificate thumbprint on hand.</span></span> <span data-ttu-id="a3ef6-179">你将需要这些字符来确认设备的注册 (参见图 6) 。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-179">You will need these characters to confirm the device’s enrollment (see Figure 6).</span></span>

<span data-ttu-id="a3ef6-180">若要在 SEMM 中向 Surface UEFI 配置包注册 Surface 设备，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a3ef6-180">To enroll a Surface device in SEMM with a Surface UEFI configuration package, follow these steps:</span></span>

1. <span data-ttu-id="a3ef6-181">在你想要在 SEMM 中注册的 Surface 设备上运行 Surface UEFI 配置包 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-181">Run the Surface UEFI configuration package .msi file on the Surface device you want to enroll in SEMM.</span></span> <span data-ttu-id="a3ef6-182">这将在设备的固件中预配 Surface UEFI 配置文件。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-182">This will provision the Surface UEFI configuration file in the device’s firmware.</span></span>
2. <span data-ttu-id="a3ef6-183">选中 **"我接受**许可协议"复选框中的条款以接受 EULA (最终用户许可协议) ，然后单击"安装"开始安装过程。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a3ef6-183">Select the **I accept the terms in the License Agreement** check box to accept the End User License Agreement (EULA), and then click **Install** to begin the installation process.</span></span>
3. <span data-ttu-id="a3ef6-184">单击 **"** 完成"以完成 Surface UEFI 配置包安装，当系统提示你这样做时，请重新启动 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-184">Click **Finish** to complete the Surface UEFI configuration package installation and restart the Surface device when you are prompted to do so.</span></span>
4. <span data-ttu-id="a3ef6-185">Surface UEFI 将加载配置文件并确定未在设备上启用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-185">Surface UEFI will load the configuration file and determine that SEMM is not enabled on the device.</span></span> <span data-ttu-id="a3ef6-186">Surface UEFI 随后将开始 SEMM 注册过程，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a3ef6-186">Surface UEFI will then begin the SEMM enrollment process, as follows:</span></span>
   * <span data-ttu-id="a3ef6-187">Surface UEFI 将验证 SEMM 配置文件是否包含 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-187">Surface UEFI will verify that the SEMM configuration file contains a SEMM certificate.</span></span>
   * <span data-ttu-id="a3ef6-188">Surface UEFI 将提示你输入证书指纹的最后两个字符以确认在 SEMM 中注册 Surface 设备，如图 8 所示。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-188">Surface UEFI will prompt you to enter the last two characters of the certificate thumbprint to confirm enrollment of the Surface device in SEMM, as shown in Figure 8.</span></span>

      ![SEMM 注册需要证书指纹的最后两个字符](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *<span data-ttu-id="a3ef6-190">图 8.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-190">Figure 8.</span></span> <span data-ttu-id="a3ef6-191">在 SEMM 中注册需要证书指纹的最后两个字符</span><span class="sxs-lookup"><span data-stu-id="a3ef6-191">Enrollment in SEMM requires the last two characters of the certificate thumbprint</span></span>*

   * <span data-ttu-id="a3ef6-192">Surface UEFI 将在固件中存储 SEMM 证书，并应用在 Surface UEFI 配置文件中指定的配置设置。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-192">Surface UEFI will store the SEMM certificate in firmware and apply the configuration settings that are specified in the Surface UEFI configuration file.</span></span>
   
5. <span data-ttu-id="a3ef6-193">Surface 设备现已在 SEMM 中注册，并且将启动到 Windows。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-193">The Surface device is now enrolled in SEMM and will boot to Windows.</span></span>

<span data-ttu-id="a3ef6-194">可以通过在程序和功能 (（如图 9) 所示）或存储在 Microsoft **Surface UEFI**配置器日志中的事件（在事件查看器 (中的应用程序和服务日志下找到）中查找**Microsoft Surface Configuration Package**来验证 Surface\*\*\*\* 设备已成功注册，如图 10) 所示。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a3ef6-194">You can verify that a Surface device has been successfully enrolled in SEMM by looking for **Microsoft Surface Configuration Package** in **Programs and Features** (as shown in Figure 9), or in the events stored in the **Microsoft Surface UEFI Configurator** log, found under **Applications and Services Logs** in Event Viewer (as shown in Figure 10).</span></span>

![在"程序和功能"中验证 Surface 设备在 SEMM 中的注册](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*<span data-ttu-id="a3ef6-196">图 9.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-196">Figure 9.</span></span> <span data-ttu-id="a3ef6-197">在"程序和功能"中验证 Surface 设备在 SEMM 中的注册情况</span><span class="sxs-lookup"><span data-stu-id="a3ef6-197">Verify the enrollment of a Surface device in SEMM in Programs and Features</span></span>*

![在事件查看器中验证 Surface 设备在 SEMM 中的注册](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*<span data-ttu-id="a3ef6-199">图 10.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-199">Figure 10.</span></span> <span data-ttu-id="a3ef6-200">在事件查看器中验证在 SEMM 中注册 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="a3ef6-200">Verify the enrollment of a Surface device in SEMM in Event Viewer</span></span>*

<span data-ttu-id="a3ef6-201">还可以验证设备是否注册到 Surface UEFI 的 SEMM 中 - 当设备注册时，Surface UEFI\*\*\*\* 将包含"企业管理"页 (如图 11) 。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-201">You can also verify that the device is enrolled in SEMM in Surface UEFI – while the device is enrolled, Surface UEFI will contain the **Enterprise management** page (as shown in Figure 11).</span></span>

![Surface UEFI 企业版管理页](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*<span data-ttu-id="a3ef6-203">图 11.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-203">Figure 11.</span></span> <span data-ttu-id="a3ef6-204">Surface UEFI 企业版管理页</span><span class="sxs-lookup"><span data-stu-id="a3ef6-204">The Surface UEFI Enterprise management page</span></span>*


## <span data-ttu-id="a3ef6-205">使用 SEMM 配置 Surface UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="a3ef6-205">Configure Surface UEFI settings with SEMM</span></span>

<span data-ttu-id="a3ef6-206">在 SEMM 中注册设备后，你可以运行使用同一 SEMM 证书签名的 Surface UEFI 配置包，以应用新的 Surface UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-206">After a device is enrolled in SEMM, you can run Surface UEFI configuration packages signed with the same SEMM certificate to apply new Surface UEFI settings.</span></span> <span data-ttu-id="a3ef6-207">这些设置将在设备下次启动时自动应用，无需用户的任何交互。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-207">These settings are applied automatically the next time the device boots, without any interaction from the user.</span></span> <span data-ttu-id="a3ef6-208">可以使用 Microsoft Endpoint Configuration Manager 等应用程序部署解决方案将 Surface UEFI 配置包部署到 Surface 设备，以更改或管理 Surface UEFI 中的设置。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-208">You can use application deployment solutions like Microsoft Endpoint Configuration Manager to deploy Surface UEFI configuration packages to Surface devices to change or manage the settings in Surface UEFI.</span></span>

<span data-ttu-id="a3ef6-209">有关如何使用 Configuration Manager 部署 Windows Installer (.msi) 文件，请参阅 [使用 Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt627959)部署和管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-209">For more information about how to deploy Windows Installer (.msi) files with Configuration Manager, see [Deploy and manage applications with Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt627959).</span></span>

<span data-ttu-id="a3ef6-210">如果你已使用密码保护 Surface UEFI，没有密码的用户尝试启动到 Surface UEFI 将只显示电脑信息、关于、\*\*\*\* 企业管理和\*\*\*\* 退出页面。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a3ef6-210">If you have secured Surface UEFI with a password, users without the password who attempt to boot to Surface UEFI will only have the **PC information**, **About**, **Enterprise management**, and **Exit** pages displayed to them.</span></span>

<span data-ttu-id="a3ef6-211">如果没有使用密码保护 Surface UEFI 或用户输入了正确的密码，则使用 SEMM 配置的设置将变暗 (不可用) 并且"某些设置由组织管理"的文本将显示在页面顶部，如图 12 所示。</span><span class="sxs-lookup"><span data-stu-id="a3ef6-211">If you have not secured Surface UEFI with a password or a user enters the password correctly, settings that are configured with SEMM will be dimmed (unavailable) and the text Some settings are managed by your organization will be displayed at the top of the page, as shown in Figure 12.</span></span>

![在 Surface UEFI 中禁用由 SEMM 管理的设置](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*<span data-ttu-id="a3ef6-213">图 12.</span><span class="sxs-lookup"><span data-stu-id="a3ef6-213">Figure 12.</span></span> <span data-ttu-id="a3ef6-214">由 SEMM 管理的设置将在 Surface UEFI 中禁用</span><span class="sxs-lookup"><span data-stu-id="a3ef6-214">Settings managed by SEMM will be disabled in Surface UEFI</span></span>*

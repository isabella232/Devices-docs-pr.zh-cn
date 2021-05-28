---
title: 使用 Microsoft 终结点配置管理器管理具有 SEMM (Surface) 的设备
description: 了解如何通过终结点配置管理器管理 Microsoft Surface 企业版管理模式 (SEMM) 。
keywords: 注册、更新、脚本、设置
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 2d31f520d8c4da54f47b2b89b58b43e2cb983f1a
ms.sourcegitcommit: 7f5b97275fe301ef700f9c77954a1054e2e8d046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145613"
---
# <span data-ttu-id="22f5a-104">使用 Microsoft Endpoint Configuration Manager 通过 SEMM 管理设备</span><span class="sxs-lookup"><span data-stu-id="22f5a-104">Use Microsoft Endpoint Configuration Manager to manage devices with SEMM</span></span>

<span data-ttu-id="22f5a-105">通过 Surface UEFI 设备的 Microsoft Surface 企业版管理模式 (SEMM) 功能，管理员可以管理并帮助保护 Surface UEFI 设置的配置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-105">The Microsoft Surface Enterprise Management Mode (SEMM) feature of Surface UEFI devices lets administrators manage and help secure the configuration of Surface UEFI settings.</span></span> <span data-ttu-id="22f5a-106">对于大多数组织，通过使用 Microsoft Surface UEFI 配置工具创建 Windows Installer ( .msi) 程序包来完成此过程。</span><span class="sxs-lookup"><span data-stu-id="22f5a-106">For most organizations, this process is accomplished by creating Windows Installer (.msi) packages with the Microsoft Surface UEFI Configurator tool.</span></span> <span data-ttu-id="22f5a-107">然后，这些程序包将在 SEMM 中运行或部署到客户端 Surface 设备，以便在中注册设备并更新 Surface UEFI 设置配置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-107">These packages are then run or deployed to the client Surface devices to enroll the devices in SEMM and to update the Surface UEFI settings configuration.</span></span>

<span data-ttu-id="22f5a-108">对于具有 Microsoft 终结点配置管理器的组织，可以使用 Microsoft Surface UEFI 配置器 .msi 过程来部署和管理 SEMM。</span><span class="sxs-lookup"><span data-stu-id="22f5a-108">For organizations with Microsoft Endpoint Configuration Manager there is an alternative to using the Microsoft Surface UEFI Configurator .msi process to deploy and administer SEMM.</span></span> <span data-ttu-id="22f5a-109">Microsoft Surface UEFI 管理器是一个轻量安装程序，可在设备上提供 SEMM 管理所需的程序集。</span><span class="sxs-lookup"><span data-stu-id="22f5a-109">Microsoft Surface UEFI Manager is a lightweight installer that makes required assemblies for SEMM management available on a device.</span></span> <span data-ttu-id="22f5a-110">通过在托管客户端上通过 Microsoft Surface UEFI 管理器安装这些程序集，SEMM 可以通过配置管理器使用 PowerShell 脚本进行管理，并将其部署为应用程序。</span><span class="sxs-lookup"><span data-stu-id="22f5a-110">By installing these assemblies with Microsoft Surface UEFI Manager on a managed client, SEMM can be administered by Configuration Manager with PowerShell scripts, deployed as applications.</span></span> <span data-ttu-id="22f5a-111">通过此过程，SEMM 管理在配置管理器中执行，从而消除了外部 Microsoft Surface UEFI 配置工具的需要。</span><span class="sxs-lookup"><span data-stu-id="22f5a-111">With this process, SEMM management is performed within Configuration Manager, which eliminates the need for the external Microsoft Surface UEFI Configurator tool.</span></span>

> [!Note]
> <span data-ttu-id="22f5a-112">虽然本文中介绍的过程可能适用于终结点配置管理器的早期版本或其他第三方管理解决方案，但只有终结点配置管理器的当前分支才支持使用 Microsoft Surface UEFI 管理器和 PowerShell 的 SEMM 管理。</span><span class="sxs-lookup"><span data-stu-id="22f5a-112">Although the process described in this article may work with earlier versions of Endpoint Configuration Manager or with other third-party management solutions, management of SEMM with Microsoft Surface UEFI Manager and PowerShell is supported only with the Current Branch of Endpoint Configuration Manager.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="22f5a-113">必备条件</span><span class="sxs-lookup"><span data-stu-id="22f5a-113">Prerequisites</span></span>

<span data-ttu-id="22f5a-114">开始本文概述的过程之前，请熟悉以下技术和工具：</span><span class="sxs-lookup"><span data-stu-id="22f5a-114">Before you begin the process outlined in this article, familiarize yourself with the following technologies and tools:</span></span>

* [<span data-ttu-id="22f5a-115">Surface UEFI</span><span class="sxs-lookup"><span data-stu-id="22f5a-115">Surface UEFI</span></span>](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [<span data-ttu-id="22f5a-116">Surface 企业管理模式 (SEMM)</span><span class="sxs-lookup"><span data-stu-id="22f5a-116">Surface Enterprise Management Mode (SEMM)</span></span>](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [<span data-ttu-id="22f5a-117">PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="22f5a-117">PowerShell scripting</span></span>](https://technet.microsoft.com/scriptcenter/dd742419)
* [<span data-ttu-id="22f5a-118">System Center Configuration Manager 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="22f5a-118">System Center Configuration Manager application deployment</span></span>](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* <span data-ttu-id="22f5a-119">证书管理</span><span class="sxs-lookup"><span data-stu-id="22f5a-119">Certificate management</span></span>

> [!Note]
> <span data-ttu-id="22f5a-120">你还需要访问用于保护 SEMM 的证书。</span><span class="sxs-lookup"><span data-stu-id="22f5a-120">You will also need access to the certificate that you intend to use to secure SEMM.</span></span> <span data-ttu-id="22f5a-121">有关此证书的要求的详细信息，请参阅 [Surface Enterprise 管理模式证书要求](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。</span><span class="sxs-lookup"><span data-stu-id="22f5a-121">For details about the requirements for this certificate, see [Surface Enterprise Management Mode certificate requirements](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span>
> 
> <span data-ttu-id="22f5a-122">将此证书保存在安全的位置并正确备份非常重要。</span><span class="sxs-lookup"><span data-stu-id="22f5a-122">It is very important that this certificate be kept in a safe location and properly backed up.</span></span> <span data-ttu-id="22f5a-123">如果此证书已丢失或不可用，则不能重置 Surface UEFI、更改托管 Surface UEFI 设置或从已注册的 Surface 设备中删除 SEMM。</span><span class="sxs-lookup"><span data-stu-id="22f5a-123">If this certificate becomes lost or unusable, it is not possible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.</span></span>

#### <span data-ttu-id="22f5a-124">下载 Microsoft Surface UEFI 管理器</span><span class="sxs-lookup"><span data-stu-id="22f5a-124">Download Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="22f5a-125">通过 Configuration Manager 管理 SEMM 需要在每个客户端 Surface 设备上安装 Microsoft Surface UEFI 管理器。</span><span class="sxs-lookup"><span data-stu-id="22f5a-125">Management of SEMM with Configuration Manager requires the installation of Microsoft Surface UEFI Manager on each client Surface device.</span></span> <span data-ttu-id="22f5a-126">你可以从 Microsoft 下载中心上的 " [Surface Tools FOR IT](https://www.microsoft.com/download/details.aspx?id=46703) " 页面下载 MICROSOFT Surface UEFI 管理器 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="22f5a-126">You can download Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center.</span></span>

#### <span data-ttu-id="22f5a-127">下载 Configuration Manager 的 SEMM 脚本</span><span class="sxs-lookup"><span data-stu-id="22f5a-127">Download SEMM scripts for Configuration Manager</span></span>

<span data-ttu-id="22f5a-128">在客户端 Surface 设备上安装 Microsoft Surface UEFI 管理器后，将通过 PowerShell 脚本部署和管理 SEMM。</span><span class="sxs-lookup"><span data-stu-id="22f5a-128">After Microsoft Surface UEFI Manager is installed on the client Surface device, SEMM is deployed and managed with PowerShell scripts.</span></span> <span data-ttu-id="22f5a-129">你可以从下载中心下载 [SEMM 管理脚本](https://www.microsoft.com/download/details.aspx?id=46703) 的示例。</span><span class="sxs-lookup"><span data-stu-id="22f5a-129">You can download samples of the [SEMM management scripts](https://www.microsoft.com/download/details.aspx?id=46703) from the Download Center.</span></span>

## <a name="deploy-microsoft-surface-uefi-manager"></a><span data-ttu-id="22f5a-130">部署 Microsoft Surface UEFI 管理器</span><span class="sxs-lookup"><span data-stu-id="22f5a-130">Deploy Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="22f5a-131">Microsoft Surface UEFI 管理器的部署是典型的应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="22f5a-131">Deployment of Microsoft Surface UEFI Manager is a typical application deployment.</span></span> <span data-ttu-id="22f5a-132">Microsoft Surface UEFI 管理器安装程序文件是标准的 Windows Installer 文件，可使用 [标准安静选项](https://msdn.microsoft.com/library/windows/desktop/aa367988)进行安装。</span><span class="sxs-lookup"><span data-stu-id="22f5a-132">The Microsoft Surface UEFI Manager installer file is a standard Windows Installer file that you can install with the [standard quiet option](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span></span>

<span data-ttu-id="22f5a-133">安装 Microsoft Surface UEFI 管理器的命令如下所示。</span><span class="sxs-lookup"><span data-stu-id="22f5a-133">The command to install Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

<span data-ttu-id="22f5a-134">用于卸载 Microsoft Surface UEFI 管理器的命令如下所示。</span><span class="sxs-lookup"><span data-stu-id="22f5a-134">The command to uninstall Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

<span data-ttu-id="22f5a-135">若要创建新的应用程序并将其部署到包含 Surface 设备的集合，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="22f5a-135">To create a new application and deploy it to a collection that contains your Surface devices, perform the following steps:</span></span>

1. <span data-ttu-id="22f5a-136">从 " **开始** " 屏幕或 " **开始** " 菜单打开 Configuration Manager 控制台。</span><span class="sxs-lookup"><span data-stu-id="22f5a-136">Open Configuration Manager Console from the **Start** screen or **Start** menu.</span></span>
2. <span data-ttu-id="22f5a-137">选择窗口左下角的 " **软件库** "。</span><span class="sxs-lookup"><span data-stu-id="22f5a-137">Select **Software Library** in the bottom left corner of the window.</span></span>
3. <span data-ttu-id="22f5a-138">展开软件库的 " **应用程序管理** " 节点，然后选择 " **应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-138">Expand the **Application Management** node of the Software Library, and then select **Applications**.</span></span>
4. <span data-ttu-id="22f5a-139">在窗口顶部的 "**开始**" 选项卡下，选择 "**创建应用程序**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="22f5a-139">Select the **Create Application** button under the **Home** tab at the top of the window.</span></span> <span data-ttu-id="22f5a-140">这将启动创建应用程序向导。</span><span class="sxs-lookup"><span data-stu-id="22f5a-140">This starts the Create Application Wizard.</span></span>
5. <span data-ttu-id="22f5a-141">创建应用程序向导显示一系列步骤：</span><span class="sxs-lookup"><span data-stu-id="22f5a-141">The Create Application Wizard presents a series of steps:</span></span>

   * <span data-ttu-id="22f5a-142">**常规** -默认情况下，" **自动检测来自安装文件的有关此应用程序的信息** " 选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="22f5a-142">**General** – The **Automatically detect information about this application from installation files** option is selected by default.</span></span> <span data-ttu-id="22f5a-143">在 " **类型** " 字段中，默认情况下也会选择 " \*\*Windows Installer ( .msi 文件") \*\* 。</span><span class="sxs-lookup"><span data-stu-id="22f5a-143">In the **Type** field, **Windows Installer (.msi file)** is also selected by default.</span></span> <span data-ttu-id="22f5a-144">选择 " **浏览** " 导航到 **SurfaceUEFIManagerSetup.msi**，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-144">Select **Browse** to navigate to and select **SurfaceUEFIManagerSetup.msi**, and then select **Next**.</span></span>
   
      > [!Note]
      > <span data-ttu-id="22f5a-145">SurfaceUEFIManagerSetup.msi 的位置必须位于网络共享位置，并且位于不包含任何其他文件的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="22f5a-145">The location of SurfaceUEFIManagerSetup.msi must be on a network share and located in a folder that contains no other files.</span></span> <span data-ttu-id="22f5a-146">无法使用本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-146">A local file location cannot be used.</span></span>

   * <span data-ttu-id="22f5a-147">**导入信息** -创建应用程序向导将解析 .msi 文件并读取 **应用程序名称** 和 **产品代码**。</span><span class="sxs-lookup"><span data-stu-id="22f5a-147">**Import Information** – The Create Application Wizard will parse the .msi file and read the **Application Name** and **Product Code**.</span></span> <span data-ttu-id="22f5a-148">SurfaceUEFIManagerSetup.msi 应作为 "行 **内容" 文件**中的唯一文件列出，如图1所示。</span><span class="sxs-lookup"><span data-stu-id="22f5a-148">SurfaceUEFIManagerSetup.msi should be listed as the only file under the line **Content Files**, as shown in Figure 1.</span></span> <span data-ttu-id="22f5a-149">选择 " **下一步** " 继续。</span><span class="sxs-lookup"><span data-stu-id="22f5a-149">Select **Next** to proceed.</span></span>

      ![来自 Surface UEFI 管理器设置的信息将自动进行分析](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *<span data-ttu-id="22f5a-151">图 1.</span><span class="sxs-lookup"><span data-stu-id="22f5a-151">Figure 1.</span></span> <span data-ttu-id="22f5a-152">来自 Microsoft Surface UEFI 管理器设置的信息将自动进行分析</span><span class="sxs-lookup"><span data-stu-id="22f5a-152">Information from Microsoft Surface UEFI Manager setup is automatically parsed</span></span>*

   * <span data-ttu-id="22f5a-153">**常规信息** -你可以修改应用程序的名称以及有关发布者和版本的信息，或在此页面上添加评论。</span><span class="sxs-lookup"><span data-stu-id="22f5a-153">**General Information** – You can modify the name of the application and information about the publisher and version, or add comments on this page.</span></span> <span data-ttu-id="22f5a-154">Microsoft Surface UEFI 管理器的安装命令将显示在 "安装程序" 字段中。</span><span class="sxs-lookup"><span data-stu-id="22f5a-154">The installation command for Microsoft Surface UEFI Manager is displayed in the Installation Program field.</span></span> <span data-ttu-id="22f5a-155">系统安装的默认安装行为将允许 Microsoft Surface UEFI 管理器为 SEMM 安装所需的程序集，即使用户未登录到 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="22f5a-155">The default installation behavior of Install for system will allow Microsoft Surface UEFI Manager to install the required assemblies for SEMM even if a user is not logged on to the Surface device.</span></span> <span data-ttu-id="22f5a-156">选择 " **下一步** " 继续。</span><span class="sxs-lookup"><span data-stu-id="22f5a-156">Select **Next** to proceed.</span></span>
   * <span data-ttu-id="22f5a-157">**摘要** -在此页面上显示在 " **导入信息** " 步骤中分析的信息和您在 " **常规信息** " 步骤中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="22f5a-157">**Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page.</span></span> <span data-ttu-id="22f5a-158">选择 " **下一步** " 确认你的选择并创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="22f5a-158">Select **Next** to confirm your selections and create the application.</span></span>
   * <span data-ttu-id="22f5a-159">**进度** –在导入应用程序并将其添加到软件库时显示进度栏和状态。</span><span class="sxs-lookup"><span data-stu-id="22f5a-159">**Progress** – Displays a progress bar and status as the application is imported and added to the Software Library.</span></span>
   * <span data-ttu-id="22f5a-160">**完成** –当应用程序创建过程完成时，将显示对成功创建应用程序创建的确认。</span><span class="sxs-lookup"><span data-stu-id="22f5a-160">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="22f5a-161">选择 " **关闭** " 以完成创建应用程序向导。</span><span class="sxs-lookup"><span data-stu-id="22f5a-161">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="22f5a-162">在 Configuration Manager 中创建应用程序后，你可以将其分配到分发点，并将其部署到包含 Surface 设备的集合。</span><span class="sxs-lookup"><span data-stu-id="22f5a-162">After the application is created in Configuration Manager, you can distribute it to your distribution points and deploy it to the collections including your Surface devices.</span></span> <span data-ttu-id="22f5a-163">此应用程序将不会在 Surface 设备上安装或启用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="22f5a-163">This application will not install or enable SEMM on the Surface device.</span></span> <span data-ttu-id="22f5a-164">它仅提供使用 PowerShell 脚本启用 SEMM 所需的程序集。</span><span class="sxs-lookup"><span data-stu-id="22f5a-164">It only provides the assemblies required for SEMM to be enabled using the PowerShell script.</span></span>

<span data-ttu-id="22f5a-165">如果您不希望在不使用 SEMM 管理的设备上安装 Microsoft Surface UEFI 管理器程序集，则可以将 Microsoft Surface UEFI 管理器配置为 SEMM Configuration Manager 脚本的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="22f5a-165">If you do not want to install the Microsoft Surface UEFI Manager assemblies on devices that will not be managed with SEMM, you can configure Microsoft Surface UEFI Manager as a dependency of the SEMM Configuration Manager scripts.</span></span> <span data-ttu-id="22f5a-166">此方案将在本文后面的 " [部署 SEMM Configuration Manager 脚本](#deploy-semm-configuration-manager-scripts) " 一节中介绍。</span><span class="sxs-lookup"><span data-stu-id="22f5a-166">This scenario is covered in the [Deploy SEMM Configuration Manager Scripts](#deploy-semm-configuration-manager-scripts) section later in this article.</span></span>

## <a name="create-or-modify-the-semm-configuration-manager-scripts"></a><span data-ttu-id="22f5a-167">创建或修改 SEMM Configuration Manager 脚本</span><span class="sxs-lookup"><span data-stu-id="22f5a-167">Create or modify the SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="22f5a-168">在设备上安装了所需的程序集后，在 SEMM 中注册设备和配置 Surface UEFI 的过程均已使用 PowerShell 脚本完成，并使用 Configuration Manager 部署为脚本应用程序。</span><span class="sxs-lookup"><span data-stu-id="22f5a-168">After the required assemblies have been installed on the devices, the process of enrolling the devices in SEMM and configuring Surface UEFI is done with PowerShell scripts and deployed as a script application with Configuration Manager.</span></span> <span data-ttu-id="22f5a-169">可以修改这些脚本以满足组织和环境的需要。</span><span class="sxs-lookup"><span data-stu-id="22f5a-169">These scripts can be modified to fit the needs of your organization and environment.</span></span> <span data-ttu-id="22f5a-170">例如，你可以为不同部门或角色中的托管 Surface 设备创建多个配置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-170">For example, you can create multiple configurations for managed Surface devices in different departments or roles.</span></span> <span data-ttu-id="22f5a-171">你可以从本文开头的 [先决条件](#prerequisites) 部分中的链接下载 SEMM 和 Configuration Manager 脚本的示例。</span><span class="sxs-lookup"><span data-stu-id="22f5a-171">You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.</span></span>

<span data-ttu-id="22f5a-172">要使用 Configuration Manager 执行 SEMM 部署，需要有两个主要脚本：</span><span class="sxs-lookup"><span data-stu-id="22f5a-172">There are two primary scripts you will need in order to perform a SEMM deployment with Configuration Manager:</span></span>

* <span data-ttu-id="22f5a-173">**ConfigureSEMM.ps1** -使用此脚本为 surface 设备创建配置程序包，使用所需的 surface UEFI 设置将指定的设置应用于 surface 设备，在 SEMM 中注册设备，并设置用于标识 SEMM 中的设备注册的注册表项。</span><span class="sxs-lookup"><span data-stu-id="22f5a-173">**ConfigureSEMM.ps1** – Use this script to create configuration packages for your Surface devices with your desired Surface UEFI settings to apply the specified settings to a Surface device, to enroll the device in SEMM, and to set a registry key used to identify the enrollment of the device in SEMM.</span></span>
* <span data-ttu-id="22f5a-174">**ResetSEMM.ps1** -使用此脚本在 surface 设备上重置 SEMM，该设备将其从 SEMM 中 unenrolls，并删除对 surface UEFI 设置的控制。</span><span class="sxs-lookup"><span data-stu-id="22f5a-174">**ResetSEMM.ps1** – Use this script to reset SEMM on a Surface device, which unenrolls it from SEMM and removes the control over Surface UEFI settings.</span></span>

<span data-ttu-id="22f5a-175">示例脚本包括有关如何设置 Surface UEFI 设置以及如何控制这些设置的权限的示例。</span><span class="sxs-lookup"><span data-stu-id="22f5a-175">The sample scripts include examples of how to set Surface UEFI settings and how to control permissions to those settings.</span></span> <span data-ttu-id="22f5a-176">可将这些设置修改为安全 Surface UEFI，并根据你的环境需求设置 Surface UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-176">These settings can be modified to secure Surface UEFI and set Surface UEFI settings according to the needs of your environment.</span></span> <span data-ttu-id="22f5a-177">本文的以下部分介绍了 ConfigureSEMM.ps1 脚本，并探索你需要对脚本进行的修改以满足你的要求。</span><span class="sxs-lookup"><span data-stu-id="22f5a-177">The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="22f5a-178">在将 SEMM Configuration Manager 脚本和导出的 SEMM 证书)  ( 文件添加到 Configuration Manager 之前，应将其放置在没有其他文件的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="22f5a-178">The SEMM Configuration Manager scripts and the exported SEMM certificate file (.pfx) should be placed in the same folder with no other files before they are added to Configuration Manager.</span></span>

### <a name="specify-certificate-and-package-names"></a><span data-ttu-id="22f5a-179">指定证书和程序包名称</span><span class="sxs-lookup"><span data-stu-id="22f5a-179">Specify certificate and package names</span></span>

<span data-ttu-id="22f5a-180">需要修改的脚本的第一个区域是指定和加载 SEMM 证书的部分，还指示 SurfaceUEFIManager 版本，以及 SEMM 配置包和 SEMM 重置程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="22f5a-180">The first region of the script that you need to modify is the portion that specifies and loads the SEMM certificate, and also indicates SurfaceUEFIManager version, and the names for the SEMM configuration package and SEMM reset package.</span></span> <span data-ttu-id="22f5a-181">证书名称和 SurfaceUEFIManager 版本在 ConfigureSEMM.ps1 脚本中的56至73行上指定。</span><span class="sxs-lookup"><span data-stu-id="22f5a-181">The certificate name and SurfaceUEFIManager version are specified on lines 56 through 73 in the ConfigureSEMM.ps1 script.</span></span>

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

<span data-ttu-id="22f5a-182">将 **$certName**变量的**FabrikamSEMMSample**值替换为 SEMM 证书文件在行58上的名称。</span><span class="sxs-lookup"><span data-stu-id="22f5a-182">Replace the **FabrikamSEMMSample.pfx** value for the **$certName** variable with the name of your SEMM Certificate file on line 58.</span></span> <span data-ttu-id="22f5a-183">该脚本将在你的脚本所在的文件夹中创建一个工作目录 (名为 Config) ，然后将证书文件复制到此工作目录。</span><span class="sxs-lookup"><span data-stu-id="22f5a-183">The script will create a working directory (named Config) in the folder where your scripts are located, and then copies the certificate file to this working directory.</span></span>

<span data-ttu-id="22f5a-184">所有者程序包和重置程序包也将在配置目录中创建，并保留由脚本生成的 Surface UEFI 设置和权限的配置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-184">Owner package and reset package will also be created in the Config directory and hold the configuration for Surface UEFI settings and permissions generated by the script.</span></span>

<span data-ttu-id="22f5a-185">在73行上，将 **$password** 变量的值从 **1234** 替换为证书文件的密码。</span><span class="sxs-lookup"><span data-stu-id="22f5a-185">On line 73, replace the value of the **$password** variable, from **1234** to the password for your certificate file.</span></span> <span data-ttu-id="22f5a-186">如果不需要密码，请删除 **1234** 文本。</span><span class="sxs-lookup"><span data-stu-id="22f5a-186">If a password is not required, delete the **1234** text.</span></span>

> [!Note]
> <span data-ttu-id="22f5a-187">在 SEMM 中注册设备需要证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="22f5a-187">The last two characters of the certificate thumbprint are required to enroll a device in SEMM.</span></span> <span data-ttu-id="22f5a-188">此脚本将向用户显示这些数字，允许用户或技术人员在系统重新引导之前记录这些数字，以在 SEMM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="22f5a-188">This script will display these digits to the user, which allows the user or technician to record these digits before the system reboots to enroll the device in SEMM.</span></span> <span data-ttu-id="22f5a-189">该脚本使用在150-155 行上找到的以下代码来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="22f5a-189">The script uses the following code, found on lines 150-155, to accomplish this.</span></span>

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

有权访问证书文件 ( .pfx) 的管理员可以随时通过在 CertMgr 中打开 .pfx 文件来读取指纹。 <span data-ttu-id="22f5a-191">若要查看 CertMgr 的指纹，请执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="22f5a-191">To view the thumbprint with CertMgr, follow this process:</span></span>

1. <span data-ttu-id="22f5a-192">右键单击 .pfx 文件，然后选择 " **打开**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-192">Right-click the .pfx file, and then select **Open**.</span></span>
2. <span data-ttu-id="22f5a-193">展开 "导航窗格" 中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f5a-193">Expand the folder in the navigation pane.</span></span>
3. <span data-ttu-id="22f5a-194">选择 " **证书**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-194">Select **Certificates**.</span></span>
4. <span data-ttu-id="22f5a-195">在主窗格中右键单击您的证书，然后选择 " **打开**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-195">Right-click your certificate in the main pane, and then select **Open**.</span></span>
5. <span data-ttu-id="22f5a-196">选择 " **详细信息** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="22f5a-196">Select the **Details** tab.</span></span>
6. <span data-ttu-id="22f5a-197">只有在 "**显示**" 下拉菜单中选择 "**全部**" 或 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-197">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
7. <span data-ttu-id="22f5a-198">选择 "字段 **指纹**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-198">Select the field **Thumbprint**.</span></span>

> [!NOTE]
> <span data-ttu-id="22f5a-199">还必须在 ResetSEMM.ps1 脚本的此部分中输入 SEMM 证书名称和密码，以使 Configuration Manager 能够通过卸载操作从设备中删除 SEMM。</span><span class="sxs-lookup"><span data-stu-id="22f5a-199">The SEMM certificate name and password must also be entered in this section of the ResetSEMM.ps1 script to enable Configuration Manager to remove SEMM from the device with the uninstall action.</span></span>

### <a name="configure-permissions"></a><span data-ttu-id="22f5a-200">配置权限</span><span class="sxs-lookup"><span data-stu-id="22f5a-200">Configure permissions</span></span>

<span data-ttu-id="22f5a-201">你将在其中指定 Surface UEFI 配置的脚本的第一个区域是 " **配置权限** " 区域。</span><span class="sxs-lookup"><span data-stu-id="22f5a-201">The first region of the script where you will specify the configuration for Surface UEFI is the **Configure Permissions** region.</span></span> <span data-ttu-id="22f5a-202">此区域从示例脚本中的第210行开始，注释 **# 配置权限** 并继续到第247行。</span><span class="sxs-lookup"><span data-stu-id="22f5a-202">This region begins at line 210 in the sample script with the comment **# Configure Permissions** and continues to line 247.</span></span> <span data-ttu-id="22f5a-203">以下代码片段首先将权限设置为所有 Surface UEFI 设置，以便它们仅可通过 SEMM 进行修改，然后添加显式权限，以允许本地用户修改 Surface UEFI 密码、TPM 和前置和后置摄像头。</span><span class="sxs-lookup"><span data-stu-id="22f5a-203">The following code fragment first sets permissions to all Surface UEFI settings so that they may be modified by SEMM only, then adds explicit permissions to allow the local user to modify the Surface UEFI password, TPM, and front and rear cameras.</span></span>

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

<span data-ttu-id="22f5a-204">每个 **$uefiV 2** 变量通过设置名称或 ID 来标识 Surface UEFI 设置，然后将权限配置为以下值之一：</span><span class="sxs-lookup"><span data-stu-id="22f5a-204">Each **$uefiV2** variable identifies a Surface UEFI setting by setting name or ID, and then configures the permissions to one of the following values:</span></span>

* <span data-ttu-id="22f5a-205">**$ownerOnly** –修改此设置的权限仅授予 SEMM。</span><span class="sxs-lookup"><span data-stu-id="22f5a-205">**$ownerOnly** – Permission to modify this setting is granted only to SEMM.</span></span>
* <span data-ttu-id="22f5a-206">**$ownerAndLocalUser** –将权限修改此设置的权限授予本地用户启动到 Surface UEFI 以及 SEMM。</span><span class="sxs-lookup"><span data-stu-id="22f5a-206">**$ownerAndLocalUser** – Permission to modify this setting is granted to a local user booting to Surface UEFI, as well as to SEMM.</span></span>

<span data-ttu-id="22f5a-207">在本文的 " [设置名称和 id](#settings-names-and-ids) " 部分中，可以找到有关 Surface UEFI 的可用设置名称和 id 的信息。</span><span class="sxs-lookup"><span data-stu-id="22f5a-207">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.</span></span>

### <a name="configure-settings"></a><span data-ttu-id="22f5a-208">配置设置</span><span class="sxs-lookup"><span data-stu-id="22f5a-208">Configure settings</span></span>

<span data-ttu-id="22f5a-209">你将在其中指定 Surface UEFI 配置的脚本的第二个区域是 ConfigureSEMM.ps1 脚本的 " **配置设置** " 区域，该区域配置是启用还是禁用每个设置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-209">The second region of the script where you will specify the configuration for Surface UEFI is the **Configure Settings** region of the ConfigureSEMM.ps1 script, which configures whether each setting is enabled or disabled.</span></span> <span data-ttu-id="22f5a-210">示例脚本包括将所有设置设置为其默认值的说明。</span><span class="sxs-lookup"><span data-stu-id="22f5a-210">The sample script includes instructions to set all settings to their default values.</span></span> <span data-ttu-id="22f5a-211">然后，该脚本将提供用于禁用 PXE 启动的 IPv6 的显式说明，并使 Surface UEFI 管理员密码保持不变。</span><span class="sxs-lookup"><span data-stu-id="22f5a-211">The script then provides explicit instructions to disable IPv6 for PXE Boot and to leave the Surface UEFI Administrator password unchanged.</span></span> <span data-ttu-id="22f5a-212">可以在示例脚本的第291至第335行中找到该区域（以 **# 配置设置** 注释开头）。</span><span class="sxs-lookup"><span data-stu-id="22f5a-212">You can find this region beginning with the **# Configure Settings** comment at line 291 through line 335 in the sample script.</span></span> <span data-ttu-id="22f5a-213">区域显示如下。</span><span class="sxs-lookup"><span data-stu-id="22f5a-213">The region appears as follows.</span></span>

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

<span data-ttu-id="22f5a-214">与在脚本的 " **配置权限** " 部分中设置的权限一样，每个 Surface UEFI 设置的配置均通过定义 **$uefiV 2** 变量来执行。</span><span class="sxs-lookup"><span data-stu-id="22f5a-214">Like the permissions set in the **Configure Permissions** section of the script, the configuration of each Surface UEFI setting is performed by defining the **$uefiV2** variable.</span></span> <span data-ttu-id="22f5a-215">对于定义 **$uefiV 2** 变量的每一行，Surface UEFI 设置通过设置名称或 ID 以及已配置的值设置为 " **启用** " 或 " **已禁用**" 来标识。</span><span class="sxs-lookup"><span data-stu-id="22f5a-215">For each line defining the **$uefiV2** variable, a Surface UEFI setting is identified by setting name or ID and the configured value is set to **Enabled** or **Disabled**.</span></span>

<span data-ttu-id="22f5a-216">如果你不想更改 Surface UEFI 设置的配置，例如，以确保不会通过将所有 Surface UEFI 设置重置为默认值的操作清除 Surface UEFI 管理员密码。你可以使用 \*\*ClearConfiguredValue ( # B1 \*\* 来强制更改此设置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-216">If you do not want to alter the configuration of a Surface UEFI setting, for example to ensure that the Surface UEFI administrator password is not cleared by the action of resetting all Surface UEFI settings to their default, you can use **ClearConfiguredValue()** to enforce that this setting will not be altered.</span></span> <span data-ttu-id="22f5a-217">在示例脚本中，在323行上使用它来防止清除 Surface UEFI 管理员密码，该密码在示例脚本中通过其设置 ID **501**进行标识。</span><span class="sxs-lookup"><span data-stu-id="22f5a-217">In the sample script, this is used on line 323 to prevent the clearing of the Surface UEFI Administrator password, identified in the sample script by its setting ID, **501**.</span></span>

<span data-ttu-id="22f5a-218">在本文后面的 " [设置名称和 id](#settings-names-and-ids) " 部分中，可以找到有关 Surface UEFI 的可用设置名称和 id 的信息。</span><span class="sxs-lookup"><span data-stu-id="22f5a-218">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.</span></span>

### <a name="settings-registry-key"></a><span data-ttu-id="22f5a-219">设置注册表项</span><span class="sxs-lookup"><span data-stu-id="22f5a-219">Settings registry key</span></span>

<span data-ttu-id="22f5a-220">若要识别配置管理器的已注册系统，ConfigureSEMM.ps1 脚本将编写注册表项，这些注册表项可用于识别已注册的系统（已使用 SEMM 配置脚本进行安装）。</span><span class="sxs-lookup"><span data-stu-id="22f5a-220">To identify enrolled systems for Configuration Manager, the ConfigureSEMM.ps1 script writes registry keys that can be used to identify enrolled systems as having been installed with the SEMM configuration script.</span></span> <span data-ttu-id="22f5a-221">可以在以下位置找到这些注册表项。</span><span class="sxs-lookup"><span data-stu-id="22f5a-221">These keys can be found at the following location.</span></span>

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

<span data-ttu-id="22f5a-222">以下代码片段在380-477 行上找到，用于写入这些注册表项。</span><span class="sxs-lookup"><span data-stu-id="22f5a-222">The following code fragment, found on lines 380-477, is used to write these registry keys.</span></span>

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <a name="settings-names-and-ids"></a><span data-ttu-id="22f5a-223">设置名称和 Id</span><span class="sxs-lookup"><span data-stu-id="22f5a-223">Settings names and IDs</span></span>

<span data-ttu-id="22f5a-224">若要为 Surface UEFI 设置配置 Surface UEFI 设置或权限，必须通过其设置名称或设置 ID 引用每个设置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-224">To configure Surface UEFI settings or permissions for Surface UEFI settings, you must refer to each setting by either its setting name or setting ID.</span></span> <span data-ttu-id="22f5a-225">对于 Surface UEFI 的每个新更新，可能会添加新设置。</span><span class="sxs-lookup"><span data-stu-id="22f5a-225">With each new update for Surface UEFI, new settings may be added.</span></span> <span data-ttu-id="22f5a-226">获取 Surface 设备上可用的设置的完整列表以及设置名称和设置 Id 的最佳方式是在[IT 下载的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)中使用来自 SEMM_Powershell.zip 的 ShowSettingsOptions.ps1 脚本</span><span class="sxs-lookup"><span data-stu-id="22f5a-226">The best way to get a complete list of the settings available on a Surface device, along with the settings name and settings IDs, is to use the ShowSettingsOptions.ps1 script from SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span> 

<span data-ttu-id="22f5a-227">运行 ShowSettingsOptions.ps1 的计算机必须安装有 Microsoft Surface UEFI 管理器，但该脚本不需要 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="22f5a-227">The computer where ShowSettingsOptions.ps1 is run must have Microsoft Surface UEFI Manager installed, but the script does not require a Surface device.</span></span>


## <a name="deploy-semm-configuration-manager-scripts"></a><span data-ttu-id="22f5a-228">部署 SEMM Configuration Manager 脚本</span><span class="sxs-lookup"><span data-stu-id="22f5a-228">Deploy SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="22f5a-229">准备好脚本以在客户端设备上配置和启用 SEMM 后，下一步是将这些脚本作为配置管理器中的应用程序添加。</span><span class="sxs-lookup"><span data-stu-id="22f5a-229">After your scripts are prepared to configure and enable SEMM on the client device, the next step is to add these scripts as an application in Configuration Manager.</span></span> <span data-ttu-id="22f5a-230">在打开配置管理器之前，请确保以下文件位于不包含其他文件的共享文件夹中：</span><span class="sxs-lookup"><span data-stu-id="22f5a-230">Before you open Configuration Manager, ensure that the following files are in a shared folder that does not include other files:</span></span>

* <span data-ttu-id="22f5a-231">ConfigureSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="22f5a-231">ConfigureSEMM.ps1</span></span>
* <span data-ttu-id="22f5a-232">ResetSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="22f5a-232">ResetSEMM.ps1</span></span>
* <span data-ttu-id="22f5a-233">您的 SEMM 证书 (例如 SEMMCertificate) </span><span class="sxs-lookup"><span data-stu-id="22f5a-233">Your SEMM certificate (for example SEMMCertificate.pfx)</span></span>

<span data-ttu-id="22f5a-234">SEMM Configuration Manager 脚本将作为脚本应用程序添加到 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="22f5a-234">The SEMM Configuration Manager scripts will be added to Configuration Manager as a script application.</span></span> <span data-ttu-id="22f5a-235">通过 ConfigureSEMM.ps1 安装 SEMM 的命令如下所示。</span><span class="sxs-lookup"><span data-stu-id="22f5a-235">The command to install SEMM with ConfigureSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

<span data-ttu-id="22f5a-236">用 ResetSEMM.ps1 卸载 SEMM 的命令如下所示。</span><span class="sxs-lookup"><span data-stu-id="22f5a-236">The command to uninstall SEMM with ResetSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ResetSEMM.ps1"`

<span data-ttu-id="22f5a-237">若要将 SEMM Configuration Manager 脚本作为应用程序添加到 Configuration Manager，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="22f5a-237">To add the SEMM Configuration Manager scripts to Configuration Manager as an application, use the following process:</span></span>

1. <span data-ttu-id="22f5a-238">使用本文前面的 [部署 Microsoft SURFACE UEFI 管理器](#deploy-microsoft-surface-uefi-manager) 部分中的步骤1至步骤5开始创建应用程序向导。</span><span class="sxs-lookup"><span data-stu-id="22f5a-238">Start the Create Application Wizard using Step 1 through Step 5 from the [Deploy Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) section earlier in this article.</span></span>

2. <span data-ttu-id="22f5a-239">按如下方式继续执行 "创建应用程序" 向导：</span><span class="sxs-lookup"><span data-stu-id="22f5a-239">Proceed through The Create Application Wizard as follows:</span></span>

   - <span data-ttu-id="22f5a-240">**常规** –选择 **"手动指定应用程序信息**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-240">**General** – Select **Manually specify the application information**, and then select **Next**.</span></span>

   - <span data-ttu-id="22f5a-241">**常规信息** -为应用程序 (输入一个名称，例如 SEMM) 和你需要的任何其他信息，如 publisher、version 或此页面上的评论。</span><span class="sxs-lookup"><span data-stu-id="22f5a-241">**General Information** – Enter a name for the application (for example SEMM) and any other information you want such as publisher, version, or comments on this page.</span></span> <span data-ttu-id="22f5a-242">选择 " **下一步** " 继续。</span><span class="sxs-lookup"><span data-stu-id="22f5a-242">Select **Next** to proceed.</span></span>

   - <span data-ttu-id="22f5a-243">**应用程序目录** -此页面上的字段可以保留其默认值。</span><span class="sxs-lookup"><span data-stu-id="22f5a-243">**Application Catalog** – The fields on this page can be left with their default values.</span></span> <span data-ttu-id="22f5a-244">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="22f5a-244">Select **Next**.</span></span>

   - <span data-ttu-id="22f5a-245">**部署类型** -选择 " **添加** " 以启动 "创建部署类型" 向导。</span><span class="sxs-lookup"><span data-stu-id="22f5a-245">**Deployment Types** – Select **Add** to start the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="22f5a-246">继续执行 "创建部署类型" 向导的步骤，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22f5a-246">Proceed through the steps of the Create Deployment Type Wizard, as follows:</span></span>

     * <span data-ttu-id="22f5a-247">**常规**-从 "**类型**" 下拉菜单中选择 "**脚本安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-247">**General** – Select **Script Installer** from the **Type** drop-down menu.</span></span> <span data-ttu-id="22f5a-248">将自动选择 " **手动指定部署类型信息** " 选项。</span><span class="sxs-lookup"><span data-stu-id="22f5a-248">The **Manually specify the deployment type information** option will automatically be selected.</span></span> <span data-ttu-id="22f5a-249">选择 " **下一步** " 继续。</span><span class="sxs-lookup"><span data-stu-id="22f5a-249">Select **Next** to proceed.</span></span>
     * <span data-ttu-id="22f5a-250">**常规信息** -为部署类型 (输入名称，例如 SEMM 配置脚本) ，然后选择 " **下一步** " 继续。</span><span class="sxs-lookup"><span data-stu-id="22f5a-250">**General Information** – Enter a name for the deployment type (for example SEMM Configuration Scripts), and then select **Next** to continue.</span></span>
     * <span data-ttu-id="22f5a-251">**内容**–选择 "**内容位置**" 字段旁边的 "**浏览**"，然后选择 SEMM Configuration Manager 脚本所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f5a-251">**Content** – Select **Browse** next to the **Content Location** field, and then select the folder where your SEMM Configuration Manager scripts are located.</span></span> <span data-ttu-id="22f5a-252">在 " **安装程序** " 字段中，键入本文前面的 [安装命令](#deploy-semm-configuration-manager-scripts) 。</span><span class="sxs-lookup"><span data-stu-id="22f5a-252">In the **Installation Program** field, type the [installation command](#deploy-semm-configuration-manager-scripts) found earlier in this article.</span></span> <span data-ttu-id="22f5a-253">在 " **卸载程序** " 字段中，输入在本文前面部分中找到的 [卸载命令](#deploy-semm-configuration-manager-scripts) (图 2) 中所示。</span><span class="sxs-lookup"><span data-stu-id="22f5a-253">In the **Uninstall Program** field, enter the [uninstallation command](#deploy-semm-configuration-manager-scripts) found earlier in this article (shown in Figure 2).</span></span> <span data-ttu-id="22f5a-254">选择 " **下一步** " 转到下一页。</span><span class="sxs-lookup"><span data-stu-id="22f5a-254">Select **Next** to move to the next page.</span></span>
    
     ![将 SEMM Configuration Manager 脚本设置为 "安装和卸载" 命令](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *<span data-ttu-id="22f5a-256">图 2.</span><span class="sxs-lookup"><span data-stu-id="22f5a-256">Figure 2.</span></span> <span data-ttu-id="22f5a-257">将 SEMM Configuration Manager 脚本设置为 "安装和卸载" 命令</span><span class="sxs-lookup"><span data-stu-id="22f5a-257">Set the SEMM Configuration Manager scripts as the install and uninstall commands</span></span>*

     * <span data-ttu-id="22f5a-258">**检测方法** -选择 **add 子句** 以添加 SEMM Configuration Manager 脚本注册表项检测规则。</span><span class="sxs-lookup"><span data-stu-id="22f5a-258">**Detection Method** – Select **Add Clause** to add the SEMM Configuration Manager script registry key detection rule.</span></span> <span data-ttu-id="22f5a-259">将显示 " **检测规则** " 窗口，如图3所示。</span><span class="sxs-lookup"><span data-stu-id="22f5a-259">The **Detection Rule** window is displayed, as shown in Figure 3.</span></span> <span data-ttu-id="22f5a-260">使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="22f5a-260">Use the following settings:</span></span>

       - <span data-ttu-id="22f5a-261">从 "**设置类型**" 下拉菜单中选择 "**注册表**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-261">Select **Registry** from the **Setting Type** drop-down menu.</span></span>
       - <span data-ttu-id="22f5a-262">从 "**配置单元**" 下拉菜单中选择 " **HKEY_LOCAL_MACHINE** "。</span><span class="sxs-lookup"><span data-stu-id="22f5a-262">Select **HKEY_LOCAL_MACHINE** from the **Hive** drop-down menu.</span></span>
       - <span data-ttu-id="22f5a-263">在 "**键**" 字段中输入**SOFTWARE\Microsoft\Surface\SEMM** 。</span><span class="sxs-lookup"><span data-stu-id="22f5a-263">Enter **SOFTWARE\Microsoft\Surface\SEMM** in the **Key** field.</span></span>
       - <span data-ttu-id="22f5a-264">在 "**值**" 字段中输入**CertName** 。</span><span class="sxs-lookup"><span data-stu-id="22f5a-264">Enter **CertName** in the **Value** field.</span></span>
       - <span data-ttu-id="22f5a-265">从 "**数据类型**" 下拉菜单中选择 "**字符串**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-265">Select **String** from the **Data Type** drop-down menu.</span></span>
       - <span data-ttu-id="22f5a-266">选择 " **此注册表设置必须满足以下规则才能指示此应用程序按钮的存在"** 。</span><span class="sxs-lookup"><span data-stu-id="22f5a-266">Select the **This registry setting must satisfy the following rule to indicate the presence of this application** button.</span></span>
       - <span data-ttu-id="22f5a-267">在 " **值** " 字段中输入你在脚本的58行中输入的证书的名称。</span><span class="sxs-lookup"><span data-stu-id="22f5a-267">Enter the name of the certificate you entered in line 58 of the script in the **Value** field.</span></span>
       - <span data-ttu-id="22f5a-268">选择 **"确定"** 关闭 " **检测规则** " 窗口。</span><span class="sxs-lookup"><span data-stu-id="22f5a-268">Select **OK** to close the **Detection Rule** window.</span></span>

     ![使用注册表项识别已注册的设备 SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *<span data-ttu-id="22f5a-270">图 3.</span><span class="sxs-lookup"><span data-stu-id="22f5a-270">Figure 3.</span></span> <span data-ttu-id="22f5a-271">使用注册表项识别已注册的设备 SEMM</span><span class="sxs-lookup"><span data-stu-id="22f5a-271">Use a registry key to identify devices enrolled in SEMM</span></span>*

     * <span data-ttu-id="22f5a-272">选择 " **下一步** " 继续下一页。</span><span class="sxs-lookup"><span data-stu-id="22f5a-272">Select **Next** to proceed to the next page.</span></span>
     
     * <span data-ttu-id="22f5a-273">**用户体验**–从 "**安装行为**" 下拉菜单中选择 "**为系统安装**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-273">**User Experience** – Select **Install for system** from the **Installation Behavior** drop-down menu.</span></span> <span data-ttu-id="22f5a-274">如果你希望你的用户自行录制和输入证书指纹，请仅将登录要求设置为 " **仅在用户登录时**"。</span><span class="sxs-lookup"><span data-stu-id="22f5a-274">If you want your users to record and enter the certificate thumbprint themselves, leave the logon requirement set to **Only when a user is logged on**.</span></span> <span data-ttu-id="22f5a-275">如果希望管理员为用户输入指纹，并且用户不需要查看指纹，请从 "**登录要求**" 下拉菜单中选择**用户是否已登录**。</span><span class="sxs-lookup"><span data-stu-id="22f5a-275">If you want your administrators to enter the thumbprint for users and the users do not need to see the thumbprint, select **Whether or not a user is logged on** from the **Logon Requirement** drop-down menu.</span></span>

     * <span data-ttu-id="22f5a-276">**要求** -在尝试启用 SEMM 之前，ConfigureSEMM.ps1 脚本会自动验证设备是否为 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="22f5a-276">**Requirements** – The ConfigureSEMM.ps1 script automatically verifies that the device is a Surface device before attempting to enable SEMM.</span></span> <span data-ttu-id="22f5a-277">但是，如果你打算将此脚本应用程序部署到具有要使用 SEMM 托管的设备之外的设备，你可以在此处添加要求，以确保此应用仅在要使用 SEMM 管理的 Surface 设备或设备上运行。</span><span class="sxs-lookup"><span data-stu-id="22f5a-277">However, if you intend to deploy this script application to a collection with devices other than those to be managed with SEMM, you could add requirements here to ensure this application would run only on Surface devices or devices you intend to manage with SEMM.</span></span> <span data-ttu-id="22f5a-278">选择 " **下一步** " 继续。</span><span class="sxs-lookup"><span data-stu-id="22f5a-278">Select **Next** to continue.</span></span>
     
     * <span data-ttu-id="22f5a-279">**相关性** -选择 " **添加** " 以打开 " **添加相关性** " 窗口。</span><span class="sxs-lookup"><span data-stu-id="22f5a-279">**Dependencies** – Select **Add** to open the **Add Dependency** window.</span></span>

       * <span data-ttu-id="22f5a-280">选择 " **添加** " 以打开 " **指定所需应用程序** " 窗口。</span><span class="sxs-lookup"><span data-stu-id="22f5a-280">Select **Add** to open the **Specify Required Application** window.</span></span>

          - <span data-ttu-id="22f5a-281">在 " **依赖项组名称** " (字段中输入 SEMM 依赖项的名称，例如， *SEMM 程序集*) 。</span><span class="sxs-lookup"><span data-stu-id="22f5a-281">Enter a name for the SEMM dependencies in the **Dependency Group Name** field (for example, *SEMM Assemblies*).</span></span>

          - <span data-ttu-id="22f5a-282">从**可用应用程序**和 MSI 部署类型列表中选择 " **Microsoft Surface UEFI 管理器**"，然后选择 **"确定"** 以关闭 "**指定所需的应用程序**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="22f5a-282">Select **Microsoft Surface UEFI Manager** from the list of **Available Applications** and the MSI deployment type, and then select **OK** to close the **Specify Required Application** window.</span></span>
          
         *   <span data-ttu-id="22f5a-283">如果你希望在使用 Configuration Manager 脚本启用 SEMM 时在设备上自动安装 Microsoft Surface UEFI 管理器，请保持 " **自动安装** " 复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="22f5a-283">Keep the **Auto Install** check box selected if you want Microsoft Surface UEFI Manager installed automatically on devices when you attempt to enable SEMM with the Configuration Manager scripts.</span></span> <span data-ttu-id="22f5a-284">选择 **"确定"** 以关闭 " **添加依赖关系** " 窗口。</span><span class="sxs-lookup"><span data-stu-id="22f5a-284">Select **OK** to close the **Add Dependency** window.</span></span>

     * <span data-ttu-id="22f5a-285">选择 " **下一步** " 继续。</span><span class="sxs-lookup"><span data-stu-id="22f5a-285">Select **Next** to proceed.</span></span>
     
     * <span data-ttu-id="22f5a-286">**摘要** -在整个 "创建部署类型" 向导中输入的信息将显示在此页面上。</span><span class="sxs-lookup"><span data-stu-id="22f5a-286">**Summary** – The information you have entered throughout the Create Deployment Type wizard is displayed on this page.</span></span> <span data-ttu-id="22f5a-287">选择 " **下一步** " 以确认您的选择。</span><span class="sxs-lookup"><span data-stu-id="22f5a-287">Select **Next** to confirm your selections.</span></span>
     
     * <span data-ttu-id="22f5a-288">**进度** –为 SEMM 脚本应用程序添加的进度栏和状态将显示在此页面上。</span><span class="sxs-lookup"><span data-stu-id="22f5a-288">**Progress** – A progress bar and status as the deployment type is added for the SEMM script application is displayed on this page.</span></span>
     
     * <span data-ttu-id="22f5a-289">**完成** –当过程完成时，将显示 "创建部署类型" 的确认。</span><span class="sxs-lookup"><span data-stu-id="22f5a-289">**Completion** – Confirmation of the deployment type creation is displayed when the process is complete.</span></span> <span data-ttu-id="22f5a-290">选择 " **关闭** " 完成 "创建部署类型" 向导。</span><span class="sxs-lookup"><span data-stu-id="22f5a-290">Select **Close** to finish the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="22f5a-291">**摘要** -显示在整个 "创建应用程序向导" 中输入的信息。</span><span class="sxs-lookup"><span data-stu-id="22f5a-291">**Summary** – The information that you entered throughout the Create Application Wizard is displayed.</span></span> <span data-ttu-id="22f5a-292">选择 " **下一步** " 创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="22f5a-292">Select **Next** to create the application.</span></span>

   - <span data-ttu-id="22f5a-293">**进度** –将应用程序添加到软件库时，进度栏和状态会显示在此页面上。</span><span class="sxs-lookup"><span data-stu-id="22f5a-293">**Progress** – A progress bar and status as the application is added to the Software Library is displayed on this page.</span></span>

   - <span data-ttu-id="22f5a-294">**完成** –当应用程序创建过程完成时，将显示对成功创建应用程序创建的确认。</span><span class="sxs-lookup"><span data-stu-id="22f5a-294">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="22f5a-295">选择 " **关闭** " 以完成创建应用程序向导。</span><span class="sxs-lookup"><span data-stu-id="22f5a-295">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="22f5a-296">在 Configuration Manager 的软件库中提供脚本应用程序后，你可以使用你准备对设备或集合的脚本分发和部署 SEMM。</span><span class="sxs-lookup"><span data-stu-id="22f5a-296">After the script application is available in the Software Library of Configuration Manager, you can distribute and deploy SEMM using the scripts you prepared to devices or collections.</span></span> <span data-ttu-id="22f5a-297">如果你已将 Microsoft Surface UEFI 管理器程序集配置为将自动安装的依赖关系，则可以通过单个步骤部署 SEMM。</span><span class="sxs-lookup"><span data-stu-id="22f5a-297">If you have configured the Microsoft Surface UEFI Manager assemblies as a dependency that will be automatically installed, you can deploy SEMM in a single step.</span></span> <span data-ttu-id="22f5a-298">如果未将程序集配置为依赖项，则必须在启用 SEMM 之前将其安装在要管理的设备上。</span><span class="sxs-lookup"><span data-stu-id="22f5a-298">If you have not configured the assemblies as a dependency, they must be installed on the devices you intend to manage before you enable SEMM.</span></span>

<span data-ttu-id="22f5a-299">使用此脚本应用程序和最终用户可见的配置部署 SEMM 时，将启动 PowerShell 脚本，并且该证书的指纹将由 PowerShell 窗口显示。</span><span class="sxs-lookup"><span data-stu-id="22f5a-299">When you deploy SEMM using this script application and with a configuration that is visible to the end user, the PowerShell script will start and the thumbprint for the certificate will be displayed by the PowerShell window.</span></span> <span data-ttu-id="22f5a-300">你可以让你的用户记录此指纹，并在设备重启后根据 Surface UEFI 的提示输入它。</span><span class="sxs-lookup"><span data-stu-id="22f5a-300">You can have your users record this thumbprint and enter it when prompted by Surface UEFI after the device reboots.</span></span>

<span data-ttu-id="22f5a-301">或者，你可以将应用程序安装配置为自动重新启动，并以不可见的的用户的安装。</span><span class="sxs-lookup"><span data-stu-id="22f5a-301">Alternatively, you can configure the application installation to reboot automatically and to install invisibly to the user.</span></span> <span data-ttu-id="22f5a-302">在此方案中，技术人员在重新启动时需要在每台设备上输入指纹。</span><span class="sxs-lookup"><span data-stu-id="22f5a-302">In this scenario, a technician will be required to enter the thumbprint on each device as it reboots.</span></span> <span data-ttu-id="22f5a-303">任何有权访问证书文件的技术人员都可以通过使用 CertMgr 查看证书来读取指纹。</span><span class="sxs-lookup"><span data-stu-id="22f5a-303">Any technician with access to the certificate file can read the thumbprint by viewing the certificate with CertMgr.</span></span> <span data-ttu-id="22f5a-304">有关查看带有 CertMgr 的指纹的说明， [请参见创建或修改本文的 SEMM Configuration Manager 脚本](#create-or-modify-the-semm-configuration-manager-scripts) 部分。</span><span class="sxs-lookup"><span data-stu-id="22f5a-304">Instructions for viewing the thumbprint with CertMgr are in the [Create or modify the SEMM Configuration Manager scripts](#create-or-modify-the-semm-configuration-manager-scripts) section of this article.</span></span>

<span data-ttu-id="22f5a-305">从使用 Configuration manager 使用 "Configuration Manager" 部署的设备中删除 SEMM 与使用 Configuration Manager 卸载应用程序一样简单。</span><span class="sxs-lookup"><span data-stu-id="22f5a-305">Removal of SEMM from a device deployed with Configuration Manager using these scripts is as easy as uninstalling the application with Configuration Manager.</span></span> <span data-ttu-id="22f5a-306">此操作将启动 ResetSEMM.ps1 脚本，并使用在 SEMM 部署期间使用的相同证书文件正确 unenrolls 设备。</span><span class="sxs-lookup"><span data-stu-id="22f5a-306">This action starts the ResetSEMM.ps1 script and properly unenrolls the device with the same certificate file that was used during the deployment of SEMM.</span></span>

> [!NOTE]
> <span data-ttu-id="22f5a-307">Microsoft Surface 建议你仅在需要取消注册设备时创建重置程序包。</span><span class="sxs-lookup"><span data-stu-id="22f5a-307">Microsoft Surface recommends that you create reset packages only when you need to unenroll a device.</span></span> <span data-ttu-id="22f5a-308">这些重置程序包通常仅对一个设备有效，由其序列号标识。</span><span class="sxs-lookup"><span data-stu-id="22f5a-308">These reset packages are typically valid for only one device, identified by its serial number.</span></span> <span data-ttu-id="22f5a-309">但是，你可以创建一个通用重置程序包，该程序包适用于使用此证书在 SEMM 中注册的任何设备。</span><span class="sxs-lookup"><span data-stu-id="22f5a-309">You can, however, create a universal reset package that would work for any device enrolled in SEMM with this certificate.</span></span>
> 
> <span data-ttu-id="22f5a-310">强烈建议你在 SEMM 中使用注册设备时所使用的证书，确保你的通用重置程序包。</span><span class="sxs-lookup"><span data-stu-id="22f5a-310">We strongly recommend that you protect your universal reset package as carefully as the certificate you used to enroll devices in SEMM.</span></span> <span data-ttu-id="22f5a-311">请记住，与证书本身一样，此通用重置程序包可用于从 SEMM 中取消组织的任何 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="22f5a-311">Please remember that, just like the certificate itself, this universal reset package can be used to unenroll any of your organization’s Surface devices from SEMM.</span></span>
> 
> <span data-ttu-id="22f5a-312">安装重置程序包时， (LSV) 的最低支持值将重置为值1。</span><span class="sxs-lookup"><span data-stu-id="22f5a-312">When you install a reset package, the Lowest Supported Value (LSV) is reset to a value of 1.</span></span> <span data-ttu-id="22f5a-313">你可以使用现有配置包重新注册设备。</span><span class="sxs-lookup"><span data-stu-id="22f5a-313">You can reenroll a device by using an existing configuration package.</span></span> <span data-ttu-id="22f5a-314">在获取所有权之前，设备将提示提供证书指纹。</span><span class="sxs-lookup"><span data-stu-id="22f5a-314">The device will prompt for the certificate thumbprint before ownership is taken.</span></span>
> 
> <span data-ttu-id="22f5a-315">出于此原因，SEMM 中的设备的 reenrollment 将要求在该设备上创建和安装新程序包。</span><span class="sxs-lookup"><span data-stu-id="22f5a-315">For this reason, the reenrollment of a device in SEMM would require a new package to be created and installed on that device.</span></span> <span data-ttu-id="22f5a-316">由于此操作是新的注册，并且在已注册在 SEMM 中的设备上不会更改配置，因此在获取所有权之前，设备将提示提供证书指纹。</span><span class="sxs-lookup"><span data-stu-id="22f5a-316">Because this action is a new enrollment and not a change in configuration on a device already enrolled in SEMM, the device will prompt for the certificate thumbprint before ownership is taken.</span></span>

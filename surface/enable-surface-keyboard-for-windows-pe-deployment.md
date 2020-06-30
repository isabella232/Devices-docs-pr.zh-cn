---
title: 如何在 MDT 部署期间启用 Surface 笔记本电脑键盘
description: 使用 MDT 将 Windows 10 部署到 Surface 笔记本电脑时，需要导入键盘驱动程序以在 Windows PE 环境中使用。
keywords: windows 10 surface，自动化，自定义，mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830791"
---
# <span data-ttu-id="0a4cb-104">如何在 MDT 部署期间启用 Surface 笔记本电脑键盘</span><span class="sxs-lookup"><span data-stu-id="0a4cb-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="0a4cb-105">本文讨论使用 Microsoft 部署工具包（MDT）的部署方法。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="0a4cb-106">你还可以将此信息应用到其他部署方法。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="0a4cb-107">在大多数类型的 Surface 设备上，键盘应在 "精简触控安装（LTI）" 期间工作。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="0a4cb-108">但是，Surface 膝上型电脑需要其他一些驱动程序才能启用键盘。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="0a4cb-109">对于 Surface 笔记本电脑（第1代）和 Surface 膝上型电脑2设备，你必须准备文件夹结构和选择配置文件，以便你可以指定在 LTI 的 Windows 预安装环境（Windows PE）阶段使用的键盘驱动程序。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="0a4cb-110">有关此文件夹结构的详细信息，请参阅[使用 MDT 部署 Windows 10 映像：步骤5：准备驱动程序存储库](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!NOTE]
> <span data-ttu-id="0a4cb-111">由于驱动程序冲突，当前不支持在同一 Windows PE 启动实例中添加 Surface 笔记本2和 Surface 笔记本3键盘驱动程序。请改用单独的实例。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-111">It is currently not supported to add Surface Laptop 2 and Surface Laptop 3 keyboard drivers in the same Windows PE boot instance due to a driver conflict; use separate instances instead.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a4cb-112">如果你要将 Windows 10 映像部署到具有预装了 Windows 10 的 S 模式的 Surface 笔记本电脑，请参阅 KB [4032347，使用预安装的 windows 10 s 模式将 windows 部署到 surface 设备时遇到问题](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-112">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="0a4cb-113">若要将键盘驱动程序添加到选择配置文件，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-113">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="0a4cb-114">从相应的位置下载最新的 Surface 笔记本电脑 MSI 文件：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-114">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="0a4cb-115">Surface 笔记本电脑（第1代）驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="0a4cb-115">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="0a4cb-116">Surface 膝上型电脑2驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="0a4cb-116">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="0a4cb-117">带有英特尔处理器驱动程序和固件的 Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="0a4cb-117">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="0a4cb-118">将 Surface 膝上型电脑 MSI 文件的内容提取到您可以轻松找到的文件夹（例如，c：\ surface_laptop_drivers）。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-118">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="0a4cb-119">若要提取内容，请打开提升的命令提示符窗口，然后运行以下示例中的命令：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-119">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="0a4cb-120">打开部署工作台并展开 "**部署共享**" 节点和部署共享，然后导航到 " **WindowsPEX64** " 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-120">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![显示部署工作台中 WindowsPEX64 文件夹位置的图像](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="0a4cb-122">右键单击 " **WindowsPEX64** " 文件夹，然后选择 "**导入驱动程序**"。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-122">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="0a4cb-123">按照导入驱动程序向导中的说明将驱动程序文件夹导入 WindowsPEX64 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-123">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="0a4cb-124">检查下载的 MSI 程序包以确定格式和目录结构。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-124">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="0a4cb-125">目录结构将从 SurfacePlatformInstaller （较旧的 MSI 文件）或 SurfaceUpdate （较新的 MSI 文件）开始，具体取决于发布 MSI 的时间。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-125">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="0a4cb-126">若要支持 Surface 笔记本电脑（第一代），请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-126">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="0a4cb-127">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-127">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="0a4cb-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="0a4cb-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="0a4cb-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="0a4cb-131">或者对于以 "SurfaceUpdate" 开头的较新 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-131">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="0a4cb-132">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-132">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="0a4cb-133">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-133">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="0a4cb-134">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-134">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="0a4cb-135">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-135">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="0a4cb-136">若要支持 Surface 膝上型电脑2，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-136">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="0a4cb-137">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-137">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="0a4cb-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="0a4cb-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="0a4cb-140">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="0a4cb-140">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="0a4cb-141">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="0a4cb-141">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="0a4cb-142">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="0a4cb-142">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="0a4cb-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="0a4cb-144">或者对于以 "SurfaceUpdate" 开头的较新 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-144">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="0a4cb-145">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-145">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="0a4cb-146">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="0a4cb-146">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="0a4cb-147">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0a4cb-147">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="0a4cb-148">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0a4cb-148">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="0a4cb-149">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0a4cb-149">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="0a4cb-150">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0a4cb-150">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="0a4cb-151">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-151">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="0a4cb-152">若要通过英特尔处理器支持 Surface 笔记本电脑3，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-152">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="0a4cb-153">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-153">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="0a4cb-154">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="0a4cb-154">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="0a4cb-155">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0a4cb-155">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="0a4cb-156">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0a4cb-156">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="0a4cb-157">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0a4cb-157">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="0a4cb-158">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0a4cb-158">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="0a4cb-159">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="0a4cb-159">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="0a4cb-160">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-160">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="0a4cb-161">导入以下文件夹将在 Surface 笔记本电脑3的 PE 中启用全键盘、触控板和触摸功能。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-161">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="0a4cb-162">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-162">IclSerialIOGPIO</span></span>
- <span data-ttu-id="0a4cb-163">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="0a4cb-163">IclSerialIOI2C</span></span>
- <span data-ttu-id="0a4cb-164">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0a4cb-164">IclSerialIOSPI</span></span>
- <span data-ttu-id="0a4cb-165">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0a4cb-165">IclSerialIOUART</span></span>
- <span data-ttu-id="0a4cb-166">itouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-166">itouch</span></span>
- <span data-ttu-id="0a4cb-167">IclChipset</span><span class="sxs-lookup"><span data-stu-id="0a4cb-167">IclChipset</span></span>
- <span data-ttu-id="0a4cb-168">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="0a4cb-168">IclChipsetLPSS</span></span>
- <span data-ttu-id="0a4cb-169">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="0a4cb-169">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="0a4cb-170">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="0a4cb-170">ManagementEngine</span></span>
- <span data-ttu-id="0a4cb-171">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="0a4cb-171">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="0a4cb-172">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="0a4cb-172">SurfaceBattery</span></span>
- <span data-ttu-id="0a4cb-173">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="0a4cb-173">SurfaceDockIntegration</span></span>
- <span data-ttu-id="0a4cb-174">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0a4cb-174">SurfaceHidMini</span></span>
- <span data-ttu-id="0a4cb-175">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="0a4cb-175">SurfaceHotPlug</span></span>
- <span data-ttu-id="0a4cb-176">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="0a4cb-176">SurfaceIntegration</span></span>
- <span data-ttu-id="0a4cb-177">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0a4cb-177">SurfaceSerialHub</span></span>
- <span data-ttu-id="0a4cb-178">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="0a4cb-178">SurfaceService</span></span>
- <span data-ttu-id="0a4cb-179">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="0a4cb-179">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="0a4cb-180">检查下载的 MSI 程序包以确定格式和目录结构。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-180">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="0a4cb-181">目录结构将从 SurfacePlatformInstaller （较旧的 MSI 文件）或 SurfaceUpdate （较新的 MSI 文件）开始，具体取决于发布 MSI 的时间。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-181">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="0a4cb-182">若要支持 Surface 笔记本电脑（第一代），请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-182">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="0a4cb-183">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-183">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="0a4cb-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="0a4cb-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="0a4cb-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="0a4cb-187">或者对于以 "SurfaceUpdate" 开头的较新 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-187">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="0a4cb-188">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-188">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="0a4cb-189">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-189">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="0a4cb-190">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-190">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="0a4cb-191">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-191">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="0a4cb-192">若要支持 Surface 膝上型电脑2，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-192">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="0a4cb-193">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-193">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="0a4cb-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="0a4cb-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0a4cb-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="0a4cb-196">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="0a4cb-196">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="0a4cb-197">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="0a4cb-197">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="0a4cb-198">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="0a4cb-198">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="0a4cb-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="0a4cb-200">或者对于以 "SurfaceUpdate" 开头的较新 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-200">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="0a4cb-201">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-201">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="0a4cb-202">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="0a4cb-202">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="0a4cb-203">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0a4cb-203">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="0a4cb-204">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0a4cb-204">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="0a4cb-205">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0a4cb-205">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="0a4cb-206">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0a4cb-206">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="0a4cb-207">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-207">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="0a4cb-208">若要通过英特尔处理器支持 Surface 笔记本电脑3，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-208">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="0a4cb-209">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0a4cb-209">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="0a4cb-210">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="0a4cb-210">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="0a4cb-211">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0a4cb-211">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="0a4cb-212">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0a4cb-212">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="0a4cb-213">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0a4cb-213">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="0a4cb-214">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0a4cb-214">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="0a4cb-215">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="0a4cb-215">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="0a4cb-216">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0a4cb-216">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a4cb-217">对于带有英特尔处理器的 Surface 笔记本电脑3，型号是 Surface 笔记本电脑3。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-217">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="0a4cb-218">剩余 Surface 笔记本电脑驱动程序位于 "\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 笔记本 3" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-218">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="0a4cb-219">验证 WindowsPEX64 文件夹现在是否包含导入的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-219">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="0a4cb-220">该文件夹应如下所示：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-220">The folder should resemble the following:</span></span>  

   ![显示部署工作台的 WindowsPEX64 文件夹中新导入的驱动程序的图像](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="0a4cb-222">配置使用 WindowsPEX64 文件夹的选择配置文件。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-222">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="0a4cb-223">选择配置文件应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-223">The selection profile should resemble the following:</span></span>  

   ![显示选定为选择配置文件一部分的 WindowsPEX64 文件夹的图像](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="0a4cb-225">将 MDT 部署共享的 Windows PE 属性配置为使用新的选择配置文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-225">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="0a4cb-226">对于 "**平台**"，选择 " **x64**"。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-226">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="0a4cb-227">对于 "**选择配置文件**"，选择新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-227">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="0a4cb-228">**从选择配置文件中选择 "包括所有驱动程序"**。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-228">Select **Include all drivers from the selection profile**.</span></span>
   
   ![显示 MDT 部署共享的 Windows PE 属性的图像](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="0a4cb-230">通过使用选择配置文件或**DriverGroup001**变量，验证是否已配置了剩余 Surface 笔记本电脑驱动程序。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-230">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="0a4cb-231">对于 Surface 笔记本电脑（第1代），模型为**Surface 膝上型电脑**。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-231">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="0a4cb-232">剩余 Surface 笔记本电脑驱动程序应位于 \MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型电脑文件夹中，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-232">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="0a4cb-233">对于 Surface 笔记本电脑2，型号是**Surface 膝上型电脑 2**。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-233">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="0a4cb-234">剩余 Surface 笔记本电脑驱动程序应位于 "\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 笔记本 2" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="0a4cb-235">对于带有英特尔处理器的 Surface 笔记本电脑3，型号是 Surface 笔记本电脑3。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-235">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="0a4cb-236">剩余 Surface 笔记本电脑驱动程序位于 "\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 笔记本 3" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-236">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![显示部署工作台的 "Surface 笔记本" 文件夹中的常规 Surface 笔记本电脑（第1代）驱动程序的图像](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="0a4cb-238">将 MDT 部署共享配置为使用新的选择配置文件和相关设置后，请按照使用 MDT 部署 Windows 10 映像中的说明继续执行部署过程[：步骤6：创建部署任务序列](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-238">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>

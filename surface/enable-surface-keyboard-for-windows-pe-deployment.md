---
title: 如何在 MDT 部署期间启用 Surface Laptop 键盘
description: 当你使用 MDT 将 Windows 10 部署到 Surface 笔记本电脑时，你需要导入键盘驱动程序以在 Windows PE 环境中使用。
keywords: windows 10 surface， 自动化， 自定义， mdt
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
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247304"
---
# <span data-ttu-id="d2fd0-104">如何在 MDT 部署期间启用 Surface Laptop 键盘</span><span class="sxs-lookup"><span data-stu-id="d2fd0-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="d2fd0-105">本文介绍使用 Microsoft Deployment Toolkit (MDT) 。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="d2fd0-106">您还可以将此信息应用于其他部署方法。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="d2fd0-107">在大多数类型的 Surface 设备上，键盘应在 Lite Touch Installation (LTI) 。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="d2fd0-108">但是，Surface Laptop 需要一些额外的驱动程序才能启用键盘。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="d2fd0-109">对于 Surface Laptop (第一代) 和 Surface Laptop 2 设备，必须准备文件夹结构和选择配置文件，以允许你指定在 LTI 的 Windows 预安装环境 (Windows PE) 阶段使用的键盘驱动程序。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="d2fd0-110">有关此文件夹结构的信息，请参阅使用 [MDT 部署 Windows 10 映像：步骤 5：准备驱动程序存储库](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d2fd0-111">如果要将 Windows 10 映像部署到已预安装 S 模式下的 Windows 10 的 Surface Laptop，请参阅 KB [4032347，](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)将 Windows 部署到在 S 模式下预安装 Windows 10 的 Surface 设备时出现问题。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-111">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="d2fd0-112">若要将键盘驱动程序添加到选择配置文件，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-112">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="d2fd0-113">从相应位置下载最新的 Surface Laptop MSI 文件：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-113">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="d2fd0-114">Surface Laptop (第一代) 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="d2fd0-114">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="d2fd0-115">Surface Laptop 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="d2fd0-115">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="d2fd0-116">带 Intel 处理器驱动程序和固件的 Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="d2fd0-116">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="d2fd0-117">将 Surface Laptop MSI 文件的内容解压缩到一个文件夹， (例如 c：\surface_laptop_drivers) 。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-117">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="d2fd0-118">若要提取内容，请打开提升的命令提示符窗口并运行以下示例中的命令：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-118">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="d2fd0-119">打开部署工作台，展开"部署共享\*\*\*\*"节点和部署共享，然后导航到**WindowsPEX64**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-119">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![显示 WindowsPEX64 文件夹在部署工作台中的位置的图像](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="d2fd0-121">右键单击**WindowsPEX64**文件夹，然后选择 **"导入驱动程序"。**</span><span class="sxs-lookup"><span data-stu-id="d2fd0-121">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="d2fd0-122">按照导入驱动程序向导中的说明将驱动程序文件夹导入到 WindowsPEX64 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-122">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="d2fd0-123">检查下载的 MSI 程序包以确定格式和目录结构。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-123">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="d2fd0-124">目录结构将首先使用 SurfacePlatformInstaller (较旧的 MSI 文件) 或 SurfaceUpdate (较新的 MSI 文件) 具体取决于 MSI 的发布时间。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-124">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="d2fd0-125">若要支持 Surface Laptop (第一代) ，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-125">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="d2fd0-126">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-126">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="d2fd0-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="d2fd0-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="d2fd0-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="d2fd0-130">或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-130">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="d2fd0-131">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-131">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="d2fd0-132">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-132">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="d2fd0-133">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-133">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="d2fd0-134">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-134">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="d2fd0-135">若要支持 Surface Laptop 2，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-135">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="d2fd0-136">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-136">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="d2fd0-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="d2fd0-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="d2fd0-139">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="d2fd0-139">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="d2fd0-140">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="d2fd0-140">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="d2fd0-141">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="d2fd0-141">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="d2fd0-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="d2fd0-143">或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-143">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="d2fd0-144">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-144">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="d2fd0-145">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d2fd0-145">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="d2fd0-146">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d2fd0-146">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="d2fd0-147">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d2fd0-147">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="d2fd0-148">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d2fd0-148">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="d2fd0-149">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d2fd0-149">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="d2fd0-150">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-150">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="d2fd0-151">若要使用 Intel 处理器支持 Surface Laptop 3，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-151">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="d2fd0-152">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-152">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="d2fd0-153">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d2fd0-153">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="d2fd0-154">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d2fd0-154">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="d2fd0-155">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d2fd0-155">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="d2fd0-156">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d2fd0-156">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="d2fd0-157">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d2fd0-157">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="d2fd0-158">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="d2fd0-158">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="d2fd0-159">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-159">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="d2fd0-160">导入以下文件夹将在 PE 中为 Surface Laptop 3 启用完整的键盘、触控板和触摸功能。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-160">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="d2fd0-161">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-161">IclSerialIOGPIO</span></span>
- <span data-ttu-id="d2fd0-162">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d2fd0-162">IclSerialIOI2C</span></span>
- <span data-ttu-id="d2fd0-163">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d2fd0-163">IclSerialIOSPI</span></span>
- <span data-ttu-id="d2fd0-164">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d2fd0-164">IclSerialIOUART</span></span>
- <span data-ttu-id="d2fd0-165">itouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-165">itouch</span></span>
- <span data-ttu-id="d2fd0-166">IclChipset</span><span class="sxs-lookup"><span data-stu-id="d2fd0-166">IclChipset</span></span>
- <span data-ttu-id="d2fd0-167">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="d2fd0-167">IclChipsetLPSS</span></span>
- <span data-ttu-id="d2fd0-168">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="d2fd0-168">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="d2fd0-169">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="d2fd0-169">ManagementEngine</span></span>
- <span data-ttu-id="d2fd0-170">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="d2fd0-170">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="d2fd0-171">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="d2fd0-171">SurfaceBattery</span></span>
- <span data-ttu-id="d2fd0-172">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="d2fd0-172">SurfaceDockIntegration</span></span>
- <span data-ttu-id="d2fd0-173">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d2fd0-173">SurfaceHidMini</span></span>
- <span data-ttu-id="d2fd0-174">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="d2fd0-174">SurfaceHotPlug</span></span>
- <span data-ttu-id="d2fd0-175">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="d2fd0-175">SurfaceIntegration</span></span>
- <span data-ttu-id="d2fd0-176">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d2fd0-176">SurfaceSerialHub</span></span>
- <span data-ttu-id="d2fd0-177">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="d2fd0-177">SurfaceService</span></span>
- <span data-ttu-id="d2fd0-178">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="d2fd0-178">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="d2fd0-179">检查下载的 MSI 程序包以确定格式和目录结构。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-179">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="d2fd0-180">目录结构将首先使用 SurfacePlatformInstaller (较旧的 MSI 文件) 或 SurfaceUpdate (较新的 MSI 文件) 具体取决于 MSI 的发布时间。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-180">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="d2fd0-181">若要支持 Surface Laptop (第一代) ，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-181">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="d2fd0-182">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-182">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="d2fd0-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="d2fd0-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="d2fd0-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="d2fd0-186">或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-186">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="d2fd0-187">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-187">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="d2fd0-188">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-188">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="d2fd0-189">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-189">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="d2fd0-190">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-190">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="d2fd0-191">若要支持 Surface Laptop 2，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-191">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="d2fd0-192">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-192">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="d2fd0-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="d2fd0-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="d2fd0-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="d2fd0-195">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="d2fd0-195">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="d2fd0-196">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="d2fd0-196">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="d2fd0-197">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="d2fd0-197">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="d2fd0-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="d2fd0-199">或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-199">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="d2fd0-200">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-200">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="d2fd0-201">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d2fd0-201">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="d2fd0-202">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d2fd0-202">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="d2fd0-203">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d2fd0-203">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="d2fd0-204">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d2fd0-204">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="d2fd0-205">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d2fd0-205">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="d2fd0-206">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-206">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="d2fd0-207">若要使用 Intel 处理器支持 Surface Laptop 3，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-207">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="d2fd0-208">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="d2fd0-208">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="d2fd0-209">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="d2fd0-209">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="d2fd0-210">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="d2fd0-210">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="d2fd0-211">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="d2fd0-211">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="d2fd0-212">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="d2fd0-212">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="d2fd0-213">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="d2fd0-213">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="d2fd0-214">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="d2fd0-214">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="d2fd0-215">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="d2fd0-215">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2fd0-216">对于带 Intel 处理器的 Surface Laptop 3，型号为 Surface Laptop 3。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-216">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="d2fd0-217">其余的 Surface Laptop 驱动程序位于 \MDT 部署共享\开箱即用驱动程序\Windows10\X64\Surface Laptop 3 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-217">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="d2fd0-218">验证 WindowsPEX64 文件夹现在是否包含导入的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-218">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="d2fd0-219">该文件夹应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-219">The folder should resemble the following:</span></span>  

   ![显示部署工作台的 WindowsPEX64 文件夹中新导入的驱动程序的图像](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="d2fd0-221">配置使用 WindowsPEX64 文件夹的选择配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-221">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="d2fd0-222">选择配置文件应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-222">The selection profile should resemble the following:</span></span>  

   ![显示选择配置文件的一部分选择的 WindowsPEX64 文件夹的图像](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="d2fd0-224">配置 MDT 部署共享 Windows PE 属性以使用新的选择配置文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d2fd0-224">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="d2fd0-225">对于 **平台**，选择 **x64**。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-225">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="d2fd0-226">对于 **"选择"** 配置文件，选择新配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-226">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="d2fd0-227">Select **Include all drivers from the selection profile.**</span><span class="sxs-lookup"><span data-stu-id="d2fd0-227">Select **Include all drivers from the selection profile**.</span></span>
   
   ![显示 MDT 部署共享 Windows PE 属性的图像](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="d2fd0-229">使用选择配置文件或 **DriverGroup001** 变量验证是否配置了其余的 Surface Laptop 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-229">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="d2fd0-230">对于 Surface Laptop (第一代) ，型号为**Surface Laptop。**</span><span class="sxs-lookup"><span data-stu-id="d2fd0-230">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="d2fd0-231">其余的 Surface Laptop 驱动程序应位于 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 文件夹中，如此列表后图所示。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-231">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="d2fd0-232">对于 Surface Laptop 2，型号为**Surface Laptop 2。**</span><span class="sxs-lookup"><span data-stu-id="d2fd0-232">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="d2fd0-233">其余的 Surface Laptop 驱动程序应位于 \MDT 部署共享\开箱即用驱动程序\Windows10\X64\Surface Laptop 2 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-233">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="d2fd0-234">对于带 Intel 处理器的 Surface Laptop 3，型号为 Surface Laptop 3。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-234">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="d2fd0-235">其余的 Surface Laptop 驱动程序位于 \MDT 部署共享\开箱即用驱动程序\Windows10\X64\Surface Laptop 3 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-235">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![显示部署工作台的 Surface Laptop 文件夹中的常规 Surface Laptop (第一代) 驱动程序的图像](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="d2fd0-237">将 MDT 部署共享配置为使用新的选择配置文件和相关设置后，继续部署过程，如使用 MDT 部署 Windows 10 映像中所述：步骤 [6：创建部署任务序列](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)。</span><span class="sxs-lookup"><span data-stu-id="d2fd0-237">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>

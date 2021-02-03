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
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312058"
---
# <span data-ttu-id="1d413-104">如何在 MDT 部署期间启用 Surface Laptop 键盘</span><span class="sxs-lookup"><span data-stu-id="1d413-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="1d413-105">本文介绍使用 Microsoft Deployment Toolkit (MDT) 。</span><span class="sxs-lookup"><span data-stu-id="1d413-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="1d413-106">您还可以将此信息应用于其他部署方法。</span><span class="sxs-lookup"><span data-stu-id="1d413-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="1d413-107">在大多数类型的 Surface 设备上，键盘应在 Lite Touch Installation (LTI) 。</span><span class="sxs-lookup"><span data-stu-id="1d413-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="1d413-108">但是，Surface Laptop 需要一些额外的驱动程序才能启用键盘。</span><span class="sxs-lookup"><span data-stu-id="1d413-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="1d413-109">对于 Surface Laptop (第一代) 和 Surface Laptop 2 设备，必须准备文件夹结构和选择配置文件，以允许你指定在 LTI 的 Windows 预安装环境 (Windows PE) 阶段使用的键盘驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1d413-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="1d413-110">有关此文件夹结构的信息，请参阅使用 [MDT 部署 Windows 10 映像：步骤 5：准备驱动程序存储库](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。</span><span class="sxs-lookup"><span data-stu-id="1d413-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!TIP]    
> <span data-ttu-id="1d413-111">在同一 Windows PE 启动实例中将 Surface Laptop 2 和 Surface Laptop 3 的键盘驱动程序用于时，如果键盘或触摸板在 Windows PE 中不起作用，可能需要手动重置固件：</span><span class="sxs-lookup"><span data-stu-id="1d413-111">When using keyboard drivers for Surface Laptop 2 and Surface Laptop 3 in the same Windows PE boot instance, you may need to manually reset the firmware if the keyboard or touchpad don’t work in Windows PE:</span></span>
>
> - <span data-ttu-id="1d413-112">长按电源按钮 30 秒。</span><span class="sxs-lookup"><span data-stu-id="1d413-112">Press and hold the Power button for 30 seconds.</span></span> <span data-ttu-id="1d413-113">如果连接到电源设备 (PSU) ，请长按电源按钮，直到看到 PSU 电缆末端的灯短暂关闭，然后再打开。</span><span class="sxs-lookup"><span data-stu-id="1d413-113">If you are connected to a power supply unit (PSU), press and hold the Power button until you see the light at the end of the PSU cord briefly turn off before turning back on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d413-114">如果要将 Windows 10 映像部署到已预安装 S 模式下的 Windows 10 的 Surface Laptop，请参阅 KB [4032347，](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)将 Windows 部署到在 S 模式下预安装 Windows 10 的 Surface 设备时出现问题。</span><span class="sxs-lookup"><span data-stu-id="1d413-114">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="1d413-115">若要将键盘驱动程序添加到选择配置文件，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="1d413-115">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="1d413-116">从适当位置下载最新的 Surface Laptop MSI 文件：</span><span class="sxs-lookup"><span data-stu-id="1d413-116">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="1d413-117">Surface Laptop (第一代) 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="1d413-117">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="1d413-118">Surface Laptop 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="1d413-118">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="1d413-119">带 Intel 处理器驱动程序和固件的 Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="1d413-119">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="1d413-120">将 Surface Laptop MSI 文件的内容解压缩到一个文件夹， (例如 c：\surface_laptop_drivers) 。</span><span class="sxs-lookup"><span data-stu-id="1d413-120">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="1d413-121">若要提取内容，请打开提升的命令提示符窗口并运行以下示例中的命令：</span><span class="sxs-lookup"><span data-stu-id="1d413-121">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="1d413-122">打开部署工作台，展开"部署共享\*\*\*\*"节点和部署共享，然后导航到**WindowsPEX64**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1d413-122">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![显示 WindowsPEX64 文件夹在部署工作台中的位置的图像](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="1d413-124">右键单击**WindowsPEX64**文件夹，然后选择 **"导入驱动程序"。**</span><span class="sxs-lookup"><span data-stu-id="1d413-124">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>

5. <span data-ttu-id="1d413-125">按照导入驱动程序向导中的说明将驱动程序文件夹导入到 WindowsPEX64 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1d413-125">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="1d413-126">检查下载的 MSI 程序包以确定格式和目录结构。</span><span class="sxs-lookup"><span data-stu-id="1d413-126">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="1d413-127">目录结构将首先使用 SurfacePlatformInstaller (较旧的 MSI 文件) 或 SurfaceUpdate (较新的 MSI 文件) 具体取决于 MSI 的发布时间。</span><span class="sxs-lookup"><span data-stu-id="1d413-127">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="1d413-128">若要支持 Surface Laptop (第一代) ，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="1d413-128">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="1d413-129">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-129">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="1d413-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="1d413-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="1d413-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="1d413-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="1d413-133">或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="1d413-133">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="1d413-134">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-134">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="1d413-135">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-135">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="1d413-136">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-136">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="1d413-137">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="1d413-137">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="1d413-138">若要支持 Surface Laptop 2，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="1d413-138">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="1d413-139">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-139">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="1d413-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="1d413-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="1d413-142">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="1d413-142">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="1d413-143">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="1d413-143">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="1d413-144">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="1d413-144">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="1d413-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="1d413-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="1d413-146">或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="1d413-146">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="1d413-147">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-147">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="1d413-148">SurfaceUpdate\serialioi2c</span><span class="sxs-lookup"><span data-stu-id="1d413-148">SurfaceUpdate\serialioi2c</span></span>
    - <span data-ttu-id="1d413-149">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="1d413-149">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="1d413-150">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="1d413-150">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="1d413-151">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="1d413-151">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="1d413-152">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="1d413-152">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="1d413-153">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="1d413-153">SurfaceUpdate\Itouch</span></span>

     
    <span data-ttu-id="1d413-154">若要使用 Intel 处理器支持 Surface Laptop 3，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="1d413-154">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="1d413-155">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-155">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="1d413-156">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="1d413-156">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="1d413-157">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="1d413-157">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="1d413-158">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="1d413-158">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="1d413-159">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="1d413-159">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="1d413-160">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="1d413-160">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="1d413-161">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="1d413-161">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="1d413-162">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="1d413-162">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="1d413-163">导入以下文件夹将在 PE 中为 Surface Laptop 3 启用完整的键盘、触控板和触摸功能。</span><span class="sxs-lookup"><span data-stu-id="1d413-163">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

    - <span data-ttu-id="1d413-164">SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-164">SerialIOGPIO</span></span>
    - <span data-ttu-id="1d413-165">SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="1d413-165">SerialIOI2C</span></span>
    - <span data-ttu-id="1d413-166">SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="1d413-166">SerialIOSPI</span></span>
    - <span data-ttu-id="1d413-167">SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="1d413-167">SerialIOUART</span></span>
    - <span data-ttu-id="1d413-168">itouch</span><span class="sxs-lookup"><span data-stu-id="1d413-168">itouch</span></span>
    - <span data-ttu-id="1d413-169">芯片集</span><span class="sxs-lookup"><span data-stu-id="1d413-169">Chipset</span></span>
    - <span data-ttu-id="1d413-170">芯片集LPS</span><span class="sxs-lookup"><span data-stu-id="1d413-170">ChipsetLPSS</span></span>
    - <span data-ttu-id="1d413-171">ChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="1d413-171">ChipsetNorthpeak</span></span>
    - <span data-ttu-id="1d413-172">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="1d413-172">ManagementEngine</span></span>
    - <span data-ttu-id="1d413-173">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="1d413-173">SurfaceAcpiNotify</span></span>
    - <span data-ttu-id="1d413-174">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="1d413-174">SurfaceBattery</span></span>
    - <span data-ttu-id="1d413-175">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="1d413-175">SurfaceDockIntegration</span></span>
    - <span data-ttu-id="1d413-176">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="1d413-176">SurfaceHidMini</span></span>
    - <span data-ttu-id="1d413-177">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="1d413-177">SurfaceHotPlug</span></span>
    - <span data-ttu-id="1d413-178">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="1d413-178">SurfaceIntegration</span></span>
    - <span data-ttu-id="1d413-179">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="1d413-179">SurfaceSerialHub</span></span>
    - <span data-ttu-id="1d413-180">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="1d413-180">SurfaceService</span></span>
    - <span data-ttu-id="1d413-181">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="1d413-181">SurfaceStorageFwUpdate</span></span>

     > [!NOTE]
     >  <span data-ttu-id="1d413-182">检查下载的 MSI 程序包以确定格式和目录结构。</span><span class="sxs-lookup"><span data-stu-id="1d413-182">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="1d413-183">目录结构将首先使用 SurfacePlatformInstaller (较旧的 MSI 文件) 或 SurfaceUpdate (较新的 MSI 文件) 具体取决于 MSI 的发布时间。</span><span class="sxs-lookup"><span data-stu-id="1d413-183">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

     <span data-ttu-id="1d413-184">若要支持 Surface Laptop (第一代) ，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="1d413-184">To support Surface Laptop (1st Gen), import the following folders:</span></span>

    - <span data-ttu-id="1d413-185">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-185">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="1d413-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="1d413-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="1d413-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="1d413-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="1d413-189">或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="1d413-189">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="1d413-190">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-190">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="1d413-191">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-191">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="1d413-192">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-192">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="1d413-193">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="1d413-193">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="1d413-194">若要支持 Surface Laptop 2，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="1d413-194">To support Surface Laptop 2, import the following folders:</span></span>

    - <span data-ttu-id="1d413-195">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-195">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="1d413-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
    - <span data-ttu-id="1d413-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="1d413-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="1d413-198">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="1d413-198">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
    - <span data-ttu-id="1d413-199">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="1d413-199">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
    - <span data-ttu-id="1d413-200">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="1d413-200">SurfacePlatformInstaller\Drivers\System\UART</span></span>
    - <span data-ttu-id="1d413-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="1d413-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="1d413-202">或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="1d413-202">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="1d413-203">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-203">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="1d413-204">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="1d413-204">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="1d413-205">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="1d413-205">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="1d413-206">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="1d413-206">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="1d413-207">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="1d413-207">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="1d413-208">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="1d413-208">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="1d413-209">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="1d413-209">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="1d413-210">若要使用 Intel 处理器支持 Surface Laptop 3，请导入以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="1d413-210">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="1d413-211">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="1d413-211">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="1d413-212">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="1d413-212">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="1d413-213">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="1d413-213">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="1d413-214">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="1d413-214">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="1d413-215">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="1d413-215">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="1d413-216">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="1d413-216">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="1d413-217">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="1d413-217">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="1d413-218">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="1d413-218">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d413-219">对于带 Intel 处理器的 Surface Laptop 3，型号为 Surface Laptop 3。</span><span class="sxs-lookup"><span data-stu-id="1d413-219">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="1d413-220">其余的 Surface Laptop 驱动程序位于 \MDT 部署共享\开箱即用驱动程序\Windows10\X64\Surface Laptop 3 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1d413-220">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="1d413-221">验证 WindowsPEX64 文件夹现在是否包含导入的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1d413-221">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="1d413-222">该文件夹应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="1d413-222">The folder should resemble the following:</span></span>  

   ![显示部署工作台的 WindowsPEX64 文件夹中新导入的驱动程序的图像](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="1d413-224">配置使用 WindowsPEX64 文件夹的选择配置文件。</span><span class="sxs-lookup"><span data-stu-id="1d413-224">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="1d413-225">选择配置文件应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="1d413-225">The selection profile should resemble the following:</span></span>  

   ![显示选择配置文件的一部分选择的 WindowsPEX64 文件夹的图像](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="1d413-227">配置 MDT 部署共享 Windows PE 属性以使用新的选择配置文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d413-227">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="1d413-228">对于 **平台**，选择 **x64**。</span><span class="sxs-lookup"><span data-stu-id="1d413-228">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="1d413-229">对于 **"选择"** 配置文件，选择新配置文件。</span><span class="sxs-lookup"><span data-stu-id="1d413-229">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="1d413-230">Select **Include all drivers from the selection profile.**</span><span class="sxs-lookup"><span data-stu-id="1d413-230">Select **Include all drivers from the selection profile**.</span></span>
   
   ![显示 MDT 部署共享 Windows PE 属性的图像](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="1d413-232">使用选择配置文件或 **DriverGroup001** 变量验证是否配置了其余的 Surface Laptop 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1d413-232">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="1d413-233">对于 Surface Laptop (第一代) ，型号为**Surface Laptop。**</span><span class="sxs-lookup"><span data-stu-id="1d413-233">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="1d413-234">其余的 Surface Laptop 驱动程序应位于 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 文件夹中，如此列表后图所示。</span><span class="sxs-lookup"><span data-stu-id="1d413-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="1d413-235">对于 Surface Laptop 2，型号为**Surface Laptop 2。**</span><span class="sxs-lookup"><span data-stu-id="1d413-235">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="1d413-236">其余的 Surface Laptop 驱动程序应位于 \MDT 部署共享\开箱即用驱动程序\Windows10\X64\Surface Laptop 2 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1d413-236">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="1d413-237">对于带 Intel 处理器的 Surface Laptop 3，型号为 Surface Laptop 3。</span><span class="sxs-lookup"><span data-stu-id="1d413-237">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="1d413-238">其余的 Surface Laptop 驱动程序位于 \MDT 部署共享\开箱即用驱动程序\Windows10\X64\Surface Laptop 3 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1d413-238">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![显示部署工作台的 Surface Laptop 文件夹中的常规 Surface Laptop (第一代) 驱动程序的图像](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="1d413-240">将 MDT 部署共享配置为使用新的选择配置文件和相关设置后，继续部署过程，如使用 MDT 部署 Windows 10 映像中所述：步骤 [6：创建部署任务序列](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)。</span><span class="sxs-lookup"><span data-stu-id="1d413-240">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>

---
title: 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文介绍了如何从 Surface Hub 2 上的 Windows 10 团队迁移到 Windows 10 专业版或 Windows 10 企业版。
keywords: Surface Hub 桌面、Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c2851505b3595ea768217de443676b45cc01a9ae
ms.sourcegitcommit: efc38524f81238e0c36371f462eb57123e46d09b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "11228553"
---
# <span data-ttu-id="1580a-104">迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="1580a-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

- [<span data-ttu-id="1580a-105">文章版本历史记录</span><span class="sxs-lookup"><span data-stu-id="1580a-105">Article version history</span></span>](#version-history)

<span data-ttu-id="1580a-106">Surface Hub 2S 预安装有 Windows 10 团队。</span><span class="sxs-lookup"><span data-stu-id="1580a-106">Surface Hub 2S comes preinstalled with Windows 10 Team.</span></span> <span data-ttu-id="1580a-107">此自定义版本的 Windows 10 旨在促进在会议室环境中进行协作。</span><span class="sxs-lookup"><span data-stu-id="1580a-107">This customized edition of Windows 10 is designed to facilitate collaboration in meeting room environments.</span></span> <span data-ttu-id="1580a-108">现在，你可以选择运行 Windows 10 专业版或企业版以使用 Surface Hub 2S，这非常像任何其他电脑。</span><span class="sxs-lookup"><span data-stu-id="1580a-108">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="1580a-109">与典型的升级或迁移不同，此过程要求您遵循一个说明性过程，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="1580a-109">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described in this article.</span></span> <span data-ttu-id="1580a-110">在继续[之前，](#solution-components)[请查看解决方案组件以及迁移](#migration-and-installation-workflow-summary)和安装工作流。</span><span class="sxs-lookup"><span data-stu-id="1580a-110">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before you continue.</span></span>


> [!NOTE]
> <span data-ttu-id="1580a-111">安装 Windows 10 专业版或企业版时，需要一个独立于现有 Windows 10 团队版许可证的新许可证。</span><span class="sxs-lookup"><span data-stu-id="1580a-111">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="1580a-112">使用单独的电脑和可下载的工具 *Surface UEFI Configurator*开始从 Windows 10 团队迁移。</span><span class="sxs-lookup"><span data-stu-id="1580a-112">Start the migration from Windows 10 Team by using a separate PC and the downloadable tool *Surface UEFI Configurator*.</span></span> <span data-ttu-id="1580a-113">使用该工具创建包含适用于 Surface Hub 2S 的新 UEFI 设置的程序包。</span><span class="sxs-lookup"><span data-stu-id="1580a-113">Use the tool  to create a package that contains a new UEFI setting that you apply to Surface Hub 2S.</span></span>  

<span data-ttu-id="1580a-114">Surface UEFI 配置器用作 SEMM (Surface 企业管理模式的) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-114">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="1580a-115">它旨在便于在企业环境中集中管理 Surface 设备的固件设置。</span><span class="sxs-lookup"><span data-stu-id="1580a-115">It's designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="1580a-116">有关详细信息，请参阅 Microsoft <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 文档</span><span class="sxs-lookup"><span data-stu-id="1580a-116">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank">Microsoft SEMM documentation</span></span></a>
 

## <span data-ttu-id="1580a-117">解决方案组件</span><span class="sxs-lookup"><span data-stu-id="1580a-117">Solution components</span></span>

- <span data-ttu-id="1580a-118">运行 Windows 10 团队操作系统的 Surface Hub 2S 设备</span><span class="sxs-lookup"><span data-stu-id="1580a-118">Surface Hub 2S device running the Windows 10 Team operating system</span></span>
- <span data-ttu-id="1580a-119">运行 Windows 10 的单独设备</span><span class="sxs-lookup"><span data-stu-id="1580a-119">Separate device running Windows 10</span></span>
- <span data-ttu-id="1580a-120">用于创建 SEMM 程序包的 Surface UEFI 配置器工具</span><span class="sxs-lookup"><span data-stu-id="1580a-120">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="1580a-121">Windows 10 专业版或企业版操作系统映像版本 1903 或更高版本</span><span class="sxs-lookup"><span data-stu-id="1580a-121">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="1580a-122">两个存储为 16 GB 的 USB 驱动器，FAT32 格式</span><span class="sxs-lookup"><span data-stu-id="1580a-122">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="1580a-123">Surface Hub 2 上适用于 Windows 10 专业版和企业操作系统的驱动程序和固件Microsoft Windows Installer (MSI) 文件</span><span class="sxs-lookup"><span data-stu-id="1580a-123">The Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="1580a-124">Internet 连接</span><span class="sxs-lookup"><span data-stu-id="1580a-124">Internet connection</span></span>
- <span data-ttu-id="1580a-125">映像解决方案 (可选) </span><span class="sxs-lookup"><span data-stu-id="1580a-125">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="1580a-126">迁移和安装工作流摘要</span><span class="sxs-lookup"><span data-stu-id="1580a-126">Migration and installation workflow summary</span></span>

| <span data-ttu-id="1580a-127">步骤</span><span class="sxs-lookup"><span data-stu-id="1580a-127">Step</span></span>  | <span data-ttu-id="1580a-128">操作</span><span class="sxs-lookup"><span data-stu-id="1580a-128">Action</span></span>                                                                                                 | <span data-ttu-id="1580a-129">摘要</span><span class="sxs-lookup"><span data-stu-id="1580a-129">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1580a-130">1</span><span class="sxs-lookup"><span data-stu-id="1580a-130">1</span></span> | [<span data-ttu-id="1580a-131">验证 Surface Hub 2S 上的 UEFI 版本是否满足最低要求。</span><span class="sxs-lookup"><span data-stu-id="1580a-131">Verify that the UEFI version on Surface Hub 2S meets minimum requirements.</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="1580a-132">确保 UEFI 版本为 694.2938.768.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1580a-132">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="1580a-133">2</span><span class="sxs-lookup"><span data-stu-id="1580a-133">2</span></span> | [<span data-ttu-id="1580a-134">下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="1580a-134">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="1580a-135">在 <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **Surface Tools for IT**页面上 </a> ，选择"**下载"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-135">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">**Surface Tools for IT** page</a>, select **Download**.</span></span> <span data-ttu-id="1580a-136">然后选择并下载 **Surface UEFI 配置器。MSI 文件** ，并安装在单独的电脑上。</span><span class="sxs-lookup"><span data-stu-id="1580a-136">Then select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="1580a-137">在 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 MSI 文件上下载适用于 Windows 10 专业版和企业操作系统的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="1580a-137">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a> <span data-ttu-id="1580a-138">保存它以在步骤 5 中使用。</span><span class="sxs-lookup"><span data-stu-id="1580a-138">Save it for use in step 5.</span></span> |
| <span data-ttu-id="1580a-139">3</span><span class="sxs-lookup"><span data-stu-id="1580a-139">3</span></span> | [<span data-ttu-id="1580a-140">准备 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="1580a-140">Prepare SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="1580a-141">准备运行 Surface UEFI 配置程序所需的证书。</span><span class="sxs-lookup"><span data-stu-id="1580a-141">Prepare the certificate that's required to run Surface UEFI Configurator.</span></span> <span data-ttu-id="1580a-142">或使用当前证书。</span><span class="sxs-lookup"><span data-stu-id="1580a-142">Or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="1580a-143">4</span><span class="sxs-lookup"><span data-stu-id="1580a-143">4</span></span> | [<span data-ttu-id="1580a-144">创建 SEMM 程序包。</span><span class="sxs-lookup"><span data-stu-id="1580a-144">Create SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="1580a-145">启动 Surface UEFI 配置器以在 USB 驱动器上创建 SEMM 程序包，其中包含在 Surface Hub 2S 上应用所需的配置文件。</span><span class="sxs-lookup"><span data-stu-id="1580a-145">Start Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="1580a-146">将这些 SEMM 程序包文件复制到电脑上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1580a-146">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="1580a-147">5</span><span class="sxs-lookup"><span data-stu-id="1580a-147">5</span></span> | [<span data-ttu-id="1580a-148">为 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统准备包含 Windows 10 映像、SEMM 程序包以及驱动程序和固件的 U 盘。</span><span class="sxs-lookup"><span data-stu-id="1580a-148">Prepare USB flash drive that contains Windows 10 image, SEMM package, and drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="1580a-149">创建一个包含 Windows 10 映像的 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="1580a-149">Create a single USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="1580a-150">本示例中，驱动器名为*BOOTME。*</span><span class="sxs-lookup"><span data-stu-id="1580a-150">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="1580a-151">将 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件 (步骤 2) ，将 SEMM 程序包文件 (步骤 4) *BOOTME* 驱动器。</span><span class="sxs-lookup"><span data-stu-id="1580a-151">Add your drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (step 2) and SEMM package files (step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="1580a-152">6</span><span class="sxs-lookup"><span data-stu-id="1580a-152">6</span></span> | [<span data-ttu-id="1580a-153">更新 Surface Hub 2S 上的 UEFI 以启用操作系统迁移。</span><span class="sxs-lookup"><span data-stu-id="1580a-153">Update UEFI on Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="1580a-154">使用 *BOOTME* 驱动器将 Surface Hub 2S 启动到 UEFI 菜单并安装 SEMM 程序包。</span><span class="sxs-lookup"><span data-stu-id="1580a-154">Use the *BOOTME* drive to boot Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="1580a-155">7</span><span class="sxs-lookup"><span data-stu-id="1580a-155">7</span></span> | [<span data-ttu-id="1580a-156">安装 Windows 10 专业版或企业版 1903 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1580a-156">Install Windows 10 Pro or Enterprise version 1903 or later.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="1580a-157">使用 *BOOTME* 驱动器安装 Windows 10 专业版或企业版 1903 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1580a-157">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="1580a-158">8</span><span class="sxs-lookup"><span data-stu-id="1580a-158">8</span></span> | [<span data-ttu-id="1580a-159">在 Surface Hub 2 上安装适用于 Windows 10 专业版和企业版操作系统的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="1580a-159">Install drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="1580a-160">若要确保你的设备具有所有最新的更新和驱动程序，请为 Surface Hub 2 MSI 文件安装适用于 Windows 10 专业版和企业操作系统的驱动程序 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 和固件。</span><span class="sxs-lookup"><span data-stu-id="1580a-160">To ensure your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="1580a-161">9</span><span class="sxs-lookup"><span data-stu-id="1580a-161">9</span></span> | [<span data-ttu-id="1580a-162">将 Surface Hub 2S 完全配置为个人生产力设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-162">Fully configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="1580a-163">启用推荐的设置和应用程序以将 Surface Hub 2S 优化为个人生产力设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-163">Enable recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="1580a-164">验证 Surface Hub 2S 上的 UEFI 版本是否满足最低要求</span><span class="sxs-lookup"><span data-stu-id="1580a-164">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="1580a-165">在将 Surface Hub 从 Windows 10 团队迁移到 Windows 10 桌面版之前，你需要至少为 *694.2938.768.0*的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="1580a-165">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need a UEFI version that's at least *694.2938.768.0*.</span></span>
 
**<span data-ttu-id="1580a-166">验证系统上的 UEFI 版本：</span><span class="sxs-lookup"><span data-stu-id="1580a-166">To verify the UEFI version on your system:</span></span>**

1. <span data-ttu-id="1580a-167">在 Surface Hub 2S 主页\*\*\*\* 上，选择"开始"，然后打开 Surface 应用 (**所有应用**  >  **Surface**) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-167">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="1580a-168">选择 Surface 以显示 **有关** Surface Hub 的信息，包括设备上当前的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="1580a-168">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="1580a-169">如果 UEFI 版本为 *694.2938.768.0* 或更高版本，如下图所示，您可以创建 SEMM 程序包以启用操作系统迁移。</span><span class="sxs-lookup"><span data-stu-id="1580a-169">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![显示 Surface 应用中的 Surface 页面的屏幕截图。](images/shm-fig1.png)
 
   - <span data-ttu-id="1580a-171">如果 UEFI 版本早于版本 694.2938.768.0，则需要通过安装 Window 10 Team 2020 Update Bare Metal Recovery (BMR) 映像或通过使用 Windows 更新来获取当前版本。</span><span class="sxs-lookup"><span data-stu-id="1580a-171">If the UEFI version is earlier than version 694.2938.768.0, you will need to obtain a current version by either installing the Window 10 Team 2020 Update Bare Metal Recovery (BMR) image, or by using Windows Update.</span></span>
   
**<span data-ttu-id="1580a-172">若要通过 Windows 更新更新 UEFI，</span><span class="sxs-lookup"><span data-stu-id="1580a-172">To update UEFI via Windows Update:</span></span>**

1. <span data-ttu-id="1580a-173">在 Surface Hub 2S 上，以管理员角色 **登录**。</span><span class="sxs-lookup"><span data-stu-id="1580a-173">On your Surface Hub 2S, sign in as **Admin**.</span></span> 
    >[!Note]
    > <span data-ttu-id="1580a-174">如果不知道用户名或管理员密码，则需要重置设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-174">If you don't know your username or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="1580a-175">有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Surface Hub 2S 的重置和恢复。</span><span class="sxs-lookup"><span data-stu-id="1580a-175">For more information, see <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank">Reset and recovery for Surface Hub 2S.</span></span></a>

1. <span data-ttu-id="1580a-176">转到 **"所有应用**  >  **设置**  >  **更新和安全**  >  **Windows 更新**"，然后安装所有更新。</span><span class="sxs-lookup"><span data-stu-id="1580a-176">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and then install all updates.</span></span> 
1. <span data-ttu-id="1580a-177">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-177">Restart the device.</span></span> 
1. <span data-ttu-id="1580a-178">使用 Surface 应用验证 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="1580a-178">Verify the UEFI version by using the Surface app.</span></span> 
1. <span data-ttu-id="1580a-179">此时，如果 UEFI 版本尚不为版本 694.2938.768.0 或更高版本，可以重复上述步骤，或者可以通过安装 Windows 10 Team 2020 Update 裸机恢复 (BMR) 映像获取最新的 UEFI。</span><span class="sxs-lookup"><span data-stu-id="1580a-179">At this point, if the UEFI version is not yet version  694.2938.768.0 or later, you can either repeat the above steps, or you can get the latest UEFI by installing the Windows 10 Team 2020 Update Bare Metal Recovery (BMR) image.</span></span>

**<span data-ttu-id="1580a-180">若要通过裸机恢复更新 UEFI (BMR) 映像：</span><span class="sxs-lookup"><span data-stu-id="1580a-180">To update UEFI via Bare Metal Recovery (BMR) image:</span></span>**

1.  <span data-ttu-id="1580a-181">转到 [Surface 恢复站点并选择](https://support.microsoft.com/surfacerecoveryimage) **Surface Hub 2S**</span><span class="sxs-lookup"><span data-stu-id="1580a-181">Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**</span></span>
3.  <span data-ttu-id="1580a-182">输入位于集线器 (电源连接旁的集线器序列号。) </span><span class="sxs-lookup"><span data-stu-id="1580a-182">Enter your Hub Serial Number (located on the rear side of the Hub next to the power connection.)</span></span>
4.  <span data-ttu-id="1580a-183">按照说明通过安装 Windows 10 Team 2020 Update 将映像下载到格式化的 USB 驱动器上。</span><span class="sxs-lookup"><span data-stu-id="1580a-183">Follow the directions to download the image onto a formatted USB drive through installing the Windows 10 Team 2020 Update.</span></span>
5.  <span data-ttu-id="1580a-184">更新完成后，设备首次进入 OOBE 设置后，无需完成 OOBE，UEFI 版本将更新。</span><span class="sxs-lookup"><span data-stu-id="1580a-184">After the update has completed and the device enters the OOBE first time setup, you do not need to complete OOBE, the UEFI version will be updated.</span></span> <span data-ttu-id="1580a-185">而是按住电源按钮关闭设备，直到屏幕关闭。</span><span class="sxs-lookup"><span data-stu-id="1580a-185">Instead power down the device by holding the power button until the screen turns off.</span></span> 

### <span data-ttu-id="1580a-186">下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="1580a-186">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="1580a-187">在单独的电脑上：</span><span class="sxs-lookup"><span data-stu-id="1580a-187">On a separate PC:</span></span>

1. <span data-ttu-id="1580a-188">在 <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT 页面上 </a> ，选择"**下载"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-188">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>  
1. <span data-ttu-id="1580a-189">选择并下载 Surface UEFI 配置器 MSI 文件，将其安装在单独的电脑上。</span><span class="sxs-lookup"><span data-stu-id="1580a-189">Select and download the Surface UEFI Configurator MSI file and install it on a separate PC.</span></span> <span data-ttu-id="1580a-190">安装 Windows 10 团队版时，Surface UEFI 配置器工具无法运行在 Surface Hub 2S 上。</span><span class="sxs-lookup"><span data-stu-id="1580a-190">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while the Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="1580a-191">下载 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 驱动程序和固件 Windows Installer MSI 文件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1580a-191">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Surface Hub 2 Drivers and Firmware Windows Installer MSI file</a>.</span></span> <span data-ttu-id="1580a-192">安装新操作系统时，将使用此文件。</span><span class="sxs-lookup"><span data-stu-id="1580a-192">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="1580a-193">准备 SEMM 证书</span><span class="sxs-lookup"><span data-stu-id="1580a-193">Prepare the SEMM certificate</span></span>

<span data-ttu-id="1580a-194">如果你之前没有使用过 Surface UEFI 配置器，则需要准备证书。</span><span class="sxs-lookup"><span data-stu-id="1580a-194">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="1580a-195">此证书可确保在 SEMM 中注册设备后，只能使用使用已批准证书创建的程序包修改 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="1580a-195">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span> 

<span data-ttu-id="1580a-196">获取证书的方式取决于组织的规模或复杂性：</span><span class="sxs-lookup"><span data-stu-id="1580a-196">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="1580a-197">企业组织通常维护自己的基础结构，以根据标准安全做法生成证书。</span><span class="sxs-lookup"><span data-stu-id="1580a-197">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="1580a-198">中型企业和其他企业可能会选择从合作伙伴提供商获取证书。</span><span class="sxs-lookup"><span data-stu-id="1580a-198">Medium-sized businesses and others might choose to get certificates from partner providers.</span></span> <span data-ttu-id="1580a-199">对于没有足够的 IT 专业知识或专门的 IT 安全团队的组织，建议使用此选项。</span><span class="sxs-lookup"><span data-stu-id="1580a-199">This option is recommended for organizations that don't have sufficient IT expertise or a dedicated IT security team.</span></span>

- <span data-ttu-id="1580a-200">或者，您可以使用 PowerShell 脚本生成自签名证书。</span><span class="sxs-lookup"><span data-stu-id="1580a-200">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="1580a-201">有关详细信息，请参阅 Surface <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> Enterprise 管理模式证书要求 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1580a-201">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank">Surface Enterprise Management Mode certificate requirements </a>.</span></span> <span data-ttu-id="1580a-202">或者，您可以使用 PowerShell 创建自己的证书。</span><span class="sxs-lookup"><span data-stu-id="1580a-202">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="1580a-203">有关详细信息，请参阅 <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate </a> 文档。</span><span class="sxs-lookup"><span data-stu-id="1580a-203">For more information, see the <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate</a> documentation.</span></span>

<span data-ttu-id="1580a-204">Surface UEFI 配置器创建的 SEMM 程序包必须使用证书进行保护。</span><span class="sxs-lookup"><span data-stu-id="1580a-204">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="1580a-205">证书先验证配置文件的签名，然后才能应用 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="1580a-205">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="1580a-206">有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 文档 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1580a-206">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM documentation</a>.</span></span>
 
 
### <span data-ttu-id="1580a-207">创建 SEMM 程序包</span><span class="sxs-lookup"><span data-stu-id="1580a-207">Create a SEMM package</span></span>

1. <span data-ttu-id="1580a-208">在单独的电脑上，安装之前下载的 Surface UEFI 配置器工具。</span><span class="sxs-lookup"><span data-stu-id="1580a-208">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span> 

2. <span data-ttu-id="1580a-209">打开 Surface UEFI 配置器，然后选择"**开始"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-209">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![打开 Surface UEFI 配置器。](images/shm-fig2.png)
   
3. <span data-ttu-id="1580a-211">选择**Surface 设备**，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-211">Select **Surface Devices**, and then select **Next**.</span></span>

   ![选择 Surface 设备。](images/shm-fig3.png)
  
4. <span data-ttu-id="1580a-213">选择 **配置包**。</span><span class="sxs-lookup"><span data-stu-id="1580a-213">Select **Configuration Package**.</span></span>

   ![选择配置包。](images/shm-fig4.png)
  
5. <span data-ttu-id="1580a-215">选择 **证书保护**。</span><span class="sxs-lookup"><span data-stu-id="1580a-215">Select **Certificate Protection**.</span></span>

   ![选择"证书保护"。](images/shm-fig5.png)

   <span data-ttu-id="1580a-217">系统将提示你添加证书 .pfx 文件。</span><span class="sxs-lookup"><span data-stu-id="1580a-217">You're prompted to add your certificate .pfx file.</span></span>

   ![添加证书。](images/shm-fig6.png)
   
7. <span data-ttu-id="1580a-219">输入你的证书密码，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-219">Enter your certificate password, and then select **OK**.</span></span>

   ![输入证书密码，然后选择"确定"。](images/shm-fig7.png)

8. <span data-ttu-id="1580a-221">选择 **密码保护** 以将密码添加到 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="1580a-221">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="1580a-222">每次启动到 UEFI 时，都需要此密码。</span><span class="sxs-lookup"><span data-stu-id="1580a-222">You'll need this password whenever you boot to UEFI.</span></span> <span data-ttu-id="1580a-223">*我们强烈建议*你设置在 Surface Hub 2S 上使用的 UEFI 密码。</span><span class="sxs-lookup"><span data-stu-id="1580a-223">We *strongly recommend* that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>

   ![选择"密码保护"。](images/shm-fig8.png)
   
9. <span data-ttu-id="1580a-225">设置 UEFI 密码，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-225">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1580a-226">将密码保存在可供管理 Surface Hub 的 IT 管理员访问的安全位置。</span><span class="sxs-lookup"><span data-stu-id="1580a-226">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> <span data-ttu-id="1580a-227">如果密码丢失，则不能恢复。</span><span class="sxs-lookup"><span data-stu-id="1580a-227">If the password is lost, it can't be recovered.</span></span> 

   ![输入 UEFI 密码。](images/shm-fig9.png)

10. <span data-ttu-id="1580a-229">选择**Surface Hub 2S，** 然后选择"下**一步"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-229">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![选择 Surface Hub 2S。](images/shm-fig10.png)
   
11. <span data-ttu-id="1580a-231">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="1580a-231">Select **Next**.</span></span>

    ![选择下一步 。](images/shm-fig10a.png)

12. <span data-ttu-id="1580a-233">若要允许安装 Windows 10 专业版或企业版，请打开**EnableOsMigration，** 然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-233">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![选择"启用 OS 迁移"。](images/shm-fig11.png)
    
    ![将"启用操作系统迁移"设置为"打开"。](images/shm-fig12.png)

### <span data-ttu-id="1580a-236">管理 SEMM 注册</span><span class="sxs-lookup"><span data-stu-id="1580a-236">Managing SEMM enrollment</span></span>

<span data-ttu-id="1580a-237">将设备注册到 SEMM 会影响你可以如何管理设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-237">Enrolling devices into SEMM affects how you can manage the device going forward.</span></span> <span data-ttu-id="1580a-238">例如，应用 SEMM 程序包后，在设备的 UEFI 菜单中，所有 UEFI 设置在锁定 (不可用) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-238">For example, after you apply a SEMM package, in the device's UEFI menu, all UEFI settings are unavailable (locked).</span></span> <span data-ttu-id="1580a-239">其他设置（如 **用于 PXE 启动的 IPv6）的** 默认值也不可用。</span><span class="sxs-lookup"><span data-stu-id="1580a-239">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span> 

<span data-ttu-id="1580a-240">若要在迁移完成后更改 UEFI 设置，请应用另一个 SEMM 程序包，或者从 SEMM 注销设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-240">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="1580a-241">如果应用另一个 SEMM 程序包来更改 UEFI 设置，则必须在生成新的 SEMM 程序包时使用原始证书。</span><span class="sxs-lookup"><span data-stu-id="1580a-241">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="1580a-242">使用 UEFI 配置器工具，将 **EnableOSMigration** (保持关闭状态，如原始迁移步骤) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-242">Use the UEFI Configurator tool and leave **EnableOSMigration** off (not on, as shown in the original migration steps).</span></span>

#### <span data-ttu-id="1580a-243">与合作伙伴合作</span><span class="sxs-lookup"><span data-stu-id="1580a-243">Working with partners</span></span>

<span data-ttu-id="1580a-244">如果你的公司将迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版外包，你可能希望让合作伙伴将 SEMM 证书、SEMM 程序包和 UEFI 密码传输给你。</span><span class="sxs-lookup"><span data-stu-id="1580a-244">If your company is outsourcing the migration to Windows 10 Pro or Enterprise on Surface Hub 2, you may want to have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you.</span></span>  <span data-ttu-id="1580a-245">或者，在迁移中心后，你可以立即从 SEMM 取消注册它，这将允许本地管理 UEFI 以及将设备转移到另一方。</span><span class="sxs-lookup"><span data-stu-id="1580a-245">Alternatively, after migrating the Hub, you can immediately un-enroll it from SEMM, which will allow local administration of UEFI and transfer of the device to another party.</span></span> <span data-ttu-id="1580a-246">但是，仍强烈建议使用可在迁移后配置的 UEFI 密码。</span><span class="sxs-lookup"><span data-stu-id="1580a-246">Nevertheless, it's still strongly recommended to use a UEFI password, which can be configured after migration.</span></span> <span data-ttu-id="1580a-247">若要了解更多信息，请参阅["管理 Surface UEFI 设置"。](https://docs.microsoft.com/surface/manage-surface-uefi-settings)</span><span class="sxs-lookup"><span data-stu-id="1580a-247">To learn more, see [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings).</span></span> 

#### <span data-ttu-id="1580a-248">回滚到 Windows 10 团队</span><span class="sxs-lookup"><span data-stu-id="1580a-248">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="1580a-249">如果在迁移后选择将设备还原到 Windows 10 团队，[](#roll-back-to-windows-10-team)如下所述，建议先从 SEMM 注销 Hub。</span><span class="sxs-lookup"><span data-stu-id="1580a-249">If after migrating you choose to restore your device to Windows 10 Team, [as described below](#roll-back-to-windows-10-team), it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="1580a-250">若要了解更多信息，请参阅 [从 SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-250">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>


#### <span data-ttu-id="1580a-251">将 SEMM 程序包保存到 U 盘</span><span class="sxs-lookup"><span data-stu-id="1580a-251">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="1580a-252">将 U 盘连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="1580a-252">Connect a USB drive to your PC.</span></span> 
1. <span data-ttu-id="1580a-253">选择**中心 2S，** 然后选择"下**一步"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-253">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![选择 USB](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="1580a-255">生成 SEMM 程序包时，将擦除 USB 驱动器上的所有现有数据。</span><span class="sxs-lookup"><span data-stu-id="1580a-255">All existing data on the USB drive is erased when the SEMM package is built.</span></span> <span data-ttu-id="1580a-256">生成 SEMM 程序包之前，请从要保存的 USB 驱动器中删除所有文件。</span><span class="sxs-lookup"><span data-stu-id="1580a-256">Before building the SEMM package, remove any files from the USB drive that you want to save.</span></span>
   
2. <span data-ttu-id="1580a-257">选择“构建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1580a-257">Select **Build**.</span></span>

   ![选择“构建”。](images/shm-fig14.png)

3. <span data-ttu-id="1580a-259">捕获此页面的屏幕截图，然后选择"结束 **"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-259">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="1580a-260">SEMM 程序包现已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="1580a-260">Your SEMM package is now ready.</span></span> <span data-ttu-id="1580a-261">它包含 SEMM 程序包 *DfciUpdate.dfi* 和一个文本文件，其中包含 SEMM 指纹 (证书指纹证书的最后两个字符) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-261">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM thumbprint (the last two characters of the certificate's thumbprint).</span></span>

   ![选择"结束"。](images/shm-fig15.png)
   
4. <span data-ttu-id="1580a-263">保存证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="1580a-263">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="1580a-264">当你在 Surface Hub 2S 上应用程序包时，你将需要这些字符来激活 SEMM。</span><span class="sxs-lookup"><span data-stu-id="1580a-264">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="1580a-265">准备包含 Windows 10 映像、SEMM 程序包和 Surface Hub 2 驱动程序和固件的 U 盘</span><span class="sxs-lookup"><span data-stu-id="1580a-265">Prepare a USB flash drive that contains a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="1580a-266">可以使用以下选项之一 (版本 1903 或) 安装 Windows 10 专业版或企业版映像：</span><span class="sxs-lookup"><span data-stu-id="1580a-266">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) by using one of the following options:</span></span>

- <span data-ttu-id="1580a-267">当前的映像解决方案。</span><span class="sxs-lookup"><span data-stu-id="1580a-267">Your current imaging solution.</span></span>

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> <span data-ttu-id="1580a-268">Surface Deployment Accelerator </a> .</span><span class="sxs-lookup"><span data-stu-id="1580a-268">Surface Deployment Accelerator</a>.</span></span> <span data-ttu-id="1580a-269">使用此工具创建可启动的 Windows 10 映像。</span><span class="sxs-lookup"><span data-stu-id="1580a-269">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="1580a-270">该映像可以包括所有当前的 Windows 10 更新、Office、你选择的其他应用以及所需的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="1580a-270">The image can include all current Windows 10 updates, Office, other apps that you choose, and the required drivers and firmware.</span></span> 

- <span data-ttu-id="1580a-271">包含 Windows 10 专业版或企业版映像的 U 盘。</span><span class="sxs-lookup"><span data-stu-id="1580a-271">USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="1580a-272">然后在 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 上安装适用于 Windows 10 专业版和企业操作系统的驱动程序和固件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1580a-272">Then install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span>
 
<span data-ttu-id="1580a-273">以下过程介绍如何从安装媒体创建 U 盘，然后在 Surface Hub 2 MSI 文件上添加 SEMM 程序包文件和适用于 Windows 10 专业版和企业操作系统的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="1580a-273">The following procedure describes how to create a USB flash drive from installation media, and then add the SEMM package files and the Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="1580a-274">如果你使用的是其他部署方法，请转到 Surface Hub [2S 上的更新 UEFI](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 以启用本文中的操作系统迁移部分。</span><span class="sxs-lookup"><span data-stu-id="1580a-274">If you're using other deployment methods, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="1580a-275">完成安装后，你将需要一个有效的 Windows 10 专业版或 Windows 10 企业版许可证，该许可证独立于现有的 Windows 10 团队版许可证。</span><span class="sxs-lookup"><span data-stu-id="1580a-275">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="1580a-276">若要创建 Windows 10 专业版安装，请按照说明在"下载 <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> Windows 10"页上 </a> 下载媒体创建工具。</span><span class="sxs-lookup"><span data-stu-id="1580a-276">To create a Windows 10 Pro installation, on the<a href="https://www.microsoft.com/software-download/windows10" target="_blank"> Download Windows 10</a> page, follow the instructions to download the media creation tool.</span></span> <span data-ttu-id="1580a-277">若要下载 Windows 10 企业版，请转到 <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft 批量许可服务中心 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1580a-277">To download Windows 10 Enterprise, go to the <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft Volume Licensing Service Center</a>.</span></span>

2. <span data-ttu-id="1580a-278">插入新的 USB 存储驱动器。</span><span class="sxs-lookup"><span data-stu-id="1580a-278">Insert a new USB storage drive.</span></span> 
1. <span data-ttu-id="1580a-279">打开媒体创建工具，选择 **"创建安装媒体**"，然后选择"下**一步"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-279">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![创建安装媒体。](images/shm-fig16.png)
   
3. <span data-ttu-id="1580a-281">选择一种语言，然后选择**Windows 10**和 64 位 (\*\*x64) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="1580a-281">Select a language, and then choose **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="1580a-282">然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-282">Then select **Next**.</span></span>

   ![选择语言，然后选择 Windows 10 和 64 位。](images/shm-fig17.png)
   
4. <span data-ttu-id="1580a-285">选择**U 盘**，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-285">Select **USB flash drive**, and then select **Next**.</span></span>

   ![选择 U S 闪存驱动器，然后选择"下一步"。](images/shm-fig18.png)
   
5. <span data-ttu-id="1580a-287">下载完成后，选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-287">When the download finishes, select **Finish**.</span></span>

   ![选择“完成”。](images/shm-fig19.png)
   
6. <span data-ttu-id="1580a-289">将 SURFACE Hub 2 上的 Windows 10 专业版和企业版操作系统的 SEMM 程序包文件和驱动程序和固件 (MSI 文件) 复制到包含 Windows 10 映像的 U 盘 (*BOOTME*) 的根目录。</span><span class="sxs-lookup"><span data-stu-id="1580a-289">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="1580a-290">BOOTME USB 驱动器包含：</span><span class="sxs-lookup"><span data-stu-id="1580a-290">The BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="1580a-291">Windows 10 可启动映像。</span><span class="sxs-lookup"><span data-stu-id="1580a-291">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="1580a-292">SEMM 包 (复制到 USB 驱动器驱动器的根) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-292">SEMM package files (copied to the root of the USB drive).</span></span>
    
      - <span data-ttu-id="1580a-293">*DfciUpdate.dfi*。</span><span class="sxs-lookup"><span data-stu-id="1580a-293">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="1580a-294">包含 SEMM 指纹的文本文件。</span><span class="sxs-lookup"><span data-stu-id="1580a-294">Text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="1580a-295"> (此示例中，该文件为 *SurfaceUEFI_2020Aug25_1058.txt*.) 自动生成的日期时间戳对应于使用 Surface UEFI 配置器创建文件的日期。</span><span class="sxs-lookup"><span data-stu-id="1580a-295">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="1580a-296">Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-296">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="1580a-297">将此文件复制到 USB 驱动器的根目录。</span><span class="sxs-lookup"><span data-stu-id="1580a-297">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="1580a-298">在 Surface Hub 2S 上更新 UEFI 以启用操作系统迁移</span><span class="sxs-lookup"><span data-stu-id="1580a-298">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="1580a-299">将 BOOTME 驱动器插入 Surface Hub 2S 上的 USB-A 端口。</span><span class="sxs-lookup"><span data-stu-id="1580a-299">Insert your BOOTME drive into the USB-A port on Surface Hub 2S.</span></span> <span data-ttu-id="1580a-300">有关所需文件的列表，请参阅上一节。</span><span class="sxs-lookup"><span data-stu-id="1580a-300">For a list of required files, see the previous section.</span></span>

2. <span data-ttu-id="1580a-301">若要启动到 UEFI：</span><span class="sxs-lookup"><span data-stu-id="1580a-301">To boot into UEFI:</span></span>

   1. <span data-ttu-id="1580a-302">关闭 (Surface Hub 2S) 关闭。</span><span class="sxs-lookup"><span data-stu-id="1580a-302">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="1580a-303">长按 **音量 +**，然后按下并释放电源按钮。</span><span class="sxs-lookup"><span data-stu-id="1580a-303">Press and hold **Volume +**, and then press and release the power button.</span></span>
   1. <span data-ttu-id="1580a-304">保持音量 **+** ，直到 UEFI 菜单出现。</span><span class="sxs-lookup"><span data-stu-id="1580a-304">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![长按调高音量按钮，直到 UEFI 菜单出现。](images/shm-fig20.png)
      
3. <span data-ttu-id="1580a-306">当设备重新启动时，输入之前创建的 UEFI 密码（如果适用 (强烈建议) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-306">When the device restarts, enter the UEFI password that you created earlier, if applicable (strongly recommended).</span></span>

   ![输入 UEFI 密码。](images/shm-fig22.png)
   
4. <span data-ttu-id="1580a-308">在 UEFI 菜单中，选择 **"从**  >  **USB 安装管理"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-308">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![Select Management and Install from U S B.](images/shm-fig21.png)
   
5. <span data-ttu-id="1580a-310">选择 **"立即重启**"，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="1580a-310">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="1580a-311">设备重新启动。</span><span class="sxs-lookup"><span data-stu-id="1580a-311">The device reboots.</span></span> <span data-ttu-id="1580a-312">它在窗口中间显示一个白色 Microsoft 徽标，然后关闭。</span><span class="sxs-lookup"><span data-stu-id="1580a-312">It displays a white Microsoft logo in the middle of the window and then shuts down.</span></span>

   ![选择"立即重启"。](images/shm-fig25.png)
   
6. <span data-ttu-id="1580a-314">按下并释放电源按钮。</span><span class="sxs-lookup"><span data-stu-id="1580a-314">Press and release the power button.</span></span> <span data-ttu-id="1580a-315">在出现的红色窗口中，激活 Surface Enterprise 管理模式。</span><span class="sxs-lookup"><span data-stu-id="1580a-315">In the red window that appears, activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="1580a-316">输入双字符证书指纹和 UEFI 设置密码。</span><span class="sxs-lookup"><span data-stu-id="1580a-316">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="1580a-317">然后选择 **"确定"。**</span><span class="sxs-lookup"><span data-stu-id="1580a-317">Then select **OK**.</span></span>

   ![输入双字符证书指纹和 UEFI 设置密码。](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="1580a-319">在设备上激活 SEMM 后，将应用新的 UEFI 设置**EnableOSMigration。**</span><span class="sxs-lookup"><span data-stu-id="1580a-319">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="1580a-320">你将无法再访问 Windows 10 团队。</span><span class="sxs-lookup"><span data-stu-id="1580a-320">You'll no longer be able to access Windows 10 Team.</span></span> <span data-ttu-id="1580a-321">相反，你必须继续执行下一步并安装 Windows 10 专业版或 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="1580a-321">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

   <span data-ttu-id="1580a-322">设备重新启动。</span><span class="sxs-lookup"><span data-stu-id="1580a-322">The device reboots.</span></span> <span data-ttu-id="1580a-323">它在屏幕中间显示白色徽标，然后再次关闭。</span><span class="sxs-lookup"><span data-stu-id="1580a-323">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="1580a-324">安装 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="1580a-324">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="1580a-325">如果你的可启动 Windows 10 专业版或企业版驱动器尚未在 Surface Hub 2 USB-A 端口中，则现在插入它。</span><span class="sxs-lookup"><span data-stu-id="1580a-325">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="1580a-326">然后按下并释放电源按钮。</span><span class="sxs-lookup"><span data-stu-id="1580a-326">Then press and release the power button.</span></span> 

    <span data-ttu-id="1580a-327">设备启动时，你将在屏幕中间看到白色徽标。</span><span class="sxs-lookup"><span data-stu-id="1580a-327">When the device starts, you see the white logo in the middle of the screen.</span></span> <span data-ttu-id="1580a-328">然后，你将在白色徽标下方看到一个旋转圆圈。</span><span class="sxs-lookup"><span data-stu-id="1580a-328">Then you see a spinning circle below the white logo.</span></span>

3. <span data-ttu-id="1580a-329">如果设备未自动启动到 USB 驱动器，请关闭设备电源 (拔下电源线，然后将其插回) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-329">If the device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="1580a-330">再次插入电缆后，设备应在几秒钟后启动。</span><span class="sxs-lookup"><span data-stu-id="1580a-330">After you plug the power cord in again, the device should boot after a few seconds.</span></span> <span data-ttu-id="1580a-331">然后，你将在屏幕中间看到白色徽标。</span><span class="sxs-lookup"><span data-stu-id="1580a-331">Then you'll see the white logo in the middle of screen.</span></span> 

    <span data-ttu-id="1580a-332">如果设备未打开，请按并释放电源按钮。</span><span class="sxs-lookup"><span data-stu-id="1580a-332">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="1580a-333">在屏幕中间看到徽标后，立即长按音量按钮，直到看到白色徽标下方的旋转圆圈。</span><span class="sxs-lookup"><span data-stu-id="1580a-333">Immediately after you see the logo in the middle of the screen, press and hold the volume button until you see the spinning circle below the white logo.</span></span>
 
   ![从美国 B 驱动器启动到 Windows 10。](images/shm-fig26.png)
   
4. <span data-ttu-id="1580a-335">当 OOBE (OOBE) 安装启动时，请按照说明安装 Windows 10 专业版或企业版 (版本 1903 或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="1580a-335">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="1580a-336">安装 Surface Hub 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="1580a-336">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="1580a-337">若要确保你的设备具有所有最新的更新和驱动程序，请为 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 上的 Windows 10 专业版和企业版操作系统安装驱动程序和固件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1580a-337">To ensure your device has all the latest updates and drivers, install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span> <span data-ttu-id="1580a-338">安装驱动程序和固件 MSI 后，重启设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-338">After installation of the drivers and firmware MSI, reboot the device.</span></span> <span data-ttu-id="1580a-339">然后，重新打开集线器电源后，将电脑电源保持打开状态一小时，然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-339">Then, after powering the Hub back on, keep the PC power on for an hour and reboot the device again.</span></span> <span data-ttu-id="1580a-340">系统不会提示您进行第二次重启。</span><span class="sxs-lookup"><span data-stu-id="1580a-340">You will not be prompted for the second reboot.</span></span> <span data-ttu-id="1580a-341">根据迁移到 Windows 10 专业版或企业版之前计算机的状态，可能需要执行第二步以确保已更新所有固件。</span><span class="sxs-lookup"><span data-stu-id="1580a-341">Depending on the state of your machine prior to migrating to Windows 10 Pro or Enterprise, this second step may be needed to ensure all of the firmware has been updated.</span></span>
 
## <span data-ttu-id="1580a-342">配置建议设置</span><span class="sxs-lookup"><span data-stu-id="1580a-342">Configure recommended settings</span></span>

<span data-ttu-id="1580a-343">若要将 Surface Hub 2S 完全配置为个人生产力设备，请参阅在 Surface Hub 2 上配置 <a href="surface-hub-2-post-install.md" target="_blank"> Windows 10 专业版或企业版 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1580a-343">To fully configure Surface Hub 2S as a personal productivity device, see <a href="surface-hub-2-post-install.md" target="_blank">Configure Windows 10 Pro or Enterprise on Surface Hub 2</a>.</span></span>

> [!NOTE]
><span data-ttu-id="1580a-344">如果本文中概述的步骤无法成功将设备迁移到适用于 Surface Hub 2 的 Windows 10 专业版或企业版，请联系 <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub 支持 </a> 人员。</span><span class="sxs-lookup"><span data-stu-id="1580a-344">If the steps outlined in this article don't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2, contact <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub Support</a>.</span></span>

## <span data-ttu-id="1580a-345">回退到 Windows 10 团队</span><span class="sxs-lookup"><span data-stu-id="1580a-345">Roll back to Windows 10 Team</span></span>

<span data-ttu-id="1580a-346">如果你想要将设备还原到 Windows 10 团队，请参阅 <a href="surface-hub-2s-recover-reset.md" target="_blank"> Surface Hub 2S 的重置和恢复 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1580a-346">If you want to restore your device to Windows 10 Team, see <a href="surface-hub-2s-recover-reset.md" target="_blank"> Reset and recovery for Surface Hub 2S</a>.</span></span>

> [!NOTE]
> <span data-ttu-id="1580a-347">在回滚到 Windows 10 团队之前，建议先从 SEMM 注销 Hub。</span><span class="sxs-lookup"><span data-stu-id="1580a-347">Before rolling back to Windows 10 Team, it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="1580a-348">若要了解更多信息，请参阅 [从 SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="1580a-348">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="1580a-349">版本历史记录</span><span class="sxs-lookup"><span data-stu-id="1580a-349">Version history</span></span>

<span data-ttu-id="1580a-350">下表汇总了对本文所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1580a-350">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="1580a-351">版本</span><span class="sxs-lookup"><span data-stu-id="1580a-351">Version</span></span> | <span data-ttu-id="1580a-352">日期</span><span class="sxs-lookup"><span data-stu-id="1580a-352">Date</span></span>               | <span data-ttu-id="1580a-353">描述</span><span class="sxs-lookup"><span data-stu-id="1580a-353">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1580a-354">v.</span><span class="sxs-lookup"><span data-stu-id="1580a-354">v.</span></span> <span data-ttu-id="1580a-355">1.4</span><span class="sxs-lookup"><span data-stu-id="1580a-355">1.4</span></span>  | <span data-ttu-id="1580a-356">2020 年 12 月 14 日</span><span class="sxs-lookup"><span data-stu-id="1580a-356">December 14, 2020</span></span> | <span data-ttu-id="1580a-357">提供有关[](#install-surface-hub-2-drivers-and-firmware)为"Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件"安装 MSI 文件的进一步信息，提示可能需要根据系统状态进行第二次重启。</span><span class="sxs-lookup"><span data-stu-id="1580a-357">Provides [further info](#install-surface-hub-2-drivers-and-firmware) about installing the MSI file for "Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2," advising that a second reboot may be necessary depending on the state of your system.</span></span>                                                          |
| <span data-ttu-id="1580a-358">v.</span><span class="sxs-lookup"><span data-stu-id="1580a-358">v.</span></span> <span data-ttu-id="1580a-359">1.3</span><span class="sxs-lookup"><span data-stu-id="1580a-359">1.3</span></span>  | <span data-ttu-id="1580a-360">2020 年 12 月 3 日</span><span class="sxs-lookup"><span data-stu-id="1580a-360">December 3, 2020</span></span> | <span data-ttu-id="1580a-361">更新了有关管理 [SEMM 注册的指南](#managing-semm-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="1580a-361">Updated with guidance about [managing SEMM enrollment](#managing-semm-enrollment).</span></span>                                                       |
| <span data-ttu-id="1580a-362">v.</span><span class="sxs-lookup"><span data-stu-id="1580a-362">v.</span></span> <span data-ttu-id="1580a-363">1.2</span><span class="sxs-lookup"><span data-stu-id="1580a-363">1.2</span></span>  | <span data-ttu-id="1580a-364">2020 年 9 月 29 日</span><span class="sxs-lookup"><span data-stu-id="1580a-364">September 29, 2020</span></span> | <span data-ttu-id="1580a-365">处理可用性反馈的杂项更新。</span><span class="sxs-lookup"><span data-stu-id="1580a-365">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="1580a-366">v.</span><span class="sxs-lookup"><span data-stu-id="1580a-366">v.</span></span> <span data-ttu-id="1580a-367">1.1</span><span class="sxs-lookup"><span data-stu-id="1580a-367">1.1</span></span>  | <span data-ttu-id="1580a-368">2020 年 9 月 15 日</span><span class="sxs-lookup"><span data-stu-id="1580a-368">September 15, 2020</span></span> | <span data-ttu-id="1580a-369">在介绍中附加了一条说明，阐明了安装新操作系统的许可要求。</span><span class="sxs-lookup"><span data-stu-id="1580a-369">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="1580a-370">v.</span><span class="sxs-lookup"><span data-stu-id="1580a-370">v.</span></span> <span data-ttu-id="1580a-371">1.0</span><span class="sxs-lookup"><span data-stu-id="1580a-371">1.0</span></span>  | <span data-ttu-id="1580a-372">2020 年 9 月 1 日</span><span class="sxs-lookup"><span data-stu-id="1580a-372">September 1, 2020</span></span>  | <span data-ttu-id="1580a-373">新文章。</span><span class="sxs-lookup"><span data-stu-id="1580a-373">New article.</span></span>                                                                                           |

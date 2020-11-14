---
title: 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文介绍如何从 Surface Hub 2 上的 Windows 10 团队迁移到 Windows 10 Pro 或 Windows 10 企业版。
keywords: Surface Hub 桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/13/2020
ms.localizationpriority: Medium
ms.openlocfilehash: d1099da397e47ad1ea44645623dce48498259eaa
ms.sourcegitcommit: 5c396f37ed90f81373b9fdf8464cb9163f2797d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168571"
---
# <span data-ttu-id="5a762-104">迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="5a762-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="5a762-105">Surface Hub 2 预装了 Windows 10 团队。</span><span class="sxs-lookup"><span data-stu-id="5a762-105">Surface Hub 2S comes preinstalled with Windows 10 Team.</span></span> <span data-ttu-id="5a762-106">此自定义版本的 Windows 10 旨在促进会议室环境中的协作。</span><span class="sxs-lookup"><span data-stu-id="5a762-106">This customized edition of Windows 10 is designed to facilitate collaboration in meeting room environments.</span></span> <span data-ttu-id="5a762-107">现在，你可以选择运行 Windows 10 专业版或企业版来使用 Surface Hub 2，与任何其他电脑非常相似。</span><span class="sxs-lookup"><span data-stu-id="5a762-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="5a762-108">与典型升级或迁移不同，此过程要求你遵循说明性过程，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="5a762-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described in this article.</span></span> <span data-ttu-id="5a762-109">继续之前，请查看 [解决方案组件](#solution-components) 和 [迁移和安装工作流](#migration-and-installation-workflow-summary) 。</span><span class="sxs-lookup"><span data-stu-id="5a762-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before you continue.</span></span>


> [!NOTE]
> <span data-ttu-id="5a762-110">安装 Windows 10 专业版或企业版时，你需要与现有 Windows 10 团队许可证分开的新许可证。</span><span class="sxs-lookup"><span data-stu-id="5a762-110">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="5a762-111">通过使用单独的 PC 和可下载的工具 *SURFACE UEFI 配置*器开始从 Windows 10 团队迁移。</span><span class="sxs-lookup"><span data-stu-id="5a762-111">Start the migration from Windows 10 Team by using a separate PC and the downloadable tool *Surface UEFI Configurator*.</span></span> <span data-ttu-id="5a762-112">使用该工具创建一个程序包，其中包含应用于 Surface Hub 2 的新 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="5a762-112">Use the tool  to create a package that contains a new UEFI setting that you apply to Surface Hub 2S.</span></span>  

<span data-ttu-id="5a762-113">Surface UEFI 配置器在 (SEMM) 的情况下用作 Surface Enterprise 管理模式的接口。</span><span class="sxs-lookup"><span data-stu-id="5a762-113">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="5a762-114">它旨在促进企业环境中 Surface 设备上的固件设置的集中管理。</span><span class="sxs-lookup"><span data-stu-id="5a762-114">It's designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="5a762-115">有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> MICROSOFT SEMM 文档</span><span class="sxs-lookup"><span data-stu-id="5a762-115">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank">Microsoft SEMM documentation</span></span></a>
 

## <span data-ttu-id="5a762-116">解决方案组件</span><span class="sxs-lookup"><span data-stu-id="5a762-116">Solution components</span></span>

- <span data-ttu-id="5a762-117">运行 Windows 10 团队操作系统的 Surface Hub 2 设备</span><span class="sxs-lookup"><span data-stu-id="5a762-117">Surface Hub 2S device running the Windows 10 Team operating system</span></span>
- <span data-ttu-id="5a762-118">运行 Windows 10 的单独设备</span><span class="sxs-lookup"><span data-stu-id="5a762-118">Separate device running Windows 10</span></span>
- <span data-ttu-id="5a762-119">用于创建 SEMM 程序包的 Surface UEFI 配置器工具</span><span class="sxs-lookup"><span data-stu-id="5a762-119">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="5a762-120">Windows 10 专业版或企业版 OS 映像、版本1903或更高版本</span><span class="sxs-lookup"><span data-stu-id="5a762-120">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="5a762-121">具有 16 GB 存储空间的两个 USB 驱动器，FAT32 格式</span><span class="sxs-lookup"><span data-stu-id="5a762-121">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="5a762-122">Surface Hub 2 Microsoft Windows Installer (MSI) 文件的 Windows 10 专业版和企业版 OS 的驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="5a762-122">The Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="5a762-123">Internet 连接</span><span class="sxs-lookup"><span data-stu-id="5a762-123">Internet connection</span></span>
- <span data-ttu-id="5a762-124">图像处理解决方案 (可选) </span><span class="sxs-lookup"><span data-stu-id="5a762-124">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="5a762-125">迁移和安装工作流摘要</span><span class="sxs-lookup"><span data-stu-id="5a762-125">Migration and installation workflow summary</span></span>

| <span data-ttu-id="5a762-126">步骤</span><span class="sxs-lookup"><span data-stu-id="5a762-126">Step</span></span>  | <span data-ttu-id="5a762-127">操作</span><span class="sxs-lookup"><span data-stu-id="5a762-127">Action</span></span>                                                                                                 | <span data-ttu-id="5a762-128">摘要</span><span class="sxs-lookup"><span data-stu-id="5a762-128">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="5a762-129">raid-1</span><span class="sxs-lookup"><span data-stu-id="5a762-129">1</span></span> | [<span data-ttu-id="5a762-130">验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求。</span><span class="sxs-lookup"><span data-stu-id="5a762-130">Verify that the UEFI version on Surface Hub 2S meets minimum requirements.</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="5a762-131">确保 UEFI 版本为694.2938.768.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5a762-131">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="5a762-132">ppls-2</span><span class="sxs-lookup"><span data-stu-id="5a762-132">2</span></span> | [<span data-ttu-id="5a762-133">下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="5a762-133">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="5a762-134">在 " <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **Surface TOOLS for IT** " 页面上 </a> ，选择 "**下载**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-134">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">**Surface Tools for IT** page</a>, select **Download**.</span></span> <span data-ttu-id="5a762-135">然后选择并下载 **SURFACE UEFI 配置器。MSI 文件** 并将其安装在单独的 PC 上。</span><span class="sxs-lookup"><span data-stu-id="5a762-135">Then select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="5a762-136">下载 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 MSI 文件上的 Windows 10 专业版和企业版操作系统的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="5a762-136">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a> <span data-ttu-id="5a762-137">将其保存为在步骤5中使用。</span><span class="sxs-lookup"><span data-stu-id="5a762-137">Save it for use in step 5.</span></span> |
| <span data-ttu-id="5a762-138">三维空间</span><span class="sxs-lookup"><span data-stu-id="5a762-138">3</span></span> | [<span data-ttu-id="5a762-139">准备 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="5a762-139">Prepare SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="5a762-140">准备运行 Surface UEFI 配置器所需的证书。</span><span class="sxs-lookup"><span data-stu-id="5a762-140">Prepare the certificate that's required to run Surface UEFI Configurator.</span></span> <span data-ttu-id="5a762-141">或使用您当前的证书。</span><span class="sxs-lookup"><span data-stu-id="5a762-141">Or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="5a762-142">第</span><span class="sxs-lookup"><span data-stu-id="5a762-142">4</span></span> | [<span data-ttu-id="5a762-143">创建 SEMM 程序包。</span><span class="sxs-lookup"><span data-stu-id="5a762-143">Create SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="5a762-144">Start Surface UEFI 配置器在 USB 驱动器上创建 SEMM 程序包，它将包含你需要在 Surface Hub 2 上应用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="5a762-144">Start Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="5a762-145">将这些 SEMM 软件包文件复制到电脑上的某个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5a762-145">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="5a762-146">级</span><span class="sxs-lookup"><span data-stu-id="5a762-146">5</span></span> | [<span data-ttu-id="5a762-147">准备 USB 闪存驱动器，其中包含适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的 Windows 10 映像、SEMM 软件包和驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="5a762-147">Prepare USB flash drive that contains Windows 10 image, SEMM package, and drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="5a762-148">创建包含 Windows 10 映像的单个 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="5a762-148">Create a single USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="5a762-149">在此示例中，驱动器名为 *BOOTME*。</span><span class="sxs-lookup"><span data-stu-id="5a762-149">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="5a762-150">将 Windows 10 专业版和企业操作系统的驱动程序和固件添加到 Surface Hub 2 (步骤 2) 和 SEMM 软件包文件 (步骤 4) 到 *BOOTME* 驱动器。</span><span class="sxs-lookup"><span data-stu-id="5a762-150">Add your drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (step 2) and SEMM package files (step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="5a762-151">型</span><span class="sxs-lookup"><span data-stu-id="5a762-151">6</span></span> | [<span data-ttu-id="5a762-152">更新 Surface Hub 2 的 UEFI 以启用操作系统迁移。</span><span class="sxs-lookup"><span data-stu-id="5a762-152">Update UEFI on Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="5a762-153">使用 *BOOTME* 驱动器将 Surface Hub 2 启动到 UEFI 菜单并安装 SEMM 程序包。</span><span class="sxs-lookup"><span data-stu-id="5a762-153">Use the *BOOTME* drive to boot Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="5a762-154">7</span><span class="sxs-lookup"><span data-stu-id="5a762-154">7</span></span> | [<span data-ttu-id="5a762-155">安装 Windows 10 专业版或企业版1903或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5a762-155">Install Windows 10 Pro or Enterprise version 1903 or later.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="5a762-156">使用 *BOOTME* 驱动器安装 Windows 10 专业版或企业版1903或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5a762-156">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="5a762-157">个</span><span class="sxs-lookup"><span data-stu-id="5a762-157">8</span></span> | [<span data-ttu-id="5a762-158">为 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统安装驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="5a762-158">Install drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="5a762-159">为确保你的设备具有所有最新的更新和驱动程序，请 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 MSI 文件上安装 Windows 10 专业版和企业版操作系统的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="5a762-159">To ensure your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="5a762-160">db-9</span><span class="sxs-lookup"><span data-stu-id="5a762-160">9</span></span> | [<span data-ttu-id="5a762-161">将 Surface Hub 2 完全配置为个人工作效率设备。</span><span class="sxs-lookup"><span data-stu-id="5a762-161">Fully configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="5a762-162">启用推荐的设置和应用程序以优化 Surface Hub 2 作为个人工作效率设备。</span><span class="sxs-lookup"><span data-stu-id="5a762-162">Enable recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="5a762-163">验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求</span><span class="sxs-lookup"><span data-stu-id="5a762-163">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="5a762-164">在将 Surface Hub 从 Windows 10 团队迁移到 Windows 10 桌面版之前，你需要一个至少 *694.2938.768.0*的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="5a762-164">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need a UEFI version that's at least *694.2938.768.0*.</span></span>
 
<span data-ttu-id="5a762-165">要在系统上验证 UEFI 版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5a762-165">To verify the UEFI version on your system:</span></span>

1. <span data-ttu-id="5a762-166">在 "Surface Hub 2" 主页上，选择 "**开始**"，然后在 "**所有应用**"  >  **图面**) 中打开 Surface app (。</span><span class="sxs-lookup"><span data-stu-id="5a762-166">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="5a762-167">选择 **你的图面** 以显示 surface Hub 的相关信息，包括设备上的当前 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="5a762-167">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="5a762-168">如果 UEFI 版本为 *694.2938.768.0* 或更高版本，如下图所示，你可以创建 SEMM 程序包以启用 OS 迁移。</span><span class="sxs-lookup"><span data-stu-id="5a762-168">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![显示 Surface 应用中的 Surface 页面的屏幕截图。](images/shm-fig1.png)
 
   - <span data-ttu-id="5a762-170">如果 UEFI 版本早于 *694.2938.768.0*，请使用 Windows Update 获取当前版本。</span><span class="sxs-lookup"><span data-stu-id="5a762-170">If the UEFI version is earlier than *694.2938.768.0*, get a current version by using Windows Update.</span></span>

<span data-ttu-id="5a762-171">若要使用 Windows 更新更新 UEFI，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5a762-171">To update the UEFI by using Windows Update:</span></span>

1. <span data-ttu-id="5a762-172">在 Surface Hub 2 秒内，以 **管理员身份**登录。</span><span class="sxs-lookup"><span data-stu-id="5a762-172">On your Surface Hub 2S, sign in as **Admin**.</span></span> 
    >[!Note]
    > <span data-ttu-id="5a762-173">如果您不知道您的用户名或管理员密码，则需要重置设备。</span><span class="sxs-lookup"><span data-stu-id="5a762-173">If you don't know your username or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="5a762-174">有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> 重置和恢复 Surface Hub 2。</span><span class="sxs-lookup"><span data-stu-id="5a762-174">For more information, see <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank">Reset and recovery for Surface Hub 2S.</span></span></a>

1. <span data-ttu-id="5a762-175">转到 "**所有应用**  >  **设置**  >  "**更新和安全**  >  **Windows 更新**，然后安装所有更新。</span><span class="sxs-lookup"><span data-stu-id="5a762-175">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and then install all updates.</span></span> 
1. <span data-ttu-id="5a762-176">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="5a762-176">Restart the device.</span></span> 
1. <span data-ttu-id="5a762-177">使用 Surface app 验证 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="5a762-177">Verify the UEFI version by using the Surface app.</span></span> 
2. <span data-ttu-id="5a762-178">重复这些步骤，直到 UEFI 版本为 *694.2938.768.0* 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5a762-178">Repeat these steps until the UEFI version is *694.2938.768.0* or later.</span></span>
3. <span data-ttu-id="5a762-179">如果在多次尝试后看不到已更新的 UEFI，请检查 " **更新历史记录** " 并查找任何失败的固件安装实例。</span><span class="sxs-lookup"><span data-stu-id="5a762-179">If you don't see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="5a762-180">你可能需要重置设备 (**设置**  >  **更新 & 安全**  >  **重置设备**) 。</span><span class="sxs-lookup"><span data-stu-id="5a762-180">You might need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="5a762-181">下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="5a762-181">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="5a762-182">在单独的 PC 上：</span><span class="sxs-lookup"><span data-stu-id="5a762-182">On a separate PC:</span></span>

1. <span data-ttu-id="5a762-183">在 " <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools FOR IT" 页面上 </a> ，选择 " **下载**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-183">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>  
1. <span data-ttu-id="5a762-184">选择并下载 Surface UEFI 配置器 MSI 文件，并将其安装在单独的电脑上。</span><span class="sxs-lookup"><span data-stu-id="5a762-184">Select and download the Surface UEFI Configurator MSI file and install it on a separate PC.</span></span> <span data-ttu-id="5a762-185">安装 Windows 10 团队版时，不能在 Surface Hub 2 上运行 Surface UEFI 配置器工具。</span><span class="sxs-lookup"><span data-stu-id="5a762-185">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while the Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="5a762-186">下载 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 驱动程序和固件 Windows INSTALLER MSI 文件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-186">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Surface Hub 2 Drivers and Firmware Windows Installer MSI file</a>.</span></span> <span data-ttu-id="5a762-187">安装新操作系统时，您将使用此文件。</span><span class="sxs-lookup"><span data-stu-id="5a762-187">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="5a762-188">准备 SEMM 证书</span><span class="sxs-lookup"><span data-stu-id="5a762-188">Prepare the SEMM certificate</span></span>

<span data-ttu-id="5a762-189">如果你之前未使用 Surface UEFI 配置器，则需要准备证书。</span><span class="sxs-lookup"><span data-stu-id="5a762-189">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="5a762-190">此证书确保在 SEMM 中注册设备后，只能使用使用已批准的证书创建的程序包修改 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="5a762-190">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span> 

<span data-ttu-id="5a762-191">证书的获取方式取决于组织的规模或复杂程度：</span><span class="sxs-lookup"><span data-stu-id="5a762-191">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="5a762-192">企业组织通常会保留自己的基础结构，以便根据标准安全做法生成证书。</span><span class="sxs-lookup"><span data-stu-id="5a762-192">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="5a762-193">中型企业和其他人可以选择从合作伙伴提供商处获取证书。</span><span class="sxs-lookup"><span data-stu-id="5a762-193">Medium-sized businesses and others might choose to get certificates from partner providers.</span></span> <span data-ttu-id="5a762-194">对于没有足够 IT 专业知识或专门 IT 安全团队的组织，建议使用此选项。</span><span class="sxs-lookup"><span data-stu-id="5a762-194">This option is recommended for organizations that don't have sufficient IT expertise or a dedicated IT security team.</span></span>

- <span data-ttu-id="5a762-195">或者，你可以使用 PowerShell 脚本生成自签名证书。</span><span class="sxs-lookup"><span data-stu-id="5a762-195">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="5a762-196">有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> Surface Enterprise 管理模式证书要求 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-196">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank">Surface Enterprise Management Mode certificate requirements </a>.</span></span> <span data-ttu-id="5a762-197">或者，你可以使用 PowerShell 创建你自己的证书。</span><span class="sxs-lookup"><span data-stu-id="5a762-197">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="5a762-198">有关详细信息，请参阅 <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> new-selfsignedcertificate </a> 文档。</span><span class="sxs-lookup"><span data-stu-id="5a762-198">For more information, see the <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate</a> documentation.</span></span>

<span data-ttu-id="5a762-199">Surface UEFI 配置器创建的 SEMM 程序包必须使用证书进行保护。</span><span class="sxs-lookup"><span data-stu-id="5a762-199">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="5a762-200">证书验证配置文件的签名，然后才能应用 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="5a762-200">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="5a762-201">有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 文档 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-201">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM documentation</a>.</span></span>
 
 
### <span data-ttu-id="5a762-202">创建 SEMM 程序包</span><span class="sxs-lookup"><span data-stu-id="5a762-202">Create a SEMM package</span></span>

1. <span data-ttu-id="5a762-203">在单独的电脑上，安装之前下载的 Surface UEFI 配置工具。</span><span class="sxs-lookup"><span data-stu-id="5a762-203">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span> 

2. <span data-ttu-id="5a762-204">打开 Surface UEFI 配置器，然后选择 " **开始**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-204">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![开放式 Surface UEFI 配置器。](images/shm-fig2.png)
   
3. <span data-ttu-id="5a762-206">选择 " **Surface 设备**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-206">Select **Surface Devices**, and then select **Next**.</span></span>

   ![选择 "Surface 设备"。](images/shm-fig3.png)
  
4. <span data-ttu-id="5a762-208">选择 " **配置包**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-208">Select **Configuration Package**.</span></span>

   ![选择 "配置包"。](images/shm-fig4.png)
  
5. <span data-ttu-id="5a762-210">选择 " **证书保护**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-210">Select **Certificate Protection**.</span></span>

   ![选择 "证书保护"。](images/shm-fig5.png)

   <span data-ttu-id="5a762-212">系统将提示您添加证书 .pfx 文件。</span><span class="sxs-lookup"><span data-stu-id="5a762-212">You're prompted to add your certificate .pfx file.</span></span>

   ![添加您的证书。](images/shm-fig6.png)
   
7. <span data-ttu-id="5a762-214">输入你的证书密码，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5a762-214">Enter your certificate password, and then select **OK**.</span></span>

   ![输入您的证书密码，然后选择 "确定"。](images/shm-fig7.png)

8. <span data-ttu-id="5a762-216">选择 " **密码保护** " 以将密码添加到 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="5a762-216">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="5a762-217">当您启动到 UEFI 时，您将需要此密码。</span><span class="sxs-lookup"><span data-stu-id="5a762-217">You'll need this password whenever you boot to UEFI.</span></span> <span data-ttu-id="5a762-218">*强烈建议*你设置你将在 Surface Hub 2 上使用的 UEFI 密码。</span><span class="sxs-lookup"><span data-stu-id="5a762-218">We *strongly recommend* that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>

   ![选择 "密码保护"。](images/shm-fig8.png)
   
9. <span data-ttu-id="5a762-220">设置 UEFI 密码，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5a762-220">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="5a762-221">将密码保存到管理 Surface Hub 的 IT 管理员可以访问的安全位置。</span><span class="sxs-lookup"><span data-stu-id="5a762-221">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> <span data-ttu-id="5a762-222">如果密码丢失，则无法恢复。</span><span class="sxs-lookup"><span data-stu-id="5a762-222">If the password is lost, it can't be recovered.</span></span> 

   ![输入 UEFI 密码。](images/shm-fig9.png)

10. <span data-ttu-id="5a762-224">选择 " **Surface Hub**2"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-224">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![选择 Surface Hub 2。](images/shm-fig10.png)
   
11. <span data-ttu-id="5a762-226">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="5a762-226">Select **Next**.</span></span>

    ![选择下一步 。](images/shm-fig10a.png)

12. <span data-ttu-id="5a762-228">若要允许安装 Windows 10 专业版或企业版，请打开 **EnableOsMigration**，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-228">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![选择 "启用 O S 迁移"。](images/shm-fig11.png)
    
    ![将 "启用 OS 迁移" 设置为 "开"。](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="5a762-231">在应用 SEMM 程序包后，在设备的 UEFI 菜单中，所有 UEFI 设置均不可用 ("已锁定") 。</span><span class="sxs-lookup"><span data-stu-id="5a762-231">After you apply a SEMM package, in the device's UEFI menu, all UEFI settings are unavailable (locked).</span></span> <span data-ttu-id="5a762-232">其他设置（如用于 **PXE 启动的 IPv6** ）的默认值也不可用。</span><span class="sxs-lookup"><span data-stu-id="5a762-232">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span> 
>
><span data-ttu-id="5a762-233">若要在完成迁移后更改 UEFI 设置，请应用另一个 SEMM 程序包或从 SEMM 取消注册设备。</span><span class="sxs-lookup"><span data-stu-id="5a762-233">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="5a762-234">如果你应用另一个 SEMM 程序包以更改 UEFI 设置，则在生成新的 SEMM 程序包时必须使用原始证书。</span><span class="sxs-lookup"><span data-stu-id="5a762-234">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="5a762-235">使用 UEFI 配置器工具，将 **EnableOSMigration** 关闭 (not on，如原始迁移步骤) 所示。</span><span class="sxs-lookup"><span data-stu-id="5a762-235">Use the UEFI Configurator tool and leave **EnableOSMigration** off (not on, as shown in the original migration steps).</span></span>

#### <span data-ttu-id="5a762-236">将 SEMM 程序包保存到 USB 驱动器</span><span class="sxs-lookup"><span data-stu-id="5a762-236">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="5a762-237">将 USB 驱动器连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="5a762-237">Connect a USB drive to your PC.</span></span> 
1. <span data-ttu-id="5a762-238">选择 " **中心2秒**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-238">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![选择 "USB](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="5a762-240">当构建 SEMM 软件包时，将擦除 USB 驱动器上的所有现有数据。</span><span class="sxs-lookup"><span data-stu-id="5a762-240">All existing data on the USB drive is erased when the SEMM package is built.</span></span> <span data-ttu-id="5a762-241">在生成 SEMM 程序包之前，请从要保存的 USB 驱动器中删除所有文件。</span><span class="sxs-lookup"><span data-stu-id="5a762-241">Before building the SEMM package, remove any files from the USB drive that you want to save.</span></span>
   
2. <span data-ttu-id="5a762-242">选择“构建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5a762-242">Select **Build**.</span></span>

   ![选择“构建”。](images/shm-fig14.png)

3. <span data-ttu-id="5a762-244">捕获此页面的屏幕截图，然后选择 " **结束**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-244">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="5a762-245">您的 SEMM 程序包现已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="5a762-245">Your SEMM package is now ready.</span></span> <span data-ttu-id="5a762-246">它包含 SEMM 程序包 *DfciUpdate dfi* 和包含 SEMM 指纹的文本文件 (证书的指纹) 的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="5a762-246">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM thumbprint (the last two characters of the certificate's thumbprint).</span></span>

   ![选择 "结束"。](images/shm-fig15.png)
   
4. <span data-ttu-id="5a762-248">保存证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="5a762-248">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="5a762-249">当你在 Surface Hub 2 上应用包时，你将需要以下字符来激活 SEMM。</span><span class="sxs-lookup"><span data-stu-id="5a762-249">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="5a762-250">准备一个包含 Windows 10 映像、SEMM 软件包和 Surface Hub 2 驱动程序和固件的 USB 闪存驱动器</span><span class="sxs-lookup"><span data-stu-id="5a762-250">Prepare a USB flash drive that contains a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="5a762-251">你可以使用以下选项之一，将 Windows 10 专业版或企业版映像安装 (版本1903或更高版本) ：</span><span class="sxs-lookup"><span data-stu-id="5a762-251">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) by using one of the following options:</span></span>

- <span data-ttu-id="5a762-252">当前的图像处理解决方案。</span><span class="sxs-lookup"><span data-stu-id="5a762-252">Your current imaging solution.</span></span>

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> <span data-ttu-id="5a762-253">Surface 部署加速器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-253">Surface Deployment Accelerator</a>.</span></span> <span data-ttu-id="5a762-254">使用此工具创建可启动的 Windows 10 映像。</span><span class="sxs-lookup"><span data-stu-id="5a762-254">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="5a762-255">该映像可以包括所有当前 Windows 10 更新、Office、你选择的其他应用以及所需的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="5a762-255">The image can include all current Windows 10 updates, Office, other apps that you choose, and the required drivers and firmware.</span></span> 

- <span data-ttu-id="5a762-256">包含 Windows 10 专业版或企业版映像的 USB 闪存驱动器。</span><span class="sxs-lookup"><span data-stu-id="5a762-256">USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="5a762-257">然后 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 上安装 Windows 10 专业版和企业版操作系统的驱动程序和固件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-257">Then install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span>
 
<span data-ttu-id="5a762-258">以下过程介绍了如何从安装媒体创建 USB 闪存驱动器，然后在 Surface Hub 2 MSI 文件上添加 Windows 10 专业版和企业操作系统的 SEMM 软件包文件和驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="5a762-258">The following procedure describes how to create a USB flash drive from installation media, and then add the SEMM package files and the Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="5a762-259">如果您使用的是其他部署方法，请转到 [Surface Hub 2 上的更新 UEFI 以启用](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 本文中的操作系统迁移部分。</span><span class="sxs-lookup"><span data-stu-id="5a762-259">If you're using other deployment methods, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="5a762-260">完成安装后，你需要与现有 Windows 10 团队许可证分开的 Windows 10 专业版或 Windows 10 企业版的有效许可证。</span><span class="sxs-lookup"><span data-stu-id="5a762-260">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="5a762-261">若要创建 Windows 10 专业版安装，请在 " <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> 下载 windows 10" </a> 页面上，按照说明下载媒体创建工具。</span><span class="sxs-lookup"><span data-stu-id="5a762-261">To create a Windows 10 Pro installation, on the<a href="https://www.microsoft.com/software-download/windows10" target="_blank"> Download Windows 10</a> page, follow the instructions to download the media creation tool.</span></span> <span data-ttu-id="5a762-262">若要下载 Windows 10 企业版，请转到 <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft 批量许可服务中心 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-262">To download Windows 10 Enterprise, go to the <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft Volume Licensing Service Center</a>.</span></span>

2. <span data-ttu-id="5a762-263">插入新的 USB 存储驱动器。</span><span class="sxs-lookup"><span data-stu-id="5a762-263">Insert a new USB storage drive.</span></span> 
1. <span data-ttu-id="5a762-264">打开媒体创建工具，选择 " **创建安装媒体**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-264">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![创建安装媒体。](images/shm-fig16.png)
   
3. <span data-ttu-id="5a762-266">选择一种语言，然后选择 " **Windows 10** 和 \*\*64 位 (x64) \*\*"。</span><span class="sxs-lookup"><span data-stu-id="5a762-266">Select a language, and then choose **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="5a762-267">然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-267">Then select **Next**.</span></span>

   ![选择 "语言"，然后选择 "Windows 10 和64位"。](images/shm-fig17.png)
   
4. <span data-ttu-id="5a762-270">选择 " **USB 闪存驱动器**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-270">Select **USB flash drive**, and then select **Next**.</span></span>

   ![选择 "U S B 闪存驱动器"，然后选择 "下一步"。](images/shm-fig18.png)
   
5. <span data-ttu-id="5a762-272">下载完成后，选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="5a762-272">When the download finishes, select **Finish**.</span></span>

   ![选择“完成”。](images/shm-fig19.png)
   
6. <span data-ttu-id="5a762-274">将 SEMM 软件包文件和 Windows 10 专业版的驱动程序和固件复制到 Surface Hub 2 上的 (MSI 文件) 到包含 Windows 10 映像的 USB 闪存驱动器 (*BOOTME*) 的根。</span><span class="sxs-lookup"><span data-stu-id="5a762-274">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="5a762-275">BOOTME USB 驱动器包含：</span><span class="sxs-lookup"><span data-stu-id="5a762-275">The BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="5a762-276">Windows 10 可启动映像。</span><span class="sxs-lookup"><span data-stu-id="5a762-276">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="5a762-277">SEMM 软件包文件 (复制到 USB 驱动器) 的根目录。</span><span class="sxs-lookup"><span data-stu-id="5a762-277">SEMM package files (copied to the root of the USB drive).</span></span>
    
      - <span data-ttu-id="5a762-278">*DfciUpdate dfi*。</span><span class="sxs-lookup"><span data-stu-id="5a762-278">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="5a762-279">包含 SEMM 指纹的文本文件。</span><span class="sxs-lookup"><span data-stu-id="5a762-279">Text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="5a762-280"> (在此示例中，文件 *SurfaceUEFI_2020Aug25_1058.txt*。 ) 自动生成的日期时间戳对应于使用 Surface UEFI 配置器创建文件的日期。</span><span class="sxs-lookup"><span data-stu-id="5a762-280">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="5a762-281">Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="5a762-281">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="5a762-282">将此文件复制到 USB 驱动器的根目录。</span><span class="sxs-lookup"><span data-stu-id="5a762-282">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="5a762-283">更新 Surface Hub 2 的 UEFI 以启用操作系统迁移</span><span class="sxs-lookup"><span data-stu-id="5a762-283">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="5a762-284">将 BOOTME 驱动器插入到 Surface Hub 2 上的 USB 端口。</span><span class="sxs-lookup"><span data-stu-id="5a762-284">Insert your BOOTME drive into the USB-A port on Surface Hub 2S.</span></span> <span data-ttu-id="5a762-285">有关所需文件的列表，请参阅上一节。</span><span class="sxs-lookup"><span data-stu-id="5a762-285">For a list of required files, see the previous section.</span></span>

2. <span data-ttu-id="5a762-286">要启动到 UEFI，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5a762-286">To boot into UEFI:</span></span>

   1. <span data-ttu-id="5a762-287">关闭 Surface Hub 2) 的 (关机。</span><span class="sxs-lookup"><span data-stu-id="5a762-287">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="5a762-288">按住 " **音量 +**"，然后按下并松开 "电源" 按钮。</span><span class="sxs-lookup"><span data-stu-id="5a762-288">Press and hold **Volume +**, and then press and release the power button.</span></span>
   1. <span data-ttu-id="5a762-289">继续保持 **音量 +** ，直到 UEFI 菜单出现。</span><span class="sxs-lookup"><span data-stu-id="5a762-289">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![按住调高音量按钮，直到 UEFI 菜单出现。](images/shm-fig20.png)
      
3. <span data-ttu-id="5a762-291">重新启动设备时，输入你之前创建的 UEFI 密码（如果适用 (强烈建议) ）。</span><span class="sxs-lookup"><span data-stu-id="5a762-291">When the device restarts, enter the UEFI password that you created earlier, if applicable (strongly recommended).</span></span>

   ![输入 UEFI 密码。](images/shm-fig22.png)
   
4. <span data-ttu-id="5a762-293">在 UEFI 菜单中，选择**Management**"  >  **从 USB 安装**管理"。</span><span class="sxs-lookup"><span data-stu-id="5a762-293">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![选择 "管理"，从 U S B 安装。](images/shm-fig21.png)
   
5. <span data-ttu-id="5a762-295">选择 " **立即重启**"，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="5a762-295">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="5a762-296">设备将重新启动。</span><span class="sxs-lookup"><span data-stu-id="5a762-296">The device reboots.</span></span> <span data-ttu-id="5a762-297">它将在窗口中间显示白色 Microsoft 徽标，然后关闭。</span><span class="sxs-lookup"><span data-stu-id="5a762-297">It displays a white Microsoft logo in the middle of the window and then shuts down.</span></span>

   ![选择 "立即重启"。](images/shm-fig25.png)
   
6. <span data-ttu-id="5a762-299">按下并释放 "电源" 按钮。</span><span class="sxs-lookup"><span data-stu-id="5a762-299">Press and release the power button.</span></span> <span data-ttu-id="5a762-300">在出现的红色窗口中，激活 Surface Enterprise 管理模式。</span><span class="sxs-lookup"><span data-stu-id="5a762-300">In the red window that appears, activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="5a762-301">输入两个字符的证书指纹和 UEFI 设置密码。</span><span class="sxs-lookup"><span data-stu-id="5a762-301">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="5a762-302">然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5a762-302">Then select **OK**.</span></span>

   ![输入两个字符的证书指纹和 UEFI 设置密码。](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="5a762-304">在设备上激活 SEMM 后，将应用新的 UEFI 设置 **EnableOSMigration** 。</span><span class="sxs-lookup"><span data-stu-id="5a762-304">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="5a762-305">您将不能再访问 Windows 10 团队。</span><span class="sxs-lookup"><span data-stu-id="5a762-305">You'll no longer be able to access Windows 10 Team.</span></span> <span data-ttu-id="5a762-306">而是必须继续下一步，并安装 Windows 10 专业版或 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="5a762-306">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

   <span data-ttu-id="5a762-307">设备将重新启动。</span><span class="sxs-lookup"><span data-stu-id="5a762-307">The device reboots.</span></span> <span data-ttu-id="5a762-308">它显示屏幕中间的白色徽标，然后再次关闭。</span><span class="sxs-lookup"><span data-stu-id="5a762-308">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="5a762-309">安装 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="5a762-309">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="5a762-310">如果可启动的 Windows 10 专业版或企业版驱动器尚不在 Surface Hub 2 USB-A 端口中，请立即插入。</span><span class="sxs-lookup"><span data-stu-id="5a762-310">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="5a762-311">然后按下并释放 "电源" 按钮。</span><span class="sxs-lookup"><span data-stu-id="5a762-311">Then press and release the power button.</span></span> 

    <span data-ttu-id="5a762-312">当设备启动时，将在屏幕的中间看到白色徽标。</span><span class="sxs-lookup"><span data-stu-id="5a762-312">When the device starts, you see the white logo in the middle of the screen.</span></span> <span data-ttu-id="5a762-313">然后，你将在白色徽标下方看到一个旋转圆。</span><span class="sxs-lookup"><span data-stu-id="5a762-313">Then you see a spinning circle below the white logo.</span></span>

3. <span data-ttu-id="5a762-314">如果设备不会自动启动到 USB 驱动器，请关闭设备 (拔出电源线，然后将其重新插入) 。</span><span class="sxs-lookup"><span data-stu-id="5a762-314">If the device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="5a762-315">再次插入电源线后，设备将在几秒钟后启动。</span><span class="sxs-lookup"><span data-stu-id="5a762-315">After you plug the power cord in again, the device should boot after a few seconds.</span></span> <span data-ttu-id="5a762-316">然后，你将在屏幕中间看到白色徽标。</span><span class="sxs-lookup"><span data-stu-id="5a762-316">Then you'll see the white logo in the middle of screen.</span></span> 

    <span data-ttu-id="5a762-317">如果设备未打开，请按下并释放 "电源" 按钮。</span><span class="sxs-lookup"><span data-stu-id="5a762-317">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="5a762-318">在屏幕中间看到徽标后，按住 "音量" 按钮，直到看到白色徽标下方的旋转圆圈。</span><span class="sxs-lookup"><span data-stu-id="5a762-318">Immediately after you see the logo in the middle of the screen, press and hold the volume button until you see the spinning circle below the white logo.</span></span>
 
   ![从 U S 驱动器启动到 Windows 10。](images/shm-fig26.png)
   
4. <span data-ttu-id="5a762-320">当 (OOBE) 安装程序启动时，请按照说明安装 Windows 10 专业版或企业版 (版本1903或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="5a762-320">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="5a762-321">安装 Surface Hub 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="5a762-321">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="5a762-322">为确保你的设备具有所有最新的更新和驱动程序，请安装 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-322">To ensure your device has all the latest updates and drivers, install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span>
 
## <span data-ttu-id="5a762-323">配置推荐的设置</span><span class="sxs-lookup"><span data-stu-id="5a762-323">Configure recommended settings</span></span>

<span data-ttu-id="5a762-324">若要将 Surface Hub 2 完全配置为个人生产力设备，请参阅 <a href="surface-hub-2-post-install.md" target="_blank"> 在 Surface hub 2 上配置 Windows 10 专业版或企业版 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-324">To fully configure Surface Hub 2S as a personal productivity device, see <a href="surface-hub-2-post-install.md" target="_blank">Configure Windows 10 Pro or Enterprise on Surface Hub 2</a>.</span></span>

> [!NOTE]
><span data-ttu-id="5a762-325">如果本文中概述的步骤未成功将设备迁移到 Windows 10 Pro 或 Surface Hub 2 的企业版，请联系 <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub 支持 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-325">If the steps outlined in this article don't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2, contact <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub Support</a>.</span></span>

## <span data-ttu-id="5a762-326">回退到 Windows 10 团队</span><span class="sxs-lookup"><span data-stu-id="5a762-326">Roll back to Windows 10 Team</span></span>

<span data-ttu-id="5a762-327">如果你想要将设备还原到 Windows 10 团队，请参阅 <a href="surface-hub-2s-recover-reset.md" target="_blank"> 重置和恢复 Surface Hub 2 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5a762-327">If you want to restore your device to Windows 10 Team, see <a href="surface-hub-2s-recover-reset.md" target="_blank"> Reset and recovery for Surface Hub 2S</a>.</span></span>

## <span data-ttu-id="5a762-328">版本历史记录</span><span class="sxs-lookup"><span data-stu-id="5a762-328">Version history</span></span>

<span data-ttu-id="5a762-329">下表总结了本文的更改。</span><span class="sxs-lookup"><span data-stu-id="5a762-329">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="5a762-330">版本</span><span class="sxs-lookup"><span data-stu-id="5a762-330">Version</span></span> | <span data-ttu-id="5a762-331">日期</span><span class="sxs-lookup"><span data-stu-id="5a762-331">Date</span></span>               | <span data-ttu-id="5a762-332">描述</span><span class="sxs-lookup"><span data-stu-id="5a762-332">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="5a762-333">视听.</span><span class="sxs-lookup"><span data-stu-id="5a762-333">v.</span></span> <span data-ttu-id="5a762-334">1.2</span><span class="sxs-lookup"><span data-stu-id="5a762-334">1.2</span></span>  | <span data-ttu-id="5a762-335">2020年9月29日</span><span class="sxs-lookup"><span data-stu-id="5a762-335">September 29, 2020</span></span> | <span data-ttu-id="5a762-336">解决可用性反馈的各种更新。</span><span class="sxs-lookup"><span data-stu-id="5a762-336">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="5a762-337">视听.</span><span class="sxs-lookup"><span data-stu-id="5a762-337">v.</span></span> <span data-ttu-id="5a762-338">1.1</span><span class="sxs-lookup"><span data-stu-id="5a762-338">1.1</span></span>  | <span data-ttu-id="5a762-339">2020年9月15日</span><span class="sxs-lookup"><span data-stu-id="5a762-339">September 15, 2020</span></span> | <span data-ttu-id="5a762-340">在介绍中放置了说明安装新操作系统的许可要求的其他说明。</span><span class="sxs-lookup"><span data-stu-id="5a762-340">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="5a762-341">视听.</span><span class="sxs-lookup"><span data-stu-id="5a762-341">v.</span></span> <span data-ttu-id="5a762-342">1.0</span><span class="sxs-lookup"><span data-stu-id="5a762-342">1.0</span></span>  | <span data-ttu-id="5a762-343">2020年9月1日</span><span class="sxs-lookup"><span data-stu-id="5a762-343">September 1, 2020</span></span>  | <span data-ttu-id="5a762-344">新文章。</span><span class="sxs-lookup"><span data-stu-id="5a762-344">New article.</span></span>                                                                                           |

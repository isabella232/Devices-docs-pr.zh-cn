---
title: 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文介绍从 Surface Hub 2 上的 Windows 10 团队迁移到 Windows 10 Pro 或 Windows 10 企业版的过程。
keywords: Surface Hub 桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 12742cc887ba495f8f7cbded8bd84dc4fd63b6f6
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145967"
---
# <span data-ttu-id="110d4-104">迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="110d4-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

## <span data-ttu-id="110d4-105">简介</span><span class="sxs-lookup"><span data-stu-id="110d4-105">Introduction</span></span>

<span data-ttu-id="110d4-106">Surface Hub 2 是预安装的 Windows 10 团队，它是 Windows 10 的自定义版本，旨在促进会议室环境轻松协作。</span><span class="sxs-lookup"><span data-stu-id="110d4-106">Surface Hub 2S comes pre-installed with Windows 10 Team, a customized edition of Windows 10 designed to facilitate easy collaboration in meeting room environments.</span></span> <span data-ttu-id="110d4-107">现在，你可以选择运行 Windows 10 专业版或企业版来使用 Surface Hub 2，与任何其他电脑非常相似。</span><span class="sxs-lookup"><span data-stu-id="110d4-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="110d4-108">与典型升级或迁移不同，此过程需要遵循说明性过程，如本页所述。</span><span class="sxs-lookup"><span data-stu-id="110d4-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described on this page.</span></span> <span data-ttu-id="110d4-109">继续之前，请先查看 [解决方案组件](#solution-components) 和 [迁移和安装工作流](#migration-and-installation-workflow-summary) 。</span><span class="sxs-lookup"><span data-stu-id="110d4-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before proceeding.</span></span>


> [!NOTE]
> <span data-ttu-id="110d4-110">安装 Windows 10 专业版或企业版时，你将需要与现有 Windows 10 团队许可证分开的新许可证。</span><span class="sxs-lookup"><span data-stu-id="110d4-110">When you install Windows 10 Pro or Enterprise, you will need a new licence separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="110d4-111">从 Windows 10 团队开始迁移，使用单独的 PC 和可下载的工具 **SURFACE UEFI 配置** 器-创建包含应用于 Surface Hub 2 的新 UEFI 设置的包。</span><span class="sxs-lookup"><span data-stu-id="110d4-111">You start the migration from Windows 10 Team using a separate PC and downloadable tool -- **Surface UEFI Configurator** --  to create a package containing a new UEFI setting that you apply to Surface Hub 2S.</span></span>  <span data-ttu-id="110d4-112">Surface UEFI 配置器充当 Surface Enterprise 管理模式 (SEMM) 的接口，旨在促进对公司环境中 Surface 设备上的固件设置的集中管理。</span><span class="sxs-lookup"><span data-stu-id="110d4-112">Surface UEFI Configurator functions as an interface into Surface Enterprise Management Mode (SEMM), designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="110d4-113">若要了解有关 SEMM 的详细信息，请参阅 [Microsoft Surface 企业管理模式文档](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="110d4-113">To learn more about SEMM, see [Microsoft Surface Enterprise Management Mode documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 

## <span data-ttu-id="110d4-114">解决方案组件</span><span class="sxs-lookup"><span data-stu-id="110d4-114">Solution Components</span></span>

- <span data-ttu-id="110d4-115">运行 Windows 10 协同操作系统的 Surface Hub 2 版设备。</span><span class="sxs-lookup"><span data-stu-id="110d4-115">Surface Hub 2S device running Windows 10 Team operating system.</span></span>
- <span data-ttu-id="110d4-116">运行 Windows 10 的单独设备。</span><span class="sxs-lookup"><span data-stu-id="110d4-116">Separate device running Windows 10.</span></span>
- <span data-ttu-id="110d4-117">用于创建 SEMM 程序包的 Surface UEFI 配置器工具。</span><span class="sxs-lookup"><span data-stu-id="110d4-117">Surface UEFI Configurator tool to create the SEMM package.</span></span>
- <span data-ttu-id="110d4-118">Windows 10 专业版或企业版操作系统映像版本1903或更高版本。</span><span class="sxs-lookup"><span data-stu-id="110d4-118">Windows 10 Pro or Enterprise OS image, version 1903 or greater.</span></span>
- <span data-ttu-id="110d4-119">两个 USB 驱动器，其存储空间为 FAT32 格式。</span><span class="sxs-lookup"><span data-stu-id="110d4-119">Two USB drives with 16GB of storage, FAT32 format.</span></span>
- <span data-ttu-id="110d4-120">Surface Hub 2、Windows 安装程序上的 Windows 10 专业版和企业版操作系统的驱动程序和固件。MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="110d4-120">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2, Windows Installer .MSI file.</span></span>
- <span data-ttu-id="110d4-121">互联网连接。</span><span class="sxs-lookup"><span data-stu-id="110d4-121">Internet connection.</span></span>
- <span data-ttu-id="110d4-122">图像处理解决方案 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="110d4-122">Imaging solution (optional).</span></span>

 
## <span data-ttu-id="110d4-123">迁移和安装工作流摘要</span><span class="sxs-lookup"><span data-stu-id="110d4-123">Migration and installation workflow summary</span></span>

| <span data-ttu-id="110d4-124">步骤</span><span class="sxs-lookup"><span data-stu-id="110d4-124">Step</span></span>  | <span data-ttu-id="110d4-125">操作</span><span class="sxs-lookup"><span data-stu-id="110d4-125">Action</span></span>                                                                                                 | <span data-ttu-id="110d4-126">摘要</span><span class="sxs-lookup"><span data-stu-id="110d4-126">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="110d4-127">raid-1</span><span class="sxs-lookup"><span data-stu-id="110d4-127">1</span></span> | [<span data-ttu-id="110d4-128">验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求</span><span class="sxs-lookup"><span data-stu-id="110d4-128">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="110d4-129">确保 UEFI 版本为 **694.2938.768.0** 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="110d4-129">Ensure the UEFI version is **694.2938.768.0** or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="110d4-130">ppls-2</span><span class="sxs-lookup"><span data-stu-id="110d4-130">2</span></span> | [<span data-ttu-id="110d4-131">下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="110d4-131">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="110d4-132">选择 " [Surface Tools FOR IT](https://www.microsoft.com/download/details.aspx?id=46703) " 页面上的 "下载" 按钮，选择并下载 **Surface UEFI 配置器。MSI 文件** 并将其安装在单独的 PC 上。</span><span class="sxs-lookup"><span data-stu-id="110d4-132">Select the Download button on the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page, select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="110d4-133">下载 [适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件。MSI 文件](https://www.microsoft.com/download/details.aspx?id=101974) 并将其保存，以便在步骤5中使用。</span><span class="sxs-lookup"><span data-stu-id="110d4-133">Download [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) and save it for use in Step 5.</span></span> |
| <span data-ttu-id="110d4-134">三维空间</span><span class="sxs-lookup"><span data-stu-id="110d4-134">3</span></span> | [<span data-ttu-id="110d4-135">准备 SEMM 证书</span><span class="sxs-lookup"><span data-stu-id="110d4-135">Prepare SEMM certificate</span></span>](#prepare-semm-certificate)                                                                          | <span data-ttu-id="110d4-136">准备运行 Surface UEFI 配置器所需的证书或使用您的当前证书。</span><span class="sxs-lookup"><span data-stu-id="110d4-136">Prepare required certificate for running Surface UEFI Configurator or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="110d4-137">第</span><span class="sxs-lookup"><span data-stu-id="110d4-137">4</span></span> | [<span data-ttu-id="110d4-138">创建 SEMM 程序包</span><span class="sxs-lookup"><span data-stu-id="110d4-138">Create SEMM package</span></span>](#create-semm-package)                                                                               | <span data-ttu-id="110d4-139">启动 Surface UEFI 配置器在 USB 驱动器上创建 SEMM 程序包，它将包含要应用于 Surface Hub 2 的必需配置文件。</span><span class="sxs-lookup"><span data-stu-id="110d4-139">Launch Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the required configuration files to apply on Surface Hub 2S.</span></span> <span data-ttu-id="110d4-140">将这些 SEMM 软件包文件复制到电脑上的某个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="110d4-140">Copy these SEMM package  files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="110d4-141">级</span><span class="sxs-lookup"><span data-stu-id="110d4-141">5</span></span> | [<span data-ttu-id="110d4-142">准备 USB 闪存驱动器，其中包含适用于 windows 10 的 Windows 10 映像、SEMM 程序包以及适用于 Surface Hub 2 的 Windows 10 专业版和企业操作系统的驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="110d4-142">Prepare USB flash drive containing Windows 10 image, SEMM package, and Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</span></span>](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="110d4-143">在此示例中创建一个 (名为 **BOOTME** 的单个 USB 驱动器，) 包含 Windows 10 图像。</span><span class="sxs-lookup"><span data-stu-id="110d4-143">Create a single USB drive (named **BOOTME** in this example) containing a Windows 10 image.</span></span> <span data-ttu-id="110d4-144">将 Windows 10 专业版和企业操作系统的驱动程序和固件添加到 Surface Hub 2 (步骤 2) 和 SEMM 软件包文件 (步骤 4) 到 **BOOTME** 驱动器。</span><span class="sxs-lookup"><span data-stu-id="110d4-144">Add your Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (Step 2) and SEMM package files (Step 4) to the **BOOTME** drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="110d4-145">型</span><span class="sxs-lookup"><span data-stu-id="110d4-145">6</span></span> | [<span data-ttu-id="110d4-146">更新 Surface Hub 2 的 UEFI 以启用操作系统迁移</span><span class="sxs-lookup"><span data-stu-id="110d4-146">Update UEFI on Surface Hub 2S to enable OS migration</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="110d4-147">使用 **BOOTME** 驱动器将 Surface Hub 2 启动到 UEFI 菜单并安装 SEMM 程序包。</span><span class="sxs-lookup"><span data-stu-id="110d4-147">Use the **BOOTME** drive to boot Surface Hub 2S to the UEFI menu and install SEMM package.</span></span>|
| <span data-ttu-id="110d4-148">7</span><span class="sxs-lookup"><span data-stu-id="110d4-148">7</span></span> | [<span data-ttu-id="110d4-149">安装 Windows 10 专业版或企业版1903或更高版本</span><span class="sxs-lookup"><span data-stu-id="110d4-149">Install Windows 10 Pro or Enterprise version 1903 or later</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="110d4-150">使用 **BOOTME** 驱动器安装 **Windows 10 专业版或企业** 版1903或更高版本。</span><span class="sxs-lookup"><span data-stu-id="110d4-150">Use the **BOOTME** drive to Install **Windows 10 Pro or Enterprise** version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="110d4-151">个</span><span class="sxs-lookup"><span data-stu-id="110d4-151">8</span></span> | [<span data-ttu-id="110d4-152">为 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统安装驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="110d4-152">Install Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="110d4-153">为确保你的设备具有所有最新的更新和驱动程序，请安装 [适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件。MSI 文件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="110d4-153">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="110d4-154">db-9</span><span class="sxs-lookup"><span data-stu-id="110d4-154">9</span></span> | [<span data-ttu-id="110d4-155">将 Surface Hub 2 完全配置为个人生产力设备</span><span class="sxs-lookup"><span data-stu-id="110d4-155">Fully configure Surface Hub 2S as a personal productivity device</span></span>](#next-steps)                                        |  <span data-ttu-id="110d4-156">启用推荐的设置和应用程序，优化将 Surface Hub 2 作为个人生产力设备使用。</span><span class="sxs-lookup"><span data-stu-id="110d4-156">Enable recommended settings and applications to optimize use of Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="110d4-157">验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求</span><span class="sxs-lookup"><span data-stu-id="110d4-157">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="110d4-158">将 Surface Hub 从 Windows 10 团队迁移到 Windows 10 桌面之前所需的最低 UEFI 版本是 **694.2938.768.0**。</span><span class="sxs-lookup"><span data-stu-id="110d4-158">The minimum UEFI version required prior to migrating the Surface Hub from Windows 10 Team to Windows 10 Desktop is **694.2938.768.0**.</span></span>
 
**<span data-ttu-id="110d4-159">要验证系统上的当前 UEFI 版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="110d4-159">To verify the current UEFI version on your system:</span></span>**

1. <span data-ttu-id="110d4-160">在 Surface Hub 2 主屏幕上，选择 "**开始**"，然后打开 " **SurfaceApp** (**所有应用**  >  **Surface** ") 。</span><span class="sxs-lookup"><span data-stu-id="110d4-160">On Surface Hub 2S home screen, select **Start** and open the **SurfaceApp** (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="110d4-161">选择 **你的图面** 以显示 surface Hub 的相关信息，包括设备上的当前 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="110d4-161">Select **Your Surface** to display information about the Surface Hub, including the current UEFI version on the device.</span></span> <span data-ttu-id="110d4-162">如果 UEFI 版本为 **694.2938.768.0** 或更高版本，如下所示，则 UEFI 有资格创建 SEMM 程序包以启用操作系统迁移。</span><span class="sxs-lookup"><span data-stu-id="110d4-162">If the UEFI version is **694.2938.768.0** or later as shown below, the UEFI is eligible for you to create the SEMM package to enable OS migration.</span></span>

    ![打开 Surface App & 选择你的 Surface](images/shm-fig1.png)
 
3. <span data-ttu-id="110d4-164">如果 UEFI 版本早于版本 **694.2938.768.0**，你将需要使用 Windows 更新获取当前版本。</span><span class="sxs-lookup"><span data-stu-id="110d4-164">If the UEFI version is earlier than version **694.2938.768.0**, you will need to obtain a current version using Windows Update.</span></span>

**<span data-ttu-id="110d4-165">要从 Windows 更新更新 UEFI，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="110d4-165">To update UEFI from Windows Update:</span></span>**

1. <span data-ttu-id="110d4-166">在 Surface Hub 2，以**管理员**身份登录，转到 "**所有应用**  >  **设置**"  >  **更新和安全**  >  **Windows 更新**并安装所有更新，然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="110d4-166">On your Surface Hub 2S, sign in as an **Admin**, go to **All apps** > **Settings** > **Update and Security** > **Windows Update** and install all updates, then restart the device.</span></span> <span data-ttu-id="110d4-167">使用 Surface App 验证 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="110d4-167">Verify the UEFI version using the Surface App.</span></span> <span data-ttu-id="110d4-168">**注意：** 如果您不知道您的用户名或管理员密码，将需要重置设备。</span><span class="sxs-lookup"><span data-stu-id="110d4-168">**Note:** If you do not know your username or admin password, you will need to reset the device.</span></span> <span data-ttu-id="110d4-169">若要了解详细信息，请参阅 [重置和恢复 Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)2。</span><span class="sxs-lookup"><span data-stu-id="110d4-169">To learn more, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

2. <span data-ttu-id="110d4-170">重复这些步骤，直到 UEFI 版本为 **694.2938.768.0** 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="110d4-170">Repeat these steps until the UEFI version is **694.2938.768.0** or later.</span></span>

3. <span data-ttu-id="110d4-171">如果在多次尝试后仍然看不到已更新的 UEFI，请检查 " **更新历史记录** " 并查找任何失败的固件安装实例。</span><span class="sxs-lookup"><span data-stu-id="110d4-171">If you still do not see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="110d4-172">你可能需要重置设备 (**设置**  >  **更新 & 安全**  >  **重置设备**) 。</span><span class="sxs-lookup"><span data-stu-id="110d4-172">You may need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="110d4-173">下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="110d4-173">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="110d4-174">在单独的 PC 上：</span><span class="sxs-lookup"><span data-stu-id="110d4-174">On a separate PC:</span></span>

- <span data-ttu-id="110d4-175">选择 " [Surface Tools FOR IT" 页面](https://www.microsoft.com/download/details.aspx?id=46703)上的 "下载" 按钮，选择并下载 Surface UEFI 配置器。MSI 文件并将其安装在单独的 PC 上。</span><span class="sxs-lookup"><span data-stu-id="110d4-175">Select the Download button on the [Surface Tools for IT page](https://www.microsoft.com/download/details.aspx?id=46703), select and download the Surface UEFI Configurator .MSI file and install it on a separate PC.</span></span> <span data-ttu-id="110d4-176">安装 Windows 10 团队版时，不能在 Surface Hub 2 上运行 Surface UEFI 配置器工具。</span><span class="sxs-lookup"><span data-stu-id="110d4-176">The Surface UEFI Configurator tool cannot be run on a Surface Hub 2S while Windows 10 Team edition is installed.</span></span>

- <span data-ttu-id="110d4-177">下载 [Surface Hub 2 驱动程序和固件 Windows 安装程序。](https://www.microsoft.com/download/details.aspx?id=101974) 安装新操作系统时要应用的 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="110d4-177">Download [Surface Hub 2 Drivers and Firmware Windows Installer .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) to be applied when installing the new operating system.</span></span>

### <span data-ttu-id="110d4-178">准备 SEMM 证书</span><span class="sxs-lookup"><span data-stu-id="110d4-178">Prepare SEMM certificate</span></span>

<span data-ttu-id="110d4-179">如果这是你第一次使用 Surface UEFI 配置器，你将需要准备证书。</span><span class="sxs-lookup"><span data-stu-id="110d4-179">If this is your first time using Surface UEFI Configurator, you’ll need to prepare a certificate.</span></span> <span data-ttu-id="110d4-180">此证书确保在 SEMM 中注册设备后，只能使用使用已批准的证书创建的程序包来修改 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="110d4-180">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify UEFI settings.</span></span> <span data-ttu-id="110d4-181">获取证书的方式可能会有所不同，具体取决于组织的规模或复杂程度：</span><span class="sxs-lookup"><span data-stu-id="110d4-181">How you acquire a certificate may vary depending on the size or complexity of your organization:</span></span>

- <span data-ttu-id="110d4-182">大型企业组织通常会保留自己的证书基础结构，以基于标准安全做法生成证书。</span><span class="sxs-lookup"><span data-stu-id="110d4-182">Large enterprise organizations typically maintain their own certificate infrastructure to generate certificates per standard security practices.</span></span>

- <span data-ttu-id="110d4-183">中型企业和其他人可以选择从第三方提供商处获取证书。</span><span class="sxs-lookup"><span data-stu-id="110d4-183">Medium-sized businesses and others may choose to obtain a certificate from third party providers.</span></span> <span data-ttu-id="110d4-184">对于没有足够 IT 专业知识或专门 IT 安全团队的组织，推荐使用此选项。</span><span class="sxs-lookup"><span data-stu-id="110d4-184">This is the recommended option for organizations without sufficient IT expertise or a dedicated IT security team.</span></span>

- <span data-ttu-id="110d4-185">或者，你可以使用以下文档的 PowerShell 脚本生成自签名证书： [Surface Enterprise 管理模式证书要求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。</span><span class="sxs-lookup"><span data-stu-id="110d4-185">Alternatively, you can generate a self-signed certificate with a PowerShell script per the following documentation: [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="110d4-186">或使用 PowerShell 创建你自己的证书，每个文档： [new-selfsignedcertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)。</span><span class="sxs-lookup"><span data-stu-id="110d4-186">Or use PowerShell to create your own certificate per the following documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>

<span data-ttu-id="110d4-187">使用 Surface UEFI 配置工具创建的 SEMM 包必须通过证书进行保护，才能验证配置文件的签名，然后才能应用 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="110d4-187">The SEMM package created by using the Surface UEFI Configurator tool must be secured with a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="110d4-188">若要了解详细信息，请参阅 [Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 文档。</span><span class="sxs-lookup"><span data-stu-id="110d4-188">To learn more, see [Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
 
### <span data-ttu-id="110d4-189">创建 SEMM 程序包</span><span class="sxs-lookup"><span data-stu-id="110d4-189">Create SEMM package</span></span>

1. <span data-ttu-id="110d4-190">将 **SURFACE UEFI 配置** 器工具（如前面已下载的）安装到单独的 PC。</span><span class="sxs-lookup"><span data-stu-id="110d4-190">Install the **Surface UEFI Configurator** tool, as downloaded earlier, to a separate PC.</span></span> 

2. <span data-ttu-id="110d4-191">打开 **SURFACE UEFI 配置** 器，然后选择 " **开始**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-191">Open **Surface UEFI Configurator** and select **Start**.</span></span>

   ![开放式 Surface UEFI 配置器](images/shm-fig2.png)
   
3. <span data-ttu-id="110d4-193">选择 " **Surface 设备** "，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-193">Select **Surface Devices** and then select **Next**.</span></span>

   ![选择 Surface 设备](images/shm-fig3.png)
  
4. <span data-ttu-id="110d4-195">选择 " **配置包**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-195">Select **Configuration Package**.</span></span>

   ![选择配置包](images/shm-fig4.png)
  
5. <span data-ttu-id="110d4-197">选择 " **证书保护**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-197">Select **Certificate Protection**.</span></span>

   ![选择证书保护](images/shm-fig5.png)

6. <span data-ttu-id="110d4-199">系统将提示您添加证书 .pfx 文件。</span><span class="sxs-lookup"><span data-stu-id="110d4-199">You will be prompted to add your certificate .pfx file.</span></span>

   ![系统将提示您添加证书](images/shm-fig6.png)
   
7. <span data-ttu-id="110d4-201">输入您的 **证书密码** ，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="110d4-201">Enter your **Certificate password** and select **OK**.</span></span>

   ![输入你的证书密码，然后选择 "确定"](images/shm-fig7.png)

8. <span data-ttu-id="110d4-203">选择 " **密码保护** " 以将密码添加到 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="110d4-203">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="110d4-204">当您启动到 UEFI 时，将需要此密码。</span><span class="sxs-lookup"><span data-stu-id="110d4-204">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="110d4-205">**强烈建议**设置你将在 Surface Hub 2 秒使用的 UEFI 密码。</span><span class="sxs-lookup"><span data-stu-id="110d4-205">It is **strongly recommended** to set a UEFI password you will use on Surface Hub 2S.</span></span>

   ![单击 "密码保护"](images/shm-fig8.png)
   
9. <span data-ttu-id="110d4-207">设置 **UEFI 密码** ，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="110d4-207">Set a **UEFI password** and select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="110d4-208">将密码保存在你的组织中负责管理 Surface Hub 的 IT 管理员可访问的安全位置。</span><span class="sxs-lookup"><span data-stu-id="110d4-208">Save the password in a secure location accessible to IT admins in your organization responsible for managing Surface Hubs.</span></span> <span data-ttu-id="110d4-209">如果密码丢失，则不会恢复过程。</span><span class="sxs-lookup"><span data-stu-id="110d4-209">If the password is lost, there is no recovery process.</span></span> 

   ![输入你的 UEFI 密码](images/shm-fig9.png)

10. <span data-ttu-id="110d4-211">选择 **Surface Hub** 2-2，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-211">Select **Surface Hub 2S** and then select **Next**.</span></span>

    ![选择 Surface Hub 2](images/shm-fig10.png)
   
11. <span data-ttu-id="110d4-213">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="110d4-213">Select **Next**.</span></span>

    ![选择 "下一步"](images/shm-fig10a.png)

12. <span data-ttu-id="110d4-215">若要允许安装 Windows 10 专业版或企业版，请选择 " **EnableOsMigration"。**</span><span class="sxs-lookup"><span data-stu-id="110d4-215">To allow installation of Windows 10 Pro or Enterprise, select **EnableOsMigration.**</span></span>

    ![选择 "启用 OS 迁移"](images/shm-fig11.png)
    
13. <span data-ttu-id="110d4-217">将 **EnableOSMigration** 设置为 **"打开"** 并选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-217">Set **EnableOSMigration** to **On** and select **Next**.</span></span>

    ![将 "启用 OS 迁移" 设置为 "开"](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="110d4-219">应用 SEMM 程序包后，所有 UEFI 设置将显示为灰色 (在设备上的 UEFI 菜单中已锁定) 。</span><span class="sxs-lookup"><span data-stu-id="110d4-219">After you apply a SEMM package, all UEFI settings will display as grayed out (locked) in the UEFI menu on the device.</span></span> <span data-ttu-id="110d4-220">这包括其他设置（如用于 PXE 启动的 IPv6）的默认值。</span><span class="sxs-lookup"><span data-stu-id="110d4-220">This includes default values for other settings such as IPv6 for PXE Boot.</span></span> <span data-ttu-id="110d4-221">若要在完成迁移后修改 UEFI 设置，你需要应用另一个 SEMM 程序包或从 SEMM 取消注册设备。</span><span class="sxs-lookup"><span data-stu-id="110d4-221">To modify UEFI settings after completing the migration, you will need to apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="110d4-222">如果你应用另一个 SEMM 包来修改 UEFI 设置，则必须使用 UEFI 配置器工具生成新的 SEMM 程序包时使用原始证书，并将 "EnableOSMigration" 关闭 (而不是 "on"，如原始迁移步骤) 所示。</span><span class="sxs-lookup"><span data-stu-id="110d4-222">If you apply another SEMM package to modify the UEFI settings, you must use the original Certificate when building the new SEMM package using the UEFI Configurator tool and leave the "EnableOSMigration" OFF (and not "on" as shown in the original migration steps).</span></span>

#### <span data-ttu-id="110d4-223">将 SEMM 软件包保存到 USB 驱动器</span><span class="sxs-lookup"><span data-stu-id="110d4-223">Save SEMM package to USB drive</span></span>

1. <span data-ttu-id="110d4-224">将 USB 驱动器连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="110d4-224">Connect a USB Drive to your PC.</span></span> <span data-ttu-id="110d4-225">选择 " **中心** 2"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-225">Choose **Hub 2S** and then select **Next**.</span></span>

   ![选择 "USB](images/shm-fig13.png)

> [!WARNING]
> <span data-ttu-id="110d4-227">生成 SEMM 程序包时，将擦除 USB 驱动器上的所有现有数据。</span><span class="sxs-lookup"><span data-stu-id="110d4-227">All existing data on the USB drive is erased when building the SEMM package.</span></span> <span data-ttu-id="110d4-228">在生成 SEMM 程序包之前，请从要保存的 USB 驱动器中删除所有文件。</span><span class="sxs-lookup"><span data-stu-id="110d4-228">Before building the SEMM package, remove any files from the USB drive that you wish to save.</span></span>
   
2. <span data-ttu-id="110d4-229">选择“构建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="110d4-229">Select **Build**.</span></span>

   ![选择 "生成"](images/shm-fig14.png)

3. <span data-ttu-id="110d4-231">捕获此页面的屏幕截图，然后选择 " **结束**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-231">Capture a screenshot of this page and then select **End**.</span></span> <span data-ttu-id="110d4-232">你的 SEMM 程序包现已准备就绪，包含 SEMM 程序包 **DfciUpdate. dfi** 和 SEMM 指纹的文本文件 (证书的指纹) 的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="110d4-232">Your SEMM package is now ready and contains the SEMM package **DfciUpdate.dfi** and a text file with the SEMM thumbprint (the last two characters of the certificate’s thumbprint).</span></span>

   ![选择结束](images/shm-fig15.png)
   
4. <span data-ttu-id="110d4-234">保存证书指纹的最后2个字符，当你在 Surface Hub 2 上应用包时，激活 SEMM 需要该字符。</span><span class="sxs-lookup"><span data-stu-id="110d4-234">Save the certificate thumbprint’s last 2 characters, which is required to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="110d4-235">准备包含 Windows 10 映像、SEMM 程序包和 Surface Hub 2 驱动程序和固件的 USB 闪存驱动器</span><span class="sxs-lookup"><span data-stu-id="110d4-235">Prepare USB flash drive containing Windows 10 image, SEMM package, and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="110d4-236">你可以使用以下选项之一 (版本1903或更高版本) 安装 Windows 10 专业版或企业版映像：</span><span class="sxs-lookup"><span data-stu-id="110d4-236">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) using one of the following options:</span></span>

- <span data-ttu-id="110d4-237">当前的图像处理解决方案。</span><span class="sxs-lookup"><span data-stu-id="110d4-237">Your current imaging solution.</span></span>

- <span data-ttu-id="110d4-238">[Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) 允许你创建可启动的 Windows 10 映像，其中包括所有当前 Windows 10 更新、Office、你选择的其他应用以及所需的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="110d4-238">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) lets you create a bootable Windows 10 image which can include all current Windows 10 updates, Office, other apps of your choice, as well as the required drivers and firmware.</span></span> 

- <span data-ttu-id="110d4-239">带有 Windows 10 专业版或企业版映像的 USB 闪存驱动器，然后安装了  [适用于 Surface Hub 2 上的 windows 10 专业版和企业版操作系统的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="110d4-239">USB flash drive with Windows 10 Pro or Enterprise image, followed by installing  [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
<span data-ttu-id="110d4-240">此过程介绍如何从安装媒体创建一个 USB 闪存驱动器，然后添加 SEMM 程序包文件和适用于 Surface Hub 2 上的 Windows 10 Pro 和企业操作系统的驱动程序和固件。MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="110d4-240">This procedure describes creating a USB flash drive from installation media and then adding the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 .MSI file.</span></span> <span data-ttu-id="110d4-241">如果你使用的是其他部署方法，请转到 [Surface Hub 2 的更新 UEFI 部分以启用操作系统迁移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)。</span><span class="sxs-lookup"><span data-stu-id="110d4-241">If you’re using other deployment methods, proceed to the section [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="110d4-242">安装后，你将需要与现有 Windows 10 团队许可证分开的 Windows 10 专业版或 Windows 10 企业版有效许可证。</span><span class="sxs-lookup"><span data-stu-id="110d4-242">Once installed, you will need a valid license for Windows 10 Pro or Windows 10 Enterprise that is separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="110d4-243">若要创建 Windows 10 专业版安装，请按照 [下载 windows 10](https://www.microsoft.com/software-download/windows10) 页面上的说明使用 **媒体创建** 工具。</span><span class="sxs-lookup"><span data-stu-id="110d4-243">To create a Windows 10 Pro installation, follow the instructions on the [Download Windows 10](https://www.microsoft.com/software-download/windows10) page for using the **Media Creation** tool.</span></span> <span data-ttu-id="110d4-244">若要下载 Windows 10 企业版，请转到 [Microsoft 批量许可服务中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="110d4-244">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

2. <span data-ttu-id="110d4-245">插入新的 **USB 存储** 驱动器。</span><span class="sxs-lookup"><span data-stu-id="110d4-245">Insert a new **USB storage** drive.</span></span> <span data-ttu-id="110d4-246">启动 " **媒体创建** " 工具，选择 " **创建安装媒体** "，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-246">Launch the **Media Creation** tool, select **Create installation media** and then select **Next**.</span></span>

   ![创建安装媒体](images/shm-fig16.png)
   
3. <span data-ttu-id="110d4-248">选择 "语言"、"Windows 10" 和 "64 (x64") 然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-248">Select language, Windows 10, and 64-bit (x64) and then select **Next**.</span></span>

   ![选择 "语言"、"Windows 10" 和 "64 位 & 选择" 下一步 "](images/shm-fig17.png)
   
4. <span data-ttu-id="110d4-250">选择 " **USB 闪存驱动器** "，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-250">Select **USB flash drive** and select **Next**.</span></span>

   ![选择 "USB 闪存驱动器"，然后选择 "下一步"](images/shm-fig18.png)
   
5. <span data-ttu-id="110d4-252">下载完成后，选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="110d4-252">When the download completes, select **Finish**.</span></span>

   ![选择 "完成"](images/shm-fig19.png)
   
6. <span data-ttu-id="110d4-254">在 Surface Hub 2 ( 上复制 Windows 10 专业版和企业版操作系统的 SEMM 软件包文件和驱动程序和固件。MSI 文件) 到包含 Windows 10 映像的 USB 闪存驱动器 (**BOOTME**) 的根。</span><span class="sxs-lookup"><span data-stu-id="110d4-254">Copy the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (.MSI file) to the ROOT of the USB flash drive (**BOOTME**) containing your Windows 10 image.</span></span> <span data-ttu-id="110d4-255">BOOTME USB 驱动器包含：</span><span class="sxs-lookup"><span data-stu-id="110d4-255">BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="110d4-256">Windows 10 可启动映像。</span><span class="sxs-lookup"><span data-stu-id="110d4-256">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="110d4-257">SEMM 软件包文件 (复制到 USB 驱动器的根目录) </span><span class="sxs-lookup"><span data-stu-id="110d4-257">SEMM package files (copied to the root of the USB drive)</span></span>
    
      - <span data-ttu-id="110d4-258">DfciUpdate.dfi.</span><span class="sxs-lookup"><span data-stu-id="110d4-258">DfciUpdate.dfi.</span></span>
      - <span data-ttu-id="110d4-259">带有 SEMM 指纹的文本文件。</span><span class="sxs-lookup"><span data-stu-id="110d4-259">Text file with the SEMM thumbprint.</span></span> <span data-ttu-id="110d4-260">此示例中的 (： SurfaceUEFI_2020Aug25_1058.txt。 ) 自动生成的日期时间戳对应于使用 Surface UEFI 配置器创建文件的日期。</span><span class="sxs-lookup"><span data-stu-id="110d4-260">(In this example: SurfaceUEFI_2020Aug25_1058.txt.) The auto-generated date timestamp corresponds to the date that you created the file using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="110d4-261">Surface Hub 2 上的 Windows 10 专业版和企业操作系统的驱动程序和固件 ( # A0) ，也复制到 USB 驱动器的根目录。</span><span class="sxs-lookup"><span data-stu-id="110d4-261">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi), also copied to the root of the USB drive.</span></span>

### <span data-ttu-id="110d4-262">更新 Surface Hub 2 的 UEFI 以启用操作系统迁移</span><span class="sxs-lookup"><span data-stu-id="110d4-262">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="110d4-263">将 **BOOTME** 驱动器插入到 Surface Hub 2 上的 USB 端口。</span><span class="sxs-lookup"><span data-stu-id="110d4-263">Insert your **BOOTME** drive into the USB-A port on Surface Hub 2S.</span></span> <span data-ttu-id="110d4-264"> (请参阅上一节，了解所需文件的列表。 ) </span><span class="sxs-lookup"><span data-stu-id="110d4-264">(See the previous section for the list of required files.)</span></span>

2. <span data-ttu-id="110d4-265">要启动到 UEFI，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="110d4-265">To boot into UEFI:</span></span>

   1. <span data-ttu-id="110d4-266">关闭 Surface Hub 2) 的 (关闭电源。</span><span class="sxs-lookup"><span data-stu-id="110d4-266">Power off (shutdown) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="110d4-267">按住 " **音量 +** "，然后按下并松开 " **电源** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="110d4-267">Press and hold **Volume +** and then press and release the **Power** button.</span></span>
   1. <span data-ttu-id="110d4-268">继续保持 **音量 +** ，直到 UEFI 菜单出现。</span><span class="sxs-lookup"><span data-stu-id="110d4-268">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![保留 holdling 的音量 +，直到 UEFI 菜单出现](images/shm-fig20.png)
      
3. <span data-ttu-id="110d4-270">重新启动设备时，输入你之前创建的 UEFI 密码（如果适用 (强烈建议) ）。</span><span class="sxs-lookup"><span data-stu-id="110d4-270">When the device restarts, enter the UEFI password you created earlier, if applicable (strongly recommended).</span></span>

   ![当设备重新启动时，请输入 UEFI paassword](images/shm-fig22.png)
   
4. <span data-ttu-id="110d4-272">在 UEFI 菜单中，选择**Management**"  >  **从 USB 安装**管理"。</span><span class="sxs-lookup"><span data-stu-id="110d4-272">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![选择 "管理 & 从 USB 安装"](images/shm-fig21.png)
   
5. <span data-ttu-id="110d4-274">选择 " **立即重启**"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="110d4-274">Select **Restart now**, as shown below.</span></span> <span data-ttu-id="110d4-275">设备将重新启动并在屏幕中间显示 "4 平方" 徽标，然后关闭。</span><span class="sxs-lookup"><span data-stu-id="110d4-275">The device will reboot and display the white 4-square logo in the middle of screen and then shut down.</span></span>

   ![选择 "立即重启"](images/shm-fig25.png)
   
6. <span data-ttu-id="110d4-277">按下并释放 "电源" 按钮，将显示一个红色屏幕，提示你激活 Surface Enterprise 管理模式。</span><span class="sxs-lookup"><span data-stu-id="110d4-277">Press and release the power button, a red screen will display prompting you to activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="110d4-278">输入你的两个字符的 **证书指纹**，你的 **UEFI 设置密码** ，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="110d4-278">Enter your two-character **certificate thumbprint**, your **UEFI settings password** and then select **OK**.</span></span>

   ![输入2个字符的证书指纹](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="110d4-280">在设备上激活 SEMM 后，将应用新的 UEFI 设置 **EnableOSMigration** 。</span><span class="sxs-lookup"><span data-stu-id="110d4-280">Once you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="110d4-281">你将无法再访问 Windows 10 团队，并且必须继续下一步，并安装 Windows 10 专业版或 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="110d4-281">You will no longer be able to access Windows 10 Team and must proceed to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

8. <span data-ttu-id="110d4-282">设备将重新启动，显示屏幕中间的白色4方形徽标，然后将再次关闭。</span><span class="sxs-lookup"><span data-stu-id="110d4-282">The device will reboot, display the white 4-square logo in the middle of the screen, and then it will shut down again.</span></span>

### <span data-ttu-id="110d4-283">安装 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="110d4-283">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="110d4-284">如果可启动的 Windows 10 专业版或企业版驱动器尚未插入 Surface Hub 2 USB-A 端口，请立即插入，然后按下并释放电源按钮。</span><span class="sxs-lookup"><span data-stu-id="110d4-284">If your bootable Windows 10 Pro or Enterprise drive is not already in the Surface Hub 2 USB-A port, insert it now and then press and release the power button.</span></span>

2. <span data-ttu-id="110d4-285">设备将启动，你将在屏幕中间看到白色的4方块，然后你将在白色四个方形的徽标下方看到旋转的圆圈。</span><span class="sxs-lookup"><span data-stu-id="110d4-285">The device will start, you will see the white 4-square in the middle of the screen, and then you will see a spinning circle below the white four-square logo.</span></span>

3. <span data-ttu-id="110d4-286">如果设备不会自动启动到 USB 驱动器，请关闭设备 (拔出电源线，然后再将其插入) 。</span><span class="sxs-lookup"><span data-stu-id="110d4-286">If the device does not automatically boot to the USB drive, power off the device (unplug the power cord and plug it back in).</span></span> <span data-ttu-id="110d4-287">重新插入电源线后，设备将在几秒钟后启动到屏幕中间的白色4方形徽标，或者按下并释放电源按钮以重新打开设备。</span><span class="sxs-lookup"><span data-stu-id="110d4-287">After plugging the power cord back in, the device should boot after a few seconds to the white 4-square logo in the middle of screen, or you can press and release the power button to turn the device back on.</span></span> <span data-ttu-id="110d4-288">在屏幕中间看到4个方形的徽标后，按住音量按钮，直到看到位于白色四个方形徽标下方的旋转圆圈。</span><span class="sxs-lookup"><span data-stu-id="110d4-288">Immediately after you see the 4-square logo in the middle of the screen, press and hold the volume down button until you see the spinning circle below the white four-square logo.</span></span>
 
   ![从 USB 启动到 Windows 10](images/shm-fig26.png)
   
4. <span data-ttu-id="110d4-290">当 (OOBE) 安装程序启动时，请按照说明安装 Windows 10 专业版或企业版 (版本1903或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="110d4-290">When the out-of-box experience (OOBE) setup launches, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="110d4-291">安装 Surface Hub 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="110d4-291">Install Surface Hub 2 drivers and firmware</span></span>

 - <span data-ttu-id="110d4-292">为确保你的设备具有所有最新的更新和驱动程序，请安装 [适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="110d4-292">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
### <span data-ttu-id="110d4-293">后续步骤</span><span class="sxs-lookup"><span data-stu-id="110d4-293">Next steps</span></span>

<span data-ttu-id="110d4-294">若要将 Surface Hub 2 完全配置为个人生产力设备，请参阅 [在 Surface hub 2 上配置 Windows 10 专业版或企业版](surface-hub-2-post-install.md)。</span><span class="sxs-lookup"><span data-stu-id="110d4-294">To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="110d4-295">如果按照本文档中概述的步骤将设备迁移到 Windows 10 Pro 或 Enterprise for Surface Hub 2，请联系 [Surface Hub 支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。</span><span class="sxs-lookup"><span data-stu-id="110d4-295">If following the steps outlined in this document is unsuccessful in migrating your device to Windows 10 Pro or Enterprise for Surface Hub 2, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

### <span data-ttu-id="110d4-296">回滚到 Windows 10 团队</span><span class="sxs-lookup"><span data-stu-id="110d4-296">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="110d4-297">如果你想要将设备还原到 Windows 10 团队，请参阅 [重置和恢复 Surface Hub](surface-hub-2s-recover-reset.md)2。</span><span class="sxs-lookup"><span data-stu-id="110d4-297">If you would Like to restore your device to Windows 10 Team, refer to [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

## <span data-ttu-id="110d4-298">版本历史记录</span><span class="sxs-lookup"><span data-stu-id="110d4-298">Version history</span></span>

| <span data-ttu-id="110d4-299">版本</span><span class="sxs-lookup"><span data-stu-id="110d4-299">Version</span></span> | <span data-ttu-id="110d4-300">日期</span><span class="sxs-lookup"><span data-stu-id="110d4-300">Date</span></span>               | <span data-ttu-id="110d4-301">描述</span><span class="sxs-lookup"><span data-stu-id="110d4-301">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="110d4-302">视听.</span><span class="sxs-lookup"><span data-stu-id="110d4-302">v.</span></span> <span data-ttu-id="110d4-303">1.2</span><span class="sxs-lookup"><span data-stu-id="110d4-303">1.2</span></span>  | <span data-ttu-id="110d4-304">2020年9月29日</span><span class="sxs-lookup"><span data-stu-id="110d4-304">September 29, 2020</span></span> | <span data-ttu-id="110d4-305">每种可用性反馈的各种更新。</span><span class="sxs-lookup"><span data-stu-id="110d4-305">Miscellaneous updates per usability feedback.</span></span>                                                        |
| <span data-ttu-id="110d4-306">视听.</span><span class="sxs-lookup"><span data-stu-id="110d4-306">v.</span></span> <span data-ttu-id="110d4-307">1.1</span><span class="sxs-lookup"><span data-stu-id="110d4-307">1.1</span></span>  | <span data-ttu-id="110d4-308">2020年9月15日</span><span class="sxs-lookup"><span data-stu-id="110d4-308">September 15, 2020</span></span> | <span data-ttu-id="110d4-309">在介绍介绍安装新操作系统的许可要求中放置了其他笔记。</span><span class="sxs-lookup"><span data-stu-id="110d4-309">Placed additional note in the Introduction clarifying licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="110d4-310">视听.</span><span class="sxs-lookup"><span data-stu-id="110d4-310">v.</span></span> <span data-ttu-id="110d4-311">1.0</span><span class="sxs-lookup"><span data-stu-id="110d4-311">1.0</span></span>  | <span data-ttu-id="110d4-312">2020年9月1日</span><span class="sxs-lookup"><span data-stu-id="110d4-312">September 1, 2020</span></span>  | <span data-ttu-id="110d4-313">新文章。</span><span class="sxs-lookup"><span data-stu-id="110d4-313">New article.</span></span>                                                                                           |

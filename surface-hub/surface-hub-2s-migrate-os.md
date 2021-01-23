---
title: 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 如何从 Surface Hub 2 上的 Windows 10 团队迁移到 Windows 10 专业版或 Windows 10 企业版。
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
ms.openlocfilehash: d7ecee2ca66640b054efc106191d12c1844b90a1
ms.sourcegitcommit: 1bc22f7343af9b1b1b8b375d540adee2af68e693
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297635"
---
# <span data-ttu-id="d11b1-104">迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="d11b1-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

- [<span data-ttu-id="d11b1-105">文章版本历史记录</span><span class="sxs-lookup"><span data-stu-id="d11b1-105">Article version history</span></span>](#version-history)

<span data-ttu-id="d11b1-106">Surface Hub 2S 附带 Windows 10 团队。</span><span class="sxs-lookup"><span data-stu-id="d11b1-106">Surface Hub 2S comes with Windows 10 Team installed.</span></span> <span data-ttu-id="d11b1-107">此自定义版本的 Windows 10 促进在会议室环境中进行协作。</span><span class="sxs-lookup"><span data-stu-id="d11b1-107">This customized edition of Windows 10 facilitates collaboration in meeting-room environments.</span></span> <span data-ttu-id="d11b1-108">你现在可以改为运行 Windows 10 专业版或企业版来使用 Surface Hub 2S，这非常像任何其他电脑。</span><span class="sxs-lookup"><span data-stu-id="d11b1-108">You can now instead run Windows 10 Pro or Enterprise to use your Surface Hub 2S much like any other PC.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d11b1-109">此迁移过程要求您遵循本文中所述的特定过程。</span><span class="sxs-lookup"><span data-stu-id="d11b1-109">This migration process requires you to follow the specific procedure that's described in this article.</span></span> <span data-ttu-id="d11b1-110">在继续之前，请阅读 [解决方案组件](#solution-components) 以及 [迁移和安装工作流](#migration-and-installation-workflow-summary)。</span><span class="sxs-lookup"><span data-stu-id="d11b1-110">Before you continue, read [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary).</span></span>

> [!NOTE]
> <span data-ttu-id="d11b1-111">安装 Windows 10 专业版或企业版时，需要一个独立于现有 Windows 10 团队版许可证的新许可证。</span><span class="sxs-lookup"><span data-stu-id="d11b1-111">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span>

<span data-ttu-id="d11b1-112">使用单独的电脑和可下载的 *Surface UEFI 配置* 器工具开始从 Windows 10 团队迁移。</span><span class="sxs-lookup"><span data-stu-id="d11b1-112">Start the migration from Windows 10 Team by using a separate PC and the downloadable *Surface UEFI Configurator* tool.</span></span> <span data-ttu-id="d11b1-113">该工具将创建一个程序包，其中包含适用于 Surface Hub 2S 的新 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="d11b1-113">The tool creates a package that contains a new UEFI setting that you apply to the Surface Hub 2S.</span></span>  

<span data-ttu-id="d11b1-114">Surface UEFI 配置器用作 SEMM (Surface 企业管理模式的) 。</span><span class="sxs-lookup"><span data-stu-id="d11b1-114">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="d11b1-115">它支持在企业环境中集中管理 Surface 设备的固件设置。</span><span class="sxs-lookup"><span data-stu-id="d11b1-115">It enables centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="d11b1-116">有关详细信息，请参阅 [Microsoft Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="d11b1-116">For more information, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 
## <span data-ttu-id="d11b1-117">解决方案组件</span><span class="sxs-lookup"><span data-stu-id="d11b1-117">Solution components</span></span>

- <span data-ttu-id="d11b1-118">运行 Windows 10 团队的 Surface Hub 2S 设备</span><span class="sxs-lookup"><span data-stu-id="d11b1-118">Surface Hub 2S device running Windows 10 Team</span></span>
- <span data-ttu-id="d11b1-119">运行 Windows 10 的单独设备</span><span class="sxs-lookup"><span data-stu-id="d11b1-119">Separate device running Windows 10</span></span>
- <span data-ttu-id="d11b1-120">用于创建 SEMM 程序包的 Surface UEFI 配置器工具</span><span class="sxs-lookup"><span data-stu-id="d11b1-120">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="d11b1-121">Windows 10 专业版或企业版操作系统映像版本 1903 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d11b1-121">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="d11b1-122">两个存储为 16 GB 的 USB 驱动器，FAT32 格式</span><span class="sxs-lookup"><span data-stu-id="d11b1-122">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="d11b1-123">Surface Hub 2 中的 Windows 10 专业版和企业版驱动程序和Microsoft Windows Installer (MSI) 文件</span><span class="sxs-lookup"><span data-stu-id="d11b1-123">The drivers and firmware for Windows 10 Pro and Enterprise in a Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="d11b1-124">Internet 连接</span><span class="sxs-lookup"><span data-stu-id="d11b1-124">Internet connection</span></span>
- <span data-ttu-id="d11b1-125">映像解决方案 (可选) </span><span class="sxs-lookup"><span data-stu-id="d11b1-125">Imaging solution (optional)</span></span>
 
## <span data-ttu-id="d11b1-126">迁移和安装工作流摘要</span><span class="sxs-lookup"><span data-stu-id="d11b1-126">Migration and installation workflow summary</span></span>

| <span data-ttu-id="d11b1-127">步骤</span><span class="sxs-lookup"><span data-stu-id="d11b1-127">Step</span></span>  | <span data-ttu-id="d11b1-128">操作</span><span class="sxs-lookup"><span data-stu-id="d11b1-128">Action</span></span>                                                                                                 | <span data-ttu-id="d11b1-129">摘要</span><span class="sxs-lookup"><span data-stu-id="d11b1-129">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d11b1-130">1</span><span class="sxs-lookup"><span data-stu-id="d11b1-130">1</span></span> | <span data-ttu-id="d11b1-131">[验证 Surface Hub 2S 上的 UEFI 版本](#verify-the-uefi-version-on-surface-hub-2s)。</span><span class="sxs-lookup"><span data-stu-id="d11b1-131">[Verify the UEFI version on the Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s).</span></span>                                  | <span data-ttu-id="d11b1-132">UEFI 版本必须为版本 *694.2938.768.0 或* 更高版本。</span><span class="sxs-lookup"><span data-stu-id="d11b1-132">The UEFI version must be version *694.2938.768.0* or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="d11b1-133">2</span><span class="sxs-lookup"><span data-stu-id="d11b1-133">2</span></span> | [<span data-ttu-id="d11b1-134">下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-134">Download Surface UEFI Configurator and the Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="d11b1-135">在**[Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)** 页面上 </a> ，选择"**下载"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-135">On the **[Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)** page</a>, select **Download**.</span></span> <span data-ttu-id="d11b1-136">然后选择并下载 **Surface UEFI 配置程序 MSI**文件，然后在单独的电脑上安装该文件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-136">Then select and download the **Surface UEFI Configurator MSI file**, and install it on a separate PC.</span></span> <span data-ttu-id="d11b1-137">此外，在 [Surface Hub 2 MSI](https://www.microsoft.com/download/details.aspx?id=101974)文件上下载适用于 Windows 10 专业版和企业操作系统的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-137">Also download the [Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span></a> <span data-ttu-id="d11b1-138">保存此程序包以在步骤 5 中使用。</span><span class="sxs-lookup"><span data-stu-id="d11b1-138">Save this package for use in step 5.</span></span> |
| <span data-ttu-id="d11b1-139">3</span><span class="sxs-lookup"><span data-stu-id="d11b1-139">3</span></span> | [<span data-ttu-id="d11b1-140">准备 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="d11b1-140">Prepare the SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="d11b1-141">准备运行 Surface UEFI 配置程序所需的证书，或使用当前证书。</span><span class="sxs-lookup"><span data-stu-id="d11b1-141">Prepare the certificate that's required to run Surface UEFI Configurator, or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="d11b1-142">4</span><span class="sxs-lookup"><span data-stu-id="d11b1-142">4</span></span> | [<span data-ttu-id="d11b1-143">创建 SEMM 程序包。</span><span class="sxs-lookup"><span data-stu-id="d11b1-143">Create a SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="d11b1-144">启动 Surface UEFI 配置器以在 USB 驱动器上创建 SEMM 程序包。</span><span class="sxs-lookup"><span data-stu-id="d11b1-144">Start Surface UEFI Configurator to create a SEMM package on a USB drive.</span></span> <span data-ttu-id="d11b1-145">此程序包将包含你需要在 Surface Hub 2S 上应用配置文件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-145">This package will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="d11b1-146">将这些 SEMM 程序包文件复制到电脑上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d11b1-146">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="d11b1-147">5</span><span class="sxs-lookup"><span data-stu-id="d11b1-147">5</span></span> | [<span data-ttu-id="d11b1-148">使用 Windows 10 映像、SEMM 程序包以及驱动程序和固件加载 U 盘。</span><span class="sxs-lookup"><span data-stu-id="d11b1-148">Load a USB flash drive with Windows 10 image, the SEMM package, and drivers and firmware.</span></span>](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="d11b1-149">创建包含 Windows 10 映像的 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="d11b1-149">Create a USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="d11b1-150">本示例中，驱动器名为*BOOTME。*</span><span class="sxs-lookup"><span data-stu-id="d11b1-150">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="d11b1-151">从步骤 2 开始，将 Surface Hub 2 (上的 Windows 10 专业版和企业版操作系统的驱动程序和固件) 步骤 4) SE (MM 程序包文件添加到 *BOOTME* 驱动器。</span><span class="sxs-lookup"><span data-stu-id="d11b1-151">Add the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (from step 2) and the SEMM package files (from step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="d11b1-152">6</span><span class="sxs-lookup"><span data-stu-id="d11b1-152">6</span></span> | [<span data-ttu-id="d11b1-153">更新 Surface Hub 2S 上的 UEFI 以启用操作系统迁移。</span><span class="sxs-lookup"><span data-stu-id="d11b1-153">Update the UEFI on the Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="d11b1-154">使用 *BOOTME* 驱动器将 Surface Hub 2S 启动到 UEFI 菜单并安装 SEMM 程序包。</span><span class="sxs-lookup"><span data-stu-id="d11b1-154">Use the *BOOTME* drive to boot the Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="d11b1-155">7</span><span class="sxs-lookup"><span data-stu-id="d11b1-155">7</span></span> | [<span data-ttu-id="d11b1-156">安装 Windows 10 专业版或企业版。</span><span class="sxs-lookup"><span data-stu-id="d11b1-156">Install Windows 10 Pro or Enterprise.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="d11b1-157">使用 *BOOTME* 驱动器安装 Windows 10 专业版或企业版 1903 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d11b1-157">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="d11b1-158">8</span><span class="sxs-lookup"><span data-stu-id="d11b1-158">8</span></span> | [<span data-ttu-id="d11b1-159">安装适用于 Windows 10 专业版和企业版驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-159">Install drivers and firmware for Windows 10 Pro and Enterprise.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="d11b1-160">若要确保你的设备具有所有最新的更新和驱动程序，请为 Surface Hub 2 MSI 文件安装适用于 Windows 10 专业版和企业版 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 操作系统的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-160">To ensure that your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="d11b1-161">9</span><span class="sxs-lookup"><span data-stu-id="d11b1-161">9</span></span> | [<span data-ttu-id="d11b1-162">将 Surface Hub 2S 配置为个人生产力设备。</span><span class="sxs-lookup"><span data-stu-id="d11b1-162">Configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="d11b1-163">启用推荐的设置和应用程序以将 Surface Hub 2S 优化为个人生产力设备。</span><span class="sxs-lookup"><span data-stu-id="d11b1-163">Enable the recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="d11b1-164">验证 Surface Hub 2S 上的 UEFI 版本</span><span class="sxs-lookup"><span data-stu-id="d11b1-164">Verify the UEFI version on Surface Hub 2S</span></span>

<span data-ttu-id="d11b1-165">在将 Surface Hub 从 Windows 10 团队迁移到 Windows 10 桌面版之前，你需要 UEFI 版本 *694.2938.768.0* 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d11b1-165">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need UEFI version *694.2938.768.0* or later.</span></span>
 
**<span data-ttu-id="d11b1-166">验证系统上的 UEFI 版本：</span><span class="sxs-lookup"><span data-stu-id="d11b1-166">To verify the UEFI version on your system:</span></span>**

1. <span data-ttu-id="d11b1-167">在 Surface Hub 2S 主页\*\*\*\* 上，选择"开始"，然后打开 Surface 应用 (**所有应用**  >  **Surface**) 。</span><span class="sxs-lookup"><span data-stu-id="d11b1-167">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="d11b1-168">选择 Surface 以显示 **有关** Surface Hub 的信息，包括设备上当前的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="d11b1-168">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="d11b1-169">如果 UEFI 版本为 *694.2938.768.0* 或更高版本，如下图所示，您可以创建 SEMM 程序包以启用操作系统迁移。</span><span class="sxs-lookup"><span data-stu-id="d11b1-169">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![Screenshot shows the "Your Surface" page in the Surface app.](images/shm-fig1.png)
 
   - <span data-ttu-id="d11b1-171">如果 UEFI 版本早于版本 *694.2938.768.0，* 请使用下列方法之一获取较新版本</span><span class="sxs-lookup"><span data-stu-id="d11b1-171">If the UEFI version is earlier than version *694.2938.768.0*, use one of the following methods to get a newer version</span></span>
   
#### <span data-ttu-id="d11b1-172">通过 Windows 更新更新 UEFI</span><span class="sxs-lookup"><span data-stu-id="d11b1-172">Update UEFI via Windows Update</span></span>

1. <span data-ttu-id="d11b1-173">在 Surface Hub 2S 上，以管理员角色 **登录**。</span><span class="sxs-lookup"><span data-stu-id="d11b1-173">On your Surface Hub 2S, sign in as **Admin**.</span></span>

    >[!Note]
    > <span data-ttu-id="d11b1-174">如果不知道用户名或管理员密码，则需要重置设备。</span><span class="sxs-lookup"><span data-stu-id="d11b1-174">If you don't know your user name or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="d11b1-175">有关详细信息，请参阅 [Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)的重置和恢复。</span><span class="sxs-lookup"><span data-stu-id="d11b1-175">For more information, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

1. <span data-ttu-id="d11b1-176">转到 **"所有应用**  >  **设置**  >  **更新和安全**  >  **Windows 更新**"，并安装所有更新。</span><span class="sxs-lookup"><span data-stu-id="d11b1-176">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and install all updates.</span></span>
1. <span data-ttu-id="d11b1-177">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="d11b1-177">Restart the device.</span></span>
1. <span data-ttu-id="d11b1-178">使用 Surface 应用验证 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="d11b1-178">Verify the UEFI version by using the Surface app.</span></span> <span data-ttu-id="d11b1-179">如果 UEFI 版本不是版本 *694.2938.768.0* 或更高版本，请重复这些步骤，或使用以下过程获取最新的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="d11b1-179">If the UEFI version isn't version *694.2938.768.0* or later, repeat these steps, or use the following procedure to get the latest UEFI version.</span></span>

#### <span data-ttu-id="d11b1-180">通过裸机恢复更新 UEFI (BMR) 映像</span><span class="sxs-lookup"><span data-stu-id="d11b1-180">Update the UEFI via bare metal recovery (BMR) image</span></span>

1.  <span data-ttu-id="d11b1-181">转到[Surface 恢复站点，](https://support.microsoft.com/surfacerecoveryimage)然后选择**Surface Hub 2S。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-181">Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**.</span></span>
3.  <span data-ttu-id="d11b1-182">输入集线器序列号。</span><span class="sxs-lookup"><span data-stu-id="d11b1-182">Enter your Hub serial number.</span></span> <span data-ttu-id="d11b1-183">它位于电源连接旁边的集线器的后面。</span><span class="sxs-lookup"><span data-stu-id="d11b1-183">It's located on the back of the Hub next to the power connection.</span></span>
4.  <span data-ttu-id="d11b1-184">按照说明通过安装 Windows 10 Team 2020 Update 将映像下载到格式化的 USB 驱动器上。</span><span class="sxs-lookup"><span data-stu-id="d11b1-184">Follow the directions to download the image onto a formatted USB drive by installing the Windows 10 Team 2020 Update.</span></span>
5.  <span data-ttu-id="d11b1-185">更新后，设备在 OOBE 设置中 (开箱) 体验。</span><span class="sxs-lookup"><span data-stu-id="d11b1-185">After the update, the device enters out-of-box-experience (OOBE) setup.</span></span> <span data-ttu-id="d11b1-186">无需完成设置。</span><span class="sxs-lookup"><span data-stu-id="d11b1-186">You don't need to complete setup.</span></span> <span data-ttu-id="d11b1-187">UEFI 版本已更新。</span><span class="sxs-lookup"><span data-stu-id="d11b1-187">The UEFI version is already updated.</span></span> <span data-ttu-id="d11b1-188">而是按住电源按钮关闭设备，直到屏幕关闭。</span><span class="sxs-lookup"><span data-stu-id="d11b1-188">Instead power down the device by holding the power button until the screen turns off.</span></span>

### <span data-ttu-id="d11b1-189">下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="d11b1-189">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="d11b1-190">在单独的电脑上，按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d11b1-190">On a separate PC, follow these steps:</span></span>

1. <span data-ttu-id="d11b1-191">在 <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> "适用于 IT 的 Surface 工具"页上 </a> ，选择"**下载"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-191">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>  
1. <span data-ttu-id="d11b1-192">选择并下载 Surface UEFI 配置器 MSI 文件，然后将其安装在单独的电脑上。</span><span class="sxs-lookup"><span data-stu-id="d11b1-192">Select and download the Surface UEFI Configurator MSI file, and install it on a separate PC.</span></span> <span data-ttu-id="d11b1-193">安装 Windows 10 团队版时，Surface UEFI 配置器工具无法运行在 Surface Hub 2S 上。</span><span class="sxs-lookup"><span data-stu-id="d11b1-193">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="d11b1-194">下载 [Surface Hub 2 驱动程序和固件 Windows Installer MSI 文件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="d11b1-194">Download the [Surface Hub 2 drivers and firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="d11b1-195">安装新操作系统时，将使用此文件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-195">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="d11b1-196">准备 SEMM 证书</span><span class="sxs-lookup"><span data-stu-id="d11b1-196">Prepare the SEMM certificate</span></span>

<span data-ttu-id="d11b1-197">如果你之前没有使用过 Surface UEFI 配置器，则需要准备证书。</span><span class="sxs-lookup"><span data-stu-id="d11b1-197">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="d11b1-198">此证书可确保在 SEMM 中注册设备后，只能使用使用已批准证书创建的程序包修改 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="d11b1-198">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span>

<span data-ttu-id="d11b1-199">获取证书的方式取决于组织的规模或复杂性：</span><span class="sxs-lookup"><span data-stu-id="d11b1-199">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="d11b1-200">企业组织通常维护自己的基础结构，以根据标准安全做法生成证书。</span><span class="sxs-lookup"><span data-stu-id="d11b1-200">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="d11b1-201">中型企业和其他企业通常选择从合作伙伴提供商获取证书。</span><span class="sxs-lookup"><span data-stu-id="d11b1-201">Medium-sized businesses and others often choose to get certificates from partner providers.</span></span> <span data-ttu-id="d11b1-202">对于没有太多 IT 专业知识或缺少专门的 IT 安全团队的组织，建议使用此选项。</span><span class="sxs-lookup"><span data-stu-id="d11b1-202">This option is recommended for organizations that don't have as much IT expertise or lack a dedicated IT security team.</span></span>

- <span data-ttu-id="d11b1-203">或者，您可以使用 PowerShell 脚本生成自签名证书。</span><span class="sxs-lookup"><span data-stu-id="d11b1-203">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="d11b1-204">有关详细信息，请参阅 Surface [Enterprise 管理模式证书要求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。</span><span class="sxs-lookup"><span data-stu-id="d11b1-204">For more information, see the [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="d11b1-205">或者，您可以使用 PowerShell 创建自己的证书。</span><span class="sxs-lookup"><span data-stu-id="d11b1-205">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="d11b1-206">有关详细信息，请参阅 [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) 文档。</span><span class="sxs-lookup"><span data-stu-id="d11b1-206">For more information, see the [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) documentation.</span></span>

<span data-ttu-id="d11b1-207">Surface UEFI 配置器创建的 SEMM 程序包必须使用证书进行保护。</span><span class="sxs-lookup"><span data-stu-id="d11b1-207">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="d11b1-208">证书先验证配置文件的签名，然后才能应用 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="d11b1-208">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="d11b1-209">有关详细信息，请参阅 [SEMM](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 文档。</span><span class="sxs-lookup"><span data-stu-id="d11b1-209">For more information, see the [SEMM](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
### <span data-ttu-id="d11b1-210">创建 SEMM 程序包</span><span class="sxs-lookup"><span data-stu-id="d11b1-210">Create a SEMM package</span></span>

1. <span data-ttu-id="d11b1-211">在单独的电脑上，安装之前下载的 Surface UEFI 配置器工具。</span><span class="sxs-lookup"><span data-stu-id="d11b1-211">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span>

1. <span data-ttu-id="d11b1-212">打开 Surface UEFI 配置器，然后选择"**开始"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-212">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![Surface UEFI 配置器开始屏幕。](images/shm-fig2.png)
   
1. <span data-ttu-id="d11b1-214">选择**Surface 设备**，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-214">Select **Surface Devices**, and then select **Next**.</span></span>

   ![Screenshot shows the Surface Devices option selected.](images/shm-fig3.png)
  
1. <span data-ttu-id="d11b1-216">选择 **配置包**。</span><span class="sxs-lookup"><span data-stu-id="d11b1-216">Select **Configuration Package**.</span></span>

   ![Screenshot shows "Select Configuration Package" selected.](images/shm-fig4.png)
  
1. <span data-ttu-id="d11b1-218">选择 **证书保护**。</span><span class="sxs-lookup"><span data-stu-id="d11b1-218">Select **Certificate Protection**.</span></span>

   ![Screenshot shows were to choose "Select Certificate Protection".](images/shm-fig5.png)

   <span data-ttu-id="d11b1-220">系统将提示你添加证书 .pfx 文件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-220">You'll be prompted to add your certificate .pfx file.</span></span>

   ![Screenshot shows where to add your certificate file.](images/shm-fig6.png)
   
1. <span data-ttu-id="d11b1-222">输入你的证书密码，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-222">Enter your certificate password, and then select **OK**.</span></span>

   ![Screenshot shows fields to enter and confirm your certificate password.](images/shm-fig7.png)

1. <span data-ttu-id="d11b1-224">选择 **密码保护** 以将密码添加到 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="d11b1-224">Select **Password Protection** to add a password to the Surface UEFI.</span></span> <span data-ttu-id="d11b1-225">每次启动到 UEFI 时，都需要此密码。</span><span class="sxs-lookup"><span data-stu-id="d11b1-225">You'll need this password whenever you boot to the UEFI.</span></span> *<span data-ttu-id="d11b1-226">我们强烈建议你设置在 Surface Hub 2S 上使用的 UEFI 密码。</span><span class="sxs-lookup"><span data-stu-id="d11b1-226">We strongly recommend that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>*

   ![屏幕截图显示在何处选择密码保护。](images/shm-fig8.png)
   
1. <span data-ttu-id="d11b1-228">设置 UEFI 密码，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-228">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d11b1-229">将密码保存在可供管理 Surface Hub 的 IT 管理员访问的安全位置。</span><span class="sxs-lookup"><span data-stu-id="d11b1-229">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> *<span data-ttu-id="d11b1-230">如果此密码丢失，则不能恢复。</span><span class="sxs-lookup"><span data-stu-id="d11b1-230">If this password is lost, it can't be recovered.</span></span>*

   ![Screenshot shows where you set the UEFI password.](images/shm-fig9.png)

1. <span data-ttu-id="d11b1-232">选择**Surface Hub 2S，** 然后选择"下**一步"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-232">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![Screenshot shows where to select Surface Hub 2S.](images/shm-fig10.png)
   
1. <span data-ttu-id="d11b1-234">再次 **选择"下一** 步"。</span><span class="sxs-lookup"><span data-stu-id="d11b1-234">Select **Next** again.</span></span>

    ![Screenshot shows to select Next under "Choose which components".](images/shm-fig10a.png)

1. <span data-ttu-id="d11b1-236">若要允许安装 Windows 10 专业版或企业版，请打开**EnableOsMigration，** 然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-236">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![Screenshot shows where to select Enable O S Migration.](images/shm-fig11.png)
    
    ![Screenshot shows where to set Enable OS Migration to on.](images/shm-fig12.png)

### <span data-ttu-id="d11b1-239">管理 SEMM 注册</span><span class="sxs-lookup"><span data-stu-id="d11b1-239">Manage SEMM enrollment</span></span>

<span data-ttu-id="d11b1-240">将设备注册到 SEMM 会影响管理设备。</span><span class="sxs-lookup"><span data-stu-id="d11b1-240">Enrolling a device into SEMM affects how you can manage it.</span></span> <span data-ttu-id="d11b1-241">例如，应用 SEMM 程序包后，所有 UEFI 设置 (UEFI) UEFI 菜单中锁定。</span><span class="sxs-lookup"><span data-stu-id="d11b1-241">For example, after you apply a SEMM package, all UEFI settings are unavailable (locked) in the device's UEFI menu.</span></span> <span data-ttu-id="d11b1-242">其他设置（如 **用于 PXE 启动的 IPv6）的** 默认值也不可用。</span><span class="sxs-lookup"><span data-stu-id="d11b1-242">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span>

<span data-ttu-id="d11b1-243">若要在迁移完成后更改 UEFI 设置，请应用另一个 SEMM 程序包，或者从 SEMM 注销设备。</span><span class="sxs-lookup"><span data-stu-id="d11b1-243">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="d11b1-244">如果应用另一个 SEMM 程序包来更改 UEFI 设置，则必须在生成新的 SEMM 程序包时使用原始证书。</span><span class="sxs-lookup"><span data-stu-id="d11b1-244">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="d11b1-245">使用 UEFI 配置器工具，使**EnableOSMigration** \*\* \* (，而不是\*像原始迁移步骤一样) 。</span><span class="sxs-lookup"><span data-stu-id="d11b1-245">Use the UEFI Configurator tool and leave **EnableOSMigration** *off* (not *on* as in the original migration steps).</span></span>

#### <span data-ttu-id="d11b1-246">如果与合作伙伴合作</span><span class="sxs-lookup"><span data-stu-id="d11b1-246">If you work with partners</span></span>

<span data-ttu-id="d11b1-247">如果你的公司将 Surface Hub 2 迁移外包到 Windows 10 专业版或企业版，你可能希望让合作伙伴将 SEMM 证书、SEMM 程序包和 UEFI 密码传输给你。</span><span class="sxs-lookup"><span data-stu-id="d11b1-247">If your company outsources the Surface Hub 2 migration to Windows 10 Pro or Enterprise, you may want to have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you.</span></span> <span data-ttu-id="d11b1-248">或者，迁移中心后，你可以立即从 SEMM 注销它。</span><span class="sxs-lookup"><span data-stu-id="d11b1-248">Or, after you migrate the Hub, you can immediately unenroll it from SEMM.</span></span> <span data-ttu-id="d11b1-249">此步骤启用 UEFI 的本地管理和将设备转移到另一方。</span><span class="sxs-lookup"><span data-stu-id="d11b1-249">This step enables local administration of UEFI and transfer of the device to another party.</span></span> <span data-ttu-id="d11b1-250">但是，我们仍强烈建议你使用 UEFI 密码，可以在迁移后进行配置。</span><span class="sxs-lookup"><span data-stu-id="d11b1-250">But we still strongly recommend that you use a UEFI password, which can be configured after migration.</span></span> <span data-ttu-id="d11b1-251">若要了解更多信息，请参阅["管理 Surface UEFI 设置"。](https://docs.microsoft.com/surface/manage-surface-uefi-settings)</span><span class="sxs-lookup"><span data-stu-id="d11b1-251">To learn more, see [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings).</span></span> 

#### <span data-ttu-id="d11b1-252">回滚到 Windows 10 团队</span><span class="sxs-lookup"><span data-stu-id="d11b1-252">To roll back to Windows 10 Team</span></span>

<span data-ttu-id="d11b1-253">如果你选择在迁移后将设备还原到 Windows 10[](#to-roll-back-to-windows-10-team)团队，如本文稍后所述，我们建议你先从 SEMM 注销 Hub。</span><span class="sxs-lookup"><span data-stu-id="d11b1-253">If you choose to restore your device to Windows 10 Team after the migration [as described later in this article](#to-roll-back-to-windows-10-team), we recommend that you first unenroll Hub from SEMM.</span></span> <span data-ttu-id="d11b1-254">若要了解更多信息，请参阅 [从 SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="d11b1-254">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

#### <span data-ttu-id="d11b1-255">将 SEMM 程序包保存到 U 盘</span><span class="sxs-lookup"><span data-stu-id="d11b1-255">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="d11b1-256">将 U 盘连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="d11b1-256">Connect a USB drive to your PC.</span></span>
1. <span data-ttu-id="d11b1-257">选择**中心 2S，** 然后选择"下**一步"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-257">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![Screenshot shows where to select Hub 2S](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="d11b1-259">生成 SEMM 程序包时，将擦除 USB 驱动器上的所有现有数据。</span><span class="sxs-lookup"><span data-stu-id="d11b1-259">All existing data on the USB drive will be erased when the SEMM package is built.</span></span> <span data-ttu-id="d11b1-260">在生成 SEMM 程序包之前，请从 USB 驱动器中删除所需的任何文件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-260">Before you build the SEMM package, remove any files that you need from the USB drive.</span></span>
   
1. <span data-ttu-id="d11b1-261">选择“构建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d11b1-261">Select **Build**.</span></span>

   ![Screenshot shows where to select Build.](images/shm-fig14.png)

1. <span data-ttu-id="d11b1-263">捕获此页面的屏幕截图，然后选择"结束 **"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-263">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="d11b1-264">SEMM 程序包现已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="d11b1-264">Your SEMM package is now ready.</span></span> <span data-ttu-id="d11b1-265">它包含 SEMM 包 *DfciUpdate.dfi* 和一个文本文件，其中包含 *SEMM*指纹，它是证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="d11b1-265">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM *thumbprint*, which is the last two characters of the certificate's thumbprint.</span></span>

   ![Screenshot shows where to select End.](images/shm-fig15.png)
   
4. <span data-ttu-id="d11b1-267">保存证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="d11b1-267">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="d11b1-268">当你在 Surface Hub 2S 上应用程序包时，你将需要这些字符来激活 SEMM。</span><span class="sxs-lookup"><span data-stu-id="d11b1-268">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="d11b1-269">使用 Windows 10 映像、SEMM 程序包和 Surface Hub 2 驱动程序和固件加载 U 盘</span><span class="sxs-lookup"><span data-stu-id="d11b1-269">Load a USB flash drive with a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="d11b1-270">可以使用以下选项之一 (*版本 1903* 或更高版本) Windows 10 专业版或企业版映像：</span><span class="sxs-lookup"><span data-stu-id="d11b1-270">You can install a Windows 10 Pro or Enterprise image (version *1903* or later) by using one of the following options:</span></span>

- <span data-ttu-id="d11b1-271">当前的映像解决方案。</span><span class="sxs-lookup"><span data-stu-id="d11b1-271">Your current imaging solution.</span></span>

- <span data-ttu-id="d11b1-272">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator).</span><span class="sxs-lookup"><span data-stu-id="d11b1-272">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator).</span></span> <span data-ttu-id="d11b1-273">使用此工具创建可启动的 Windows 10 映像。</span><span class="sxs-lookup"><span data-stu-id="d11b1-273">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="d11b1-274">映像可以包括所有当前的 Windows 10 更新、Microsoft Office、其他应用以及所需的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-274">The image can include all current Windows 10 updates, Microsoft Office, other apps, and the required drivers and firmware.</span></span>

- <span data-ttu-id="d11b1-275">包含 Windows 10 专业版或企业版映像的 U 盘。</span><span class="sxs-lookup"><span data-stu-id="d11b1-275">A USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="d11b1-276">然后，在 Surface Hub 2 上为 [Windows 10 专业版和企业](https://www.microsoft.com/download/details.aspx?id=101974) 版安装驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-276">Then install [drivers and firmware for Windows 10 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974) on Surface Hub 2.</span></span>
 
<span data-ttu-id="d11b1-277">以下步骤显示如何从安装媒体创建 U 盘，然后在 Surface Hub 2 MSI 文件上为 Windows 10 专业版和企业版操作系统添加 SEMM 程序包文件和驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-277">The following steps show how to create a USB flash drive from installation media and then add the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="d11b1-278">如果你使用另一种部署方法，请转到 [Surface Hub 2S 上的更新 UEFI 以](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 启用本文中的操作系统迁移部分。</span><span class="sxs-lookup"><span data-stu-id="d11b1-278">If you use another deployment method, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="d11b1-279">完成安装后，你需要一个与现有 Windows 10 团队版许可证分开的有效 Windows 10 专业版或 Windows 10 企业版许可证。</span><span class="sxs-lookup"><span data-stu-id="d11b1-279">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="d11b1-280">若要创建 Windows 10 专业版安装，请按照说明下载 Windows [10](https://www.microsoft.com/software-download/windows10)中的媒体创建工具。</span><span class="sxs-lookup"><span data-stu-id="d11b1-280">To create a Windows 10 Pro installation, follow the instructions to download the media creation tool at [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span> <span data-ttu-id="d11b1-281">若要下载 Windows 10 企业版，请转到 [Microsoft 批量许可服务中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d11b1-281">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

1. <span data-ttu-id="d11b1-282">插入新的 USB 存储驱动器。</span><span class="sxs-lookup"><span data-stu-id="d11b1-282">Insert a new USB storage drive.</span></span>
1. <span data-ttu-id="d11b1-283">打开媒体创建工具，选择 **"创建安装媒体**"，然后选择"下**一步"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-283">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![Screenshot shows the option to create installation media.](images/shm-fig16.png)
   
3. <span data-ttu-id="d11b1-285">选择一种语言，然后选择**Windows 10**和 64 位 (\*\*x64) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="d11b1-285">Select a language, and then select **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="d11b1-286">然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-286">Then select **Next**.</span></span>

   ![Screenshot shows where you select the language， O S edition， and architecture type.](images/shm-fig17.png)
   
4. <span data-ttu-id="d11b1-288">选择**U 盘**，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-288">Select **USB flash drive**, and then select **Next**.</span></span>

   ![Screenshot shows where to select U S B flash drive.](images/shm-fig18.png)
   
5. <span data-ttu-id="d11b1-290">下载完成后，选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-290">When the download finishes, select **Finish**.</span></span>

   ![屏幕报告 U S B 驱动器已准备就绪，并包含"完成"按钮。](images/shm-fig19.png)
   
6. <span data-ttu-id="d11b1-292">将 SURFACE Hub 2 上的 Windows 10 专业版和企业版操作系统的 SEMM 程序包文件和驱动程序和固件 (MSI 文件) 复制到包含 Windows 10 映像的 U 盘 (*BOOTME*) 的根目录。</span><span class="sxs-lookup"><span data-stu-id="d11b1-292">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="d11b1-293">BOOTME USB 驱动器将包含：</span><span class="sxs-lookup"><span data-stu-id="d11b1-293">The BOOTME USB drive will contain:</span></span>

    - <span data-ttu-id="d11b1-294">Windows 10 可启动映像。</span><span class="sxs-lookup"><span data-stu-id="d11b1-294">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="d11b1-295">复制到 USB 驱动器根目录的 SEMM 包文件：</span><span class="sxs-lookup"><span data-stu-id="d11b1-295">The SEMM package files, copied to the root of the USB drive:</span></span>
    
      - <span data-ttu-id="d11b1-296">*DfciUpdate.dfi*.</span><span class="sxs-lookup"><span data-stu-id="d11b1-296">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="d11b1-297">包含 SEMM 指纹的文本文件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-297">A text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="d11b1-298"> (此示例中，该文件为 *SurfaceUEFI_2020Aug25_1058.txt*.) 自动生成的日期时间戳对应于使用 Surface UEFI 配置器创建文件的日期。</span><span class="sxs-lookup"><span data-stu-id="d11b1-298">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date-time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="d11b1-299">Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi) 。</span><span class="sxs-lookup"><span data-stu-id="d11b1-299">The drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="d11b1-300">将此文件复制到 USB 驱动器的根目录。</span><span class="sxs-lookup"><span data-stu-id="d11b1-300">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="d11b1-301">在 Surface Hub 2S 上更新 UEFI 以启用操作系统迁移</span><span class="sxs-lookup"><span data-stu-id="d11b1-301">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="d11b1-302">将 BOOTME 驱动器插入 Surface Hub 2S 上的 USB-A 端口。</span><span class="sxs-lookup"><span data-stu-id="d11b1-302">Insert your BOOTME drive into the USB-A port on the Surface Hub 2S.</span></span> <span data-ttu-id="d11b1-303">有关所需内容的列表，请参阅上一节。</span><span class="sxs-lookup"><span data-stu-id="d11b1-303">For a list of its required contents, see the previous section.</span></span>

1. <span data-ttu-id="d11b1-304">若要启动到 UEFI：</span><span class="sxs-lookup"><span data-stu-id="d11b1-304">To boot into UEFI:</span></span>

   1. <span data-ttu-id="d11b1-305">关闭 (Surface Hub 2S) 关闭。</span><span class="sxs-lookup"><span data-stu-id="d11b1-305">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="d11b1-306">长按 **音量 +**，然后按下并释放电源按钮。</span><span class="sxs-lookup"><span data-stu-id="d11b1-306">Press and hold **Volume +**, and then press and release the power button.</span></span> <span data-ttu-id="d11b1-307">保持音量 **+** ，直到 UEFI 菜单出现。</span><span class="sxs-lookup"><span data-stu-id="d11b1-307">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![绘图显示音量和电源按钮。](images/shm-fig20.png)
      
3. <span data-ttu-id="d11b1-309">当设备重新启动时，输入之前创建的 UEFI 密码（如果适用 (推荐) 。</span><span class="sxs-lookup"><span data-stu-id="d11b1-309">When the device restarts, enter the UEFI password that you created earlier, if applicable (recommended).</span></span>

   ![系统密码屏幕。](images/shm-fig22.png)
   
4. <span data-ttu-id="d11b1-311">从 UEFI 菜单中，选择"**管理"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-311">From the UEFI menu, select **Management**.</span></span> <span data-ttu-id="d11b1-312">然后选择"**从 USB 安装"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-312">Then select  **Install from USB**.</span></span>

   ![Screenshot shows where to select Management and then "Install from U S B".](images/shm-fig21.png)
   
5. <span data-ttu-id="d11b1-314">选择 **"立即重启**"，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="d11b1-314">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="d11b1-315">设备将启动。</span><span class="sxs-lookup"><span data-stu-id="d11b1-315">The device will restart.</span></span> <span data-ttu-id="d11b1-316">它将在窗口中间显示一个白色 Microsoft 徽标，然后关闭。</span><span class="sxs-lookup"><span data-stu-id="d11b1-316">It will display a white Microsoft logo in the middle of the window and then shut down.</span></span>

   ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)
   
6. <span data-ttu-id="d11b1-318">按下并释放电源按钮。</span><span class="sxs-lookup"><span data-stu-id="d11b1-318">Press and release the power button.</span></span> <span data-ttu-id="d11b1-319">在出现的红色对话框中，选择激活 Surface Enterprise 管理模式。</span><span class="sxs-lookup"><span data-stu-id="d11b1-319">In the red dialog box that appears, choose to activate Surface Enterprise Management Mode.</span></span>

7. <span data-ttu-id="d11b1-320">输入双字符证书指纹和 UEFI 设置密码。</span><span class="sxs-lookup"><span data-stu-id="d11b1-320">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="d11b1-321">然后选择 **"确定"。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-321">Then select **OK**.</span></span>

   ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="d11b1-323">在设备上激活 SEMM 后，将应用新的 UEFI 设置**EnableOSMigration。**</span><span class="sxs-lookup"><span data-stu-id="d11b1-323">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="d11b1-324">你无法再访问 Windows 10 团队。</span><span class="sxs-lookup"><span data-stu-id="d11b1-324">You can no longer access Windows 10 Team.</span></span> <span data-ttu-id="d11b1-325">相反，你必须继续执行下一步并安装 Windows 10 专业版或 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="d11b1-325">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span>

   <span data-ttu-id="d11b1-326">设备重新启动。</span><span class="sxs-lookup"><span data-stu-id="d11b1-326">The device reboots.</span></span> <span data-ttu-id="d11b1-327">它在屏幕中间显示白色徽标，然后再次关闭。</span><span class="sxs-lookup"><span data-stu-id="d11b1-327">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="d11b1-328">安装 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="d11b1-328">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="d11b1-329">如果你的可启动 Windows 10 专业版或企业版驱动器尚未在 Surface Hub 2 USB-A 端口中，则现在插入它。</span><span class="sxs-lookup"><span data-stu-id="d11b1-329">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="d11b1-330">然后按下并释放电源按钮。</span><span class="sxs-lookup"><span data-stu-id="d11b1-330">Then press and release the power button.</span></span>

    <span data-ttu-id="d11b1-331">设备启动时，你将在屏幕中间看到白色徽标。</span><span class="sxs-lookup"><span data-stu-id="d11b1-331">When the device starts, you'll see the white logo in the middle of the screen.</span></span> <span data-ttu-id="d11b1-332">然后，白色徽标下方出现旋转圆圈。</span><span class="sxs-lookup"><span data-stu-id="d11b1-332">Then a spinning circle appears below the white logo.</span></span>

3. <span data-ttu-id="d11b1-333">如果 Surface 设备未自动启动到 USB 驱动器，请关闭设备电源 (拔下电源线，然后将其插回) 。</span><span class="sxs-lookup"><span data-stu-id="d11b1-333">If the Surface device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="d11b1-334">再次插入电缆后，设备应在几秒钟后启动。</span><span class="sxs-lookup"><span data-stu-id="d11b1-334">After you plug in the power cord again, the device should boot after a few seconds.</span></span> <span data-ttu-id="d11b1-335">然后，你将在屏幕中间看到白色徽标。</span><span class="sxs-lookup"><span data-stu-id="d11b1-335">Then you'll see the white logo in the middle of screen.</span></span>

    <span data-ttu-id="d11b1-336">如果设备未打开，请按并释放电源按钮。</span><span class="sxs-lookup"><span data-stu-id="d11b1-336">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="d11b1-337">在屏幕中间看到徽标后，立即长按音量按钮，直到看到白色徽标下方的旋转圆圈。</span><span class="sxs-lookup"><span data-stu-id="d11b1-337">Immediately after you see the logo in the middle of the screen, press and hold the volume button until you see the spinning circle below the white logo.</span></span>
 
   ![音量和电源按钮的图片。](images/shm-fig26.png)
   
4. <span data-ttu-id="d11b1-339">当 OOBE (OOBE) 安装启动时，请按照说明安装 Windows 10 专业版或企业版 (版本 1903 或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="d11b1-339">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="d11b1-340">安装 Surface Hub 2 驱动程序和固件</span><span class="sxs-lookup"><span data-stu-id="d11b1-340">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="d11b1-341">若要确保 Surface Hub 2 是最新的，请为 [Windows 10](https://www.microsoft.com/download/details.aspx?id=101974)专业版和企业版安装驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="d11b1-341">To ensure that your Surface Hub 2 is up to date, install [drivers and firmware for Windows 10 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="d11b1-342">然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="d11b1-342">Then reboot the device.</span></span> <span data-ttu-id="d11b1-343">将 Surface 保持打开状态一小时，然后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="d11b1-343">Keep the Surface turned on for an hour, and then reboot it again.</span></span> <span data-ttu-id="d11b1-344">系统不会提示您进行第二次重启。</span><span class="sxs-lookup"><span data-stu-id="d11b1-344">You won't be prompted for the second reboot.</span></span> <span data-ttu-id="d11b1-345">此暂停和额外重启可确保固件已完全更新。</span><span class="sxs-lookup"><span data-stu-id="d11b1-345">This pause and extra reboot ensures that the firmware has been fully updated.</span></span>
 
## <span data-ttu-id="d11b1-346">配置建议设置</span><span class="sxs-lookup"><span data-stu-id="d11b1-346">Configure recommended settings</span></span>

<span data-ttu-id="d11b1-347">若要将 Surface Hub 2S 配置为个人生产力设备，请参阅在 Surface Hub 2 上配置 [Windows 10](surface-hub-2-post-install.md)专业版或企业版。</span><span class="sxs-lookup"><span data-stu-id="d11b1-347">To configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="d11b1-348">如果你无法按照本文中概述的步骤将设备成功迁移到适用于 Surface Hub 2 的 Windows 10 专业版或企业版，请联系 [Surface Hub 支持人员](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。</span><span class="sxs-lookup"><span data-stu-id="d11b1-348">If you can't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2 by following the steps outlined in this article, contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="d11b1-349">回滚到 Windows 10 团队</span><span class="sxs-lookup"><span data-stu-id="d11b1-349">To roll back to Windows 10 Team</span></span>

<span data-ttu-id="d11b1-350">如果你想要将设备还原到 Windows 10 团队，请参阅 [Surface Hub 2S 的重置和恢复](surface-hub-2s-recover-reset.md)。</span><span class="sxs-lookup"><span data-stu-id="d11b1-350">If you want to restore your device to Windows 10 Team, see [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d11b1-351">在回退到 Windows 10 团队之前，我们建议你先从 SEMM 注销 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="d11b1-351">Before you roll back to Windows 10 Team, we recommended that you first unenroll the Surface Hub from SEMM.</span></span> <span data-ttu-id="d11b1-352">若要了解更多信息，请参阅 [从 SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="d11b1-352">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="d11b1-353">版本历史记录</span><span class="sxs-lookup"><span data-stu-id="d11b1-353">Version history</span></span>

<span data-ttu-id="d11b1-354">下表汇总了对本文所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d11b1-354">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="d11b1-355">版本</span><span class="sxs-lookup"><span data-stu-id="d11b1-355">Version</span></span> | <span data-ttu-id="d11b1-356">日期</span><span class="sxs-lookup"><span data-stu-id="d11b1-356">Date</span></span>               | <span data-ttu-id="d11b1-357">描述</span><span class="sxs-lookup"><span data-stu-id="d11b1-357">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d11b1-358">v.</span><span class="sxs-lookup"><span data-stu-id="d11b1-358">v.</span></span> <span data-ttu-id="d11b1-359">1.4</span><span class="sxs-lookup"><span data-stu-id="d11b1-359">1.4</span></span>  | <span data-ttu-id="d11b1-360">2020 年 12 月 14 日</span><span class="sxs-lookup"><span data-stu-id="d11b1-360">December 14, 2020</span></span> | <span data-ttu-id="d11b1-361">提供有关[](#install-surface-hub-2-drivers-and-firmware)为"Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件"安装 MSI 文件的进一步信息，提示可能需要根据系统状态进行第二次重启。</span><span class="sxs-lookup"><span data-stu-id="d11b1-361">Provides [further info](#install-surface-hub-2-drivers-and-firmware) about installing the MSI file for "Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2," advising that a second reboot may be necessary depending on the state of your system.</span></span>                                                          |
| <span data-ttu-id="d11b1-362">v.</span><span class="sxs-lookup"><span data-stu-id="d11b1-362">v.</span></span> <span data-ttu-id="d11b1-363">1.3</span><span class="sxs-lookup"><span data-stu-id="d11b1-363">1.3</span></span>  | <span data-ttu-id="d11b1-364">2020 年 12 月 3 日</span><span class="sxs-lookup"><span data-stu-id="d11b1-364">December 3, 2020</span></span> | <span data-ttu-id="d11b1-365">更新了有关管理 [SEMM 注册的指南](#manage-semm-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="d11b1-365">Updated with guidance about [managing SEMM enrollment](#manage-semm-enrollment).</span></span>                                                       |
| <span data-ttu-id="d11b1-366">v.</span><span class="sxs-lookup"><span data-stu-id="d11b1-366">v.</span></span> <span data-ttu-id="d11b1-367">1.2</span><span class="sxs-lookup"><span data-stu-id="d11b1-367">1.2</span></span>  | <span data-ttu-id="d11b1-368">2020 年 9 月 29 日</span><span class="sxs-lookup"><span data-stu-id="d11b1-368">September 29, 2020</span></span> | <span data-ttu-id="d11b1-369">处理可用性反馈的杂项更新。</span><span class="sxs-lookup"><span data-stu-id="d11b1-369">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="d11b1-370">v.</span><span class="sxs-lookup"><span data-stu-id="d11b1-370">v.</span></span> <span data-ttu-id="d11b1-371">1.1</span><span class="sxs-lookup"><span data-stu-id="d11b1-371">1.1</span></span>  | <span data-ttu-id="d11b1-372">2020 年 9 月 15 日</span><span class="sxs-lookup"><span data-stu-id="d11b1-372">September 15, 2020</span></span> | <span data-ttu-id="d11b1-373">在介绍中附加了一条说明，阐明了安装新操作系统的许可要求。</span><span class="sxs-lookup"><span data-stu-id="d11b1-373">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="d11b1-374">v.</span><span class="sxs-lookup"><span data-stu-id="d11b1-374">v.</span></span> <span data-ttu-id="d11b1-375">1.0</span><span class="sxs-lookup"><span data-stu-id="d11b1-375">1.0</span></span>  | <span data-ttu-id="d11b1-376">2020 年 9 月 1 日</span><span class="sxs-lookup"><span data-stu-id="d11b1-376">September 1, 2020</span></span>  | <span data-ttu-id="d11b1-377">新文章。</span><span class="sxs-lookup"><span data-stu-id="d11b1-377">New article.</span></span>                                                                                           |

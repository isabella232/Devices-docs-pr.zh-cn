---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator 为组织提供一种简单快速的部署机制，以用于重置 Surface 设备的映像。
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: 部署, 安装, 工具
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 3ede7311289dc4bc720735c0142ff3a46fbb69e7
ms.sourcegitcommit: 582c5a79881c58c4f1aa66cfcab46db966ca9f24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016553"
---
# <span data-ttu-id="d8dd6-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="d8dd6-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="d8dd6-105">Microsoft Surface 部署加速器 (SDA) 通过使用免费的 Microsoft 部署工具自动创建和配置 Microsoft 推荐的部署体验。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="d8dd6-106">在2020年4月重新设计，可在企业环境中简化和自动化图面图像的部署，SDA 工具允许你构建一个 "工厂式" Windows 映像，你可以自定义此类 Windows 映像，以便你的组织要求进行自定义。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="d8dd6-107">开放源代码、脚本驱动的 SDA 工具利用 Windows for Windows 10 (ADK) 的 Windows 评估和部署工具包，从而有助于在测试或生产环境中创建 Windows 映像 (WIM) 。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="d8dd6-108">如果尚未安装最新的 ADK，将在运行 SDA 工具时下载并安装它。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="d8dd6-109">生成的图像与裸机恢复 (BMR) 图像的配置紧密匹配，没有任何预安装的应用程序（如 Microsoft Office 或 Surface UWP 应用程序）。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

## <span data-ttu-id="d8dd6-110">要求</span><span class="sxs-lookup"><span data-stu-id="d8dd6-110">Requirements</span></span>

1. <span data-ttu-id="d8dd6-111">USB 拇指驱动器的大小至少为 16 GB。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-111">A USB thumb drive at least 16 GB in size.</span></span> <span data-ttu-id="d8dd6-112">将格式化 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-112">The USB drive will be formatted.</span></span>
2. <span data-ttu-id="d8dd6-113">带有 Windows 10 专业版或 Windows 10 企业版的 .iso 文件。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-113">An .iso file with Windows 10 Pro or Windows 10 Enterprise.</span></span> <span data-ttu-id="d8dd6-114">媒体创建工具可用于下载 Windows 10 并创建一个 .iso 文件。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-114">The media creation tool can be used to download Windows 10 and create an .iso file.</span></span> <span data-ttu-id="d8dd6-115">有关详细信息，请参阅 [下载 Windows 10](https://www.microsoft.com/software-download/windows10)。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-115">For more information, see [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span>
3. <span data-ttu-id="d8dd6-116">运行 Windows 10 版本2004或更高版本且具有 Internet 访问权限的设备。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-116">A device running Windows 10, version 2004 or later with Internet access.</span></span>

<span data-ttu-id="d8dd6-117">有关要求的详细列表，请参阅自述文档的 " [先决条件](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) " 部分。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-117">See the [Prerequisites](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) section of the README document for a detailed list of requirements.</span></span>

## <span data-ttu-id="d8dd6-118">如何运行 SDA</span><span class="sxs-lookup"><span data-stu-id="d8dd6-118">How to run the SDA</span></span>

**<span data-ttu-id="d8dd6-119">要运行 SDA，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8dd6-119">To run SDA:</span></span>**

1. <span data-ttu-id="d8dd6-120">转到 GitHub 上的 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-120">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="d8dd6-121">查看 [自述](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-121">Review the [README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) documentation.</span></span>
3. <span data-ttu-id="d8dd6-122">在 " [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) " 页面上，单击 " **代码** " 按钮，然后选择 " **下载 ZIP** " 将文件本地保存到计算机上。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-122">On the [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) page, click the **Code** button and then select **Download ZIP** to save the files locally on your computer.</span></span>
4. <span data-ttu-id="d8dd6-123">右键单击 .zip 文件，然后单击 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-123">Right-click the .zip file and then click **Properties**.</span></span>
5. <span data-ttu-id="d8dd6-124">在 " **常规** " 选项卡上，选中 " **取消阻止** " 复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-124">On the **General** tab, select the **Unblock** checkbox and then click **OK**.</span></span>
6. <span data-ttu-id="d8dd6-125">将 .zip 文件解压缩到硬盘上的某个位置 (ex： C:\SDA) 。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-125">Extract the .zip file to a location on your hard drive (ex: C:\SDA).</span></span>
7. <span data-ttu-id="d8dd6-126">打开提升了权限的 Windows PowerShell 提示，并将当前会话的 Set-executionpolicy 设置为 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-126">Open an elevated Windows PowerShell prompt and set ExecutionPolicy for the current session to Unrestricted.</span></span>

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. <span data-ttu-id="d8dd6-127">运行用于为你的环境指定参数的 SDA 脚本。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-127">Run the SDA script specifying parameters for your environment.</span></span> <span data-ttu-id="d8dd6-128">该脚本可用于创建在各种 Surface 设备上安装 Windows 10 的映像。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-128">The script can be used to create images to install Windows 10 on a variety of Surface devices.</span></span> <span data-ttu-id="d8dd6-129">有关受支持的设备的完整列表，请参阅 SDA 自述文章中的 [设备参数说明](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) 。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-129">For a full list of supported devices, see the [Device parameter description](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) in the SDA README article.</span></span> 

    <span data-ttu-id="d8dd6-130">例如，以下命令将创建可用于 [在 Surface Hub 2 上安装 Windows 10](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os)的可启动 USB 驱动器：</span><span class="sxs-lookup"><span data-stu-id="d8dd6-130">For example, the following command will create a bootable USB drive that can be used to [install Windows 10 on Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span></span>

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    <span data-ttu-id="d8dd6-131">示例脚本输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-131">Sample script output is below.</span></span>

   ![运行 Surface 部署加速器工具](images/sda1.png)

    <span data-ttu-id="d8dd6-133">脚本将需要大约45分钟才能运行，但可能需要较长时间，具体取决于可用的 CPU 和磁盘资源。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-133">The script will require about 45 minutes to run, but could take longer depending on available CPU and disk resources.</span></span> 

    <span data-ttu-id="d8dd6-134">创建 Windows 映像后，脚本将要求您插入并确认您的 USB 驱动器的驱动器号。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-134">After creating a Windows image, the script will ask you to insert and confirm the drive letter of your USB drive.</span></span> <span data-ttu-id="d8dd6-135">然后，将格式化 USB 驱动器，将其配置为可启动，并复制文件以允许安装适用于 Surface 设备的自定义 Windows 10 映像。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-135">The USB drive will then be formatted, configured as bootable, and files copied to enable installation of the custom Windows 10 image for Surface devices.</span></span>

9. <span data-ttu-id="d8dd6-136">将 USB 驱动器插入要在其中安装 Windows 10 的设备，然后重新启动以开始安装 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-136">Insert the USB drive into the device where you want to install Windows 10 and reboot to begin installing Windows 10.</span></span> <span data-ttu-id="d8dd6-137">必须在 BIOS 中启用 USB 引导，这可能需要暂时禁用安全启动。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-137">USB boot must be enabled in BIOS, which can require that you temporarily disable Secure Boot.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8dd6-138">从 USB 驱动器启动将立即开始安装 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-138">Booting from the USB drive will immediately begin installing Windows 10.</span></span> <span data-ttu-id="d8dd6-139">在插入 USB 并重新启动之前，请确保你的设备已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="d8dd6-139">Ensure that your device is ready before inserting the USB and restarting.</span></span> 

## <span data-ttu-id="d8dd6-140">相关链接</span><span class="sxs-lookup"><span data-stu-id="d8dd6-140">Related links</span></span>

 - [<span data-ttu-id="d8dd6-141">在 GitHub 上发布的 "打开源映像部署工具"</span><span class="sxs-lookup"><span data-stu-id="d8dd6-141">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [<span data-ttu-id="d8dd6-142">下载并安装 Windows ADK</span><span class="sxs-lookup"><span data-stu-id="d8dd6-142">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

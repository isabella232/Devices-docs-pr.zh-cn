---
title: 使用 Surface Hub 恢复工具
description: 如何使用 Surface Hub 恢复工具重新映像 SSD。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/18/2018
ms.localizationpriority: medium
ms.openlocfilehash: a9ebab6848efa706609a39b0eb99fa42df2156bf
ms.sourcegitcommit: ce7ad475b776a78ba215e77111ea5371afeb4f28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/18/2020
ms.locfileid: "11237303"
---
# <span data-ttu-id="34e7e-104">使用 Surface Hub 恢复工具</span><span class="sxs-lookup"><span data-stu-id="34e7e-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="34e7e-105">[Microsoft Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210)恢复工具可帮助你使用 Windows 10 桌面设备重新映像 Surface Hub 固态硬盘 (SSD) ，而无需调用支持或更换 SSD。</span><span class="sxs-lookup"><span data-stu-id="34e7e-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="34e7e-106">使用此工具，你可以为具有未知管理员密码、启动错误、无法完成云恢复的 SSD 或具有较旧版本操作系统的设备重置映像。</span><span class="sxs-lookup"><span data-stu-id="34e7e-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="34e7e-107">该工具不会修复物理损坏的 SSD。</span><span class="sxs-lookup"><span data-stu-id="34e7e-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="34e7e-108">若要使用恢复工具重新映像 Surface Hub SSD，你需要从 Surface Hub 中删除 SSD，将驱动器连接到 USB 到 SATA 电缆，然后将电缆连接到安装了恢复工具的台式电脑。</span><span class="sxs-lookup"><span data-stu-id="34e7e-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="34e7e-109">若要详细了解如何从 Surface Hub 中删除现有驱动器，请参阅 [Surface Hub SSD 替换](surface-hub-ssd-replacement.md)。</span><span class="sxs-lookup"><span data-stu-id="34e7e-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34e7e-110">请勿让设备进入睡眠状态或中断映像文件的下载。</span><span class="sxs-lookup"><span data-stu-id="34e7e-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="34e7e-111">如果工具在重新映像驱动器时失败，请联系 [Surface Hub 支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人员。</span><span class="sxs-lookup"><span data-stu-id="34e7e-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="34e7e-112">必备条件</span><span class="sxs-lookup"><span data-stu-id="34e7e-112">Prerequisites</span></span>

### <span data-ttu-id="34e7e-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="34e7e-113">Mandatory</span></span>

- <span data-ttu-id="34e7e-114">运行 64 位版本的 Windows 10 版本 1607 或更高版本的主机电脑。</span><span class="sxs-lookup"><span data-stu-id="34e7e-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="34e7e-115">Internet 访问权限</span><span class="sxs-lookup"><span data-stu-id="34e7e-115">Internet access</span></span>
- <span data-ttu-id="34e7e-116">打开 USB 2.0 或更大端口</span><span class="sxs-lookup"><span data-stu-id="34e7e-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="34e7e-117">USB 到 SATA 电缆</span><span class="sxs-lookup"><span data-stu-id="34e7e-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="34e7e-118">主计算机上 10 GB 的可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="34e7e-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="34e7e-119">Surface Hub 附带的 SSD 或由支持提供的 SSD 作为替代。</span><span class="sxs-lookup"><span data-stu-id="34e7e-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="34e7e-120">不支持 Microsoft 未提供的 SSD。</span><span class="sxs-lookup"><span data-stu-id="34e7e-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="34e7e-121">推荐</span><span class="sxs-lookup"><span data-stu-id="34e7e-121">Recommended</span></span>

- <span data-ttu-id="34e7e-122">高速 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="34e7e-122">High-speed Internet connection</span></span>
- <span data-ttu-id="34e7e-123">打开 USB 3.0 端口</span><span class="sxs-lookup"><span data-stu-id="34e7e-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="34e7e-124">USB 3.0 或更高版本的 USB 到 SATA 电缆</span><span class="sxs-lookup"><span data-stu-id="34e7e-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="34e7e-125">使用以下电缆型号和型号测试了映像工具：</span><span class="sxs-lookup"><span data-stu-id="34e7e-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="34e7e-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="34e7e-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="34e7e-127">将 rcUC16001</span><span class="sxs-lookup"><span data-stu-id="34e7e-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="34e7e-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="34e7e-128">Ugreen 20231</span></span>

## <span data-ttu-id="34e7e-129">下载 Surface Hub 恢复工具</span><span class="sxs-lookup"><span data-stu-id="34e7e-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="34e7e-130">Surface Hub 恢复工具可从适用于[IT](https://www.microsoft.com/download/details.aspx?id=52210)的 Surface Hub 工具的文件名下下载\*\*SurfaceHub_Recovery_v2.0.139.0.msi。 \*\*</span><span class="sxs-lookup"><span data-stu-id="34e7e-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v2.0.139.0.msi**.</span></span>

<span data-ttu-id="34e7e-131">若要开始下载 **，请单击"** 下载"，**从SurfaceHub_Recovery_v2.0.139.0.msi**选择"下载"，然后单击"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="34e7e-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v2.0.139.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="34e7e-132">从弹出窗口中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="34e7e-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="34e7e-133">单击 **"** 运行"立即启动安装。</span><span class="sxs-lookup"><span data-stu-id="34e7e-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="34e7e-134">单击 **"** 保存"将下载复制到计算机，以稍后安装。</span><span class="sxs-lookup"><span data-stu-id="34e7e-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="34e7e-135">在主电脑上安装 Surface Hub 恢复工具。</span><span class="sxs-lookup"><span data-stu-id="34e7e-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="34e7e-136">运行 Surface Hub 恢复工具</span><span class="sxs-lookup"><span data-stu-id="34e7e-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="34e7e-137">在主机电脑上，选择 **"** 开始"按钮，滚动左侧按字母顺序排列的列表，然后选择恢复工具快捷方式。</span><span class="sxs-lookup"><span data-stu-id="34e7e-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Microsoft Surface Hub 恢复工具快捷方式](images/shrt-shortcut.png)

2. <span data-ttu-id="34e7e-139">单击**开始**。</span><span class="sxs-lookup"><span data-stu-id="34e7e-139">Click **Start**.</span></span>

    ![恢复工具"开始"按钮](images/shrt-start.png)


3. <span data-ttu-id="34e7e-141">在"**指南"** 窗口中，单击"下**一步"。**</span><span class="sxs-lookup"><span data-stu-id="34e7e-141">In the **Guidance** window, click **Next**.</span></span>

    ![不要让计算机进入睡眠指南](images/shrt-guidance.png)

4. <span data-ttu-id="34e7e-143">在"选择图像"窗口中，单击**RS2**或后续版本**20H2，\*\*\*\*选择"继续**"，然后选择"**下载图像"。**</span><span class="sxs-lookup"><span data-stu-id="34e7e-143">In the Select image window, click either **RS2** or its successor **20H2**, select **Continue,** and then select **Download image.**</span></span>

     <span data-ttu-id="34e7e-144">![恢复工具 选择映像 ](images/shrt-select-image.png) ![ 恢复工具下载映像](images/shrt-download-image.png)</span><span class="sxs-lookup"><span data-stu-id="34e7e-144">![Recovery Tool Select image](images/shrt-select-image.png) ![Recovery Tool Download image](images/shrt-download-image.png)</span></span>

5. <span data-ttu-id="34e7e-145">下载恢复映像的时间取决于 Internet 连接速度。</span><span class="sxs-lookup"><span data-stu-id="34e7e-145">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="34e7e-146">一般的公司连接可能需要一个小时才能下载 8GB 的图像文件。</span><span class="sxs-lookup"><span data-stu-id="34e7e-146">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![下载图像](images/shrt-download.png)



5. <span data-ttu-id="34e7e-148">下载完成后，该工具会指示你连接 SSD 驱动器。</span><span class="sxs-lookup"><span data-stu-id="34e7e-148">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="34e7e-149">如果工具无法找到连接的驱动器，则很有可能使用的电缆未向 Windows 报告 SSD 的名称。</span><span class="sxs-lookup"><span data-stu-id="34e7e-149">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="34e7e-150">映像工具必须找到驱动器名称"LITEON L CH-128V2S USB 设备"，然后才能继续。</span><span class="sxs-lookup"><span data-stu-id="34e7e-150">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="34e7e-151">若要详细了解如何从 Surface Hub 中删除现有驱动器，请参阅 [Surface Hub SSD 替换](surface-hub-ssd-replacement.md)。</span><span class="sxs-lookup"><span data-stu-id="34e7e-151">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![连接 SSD](images/shrt-drive.png)

6. <span data-ttu-id="34e7e-153">识别驱动器后，单击"开始"\*\*\*\* 开始重新映像处理。</span><span class="sxs-lookup"><span data-stu-id="34e7e-153">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="34e7e-154">On the warning that the all data on the drive will be erased， click **OK**.</span><span class="sxs-lookup"><span data-stu-id="34e7e-154">On the warning that all data on the drive will be erased, click **OK**.</span></span>



    <span data-ttu-id="34e7e-155">在将系统映像应用到驱动器之前，SSD 会重新分区并设置格式。</span><span class="sxs-lookup"><span data-stu-id="34e7e-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="34e7e-156">复制系统二进制文件大约需要 30 分钟，但可能需要更长时间，具体取决于 USB 总线的速度、使用的电缆或系统上安装的防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="34e7e-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>



## <span data-ttu-id="34e7e-157">疑难解答和常见问题</span><span class="sxs-lookup"><span data-stu-id="34e7e-157">Troubleshooting and common problems</span></span>

<span data-ttu-id="34e7e-158">问题</span><span class="sxs-lookup"><span data-stu-id="34e7e-158">Issue</span></span> | <span data-ttu-id="34e7e-159">注释</span><span class="sxs-lookup"><span data-stu-id="34e7e-159">Notes</span></span>
--- | ---
<span data-ttu-id="34e7e-160">该工具无法映像 SSD</span><span class="sxs-lookup"><span data-stu-id="34e7e-160">The tool fails to image the SSD</span></span> | <span data-ttu-id="34e7e-161">确保使用的是出厂提供的 SSD 和一条经过测试的电缆。</span><span class="sxs-lookup"><span data-stu-id="34e7e-161">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="34e7e-162">重新映像过程似乎已停止/冻结</span><span class="sxs-lookup"><span data-stu-id="34e7e-162">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="34e7e-163">可以安全地关闭并重新启动 Surface Hub 恢复工具，而对 SSD 没有不良影响。</span><span class="sxs-lookup"><span data-stu-id="34e7e-163">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="34e7e-164">工具无法识别驱动器</span><span class="sxs-lookup"><span data-stu-id="34e7e-164">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="34e7e-165">验证 Surface Hub SSD 是否枚举为Lite-On驱动器"LITEON L CH-128V2S USB 设备"。</span><span class="sxs-lookup"><span data-stu-id="34e7e-165">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="34e7e-166">如果驱动器被识别为另一个命名设备，则当前电缆不兼容。</span><span class="sxs-lookup"><span data-stu-id="34e7e-166">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="34e7e-167">请尝试其他电缆或上面列出的测试电缆之一。</span><span class="sxs-lookup"><span data-stu-id="34e7e-167">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="34e7e-168">错误：-2147024809</span><span class="sxs-lookup"><span data-stu-id="34e7e-168">Error: -2147024809</span></span> | <span data-ttu-id="34e7e-169">打开磁盘管理器并删除 Surface Hub 驱动器上的分区。</span><span class="sxs-lookup"><span data-stu-id="34e7e-169">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="34e7e-170">断开驱动器连接，然后重新连接到主机。</span><span class="sxs-lookup"><span data-stu-id="34e7e-170">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="34e7e-171">再次重新启动映像工具。</span><span class="sxs-lookup"><span data-stu-id="34e7e-171">Restart the imaging tool again.</span></span>

<span data-ttu-id="34e7e-172">如果工具在重新映像驱动器时失败，请联系 [Surface Hub 支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人员。</span><span class="sxs-lookup"><span data-stu-id="34e7e-172">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="34e7e-173">版本历史记录</span><span class="sxs-lookup"><span data-stu-id="34e7e-173">Version history</span></span>

### <span data-ttu-id="34e7e-174">版本 v2.0.139.0</span><span class="sxs-lookup"><span data-stu-id="34e7e-174">Version v2.0.139.0</span></span>

*<span data-ttu-id="34e7e-175">发布日期：2020 年 12 月 18 日</span><span class="sxs-lookup"><span data-stu-id="34e7e-175">Release date: December 18, 2020</span></span>*<br>
<span data-ttu-id="34e7e-176">此版本的 Surface Hub 恢复工具增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="34e7e-176">This version of Surface Hub Recovery Tool adds support for the following:</span></span>
- <span data-ttu-id="34e7e-177">更新以支持 Windows 10 Team 2020 Update (20H2) </span><span class="sxs-lookup"><span data-stu-id="34e7e-177">Update to support Windows 10 Team 2020 Update (20H2)</span></span>
- <span data-ttu-id="34e7e-178">用户体验改进</span><span class="sxs-lookup"><span data-stu-id="34e7e-178">User experience improvements</span></span>
- <span data-ttu-id="34e7e-179">体系结构更改</span><span class="sxs-lookup"><span data-stu-id="34e7e-179">Architectural changes</span></span>
- <span data-ttu-id="34e7e-180">遥测新增功能</span><span class="sxs-lookup"><span data-stu-id="34e7e-180">Telemetry additions</span></span>


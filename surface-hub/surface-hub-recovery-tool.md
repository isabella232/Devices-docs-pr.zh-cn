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
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: 0cc444eab51e9c3cc0bf2f9c2f0c36ac491906b1
ms.sourcegitcommit: 7b09b4bc757c5385c4f5560713cb03448afde9ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2021
ms.locfileid: "11339363"
---
# <span data-ttu-id="5a329-104">使用 Surface Hub 恢复工具</span><span class="sxs-lookup"><span data-stu-id="5a329-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="5a329-105">[Microsoft Surface Hub 恢复](https://www.microsoft.com/download/details.aspx?id=52210)工具可帮助你使用 Windows 10 桌面设备重新映像 Surface Hub 固态硬盘 (SSD) ，而无需调用支持或替换 SSD。</span><span class="sxs-lookup"><span data-stu-id="5a329-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="5a329-106">使用此工具，你可以为具有未知管理员密码、启动错误、无法完成云恢复的 SSD 或具有较旧版本操作系统的设备重置映像。</span><span class="sxs-lookup"><span data-stu-id="5a329-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="5a329-107">该工具不会修复物理损坏的 SSD。</span><span class="sxs-lookup"><span data-stu-id="5a329-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="5a329-108">若要使用恢复工具重新映像 Surface Hub SSD，你需要从 Surface Hub 中删除 SSD，将驱动器连接到 USB 到 SATA 电缆，然后将电缆连接到安装了恢复工具的台式电脑。</span><span class="sxs-lookup"><span data-stu-id="5a329-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="5a329-109">若要详细了解如何从 Surface Hub 中删除现有驱动器，请参阅 [Surface Hub SSD 替换](surface-hub-ssd-replacement.md)。</span><span class="sxs-lookup"><span data-stu-id="5a329-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a329-110">请勿让设备进入睡眠状态或中断映像文件的下载。</span><span class="sxs-lookup"><span data-stu-id="5a329-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="5a329-111">如果该工具在重新映像驱动器时失败，请联系 [Surface Hub 支持人员](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。</span><span class="sxs-lookup"><span data-stu-id="5a329-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="5a329-112">必备条件</span><span class="sxs-lookup"><span data-stu-id="5a329-112">Prerequisites</span></span>

### <span data-ttu-id="5a329-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="5a329-113">Mandatory</span></span>

- <span data-ttu-id="5a329-114">运行 64 位版本的 Windows 10 版本 1607 或更高版本的主机电脑。</span><span class="sxs-lookup"><span data-stu-id="5a329-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="5a329-115">Internet 访问权限</span><span class="sxs-lookup"><span data-stu-id="5a329-115">Internet access</span></span>
- <span data-ttu-id="5a329-116">打开 USB 2.0 或更大端口</span><span class="sxs-lookup"><span data-stu-id="5a329-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="5a329-117">USB 到 SATA 电缆</span><span class="sxs-lookup"><span data-stu-id="5a329-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="5a329-118">主计算机上 10 GB 的可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="5a329-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="5a329-119">Surface Hub 附带的 SSD 或由支持提供的 SSD 作为替代。</span><span class="sxs-lookup"><span data-stu-id="5a329-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="5a329-120">不支持 Microsoft 未提供的 SSD。</span><span class="sxs-lookup"><span data-stu-id="5a329-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="5a329-121">推荐</span><span class="sxs-lookup"><span data-stu-id="5a329-121">Recommended</span></span>

- <span data-ttu-id="5a329-122">高速 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="5a329-122">High-speed Internet connection</span></span>
- <span data-ttu-id="5a329-123">打开 USB 3.0 端口</span><span class="sxs-lookup"><span data-stu-id="5a329-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="5a329-124">USB 3.0 或更高版本的 USB 到 SATA 电缆</span><span class="sxs-lookup"><span data-stu-id="5a329-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="5a329-125">使用电缆的以下型号和型号测试了映像工具：</span><span class="sxs-lookup"><span data-stu-id="5a329-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="5a329-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="5a329-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="5a329-127">Will RCUC16001</span><span class="sxs-lookup"><span data-stu-id="5a329-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="5a329-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="5a329-128">Ugreen 20231</span></span>

## <span data-ttu-id="5a329-129">下载 Surface Hub 恢复工具</span><span class="sxs-lookup"><span data-stu-id="5a329-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="5a329-130">Surface Hub 恢复工具可从[Surface Hub Tools](https://www.microsoft.com/download/details.aspx?id=52210)中下载，用于 IT 的文件名下SurfaceHub_Recovery_v2.7.139.0.msi。 \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="5a329-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v2.7.139.0.msi**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a329-131">此版本于 2021 年 2 月 11 日发布，取代了不再起作用的早期版本。</span><span class="sxs-lookup"><span data-stu-id="5a329-131">This version, released Feb 11, 2021, replaces the earlier build, which is no longer functional.</span></span> <span data-ttu-id="5a329-132">如果之前已下载此工具，请将其卸载并安装当前版本。</span><span class="sxs-lookup"><span data-stu-id="5a329-132">If you downloaded this tool previously, please uninstall it and install the current version.</span></span>

<span data-ttu-id="5a329-133">若要开始下载，请单击"\*\*\*\* 下载"，从**SurfaceHub_Recovery_v2.7.139.0.msi**中选择"下载"，然后单击"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="5a329-133">To start the download, click **Download**, choose **SurfaceHub_Recovery_v2.7.139.0.msi**  from the list, and click **Next**.</span></span> <span data-ttu-id="5a329-134">从弹出窗口中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="5a329-134">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="5a329-135">单击 **"** 运行"立即启动安装。</span><span class="sxs-lookup"><span data-stu-id="5a329-135">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="5a329-136">单击 **"** 保存"将下载复制到计算机以稍后安装。</span><span class="sxs-lookup"><span data-stu-id="5a329-136">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="5a329-137">在主机计算机上安装 Surface Hub 恢复工具。</span><span class="sxs-lookup"><span data-stu-id="5a329-137">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="5a329-138">运行 Surface Hub 恢复工具</span><span class="sxs-lookup"><span data-stu-id="5a329-138">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="5a329-139">在主机电脑上 **，选择"** 开始"按钮，滚动左侧的字母列表，然后选择恢复工具快捷方式。</span><span class="sxs-lookup"><span data-stu-id="5a329-139">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Microsoft Surface Hub 恢复工具快捷方式](images/shrt-shortcut.png)

2. <span data-ttu-id="5a329-141">单击**开始**。</span><span class="sxs-lookup"><span data-stu-id="5a329-141">Click **Start**.</span></span>

    ![恢复工具"开始"按钮](images/shrt-start.png)


3. <span data-ttu-id="5a329-143">在"**指南"** 窗口中，单击"下**一步"。**</span><span class="sxs-lookup"><span data-stu-id="5a329-143">In the **Guidance** window, click **Next**.</span></span>

    ![不允许计算机进入睡眠指南](images/shrt-guidance.png)

4. <span data-ttu-id="5a329-145">在"选择图像"窗口中，单击**RS2**或后续**20H2，\*\*\*\*选择"继续**"，然后选择"**下载图像"。**</span><span class="sxs-lookup"><span data-stu-id="5a329-145">In the Select image window, click either **RS2** or its successor **20H2**, select **Continue,** and then select **Download image.**</span></span>

     <span data-ttu-id="5a329-146">![恢复工具 选择映像 ](images/shrt-select-image.png) ![ 恢复工具下载映像](images/shrt-download-image.png)</span><span class="sxs-lookup"><span data-stu-id="5a329-146">![Recovery Tool Select image](images/shrt-select-image.png) ![Recovery Tool Download image](images/shrt-download-image.png)</span></span>

5. <span data-ttu-id="5a329-147">下载恢复映像的时间取决于 Internet 连接速度。</span><span class="sxs-lookup"><span data-stu-id="5a329-147">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="5a329-148">一般公司连接可能需要一小时才能下载 8GB 图像文件。</span><span class="sxs-lookup"><span data-stu-id="5a329-148">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![下载图像](images/shrt-download.png)



5. <span data-ttu-id="5a329-150">下载完成后，该工具会指示你连接 SSD 驱动器。</span><span class="sxs-lookup"><span data-stu-id="5a329-150">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="5a329-151">如果工具无法找到连接的驱动器，则很有可能使用的电缆不会将 SSD 的名称报告给 Windows。</span><span class="sxs-lookup"><span data-stu-id="5a329-151">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="5a329-152">映像工具必须找到驱动器的名称"LITEON L CH-128V2S USB 设备"，然后才能继续。</span><span class="sxs-lookup"><span data-stu-id="5a329-152">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="5a329-153">若要详细了解如何从 Surface Hub 中删除现有驱动器，请参阅 [Surface Hub SSD 替换](surface-hub-ssd-replacement.md)。</span><span class="sxs-lookup"><span data-stu-id="5a329-153">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![连接 SSD](images/shrt-drive.png)

6. <span data-ttu-id="5a329-155">识别驱动器后 **，单击"** 开始"开始重新映像处理。</span><span class="sxs-lookup"><span data-stu-id="5a329-155">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="5a329-156">在驱动器上的所有数据将被擦除的警告上，单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="5a329-156">On the warning that all data on the drive will be erased, click **OK**.</span></span>



    <span data-ttu-id="5a329-157">在将系统映像应用到驱动器之前，SSD 会重新分区并设置格式。</span><span class="sxs-lookup"><span data-stu-id="5a329-157">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="5a329-158">复制系统二进制文件大约需要 30 分钟，但可能需要更长时间，具体取决于 USB 总线的速度、使用的电缆或系统上安装的防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="5a329-158">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>



## <span data-ttu-id="5a329-159">疑难解答和常见问题</span><span class="sxs-lookup"><span data-stu-id="5a329-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="5a329-160">问题</span><span class="sxs-lookup"><span data-stu-id="5a329-160">Issue</span></span> | <span data-ttu-id="5a329-161">注释</span><span class="sxs-lookup"><span data-stu-id="5a329-161">Notes</span></span>
--- | ---
<span data-ttu-id="5a329-162">该工具无法映像 SSD</span><span class="sxs-lookup"><span data-stu-id="5a329-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="5a329-163">确保使用的是出厂提供的 SSD 和一条经过测试的电缆。</span><span class="sxs-lookup"><span data-stu-id="5a329-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="5a329-164">重新映像化过程似乎已停止/冻结</span><span class="sxs-lookup"><span data-stu-id="5a329-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="5a329-165">可以安全地关闭并重新启动 Surface Hub 恢复工具，对 SSD 没有不良影响。</span><span class="sxs-lookup"><span data-stu-id="5a329-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="5a329-166">工具无法识别驱动器</span><span class="sxs-lookup"><span data-stu-id="5a329-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="5a329-167">验证 Surface Hub SSD 是否枚举为Lite-On驱动器"LITEON L CH-128V2S USB 设备"。</span><span class="sxs-lookup"><span data-stu-id="5a329-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="5a329-168">如果驱动器被识别为另一个命名设备，则当前电缆不兼容。</span><span class="sxs-lookup"><span data-stu-id="5a329-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="5a329-169">请尝试其他电缆或上面列出的测试电缆之一。</span><span class="sxs-lookup"><span data-stu-id="5a329-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="5a329-170">错误：-2147024809</span><span class="sxs-lookup"><span data-stu-id="5a329-170">Error: -2147024809</span></span> | <span data-ttu-id="5a329-171">打开磁盘管理器并删除 Surface Hub 驱动器上的分区。</span><span class="sxs-lookup"><span data-stu-id="5a329-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="5a329-172">断开驱动器连接，然后重新连接到主机。</span><span class="sxs-lookup"><span data-stu-id="5a329-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="5a329-173">再次重新启动映像工具。</span><span class="sxs-lookup"><span data-stu-id="5a329-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="5a329-174">如果该工具在重新映像驱动器时失败，请联系 [Surface Hub 支持人员](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。</span><span class="sxs-lookup"><span data-stu-id="5a329-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="5a329-175">版本历史记录</span><span class="sxs-lookup"><span data-stu-id="5a329-175">Version history</span></span>


### <span data-ttu-id="5a329-176">版本 v2.7.139.0</span><span class="sxs-lookup"><span data-stu-id="5a329-176">Version v2.7.139.0</span></span>

*<span data-ttu-id="5a329-177">发布日期：2021 年 2 月 11 日</span><span class="sxs-lookup"><span data-stu-id="5a329-177">Release date: February 11, 2021</span></span>*<br>
<span data-ttu-id="5a329-178">此版本的 Surface Hub 恢复工具增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="5a329-178">This version of Surface Hub Recovery Tool adds support for the following:</span></span>

- <span data-ttu-id="5a329-179">安全更新</span><span class="sxs-lookup"><span data-stu-id="5a329-179">Security update</span></span>


### <span data-ttu-id="5a329-180">版本 v2.0.139.0</span><span class="sxs-lookup"><span data-stu-id="5a329-180">Version v2.0.139.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a329-181">此版本不再可用。</span><span class="sxs-lookup"><span data-stu-id="5a329-181">This version is no longer functional.</span></span> <span data-ttu-id="5a329-182">请下载上面列出的当前版本。</span><span class="sxs-lookup"><span data-stu-id="5a329-182">Please download the current version, listed above.</span></span> 

*<span data-ttu-id="5a329-183">发布日期：2020 年 12 月 18 日</span><span class="sxs-lookup"><span data-stu-id="5a329-183">Release date: December 18, 2020</span></span>*<br>
<span data-ttu-id="5a329-184">此版本的 Surface Hub 恢复工具增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="5a329-184">This version of Surface Hub Recovery Tool adds support for the following:</span></span>
- <span data-ttu-id="5a329-185">更新以支持 Windows 10 Team 2020 Update (20H2) </span><span class="sxs-lookup"><span data-stu-id="5a329-185">Update to support Windows 10 Team 2020 Update (20H2)</span></span>
- <span data-ttu-id="5a329-186">用户体验改进</span><span class="sxs-lookup"><span data-stu-id="5a329-186">User experience improvements</span></span>
- <span data-ttu-id="5a329-187">体系结构更改</span><span class="sxs-lookup"><span data-stu-id="5a329-187">Architectural changes</span></span>
- <span data-ttu-id="5a329-188">遥测添加</span><span class="sxs-lookup"><span data-stu-id="5a329-188">Telemetry additions</span></span>


---
title: 使用 Surface Hub 恢复工具
description: 如何使用 Surface Hub 恢复工具重新镜像 SSD。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832168"
---
# <span data-ttu-id="dd1fd-104">使用 Surface Hub 恢复工具</span><span class="sxs-lookup"><span data-stu-id="dd1fd-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="dd1fd-105">[Microsoft Surface Hub 恢复工具](https://www.microsoft.com/download/details.aspx?id=52210)可帮助你使用 Windows 10 桌面设备重新镜像 Surface Hub 固态驱动器（SSD），而无需调用支持或更换 SSD。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="dd1fd-106">使用此工具，你可以重置具有未知管理员密码、启动错误、无法完成云恢复的 SSD，或者重置具有较早版本的操作系统的设备的映像。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="dd1fd-107">该工具不会修复物理损坏的 SSDs。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="dd1fd-108">要使用恢复工具重新镜像 Surface Hub SSD，你需要从 Surface Hub 中删除 SSD，将驱动器连接到 USB 至 SATA 电缆，然后将电缆连接到安装了恢复工具的桌面电脑。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="dd1fd-109">有关如何从 Surface Hub 中删除现有驱动器的详细信息，请参阅[Surface HUB SSD 替换](surface-hub-ssd-replacement.md)。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd1fd-110">不要让设备进入睡眠状态或中断图像文件的下载。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="dd1fd-111">如果该工具在重新映像驱动器中未成功，请联系[Surface Hub 支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="dd1fd-112">必备条件</span><span class="sxs-lookup"><span data-stu-id="dd1fd-112">Prerequisites</span></span>

### <span data-ttu-id="dd1fd-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="dd1fd-113">Mandatory</span></span>

- <span data-ttu-id="dd1fd-114">运行64位版本的 Windows 10、版本1607或更高版本的主机电脑。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="dd1fd-115">Internet 访问权限</span><span class="sxs-lookup"><span data-stu-id="dd1fd-115">Internet access</span></span>
- <span data-ttu-id="dd1fd-116">打开 USB 2.0 或更高端口</span><span class="sxs-lookup"><span data-stu-id="dd1fd-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="dd1fd-117">USB 至 SATA 电缆</span><span class="sxs-lookup"><span data-stu-id="dd1fd-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="dd1fd-118">主计算机上有 10 GB 的可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="dd1fd-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="dd1fd-119">SSDs 附带 Surface Hub 或 SSD 提供的支持作为替代。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="dd1fd-120">不支持 Microsoft 提供的 SSDs。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="dd1fd-121">推荐</span><span class="sxs-lookup"><span data-stu-id="dd1fd-121">Recommended</span></span>

- <span data-ttu-id="dd1fd-122">高速互联网连接</span><span class="sxs-lookup"><span data-stu-id="dd1fd-122">High-speed Internet connection</span></span>
- <span data-ttu-id="dd1fd-123">打开 USB 3.0 端口</span><span class="sxs-lookup"><span data-stu-id="dd1fd-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="dd1fd-124">USB 3.0 或更高版本的 USB 至 SATA 电缆</span><span class="sxs-lookup"><span data-stu-id="dd1fd-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="dd1fd-125">已通过以下电缆和型号对图像处理工具进行了测试：</span><span class="sxs-lookup"><span data-stu-id="dd1fd-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="dd1fd-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="dd1fd-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="dd1fd-127">Rosewill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="dd1fd-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="dd1fd-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="dd1fd-128">Ugreen 20231</span></span>

## <span data-ttu-id="dd1fd-129">下载 Surface Hub 恢复工具</span><span class="sxs-lookup"><span data-stu-id="dd1fd-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="dd1fd-130">Surface Hub 恢复工具可从[Surface Hub 工具](https://www.microsoft.com/download/details.aspx?id=52210)下载，在文件名**SurfaceHub_Recovery_v1.14.137.0.msi**下。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v1.14.137.0.msi**.</span></span>

<span data-ttu-id="dd1fd-131">若要开始下载，请单击 "**下载**"，从列表中选择 " **SurfaceHub_Recovery_v1.14.137.0.msi** "，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v1.14.137.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="dd1fd-132">从弹出窗口中，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="dd1fd-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="dd1fd-133">单击 "**运行**" 立即开始安装。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="dd1fd-134">单击 "**保存**" 将下载内容复制到计算机以供以后安装。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="dd1fd-135">在主机 PC 上安装 Surface Hub 恢复工具。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="dd1fd-136">运行 Surface Hub 恢复工具</span><span class="sxs-lookup"><span data-stu-id="dd1fd-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="dd1fd-137">在主机 PC 上，选择 "**开始**" 按钮，滚动到左侧的 "按字母顺序" 列表，然后选择 "恢复工具" 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Microsoft Surface Hub 恢复工具快捷方式](images/shrt-shortcut.png)

2. <span data-ttu-id="dd1fd-139">单击**开始**。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-139">Click **Start**.</span></span>

    ![恢复工具 "开始" 按钮](images/shrt-start.png)

3. <span data-ttu-id="dd1fd-141">在 "**指南**" 窗口中，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-141">In the **Guidance** window, click **Next**.</span></span>

    ![不要让计算机转到睡眠指南](images/shrt-guidance.png)

4. <span data-ttu-id="dd1fd-143">单击 **"是"** 下载图像。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-143">click **Yes** to download the image.</span></span> <span data-ttu-id="dd1fd-144">下载恢复映像的时间取决于互联网连接速度。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-144">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="dd1fd-145">在一般的企业连接中，下载8GB 图像文件最多可能需要一个小时。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-145">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![下载图像？](images/shrt-download.png)

5. <span data-ttu-id="dd1fd-147">下载完成后，该工具指示你连接 SSD 驱动器。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-147">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="dd1fd-148">如果该工具无法找到连接的驱动器，则很有可能是使用电缆时不报告 SSD 的名称到 Windows。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-148">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="dd1fd-149">图像处理工具必须找到驱动器的名称，就像 "LITEON L CH-128V2S USB 设备"，然后它才能继续。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-149">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="dd1fd-150">有关如何从 Surface Hub 中删除现有驱动器的详细信息，请参阅[Surface HUB SSD 替换](surface-hub-ssd-replacement.md)。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-150">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![连接 SSD](images/shrt-drive.png)

6. <span data-ttu-id="dd1fd-152">识别驱动器时，单击 "**开始**" 以开始重新映像过程。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-152">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="dd1fd-153">当出现有关将擦除驱动器上的所有数据的警告时，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-153">On the warning that all data on the drive will be erased, click **OK**.</span></span>

    ![开始重新映像 SSD](images/shrt-drive-start.png)

    <span data-ttu-id="dd1fd-155">在将系统映像应用到驱动器之前，将对 SSD 进行重新分区和格式化。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="dd1fd-156">复制系统二进制文件大约需要30分钟，但可能需要较长时间，具体取决于 USB 总线的速度、所使用的电缆或系统上安装的防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>

    ![复制完成](images/shrt-done.png)

    ![映像完成](images/shrt-complete.png)

## <span data-ttu-id="dd1fd-159">疑难解答和常见问题</span><span class="sxs-lookup"><span data-stu-id="dd1fd-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="dd1fd-160">问题</span><span class="sxs-lookup"><span data-stu-id="dd1fd-160">Issue</span></span> | <span data-ttu-id="dd1fd-161">注释</span><span class="sxs-lookup"><span data-stu-id="dd1fd-161">Notes</span></span>
--- | ---
<span data-ttu-id="dd1fd-162">该工具无法映像 SSD</span><span class="sxs-lookup"><span data-stu-id="dd1fd-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="dd1fd-163">确保使用工厂提供的 SSD 和已测试的电缆之一。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="dd1fd-164">映像进程显示已暂停/已冻结</span><span class="sxs-lookup"><span data-stu-id="dd1fd-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="dd1fd-165">可安全关闭并重新启动 Surface Hub 恢复工具，对 SSD 不产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="dd1fd-166">该工具无法识别该驱动器</span><span class="sxs-lookup"><span data-stu-id="dd1fd-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="dd1fd-167">验证 Surface Hub SSD 是否被枚举为一个精简的驱动器，"LITEON L CH-128V2S USB 设备"。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="dd1fd-168">如果驱动器被识别为另一个已命名的设备，则当前电缆不兼容。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="dd1fd-169">尝试其他电缆或上面列出的已测试电缆之一。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="dd1fd-170">错误：-2147024809</span><span class="sxs-lookup"><span data-stu-id="dd1fd-170">Error: -2147024809</span></span> | <span data-ttu-id="dd1fd-171">打开磁盘管理器并删除 Surface Hub 驱动器上的分区。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="dd1fd-172">断开连接并将驱动器重新连接到主计算机。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="dd1fd-173">重新启动图像处理工具。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="dd1fd-174">如果该工具在重新映像驱动器中未成功，请联系[Surface Hub 支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。</span><span class="sxs-lookup"><span data-stu-id="dd1fd-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

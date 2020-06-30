---
title: 更新 Surface Hub 2 上的笔固件
description: 本页介绍如何更新 Surface Hub 2 笔的固件。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c0ad8f275d2476e42c9a5bd3f1130fbca85a5599
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830958"
---
# <span data-ttu-id="d93d9-104">更新 Surface Hub 2 上的笔固件</span><span class="sxs-lookup"><span data-stu-id="d93d9-104">Update pen firmware on Surface Hub 2S</span></span>

<span data-ttu-id="d93d9-105">你可以从 Windows 更新 for Business 或将固件更新下载到单独的电脑，从 Surface Hub 2 笔更新固件。</span><span class="sxs-lookup"><span data-stu-id="d93d9-105">You can update firmware on Surface Hub 2 pen from Windows Update for Business or by downloading the firmware update to a separate PC.</span></span> <span data-ttu-id="d93d9-106">从2020年2月26日开始，Windows 更新提供已更新的固件。</span><span class="sxs-lookup"><span data-stu-id="d93d9-106">Updated firmware is available from Windows Update beginning February 26, 2020.</span></span> 

## <span data-ttu-id="d93d9-107">使用 Windows 更新商业版更新笔固件</span><span class="sxs-lookup"><span data-stu-id="d93d9-107">Update pen firmware using Windows Update for Business</span></span>

<span data-ttu-id="d93d9-108">本部分介绍如何通过 Windows 更新的自动维护周期（默认情况下，默认情况下，在晚上3点）更新笔固件。</span><span class="sxs-lookup"><span data-stu-id="d93d9-108">This section describes how to update pen firmware via the automated maintenance cycles for Windows Update, configured by default to occur nightly at 3 a.m.</span></span> <span data-ttu-id="d93d9-109">在将更新应用到 Surface Hub 2 笔之前，您需要规划两个维护周期才能完成。</span><span class="sxs-lookup"><span data-stu-id="d93d9-109">You will need to plan for two maintenance cycles to complete before applying the update to the Surface Hub 2 pen.</span></span> <span data-ttu-id="d93d9-110">或者，也可以使用 Windows Server 更新服务（WSUS）应用笔固件。</span><span class="sxs-lookup"><span data-stu-id="d93d9-110">Alternately, like any other update, you can use Windows Server Update Services (WSUS) to apply the pen firmware.</span></span> <span data-ttu-id="d93d9-111">有关详细信息，请参阅[管理 Surface Hub 上的 Windows 更新](manage-windows-updates-for-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="d93d9-111">For more information, see [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).</span></span>

1. <span data-ttu-id="d93d9-112">确保 Surface Hub 2 笔与 Surface Hub 2 配对：长按**顶部**按钮，直到白色指示灯的指示灯开始闪烁。</span><span class="sxs-lookup"><span data-stu-id="d93d9-112">Ensure the Surface Hub 2 pen is paired to Surface Hub 2S: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 笔](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="d93d9-114">在 Surface Hub 上，以管理员身份登录，打开 "**设置**"，然后扫描新的蓝牙设备。</span><span class="sxs-lookup"><span data-stu-id="d93d9-114">On Surface Hub, login as an Admin, open **Settings**, and then scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="d93d9-115">选择笔完成配对过程。</span><span class="sxs-lookup"><span data-stu-id="d93d9-115">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="d93d9-116">按笔上的**顶部**按钮以应用更新。</span><span class="sxs-lookup"><span data-stu-id="d93d9-116">Press the **top** button on the pen to apply the update.</span></span> <span data-ttu-id="d93d9-117">最多可能需要两个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="d93d9-117">It may take up to two hours to complete.</span></span>

## <span data-ttu-id="d93d9-118">通过下载到单独的电脑更新笔固件</span><span class="sxs-lookup"><span data-stu-id="d93d9-118">Update pen firmware by downloading to separate PC</span></span>

<span data-ttu-id="d93d9-119">你可以从运行 Windows 10 的单独电脑更新 Surface Hub 2 笔上的固件。</span><span class="sxs-lookup"><span data-stu-id="d93d9-119">You can update the firmware on Surface Hub 2 pen from a separate PC running Windows 10.</span></span> <span data-ttu-id="d93d9-120">此方法还允许你验证笔固件是否已成功更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="d93d9-120">This method also enables you to verify that the pen firmware has successfully updated to the latest version.</span></span>

1. <span data-ttu-id="d93d9-121">将 Surface Hub 2 笔与支持蓝牙功能的电脑配对：按住**顶部**按钮，直到白色指示灯的指示灯开始闪烁。</span><span class="sxs-lookup"><span data-stu-id="d93d9-121">Pair the Surface Hub 2 pen to your Bluetooth-capable PC: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 笔](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="d93d9-123">在电脑上，扫描新的蓝牙设备。</span><span class="sxs-lookup"><span data-stu-id="d93d9-123">On the PC, scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="d93d9-124">选择笔完成配对过程。</span><span class="sxs-lookup"><span data-stu-id="d93d9-124">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="d93d9-125">开始新的更新之前，请断开所有其他 Surface Hub 2 笔连接。</span><span class="sxs-lookup"><span data-stu-id="d93d9-125">Disconnect all other Surface Hub 2s pens before starting a new update.</span></span>
3. <span data-ttu-id="d93d9-126">将[Surface Hub 2 笔固件更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下载到你的电脑。</span><span class="sxs-lookup"><span data-stu-id="d93d9-126">Download the [Surface Hub 2 Pen Firmware Update Tool](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) to your PC.</span></span>
4. <span data-ttu-id="d93d9-127">运行**PenCfu.exe。**</span><span class="sxs-lookup"><span data-stu-id="d93d9-127">Run **PenCfu.exe.**</span></span> <span data-ttu-id="d93d9-128">安装进度将显示在工具中。</span><span class="sxs-lookup"><span data-stu-id="d93d9-128">The install progress is displayed in the tool.</span></span> <span data-ttu-id="d93d9-129">完成更新可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="d93d9-129">It may take several minutes to finish updating.</span></span> 


## <span data-ttu-id="d93d9-130">检查 Surface Hub 2 笔的固件版本</span><span class="sxs-lookup"><span data-stu-id="d93d9-130">Check firmware version of Surface Hub 2 pen</span></span>

1. <span data-ttu-id="d93d9-131">运行**get_version.bat** ，然后按笔上的**上**一个按钮。</span><span class="sxs-lookup"><span data-stu-id="d93d9-131">Run **get_version.bat** and press the **top** button on the pen.</span></span>
2. <span data-ttu-id="d93d9-132">该工具将报告笔的固件版本。</span><span class="sxs-lookup"><span data-stu-id="d93d9-132">The tool will report the firmware version of the pen.</span></span> <span data-ttu-id="d93d9-133">示例：</span><span class="sxs-lookup"><span data-stu-id="d93d9-133">Example:</span></span>
    - <span data-ttu-id="d93d9-134">旧固件为468.2727.368</span><span class="sxs-lookup"><span data-stu-id="d93d9-134">Old firmware is 468.2727.368</span></span>
    - <span data-ttu-id="d93d9-135">新固件为468.2863.369</span><span class="sxs-lookup"><span data-stu-id="d93d9-135">New firmware is 468.2863.369</span></span>

## <span data-ttu-id="d93d9-136">命令行选项</span><span class="sxs-lookup"><span data-stu-id="d93d9-136">Command line options</span></span>

<span data-ttu-id="d93d9-137">你可以从命令行运行 Surface Hub 2 笔固件更新工具（PenCfu.exe）。</span><span class="sxs-lookup"><span data-stu-id="d93d9-137">You can run Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) from the command line.</span></span>

1. <span data-ttu-id="d93d9-138">将笔与 PC 配对，然后单击笔上的**上**一个按钮。</span><span class="sxs-lookup"><span data-stu-id="d93d9-138">Pair the pen to your PC and click the **top** button on the pen.</span></span>
2. <span data-ttu-id="d93d9-139">双击 " **PenCfu.exe** " 以启动固件更新。</span><span class="sxs-lookup"><span data-stu-id="d93d9-139">Double click **PenCfu.exe** to initiate the firmware update.</span></span> <span data-ttu-id="d93d9-140">请注意，配置文件和固件图像文件必须存储在该工具所在的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d93d9-140">Note that the configuration file and the firmware image files must be stored in the same folder as the tool.</span></span>
3. <span data-ttu-id="d93d9-141">对于其他选项，请运行**PenCfu.exe-h**以显示可用参数，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="d93d9-141">For additional options, run **PenCfu.exe -h** to display the available parameters, as listed in the following table.</span></span>  
    - <span data-ttu-id="d93d9-142">示例： PenCfu.exe-h</span><span class="sxs-lookup"><span data-stu-id="d93d9-142">Example: PenCfu.exe -h</span></span>
4. <span data-ttu-id="d93d9-143">输入**Ctrl + C**以安全关闭该工具。</span><span class="sxs-lookup"><span data-stu-id="d93d9-143">Enter **Ctrl+C** to safely shut down the tool.</span></span>

 

| **<span data-ttu-id="d93d9-144">命令</span><span class="sxs-lookup"><span data-stu-id="d93d9-144">Command</span></span>**    | **<span data-ttu-id="d93d9-145">描述</span><span class="sxs-lookup"><span data-stu-id="d93d9-145">Description</span></span>**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d93d9-146">-h 帮助</span><span class="sxs-lookup"><span data-stu-id="d93d9-146">-h help</span></span>        | <span data-ttu-id="d93d9-147">显示工具命令行界面帮助和退出。</span><span class="sxs-lookup"><span data-stu-id="d93d9-147">Display tool command line interface help and exit.</span></span>                                                                                                                                                                                                                                                                                                                                             |
| <span data-ttu-id="d93d9-148">-v 版本</span><span class="sxs-lookup"><span data-stu-id="d93d9-148">-v version</span></span>     | <span data-ttu-id="d93d9-149">显示工具版本并退出。</span><span class="sxs-lookup"><span data-stu-id="d93d9-149">Display tool version and exit.</span></span>                                                                                                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="d93d9-150">-l 记录-筛选器</span><span class="sxs-lookup"><span data-stu-id="d93d9-150">-l log-filter</span></span>  | <span data-ttu-id="d93d9-151">为日志文件设置筛选器级别。</span><span class="sxs-lookup"><span data-stu-id="d93d9-151">Set a filter level for the log file.</span></span> <span data-ttu-id="d93d9-152">日志消息具有4个可能的级别：调试（最低）、信息、警告和错误（最高）。</span><span class="sxs-lookup"><span data-stu-id="d93d9-152">Log messages have 4 possible levels: DEBUG (lowest), INFO, WARNING and ERROR (highest).</span></span> <span data-ttu-id="d93d9-153">设置日志筛选器级别筛选器仅将消息记录到同一级别或更高级别的邮件中。</span><span class="sxs-lookup"><span data-stu-id="d93d9-153">Setting a log filter level filters log messages to only message with the same level or higher.</span></span> <span data-ttu-id="d93d9-154">例如，如果筛选器级别设置为 "警告"，则仅记录警告和错误消息。</span><span class="sxs-lookup"><span data-stu-id="d93d9-154">For example, if the filter level is set to WARNING, only WARNING and ERROR messages will be logged.</span></span> <span data-ttu-id="d93d9-155">默认情况下，此选项设置为 "关闭"，这将禁用日志记录。</span><span class="sxs-lookup"><span data-stu-id="d93d9-155">By default, this option is set to OFF, which disables logging.</span></span> |
| <span data-ttu-id="d93d9-156">-g get 版本</span><span class="sxs-lookup"><span data-stu-id="d93d9-156">-g get-version</span></span> | <span data-ttu-id="d93d9-157">如果已指定，该工具将仅获取与工具存储在同一文件夹中的配置文件相匹配的已连接笔的固件版本。</span><span class="sxs-lookup"><span data-stu-id="d93d9-157">If specified, the tool will only get the FW version of the connected pen that matches the configuration file that is stored in the same folder as the tool.</span></span>                                                                                                                                                                                                                                    
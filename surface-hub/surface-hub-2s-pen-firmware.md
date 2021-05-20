---
title: 更新 Surface Hub 2S 手写笔固件
description: 此页面介绍如何更新 2 个笔Surface Hub固件。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 6f1ca4f05653ec798ed1b47d2e42e974e7f7414d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576952"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a><span data-ttu-id="562da-104">更新 Surface Hub 2S 手写笔固件</span><span class="sxs-lookup"><span data-stu-id="562da-104">Update pen firmware on Surface Hub 2S</span></span>

<span data-ttu-id="562da-105">你可以从适用于Surface Hub更新Windows 2 触控笔上更新固件，或者将固件更新下载到单独的电脑。</span><span class="sxs-lookup"><span data-stu-id="562da-105">You can update firmware on Surface Hub 2 pen from Windows Update for Business or by downloading the firmware update to a separate PC.</span></span> <span data-ttu-id="562da-106">从 2020 年 2 Windows 26 日起更新固件。</span><span class="sxs-lookup"><span data-stu-id="562da-106">Updated firmware is available from Windows Update beginning February 26, 2020.</span></span> 

## <a name="update-pen-firmware-using-windows-update-for-business"></a><span data-ttu-id="562da-107">使用适用于Windows更新更新笔固件</span><span class="sxs-lookup"><span data-stu-id="562da-107">Update pen firmware using Windows Update for Business</span></span>

<span data-ttu-id="562da-108">本节介绍如何通过 Windows 更新的自动维护周期来更新笔固件，该更新默认配置为在下午 3 点发生。</span><span class="sxs-lookup"><span data-stu-id="562da-108">This section describes how to update pen firmware via the automated maintenance cycles for Windows Update, configured by default to occur nightly at 3 a.m.</span></span> <span data-ttu-id="562da-109">在将更新应用到 2 个笔之前，您需要规划两个维护Surface Hub完成。</span><span class="sxs-lookup"><span data-stu-id="562da-109">You will need to plan for two maintenance cycles to complete before applying the update to the Surface Hub 2 pen.</span></span> <span data-ttu-id="562da-110">或者，与任何其他更新一样，您可以使用 Windows Update for Business (WUfB) 应用笔固件。</span><span class="sxs-lookup"><span data-stu-id="562da-110">Alternately, like any other update, you can use Windows Update for Business (WUfB) to apply the pen firmware.</span></span> <span data-ttu-id="562da-111">有关详细信息，请参阅管理Windows[更新Surface Hub。](manage-windows-updates-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="562da-111">For more information, see [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).</span></span>

1. <span data-ttu-id="562da-112">确保将Surface Hub 2 个笔配对Surface Hub 2S：长按顶部按钮，直到白色指示灯\*\*\*\* 开始闪烁。</span><span class="sxs-lookup"><span data-stu-id="562da-112">Ensure the Surface Hub 2 pen is paired to Surface Hub 2S: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 个笔](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="562da-114">On Surface Hub， login as an Admin， open**设置**， and then scan for new 蓝牙 devices.</span><span class="sxs-lookup"><span data-stu-id="562da-114">On Surface Hub, login as an Admin, open **Settings**, and then scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="562da-115">选择笔以完成配对过程。</span><span class="sxs-lookup"><span data-stu-id="562da-115">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="562da-116">按 **笔** 上的顶部按钮应用更新。</span><span class="sxs-lookup"><span data-stu-id="562da-116">Press the **top** button on the pen to apply the update.</span></span> <span data-ttu-id="562da-117">可能需要两个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="562da-117">It may take up to two hours to complete.</span></span>

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a><span data-ttu-id="562da-118">通过下载到单独的电脑更新笔固件</span><span class="sxs-lookup"><span data-stu-id="562da-118">Update pen firmware by downloading to separate PC</span></span>

<span data-ttu-id="562da-119">你可以从运行 Surface Hub 2 触控笔的单独电脑上更新Windows 10。</span><span class="sxs-lookup"><span data-stu-id="562da-119">You can update the firmware on Surface Hub 2 pen from a separate PC running Windows 10.</span></span> <span data-ttu-id="562da-120">此方法还允许您验证笔固件已成功更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="562da-120">This method also enables you to verify that the pen firmware has successfully updated to the latest version.</span></span>

1. <span data-ttu-id="562da-121">将 Surface Hub 2 个笔与蓝牙的电脑配对：长按顶部按钮，直到白色指示灯开始\*\*\*\* 闪烁。</span><span class="sxs-lookup"><span data-stu-id="562da-121">Pair the Surface Hub 2 pen to your Bluetooth-capable PC: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 个笔](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="562da-123">在电脑上，扫描新的蓝牙设备。</span><span class="sxs-lookup"><span data-stu-id="562da-123">On the PC, scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="562da-124">选择笔以完成配对过程。</span><span class="sxs-lookup"><span data-stu-id="562da-124">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="562da-125">在开始新Surface Hub之前断开所有其他 2s 笔连接。</span><span class="sxs-lookup"><span data-stu-id="562da-125">Disconnect all other Surface Hub 2s pens before starting a new update.</span></span>
3. <span data-ttu-id="562da-126">将[Surface Hub 2 触控笔固件更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下载到电脑。</span><span class="sxs-lookup"><span data-stu-id="562da-126">Download the [Surface Hub 2 Pen Firmware Update Tool](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) to your PC.</span></span>
4. <span data-ttu-id="562da-127">运行 **PenCfu.exe。**</span><span class="sxs-lookup"><span data-stu-id="562da-127">Run **PenCfu.exe.**</span></span> <span data-ttu-id="562da-128">安装进度将显示在工具中。</span><span class="sxs-lookup"><span data-stu-id="562da-128">The install progress is displayed in the tool.</span></span> <span data-ttu-id="562da-129">可能需要几分钟才能完成更新。</span><span class="sxs-lookup"><span data-stu-id="562da-129">It may take several minutes to finish updating.</span></span> 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a><span data-ttu-id="562da-130">检查 2 个Surface Hub固件版本</span><span class="sxs-lookup"><span data-stu-id="562da-130">Check firmware version of Surface Hub 2 pen</span></span>

1. <span data-ttu-id="562da-131">运行 \*\*get_version.bat， \*\* 然后按 **触控笔** 上的顶部按钮。</span><span class="sxs-lookup"><span data-stu-id="562da-131">Run **get_version.bat** and press the **top** button on the pen.</span></span>
2. <span data-ttu-id="562da-132">该工具将报告笔的固件版本。</span><span class="sxs-lookup"><span data-stu-id="562da-132">The tool will report the firmware version of the pen.</span></span> <span data-ttu-id="562da-133">示例：</span><span class="sxs-lookup"><span data-stu-id="562da-133">Example:</span></span>
    - <span data-ttu-id="562da-134">旧固件为 468.2727.368</span><span class="sxs-lookup"><span data-stu-id="562da-134">Old firmware is 468.2727.368</span></span>
    - <span data-ttu-id="562da-135">新固件为 468.3347.368</span><span class="sxs-lookup"><span data-stu-id="562da-135">New firmware is 468.3347.368</span></span>

## <a name="command-line-options"></a><span data-ttu-id="562da-136">命令行选项</span><span class="sxs-lookup"><span data-stu-id="562da-136">Command line options</span></span>

<span data-ttu-id="562da-137">你可以从Surface Hub运行 (PenCfu.exe) 2 笔固件更新工具。</span><span class="sxs-lookup"><span data-stu-id="562da-137">You can run Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) from the command line.</span></span>

1. <span data-ttu-id="562da-138">将笔与电脑配对，然后单击 **笔** 上的顶部按钮。</span><span class="sxs-lookup"><span data-stu-id="562da-138">Pair the pen to your PC and click the **top** button on the pen.</span></span>
2. <span data-ttu-id="562da-139">双击PenCfu.exe\*\* 启动 \*\* 固件更新。</span><span class="sxs-lookup"><span data-stu-id="562da-139">Double click **PenCfu.exe** to initiate the firmware update.</span></span> <span data-ttu-id="562da-140">请注意，配置文件和固件映像文件必须与工具存储在同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="562da-140">Note that the configuration file and the firmware image files must be stored in the same folder as the tool.</span></span>
3. <span data-ttu-id="562da-141">对于其他选项，PenCfu.exe \*\* -h\*\* 来显示可用参数，如下表所列。</span><span class="sxs-lookup"><span data-stu-id="562da-141">For additional options, run **PenCfu.exe -h** to display the available parameters, as listed in the following table.</span></span>  
    - <span data-ttu-id="562da-142">示例：PenCfu.exe -h</span><span class="sxs-lookup"><span data-stu-id="562da-142">Example: PenCfu.exe -h</span></span>
4. <span data-ttu-id="562da-143">输入 **Ctrl+C** 可安全关闭该工具。</span><span class="sxs-lookup"><span data-stu-id="562da-143">Enter **Ctrl+C** to safely shut down the tool.</span></span>

 

| **<span data-ttu-id="562da-144">命令</span><span class="sxs-lookup"><span data-stu-id="562da-144">Command</span></span>**    | **<span data-ttu-id="562da-145">描述</span><span class="sxs-lookup"><span data-stu-id="562da-145">Description</span></span>**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="562da-146">-h 帮助</span><span class="sxs-lookup"><span data-stu-id="562da-146">-h help</span></span>        | <span data-ttu-id="562da-147">显示工具命令行界面帮助和退出。</span><span class="sxs-lookup"><span data-stu-id="562da-147">Display tool command line interface help and exit.</span></span>                                                                                                                                                                                                                                                                                                                                             |
| <span data-ttu-id="562da-148">-v 版本</span><span class="sxs-lookup"><span data-stu-id="562da-148">-v version</span></span>     | <span data-ttu-id="562da-149">显示工具版本和退出。</span><span class="sxs-lookup"><span data-stu-id="562da-149">Display tool version and exit.</span></span>                                                                                                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="562da-150">-l log-filter</span><span class="sxs-lookup"><span data-stu-id="562da-150">-l log-filter</span></span>  | <span data-ttu-id="562da-151">为项目设置筛选日志文件。</span><span class="sxs-lookup"><span data-stu-id="562da-151">Set a filter level for the log file.</span></span> <span data-ttu-id="562da-152">日志消息有 4 个可能级别：DEBUG (最低) 、INFO、WARNING 和 ERROR (最高) 。</span><span class="sxs-lookup"><span data-stu-id="562da-152">Log messages have 4 possible levels: DEBUG (lowest), INFO, WARNING and ERROR (highest).</span></span> <span data-ttu-id="562da-153">设置日志筛选器级别将日志消息筛选为仅具有相同级别或更高级别的消息。</span><span class="sxs-lookup"><span data-stu-id="562da-153">Setting a log filter level filters log messages to only message with the same level or higher.</span></span> <span data-ttu-id="562da-154">例如，如果筛选器级别设置为 WARNING，则只会记录 WARNING 和 ERROR 消息。</span><span class="sxs-lookup"><span data-stu-id="562da-154">For example, if the filter level is set to WARNING, only WARNING and ERROR messages will be logged.</span></span> <span data-ttu-id="562da-155">默认情况下，此选项设置为 OFF，这将禁用日志记录。</span><span class="sxs-lookup"><span data-stu-id="562da-155">By default, this option is set to OFF, which disables logging.</span></span> |
| <span data-ttu-id="562da-156">-g get-version</span><span class="sxs-lookup"><span data-stu-id="562da-156">-g get-version</span></span> | <span data-ttu-id="562da-157">如果指定，该工具将仅获取与存储在工具同一文件夹中的配置文件匹配的已连接笔的 FW 版本。</span><span class="sxs-lookup"><span data-stu-id="562da-157">If specified, the tool will only get the FW version of the connected pen that matches the configuration file that is stored in the same folder as the tool.</span></span>                                                                                                                                                                                                                                    

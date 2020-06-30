---
title: 在桌面模式下使用适用于企业的 Surface 诊断工具包
description: 如何使用 SDT 帮助你的组织中的用户运行该工具来识别和诊断 Surface 设备的问题。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 9e6b34a8d34081fc12cab4851104f0b67c3dfea4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830679"
---
# <span data-ttu-id="5011c-103">在桌面模式下使用适用于企业的 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="5011c-103">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>

<span data-ttu-id="5011c-104">本主题介绍了如何使用 Surface 诊断工具包（SDT）来帮助你的组织中的用户运行该工具来识别和诊断 Surface 设备的问题。</span><span class="sxs-lookup"><span data-stu-id="5011c-104">This topic explains how to use the Surface Diagnostic Toolkit (SDT) to help users in your organization run the tool to identify and diagnose issues with the Surface device.</span></span> <span data-ttu-id="5011c-105">成功运行 SDT 可以快速确定报告的问题是否由硬件故障或用户错误引起。</span><span class="sxs-lookup"><span data-stu-id="5011c-105">Successfully running SDT can quickly determine if a reported issue is caused by failed hardware or user error.</span></span> <span data-ttu-id="5011c-106">有关 SDT 中受支持的 Surface 设备的列表，请参阅[部署适用于企业的 Surface 诊断工具包](surface-diagnostic-toolkit-business.md)。</span><span class="sxs-lookup"><span data-stu-id="5011c-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>


1. <span data-ttu-id="5011c-107">指导用户从软件分发点或网络共享安装[SDT 程序包](surface-diagnostic-toolkit-business.md#create-custom-sdt)。</span><span class="sxs-lookup"><span data-stu-id="5011c-107">Direct the user to install [the SDT package](surface-diagnostic-toolkit-business.md#create-custom-sdt) from a software distribution point or network share.</span></span> <span data-ttu-id="5011c-108">安装完成后，你可以通过一系列测试来指导用户。</span><span class="sxs-lookup"><span data-stu-id="5011c-108">After it is installed, you’re ready to guide the user through a series of tests.</span></span> 

2. <span data-ttu-id="5011c-109">从主页开始，该页面允许用户输入问题的描述，然后单击 "**继续**"，如图1所示。</span><span class="sxs-lookup"><span data-stu-id="5011c-109">Begin at the home page, which allows users to enter a description of the issue, and click **Continue**, as shown in figure 1.</span></span>

    ![<span data-ttu-id="5011c-110">在桌面模式下启动 SDT ](images/sdt-desk-1.png)
 *图1。桌面模式中的 SDT*</span><span class="sxs-lookup"><span data-stu-id="5011c-110">Start SDT in desktop mode](images/sdt-desk-1.png)
*Figure 1. SDT in desktop mode*</span></span>

3. <span data-ttu-id="5011c-111">当 SDT 指示设备具有最新的更新时，请单击 "**继续**" 以转到可用测试的目录，如图2所示。</span><span class="sxs-lookup"><span data-stu-id="5011c-111">When SDT indicates the device has the latest updates, click **Continue** to advance to the catalog of available tests, as shown in figure 2.</span></span>

    ![<span data-ttu-id="5011c-112">从 SDT 选项中选择 ](images/sdt-desk-2.png)
 *图2。从 SDT 选项中选择*</span><span class="sxs-lookup"><span data-stu-id="5011c-112">Select from SDT options](images/sdt-desk-2.png)
*Figure 2. Select from SDT options*</span></span>

4. <span data-ttu-id="5011c-113">你可以选择运行所有诊断测试。</span><span class="sxs-lookup"><span data-stu-id="5011c-113">You can choose to run all the diagnostic tests.</span></span> <span data-ttu-id="5011c-114">或者，如果你怀疑某个特定问题（如显示错误或电源问题），请单击 "**选择**" 以从可用测试中进行选择，然后单击 "**运行所选**"，如图3所示。</span><span class="sxs-lookup"><span data-stu-id="5011c-114">Or, if you already suspect a particular issue such as a faulty display or a power supply problem, click **Select** to choose from the available tests and click **Run Selected**, as shown in figure 3.</span></span> <span data-ttu-id="5011c-115">有关每个测试的详细信息，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5011c-115">See the following table for details of each test.</span></span> 

    ![<span data-ttu-id="5011c-116">选择硬件测试 ](images/sdt-desk-3.png)
 *图3。选择硬件测试*</span><span class="sxs-lookup"><span data-stu-id="5011c-116">Select hardware tests](images/sdt-desk-3.png)
*Figure 3. Select hardware tests*</span></span>

    <span data-ttu-id="5011c-117">硬件测试</span><span class="sxs-lookup"><span data-stu-id="5011c-117">Hardware test</span></span> | <span data-ttu-id="5011c-118">描述</span><span class="sxs-lookup"><span data-stu-id="5011c-118">Description</span></span>
    --- | ---
    <span data-ttu-id="5011c-119">电源设备和电池</span><span class="sxs-lookup"><span data-stu-id="5011c-119">Power Supply and Battery</span></span> |  <span data-ttu-id="5011c-120">检查电源的运行速度最佳</span><span class="sxs-lookup"><span data-stu-id="5011c-120">Checks Power supply is functioning optimally</span></span>
    <span data-ttu-id="5011c-121">显示和声音</span><span class="sxs-lookup"><span data-stu-id="5011c-121">Display and Sound</span></span>   | <span data-ttu-id="5011c-122">检查亮度、粘滞或死像素、扬声器和麦克风功能</span><span class="sxs-lookup"><span data-stu-id="5011c-122">Checks brightness, stuck or dead pixels, speaker and microphone functioning</span></span>
    <span data-ttu-id="5011c-123">端口和附件</span><span class="sxs-lookup"><span data-stu-id="5011c-123">Ports and Accessories</span></span>   | <span data-ttu-id="5011c-124">检查附件、屏幕连接和 USB 运行状况</span><span class="sxs-lookup"><span data-stu-id="5011c-124">Checks accessories, screen attach and USB functioning</span></span>
    <span data-ttu-id="5011c-125">连接性</span><span class="sxs-lookup"><span data-stu-id="5011c-125">Connectivity</span></span> |  <span data-ttu-id="5011c-126">检查蓝牙、无线和 LTE 连接</span><span class="sxs-lookup"><span data-stu-id="5011c-126">Checks Bluetooth, wireless and LTE connectivity</span></span>
    <span data-ttu-id="5011c-127">安全性</span><span class="sxs-lookup"><span data-stu-id="5011c-127">Security</span></span>    | <span data-ttu-id="5011c-128">检查与安全性相关的问题</span><span class="sxs-lookup"><span data-stu-id="5011c-128">Checks security related issues</span></span>
    <span data-ttu-id="5011c-129">触控</span><span class="sxs-lookup"><span data-stu-id="5011c-129">Touch</span></span>   | <span data-ttu-id="5011c-130">检查触摸相关问题</span><span class="sxs-lookup"><span data-stu-id="5011c-130">Checks touch related issues</span></span>
    <span data-ttu-id="5011c-131">键盘和触控</span><span class="sxs-lookup"><span data-stu-id="5011c-131">Keyboard and touch</span></span> |    <span data-ttu-id="5011c-132">检查集成键盘连接和输入封面</span><span class="sxs-lookup"><span data-stu-id="5011c-132">Checks integrated keyboard connection and type cover</span></span>
    <span data-ttu-id="5011c-133">传感器</span><span class="sxs-lookup"><span data-stu-id="5011c-133">Sensors</span></span> | <span data-ttu-id="5011c-134">检查设备中不同传感器的运行情况</span><span class="sxs-lookup"><span data-stu-id="5011c-134">Checks functioning of different sensors in the device</span></span>
    <span data-ttu-id="5011c-135">硬件</span><span class="sxs-lookup"><span data-stu-id="5011c-135">Hardware</span></span> |  <span data-ttu-id="5011c-136">检查不同硬件组件（如图形卡和照相机）的问题</span><span class="sxs-lookup"><span data-stu-id="5011c-136">Checks issues with different hardware components such as graphics card and camera</span></span>





<span id="multiple" />

## <span data-ttu-id="5011c-137">运行多个硬件测试以解决问题</span><span class="sxs-lookup"><span data-stu-id="5011c-137">Running multiple hardware tests to troubleshoot issues</span></span>

<span data-ttu-id="5011c-138">SDT 设计为可运行一系列测试的交互式工具。</span><span class="sxs-lookup"><span data-stu-id="5011c-138">SDT is designed as an interactive tool that runs a series of tests.</span></span> <span data-ttu-id="5011c-139">对于每个测试，SDT 都提供有关测试性质的说明以及用户应期望或查找的内容，以便测试成功。</span><span class="sxs-lookup"><span data-stu-id="5011c-139">For each test, SDT provides instructions summarizing  the nature of the test and what users should expect or look for in order for the test to be successful.</span></span> <span data-ttu-id="5011c-140">例如，若要诊断显示亮度是否正常工作，SDT 将从零开始，并将亮度增加到100%，要求用户通过回答 **"是"** 或 "**否**" 来进行确认--该亮度按预期方式工作，如图4所示。</span><span class="sxs-lookup"><span data-stu-id="5011c-140">For example, to diagnose if the display brightness is working properly, SDT starts at zero and increases the brightness to 100 percent, asking users to confirm – by answering **Yes** or **No** -- that brightness is functioning as expected, as shown in figure 4.</span></span> 

<span data-ttu-id="5011c-141">对于每个测试，如果功能不按预期工作，并且用户单击 "**否**"，则 SDT 将生成可能的原因和解决问题的方法的报告。</span><span class="sxs-lookup"><span data-stu-id="5011c-141">For each test, if functionality does not work as expected and the user clicks **No**, SDT generates a report of the possible causes and ways to troubleshoot it.</span></span> 

![<span data-ttu-id="5011c-142">运行硬件诊断 ](images/sdt-desk-4.png)
 *图4。运行硬件诊断*</span><span class="sxs-lookup"><span data-stu-id="5011c-142">Running hardware diagnostics](images/sdt-desk-4.png)
*Figure 4. Running hardware diagnostics*</span></span>

1. <span data-ttu-id="5011c-143">如果亮度已按预期成功地调整了0-100%，请直接在用户单击 **"是"** ，然后单击 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="5011c-143">If the brightness successfully adjusts from 0-100 percent as expected, direct the user to click **Yes** and then click **Continue**.</span></span> 
2. <span data-ttu-id="5011c-144">如果亮度无法按预期调整0-100%，请指示用户单击 "**否**"，然后单击 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="5011c-144">If the brightness fails to adjust from 0-100 percent as expected, direct the user to click **No** and then click **Continue**.</span></span> 
3. <span data-ttu-id="5011c-145">根据需要指导用户完成剩余的测试。</span><span class="sxs-lookup"><span data-stu-id="5011c-145">Guide users through remaining tests as appropriate.</span></span> <span data-ttu-id="5011c-146">完成后，SDT 将自动提供报表的高级别摘要，包括任何硬件问题的可能原因以及解决方案的指南。</span><span class="sxs-lookup"><span data-stu-id="5011c-146">When finished, SDT automatically provides a high-level summary of the report, including the possible causes of any hardware issues along with guidance for resolution.</span></span>


### <span data-ttu-id="5011c-147">修复应用程序</span><span class="sxs-lookup"><span data-stu-id="5011c-147">Repairing applications</span></span>

<span data-ttu-id="5011c-148">SDT 使你能够诊断和修复可能导致问题的应用程序，如图5所示。</span><span class="sxs-lookup"><span data-stu-id="5011c-148">SDT enables you to diagnose and repair applications that may be causing issues, as shown in figure 5.</span></span>

![<span data-ttu-id="5011c-149">正在运行修复 ](images/sdt-desk-5.png)
 *图5。正在运行修复*</span><span class="sxs-lookup"><span data-stu-id="5011c-149">Running repairs](images/sdt-desk-5.png)
*Figure 5. Running repairs*</span></span>
<span id="logs" />

### <span data-ttu-id="5011c-150">生成用于分析问题的日志</span><span class="sxs-lookup"><span data-stu-id="5011c-150">Generating logs for analyzing issues</span></span> 

<span data-ttu-id="5011c-151">SDT 在应用程序、驱动程序、硬件和操作系统问题上提供丰富的支持日志的诊断支持，如图6所示。</span><span class="sxs-lookup"><span data-stu-id="5011c-151">SDT provides extensive log-enabled diagnosis support across applications, drivers, hardware, and operating system issues, as shown in figure 6.</span></span>

![<span data-ttu-id="5011c-152">生成日志 ](images/sdt-desk-6.png)
 *图6。生成日志*</span><span class="sxs-lookup"><span data-stu-id="5011c-152">Generating logs](images/sdt-desk-6.png)
*Figure 6. Generating logs*</span></span>

<span id="detailed-report" />

### <span data-ttu-id="5011c-153">生成比较设备和最佳配置的详细报告</span><span class="sxs-lookup"><span data-stu-id="5011c-153">Generating detailed report comparing device vs. optimal configuration</span></span>

<span data-ttu-id="5011c-154">根据日志，SDT 将为基于软件和固件的问题生成报表，你可以将这些问题保存到首选位置。</span><span class="sxs-lookup"><span data-stu-id="5011c-154">Based on the logs, SDT generates a report for software- and firmware-based issues that you can save to a preferred location.</span></span>

## <span data-ttu-id="5011c-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="5011c-155">Related topics</span></span>

- [<span data-ttu-id="5011c-156">使用命令运行适用于企业的 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="5011c-156">Run Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)


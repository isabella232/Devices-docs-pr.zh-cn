---
title: 使用命令运行适用于企业的 Surface 诊断工具包
description: 如何在命令控制台中Toolkit Surface Diagnostic Toolkit
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
ms.openlocfilehash: f3856499bd769b96e22c0a47323c984eb38d8a18
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327326"
---
# <span data-ttu-id="a2902-103">使用命令运行适用于企业的 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="a2902-103">Run Surface Diagnostic Toolkit for Business using commands</span></span>

<span data-ttu-id="a2902-104">在命令提示符Toolkit (Surface Diagnostic) SDT 应用需要下载 SDT 应用控制台。</span><span class="sxs-lookup"><span data-stu-id="a2902-104">Running the Surface Diagnostic Toolkit (SDT) at a command prompt requires downloading the SDT app console.</span></span> <span data-ttu-id="a2902-105">安装 SDT 后，可以通过 Windows 命令控制台 (cmd.exe) 或 Windows PowerShell（包括 PowerShell 集成脚本环境 (ISE) ）在命令提示符下运行 SDT，它支持自动完成命令、复制/粘贴和其他功能。</span><span class="sxs-lookup"><span data-stu-id="a2902-105">After it's installed, you can run SDT at a command prompt via the Windows command console (cmd.exe) or using Windows PowerShell, including PowerShell Integrated Scripting Environment (ISE), which provides support for autocompletion of commands, copy/paste, and other features.</span></span>  <span data-ttu-id="a2902-106">有关 SDT 中受支持的 Surface 设备的列表，请参阅部署 [适用于Toolkit Surface 诊断设备](surface-diagnostic-toolkit-business.md)。</span><span class="sxs-lookup"><span data-stu-id="a2902-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>

>[!NOTE]
><span data-ttu-id="a2902-107">若要使用命令运行 SDT，必须登录到管理员帐户或登录到作为 Surface 设备上 Administrator 组的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="a2902-107">To run SDT using commands, you must be signed in to the Administrator account or signed in to an account that is a member of the Administrator group on your Surface device.</span></span>

## <span data-ttu-id="a2902-108">运行 SDT 应用控制台</span><span class="sxs-lookup"><span data-stu-id="a2902-108">Running SDT app console</span></span>

<span data-ttu-id="a2902-109">从 Surface Tools for IT 下载页面下载并安装 SDT [应用控制台](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="a2902-109">Download and install SDT app console from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="a2902-110">可以使用 Windows 命令提示符 (cmd.exe) 或Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="a2902-110">You can use the Windows command prompt (cmd.exe) or Windows PowerShell to:</span></span> 

- <span data-ttu-id="a2902-111">收集所有日志文件。</span><span class="sxs-lookup"><span data-stu-id="a2902-111">Collect all log files.</span></span>
- <span data-ttu-id="a2902-112">使用最佳做法分析器运行运行状况诊断。</span><span class="sxs-lookup"><span data-stu-id="a2902-112">Run health diagnostics using Best Practice Analyzer.</span></span>
- <span data-ttu-id="a2902-113">检查更新中缺少固件或驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="a2902-113">Check update for missing firmware or driver updates.</span></span>

>[!NOTE]
><span data-ttu-id="a2902-114">在此版本中，SDT 应用控制台仅支持单个命令。</span><span class="sxs-lookup"><span data-stu-id="a2902-114">In this release, the SDT app console supports single commands only.</span></span> <span data-ttu-id="a2902-115">运行多个命令行选项需要单独运行每个命令的控制台 exe。</span><span class="sxs-lookup"><span data-stu-id="a2902-115">Running multiple command line options requires running the console exe separately for each command.</span></span> 

<span data-ttu-id="a2902-116">默认情况下，输出文件与控制台应用保存在同一位置。</span><span class="sxs-lookup"><span data-stu-id="a2902-116">By default, output files are saved in the same location as the console app.</span></span> <span data-ttu-id="a2902-117">有关命令的完整列表，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a2902-117">Refer to the following table for a complete list of commands.</span></span>

<span data-ttu-id="a2902-118">命令</span><span class="sxs-lookup"><span data-stu-id="a2902-118">Command</span></span> | <span data-ttu-id="a2902-119">注释</span><span class="sxs-lookup"><span data-stu-id="a2902-119">Notes</span></span>
--- | ---
<span data-ttu-id="a2902-120">-DataCollector "output file"</span><span class="sxs-lookup"><span data-stu-id="a2902-120">-DataCollector "output file"</span></span> | <span data-ttu-id="a2902-121">将系统详细信息收集到 zip 文件中。</span><span class="sxs-lookup"><span data-stu-id="a2902-121">Collects system details into a zip file.</span></span> <span data-ttu-id="a2902-122">"输出文件"是创建系统详细信息 zip 文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="a2902-122">"output file" is the file path to create system details zip file.</span></span><br><br><span data-ttu-id="a2902-123">**示例**：</span><span class="sxs-lookup"><span data-stu-id="a2902-123">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
<span data-ttu-id="a2902-124">-bpa "output file"</span><span class="sxs-lookup"><span data-stu-id="a2902-124">-bpa "output file"</span></span> | <span data-ttu-id="a2902-125">检查设备中的多个设置和运行状况指示器。</span><span class="sxs-lookup"><span data-stu-id="a2902-125">Checks several settings and health indicators in the device.</span></span> <span data-ttu-id="a2902-126">"输出文件"是创建 HTML 报表的文件路径。</span><span class="sxs-lookup"><span data-stu-id="a2902-126">“output file" is the file path to create the HTML report.</span></span><br><br><span data-ttu-id="a2902-127">**示例**：</span><span class="sxs-lookup"><span data-stu-id="a2902-127">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
<span data-ttu-id="a2902-128">-windowsupdate</span><span class="sxs-lookup"><span data-stu-id="a2902-128">-windowsupdate</span></span> | <span data-ttu-id="a2902-129">检查 Windows 更新联机服务器是否缺少固件和/或驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="a2902-129">Checks Windows Update online servers for missing firmware and/or driver updates.</span></span><br><br><span data-ttu-id="a2902-130">**示例**：</span><span class="sxs-lookup"><span data-stu-id="a2902-130">**Example**:</span></span><br><span data-ttu-id="a2902-131">Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate</span><span class="sxs-lookup"><span data-stu-id="a2902-131">Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate</span></span>
<span data-ttu-id="a2902-132">-担保"输出文件"</span><span class="sxs-lookup"><span data-stu-id="a2902-132">-warranty "output file"</span></span> | <span data-ttu-id="a2902-133">检查设备上的担保信息 (有效或无效) 。</span><span class="sxs-lookup"><span data-stu-id="a2902-133">Checks warranty information on the device (valid or invalid).</span></span> <span data-ttu-id="a2902-134">可选"输出文件"是创建 xml 文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="a2902-134">The optional “output file” is the file path to create the xml file.</span></span> <br><br><span data-ttu-id="a2902-135">**示例**：</span><span class="sxs-lookup"><span data-stu-id="a2902-135">**Example**:</span></span> <br><span data-ttu-id="a2902-136">Microsoft.Surface.Diagnostics.App.Console.exe –warranty "warranty.xml"</span><span class="sxs-lookup"><span data-stu-id="a2902-136">Microsoft.Surface.Diagnostics.App.Console.exe –warranty “warranty.xml”</span></span>


>[!NOTE]
><span data-ttu-id="a2902-137">若要在目标设备上远程运行 SDT 应用控制台，可以使用 Microsoft Endpoint Configuration Manager 等配置管理工具。</span><span class="sxs-lookup"><span data-stu-id="a2902-137">To run the SDT app console remotely on target devices, you can use a configuration management tool such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="a2902-138">或者，您可以创建一个包含控制台应用和相应控制台命令的 .zip 文件，并按组织的软件分发过程进行部署。</span><span class="sxs-lookup"><span data-stu-id="a2902-138">Alternatively, you can create a .zip file containing the console app and appropriate console commands and deploy per your organization’s software distribution processes.</span></span> 

## <span data-ttu-id="a2902-139">运行最佳做法分析器</span><span class="sxs-lookup"><span data-stu-id="a2902-139">Running Best Practice Analyzer</span></span> 

<span data-ttu-id="a2902-140">你可以跨关键组件（如 BitLocker、安全启动和受信任的平台模块 (TPM) ）运行 BPA 测试，然后将结果输出到可共享的文件。</span><span class="sxs-lookup"><span data-stu-id="a2902-140">You can run BPA tests across key components such as BitLocker, Secure Boot, and Trusted Platform Module (TPM) and then output the results to a shareable file.</span></span> <span data-ttu-id="a2902-141">该工具生成一系列表，这些表格包含颜色编码的标题和条件描述符，以及有关如何解决该问题的指导。</span><span class="sxs-lookup"><span data-stu-id="a2902-141">The tool generates a series of tables with color-coded headings and condition descriptors along with guidance about how to approach resolving the issue.</span></span> 

- <span data-ttu-id="a2902-142">绿色表示组件在最佳条件下运行， (最佳) 。</span><span class="sxs-lookup"><span data-stu-id="a2902-142">Green indicates the component is running in an optimal condition (optimal).</span></span>
- <span data-ttu-id="a2902-143">橙色表示组件未在最佳条件下运行， (运行) 。</span><span class="sxs-lookup"><span data-stu-id="a2902-143">Orange indicates the component is not running in an optimal condition (not optimal).</span></span>
- <span data-ttu-id="a2902-144">红色表示组件状态异常。</span><span class="sxs-lookup"><span data-stu-id="a2902-144">Red indicates the component is in an abnormal state.</span></span> 

### <span data-ttu-id="a2902-145">示例 BPA 结果输出</span><span class="sxs-lookup"><span data-stu-id="a2902-145">Sample BPA results output</span></span>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-146">BitLocker</span><span class="sxs-lookup"><span data-stu-id="a2902-146">BitLocker</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-147">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-147">Description:</span></span></strong></td><td><span data-ttu-id="a2902-148">检查系统驱动器上是否启用了 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="a2902-148">Checks if BitLocker is enabled on the system drive.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-149">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-149">Value:</span></span></strong></td><td><span data-ttu-id="a2902-150">保护打开</span><span class="sxs-lookup"><span data-stu-id="a2902-150">Protection On</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-151">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-151">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-152">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-152">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-153">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-153">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-154">强烈建议启用 BitLocker 来保护你的数据。</span><span class="sxs-lookup"><span data-stu-id="a2902-154">It is highly recommended to enable BitLocker to protect your data.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-155">安全启动</span><span class="sxs-lookup"><span data-stu-id="a2902-155">Secure Boot</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-156">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-156">Description:</span></span></strong></td><td><span data-ttu-id="a2902-157">检查安全启动是否已启用。</span><span class="sxs-lookup"><span data-stu-id="a2902-157">Checks if Secure Boot is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-158">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-158">Value:</span></span></strong></td><td><span data-ttu-id="a2902-159">True</span><span class="sxs-lookup"><span data-stu-id="a2902-159">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-160">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-160">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-161">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-161">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-162">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-162">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-163">强烈建议启用安全启动来保护电脑。</span><span class="sxs-lookup"><span data-stu-id="a2902-163">It is highly recommended to enable Secure Boot to protect your PC.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-164">受信任的平台模块</span><span class="sxs-lookup"><span data-stu-id="a2902-164">Trusted Platform Module</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-165">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-165">Description:</span></span></strong></td><td><span data-ttu-id="a2902-166">确保 TPM 正常工作。</span><span class="sxs-lookup"><span data-stu-id="a2902-166">Ensures that the TPM is functional.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-167">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-167">Value:</span></span></strong></td><td><span data-ttu-id="a2902-168">True</span><span class="sxs-lookup"><span data-stu-id="a2902-168">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-169">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-169">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-170">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-170">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-171">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-171">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-172">如果没有功能 TPM，基于安全性的函数（如 BitLocker）可能无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="a2902-172">Without a functional TPM, security-based functions such as BitLocker may not work properly.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-173">连接待机</span><span class="sxs-lookup"><span data-stu-id="a2902-173">Connected Standby</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-174">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-174">Description:</span></span></strong></td><td><span data-ttu-id="a2902-175">检查连接待机是否已启用。</span><span class="sxs-lookup"><span data-stu-id="a2902-175">Checks if Connected Standby is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-176">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-176">Value:</span></span></strong></td><td><span data-ttu-id="a2902-177">True</span><span class="sxs-lookup"><span data-stu-id="a2902-177">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-178">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-178">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-179">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-179">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-180">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-180">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-181">连接待机允许 Surface 设备在未使用时接收更新和通知。</span><span class="sxs-lookup"><span data-stu-id="a2902-181">Connected Standby allows a Surface device to receive updates and notifications while not being used.</span></span> <span data-ttu-id="a2902-182">为了获得最佳体验，应启用连接待机。</span><span class="sxs-lookup"><span data-stu-id="a2902-182">For best experience, Connected Standby should be enabled.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-183">蓝牙</span><span class="sxs-lookup"><span data-stu-id="a2902-183">Bluetooth</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-184">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-184">Description:</span></span></strong></td><td><span data-ttu-id="a2902-185">检查Bluetooth是否已启用。</span><span class="sxs-lookup"><span data-stu-id="a2902-185">Checks if Bluetooth is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-186">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-186">Value:</span></span></strong></td><td><span data-ttu-id="a2902-187">启用</span><span class="sxs-lookup"><span data-stu-id="a2902-187">Enabled</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-188">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-188">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-189">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-189">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-190">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-190">Guidance:</span></span></strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-191">调试模式</span><span class="sxs-lookup"><span data-stu-id="a2902-191">Debug Mode</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-192">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-192">Description:</span></span></strong></td><td><span data-ttu-id="a2902-193">检查操作系统是否位于调试模式。</span><span class="sxs-lookup"><span data-stu-id="a2902-193">Checks if the operating system is in Debug mode.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-194">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-194">Value:</span></span></strong></td><td><span data-ttu-id="a2902-195">正常</span><span class="sxs-lookup"><span data-stu-id="a2902-195">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-196">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-196">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-197">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-197">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-198">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-198">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-199">调试启动选项启用或禁用 Windows 操作系统的内核调试。</span><span class="sxs-lookup"><span data-stu-id="a2902-199">The debug boot option enables or disables kernel debugging of the Windows operating system.</span></span> <span data-ttu-id="a2902-200">启用此选项可能会导致系统不稳定，并可能阻止 DRM (受保护媒体) 管理方式的 DRM。</span><span class="sxs-lookup"><span data-stu-id="a2902-200">Enabling this option can cause system instability and can prevent DRM (digital rights managemend) protected media from playing.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-201">测试签名</span><span class="sxs-lookup"><span data-stu-id="a2902-201">Test Signing</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-202">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-202">Description:</span></span></strong></td><td><span data-ttu-id="a2902-203">检查测试签名是否已启用。</span><span class="sxs-lookup"><span data-stu-id="a2902-203">Checks if Test Signing is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-204">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-204">Value:</span></span></strong></td><td><span data-ttu-id="a2902-205">正常</span><span class="sxs-lookup"><span data-stu-id="a2902-205">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-206">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-206">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-207">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-207">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-208">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-208">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-209">测试签名是一种 Windows 启动设置，只能用于测试预发布驱动程序。</span><span class="sxs-lookup"><span data-stu-id="a2902-209">Test Signing is a Windows startup setting that should only be used to test pre-release drivers.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-210">活动电源计划</span><span class="sxs-lookup"><span data-stu-id="a2902-210">Active Power Plan</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-211">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-211">Description:</span></span></strong></td><td><span data-ttu-id="a2902-212">检查正确的电源计划是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a2902-212">Checks that the correct power plan is active.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-213">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-213">Value:</span></span></strong></td><td><span data-ttu-id="a2902-214">平衡</span><span class="sxs-lookup"><span data-stu-id="a2902-214">Balanced</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-215">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-215">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-216">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-216">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-217">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-217">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-218">强烈建议使用"平衡"电源计划，以最大限度地提高工作效率和电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="a2902-218">It is highly recommended to use the "Balanced" power plan to maximize productivity and battery life.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500"><span data-ttu-id="a2902-219">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="a2902-219">Windows Update</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-220">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-220">Description:</span></span></strong></td><td><span data-ttu-id="a2902-221">检查设备是否随 Windows 更新一起更新。</span><span class="sxs-lookup"><span data-stu-id="a2902-221">Checks if the device is up to date with Windows updates.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-222">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-222">Value:</span></span></strong></td><td><span data-ttu-id="a2902-223">Microsoft Silverlight (KB4023307) ，Windows Defender 防病毒的定义更新 - KB2267602 (定义 1.279.1433.0) </span><span class="sxs-lookup"><span data-stu-id="a2902-223">Microsoft Silverlight (KB4023307), Definition Update for Windows Defender Antivirus - KB2267602 (Definition 1.279.1433.0)</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-224">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-224">Condition:</span></span></strong></td><td><font color="ff9500"><span data-ttu-id="a2902-225">不是最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-225">Not Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-226">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-226">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-227">更新到最新窗口，确保你使用最新的固件和驱动程序。</span><span class="sxs-lookup"><span data-stu-id="a2902-227">Updating to the latest windows makes sure you are on the latest firmware and drivers.</span></span> <span data-ttu-id="a2902-228">建议始终使设备保持最新</span><span class="sxs-lookup"><span data-stu-id="a2902-228">It is recommended to always keep your device up to date</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-229">免费硬盘空间</span><span class="sxs-lookup"><span data-stu-id="a2902-229">Free Hard Drive Space</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-230">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-230">Description:</span></span></strong></td><td><span data-ttu-id="a2902-231">检查可用硬盘空间是否不足。</span><span class="sxs-lookup"><span data-stu-id="a2902-231">Checks for low free hard drive space.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-232">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-232">Value:</span></span></strong></td><td><span data-ttu-id="a2902-233">66%</span><span class="sxs-lookup"><span data-stu-id="a2902-233">66%</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-234">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-234">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-235">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-235">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-236">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-236">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-237">为获得最佳性能，硬盘应至少有 10% 的容量作为可用空间。</span><span class="sxs-lookup"><span data-stu-id="a2902-237">For best performance, your hard drive should have at least 10% of its capacity as free space.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-238">无法正常工作的设备</span><span class="sxs-lookup"><span data-stu-id="a2902-238">Non-Functioning Devices</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-239">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-239">Description:</span></span></strong></td><td><span data-ttu-id="a2902-240">设备管理器中无法正常工作的设备列表。</span><span class="sxs-lookup"><span data-stu-id="a2902-240">List of non-functioning devices in Device Manager.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-241">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-241">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="a2902-242">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-242">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-243">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-243">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-244">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-244">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-245">设备管理器中无法正常工作的设备可能会导致 Surface 设备出现不可预知的问题，例如（但不限于）各自硬件组件的节电。</span><span class="sxs-lookup"><span data-stu-id="a2902-245">Non-functioning devices in Device Manager may cause unpredictable problems with Surface devices such as, but not limited to, no power savings for the respective hardware component.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="a2902-246">外部监视器</span><span class="sxs-lookup"><span data-stu-id="a2902-246">External Monitor</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="a2902-247">描述：</span><span class="sxs-lookup"><span data-stu-id="a2902-247">Description:</span></span></strong></td><td><span data-ttu-id="a2902-248">检查可能具有兼容性问题的外部监视器。</span><span class="sxs-lookup"><span data-stu-id="a2902-248">Checks for an external monitor that may have compatibility issues.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="a2902-249">值：</span><span class="sxs-lookup"><span data-stu-id="a2902-249">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="a2902-250">条件：</span><span class="sxs-lookup"><span data-stu-id="a2902-250">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="a2902-251">最佳</span><span class="sxs-lookup"><span data-stu-id="a2902-251">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="a2902-252">指南：</span><span class="sxs-lookup"><span data-stu-id="a2902-252">Guidance:</span></span></strong></td><td><span data-ttu-id="a2902-253">请与原始设备制造商核实与 Surface 设备的兼容性。</span><span class="sxs-lookup"><span data-stu-id="a2902-253">Check with the original equipment manufacturer for compatibility with your Surface device.</span></span></td></tr>
</table>

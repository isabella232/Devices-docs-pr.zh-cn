---
title: 使用命令运行适用于企业的 Surface 诊断工具包
description: 如何在命令控制台中运行 Surface 诊断工具包
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
ms.openlocfilehash: 6a56e1231ff5d2f672305d7166bbfa46d1bc0354
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830686"
---
# <span data-ttu-id="172cb-103">使用命令运行适用于企业的 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="172cb-103">Run Surface Diagnostic Toolkit for Business using commands</span></span>

<span data-ttu-id="172cb-104">在命令提示符处运行 Surface 诊断工具包（SDT）需要下载 STD 应用控制台。</span><span class="sxs-lookup"><span data-stu-id="172cb-104">Running the Surface Diagnostic Toolkit (SDT) at a command prompt requires downloading the STD app console.</span></span> <span data-ttu-id="172cb-105">安装完成后，你可以通过 Windows 命令控制台（cmd.exe）或使用 Windows PowerShell （包括 PowerShell 集成脚本环境（ISE））在命令提示符处运行 SDT，它提供了支持命令、复制/粘贴和其他功能的自动完成功能的支持。</span><span class="sxs-lookup"><span data-stu-id="172cb-105">After it's installed, you can run SDT at a command prompt via the Windows command console (cmd.exe) or using Windows PowerShell, including PowerShell Integrated Scripting Environment (ISE), which provides support for autocompletion of commands, copy/paste, and other features.</span></span>  <span data-ttu-id="172cb-106">有关 SDT 中受支持的 Surface 设备的列表，请参阅[部署适用于企业的 Surface 诊断工具包](surface-diagnostic-toolkit-business.md)。</span><span class="sxs-lookup"><span data-stu-id="172cb-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>

>[!NOTE]
><span data-ttu-id="172cb-107">若要使用命令运行 SDT，您必须登录到管理员帐户或登录到属于你的 Surface 设备上管理员组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="172cb-107">To run SDT using commands, you must be signed in to the Administrator account or signed in to an account that is a member of the Administrator group on your Surface device.</span></span>

## <span data-ttu-id="172cb-108">运行 SDT 应用控制台</span><span class="sxs-lookup"><span data-stu-id="172cb-108">Running SDT app console</span></span>

<span data-ttu-id="172cb-109">从 "[适用于 IT 的 Surface Tools" 下载页面](https://www.microsoft.com/download/details.aspx?id=46703)下载并安装 SDT 应用控制台。</span><span class="sxs-lookup"><span data-stu-id="172cb-109">Download and install SDT app console from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="172cb-110">你可以使用 Windows 命令提示符（cmd.exe）或 Windows PowerShell 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="172cb-110">You can use the Windows command prompt (cmd.exe) or Windows PowerShell to:</span></span> 

- <span data-ttu-id="172cb-111">收集所有日志文件。</span><span class="sxs-lookup"><span data-stu-id="172cb-111">Collect all log files.</span></span>
- <span data-ttu-id="172cb-112">使用最佳做法分析器运行运行状况诊断。</span><span class="sxs-lookup"><span data-stu-id="172cb-112">Run health diagnostics using Best Practice Analyzer.</span></span>
- <span data-ttu-id="172cb-113">检查更新缺少固件或驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="172cb-113">Check update for missing firmware or driver updates.</span></span>

>[!NOTE]
><span data-ttu-id="172cb-114">在此版本中，SDT 应用控制台仅支持单个命令。</span><span class="sxs-lookup"><span data-stu-id="172cb-114">In this release, the SDT app console supports single commands only.</span></span> <span data-ttu-id="172cb-115">运行多个命令行选项需要单独运行每个命令的控制台 exe。</span><span class="sxs-lookup"><span data-stu-id="172cb-115">Running multiple command line options requires running the console exe separately for each command.</span></span> 

<span data-ttu-id="172cb-116">默认情况下，输出文件将保存在与控制台应用相同的位置。</span><span class="sxs-lookup"><span data-stu-id="172cb-116">By default, output files are saved in the same location as the console app.</span></span> <span data-ttu-id="172cb-117">有关命令的完整列表，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="172cb-117">Refer to the following table for a complete list of commands.</span></span>

<span data-ttu-id="172cb-118">命令</span><span class="sxs-lookup"><span data-stu-id="172cb-118">Command</span></span> | <span data-ttu-id="172cb-119">注释</span><span class="sxs-lookup"><span data-stu-id="172cb-119">Notes</span></span>
--- | ---
<span data-ttu-id="172cb-120">-DataCollector "output file"</span><span class="sxs-lookup"><span data-stu-id="172cb-120">-DataCollector "output file"</span></span> | <span data-ttu-id="172cb-121">将系统详细信息收集到 zip 文件中。</span><span class="sxs-lookup"><span data-stu-id="172cb-121">Collects system details into a zip file.</span></span> <span data-ttu-id="172cb-122">"输出文件" 是创建系统详细信息 zip 文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="172cb-122">"output file" is the file path to create system details zip file.</span></span><br><br><span data-ttu-id="172cb-123">**示例**：</span><span class="sxs-lookup"><span data-stu-id="172cb-123">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
<span data-ttu-id="172cb-124">-bpa "输出文件"</span><span class="sxs-lookup"><span data-stu-id="172cb-124">-bpa "output file"</span></span> | <span data-ttu-id="172cb-125">检查设备中的多个设置和运行状况指示器。</span><span class="sxs-lookup"><span data-stu-id="172cb-125">Checks several settings and health indicators in the device.</span></span> <span data-ttu-id="172cb-126">"输出文件" 是创建 HTML 报表的文件路径。</span><span class="sxs-lookup"><span data-stu-id="172cb-126">“output file" is the file path to create the HTML report.</span></span><br><br><span data-ttu-id="172cb-127">**示例**：</span><span class="sxs-lookup"><span data-stu-id="172cb-127">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
<span data-ttu-id="172cb-128">-windowsupdate</span><span class="sxs-lookup"><span data-stu-id="172cb-128">-windowsupdate</span></span> | <span data-ttu-id="172cb-129">检查 Windows 更新联机服务器是否缺少固件和/或驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="172cb-129">Checks Windows Update online servers for missing firmware and/or driver updates.</span></span><br><br><span data-ttu-id="172cb-130">**示例**：</span><span class="sxs-lookup"><span data-stu-id="172cb-130">**Example**:</span></span><br><span data-ttu-id="172cb-131">Microsoft.Surface.Diagnostics.App.Console.exe-windowsupdate</span><span class="sxs-lookup"><span data-stu-id="172cb-131">Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate</span></span>
<span data-ttu-id="172cb-132">-保修 "输出文件"</span><span class="sxs-lookup"><span data-stu-id="172cb-132">-warranty "output file"</span></span> | <span data-ttu-id="172cb-133">检查设备上的保修信息（有效或无效）。</span><span class="sxs-lookup"><span data-stu-id="172cb-133">Checks warranty information on the device (valid or invalid).</span></span> <span data-ttu-id="172cb-134">可选的 "输出文件" 是创建 xml 文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="172cb-134">The optional “output file” is the file path to create the xml file.</span></span> <br><br><span data-ttu-id="172cb-135">**示例**：</span><span class="sxs-lookup"><span data-stu-id="172cb-135">**Example**:</span></span> <br><span data-ttu-id="172cb-136">Microsoft.Surface.Diagnostics.App.Console.exe-保修期 "warranty.xml"</span><span class="sxs-lookup"><span data-stu-id="172cb-136">Microsoft.Surface.Diagnostics.App.Console.exe –warranty “warranty.xml”</span></span>


>[!NOTE]
><span data-ttu-id="172cb-137">若要在目标设备上远程运行 SDT 应用控制台，可以使用配置管理工具，例如 Microsoft 终结点配置管理器。</span><span class="sxs-lookup"><span data-stu-id="172cb-137">To run the SDT app console remotely on target devices, you can use a configuration management tool such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="172cb-138">或者，你可以创建包含控制台应用和相应的控制台命令的 .zip 文件，并根据组织的软件分发过程进行部署。</span><span class="sxs-lookup"><span data-stu-id="172cb-138">Alternatively, you can create a .zip file containing the console app and appropriate console commands and deploy per your organization’s software distribution processes.</span></span> 

## <span data-ttu-id="172cb-139">运行最佳做法分析器</span><span class="sxs-lookup"><span data-stu-id="172cb-139">Running Best Practice Analyzer</span></span> 

<span data-ttu-id="172cb-140">你可以跨关键组件（如 BitLocker、安全启动和受信任的平台模块（TPM））运行 BPA 测试，然后将结果输出到可共享的文件。</span><span class="sxs-lookup"><span data-stu-id="172cb-140">You can run BPA tests across key components such as BitLocker, Secure Boot, and Trusted Platform Module (TPM) and then output the results to a shareable file.</span></span> <span data-ttu-id="172cb-141">该工具将生成一系列具有颜色编码的标题和条件描述符的表，以及有关如何解决该问题的指导。</span><span class="sxs-lookup"><span data-stu-id="172cb-141">The tool generates a series of tables with color-coded headings and condition descriptors along with guidance about how to approach resolving the issue.</span></span> 

- <span data-ttu-id="172cb-142">绿色表示该组件在最佳条件中运行（最佳）。</span><span class="sxs-lookup"><span data-stu-id="172cb-142">Green indicates the component is running in an optimal condition (optimal).</span></span>
- <span data-ttu-id="172cb-143">橙色表示组件未在最佳条件中运行（不是最佳情况）。</span><span class="sxs-lookup"><span data-stu-id="172cb-143">Orange indicates the component is not running in an optimal condition (not optimal).</span></span>
- <span data-ttu-id="172cb-144">红色表示组件处于不正常状态。</span><span class="sxs-lookup"><span data-stu-id="172cb-144">Red indicates the component is in an abnormal state.</span></span> 

### <span data-ttu-id="172cb-145">BPA 结果输出示例</span><span class="sxs-lookup"><span data-stu-id="172cb-145">Sample BPA results output</span></span>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-146">BitLocker</span><span class="sxs-lookup"><span data-stu-id="172cb-146">BitLocker</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-147">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-147">Description:</span></span></strong></td><td><span data-ttu-id="172cb-148">检查是否已在系统驱动器上启用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="172cb-148">Checks if BitLocker is enabled on the system drive.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-149">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-149">Value:</span></span></strong></td><td><span data-ttu-id="172cb-150">保护打开</span><span class="sxs-lookup"><span data-stu-id="172cb-150">Protection On</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-151">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-151">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-152">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-152">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-153">性</span><span class="sxs-lookup"><span data-stu-id="172cb-153">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-154">强烈建议启用 BitLocker 以保护你的数据。</span><span class="sxs-lookup"><span data-stu-id="172cb-154">It is highly recommended to enable BitLocker to protect your data.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-155">安全启动</span><span class="sxs-lookup"><span data-stu-id="172cb-155">Secure Boot</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-156">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-156">Description:</span></span></strong></td><td><span data-ttu-id="172cb-157">检查是否已启用安全启动。</span><span class="sxs-lookup"><span data-stu-id="172cb-157">Checks if Secure Boot is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-158">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-158">Value:</span></span></strong></td><td><span data-ttu-id="172cb-159">True</span><span class="sxs-lookup"><span data-stu-id="172cb-159">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-160">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-160">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-161">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-161">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-162">性</span><span class="sxs-lookup"><span data-stu-id="172cb-162">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-163">强烈建议启用安全启动以保护你的电脑。</span><span class="sxs-lookup"><span data-stu-id="172cb-163">It is highly recommended to enable Secure Boot to protect your PC.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-164">受信任的平台模块</span><span class="sxs-lookup"><span data-stu-id="172cb-164">Trusted Platform Module</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-165">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-165">Description:</span></span></strong></td><td><span data-ttu-id="172cb-166">确保 TPM 正常工作。</span><span class="sxs-lookup"><span data-stu-id="172cb-166">Ensures that the TPM is functional.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-167">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-167">Value:</span></span></strong></td><td><span data-ttu-id="172cb-168">True</span><span class="sxs-lookup"><span data-stu-id="172cb-168">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-169">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-169">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-170">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-170">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-171">性</span><span class="sxs-lookup"><span data-stu-id="172cb-171">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-172">如果没有功能的 TPM，则基于安全的功能（如 BitLocker）可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="172cb-172">Without a functional TPM, security-based functions such as BitLocker may not work properly.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-173">连接待机</span><span class="sxs-lookup"><span data-stu-id="172cb-173">Connected Standby</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-174">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-174">Description:</span></span></strong></td><td><span data-ttu-id="172cb-175">检查是否已启用 "连接待机"。</span><span class="sxs-lookup"><span data-stu-id="172cb-175">Checks if Connected Standby is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-176">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-176">Value:</span></span></strong></td><td><span data-ttu-id="172cb-177">True</span><span class="sxs-lookup"><span data-stu-id="172cb-177">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-178">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-178">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-179">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-179">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-180">性</span><span class="sxs-lookup"><span data-stu-id="172cb-180">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-181">已连接待机允许 Surface 设备在未使用的情况下接收更新和通知。</span><span class="sxs-lookup"><span data-stu-id="172cb-181">Connected Standby allows a Surface device to receive updates and notifications while not being used.</span></span> <span data-ttu-id="172cb-182">为了获得最佳体验，应启用连接待机。</span><span class="sxs-lookup"><span data-stu-id="172cb-182">For best experience, Connected Standby should be enabled.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-183">蓝牙</span><span class="sxs-lookup"><span data-stu-id="172cb-183">Bluetooth</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-184">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-184">Description:</span></span></strong></td><td><span data-ttu-id="172cb-185">检查是否已启用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="172cb-185">Checks if Bluetooth is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-186">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-186">Value:</span></span></strong></td><td><span data-ttu-id="172cb-187">启用</span><span class="sxs-lookup"><span data-stu-id="172cb-187">Enabled</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-188">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-188">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-189">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-189">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-190">性</span><span class="sxs-lookup"><span data-stu-id="172cb-190">Guidance:</span></span></strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-191">调试模式</span><span class="sxs-lookup"><span data-stu-id="172cb-191">Debug Mode</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-192">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-192">Description:</span></span></strong></td><td><span data-ttu-id="172cb-193">检查操作系统是否处于调试模式。</span><span class="sxs-lookup"><span data-stu-id="172cb-193">Checks if the operating system is in Debug mode.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-194">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-194">Value:</span></span></strong></td><td><span data-ttu-id="172cb-195">正常</span><span class="sxs-lookup"><span data-stu-id="172cb-195">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-196">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-196">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-197">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-197">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-198">性</span><span class="sxs-lookup"><span data-stu-id="172cb-198">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-199">调试启动选项启用或禁用 Windows 操作系统的内核调试。</span><span class="sxs-lookup"><span data-stu-id="172cb-199">The debug boot option enables or disables kernel debugging of the Windows operating system.</span></span> <span data-ttu-id="172cb-200">启用此选项可能会导致系统不稳定，并且可以阻止 DRM （数字权限 managemend）受保护的媒体播放。</span><span class="sxs-lookup"><span data-stu-id="172cb-200">Enabling this option can cause system instability and can prevent DRM (digital rights managemend) protected media from playing.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-201">测试签名</span><span class="sxs-lookup"><span data-stu-id="172cb-201">Test Signing</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-202">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-202">Description:</span></span></strong></td><td><span data-ttu-id="172cb-203">检查是否已启用测试签名。</span><span class="sxs-lookup"><span data-stu-id="172cb-203">Checks if Test Signing is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-204">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-204">Value:</span></span></strong></td><td><span data-ttu-id="172cb-205">正常</span><span class="sxs-lookup"><span data-stu-id="172cb-205">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-206">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-206">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-207">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-207">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-208">性</span><span class="sxs-lookup"><span data-stu-id="172cb-208">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-209">测试签名是 Windows 启动设置，只应用于测试预发布驱动程序。</span><span class="sxs-lookup"><span data-stu-id="172cb-209">Test Signing is a Windows startup setting that should only be used to test pre-release drivers.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-210">活动电源计划</span><span class="sxs-lookup"><span data-stu-id="172cb-210">Active Power Plan</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-211">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-211">Description:</span></span></strong></td><td><span data-ttu-id="172cb-212">检查正确的电源计划是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="172cb-212">Checks that the correct power plan is active.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-213">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-213">Value:</span></span></strong></td><td><span data-ttu-id="172cb-214">平衡</span><span class="sxs-lookup"><span data-stu-id="172cb-214">Balanced</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-215">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-215">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-216">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-216">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-217">性</span><span class="sxs-lookup"><span data-stu-id="172cb-217">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-218">强烈建议使用 "已平衡" 电源计划以最大限度地提高工作效率和电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="172cb-218">It is highly recommended to use the "Balanced" power plan to maximize productivity and battery life.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500"><span data-ttu-id="172cb-219">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="172cb-219">Windows Update</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-220">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-220">Description:</span></span></strong></td><td><span data-ttu-id="172cb-221">检查设备是否具有 Windows 更新的最新状态。</span><span class="sxs-lookup"><span data-stu-id="172cb-221">Checks if the device is up to date with Windows updates.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-222">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-222">Value:</span></span></strong></td><td><span data-ttu-id="172cb-223">Microsoft Silverlight （KB4023307），Windows Defender 防病毒的定义更新-KB2267602 （定义1.279.1433.0）</span><span class="sxs-lookup"><span data-stu-id="172cb-223">Microsoft Silverlight (KB4023307), Definition Update for Windows Defender Antivirus - KB2267602 (Definition 1.279.1433.0)</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-224">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-224">Condition:</span></span></strong></td><td><font color="ff9500"><span data-ttu-id="172cb-225">不优化</span><span class="sxs-lookup"><span data-stu-id="172cb-225">Not Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-226">性</span><span class="sxs-lookup"><span data-stu-id="172cb-226">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-227">更新到最新的 windows 可确保你在最新的固件和驱动程序上。</span><span class="sxs-lookup"><span data-stu-id="172cb-227">Updating to the latest windows makes sure you are on the latest firmware and drivers.</span></span> <span data-ttu-id="172cb-228">建议始终让你的设备保持最新状态</span><span class="sxs-lookup"><span data-stu-id="172cb-228">It is recommended to always keep your device up to date</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-229">可用硬盘空间</span><span class="sxs-lookup"><span data-stu-id="172cb-229">Free Hard Drive Space</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-230">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-230">Description:</span></span></strong></td><td><span data-ttu-id="172cb-231">检查是否有较少的可用硬盘空间。</span><span class="sxs-lookup"><span data-stu-id="172cb-231">Checks for low free hard drive space.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-232">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-232">Value:</span></span></strong></td><td><span data-ttu-id="172cb-233">66%</span><span class="sxs-lookup"><span data-stu-id="172cb-233">66%</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-234">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-234">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-235">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-235">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-236">性</span><span class="sxs-lookup"><span data-stu-id="172cb-236">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-237">为了获得最佳性能，你的硬盘的容量至少应为可用空间的10%。</span><span class="sxs-lookup"><span data-stu-id="172cb-237">For best performance, your hard drive should have at least 10% of its capacity as free space.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-238">非工作设备</span><span class="sxs-lookup"><span data-stu-id="172cb-238">Non-Functioning Devices</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-239">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-239">Description:</span></span></strong></td><td><span data-ttu-id="172cb-240">设备管理器中无法正常工作的设备列表。</span><span class="sxs-lookup"><span data-stu-id="172cb-240">List of non-functioning devices in Device Manager.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-241">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-241">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="172cb-242">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-242">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-243">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-243">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-244">性</span><span class="sxs-lookup"><span data-stu-id="172cb-244">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-245">设备管理器中的不起作用的设备可能会导致各种硬件组件的表面设备（但不限于）的不可预测问题。</span><span class="sxs-lookup"><span data-stu-id="172cb-245">Non-functioning devices in Device Manager may cause unpredictable problems with Surface devices such as, but not limited to, no power savings for the respective hardware component.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="172cb-246">外部监视器</span><span class="sxs-lookup"><span data-stu-id="172cb-246">External Monitor</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="172cb-247">描述：</span><span class="sxs-lookup"><span data-stu-id="172cb-247">Description:</span></span></strong></td><td><span data-ttu-id="172cb-248">检查可能存在兼容性问题的外部监视器。</span><span class="sxs-lookup"><span data-stu-id="172cb-248">Checks for an external monitor that may have compatibility issues.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="172cb-249">取值</span><span class="sxs-lookup"><span data-stu-id="172cb-249">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="172cb-250">符合</span><span class="sxs-lookup"><span data-stu-id="172cb-250">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="172cb-251">最佳</span><span class="sxs-lookup"><span data-stu-id="172cb-251">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="172cb-252">性</span><span class="sxs-lookup"><span data-stu-id="172cb-252">Guidance:</span></span></strong></td><td><span data-ttu-id="172cb-253">请与原始设备制造商联系，了解您的 Surface 设备是否兼容。</span><span class="sxs-lookup"><span data-stu-id="172cb-253">Check with the original equipment manufacturer for compatibility with your Surface device.</span></span></td></tr>
</table>

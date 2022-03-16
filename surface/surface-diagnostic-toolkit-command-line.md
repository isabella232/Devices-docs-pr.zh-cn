---
title: 使用适用于 Business 的 Surface Diagnostic Toolkit运行命令行应用控制台
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: bdd91df1f1ce105ecd19ea15e78bd9dc29d0ee95
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448465"
---
# <a name="run-command-line-app-console-with-surface-diagnostic-toolkit-for-business"></a>使用适用于 Business 的 Surface Diagnostic Toolkit运行命令行应用控制台

在命令提示Toolkit (运行 Surface Diagnostic) SDT 需要下载 SDT 应用控制台。 安装 SDT 后，可以通过 Windows 命令控制台 (cmd.exe) 或 Windows PowerShell（包括 PowerShell 集成脚本环境 (ISE) ）在命令提示符下运行 SDT，该环境支持自动完成命令、复制/粘贴和其他功能。  有关 SDT 中受支持的 Surface 设备的列表，请参阅[部署适用于Toolkit Surface 诊断设备](surface-diagnostic-toolkit-business.md)。

>[!NOTE]
>若要使用命令运行 SDT，必须登录到管理员帐户或登录到作为 Surface 设备上 Administrator 组的成员的帐户。

## <a name="running-sdt-app-console"></a>运行 SDT 应用控制台

1. 从 Surface [Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) 下载页面下载并安装 SDT 应用控制台。

- 对于 Intel/AMD 设备，请下载： **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0.exe**
- 对于ARM设备，请下载： **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0_x86.exe**

2. 使用 Windows命令提示符 (cmd.exe) 或 Windows PowerShell：

- 收集所有日志文件
- 使用最佳做法分析器运行运行状况诊断
- 检查缺少固件或驱动程序更新的更新

>[!NOTE]
>在此版本中，SDT 应用控制台仅支持单个命令。 运行多个命令行选项需要针对每个命令单独运行控制台 exe。

默认情况下，输出文件与控制台应用保存在同一位置。 有关命令的完整列表，请参阅下表。

命令 | 注释
--- | ---
-DataCollector "output file" | 将系统详细信息收集到 zip 文件中。 "output file"是创建系统详细信息 zip 文件的文件路径。<br><br>**示例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "output file" | 检查设备中的多个设置和运行状况指示器。 "output file"是创建 HTML 报告的文件路径。<br><br>**示例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | 检查Windows更新联机服务器，以检查缺少固件和/或驱动程序更新。<br><br>**示例**：<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-担保"输出文件" | 检查设备上有效或无效 (的担保) 。 可选"输出文件"是创建 xml 文件的文件路径。 <br><br>**示例**： <br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty "warranty.xml"

>[!NOTE]
>若要在目标设备上远程运行 SDT 应用控制台，可以使用配置管理工具（如 Microsoft Endpoint Configuration Manager）。 或者，你可以创建一个.zip文件，其中包含控制台应用和相应的控制台命令，并按组织的软件分发过程进行部署。

## <a name="running-best-practice-analyzer"></a>运行最佳做法分析器

你可以跨关键组件（如 BitLocker、安全启动和受信任的平台模块 (TPM) ）运行 BPA 测试，然后将结果输出到可共享的文件。 该工具生成一系列表，这些表包含颜色编码的标题和条件描述符，以及有关如何解决此问题的指导。

- 绿色表示组件在最佳条件下运行， (最佳) 。
- 橙色表示组件未在最佳条件下运行， (不是最佳) 。
- 红色表示组件为异常状态。

### <a name="sample-bpa-results-output"></a>示例 BPA 结果输出

<table>
<tr><th colspan="2">BitLocker</th></tr>
<tr><td><strong>描述：</strong></td><td>检查系统驱动器上是否启用了 BitLocker。</td></tr>
<tr><td><strong>值：</strong></td><td>保护打开</td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>强烈建议启用 BitLocker 来保护你的数据。</td></tr>
</table>

<table>
<tr><th colspan="2">安全启动</th></tr>
<tr><td><strong>描述：</strong></td><td>检查安全启动是否已启用。</td></tr>
<tr><td><strong>值：</strong></td><td>True</td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>强烈建议启用安全启动来保护你的电脑。</td></tr>
</table>

<table>
<tr><th colspan="2">受信任的平台模块</th></tr>
<tr><td><strong>描述：</strong></td><td>确保 TPM 正常工作。</td></tr>
<tr><td><strong>值：</strong></td><td>True</td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>如果没有功能 TPM，基于安全的函数（如 BitLocker）可能无法正常运行。</td></tr>
</table>

<table>
<tr><th colspan="2">连接待机</th></tr>
<tr><td><strong>描述：</strong></td><td>检查连接待机是否已启用。</td></tr>
<tr><td><strong>值：</strong></td><td>True</td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>连接待机允许 Surface 设备在未使用时接收更新和通知。 为了获得最佳体验，应启用连接待机。</td></tr>
</table>

<table>
<tr><th colspan="2">蓝牙</th></tr>
<tr><td><strong>描述：</strong></td><td>检查蓝牙是否已启用。</td></tr>
<tr><td><strong>值：</strong></td><td>已启用</td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2">调试模式</th></tr>
<tr><td><strong>描述：</strong></td><td>检查操作系统是否位于调试模式。</td></tr>
<tr><td><strong>值：</strong></td><td>正常</td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>调试启动选项启用或禁用操作系统的Windows调试。 启用此选项可能会导致系统不稳定，并可能阻止 DRM (受保护的媒体) 管理的数字权限。</td></tr>
</table>

<table>
<tr><th colspan="2">测试签名</th></tr>
<tr><td><strong>描述：</strong></td><td>检查测试签名是否已启用。</td></tr>
<tr><td><strong>值：</strong></td><td>正常</td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>测试签名是Windows启动设置，只能用于测试预发布驱动程序。</td></tr>
</table>

<table>
<tr><th colspan="2">活动电源计划</th></tr>
<tr><td><strong>描述：</strong></td><td>检查正确的电源计划是否处于活动状态。</td></tr>
<tr><td><strong>值：</strong></td><td>平衡</td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>强烈建议使用"平衡"电源计划以最大化生产效率和电池使用时间。</td></tr>
</table>

<table>
<tr><th colspan="2">Windows 更新</th></tr>
<tr><td><strong>描述：</strong></td><td>使用最新更新检查设备Windows更新。</td></tr>
<tr><td><strong>值：</strong></td><td>Microsoft Silverlight (KB4023307) ，Windows Defender 防病毒 定义更新 - KB2267602 (Definition 1.279.1433.0) </td></tr>
<tr><td><strong>条件：</strong></td><td>不是最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>更新到最新窗口，确保你使用最新的固件和驱动程序。 建议始终使设备保持最新</td></tr>
</table>

<table>
<tr><th colspan="2">可用硬盘空间</th></tr>
<tr><td><strong>描述：</strong></td><td>检查可用硬盘空间是否不足。</td></tr>
<tr><td><strong>值：</strong></td><td>66%</td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>为获得最佳性能，您的硬盘驱动器应至少具有其 10% 的容量作为可用空间。</td></tr>
</table>

<table>
<tr><th colspan="2">非正常运行的设备</th></tr>
<tr><td><strong>描述：</strong></td><td>设备管理器中未正常运行的设备列表。</td></tr>
<tr><td><strong>值：</strong></td><td></td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>设备管理器中的未正常运行的设备可能会导致 Surface 设备出现不可预知的问题，例如（但不限于）各自硬件组件的节能。</td></tr>
</table>

<table>
<tr><th colspan="2">外部监视器</th></tr>
<tr><td><strong>描述：</strong></td><td>检查可能具有兼容性问题的外部监视器。</td></tr>
<tr><td><strong>值：</strong></td><td></td></tr>
<tr><td><strong>条件：</strong></td><td>最佳</td></tr>
<tr><td><strong>指南：</strong></td><td>请与原始设备制造商联系，了解 Surface 设备的兼容性。</td></tr>
</table>

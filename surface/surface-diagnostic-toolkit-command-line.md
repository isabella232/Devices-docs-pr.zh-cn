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
# 使用命令运行适用于企业的 Surface 诊断工具包

在命令提示符Toolkit (Surface Diagnostic) SDT 应用需要下载 SDT 应用控制台。 安装 SDT 后，可以通过 Windows 命令控制台 (cmd.exe) 或 Windows PowerShell（包括 PowerShell 集成脚本环境 (ISE) ）在命令提示符下运行 SDT，它支持自动完成命令、复制/粘贴和其他功能。  有关 SDT 中受支持的 Surface 设备的列表，请参阅部署 [适用于Toolkit Surface 诊断设备](surface-diagnostic-toolkit-business.md)。

>[!NOTE]
>若要使用命令运行 SDT，必须登录到管理员帐户或登录到作为 Surface 设备上 Administrator 组的成员的帐户。

##  <a name="running-sdt-app-console"></a>运行 SDT 应用控制台

从 Surface Tools for IT 下载页面下载并安装 SDT [应用控制台](https://www.microsoft.com/download/details.aspx?id=46703)。 可以使用 Windows 命令提示符 (cmd.exe) 或Windows PowerShell： 

- 收集所有日志文件。
- 使用最佳做法分析器运行运行状况诊断。
- 检查更新中缺少固件或驱动程序更新。

>[!NOTE]
>在此版本中，SDT 应用控制台仅支持单个命令。 运行多个命令行选项需要单独运行每个命令的控制台 exe。 

默认情况下，输出文件与控制台应用保存在同一位置。 有关命令的完整列表，请参阅下表。

命令 | 注释
--- | ---
-DataCollector "output file" | 将系统详细信息收集到 zip 文件中。 "输出文件"是创建系统详细信息 zip 文件的文件路径。<br><br>**示例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "output file" | 检查设备中的多个设置和运行状况指示器。 "输出文件"是创建 HTML 报表的文件路径。<br><br>**示例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | 检查 Windows 更新联机服务器是否缺少固件和/或驱动程序更新。<br><br>**示例**：<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-担保"输出文件" | 检查设备上的担保信息 (有效或无效) 。 可选"输出文件"是创建 xml 文件的文件路径。 <br><br>**示例**： <br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty "warranty.xml"


>[!NOTE]
>若要在目标设备上远程运行 SDT 应用控制台，可以使用 Microsoft Endpoint Configuration Manager 等配置管理工具。 或者，您可以创建一个包含控制台应用和相应控制台命令的 .zip 文件，并按组织的软件分发过程进行部署。 

##  <a name="running-best-practice-analyzer"></a>运行最佳做法分析器 

你可以跨关键组件（如 BitLocker、安全启动和受信任的平台模块 (TPM) ）运行 BPA 测试，然后将结果输出到可共享的文件。 该工具生成一系列表，这些表格包含颜色编码的标题和条件描述符，以及有关如何解决该问题的指导。 

- 绿色表示组件在最佳条件下运行， (最佳) 。
- 橙色表示组件未在最佳条件下运行， (运行) 。
- 红色表示组件状态异常。 

###  <a name="sample-bpa-results-output"></a>示例 BPA 结果输出

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查系统驱动器上是否启用了 BitLocker。</td></tr>
<tr><td><strong>值：</strong></td><td>保护打开</td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>强烈建议启用 BitLocker 来保护你的数据。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">安全启动</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查安全启动是否已启用。</td></tr>
<tr><td><strong>值：</strong></td><td>True</td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>强烈建议启用安全启动来保护电脑。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">受信任的平台模块</font></th></tr>
<tr><td><strong>描述：</strong></td><td>确保 TPM 正常工作。</td></tr>
<tr><td><strong>值：</strong></td><td>True</td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>如果没有功能 TPM，基于安全性的函数（如 BitLocker）可能无法正常运行。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">连接待机</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查连接待机是否已启用。</td></tr>
<tr><td><strong>值：</strong></td><td>True</td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>连接待机允许 Surface 设备在未使用时接收更新和通知。 为了获得最佳体验，应启用连接待机。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">蓝牙</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查Bluetooth是否已启用。</td></tr>
<tr><td><strong>值：</strong></td><td>启用</td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">调试模式</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查操作系统是否位于调试模式。</td></tr>
<tr><td><strong>值：</strong></td><td>正常</td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>调试启动选项启用或禁用 Windows 操作系统的内核调试。 启用此选项可能会导致系统不稳定，并可能阻止 DRM (受保护媒体) 管理方式的 DRM。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">测试签名</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查测试签名是否已启用。</td></tr>
<tr><td><strong>值：</strong></td><td>正常</td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>测试签名是一种 Windows 启动设置，只能用于测试预发布驱动程序。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">活动电源计划</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查正确的电源计划是否处于活动状态。</td></tr>
<tr><td><strong>值：</strong></td><td>平衡</td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>强烈建议使用"平衡"电源计划，以最大限度地提高工作效率和电池使用时间。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows 更新</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查设备是否随 Windows 更新一起更新。</td></tr>
<tr><td><strong>值：</strong></td><td>Microsoft Silverlight (KB4023307) ，Windows Defender 防病毒的定义更新 - KB2267602 (定义 1.279.1433.0) </td></tr>
<tr><td><strong>条件：</strong></td><td><font color="ff9500">不是最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>更新到最新窗口，确保你使用最新的固件和驱动程序。 建议始终使设备保持最新</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">免费硬盘空间</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查可用硬盘空间是否不足。</td></tr>
<tr><td><strong>值：</strong></td><td>66%</td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>为获得最佳性能，硬盘应至少有 10% 的容量作为可用空间。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">无法正常工作的设备</font></th></tr>
<tr><td><strong>描述：</strong></td><td>设备管理器中无法正常工作的设备列表。</td></tr>
<tr><td><strong>值：</strong></td><td></td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>设备管理器中无法正常工作的设备可能会导致 Surface 设备出现不可预知的问题，例如（但不限于）各自硬件组件的节电。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">外部监视器</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查可能具有兼容性问题的外部监视器。</td></tr>
<tr><td><strong>值：</strong></td><td></td></tr>
<tr><td><strong>条件：</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>指南：</strong></td><td>请与原始设备制造商核实与 Surface 设备的兼容性。</td></tr>
</table>

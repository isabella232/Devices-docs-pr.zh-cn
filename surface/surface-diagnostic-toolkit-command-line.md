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
# 使用命令运行适用于企业的 Surface 诊断工具包

在命令提示符处运行 Surface 诊断工具包（SDT）需要下载 STD 应用控制台。 安装完成后，你可以通过 Windows 命令控制台（cmd.exe）或使用 Windows PowerShell （包括 PowerShell 集成脚本环境（ISE））在命令提示符处运行 SDT，它提供了支持命令、复制/粘贴和其他功能的自动完成功能的支持。  有关 SDT 中受支持的 Surface 设备的列表，请参阅[部署适用于企业的 Surface 诊断工具包](surface-diagnostic-toolkit-business.md)。

>[!NOTE]
>若要使用命令运行 SDT，您必须登录到管理员帐户或登录到属于你的 Surface 设备上管理员组成员的帐户。

## 运行 SDT 应用控制台

从 "[适用于 IT 的 Surface Tools" 下载页面](https://www.microsoft.com/download/details.aspx?id=46703)下载并安装 SDT 应用控制台。 你可以使用 Windows 命令提示符（cmd.exe）或 Windows PowerShell 执行以下操作： 

- 收集所有日志文件。
- 使用最佳做法分析器运行运行状况诊断。
- 检查更新缺少固件或驱动程序更新。

>[!NOTE]
>在此版本中，SDT 应用控制台仅支持单个命令。 运行多个命令行选项需要单独运行每个命令的控制台 exe。 

默认情况下，输出文件将保存在与控制台应用相同的位置。 有关命令的完整列表，请参阅下表。

命令 | 注释
--- | ---
-DataCollector "output file" | 将系统详细信息收集到 zip 文件中。 "输出文件" 是创建系统详细信息 zip 文件的文件路径。<br><br>**示例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "输出文件" | 检查设备中的多个设置和运行状况指示器。 "输出文件" 是创建 HTML 报表的文件路径。<br><br>**示例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | 检查 Windows 更新联机服务器是否缺少固件和/或驱动程序更新。<br><br>**示例**：<br>Microsoft.Surface.Diagnostics.App.Console.exe-windowsupdate
-保修 "输出文件" | 检查设备上的保修信息（有效或无效）。 可选的 "输出文件" 是创建 xml 文件的文件路径。 <br><br>**示例**： <br>Microsoft.Surface.Diagnostics.App.Console.exe-保修期 "warranty.xml"


>[!NOTE]
>若要在目标设备上远程运行 SDT 应用控制台，可以使用配置管理工具，例如 Microsoft 终结点配置管理器。 或者，你可以创建包含控制台应用和相应的控制台命令的 .zip 文件，并根据组织的软件分发过程进行部署。 

## 运行最佳做法分析器 

你可以跨关键组件（如 BitLocker、安全启动和受信任的平台模块（TPM））运行 BPA 测试，然后将结果输出到可共享的文件。 该工具将生成一系列具有颜色编码的标题和条件描述符的表，以及有关如何解决该问题的指导。 

- 绿色表示该组件在最佳条件中运行（最佳）。
- 橙色表示组件未在最佳条件中运行（不是最佳情况）。
- 红色表示组件处于不正常状态。 

### BPA 结果输出示例

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查是否已在系统驱动器上启用 BitLocker。</td></tr>
<tr><td><strong>取值</strong></td><td>保护打开</td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>强烈建议启用 BitLocker 以保护你的数据。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">安全启动</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查是否已启用安全启动。</td></tr>
<tr><td><strong>取值</strong></td><td>True</td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>强烈建议启用安全启动以保护你的电脑。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">受信任的平台模块</font></th></tr>
<tr><td><strong>描述：</strong></td><td>确保 TPM 正常工作。</td></tr>
<tr><td><strong>取值</strong></td><td>True</td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>如果没有功能的 TPM，则基于安全的功能（如 BitLocker）可能无法正常工作。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">连接待机</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查是否已启用 "连接待机"。</td></tr>
<tr><td><strong>取值</strong></td><td>True</td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>已连接待机允许 Surface 设备在未使用的情况下接收更新和通知。 为了获得最佳体验，应启用连接待机。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">蓝牙</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查是否已启用蓝牙。</td></tr>
<tr><td><strong>取值</strong></td><td>启用</td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">调试模式</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查操作系统是否处于调试模式。</td></tr>
<tr><td><strong>取值</strong></td><td>正常</td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>调试启动选项启用或禁用 Windows 操作系统的内核调试。 启用此选项可能会导致系统不稳定，并且可以阻止 DRM （数字权限 managemend）受保护的媒体播放。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">测试签名</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查是否已启用测试签名。</td></tr>
<tr><td><strong>取值</strong></td><td>正常</td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>测试签名是 Windows 启动设置，只应用于测试预发布驱动程序。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">活动电源计划</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查正确的电源计划是否处于活动状态。</td></tr>
<tr><td><strong>取值</strong></td><td>平衡</td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>强烈建议使用 "已平衡" 电源计划以最大限度地提高工作效率和电池使用时间。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows 更新</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查设备是否具有 Windows 更新的最新状态。</td></tr>
<tr><td><strong>取值</strong></td><td>Microsoft Silverlight （KB4023307），Windows Defender 防病毒的定义更新-KB2267602 （定义1.279.1433.0）</td></tr>
<tr><td><strong>符合</strong></td><td><font color="ff9500">不优化</font></td></tr>
<tr><td><strong>性</strong></td><td>更新到最新的 windows 可确保你在最新的固件和驱动程序上。 建议始终让你的设备保持最新状态</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">可用硬盘空间</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查是否有较少的可用硬盘空间。</td></tr>
<tr><td><strong>取值</strong></td><td>66%</td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>为了获得最佳性能，你的硬盘的容量至少应为可用空间的10%。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">非工作设备</font></th></tr>
<tr><td><strong>描述：</strong></td><td>设备管理器中无法正常工作的设备列表。</td></tr>
<tr><td><strong>取值</strong></td><td></td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>设备管理器中的不起作用的设备可能会导致各种硬件组件的表面设备（但不限于）的不可预测问题。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">外部监视器</font></th></tr>
<tr><td><strong>描述：</strong></td><td>检查可能存在兼容性问题的外部监视器。</td></tr>
<tr><td><strong>取值</strong></td><td></td></tr>
<tr><td><strong>符合</strong></td><td><font color="00ff00">最佳</font></td></tr>
<tr><td><strong>性</strong></td><td>请与原始设备制造商联系，了解您的 Surface 设备是否兼容。</td></tr>
</table>

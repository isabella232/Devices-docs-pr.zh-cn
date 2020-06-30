---
title: 连接其他设备并使用 Surface Hub 显示
description: 你可以将其他设备连接到 Surface Hub 来显示内容。
ms.assetid: 8BB80FA3-D364-4A90-B72B-65F0F0FC1F0D
ms.reviewer: ''
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 2d8d814d5e33a878fab066321a0d7800ae5104c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832079"
---
# 连接其他设备并使用 Surface Hub 显示


你可以将其他设备连接到 Microsoft Surface Hub 来显示内容。 本主题介绍了通过有线连接可用的来宾模式、替换电脑模式和视频输出功能，并列出了你可使用[蓝牙](#bluetooth-accessories)连接到 Surface Hub 的外部设备。

>[!NOTE]
>Surface Hub 将使用您选择的视频输入，直到建立新连接、现有连接中断或连接应用关闭。

## 我应该选择哪一种方法？

将外部设备和屏幕连接到 Surface Hub 时，有几个可用选项。 根据你的方案和需求，确定要使用的方法。 

| 所需操作： | 使用此方法： |
| --- | --- |
| 在另一台设备上镜像 Surface Hub 的屏幕。 | [视频输出](#video-out) |
| 在 Surface Hub 屏幕上显示另一台设备的屏幕，并同时与该设备的内容和内置 Surface Hub 体验交互。 | [来宾模式](#guest-mode) |
| 通过外部 Windows 10 电脑使用 Surface Hub，关闭 Surface Hub 的嵌入计算机。 除了笔和触摸，还可向外部电脑发送相机、麦克风、扬声器和其他外设。 | [替换电脑模式](#replacement-pc-mode) |


## 来宾模式


来宾模式使用有线连接，因此用户可将其设备中的内容显示到 Surface Hub。 如果源设备基于 Windows，则该设备还提供 Touchback 和 Inkback。 Surface Hub 的内部电脑提取连接设备中的视频和音频，并将它们显示在 Surface Hub 上。 如果 Surface Hub 遇到高带宽数字内容保护（HDCP）信号，则源将显示为黑色图像。 若要在不违反 HDCP 要求情况下显示内容，请使用 Surface Hub 右侧的小键盘直接选择外部源。

>[!NOTE]
>当连接 HDCP 源时，使用侧键盘更改源输入。

### 端口

针对来宾模式使用 Surface Hub 上的这些端口。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>接口</th>
<th>类型</th>
<th>说明</th>
<th>功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>显示端口 1.1a</p></td>
<td><p>视频输入</p></td>
<td><p>来宾输入 #1</p></td>
<td><ul>
<li><p>支持带有来宾输入 #2 和来宾输入 #3 的同时来宾输入显示（一个全屏，两个缩略图）。</p></li>
<li><p>在绕过模式中符合 HDCP 标准</p></li>
<li><p>Touchback 已启用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>HDMI 1.4</p></td>
<td><p>视频输入</p></td>
<td><p>来宾输入 #2</p></td>
<td><ul>
<li><p>支持带有来宾输入 #1 和来宾输入 #3 的同时来宾输入显示（一个全屏，两个缩略图）。</p></li>
<li><p>在绕过模式中符合 HDCP 标准</p></li>
<li><p>Touchback 已启用</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>VGA</p></td>
<td><p>视频输入</p></td>
<td><p>来宾输入 #3</p></td>
<td><ul>
<li><p>支持带有来宾输入 #1 和来宾输入 #2 的同时来宾输入显示（一个全屏，两个缩略图）。</p></li>
<li><p>在绕过模式中符合 HDCP 标准</p></li>
<li><p>Touchback 已启用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>3.5 毫米插孔</p></td>
<td><p>音频输入</p></td>
<td><p>模拟音频输入</p></td>
<td><ul>
<li><p>插入 Surface Hub 电脑，通常使用 VGA 视频输入。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 2.0，类型 B</p></td>
<td><p>USB 输出</p></td>
<td><p>Touchback</p></td>
<td><ul>
<li><p>提供对来宾电脑的 HID 输入设备鼠标、触摸、键盘和触笔的访问权限。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### 端口位置

这些是在 55 英寸和 84 英寸 Surface Hub 上用于来宾模式的端口连接。

![显示 55 英寸 Surface Hub 上的来宾端口的图像。](images/sh-55-guest-ports.png)

55 英寸 Surface Hub 上的有线端口连接

![显示 84 英寸 Surface Hub 上的来宾端口的图像。](images/sh-84-guest-ports.png)

84 英寸 Surface Hub 上的有线端口连接

### 端口枚举

当 Surface Hub 通过有线连接 USB 端口连接到来宾计算机时，会发现并配置多台 USB 设备。 这些外围设备针对 Touchback 和 Inkback 创建。 可以在设备管理器中查看外围设备。 设备管理器将显示某些设备的重复名称。

**人机接口设备**

-   符合 HID 标准的消费者控制设备

-   符合 HID 标准的笔

-   符合 HID 标准的笔（重复项）

-   符合 HID 标准的笔（重复项）

-   符合 HID 标准的触摸屏

-   USB 输入设备

-   USB 输入设备（重复项）

**键盘**

-   标准 PS/2 键盘

**鼠标和其他指针设备**

-   符合 HID 标准的鼠标

**通用串行总线控制器**

-   通用 USB 集线器

-   USB 复合设备

### 来宾模式连接

你对视频电缆的选择取决于源输入的可用电缆。 Surface Hub 有三种视频输入选择：DisplayPort、HDMI 和 VGA。 请参见下图中的可用分辨率。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th>信号类型</th>
<th>分辨率</th>
<th>帧速率</th>
<th>HDMI - RGB</th>
<th>DisplayPort</th>
<th>VGA</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PC</p></td>
<td><p>640 x 480</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>PC</p></td>
<td><p>720 x 480</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>PC</p></td>
<td><p>1024 x 768</p></td>
<td><p>60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>HDTV</p></td>
<td><p>720p</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>HDTV</p></td>
<td><p>1080p</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>

 

源音频由 DisplayPort 和 HDMI 电缆提供。 如果你必须使用 VGA，则 Surface Hub 具有使用 3.5 毫米插头的音频输入端口。 Surface Hub 还使用 USB 电缆，该电缆提供从 Surface Hub 到兼容 Windows 10 设备的 Touchback 和 Inkback。 USB 电缆可与已经使用电缆连接的任何视频输入结合使用。

使用来宾模式连接电脑的用户会使用以下选项之一：

**DisplayPort** -- DisplayPort 电缆和 USB 2.0 电缆

**HDMI** -- HDMI电缆和 USB 2.0 电缆

**VGA** -- VGA 电缆、3.5 毫米音频电缆和 USB 2.0 电缆

如果你为来宾模式使用的计算机与 Touchback 和 Inkback 不兼容，则你不需要 USB 电缆。

## 替换电脑模式


在替换电脑模式中，Surface Hub 的嵌入计算机处于关闭状态，而将一台外部电脑连接到 Surface Hub。 连接到替换电脑端口可访问 Surface Hub 上的关键外设，包括屏幕、笔和触摸功能。 这意味着你的 Surface Hub 不会获得 Windows 团队体验的优势，但你将拥有提供和管理你自己的 Windows 计算机所提供的灵活性。

### 软件要求

你可以在 64 位版本的 Windows 10 家庭版、Windows 10 专业版和 Windows 10 企业版中在替换电脑模式下运行 Surface Hub。 你可以从 Microsoft 下载中心下载 [Surface Hub 替换电脑驱动程序包](https://www.microsoft.com/download/details.aspx?id=52210)。 我们建议在任何计划用作替换电脑的计算机上安装这些驱动程序。

### 硬件要求

Surface Hub 与多种硬件兼容。 为你的替换电脑选择处理器和内存确认，以便它支持你将使用的程序。 你的替换电脑硬件需要支持 64 位版本的 Windows 10。

### 图形适配器

在替换电脑模式下，Surface Hub 支持可生成 DisplayPort 信号的任何图形适配器。 通过可与 Surface Hub 的分辨率和刷新率匹配的图形适配器，你将改进你的体验。 例如，Surface Hub 上的最佳和推荐替换电脑体验是采用 120Hz 视频信号。

**55 英寸 Surface Hubs** - 为了获得最佳体验，请使用支持 120Hz 的 1080p 分辨率的显卡。

**84 英寸 Surface Hub** - 为了获得最佳体验，请使用支持输出四个 DisplayPort 1.2 流的显卡以生成 120Hz 的 2160p（120Hz 垂直刷新的 3840 x 2160）。 我们已验证，这适用于 NVIDIA Quadro K2200、NVIDIA Quadro K4200、NVIDIA Quadro M6000、AMD FirePro W5100、AMD FirePro W7100 和 AMD FirePro W9100。 这些不是唯一的显卡，来自其他供应商的显卡也可用。 

请直接咨询显卡供应商以获取最新的驱动程序。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>显卡供应商</th>
<th>驱动程序下载页面</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NVIDIA</p></td>
<td><p><a href="http://nvidia.com/Download/index.aspx" data-raw-source="[http://nvidia.com/Download/index.aspx](http://nvidia.com/Download/index.aspx)">http://nvidia.com/Download/index.aspx</a></p></td>
</tr>
<tr class="even">
<td><p>AMD</p></td>
<td><p><a href="http://support.amd.com/en-us/download" data-raw-source="[http://support.amd.com/en-us/download](http://support.amd.com/en-us/download)">http://support.amd.com/en-us/download</a></p></td>
</tr>
<tr class="odd">
<td><p>Intel</p></td>
<td><p><a href="https://downloadcenter.intel.com/" data-raw-source="[https://downloadcenter.intel.com/](https://downloadcenter.intel.com/)">https://downloadcenter.intel.com/</a></p></td>
</tr>
</tbody>
</table>

 

### 端口

55 英寸 Surface Hub 上的替换电脑端口

![显示 55 英寸 Surface Hub 上的替换电脑端口的图像。](images/sh-55-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>类型</th>
<th>接口</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>电脑视频</p></td>
<td><p>视频输入</p></td>
<td><p>DP 1.2</p></td>
<td><ul>
<li><p>120 Hz 的 1080p 的全屏显示，带有音频</p></li>
<li><p>符合 HDCP 的标准</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>内部外设</p></td>
<td><p>USB 输出</p></td>
<td><p>USB 2.0 类型 B</p></td>
<td><ul>
<li><p>触摸</p></li>
<li><p>笔</p></li>
<li><p>扬声器</p></li>
<li><p>麦克风</p></li>
<li><p>相机</p></li>
<li><p>NFC 传感器</p></li>
<li><p>环境光传感器</p></li>
<li><p>被动红外传感器</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 集线器</p></td>
<td><p>USB 输出</p></td>
<td><p>USB 2.0 类型 B</p></td>
<td><ul>
<li><p>底部 USB 端口</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

84 英寸 Surface Hub 上的替换电脑端口

![显示 84 英寸 Surface Hub 上的替换电脑端口的图像。](images/sh-84-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>类型</th>
<th>接口</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>电脑视频</p></td>
<td><p>视频输入</p></td>
<td><p>DP 1.2 (2x)</p></td>
<td><ul>
<li><p>120 Hz 的 2160p 的全屏显示，带有音频</p></li>
<li><p>符合 HDCP 的标准</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>内部外设</p></td>
<td><p>USB 输出</p></td>
<td><p>USB 2.0 类型 B</p></td>
<td><ul>
<li><p>触摸</p></li>
<li><p>笔</p></li>
<li><p>扬声器</p></li>
<li><p>麦克风</p></li>
<li><p>相机</p></li>
<li><p>NFC 传感器</p></li>
<li><p>环境光传感器</p></li>
<li><p>被动红外传感器</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 集线器</p></td>
<td><p>USB 输出</p></td>
<td><p>USB 2.0 类型 B</p></td>
<td><ul>
<li><p>底部 USB 端口</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### 替换电脑设置说明

**使用替换电脑模式**

1.  在替换电脑上下载并安装 [Surface Hub 替换电脑驱动程序包](https://www.microsoft.com/download/details.aspx?id=52210)。

    >[!NOTE]
    >我们建议你在替换电脑上设置睡眠或休眠，以便 Surface Hub 在不使用时关闭屏幕。

2.  使用电源电缆旁边的电源开关关闭 Surface Hub。

3.  将电缆从 Surface Hub 的替换电脑端口连接到替换电脑。 这些端口通常被可移动的塑料盖覆盖。

    55 英寸 Surface Hub -- 连接一根 DisplayPort 电缆和两根 USB 电缆。

    84 英寸 Surface Hub -- 连接两根 DisplayPort 电缆和两根 USB 电缆。

4.  将模式开关切换到**替换电脑**。 模式开关在替换电脑端口旁边。

5.  使用电源电缆旁边的电源开关打开 Surface Hub。

6.  按下 Surface Hub 右侧的电源按钮。

可以切换 Surface Hub 以使用内部电脑。

**切换回内部电脑**

1.  使用电源电缆旁边的电源开关关闭 Surface Hub。

2.  将模式开关切换到内部电脑。 模式开关在替换电脑端口旁边。

3.  使用电源电缆旁边的电源开关打开 Surface Hub。

 
## 视频输出
 
Surface Hub 包括视频输出端口，用于将可视内容从 Surface Hub 镜像到其他屏幕。

### 端口

55 英寸 Surface Hub 上的视频输出端口

![视频输出端口图示](images/video-out-55.png)

84 英寸 Surface Hub 上的视频输出端口

![视频输出端口图示](images/video-out-84.png)

<table>
<thead>
<tr class="header">
<th>描述</th>
<th>类型</th>
<th>接口</th>
<th>功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>视频输出镜像</p></td>
<td><p>视频输出</p></td>
<td><p>视频输出</p></td>
<td><ul>
<li><p>支持连接到标准 DisplayPort 监视器（仅支持显示 24bpp 的 1080p60 分辨率的 x4 Link）</p></li>
<li><p>支持通过 DisplayPort-to-HDMI 适配器与 HDMI 监视器（支持 1080p60）结合使用</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 电缆

对 55 英寸和 84 英寸 Surface Hub 设备进行了测试，可与已认证的 DisplayPort 和 HDMI 电缆一起使用。  尽管供应商确实会销售可适用于 Surface Hub 的较长电缆，但是只有经实验室认证的电缆才能确定用于 Hub。 例如，经认证的 DisplayPort 电缆最长为 3 米，但是许多供应商销售的电缆可达这一长度的 3 倍。 如有需要使用长电缆，我们强烈建议使用 HDMI。  对于长程电缆，HDMI 有多种经济高效的解决方案，包括使用中继器。 如果检测到 HDMI 接收器，则几乎每个 DisplayPort 源都能自动切换到 HDMI 信号。


## 蓝牙外部设备

你可以使用蓝牙将以下外部设备连接到 Surface Hub：

- 鼠标
- 键盘
- 耳机
- 扬声器

>[!NOTE]
>连接蓝牙耳机或扬声器后，你可能需要更改[默认麦克风和扬声器设置](local-management-surface-hub-settings.md)。

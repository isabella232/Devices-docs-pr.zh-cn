---
title: 将设备连接到 Surface Hub 2S
description: 此页面介绍如何将外部设备连接到 Surface Hub 2。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/24/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1c4f9b4a74b50edb5587185f28a18163a02d62f9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831599"
---
# 将设备连接到 Surface Hub 2S
Surface Hub 2 使你能够连接外部设备、将 Surface Hub 2 的显示镜像到另一台设备，以及连接多个第三方外围设备，包括视频会议相机、电话会议和房间系统设备。

你可以将设备中的内容显示到 Surface Hub 2。 如果源设备是基于 Windows 的，则该设备还可以提供 TouchBack 和 InkBack，它从已连接的设备获取视频和音频，并将其显示在 Surface Hub 2。 如果 Surface Hub 2 遇到高带宽数字内容保护（HDCP）信号（如蓝光 DVD 播放器），源将显示为黑色图像。

> [!NOTE]
> Surface Hub 2 使用选择的视频输入，直到建立新连接、现有连接中断或连接应用关闭。

## 推荐的有线配置 

通常情况下，建议尽可能使用本机电缆连接（如 USB-C 至 USB-C）或 HDMI 到 HDMI。 其他组合，如 MiniDP 到 HDMI 或 MiniDP 到 USB-C 也会正常工作。 如本页所述，可能需要一些其他配置来优化视频输出体验。

| **左侧的“连接”** | **功能** | **描述**|
| --- | --- | ---|
| HDMI + USB-C | 用于音频和视频的 HDMI<br><br>TouchBack 和 InkBack 的 USB-C | USB-C 支持使用 HDMI A/V 连接的 TouchBack 和 InkBack。<br><br>将 USB-C 连接到 USB-A 连接到旧式计算机。<br><br>**注意：** 为获得最佳效果，请在连接 USB 数据线之前连接 HDMI。 如果您使用的是用于 HDMI 的计算机与 TouchBack 和 InkBack 不兼容，则不需要使用 USB-C 线。 |
| USB-C <br> （通过计算模块） | 视频-入 <br>音频 | A/V 需要单线缆<br><br>支持 TouchBack 和 InkBack<br><br>HDCP 已启用 |
| HDMI （在端口中） | 视频，音频进入 Surface Hub 2 | A/V 需要单线缆<br><br>不支持 TouchBack 和 InkBack<br><br>HDCP 已启用 |
| MiniDP 1.2 输出 | 视频输出，如镜像到更大的投影仪。 | A/V 需要单线缆 |

通过 USB-C 端口将来宾计算机连接到 Surface Hub 2 时，将发现并配置多个 USB 设备。 这些外围设备是为 TouchBack 和 InkBack 创建的。 如下表所示，外围设备可在 "设备管理器" 中查看，这将显示某些设备的重复名称，如下表所示。

 
|**外设**| **设备管理器中的列表** |
| ---------------------------- |------------- | ------------------------------|
| 人机接口设备 | 符合 HID 标准的消费者控制设备<br>符合 HID 标准的笔<br>符合 HID 标准的笔（重复项）<br>符合 HID 标准的笔（重复项）<br>符合 HID 标准的触摸屏<br>USB 输入设备<br>USB 输入设备（重复项） |
| 键盘 | 标准 PS/2 键盘 |
| 鼠标和其他指针设备 | 符合 HID 标准的鼠标 |
| USB 控制器 | 通用 USB 集线器<br>USB 复合设备 |

## 将视频连接到 Surface Hub 2

你可以使用 USB-C 或 HDMI 输入 Surface Hub 2 的视频，如下表所示。  

### Surface Hub 2/秒视频入设置

| **信号类型** | **分辨率** | **帧速率** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| 电脑              | 640 x 480      | 60             | X        | X         |
| PC              | 720 x 480      | 60             | X        | X         |
| PC              | 1024 x 768     | 60             | X        | X         |
| PC              | 1920 x 1080    | 60             | X        | X         |
| PC              | 3840x2560      | 大约             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 大约             | X        | X         |

> [!NOTE]
> 仅当连接到计算模块上的端口时，才支持 4K UHD 分辨率（3840×2560）。 在设备左侧、顶部和右侧的 "来宾" USB 端口上不支持该功能。

> [!NOTE]
> 当 Surface Hub 2 上显示时，连接的外部电脑上的视频可能会变得更小。

## 镜像 Surface Hub 2 秒显示在另一个设备上

你可以使用 MiniDP 将视频输出到另一个显示器，如下表所示。

### Surface Hub 2 视频输出设置

| **信号类型** | **分辨率** | **帧速率** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| 电脑              | 640 x 480      | 60             | X          |
| PC              | 720 x 480      | 60             | X          |
| PC              | 1024 x 768     | 60             | X          |
| PC              | 1920 x 1080    | 60             | X          |
| PC              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4K UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 2 包含一个 MiniDP 视频输出端口，用于将 Surface Hub 2 的可视内容投影到另一个显示器。 如果你计划使用 Surface Hub 2 到另一个显示器，请注意以下建议：

- **需要键盘。** 开始之前，您需要将支持有线或支持蓝牙的外部键盘连接到 Surface Hub 2。 请注意，与原始 Surface Hub 不同，Surface Hub 2 的键盘是单独销售的，不包含在装运包中。<br><br>
- **设置重复模式。** Surface Hub 2 仅支持在重复模式下视频输出。 但是，当您首次连接时，您仍需要手动配置显示模式：
    1. 输入**Windows 徽标键**  +  **P**，该参数将在 Surface Hub 2 的右侧打开 "项目" 窗格，然后选择 "**复制**模式"。
    2. 完成 Surface Hub 2 会话后，选择 "**结束会话**"。 这可确保为下一个会话保存 "重复" 设置。<br><br>
- **规划不同的纵横比。** 与其他 Surface 设备一样，Surface Hub 2 使用3:2 显示纵横比（显示的宽度和高度之间的关系）。 支持在具有不同纵横比的显示器上投影 Surface Hub 2。 请注意，由于 Surface Hub 2 是复制显示器，因此 MiniDP 输出还将仅显示3:2 纵横比，这可能会导致 letterboxing 或 curtaining，具体取决于接收显示器的纵横比。 

> [!NOTE]
> 如果第二台监视器使用的是16:9 纵横比（大多数电视监视器的主要比率），则会在镜像显示的左侧和右侧显示黑色条。 如果出现这种情况，您可能希望通知用户不需要调整第二个显示器。

## 选择电缆

请注意以下建议：

- **“USB”。** USB 3.1 第2代电缆。
- **MiniDP.** DisplayPort 缆线的认证长度最多为3米。
- **HDMI.** 如果需要长电缆，则建议使用 HDMI，因为具有经济高效的远距离缆线的广泛可用性，并且能够根据需要安装中继器。

> [!NOTE]
> 如果检测到 HDMI，大多数 DisplayPort 源将自动切换到 HDMI 信号。

## 无线连接到 Surface Hub 2

Windows 10 本身支持 Miracast，使你可以无线连接到 Surface Hub 2。<br><br>

### 要使用 Miracast 进行连接，请执行以下操作：

1. 在 Windows 10 设备上，输入**windows 徽标键**  +  **K**。 
2. 在 "连接" 窗口中，查找邻近设备列表中 Surface Hub 2 的名称。 你可以在显示屏左下角找到 Surface Hub 2 的名称。
3. 如果系统管理员已启用 Miracast 连接的 PIN 设置，请输入 PIN。 这要求你第一次连接到 Surface Hub 2 时输入 PIN 码。

> [!NOTE]
>如果看不到所需的 Surface Hub 2 设备的名称，则可能是以前的会话已过早关闭。 如果是这样，请直接登录 Surface Hub 2 以结束上一个会话，然后从外部设备进行连接。

## 将外围设备连接到 Surface Hub 2

### 蓝牙外部设备

您可以使用蓝牙将以下附件连接到 Surface Hub-2：

- 鼠标
- 键盘
- 耳机
- 扬声器
- Surface Hub 2 笔

> [!NOTE]
> 连接蓝牙耳机或扬声器后，你可能需要更改默认麦克风和扬声器设置。 有关详细信息，请参阅[**本地管理 Surface Hub 设置**](https://docs.microsoft.com/surface-hub/local-management-surface-hub-settings)。

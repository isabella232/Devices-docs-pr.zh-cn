---
title: 将设备连接到 Surface Hub 2S
description: 本页介绍如何将外部设备连接到 Surface Hub 2S。
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
ms.openlocfilehash: e3d1aa79ad056e790d5dc6a46f299cbaa9b5f9b0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497472"
---
# <a name="connect-devices-to-surface-hub-2s"></a>将设备连接到 Surface Hub 2S

Surface Hub 2S 使你能够连接外部设备、将 Surface Hub 2S 上的显示镜像到另一台设备，以及连接多个第三方外围设备，包括视频会议摄像头、会议电话和会议室系统设备。

可以将设备中的内容显示为 Surface Hub 2S。 如果源设备基于Windows，则该设备还可以提供 TouchBack 和 InkBack，后者从连接的设备获取视频和音频，并在 Surface Hub 2S 上显示它们。 如果 Surface Hub 2S 遇到High-Bandwidth数字内容保护 (HDCP) 信号（如蓝光 DVD 播放器），则源将显示为黑色图像。

> [!NOTE]
> Surface Hub 2S 使用选择的视频输入，直到建立新连接、中断现有连接或关闭连接应用。

## <a name="recommended-wired-configurations"></a>建议的有线配置 

通常，建议尽可能使用本机电缆连接，例如 USB-C 到 USB-C 或 HDMI 到 HDMI。 其他组合（如 MiniDP 到 HDMI 或 MiniDP 到 USB-C）也将有效。 可能需要其他一些配置来优化视频发布体验，如本页所述。

| **左侧的“连接”** | **功能** | **描述**|
| --- | --- | ---|
| HDMI + USB-C | 用于音频和视频的 HDMI-in<br><br>适用于 TouchBack 和 InkBack 的 USB-C | USB-C 支持使用 HDMI A/V 连接的 TouchBack 和 InkBack。<br><br>使用 USB-C 到 USB-A 连接到旧计算机。<br><br>**注意：** 为了获得最佳结果，请在连接 USB-C 电缆之前连接 HDMI。 如果用于 HDMI 的计算机与 TouchBack 和 InkBack 不兼容，则不需要 USB-C 电缆。 |
| USB-C <br> 通过计算模块 ()  | 视频入场 <br>音频 | A/V 所需的单根电缆<br><br>支持 TouchBack 和 InkBack<br><br>已启用 HDCP |
| 端口) 中的 HDMI ( | 视频，音频到Surface Hub 2S | A/V 所需的单根电缆<br><br>不支持 TouchBack 和 InkBack<br><br>已启用 HDCP |
| MiniDP 1.2 输出 | 视频播放，例如镜像到更大的投影器。 | A/V 所需的单根电缆 |

通过 USB-C 端口将来宾计算机连接到 Surface Hub 2S 时，会发现并配置多个 USB 设备。 这些外围设备是为 TouchBack 和 InkBack 创建的。 如下表所示，可以在设备管理器中查看外围设备，这将显示某些设备的重复名称，如下表所示。

 
|**外设**| **在设备管理器中列出** |
| ---------------------------- |------------- | ------------------------------|
| 人机接口设备 | 符合 HID 标准的消费者控制设备<br>符合 HID 标准的笔<br>符合 HID 标准的笔（重复项）<br>符合 HID 标准的笔（重复项）<br>符合 HID 标准的触摸屏<br>USB 输入设备<br>USB 输入设备（重复项） |
| 键盘 | 标准 PS/2 键盘 |
| 鼠标和其他指针设备 | 符合 HID 标准的鼠标 |
| USB 控制器 | 通用 USB 集线器<br>USB 复合设备 |

## <a name="connecting-video-in-to-surface-hub-2s"></a>将视频连接到 Surface Hub 2S

可以使用 USB-C 或 HDMI 将视频输入到 Surface Hub 2S，如下表所示。  

### <a name="surface-hub-2s-video-in-settings"></a>Surface Hub 2S 视频入场设置

| **信号类型** | **分辨率** | **帧速率** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| PC              | 640 x 480      | 60             | X        | X         |
| PC              | 720 x 480      | 60             | X        | X         |
| PC              | 1024 x 768     | 60             | X        | X         |
| PC              | 1920 x 1080    | 60             | X        | X         |
| PC              | 3840x2560      | 30             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 30             | X        | X         |

> [!NOTE]
> 4K UHD 解析 (3840×2560) 仅在连接到计算模块上的端口时才受支持。 位于设备左侧、顶部和右侧的“来宾”USB 端口不支持此功能。

> [!NOTE]
> 在 Surface Hub 2S 上显示时，连接的外部电脑中的视频可能看起来更小。

## <a name="mirroring-surface-hub-2s-display-on-another-device"></a>镜像Surface Hub 2S 显示在另一台设备上

可以使用 MiniDP 将视频输出到另一个显示屏，如下表所示。

### <a name="surface-hub-2s-video-out-settings"></a>Surface Hub 2S 视频分发设置

| **信号类型** | **分辨率** | **帧速率** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| PC              | 640 x 480      | 60             | X          |
| PC              | 720 x 480      | 60             | X          |
| PC              | 1024 x 768     | 60             | X          |
| PC              | 1920 x 1080    | 60             | X          |
| PC              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4K UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 2S 包含一个 MiniDP 视频端口，用于将视觉内容从 Surface Hub 2S 投影到另一个显示器。 如果计划使用 Surface Hub 2S 投影到另一个显示屏，请注意以下建议：

- **需要键盘。** 在开始之前，需要将已连接或启用蓝牙的外部键盘连接到 Surface Hub 2S。 请注意，与原始Surface Hub不同，Surface Hub 2S 的键盘单独出售，不包含在发货包中。<br><br>
- **设置重复模式。** Surface Hub 2S 仅支持重复模式下的视频输出。 但是，首次连接时仍需手动配置显示模式：
    1. 输入**Windows徽标键** + **P**，打开Surface Hub 2S 右侧的Project窗格，然后选择 **“重复**”模式。
    2. 完成Surface Hub 2S 会话后，选择 **“结束会话**”。 这可确保为下一个会话保存重复设置。<br><br>
- **规划不同的纵横比。** 与其他 Surface 设备一样，Surface Hub 2S 使用 3：2 显示纵横比 (显示) 的宽度和高度之间的关系。 支持将Surface Hub 2S 投影到具有不同纵横比的显示器上。 但是，请注意，由于Surface Hub 2S 重复显示，因此 MiniDP 输出也将仅以 3：2 纵横比显示，这可能会导致信箱或窗帘，具体取决于接收显示器的纵横比。 

> [!NOTE]
> 如果第二个监视器使用 16：9 纵横比 (大多数电视监视器) 的主要比率，则黑条可能会显示在镜像显示器的左侧和右侧。 如果发生这种情况，你可能希望通知用户无需调整第二个显示。

## <a name="selecting-cables"></a>选择电缆

请注意以下建议：

- **“USB”。** USB 3.1 Gen 2 电缆。
- **MiniDP。** 经认证长度高达 3 米的 DisplayPort 电缆。
- **HDMI。** 如果需要长电缆，建议使用 HDMI，因为可以广泛提供经济高效的长途电缆，并能够根据需要安装中继器。

> [!NOTE]
> 如果检测到 HDMI，大多数 DisplayPort 源将自动切换到 HDMI 信号。

## <a name="wirelessly-connect-to-surface-hub-2s"></a>以无线方式连接到 Surface Hub 2S

Windows 10/11 本机支持Miracast，使你能够无线连接到 Surface Hub 2S。<br><br>

### <a name="to-connect-using-miracast"></a>若要使用Miracast进行连接：

1. 在Windows 10/11 设备上，输入**Windows徽标密钥** + **。** 
2. 在连接窗口中，在附近的设备列表中查找Surface Hub 2S 的名称。 可以在显示屏左下角找到Surface Hub 2S 的名称。
3. 如果系统管理员已为Miracast连接启用 PIN 设置，请输入 PIN。 这要求首次连接到 Surface Hub 2S 时输入 PIN 编号。

> [!NOTE]
>如果未按预期看到 Surface Hub 2S 设备的名称，则可能会提前关闭上一个会话。 如果是这样，请直接登录到 Surface Hub 2S 以结束上一个会话，然后从外部设备进行连接。

## <a name="connecting-peripherals-to-surface-hub-2s"></a>将外围设备连接到 Surface Hub 2S

### <a name="bluetooth-accessories"></a>蓝牙外部设备

可以使用蓝牙将以下附件连接到 Surface Hub-2S：

- 鼠标
- 键盘
- 耳机
- 扬声器
- Surface Hub 2 支笔

> [!NOTE]
> 连接蓝牙耳机或扬声器后，你可能需要更改默认麦克风和扬声器设置。 有关详细信息，请参阅 [Surface Hub 设置的本地管理](local-management-surface-hub-settings.md)。

---
title: 适用于 Surface Hub 2 的 Windows 10 专业版和企业版的基本加载项
description: 本文提供有关可用于 Surface Hub 2 的 Windows 10 专业版或企业版的可选附件的信息。
keywords: Surface Hub，Windows 10，桌面，指纹读取器，Windows Hello
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.date: 09/16/2020
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: d908c937c331e36f6b82f4c3c5ee213abf8a0176
ms.sourcegitcommit: 2ac88d30b7d104d86b3bec657941457c916a116c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11026996"
---
# 适用于 Surface Hub 2 的 Windows 10 专业版和企业版的基本加载项

如果已从 Windows 10 团队迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版，则可以从各种通过 USB-C、USB A、HDMI 或蓝牙连接的附件中进行选择。 

## Surface Hub 2 指纹读取器

如果你在 Surface Hub 2 上运行 Windows 10 专业版或 Windows 10 企业版，则可以使用可选 Surface Hub 2 指纹读取器（使用 [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)的生物识别身份验证选项登录）。

### 订购

商业客户可以通过其 Surface 授权设备经销商下的订单。

**要使用 Surface Hub 2 指纹读取器，请执行以下操作：**

1. 将指纹读取器插入位于设备每侧的任何 USB C 挡板端口中。
2. **转到 "开始**  >  "**设置**  > **帐户**  > **登录选项**  > **Windows Hello 指纹**来注册指纹。

有关将指纹读取器配置为使用 Windows Hello 登录的详细信息，请参阅以下内容：

- [了解 Windows Hello 并对其进行设置](https://support.microsoft.com/help/4028017/windows-learn-about-windows-hello-and-set-it-up)
- [企业版中的 Windows Hello 生物识别](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise)。

  
### 表 1.  Surface Hub 2 指纹读取器技术规格


| 组件                       | 描述                                                                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **USB**                         | 自定义 USB 类型-C                                                                                                           |
| **系统要求**          | Windows 10 专业版、Windows 10 企业版。                                                                                               |
| **Windows 证书**       | Windows 10                                                                                                                           |
| ** (远) 的接受率为假** | 1/1.5 万。 目前显示生物识别安全系统错误地接受未经授权用户的访问尝试的可能性。 |


> [!NOTE]
> 在 Surface Hub 2 上运行的 Windows 10 团队不支持 Surface Hub 2 指纹读取器。 这是因为 Windows 10 团队设计为允许多个用户与会议会议室环境中的设备交互。 
 
## Windows Hello 人脸识别

Surface Hub 2 上的 windows 10 专业版和企业版支持 Windows Hello 身份验证，需要 Windows Hello 认证的相机附件。 请注意，Surface Hub 2 的内置相机不是为身份验证设计的，并且不支持 Windows Hello。 有关详细信息，请参阅 [Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)


## 音频和视频附件

您可以使用 USB-C 或 USB 端口，使用音频和照相机外围设备扩展 Surface Hub 2 的音频和视频功能。

有关推荐的附件的信息，请参阅：

- [为 Microsoft 团队认证的 USB 音频和视频设备](https://docs.microsoft.com/microsoftteams/devices/usb-devices)
- [适用于 Microsoft 团队的 IP 手机认证](https://docs.microsoft.com/microsoftteams/devices/teams-ip-phones)



## 其他附件
Surface Hub 2 包括用于连接各种设备的以下端口。 

- 1个 USB "计算" 模块上的端口 ("背后显示") 
- bezels 上的4个 USB C 端口
- 蓝牙4.1 支持
- HDMI 2。0

 ![I/O 连接和物理按钮的 "正面朝" 和 "中" 视图](images/hub2s-schematic.png)

有关详细信息，请参阅 [Surface Hub 2 端口和键盘概述](surface-hub-2s-port-keypad-overview.md)


## 了解详细信息

- [在 Surface Hub 2 上配置 Windows 10 专业版或企业版](surface-hub-2-post-install.md)。
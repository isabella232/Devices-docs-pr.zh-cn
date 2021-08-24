---
title: 适用于 Surface Hub 2 的 Windows 10 专业版和企业版的基本加载项
description: 本文提供有关可选附件的信息，可以在 Windows 10 专业版 2 Enterprise Surface Hub附件。
keywords: Surface Hub、Windows 10、桌面、指纹读取器、Windows Hello
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
ms.date: 09/18/2020
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: cd62a5217a5bd5e42fcee6ea7059b4cf5be551ac
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910957"
---
# <a name="essential-add-ons-for-windows-10-pro-and-enterprise-on-surface-hub-2"></a>适用于 Surface Hub 2 的 Windows 10 专业版和企业版的基本加载项

如果在 Surface Hub 2 上从 Windows 10 协同版 迁移到 Windows 10 专业版 或 Enterprise，可以从通过 USB-C、USB-A、HDMI 或 蓝牙 连接的各种附件中选择。 

## <a name="surface-hub-2-fingerprint-reader"></a>Surface Hub 2 指纹读取器

如果你在 Windows 10 专业版 2 上运行 Windows 10 专业版 或 Surface Hub Windows 10 企业版，可以使用可选的 Surface Hub 2 指纹读取器（使用指纹读取器的生物识别Windows Hello）[登录](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)。

### <a name="ordering"></a>订购

商业客户可以通过 Surface 授权的设备经销商下订单。

**若要使用 Surface Hub 2 指纹读取器：**

1. 将指纹读取器插入位于设备每一侧的任何 USB 连接端口。
2. **转到开始**  > **设置**  > **帐户**  > **登录选项**  > **Windows Hello指纹**注册指纹。

有关配置指纹读取器以使用密码登录Windows Hello，请参阅以下内容：

- [了解 Windows Hello 并对其进行设置](https://support.microsoft.com/help/4028017/windows-learn-about-windows-hello-and-set-it-up)
- [Windows Hello企业中的生物识别](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise)。

  
### <a name="table-1-surface-hub-2-fingerprint-reader-tech-specs"></a>表 1. Surface Hub 2 指纹读取器技术规范


| 组件                       | 描述                                                                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **USB**                         | 自定义的 USB Type-C                                                                                                           |
| **系统要求**          | Windows 10 专业版、Windows 10 企业版。                                                                                               |
| **Windows认证**       | Windows 10                                                                                                                           |
| **FALSE 接受率 (FAR) ** | 1/150 万。 FAR 显示生物识别安全系统错误地接受未经授权的用户访问尝试的可能性。 |
| **FRR (率错误) ** | 4.9%. FRR 显示生物识别安全系统错误地拒绝授权用户访问尝试的可能性。 |


> [!NOTE]
> Windows 10 协同版，在 2S Surface Hub上运行的指纹读取器不支持 Surface Hub 2 指纹读取器。 这是因为Windows 10 协同版设计为允许多个用户与会议室环境中的设备进行交互。 
 
## <a name="windows-hello-face-recognition"></a>Windows Hello人脸识别

Windows 10 专业版 Enterprise 2 Surface Hub支持Windows Hello身份验证，并且需要经过Windows Hello认证的相机附件。 请注意，适用于 Surface Hub 2S 的内置相机不用于身份验证，并且不支持Windows Hello。 有关详细信息，请参阅[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)


## <a name="audio-and-video-accessories"></a>音频和视频附件

可以使用 USB-C 或 USB-A 端口将 Surface Hub 2 的音频和视频功能与音频和视频外围设备一起扩展。

有关推荐附件的信息，请参阅：

- [经认证的 USB 音频和视频设备Microsoft Teams](https://docs.microsoft.com/microsoftteams/devices/usb-devices)
- [经认证的 IP 电话Microsoft Teams](https://docs.microsoft.com/microsoftteams/devices/teams-ip-phones)



## <a name="other-accessories"></a>其他附件
Surface Hub 2 包括用于连接各种设备的以下端口。 

- 计算模块上的 1 x USB A 端口 (显示器) 
- 4 x U 盘上的 USB C 端口
- 蓝牙 4.1 支持
- HDMI 2.0

 ![I/O 连接和物理按钮的正面和背面视图。](images/hub2s-schematic.png)

有关详细信息，请参阅[Surface Hub 2S 端口和小键盘概述](surface-hub-2s-port-keypad-overview.md)


## <a name="learn-more"></a>了解详细信息

- [在 Windows 10 专业版 2 Enterprise配置 Surface Hub 或 Surface Hub。](surface-hub-2-post-install.md)
---
title: Surface Hub 2 上Windows 10/11 Pro和Enterprise的基本加载项
description: 本文提供有关可在 Windows 10/11 Pro或 Surface Hub 2 上Enterprise使用的可选附件的信息。
keywords: Surface Hub、Windows 10、Windows 11、桌面、指纹读取器Windows Hello
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
ms.openlocfilehash: f146c2085f0d7c06e03da32ed4cc99821bd1abb2
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497905"
---
# <a name="essential-add-ons-for-windows-1011-pro-and-enterprise-on-surface-hub-2"></a>Surface Hub 2 上Windows 10/11 Pro和Enterprise的基本加载项

如果已在 Surface Hub 2 上从Windows 10 协同版迁移到Windows 10、Windows 11 专业版或Enterprise，则可从通过 USB-C、USB-A、HDMI 或 蓝牙 连接的各种附件中进行选择。 

## <a name="surface-hub-2-fingerprint-reader"></a>Surface Hub 2 指纹读取器

如果在 Surface Hub 2 上运行Windows 10/11 Pro或Windows 10/11 Enterprise，则可以使用可选的Surface Hub 2 指纹读取器（使用[Windows Hello](/windows-hardware/design/device-experiences/windows-hello)的生物识别身份验证选项）登录。

### <a name="ordering"></a>订购

商业客户可以通过其 Surface 授权设备经销商下订单。

**若要使用 Surface Hub 2 指纹读取器：**

1. 将指纹读取器插入设备两侧的任何 USB C 挡板端口。
2. **转到“开始”** > **** > 设置**AccountsSign-in** >  **选项** > **Windows Hello指纹**注册指纹。

有关配置指纹读取器以使用Windows Hello登录的详细信息，请参阅以下内容：

- [了解 Windows Hello 并对其进行设置](https://support.microsoft.com/help/4028017/windows-learn-about-windows-hello-and-set-it-up)
- [Windows Hello企业中的生物识别](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise)。

  
### <a name="table-1-surface-hub-2-fingerprint-reader-tech-specs"></a>表 1. Surface Hub 2 指纹读取器技术规格


| 组件                       | 描述                                                                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **USB**                         | 自定义 USB 类型 C                                                                                                           |
| **系统要求**          | Windows 10/11 Pro，Windows 10/11 Enterprise。                                                                                               |
| **Windows认证**       | Windows 10/11                                                                                                                           |
| **误接受率 (FAR) ** | 1/150万。 FAR 显示生物识别安全系统错误地接受未经授权用户的访问尝试的概率。 |
| **错误拒绝率 (FRR) ** | 4.9%. FRR 显示生物识别安全系统错误地拒绝授权用户的访问尝试的概率。 |


> [!NOTE]
> 在 Surface Hub 2S 上运行的Windows 10 协同版不支持Surface Hub 2 指纹读取器。 这是因为Windows 10 协同版旨在允许多个用户在会议室环境中与设备交互。 
 
## <a name="windows-hello-face-recognition"></a>Windows Hello人脸识别

Surface Hub 2 上的Windows 10/11 Pro和Enterprise支持Windows Hello进行身份验证，并且需要Windows Hello认证的相机配件。 请注意，Surface Hub 2S 的内置相机不是为身份验证而设计的，也不支持Windows Hello。 有关详细信息，请参阅[Windows Hello。](/windows-hardware/design/device-experiences/windows-hello)


## <a name="audio-and-video-accessories"></a>音频和视频配件

可以使用 USB-C 或 USB-A 端口通过音频和相机外围设备扩展 Surface Hub 2 的音频和视频功能。

有关建议的附件的信息，请参阅：

- [经认证为Microsoft Teams的 USB 音频和视频设备](/microsoftteams/devices/usb-devices)
- [已通过Microsoft Teams认证的 IP 电话](/microsoftteams/devices/teams-ip-phones)



## <a name="other-accessories"></a>其他附件
Surface Hub 2 包含以下用于连接各种设备的端口。 

- 1 x USB 计算模块上的 A 端口 (显示) 
- 挡板上的 4 x USB C 端口
- 蓝牙 4.1 支持
- HDMI 2.0

 ![I/O 连接和物理按钮的前置和下侧视图。](images/hub2s-schematic.png)

有关详细信息，请参阅 [Surface Hub 2S 端口和键盘概述](surface-hub-2s-port-keypad-overview.md)


## <a name="learn-more"></a>了解详细信息

- 在 [Surface Hub 2 上配置Windows 10/11 Pro或Enterprise](surface-hub-2-post-install.md)。
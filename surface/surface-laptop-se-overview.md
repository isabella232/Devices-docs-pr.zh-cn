---
title: Surface Laptop SE 概述
description: 本文提供适用于教育Surface Laptop 标准版概述。
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/11/2022
ms.reviewer: hachidan
manager: laurawi
audience: itpro
appliesto:
- Windows 11
ms.openlocfilehash: a99c3241eea0099b90de9c64ff840306aa98e58d
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448316"
---
# <a name="surface-laptop-se-overview"></a>Surface Laptop SE 概述

Surface Laptop 标准版提供托管设备体验，以经济实惠的价格为学生简化学习。 它Windows 11 标准版云第一操作系统，并预加载广泛使用的应用，如 [](#pre-installed-apps) Microsoft Teams、Word、PowerPoint、Excel、OneNote、Edge、Minecraft: Education Edition、Flipgrid等。 

:::image type="content" source="images/surface-laptop-se.png" alt-text="Surface Laptop 标准版显示Windows 11 标准版 &quot;开始&quot;菜单":::<br>
*图 1. Surface Laptop 标准版显示Windows 11 标准版 "开始"菜单*

Surface Laptop 标准版支持学生和教师所需的大多数应用程序，包括渐进式 Web 应用 (PWA) 、通用 Windows 平台应用 (UP) 以及一组特建的 [Win32 & Microsoft Store 应用](#install-optional-apps)。 与其他 Surface 设备不同，Surface Laptop 标准版阻止用户安装自己的应用。 相反，IT 管理员或技术Surface Laptop 标准版使用 Microsoft Endpoint Manager 管理 Microsoft Endpoint Manager 设备，其中包括 [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)、[Microsoft Intune for Education](https://www.microsoft.com/education/intune) 和新的 [Surface Management Portal](surface-management-portal.md)。 

> [!NOTE]
> 本文适用于为学校用户部署和管理设备的 IT 管理员和教育人员。 有关常规信息或订购，请参阅 [Surface Laptop 标准版 Laptop Laptop for Students](https://www.microsoft.com/surface/business/surface-laptop-se)。

## <a name="simplified-deployment-management--security"></a>简化了部署、&安全性

- 使用 Autopilot 完成新设备的低接触Windows，快速应用策略和安装应用。 Windows Autopilot 提供开箱即用、具有预安装和预配置的许多应用和策略的低接触部署和映像。 IT 可以轻松调整设备设置（包括固件设置）并安装学生所需的应用，以便当他们首次打开设备电源时一切准备就绪。
- 部署设备后，Microsoft Intune在整个学校年度提供简化的远程管理，使 IT 能够管理应用、控制安全性和隐私以及生成合规性报告。
- 在笔记本电脑关闭时，使用盖锁锁定操作系统，使用集成的 Kensington Nano 安全插槽控制物理访问™。
- 新设计的未公开容器、一个机架机架和一个环绕屏幕的空边框，这些边框可提供额外的持续性，以更好地满足学生使用的需求。
- Intune 和 DFCI 支持固件层的安全设备更新和管理。 IT 管理员可以控制硬件元素（如麦克风、USB 端口、相机和蓝牙设备）并消除外设电源。 唯一可扫描的 Surface 打包便于标识设备，设备 ID 号在重新注册时保持不变。

### <a name="surface-management-portal"></a>Surface 管理门户

当你注册Surface Laptop 标准版和用户首次登录时，这些 Surface 设备的信息会自动流入 [Surface 管理](surface-management-portal.md)门户，从而提供特定于 Surface 的设备管理员活动的单一窗格。 你可以深入了解设备合规性、支持活动和担保范围。 快速查看每台设备的状态、哪些设备仍在担保中或即将过期，以及活动支持请求的状态。

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="显示产品/服务担保范围Surface Laptop 标准版":::
*图 2. 显示产品/服务担保范围Surface Laptop 标准版*

## <a name="common-admin-scenarios"></a>常见的管理员方案

| 方案                                                            | 说明                                                                                                                                                                                                                                                                                                                          | 了解详细信息                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 使用 Autopilot Surface Laptop 标准版远程配置Windows设备 | Windows Autopilot 提供开箱即用式低接触部署和映像，预安装和预配置了许多应用和策略。 IT 可以轻松调整设备设置（包括固件设置）并安装学生所需的应用，以便当他们首次打开设备电源时一切准备就绪。                 |[使用 Autopilot 设置 Intune for Education Windows设备](/intune-education/windows-autopilot-setup)<br><br>[如何注册我的设备？](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| 通过 Intune for Education 部署更新                             | IT 管理员可以使用Microsoft Intune在整个一年将操作系统Surface Laptop 标准版应用更新推送到整个学校的设备。 如有必要，他们可以在单个设备上禁用蓝牙设备等硬件元素，或重置特定设备（如果学生遇到技术问题）。 |[管理运行 Windows 11 标准版](/intune-education/windows-11-se-overview)<br><br>[Microsoft 教育版文档和资源](/microsoft-365/education/)<br><br>[Intune for Education 入门](/microsoft-365/education/deploy/intune-for-education)<br><br>[使用 Intune for Education 管理组、应用和设置](/microsoft-365/education/deploy/use-intune-for-education) |
| 根据需要替换设备                                           | 如果学生破解屏幕或以其他方式损坏设备，IT 管理员可以快速部署备用设备，将学生云标识传输到新设备。                                                                                                  |[Intune for Education 中的远程设备操作](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| 通过 Intune 部署新应用                                          | 如果教师请求新应用，IT 管理员可以使用 Intune 在所有学生设备上远程安装它。                                                                                                                                                                                                                            |[为所有用户安装应用](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| 通过 Intune 重置设备                                            | 当学生在学年结束时打开 Surface Laptop 标准版 设备时，IT 管理员可以使用 Intune 重置下一个班级的设备，下一个学年度开始时将需要这些设备。                                                                                                           |[使用 Autopilot 重置通过 Intune for Education 重新配置设备](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>预安装的应用

Surface Laptop标准版预安装的应用：  

- Microsoft Excel
- Flipgrid
- Groove音乐
- 地图
- Microsoft Edge
- Microsoft 资讯
- Microsoft Teams
- 微软待办
- Microsoft Whiteboard
- 我的世界教育版
- 记事本
- Microsoft Office
- OneDrive
- OneNote
- Outlook 网页版
- 画图
- 照片
- PowerPoint
- Snipping 工具
- 便笺
- Surface 应用
- Surface Diagnostic Toolkit
- 提示
- 语音录音机
- 天气
- 文字

## <a name="install-optional-apps"></a>安装可选应用

IT 管理员可以通过 Intune [安装其他应用](/education/windows/windows-11-se-overview#available-apps) ，例如 Chrome 或 Zoom。 请注意，没有适用于应用商店Surface Laptop 标准版。 请参阅以下说明以完成应用部署： 

- [应用部署](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>可修复性

Surface Laptop 标准版 Surface Laptop 标准版快速更换核心组件，使技能熟练技术人员能够在本地为设备提供服务：

- 显示模块  
- 键盘&存储桶
- 扬声器& Wi-Fi模块
- 电池
- 英尺

学校可以使用经授权的服务提供商或自己熟练掌握的技术人员，按照 Microsoft 提供的"Surface Laptop 标准版服务指南"现场修复设备，该指南可从 [Surface Service Guides 获得](https://www.microsoft.com/download/100440)。

若要了解更多，请参阅：

- [Surface Laptop 标准版修复视频](https://youtu.be/fVjjSqfp75g)
- [适用于 Surface 设备的卓越支持解决方案](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop 标准版技术规格

| 功能                     | 说明                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **维度**              | - 11.17" x 7.6" x 0.70" (283.70 mm x 193.05 mm x 17.85 mm)                                                                                                                                                 |
| ****<sup>存储1</sup>     | - 板载、嵌入式多媒体卡 (eMMC) 64GB 或 128GB                                                                                                                                                 |
| **显示器**                 | - 屏幕：11.6" TFT 安装设备显示模块<br>- 显示分辨率：1366 x 768 (135 PPI) <br>- 纵横比：16：9<br>- 对比率：800：1 (典型) <br>- 亮度：220 nits<br>- 无覆盖层 |
| **电池**                 | - 35Wh () ，33.9Wh (分钟) <br>- 电池使用时间 16 小时 <sup>2</sup>                                                                                                                                              |
| **内存**                  | - 4GB 或 8GB (2400 MHz，最低)                                                                                                                                                                           |
| **CPU/图形**          | - Intel® Processor® N4020 / IntelUHD® Graphics 600<br>- Intel® Processor® N4120 / IntelUHD® Graphics 600                                                                                |
| **连接**             | - 1 x USB-A<br>- 1 x USB-C<br>- 1 x 筒类型 DC 连接器<br>- 1 x 3.5 毫米耳机/麦克风 Jack                                                                                                           |
| **安全性**                | - 所有配置中的固件 TPM (商业) <br>- Nano 安全锁槽                                                                                                                        |
| **相机、视频&音频** | - 1MP 前置摄像头，最多 720p 30fps 视频<br>- 2W 立体声扬声器<br>- 单个数字麦克风                                                                                              |
| **软件**                | - Windows 11 标准版<br>- Microsoft 365教育<sup>版 3</sup>                                                                                                                                                         |
| **无线**                | - WLAN：802.11ac (2x2) <br>- 蓝牙 Wireless 5.0 LE                                                                                                                                                    |
| **传感器**                 | - 1 x 大厅效果传感器                                                                                                                                                                                  |
| **百年**                | - 大小写：所有未配对的正文<br>- 颜色：月光<br>- 物理按钮：键盘上的电源和音量<br>- 倾斜：135 度开放角度                                                          |
| **粗细**                  | - 2.45 lb. (1，111.3 g)                                                                                                                                                                                     |
| **键盘和触控板**   | - 无 Windows 11.6" 的标准键盘<br>- 标准无浮动精度跟踪板                                                                                                      |
| **热**                | - 被动冷                                                                                                                                                                                        |
| **电源**            | - 箱内，45W（带 DC 桶）                                                                                                                                                                      |
| **包装箱内包含：**              | - Surface 设备<br>- 电源<br>- 快速入门指南<br>- 安全和担保文档                                                                                                              |
| **担保**<sup>4</sup>    | - 一年有限硬件担保                                                                                                                                                                      |

## <a name="references"></a>参考

1. 系统软件和更新使用大量存储空间。 可用存储可能会根据系统软件、更新和应用使用情况发生变化。 1 GB = 10 亿字节。 1 TB = 1，000 GB。 有关详细信息[，存储](https://support.microsoft.com/help/4023513/surface-surface-storage?) Surface 存储。
2. 电池使用时间因使用情况、网络和功能配置、信号强度、设置和其他因素而显著不同。 有关详细信息 [，请参阅 Surface 电池测试和估计](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) 性能。
3. 需要合格的Microsoft 365或Office 365许可证;单独出售。 [比较Microsoft 365教育计划](https://aka.ms/EDU-Plan-Comparison)。
4. Microsoft 的有限担保是消费者法权利补充。


## <a name="learn-more"></a>了解详细信息

- [订单Surface Laptop 标准版](https://www.microsoft.com/surface/business/surface-laptop-se)
- [Surface Laptop 标准版教育](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [Windows 11 标准教育版](/education/windows/windows-11-se-overview)
- [管理运行 Windows 11 标准版](/intune-education/windows-11-se-overview)
- [使用 Autopilot 设置 Intune for Education Windows设备](/intune-education/windows-autopilot-setup)
- [Microsoft 教育版文档和资源](/microsoft-365/education/)
- [Outlook 网页版](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)

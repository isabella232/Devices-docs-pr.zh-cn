---
title: Surface Laptop SE 概述
description: 本文概述了教育Surface Laptop 标准版。
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
ms.openlocfilehash: 2d16d63dda53bbfffbf5d7d9cb080c4e595217a5
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472581"
---
# <a name="surface-laptop-se-overview"></a>Surface Laptop SE 概述

Surface Laptop 标准版提供托管设备体验，以经济实惠的成本简化学生学习。 它Windows 11 标准版（云优先 OS）运行，并[预加载了广泛使用的应用](#pre-installed-apps)，如 Microsoft Teams、Word、PowerPoint、Excel、OneNote、Edge、Minecraft: Education Edition、Flipgrid等。 

:::image type="content" source="images/surface-laptop-se.png" alt-text="显示Windows 11 标准版 &quot;开始&quot;菜单Surface Laptop 标准版":::<br>
*图 1. 显示Windows 11 标准版 "开始"菜单Surface Laptop 标准版*

Surface Laptop 标准版支持学生和教师所需的大多数应用程序，包括渐进式Web 应用 (PVA) 、通用 Windows 平台应用 (UWP) ，以及一[组精选的 Win32 & Microsoft Store应用](#install-optional-apps)。 与其他 Surface 设备不同，Surface Laptop 标准版阻止用户安装自己的应用。 相反，IT 管理员或技术主管使用Microsoft Endpoint Manager管理Surface Laptop 标准版设备，其中包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)、[教育Microsoft Intune](https://www.microsoft.com/education/intune)和新的 [Surface Management 门户](surface-management-portal.md)。 

> [!NOTE]
> 本文适用于为学校用户部署和管理设备的 IT 管理员和教育人员。 有关常规信息或订购，请参阅[Surface Laptop 标准版适用于学生的精简笔记本电脑](https://www.microsoft.com/surface/business/surface-laptop-se)。

## <a name="simplified-deployment-management--security"></a>简化的部署、管理&安全性

- 使用 Windows Autopilot 完成新设备的低触控部署，快速应用策略并安装应用。 Windows Autopilot 提供低触控部署和现成映像，并预安装并预配置了许多应用和策略。 IT 可以轻松调整设备设置（包括固件设置），并安装学生所需的应用，以便在首次在设备上供电时一切就绪。
- 部署设备后，Microsoft Intune在整个学年提供简化的远程管理，使 IT 能够管理应用、控制安全和隐私以及生成合规性报告。
- 关闭笔记本电脑时，使用盖锁锁定操作系统，并使用集成的肯辛顿 Nano 安全槽™控制物理访问。
- 新设计的非公开铰链、塑料底盘和屏幕周围的塑料边框，用于挡板，可提供额外的持久性，以更好地满足学生使用的需求和需求。
- Intune和 DFCI 支持对固件层进行安全的设备更新和管理。 IT 管理员可以控制硬件元素（如麦克风、USB 端口、相机和蓝牙），并删除外围设备的电源。 独特的可扫描 Surface 打包允许轻松识别设备，在重新注册时设备 ID 号保持不变。

### <a name="surface-management-portal"></a>Surface 管理门户

注册云管理Surface Laptop 标准版并且用户首次登录时，来自这些 Surface 设备的信息会自动流入 [Surface Management 门户](surface-management-portal.md)，为特定于 Surface 的设备管理活动提供单个玻璃窗格。 可以深入了解设备符合性、支持活动和保修范围。 快速查看每个设备的状态（哪些设备仍在保修或即将到期）以及活动支持请求的状态。

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="显示Surface Laptop 标准版保修覆盖率的 Surface Management 门户":::
*图 2. 显示Surface Laptop 标准版保修覆盖率的 Surface Management 门户*

## <a name="common-admin-scenarios"></a>常见管理员方案

| 方案                                                            | 描述                                                                                                                                                                                                                                                                                                                          | 了解详细信息                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 使用 Windows Autopilot 远程配置Surface Laptop 标准版设备 | Windows Autopilot 提供现成的低触控部署和映像，并预安装并预配置了许多应用和策略。 IT 可以轻松调整设备设置（包括固件设置），并安装学生所需的应用，以便在首次在设备上供电时一切就绪。                 |[使用 Windows Autopilot 为教育设备设置Intune](/intune-education/windows-autopilot-setup)<br><br>[应如何注册我的设备？](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| 通过教育Intune部署更新                             | IT 管理员可以使用Microsoft Intune全年向全校Surface Laptop 标准版设备推出 OS 和应用更新。 如有必要，他们可以在单个设备上禁用相机或蓝牙等硬件元素，或者在学生遇到技术问题时重置特定设备。 |[管理运行Windows 11 标准版的设备](/intune-education/windows-11-se-overview)<br><br>[Microsoft 教育版文档和资源](/microsoft-365/education/)<br><br>[开始教育Intune](/microsoft-365/education/deploy/intune-for-education)<br><br>[使用 Intune for Education 管理组、应用和设置](/microsoft-365/education/deploy/use-intune-for-education) |
| 根据需要替换设备                                           | 如果学生破解屏幕或以其他方式损坏设备，IT 管理员可以快速部署备用设备，将学生的云标识传输到新设备。                                                                                                  |[Intune教育版中的远程设备操作](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| 通过Intune部署新应用                                          | 如果教师请求新的应用，IT 管理员可以使用Intune在所有学生设备上远程安装它。                                                                                                                                                                                                                            |[为所有用户安装应用](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| 通过Intune重置设备                                            | 当学生在学年结束时交上Surface Laptop 标准版设备时，IT 管理员可以使用Intune为下一学年开始时需要这些设备的下一班重置设备。                                                                                                           |[使用 Autopilot Reset 使用教育Intune重新配置设备](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>预安装的应用

Surface Laptop标准版附带以下预安装的应用：  

- Microsoft Excel
- Flipgrid
- Groove 音乐
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
- 剪切工具
- 便笺
- Surface 应用
- Surface Diagnostic Toolkit
- 提示
- 语音录音机
- 天气
- 文字

## <a name="install-optional-apps"></a>安装可选应用

IT 管理员可以通过Intune安装[其他应用](/education/windows/windows-11-se-overview#available-apps)，如 Chrome 或 Zoom。 请注意，Surface Laptop 标准版没有应用商店。 请参阅以下说明来完成应用部署： 

- [应用部署](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>可修复性

Surface Laptop 标准版 Surface Laptop 标准版旨在通过快速替换核心组件，使熟练的技术人员能够在本地为设备提供服务：

- 显示模块  
- 键盘&存储桶
- 扬声器& Wi-Fi模块
- 电池
- 脚

学校可以使用授权的服务提供程序或他们自己的熟练技术人员，根据 Microsoft 提供的"Surface Laptop 标准版服务指南"（从 [Surface Service Guides](https://www.microsoft.com/download/100440) 提供）现场修复设备。

若要了解更多，请参阅：

- [Surface Laptop 标准版修复视频](https://youtu.be/fVjjSqfp75g)
- [适用于 Surface 设备的卓越支持解决方案](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop 标准版技术规范

| 功能                     | 描述                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **尺寸**              | - 11.17" x 7.6" x 0.70" (283.70 mm x 193.05 mm x 17.85 mm)                                                                                                                                                 |
| ****<sup>存储1</sup>     | - 在船上，嵌入式多媒体卡 (eMMC) 64GB 或 128GB                                                                                                                                                 |
| **显示器**                 | - 屏幕：11.6" TFT 液晶显示模块<br>- 显示分辨率：1366 x 768 (135 PPI) <br>- 纵横比：16：9<br>- 对比度：800：1 (典型) <br>- 亮度：220 尼特<br>- 无盖玻璃 |
| **电池**                 | - 35 时 (名义) ，33.9 时 (分钟) <br>- 电池续航 <sup>时间 16 小时 2</sup>                                                                                                                                              |
| **内存**                  | - 4GB 或 8GB DDR4 (2400 MHz min)                                                                                                                                                                           |
| **CPU/图形**          | - Intel® Celeron® 处理器 N4020/ Intel® UHD 图形 600<br>- Intel® Celeron® 处理器 N4120/ Intel® UHD 图形 600                                                                                |
| **连接**             | - 1 x USB-A<br>- 1 x USB-C<br>- 1 x 桶型 DC 连接器<br>- 1 x 3.5 毫米耳机/麦克风杰克                                                                                                           |
| **安全性**                | - 所有配置的固件 TPM (商业) <br>- Nano 安全锁定槽                                                                                                                        |
| **相机、视频、&音频** | - 1MP 前置摄像头，最高 720p 30fps 视频<br>- 2W 立体声扬声器<br>- 单数字麦克风                                                                                              |
| **软件**                | - Windows 11 标准版<br>- Microsoft 365教育<sup>版 3</sup>                                                                                                                                                         |
| **无线**                | - Wi-Fi：802.11ac (2x2) <br>- 蓝牙无线 5.0 LE                                                                                                                                                    |
| **传感器**                 | - 1 x 大厅效果传感器                                                                                                                                                                                  |
| **外部**                | - 大小写：所有未涂漆的塑料正文<br>- 颜色：冰川<br>- 物理按钮：键盘上的电源和音量<br>- 兴格：135度开放角度                                                          |
| **粗细**                  | - 2.45 磅 (1，111.3 g)                                                                                                                                                                                     |
| **键盘和触控板**   | - 不带背光的标准Windows键盘 11.6"<br>- 标准无浮精度触控板                                                                                                      |
| **热**                | - 被动冷却                                                                                                                                                                                        |
| **电源**            | - 内置，45W 与 DC 桶充电器                                                                                                                                                                      |
| **包装箱内包含：**              | - Surface 设备<br>- 电源<br>- 快速入门指南<br>- 安全和保修文档                                                                                                              |
| **保修**<sup>4</sup>    | - 一年限量硬件保修                                                                                                                                                                      |

## <a name="references"></a>参考

1. 系统软件和更新使用大量的存储空间。 可用存储可能会根据系统软件、更新和应用使用情况进行更改。 1 GB = 10 亿字节。 1 TB = 1，000 GB。 有关更多详细信息，请参阅 [Surface 存储](https://support.microsoft.com/help/4023513/surface-surface-storage?)。
2. 电池使用时间因使用情况、网络和功能配置、信号强度、设置和其他因素而有显著差异。 有关详细信息，请参阅 [Surface 电池测试和估计性能](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) 。
3. 需要符合条件的Microsoft 365或Office 365许可证;单独出售。 [比较Microsoft 365教育计划](https://aka.ms/EDU-Plan-Comparison)。
4. Microsoft 的有限保修是消费者法律权利的补充。


## <a name="learn-more"></a>了解详细信息

- [订单Surface Laptop 标准版](https://www.microsoft.com/surface/business/surface-laptop-se)
- [教育Surface Laptop 标准版简介](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [Windows 11 标准教育版](/education/windows/windows-11-se-overview)
- [管理运行Windows 11 标准版的设备](/intune-education/windows-11-se-overview)
- [使用 Windows Autopilot 为教育设备设置Intune](/intune-education/windows-autopilot-setup)
- [Microsoft 教育版文档和资源](/microsoft-365/education/)
- [Outlook 网页版](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)
- [用于教育的专用硬件&软件解决方案](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/a-purpose-built-hardware-amp-software-solution-for-education/ba-p/1419013)
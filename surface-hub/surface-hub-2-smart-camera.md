---
title: 安装和管理 Surface Hub 2 智能相机
description: 介绍如何安装和管理 Surface Hub 2 智能相机的设置。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/16/2022
ms.localizationpriority: Medium
ms.openlocfilehash: 9cdf7d2d5b6f1f6a99d2f3caa1168804c2110159
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472677"
---
# <a name="install-and-manage-surface-hub-2-smart-camera"></a>安装和管理 Surface Hub 2 智能相机

Surface Hub 2 智能相机<sup> 1</sup> 专为混合团队设计，针对远程参与者进行了优化。 远程参与者可以敏锐地关注前台和背景，可以看到用户与Surface Hub上的内容进行交互，同时查看会议室中的其他人。 Surface Hub 2 智能相机具有大于 136 度的宽视区、自动框架、高质量的玻璃光学和低光传感器。
![超宽相机视图包括人们在 85 英寸中心的极端边缘上加入白板](images/surface-hub-2-smart-camera-fov.png)

*超宽相机视图包括人们在 85 英寸中心的极端边缘上加入白板*

## <a name="system-requirements"></a>系统要求

对于运行 Team OS 的 Surface Hub，Surface Hub 2 智能相机需要针对 [Surface Hub 20H2 Windows 10 协同版 2020 更新](surface-hub-2020-update-whats-new.md) (20H2) 进行以下更新：

- Windows 10 协同版 2020 年更新 2 (KB5010415 或后续Windows更新) 
- 系统硬件更新 - 2022/1/21 (或后续的系统硬件更新) 

若要了解详细信息，请参阅[Surface Hub更新历史记录](surface-hub-update-history.md)。

> [!NOTE]
> 迁移到运行Windows 10或Windows 11 专业版/Enterprise的 Surface Hub 无需其他更新。

## <a name="install-smart-camera"></a>安装智能相机

1. 将相机附加到 Surface Hub 2 顶部的 USB-C 端口。 当相机连接并持续使用相机时，指示器 LED 会短暂亮起。

     ![将相机附加到 Surface Hub 2 顶部的 USB-C 端口。](images/hub2smartcamera1.png)

2. 若要删除相机，请向上拉取和向前拉取。 磁性系绳可防止相机被敲掉或向后拉。

    ![若要删除相机，请向上拉取和向前拉取。](images/hub2smartcamera2.png)

> [!TIP]
> 相机覆盖磁贴到前面的隐私和背面存储时，不使用。

## <a name="manage-automatic-framing-settings"></a>管理自动框架设置

自动框架动态缩放，并在四处移动时保持视频中心。 如何管理设置取决于在Surface Hub上安装的 OS：

- [Windows 10 协同版 2020 年更新 (20H2) ](#windows-10-team-2020-update-20h2)
- [Windows 11桌面Surface Hub](#windows-11-desktop-on-surface-hub)
- [Windows 10桌面Surface Hub](#windows-10-desktop-on-surface-hub)

### <a name="windows-10-team-2020-update-20h2"></a>Windows 10 协同版 2020 年更新 (20H2) 

安装Surface Hub智能相机时，默认情况下会启用自动框架。 管理员可以通过打开/关闭切换从设置管理自动框架，该开关在每个Surface Hub会话开始时设置自动框架状态。

**调整自动框架：**

1. 在Surface Hub 2S 上，以**管理员**身份登录。

> [!NOTE]
> 如果不知道用户名或管理员密码，则需要重置设备。 有关详细信息，请参阅 [Surface Hub 2S 的重置和恢复](/surface-hub/surface-hub-2s-recover-reset)。

2. 打开**设置**并转到**Surface Hub >呼叫&音频。**
3. 在 **"自动框架**"下，根据需要调整切换。 
4. 选择 **"结束"会话**;启动新会话时将应用修改后的设置。 

如果切换设置为 **"打开**"，则当用户在Surface Hub上开始会话时，自动框架将始终处于默认状态。 如果切换设置为 **"关闭**"，则在Surface Hub上启动会话时，自动帧将始终处于关闭状态。

#### <a name="manage-camera-settings-via-an-mdm-provider"></a>通过 MDM 提供程序管理相机设置

管理员可以通过 [Surface Hub 配置服务提供商](/windows/client-management/mdm/surfacehub-csp) (CSP) 从 Intune 或第三方移动设备管理 (MDM) 提供程序管理自动框架。

|CSP 策略设置| 描述|
|------------------|------------|
|DefaultAutomaticFraming|如果启用此策略设置，则会启用自动框架。 如果关闭此策略设置，则会禁用自动框架。 如果不配置此策略设置，则会启用自动框架。 |

若要了解详细信息，请参阅以下内容：

- [使用 MDM 提供程序管理设置](/surface-hub/manage-settings-with-mdm-for-surface-hub#create-custom-configuration-profile)
- [SurfaceHub CSP - Windows客户端管理](/windows/client-management/mdm/surfacehub-csp)

### <a name="windows-11-desktop-on-surface-hub"></a>Windows 11桌面Surface Hub

如果已[迁移Surface Hub](surface-hub-2s-migrate-os.md)以运行Windows 11 专业版或Windows 11 企业版，则需要为Surface Hub智能相机启用自动框架。 默认情况下，自动框架处于关闭状态。

若要启用自动框架，请转到**设置 > 蓝牙 &设备>管理相机> Surface Hub 2 智能相机。**

### <a name="windows-10-desktop-on-surface-hub"></a>Windows 10桌面Surface Hub

自动框架始终处于启用状态，无法禁用或以其他方式配置。

## <a name="order-surface-hub-2-smart-camera"></a>订购Surface Hub 2 台智能相机

从[授权的 Microsoft Surface 经销商](https://www.microsoft.com/surface/business/where-to-buy-microsoft-surface?)处购买Surface Hub 2 台智能相机。

### <a name="references"></a>参考

1. Surface Hub 2 智能相机，从 2022 年 3 月 16 日开始单独销售，动态调整远程参与者的视频源。 从 2022 年 5 月开始，Surface Hub 2 智能相机将包含在包含 Surface Hub 2S 85"的框中。

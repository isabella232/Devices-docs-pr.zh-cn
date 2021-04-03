---
title: 实现 Surface Hub 上的服务质量
ms.reviewer: ''
manager: laurawi
description: 了解如何在 Surface Hub 上配置 QoS。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470480"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>在 Surface Hub 上 (服务质量) QoS 服务

QoS (Qo) S (是网络技术的组合，使管理员能够优化实时音频/视频和应用程序共享通信的体验。
 
在 Surface Hub 上配置适用于 Skype for Business 的 [QoS](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 可以使用你的移动设备管理 (MDM) [提供商](manage-settings-with-mdm-for-surface-hub.md) 或预配 [包完成](provisioning-packages-for-surface-hub.md)。 
 
 
此过程介绍如何使用 Microsoft Intune 为 Surface Hub 配置 QoS。 

1. 在 Intune 中 [，创建自定义策略](https://docs.microsoft.com/intune/custom-settings-configure)。

    > [!div class="mx-imgBorder"]
    > ![Intune 中的自定义策略创建对话框的屏幕截图](images/qos-create.png)

2. 在 **"自定义 OMA-URI 设置"中**，选择"**添加"。** 对于你添加的每个设置，你将输入名称、描述 (可选) 、数据类型、OMA-URI 和值。

    > [!div class="mx-imgBorder"]
    > ![空白 OMA-URI 设置对话框的屏幕截图](images/qos-setting.png)

3. 添加以下自定义 OMA-URI 设置：<br/><br/>

    名称 | 数据类型 | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  值
    --- | --- | --- | ---
    音频源端口 | 字符串 |  /HubAudio/SourcePortMatchCondition  |   从 Skype 管理员获取值
    音频 DSCP | 整型 |  /HubAudio/DSCPAction  |   46
    视频源端口 | 字符串 |  /HubVideo/SourcePortMatchCondition   |  从 Skype 管理员获取值
    视频 DSCP | 整型 |  /HubVideo/DSCPAction   |   34
    音频进程名称 | 字符串 |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    视频进程名称 | 字符串 |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >每个 **OMA-URI** 路径以 `./Device/Vendor/MSFT/NetworkQoSPolicy` 开头。 例如，音频源端口设置的完整路径将为 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 。

4. 创建策略后，将其部署到 Surface Hub。


>[!WARNING]
>目前，您无法在[NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)中配置**IPProtocolMatchCondition**设置。 如果配置了此设置，则策略将无法应用。
 

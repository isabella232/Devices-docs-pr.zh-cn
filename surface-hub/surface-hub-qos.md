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
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830910"
---
# 在 Surface Hub 上实施服务质量（QoS）

服务质量（QoS）是网络技术的组合，允许管理员优化实时音频/视频和应用程序共享通信的体验。
 
在 Surface Hub 上[为 Skype For business 配置 QoS](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)可以使用[移动设备管理（MDM）提供程序](manage-settings-with-mdm-for-surface-hub.md)或通过[预配包](provisioning-packages-for-surface-hub.md)完成。 
 
 
此过程介绍如何使用 Microsoft Intune 配置 Surface Hub 的 QoS。 

1. 在 Intune 中，[创建自定义策略](https://docs.microsoft.com/intune/custom-settings-configure)。

    ![Intune 中自定义策略创建对话框的屏幕截图](images/qos-create.png)

2. 在 "**自定义 OMA URI 设置**" 中，选择 "**添加**"。 对于你添加的每个设置，你将输入名称、描述（可选）、数据类型、OMA URI 和值。

    ![空白 OMA URI 设置对话框的屏幕截图](images/qos-setting.png)

3. 添加以下自定义 OMA URI 设置：

    名称 | 数据类型 | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  值
    --- | --- | --- | ---
    音频源端口 | 字符串 |  /HubAudio/SourcePortMatchCondition  |   从您的 Skype 管理员获取值
    音频 DSCP | 整型 |  /HubAudio/DSCPAction  |   46
    视频源端口 | 字符串 |  /HubVideo/SourcePortMatchCondition   |  从您的 Skype 管理员获取值
    视频 DSCP | 整型 |  /HubVideo/DSCPAction   |   34
    音频流程名称 | 字符串 |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    视频流程名称 | 字符串 |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >每个**OMA URI**路径均以开头 `./Device/Vendor/MSFT/NetworkQoSPolicy` 。 例如，音频源端口设置的完整路径将为 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 。




4. 创建策略后，将[其部署到 Surface Hub。](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)


>[!WARNING]
>目前，你不能在[NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)中配置设置**IPProtocolMatchCondition** 。 如果配置了此设置，则该策略将无法应用。
 

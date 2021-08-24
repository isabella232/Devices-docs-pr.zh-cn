---
title: 实现 Surface Hub 上的服务质量
ms.reviewer: ''
manager: laurawi
description: 了解如何在客户端上配置 QoS Surface Hub。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: b235ab8e19df42fa63efe5e66ac590c58c50d179
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910947"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>在服务上 (QoS) 服务质量Surface Hub

服务质量 (QoS) 是网络技术的组合，使管理员能够优化实时音频/视频和应用程序共享通信的体验。
 
通过使用移动设备管理 Skype for Business MDM Surface Hub 提供程序或预配包[， (为](manage-settings-with-mdm-for-surface-hub.md)) 配置[](provisioning-packages-for-surface-hub.md)[QoS。](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 
 
 
此过程说明如何使用 Surface Hub 配置 qoS Microsoft Intune。 

1. 在 Intune 中 [，创建自定义策略](https://docs.microsoft.com/intune/custom-settings-configure)。

    > [!div class="mx-imgBorder"]
    > ![Intune 中自定义策略创建对话框的屏幕截图。](images/qos-create.png)

2. 在**自定义 OMA-URI 设置，****选择添加**。 对于你添加的每个设置，你将输入名称、描述 (可选) 、数据类型、OMA-URI 和值。

    > [!div class="mx-imgBorder"]
    > ![空白 OMA-URI 设置对话框的屏幕截图。](images/qos-setting.png)

3. 添加以下自定义 OMA-URI 设置：<br/><br/>

    名称 | 数据类型 | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  值
    --- | --- | --- | ---
    音频源端口 | 字符串 |  /HubAudio/SourcePortMatchCondition  |   从管理员Skype值
    音频 DSCP | 整型 |  /HubAudio/DSCPAction  |   46
    视频源端口 | 字符串 |  /HubVideo/SourcePortMatchCondition   |  从管理员Skype值
    视频 DSCP | 整型 |  /HubVideo/DSCPAction   |   34
    音频进程名称 | 字符串 |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    视频进程名称 | 字符串 |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >每个 **OMA-URI** 路径以 `./Device/Vendor/MSFT/NetworkQoSPolicy` 开头。 例如，音频源端口设置的完整路径将为 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 。

4. 创建策略后，将其部署到Surface Hub。


>[!WARNING]
>目前，您无法在[NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)中配置**IPProtocolMatchCondition**设置。 如果配置了此设置，则策略将无法应用。
 

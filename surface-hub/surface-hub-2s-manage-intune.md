---
title: 使用 Intune 管理 Surface Hub 2S
description: 了解如何使用 Intune 更新和管理 Surface Hub 2S。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/28/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1d1b836c18a41982497bb28c57f379408c04f8a5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832044"
---
# 使用 Intune 管理 Surface Hub 2S

## 使用 Intune 注册 Surface Hub 2S

Surface Hub 2S 支持 IT 管理员使用移动设备管理 (MDM) 提供程序管理设置和策略。 Surface Hub 2S 具有内置管理组件，可与管理服务器通信，因此无需在设备上安装其他客户端。

### 手动注册

1. 以本地管理员身份登录 Surface Hub 2S，然后打开“**设置**”应用。 选择“**Surface Hub**” > “**设备管理**”，然后选择 **+** 进行添加。
2. 进行身份验证后，该设备将自动使用 Intune 进行注册。

   ![使用 Intune 注册 Surface Hub 2S](images/sh2-set-intune1.png)<br>

### 自动注册 — 与 Azure Active Directory 关联

在初始设置流程中，将 Surface Hub 与已启用 Intune 自动注册的 Azure AD 租户相关联时，设备将自动使用 Intune 注册。 有关详细信息，请参阅[适用于 Windows 设备的 Intune 注册方法](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods)。 Surface Hub 需要进行 Azure AD 关联和 Intune 自动注册才能成为 Intune 中的“合规设备”。 

## Windows 10 协同版设置

为 Surface Hub 和 Surface Hub 2S 的设备限制设置预置选择“Windows 10 协同版”。

 ![设置 Surface Hub 2S 的设备限制。](images/sh2-set-intune3.png) <br>

这些设置包括用户体验和应用行为、Azure Log Analytics 注册、维护 Windows 配置、会话设置和 Miracast 设置。 有关 Windows 10 协同版可用设置的完整列表，请参阅 [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)。

## 支持的其他配置服务提供程序 (CSP)

有关支持的其他 CSP，请参阅 [Windows 10 中的 Surface Hub CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)。

## 服务质量 (QoS) 概述

若要确保 Surface Hub 2S 获得最佳视频和音频质量，请向设备添加以下 QoS 设置。 

### Microsoft Teams QoS 设置 

|**名称**|**描述**|**OMA-URI**|**类型**|**值**|
|:------ |:------------- |:--------- |:------ |:------- |
|**音频端口**| 音频端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | 字符串  | 3478-3479 |
|**音频 DSCP**| 音频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | 整型 | 46 |
|**视频端口**| 视频端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | 字符串  | 3480 |
|**视频 DSCP**| 视频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | 整型 | 34 |
|**P2P 音频端口**| 音频端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | 字符串  | 50000-50019 |
|**P2P 音频 DSCP**| 音频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | 整型 | 46 |
|**P2P 视频端口**| 视频端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | 字符串  | 50020-50039 |
|**P2P 视频 DSCP**| 视频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | 整型 | 34 |


### Skype for Business QoS 设置

| 名称               | 描述         | OMA-URI                                                                  | 类型    | 值                          |
| ------------------ | ------------------- | ------------------------------------------------------------------------ | ------- | ------------------------------ |
| 音频端口        | 音频端口范围    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition  | 字符串  | 50000-50019                    |
| 音频 DSCP         | 音频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                | 整型 | 46                             |
| 音频媒体源 | Skype 应用名称      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition | 字符串  | Microsoft.PPISkype.Windows.exe |
| 视频端口        | 视频端口范围    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition  | 字符串  | 50020-50039                    |
| 视频 DSCP         | 视频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                | 整型 | 34                             |
| 视频媒体源 | Skype 应用名称      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition | 字符串  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> 两张表都显示了默认端口范围。 管理员可以在 Skype for Business 和 Teams 控制面板中更改端口范围。

## Microsoft Teams 模式设置

可以使用 Intune 设置 Microsoft Teams 应用的模式。 Surface Hub 2S 安装时附带模式 0 的 Microsoft Teams，该模式同时支持 Microsoft Teams 和 Skype for Business。 可按如下所示调整模式。

### 模式：

- 模式 0 — 具有 Microsoft Teams 计划会议功能的 Skype for Business。
- 模式 1 — 具有 Skype for Business 计划会议功能的 Microsoft Teams。
- 模式 2 — 仅 Microsoft Teams。

若要设置模式，请将以下设置添加至设备配置文件。

|**名称**|**描述**|**OMA-URI**|**类型**|**值**|
|:--- |:--- |:--- |:--- |:--- |
|**Teams 应用 ID**|应用名称|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|字符串| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 应用模式**|Teams 模式|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|整型| 0 或 1 或 2|

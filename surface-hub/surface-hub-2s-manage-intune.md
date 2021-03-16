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
ms.date: 12/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 406fcc58bdb09d7fd47966cd17123d55faec2b65
ms.sourcegitcommit: ea853f2dba67e63e6df33538670fd581e17facab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "11408787"
---
# <a name="manage-surface-hub-2s-with-intune"></a>使用 Intune 管理 Surface Hub 2S

## <a name="register-surface-hub-2s-with-intune"></a>使用 Intune 注册 Surface Hub 2S

Surface Hub 2S 支持 IT 管理员使用移动设备管理 (MDM) 提供程序管理设置和策略。 Surface Hub 2S 具有内置管理组件，可与管理服务器通信，因此无需在设备上安装其他客户端。

### <a name="manual-registration"></a>手动注册

1. 打开**** Surface Hub 2S 上的"设置"应用，然后以本地管理员登录。 选择“**Surface Hub**” > “**设备管理**”，然后选择 **+** 进行添加。
2. 系统将提示你使用用于 Intune 的帐户登录。 进行身份验证后，该设备将自动使用 Intune 进行注册。

   ![使用 Intune 注册 Surface Hub 2S](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> 用于身份验证的帐户将是 Intune 注册帐户，并且必须获得 Intune 许可。

### <a name="auto-registration--azure-active-directory-affiliated"></a>自动注册 — 与 Azure Active Directory 关联

在初始设置流程中，将 Surface Hub 与已启用 Intune 自动注册的 Azure AD 租户相关联时，设备将自动使用 Intune 注册。 有关详细信息，请参阅[适用于 Windows 设备的 Intune 注册方法](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods)。 Surface Hub 需要进行 Azure AD 关联和 Intune 自动注册才能成为 Intune 中的“合规设备”。 

## <a name="managing-windows-10-team-settings-with-intune"></a>使用 Intune 管理 Windows 10 团队设置

1. 登录到**Microsoft Endpoint Manager，** 选择 **"设备**  >  **配置文件**  >  **""创建配置文件"。** 
2. 在**平台**下，**选择 Windows 10 和更高版本**的模板 ( >  ****  >  **Windows 10**) 然后选择创建 。 **** 
3. 现在，你可以浏览并选择 Surface Hub 和 Surface Hub 2S 的预设设备限制设置。

 ![设置 Surface Hub 2S 的设备限制。](images/sh2-set-intune3.png) <br>

这些设置包括以下类别：应用和体验、Azure 操作见解、维护、会话和无线投影。  

## <a name="supported-configuration-service-providers-csps"></a>支持的配置服务提供程序 (SP) 

除了通过 Intune 控制台直接提供的策略之外，还有许多映射到注册表项或 (CSP) 配置服务提供程序。 

Microsoft 通常会为 Windows 10 操作系统的每个新版本提供新的 CSP。 [Windows 10 Team 2020 更新](surface-hub-2020-update.md)包括 20 多个适用于 Surface Hub 和 Surface Hub 2S 的新设备管理策略和更新的设备管理策略。 借助这些 MDM 策略，IT 管理员可增强对来自 Microsoft Store 的应用更新、无线投影设置（如基础结构的 Miracast、网络设置（如服务质量和 802.1x 有线身份验证）以及新的隐私/GDPR 相关设置的控制。

有关详情，请参阅以下资源： 

- [配置服务提供程序参考](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub 云解决方案提供商](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Microsoft Surface Hub 支持的策略 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Surface Hub Team 2020 更新中的新增功能](surface-hub-2020-update-whats-new.md)

## <a name="quality-of-service-qos-settings"></a>服务质量 (QoS) 概述

若要确保 Surface Hub 2S 获得最佳视频和音频质量，请向设备添加以下 QoS 设置。 

### <a name="microsoft-teams-qos-settings"></a>Microsoft Teams QoS 设置 

| 名称 | 描述 | OMA-URI | 类型 | 值 |
|:------ |:------------- |:--------- |:------ |:------- |
|**音频端口**| 音频端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | 字符串  | 3478-3479 |
|**音频 DSCP**| 音频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | 整型 | 46 |
|**视频端口**| 视频端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | 字符串  | 3480 |
|**视频 DSCP**| 视频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | 整型 | 34 |
|**共享端口**| 共享端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | 字符串  | 3481 |
|**共享 DSCP**| 共享端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | 整型 | 18 |
|**P2P 音频端口**| 音频端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | 字符串  | 50000-50019 |
|**P2P 音频 DSCP**| 音频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | 整型 | 46 |
|**P2P 视频端口**| 视频端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | 字符串  | 50020-50039 |
|**P2P 视频 DSCP**| 视频端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | 整型 | 34 |
|**P2P 共享端口**| 共享端口范围 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | 字符串  | 50040-50059 |
|**P2P 共享 DSCP**| 共享端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | 整型 | 18 |


### <a name="skype-for-business-qos-settings"></a>Skype for Business QoS 设置

| 名称                 | 描述           | OMA-URI                                                                    | 类型    | 值                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| 音频端口          | 音频端口范围      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | 字符串  | 50000-50019                    |
| 音频 DSCP           | 音频端口标记   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | 整型 | 46                             |
| 音频媒体源   | Skype 应用名称        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | 字符串  | Microsoft.PPISkype.Windows.exe |
| 视频端口          | 视频端口范围      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | 字符串  | 50020-50039                    |
| 视频 DSCP           | 视频端口标记   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | 整型 | 34                             |
| 视频媒体源   | Skype 应用名称        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | 字符串  | Microsoft.PPISkype.Windows.exe |
| 共享端口        | 共享端口范围    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | 字符串  | 50040-50059                    |
| 共享 DSCP         | 共享端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | 整型 | 18                             |
| 共享媒体源 | Skype 应用名称        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | 字符串  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> 两张表都显示了默认端口范围。 管理员可以在 Skype for Business 和 Teams 控制面板中更改端口范围。

## <a name="microsoft-teams-settings"></a>Microsoft Teams 设置

可以使用 Intune 配置各种 Microsoft Teams 设置。

### <a name="modes"></a>模式

Surface Hub 2S 安装时附带模式 0 的 Microsoft Teams，该模式同时支持 Microsoft Teams 和 Skype for Business。 这些模式的功能如下所述：

- 模式 0 — 具有 Microsoft Teams 计划会议功能的 Skype for Business。
- 模式 1 — 具有 Skype for Business 计划会议功能的 Microsoft Teams。
- 模式 2 — 仅 Microsoft Teams。

若要调整模式，将以下设置添加到[自定义设备配置文件。](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

| 名称 | 描述 | OMA-URI | 类型 | 值 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 应用 ID**|应用名称|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|字符串| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 应用模式**|Teams 模式|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|整型| 0 或 1 或 2|

### <a name="coordinated-meetings-and-proximity-join"></a>协调会议和邻近感应加入

可以通过通过 Intune 配置文件部署的 [XML](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) 文件配置 Teams 协调会议与邻近感应加入功能。

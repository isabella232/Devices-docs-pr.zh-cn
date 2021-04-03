---
title: 使用 MDM 提供程序管理设置 (Surface Hub)
description: Microsoft Surface Hub 提供的企业管理解决方案可帮助 IT 管理员在这些设备上使用移动设备管理 (MDM) 解决方案管理策略和业务应用程序。
ms.assetid: 18EB8464-6E22-479D-B0C3-21C4ADD168FE
ms.reviewer: ''
manager: laurawi
keywords: 移动设备管理, MDM, 管理策略
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 1afa4d63dde793e61e30d1c4dd54f552b5581a81
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470451"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>使用 MDM 提供程序管理 Surface Hub

Surface Hub 允许 IT 管理员使用移动设备管理来管理设置和策略， (MDM) 提供程序（如 Microsoft Intune）。 Surface Hub 具有与管理服务器通信的内置管理组件。 无需在设备上安装其他客户端。

## <a name="enrolling-surface-hub-into-mdm-management"></a>将 Surface Hub 注册到 MDM 管理 

可以通过手动或自动注册将 Surface 注册到 Microsoft Intune 或其他 MDM 提供程序。

### <a name="manual-enrollment"></a>手动注册

1. 打开 **"设置** "应用，然后以本地管理员登录。 选择**Surface Hub**  >  **设备管理，** 然后选择 **+设备管理**。
2. 系统将提示你使用帐户登录以用于 MDM 提供程序。 进行身份验证后，设备将自动注册 MDM 提供程序。

> [!TIP]
> 如果你使用的是 Intune 并且未检测到服务器地址，请输入**manage.microsoft.com。**
   
> [!NOTE]
>  MDM 注册使用为身份验证提供的帐户详细信息。 帐户必须拥有注册 Windows 设备的权限，以及 Intune 许可证 (或第三方 MDM 提供程序策略中配置的等效注册) 。

### <a name="auto-enrollment--azure-ad-affiliated"></a>自动注册 — Azure AD 附属

在初始设置过程中，将 Surface Hub 与启用了 Intune 自动注册的 Azure Active Directory (AD) 租户关联时，设备将自动注册 Intune。 若要了解详情，请参阅 [Windows 设备的 Intune 注册方法](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods)。 Surface Hub 需要进行 Azure AD 关联和 Intune 自动注册才能成为 Intune 中的“合规设备”。 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>使用 Intune 管理 Surface Hub Windows 10 团队设置

Intune 和其他 MDM 提供程序中策略设置管理的基础构建块是基于 XML 的 Open Mobile Alliance-Device Management (OMA-DM) 协议。 Windows 10 通过许多可用的配置服务提供程序 (CSP) （名称如 AccountManagement CSP、DeviceStatus CSP、Wirednetwork-CSP 等）之一来实现 OMA-DM XML。 有关完整列表，请参阅[Microsoft Surface Hub 中支持的 CSP。](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)


Microsoft Intune 和其他 MDM 提供程序使用 CSP 提供 UI，使你能够在配置文件中配置策略设置。 Intune 将 Surface Hub CSP 用于其内置配置文件（设备限制  ** (Windows 10 ** 团队) ）让你可以配置基本设置，例如防止 Surface Hub 在邻近感应范围内附近移动时"唤醒"。 若要在 Intune 的内置配置文件之外管理中心设置和功能，你需要使用自定义配置文件， [如下所示](#create-custom-configuration-profile)。 

总之，在 Intune 中配置和管理策略设置的选项包括： 
 
- **创建设备限制配置文件。** 使用 Intune 的内置配置文件，并直接在 Intune UI 中配置设置。 请参阅 [创建设备限制配置文件](#create-device-restriction-profile)。
- **创建设备配置文件。**  选择侧重于特定功能或技术的模板，例如 Microsoft Defender 或安全证书。 请参阅 [创建设备配置文件](#create-device-configuration-profile)。
- **创建自定义配置文件。**  使用 OMA 统一资源标识符 (OMA URI) Microsoft Surface Hub 支持的任何 [CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)扩展管理作用域。 请参阅 [创建自定义配置文件](#create-custom-configuration-profile)。


## <a name="create-device-restriction-profile"></a>创建设备限制配置文件

1. 登录到[**Microsoft Endpoint Manager 管理中心，选择**](https://endpoint.microsoft.com/)**"设备**  >  **配置文件""**  >  **+** **创建配置文件"。**
2. 在 **平台**下，选择 **Windows 10 和更高版本** >
3. 在配置文件类型下 **，** 选择**模板**，然后选择 Windows **10 (设备**限制) 
4. 选择 **"创建**"，添加名称，然后选择"下一 **步"。**
6. 现在，你可以跨以下类别浏览并选择 Surface Hub 的预设设备限制设置：应用和体验、Azure 操作见解、维护、会话和无线投影。 下图中显示的示例为屏幕、睡眠和会话恢复指定 4 小时维护窗口和 15 分钟超时。

     ![使用 Intune 设备限制配置文件配置 Surface Hub 设置](images/sh-device-restrictions.png)

有关创建和管理配置文件的信息，请参阅使用 Microsoft Intune 中的策略 [限制设备功能](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile)。
 
若要详细了解如何管理 Surface Hub 功能和设置，请参阅 [Microsoft Intune 中的 Surface Hub Windows 10 团队设备限制](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>创建设备配置文件

1. 登录到[**Microsoft Endpoint Manager 管理中心，选择**](https://endpoint.microsoft.com/)**"设备**  >  **配置文件**  >  **+ 创建配置文件"。**
2. 在 **平台**下，选择 **Windows 10 和更高版本** >
3. 在 **"配置文件类型**"下 **，选择"** 模板"，然后从 Surface Hub 上支持的以下模板中选择：

    - Windows 10 (的设备) ，如上一部分 [中所述](#create-device-restriction-profile)。
    - Microsoft Defender for Endpoint (Windows 10 桌面版) 
    - PKCS 证书
    - PKCS 导入的证书
    - SCEP 证书
    - 受信任的证书

## <a name="create-custom-configuration-profile"></a>创建自定义配置文件

可以通过从 Microsoft Surface Hub[](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)中支持的任何[CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)使用 OMA URI 创建自定义配置文件来扩展管理作用域。 CSP 中的每个设置都有一个对应的 OMA-URI，可以使用 Intune 中的自定义配置文件设置该 OMA-URI。 有关 Surface Hub 支持的 CSP 的详细信息，你可以参考以下资源： 

- [配置服务提供程序参考](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Microsoft Surface Hub 支持的策略 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub 云解决方案提供商](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> 使用 [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) 中的设置管理设备帐户当前无法通过 Intune 实现，并且需要使用第三方 MDM 提供程序。

若要实现基于 CSP 的策略设置，请首先生成 OMA URI，然后将其添加到 Intune 中的自定义配置文件。

### <a name="generate-oma-uri-for-target-setting"></a>为目标设置生成 OMA URI
 
若要生成任何设置的 OMA URI：

1. 在 [云解决方案提供商文档中](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)，标识云解决方案提供商的根节点。 通常，这类似于 **./Vendor/MSFT/ <name of CSP> **。 
    - **示例：**[SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)的根节点是 **./Vendor/MSFT/SurfaceHub**。
2. 标识想要使用的设置的节点路径。 
    - **示例：** 启用无线投影的设置的节点路径为 **InBoxApps/WirelessProjection/Enabled**。
3. 将节点路径附加到根节点，生成 OMA URI。 
    - **示例：** 启用无线投影设置的 OMA URI 为 **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled。**
4. 数据类型也在云解决方案提供商文档中作了介绍。 最常见的数据类型有：
    - char（字符串）
    - int（整数）
    - bool（布尔值）

### <a name="add-oma-uri-to-custom-configuration-profile"></a>将 OMA URI 添加到自定义配置文件

1. 在"终结点管理器"中 **，选择"设备**  >  **配置文件**  >  **""创建配置文件"。**
2. 在"平台"下 **，选择"Windows 10 及更高版本"。** 在"配置文件"下 **，选择"自定义**"，然后选择"创建 **"。**
3. 添加名称和可选说明，然后选择"下一 **步"。**
4. 在**配置设置**  >  **OMA-URI 设置下**，选择添加 。 ****

  
## <a name="manage-specific-surface-hub-features"></a>管理特定 Surface Hub 功能

本部分重点介绍了有关可通过 Intune 或其他 MDM 提供程序管理的功能的信息。 这包括：

- [QoS (服务质量) ](#quality-of-service-settings)
- [Microsoft Teams 和 Skype for Business](#microsoft-teams-and-skype-for-business-settings)

### <a name="quality-of-service-settings"></a>服务质量设置

若要确保 Surface Hub 上的最佳视频和音频质量，请向设备添加以下 QoS 设置。 

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


#### <a name="skype-for-business-qos-settings"></a>Skype for Business QoS 设置

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

### <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams 和 Skype for Business 设置

你可以创建自定义配置文件来管理 Teams 协调会议、邻近感应加入和其他功能。 若要了解详细信息，请参阅 [在 Surface Hub 上管理 Microsoft Teams 配置](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)。

#### <a name="changing-default-business-communications-platform"></a>更改默认业务通信平台

Surface Hub 上的默认业务通信平台因你安装 Windows 10 Team 2020 Update (（即 Windows 10 20H2 版本）) 。 如果将 Surface Hub 重新映像到 Windows 10 20H2，Microsoft Teams 将设置为默认值，Skype for Business 功能在模式 1 (可用) 。 如果你从较早的操作系统版本升级 Hub，Skype for Business 将保留为默认版本，Teams 功能在 (模式 0) 除非已配置 Teams 作为默认版本。 

若要更改默认安装，请通过设置[](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)Teams 应用模式来使用自定义配置文件，如下所示：  

- 模式 0 — 具有 Microsoft Teams 计划会议功能的 Skype for Business。
- 模式 1 — 具有 Skype for Business 计划会议功能的 Microsoft Teams。
- 模式 2 — 仅 Microsoft Teams。

| 名称 | 描述 | OMA-URI | 类型 | 值 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 应用 ID**|应用名称|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|字符串| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 应用模式**|Teams 模式|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|整型| 0 或 1 或 2|











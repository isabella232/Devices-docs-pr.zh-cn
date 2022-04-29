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
ms.openlocfilehash: e126799fe023d97468e58c01b003ce4b605f2db7
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497785"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>通过 MDM 提供商管理 Surface Hub

Surface Hub允许 IT 管理员使用移动设备管理 (MDM) 提供程序（例如Microsoft Intune）来管理设置和策略。 Surface Hub有一个内置的管理组件，用于与管理服务器通信。 无需在设备上安装其他客户端。

## <a name="enrolling-surface-hub-into-mdm-management"></a>将Surface Hub注册到 MDM 管理 

可以通过手动或自动注册将 Surface 注册到 Microsoft Intune 或其他 MDM 提供程序。

### <a name="manual-enrollment"></a>手动注册

1. 打开**设置**应用并以本地管理员身份登录。 选择**Surface Hub** >  **Device 管理**，然后选择 **“+设备管理**”。
2. 系统将提示你使用要用于 MDM 提供程序的帐户登录。 身份验证后，设备会自动向 MDM 提供程序注册。

> [!TIP]
> 如果使用的是Intune且未检测到服务器地址，请输入 **manage.microsoft.com**。
   
> [!NOTE]
> MDM 注册使用为身份验证提供的帐户详细信息。 该帐户必须有权注册Windows设备以及Intune许可证 (或在第三方 MDM 提供程序) 中配置的等效注册授权。

### <a name="auto-enrollment--azure-ad-affiliated"></a>自动注册 - Azure AD附属

在初始设置过程中，将Surface Hub与启用了Intune自动注册的Azure Active Directory (AD) 租户关联时，设备将自动注册Intune。 若要了解详细信息，请参阅[Windows设备的Intune注册方法](/intune/enrollment/windows-enrollment-methods)。 Surface Hub 需要进行 Azure AD 关联和 Intune 自动注册才能成为 Intune 中的“合规设备”。 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>使用Intune管理Surface Hub Windows 10 协同版设置

Intune和其他 MDM 提供程序中策略设置管理的基础构建基块是基于 XML 的 Open Mobile Alliance-Device 管理 (OMA-DM) 协议。 Windows通过许多可用的配置服务提供程序之一实现 OMA-DM XML， (CSP) 名称，例如 AccountManagement CSP、DeviceStatus CSP、WiFi-CSP 等。 有关完整列表，请参阅[Microsoft Surface Hub中支持的 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)。

Microsoft Intune和其他 MDM 提供程序使用 CSP 来提供 UI，使你可以在配置文件中配置策略设置。 Intune对其内置配置文件（**设备限制 (Windows 10 协同版) ** ）使用Surface Hub CSP，让你配置基本设置，例如，每当有人在其邻近范围内移动时，阻止Surface Hub“醒来”。 若要管理Intune内置配置文件之外的中心设置和功能，需要使用自定义配置文件，[如下所示](#create-custom-configuration-profile)。 

总之，在Intune中配置和管理策略设置的选项包括： 
 
- **创建设备限制配置文件。** 使用Intune内置配置文件，并直接在 Intune UI 中配置设置。 请参阅 [“创建设备限制配置文件](#create-device-restriction-profile)”。
- **创建设备配置文件。**  选择专注于特定功能或技术（如 Microsoft Defender 或安全证书）的模板。 请参阅 [“创建设备配置文件](#create-device-configuration-profile)”。
- **创建自定义配置文件。**  使用 OMA 统一资源标识符 (OMA URI) 从Microsoft Surface Hub[中支持的任何 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) 扩展管理范围。 请参阅 [“创建自定义配置文件](#create-custom-configuration-profile)”。

> [!NOTE]
> 配置文件应分配给包含已注册Surface Hub设备的设备组。

## <a name="create-device-restriction-profile"></a>创建设备限制配置文件

1. 登录[**到Microsoft Endpoint Manager管理中心**](https://endpoint.microsoft.com/)，选择 **“****DevicesConfiguration** >  配置文件 > **+****创建配置文件**”。
2. 在 **“平台**”下，选择**Windows 10及更高版本** >
3. 在****配置文件类型下 **，** 选择**模板**，然后选择**设备限制 (Windows 10 协同版) **
4. 选择 **“创建”**，添加名称，然后选择 **“下一步”。**
6. 现在，可以浏览并从预设设备限制设置中选择以下类别的Surface Hub：应用和体验、Azure 操作见解、维护、会话和无线投影。 下图所示的示例指定屏幕、睡眠和会话恢复的 4 小时维护时段和 15 分钟的超时时间。

     ![使用Intune设备限制配置文件配置Surface Hub设置。](images/sh-device-restrictions.png)

有关创建和管理配置文件的详细信息，请参阅[Microsoft Intune中使用策略限制设备功能](/mem/intune/configuration/device-restrictions-configure#create-the-profile)。
 
有关如何管理Surface Hub功能和设置的详细信息，请[参阅Windows 10 协同版设置，以允许或限制Surface Hub使用Intune](/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>创建设备配置文件

1. 登录[**到Microsoft Endpoint Manager管理中心**](https://endpoint.microsoft.com/)，选择 **“****DevicesConfiguration** >  配置文件 > **+ 创建配置文件**”。
2. 在 **“平台**”下，选择**Windows 10及更高版本** >
3. 在 **“配置文件”类型**下，选择 **“模板**”，然后从Surface Hub上支持的以下模板中进行选择：

    - 设备限制 (Windows 10 协同版) ，如[上一部分](#create-device-restriction-profile)所述。
    - Microsoft Defender for Endpoint (Windows 10桌面) 
    - PKCS 证书
    - PKCS 导入证书
    - SCEP 证书
    - 受信任的证书

## <a name="create-custom-configuration-profile"></a>创建自定义配置文件

可以使用 OMA URI 从 [Microsoft Surface Hub 中支持的任何 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) [创建自定义配置文件](/mem/intune/configuration/custom-settings-configure)来扩展管理范围。 CSP 中的每个设置都有一个相应的 OMA-URI，可以在Intune中使用自定义配置文件进行设置。 有关Surface Hub支持的 CSP 的详细信息，可以参考以下资源： 

- [配置服务提供程序参考](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Microsoft Surface Hub 支持的策略 CSP](/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub 云解决方案提供商](/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> 目前无法使用 [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp) 中的设置管理设备帐户，Intune需要使用第三方 MDM 提供程序。

若要实现基于 CSP 的策略设置，首先生成 OMA URI，然后将其添加到 Intune 中的自定义配置文件。

### <a name="generate-oma-uri-for-target-setting"></a>为目标设置生成 OMA URI
 
若要为任何设置生成 OMA URI，请执行以下操作：

1. 在 [CSP 文档](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)中，标识 CSP 的根节点。 一般情况下，这类似于 **./Vendor/MSFT/NameOfCSP**。 
    - **例子：**[SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp) 的根节点是 **./Vendor/MSFT/SurfaceHub**。
2. 标识想要使用的设置的节点路径。 
    - **例子：** 用于启用无线投影的设置的节点路径是 **InBoxApps/WirelessProjection/Enabled**。
3. 将节点路径附加到根节点，生成 OMA URI。 
    - **例子：** 用于启用无线投影的设置的 OMA URI 为 **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled。**
4. 数据类型也在云解决方案提供商文档中作了介绍。 最常见的数据类型有：
    - char（字符串）
    - int（整数）
    - bool（布尔值）

### <a name="add-oma-uri-to-custom-configuration-profile"></a>将 OMA URI 添加到自定义配置文件

1. 在Endpoint Manager中，选择 **“****DevicesConfiguration** >  **profilesCreate** >  配置文件”。
2. 在“平台”下选择**Windows 10及更高版本。** 在“配置文件”下，选择 **“自定义**”，然后选择 **“创建”。**
3. 添加名称和可选说明，然后选择 **“下一步”。**
4. 在**配置设置** > **OMA-URI设置**下，选择 **“添加**”。

  
## <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams和Skype for Business设置

本部分重点介绍可通过 Intune 或其他 MDM 提供程序管理的Teams和Skype for Business设置。 这包括：

- [服务质量 (QoS) ](#quality-of-service-settings)
- [管理特定于Teams的功能](#manage-teams-specific-features)

### <a name="quality-of-service-settings"></a>服务质量设置

若要确保Surface Hub上的最佳视频和音频质量，请将以下 QoS 设置添加到设备。 

| 名称                 | 描述           | OMA-URI                                                                 | 类型    | 值                          |
| -------------------- | --------------------- | ----------------------------------------------------------------------- | ------- | ------------------------------ |
| 音频端口          | 音频端口范围      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/SourcePortMatchCondition    | 字符串  | 50000-50019                    |
| 音频 DSCP           | 音频端口标记   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/DSCPAction                  | 整型 | 46                             |
| 视频端口          | 视频端口范围      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/SourcePortMatchCondition    | 字符串  | 50020-50039                    |
| 视频 DSCP           | 视频端口标记   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/DSCPAction                  | 整型 | 34                             |
| 共享端口        | 共享端口范围    | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/SourcePortMatchCondition  | 字符串  | 50040-50059                    |
| 共享 DSCP         | 共享端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/DSCPAction                | 整型 | 18                             |

> [!NOTE]
> 该表显示默认端口范围。 管理员可以在 Skype for Business 和 Teams 控制面板中更改端口范围。

### <a name="manage-teams-specific-features"></a>管理特定于Teams的功能

可以创建自定义配置文件来管理Teams协调会议、邻近加入和其他功能。 若要了解详细信息，请参阅[Surface Hub上的管理Microsoft Teams配置](/microsoftteams/rooms/surface-hub-manage-config)。

### <a name="changing-default-app-for-meetings--calls"></a>更改会议的默认应用&调用

会议的默认应用& Surface Hub上的调用因安装Windows 10 协同版 2020 更新 (又名 Windows 10 20H2 Team edition) 的方式而异。 如果将Surface Hub重新映像到 Windows 10 20H2，Microsoft Teams将设置为默认值，Skype for Business在模式 1)  (不可用。 如果从早期 OS 版本升级中心，则Skype for Business将保留为默认值，Teams功能可 (模式 0) ，除非已将Teams配置为默认版本。 

若要更改默认安装，请使用[自定义配置文件](/mem/intune/configuration/custom-settings-configure)设置Teams会议模式，如下所示：  

- 模式 0 — 具有 Microsoft Teams 计划会议功能的 Skype for Business。
- 模式 1 - 仅Microsoft Teams。

| 名称 | 描述 | OMA-URI | 类型 | 值 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 应用 ID**|应用名称|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|字符串| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 应用模式**|Teams 模式|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|整型| 0 或 1|



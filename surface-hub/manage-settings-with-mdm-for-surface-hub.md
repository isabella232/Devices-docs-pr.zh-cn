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
ms.date: 03/07/2018
ms.localizationpriority: medium
ms.openlocfilehash: 2bee8b58b7978923c6e60e43f9e10a85dc4bec06
ms.sourcegitcommit: 17170c03206d190851b5f8e794fcc83ebbed7b5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103898"
---
# 使用 MDM 提供程序管理设置 (Surface Hub)

Surface Hub 和其他 Windows10 设备支持 IT 管理员使用移动设备管理 (MDM) 提供程序管理设置和策略。 内置管理组件与管理服务器通信，因此无需在设备上安装其他客户端。 有关详细信息，请参阅 [Windows10 移动设备管理](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx)。

Surface Hub 已通过 Microsoft 的第一方 MDM 提供程序进行验证：
- Microsoft Intune 独立
- Microsoft Endpoint Configuration Manager 的本地 MDM

还可使用通过 MDM 协议与 Windows10 通信的任何第三方 MDM 提供程序管理 Surface Hub。

## <a href="" id="enroll-into-mdm"></a>将 Surface Hub 注册到 MDM 中
你可以使用 "批量"、"手动" 或 "自动注册" 注册 Surface Hub。

### 批量注册
**配置批量注册**
- Surface Hub 支持[预配云解决方案提供商](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx)，可批量注册到 MDM。 有关详细信息，请参阅 [Windows10 批量注册](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx)。<br>
--或--
- 如果你有一个本地 Microsoft 终结点配置管理器基础结构，请参阅 [如何在 Microsoft 终结点配置管理器中使用本地移动设备管理批量注册设备](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm)。

### 手动注册
**配置手动注册**
1. 在 Surface Hub 上，打开**设置**。
2. 请在系统提示时，键入该设备的管理员凭据。
3. 选择**此设备**，然后导航到**设备管理**。
4. 在**设备管理**下，选择 **+ 设备管理**。
5. 按照对话框中的说明操作，连接到 MDM 提供程序。

### 通过 Azure Active Directory 加入自动注册

Surface Hub 现在支持通过将设备加入 Azure Active Directory 来自动注册 Intune。 

第一步是设置自动 MDM 注册。 请参阅 [启用 Windows 10 自动注册](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)。

然后，在首次运行时设置设备时，请选择加入 Azure Active Directory 的选项，请参阅 [设置此设备的管理员页面](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page)

## 使用 MDM 管理 Surface Hub 设置

可使用 MDM 管理某些 [Surface Hub 云解决方案提供商设置](#supported-surface-hub-csp-settings)和 [Windows10 设置](#supported-windows-10-settings)。 可使用内置用户界面或通过部署自定义 SyncML 设置这些设置，具体取决于所使用的 MDM 提供程序。 Microsoft Intune 和 Microsoft 终结点配置管理器提供内置体验，可帮助为 Surface Hub 创建策略模板。 参考 MDM 提供程序中的文档，了解如何创建和部署 SyncML。

### 受支持的 Surface Hub 云解决方案提供商设置

可使用 MDM 配置下表中的 Surface Hub 设置。 该表标识该设置是否受 Microsoft Intune、Microsoft 终结点配置管理器或 SyncML 支持。

有关详细信息，请参阅 [SurfaceHub 配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/mt608323)。 


|                                     设置                                      |                                                    SurfaceHub 云解决方案提供商中的节点                                                    |            支持<br>Intune?             |    支持<br>Configuration Manager?     | 支持<br>SyncML\*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                维护时间                                 |                        MaintenanceHoursSimple/Hours/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       是                        |                       是                       |             是             |
|              使用运动传感器自动打开屏幕               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       是                        |                       是                       |             是             |
|                      需要用于无线投影的 PIN                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       是                        |                       是                       |             是             |
|                            启用无线投影                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       是                        | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                 用于无线投影的 Miracast 通道                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       是                        | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|              连接到 Operations Management Suite 工作区               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       是                        | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                         欢迎屏幕背景图像                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       是                        | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               欢迎屏幕上显示的会议信息                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       是                        | 是。<br> [使用自定义设置。] ( 的示例-管理-surface-集线器-microsoft-终结点-配置管理器 |             是             |
|                      无线投影的友好名称                       |                                                     Properties/FriendlyName                                                      | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                   设备帐户                                                 | DeviceAccount/*`<name_of_policy>`* <br> 请参阅 [SurfaceHub CSP](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)。 |                        否                        |                       否                        |             是             |
|                               指定 Skype 域                               |                                              InBoxApps/SkypeForBusiness/DomainName                                               |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               开始投影时自动启动“连接”应用               |                                                   InBoxApps/Connect/AutoLaunch                                                   |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                                设置默认卷                                |                                                     Properties/DefaultVolume                                                     |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                                设置屏幕超时                                |                                                     Properties/ScreenTimeout                                                     |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                               设置会话超时                                |                                                    Properties/SessionTimeout                                                     |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                                设置睡眠超时                                 |                                                     Properties/SleepTimeout                                                      |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                   允许会话在屏幕空闲后恢复                   |                                                  Properties/AllowSessionResume                                                   |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|             允许设备帐户用于代理身份验证             |                                                  Properties/AllowAutoProxyAuth                                                   |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
| 禁止使用来自计划会议的受邀人自动填充登录对话框 |                                               Properties/DisableSignInSuggestions                                                |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|              在“开始”菜单中禁用“我的会议和文件”功能               |                                              Properties/DoNotShowMyMeetingsAndFiles                                              |                    是 </br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                     为 802.1x 有线身份验证设置 LanProfile                     |                                                         Dot3/LanProfile                                                          | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                    为 802.1x 有线身份验证设置 EapUserData                     |                                                         Dot3/EapUserData                                                         | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。

### 受支持的 Windows 10 设置

除特定于 Surface Hub 的设置外，还有许多设置通用于所有 Windows 10 设备。 这些设置都在[配置服务提供程序参考](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference)中定义。 

下表包含有关通过 Surface Hub 验证的 Windows10 设置的信息。 有一张表介绍以下这些区域的设置：安全、浏览器、Windows 更新、Windows Defender、远程重启、证书和日志。 每个表标识该设置是否受 Microsoft Intune、Microsoft 终结点配置管理器或 SyncML 支持。

#### 安全设置

|      设置       |                                            详细信息                                             |                                                                          CSP 参考                                                                           |            支持<br>Intune?             |    支持<br>Configuration Manager?     | 支持<br>SyncML\*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  允许蓝牙   |                      使其处于启用状态，支持蓝牙外围设备。                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    是。 <br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
| 蓝牙策略 | 用以设置蓝牙设备名称，并阻止广告、发现和自动配对。 |                     蓝牙/*`<name of policy>`* <br> 请参阅[策略 CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                      |                    是。 <br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|    允许照相机    |                           使其在 Skype for Business 中处于启用状态。                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    是。 <br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|   允许位置   |                        使其处于启用状态，支持类似“地图”等应用。                         |                          [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   是。 <br> .                    | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|  允许遥测   |                    使其处于启用状态，帮助 Microsoft 改进 Surface Hub。                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    是。 <br>                     | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|  允许 U 盘  |                     使其处于启用状态，支持 Surface Hub 上的 U 盘                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。 

#### 浏览器设置

|                          设置                          |                                                                        详细信息                                                                        |                                                                             CSP 参考                                                                              |            支持<br>Intune?             |    支持<br>Configuration Manager?     | 支持<br>SyncML\*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         主页                         |                                               用以在 Microsoft Edge 中设置默认主页。                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                       允许 Cookie                       |                    Surface Hub 在会话结束时自动删除 Cookie。 用以在会话中阻止 Cookie。                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                   允许开发人员工具                   |                                                   用以阻止用户使用 F12 开发人员工具。                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                    允许 Do Not Track                     |                                                          用以启用 Do Not Track 标头。                                                          |                          [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                       允许弹出窗口                       |                                                         用以阻止浏览器弹出窗口。                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                 允许搜索建议                  |                                                  用以在地址栏中阻止搜索建议。                                                  |       [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                     允许 Windows Defender SmartScreen                     |                                                       将其启用以启用 Windows Defender SmartScreen。                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
| 阻止忽略网站的 Windows Defender SmartScreen 警告 |     为了获得更高的安全性，请使用阻止用户忽略 Windows Defender SmartScreen 警告并阻止用户访问潜在的恶意网站。     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|  防止忽略文件的 Windows Defender SmartScreen 警告   | 为了获得更高的安全性，请使用阻止用户忽略 Windows Defender SmartScreen 警告并阻止用户从 Microsoft Edge 下载未验证的文件。 | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。

#### Windows 更新设置

|                      设置                      |                                                                                                           详细信息                                                                                                            |                                                                    CSP 参考                                                                    |            支持<br>Intune?             |    支持<br>Configuration Manager?     | 支持<br>SyncML\*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| 使用 Current Branch 或 Current Branch for Business |                                                       用以配置适用于企业的 Windows 更新 – 请参阅 [Windows 更新](manage-windows-updates-for-surface-hub.md)。                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               延迟功能更新               |                                                                                                          请参阅上述内容。                                                                                                          | [Update/ DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               延迟质量更新               |                                                                                                          请参阅上述内容。                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               暂停功能更新               |                                                                                                          请参阅上述内容。                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               暂停质量更新               |                                                                                                          请参阅上述内容。                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|           配置设备以使用 WSUS            |                                            用以将 Surface Hub 连接到 WSUS（而非 Windows 更新）– 请参阅 [Windows 更新](manage-windows-updates-for-surface-hub.md)。                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               传递优化               | 使用对等内容共享减少更新中的带宽问题。 有关详细信息，请参阅[配置 Windows 10 的传递优化](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization)。 |         DeliveryOptimization/*`<name of policy>`* <br> 请参阅[策略 CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)          | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。

#### Windows Defender 设置

|      设置      |                                              详细信息                                               |                                                     CSP 参考                                                      |            支持<br>Intune?             |    支持<br>Configuration Manager?     | 支持<br>SyncML\*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Defender 策略 |            用以配置各种 Defender 设置，包括计划扫描时间。            | Defender/*`<name of policy>`* <br> 请参阅[策略 CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx) | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|  Defender 状态  | 用于启动 Defender 扫描、强制执行安全智能更新、查询检测到的任何威胁。 |                   [Defender 云解决方案提供商](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       是                        |                       是                       |             是             |

\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。

#### 远程重新启动

|                       设置                        |                                                          详细信息                                                          |                                                             CSP 参考                                                             |            支持<br>Intune?             |    支持<br>Configuration Manager?     | 支持<br>SyncML\*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            立即重新启动设备             | 与 OMS 一起使用，将支持成本降到最低 – 请参阅[监视 Microsoft Surface Hub](monitor-surface-hub.md)。 |        ./Vendor/MSFT/Reboot/RebootNow <br> 请参阅[重启 CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)        |                       是                        |                       否                        |             是             |
|    在计划的日期和时间重启设备    |                                                        请参阅上述内容。                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> 请参阅[重启 CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)     | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
| 每天在计划的日期和时间重启设备 |                                                        请参阅上述内容。                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> 请参阅[重启 CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。

#### 安装证书

|             设置             |                           详细信息                            |                                           CSP 参考                                            |                                                         支持<br>Intune?                                                          |                                                                  支持<br>Configuration Manager?                                                                  | 支持<br>SyncML\*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| 安装受信任的 CA 证书 | 用以部署受信任的根证书和中间 CA 证书。 | [RootCATrustedCertificates CSP](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | 是。 <br> 请参阅[配置 Intune 证书配置文件](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles)。 | 是。 <br> 请参阅 [如何在 Microsoft 终结点配置管理器中创建证书配置文件](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles)。 |             是             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。

#### 收集日志

|     设置      |                      详细信息                       |                                     CSP 参考                                      | 支持<br>Intune? | 支持<br>Configuration Manager? | 支持<br>SyncML\*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| 收集 ETW 日志 | 用以远程收集 Surface Hub 的 ETW 日志。 | [DiagnosticLog CSP](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            否             |                    否                    |             是             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。

#### 设置网络服务质量 (QoS) 策略

|        设置         |                                                            详细信息                                                             |                                                    CSP 参考                                                     |            支持<br>Intune?             |    支持<br>Configuration Manager?     | 支持<br>SyncML\*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| 设置网络 QoS 策略 | 用于将 QoS 策略设置为对网络流量执行一组操作。 这对于设置 Skype 网络数据包的优先级很有用。 | [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。

#### 设置网络代理

|      设置      |                               详细信息                               |                                                CSP 参考                                                 |            支持<br>Intune?             |    支持<br>Configuration Manager?     | 支持<br>SyncML\*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| 设置网络代理 | 用于配置以太网和 WLAN 连接的代理服务器。 | [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*还可在 Windows 配置设计器预配程序包中配置 SyncML 支持的设置。

#### 配置“开始”菜单

|       设置        |                                                                       详细信息                                                                        |                                                        CSP 参考                                                         |            支持<br>Intune?             |    支持<br>Configuration Manager?     | 支持<br>SyncML\*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| 配置“开始”菜单 | 用于配置在“开始”菜单上显示的应用类型。 有关详细信息，请参阅[配置 Surface Hub 的“开始”菜单](surface-hub-start-menu.md) | [策略 CSP: 开始/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | 是 <br> [使用自定义策略。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自定义设置。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支持的设置也可以在 Windows 配置设计器预配包中进行配置。

### 生成设置的 OMA URI 
您需要使用设置的 OMA URI 在 Intune 中创建自定义策略，或使用 Microsoft 终结点配置管理器中的自定义设置。

**为云解决方案提供商文档中的任何设置生成 OMA URI**
1. 在云解决方案提供商文档中，标识云解决方案提供商的根节点。 通常，这看起来像 `./Vendor/MSFT/<name of CSP>` <br>
*例如 [SurfaceHub 云解决方案提供商](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)的根节点是 `./Vendor/MSFT/SurfaceHub`。*
2. 标识想要使用的设置的节点路径。 <br>
*例如，启用无线投影的设置的节点路径是 `InBoxApps/WirelessProjection/Enabled`。*
3. 将节点路径附加到根节点，生成 OMA URI。 <br>
*例如，启用无线投影的设置的 OMA URI 是 `./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled`。*

数据类型也在云解决方案提供商文档中作了介绍。 最常见的数据类型有：
- char（字符串）
- int（整数）
- bool（布尔值）


## 示例：使用 Micosoft Intune 管理 Surface Hub 设置

可使用 Microsoft Intune 管理 Surface Hub 设置。 有关自定义设置，请按照[如何在 Microsoft Intune 中配置自定义设备设置](https://docs.microsoft.com/intune/custom-settings-configure)中的说明进行操作。 对于**平台**，请选择**Windows 10 和更高版本**，再在**配置文件类型**中选择**设备限制(Windows 10 协同版)**。



## 示例：通过 Microsoft 终结点配置管理器管理 Surface Hub 设置
配置管理器支持管理不需要 Configuration Manager 客户端管理的新式设备，包括 Surface Hub。 如果你已使用 Configuration Manager 管理你的组织中的其他设备，你可以继续将 Configuration Manager 控制台用作管理 Surface Hub 的单个位置。

> [!NOTE]
> 这些说明基于 Configuration Manager 的当前分支。

**为 Surface Hub 设置创建配置项**

1. 在 Configuration Manager 控制台的**资源和合规性**工作区上，单击**概述** > **合规性设置** > **配置项**。
2. 在**主页**选项卡的**创建**组中，单击**创建配置项**。
3. 在“创建配置项向导”的**常规**页上，为配置项指定名称和可选描述。
4. 在**不使用‘配置管理器’客户端管理的设备设置**下，选择**Windows 8.1 和 Windows 10**，然后单击**下一步**。

    ![UI 示例](images/configmgr-create.png)
5. 在**受支持的平台**页上，展开**Windows 10**，然后选择**所有 Windows 10 协同版和更高版本**。 取消选择其他 Windows 平台，然后单击**下一步**。

    ![选择平台](images/configmgr-platform.png)
7. 在**设备设置**页的**设备设置组**下，选择**Windows 10 协同版**。


8. 在**Windows 10 协同版**页上，配置所需设置。

    ![Windows 10 协同版](images/configmgr-team.png)
9. 管理 Windows 10 协同版页中不可用的设置需要创建自定义设置。 在**设备设置**页上，选中**配置不在默认设置组中的其他设置**复选框。

    ![其他设置](images/configmgr-additional.png)
10. 在**其他设置**页上，单击**添加**。
11. 在**浏览设置**对话框中，单击**创建设置**。
12. 在**创建设置**对话框的**常规**选项卡下，为自定义设置指定名称和可选描述。
13. 在**设置类型**下，选择**OMA URI**。
14. 填写表单，创建新设置，然后单击**确定**。

    ![OMA URI 设置](images/configmgr-oma-uri.png)
15. 在**浏览设置**对话框的**可用设置**下，选择创建的新设置，然后单击**选择**。
16. 在**创建规则**对话框上，填写表单，指定设置规则，然后单击**确定**。
17. 为添加到配置项中的每个自定义设置重复步骤 9 至 15。
18. 完成操作时，在 **浏览设置**对话框上，单击**关闭**。
19. 完成该向导。 <br> 可在**资源和合规性**工作区的**配置项**节点中查看新配置项。

有关详细信息，请参阅为 [没有 Microsoft 终结点配置管理器客户端管理的 windows 8.1 和 windows 10 设备创建配置项目](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client)。

## 相关主题

[管理 Microsoft Surface Hub](manage-surface-hub.md)












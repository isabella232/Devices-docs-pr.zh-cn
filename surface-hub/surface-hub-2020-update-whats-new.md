---
title: Windows 10 协同版 2020 更新中的新增功能
description: 请查看 2020 年 10 月Surface Hub更新中的新增功能Windows 10 协同版更新。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
ms.openlocfilehash: c44ec68a39158910c841375aeda0a6d6bf11635f
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448265"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>Windows 10 协同版 2020 更新中的新增功能

Surface Hub提供新特性和功能的定期更新。 2020 update (20H2) to Windows 10 协同版，以及随后更新 1 & Update 2，对设备部署和可管理性以及最新的 Windows 10 功能进行了重大改进。

## <a name="windows-10-team-2020-update-2"></a>Windows 10 协同版 2020 Update 2 

### <a name="gcc-high-support"></a>GCC高支持

在安装此更新 ([KB5010415](https://support.microsoft.com/help/5010415) 或后续 Windows CU) 后，Surface Hub 在 GCC 高环境中受支持。 目前，[需要执行其他](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h)步骤，Teams 会议室客户端才能成功连接到GCC租户。

### <a name="ease-of-access-updates"></a>轻松使用更新

用户可以在 Surface Hub 会话期间调整"轻松使用"设置，并关闭应用，就像在 Windows 10 的其他版本中一样。 

- **轻松使用**。 用户无需登录即可调整以下设置：显示、文本光标、放大镜、高对比度、讲述人、隐藏式字幕和键盘。 
- **熟悉的应用 UI**。 用户可以通过选择Surface Hub右上角的"关闭"按钮关闭应用。 这样一来，无需通过将其拖动到屏幕底部来关闭Surface Hub应用。  (注意：此功能将在边缘浏览器上作为下一个边缘更新的一部分（计划于 2022 年 3 月进行）提供)  

若要了解更多信息，请参阅"调整"["轻松使用"Surface Hub](accessibility-surface-hub.md)。

### <a name="administrator-updates"></a>管理员更新

- **事件查看器**。 管理员可以直接从 Windows 应用访问 设置 事件查看器。 
- **MDM 的新移动设备管理 (MDM) 策略设置**。 新配置服务提供程序 (SP) 包括：

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

若要了解更多信息，请参阅配置[非全局管理员帐户Surface Hub](surface-hub-2s-nonglobal-admin.md)。


## <a name="windows-10-team-2020-update-1"></a>Windows 10 协同版 2020 Update 1

### <a name="support-for-new-teams-rooms-application"></a>支持新的 Teams 会议室 应用程序

在安装此更新 ([KB5005101](https://support.microsoft.com/help/5005101) 或后续 Windows CU) 后，Surface Hub 支持通过 Windows Update 自动升级到新的 [Teams 会议室](surface-hub-teams-rooms.md) 客户端。

### <a name="support-for-new-whiteboard-application"></a>支持新的白板应用程序

安装此更新后，Surface Hub 支持自动 (更新) 新白板应用[时自动Microsoft Store](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226)升级。

### <a name="new-microsoft-edge-browser-installed-by-default"></a>默认情况下Microsoft Edge新浏览器

安装此更新后，Surface Hub 将自动将其Microsoft Edge 旧版替换为新的基于 Chromium 的边缘浏览器。  若要了解更多信息，请参阅管理[Microsoft Edge Surface Hub](surface-hub-install-chromium-edge.md)。 在安装此更新或后续 Windows 10 协同版 CU 后，Edge Legacy 不再Windows上。


## <a name="windows-10-team-2020-update-20h2"></a>Windows 10 协同版 2020 更新 (20H2)

### <a name="deployment-and-manageability"></a>部署和可管理性

- **云设备帐户的新式验证**。 Surface Hub支持 Exchange Web 服务 (EWS) 和基于 ADAL (ADAL) 的身份验证连接到 Exchange，从而允许客户弃用基本身份验证。 若要了解更多信息，请参阅新式[验证Surface Hub](surface-hub-modern-auth.md)。
- **超过 20 个新的和更新的 MDM 策略设置**。  这些策略设置使 IT 管理员改进了对多个设备设置的控制，包括来自 Microsoft Store 的应用更新、基于基础结构的 Miracast 等无线投影设置、网络设置（如服务质量和 802.1x 有线身份验证）以及新的隐私/GDPR 相关设置。 新的 CSP 包括：

  - [帐户云解决方案提供商](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe 云解决方案提供商](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

若要了解更多，请参阅：

- [支持 CSP Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [通过 MDM 提供商管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory已加入的设备

- **对于已加入 () 设备Azure AD单一登录。** 当用户使用其 Microsoft 365 凭据登录"我的会议"时，**** 他们的凭据将无缝地从应用流到应用，Microsoft 365浏览器中的体验。
- **已加入 (设备) CA Azure AD条件访问**。 IT 管理员可以控制用户从已加入的 Surface Hub Azure AD访问组织资源，按照其公司安全性和合规性要求分配设备策略。
- **对已加入设备的非Azure AD的支持**。 客户可以选择其管理员层次结构中更精细的一组管理员来管理Surface Hub。 若要了解更多信息，请参阅配置[非全局管理员帐户Surface Hub](surface-hub-2s-nonglobal-admin.md)。

### <a name="inking-improvements"></a>墨迹书写改进

- **在 2S 上支持双笔Surface Hub墨迹**书写。  使用白板并使用两个 2 个笔在 Surface Hub 2S 上Surface Hub协作。 升级到 Windows 10 协同版 2020 后安装的任何系统硬件更新都将添加对此方案的固件支持。

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams安装。** Microsoft Teams作为默认应用包含在新的 Surface Hub 设备上用于会议、通话和协作，可通过 MDM 更改或配置这些应用，也可使用 设置 应用直接在 Surface Hub 上进行更改或配置。 若要了解更多信息，请参阅部署[Microsoft Teams](/MicrosoftTeams/teams-surface-hub)。
- **支持使用邻近感应Microsoft Teams**。  Proximity Join 允许用户使用笔记本电脑或Microsoft Teams附近电话Surface Hub安排的呼叫。  它还允许用户将进行中的会议转换为附近的Surface Hub。 Windows 10 协同版 2020 更新添加了移动设备管理 (MDM) 配置邻近感应联接的支持。 若要了解更多，请参阅：

  - [Microsoft Teams博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)。
  - [在 Surface Hub 上管理 Microsoft Teams 设置](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **支持与会议协调Microsoft Teams**。 在具有 Surface Hub 和 Microsoft Teams Room 设备的会议室，或具有两个 Surface Hub 设备的会议室中，协调会议使用户能够在 Microsoft Teams 会议期间快速利用这两台设备。 用户可以通过一次点击从任一设备加入会议，并且可以通过在一台设备上显示视频源和另一台设备上的数字白板或内容来最大化屏幕空间。 Windows 10 协同版 2020 更新添加了移动设备管理 (MDM) 支持以配置协调会议，随后该功能将作为 Microsoft Teams 更新通过 Microsoft Store 发布。 若要了解更多信息，请参阅使用会议和[会议Microsoft Teams 会议室Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings)。

### <a name="security"></a>安全性

- **使用 FIDO2 安全密钥进行无密码登录**使用 FIDO2 安全密钥，用户可以快速登录Surface Hub而无需键入用户名和密码。 与 Single Sign-On (SSO) 结合使用，此功能在会议期间提供对文件、应用和网站的快速无缝身份验证。 若要了解更多信息，请参阅在登录[时配置无密码Surface Hub](surface-hub-2s-phone-authenticate.md)。
- **改进了使用无密码登录Microsoft Authenticator**。  对于使用 Azure AD，用户可以使用 Microsoft Authenticator 应用登录。 此外，用户可以使用他们的首选电子邮件别名登录Azure AD用户主体名称 (UPN) 。 若要了解更多信息，请参阅[使用Surface Hub登录Microsoft Authenticator](surface-hub-authenticator-app.md)。

## <a name="learn-more"></a>了解详细信息

- [Windows 10 协同版 Surface Hub 发布的 2020 更新 1](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 协同版 2020 年 10 月 27 日提供更新](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [安装 Windows 10 协同版 2020 更新](surface-hub-2020-update.md)

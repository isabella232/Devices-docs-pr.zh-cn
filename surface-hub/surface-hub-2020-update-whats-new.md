---
title: 2020 Windows 10 协同版更新中的新增功能
description: 查看 Surface Hub 操作系统的最新更新（Windows 10 协同版 2020 年更新）中的新增功能。
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
ms.openlocfilehash: 995766eb216051de270a387c15c96ee42dd008a3
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497955"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>2020 Windows 10 协同版更新中的新增功能

Surface Hub从提供新功能的定期更新中获益。 2020 年更新 (20H2) Windows 10 协同版，随后更新 1 & Update 2，对设备部署和可管理性以及最新的Windows功能进行了重大改进。

## <a name="windows-10-team-2020-update-2"></a>Windows 10 协同版 2020 年更新 2 

### <a name="gcc-high-support"></a>GCC高支持

安装此更新 ([KB5010415](https://support.microsoft.com/help/5010415) 或后续Windows CU) 后，GCC高环境支持 Surface Hub。 目前，Teams 会议室客户端需要[执行其他步骤](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h)才能成功连接到GCC高租户。

### <a name="support-for-surface-hub-2-smart-camera"></a>支持 Surface Hub 2 智能相机

AI 支持的 Surface Hub 2 智能相机针对混合团队进行了优化，允许远程参与者查看用户与Surface Hub上的内容交互，同时查看会议室中的其他人。  若要了解详细信息，请参阅[安装和管理 Surface Hub 2 智能相机](surface-hub-2-smart-camera.md)。 

### <a name="support-for-progressive-web-apps-pwas"></a>支持渐进式Web 应用 (PVA) 

管理员可以使用移动设备管理提供程序在 Surface Hub 上远程安装 PVA， (MDM) 应用预配包。 若要了解详细信息，请参阅[在Surface Hub上安装渐进式Web 应用](install-pwa-surface-hub.md)。 

### <a name="ease-of-access-updates"></a>轻松访问更新

用户可以在Surface Hub会话期间调整轻松访问设置，并关闭应用，就像在其他版本的Windows 10或Windows 11中一样。 

- **易于访问**。 用户无需登录即可调整以下设置：显示、文本光标、放大镜、高对比度、讲述人、隐藏字幕和键盘。 
- **熟悉的应用 UI**。 用户可以通过选择应用右上角的“关闭”按钮来关闭Surface Hub上的应用。 这将通过将应用拖到Surface Hub显示器底部来消除关闭应用的需要。  (注意：作为定于 2022 年 3 月举行的下一次 Edge 更新的一部分，此功能将在 Edge 浏览器上提供)  

若要了解详细信息，请参阅[Surface Hub上的“调整轻松访问”设置](accessibility-surface-hub.md)。

### <a name="administrator-updates"></a>管理员更新

- **事件查看器**。 管理员可以直接从设置应用访问Windows 事件查看器。 
- **新的移动设备管理 (MDM) 策略设置**。 新的配置服务提供商 (CSP) 包括：

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

若要了解详细信息，请参阅在[Surface Hub上配置非全局管理员帐户](surface-hub-2s-nonglobal-admin.md)。


## <a name="windows-10-team-2020-update-1"></a>Windows 10 协同版 2020 年更新 1

### <a name="support-for-new-teams-rooms-application"></a>对新Teams 会议室应用程序的支持

安装此更新 ([KB5005101](https://support.microsoft.com/help/5005101) 或后续Windows CU) 后，Surface Hub 支持通过Windows 更新自动升级到新[Teams 会议室客户端](surface-hub-teams-rooms.md)。

### <a name="support-for-new-whiteboard-application"></a>支持新的 Whiteboard 应用程序

安装此更新后，Surface Hub 支持在通过Microsoft Store更新) 到新的 [Whiteboard 应用](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226)时自动升级 (。

### <a name="new-microsoft-edge-browser-installed-by-default"></a>默认情况下安装的新Microsoft Edge浏览器

安装此更新后，Surface Hub 会自动将其Microsoft Edge 旧版浏览器替换为新的基于 Chromium 的 Edge 浏览器。  若要了解详细信息，请参阅[Surface Hub上的管理Microsoft Edge](surface-hub-install-chromium-edge.md)。 安装此更新或后续Windows CU 后，Windows 10 协同版上不再提供 Edge Legacy。


## <a name="windows-10-team-2020-update-20h2"></a>Windows 10 协同版 2020 更新 (20H2)

### <a name="deployment-and-manageability"></a>部署和可管理性

- **云设备帐户的新式身份验证**。 Surface Hub支持Exchange Web 服务 (EWS) 和 Active Directory 身份验证库 (基于 ADAL) 的身份验证来连接到Exchange，从而允许客户弃用基本身份验证。 若要了解详细信息，请参阅[有关Surface Hub的新式身份验证](surface-hub-modern-auth.md)。
- **20 多个新的和更新的 MDM 策略设置**。  这些策略设置使 IT 管理员可以改进对多个设备设置的控制，包括来自Microsoft Store的应用更新、无线投影设置，例如基础结构上的Miracast、网络设置（如服务质量和 802.1x 有线身份验证）以及新的隐私/GDPR 相关设置。 新的 CSP 包括：

  - [帐户云解决方案提供商](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe 云解决方案提供商](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

若要了解更多，请参阅：

- [Microsoft Surface Hub支持 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [通过 MDM 提供商管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory联接设备

- **已加入Azure AD设备的单一登录 (SSO) **。 当用户使用其Microsoft 365凭据登录到 **“我的会议和文件**”时，他们的凭据将无缝地从应用流向应用，包括浏览器中的Microsoft 365体验。
- **已加入Azure AD设备的条件访问 (CA) **。 IT 管理员可以通过根据其公司安全性和合规性要求分配设备策略，控制用户从Azure AD加入 Surface Hub 对组织资源的访问。
- **支持加入Azure AD设备的非全局管理员**。 客户可在其管理员层次结构中选择更精细的管理员集来管理Surface Hub。 若要了解详细信息，请参阅在[Surface Hub上配置非全局管理员帐户](surface-hub-2s-nonglobal-admin.md)。

### <a name="inking-improvements"></a>墨迹墨迹改进

- **支持在 Surface Hub 2S 上使用双笔墨迹**。  使用白板，在具有两Surface Hub 2 笔的 Surface Hub 2S 上并排协作。 升级到 Windows 10 协同版 2020 后安装的任何系统硬件更新都将为此方案添加固件支持。

### <a name="microsoft-teams"></a>Microsoft Teams  

- **默认情况下安装Microsoft Teams**。 Microsoft Teams是用于新Surface Hub设备上的会议、呼叫和协作的默认应用，可通过 MDM 更改或配置，也可以使用设置应用直接在Surface Hub上进行配置。 若要了解详细信息，请参阅[“部署Microsoft Teams](/MicrosoftTeams/teams-surface-hub)。
- **支持使用 Microsoft Teams 的邻近加入**。  邻近加入允许用户使用笔记本电脑或手机在附近的Surface Hub进行计划的Microsoft Teams呼叫。  它还允许用户将正在进行的会议转换为附近的Surface Hub。 Windows 10 协同版 2020 更新添加了移动设备管理 (MDM) 支持来配置邻近加入。 若要了解更多，请参阅：

  - [Microsoft Teams博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)。
  - [在 Surface Hub 上管理 Microsoft Teams 设置](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **支持与Microsoft Teams协调会议**。 在具有Surface Hub和Microsoft Teams会议室设备的会议室或具有两个Surface Hub设备的空间中，协调会议可让用户在Microsoft Teams会议期间快速利用这两个设备。 用户可以通过单击一次点击从任一设备加入会议，并通过在一台设备上显示视频源和数字白板或另一台设备上的内容来最大化屏幕空间。 Windows 10 协同版 2020 更新添加了移动设备管理 (MDM) 支持来配置协调会议，该功能随后将作为Microsoft Teams更新通过Microsoft Store发布。 若要了解详细信息，请参阅[使用Microsoft Teams 会议室和Surface Hub设置协调会议](/MicrosoftTeams/rooms/coordinated-meetings)。

### <a name="security"></a>安全性

- **使用 FIDO2 安全密钥进行无密码登录**使用 FIDO2 安全密钥，用户可以快速登录到Surface Hub，而无需键入用户名和密码。 结合单Sign-On (SSO) ，此功能在会议期间为文件、应用和网站提供快速、无缝的身份验证。 若要了解详细信息，请参阅Surface Hub[配置无密码登录](surface-hub-2s-phone-authenticate.md)。
- **使用Microsoft Authenticator改进无密码登录**。  对于使用Azure AD的组织，用户可以使用Microsoft Authenticator应用登录。 此外，用户可以使用其首选电子邮件别名登录Azure AD或用户主体名称 (UPN) 。 若要了解详细信息，请[参阅使用Microsoft Authenticator登录Surface Hub](surface-hub-authenticator-app.md)。

## <a name="learn-more"></a>了解详细信息

- [Windows 10 协同版发布到所有 Surface Hub 的 2020 年更新 1](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 协同版 2020 年 10 月 27 日可用的更新](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [安装 Windows 10 协同版 2020 更新](surface-hub-2020-update.md)

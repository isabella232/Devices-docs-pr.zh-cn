---
title: Windows 10 协同版 2020 更新中的新增功能
description: 请查看 2020 年 Surface Hub 2020 更新的最新更新Windows 10 协同版新增功能。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/19/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 3b9dbf0e4b7412967c3f2c68ddc10a6fccac8907
ms.sourcegitcommit: 4012a9499f658799197fedc7ea1a0c35d6127ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2021
ms.locfileid: "12101219"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Windows 10 协同版 2020 更新中的新增功能

Windows 10 协同版 2020 更新对设备部署和可管理性进行了重大改进以及最新的 Windows 10 功能。

## <a name="deployment-and-manageability"></a>部署和可管理性

- **云设备帐户的新式验证**。 Surface Hub支持 Exchange Web 服务 (EWS) 和基于 ADAL) 的 Active Directory 身份验证库 (连接到 Exchange，从而允许客户弃用基本身份验证。 若要了解更多信息，请参阅新式[验证Surface Hub。](surface-hub-modern-auth.md)
- **MDM 中超过 20 个新的和更新的移动设备 () 策略设置。**  这些策略设置使 IT 管理员改进了对多个设备设置的控制，包括：Microsoft Store 中的应用更新、基于基础结构的 Miracast 等无线投影设置、网络设置（如服务质量和 802.1x 有线身份验证）以及新的隐私/GDPR 相关设置。 新配置服务提供程序 (SP) 包括： 

  - [帐户云解决方案提供商](/windows/client-management/mdm/accounts-csp) 
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp) 
  - [RemoteWipe 云解决方案提供商](/windows/client-management/mdm/remotewipe-csp) 
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp) 
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp) 

若要了解更多，请参阅： 
- [支持 CSP Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [通过 MDM 提供商管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md)

## <a name="azure-active-directory-joined-devices"></a>Azure Active Directory已加入设备

- **对于已加入 () ，** 单一登录Azure AD SSO 帐户。 当用户使用其 Microsoft 365 凭据登录"我的会议和文件"时，他们的用户凭据将无缝地从应用流到应用，Microsoft 365浏览器中的体验。
- **已加入 (设备) 条件**Azure AD CA 配置。 IT 管理员可以根据用户的企业安全性和合规性要求分配设备策略，控制用户Azure AD已加入的 Surface Hub 访问组织资源。
- **支持非全局管理员加入Azure AD设备**。 客户可以在其管理员层次结构中选择一组更精细的管理员来管理Surface Hub。 若要了解更多信息，请参阅在上[配置非全局管理员Surface Hub。](surface-hub-2s-nonglobal-admin.md)

## <a name="browser-and-pen"></a>浏览器和笔

- **默认情况下Microsoft Edge安装的新服务器**。 Microsoft Edge兼容性性能、安全性和隐私性进行了重新生成。 若要了解更多信息，请参阅在 Surface Hub 上[Microsoft Edge管理Surface Hub。](surface-hub-install-chromium-edge.md)
- **2S 上的双笔Surface Hub墨迹**书写。   用户可以使用两个 2 个笔在 Surface Hub 2S 上Surface Hub并协作。 启用双笔墨迹书写所需的固件更新将随后续更新一起发布。

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams安装。**        Microsoft Teams作为默认会议、通话和协作应用包含在新的 Surface Hub 设备上，可通过 MDM 进行更改或配置，或者直接在 Surface Hub 上使用 设置 应用。 若要了解更多信息，请参阅 [[部署Microsoft Teams](/MicrosoftTeams/teams-surface-hub)。
- **支持使用邻近感应Microsoft Teams。**  Proximity Join 使用户能够使用笔记本电脑/电话Microsoft Teams附近会议Surface Hub安排的呼叫，或将进行中的会议无缝转换到附近的会议Surface Hub。 Windows 10 协同版 2020 更新添加了移动设备管理 (MDM) 支持来配置邻近感应联接。 若要了解更多，请参阅： 

  - [Microsoft Teams博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)。 
  - [在 Surface Hub 上管理 Microsoft Teams 设置](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **支持与会议协调Microsoft Teams。** 在具有 Surface Hub 和 Microsoft Teams Room 设备的会议室，或具有两个 Surface Hub 设备的会议室中，协调会议使用户能够在 Microsoft Teams 会议期间轻松利用这两台设备。 通过一次点击，用户可以通过在一台设备上显示视频源，而在其他设备上显示数字白板或内容，从任一设备加入会议并最大化屏幕空间。 Windows 10 协同版 2020 更新添加了移动设备管理 (MDM) 支持以配置协调会议，随后该功能会作为 Microsoft Teams 更新通过 Microsoft Store 发布。若要了解更多信息，请参阅使用 Microsoft Teams 会议室[和 Surface Hub 设置协调Surface Hub。](/MicrosoftTeams/rooms/coordinated-meetings)

## <a name="security"></a>安全性

- **使用 FIDO2 安全密钥进行无密码登录**    使用 FIDO2 安全密钥，客户可以快速轻松地登录Surface Hub而无需键入用户名和密码。 与 Single Sign-On (SSO) 结合使用，此功能在会议期间提供对文件、应用和网站的快速无缝身份验证。 若要了解更多信息，请参阅在 Surface Hub 上[配置无密码登录](surface-hub-2s-phone-authenticate.md)。
- **改进了使用密码登录的无Microsoft Authenticator。**  对于使用 Azure AD，用户可以使用 Microsoft Authenticator 应用登录，而无需键入用户名和密码。 此外，除了用户主体名称或 UPN Azure AD，用户还可以在 (中使用首选电子邮件) 。 若要了解更多信息，请参阅使用 Surface Hub[登录Microsoft Authenticator。](surface-hub-authenticator-app.md)

## <a name="learn-more"></a>了解详细信息

- [Windows 10 协同版所有 Surface Hub 发布的 2020 Update 1](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [安装 Windows 10 协同版 2020 更新](surface-hub-2020-update.md)  
 
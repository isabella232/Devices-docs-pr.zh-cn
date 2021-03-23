---
title: Windows 10 协同版 2020 更新中的新增功能
description: 请查看 Surface Hub 操作系统的最新更新 Windows 10 Team 2020 Update 中的新增功能。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 96452885e19adc9784bb8d14be8ac6f2f86e883d
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442866"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Windows 10 协同版 2020 更新中的新增功能

Windows 10 Team 2020 Update 对设备部署和可管理性以及最新的 Windows 10 功能进行了重大改进。

##  <a name="deployment-and-manageability"></a>部署和可管理性

- **云设备帐户的新式验证**。 Surface Hub 支持 Exchange Web 服务 (EWS) 和基于 ADAL) 的 Active Directory 身份验证库 (ADAL 身份验证连接到 Exchange，从而允许客户弃用基本身份验证。 若要了解更多信息，请参阅 [Surface Hub 上的新式验证](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)。
- **超过 20 个新的和更新的**移动设备管理 (MDM) 策略。      这些策略使 IT 管理员改进了对多个设备设置的控制，包括：来自 Microsoft Store 的应用更新、无线投影设置（如基础结构的 Miracast、网络设置（如服务质量和 802.1x 有线身份验证）以及新的隐私/GDPR 相关设置。 若要了解更多，请参阅： 
- [使用 Microsoft Intune 管理 Surface Hub。](surface-hub-2s-manage-intune.md)
- [Microsoft Surface Hub 支持的策略 CSP](https://docs.microsoft.com//windows/client-management/mdm/policy-csps-supported-by-surface-hub)

##  <a name="azure-active-directory-joined-devices"></a>加入 Azure Active Directory 的设备

- **单一登录 (Azure AD) 的 SSO 帐户**。 当用户使用 Microsoft 365 凭据登录"我的会议和文件"时，他们的用户凭据将无缝地从应用流到应用，包括浏览器中的 Microsoft 365 体验。
- **条件访问 (加入 Azure AD) 设备的条件访问**。       IT 管理员可以将设备级别的安全策略部署到其加入 Azure AD 的 Surface Hub，以根据公司安全性和合规性要求控制对组织资源的访问。
- **支持加入 Azure AD 的设备的非全局管理员**。 客户可以在其管理员层次结构中选择一组更精细的管理员来管理 Surface Hub。 若要了解更多信息，请参阅 [在 Surface Hub 上配置非全局管理员帐户](surface-hub-2s-nonglobal-admin.md)。


## <a name="browser-and-pen"></a>浏览器和笔

- **支持新的 Microsoft Edge**。 Microsoft Edge 已经过重新生成，以实现最佳的兼容性性能、安全性和隐私性。 若要了解更多信息，请参阅在 Surface Hub 上安装和配置[新的 Microsoft Edge。](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)
- **Surface Hub 2S 上的双笔墨迹书写**。   用户可以使用两个 Surface Hub 2 触控笔在 Surface Hub 2S 上并行白板和协作。 启用双笔墨迹书写所需的固件更新将随后续更新一起发布。

## <a name="microsoft-teams"></a>Microsoft Teams  

- **默认安装的 Microsoft Teams**。        Microsoft Teams 作为默认会议、通话和协作应用包含在新的 Surface Hub 设备上，可通过 MDM 更改或配置，或者直接在 Surface Hub 上使用"设置"应用进行更改或配置。 若要了解更多信息，请参阅[部署 Microsoft Teams。](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)
- **支持使用 Microsoft Teams 加入邻近感应**。  Proximity Join 使用户能够使用笔记本电脑/手机在附近的 Surface Hub 上进行安排的 Microsoft Teams 通话，或将正在进行中的会议无缝转换到附近的 Surface Hub。 Windows 10 Team 2020 Update 添加了移动设备管理 (MDM) 配置邻近感应联接的支持。 若要了解更多，请参阅： 

  - [Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)。 
  - [在 Surface Hub 上管理 Microsoft Teams 设置](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **支持与 Microsoft Teams 协调会议**。 在具有 Surface Hub 和 Microsoft Teams 会议室设备的会议室或具有两个 Surface Hub 设备的空间中，协调会议使用户能够在 Microsoft Teams 会议期间轻松利用这两台设备。 通过一次点击，用户可以通过在一台设备上显示视频源和另一台设备上的数字白板或内容，从任一设备加入会议并最大化屏幕空间。 Windows 10 协同版 2020 更新添加了移动设备管理 (MDM) 支持，用于配置协调会议，该功能随后会作为 Microsoft Teams 更新通过 Microsoft Store.To 发布，了解更多信息，请参阅使用 Microsoft Teams 会议室和 [Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)设置协调会议。

## <a name="security"></a>安全

- **使用 FIDO2 安全密钥进行无密码登录**     使用 FIDO2 安全密钥，客户可以快速轻松地登录到 Surface Hub，而无需键入用户名和密码。 与单Sign-On (SSO) 结合使用，此功能在会议期间提供对文件、应用和网站的快速无缝身份验证。 若要了解更多信息，请参阅 [在 Surface Hub 上配置无密码登录](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)。
- **对使用 Microsoft Authenticator 的无密码登录进行了改进**。  对于使用 Azure AD 的组织，用户可以使用 Microsoft Authenticator 应用登录，而无需键入用户名和密码。 此外，用户可以使用 Azure AD 中的首选电子邮件别名以及其用户主体名称 (UPN) 。 若要了解更多信息，请参阅使用[Microsoft Authenticator 登录 Surface Hub。](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)


## <a name="learn-more"></a>了解详细信息

- [Windows 10 协同版推出更新](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [安装 Windows 10 协同版 2020 更新](surface-hub-2020-update.md)  
 
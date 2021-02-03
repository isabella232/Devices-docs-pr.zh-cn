---
title: Windows 10 协同版 2020 更新中的新增功能
description: 查看 Surface Hub 操作系统的最新更新（Windows 10 Team 2020 更新）中的新增功能。
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
ms.openlocfilehash: f87b8f084b8731bfb329b6c52403d565bca03e3e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312048"
---
# Windows 10 协同版 2020 更新中的新增功能

Windows 10 Team 2020 Update 对设备部署和可管理性以及最新的 Windows 10 功能进行了重大改进。

##  部署和可管理性

- **云设备帐户的新式验证**。 Surface Hub 支持 Exchange Web 服务 (EWS) 和基于 ADAL) 的 Active Directory 身份验证库 (ADAL 身份验证连接到 Exchange，从而允许客户弃用基本身份验证。 若要了解更多信息，请参阅 [Surface Hub 上的新式验证](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)。
- **超过 20 个新的和更新**的移动设备管理 (MDM) 策略。      这些策略使 IT 管理员改进了对多个设备设置的控制，包括：来自 Microsoft Store 的应用更新、无线投影设置（如基础结构的 Miracast、网络设置（如服务质量和 802.1x 有线身份验证）以及新的隐私/GDPR 相关设置。 若要了解更多，请参阅： 
- [使用 Microsoft Intune 管理 Surface Hub 2S。](surface-hub-2s-manage-intune.md)
- [Microsoft Surface Hub 支持的策略 CSP](https://docs.microsoft.com//windows/client-management/mdm/policy-csps-supported-by-surface-hub)

##  已加入 Azure Active Directory 的设备

- **对于加入 Azure AD (，) 单**一登录 SSO 帐户。 当用户使用 Microsoft 365 凭据登录"我的会议和文件"时，他们的用户凭据将无缝地在应用之间流动，包括浏览器中的 Microsoft 365 体验。
- **条件访问 (CA) Azure AD 联接设备的条件访问**。       IT 管理员可以将设备级别的安全策略部署到其加入 Azure AD 的 Surface Hub，以根据公司安全性和合规性要求控制对组织资源的访问。
- **支持加入 Azure AD**的设备的非全局管理员。 客户可以在其管理员层次结构中选择一组更精细的管理员来管理 Surface Hub。 若要了解更多信息，请参阅 [在 Surface Hub 2S 上配置非全局管理员帐户](surface-hub-2s-nonglobal-admin.md)。


## 浏览器和笔

- **支持新的 Microsoft Edge**。 为了获得最佳兼容性性能、安全性和隐私，已重新生成 Microsoft Edge。 若要了解更多信息，请参阅在 Surface Hub 上安装和配置[新的 Microsoft Edge。](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)
- - **Surface Hub 2S 上的双笔墨迹书写**。   用户可以使用两个 Surface Hub 2 触控笔在 Surface Hub 2S 上并行白板和协作。 启用双笔墨迹书写所需的固件更新将随后续更新一起发布。

## Microsoft Teams  

- **默认安装的 Microsoft Teams。**        Microsoft Teams 作为默认会议、通话和协作应用包含在新的 Surface Hub 设备上，可通过 MDM 更改或配置，或者直接在 Surface Hub 上使用"设置"应用进行更改或配置。 若要了解更多信息，请参阅[部署 Microsoft Teams。](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)
- **支持使用 Microsoft Teams 进行邻近加入**。  邻近感应联接使用户能够使用笔记本电脑/手机在附近的 Surface Hub 上进行安排的 Microsoft Teams 通话，或将正在进行中的会议无缝转换到附近的 Surface Hub。 Windows 10 Team 2020 Update 添加了移动设备管理 (MDM) 支持来配置邻近感应联接。 若要了解更多，请参阅： 

  - [Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)。 
  - [在 Surface Hub 上管理 Microsoft Teams 设置](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **支持与 Microsoft Teams 协调会议**。 在具有 Surface Hub 和 Microsoft Teams 会议室设备的会议室中，或具有两台 Surface Hub 设备的空格中，协调会议使用户能够在 Microsoft Teams 会议期间轻松利用这两台设备。 通过一次点击，用户可以通过在一台设备上显示视频源和另一台设备上的数字白板或内容，从任一设备加入会议并最大化屏幕空间。 Windows 10 协同版 2020 更新添加了移动设备管理 (MDM) 支持，用于配置协调会议，该功能随后会作为 Microsoft Teams 更新通过 Microsoft Store.To 发布，了解更多信息，请参阅"使用 Microsoft Teams 会议室和 [Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)设置协调会议"。

## 安全性

- **使用 FIDO2 安全密钥进行无密码登录**     使用 FIDO2 安全密钥，客户可以快速轻松地登录到 Surface Hub，而无需键入用户名和密码。 与单一 Sign-On (SSO) 相结合，此功能在会议期间提供对文件、应用和网站的快速而无缝的身份验证。 若要了解更多信息，请参阅 [在 Surface Hub 上配置无密码登录](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)。
- **对使用 Microsoft Authenticator 的无密码登录进行了改进**。  对于使用 Azure AD 的组织，用户可以使用 Microsoft Authenticator 应用登录，而无需键入用户名和密码。 此外，除了用户主体名称 (UPN 帐户之外，用户还可使用 Azure AD 中的首选电子邮件别名) 。 若要了解更多信息，请参阅使用[Microsoft Authenticator 登录 Surface Hub。](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)


## 了解详细信息

- [Windows 10 协同版推出更新](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [安装 Windows 10 协同版 2020 更新](surface-hub-2020-update.md)  
 
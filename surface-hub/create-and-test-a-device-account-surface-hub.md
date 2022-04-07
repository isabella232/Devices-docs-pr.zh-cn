---
title: 创建和测试设备帐户 (Surface Hub)
description: 本主题介绍了如何创建和测试 Microsoft Surface Hub 用于与 Microsoft Exchange 和 Skype 进行通信的设备帐户。
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: 创建和测试设备帐户, 设备帐户, Surface Hub 和 Microsoft Exchange, Surface Hub 和 Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/01/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: c925cb952c7fd04a86d824dfba99a373c07b313e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472621"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>创建和测试设备帐户 (Surface Hub)

创建Surface Hub设备帐户 (也称为资源帐户/会议室邮箱) 允许Surface Hub接收、批准或拒绝会议请求和加入会议。

在Surface Hub上预配设备帐户后，用户可以像邀请会议室一样将此帐户添加到会议邀请中。 

可以在" [现用体验" (OOBE) 设置](first-run-program-surface-hub.md)期间配置设备帐户。 如果需要，还可以稍后在 **设置** > **Surface Hub** >  **Accounts** 中更改它。

## <a name="configuration-overview"></a>配置概述

此表介绍了创建设备帐户时的主要步骤和配置决策。
 
| 步骤 | 描述                     |  用途                             |
|------|---------------------------------|--------------------------------------|
| 1    | 创建启用登录的会议室邮箱 (Exchange Online或Exchange Server 2016 及更高版本)  | 这种类型的邮箱允许设备维护会议日历、接收会议请求和发送邮件。 必须启用登录才能与Surface Hub一起使用。 |
| 2    | 配置邮箱属性 | 必须使用正确的属性配置邮箱，才能在 Surface Hub 上获得最佳会议体验。 有关邮箱属性的详细信息，请参阅[邮箱属性](exchange-properties-for-surface-hub-device-accounts.md)。 |
| 3    | 确保已启用 Exchange Web 服务 (EWS) ，并禁用 MFA)  (多重身份验证 | Surface Hub使用 EWS 同步其日历。 如果默认情况下不允许环境中的 EWS，则中心邮箱需要显式启用它。 由于Surface Hub在没有用户交互的情况下登录到后台Exchange，因此无法响应任何交互式提示，例如 MFA。 创建的设备帐户必须排除在任何此类身份验证要求之外。 否则，Surface Hub 无法同步邮箱和日历信息。 |
| 4    | 为 Teams 或 Skype for Business (Skype for Business Server 2015 及更高版本启用帐户)  | 必须启用Skype for Business或Teams才能使用会议功能，如视频通话和屏幕共享。 有关启用Teams的许可证的详细信息，请[参阅Teams 会议室许可](/MicrosoftTeams/rooms/rooms-licensing)和[Teams服务说明](/office365/servicedescriptions/teams-service-description)。 Surface Hub上的Teams和 SfB 应用程序与需要设备信息 [Azure AD的条件访问策略（](/azure/active-directory/conditional-access/concept-conditional-access-policies)如符合性) ）不兼容 (条件访问策略。 创建的设备帐户必须从任何此类 CA 策略中排除。 否则，Surface Hub无法使用任何会议功能。 |
| 5    | （可选）禁用密码过期 | 为了简化管理，可以关闭设备帐户的密码过期设置，并允许 Surface Hub 自动轮换设备帐户密码。 有关密码管理的详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。  |

> [!NOTE]  
> Surface Hub设备帐户不支持第三方联合标识提供者 (IDP) ，必须通过 Active Directory 或 Azure Active Directory 进行身份验证。

## <a name="detailed-configuration-steps"></a>详细的配置步骤 

设备帐户设置步骤可能因环境而异。 从下表中选择部署方案以查找相应的步骤，并在预配帐户后记下用于配置 Surface Hub 的"格式"列。

| 组织部署             |  描述                  |        设置Surface Hub期间使用的格式
|---------------------------------|--------------------------------------|
| [联机部署 (Microsoft 365) ](/MicrosoftTeams/rooms/with-office-365?tabs=m365-admin-center) |组织的环境完全部署在Microsoft 365上。 | username@domain.com |
| [混合部署 (Exchange本地) ](/MicrosoftTeams/rooms/with-office-365?tabs=exchange-server) | 组织包含多种服务，Exchange Server托管在本地，Microsoft Teams联机。 | username@domain.com 如果在 Exchange 中启用[了混合新式身份验证](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication)，则 DOMAIN\username 否则为 |
| [混合部署 (Exchange Online) ](/skypeforbusiness/deploy/deploy-clients/hybrid-deployments) | 组织包含多种服务，Skype for Business Server托管在本地和Exchange Online。 | username@domain.com 如果在 SfB、DOMAIN\username 中启用 [混合新式身份验证](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) ，则为 ;否则为 |
| [本地部署（单个林）](/skypeforbusiness/deploy/deploy-clients/single-forest-on-premises-deployments) | 组织拥有它控制的服务器，其中 Active Directory、Exchange 和Skype for Business Server托管在单林环境中。  | 域\用户名 |
| [本地部署（多个林）](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | 组织拥有它控制的服务器，其中 Active Directory、Exchange 和Skype for Business Server托管在多林环境中。 | ACCOUNTFOREST\username |

对于联机部署，M365 管理中心中还有一个[直接供Microsoft 365管理员使用的部署向导](https://admin.microsoft.com/Adminportal/Home#/modernonboarding/surfacehubsetupguide)。 此向导可以帮助创建新的设备帐户，或验证现有的资源帐户，以帮助将它们转换为兼容的Surface Hub设备帐户。

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
ms.openlocfilehash: 9d2214453c8cb4c8d03f526dd4ac83264d2a16ad
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676376"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>创建和测试设备帐户 (Surface Hub)

通过创建Surface Hub帐户 (也称为资源帐户/会议室邮箱) ，Surface Hub 可以接收、批准或拒绝会议请求并加入会议。

在设备上设置设备帐户Surface Hub，用户可以将此帐户添加到会议邀请中，方式与邀请会议室的方式相同。 

可以在 OOBE 安装期间配置设备 ([OOBE) 帐户](first-run-program-surface-hub.md)。 如果需要，还可以稍后在"帐户****  >  **"设置Surface Hub**  >  **更改**。

## <a name="configuration-overview"></a>配置概述

此表介绍了创建设备帐户时的主要步骤和配置决策。
 
| 步骤 | 描述                     |  用途                             |
|------|---------------------------------|--------------------------------------|
| 1    | 在 2016 和更高版本 (Exchange Online或Exchange Server启用登录的会议室)  | 此类型的邮箱允许设备维护会议日历、接收会议请求和发送邮件。 必须启用登录才能用于Surface Hub。 |
| 2    | 配置邮箱属性 | 必须使用正确的属性配置邮箱，才能在 Surface Hub 上获得最佳会议体验。 有关邮箱属性的详细信息，请参阅[邮箱属性](exchange-properties-for-surface-hub-device-accounts.md)。 |
| 3    | 确保Exchange EWS (EWS) ，并禁用 MFA (多重) 身份验证 | 该Surface Hub使用 EWS 同步其日历。 如果默认情况下不允许在环境中使用 EWS，则中心邮箱需要显式启用它。 由于Surface Hub登录Exchange用户交互的情况下在后台登录，因此它无法响应任何交互式提示，如 MFA。 你创建的设备帐户必须从任何此类身份验证要求中排除。 否则，Surface Hub 无法同步邮箱和日历信息。 |
| 4    | 为 Teams 2015 Skype for Business (Skype for Business Server及更高版本启用帐户)  | Skype for Business或Teams启用会议功能，如视频呼叫和屏幕共享。 有关启用许可证许可证Teams，请参阅Teams 会议室[许可](/MicrosoftTeams/rooms/rooms-licensing)和服务Teams[说明](/office365/servicedescriptions/teams-service-description)。 Teams上的 Surface Hub 和 SfB 应用程序与需要设备信息（例如合规性 (）的[Azure AD](/azure/active-directory/conditional-access/concept-conditional-access-policies)条件访问策略) 。 你创建的设备帐户必须从任何此类 CA 策略中排除。 否则Surface Hub会议功能。 |
| 5    | （可选）禁用密码过期 | 为了简化管理，可以关闭设备帐户的密码过期设置，并允许 Surface Hub 自动轮换设备帐户密码。 有关密码管理的详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。  |
| 6    |  (可选) 配置Exchange策略以允许 ActiveSync | 对于某些本地部署Exchange Server & Active Directory 部署，ActiveSync 将用于同步设备帐户邮件和日历信息。 有关要配置的策略详细信息，请参阅[ActiveSync policies for Surface Hub accounts](apply-activesync-policies-for-surface-hub-device-accounts.md)。 |

> [!NOTE]  
> Surface Hub设备帐户不支持第三方联合标识提供程序 (IDP) 必须通过 Active Directory 或 Azure Active Directory。

## <a name="detailed-configuration-steps"></a>详细的配置步骤 

我们建议使用远程Surface Hub设置你的 Windows PowerShell。 Microsoft[提供了SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)脚本可帮助创建新的资源帐户或验证你拥有的现有资源帐户，以帮助你将其转换为兼容的Surface Hub帐户。 如果愿意，可以从下表中选择一个选项，并按照基于组织部署的详细 PowerShell 步骤操作。

| 组织部署             |  描述                  |        在设置过程中Surface Hub格式
|---------------------------------|--------------------------------------|
| [联机部署 (Microsoft 365或Office 365) ](/MicrosoftTeams/rooms/with-office-365) |组织的环境完全部署在 Microsoft 365 或 Office 365。 | username@domain.com |
| [混合部署 (Exchange内部部署) ](/MicrosoftTeams/rooms/with-exchange-on-premises) | 你的组织混合了各种服务，Exchange Server内部部署和Microsoft Teams托管。 | username@domain.com 中启用[混合](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication)新式验证，否则Exchange DOMAIN\username |
| [混合部署 (Exchange Online) ](/MicrosoftTeams/rooms/with-exchange-online) | 你的组织混合了各种服务，Skype for Business Server托管在本地和Exchange Online。 | username@domain.com SfB [中启用](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) 混合新式验证，否则为 DOMAIN\username |
| [本地部署（单个林）](/MicrosoftTeams/rooms/with-skype-for-business-server-2015) | 您的组织具有它控制的服务器，其中 Active Directory、Exchange 和 Skype for Business Server托管在单林环境中。  | 域\用户名 |
| [本地部署（多个林）](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | 您的组织具有它控制的服务器，其中 Active Directory、Exchange 和 Skype for Business Server托管在多林环境中。 | ACCOUNTFOREST\username |


## <a name="account-verification-and-testing"></a>帐户验证和测试

有两种方法可用于验证和测试设备帐户[Surface Hub：SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)和Surface Hub[诊断应用](https://www.microsoft.com/store/apps/9nblggh51f2g)。 帐户预配脚本可以从电脑使用 PowerShell 验证之前创建的设备帐户。 Surface Hub 硬件诊断应用安装在 Surface Hub 上，提供有关登录和通信失败的详细反馈。 两种工具在测试新创建的设备帐户时都非常有用，须用于确保帐户可用性达到最佳。

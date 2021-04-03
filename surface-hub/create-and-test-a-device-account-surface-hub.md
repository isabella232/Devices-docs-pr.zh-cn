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
ms.openlocfilehash: 685359f1371a1bef8bd216223a98b934c997a1d8
ms.sourcegitcommit: 879e80200aea26f6705c887fa392db5db35b99ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2021
ms.locfileid: "11475086"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>创建和测试设备帐户 (Surface Hub)

创建 Surface Hub 设备帐户 (也称为资源帐户/会议室邮箱) 允许 Surface Hub 接收、批准或拒绝会议请求并加入会议。

在 Surface Hub 上预配设备帐户后，用户可以将此帐户添加到会议邀请中，方式与邀请会议室的方式相同。 

可以在 OOBE 安装期间配置设备 ([OOBE) 帐户](first-run-program-surface-hub.md)。 如果需要，还可以稍后在设置 Surface Hub**帐户**  >  **中**  >  **更改它**。

## <a name="configuration-overview"></a>配置概述

此表介绍了创建设备帐户时的主要步骤和配置决策。
 
| 步骤 | 描述                     |  用途                             |
|------|---------------------------------|--------------------------------------|
| 1    | 在 Exchange Online 或 Exchange Server 2016 及更高版本 (启用登录的会议室)  | 此类型的邮箱允许设备维护会议日历、接收会议请求和发送邮件。 必须启用登录才能与 Surface Hub 一同使用。 |
| 2    | 配置邮箱属性 | 必须使用正确的属性配置邮箱，才能在 Surface Hub 上获得最佳会议体验。 有关邮箱属性的详细信息，请参阅[邮箱属性](exchange-properties-for-surface-hub-device-accounts.md)。 |
| 3    | 确保已启用 Exchange Web (EWS) ，并禁用了 MFA (多重) 身份验证 | Surface Hub 使用 EWS 同步其日历。 如果默认情况下不允许在环境中使用 EWS，则中心邮箱需要显式启用它。 当 Surface Hub 在后台登录 Exchange 而不需要用户交互时，它无法响应任何交互式提示，如 MFA。 你创建的设备帐户必须从任何此类身份验证要求中排除。 否则，Surface Hub 无法同步邮箱和日历信息。 |
| 4    | 在 Skype for Business Server 2015 及更高版本中 (Teams 或 Skype for Business)  | 必须启用 Skype for Business 或 Teams，以使用视频呼叫、IM 和屏幕共享等会议功能。 有关启用 Teams 的许可证详细信息，请参阅 [Teams 会议室许可](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-licensing) 和 [Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。 |
| 5    | （可选）禁用密码过期 | 为了简化管理，可以关闭设备帐户的密码过期设置，并允许 Surface Hub 自动轮换设备帐户密码。 有关密码管理的详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。  |
| 6    |  (可选) 配置 Exchange 策略以允许 ActiveSync | 对于某些本地 Exchange Server & Active Directory 部署，ActiveSync 将用于同步设备帐户邮件和日历信息。 有关要配置的策略详细信息，请参阅 Surface [Hub 帐户的 ActiveSync 策略](apply-activesync-policies-for-surface-hub-device-accounts.md)。 |

> [!NOTE]  
> Surface Hub 设备帐户不支持第三方联合标识提供程序 (IdPs) 必须通过 Active Directory 或 Azure Active Directory 进行身份验证。

## <a name="detailed-configuration-steps"></a>详细的配置步骤 

我们建议使用远程设备设置 Surface Hub 设备Windows PowerShell。 Microsoft [ 提供了SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)脚本可帮助创建新的资源帐户或验证你拥有的现有资源帐户，以帮助你将其转换为兼容的 Surface Hub 设备帐户。 如果愿意，可以从下表中选择一个选项，并按照基于组织部署的详细 PowerShell 步骤操作。

| 组织部署             |  描述                  |        Surface Hub 设置期间使用的格式
|---------------------------------|--------------------------------------|
| [Microsoft 365 (Office 365 联机部署) ](https://docs.microsoft.com/microsoftteams/rooms/with-office-365) |组织的环境完全部署在 Microsoft 365 或 Office 365 上。 | username@domain.com |
| [混合部署 (Exchange 内部部署) ](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-on-premises) | 你的组织混合了各种服务，Exchange Server本地和 Microsoft Teams 在线托管。 | username@domain.com Exchange 中 [启用混合](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) 新式验证，否则为 DOMAIN\username |
| [Exchange Online (混合) ](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-online) | 你的组织混合了各种服务，Skype for Business Server 托管在本地和 Exchange Online 上。 | username@domain.com SfB [中启用](https://docs.microsoft.com/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) 混合新式验证，否则为 DOMAIN\username |
| [本地部署（单个林）](https://docs.microsoft.com/microsoftteams/rooms/with-skype-for-business-server-2015) | 你的组织具有它控制的服务器，其中 Active Directory、Exchange 和 Skype for Business Server 托管在单林环境中。  | 域\用户名 |
| [本地部署（多个林）](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | 你的组织具有它控制的服务器，其中 Active Directory、Exchange 和 Skype for Business Server 托管在多林环境中。 | ACCOUNTFOREST\username |


## <a name="account-verification-and-testing"></a>帐户验证和测试

有两种方法可用于验证和测试 Surface Hub 设备帐户：SkypeRoomProvisioningScript.ps1[ 和 ](https://go.microsoft.com/fwlink/?linkid=870105) Surface [Hub 硬件诊断应用](https://www.microsoft.com/store/apps/9nblggh51f2g)。 帐户预配脚本可以从电脑使用 PowerShell 验证之前创建的设备帐户。 Surface Hub 硬件诊断应用安装在 Surface Hub 上，提供有关登录和通信失败的详细反馈。 两种工具在测试新创建的设备帐户时都非常有用，须用于确保帐户可用性达到最佳。

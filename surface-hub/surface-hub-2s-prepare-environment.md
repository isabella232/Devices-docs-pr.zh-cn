---
title: 为 Surface Hub 2S 准备环境
description: 了解为 Surface Hub 2S 准备环境需要执行哪些工作。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 2/26/2021
ms.localizationpriority: Medium
ms.openlocfilehash: caa6372820222f6f2f225f028161b3441b147a82
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385140"
---
# <a name="prepare-your-environment-for-surface-hub-2s"></a>为 Surface Hub 2S 准备环境

## <a name="office-365-readiness"></a>Office 365 准备情况

如果使用 Exchange Online、Skype for Business Online、Microsoft Teams 或 Microsoft Whiteboard，并且打算使用 Intune 管理 Surface Hub 2S，请首先查看终结点的 [Office 365 要求](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)。

Office 365 终结点通过防火墙直接发送所有受信任的 Office 365 网络请求，绕过其他所有数据包级别检查或处理，帮助优化网络。 此功能可减少延迟和外围容量要求。

Microsoft 会定期更新 Office 365 服务，其中新增了一些特性和功能，可能会更改所需的端口、URL 和 IP 地址。 若要评估、配置和随时了解最新更改，请订阅 [Office 365 IP 地址和 URL Web 服务](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。

> [!NOTE]
> Surface Hub 适用于 Microsoft Teams、Skype for Business Server 2019、Skype for Business Server 2015 或 Skype for Business Online。
不支持早期平台，如 Lync Server 2013。 Surface Hub 在 GCC-High 或 DoD 环境中不受支持。


## <a name="device-affiliation"></a>设备附属关系

使用设备附属关系管理用户对 Surface Hub 2S 上的"设置"应用的访问权限。
使用在 Surface Hub 2S (上运行的 Windows 10 团队) ，只有授权用户可以使用"设置"应用调整设置。 由于选择附属关系可能会影响功能可用性，请进行相应规划以确保用户可以访问预期的功能。

> [!NOTE]
> 只能在初始开箱即用体验期间设置设备附属 (OOBE) 设置。 如果需要重置设备附属关系，必须重复 OOBE 设置。

## <a name="no-affiliation"></a>无附属关系

没有任何附属关系，就像在每个 Surface Hub 2S 上将 Surface Hub 2S 放在具有不同本地管理员帐户的工作组中。 如果选择"不附属关系"，则必须本地将 [BitLocker 密钥保存到 U 盘](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)。 你仍然可以使用 Intune 注册设备;但是，只有本地管理员可以使用 OOBE 期间配置的帐户凭据访问"设置"应用。 可以从"设置"应用更改管理员帐户密码。

## <a name="active-directory-domain-services"></a>Active Directory 域服务

如果将 Surface Hub 2S 与本地 Active Directory 域服务关联，则需要使用域中的安全组管理对"设置"应用的访问权限。 这有助于确保所有安全组成员都有权更改 Surface Hub 2S 上的设置。 另请注意以下事项：

- 当 Surface Hub 2S 与本地 Active Directory 域服务关联时，BitLocker 密钥可以保存在 Active Directory 架构中。 有关详细信息，请参阅 [为组织准备 BitLocker：规划和策略](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。

- 组织的受信任根 AS 被推送到 Surface Hub 2S 中的同一容器，这意味着你无需使用预配包导入它们。

- 你仍然可以使用 Intune 注册设备，以集中管理 Surface Hub 2S 上的设置。

## <a name="azure-active-directory"></a>Azure Active Directory

当你选择将 Surface Hub 2S 与 Azure Active Directory (Azure AD) 关联时，全局管理员安全组的任何用户都可以登录到 Surface Hub 2S 上的"设置"应用。 还可以配置非全局管理员帐户，以限制对 Surface Hub 2S 上"设置"应用的管理权限。 这使你能够仅确定 Surface Hub 2S 的管理员权限范围，并在整个 Azure AD 域中阻止可能不需要的管理员访问权限。 

如果你为组织启用了 Intune 自动注册，Surface Hub 2S 将自动在 Intune 中注册自身。 设备的 BitLocker 密钥会自动保存在 Azure AD 中。 

若要了解有关使用 Azure AD 管理 Surface Hub 的信息，请参阅： 

 - [管理员组管理](admin-group-management-for-surface-hub.md)
 - [配置 Surface Hub 2 上的非全局管理员帐户](surface-hub-2s-nonglobal-admin.md)


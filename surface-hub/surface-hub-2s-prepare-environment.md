---
title: 为 Surface Hub 2S 准备环境
description: 了解为 Surface Hub 2 准备环境需要执行哪些操作。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/21/2019
ms.localizationpriority: Medium
ms.openlocfilehash: dddab2adce1bec9ff722a3324b9c4b1be609ae89
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934842"
---
# 为 Surface Hub 2S 准备环境

## Office 365 准备情况

如果您使用的是 Exchange Online、Skype for Business Online、Microsoft 团队或 Microsoft 白板，并且想要使用 Intune 管理 Surface Hub 2，请首先查看 [终结点的 Office 365 要求](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)。

Office 365 终结点通过防火墙直接发送所有受信任的 Office 365 网络请求来帮助优化你的网络，绕过所有其他数据包级别的检查或处理。 此功能可减少延迟和外围容量需求。

Microsoft 定期用新的功能和功能更新 Office 365 服务，这些功能可能会改变所需的端口、Url 和 IP 地址。 若要评估、配置和保持最新的更改，请订阅 [Office 365 IP 地址和 URL Web 服务](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。

## 设备附属关系

使用设备从属关系管理用户访问 Surface Hub 2 上的 "设置" 应用。
通过在 Surface Hub 2) 上运行的 Windows 10 Team 操作系统 (，只有授权用户可以使用 "设置" 应用调整设置。 由于选择 "隶属关系" 可能会影响功能的可用性，请适当规划以确保用户可以按预期访问功能。

> [!NOTE]
> 仅在 OOBE) 设置 (的初始全新体验期间，才能设置设备从属关系。 如果需要重置设备从属关系，则必须重复 OOBE 设置。

## 无隶属关系

没有任何关系，就像在每个 Surface Hub 2 的不同本地管理员帐户的工作组中使用 Surface Hub 2。 如果选择 "无关系"，则必须在本地将 [BitLocker 密钥保存到 USB 拇指驱动器](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)。 你仍可以通过 Intune 注册设备;但是，只有本地管理员才能使用在 OOBE 期间配置的帐户凭据访问 "设置" 应用。 您可以从 "设置" 应用更改管理员帐户密码。

## Active Directory 域服务

如果将 Surface Hub 2 与本地 Active Directory 域服务关联，则需要使用域上的安全组管理对设置应用的访问权限。 这有助于确保所有安全组成员都有权更改 Surface Hub 2 上的设置。 另请注意以下事项：

- 当 Surface Hub 2 和你的本地 Active Directory 域服务的联盟时，BitLocker 密钥可以保存在 Active Directory 架构中。 有关详细信息，请参阅 [为 BitLocker 准备组织：计划和策略](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。 
- 组织的受信任根 Ca 被推送到 Surface Hub 2 中的相同容器，这意味着无需使用预配包导入。
- 你仍然可以向 Intune 注册设备，以便集中管理 Surface Hub 2 上的设置。

## Azure Active Directory

当你选择将 Surface Hub 2 与 Azure Active Directory (Azure AD) 关联时，全局管理员安全组中的任何用户都可以登录 Surface Hub 2 上的 "设置" 应用。 当前，不能委派任何其他组登录 Surface Hub 2 的设置应用。

如果为你的组织启用了 Intune 自动注册，Surface Hub 2 将自动向 Intune 注册自己。 设备的 BitLocker 密钥会自动保存在 Azure AD 中。 当 affiliating Surface Hub 2 与 Azure AD 一起使用时，单一登录和轻松身份验证将不起作用。

---
title: Surface Hub 新式身份验证
description: 此页介绍在 Surface Hub 上使用新式验证与传统基本身份验证的对比。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 3873d0ac7ffff3fa790f44b474d937772e5a0900
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474759"
---
# <a name="modern-authentication-on-surface-hub"></a>Surface Hub 新式身份验证

Windows 10 Team 2020 更新在某些情况下增加了对中心设备帐户的新式验证的支持。 安装 2020 更新后，如果设备帐户通过 Azure Active Directory 进行身份验证并且帐户邮箱托管在 Exchange Online 中，可以从传统基本身份验证迁移，以使用最新的安全改进。 通过 2020 更新，Surface Hub 在将设备帐户与 Exchange Online 同步时支持 Exchange Web 服务 (EWS) 协议和基于 ADAL) 的 Active Directory 身份验证库 (。

对于新的基于云的帐户，Surface Hub 自动使用新式验证连接到 Exchange Online，无需其他配置，只需使用 alias@contoso.com 格式将设备帐户 [添加到 Surface](mailto:alias@contoso.com)Hub 即可。 请勿使用旧格式 -Contoso\alias，新式验证不支持这种格式。 有关详细信息，请参阅 [创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md)。

> [!NOTE]
> 本地 Surface Hub 帐户不支持新式验证。 帐户只能使用 Azure AD 进行身份验证。

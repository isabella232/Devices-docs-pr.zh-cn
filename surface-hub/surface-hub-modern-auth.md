---
title: Surface Hub 新式身份验证
description: 本页介绍在 Surface Hub 上使用新式验证与旧式基本身份验证相比。
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
ms.openlocfilehash: 1674b7abd74a666e2ab1040f66d9ea548ab3c201
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385160"
---
# <a name="modern-authentication-on-surface-hub"></a>Surface Hub 新式身份验证

在某些情况下，Windows 10 团队 2020 更新增加了对中心设备帐户的新式验证的支持。 安装 2020 更新后，如果设备帐户通过 Azure Active Directory 进行身份验证，并且帐户的邮箱托管在 Exchange Online 中，可以从传统基本身份验证迁移以使用最新的安全改进。 通过 2020 更新，Surface Hub 在将设备帐户与 Exchange Online 同步时支持 Exchange Web 服务 (EWS) 协议和基于 Active Directory 身份验证库 (ADAL) 的身份验证。

对于新的基于云的帐户，Surface Hub 自动使用新式验证连接到 Exchange Online，而无需进行额外配置，而只需使用 alias@contoso.com 格式 [创建设备帐户](mailto:alias@contoso.com)。 请勿使用旧版格式 -Contoso\alias，新式验证不支持这种格式。 有关详细信息，请参阅创建 [Surface Hub 2S 设备帐户](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。

> [!NOTE]
> Surface Hub 不支持内部部署帐户的新式验证。 必须在云中创建帐户。


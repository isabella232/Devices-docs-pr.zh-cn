---
title: Surface Hub 上的新式验证
description: 此页面介绍了与传统基本身份验证相比，Surface Hub 上的新式身份验证的使用。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 387d799e15ae25bb1043e9ee3417aa3c31676825
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893129"
---
# Surface Hub 上的新式验证

对基于云的帐户的新式验证的支持在 Windows 10 Team 2020 更新中完全集成，使你可以从旧的基本身份验证进行迁移并利用 Microsoft Azure 和 Exchange Online 中的最新安全改进。 通过2020更新，Surface Hub 支持 Exchange Web 服务（EWS）协议和基于 Active Directory 身份验证库（ADAL）的身份验证，从而支持 Exchange Online 设备帐户同步。

对于基于云的新帐户，Surface Hub 会自动使用新式身份验证连接到 Exchange Online，而不只是使用[alias@contoso.com](mailto:alias@contoso.com)格式创建设备帐户，而无需额外配置。 请勿使用旧格式-Contoso\alias，这对于新式验证不受支持。 有关详细信息，请参阅[创建 Surface Hub 2 版设备帐户](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。

> [!NOTE]
> Surface Hub 不支持本地帐户的新式验证。 必须在云中创建帐户。


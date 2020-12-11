---
title: Surface Hub 新式身份验证
description: 此页介绍在 Surface Hub 上使用新式验证与旧式基本身份验证不同。
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
ms.openlocfilehash: dd0b0ad257abbc52c443b075e62db00dcf5713ea
ms.sourcegitcommit: 4b1cfcac090910a3ea634929942063eb51fc54f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "11206276"
---
# Surface Hub 新式身份验证

对基于云的帐户的新式验证的支持完全集成在 Windows [10 Team 2020 Update 中](surface-hub-2020-update.md)。 安装 2020 更新后，可以从旧式基本身份验证迁移，并使用 Microsoft Azure 和 Exchange Online 的最新安全改进。 通过 2020 更新，Surface Hub 支持 Exchange Web 服务 (EWS) 协议和基于 ADAL) 的基于 ADAL (的身份验证，从而启用 Exchange Online 设备帐户同步。

对于新的基于云的帐户，Surface Hub 自动使用新式验证连接到 Exchange Online，除了只需使用 alias@contoso.com 格式创建设备帐户[之外，还需要其他alias@contoso.com。](mailto:alias@contoso.com) 请勿使用旧格式 -Contoso\alias，新式验证不支持这种格式。 有关详细信息，请参阅创建 [Surface Hub 2S 设备帐户](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。

> [!NOTE]
> Surface Hub 不支持内部部署帐户的新式验证。 必须在云中创建帐户。


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
# <span data-ttu-id="c61fa-104">Surface Hub 新式身份验证</span><span class="sxs-lookup"><span data-stu-id="c61fa-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="c61fa-105">对基于云的帐户的新式验证的支持完全集成在 Windows [10 Team 2020 Update 中](surface-hub-2020-update.md)。</span><span class="sxs-lookup"><span data-stu-id="c61fa-105">Support for modern authentication of cloud-based accounts is fully integrated in [Windows 10 Team 2020 Update](surface-hub-2020-update.md).</span></span> <span data-ttu-id="c61fa-106">安装 2020 更新后，可以从旧式基本身份验证迁移，并使用 Microsoft Azure 和 Exchange Online 的最新安全改进。</span><span class="sxs-lookup"><span data-stu-id="c61fa-106">Once you install the 2020 update, you can migrate from legacy basic authentication and use the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="c61fa-107">通过 2020 更新，Surface Hub 支持 Exchange Web 服务 (EWS) 协议和基于 ADAL) 的基于 ADAL (的身份验证，从而启用 Exchange Online 设备帐户同步。</span><span class="sxs-lookup"><span data-stu-id="c61fa-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="c61fa-108">对于新的基于云的帐户，Surface Hub 自动使用新式验证连接到 Exchange Online，除了只需使用 alias@contoso.com 格式创建设备帐户[之外，还需要其他alias@contoso.com。](mailto:alias@contoso.com)</span><span class="sxs-lookup"><span data-stu-id="c61fa-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="c61fa-109">请勿使用旧格式 -Contoso\alias，新式验证不支持这种格式。</span><span class="sxs-lookup"><span data-stu-id="c61fa-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="c61fa-110">有关详细信息，请参阅创建 [Surface Hub 2S 设备帐户](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。</span><span class="sxs-lookup"><span data-stu-id="c61fa-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="c61fa-111">Surface Hub 不支持内部部署帐户的新式验证。</span><span class="sxs-lookup"><span data-stu-id="c61fa-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="c61fa-112">必须在云中创建帐户。</span><span class="sxs-lookup"><span data-stu-id="c61fa-112">The accounts must be created in the cloud.</span></span>


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
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="32af9-104">Surface Hub 新式身份验证</span><span class="sxs-lookup"><span data-stu-id="32af9-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="32af9-105">在某些情况下，Windows 10 团队 2020 更新增加了对中心设备帐户的新式验证的支持。</span><span class="sxs-lookup"><span data-stu-id="32af9-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="32af9-106">安装 2020 更新后，如果设备帐户通过 Azure Active Directory 进行身份验证，并且帐户的邮箱托管在 Exchange Online 中，可以从传统基本身份验证迁移以使用最新的安全改进。</span><span class="sxs-lookup"><span data-stu-id="32af9-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="32af9-107">通过 2020 更新，Surface Hub 在将设备帐户与 Exchange Online 同步时支持 Exchange Web 服务 (EWS) 协议和基于 Active Directory 身份验证库 (ADAL) 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="32af9-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="32af9-108">对于新的基于云的帐户，Surface Hub 自动使用新式验证连接到 Exchange Online，而无需进行额外配置，而只需使用 alias@contoso.com 格式 [创建设备帐户](mailto:alias@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="32af9-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="32af9-109">请勿使用旧版格式 -Contoso\alias，新式验证不支持这种格式。</span><span class="sxs-lookup"><span data-stu-id="32af9-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="32af9-110">有关详细信息，请参阅创建 [Surface Hub 2S 设备帐户](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。</span><span class="sxs-lookup"><span data-stu-id="32af9-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="32af9-111">Surface Hub 不支持内部部署帐户的新式验证。</span><span class="sxs-lookup"><span data-stu-id="32af9-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="32af9-112">必须在云中创建帐户。</span><span class="sxs-lookup"><span data-stu-id="32af9-112">The accounts must be created in the cloud.</span></span>


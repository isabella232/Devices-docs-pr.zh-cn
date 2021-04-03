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
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="c3401-104">Surface Hub 新式身份验证</span><span class="sxs-lookup"><span data-stu-id="c3401-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="c3401-105">Windows 10 Team 2020 更新在某些情况下增加了对中心设备帐户的新式验证的支持。</span><span class="sxs-lookup"><span data-stu-id="c3401-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="c3401-106">安装 2020 更新后，如果设备帐户通过 Azure Active Directory 进行身份验证并且帐户邮箱托管在 Exchange Online 中，可以从传统基本身份验证迁移，以使用最新的安全改进。</span><span class="sxs-lookup"><span data-stu-id="c3401-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="c3401-107">通过 2020 更新，Surface Hub 在将设备帐户与 Exchange Online 同步时支持 Exchange Web 服务 (EWS) 协议和基于 ADAL) 的 Active Directory 身份验证库 (。</span><span class="sxs-lookup"><span data-stu-id="c3401-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="c3401-108">对于新的基于云的帐户，Surface Hub 自动使用新式验证连接到 Exchange Online，无需其他配置，只需使用 alias@contoso.com 格式将设备帐户 [添加到 Surface](mailto:alias@contoso.com)Hub 即可。</span><span class="sxs-lookup"><span data-stu-id="c3401-108">For new cloud-based accounts, the Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply adding the device account to the Surface Hub using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="c3401-109">请勿使用旧格式 -Contoso\alias，新式验证不支持这种格式。</span><span class="sxs-lookup"><span data-stu-id="c3401-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="c3401-110">有关详细信息，请参阅 [创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="c3401-110">For more information, see [create and test a device account](create-and-test-a-device-account-surface-hub.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c3401-111">本地 Surface Hub 帐户不支持新式验证。</span><span class="sxs-lookup"><span data-stu-id="c3401-111">Modern authentication is not supported for on-premises Surface Hub accounts.</span></span> <span data-ttu-id="c3401-112">帐户只能使用 Azure AD 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c3401-112">The accounts must use only Azure AD for authentication.</span></span>

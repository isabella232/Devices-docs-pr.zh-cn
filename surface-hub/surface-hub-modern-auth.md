---
title: Surface Hub 新式身份验证
description: 此页面介绍了与传统基本身份验证相比，Surface Hub 上的新式身份验证的使用。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 14be433923ca564123952c2d1d7b1c158e725af3
ms.sourcegitcommit: d24759da42dfe0b913fd9ebf716407a673c2b818
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004464"
---
# <span data-ttu-id="dda6e-104">Surface Hub 新式身份验证</span><span class="sxs-lookup"><span data-stu-id="dda6e-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="dda6e-105">在即将推出的 Windows 10 Team 2020 更新中，通过 [windows 预览体验计划](https://insider.windows.com/)提供的预览版可完全集成基于云帐户的新式验证。</span><span class="sxs-lookup"><span data-stu-id="dda6e-105">Support for modern authentication of cloud-based accounts is fully integrated in the upcoming Windows 10 Team 2020 Update, with preview builds available from the [Windows Insider Program](https://insider.windows.com/).</span></span> <span data-ttu-id="dda6e-106">[安装预览版本](surface-hub-install-2020preview.md)后，您可以从旧版基本身份验证迁移，并利用 Microsoft Azure 和 Exchange Online 中的最新安全改进功能。</span><span class="sxs-lookup"><span data-stu-id="dda6e-106">Once you [install the preview build](surface-hub-install-2020preview.md), you can migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="dda6e-107">通过2020更新，Surface Hub 支持 Exchange Web 服务 (EWS) 协议和 Active Directory 身份验证库 (ADAL) 基于设备帐户同步的 Exchange Online 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="dda6e-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="dda6e-108">对于基于云的新帐户，Surface Hub 会自动使用新式身份验证连接到 Exchange Online，而不只是使用 [alias@contoso.com](mailto:alias@contoso.com)格式创建设备帐户，而无需额外配置。</span><span class="sxs-lookup"><span data-stu-id="dda6e-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="dda6e-109">请勿使用旧格式-Contoso\alias，这对于新式验证不受支持。</span><span class="sxs-lookup"><span data-stu-id="dda6e-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="dda6e-110">有关详细信息，请参阅 [创建 Surface Hub 2 版设备帐户](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。</span><span class="sxs-lookup"><span data-stu-id="dda6e-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="dda6e-111">Surface Hub 不支持本地帐户的新式验证。</span><span class="sxs-lookup"><span data-stu-id="dda6e-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="dda6e-112">必须在云中创建帐户。</span><span class="sxs-lookup"><span data-stu-id="dda6e-112">The accounts must be created in the cloud.</span></span>


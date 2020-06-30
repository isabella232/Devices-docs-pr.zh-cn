---
title: 密码管理 (Surface Hub)
description: 每个 Microsoft Surface Hub 设备帐户都需要密码才能进行身份验证并启用设备上的功能。
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: 密码, 密码管理, 密码轮换, 设备帐户
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832067"
---
# <span data-ttu-id="d584b-104">密码管理 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="d584b-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="d584b-105">每个 Microsoft Surface Hub 设备帐户都需要密码才能进行身份验证并启用设备上的功能。</span><span class="sxs-lookup"><span data-stu-id="d584b-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="d584b-106">出于安全原因，你可能想要定期更改（或“轮换”）此密码。</span><span class="sxs-lookup"><span data-stu-id="d584b-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="d584b-107">但是，如果更改了设备帐户密码，之前存储在 Surface Hub 上的密码将失效，并且依赖该设备帐户的所有功能都将禁用。</span><span class="sxs-lookup"><span data-stu-id="d584b-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="d584b-108">可通过“设置”应用更新 Surface Hub 上的设备帐户密码，以便重新启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="d584b-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="d584b-109">有两个选项可简化 Surface Hub 设备帐户密码的管理事宜：</span><span class="sxs-lookup"><span data-stu-id="d584b-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="d584b-110">关闭设备帐户密码过期。</span><span class="sxs-lookup"><span data-stu-id="d584b-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="d584b-111">允许 Surface Hub 自动轮换设备帐户密码。</span><span class="sxs-lookup"><span data-stu-id="d584b-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <span data-ttu-id="d584b-112">为设备帐户关闭密码轮换</span><span class="sxs-lookup"><span data-stu-id="d584b-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="d584b-113">将设备帐户的 **PasswordNeverExpires** 属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="d584b-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="d584b-114">应验证此操作是否满足组织的安全要求。</span><span class="sxs-lookup"><span data-stu-id="d584b-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <span data-ttu-id="d584b-115">允许 Surface Hub 自动轮换设备帐户密码</span><span class="sxs-lookup"><span data-stu-id="d584b-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="d584b-116">Surface Hub 可通过经常更改设备帐户密码来对其进行管理，无需手动更新设备帐户信息。</span><span class="sxs-lookup"><span data-stu-id="d584b-116">The Surface Hub can manage a device account’s password by changing it frequently without requiring you to manually update the device account’s information.</span></span> <span data-ttu-id="d584b-117">可在“设置” \*\*\*\* 中启用此功能。</span><span class="sxs-lookup"><span data-stu-id="d584b-117">You can enable this feature in **Settings**.</span></span> <span data-ttu-id="d584b-118">启用后，设备帐户密码在维护时间内将每周进行更改。</span><span class="sxs-lookup"><span data-stu-id="d584b-118">Once enabled, the device account's password will change weekly during maintenance hours.</span></span>

<span data-ttu-id="d584b-119">注意设备帐户的密码发生更改时，将不会向用户显示新密码。</span><span class="sxs-lookup"><span data-stu-id="d584b-119">Note that when the device account’s password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="d584b-120">如果用户需要登录帐户或重新提供密码（例如，如果希望更改 Surface Hub 上的设备帐户设置），需要使用 Active Directory 或 Office 365 管理员门户重置密码。</span><span class="sxs-lookup"><span data-stu-id="d584b-120">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Office 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d584b-121">如果组织使用混合拓扑（某些服务是本地托管，而某些是通过 Office 365 联机托管），则必须按“域\用户名”\*\*\*\* 格式设置设备帐户。</span><span class="sxs-lookup"><span data-stu-id="d584b-121">If your organization uses a hybrid topology (some services are hosted on-premises and some are hosted online through Office 365), you must setup the device account in **domain\username** format.</span></span> <span data-ttu-id="d584b-122">否则，密码轮换将没有效果。</span><span class="sxs-lookup"><span data-stu-id="d584b-122">Otherwise, password rotation will not work.</span></span>

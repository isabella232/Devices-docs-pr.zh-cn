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
ms.openlocfilehash: 215736527121306c712932f57a5a3a853fb3bb20
ms.sourcegitcommit: 366eedceb9f859f5e87ba032b161f248360cb895
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445578"
---
# <a name="password-management-surface-hub"></a><span data-ttu-id="d6164-104">密码管理 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="d6164-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="d6164-105">每个 Microsoft Surface Hub 设备帐户都需要密码才能进行身份验证并启用设备上的功能。</span><span class="sxs-lookup"><span data-stu-id="d6164-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="d6164-106">出于安全原因，你可能想要定期更改（或“轮换”）此密码。</span><span class="sxs-lookup"><span data-stu-id="d6164-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="d6164-107">但是，如果更改了设备帐户密码，之前存储在 Surface Hub 上的密码将失效，并且依赖该设备帐户的所有功能都将禁用。</span><span class="sxs-lookup"><span data-stu-id="d6164-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="d6164-108">可通过“设置”应用更新 Surface Hub 上的设备帐户密码，以便重新启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="d6164-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="d6164-109">有两个选项可简化 Surface Hub 设备帐户密码的管理事宜：</span><span class="sxs-lookup"><span data-stu-id="d6164-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="d6164-110">关闭设备帐户密码过期。</span><span class="sxs-lookup"><span data-stu-id="d6164-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="d6164-111">允许 Surface Hub 自动轮换设备帐户密码。</span><span class="sxs-lookup"><span data-stu-id="d6164-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <a name="turn-off-password-rotation-for-the-device-account"></a><span data-ttu-id="d6164-112">为设备帐户关闭密码轮换</span><span class="sxs-lookup"><span data-stu-id="d6164-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="d6164-113">将设备帐户的 **PasswordNeverExpires** 属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="d6164-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="d6164-114">应验证此操作是否满足组织的安全要求。</span><span class="sxs-lookup"><span data-stu-id="d6164-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a><span data-ttu-id="d6164-115">允许 Surface Hub 自动轮换设备帐户密码</span><span class="sxs-lookup"><span data-stu-id="d6164-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="d6164-116">Surface Hub 可以自动更改设备帐户的密码，而无需手动更新它。</span><span class="sxs-lookup"><span data-stu-id="d6164-116">The Surface Hub can automatically change a device account's password without requiring you to manually update it.</span></span> <span data-ttu-id="d6164-117">可以在设置 Surface Hub 帐户**中**  >  **启用**  >  **此功能**。</span><span class="sxs-lookup"><span data-stu-id="d6164-117">You can enable this feature in **Settings** > **Surface Hub** > **Accounts**.</span></span> <span data-ttu-id="d6164-118">如果打开"密码轮换"，Surface Hub 将尝试在维护期间每 7 天更改一次密码。</span><span class="sxs-lookup"><span data-stu-id="d6164-118">If you turn on Password Rotation, the Surface Hub will attempt to change the password every 7 days during maintenance hours.</span></span> <span data-ttu-id="d6164-119">会议期间不会更改密码。</span><span class="sxs-lookup"><span data-stu-id="d6164-119">Passwords do not change during a meeting.</span></span> <span data-ttu-id="d6164-120">如果自上次密码轮换以来已过去 7 天，但 Surface Hub 已关闭，它将尝试在打开后立即更改密码，或者每隔 10 分钟更改一次密码，直到成功。</span><span class="sxs-lookup"><span data-stu-id="d6164-120">If 7 days have passed since the last password rotation, but the Surface Hub was off, it will attempt to change the password immediately when turned on or every 10 minutes until successful.</span></span>

<span data-ttu-id="d6164-121">自动生成的密码包含 15-32 个字符，包括大写和小写字母、数字和特殊字符的组合。</span><span class="sxs-lookup"><span data-stu-id="d6164-121">The automatically generated passwords contain 15-32 characters including a combination of uppercase and lowercase letters, numbers, and special characters.</span></span> <span data-ttu-id="d6164-122">请注意，当设备帐户的密码更改时，不会显示新密码。</span><span class="sxs-lookup"><span data-stu-id="d6164-122">Note that when the device account's password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="d6164-123">如果你需要登录帐户，或再次提供密码 (例如，如果你想要更改 Surface Hub) 上的设备帐户设置，则需要使用 Active Directory 或 Microsoft 365 管理门户重置密码。</span><span class="sxs-lookup"><span data-stu-id="d6164-123">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Microsoft 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6164-124">将设备帐户添加到 Surface Hub 时所使用的格式会影响必须使用哪个设备附属[](prepare-your-environment-for-surface-hub.md)选项才能使密码旋转正常工作。</span><span class="sxs-lookup"><span data-stu-id="d6164-124">The format used when adding the device account to the Surface Hub has an impact on which [device affiliation](prepare-your-environment-for-surface-hub.md) option must be used in order for password rotation to work.</span></span> <span data-ttu-id="d6164-125">如果以 **域\用户名格式** 添加帐户，则初始设置期间将中心与本地 Active Directory 关联。</span><span class="sxs-lookup"><span data-stu-id="d6164-125">If adding the account in **domain\username** format, affiliate the Hub with on-premises Active Directory during initial setup.</span></span> <span data-ttu-id="d6164-126">如果以格式添加帐户，在初始设置期间将中心与 `username@domain.com` Azure Active Directory 关联。</span><span class="sxs-lookup"><span data-stu-id="d6164-126">If adding the account in `username@domain.com` format, affiliate the Hub with Azure Active Directory during initial setup.</span></span> <span data-ttu-id="d6164-127">否则，密码轮换将没有效果。</span><span class="sxs-lookup"><span data-stu-id="d6164-127">Otherwise, password rotation will not work.</span></span>

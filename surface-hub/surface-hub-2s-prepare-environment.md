---
title: 为 Surface Hub 2S 准备环境
description: 了解为 Surface Hub 2S 准备环境需要执行哪些工作。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 2/26/2021
ms.localizationpriority: Medium
ms.openlocfilehash: caa6372820222f6f2f225f028161b3441b147a82
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385140"
---
# <a name="prepare-your-environment-for-surface-hub-2s"></a><span data-ttu-id="b941d-104">为 Surface Hub 2S 准备环境</span><span class="sxs-lookup"><span data-stu-id="b941d-104">Prepare your environment for Surface Hub 2S</span></span>

## <a name="office-365-readiness"></a><span data-ttu-id="b941d-105">Office 365 准备情况</span><span class="sxs-lookup"><span data-stu-id="b941d-105">Office 365 readiness</span></span>

<span data-ttu-id="b941d-106">如果使用 Exchange Online、Skype for Business Online、Microsoft Teams 或 Microsoft Whiteboard，并且打算使用 Intune 管理 Surface Hub 2S，请首先查看终结点的 [Office 365 要求](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="b941d-106">If you use Exchange Online, Skype for Business Online, Microsoft Teams, or Microsoft Whiteboard, and intend to manage Surface Hub 2S with Intune, first review the [Office 365 requirements for endpoints](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).</span></span>

<span data-ttu-id="b941d-107">Office 365 终结点通过防火墙直接发送所有受信任的 Office 365 网络请求，绕过其他所有数据包级别检查或处理，帮助优化网络。</span><span class="sxs-lookup"><span data-stu-id="b941d-107">Office 365 endpoints help optimize your network by sending all trusted Office 365 network requests directly through your firewall, bypassing all additional packet-level inspection or processing.</span></span> <span data-ttu-id="b941d-108">此功能可减少延迟和外围容量要求。</span><span class="sxs-lookup"><span data-stu-id="b941d-108">This feature reduces latency and your perimeter capacity requirements.</span></span>

<span data-ttu-id="b941d-109">Microsoft 会定期更新 Office 365 服务，其中新增了一些特性和功能，可能会更改所需的端口、URL 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b941d-109">Microsoft regularly updates the Office 365 service with new features and functionality, which may alter required ports, URLs, and IP addresses.</span></span> <span data-ttu-id="b941d-110">若要评估、配置和随时了解最新更改，请订阅 [Office 365 IP 地址和 URL Web 服务](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。</span><span class="sxs-lookup"><span data-stu-id="b941d-110">To evaluate, configure, and stay up to date with changes, subscribe to the [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

> [!NOTE]
> <span data-ttu-id="b941d-111">Surface Hub 适用于 Microsoft Teams、Skype for Business Server 2019、Skype for Business Server 2015 或 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="b941d-111">Surface Hub works with Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015, or Skype for Business Online.</span></span>
<span data-ttu-id="b941d-112">不支持早期平台，如 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b941d-112">Earlier platforms, such as Lync Server 2013, are not supported.</span></span> <span data-ttu-id="b941d-113">Surface Hub 在 GCC-High 或 DoD 环境中不受支持。</span><span class="sxs-lookup"><span data-stu-id="b941d-113">Surface Hub is not supported in GCC-High or DoD environments.</span></span>


## <a name="device-affiliation"></a><span data-ttu-id="b941d-114">设备附属关系</span><span class="sxs-lookup"><span data-stu-id="b941d-114">Device affiliation</span></span>

<span data-ttu-id="b941d-115">使用设备附属关系管理用户对 Surface Hub 2S 上的"设置"应用的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b941d-115">Use Device affiliation to manage user access to the Settings app on Surface Hub 2S.</span></span>
<span data-ttu-id="b941d-116">使用在 Surface Hub 2S (上运行的 Windows 10 团队) ，只有授权用户可以使用"设置"应用调整设置。</span><span class="sxs-lookup"><span data-stu-id="b941d-116">With the Windows 10 Team operating system (that runs on Surface Hub 2S),  only authorized users can adjust settings using the Settings app.</span></span> <span data-ttu-id="b941d-117">由于选择附属关系可能会影响功能可用性，请进行相应规划以确保用户可以访问预期的功能。</span><span class="sxs-lookup"><span data-stu-id="b941d-117">Since choosing the affiliation can impact feature availability, plan appropriately to ensure that users can access features as intended.</span></span>

> [!NOTE]
> <span data-ttu-id="b941d-118">只能在初始开箱即用体验期间设置设备附属 (OOBE) 设置。</span><span class="sxs-lookup"><span data-stu-id="b941d-118">You can only set Device affiliation during the initial out-of-box experience (OOBE) setup.</span></span> <span data-ttu-id="b941d-119">如果需要重置设备附属关系，必须重复 OOBE 设置。</span><span class="sxs-lookup"><span data-stu-id="b941d-119">If you need to reset Device affiliation, you’ll have to repeat OOBE setup.</span></span>

## <a name="no-affiliation"></a><span data-ttu-id="b941d-120">无附属关系</span><span class="sxs-lookup"><span data-stu-id="b941d-120">No affiliation</span></span>

<span data-ttu-id="b941d-121">没有任何附属关系，就像在每个 Surface Hub 2S 上将 Surface Hub 2S 放在具有不同本地管理员帐户的工作组中。</span><span class="sxs-lookup"><span data-stu-id="b941d-121">No affiliation is like having Surface Hub 2S in a workgroup with a different local Administrator account on each Surface Hub 2S.</span></span> <span data-ttu-id="b941d-122">如果选择"不附属关系"，则必须本地将 [BitLocker 密钥保存到 U 盘](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)。</span><span class="sxs-lookup"><span data-stu-id="b941d-122">If you choose No affiliation, you must locally save the [BitLocker Key to a USB thumb drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq).</span></span> <span data-ttu-id="b941d-123">你仍然可以使用 Intune 注册设备;但是，只有本地管理员可以使用 OOBE 期间配置的帐户凭据访问"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="b941d-123">You can still enroll the device with Intune; however, only the local admin can access the Settings app using the account credentials configured during OOBE.</span></span> <span data-ttu-id="b941d-124">可以从"设置"应用更改管理员帐户密码。</span><span class="sxs-lookup"><span data-stu-id="b941d-124">You can change the Administrator account password from the Settings app.</span></span>

## <a name="active-directory-domain-services"></a><span data-ttu-id="b941d-125">Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="b941d-125">Active Directory Domain Services</span></span>

<span data-ttu-id="b941d-126">如果将 Surface Hub 2S 与本地 Active Directory 域服务关联，则需要使用域中的安全组管理对"设置"应用的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b941d-126">If you affiliate Surface Hub 2S with on-premises Active Directory Domain Services, you need to manage access to the Settings app using a security group on your domain.</span></span> <span data-ttu-id="b941d-127">这有助于确保所有安全组成员都有权更改 Surface Hub 2S 上的设置。</span><span class="sxs-lookup"><span data-stu-id="b941d-127">This helps ensure that all security group members have permissions to change settings on Surface Hub 2S.</span></span> <span data-ttu-id="b941d-128">另请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="b941d-128">Also note the following:</span></span>

- <span data-ttu-id="b941d-129">当 Surface Hub 2S 与本地 Active Directory 域服务关联时，BitLocker 密钥可以保存在 Active Directory 架构中。</span><span class="sxs-lookup"><span data-stu-id="b941d-129">When Surface Hub 2S affiliates with your on-premises Active Directory Domain Services, the BitLocker key can be saved in the Active Directory Schema.</span></span> <span data-ttu-id="b941d-130">有关详细信息，请参阅 [为组织准备 BitLocker：规划和策略](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。</span><span class="sxs-lookup"><span data-stu-id="b941d-130">For more information, see [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).</span></span>

- <span data-ttu-id="b941d-131">组织的受信任根 AS 被推送到 Surface Hub 2S 中的同一容器，这意味着你无需使用预配包导入它们。</span><span class="sxs-lookup"><span data-stu-id="b941d-131">Your organization’s Trusted Root CAs are pushed to the same container in Surface Hub 2S, which means you don’t need to import them using a provisioning package.</span></span>

- <span data-ttu-id="b941d-132">你仍然可以使用 Intune 注册设备，以集中管理 Surface Hub 2S 上的设置。</span><span class="sxs-lookup"><span data-stu-id="b941d-132">You can still enroll the device with Intune to centrally manage settings on your Surface Hub 2S.</span></span>

## <a name="azure-active-directory"></a><span data-ttu-id="b941d-133">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b941d-133">Azure Active Directory</span></span>

<span data-ttu-id="b941d-134">当你选择将 Surface Hub 2S 与 Azure Active Directory (Azure AD) 关联时，全局管理员安全组的任何用户都可以登录到 Surface Hub 2S 上的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="b941d-134">When you choose to affiliate your Surface Hub 2S with Azure Active Directory (Azure AD), any user in the Global Admins Security Group can sign in to the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="b941d-135">还可以配置非全局管理员帐户，以限制对 Surface Hub 2S 上"设置"应用的管理权限。</span><span class="sxs-lookup"><span data-stu-id="b941d-135">You can also configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="b941d-136">这使你能够仅确定 Surface Hub 2S 的管理员权限范围，并在整个 Azure AD 域中阻止可能不需要的管理员访问权限。</span><span class="sxs-lookup"><span data-stu-id="b941d-136">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> 

<span data-ttu-id="b941d-137">如果你为组织启用了 Intune 自动注册，Surface Hub 2S 将自动在 Intune 中注册自身。</span><span class="sxs-lookup"><span data-stu-id="b941d-137">If you enabled Intune Automatic Enrollment for your organization, Surface Hub 2S will automatically enroll itself with Intune.</span></span> <span data-ttu-id="b941d-138">设备的 BitLocker 密钥会自动保存在 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="b941d-138">The device’s BitLocker key is automatically saved in Azure AD.</span></span> 

<span data-ttu-id="b941d-139">若要了解有关使用 Azure AD 管理 Surface Hub 的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b941d-139">To learn more about managing Surface Hub with Azure AD, see:</span></span> 

 - [<span data-ttu-id="b941d-140">管理员组管理</span><span class="sxs-lookup"><span data-stu-id="b941d-140">Admin group management</span></span>](admin-group-management-for-surface-hub.md)
 - [<span data-ttu-id="b941d-141">配置 Surface Hub 2 上的非全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="b941d-141">Configure non Global admin accounts on Surface Hub 2S</span></span>](surface-hub-2s-nonglobal-admin.md)


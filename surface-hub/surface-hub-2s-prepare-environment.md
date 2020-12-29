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
ms.date: 12/28/2020
ms.localizationpriority: Medium
ms.openlocfilehash: af66449806c9aa525fa3f5df84012d3daeed96ba
ms.sourcegitcommit: dbd14649442ad039aeb265cd60ed029d483a4bb0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2020
ms.locfileid: "11251449"
---
# <span data-ttu-id="afb21-104">为 Surface Hub 2S 准备环境</span><span class="sxs-lookup"><span data-stu-id="afb21-104">Prepare your environment for Surface Hub 2S</span></span>

## <span data-ttu-id="afb21-105">Office 365 准备情况</span><span class="sxs-lookup"><span data-stu-id="afb21-105">Office 365 readiness</span></span>

<span data-ttu-id="afb21-106">如果你使用 Exchange Online、Skype for Business Online、Microsoft Teams 或 Microsoft Whiteboard，并且打算使用 Intune 管理 Surface Hub 2S，请首先查看终结点的 [Office 365 要求](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="afb21-106">If you use Exchange Online, Skype for Business Online, Microsoft Teams, or Microsoft Whiteboard, and intend to manage Surface Hub 2S with Intune, first review the [Office 365 requirements for endpoints](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).</span></span>

<span data-ttu-id="afb21-107">Office 365 终结点通过防火墙直接发送所有受信任的 Office 365 网络请求，绕过所有其他数据包级检查或处理，帮助优化网络。</span><span class="sxs-lookup"><span data-stu-id="afb21-107">Office 365 endpoints help optimize your network by sending all trusted Office 365 network requests directly through your firewall, bypassing all additional packet-level inspection or processing.</span></span> <span data-ttu-id="afb21-108">此功能可减少延迟和外围容量要求。</span><span class="sxs-lookup"><span data-stu-id="afb21-108">This feature reduces latency and your perimeter capacity requirements.</span></span>

<span data-ttu-id="afb21-109">Microsoft 会定期更新 Office 365 服务的新特性和功能，这可能会改变所需的端口、URL 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="afb21-109">Microsoft regularly updates the Office 365 service with new features and functionality, which may alter required ports, URLs, and IP addresses.</span></span> <span data-ttu-id="afb21-110">若要评估、配置并随时了解最新更改，请订阅 [Office 365 IP 地址和 URL Web 服务](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。</span><span class="sxs-lookup"><span data-stu-id="afb21-110">To evaluate, configure, and stay up to date with changes, subscribe to the [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

> [!NOTE]
> <span data-ttu-id="afb21-111">Surface Hub 适用于 Microsoft Teams、Skype for Business Server 2019、Skype for Business Server 2015 或 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="afb21-111">Surface Hub works with Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015, or Skype for Business Online.</span></span>
<span data-ttu-id="afb21-112">不支持早期平台，如 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="afb21-112">Earlier platforms, such as Lync Server 2013, are not supported.</span></span> <span data-ttu-id="afb21-113">Surface Hub 在 GCC-High 或 DoD 环境中不受支持。</span><span class="sxs-lookup"><span data-stu-id="afb21-113">Surface Hub is not supported in GCC-High or DoD environments.</span></span>


## <span data-ttu-id="afb21-114">设备附属关系</span><span class="sxs-lookup"><span data-stu-id="afb21-114">Device affiliation</span></span>

<span data-ttu-id="afb21-115">使用设备附属关系管理用户对 Surface Hub 2S 上的"设置"应用的访问权限。</span><span class="sxs-lookup"><span data-stu-id="afb21-115">Use Device affiliation to manage user access to the Settings app on Surface Hub 2S.</span></span>
<span data-ttu-id="afb21-116">使用在 Surface Hub 2S (上运行的 Windows 10 团队) ，只有授权用户可以使用"设置"应用调整设置。</span><span class="sxs-lookup"><span data-stu-id="afb21-116">With the Windows 10 Team operating system (that runs on Surface Hub 2S),  only authorized users can adjust settings using the Settings app.</span></span> <span data-ttu-id="afb21-117">由于选择附属关系可能会影响功能可用性，请进行相应规划以确保用户可以访问预期功能。</span><span class="sxs-lookup"><span data-stu-id="afb21-117">Since choosing the affiliation can impact feature availability, plan appropriately to ensure that users can access features as intended.</span></span>

> [!NOTE]
> <span data-ttu-id="afb21-118">在 OOBE 设置的初始开箱即用体验期间，你 (设备) 关系。</span><span class="sxs-lookup"><span data-stu-id="afb21-118">You can only set Device affiliation during the initial out-of-box experience (OOBE) setup.</span></span> <span data-ttu-id="afb21-119">如果需要重置设备附属关系，必须重复 OOBE 设置。</span><span class="sxs-lookup"><span data-stu-id="afb21-119">If you need to reset Device affiliation, you’ll have to repeat OOBE setup.</span></span>

## <span data-ttu-id="afb21-120">无附属关系</span><span class="sxs-lookup"><span data-stu-id="afb21-120">No affiliation</span></span>

<span data-ttu-id="afb21-121">无附属关系就像在每个 Surface Hub 2S 上具有不同本地管理员帐户的工作组中拥有 Surface Hub 2S。</span><span class="sxs-lookup"><span data-stu-id="afb21-121">No affiliation is like having Surface Hub 2S in a workgroup with a different local Administrator account on each Surface Hub 2S.</span></span> <span data-ttu-id="afb21-122">如果选择"无附属关系"，则必须本地将 [BitLocker 密钥保存到 U 盘](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)。</span><span class="sxs-lookup"><span data-stu-id="afb21-122">If you choose No affiliation, you must locally save the [BitLocker Key to a USB thumb drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq).</span></span> <span data-ttu-id="afb21-123">你仍可以使用 Intune 注册设备;但是，只有本地管理员可以使用在 OOBE 期间配置的帐户凭据访问"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="afb21-123">You can still enroll the device with Intune; however, only the local admin can access the Settings app using the account credentials configured during OOBE.</span></span> <span data-ttu-id="afb21-124">可以从"设置"应用更改管理员帐户密码。</span><span class="sxs-lookup"><span data-stu-id="afb21-124">You can change the Administrator account password from the Settings app.</span></span>

## <span data-ttu-id="afb21-125">Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="afb21-125">Active Directory Domain Services</span></span>

<span data-ttu-id="afb21-126">如果将 Surface Hub 2S 与本地 Active Directory 域服务关联，则需要使用域中的安全组管理对"设置"应用的访问权限。</span><span class="sxs-lookup"><span data-stu-id="afb21-126">If you affiliate Surface Hub 2S with on-premises Active Directory Domain Services, you need to manage access to the Settings app using a security group on your domain.</span></span> <span data-ttu-id="afb21-127">这有助于确保所有安全组成员都有权更改 Surface Hub 2S 上的设置。</span><span class="sxs-lookup"><span data-stu-id="afb21-127">This helps ensure that all security group members have permissions to change settings on Surface Hub 2S.</span></span> <span data-ttu-id="afb21-128">另请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="afb21-128">Also note the following:</span></span>

- <span data-ttu-id="afb21-129">当 Surface Hub 2S 关联与本地 Active Directory 域服务关联时，BitLocker 密钥可以保存在 Active Directory 架构中。</span><span class="sxs-lookup"><span data-stu-id="afb21-129">When Surface Hub 2S affiliates with your on-premises Active Directory Domain Services, the BitLocker key can be saved in the Active Directory Schema.</span></span> <span data-ttu-id="afb21-130">有关详细信息，请参阅["为组织准备 BitLocker：规划和策略"。](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)</span><span class="sxs-lookup"><span data-stu-id="afb21-130">For more information, see [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).</span></span>

- <span data-ttu-id="afb21-131">你的组织的受信任根 CA 被推送到 Surface Hub 2S 中的同一容器，这意味着你无需使用预配包导入它们。</span><span class="sxs-lookup"><span data-stu-id="afb21-131">Your organization’s Trusted Root CAs are pushed to the same container in Surface Hub 2S, which means you don’t need to import them using a provisioning package.</span></span>

- <span data-ttu-id="afb21-132">你仍然可以使用 Intune 注册设备，以集中管理 Surface Hub 2S 上的设置。</span><span class="sxs-lookup"><span data-stu-id="afb21-132">You can still enroll the device with Intune to centrally manage settings on your Surface Hub 2S.</span></span>

## <span data-ttu-id="afb21-133">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="afb21-133">Azure Active Directory</span></span>

<span data-ttu-id="afb21-134">当你选择将 Surface Hub 2S 与 Azure Active Directory (Azure AD) 关联时，全局管理员安全组的任何用户都可以登录到 Surface Hub 2S 上的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="afb21-134">When you choose to affiliate your Surface Hub 2S with Azure Active Directory (Azure AD), any user in the Global Admins Security Group can sign in to the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="afb21-135">目前，无法委派任何其他组以登录到 Surface Hub 2S 上的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="afb21-135">Currently, no other group can be delegated to sign in to the Settings app on Surface Hub 2S.</span></span>

<span data-ttu-id="afb21-136">如果你为组织启用了 Intune 自动注册，Surface Hub 2S 将自动向 Intune 注册自身。</span><span class="sxs-lookup"><span data-stu-id="afb21-136">If you enabled Intune Automatic Enrollment for your organization, Surface Hub 2S will automatically enroll itself with Intune.</span></span> <span data-ttu-id="afb21-137">设备的 BitLocker 密钥会自动保存在 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="afb21-137">The device’s BitLocker key is automatically saved in Azure AD.</span></span> <span data-ttu-id="afb21-138">将 Surface Hub 2S 与 Azure AD 关联时，单一登录和轻松身份验证将不起作用。</span><span class="sxs-lookup"><span data-stu-id="afb21-138">When affiliating Surface Hub 2S with Azure AD, single sign-on and Easy Authentication will not work.</span></span>

---
title: 为 Surface Hub 2S 准备环境
description: 了解为 Surface Hub 2 准备环境需要执行哪些操作。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/21/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 38f02b885a0ac2789ffc82f1ab38dc57fea5e841
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830948"
---
# <span data-ttu-id="21f4e-104">为 Surface Hub 2S 准备环境</span><span class="sxs-lookup"><span data-stu-id="21f4e-104">Prepare your environment for Surface Hub 2S</span></span>

## <span data-ttu-id="21f4e-105">Office 365 准备情况</span><span class="sxs-lookup"><span data-stu-id="21f4e-105">Office 365 readiness</span></span>

<span data-ttu-id="21f4e-106">如果您使用的是 Exchange Online、Skype for Business Online、Microsoft 团队或 Microsoft 白板，并且想要使用 Intune 管理 Surface Hub 2，请首先查看[终结点的 Office 365 要求](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="21f4e-106">If you use Exchange Online, Skype for Business Online, Microsoft Teams, or Microsoft Whiteboard, and intend to manage Surface Hub 2S with Intune, first review the [Office 365 requirements for endpoints](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).</span></span>

<span data-ttu-id="21f4e-107">Office 365 终结点通过防火墙直接发送所有受信任的 Office 365 网络请求来帮助优化你的网络，绕过所有其他数据包级别的检查或处理。</span><span class="sxs-lookup"><span data-stu-id="21f4e-107">Office 365 endpoints help optimize your network by sending all trusted Office 365 network requests directly through your firewall, bypassing all additional packet-level inspection or processing.</span></span> <span data-ttu-id="21f4e-108">此功能可减少延迟和外围容量需求。</span><span class="sxs-lookup"><span data-stu-id="21f4e-108">This feature reduces latency and your perimeter capacity requirements.</span></span>

<span data-ttu-id="21f4e-109">Microsoft 定期用新的功能和功能更新 Office 365 服务，这些功能可能会改变所需的端口、Url 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="21f4e-109">Microsoft regularly updates the Office 365 service with new features and functionality, which may alter required ports, URLs, and IP addresses.</span></span> <span data-ttu-id="21f4e-110">若要评估、配置和保持最新的更改，请订阅[Office 365 IP 地址和 URL Web 服务](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。</span><span class="sxs-lookup"><span data-stu-id="21f4e-110">To evaluate, configure, and stay up to date with changes, subscribe to the [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

## <span data-ttu-id="21f4e-111">设备附属关系</span><span class="sxs-lookup"><span data-stu-id="21f4e-111">Device affiliation</span></span>

<span data-ttu-id="21f4e-112">使用设备从属关系管理用户访问 Surface Hub 2 上的 "设置" 应用。</span><span class="sxs-lookup"><span data-stu-id="21f4e-112">Use Device affiliation to manage user access to the Settings app on Surface Hub 2S.</span></span>
<span data-ttu-id="21f4e-113">使用 Windows 10 Team Edition 操作系统（在 Surface Hub 2 上运行），只有授权用户可以使用 "设置" 应用调整设置。</span><span class="sxs-lookup"><span data-stu-id="21f4e-113">With the Windows 10 Team Edition operating system (that runs on Surface Hub 2S),  only authorized users can adjust settings using the Settings app.</span></span> <span data-ttu-id="21f4e-114">由于选择 "隶属关系" 可能会影响功能的可用性，请适当规划以确保用户可以按预期访问功能。</span><span class="sxs-lookup"><span data-stu-id="21f4e-114">Since choosing the affiliation can impact feature availability, plan appropriately to ensure that users can access features as intended.</span></span>

> [!NOTE]
> <span data-ttu-id="21f4e-115">你只能在初始全新体验（OOBE）设置期间设置设备从属关系。</span><span class="sxs-lookup"><span data-stu-id="21f4e-115">You can only set Device affiliation during the initial out-of-box experience (OOBE) setup.</span></span> <span data-ttu-id="21f4e-116">如果需要重置设备从属关系，则必须重复 OOBE 设置。</span><span class="sxs-lookup"><span data-stu-id="21f4e-116">If you need to reset Device affiliation, you’ll have to repeat OOBE setup.</span></span>

## <span data-ttu-id="21f4e-117">无隶属关系</span><span class="sxs-lookup"><span data-stu-id="21f4e-117">No affiliation</span></span>

<span data-ttu-id="21f4e-118">没有任何关系，就像在每个 Surface Hub 2 的不同本地管理员帐户的工作组中使用 Surface Hub 2。</span><span class="sxs-lookup"><span data-stu-id="21f4e-118">No affiliation is like having Surface Hub 2S in a workgroup with a different local Administrator account on each Surface Hub 2S.</span></span> <span data-ttu-id="21f4e-119">如果选择 "无关系"，则必须在本地将[BitLocker 密钥保存到 USB 拇指驱动器](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)。</span><span class="sxs-lookup"><span data-stu-id="21f4e-119">If you choose No affiliation, you must locally save the [BitLocker Key to a USB thumb drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq).</span></span> <span data-ttu-id="21f4e-120">你仍可以通过 Intune 注册设备;但是，只有本地管理员才能使用在 OOBE 期间配置的帐户凭据访问 "设置" 应用。</span><span class="sxs-lookup"><span data-stu-id="21f4e-120">You can still enroll the device with Intune; however, only the local admin can access the Settings app using the account credentials configured during OOBE.</span></span> <span data-ttu-id="21f4e-121">您可以从 "设置" 应用更改管理员帐户密码。</span><span class="sxs-lookup"><span data-stu-id="21f4e-121">You can change the Administrator account password from the Settings app.</span></span>

## <span data-ttu-id="21f4e-122">Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="21f4e-122">Active Directory Domain Services</span></span>

<span data-ttu-id="21f4e-123">如果将 Surface Hub 2 与本地 Active Directory 域服务关联，则需要使用域上的安全组管理对设置应用的访问权限。</span><span class="sxs-lookup"><span data-stu-id="21f4e-123">If you affiliate Surface Hub 2S with on-premises Active Directory Domain Services, you need to manage access to the Settings app using a security group on your domain.</span></span> <span data-ttu-id="21f4e-124">这有助于确保所有安全组成员都有权更改 Surface Hub 2 上的设置。</span><span class="sxs-lookup"><span data-stu-id="21f4e-124">This helps ensure that all security group members have permissions to change settings on Surface Hub 2S.</span></span> <span data-ttu-id="21f4e-125">另请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="21f4e-125">Also note the following:</span></span>

- <span data-ttu-id="21f4e-126">当 Surface Hub 2 和你的本地 Active Directory 域服务的联盟时，BitLocker 密钥可以保存在 Active Directory 架构中。</span><span class="sxs-lookup"><span data-stu-id="21f4e-126">When Surface Hub 2S affiliates with your on-premises Active Directory Domain Services, the BitLocker key can be saved in the Active Directory Schema.</span></span> <span data-ttu-id="21f4e-127">有关详细信息，请参阅[为 BitLocker 准备组织：计划和策略](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。</span><span class="sxs-lookup"><span data-stu-id="21f4e-127">For more information, see [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).</span></span> 
- <span data-ttu-id="21f4e-128">组织的受信任根 Ca 被推送到 Surface Hub 2 中的相同容器，这意味着无需使用预配包导入。</span><span class="sxs-lookup"><span data-stu-id="21f4e-128">Your organization’s Trusted Root CAs are pushed to the same container in Surface Hub 2S, which means you don’t need to import them using a provisioning package.</span></span>
- <span data-ttu-id="21f4e-129">你仍然可以向 Intune 注册设备，以便集中管理 Surface Hub 2 上的设置。</span><span class="sxs-lookup"><span data-stu-id="21f4e-129">You can still enroll the device with Intune to centrally manage settings on your Surface Hub 2S.</span></span>

## <span data-ttu-id="21f4e-130">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="21f4e-130">Azure Active Directory</span></span>

<span data-ttu-id="21f4e-131">当你选择将 Surface Hub 2 与 Azure Active Directory （Azure AD）关联时，全局管理员安全组中的任何用户都可以登录 Surface Hub 2 上的 "设置" 应用。</span><span class="sxs-lookup"><span data-stu-id="21f4e-131">When you choose to affiliate your Surface Hub 2S with Azure Active Directory (Azure AD), any user in the Global Admins Security Group can sign in to the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="21f4e-132">当前，不能委派任何其他组登录 Surface Hub 2 的设置应用。</span><span class="sxs-lookup"><span data-stu-id="21f4e-132">Currently, no other group can be delegated to sign in to the Settings app on Surface Hub 2S.</span></span>

<span data-ttu-id="21f4e-133">如果为你的组织启用了 Intune 自动注册，Surface Hub 2 将自动向 Intune 注册自己。</span><span class="sxs-lookup"><span data-stu-id="21f4e-133">If you enabled Intune Automatic Enrollment for your organization, Surface Hub 2S will automatically enroll itself with Intune.</span></span> <span data-ttu-id="21f4e-134">设备的 BitLocker 密钥会自动保存在 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="21f4e-134">The device’s BitLocker key is automatically saved in Azure AD.</span></span> <span data-ttu-id="21f4e-135">当 affiliating Surface Hub 2 与 Azure AD 一起使用时，单一登录和轻松身份验证将不起作用。</span><span class="sxs-lookup"><span data-stu-id="21f4e-135">When affiliating Surface Hub 2S with Azure AD, single sign-on and Easy Authentication will not work.</span></span>

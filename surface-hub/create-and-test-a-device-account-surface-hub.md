---
title: 创建和测试设备帐户 (Surface Hub)
description: 本主题介绍了如何创建和测试 Microsoft Surface Hub 用于与 Microsoft Exchange 和 Skype 进行通信的设备帐户。
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: 创建和测试设备帐户, 设备帐户, Surface Hub 和 Microsoft Exchange, Surface Hub 和 Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831896"
---
# <span data-ttu-id="52558-104">创建和测试设备帐户 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="52558-104">Create and test a device account (Surface Hub)</span></span>


<span data-ttu-id="52558-105">本主题介绍了如何创建和测试 Microsoft Surface Hub 用于与 Microsoft Exchange 和 Skype 进行通信的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="52558-105">This topic introduces how to create and test the device account that Microsoft Surface Hub uses to communicate with Microsoft Exchange and Skype.</span></span>

<span data-ttu-id="52558-106">“设备帐户”\*\*\*\* 是 Surface Hub 用于执行以下操作的 Exchange 资源帐户：</span><span class="sxs-lookup"><span data-stu-id="52558-106">A **device account** is an Exchange resource account that Surface Hub uses to:</span></span>

-   <span data-ttu-id="52558-107">显示会议日历</span><span class="sxs-lookup"><span data-stu-id="52558-107">Display its meeting calendar</span></span>
-   <span data-ttu-id="52558-108">加入团队或 Skype for Business 呼叫</span><span class="sxs-lookup"><span data-stu-id="52558-108">Join Teams or Skype for Business calls</span></span>
-   <span data-ttu-id="52558-109">发送电子邮件（例如以电子邮件形式发送会议的白板内容）</span><span class="sxs-lookup"><span data-stu-id="52558-109">Send email (for example, email whiteboard content from a meeting)</span></span>

<span data-ttu-id="52558-110">预配了 Surface Hub 的设备帐户后，用户可将此帐户添加到会议邀请，方式与邀请用户加入会议室的方式相同。</span><span class="sxs-lookup"><span data-stu-id="52558-110">Once the device account is provisioned to a Surface Hub, people can add this account to a meeting invitation the same way that they would invite a meeting room.</span></span> 

## <span data-ttu-id="52558-111">配置概述</span><span class="sxs-lookup"><span data-stu-id="52558-111">Configuration overview</span></span>

<span data-ttu-id="52558-112">此表介绍了创建设备帐户时的主要步骤和配置决策。</span><span class="sxs-lookup"><span data-stu-id="52558-112">This table explains the main steps and configuration decisions when you create a device account.</span></span> 
 
| <span data-ttu-id="52558-113">步骤</span><span class="sxs-lookup"><span data-stu-id="52558-113">Step</span></span> | <span data-ttu-id="52558-114">描述</span><span class="sxs-lookup"><span data-stu-id="52558-114">Description</span></span>                     |  <span data-ttu-id="52558-115">用途</span><span class="sxs-lookup"><span data-stu-id="52558-115">Purpose</span></span>                             |
|------|---------------------------------|--------------------------------------|
| <span data-ttu-id="52558-116">raid-1</span><span class="sxs-lookup"><span data-stu-id="52558-116">1</span></span>    | <span data-ttu-id="52558-117">创建支持登录的 Exchange 资源邮箱（Exchange 2013 或更高版本，或者 Exchange Online）</span><span class="sxs-lookup"><span data-stu-id="52558-117">Created a logon-enabled Exchange resource mailbox (Exchange 2013 or later, or Exchange Online)</span></span> | <span data-ttu-id="52558-118">此资源邮箱允许设备保留会议日历、接收会议请求和发送邮件。</span><span class="sxs-lookup"><span data-stu-id="52558-118">This resource mailbox allows the device to maintain a meeting calendar, receive meeting requests, and send mail.</span></span> <span data-ttu-id="52558-119">必须支持登录，才能为 Surface Hub 进行预配。</span><span class="sxs-lookup"><span data-stu-id="52558-119">It must be logon-enabled to be provisioned to a Surface Hub.</span></span> |
| <span data-ttu-id="52558-120">ppls-2</span><span class="sxs-lookup"><span data-stu-id="52558-120">2</span></span>    | <span data-ttu-id="52558-121">配置邮箱属性</span><span class="sxs-lookup"><span data-stu-id="52558-121">Configure mailbox properties</span></span> | <span data-ttu-id="52558-122">必须使用正确的属性配置邮箱，才能在 Surface Hub 上获得最佳会议体验。</span><span class="sxs-lookup"><span data-stu-id="52558-122">The mailbox must be configured with the correct properties to enable the best meeting experience on Surface Hub.</span></span> <span data-ttu-id="52558-123">有关邮箱属性的详细信息，请参阅[邮箱属性](exchange-properties-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="52558-123">For more information on mailbox properties, see [Mailbox properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> |
| <span data-ttu-id="52558-124">三维空间</span><span class="sxs-lookup"><span data-stu-id="52558-124">3</span></span>    | <span data-ttu-id="52558-125">将可兼容的移动设备邮箱策略应用到邮箱</span><span class="sxs-lookup"><span data-stu-id="52558-125">Apply a compatible mobile device mailbox policy to the mailbox</span></span> | <span data-ttu-id="52558-126">Surface Hub 使用移动设备管理 (MDM) 进行管理，而非通过移动设备邮箱策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="52558-126">Surface Hub is managed using mobile device management (MDM) rather than through mobile device mailbox policies.</span></span> <span data-ttu-id="52558-127">对于兼容性，设备帐户必须具备移动设备邮箱策略，并且 **PasswordEnabled** 设置已设为 False。</span><span class="sxs-lookup"><span data-stu-id="52558-127">For compatibility, the device account must have a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="52558-128">否则，Surface Hub 无法同步邮箱和日历信息。</span><span class="sxs-lookup"><span data-stu-id="52558-128">Otherwise, Surface Hub can't sync mail and calendar info.</span></span> |
| <span data-ttu-id="52558-129">第</span><span class="sxs-lookup"><span data-stu-id="52558-129">4</span></span>    | <span data-ttu-id="52558-130">通过 Skype for Business 启用邮箱（Lync Server 2013 或更高版本，或者 Skype for Business Online）</span><span class="sxs-lookup"><span data-stu-id="52558-130">Enable mailbox with Skype for Business (Lync Server 2013 or later, or Skype for Business Online)</span></span> | <span data-ttu-id="52558-131">必须启用 Skype for Business 才能使用各种会议功能，例如视频通话、IM 和屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="52558-131">Skype for Business must be enabled to use conferencing features like video calls, IM, and screen sharing.</span></span>  |
| <span data-ttu-id="52558-132">级</span><span class="sxs-lookup"><span data-stu-id="52558-132">5</span></span>    | <span data-ttu-id="52558-133">（可选）将 ActiveSync 设备 ID 加入允许列表</span><span class="sxs-lookup"><span data-stu-id="52558-133">(Optional) Whitelist ActiveSync Device ID</span></span> | <span data-ttu-id="52558-134">组织可能具有全局策略，可阻止设备帐户同步邮件和日历信息。</span><span class="sxs-lookup"><span data-stu-id="52558-134">Your organization may have a global policy that prevents device accounts from syncing mail and calendar info.</span></span> <span data-ttu-id="52558-135">如果是这样，你需要允许 Surface Hub 的 ActiveSync 设备 ID。</span><span class="sxs-lookup"><span data-stu-id="52558-135">If so, you need to allow the ActiveSync Device ID of your Surface Hub.</span></span> |
| <span data-ttu-id="52558-136">型</span><span class="sxs-lookup"><span data-stu-id="52558-136">6</span></span>    | <span data-ttu-id="52558-137">（可选）禁用密码过期</span><span class="sxs-lookup"><span data-stu-id="52558-137">(Optional) Disable password expiration</span></span> | <span data-ttu-id="52558-138">为了简化管理，可以关闭设备帐户的密码过期设置，并允许 Surface Hub 自动轮换设备帐户密码。</span><span class="sxs-lookup"><span data-stu-id="52558-138">To simplify management, you can turn off password expiration for the device account and allow Surface Hub to automatically rotate the device account password.</span></span> <span data-ttu-id="52558-139">有关密码管理的详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="52558-139">For more information about password management, see [Password management](password-management-for-surface-hub-device-accounts.md).</span></span>  |

## <span data-ttu-id="52558-140">详细的配置步骤</span><span class="sxs-lookup"><span data-stu-id="52558-140">Detailed configuration steps</span></span> 

<span data-ttu-id="52558-141">我们建议使用远程 PowerShell 设置设备帐户。</span><span class="sxs-lookup"><span data-stu-id="52558-141">We recommend setting up your device accounts using remote PowerShell.</span></span> <span data-ttu-id="52558-142">可使用 PowerShell 脚本帮助创建和验证设备帐户。有关 PowerShell 脚本和说明的详细信息，请参阅[附录 A：PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="52558-142">There are PowerShell scripts available to help create and validate device accounts For more information on PowerShell scripts and instructions, see [Appendix A: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md).</span></span> 

<span data-ttu-id="52558-143">有关使用 PowerShell 预配设备帐户的详细步骤，请根据组织部署情况，选择表中某个选项。</span><span class="sxs-lookup"><span data-stu-id="52558-143">For detailed steps using PowerShell to provision a device account, choose an option from the table, based on your organization deployment.</span></span> 

| <span data-ttu-id="52558-144">组织部署</span><span class="sxs-lookup"><span data-stu-id="52558-144">Organization deployment</span></span>             |  <span data-ttu-id="52558-145">描述</span><span class="sxs-lookup"><span data-stu-id="52558-145">Description</span></span>                  |
|---------------------------------|--------------------------------------|
| [<span data-ttu-id="52558-146">联机部署 (Office 365)</span><span class="sxs-lookup"><span data-stu-id="52558-146">Online deployment (Office 365)</span></span>](online-deployment-surface-hub-device-accounts.md) | <span data-ttu-id="52558-147">组织的环境完全在 Office 365 上进行部署。</span><span class="sxs-lookup"><span data-stu-id="52558-147">Your organization's environment is deployed entirely on Office 365.</span></span> |
| [<span data-ttu-id="52558-148">本地部署（单林）</span><span class="sxs-lookup"><span data-stu-id="52558-148">On-premises deployment (single-forest)</span></span>](on-premises-deployment-surface-hub-device-accounts.md) | <span data-ttu-id="52558-149">组织具有受其控制并用于在单林环境中托管 Active Directory、Exchange 和 Skype for Business（或 Lync）的服务器。</span><span class="sxs-lookup"><span data-stu-id="52558-149">Your organization has servers that it controls and uses to host Active Directory, Exchange, and Skype for Business (or Lync) in a single-forest environment.</span></span> |
| [<span data-ttu-id="52558-150">本地部署（多林）</span><span class="sxs-lookup"><span data-stu-id="52558-150">On-premises deployment (multiple forests)</span></span>](on-premises-deployment-surface-hub-multi-forest.md) | <span data-ttu-id="52558-151">组织具有受其控制并用于在多林环境中托管 Active Directory、Exchange 和 Skype for Business（或 Lync）的服务器。</span><span class="sxs-lookup"><span data-stu-id="52558-151">Your organization has servers that it controls and uses to host Active Directory, Exchange, and Skype for Business (or Lync) in a multi-forest environment.</span></span> |
| [<span data-ttu-id="52558-152">混合部署</span><span class="sxs-lookup"><span data-stu-id="52558-152">Hybrid deployment</span></span>](hybrid-deployment-surface-hub-device-accounts.md) | <span data-ttu-id="52558-153">组织混合使用多个服务，其中一些服务本地托管，而另一些服务通过 Office 365 联机托管。</span><span class="sxs-lookup"><span data-stu-id="52558-153">Your organization has a mix of services, with some hosted on-premises and some hosted online through Office 365.</span></span> |
| [<span data-ttu-id="52558-154">使用 Skype 混合语音环境的联机或混合部署</span><span class="sxs-lookup"><span data-stu-id="52558-154">Online or hybrid deployment using Skype Hybrid Voice environment</span></span>](skype-hybrid-voice.md) | <span data-ttu-id="52558-155">组织在云中具有 Skype for Business 主池和 Exchange 服务器，并使用 Skype for Business 2015 本地池或通过公用电话交换网 (PSTN) 连接的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="52558-155">Your organization has Skype for Business home pools and Exchange servers in the cloud, and uses an on-premises pool of Skype for Business 2015 or Cloud Connector edition connected via Public Switched Telephone Network (PSTN).</span></span> |


<span data-ttu-id="52558-156">如果倾向于使用图形用户界面 (UI)，可使用 UI 而非 PowerShell 执行某些步骤。</span><span class="sxs-lookup"><span data-stu-id="52558-156">If you prefer to use a graphical user interface (UI), some steps can be done using UI instead of PowerShell.</span></span> <span data-ttu-id="52558-157">有关详细信息，请参阅[使用 UI 创建设备帐户](create-a-device-account-using-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="52558-157">For more information, see [Creating a device account using UI](create-a-device-account-using-office-365.md).</span></span>

## <span data-ttu-id="52558-158">帐户验证和测试</span><span class="sxs-lookup"><span data-stu-id="52558-158">Account verification and testing</span></span>

<span data-ttu-id="52558-159">有两种方法可用于验证和测试 Surface Hub 设备帐户: [帐户验证脚本](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)和 [Surface Hub 硬件诊断应用](https://www.microsoft.com/store/apps/9nblggh51f2g)。</span><span class="sxs-lookup"><span data-stu-id="52558-159">There are two methods available that you can use to validate and test a Surface Hub device account: [account verifications scripts](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts) and the [Surface Hub Hardware Diagnostic app](https://www.microsoft.com/store/apps/9nblggh51f2g).</span></span> <span data-ttu-id="52558-160">帐户验证脚本将使用桌面上的 PowerShell 验证之前创建的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="52558-160">The account verification script will validate a previously-created device account using PowerShell from your desktop.</span></span> <span data-ttu-id="52558-161">Surface Hub 硬件诊断应用安装在 Surface Hub 上，提供有关登录和通信失败的详细反馈。</span><span class="sxs-lookup"><span data-stu-id="52558-161">The Surface Hub Hardware Diagnostic app is installed on your Surface Hub and provides detailed feedback about signin and communication failures.</span></span> <span data-ttu-id="52558-162">两种工具在测试新创建的设备帐户时都非常有用，须用于确保帐户可用性达到最佳。</span><span class="sxs-lookup"><span data-stu-id="52558-162">Both are valuable tools to test newly created device accounts and should be used to ensure optimal account availability.</span></span>

 

 

 






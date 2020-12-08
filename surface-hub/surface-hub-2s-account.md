---
title: 创建 Surface Hub 2S 设备帐户
description: 本页介绍创建 Surface Hub 2 设备帐户的过程。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196725"
---
# <span data-ttu-id="bc7e1-104">创建 Surface Hub 2S 设备帐户</span><span class="sxs-lookup"><span data-stu-id="bc7e1-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="bc7e1-105">创建 Surface Hub 设备帐户 (也称为会议室邮箱) 允许 Surface Hub 2 使用 Microsoft 团队或 Skype for business 接收、批准或拒绝会议请求并加入会议。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="bc7e1-106"> (OOBE) 安装程序时在全新体验期间配置设备帐户。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="bc7e1-107">如果需要，您可以在以后 (更改它，而无需通过 OOBE 设置) 。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="bc7e1-108">与默认情况下处于禁用状态的标准会议室邮箱不同，你需要启用 Surface Hub 2 设备帐户以登录到 Microsoft 团队和 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="bc7e1-109">Surface Hub 2 依赖 Exchange ActiveSync，这需要设备帐户上的 ActiveSync 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="bc7e1-110">应用 Exchange Online 附带的默认 ActiveSync 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="bc7e1-111">使用 Microsoft 365 管理中心或使用 PowerShell 创建帐户。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="bc7e1-112">你可以使用 Exchange Online PowerShell 配置特定功能，包括：</span><span class="sxs-lookup"><span data-stu-id="bc7e1-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="bc7e1-113">每个 Surface Hub 设备帐户的日历处理。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="bc7e1-114">自定义自动答复日程安排请求。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="bc7e1-115">如果默认的 ActiveSync 邮箱策略已由其他人或另一个进程修改，则可能需要创建并分配新的 ActiveSync 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="bc7e1-116">Surface Hub 设备帐户不支持 (FIPs) 的第三方联合身份提供程序，并且必须是标准 Active Directory 或 Azure Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="bc7e1-117">使用 Microsoft 365 管理中心创建帐户</span><span class="sxs-lookup"><span data-stu-id="bc7e1-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="bc7e1-118">在 Microsoft 365 管理中心中，转到 " **资源** " 并选择 " **会议室" & 设备** ，然后选择 " **+ 会议室**"。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="bc7e1-119">提供设备帐户的名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="bc7e1-120">保留默认状态中的 "剩余设置" 不变。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-120">Leave remaining settings unchanged in the default state.</span></span>

   ![提供姓名和电子邮件地址](images/sh2-account2.png)

   ![保留默认状态中的 "剩余设置" 不变](images/sh2-account3.png)

3. <span data-ttu-id="bc7e1-123">设置设备帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-123">Set the password for the device account.</span></span> <span data-ttu-id="bc7e1-124">若要设置密码，请选择 " **用户** "，然后选择 " **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="bc7e1-125">现在，搜索新创建的用户以设置密码。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="bc7e1-126">确保**未**选中 "将**此用户首次登录时，使此用户更改其密码**" 选项。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![设置设备帐户的密码](images/sh2-account4.png)

4. <span data-ttu-id="bc7e1-128">使用 Office 365 许可证分配会议室。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="bc7e1-129">建议分配 Office 365 **会议室** 许可证，这是一个新选项，可自动为 Skype For business Online 和 Microsoft 团队启用帐户。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![分配 Office 365 许可证](images/sh2-account5.png)

### <span data-ttu-id="bc7e1-131">通过 PowerShell 完成安装</span><span class="sxs-lookup"><span data-stu-id="bc7e1-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="bc7e1-132">**Microsoft 团队和 Skype for Business 日历：** 为此帐户设置 [**日历自动处理**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) 。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-132">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="bc7e1-133">使用 PowerShell 创建帐户</span><span class="sxs-lookup"><span data-stu-id="bc7e1-133">Create account using PowerShell</span></span>

<span data-ttu-id="bc7e1-134">你可以使用 PowerShell 创建帐户，而不是使用 Microsoft 管理中心门户。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-134">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="bc7e1-135">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc7e1-135">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="bc7e1-136">创建邮箱</span><span class="sxs-lookup"><span data-stu-id="bc7e1-136">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="bc7e1-137">设置日历自动处理</span><span class="sxs-lookup"><span data-stu-id="bc7e1-137">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="bc7e1-138">如果需要使用电子邮件应用，请启用 "动态同步"</span><span class="sxs-lookup"><span data-stu-id="bc7e1-138">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="bc7e1-139">如果 unchnaged，则默认 ActiveSync 策略将正常工作。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-139">The default ActiveSync Policy will work if unchnaged.</span></span> <span data-ttu-id="bc7e1-140">否则，创建新策略并分配。</span><span class="sxs-lookup"><span data-stu-id="bc7e1-140">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### <span data-ttu-id="bc7e1-141">连接到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="bc7e1-141">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="bc7e1-142">分配许可证</span><span class="sxs-lookup"><span data-stu-id="bc7e1-142">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="bc7e1-143">检查可用的许可证</span><span class="sxs-lookup"><span data-stu-id="bc7e1-143">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```
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
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831916"
---
# <span data-ttu-id="06f1f-104">创建 Surface Hub 2S 设备帐户</span><span class="sxs-lookup"><span data-stu-id="06f1f-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="06f1f-105">创建 Surface Hub 设备帐户（也称为会议室邮箱）允许 Surface Hub 2 接收、批准或拒绝会议请求，并使用 Microsoft 团队或 Skype for business 加入会议。</span><span class="sxs-lookup"><span data-stu-id="06f1f-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="06f1f-106">在全新体验设置期间配置设备帐户（OOBE）。</span><span class="sxs-lookup"><span data-stu-id="06f1f-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="06f1f-107">如果需要，您可以稍后更改它（无需通过 OOBE 设置）。</span><span class="sxs-lookup"><span data-stu-id="06f1f-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="06f1f-108">与默认情况下处于禁用状态的标准会议室邮箱不同，你需要启用 Surface Hub 2 设备帐户以登录到 Microsoft 团队和 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="06f1f-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="06f1f-109">Surface Hub 2 依赖 Exchange ActiveSync，这需要设备帐户上的 ActiveSync 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="06f1f-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="06f1f-110">应用 Exchange Online 附带的默认 ActiveSync 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="06f1f-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="06f1f-111">使用 Microsoft 365 管理中心或使用 PowerShell 创建帐户。</span><span class="sxs-lookup"><span data-stu-id="06f1f-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="06f1f-112">你可以使用 Exchange Online PowerShell 配置特定功能，包括：</span><span class="sxs-lookup"><span data-stu-id="06f1f-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="06f1f-113">每个 Surface Hub 设备帐户的日历处理。</span><span class="sxs-lookup"><span data-stu-id="06f1f-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="06f1f-114">自定义自动答复日程安排请求。</span><span class="sxs-lookup"><span data-stu-id="06f1f-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="06f1f-115">如果默认的 ActiveSync 邮箱策略已由其他人或另一个进程修改，则可能需要创建并分配新的 ActiveSync 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="06f1f-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="06f1f-116">Surface Hub 设备帐户不支持第三方联合身份提供程序（FIPs），并且必须是标准的 Active Directory 或 Azure Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="06f1f-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="06f1f-117">使用 Microsoft 365 管理中心创建帐户</span><span class="sxs-lookup"><span data-stu-id="06f1f-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="06f1f-118">在 Microsoft 365 管理中心中，转到 "**资源**" 并选择 "**会议室" & 设备**，然后选择 " **+ 会议室**"。</span><span class="sxs-lookup"><span data-stu-id="06f1f-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="06f1f-119">提供设备帐户的名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="06f1f-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="06f1f-120">保留默认状态中的 "剩余设置" 不变。</span><span class="sxs-lookup"><span data-stu-id="06f1f-120">Leave remaining settings unchanged in the default state.</span></span>

   ![提供姓名和电子邮件地址](images/sh2-account2.png)

   ![保留默认状态中的 "剩余设置" 不变](images/sh2-account3.png)

3. <span data-ttu-id="06f1f-123">设置设备帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="06f1f-123">Set the password for the device account.</span></span> <span data-ttu-id="06f1f-124">若要设置密码，请选择 "**用户**"，然后选择 "**活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="06f1f-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="06f1f-125">现在，搜索新创建的用户以设置密码。</span><span class="sxs-lookup"><span data-stu-id="06f1f-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="06f1f-126">确保**未**选中 "将**此用户首次登录时，使此用户更改其密码**" 选项。</span><span class="sxs-lookup"><span data-stu-id="06f1f-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![设置设备帐户的密码](images/sh2-account4.png)

4. <span data-ttu-id="06f1f-128">使用 Office 365 许可证分配会议室。</span><span class="sxs-lookup"><span data-stu-id="06f1f-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="06f1f-129">建议分配 Office 365**会议室**许可证，这是一个新选项，可自动为 Skype For business Online 和 Microsoft 团队启用帐户。</span><span class="sxs-lookup"><span data-stu-id="06f1f-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![分配 Office 365 许可证](images/sh2-account5.png)

### <span data-ttu-id="06f1f-131">通过 PowerShell 完成安装</span><span class="sxs-lookup"><span data-stu-id="06f1f-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="06f1f-132">**Skype For business：** 对于仅限 Skype for business （本地版或联机版），您可以通过运行**enable-CsMeetingRoom**启用 skype for business 对象来启用音频和会议厅保留的会议室提示功能。</span><span class="sxs-lookup"><span data-stu-id="06f1f-132">**Skype for Business:** For Skype for Business only (on-premises or online), you can enable the Skype for Business object by running **Enable-CsMeetingRoom** to enable features such as Meeting room prompt for audio and Lobby hold.</span></span>

- <span data-ttu-id="06f1f-133">**Microsoft 团队和 Skype for Business 日历：** 为此帐户设置[**日历自动处理**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing)。</span><span class="sxs-lookup"><span data-stu-id="06f1f-133">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="06f1f-134">使用 PowerShell 创建帐户</span><span class="sxs-lookup"><span data-stu-id="06f1f-134">Create account using PowerShell</span></span>

<span data-ttu-id="06f1f-135">你可以使用 PowerShell 创建帐户，而不是使用 Microsoft 管理中心门户。</span><span class="sxs-lookup"><span data-stu-id="06f1f-135">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="06f1f-136">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="06f1f-136">Connect to Exchange Online PowerShell</span></span>

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### <span data-ttu-id="06f1f-137">创建新的会议室邮箱</span><span class="sxs-lookup"><span data-stu-id="06f1f-137">Create a new Room mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### <span data-ttu-id="06f1f-138">设置日历自动处理</span><span class="sxs-lookup"><span data-stu-id="06f1f-138">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### <span data-ttu-id="06f1f-139">分配许可证</span><span class="sxs-lookup"><span data-stu-id="06f1f-139">Assign a license</span></span>

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## <span data-ttu-id="06f1f-140">使用 PowerShell 连接到 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="06f1f-140">Connect to Skype for Business Online using PowerShell</span></span>

### <span data-ttu-id="06f1f-141">安装先决条件</span><span class="sxs-lookup"><span data-stu-id="06f1f-141">Install pre-requisites</span></span>

- [<span data-ttu-id="06f1f-142">Visual c + + 2017 可再发行组件</span><span class="sxs-lookup"><span data-stu-id="06f1f-142">Visual C++ 2017 Redistributable</span></span>](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [<span data-ttu-id="06f1f-143">Skype for Business Online PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="06f1f-143">Skype for Business Online PowerShell Module</span></span>](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```

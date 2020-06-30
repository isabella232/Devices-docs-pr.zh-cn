---
title: 混合部署 (Surface Hub)
description: 混合部署需要特殊处理，才能为 Microsoft Surface Hub 设置设备帐户。
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: 混合部署, Surface Hub 的设备帐户, 本地托管的 Exchange, 联机托管的 Exchange
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831828"
---
# <span data-ttu-id="7b2af-104">混合部署 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="7b2af-104">Hybrid deployment (Surface Hub)</span></span>

<span data-ttu-id="7b2af-105">混合部署需要特殊处理，才能为 Microsoft Surface Hub 设置设备帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-105">A hybrid deployment requires special processing to set up a device account for your Microsoft Surface Hub.</span></span> <span data-ttu-id="7b2af-106">如果使用的是混合部署（即组织中混合服务的一部分是本地托管的，另一部分是联机托管的），你的配置将取决于每个服务的托管位置。</span><span class="sxs-lookup"><span data-stu-id="7b2af-106">If you’re using a hybrid deployment, in which your organization has a mix of services, with some hosted on-premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="7b2af-107">本主题涵盖[本地托管的 Exchange](#exchange-on-premises)、[联机托管的 Exchange](#exchange-online)、本地 Skype for Business、Skype for Business Online 和混合 Skype for Business 的混合部署。</span><span class="sxs-lookup"><span data-stu-id="7b2af-107">This topic covers hybrid deployments for [Exchange hosted on-premises](#exchange-on-premises), [Exchange hosted online](#exchange-online), Skype for Business on-premises, Skype for Business online, and Skype for Business hybrid.</span></span> <span data-ttu-id="7b2af-108">由于这种类型的部署有很多不同的变体，因此无法针对所有部署提供详细说明。</span><span class="sxs-lookup"><span data-stu-id="7b2af-108">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="7b2af-109">以下过程将适用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="7b2af-109">The following process will work for many configurations.</span></span> <span data-ttu-id="7b2af-110">如果该过程不适合你的设置，我们建议你使用 PowerShell（请参阅[附录：PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)）以针对其他部署选项获得相同的最终结果，如此处所述。</span><span class="sxs-lookup"><span data-stu-id="7b2af-110">If the process isn't right for your setup, we recommend that you use PowerShell (see [Appendix: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="7b2af-111">然后，应使用提供的 Powershell 脚本验证 Surface Hub 设置。</span><span class="sxs-lookup"><span data-stu-id="7b2af-111">You should then use the provided Powershell script to verify your Surface Hub setup.</span></span> <span data-ttu-id="7b2af-112">（请参阅[帐户验证脚本](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)。）</span><span class="sxs-lookup"><span data-stu-id="7b2af-112">(See [Account Verification Script](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span></span>

> [!NOTE]
> <span data-ttu-id="7b2af-113">在 Exchange 混合环境中，按照[本地 exchange](#exchange-on-premises)的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="7b2af-113">In an Exchange hybrid environment, follow the steps for [Exchange on-premises](#exchange-on-premises).</span></span> <span data-ttu-id="7b2af-114">若要将 Exchange 对象移动到 Office 365，请使用[MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b2af-114">To move Exchange objects to Office 365, use the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet.</span></span>

## <span data-ttu-id="7b2af-115">本地 Exchange</span><span class="sxs-lookup"><span data-stu-id="7b2af-115">Exchange on-premises</span></span>

<span data-ttu-id="7b2af-116">如果你使用本地 Exchange，请使用此过程。</span><span class="sxs-lookup"><span data-stu-id="7b2af-116">Use this procedure if you use Exchange on-premises.</span></span>

1. <span data-ttu-id="7b2af-117">在此过程中，你将使用 AD 管理员工具为你的本地域帐户添加电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7b2af-117">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="7b2af-118">此帐户将同步到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7b2af-118">This account will be synced to Office 365.</span></span>

- <span data-ttu-id="7b2af-119">在 **Active Directory 用户和计算机** AD 工具中，右键单击将在其中创建 Surface Hub 帐户的文件夹或组织单位，然后依次单击**新建**和**用户**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-119">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="7b2af-120">将上一 cmdlet 的显示名称键入到**全名**框中，而将别名键入到**用户登录名称**框中。</span><span class="sxs-lookup"><span data-stu-id="7b2af-120">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="7b2af-121">单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-121">Click **Next**.</span></span><p>

![用于在 Active Directory 中创建新用户的新对象框。](images/hybriddeployment-01a.png)

- <span data-ttu-id="7b2af-123">键入此帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="7b2af-123">Type the password for this account.</span></span> <span data-ttu-id="7b2af-124">你将需要重新键入它以供验证。</span><span class="sxs-lookup"><span data-stu-id="7b2af-124">You'll need to retype it for verification.</span></span> <span data-ttu-id="7b2af-125">请确保**密码永不过期**复选框是唯一处于选中状态的选项。</span><span class="sxs-lookup"><span data-stu-id="7b2af-125">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> <span data-ttu-id="7b2af-126">**重要提示** Surface Hub 上的 Skype for Business 要求选择**密码永不过期**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-126">**Important** Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="7b2af-127">域规则可能会禁止未过期的密码。</span><span class="sxs-lookup"><span data-stu-id="7b2af-127">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="7b2af-128">如果是这样，你将需要针对每个 Surface Hub 设备帐户创建例外。</span><span class="sxs-lookup"><span data-stu-id="7b2af-128">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![显示密码对话框的图像。](images/hybriddeployment-02a.png)

-   <span data-ttu-id="7b2af-130">单击**完成**以创建帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-130">Click **Finish** to create the account.</span></span>

![具有新用户的帐户名称、登录名称和密码选项的图像。](images/hybriddeployment-03a.png)

2. <span data-ttu-id="7b2af-132">启用远程邮箱。</span><span class="sxs-lookup"><span data-stu-id="7b2af-132">Enable the remote mailbox.</span></span>

<span data-ttu-id="7b2af-133">使用管理员权限打开你的本地 Exchange 命令行管理程序，并运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b2af-133">Open your on-premises Exchange Management Shell with administrator permissions, and run this cmdlet.</span></span>

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> <span data-ttu-id="7b2af-134">如果没有本地 Exchange 环境来运行此 cmdlet，则你可以直接对此帐户的 Active Directory 对象进行相同的更改。</span><span class="sxs-lookup"><span data-stu-id="7b2af-134">If you don't have an on-premises Exchange environment to run this cmdlet, you can make the same changes directly to the Active Directory object for the account.</span></span>
>
> <span data-ttu-id="7b2af-135">msExchRemoteRecipientType = 33</span><span class="sxs-lookup"><span data-stu-id="7b2af-135">msExchRemoteRecipientType = 33</span></span>
>
> <span data-ttu-id="7b2af-136">msExchRecipientDisplayType = -2147481850</span><span class="sxs-lookup"><span data-stu-id="7b2af-136">msExchRecipientDisplayType = -2147481850</span></span>
>
> <span data-ttu-id="7b2af-137">msExchRecipientTypeDetails = 8589934592</span><span class="sxs-lookup"><span data-stu-id="7b2af-137">msExchRecipientTypeDetails = 8589934592</span></span>

3. <span data-ttu-id="7b2af-138">创建完帐户后，运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="7b2af-138">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="7b2af-139">完成后，转到 Microsoft 365 管理中心中的 "用户" 页面，并验证在先前步骤中创建的帐户是否已合并到 "联机"。</span><span class="sxs-lookup"><span data-stu-id="7b2af-139">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

4. <span data-ttu-id="7b2af-140">连接到 Microsoft Exchange Online 并在 Office 365 中设置帐户的某些属性。</span><span class="sxs-lookup"><span data-stu-id="7b2af-140">Connect to Microsoft Exchange Online and set some properties for the account in Office 365.</span></span>

<span data-ttu-id="7b2af-141">在电脑上启动远程 PowerShell 会话，并连接到 Microsoft Exchange。</span><span class="sxs-lookup"><span data-stu-id="7b2af-141">Start a remote PowerShell session on a PC and connect to Microsoft Exchange.</span></span> <span data-ttu-id="7b2af-142">请确保已设置正确的权限来运行关联的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b2af-142">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

<span data-ttu-id="7b2af-143">后续步骤将在你的 Office 365 租户上运行。</span><span class="sxs-lookup"><span data-stu-id="7b2af-143">The next steps will be run on your Office 365 tenant.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. <span data-ttu-id="7b2af-144">创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。</span><span class="sxs-lookup"><span data-stu-id="7b2af-144">Create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="7b2af-145">设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。</span><span class="sxs-lookup"><span data-stu-id="7b2af-145">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy or use a compatible existing policy.</span></span>

<span data-ttu-id="7b2af-146">Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 False）兼容。</span><span class="sxs-lookup"><span data-stu-id="7b2af-146">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="7b2af-147">如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。</span><span class="sxs-lookup"><span data-stu-id="7b2af-147">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

<span data-ttu-id="7b2af-148">如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。</span><span class="sxs-lookup"><span data-stu-id="7b2af-148">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="7b2af-149">完成创建后，你可以对其他设备帐户应用相同的策略。</span><span class="sxs-lookup"><span data-stu-id="7b2af-149">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="7b2af-150">一旦你有兼容的策略，你将需要将策略应用到设备帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-150">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. <span data-ttu-id="7b2af-151">设置 Exchange 属性。</span><span class="sxs-lookup"><span data-stu-id="7b2af-151">Set Exchange properties.</span></span>

<span data-ttu-id="7b2af-152">可通过设置设备帐户上的 Exchange 属性来改进会议体验。</span><span class="sxs-lookup"><span data-stu-id="7b2af-152">Setting Exchange properties on the device account to improve the meeting experience.</span></span> <span data-ttu-id="7b2af-153">你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md) 部分中查看需要设置哪些属性。</span><span class="sxs-lookup"><span data-stu-id="7b2af-153">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. <span data-ttu-id="7b2af-154">连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7b2af-154">Connect to Azure AD.</span></span>

<span data-ttu-id="7b2af-155">首先需要安装 PowerShell 版本 2 的 Azure AD 模块。</span><span class="sxs-lookup"><span data-stu-id="7b2af-155">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="7b2af-156">在提升的 PowerShell 提示符下，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b2af-156">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="7b2af-157">需要连接到 Azure AD 才能应用某些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="7b2af-157">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="7b2af-158">你可以运行此 cmdlet 来进行连接。</span><span class="sxs-lookup"><span data-stu-id="7b2af-158">You can run this cmdlet to connect.</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="7b2af-159">分配 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="7b2af-159">Assign an Office 365 license.</span></span>

<span data-ttu-id="7b2af-160">设备帐户需要有一个有效的 Office 365 (O365) 许可证，否则 Exchange 和 Skype for Business 将不可用。</span><span class="sxs-lookup"><span data-stu-id="7b2af-160">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="7b2af-161">如果已拥有许可证，则需要将使用位置分配给设备帐户，以便确定适用于你的帐户的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="7b2af-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="7b2af-162">可使用 `Get-AzureADSubscribedSku` 检索可供 O365 租户使用的 SKU 列表。</span><span class="sxs-lookup"><span data-stu-id="7b2af-162">You can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="7b2af-163">列出 SKU 后，需要将所需的 SkuId 分配给 `$License.SkuId` 变量。</span><span class="sxs-lookup"><span data-stu-id="7b2af-163">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

<span data-ttu-id="7b2af-164">接下来，使用 [Skype for Business Online](#skype-for-business-online)、[本地 Skype for Business](#skype-for-business-on-premises) 或[混合 Skype for Business](#skype-for-business-hybrid) 启用设备帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-164">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="7b2af-165">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7b2af-165">Skype for Business Online</span></span>

<span data-ttu-id="7b2af-166">若要启用 Skype for Business Online，租户用户必须具有 Exchange 邮箱（至少需要租户中的一个 Exchange 邮箱）。</span><span class="sxs-lookup"><span data-stu-id="7b2af-166">To enable Skype for Business online, your tenant users must have Exchange mailboxes (at least one Exchange mailbox in the tenant is required).</span></span> <span data-ttu-id="7b2af-167">下表说明了你需要的计划或附加服务。</span><span class="sxs-lookup"><span data-stu-id="7b2af-167">The following table explains which plans or additional services you need.</span></span>

| <span data-ttu-id="7b2af-168">Skype 房间系统方案</span><span class="sxs-lookup"><span data-stu-id="7b2af-168">Skype room system scenario</span></span> | <span data-ttu-id="7b2af-169">如果您有 Office 365 Premium、Microsoft 365 适用的企业版或 Skype for business 独立计划2，您需要：</span><span class="sxs-lookup"><span data-stu-id="7b2af-169">If you have Office 365 Premium, Microsoft 365 Apps for enterprise, or Skype for Business Standalone Plan 2, you need:</span></span> | <span data-ttu-id="7b2af-170">如果你有基于企业版的计划，则需要：</span><span class="sxs-lookup"><span data-stu-id="7b2af-170">If you have an Enterprise-based plan, you need:</span></span> | <span data-ttu-id="7b2af-171">如果您有 Skype for business Server 2015 （本地或混合版），您需要：</span><span class="sxs-lookup"><span data-stu-id="7b2af-171">If you have Skype for Business Server 2015 (on-premises or hybrid), you need:</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="7b2af-172">加入计划的会议</span><span class="sxs-lookup"><span data-stu-id="7b2af-172">Join a scheduled meeting</span></span> | <span data-ttu-id="7b2af-173">Skype for Business 独立计划 1</span><span class="sxs-lookup"><span data-stu-id="7b2af-173">Skype for Business Standalone Plan 1</span></span> | <span data-ttu-id="7b2af-174">E1、3、4 或 5</span><span class="sxs-lookup"><span data-stu-id="7b2af-174">E1, 3, 4, or 5</span></span> | <span data-ttu-id="7b2af-175">Skype for Business Server 标准 CAL</span><span class="sxs-lookup"><span data-stu-id="7b2af-175">Skype for Business Server Standard CAL</span></span> |
| <span data-ttu-id="7b2af-176">启动临时安排的会议</span><span class="sxs-lookup"><span data-stu-id="7b2af-176">Initiate an ad-hoc meeting</span></span> | <span data-ttu-id="7b2af-177">Skype for Business 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="7b2af-177">Skype for Business Standalone Plan 2</span></span> | <span data-ttu-id="7b2af-178">E 1、3、4 或 5</span><span class="sxs-lookup"><span data-stu-id="7b2af-178">E 1, 3, 4, or 5</span></span> | <span data-ttu-id="7b2af-179">Skype for Business Server 标准 CAL 或企业 CAL</span><span class="sxs-lookup"><span data-stu-id="7b2af-179">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="7b2af-180">启动临时安排的会议并在会议中拨出电话号码</span><span class="sxs-lookup"><span data-stu-id="7b2af-180">Initiate an ad-hoc meeting and dial out from a meeting to phone numbers</span></span> | <span data-ttu-id="7b2af-181">带有音频会议的 Skype for business 独立计划2</span><span class="sxs-lookup"><span data-stu-id="7b2af-181">Skype for Business Standalone Plan 2 with Audio Conferencing</span></span></br></br><span data-ttu-id="7b2af-182">**注意** PSTN 用量计费为可选项</span><span class="sxs-lookup"><span data-stu-id="7b2af-182">**Note** PSTN consumption billing is optional</span></span> | <span data-ttu-id="7b2af-183">具有音频会议或 E5 的 E1 或 E3</span><span class="sxs-lookup"><span data-stu-id="7b2af-183">E1 or E3 with Audio Conferencing, or E5</span></span>| <span data-ttu-id="7b2af-184">Skype for Business Server 标准 CAL 或企业 CAL</span><span class="sxs-lookup"><span data-stu-id="7b2af-184">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="7b2af-185">为房间提供电话号码，并从房间拨打或接听电话或者使用电话号码加入电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="7b2af-185">Give the room a phone number and make or receive calls from the room or join a dial-in conference using a phone number</span></span> | <span data-ttu-id="7b2af-186">Skype for business 独立计划2，带有电话系统和 PSTN 语音呼叫计划</span><span class="sxs-lookup"><span data-stu-id="7b2af-186">Skype for Business Standalone Plan 2 with Phone System and a PSTN Voice Calling plan</span></span> | <span data-ttu-id="7b2af-187">与电话系统和 PSTN 语音呼叫计划（即 E5）的 E1 或 E3</span><span class="sxs-lookup"><span data-stu-id="7b2af-187">E1 or E3 with Phone System and a PSTN Voice Calling plan, or E5</span></span> | <span data-ttu-id="7b2af-188">Skype for Business Server 标准 CAL 或 Plus CAL</span><span class="sxs-lookup"><span data-stu-id="7b2af-188">Skype for Business Server Standard CAL or Plus CAL</span></span> |

<span data-ttu-id="7b2af-189">下表列出了 Office 365 计划和 Skype for Business 选项。</span><span class="sxs-lookup"><span data-stu-id="7b2af-189">The following table lists the Office 365 plans and Skype for Business options.</span></span>

| <span data-ttu-id="7b2af-190">O365 计划</span><span class="sxs-lookup"><span data-stu-id="7b2af-190">O365 Plan</span></span> | <span data-ttu-id="7b2af-191">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7b2af-191">Skype for Business</span></span> | <span data-ttu-id="7b2af-192">电话系统</span><span class="sxs-lookup"><span data-stu-id="7b2af-192">Phone System</span></span> | <span data-ttu-id="7b2af-193">音频会议</span><span class="sxs-lookup"><span data-stu-id="7b2af-193">Audio Conferencing</span></span> | <span data-ttu-id="7b2af-194">通话计划</span><span class="sxs-lookup"><span data-stu-id="7b2af-194">Calling Plans</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="7b2af-195">O365 商业协作版</span><span class="sxs-lookup"><span data-stu-id="7b2af-195">O365 Business Essentials</span></span> | <span data-ttu-id="7b2af-196">已包含</span><span class="sxs-lookup"><span data-stu-id="7b2af-196">Included</span></span> |  |  |  |
| <span data-ttu-id="7b2af-197">O365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="7b2af-197">O365 Business Premium</span></span> | <span data-ttu-id="7b2af-198">已包含</span><span class="sxs-lookup"><span data-stu-id="7b2af-198">Included</span></span> |  |  |  |
| <span data-ttu-id="7b2af-199">E1</span><span class="sxs-lookup"><span data-stu-id="7b2af-199">E1</span></span> | <span data-ttu-id="7b2af-200">已包含</span><span class="sxs-lookup"><span data-stu-id="7b2af-200">Included</span></span> | <span data-ttu-id="7b2af-201">加载项</span><span class="sxs-lookup"><span data-stu-id="7b2af-201">Add-on</span></span> | <span data-ttu-id="7b2af-202">加载项</span><span class="sxs-lookup"><span data-stu-id="7b2af-202">Add-on</span></span> | <span data-ttu-id="7b2af-203">加载项（需要电话系统加载项）</span><span class="sxs-lookup"><span data-stu-id="7b2af-203">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="7b2af-204">E3</span><span class="sxs-lookup"><span data-stu-id="7b2af-204">E3</span></span> | <span data-ttu-id="7b2af-205">已包含</span><span class="sxs-lookup"><span data-stu-id="7b2af-205">Included</span></span> | <span data-ttu-id="7b2af-206">加载项</span><span class="sxs-lookup"><span data-stu-id="7b2af-206">Add-on</span></span> | <span data-ttu-id="7b2af-207">加载项</span><span class="sxs-lookup"><span data-stu-id="7b2af-207">Add-on</span></span> | <span data-ttu-id="7b2af-208">加载项（需要电话系统加载项）</span><span class="sxs-lookup"><span data-stu-id="7b2af-208">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="7b2af-209">E5</span><span class="sxs-lookup"><span data-stu-id="7b2af-209">E5</span></span> | <span data-ttu-id="7b2af-210">已包含</span><span class="sxs-lookup"><span data-stu-id="7b2af-210">Included</span></span> | <span data-ttu-id="7b2af-211">已包含</span><span class="sxs-lookup"><span data-stu-id="7b2af-211">Included</span></span> | <span data-ttu-id="7b2af-212">已包含</span><span class="sxs-lookup"><span data-stu-id="7b2af-212">Included</span></span> | <span data-ttu-id="7b2af-213">加载项</span><span class="sxs-lookup"><span data-stu-id="7b2af-213">Add-on</span></span>  |

1. <span data-ttu-id="7b2af-214">首先，创建从电脑到 Skype for Business Online 环境的远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="7b2af-214">Start by creating a remote PowerShell session from a PC to the Skype for Business online environment.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="7b2af-215">若要为 Skype for Business Server 启用你的 Surface Hub 帐户，请运行此 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7b2af-215">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

<span data-ttu-id="7b2af-216">如果你不确定在你的环境中要用于 `RegistrarPool` 参数的值，你可以使用此 cmdlet 从现有 Skype for Business 用户获取值：</span><span class="sxs-lookup"><span data-stu-id="7b2af-216">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. <span data-ttu-id="7b2af-217">将 Skype for Business 许可证分配给你的 Surface Hub 帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-217">Assign Skype for Business license to your Surface Hub account.</span></span>

 <span data-ttu-id="7b2af-218">在完成上述用来在 Skype for Business Online 中启用 Surface Hub 帐户的步骤后，你需要将许可证分配给 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="7b2af-218">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="7b2af-219">使用 O365 管理门户，为设备分配 Skype for business Online （计划2）或 Skype for business Online （计划3）许可证。</span><span class="sxs-lookup"><span data-stu-id="7b2af-219">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="7b2af-220">以租户管理员身份登录、打开 O365 管理门户，然后单击管理员应用。</span><span class="sxs-lookup"><span data-stu-id="7b2af-220">Login as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="7b2af-221">单击**用户和组**，然后单击**添加用户、重置密码等**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-221">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="7b2af-222">单击 Surface Hub 帐户，然后单击笔图标以编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="7b2af-222">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="7b2af-223">单击**许可证**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-223">Click **Licenses**.</span></span>

- <span data-ttu-id="7b2af-224">在 "**分配许可证**" 中，选择 "skype for Business （计划1）" 或 "skype for business" （计划2），具体取决于你的许可和企业语音要求。</span><span class="sxs-lookup"><span data-stu-id="7b2af-224">In **Assign licenses**, select Skype for Business (Plan 1) or Skype for Business (Plan 2), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="7b2af-225">如果要在 Surface Hub 上使用企业语音，则必须使用计划2许可证。</span><span class="sxs-lookup"><span data-stu-id="7b2af-225">You'll have to use a Plan 2 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="7b2af-226">单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-226">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7b2af-227">还可以使用适用于 Windows Powershell 的 Windows Azure Active Directory 模块，运行分配这些许可证之一所需的 cmdlet，但此处未做介绍。</span><span class="sxs-lookup"><span data-stu-id="7b2af-227">You can also use the Windows Azure Active Directory Module for Windows Powershell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="7b2af-228">为了进行验证，你应该能使用任一 Skype for Business Client（电脑、Android 等）登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-228">For validation, you should be able to use any Skype for Business client (PC, Android, etc.) to sign in to this account.</span></span>

### <span data-ttu-id="7b2af-229">本地 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7b2af-229">Skype for Business on-premises</span></span>

<span data-ttu-id="7b2af-230">若要运行此 cmdlet，你将需要连接到 Skype 前端之一。</span><span class="sxs-lookup"><span data-stu-id="7b2af-230">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="7b2af-231">打开 Skype PowerShell 并运行：</span><span class="sxs-lookup"><span data-stu-id="7b2af-231">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="7b2af-232">混合 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7b2af-232">Skype for Business hybrid</span></span>

<span data-ttu-id="7b2af-233">如果你的组织已设置 [Skype for Business Server 和 Skype for Business Online ](https://technet.microsoft.com/library/jj205403.aspx)之间的混合连接，创建帐户的指南与标准 Surface Hub 部署不同。</span><span class="sxs-lookup"><span data-stu-id="7b2af-233">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="7b2af-234">Surface Hub 需要类型为 `meetingroom` 的 Skype 帐户，而普通用户将在 Skype 中使用用户类型帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-234">The Surface Hub requires a Skype account of the type `meetingroom`, while a normal user would use a user type account in Skype.</span></span> <span data-ttu-id="7b2af-235">如果针对一些用户在本地 Skype 服务器上，而一些用户托管在 Office 365 上的混合环境设置你的 Skype 服务器，你可能在尝试创建 Surface Hub 帐户时遇到几个问题。</span><span class="sxs-lookup"><span data-stu-id="7b2af-235">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="7b2af-236">在 Skype for Business Server 2015 混合环境中，你希望在 Skype for Business Online 中使用的任何用户都必须先在本地部署中创建，以便在 Active Directory 域服务中创建用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-236">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="7b2af-237">然后，您可以将用户移动到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="7b2af-237">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="7b2af-238">从本地到联机的用户帐户的移动通过[move-csuser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="7b2af-238">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="7b2af-239">若要移动 Csmeetingroom 对象，请使用[Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b2af-239">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="7b2af-240">若要使用 CsMeetingRoom cmdlet，你必须已安装适用于[Skype For Business Server 2015 的2017累积更新 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)或[Lync Server 2013 的7月2017累积更新 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)。</span><span class="sxs-lookup"><span data-stu-id="7b2af-240">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>


## <span data-ttu-id="7b2af-241">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7b2af-241">Exchange online</span></span>

<span data-ttu-id="7b2af-242">如果你使用 Exchange Online，请使用此过程。</span><span class="sxs-lookup"><span data-stu-id="7b2af-242">Use this procedure if you use Exchange online.</span></span>

1. <span data-ttu-id="7b2af-243">在 Office 365 中创建电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-243">Create an email account in Office 365.</span></span>

<span data-ttu-id="7b2af-244">在电脑上启动远程 PowerShell 会话，并连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="7b2af-244">Start a remote PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="7b2af-245">请确保已设置正确的权限来运行关联的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b2af-245">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. <span data-ttu-id="7b2af-246">设置邮箱。</span><span class="sxs-lookup"><span data-stu-id="7b2af-246">Set up a mailbox.</span></span>

<span data-ttu-id="7b2af-247">建立会话后，你将创建一个新邮箱并启用它作为 RoomMailboxAccount，或更改现有会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="7b2af-247">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="7b2af-248">这将允许在 Surface Hub 中对帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7b2af-248">This will allow the account to authenticate into the Surface Hub.</span></span>

<span data-ttu-id="7b2af-249">如果要更改现有资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="7b2af-249">If you're changing an existing resource mailbox:</span></span>

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="7b2af-250">如果要创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="7b2af-250">If you’re creating a new resource mailbox:</span></span>

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. <span data-ttu-id="7b2af-251">创建 Exchange ActiveSync 策略。</span><span class="sxs-lookup"><span data-stu-id="7b2af-251">Create Exchange ActiveSync policy.</span></span>

<span data-ttu-id="7b2af-252">设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。</span><span class="sxs-lookup"><span data-stu-id="7b2af-252">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="7b2af-253">Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 False）兼容。</span><span class="sxs-lookup"><span data-stu-id="7b2af-253">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="7b2af-254">如果未正确设置，Surface Hub （"邮件"、"日历" 和 "加入会议"）上的 Exchange 服务将不会启用。</span><span class="sxs-lookup"><span data-stu-id="7b2af-254">If this isn’t set properly, Exchange services on the Surface Hub (mail, calendar, and joining meetings) will not be enabled.</span></span>

<span data-ttu-id="7b2af-255">如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。</span><span class="sxs-lookup"><span data-stu-id="7b2af-255">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="7b2af-256">完成创建后，你可以对其他设备帐户应用相同的策略。</span><span class="sxs-lookup"><span data-stu-id="7b2af-256">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="7b2af-257">一旦你有兼容的策略，你将需要将策略应用到设备帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-257">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> <span data-ttu-id="7b2af-258">但是，仅可以将策略应用到用户帐户，而非资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="7b2af-258">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="7b2af-259">你需要将邮箱转换为用户类型、应用策略，然后将其转换回邮箱 — 你可能需要重新启用它并重新设置密码。</span><span class="sxs-lookup"><span data-stu-id="7b2af-259">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. <span data-ttu-id="7b2af-260">设置 Exchange 属性。</span><span class="sxs-lookup"><span data-stu-id="7b2af-260">Set Exchange properties.</span></span>

<span data-ttu-id="7b2af-261">必须在设备帐户上设置各种 Exchange 属性才能改进会议体验。</span><span class="sxs-lookup"><span data-stu-id="7b2af-261">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="7b2af-262">你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md) 部分中查看需要设置哪些属性。</span><span class="sxs-lookup"><span data-stu-id="7b2af-262">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. <span data-ttu-id="7b2af-263">为您的本地域帐户添加电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7b2af-263">Add an email address for your on-premises domain account.</span></span>

<span data-ttu-id="7b2af-264">在此过程中，你将使用 AD 管理员工具为你的本地域帐户添加电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7b2af-264">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span>

- <span data-ttu-id="7b2af-265">在 **Active Directory 用户和计算机** AD 工具中，右键单击将在其中创建 Surface Hub 帐户的文件夹或组织单位，然后依次单击**新建**和**用户**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-265">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="7b2af-266">将上一 cmdlet 的显示名称键入到**全名**框中，而将别名键入到**用户登录名称**框中。</span><span class="sxs-lookup"><span data-stu-id="7b2af-266">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="7b2af-267">单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-267">Click **Next**.</span></span>

![用于在 Active Directory 中创建新用户的新对象框。](images/hybriddeployment-01a.png)

- <span data-ttu-id="7b2af-269">键入此帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="7b2af-269">Type the password for this account.</span></span> <span data-ttu-id="7b2af-270">你将需要重新键入它以供验证。</span><span class="sxs-lookup"><span data-stu-id="7b2af-270">You'll need to retype it for verification.</span></span> <span data-ttu-id="7b2af-271">请确保**密码永不过期**复选框是唯一处于选中状态的选项。</span><span class="sxs-lookup"><span data-stu-id="7b2af-271">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b2af-272">选择 "**密码永不过期**" 是对 Surface Hub 上的 Skype for business 的要求。</span><span class="sxs-lookup"><span data-stu-id="7b2af-272">Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="7b2af-273">域规则可能会禁止未过期的密码。</span><span class="sxs-lookup"><span data-stu-id="7b2af-273">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="7b2af-274">如果是这样，你将需要针对每个 Surface Hub 设备帐户创建例外。</span><span class="sxs-lookup"><span data-stu-id="7b2af-274">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![显示密码对话框的图像。](images/hybriddeployment-02a.png)

- <span data-ttu-id="7b2af-276">单击**完成**以创建帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-276">Click **Finish** to create the account.</span></span>

![具有新用户的帐户名称、登录名称和密码选项的图像。](images/hybriddeployment-03a.png)

6. <span data-ttu-id="7b2af-278">运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="7b2af-278">Run directory synchronization.</span></span>

<span data-ttu-id="7b2af-279">创建完帐户后，运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="7b2af-279">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="7b2af-280">完成后，请转到用户页，并验证前面步骤中创建的两个帐户是否已合并。</span><span class="sxs-lookup"><span data-stu-id="7b2af-280">When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

7. <span data-ttu-id="7b2af-281">连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7b2af-281">Connect to Azure AD.</span></span>

<span data-ttu-id="7b2af-282">首先需要安装 PowerShell 版本 2 的 Azure AD 模块。</span><span class="sxs-lookup"><span data-stu-id="7b2af-282">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="7b2af-283">在提升的 PowerShell 提示符下，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b2af-283">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="7b2af-284">需要连接到 Azure AD 才能应用某些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="7b2af-284">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="7b2af-285">你可以运行此 cmdlet 连接到：</span><span class="sxs-lookup"><span data-stu-id="7b2af-285">You can run this cmdlet to connect:</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="7b2af-286">分配 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="7b2af-286">Assign an Office 365 license.</span></span>

<span data-ttu-id="7b2af-287">设备帐户需要有一个有效的 Office 365 (O365) 许可证，否则 Exchange 和 Skype for Business 将不可用。</span><span class="sxs-lookup"><span data-stu-id="7b2af-287">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="7b2af-288">如果已拥有许可证，则需要将使用位置分配给设备帐户，以便确定适用于你的帐户的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="7b2af-288">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="7b2af-289">接下来，可使用 `Get-AzureADSubscribedSku` 检索可供 O365 租户使用的 SKU 列表。</span><span class="sxs-lookup"><span data-stu-id="7b2af-289">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="7b2af-290">列出 SKU 后，需要将所需的 SkuId 分配给 `$License.SkuId` 变量。</span><span class="sxs-lookup"><span data-stu-id="7b2af-290">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

<span data-ttu-id="7b2af-291">接下来，使用 [Skype for Business Online](#skype-for-business-online)、[本地 Skype for Business](#skype-for-business-on-premises) 或[混合 Skype for Business](#skype-for-business-hybrid) 启用设备帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-291">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="7b2af-292">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7b2af-292">Skype for Business Online</span></span>

<span data-ttu-id="7b2af-293">为了启用 Skype for Business，你的环境将需要满足 [Skype for Business Online 的必备条件](#skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="7b2af-293">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](#skype-for-business-online).</span></span>

1. <span data-ttu-id="7b2af-294">首先，创建从电脑到 Skype for Business Online 环境的远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="7b2af-294">Start by creating a remote PowerShell session to the Skype for Business online environment from a PC.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="7b2af-295">若要为 Skype for Business Server 启用你的 Surface Hub 帐户，请运行此 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7b2af-295">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   <span data-ttu-id="7b2af-296">如果你不确定在你的环境中要用于 `RegistrarPool` 参数的值，你可以使用此 cmdlet 从现有 Skype for Business 用户获取值：</span><span class="sxs-lookup"><span data-stu-id="7b2af-296">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. <span data-ttu-id="7b2af-297">将 Skype for Business 许可证分配给你的 Surface Hub 帐户</span><span class="sxs-lookup"><span data-stu-id="7b2af-297">Assign Skype for Business license to your Surface Hub account</span></span>

<span data-ttu-id="7b2af-298">在完成上述用来在 Skype for Business Online 中启用 Surface Hub 帐户的步骤后，你需要将许可证分配给 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="7b2af-298">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="7b2af-299">使用 O365 管理门户，为设备分配 Skype for business Online （计划2）或 Skype for business Online （计划3）许可证。</span><span class="sxs-lookup"><span data-stu-id="7b2af-299">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="7b2af-300">以租户管理员身份登录、打开 O365 管理门户，然后单击管理员应用。</span><span class="sxs-lookup"><span data-stu-id="7b2af-300">Sign in as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="7b2af-301">单击**用户和组**，然后单击**添加用户、重置密码等**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-301">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="7b2af-302">单击 Surface Hub 帐户，然后单击笔图标以编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="7b2af-302">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="7b2af-303">单击**许可证**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-303">Click **Licenses**.</span></span>

- <span data-ttu-id="7b2af-304">在**分配许可证**中，选择 Skype for Business（计划 2）或 Skype for Business（计划 3），具体取决于你的许可和企业语音要求。</span><span class="sxs-lookup"><span data-stu-id="7b2af-304">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="7b2af-305">如果你想要在 Surface Hub 上使用企业语音，你将需要使用计划 3 许可证。</span><span class="sxs-lookup"><span data-stu-id="7b2af-305">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="7b2af-306">单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="7b2af-306">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7b2af-307">你还可以使用适用于 Windows PowerShell 的 Windows Azure Active Directory 模块，运行分配这些许可证之一所需的 cmdlet，但此处未做介绍。</span><span class="sxs-lookup"><span data-stu-id="7b2af-307">You can also use the Windows Azure Active Directory Module for Windows PowerShell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="7b2af-308">为了进行验证，你应该能使用任一 Skype for Business Client（电脑、Android 等）登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-308">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>

### <span data-ttu-id="7b2af-309">本地 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7b2af-309">Skype for Business on-premises</span></span>

<span data-ttu-id="7b2af-310">若要运行此 cmdlet，你将需要连接到 Skype 前端之一。</span><span class="sxs-lookup"><span data-stu-id="7b2af-310">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="7b2af-311">打开 Skype PowerShell 并运行：</span><span class="sxs-lookup"><span data-stu-id="7b2af-311">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="7b2af-312">混合 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7b2af-312">Skype for Business hybrid</span></span>

<span data-ttu-id="7b2af-313">如果你的组织已设置 [Skype for Business Server 和 Skype for Business Online ](https://technet.microsoft.com/library/jj205403.aspx)之间的混合连接，创建帐户的指南与标准 Surface Hub 部署不同。</span><span class="sxs-lookup"><span data-stu-id="7b2af-313">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="7b2af-314">Surface Hub 需要类型为*会议室*的 Skype 帐户，而普通用户将在 Skype 中使用*用户*类型帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-314">The Surface Hub requires a Skype account of the type *meetingroom*, while a normal user would use a *user* type account in Skype.</span></span> <span data-ttu-id="7b2af-315">如果针对一些用户在本地 Skype 服务器上，而一些用户托管在 Office 365 上的混合环境设置你的 Skype 服务器，你可能在尝试创建 Surface Hub 帐户时遇到几个问题。</span><span class="sxs-lookup"><span data-stu-id="7b2af-315">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="7b2af-316">在 Skype for Business Server 2015 混合环境中，你希望在 Skype for Business Online 中使用的任何用户都必须先在本地部署中创建，以便在 Active Directory 域服务中创建用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7b2af-316">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="7b2af-317">然后，您可以将用户移动到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="7b2af-317">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="7b2af-318">从本地到联机的用户帐户的移动通过[move-csuser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="7b2af-318">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="7b2af-319">若要移动 Csmeetingroom 对象，请使用[Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b2af-319">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="7b2af-320">若要使用 CsMeetingRoom cmdlet，你必须已安装适用于[Skype For Business Server 2015 的2017累积更新 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)或[Lync Server 2013 的7月2017累积更新 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)。</span><span class="sxs-lookup"><span data-stu-id="7b2af-320">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>

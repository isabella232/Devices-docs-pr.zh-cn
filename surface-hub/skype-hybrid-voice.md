---
title: 使用 Skype 混合语音环境的联机或混合部署 (Surface Hub)
description: 本主题介绍了如何通过云连接器版本或 Skype for Business 2015 池使用本地 PSTN 连接启用 Skype for Business 云 PBX。
keywords: 混合部署, Skype 混合语音
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831943"
---
# <span data-ttu-id="aeb99-104">使用 Skype 混合语音环境的联机或混合部署 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="aeb99-104">Online or hybrid deployment using Skype Hybrid Voice environment  (Surface Hub)</span></span>

<span data-ttu-id="aeb99-105">本主题介绍了如何通过云连接器或 Skype for Business 2015 池使用本地公用电话交换网 (PSTN) 连接启用 Skype for Business 云 PBX。</span><span class="sxs-lookup"><span data-stu-id="aeb99-105">This topic explains how to enable Skype for Business Cloud PBX with on-premises Public Switched Telephone Network (PSTN) connectivity via Cloud Connector Edition or Skype for Business 2015 pool.</span></span> <span data-ttu-id="aeb99-106">在此选项中，</span><span class="sxs-lookup"><span data-stu-id="aeb99-106">In this option.</span></span> <span data-ttu-id="aeb99-107">Skype for Business 主池和 Exchange 服务器都位于云中，并通过运行 Skype for Business 2015 或云连接版本的本地池由 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="aeb99-107">your Skype for Business home pools and Exchange servers are in the cloud, and are connected by PSTN via an on-premises pool running Skype for Business 2015 or Cloud Connector edition.</span></span> <span data-ttu-id="aeb99-108">[了解有关不同的云 PBX 选项的详细信息](https://technet.microsoft.com/library/mt612869.aspx)。</span><span class="sxs-lookup"><span data-stu-id="aeb99-108">[Learn more about different Cloud PBX options](https://technet.microsoft.com/library/mt612869.aspx).</span></span>  

<span data-ttu-id="aeb99-109">如果使用混合语音选项之一部署 Skype for Business 云 PBX，请执行以下步骤，为 Surface Hub 启用会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="aeb99-109">If you deployed Skype for Business Cloud PBX with one of the hybrid voice options, follow the steps below to enable the room account for Surface Hub.</span></span> <span data-ttu-id="aeb99-110">请务必先创建常规用户帐户，分配所有混合语音选项和电话号码，然后再将该帐户转换为会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="aeb99-110">It is important to create a regular user account first, assign all hybrid voice options and phone numbers, and then convert the account to a room account.</span></span> <span data-ttu-id="aeb99-111">如果未遵循此顺序，将无法分配混合电话号码。</span><span class="sxs-lookup"><span data-stu-id="aeb99-111">If you do not follow this order, you will not be able to assign a hybrid phone number.</span></span>  

>[!WARNING]
><span data-ttu-id="aeb99-112">如果在配置混合语音前创建帐户（运行 Enable-CSMeetingRoom 命令），将无法配置需要的混合语音参数。</span><span class="sxs-lookup"><span data-stu-id="aeb99-112">If you create an account before configuration of Hybrid voice (you run Enable-CSMeetingRoom command), you will not be able to configure required hybrid voice parameters.</span></span> <span data-ttu-id="aeb99-113">若要为之前配置的帐户配置混合语音参数或重新配置电话号码，请删除 E5 或 E3 + 云 PBX 加载项许可证，然后执行以下步骤，从步骤 3 开始。</span><span class="sxs-lookup"><span data-stu-id="aeb99-113">In order to configure hybrid voice parameters for a previously configured account or to reconfigure a phone number, delete the E5 or E3  + Cloud PBX add-on license, and then follow the steps below, starting at step 3.</span></span>

1. <span data-ttu-id="aeb99-114">创建新的 Surface Hub 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aeb99-114">Create a new user account for Surface Hub.</span></span> <span data-ttu-id="aeb99-115">此示例使用 <strong> surfacehub2@adatum.com </strong> 。</span><span class="sxs-lookup"><span data-stu-id="aeb99-115">This example uses <strong>surfacehub2@adatum.com</strong>.</span></span> <span data-ttu-id="aeb99-116">可在本地 Active Directory 中创建帐户并将其同步到云，或直接在云中创建。</span><span class="sxs-lookup"><span data-stu-id="aeb99-116">The account can be created in local Active Directory and synchronized to the cloud, or created directly in the cloud.</span></span> 

    ![新建对象 - 用户](images/new-user-hybrid-voice.png)

2. <span data-ttu-id="aeb99-118">选择**密码永不过期**。</span><span class="sxs-lookup"><span data-stu-id="aeb99-118">Select **Password Never Expires**.</span></span> <span data-ttu-id="aeb99-119">这对于 Surface Hub 设备非常重要。</span><span class="sxs-lookup"><span data-stu-id="aeb99-119">This is important for a Surface Hub device.</span></span>

   ![密码永不过期](images/new-user-password-hybrid-voice.png)

3. <span data-ttu-id="aeb99-121">在 Office 365 中，将 **E5** 许可证或 **E3 和云 PBX** 加载项添加至针对会议室创建的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aeb99-121">In Office 365, add **E5** license or **E3 and Cloud PBX** add-on to the user account created for the room.</span></span> <span data-ttu-id="aeb99-122">这是使用混合语音的必需条件。</span><span class="sxs-lookup"><span data-stu-id="aeb99-122">This is required for Hybrid Voice to work.</span></span>

   ![添加产品许可证](images/product-license-hybrid-voice.png)

4. <span data-ttu-id="aeb99-124">等待大约 15 分钟，直到 Skype for Business Online 中出现会议室用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aeb99-124">Wait approximately 15 minutes until the user account for the room appears in Skype for Business Online.</span></span>

5. <span data-ttu-id="aeb99-125">在 Skype for Business Online 中创建会议室用户帐户后，通过运行下列 cmdlet 在 Skype for Business 远程 PowerShell 中对混合语音启用它：</span><span class="sxs-lookup"><span data-stu-id="aeb99-125">After the user account for room is created in Skype for Business Online, enable it for Hybrid Voice in Skype for Business Remote PowerShell by running the following cmdlet:</span></span>

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. <span data-ttu-id="aeb99-126">通过从 Surface Hub 拨打测试电话验证混合语音呼叫流。</span><span class="sxs-lookup"><span data-stu-id="aeb99-126">Validate Hybrid Voice call flow by placing test calls from the Surface Hub.</span></span>

7. <span data-ttu-id="aeb99-127">在电脑上启动远程 PowerShell 会话，并通过运行下列 cmdlet 连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="aeb99-127">Start a remote PowerShell session on a PC and connect to Exchange by running the following cmdlets.</span></span>

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. <span data-ttu-id="aeb99-128">建立会话后，通过运行下列 cmdlet 修改会议室的用户帐户以将其作为 **RoomMailboxAccount** 启用。</span><span class="sxs-lookup"><span data-stu-id="aeb99-128">After establishing a session, modify the user account for the room to enable it as a **RoomMailboxAccount** by running the following cmdlets.</span></span> <span data-ttu-id="aeb99-129">这会允许在 Surface Hub 中对帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="aeb99-129">This allows the account to authenticate with Surface Hub.</span></span>

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. <span data-ttu-id="aeb99-130">设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。</span><span class="sxs-lookup"><span data-stu-id="aeb99-130">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="aeb99-131">Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 **False**）兼容。</span><span class="sxs-lookup"><span data-stu-id="aeb99-131">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="aeb99-132">如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。</span><span class="sxs-lookup"><span data-stu-id="aeb99-132">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>
    
   <span data-ttu-id="aeb99-133">如果尚未创建兼容的策略，请使用以下 cmdlet（该 cmdlet 将创建名为“Surface Hubs”的策略）。</span><span class="sxs-lookup"><span data-stu-id="aeb99-133">If you haven’t created a compatible policy yet, use the following cmdlet (this one creates a policy called "Surface Hubs").</span></span> <span data-ttu-id="aeb99-134">完成创建后，你可以对其他设备帐户应用相同的策略。</span><span class="sxs-lookup"><span data-stu-id="aeb99-134">After it’s created, you can apply the same policy to other device accounts.</span></span>

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   <span data-ttu-id="aeb99-135">具有兼容的策略后，你需要将该策略应用于设备帐户。</span><span class="sxs-lookup"><span data-stu-id="aeb99-135">After you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="aeb99-136">但是，仅可以将策略应用到用户帐户，而非资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="aeb99-136">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="aeb99-137">运行下列 cmdlet 将邮箱转换为用户类型、应用策略，然后将其转换回邮箱（你可能需要重新启用此帐户并重新设置密码）。</span><span class="sxs-lookup"><span data-stu-id="aeb99-137">Run the following cmdlets to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox (you may need to re-enable the account and set the password again).</span></span>
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. <span data-ttu-id="aeb99-138">必须在设备帐户上设置各种 Exchange 属性才能改进会议体验。</span><span class="sxs-lookup"><span data-stu-id="aeb99-138">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="aeb99-139">可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)中查看可以设置哪些属性。</span><span class="sxs-lookup"><span data-stu-id="aeb99-139">You can see which properties can be set in [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> <span data-ttu-id="aeb99-140">以下 cmdlet 提供了设置 Exchange 属性的示例。</span><span class="sxs-lookup"><span data-stu-id="aeb99-140">The following cmdlets provide an example of setting Exchange properties.</span></span>

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. <span data-ttu-id="aeb99-141">在 Skype for Business Online 中将邮箱作为会议室设备启用。</span><span class="sxs-lookup"><span data-stu-id="aeb99-141">Enable the mailbox as a meeting device in Skype for Business Online.</span></span> <span data-ttu-id="aeb99-142">运行以下支持将帐户作为会议设备的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aeb99-142">Run the following cmdlet which enables the account as a meeting device.</span></span> 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    <span data-ttu-id="aeb99-143">运行此 cmdlet 后，系统将询问用户是否在会议室中，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="aeb99-143">As a result of running this cmdlet, users will be asked if they are in a meeting room, as shown in the following image.</span></span> <span data-ttu-id="aeb99-144">**是**会使麦克风和扬声器静音。</span><span class="sxs-lookup"><span data-stu-id="aeb99-144">**Yes** will mute the microphone and speaker.</span></span>

    ![](images/adjust-room-audio.png)


    
<span data-ttu-id="aeb99-145">此时，已完全配置会议室帐户，包括混合语音。</span><span class="sxs-lookup"><span data-stu-id="aeb99-145">At this moment the room account is fully configured, including Hybrid Voice.</span></span> <span data-ttu-id="aeb99-146">如果使用本地 Skype，可以在本地配置如描述、位置等附加属性。</span><span class="sxs-lookup"><span data-stu-id="aeb99-146">If you use Skype on-premises, you can configure additional attributes, like description, location, etc., on-premises.</span></span> <span data-ttu-id="aeb99-147">如果在 Skype Online 中创建会议室，则可以联机设置这些参数。</span><span class="sxs-lookup"><span data-stu-id="aeb99-147">If you create a room in Skype Online, these parameters can be set online.</span></span> 

<span data-ttu-id="aeb99-148">在下图中，可以看到向用户显示设备的方式。</span><span class="sxs-lookup"><span data-stu-id="aeb99-148">In the following image, you can see how the device appears to users.</span></span>


![](images/select-room-hybrid-voice.png)

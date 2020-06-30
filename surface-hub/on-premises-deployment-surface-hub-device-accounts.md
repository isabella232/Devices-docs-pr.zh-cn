---
title: 本地部署单林 (Surface Hub)
description: 本主题介绍如何在具有单林的本地部署时为 Microsoft Surface Hub 添加设备帐户。
ms.assetid: 80E12195-A65B-42D1-8B84-ECC3FCBAAFC6
ms.reviewer: ''
manager: laurawi
keywords: 单林部署, 本地部署, 设备帐户, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.localizationpriority: medium
ms.openlocfilehash: 37b157268769ddcdeaef67b7e19cc7260cd392b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831811"
---
# <span data-ttu-id="924c2-104">单林环境中 Surface Hub 的本地部署</span><span class="sxs-lookup"><span data-stu-id="924c2-104">On-premises deployment for Surface Hub in a single-forest environment</span></span>


<span data-ttu-id="924c2-105">本主题介绍如何在具有单林的本地部署时为 Microsoft Surface Hub 添加设备帐户。</span><span class="sxs-lookup"><span data-stu-id="924c2-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a single-forest, on-premises deployment.</span></span>

<span data-ttu-id="924c2-106">如果具有带 Microsoft Exchange 2013 或更高版本和 Skype for Business 2013 或更高版本的单林本地部署，则可以[使用提供的 PowerShell 脚本](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts)创建设备帐户。</span><span class="sxs-lookup"><span data-stu-id="924c2-106">If you have a single-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="924c2-107">如果使用的是多林部署，请参阅[多林环境中 Surface Hub 的本地部署](on-premises-deployment-surface-hub-multi-forest.md)。</span><span class="sxs-lookup"><span data-stu-id="924c2-107">If you’re using a multi-forest deployment, see [On-premises deployment for Surface Hub in a multi-forest environment](on-premises-deployment-surface-hub-multi-forest.md).</span></span>

1. <span data-ttu-id="924c2-108">在电脑上启动远程 PowerShell 会话，并连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="924c2-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

   <span data-ttu-id="924c2-109">请确保已设置正确的权限来运行关联的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="924c2-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   <span data-ttu-id="924c2-110">请注意下面，`$strExchangeServer` 是你的 Exchange Server 的完全限定的域名 (FQDN)，而 `$strLyncFQDN` 是你的 Skype for Business 服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="924c2-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. <span data-ttu-id="924c2-111">建立会话后，你将创建一个新邮箱并启用它作为 RoomMailboxAccount，或更改现有会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="924c2-111">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="924c2-112">这将允许在 Surface Hub 中对帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="924c2-112">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="924c2-113">如果要更改现有资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="924c2-113">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="924c2-114">如果要创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="924c2-114">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> <span data-ttu-id="924c2-115">需要启用 ActiveSync 虚拟目录基本身份验证，因为 Surface Hub 无法使用其他身份验证方法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="924c2-115">ActiveSync Virtual Directory Basic Authentication is required to be enabled as the Surface Hub is unable to authenticate using other authentication methods.</span></span>

3. <span data-ttu-id="924c2-116">设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。</span><span class="sxs-lookup"><span data-stu-id="924c2-116">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="924c2-117">Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 False）兼容。</span><span class="sxs-lookup"><span data-stu-id="924c2-117">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="924c2-118">如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。</span><span class="sxs-lookup"><span data-stu-id="924c2-118">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="924c2-119">如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。</span><span class="sxs-lookup"><span data-stu-id="924c2-119">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="924c2-120">完成创建后，你可以对其他设备帐户应用相同的策略。</span><span class="sxs-lookup"><span data-stu-id="924c2-120">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   <span data-ttu-id="924c2-121">具有兼容的策略后，你需要将该策略应用于设备帐户。</span><span class="sxs-lookup"><span data-stu-id="924c2-121">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="924c2-122">但是，仅可以将策略应用到用户帐户，而非资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="924c2-122">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="924c2-123">你需要将邮箱转换为用户类型、应用策略，然后将其转换回邮箱 — 你可能需要重新启用它并重新设置密码。</span><span class="sxs-lookup"><span data-stu-id="924c2-123">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. <span data-ttu-id="924c2-124">可在设备帐户上设置各种 Exchange 属性以改进用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="924c2-124">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="924c2-125">你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)部分中查看需要设置哪些属性。</span><span class="sxs-lookup"><span data-stu-id="924c2-125">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="924c2-126">如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。</span><span class="sxs-lookup"><span data-stu-id="924c2-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="924c2-127">有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="924c2-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. <span data-ttu-id="924c2-128">启用 Active Directory 中的帐户，以便它将在 Surface Hub 中进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="924c2-128">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. <span data-ttu-id="924c2-129">通过在 Skype for Business Server 池上启用你的 Surface Hub AD 帐户，使用 Skype for Business 启用设备帐户：</span><span class="sxs-lookup"><span data-stu-id="924c2-129">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   <span data-ttu-id="924c2-130">你将需要针对 Surface Hub 使用会话初始协议 (SIP) 地址和域控制器，以及你自己的 Skype for Business Server 池标识符和用户身份。</span><span class="sxs-lookup"><span data-stu-id="924c2-130">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>

8. <span data-ttu-id="924c2-131">可选：你还可以通过为你的帐户启用企业语音，从而让你的 Surface Hub 可以接打公用电话交换网 (PSTN) 电话。</span><span class="sxs-lookup"><span data-stu-id="924c2-131">OPTIONAL: You can also allow your Surface Hub to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="924c2-132">Surface Hub 不要求企业语音，但是如果你想要使用 Surface Hub 客户端的 PSTN 拨号功能，下面是启用它的方法：</span><span class="sxs-lookup"><span data-stu-id="924c2-132">Enterprise Voice isn't a requirement for Surface Hub, but if you want PSTN dialing functionality for the Surface Hub client, here's how to enable it:</span></span>

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   <span data-ttu-id="924c2-133">同样，您需要将所提供的域控制器和电话号码示例替换为您自己的信息。</span><span class="sxs-lookup"><span data-stu-id="924c2-133">Again, you need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="924c2-134">参数值 `$true` 保持不变。</span><span class="sxs-lookup"><span data-stu-id="924c2-134">The parameter value `$true` stays the same.</span></span>
    

 ## <span data-ttu-id="924c2-135">禁用匿名电子邮件和即时消息</span><span class="sxs-lookup"><span data-stu-id="924c2-135">Disable anonymous email and IM</span></span>




<span data-ttu-id="924c2-136">Surface Hub 使用设备帐户提供电子邮件和协作服务（IM、视频和语音）。</span><span class="sxs-lookup"><span data-stu-id="924c2-136">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="924c2-137">此设备帐户在发送电子邮件、即时消息和呼叫时用作源标识（"发件人" 一方）。</span><span class="sxs-lookup"><span data-stu-id="924c2-137">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="924c2-138">由于此帐户不是来自个人可标识的用户，因此它被视为 "匿名"，因为它来源于 Surface Hub 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="924c2-138">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="924c2-139">假设你有一个每用户客户端策略，该策略分配给每个具有**SurfaceHubPolicy**标识的会议室设备。</span><span class="sxs-lookup"><span data-stu-id="924c2-139">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="924c2-140">若要禁用匿名电子邮件和消息，请使用以下命令将 clientPolicyEntry 添加到此客户端策略。</span><span class="sxs-lookup"><span data-stu-id="924c2-140">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="924c2-141">若要验证是否已设置策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="924c2-141">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="924c2-142">输出应为：</span><span class="sxs-lookup"><span data-stu-id="924c2-142">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="924c2-143">若要更改策略条目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="924c2-143">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="924c2-144">要删除策略条目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="924c2-144">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```

 






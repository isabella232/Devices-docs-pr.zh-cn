---
title: 本地部署多林 (Surface Hub)
description: 本主题介绍如何在具有多林的本地部署时为 Microsoft Surface Hub 添加设备帐户。
keywords: 多林部署, 本地部署, 设备帐户, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831795"
---
# <span data-ttu-id="95310-104">多林环境中的 Surface Hub 的本地部署</span><span class="sxs-lookup"><span data-stu-id="95310-104">On-premises deployment for Surface Hub in a multi-forest environment</span></span>


<span data-ttu-id="95310-105">本主题介绍如何在具有多林的本地部署时为 Microsoft Surface Hub 添加设备帐户。</span><span class="sxs-lookup"><span data-stu-id="95310-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a multi-forest, on-premises deployment.</span></span>

<span data-ttu-id="95310-106">如果具有带 Microsoft Exchange 2013 或更高版本和 Skype for Business 2013 或更高版本的多林本地部署，则可以[使用提供的 PowerShell 脚本](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts)创建设备帐户。</span><span class="sxs-lookup"><span data-stu-id="95310-106">If you have a multi-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="95310-107">如果使用的是单林部署，请参阅[单林环境中 Surface Hub 的本地部署](on-premises-deployment-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="95310-107">If you’re using a single-forest deployment, see [On-premises deployment for Surface Hub in a single-forest environment](on-premises-deployment-surface-hub-device-accounts.md).</span></span>

1.  <span data-ttu-id="95310-108">在电脑上启动远程 PowerShell 会话，并连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="95310-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

    <span data-ttu-id="95310-109">请确保已设置正确的权限来运行关联的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95310-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

    <span data-ttu-id="95310-110">请注意下面，`$strExchangeServer` 是你的 Exchange Server 的完全限定的域名 (FQDN)，而 `$strLyncFQDN` 是你的 Skype for Business Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="95310-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  <span data-ttu-id="95310-111">建立会话后，在资源林中创建新的邮箱。</span><span class="sxs-lookup"><span data-stu-id="95310-111">After establishing a session, create a new mailbox in the Resource Forest.</span></span> <span data-ttu-id="95310-112">这将允许帐户在 Surface Hub 中进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="95310-112">This will allow the account to authenticate into the Surface Hub.</span></span>

    <span data-ttu-id="95310-113">如果要更改现有资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="95310-113">If you're changing an existing resource mailbox:</span></span>

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  <span data-ttu-id="95310-114">设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用现有兼容的策略。</span><span class="sxs-lookup"><span data-stu-id="95310-114">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

    <span data-ttu-id="95310-115">Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 **False**）兼容。</span><span class="sxs-lookup"><span data-stu-id="95310-115">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="95310-116">如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。</span><span class="sxs-lookup"><span data-stu-id="95310-116">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

    <span data-ttu-id="95310-117">如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。</span><span class="sxs-lookup"><span data-stu-id="95310-117">If you haven’t created a compatible policy yet, use the following cmdlet-—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="95310-118">完成创建后，你可以对其他设备帐户应用相同的策略。</span><span class="sxs-lookup"><span data-stu-id="95310-118">Once it’s created, you can apply the same policy to other device accounts.</span></span>

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    <span data-ttu-id="95310-119">具有兼容的策略后，需要将该策略应用于设备帐户。</span><span class="sxs-lookup"><span data-stu-id="95310-119">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  <span data-ttu-id="95310-120">可在设备帐户上设置各种 Exchange 属性，以改进用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="95310-120">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="95310-121">你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)部分中查看需要设置哪些属性。</span><span class="sxs-lookup"><span data-stu-id="95310-121">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="95310-122">如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。</span><span class="sxs-lookup"><span data-stu-id="95310-122">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="95310-123">有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="95310-123">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span> <span data-ttu-id="95310-124">这应该在用户林中设置。</span><span class="sxs-lookup"><span data-stu-id="95310-124">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  <span data-ttu-id="95310-125">在 Active Directory 中启用帐户，以便它对 Surface Hub 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="95310-125">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span> <span data-ttu-id="95310-126">这应该在用户林中设置。</span><span class="sxs-lookup"><span data-stu-id="95310-126">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. <span data-ttu-id="95310-127">你现在需要将会议室邮箱更改为已链接的邮箱：</span><span class="sxs-lookup"><span data-stu-id="95310-127">You now need to change the room mailbox to a linked mailbox:</span></span>

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  <span data-ttu-id="95310-128">通过在 Skype for Business Server 池上启用 Surface Hub AD 帐户，启用带 Skype for Business 的设备帐户：</span><span class="sxs-lookup"><span data-stu-id="95310-128">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    <span data-ttu-id="95310-129">你将需要针对 Surface Hub 使用会话初始协议 (SIP) 地址和域控制器，以及你自己的 Skype for Business Server 池标识符和用户身份。</span><span class="sxs-lookup"><span data-stu-id="95310-129">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>


## <span data-ttu-id="95310-130">禁用匿名电子邮件和即时消息</span><span class="sxs-lookup"><span data-stu-id="95310-130">Disable anonymous email and IM</span></span>



<span data-ttu-id="95310-131">Surface Hub 使用设备帐户提供电子邮件和协作服务（IM、视频和语音）。</span><span class="sxs-lookup"><span data-stu-id="95310-131">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="95310-132">此设备帐户在发送电子邮件、即时消息和呼叫时用作源标识（"发件人" 一方）。</span><span class="sxs-lookup"><span data-stu-id="95310-132">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="95310-133">由于此帐户不是来自个人可标识的用户，因此它被视为 "匿名"，因为它来源于 Surface Hub 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="95310-133">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="95310-134">假设你有一个每用户客户端策略，该策略分配给每个具有**SurfaceHubPolicy**标识的会议室设备。</span><span class="sxs-lookup"><span data-stu-id="95310-134">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="95310-135">若要禁用匿名电子邮件和消息，请使用以下命令将 clientPolicyEntry 添加到此客户端策略。</span><span class="sxs-lookup"><span data-stu-id="95310-135">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="95310-136">若要验证是否已设置策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95310-136">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="95310-137">输出应为：</span><span class="sxs-lookup"><span data-stu-id="95310-137">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="95310-138">若要更改策略条目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95310-138">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="95310-139">要删除策略条目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95310-139">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 






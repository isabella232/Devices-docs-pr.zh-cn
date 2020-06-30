---
title: 使用 Office 365 的联机部署 (Surface Hub)
description: 本主题提供有关在具有纯联机部署时为 Microsoft Surface Hub 添加设备帐户的说明。
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 的设备帐户, 联机部署
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831792"
---
# <span data-ttu-id="f4b1c-104">使用 Office 365 的联机部署 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="f4b1c-104">Online deployment with Office 365 (Surface Hub)</span></span>


<span data-ttu-id="f4b1c-105">本主题提供有关在具有纯联机部署时为 Microsoft Surface Hub 添加设备帐户的说明。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-105">This topic has instructions for adding a device account for your Microsoft Surface Hub when you have a pure, online deployment.</span></span>

<span data-ttu-id="f4b1c-106">如果具有纯联机 (O365) 部署，可[使用提供的 PowerShell 脚本](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts)创建设备帐户。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-106">If you have a pure, online (O365) deployment, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) to create device accounts.</span></span> 

1. <span data-ttu-id="f4b1c-107">在电脑上启动远程 PowerShell 会话，并连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-107">Start a remote PowerShell session on a PC and connect to Exchange.</span></span>

   <span data-ttu-id="f4b1c-108">请确保已设置正确的权限来运行关联的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-108">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="f4b1c-109">建立会话后，你将创建一个新邮箱并启用它作为 RoomMailboxAccount，或更改现有会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-109">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="f4b1c-110">这将允许在 Surface Hub 中对帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-110">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="f4b1c-111">如果要更改现有资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="f4b1c-111">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="f4b1c-112">如果要创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="f4b1c-112">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="f4b1c-113">设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-113">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="f4b1c-114">Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 False）兼容。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-114">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="f4b1c-115">如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-115">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="f4b1c-116">如果尚未创建兼容的策略，请使用以下 cmdlet，该 cmdlet 将创建名为“Surface Hubs”的策略。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-116">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="f4b1c-117">完成创建后，你可以对其他设备帐户应用相同的策略。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-117">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   <span data-ttu-id="f4b1c-118">具有兼容的策略后，你需要将该策略应用于设备帐户。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-118">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span>

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. <span data-ttu-id="f4b1c-119">必须在设备帐户上设置各种 Exchange 属性才能改进会议体验。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-119">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="f4b1c-120">你可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md) 部分中查看需要设置哪些属性。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-120">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="f4b1c-121">连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-121">Connect to Azure AD.</span></span>
    
   <span data-ttu-id="f4b1c-122">首先需要安装 PowerShell 版本 2 的 Azure AD 模块。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-122">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="f4b1c-123">在提升的命令提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="f4b1c-123">In an elevated powershell prompt run the following command :</span></span>
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   <span data-ttu-id="f4b1c-124">需要连接到 Azure AD 才能应用某些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-124">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="f4b1c-125">你可以运行此 cmdlet 来进行连接。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-125">You can run this cmdlet to connect.</span></span>

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. <span data-ttu-id="f4b1c-126">如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="f4b1c-127">有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. <span data-ttu-id="f4b1c-128">Surface Hub 需要许可证以使用 Skype for Business 功能。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-128">Surface Hub requires a license for Skype for Business functionality.</span></span> <span data-ttu-id="f4b1c-129">为了启用 Skype for Business，你的环境将需要满足 [Skype for Business Online 的必备条件](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-129">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span></span>
   
   <span data-ttu-id="f4b1c-130">接下来，可使用 `Get-AzureADSubscribedSku` 检索可供 O365 租户使用的 SKU 列表。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-130">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

   <span data-ttu-id="f4b1c-131">列出 SKU 后，需要将所需的 SkuId 分配给 `$License.SkuId` 变量。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-131">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

8. <span data-ttu-id="f4b1c-132">使用 Skype for Business 启用设备帐户。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-132">Enable the device account with Skype for Business.</span></span>
   <span data-ttu-id="f4b1c-133">如果未安装 Skype for Business PowerShell 模块，请[下载 Skype for Business Online Windows PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-133">If the Skype for Business PowerShell module is not installed, [download the Skype for Business Online Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 

   - <span data-ttu-id="f4b1c-134">首先在电脑上创建一个远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-134">Start by creating a remote PowerShell session from a PC.</span></span>

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - <span data-ttu-id="f4b1c-135">接着，如果你不确定将哪个值用于环境中的 `RegistrarPool` 参数，则可以使用此 cmdlet（例如，<em>alice@contoso.com</em>），从现有的 Skype for Business 用户中获取值：</span><span class="sxs-lookup"><span data-stu-id="f4b1c-135">Next, if you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet (for example, <em>alice@contoso.com</em>):</span></span>

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       <span data-ttu-id="f4b1c-136">或通过设置变量获取值</span><span class="sxs-lookup"><span data-stu-id="f4b1c-136">OR by setting a variable</span></span>
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - <span data-ttu-id="f4b1c-137">使用以下 cmdlet 启用 Surface Hub 帐户：</span><span class="sxs-lookup"><span data-stu-id="f4b1c-137">Enable the Surface Hub account with the following cmdlet:</span></span>
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       <span data-ttu-id="f4b1c-138">或使用上文中的 $strRegistarPool 变量</span><span class="sxs-lookup"><span data-stu-id="f4b1c-138">OR using the $strRegistarPool variable from above</span></span>
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

<span data-ttu-id="f4b1c-139">为了进行验证，你应该能使用任一 Skype for Business 客户端（电脑、Android 等）登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="f4b1c-139">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>






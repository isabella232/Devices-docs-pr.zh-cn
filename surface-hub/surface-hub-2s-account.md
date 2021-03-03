---
title: 创建 Surface Hub 2S 设备帐户
description: 此页面介绍创建 Surface Hub 2S 设备帐户的过程。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/18/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 3afd4115ff4bd22a84f9a5fb86ceb6805c347f8a
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385220"
---
# <a name="create-surface-hub-2s-device-account"></a><span data-ttu-id="797f3-104">创建 Surface Hub 2S 设备帐户</span><span class="sxs-lookup"><span data-stu-id="797f3-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="797f3-105">创建 Surface Hub 设备帐户 (也称为会议室邮箱) 允许 Surface Hub 2S 接收、批准或拒绝会议请求和加入会议。</span><span class="sxs-lookup"><span data-stu-id="797f3-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings.</span></span> <span data-ttu-id="797f3-106">在开箱即用体验期间配置设备帐户 (OOBE) 设置。</span><span class="sxs-lookup"><span data-stu-id="797f3-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="797f3-107">如果需要，可以在以后更改 (OOBE 安装程序) 。</span><span class="sxs-lookup"><span data-stu-id="797f3-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="797f3-108">你可以结合使用 Microsoft 365 管理中心创建帐户Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="797f3-108">You can create the account from  Microsoft 365 Admin center in combination with Windows PowerShell:</span></span> 

- <span data-ttu-id="797f3-109">**通过管理中心创建帐户**。</span><span class="sxs-lookup"><span data-stu-id="797f3-109">**Create account via Admin center**.</span></span> <span data-ttu-id="797f3-110">若要满足最低要求，你可以直接从 [Microsoft 365](https://admin.microsoft.com/AdminPortal)管理中心配置帐户所需的一切。</span><span class="sxs-lookup"><span data-stu-id="797f3-110">To meet minimum requirements, you can configure everything you need for the account directly from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal).</span></span> <span data-ttu-id="797f3-111">某些功能（如直接从白板应用共享白板）需要使用 PowerShell 配置 ActiveSync;如果 [此页上需要使用电子邮件应用](#enable-activesync-if-use-of-email-app-is-required) ，请参阅"启用 ActiveSync"。</span><span class="sxs-lookup"><span data-stu-id="797f3-111">Some features like sharing whiteboards directly from the whiteboard app require using PowerShell to configure ActiveSync; see [Enable ActiveSync if use of email app is required](#enable-activesync-if-use-of-email-app-is-required) on this page.</span></span>

- <span data-ttu-id="797f3-112">**通过 PowerShell 创建帐户**。</span><span class="sxs-lookup"><span data-stu-id="797f3-112">**Create account via PowerShell**.</span></span> <span data-ttu-id="797f3-113">可以使用 PowerShell 脚本促进创建多个设备帐户并快速配置特定功能，包括：</span><span class="sxs-lookup"><span data-stu-id="797f3-113">You can use PowerShell scripts to facilitate creation of multiple device accounts and quickly configure specific features including:</span></span>
    - <span data-ttu-id="797f3-114">每个 Surface Hub 设备帐户的日历处理。</span><span class="sxs-lookup"><span data-stu-id="797f3-114">Calendar processing for every Surface Hub device account.</span></span>
    - <span data-ttu-id="797f3-115">对计划请求的自定义自动答复。</span><span class="sxs-lookup"><span data-stu-id="797f3-115">Custom auto replies to scheduling requests.</span></span>
    - <span data-ttu-id="797f3-116">如果默认 ActiveSync 邮箱策略已由其他人或其他进程修改，您可能必须创建和分配新的 ActiveSync 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="797f3-116">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!TIP]
> <span data-ttu-id="797f3-117">可以通过运行下面的帐户验证脚本 [来检查帐户](#account-verification-script) 设置。</span><span class="sxs-lookup"><span data-stu-id="797f3-117">You can check account setup by running the [Account verification script](#account-verification-script) below.</span></span>

> [!NOTE]  
> <span data-ttu-id="797f3-118">Surface Hub 设备帐户不支持第三方联合身份提供程序 (FIPs) 并且必须是标准 Active Directory 或 Azure Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="797f3-118">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <a name="create-account-via-admin-center"></a><span data-ttu-id="797f3-119">通过管理中心创建帐户</span><span class="sxs-lookup"><span data-stu-id="797f3-119">Create account via admin center</span></span>

1. <span data-ttu-id="797f3-120">在 Microsoft 365 管理中心中\*\*\*\*，转到"资源"并选择"会议室&**设备**"，然后选择" + 添加**资源"。**</span><span class="sxs-lookup"><span data-stu-id="797f3-120">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Add resource**.</span></span>

2. <span data-ttu-id="797f3-121">提供设备帐户的名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="797f3-121">Provide a name and email address for the device account.</span></span> <span data-ttu-id="797f3-122">将其余设置保持默认状态不变。</span><span class="sxs-lookup"><span data-stu-id="797f3-122">Leave remaining settings unchanged in the default state.</span></span>

   ![提供名称和电子邮件地址](images/sh2-account2.png)

   ![将其余设置保持默认状态不变](images/sh2-account3.png)

3. <span data-ttu-id="797f3-125">设置设备帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="797f3-125">Set the password for the device account.</span></span> <span data-ttu-id="797f3-126">若要设置密码，请选择 **"用户"，** 然后选择 **"活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="797f3-126">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="797f3-127">现在搜索新创建的用户以设置密码。</span><span class="sxs-lookup"><span data-stu-id="797f3-127">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="797f3-128">确保您未 **选择"** 使 **此用户在首次登录时更改其密码"选项。**</span><span class="sxs-lookup"><span data-stu-id="797f3-128">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![设置设备帐户的密码](images/sh2-account4.png)

4. <span data-ttu-id="797f3-130">使用 Office 365 许可证分配会议室。</span><span class="sxs-lookup"><span data-stu-id="797f3-130">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="797f3-131">建议分配 Office 365 会议室许可证\*\*\*\*，该许可证将自动启用 Microsoft Teams 和 Skype for Business 的帐户。</span><span class="sxs-lookup"><span data-stu-id="797f3-131">It’s recommended to assign the Office 365 **Meeting Room** license, which automatically enables the account for Microsoft Teams and Skype for Business.</span></span>

   ![分配 Office 365 许可证](images/sh2-account5.png)


> [!NOTE]  
> <span data-ttu-id="797f3-133">如果使用 Skype for Business，则需要通过 PowerShell 完成设置 - Skype for Business 日历：为此 [帐户设置](#set-calendar-auto-processing-skype-for-business-only) 日历自动处理。</span><span class="sxs-lookup"><span data-stu-id="797f3-133">If using Skype for Business, you will need to finalize setup via PowerShell -- Skype for Business Calendar: Set [Calendar Autoprocessing](#set-calendar-auto-processing-skype-for-business-only) for this account.</span></span> 

## <a name="create-account-via-powershell"></a><span data-ttu-id="797f3-134">通过 PowerShell 创建帐户</span><span class="sxs-lookup"><span data-stu-id="797f3-134">Create account via PowerShell</span></span>

 <span data-ttu-id="797f3-135">使用 PowerShell 在 Surface Hub 上快速自动执行任务不一定需要 PowerShell 专业知识。</span><span class="sxs-lookup"><span data-stu-id="797f3-135">Using PowerShell to rapidly automate tasks on Surface Hub does not necessarily require PowerShell expertise.</span></span> <span data-ttu-id="797f3-136">在使用此页面上的适当脚本之前，请确保已完成安装先决条件。</span><span class="sxs-lookup"><span data-stu-id="797f3-136">Ensure you have completed the setup prerequisites before using the appropriate scripts on this page.</span></span>

### <a name="prerequisites-for-using-powershell-to-manage-surface-hub"></a><span data-ttu-id="797f3-137">使用 PowerShell 管理 Surface Hub 的先决条件</span><span class="sxs-lookup"><span data-stu-id="797f3-137">Prerequisites for using PowerShell to manage Surface Hub</span></span> 

1. <span data-ttu-id="797f3-138">使用提升的帐户权限启动 PowerShell (**以** 管理员) ，并确保系统配置为运行 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="797f3-138">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="797f3-139">若要了解详情，请参阅"[关于执行策略"。](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)</span><span class="sxs-lookup"><span data-stu-id="797f3-139">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="797f3-140">[安装 Azure PowerShell 模块](https://docs.microsoft.com/powershell/azure/install-az-ps)。</span><span class="sxs-lookup"><span data-stu-id="797f3-140">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>


### <a name="connect-to-exchange-online-powershell"></a><span data-ttu-id="797f3-141">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="797f3-141">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <a name="create-mailbox"></a><span data-ttu-id="797f3-142">创建邮箱</span><span class="sxs-lookup"><span data-stu-id="797f3-142">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <a name="set-calendar-auto-processing-skype-for-business-only"></a><span data-ttu-id="797f3-143">仅设置 Skype for Business (日历自动处理) </span><span class="sxs-lookup"><span data-stu-id="797f3-143">Set Calendar auto-processing (Skype for Business only)</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <a name="enable-activesync-if-use-of-email-app-is-required"></a><span data-ttu-id="797f3-144">如果需要使用电子邮件应用，则启用 ActiveSync</span><span class="sxs-lookup"><span data-stu-id="797f3-144">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="797f3-145">如果未更改，则默认 ActiveSync 策略将有效。</span><span class="sxs-lookup"><span data-stu-id="797f3-145">The default ActiveSync Policy will work if unchanged.</span></span> <span data-ttu-id="797f3-146">否则，创建新的策略并分配。</span><span class="sxs-lookup"><span data-stu-id="797f3-146">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <a name="connect-to-azure-ad"></a><span data-ttu-id="797f3-147">连接到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="797f3-147">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <a name="assign-a-license"></a><span data-ttu-id="797f3-148">分配许可证</span><span class="sxs-lookup"><span data-stu-id="797f3-148">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <a name="check-for-available-licenses"></a><span data-ttu-id="797f3-149">检查可用的许可证</span><span class="sxs-lookup"><span data-stu-id="797f3-149">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <a name="account-verification-script"></a><span data-ttu-id="797f3-150">帐户验证脚本</span><span class="sxs-lookup"><span data-stu-id="797f3-150">Account verification script</span></span>

<span data-ttu-id="797f3-151">创建设备帐户后，可以运行以下验证脚本。</span><span class="sxs-lookup"><span data-stu-id="797f3-151">After creating the device account, you can run the following verification script.</span></span> <span data-ttu-id="797f3-152">此脚本验证以前创建的设备帐户并生成摘要报告。</span><span class="sxs-lookup"><span data-stu-id="797f3-152">This script validates a previously-created device account and produces a summary report.</span></span> <span data-ttu-id="797f3-153">例如：</span><span class="sxs-lookup"><span data-stu-id="797f3-153">For example:</span></span>

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

<span data-ttu-id="797f3-154">不会显示特定设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="797f3-154">Details of specific settings will not be shown.</span></span>

```PowerShell
# SHAccountValidate.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"


# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessEx)
    {
        Remove-PSSession $sessEx
    }
    if ($sessSfb)
    {
        Remove-PSSession $sessSfb
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor "red"
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor "green"
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

$strUpn = Read-Host "What is the email address of the account you wish to validate?"
if (!$strUpn.Contains('@'))
{
    CleanupAndFail "$strUpn is not a valid email address"
}
$strExServer = Read-Host "What is your exchange server? (leave blank for online tenants)"
if ($strExServer.Equals(""))
{
    $fExIsOnline = $true
}
else
{
    $fExIsOnline = $false
}
$credEx = Get-Credential -Message "Please provide exchange user credentials"

$strRegistrarPool = Read-Host ("What is the Skype for Business registrar pool for $strUpn" + "? (leave blank for online tenants)")
$fSfbIsOnline = $strRegistrarPool.Equals("")

$fHasOnPrem = $true
if ($fSfbIsOnline -and $fExIsOnline)
{
    do
    {
        $strHasOnPrem = (Read-Host "Do you have an on-premises Active Directory (Y/N) (No if your domain services are hosted entirely online)").ToUpper()
    } while ($strHasOnPrem -ne "Y" -and $strHasOnPrem -ne "N")
    $fHasOnPrem = $strHasOnPrem.Equals("Y")
}

$fHasOnline = $false
if ($fSfbIsOnline -or $fExIsOnline)
{
    $fHasOnline = $true
}

if ($fSfbIsOnline)
{
    try {
        Import-Module SkypeOnlineConnector
    }
    catch
    {
        CleanupAndFail "To verify Skype for Business in online tenants you need the Lync Online Connector module from https://www.microsoft.com/download/details.aspx?id=39366"
    }
}
else
{
    $credSfb = (Get-Credential -Message "Please enter Skype for Business admin credentials")
}

if ($fHasOnline)
{
    $credSfb = $credEx
    try {
        Import-Module MSOnline
    }
    catch
    {
        CleanupAndFail "To verify accounts in online tenants you need the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
    }
}

PrintAction "Connecting to Exchange Powershell Session..."
[System.Management.Automation.Runspaces.AuthenticationMechanism] $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Kerberos
if ($fExIsOnline)
{
    $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Basic
}
try
{
    $sessEx = $null
    if ($fExIsOnline)
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -WarningAction SilentlyContinue
    }
    else
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri https://$strExServer/powershell -WarningAction SilentlyContinue
    }
}
catch
{
}

if (!$sessEx)
{
    CleanupAndFail "Connecting to Exchange Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Exchange Powershell Session"

PrintAction "Connecting to Skype for Business Powershell Session..."

if ($fSfbIsOnline)
{
    $sessSfb = New-CsOnlineSession -Credential $credSfb
}
else
{
    $sessSfb = New-PSSession -Credential $credSfb -ConnectionURI "https://$strRegistrarPool/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
}

if (!$sessSfb)
{
    CleanupAndFail "Connecting to Skype for Business Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Skype for Business Powershell"

if ($fHasOnline)
{
    $credMsol = $null
    if ($fExIsOnline)
    {
        $credMsol = $credEx
    }
    elseif ($fSfbIsOnline)
    {
        $credMsol = $credSfb
    }
    else
    {
        CleanupAndFail "Internal error - could not determine MS Online credentials"
    }
    try
    {
        PrintAction "Connecting to Azure Active Directory Services..."
        Connect-MsolService -Credential $credMsol
        PrintSuccess "Connected to Azure Active Directory Services"
    }
    catch
    {
        # This really shouldn't happen unless there is a network error
        CleanupAndFail "Failed to connect to MSOnline"
    }
}


PrintAction "Importing remote sessions into the local session..."
try
{
    $importEx = Import-PSSession $sessEx -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
    $importSfb = Import-PSSession $sessSfb -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
}
catch
{
}
if (!$importEx -or !$importSfb)
{
    CleanupAndFail "Import failed"
}
PrintSuccess "Import successful"


$mailbox = $null
try
{
    $mailbox = Get-Mailbox -Identity $strUpn
}
catch
{
}

if (!$mailbox)
{
    CleanupAndFail "Account exists check failed. Unable to find the mailbox for $strUpn - please make sure the Exchange account exists on $strExServer"
}

$exchange = $null
if (!$fExIsOnline)
{
    $exchange = Get-ExchangeServer
    if (!$exchange -or !$exchange.IsE14OrLater)
    {
        CleanupAndFail "A compatible exchange server version was not found. Please use at least exchange 2010."
    }
}


$strAlias = $mailbox.UserPrincipalName
$strDisplayName = $mailbox.DisplayName

$strLinkedAccount = $strLinkedDomain = $strLinkedUser = $strLinkedServer = $null
$credLinkedDomain = $Null
if (!$fExIsOnline -and ![System.String]::IsNullOrEmpty($mailbox.LinkedMasterAccount) -and !$mailbox.LinkedMasterAccount.EndsWith("\SELF"))
{
    $strLinkedAccount = $mailbox.LinkedMasterAccount
    $strLinkedDomain = $strLinkedAccount.substring(0,$strLinkedAccount.IndexOf('\'))
    $strLinkedUser = $strLinkedAccount.substring($strLinkedAccount.IndexOf('\') + 1)
    $strLinkedServer = Read-Host "What is the domain controller for the $strLinkedDomain"
    $credLinkedDomain = (Get-Credential -Message "Please provide credentials for $strLinkedDomain")
}







Write-Host
Write-Host
Write-Host
PrintAction "Performing verification checks on $strDisplayName..."
$Global:iTotalFailures = 0
$global:iTotalWarnings = 0
$Global:iTotalPasses = 0

function Validate()
{
    Param(
        [string]$Test,
        [bool]  $Condition,
        [string]$FailureMsg,
        [switch]$WarningOnly
    )

    Write-Host -NoNewline -ForegroundColor White $Test.PadRight(100,'.')
    if ($Condition)
    {
        Write-Host -ForegroundColor Green "Passed"
        $global:iTotalPasses++
    }
    else
    {
        if ($WarningOnly)
        {
            Write-Host -ForegroundColor Yellow ("Warning: "+$FailureMsg)
            $global:iTotalWarnings++
        }
        else
        {
            Write-Host -ForegroundColor Red ("Failed: "+$FailureMsg)
            $global:iTotalFailures++
        }
    }
}
```

## <a name="learn-more"></a><span data-ttu-id="797f3-155">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="797f3-155">Learn more</span></span>

- [<span data-ttu-id="797f3-156">使用 PowerShell 创建 Surface Hub 2S 的本地帐户</span><span class="sxs-lookup"><span data-stu-id="797f3-156">Create Surface Hub 2S on-premises accounts with PowerShell</span></span>](surface-hub-2s-onprem-powershell.md)
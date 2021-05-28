---
title: Microsoft Surface Hub 疑难解答
description: 常见问题疑难解答，包括设置问题和 Exchange ActiveSync 错误。
ms.assetid: CF58F74D-8077-48C3-981E-FCFDCA34B34A
ms.reviewer: ''
manager: laurawi
keywords: 常见问题疑难解答, 设置问题, Exchange ActiveSync 错误
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2018
ms.localizationpriority: medium
ms.openlocfilehash: fe87c56474a05152f991a5b63f6abf0cf05e8b03
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830835"
---
# <span data-ttu-id="94cdb-104">Microsoft Surface Hub 疑难解答</span><span class="sxs-lookup"><span data-stu-id="94cdb-104">Troubleshoot Microsoft Surface Hub</span></span>


<span data-ttu-id="94cdb-105">常见问题疑难解答，包括设置问题和 Exchange ActiveSync 错误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-105">Troubleshoot common problems, including setup issues, Exchange ActiveSync errors.</span></span>

<span data-ttu-id="94cdb-106">[Surface Hub 硬件诊断工具](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab)包含交互式测试，可确认你的中心的基本功能是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="94cdb-106">The [Surface Hub Hardware Diagnostic tool](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) contains interactive tests which allow you to confirm essential functionality of your Hub is working as expected.</span></span> <span data-ttu-id="94cdb-107">除了测试硬件，诊断还可测试资源帐户，验证其是否已针对你的环境适当配置。</span><span class="sxs-lookup"><span data-stu-id="94cdb-107">In addition to testing hardware, the diagnostic can test the resource account to verify that it is configured properly for your environment.</span></span> <span data-ttu-id="94cdb-108">如果遇到问题，可保存结果并与 Surface Hub 支持团队共享。</span><span class="sxs-lookup"><span data-stu-id="94cdb-108">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="94cdb-109">若要了解使用情况，请参阅[使用 Surface Hub 硬件诊断工具测试设备帐户](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun)。</span><span class="sxs-lookup"><span data-stu-id="94cdb-109">For usage information, see [Using the Surface Hub Hardware Diagnostic Tool to test a device account](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).</span></span>

<span data-ttu-id="94cdb-110">下表中列出了常见问题和原因以及可能的修补程序。</span><span class="sxs-lookup"><span data-stu-id="94cdb-110">Common issues are listed in the following table, along with causes and possible fixes.</span></span> <span data-ttu-id="94cdb-111">[设置疑难解答](#setup-troubleshooting)部分包含设备上的问题列表，以及在首次运行体验期间可能遇到的多种问题类型。</span><span class="sxs-lookup"><span data-stu-id="94cdb-111">The [Setup troubleshooting](#setup-troubleshooting) section contains a listing of on-device problems, along with several types of issues that may be encountered during the first-run experience.</span></span> <span data-ttu-id="94cdb-112">[Exchange ActiveSync 错误](#exchange-activesync-errors)部分列出了设备在尝试与 Microsoft Exchange ActiveSync 服务器同步时可能遇到的常见错误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-112">The [Exchange ActiveSync errors](#exchange-activesync-errors) section lists common errors the device may encounter when trying to synchronize with an Microsoft Exchange ActiveSync server.</span></span>




## <a name="setup-troubleshooting"></a><span data-ttu-id="94cdb-113">设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="94cdb-113">Setup troubleshooting</span></span>


<span data-ttu-id="94cdb-114">本部分列出了原因和可能的修补程序，以帮助解决在设置 Microsoft Surface Hub 时可能发现的问题。</span><span class="sxs-lookup"><span data-stu-id="94cdb-114">This section lists causes, and possible fixes to help troubleshoot issues you might find when you set up your Microsoft Surface Hub.</span></span>

### <a name="on-device"></a><span data-ttu-id="94cdb-115">设备上</span><span class="sxs-lookup"><span data-stu-id="94cdb-115">On-device</span></span>

<span data-ttu-id="94cdb-116">完成首次运行计划后 Surface Hub 上的问题的可能修补程序。</span><span class="sxs-lookup"><span data-stu-id="94cdb-116">Possible fixes for issues on the Surface Hub after you've completed the first-run program.</span></span>

<table>
<tr>
<th><span data-ttu-id="94cdb-117">问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-117">Issue</span></span></th>
<th><span data-ttu-id="94cdb-118">原因</span><span class="sxs-lookup"><span data-stu-id="94cdb-118">Causes</span></span></th>
<th><span data-ttu-id="94cdb-119">可能的修补程序</span><span class="sxs-lookup"><span data-stu-id="94cdb-119">Possible fixes</span></span></th>
</tr>
<tr>
<td rowspan="2">
<p><span data-ttu-id="94cdb-120">未收到自动接受/拒绝消息。</span><span class="sxs-lookup"><span data-stu-id="94cdb-120">Not receiving automatic accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-121">设备帐户未配置为自动接受/拒绝消息。</span><span class="sxs-lookup"><span data-stu-id="94cdb-121">The device account isn't configured to automatically accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-122">使用 PowerShell cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>。</span><span class="sxs-lookup"><span data-stu-id="94cdb-122">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-123">设备帐户未配置为处理外部会议请求。</span><span class="sxs-lookup"><span data-stu-id="94cdb-123">The device account isn't configured to process external meeting requests.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-124">使用 PowerShell cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>。</span><span class="sxs-lookup"><span data-stu-id="94cdb-124">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-125">日历未显示在欢迎屏幕上，或显示消息“约会过期(没有设置帐户)”。</span><span class="sxs-lookup"><span data-stu-id="94cdb-125">Calendar is not showing on the Welcome screen, or message "Appointments of date (no account provisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-126">此 Surface Hub 上未设置任何设备帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-126">No device account is set up on this Surface Hub.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-127">通过“设置”预配设备帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-127">Provision a device account through Settings.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-128">日历未显示在欢迎屏幕上，或显示消息“约会过期(预配过度)”。</span><span class="sxs-lookup"><span data-stu-id="94cdb-128">Calendar is not showing on the Welcome screen or message "Appointments of date (overprovisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-129">设备帐户在过多的设备上预配。</span><span class="sxs-lookup"><span data-stu-id="94cdb-129">The device account is provisioned on too many devices.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-130">将设备帐户从已预配到的其他设备中删除。</span><span class="sxs-lookup"><span data-stu-id="94cdb-130">Remove the device account from other devices that it's provisioned to.</span></span> <span data-ttu-id="94cdb-131">这可以通过使用 Exchange 管理端口来实现。</span><span class="sxs-lookup"><span data-stu-id="94cdb-131">This can be done using the Exchange admin portal.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-132">日历未显示在欢迎屏幕上，或显示消息“约会过期(凭据无效)”。</span><span class="sxs-lookup"><span data-stu-id="94cdb-132">Calendar is not showing on the Welcome screen or message "Appointments of date (invalid credentials)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-133">设备帐户的密码已过期，将不再有效。</span><span class="sxs-lookup"><span data-stu-id="94cdb-133">The device account's password has expired and is no longer valid.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-134">在“设置”中更新帐户密码。</span><span class="sxs-lookup"><span data-stu-id="94cdb-134">Update the account's password in Settings.</span></span> <span data-ttu-id="94cdb-135">另请参阅<a href="password-management-for-surface-hub-device-accounts.md">密码管理</a>。</span><span class="sxs-lookup"><span data-stu-id="94cdb-135">Also see <a href="password-management-for-surface-hub-device-accounts.md">Password management</a>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-136">日历未显示在欢迎屏幕上，或显示消息“约会过期(帐户策略)”。</span><span class="sxs-lookup"><span data-stu-id="94cdb-136">Calendar is not showing on the Welcome screen or message "Appointments of date (account policy)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-137">设备帐户使用的 ActiveSync 策略无效。</span><span class="sxs-lookup"><span data-stu-id="94cdb-137">The device account is using an invalid ActiveSync policy.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-138">请确保设备帐户具有 ActiveSync 策略，其中 <code>PasswordEnabled == False</code>。</span><span class="sxs-lookup"><span data-stu-id="94cdb-138">Make sure the device account has an ActiveSync policy where <code>PasswordEnabled == False</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-139">日历未显示在欢迎屏幕上，或显示消息“约会可能已过期”。</span><span class="sxs-lookup"><span data-stu-id="94cdb-139">Calendar is not showing on the Welcome screen or message "Appointments may be out of date" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-140">未启用 Exchange。</span><span class="sxs-lookup"><span data-stu-id="94cdb-140">Exchange is not enabled.</span></span></p>
</td>
<td><span data-ttu-id="94cdb-141">通过“设置”为 Exchange 服务启用设备帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-141">Enable the device account for Exchange services through Settings.</span></span> <span data-ttu-id="94cdb-142">需确保你不仅拥有正确的 ActiveSync 策略集，而且还已安装 Exchange 服务正常运行所需的所有证书。</span><span class="sxs-lookup"><span data-stu-id="94cdb-142">You need to make sure you have the right set of ActiveSync policies and have also installed any necessary certificates for Exchange services to work.</span></span></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-143">无法登录 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="94cdb-143">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-144">设备帐户不具有会话初始协议 (SIP) 地址属性。</span><span class="sxs-lookup"><span data-stu-id="94cdb-144">The device account does not have a Session Initiation Protocol (SIP) address property.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-145">帐户不具有 SIP 地址属性，并且其用户主体名称 (UPN) 与实际的 SIP 地址不匹配。</span><span class="sxs-lookup"><span data-stu-id="94cdb-145">The account does not have a SIP address property and its User Principal Name (UPN) does not match the actual SIP address.</span></span> <span data-ttu-id="94cdb-146">帐户必须设置其 SIP 地址，或者应使用“设置”应用来添加 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="94cdb-146">The account must have its SIP address set, or the SIP address should be added using the Settings app.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-147">无法登录 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="94cdb-147">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-148">设备帐户需要证书才能在 Skype for Business 中进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="94cdb-148">The device account requires a certificate to authenticate into Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-149">使用设置包安装适当的证书。</span><span class="sxs-lookup"><span data-stu-id="94cdb-149">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
</table>
 

### <a name="first-run"></a><span data-ttu-id="94cdb-150">首次运行</span><span class="sxs-lookup"><span data-stu-id="94cdb-150">First run</span></span>

<span data-ttu-id="94cdb-151">Surface Hub 首次运行计划的问题的可能修补程序。</span><span class="sxs-lookup"><span data-stu-id="94cdb-151">Possible fixes for issues with Surface Hub first-run program.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94cdb-152">问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-152">Issue</span></span></th>
<th align="left"><span data-ttu-id="94cdb-153">原因</span><span class="sxs-lookup"><span data-stu-id="94cdb-153">Causes</span></span></th>
<th align="left"><span data-ttu-id="94cdb-154">可能的修补程序</span><span class="sxs-lookup"><span data-stu-id="94cdb-154">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-155">当系统请求域和用户名时找不到帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-155">Cannot find account when asked for domain and user name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-156">域需采用完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="94cdb-156">Domain needs to be the fully qualified domain name (FQDN).</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-157">应在域字段中提供 FQDN。</span><span class="sxs-lookup"><span data-stu-id="94cdb-157">The FQDN should be provided in the domain field.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a><span data-ttu-id="94cdb-158">设备帐户页面，有关新帐户设置的问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-158">Device account page, issues for new account settings</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94cdb-159">问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-159">Issue</span></span></th>
<th align="left"><span data-ttu-id="94cdb-160">原因</span><span class="sxs-lookup"><span data-stu-id="94cdb-160">Causes</span></span></th>
<th align="left"><span data-ttu-id="94cdb-161">可能的修补程序</span><span class="sxs-lookup"><span data-stu-id="94cdb-161">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-162">在 Azure AD 中找不到提供的帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-162">Unable to find the provided account in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-163">所提供帐户的用户主体名称 (UPN) 具有一个在 Azure AD 中无法访问的租户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-163">The provided account's User Principal Name (UPN) has a tenant that can't be reached in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-164">确保具有正常的 Internet 连接，并且设备可以访问 Microsoft Online Services。</span><span class="sxs-lookup"><span data-stu-id="94cdb-164">Make sure that you have a working Internet connection, and that the device can reach Microsoft Online Services.</span></span> <span data-ttu-id="94cdb-165">确保输入的帐户凭据正确。</span><span class="sxs-lookup"><span data-stu-id="94cdb-165">Make sure the account credentials are entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-166">无法访问指定的目录。</span><span class="sxs-lookup"><span data-stu-id="94cdb-166">Unable to reach the specified directory.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-167">无法访问提供的帐户域所指定的域。</span><span class="sxs-lookup"><span data-stu-id="94cdb-167">The provided account domain specifies a domain that can't be reached.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-168">确保具有正常的网络连接，并且设备可以访问域控制器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-168">Make sure that you have a working network connection, and that the device can reach the domain controller.</span></span> <span data-ttu-id="94cdb-169">确保输入的帐户凭据正确。</span><span class="sxs-lookup"><span data-stu-id="94cdb-169">Make sure the account credentials are entered correctly.</span></span> <span data-ttu-id="94cdb-170">也可以尝试改用 FQDN。</span><span class="sxs-lookup"><span data-stu-id="94cdb-170">You can also try using the FQDN instead.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-171">无法自动发现 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="94cdb-171">Can't auto-discover Exchange server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-172">Exchange Server 未配置为自动发现。</span><span class="sxs-lookup"><span data-stu-id="94cdb-172">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-173">为设备帐户启用 Exchange Server 的自动发现，或手动输入帐户的 Exchange Server 地址。</span><span class="sxs-lookup"><span data-stu-id="94cdb-173">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-174">在输入帐户凭据后，未发现 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="94cdb-174">Could not discover the SIP address after entering the account credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-175">Active Directory 或 Azure AD 中没有 SIP 地址项。</span><span class="sxs-lookup"><span data-stu-id="94cdb-175">There was no SIP address entry in Active Directory or Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-176">确保帐户已通过 Skype for Business 启用并且具有一个 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="94cdb-176">Make sure the account is enabled with Skype for Business and has a SIP address.</span></span> <span data-ttu-id="94cdb-177">如果没有，你可以在文本框中手动输入 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="94cdb-177">If not, you can enter the SIP address manually into the text box.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a name="device-account-page,-issues-for-existing-account-settings"></a><span data-ttu-id="94cdb-178">设备帐户页面，有关现有帐户设置的问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-178">Device account page, issues for existing account settings</span></span>

<table>
<tr>
<th><span data-ttu-id="94cdb-179">问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-179">Issue</span></span></th>
<th><span data-ttu-id="94cdb-180">原因</span><span class="sxs-lookup"><span data-stu-id="94cdb-180">Causes</span></span></th>
<th><span data-ttu-id="94cdb-181">错误代码</span><span class="sxs-lookup"><span data-stu-id="94cdb-181">Error codes</span></span></th>
<th><span data-ttu-id="94cdb-182">可能的修补程序</span><span class="sxs-lookup"><span data-stu-id="94cdb-182">Possible fixes</span></span></th>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-183">帐户无法使用指定的凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="94cdb-183">Account could not authenticate with the specified credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-184">帐户未以 Active Directory (AD) 中的用户身份进行启用，需要密码来进行身份验证，或者密码不正确。</span><span class="sxs-lookup"><span data-stu-id="94cdb-184">The account is not enabled as a user in Active Directory (AD), needs a password to authenticate, or the password is incorrect.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-185">无</span><span class="sxs-lookup"><span data-stu-id="94cdb-185">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-186">确保输入的凭据正确。</span><span class="sxs-lookup"><span data-stu-id="94cdb-186">Make sure the credentials are entered correctly.</span></span> <span data-ttu-id="94cdb-187">以 AD 中的用户身份启用帐户和添加密码，或设置 RoomMailboxPassword</span><span class="sxs-lookup"><span data-stu-id="94cdb-187">Enable the account as a user in AD and add a password, or set the RoomMailboxPassword</span></span></p><span data-ttu-id="94cdb-188">.</span><span class="sxs-lookup"><span data-stu-id="94cdb-188">.</span></span> </td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-189">在提供 Exchange Server 时，显示错误 0x800C0019。</span><span class="sxs-lookup"><span data-stu-id="94cdb-189">Error 0x800C0019 is displayed when providing an Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-190">设备帐户需要证书才能进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="94cdb-190">The device account requires a certificate to authenticate.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-191">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="94cdb-191">0x800C0019</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-192">使用设置包安装适当的证书。</span><span class="sxs-lookup"><span data-stu-id="94cdb-192">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-193">设备帐户凭据对提供的 Exchange Server 无效。</span><span class="sxs-lookup"><span data-stu-id="94cdb-193">Device account credentials are not valid for the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-194">提供的 Exchange Server 不在设备帐户邮箱的托管位置。</span><span class="sxs-lookup"><span data-stu-id="94cdb-194">The provided Exchange server is not where the device account's mailbox is hosted.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-195">无</span><span class="sxs-lookup"><span data-stu-id="94cdb-195">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-196">确保为设备帐户提供了正确的 Exchange 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-196">Make sure you are providing the correct Exchange mail server for the device account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-197">在尝试访问 Exchange Server 时 HTTP 超时。</span><span class="sxs-lookup"><span data-stu-id="94cdb-197">HTTP timeout while trying to reach Exchange server.</span></span></p>
</td>
<td></td>
<td>
<p><span data-ttu-id="94cdb-198">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="94cdb-198">0x80072EE2</span></span></p>
</td>
<td></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-199">找不到提供的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="94cdb-199">Couldn't find the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-200">找不到提供的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="94cdb-200">The Exchange server provided could not be found.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-201">无</span><span class="sxs-lookup"><span data-stu-id="94cdb-201">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-202">确保具有正常的网络或 Internet 连接，并且所提供的 Exchange Server 正确。</span><span class="sxs-lookup"><span data-stu-id="94cdb-202">Ensure that you have a working network or Internet connection, and that the Exchange server you provided is correct.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-203">不支持 http。</span><span class="sxs-lookup"><span data-stu-id="94cdb-203">http not supported.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-204">提供了采用 <i>http://</i>（而不是 <i>https://</i>）的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="94cdb-204">An Exchange server with <i>http://</i> instead of <i>https://</i> was provided.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-205">无</span><span class="sxs-lookup"><span data-stu-id="94cdb-205">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-206">使用采用 https 的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="94cdb-206">Use an Exchange server that uses https.</span></span></p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p><span data-ttu-id="94cdb-207">用户登录到标题名为“此帐户有问题”的 ActiveSync 相关页面。</span><span class="sxs-lookup"><span data-stu-id="94cdb-207">People land on the page titled "There's a problem with this account" regarding ActiveSync.</span></span></p>
</div>
<div> </div>
</td>
<td>
<p><span data-ttu-id="94cdb-208">ActiveSync 策略 PasswordEnabled 设置为 True（或 1）。</span><span class="sxs-lookup"><span data-stu-id="94cdb-208">The ActiveSync policy PasswordEnabled is set to True (or 1).</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-209">无</span><span class="sxs-lookup"><span data-stu-id="94cdb-209">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-210">创建一个新的 ActiveSync 策略，其中 PasswordEnabled 设置为 False（或 0），然后将该策略应用到帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-210">Create a new ActiveSync policy where PasswordEnabled is set to False (or 0), and then apply that policy to the account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-211">Surface Hub 未连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="94cdb-211">The Surface Hub doesn't have a connection to Exchange.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-212">无</span><span class="sxs-lookup"><span data-stu-id="94cdb-212">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-213">确保具有正常的网络或 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="94cdb-213">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="94cdb-214">Exchange 返回一个指示错误的状态代码。</span><span class="sxs-lookup"><span data-stu-id="94cdb-214">Exchange returns a status code indicating an error.</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-215">无</span><span class="sxs-lookup"><span data-stu-id="94cdb-215">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="94cdb-216">确保具有正常的网络或 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="94cdb-216">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a><span data-ttu-id="94cdb-217">首次运行，域加入页面问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-217">First run, Domain join page issues</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94cdb-218">问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-218">Issue</span></span></th>
<th align="left"><span data-ttu-id="94cdb-219">原因</span><span class="sxs-lookup"><span data-stu-id="94cdb-219">Causes</span></span></th>
<th align="left"><span data-ttu-id="94cdb-220">可能的修补程序</span><span class="sxs-lookup"><span data-stu-id="94cdb-220">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-221">在尝试加入域时，错误会显示帐户无法使用指定的凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="94cdb-221">When trying to join a domain, an error shows that the account couldn't authenticate using the specified credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-222">提供的凭据不能加入指定域。</span><span class="sxs-lookup"><span data-stu-id="94cdb-222">The credentials provided are not capable of joining the specified domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-223">针对指定域中存在的帐户输入正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="94cdb-223">Enter correct credentials for an account that exists in the specified domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-224">从域指定某个组时，错误会显示在域上找不到该组。</span><span class="sxs-lookup"><span data-stu-id="94cdb-224">When specifying a group from a domain, an error shows that the group couldn't be found on the domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-225">该组已删除或不再存在。</span><span class="sxs-lookup"><span data-stu-id="94cdb-225">The group may have been removed or no longer exists.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-226">验证该组是否存在于域中。</span><span class="sxs-lookup"><span data-stu-id="94cdb-226">Verify that the group exists within the domain.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a name="first-run,-exchange-server-page"></a><span data-ttu-id="94cdb-227">首次运行，Exchange Server 页面</span><span class="sxs-lookup"><span data-stu-id="94cdb-227">First run, Exchange server page</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94cdb-228">问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-228">Issue</span></span></th>
<th align="left"><span data-ttu-id="94cdb-229">原因</span><span class="sxs-lookup"><span data-stu-id="94cdb-229">Causes</span></span></th>
<th align="left"><span data-ttu-id="94cdb-230">可能的修补程序</span><span class="sxs-lookup"><span data-stu-id="94cdb-230">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-231">用户登录到此页面，然后要求提供 Exchange Server 地址。</span><span class="sxs-lookup"><span data-stu-id="94cdb-231">People land on this page and are asked for the Exchange server address.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-232">Exchange Server 未配置为自动发现。</span><span class="sxs-lookup"><span data-stu-id="94cdb-232">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-233">为设备帐户启用 Exchange Server 的自动发现，或手动输入帐户的 Exchange Server 地址。</span><span class="sxs-lookup"><span data-stu-id="94cdb-233">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a><span data-ttu-id="94cdb-234">首次运行，设备上的问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-234">First run, On-device issues</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94cdb-235">问题</span><span class="sxs-lookup"><span data-stu-id="94cdb-235">Issue</span></span></th>
<th align="left"><span data-ttu-id="94cdb-236">原因</span><span class="sxs-lookup"><span data-stu-id="94cdb-236">Causes</span></span></th>
<th align="left"><span data-ttu-id="94cdb-237">错误代码</span><span class="sxs-lookup"><span data-stu-id="94cdb-237">Error codes</span></span></th>
<th align="left"><span data-ttu-id="94cdb-238">可能的修补程序</span><span class="sxs-lookup"><span data-stu-id="94cdb-238">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-239">无法同步邮件/日历。</span><span class="sxs-lookup"><span data-stu-id="94cdb-239">Can't sync mail/calendar.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-240">帐户不允许 Surface Hub 作为允许设备。</span><span class="sxs-lookup"><span data-stu-id="94cdb-240">The account has not allowed the Surface Hub as an allowed device.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-241">0x86000C1C</span><span class="sxs-lookup"><span data-stu-id="94cdb-241">0x86000C1C</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-242">通过设置邮箱的 ActiveSyncAllowedDeviceIds 属性，将 Surface Hub 设备 ID 添加到 "允许列表" <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="94cdb-242">Add the Surface Hub device ID to the allowed list by setting the <strong>ActiveSyncAllowedDeviceIds</strong> property for the mailbox.</span></span></p></td>
</tr>
</tbody>
</table>

 



 

## <a name="exchange-activesync-errors"></a><span data-ttu-id="94cdb-243">Exchange ActiveSync 错误</span><span class="sxs-lookup"><span data-stu-id="94cdb-243">Exchange ActiveSync errors</span></span>


<span data-ttu-id="94cdb-244">本部分列出了状态代码、映射、用户消息，以及管理员为解决 Exchange ActiveSync 错误可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="94cdb-244">This section lists status codes, mapping, user messages, and actions an admin can take to solve Exchange ActiveSync errors.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94cdb-245">十六进制代码</span><span class="sxs-lookup"><span data-stu-id="94cdb-245">Hex Code</span></span></th>
<th align="left"><span data-ttu-id="94cdb-246">映射</span><span class="sxs-lookup"><span data-stu-id="94cdb-246">Mapping</span></span></th>
<th align="left"><span data-ttu-id="94cdb-247">用户友好消息</span><span class="sxs-lookup"><span data-stu-id="94cdb-247">User-Friendly Message</span></span></th>
<th align="left"><span data-ttu-id="94cdb-248">管理员应采取的操作</span><span class="sxs-lookup"><span data-stu-id="94cdb-248">Action admin should take</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-249">0x85010002</span><span class="sxs-lookup"><span data-stu-id="94cdb-249">0x85010002</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-250">E_HTTP_DENIED</span><span class="sxs-lookup"><span data-stu-id="94cdb-250">E_HTTP_DENIED</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-251">必须更新密码。</span><span class="sxs-lookup"><span data-stu-id="94cdb-251">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-252">更新密码。</span><span class="sxs-lookup"><span data-stu-id="94cdb-252">Update the password.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-253">0x80072EFD</span><span class="sxs-lookup"><span data-stu-id="94cdb-253">0x80072EFD</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-254">WININET_E_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="94cdb-254">WININET_E_CANNOT_CONNECT</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-255">目前无法连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-255">Can't connect to the server right now.</span></span> <span data-ttu-id="94cdb-256">请稍等片刻，然后重试，或检查帐户设置。</span><span class="sxs-lookup"><span data-stu-id="94cdb-256">Wait a while and try again, or check the account settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-257">验证服务器名称是否正确且可访问。</span><span class="sxs-lookup"><span data-stu-id="94cdb-257">Verify that the server name is correct and reachable.</span></span> <span data-ttu-id="94cdb-258">验证设备是否已连接到网络。</span><span class="sxs-lookup"><span data-stu-id="94cdb-258">Verify that the device is connected to the network.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-259">0x86000C29</span><span class="sxs-lookup"><span data-stu-id="94cdb-259">0x86000C29</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED （策略不匹配）</span><span class="sxs-lookup"><span data-stu-id="94cdb-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (policies don't match)</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-261">使用了与 Surface Hub 不兼容的策略配置帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-261">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-262">为此帐户禁用 <strong>PasswordEnabled</strong> 策略。</span><span class="sxs-lookup"><span data-stu-id="94cdb-262">Disable the <strong>PasswordEnabled</strong> policy for this account.</span></span></p>
<p><span data-ttu-id="94cdb-263">如果在策略刷新间隔内帐户未收到任何服务器通知，我们有一个 bug，我们可能会出现策略错误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-263">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-264">0x86000C4C</span><span class="sxs-lookup"><span data-stu-id="94cdb-264">0x86000C4C</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span><span class="sxs-lookup"><span data-stu-id="94cdb-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-266">帐户有过多的设备合作关系。</span><span class="sxs-lookup"><span data-stu-id="94cdb-266">The account has too many device partnerships.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-267">在服务器上删除一个或多个合作关系。</span><span class="sxs-lookup"><span data-stu-id="94cdb-267">Delete one or more partnerships on the server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-268">0x86000C0A</span><span class="sxs-lookup"><span data-stu-id="94cdb-268">0x86000C0A</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span><span class="sxs-lookup"><span data-stu-id="94cdb-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-270">目前无法连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-270">Can't connect to the server right now.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-271">在服务器重新联机之前，请等待。</span><span class="sxs-lookup"><span data-stu-id="94cdb-271">Wait until the server comes back online.</span></span> <span data-ttu-id="94cdb-272">如果问题仍然存在，请重新预配帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-272">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-273">0x85050003</span><span class="sxs-lookup"><span data-stu-id="94cdb-273">0x85050003</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-274">E_CREDENTIALS_EXPIRED（凭据已过期，因此需要进行更新）</span><span class="sxs-lookup"><span data-stu-id="94cdb-274">E_CREDENTIALS_EXPIRED (Credentials have expired and need to be updated)</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-275">必须更新密码。</span><span class="sxs-lookup"><span data-stu-id="94cdb-275">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-276">更新密码。</span><span class="sxs-lookup"><span data-stu-id="94cdb-276">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-277">0x8505000D</span><span class="sxs-lookup"><span data-stu-id="94cdb-277">0x8505000D</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-278">E_AIRSYNC_RESET_RETRY</span><span class="sxs-lookup"><span data-stu-id="94cdb-278">E_AIRSYNC_RESET_RETRY</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-279">目前无法连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-279">Can't connect to the server right now.</span></span> <span data-ttu-id="94cdb-280">等待一段时间，或检查帐户的设置。</span><span class="sxs-lookup"><span data-stu-id="94cdb-280">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-281">这通常是一个暂时性错误，但如果问题仍然存在，请检查与帐户关联的设备数目，并删除其中一些设备（如果数目较大）。</span><span class="sxs-lookup"><span data-stu-id="94cdb-281">This is normally a transient error but if the issue persists check the number of devices associated with the account and delete some of them if the number is large.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-282">0x86000C16</span><span class="sxs-lookup"><span data-stu-id="94cdb-282">0x86000C16</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span><span class="sxs-lookup"><span data-stu-id="94cdb-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-284">邮箱已迁移到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-284">The mailbox was migrated to a different server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-285">你应该从未看到此错误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-285">You should never see this error.</span></span> <span data-ttu-id="94cdb-286">如果问题仍然存在，请重新预配帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-286">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-287">0x85010004</span><span class="sxs-lookup"><span data-stu-id="94cdb-287">0x85010004</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-288">E_HTTP_FORBIDDEN</span><span class="sxs-lookup"><span data-stu-id="94cdb-288">E_HTTP_FORBIDDEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-289">目前无法连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-289">Can't connect to the server right now.</span></span> <span data-ttu-id="94cdb-290">请稍后再试，或检查帐户的设置。</span><span class="sxs-lookup"><span data-stu-id="94cdb-290">Wait a while and try again, or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-291">验证服务器名称，以确保其正确无误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-291">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="94cdb-292">如果帐户使用基于证书的身份验证，请确保该证书仍有效，并更新它（如果无效）。</span><span class="sxs-lookup"><span data-stu-id="94cdb-292">If the account is using cert based authentication make sure the certificate is still valid and update it if not.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-293">0x85030028</span><span class="sxs-lookup"><span data-stu-id="94cdb-293">0x85030028</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span><span class="sxs-lookup"><span data-stu-id="94cdb-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-295">帐户的密码或客户证书缺失或无效。</span><span class="sxs-lookup"><span data-stu-id="94cdb-295">The account's password or client certificate are missing or invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-296">更新密码和/或部署客户端证书。</span><span class="sxs-lookup"><span data-stu-id="94cdb-296">Update the password and/or deploy the client certificate.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-297">0x86000C2A</span><span class="sxs-lookup"><span data-stu-id="94cdb-297">0x86000C2A</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span><span class="sxs-lookup"><span data-stu-id="94cdb-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-299">使用了与 Surface Hub 不兼容的策略配置帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-299">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-300">为此帐户禁用 PasswordEnabled 策略。</span><span class="sxs-lookup"><span data-stu-id="94cdb-300">Disable the PasswordEnabled policy for this account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-301">0x85050002</span><span class="sxs-lookup"><span data-stu-id="94cdb-301">0x85050002</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-302">E_CREDENTIALS_UNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94cdb-302">E_CREDENTIALS_UNAVAILABLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-303">必须更新密码。</span><span class="sxs-lookup"><span data-stu-id="94cdb-303">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-304">更新密码。</span><span class="sxs-lookup"><span data-stu-id="94cdb-304">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-305">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="94cdb-305">0x80072EE2</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-306">WININET_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94cdb-306">WININET_E_TIMEOUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-307">网络不支持接收服务器通知所需的最小空闲超时，或者服务器处于离线状态。</span><span class="sxs-lookup"><span data-stu-id="94cdb-307">The network doesn't support the minimum idle timeout required to receive server notification, or the server is offline.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-308">验证服务器是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="94cdb-308">Verify that the server is running.</span></span> <span data-ttu-id="94cdb-309">验证 NAT 设置。</span><span class="sxs-lookup"><span data-stu-id="94cdb-309">Verify the NAT settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-310">0x85002004</span><span class="sxs-lookup"><span data-stu-id="94cdb-310">0x85002004</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-311">E_FAIL_ABORT</span><span class="sxs-lookup"><span data-stu-id="94cdb-311">E_FAIL_ABORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-312">此错误用于中断挂起的同步，将不会向用户公开。</span><span class="sxs-lookup"><span data-stu-id="94cdb-312">This error is used to interrupt the hanging sync, and will not be exposed to users.</span></span> <span data-ttu-id="94cdb-313">该错误将显示在诊断数据中(如果强制执行交互式同步、删除帐户或更新其设置)。</span><span class="sxs-lookup"><span data-stu-id="94cdb-313">It will be shown in the diagnostic data if you force an interactive sync, delete the account, or update its settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-314">无。</span><span class="sxs-lookup"><span data-stu-id="94cdb-314">Nothing.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-315">0x85010017</span><span class="sxs-lookup"><span data-stu-id="94cdb-315">0x85010017</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-316">E_HTTP_SERVICE_UNAVAIL</span><span class="sxs-lookup"><span data-stu-id="94cdb-316">E_HTTP_SERVICE_UNAVAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-317">目前无法连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-317">Can't connect to the server right now.</span></span> <span data-ttu-id="94cdb-318">等待一段时间，或检查帐户的设置。</span><span class="sxs-lookup"><span data-stu-id="94cdb-318">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-319">验证服务器名称，以确保其正确无误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-319">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="94cdb-320">在服务器重新联机之前，请等待。</span><span class="sxs-lookup"><span data-stu-id="94cdb-320">Wait until the server comes back online.</span></span> <span data-ttu-id="94cdb-321">如果问题仍然存在，请重新预配帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-321">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-322">0x86000C0D</span><span class="sxs-lookup"><span data-stu-id="94cdb-322">0x86000C0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span><span class="sxs-lookup"><span data-stu-id="94cdb-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-324">目前无法连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-324">Can't connect to the server right now.</span></span> <span data-ttu-id="94cdb-325">等待一段时间，或检查帐户的设置。</span><span class="sxs-lookup"><span data-stu-id="94cdb-325">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-326">验证服务器名称，以确保其正确无误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-326">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="94cdb-327">在服务器重新联机之前，请等待。</span><span class="sxs-lookup"><span data-stu-id="94cdb-327">Wait until the server comes back online.</span></span> <span data-ttu-id="94cdb-328">如果问题仍然存在，请重新预配帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-328">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-329">0x85030027</span><span class="sxs-lookup"><span data-stu-id="94cdb-329">0x85030027</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-330">E_ACTIVESYNC_GETCERT</span><span class="sxs-lookup"><span data-stu-id="94cdb-330">E_ACTIVESYNC_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-331">Exchange Server 需要证书。</span><span class="sxs-lookup"><span data-stu-id="94cdb-331">The Exchange server requires a certificate.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-332">在 Surface Hub 上导入相应的 EAS 证书。</span><span class="sxs-lookup"><span data-stu-id="94cdb-332">Import the appropriate EAS certificate on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-333">0x86000C2B</span><span class="sxs-lookup"><span data-stu-id="94cdb-333">0x86000C2B</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span><span class="sxs-lookup"><span data-stu-id="94cdb-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-335">使用了与 Surface Hub 不兼容的策略配置帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-335">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-336">为此帐户禁用 PasswordEnabled 策略。</span><span class="sxs-lookup"><span data-stu-id="94cdb-336">Disable the PasswordEnabled policy for this account.</span></span></p>
<p><span data-ttu-id="94cdb-337">如果在策略刷新间隔内帐户未收到任何服务器通知，我们有一个 bug，我们可能会出现策略错误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-337">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-338">0x85010005</span><span class="sxs-lookup"><span data-stu-id="94cdb-338">0x85010005</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-339">E_HTTP_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="94cdb-339">E_HTTP_NOT_FOUND</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-340">服务器名称无效。</span><span class="sxs-lookup"><span data-stu-id="94cdb-340">The server name is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-341">验证服务器名称，以确保其正确无误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-341">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="94cdb-342">如果问题仍然存在，请重新预配帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-342">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-343">0x85010014</span><span class="sxs-lookup"><span data-stu-id="94cdb-343">0x85010014</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-344">E_HTTP_SERVER_ERROR</span><span class="sxs-lookup"><span data-stu-id="94cdb-344">E_HTTP_SERVER_ERROR</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-345">无法连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="94cdb-345">Can't connect to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-346">验证服务器名称，以确保其正确无误。</span><span class="sxs-lookup"><span data-stu-id="94cdb-346">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="94cdb-347">触发同步，如果问题仍然存在，请重新预预配帐户。</span><span class="sxs-lookup"><span data-stu-id="94cdb-347">Trigger a sync and, if the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-348">0x80072EE7</span><span class="sxs-lookup"><span data-stu-id="94cdb-348">0x80072EE7</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-349">WININET_E_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="94cdb-349">WININET_E_NAME_NOT_RESOLVED</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-350">无法解析服务器名称或地址。</span><span class="sxs-lookup"><span data-stu-id="94cdb-350">The server name or address could not be resolved.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-351">确保输入的服务器名称正确。</span><span class="sxs-lookup"><span data-stu-id="94cdb-351">Make sure the server name is entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-352">0x8007052F</span><span class="sxs-lookup"><span data-stu-id="94cdb-352">0x8007052F</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-353">ERROR_ACCOUNT_RESTRICTION</span><span class="sxs-lookup"><span data-stu-id="94cdb-353">ERROR_ACCOUNT_RESTRICTION</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-354">自动发现 Exchange Server 时，应用可阻止登录的用户登录到该服务器的策略。</span><span class="sxs-lookup"><span data-stu-id="94cdb-354">While auto-discovering the Exchange server, a policy is applied that prevents the logged-in user from logging in to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-355">这是一个计时问题。</span><span class="sxs-lookup"><span data-stu-id="94cdb-355">This is a timing issue.</span></span> <span data-ttu-id="94cdb-356">重新验证帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="94cdb-356">Re-verify the account's credentials.</span></span> <span data-ttu-id="94cdb-357">如果它们正确无误，请尝试重新预配。</span><span class="sxs-lookup"><span data-stu-id="94cdb-357">Try to re-provision when they're correct.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-358">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="94cdb-358">0x800C0019</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-359">INET_E_INVALID_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="94cdb-359">INET_E_INVALID_CERTIFICATE</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-360">访问此资源所需的安全证书无效。</span><span class="sxs-lookup"><span data-stu-id="94cdb-360">Security certificate required to access this resource is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-361">安装提供的设备帐户所需的正确 ActiveSync 证书。</span><span class="sxs-lookup"><span data-stu-id="94cdb-361">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="94cdb-362">0x80072F0D</span><span class="sxs-lookup"><span data-stu-id="94cdb-362">0x80072F0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-363">ININET_E_INVALID_CA</span><span class="sxs-lookup"><span data-stu-id="94cdb-363">WININET_E_INVALID_CA</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-364">证书颁发机构无效或不正确。</span><span class="sxs-lookup"><span data-stu-id="94cdb-364">The certificate authority is invalid or is incorrect.</span></span> <span data-ttu-id="94cdb-365">无法自动发现 Exchange Server，因为缺少证书。</span><span class="sxs-lookup"><span data-stu-id="94cdb-365">Could not auto-discover the Exchange server because a certificate is missing.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-366">安装提供的设备帐户所需的正确 ActiveSync 证书。</span><span class="sxs-lookup"><span data-stu-id="94cdb-366">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="94cdb-367">0x80004005</span><span class="sxs-lookup"><span data-stu-id="94cdb-367">0x80004005</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-368">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94cdb-368">E_FAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-369">找不到提供的域。</span><span class="sxs-lookup"><span data-stu-id="94cdb-369">The domain provided couldn't be found.</span></span> <span data-ttu-id="94cdb-370">无法自动发现 Exchange Server，且未在设置中提供它。</span><span class="sxs-lookup"><span data-stu-id="94cdb-370">The Exchange server could not be auto-discovered and was not provided in the settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94cdb-371">确保输入的域是 FQDN，且在 Exchange Server 文本框中输入的是 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="94cdb-371">Make sure that the domain entered is the FQDN, and that there is an Exchange server entered in the Exchange server text box.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="contact-support"></a><span data-ttu-id="94cdb-372">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="94cdb-372">Contact Support</span></span>

<span data-ttu-id="94cdb-373">如果有疑问或需要帮助，您可以[创建支持请求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="94cdb-373">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


 
## <a name="related-content"></a><span data-ttu-id="94cdb-374">相关内容</span><span class="sxs-lookup"><span data-stu-id="94cdb-374">Related content</span></span>

- [<span data-ttu-id="94cdb-375">Surface Hub 的 Miracast 连接疑难解答</span><span class="sxs-lookup"><span data-stu-id="94cdb-375">Troubleshooting Miracast connection to the Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 






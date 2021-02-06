---
title: '使用 Surface Hub v1 (UI 创建设备) '
description: 如果你希望使用图形用户界面，可通过 Office 365 UI 或 Exchange 管理中心为 Microsoft Surface Hub 创建设备帐户。
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: 创建设备帐户， Office 365 UI， Exchange 管理中心， Microsoft 365 管理中心， Skype for Business， 移动设备邮箱策略
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: 9e6d72dc2b36bb149ee09c2edab885c80e60ac14
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314465"
---
# <span data-ttu-id="27716-104">使用 Surface Hub v1 (UI 创建设备) </span><span class="sxs-lookup"><span data-stu-id="27716-104">Create a device account using UI (Surface Hub v1)</span></span>

 > [!NOTE]
 ><span data-ttu-id="27716-105">此页面包含有关 v1 版本 (Surface Hub) 。</span><span class="sxs-lookup"><span data-stu-id="27716-105">This page includes information about the original Surface Hub (v1).</span></span> <span data-ttu-id="27716-106">对于 Surface Hub 2S，请参阅["创建 Surface Hub 2S 设备帐户"。](surface-hub-2s-account.md)</span><span class="sxs-lookup"><span data-stu-id="27716-106">For Surface Hub 2S, see [Create Surface Hub 2S device account](surface-hub-2s-account.md).</span></span>

<span data-ttu-id="27716-107">如果你希望使用图形用户界面，可通过 [Office 365 UI](#create-device-acct-o365) 或 [Exchange 管理中心](#create-device-acct-eac)为 Microsoft Surface Hub 创建设备帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-107">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="27716-108">使用 Office 365 创建设备帐户</span><span class="sxs-lookup"><span data-stu-id="27716-108">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="27716-109">[在 Microsoft 365 管理中心创建帐户](#create-device-acct-o365-admin-ctr)。</span><span class="sxs-lookup"><span data-stu-id="27716-109">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="27716-110">[从 Microsoft Exchange 管理中心创建移动设备邮箱 (ActiveSync) 策略](#create-device-acct-o365-mbx-policy)。</span><span class="sxs-lookup"><span data-stu-id="27716-110">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="27716-111">[使用 PowerShell 完成设备帐户的创建](#create-device-acct-o365-complete-acct)。</span><span class="sxs-lookup"><span data-stu-id="27716-111">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="27716-112">[使用 PowerShell 来配置帐户的 Exchange 属性](#create-device-acct-o365-configure-exch-prop)。</span><span class="sxs-lookup"><span data-stu-id="27716-112">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="27716-113">[启用带 Skype for Business 的帐户](#create-device-acct-o365-skype-for-business)。</span><span class="sxs-lookup"><span data-stu-id="27716-113">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="27716-114">在管理中心创建帐户</span><span class="sxs-lookup"><span data-stu-id="27716-114">Create the account in the admin center</span></span>

1.  <span data-ttu-id="27716-115">通过访问登录到 Office 365 https://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="27716-115">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="27716-116">提供你的 Office 365 租户的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="27716-116">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="27716-117">这会将你带至 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="27716-117">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Microsoft 365 管理中心。](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="27716-119">在管理中心中， **导航到左侧** 面板中的"资源"，然后单击"会议室& **设备**。</span><span class="sxs-lookup"><span data-stu-id="27716-119">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![管理&中的会议室和设备选项](images/room-equipment.png)

4. <span data-ttu-id="27716-121">单击 **“添加”** 创建新的房间帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-121">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="27716-122">输入帐户的显示名称和电子邮件地址，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="27716-122">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![创建新的房间帐户窗口](images/room-add.png)

5. <span data-ttu-id="27716-124">从活动用户列表中选择刚创建的房间帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-124">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="27716-125">在右侧面板中，你可以看到帐户属性和多个可选操作。</span><span class="sxs-lookup"><span data-stu-id="27716-125">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="27716-126">单击**重置密码**更改密码，然后取消选择**在用户首次登录时，让其更改密码**，因为无法通过 Surface Hub 登录流程更改密码。</span><span class="sxs-lookup"><span data-stu-id="27716-126">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="27716-127">在**已分配的许可证**部分，单击**编辑**，然后单击相应许可证旁边的下拉箭头以展开详细信息。</span><span class="sxs-lookup"><span data-stu-id="27716-127">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="27716-128">选择用户位置，然后在许可证列表中，切换 **Skype for Business Online（计划 2）**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="27716-128">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="27716-129">许可证根据组织的情况而异（例如，你可能拥有计划 2，也可能是计划 3）。</span><span class="sxs-lookup"><span data-stu-id="27716-129">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="27716-130">从 Exchange 管理中心创建移动设备邮箱 (ActiveSync) 策略</span><span class="sxs-lookup"><span data-stu-id="27716-130">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="27716-131">在管理中心的左面板中，单击 **"管理**"，然后单击 **"Exchange"。**</span><span class="sxs-lookup"><span data-stu-id="27716-131">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![管理中心，显示 Exchange 活动用户。](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="27716-133">这将打开浏览器上的其他选项卡以将你带到 Exchange 管理中心，可在其中为 Surface Hub 创建和设置邮箱设置。</span><span class="sxs-lookup"><span data-stu-id="27716-133">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Exchange 管理中心。](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="27716-135">若要创建移动设备邮箱策略，请从左侧面板单击**移动**，然后单击**移动设备邮箱策略**。</span><span class="sxs-lookup"><span data-stu-id="27716-135">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="27716-136">Surface Hub 需要一个具有不需要密码的移动设备邮箱策略的帐户，因此如果你具有一个符合该要求的现有策略，可将该策略应用到帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-136">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="27716-137">如若不然，请使用以下步骤创建一个仅用于 Surface Hub 设备帐户的新帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-137">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Exchange 管理中心 - 创建移动设备邮箱策略。](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="27716-139">若要创建新的 Surface Hub 移动设备邮箱策略，请从策略列表上方的控件中单击 **+** 按钮来添加新策略。</span><span class="sxs-lookup"><span data-stu-id="27716-139">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="27716-140">对于名称，提供一个可帮助你将此策略与其他设备帐户区分开来的名称（例如 *SurfaceHubDeviceMobilePolicy*）。</span><span class="sxs-lookup"><span data-stu-id="27716-140">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="27716-141">确保该策略不需要已分配给设备的密码，因此请确保**需要密码**仍处于未选中状态，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="27716-141">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![显示新移动设备策略的图像。](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="27716-143">创建新的移动设备邮箱策略后，将返回到**Exchange 管理中心**，随后你将看到列出的新策略。</span><span class="sxs-lookup"><span data-stu-id="27716-143">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![具有 Exchange 管理中心中的新移动设备邮箱策略的图像。](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="27716-145">使用 PowerShell 完成设备帐户的创建</span><span class="sxs-lookup"><span data-stu-id="27716-145">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="27716-146">从此处开始，将需要使用 PowerShell 完成帐户创建过程以设置一些配置。</span><span class="sxs-lookup"><span data-stu-id="27716-146">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="27716-147">为了运行这些 PowerShell 脚本所使用的 cmdlet，必须为管理 PowerShell 控制台安装以下项：</span><span class="sxs-lookup"><span data-stu-id="27716-147">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="27716-148">Microsoft Online Services Sign-In IT 专业人员 RTW 的助理</span><span class="sxs-lookup"><span data-stu-id="27716-148">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="27716-149">Windows PowerShell 的 Windows Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="27716-149">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="27716-150">Skype for Business Online、Windows PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="27716-150">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="27716-151">在 Powershell 中安装以下模块</span><span class="sxs-lookup"><span data-stu-id="27716-151">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="27716-152">连接到在线服务</span><span class="sxs-lookup"><span data-stu-id="27716-152">Connecting to online services</span></span>

1.  <span data-ttu-id="27716-153">以管理员身份运行 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="27716-153">Run Windows PowerShell as Administrator.</span></span>

    ![显示如何以管理员身份启动和运行 Windows PowerShell 的图像。](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="27716-155">创建凭据对象，随后创建连接到 Skype for Business Online 的新会话，并提供全局租户管理员帐户，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="27716-155">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Windows PowerShell 凭据请求的图像。](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="27716-157">若要连接到 Microsoft Online Services，请运行：</span><span class="sxs-lookup"><span data-stu-id="27716-157">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="27716-159">现在，如果要连接到 Skype for Business Online Services，请运行：</span><span class="sxs-lookup"><span data-stu-id="27716-159">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="27716-161">最后，如果要连接到 Exchange Online Services，请运行：</span><span class="sxs-lookup"><span data-stu-id="27716-161">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="27716-163">现在，你需要导入刚创建的 Skype for Business Online 会话和 Exchange Online 会话，从而将导入 Exchange 和 Skype 命令，以便你可以在本地使用它们。</span><span class="sxs-lookup"><span data-stu-id="27716-163">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="27716-164">请注意，这可能需要一段时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="27716-164">Note that this could take a while to complete.</span></span>

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="27716-166">连接到在线服务后，还需要运行几个 cmdlet 才能将此帐户配置为 Surface Hub 设备帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-166">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="27716-167">使用 PowerShell 来配置帐户的 Exchange 属性</span><span class="sxs-lookup"><span data-stu-id="27716-167">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="27716-168">现在你已连接到在线服务，便可完成设备帐户的设置。</span><span class="sxs-lookup"><span data-stu-id="27716-168">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="27716-169">将使用设备帐户电子邮件地址执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="27716-169">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="27716-170">将邮箱类型从常规更改为会议室。</span><span class="sxs-lookup"><span data-stu-id="27716-170">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="27716-171">设置密码并启用会议室邮箱帐户</span><span class="sxs-lookup"><span data-stu-id="27716-171">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="27716-172">更改各种 Exchange 属性</span><span class="sxs-lookup"><span data-stu-id="27716-172">Change various Exchange properties</span></span>
-   <span data-ttu-id="27716-173">将用户帐户密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="27716-173">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="27716-174">你将需要输入帐户的邮件地址，并使用该值创建一个变量：</span><span class="sxs-lookup"><span data-stu-id="27716-174">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="27716-175">若要存储从邮箱获取的值：</span><span class="sxs-lookup"><span data-stu-id="27716-175">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="27716-176">打印值：</span><span class="sxs-lookup"><span data-stu-id="27716-176">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="27716-177">你将看到相应的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="27716-177">You will see the correct email address.</span></span>

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="27716-179">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="27716-179">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="27716-180">可以在设备帐户上设置各种 Exchange 属性以改进会议体验。</span><span class="sxs-lookup"><span data-stu-id="27716-180">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="27716-181">可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)部分中查看哪些属性需要设置。</span><span class="sxs-lookup"><span data-stu-id="27716-181">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="27716-183">如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。</span><span class="sxs-lookup"><span data-stu-id="27716-183">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="27716-184">有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="27716-184">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="27716-185">启用带 Skype for Business 的帐户</span><span class="sxs-lookup"><span data-stu-id="27716-185">Enable the account with Skype for Business</span></span>

<span data-ttu-id="27716-186">启用带 Skype for Business 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-186">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="27716-187">为了启用 Skype for Business，你的环境将需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="27716-187">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="27716-188">你需要在 O365 计划中拥有 Skype for Business Online 独立计划 2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="27716-188">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="27716-189">该计划需要支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="27716-189">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="27716-190">如果需要使用 Surface Hub 企业语音 (服务提供商) PSTN 电话服务，则需要 Skype for Business Online 独立计划 3。</span><span class="sxs-lookup"><span data-stu-id="27716-190">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="27716-191">租户用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="27716-191">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="27716-192">Surface Hub 帐户确实需要 Skype for Business Online 独立计划 2 或 Skype for Business Online 独立计划 3 许可证，但不需要 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="27716-192">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="27716-193">首先从电脑创建一个远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="27716-193">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="27716-194">若要为 Skype for Business Server 启用你的 Surface Hub 帐户，请运行此 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="27716-194">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="27716-195">如果你不确定在你的环境中要用于 `RegistrarPool` 参数的值，可以使用此 cmdlet 从现有 Skype for Business 用户获取值：</span><span class="sxs-lookup"><span data-stu-id="27716-195">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="27716-196">使用 Exchange 管理中心创建设备帐户</span><span class="sxs-lookup"><span data-stu-id="27716-196">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="27716-197">此方法仅在从本地 Active Directory 同步时有效。</span><span class="sxs-lookup"><span data-stu-id="27716-197">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="27716-198">可以使用 Exchange 管理中心来创建设备帐户：</span><span class="sxs-lookup"><span data-stu-id="27716-198">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="27716-199">[使用 Exchange 管理中心创建帐户和邮箱](#create-device-acct-exch-admin-ctr)。</span><span class="sxs-lookup"><span data-stu-id="27716-199">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="27716-200">[从 Exchange 管理中心创建移动设备邮箱策略](#create-device-acct-exch-mbx-policy)。</span><span class="sxs-lookup"><span data-stu-id="27716-200">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="27716-201">[使用 PowerShell 来配置帐户](#create-device-acct-exch-powershell-conf)。</span><span class="sxs-lookup"><span data-stu-id="27716-201">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="27716-202">[启用带 Skype for Business 的帐户](#create-device-acct-exch-skype-for-business)。</span><span class="sxs-lookup"><span data-stu-id="27716-202">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="27716-203">使用 Exchange 管理中心创建帐户和邮箱</span><span class="sxs-lookup"><span data-stu-id="27716-203">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="27716-204">使用 Exchange 管理凭据登录到你的 Exchange 管理中心。</span><span class="sxs-lookup"><span data-stu-id="27716-204">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="27716-205">进入 Exchange 管理中心 (EAC) 后，导航到左侧面板中的**收件人**。</span><span class="sxs-lookup"><span data-stu-id="27716-205">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![在 Exchange 管理中心显示邮箱的图像。](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="27716-207">在邮箱列表上方的控件上，选择 **+** 来创建一个新邮箱，并提供**显示名称**、**名称**和**用户登录名称**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="27716-207">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![显示创建新邮箱的图像。](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="27716-209">从 Exchange 管理中心创建移动设备邮箱策略</span><span class="sxs-lookup"><span data-stu-id="27716-209">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="27716-210">如果要创建策略并将其分配给您创建的帐户，并且正在使用 Exchange 2010，则使用 EMC (Exchange 管理控制台管理控制台时查找有关策略创建和策略分配的相应) 。</span><span class="sxs-lookup"><span data-stu-id="27716-210">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="27716-211">转到 Exchange 管理中心。</span><span class="sxs-lookup"><span data-stu-id="27716-211">Go to the Exchange Admin Center.</span></span>

    ![显示 Exchange 管理中心的图像。](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="27716-213">若要创建移动设备邮箱策略，请从左侧面板中单击**移动**，然后单击**移动设备邮箱策略**。</span><span class="sxs-lookup"><span data-stu-id="27716-213">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="27716-214">Surface Hub 需要一个具有不需要密码的移动设备邮箱策略的帐户，因此如果你具有一个符合该要求的现有策略，可将该策略应用到帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-214">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="27716-215">如若不然，请使用以下步骤创建一个仅用于 Surface Hub 设备帐户的新帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-215">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![显示将 Exchange 管理中心用于创建移动设备邮箱策略的图像。](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="27716-217">若要创建新的移动设备帐户邮箱策略，请从策略列表上方的控件中单击 **+** 按钮以添加新策略。</span><span class="sxs-lookup"><span data-stu-id="27716-217">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="27716-218">对于名称，提供一个可帮助你将此策略与其他设备帐户区分开来的名称（例如 *SurfaceHubDeviceMobilePolicy*）。</span><span class="sxs-lookup"><span data-stu-id="27716-218">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="27716-219">策略不得受密码保护，因此请确保**需要密码**仍处于未选中状态，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="27716-219">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![显示新移动设备邮箱策略的图像。](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="27716-221">在创建新的移动设备邮箱策略后，返回到 Exchange 管理中心，随后你将看到列出的新策略。</span><span class="sxs-lookup"><span data-stu-id="27716-221">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![在 Exchange 管理中心显示新移动设备邮箱策略的图像。](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="27716-223">若要在未使用 PowerShell 的情况下应用 ActiveSync 策略，可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="27716-223">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="27716-224">在 EAC 中，依次单击**收件人**&gt;**邮箱**，然后选择邮箱。</span><span class="sxs-lookup"><span data-stu-id="27716-224">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![显示 Exchange 管理中心的图像。](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="27716-226">在**详细信息**窗格中，滚动到**电话和语音功能**，然后单击**查看详细信息**以显示**移动设备详细信息**屏幕。</span><span class="sxs-lookup"><span data-stu-id="27716-226">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![显示邮箱详细信息的图像。](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="27716-228">将显示当前已分配的移动设备邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="27716-228">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="27716-229">若要更改移动设备邮箱策略，请单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="27716-229">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![显示当前已分配的移动设备邮箱策略的图像。](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="27716-231">从列表中选择相应的移动设备邮箱策略，然后依次单击**确定**和**保存**。</span><span class="sxs-lookup"><span data-stu-id="27716-231">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![显示移动设备邮箱策略列表的图像。](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="27716-233">使用 PowerShell 配置帐户</span><span class="sxs-lookup"><span data-stu-id="27716-233">Use PowerShell to configure the account</span></span>

<span data-ttu-id="27716-234">现在你已连接到在线服务，便可完成设备帐户的设置。</span><span class="sxs-lookup"><span data-stu-id="27716-234">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="27716-235">将使用设备帐户电子邮件地址执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="27716-235">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="27716-236">将邮箱类型从常规更改为会议室。</span><span class="sxs-lookup"><span data-stu-id="27716-236">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="27716-237">更改各种 Exchange 属性</span><span class="sxs-lookup"><span data-stu-id="27716-237">Change various Exchange properties</span></span>
-   <span data-ttu-id="27716-238">将用户帐户密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="27716-238">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="27716-239">你将需要输入帐户的邮件地址，并使用该值创建一个变量：</span><span class="sxs-lookup"><span data-stu-id="27716-239">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="27716-240">若要存储从邮箱中获取的值：</span><span class="sxs-lookup"><span data-stu-id="27716-240">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="27716-241">通过运行以下内容打印值：</span><span class="sxs-lookup"><span data-stu-id="27716-241">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="27716-242">你将看到相应的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="27716-242">You will see the correct email address.</span></span>

2.  <span data-ttu-id="27716-243">你需要将帐户转换为会议室邮箱，因此请运行：</span><span class="sxs-lookup"><span data-stu-id="27716-243">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="27716-244">为了使设备帐户能够在 Surface Hub 上进行身份验证，你需要启用会议室邮箱帐户并设置密码，以便该帐户可由设备用于使用 ActiveSync 来获取会议信息并登录到 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="27716-244">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="27716-245">可以在设备帐户上设置各种 Exchange 属性以改进会议体验。</span><span class="sxs-lookup"><span data-stu-id="27716-245">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="27716-246">可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)部分中查看哪些属性需要设置。</span><span class="sxs-lookup"><span data-stu-id="27716-246">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="27716-247">现在我们必须在 AD 中设置一些属性。</span><span class="sxs-lookup"><span data-stu-id="27716-247">Now we have to set some properties in AD.</span></span> <span data-ttu-id="27716-248">为此，你需要帐户的别名（这是位于“@”之前的 UPN 的一部分）。</span><span class="sxs-lookup"><span data-stu-id="27716-248">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="27716-249">用户需要在 AD 中进行启用，然后才能使用 Surface Hub 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="27716-249">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="27716-250">运行：</span><span class="sxs-lookup"><span data-stu-id="27716-250">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="27716-251">如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。</span><span class="sxs-lookup"><span data-stu-id="27716-251">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="27716-252">有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="27716-252">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="27716-253">启用带 Skype for Business 的帐户</span><span class="sxs-lookup"><span data-stu-id="27716-253">Enable the account with Skype for Business</span></span>

<span data-ttu-id="27716-254">启用带 Skype for Business 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="27716-254">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="27716-255">为了启用 Skype for Business，你的环境将需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="27716-255">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

- <span data-ttu-id="27716-256">你需要在 O365 计划中拥有 Skype for Business Online 独立计划 2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="27716-256">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="27716-257">该计划需要支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="27716-257">The plan needs to support conferencing capability.</span></span>
- <span data-ttu-id="27716-258">如果需要使用 Surface Hub 企业语音 (服务提供商) PSTN 电话服务，则需要 Skype for Business Online 独立计划 3。</span><span class="sxs-lookup"><span data-stu-id="27716-258">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
- <span data-ttu-id="27716-259">租户用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="27716-259">Your tenant users must have Exchange mailboxes.</span></span>
- <span data-ttu-id="27716-260">Surface Hub 帐户确实需要 Skype for Business Online 独立计划 2 或 Skype for Business Online 独立计划 3 许可证，但不需要 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="27716-260">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1. <span data-ttu-id="27716-261">首先在电脑上创建一个远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="27716-261">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="27716-262">检索 Surface Hub 帐户注册器池</span><span class="sxs-lookup"><span data-stu-id="27716-262">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="27716-263">如果你不确定在你的环境中要用于 `RegistrarPool` 参数的值，你可以使用此 cmdlet 从现有 Skype for Business 用户获取值：</span><span class="sxs-lookup"><span data-stu-id="27716-263">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

 ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
 ```

3. <span data-ttu-id="27716-264">若要为 Skype for Business Server 启用你的 Surface Hub 帐户，请运行此 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="27716-264">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```
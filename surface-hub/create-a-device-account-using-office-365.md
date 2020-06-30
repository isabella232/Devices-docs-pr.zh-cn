---
title: 使用 UI 创建设备帐户 (Surface Hub)
description: 如果你希望使用图形用户界面，可通过 Office 365 UI 或 Exchange 管理中心为 Microsoft Surface Hub 创建设备帐户。
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: 创建设备帐户、Office 365 UI、Exchange Admin center、Microsoft 365 管理中心、Skype for business、移动设备邮箱策略
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: e1f82f084103d4eef942e812c5e4f0e8bf425def
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832099"
---
# 使用 UI 创建设备帐户 (Surface Hub)


如果你希望使用图形用户界面，可通过 [Office 365 UI](#create-device-acct-o365) 或 [Exchange 管理中心](#create-device-acct-eac)为 Microsoft Surface Hub 创建设备帐户。

## <a href="" id="create-device-acct-o365"></a>使用 Office 365 创建设备帐户


1.  [在 Microsoft 365 管理中心创建帐户](#create-device-acct-o365-admin-ctr)。
2.  [从 Microsoft Exchange 管理中心创建移动设备邮箱 (ActiveSync) 策略](#create-device-acct-o365-mbx-policy)。
3.  [使用 PowerShell 完成设备帐户的创建](#create-device-acct-o365-complete-acct)。
4.  [使用 PowerShell 来配置帐户的 Exchange 属性](#create-device-acct-o365-configure-exch-prop)。
5.  [启用带 Skype for Business 的帐户](#create-device-acct-o365-skype-for-business)。

### <a href="" id="create-device-acct-o365-admin-ctr"></a>在管理中心创建帐户

1.  通过访问登录到 Office 365https://portal.office.com
2.  提供你的 Office 365 租户的管理凭据。 这将把你转到 Microsoft 365 管理中心。

    ![Microsoft 365 管理中心。](images/setupdeviceaccto365-02.png)

3. 在管理中心中，导航到左面板中的 "**资源**"，然后单击 "**会议室" & 设备**。

    ![管理中心中的会议室 & 设备选项](images/room-equipment.png)

4. 单击 **“添加”** 创建新的房间帐户。 输入帐户的显示名称和电子邮件地址，然后单击**添加**。

    ![创建新的房间帐户窗口](images/room-add.png)

5. 从活动用户列表中选择刚创建的房间帐户。 在右侧面板中，你可以看到帐户属性和多个可选操作。 单击**重置密码**更改密码，然后取消选择**在用户首次登录时，让其更改密码**，因为无法通过 Surface Hub 登录流程更改密码。

6. 在**已分配的许可证**部分，单击**编辑**，然后单击相应许可证旁边的下拉箭头以展开详细信息。 选择用户位置，然后在许可证列表中，切换 **Skype for Business Online（计划 2）**，然后单击**保存**。 许可证根据组织的情况而异（例如，你可能拥有计划 2，也可能是计划 3）。

### <a href="" id="create-device-acct-o365-mbx-policy"></a>从 Exchange 管理中心创建移动设备邮箱 (ActiveSync) 策略

1.  在管理中心的左面板中，单击 "**管理**"，然后单击 " **Exchange**"。

    ![管理中心，显示 exchange 活动用户。](images/setupdeviceaccto365-08.png)

2.  这将打开浏览器上的其他选项卡以将你带到 Exchange 管理中心，可在其中为 Surface Hub 创建和设置邮箱设置。

    ![Exchange 管理中心。](images/setupdeviceaccto365-09.png)

3.  若要创建移动设备邮箱策略，请从左侧面板单击**移动**，然后单击**移动设备邮箱策略**。 Surface Hub 需要一个具有不需要密码的移动设备邮箱策略的帐户，因此如果你具有一个符合该要求的现有策略，可将该策略应用到帐户。 如若不然，请使用以下步骤创建一个仅用于 Surface Hub 设备帐户的新帐户。

    ![Exchange 管理中心 - 创建移动设备邮箱策略。](images/setupdeviceaccto365-10.png)

4.  若要创建新的 Surface Hub 移动设备邮箱策略，请从策略列表上方的控件中单击 **+** 按钮来添加新策略。 对于名称，提供一个可帮助你将此策略与其他设备帐户区分开来的名称（例如 *SurfaceHubDeviceMobilePolicy*）。 确保该策略不需要已分配给设备的密码，因此请确保**需要密码**仍处于未选中状态，然后单击**保存**。

    ![显示新移动设备策略的图像。](images/setupdeviceaccto365-11.png)

5.  创建新的移动设备邮箱策略后，将返回到**Exchange 管理中心**，随后你将看到列出的新策略。

    ![具有 Exchange 管理中心中的新移动设备邮箱策略的图像。](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a>使用 PowerShell 完成设备帐户的创建

从此处开始，将需要使用 PowerShell 完成帐户创建过程以设置一些配置。

为了运行这些 PowerShell 脚本所使用的 cmdlet，必须为管理 PowerShell 控制台安装以下项：

-   [面向 IT 专业人员的 Microsoft Online Services 登录助手 RTW](https://www.microsoft.com/download/details.aspx?id=41950)
-   [Windows PowerShell 的 Windows Azure Active Directory 模块](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [Skype for Business Online、Windows PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)

在 Powershell 中安装以下模块
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### 连接到在线服务

1.  以管理员身份运行 Windows PowerShell。

    ![显示如何以管理员身份启动和运行 Windows PowerShell 的图像。](images/setupdeviceaccto365-17.png)

2.  创建凭据对象，随后创建连接到 Skype for Business Online 的新会话，并提供全局租户管理员帐户，然后单击**确定**。

    ![Windows PowerShell 凭据请求的图像。](images/setupdeviceaccto365-18.png)

3.  若要连接到 Microsoft Online Services，请运行：

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-19.png)

4.  现在，如果要连接到 Skype for Business Online Services，请运行：

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-20.png)

5.  最后，如果要连接到 Exchange Online Services，请运行：

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-21.png)

6.  现在，你需要导入刚创建的 Skype for Business Online 会话和 Exchange Online 会话，从而将导入 Exchange 和 Skype 命令，以便你可以在本地使用它们。

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    请注意，这可能需要一段时间才能完成。

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-22.png)

7.  连接到在线服务后，还需要运行几个 cmdlet 才能将此帐户配置为 Surface Hub 设备帐户。

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a>使用 PowerShell 来配置帐户的 Exchange 属性

现在你已连接到在线服务，便可完成设备帐户的设置。 将使用设备帐户电子邮件地址执行以下操作：

-   将邮箱类型从常规更改为会议室。
-   设置密码并启用会议室邮箱帐户
-   更改各种 Exchange 属性
-   将用户帐户密码设置为永不过期。

1.  你将需要输入帐户的邮件地址，并使用该值创建一个变量：

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    若要存储从邮箱获取的值：

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    打印值：

    ```powershell
    $strEmail
    ```

    你将看到相应的电子邮件地址。

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-23.png)

2. 运行以下 cmdlet：

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  可以在设备帐户上设置各种 Exchange 属性以改进会议体验。 可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)部分中查看哪些属性需要设置。

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![显示 PowerShell cmdlet 的图像。](images/setupdeviceaccto365-26.png)

5.  如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。 有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a>启用带 Skype for Business 的帐户

启用带 Skype for Business 的设备帐户。

为了启用 Skype for Business，你的环境将需要满足以下先决条件：

-   您需要在 O365 计划中安装 Skype for business Online 独立计划2或更高版本。 该计划需要支持会议功能。
-   如果您需要针对 Surface Hub 的电话服务提供商使用企业语音（PSTN 电话服务），则需要 Skype for Business Online 独立计划3。
-   租户用户必须具有 Exchange 邮箱。
-   Surface Hub 帐户需要 Skype for business Online 独立计划2或 Skype for business Online 独立计划3许可证，但不需要 Exchange Online 许可证。

1.  首先从电脑创建一个远程 PowerShell 会话。

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  若要为 Skype for Business Server 启用你的 Surface Hub 帐户，请运行此 cmdlet：

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    如果你不确定在你的环境中要用于 `RegistrarPool` 参数的值，可以使用此 cmdlet 从现有 Skype for Business 用户获取值：

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a>使用 Exchange 管理中心创建设备帐户

>[!NOTE]
>仅当你从本地 Active Directory 进行同步时，此方法才会起作用。

可以使用 Exchange 管理中心来创建设备帐户：

1.  [使用 Exchange 管理中心创建帐户和邮箱](#create-device-acct-exch-admin-ctr)。
2.  [从 Exchange 管理中心创建移动设备邮箱策略](#create-device-acct-exch-mbx-policy)。
3.  [使用 PowerShell 来配置帐户](#create-device-acct-exch-powershell-conf)。
4.  [启用带 Skype for Business 的帐户](#create-device-acct-exch-skype-for-business)。

### <a href="" id="create-device-acct-exch-admin-ctr"></a>使用 Exchange 管理中心创建帐户和邮箱

1.  使用 Exchange 管理凭据登录到你的 Exchange 管理中心。
2.  进入 Exchange 管理中心 (EAC) 后，导航到左侧面板中的**收件人**。

    ![在 Exchange 管理中心显示邮箱的图像。](images/setupdeviceacctexch-01.png)

3.  在邮箱列表上方的控件上，选择 **+** 来创建一个新邮箱，并提供**显示名称**、**名称**和**用户登录名称**，然后单击**保存**。

    ![显示创建新邮箱的图像。](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a>从 Exchange 管理中心创建移动设备邮箱策略

>[!NOTE]
>如果你想要为你创建的帐户创建和分配策略，并且使用的是 Exchange 2010，请在使用 EMC （Exchange 管理控制台）时查找有关策略创建和策略分配的相应信息。

 

1.  转到 Exchange 管理中心。

    ![显示 Exchange 管理中心的图像。](images/setupdeviceacctexch-03.png)

2.  若要创建移动设备邮箱策略，请从左侧面板中单击**移动**，然后单击**移动设备邮箱策略**。 Surface Hub 需要一个具有不需要密码的移动设备邮箱策略的帐户，因此如果你具有一个符合该要求的现有策略，可将该策略应用到帐户。 如若不然，请使用以下步骤创建一个仅用于 Surface Hub 设备帐户的新帐户。

    ![显示将 Exchange 管理中心用于创建移动设备邮箱策略的图像。](images/setupdeviceacctexch-05.png)

3.  若要创建新的移动设备帐户邮箱策略，请从策略列表上方的控件中单击 **+** 按钮以添加新策略。 对于名称，提供一个可帮助你将此策略与其他设备帐户区分开来的名称（例如 *SurfaceHubDeviceMobilePolicy*）。 策略不得受密码保护，因此请确保**需要密码**仍处于未选中状态，然后单击**保存**。

    ![显示新移动设备邮箱策略的图像。](images/setupdeviceacctexch-06.png)

4.  在创建新的移动设备邮箱策略后，返回到 Exchange 管理中心，随后你将看到列出的新策略。

    ![在 Exchange 管理中心显示新移动设备邮箱策略的图像。](images/setupdeviceacctexch-07.png)

5.  若要在未使用 PowerShell 的情况下应用 ActiveSync 策略，可执行以下操作：

    -   在 EAC 中，依次单击**收件人**&gt;**邮箱**，然后选择邮箱。

        ![显示 Exchange 管理中心的图像。](images/setupdeviceacctexch-08.png)

    -   在**详细信息**窗格中，滚动到**电话和语音功能**，然后单击**查看详细信息**以显示**移动设备详细信息**屏幕。

        ![显示邮箱详细信息的图像。](images/setupdeviceacctexch-09.png)

    -   将显示当前已分配的移动设备邮箱策略。 若要更改移动设备邮箱策略，请单击**浏览**。

        ![显示当前已分配的移动设备邮箱策略的图像。](images/setupdeviceacctexch-10.png)

    -   从列表中选择相应的移动设备邮箱策略，然后依次单击**确定**和**保存**。

        ![显示移动设备邮箱策略列表的图像。](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a>使用 PowerShell 配置帐户

现在你已连接到在线服务，便可完成设备帐户的设置。 将使用设备帐户电子邮件地址执行以下操作：

-   将邮箱类型从常规更改为会议室。
-   更改各种 Exchange 属性
-   将用户帐户密码设置为永不过期。

1.  你将需要输入帐户的邮件地址，并使用该值创建一个变量：

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    若要存储从邮箱中获取的值：

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    通过运行以下内容打印值：

    ``` syntax
    $strEmail
    ```

    你将看到相应的电子邮件地址。

2.  您需要将帐户转换为会议室邮箱，因此请运行：

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  为了使设备帐户能够在 Surface Hub 上进行身份验证，你需要启用会议室邮箱帐户并设置密码，以便该帐户可由设备用于使用 ActiveSync 来获取会议信息并登录到 Skype for Business。

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  可以在设备帐户上设置各种 Exchange 属性以改进会议体验。 可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)部分中查看哪些属性需要设置。

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  现在我们必须在 AD 中设置一些属性。 为此，你需要帐户的别名（这是位于“@”之前的 UPN 的一部分）。

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  用户需要在 AD 中进行启用，然后才能使用 Surface Hub 进行身份验证。 运行：

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  如果你确定密码未过期，也可以使用 PowerShell cmdlet 来设置它。 有关详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a>启用带 Skype for Business 的帐户

启用带 Skype for Business 的设备帐户。

为了启用 Skype for Business，你的环境将需要满足以下先决条件：

-   您需要在 O365 计划中安装 Skype for business Online 独立计划2或更高版本。 该计划需要支持会议功能。
-   如果您需要针对 Surface Hub 的电话服务提供商使用企业语音（PSTN 电话服务），则需要 Skype for Business Online 独立计划3。
-   租户用户必须具有 Exchange 邮箱。
-   Surface Hub 帐户需要 Skype for business Online 独立计划2或 Skype for business Online 独立计划3许可证，但不需要 Exchange Online 许可证。

1.  首先在电脑上创建一个远程 PowerShell 会话。

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. 检索 Surface Hub 帐户注册机构池

如果你不确定在你的环境中要用于 `RegistrarPool` 参数的值，你可以使用此 cmdlet 从现有 Skype for Business 用户获取值：

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```
    
3. 若要为 Skype for Business Server 启用你的 Surface Hub 帐户，请运行此 cmdlet：

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    






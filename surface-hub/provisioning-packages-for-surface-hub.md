---
title: 创建设置包
description: 对于 Windows 10，使用注册表或配置服务提供程序 (CSP) 的设置可通过预配包进行配置。
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: 添加证书, 预配包
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/28/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 087826a7a0cba7a47accc0d3d66714289f2ae9d2
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613939"
---
# <a name="create-provisioning-packages-for-surface-hub"></a><span data-ttu-id="cafb5-104">为用户创建预配Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cafb5-104">Create provisioning packages for Surface Hub</span></span>

<span data-ttu-id="cafb5-105">预配包允许你自动部署关键功能，从而有助于在组织的所有 Surface Hub 中提供一致的体验。</span><span class="sxs-lookup"><span data-stu-id="cafb5-105">Provisioning packages allow you to automate deployment of key features, helping deliver a consistent experience across all Surface Hubs in your organization.</span></span>  <span data-ttu-id="cafb5-106">在Windows电脑上 (WCD) 配置设计器，可以完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="cafb5-106">Using  Windows Configuration Designer (WCD) on a separate PC, you can complete the following tasks:</span></span>

- <span data-ttu-id="cafb5-107">注册 Active Directory 或 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cafb5-107">Enroll in Active Directory or Azure Active Directory</span></span>
- <span data-ttu-id="cafb5-108">创建设备管理员帐户</span><span class="sxs-lookup"><span data-stu-id="cafb5-108">Create a device administrator account</span></span>
- <span data-ttu-id="cafb5-109">添加应用程序和证书</span><span class="sxs-lookup"><span data-stu-id="cafb5-109">Add applications and certificates</span></span>
- <span data-ttu-id="cafb5-110">配置代理设置</span><span class="sxs-lookup"><span data-stu-id="cafb5-110">Configure proxy settings</span></span>
- <span data-ttu-id="cafb5-111">添加 Surface Hub 配置文件</span><span class="sxs-lookup"><span data-stu-id="cafb5-111">Add a Surface Hub configuration file</span></span>
- <span data-ttu-id="cafb5-112">配置 [配置服务提供程序 (CSP) 设置](/windows/client-management/mdm/surfacehub-csp)</span><span class="sxs-lookup"><span data-stu-id="cafb5-112">Configure [Configuration Service Provider (CSP) settings](/windows/client-management/mdm/surfacehub-csp)</span></span>

## <a name="overview"></a><span data-ttu-id="cafb5-113">概述</span><span class="sxs-lookup"><span data-stu-id="cafb5-113">Overview</span></span>

1. <span data-ttu-id="cafb5-114">在运行安装程序的Windows 10，从Windows[安装](https://www.microsoft.com/store/apps/9nblggh4tx22)配置设计器Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="cafb5-114">On a separate PC running Windows 10, install [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) from the Microsoft Store.</span></span>
1. <span data-ttu-id="cafb5-115">选择[**"Surface Hub**](#use-surface-hub-provisioning-wizard)设备"以使用向导配置常见设置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-115">Select [**Provision Surface Hub devices**](#use-surface-hub-provisioning-wizard) to configure common settings using a wizard.</span></span> <span data-ttu-id="cafb5-116">或者， [选择"高级预配](#use-advanced-provisioning) "以查看和配置所有可能的设置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-116">Or select [Advanced provisioning](#use-advanced-provisioning) to view and configure all possible settings.</span></span>
1. <span data-ttu-id="cafb5-117">创建预配包并将其保存到 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="cafb5-117">Create the provisioning package and save it to a USB drive.</span></span>
1. <span data-ttu-id="cafb5-118">在首次运行安装Surface Hub或通过应用将程序包部署到设置程序包。</span><span class="sxs-lookup"><span data-stu-id="cafb5-118">Deploy the package to your Surface Hub during first-run setup, or through the Settings app.</span></span> <span data-ttu-id="cafb5-119">若要了解更多信息，请参阅[为用户创建预配Windows 10。](/windows/configuration/provisioning-packages/provisioning-create-package)</span><span class="sxs-lookup"><span data-stu-id="cafb5-119">To learn more, see [Create a provisioning package for Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package).</span></span>

## <a name="use-surface-hub-provisioning-wizard"></a><span data-ttu-id="cafb5-120">使用Surface Hub预配向导</span><span class="sxs-lookup"><span data-stu-id="cafb5-120">Use Surface Hub provisioning wizard</span></span>

1. <span data-ttu-id="cafb5-121">打开Windows配置设计器"，然后选择 **"Surface Hub设备"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-121">Open Windows Configuration Designer and select **Provision Surface Hub devices**.</span></span><br>
    ![使用 Surface Hub 预配向导](images/sh-prov-start.png)
    
2. <span data-ttu-id="cafb5-123">将项目命名，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-123">Name your project and select **Next**.</span></span>

### <a name="add-certificates"></a><span data-ttu-id="cafb5-124">添加证书</span><span class="sxs-lookup"><span data-stu-id="cafb5-124">Add certificates</span></span>

> [!div class="mx-imgBorder"]
> ![添加证书](images/sh-prov-cert.png)

<span data-ttu-id="cafb5-126">若要使用证书预配设备，请选择"**添加证书"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-126">To provision the device with a certificate, select **Add a certificate**.</span></span> <span data-ttu-id="cafb5-127">输入证书的名称，然后浏览以选择要使用的证书。</span><span class="sxs-lookup"><span data-stu-id="cafb5-127">Enter a name for the certificate, and then browse to select the certificate to be used.</span></span>  <span data-ttu-id="cafb5-128">有关高级预配选项，请参阅下面的将 [证书添加到程序包部分](#add-a-certificate-to-your-package)。</span><span class="sxs-lookup"><span data-stu-id="cafb5-128">For advanced provisioning options, refer to the section below [Add a certificate to your package](#add-a-certificate-to-your-package).</span></span>

### <a name="configure-proxy-settings"></a><span data-ttu-id="cafb5-129">配置代理设置</span><span class="sxs-lookup"><span data-stu-id="cafb5-129">Configure proxy settings</span></span>

> [!div class="mx-imgBorder"]
> ![配置代理设置](images/sh-prov-proxy.png)

1. <span data-ttu-id="cafb5-131">对代理设置切换为**是**或**否**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-131">Toggle **Yes** or **No** for proxy settings.</span></span> <span data-ttu-id="cafb5-132">默认情况下，Surface Hub自动检测代理设置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-132">By default, Surface Hub automatically detects proxy settings.</span></span> <span data-ttu-id="cafb5-133">但是，如果你的基础结构以前需要使用代理服务器，现已更改为不需要代理服务器，你可以使用预配包将你的 Surface Hub 设备恢复为默认设置，方法是依次选择**是**和**自动检测设置**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-133">However, if your infrastructure previously required using a proxy server and has changed to not require a proxy server, you can use a provisioning package to revert your Surface Hub devices to the default settings by selecting **Yes** and **Automatically detect settings**.</span></span>
2. <span data-ttu-id="cafb5-134">如果切换 **"是"，** 可以选择自动检测代理设置，也可以输入以下选项之一手动配置设置：</span><span class="sxs-lookup"><span data-stu-id="cafb5-134">If you toggle **Yes**, you can select to automatically detect proxy settings or manually configure the settings by entering one of the following:</span></span>

    - <span data-ttu-id="cafb5-135">设置脚本的 URL。</span><span class="sxs-lookup"><span data-stu-id="cafb5-135">A URL to a setup script.</span></span>
    - <span data-ttu-id="cafb5-136">静态代理服务器地址和端口信息。</span><span class="sxs-lookup"><span data-stu-id="cafb5-136">A static proxy server address and port information.</span></span>

3. <span data-ttu-id="cafb5-137">如果打算使用安装程序脚本或代理服务器，请关闭"**自动检测设置"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-137">If you intend to use a setup script or proxy server, turn off **Automatically detect settings**.</span></span> <span data-ttu-id="cafb5-138">您可以使用安装程序 *脚本或代理服务器* ，而不是同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="cafb5-138">You can use a setup script *or* a proxy server, not both.</span></span>
4. <span data-ttu-id="cafb5-139">输入例外 (，Surface Hub直接连接到的地址，而无需使用代理服务器) 。</span><span class="sxs-lookup"><span data-stu-id="cafb5-139">Enter exceptions (addresses that Surface Hub should connect to directly without using the proxy server).</span></span> <span data-ttu-id="cafb5-140">**示例：\*.office365.com**</span><span class="sxs-lookup"><span data-stu-id="cafb5-140">**Example:** \*.office365.com</span></span>
5. <span data-ttu-id="cafb5-141">确定是否对本地地址使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="cafb5-141">Identify whether to use the proxy server for local addresses.</span></span>

### <a name="set-up-device-admins"></a><span data-ttu-id="cafb5-142">设置设备管理员</span><span class="sxs-lookup"><span data-stu-id="cafb5-142">Set up device admins</span></span>

 > [!div class="mx-imgBorder"]
 > ![加入 Active Directory、Azure AD 或创建本地管理员帐户](images/sh2-wcd.png)

<span data-ttu-id="cafb5-144">你可以在 Active Directory 中注册设备并指定安全组使用设置应用，在 Azure Active Directory 中注册以允许全局管理员使用设置应用，或在该设备上创建本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="cafb5-144">You can enroll the device in Active Directory and specify a security group to use the Settings app, enroll in Azure Active Directory to allow global admins to use the Settings app, or create a local administrator account on the device.</span></span>

1. <span data-ttu-id="cafb5-145">在 Active Directory 中注册设备，请输入最低特权用户帐户的凭据，以将该设备加入域，并指定安全组在 Surface Hub 上拥有管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="cafb5-145">To enroll the device in Active Directory, enter the credentials for a least-privileged user account to join the device to the domain, and specify the security group to have admin credentials on Surface Hub.</span></span> <span data-ttu-id="cafb5-146">如果将程序包应用于重置Surface Hub，可以使用同一个域帐户，只要它是最初设置该域Surface Hub帐户。</span><span class="sxs-lookup"><span data-stu-id="cafb5-146">If applying the package to a Surface Hub that was reset, you can use the same domain account as long as it's the same account that set up the Surface Hub initially.</span></span> <span data-ttu-id="cafb5-147">否则，必须在预配包中使用不同的域帐户。</span><span class="sxs-lookup"><span data-stu-id="cafb5-147">Otherwise, a different domain account must be used in the provisioning package.</span></span>
2. <span data-ttu-id="cafb5-148">使用配置Windows配置设计器配置批量 Azure AD 注册之前，[请规划 Azure AD 加入实现](/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="cafb5-148">Before you use Windows Configuration Designer to configure bulk Azure AD enrollment, [Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="cafb5-149">Azure AD 租户中的**每个用户的最大设备数**设置用于确定你在该向导中获取的批量令牌可使用的次数。</span><span class="sxs-lookup"><span data-stu-id="cafb5-149">The **maximum number of devices per user** setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span>
3. <span data-ttu-id="cafb5-150">若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。</span><span class="sxs-lookup"><span data-stu-id="cafb5-150">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="cafb5-151">设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。</span><span class="sxs-lookup"><span data-stu-id="cafb5-151">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="cafb5-152">选择 **"获取批量令牌"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-152">Select **Get bulk token**.</span></span> <span data-ttu-id="cafb5-153">在**让我们帮你登录**窗口中，输入有权限将设备加入 Azure AD 的帐户，然后再输入密码。</span><span class="sxs-lookup"><span data-stu-id="cafb5-153">In the **Let's get you signed in** window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="cafb5-154">选择 **"** 接受"Windows为配置设计器授予必要的权限。</span><span class="sxs-lookup"><span data-stu-id="cafb5-154">Select **Accept** to give Windows Configuration Designer the necessary permissions.</span></span>
4. <span data-ttu-id="cafb5-155">若要创建本地管理员帐户，请选择该选项，然后输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="cafb5-155">To create a local administrator account, select that option and enter a user name and password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cafb5-156">如果在预配包中创建本地帐户，则必须每 42 天使用**设置**应用更改密码。</span><span class="sxs-lookup"><span data-stu-id="cafb5-156">If you create a local account in the provisioning package, you must change the password using the **Settings** app every 42 days.</span></span> <span data-ttu-id="cafb5-157">如果在此期限内未更改密码，帐户可能会被锁定而无法登录。</span><span class="sxs-lookup"><span data-stu-id="cafb5-157">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>

### <a name="enroll-in-third-party-mdm-provider"></a><span data-ttu-id="cafb5-158">注册第三方 MDM 提供程序</span><span class="sxs-lookup"><span data-stu-id="cafb5-158">Enroll in third party MDM provider</span></span>

> [!div class="mx-imgBorder"]
> ![注册第三方移动设备管理](images/sh-prov-mdm.png)

<span data-ttu-id="cafb5-160">如果你使用 MDM (第三方移动设备) ，可以使用本部分注册Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="cafb5-160">If you use a third party mobile device management (MDM) provider, you can use this section to enroll Surface Hub.</span></span> <span data-ttu-id="cafb5-161">若要在 Intune 中注册，请首先设置 Azure AD 加入（如上一部分中所述）并按照以下 Intune 文档中的说明操作：为设备设置Windows 10[注册](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="cafb5-161">To enroll in Intune, first setup Azure AD join, as described in the previous section, and follow the instructions in the following Intune documentation: [Set up automatic enrollment for Windows 10 devices](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

1. <span data-ttu-id="cafb5-162">为 **注册** 第 **三** 方 MDM 切换"是"或"否"。</span><span class="sxs-lookup"><span data-stu-id="cafb5-162">Toggle **Yes** or **No** for enrollment in third party MDM.</span></span>
2. <span data-ttu-id="cafb5-163">如果切换 **"是"，** 则提供经授权注册设备并指定身份验证类型的服务帐户和密码或证书指纹。</span><span class="sxs-lookup"><span data-stu-id="cafb5-163">If you toggle **Yes**, provide a service account and password or certificate thumbprint that is authorized to enroll the device and specify the authentication type.</span></span>
3. <span data-ttu-id="cafb5-164">如果 MDM 提供程序要求，请输入发现服务、注册服务和策略服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="cafb5-164">If required by your MDM provider, enter the URLs for the discovery service, enrollment service, and policy service.</span></span>

 <span data-ttu-id="cafb5-165">若要了解更多信息，请参阅[使用 MDM Surface Hub管理应用。](manage-settings-with-mdm-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="cafb5-165">To learn more, see [Manage Surface Hub with an MDM provider.](manage-settings-with-mdm-for-surface-hub.md)</span></span>

### <a name="add-applications"></a><span data-ttu-id="cafb5-166">添加应用程序</span><span class="sxs-lookup"><span data-stu-id="cafb5-166">Add applications</span></span>

> [!div class="mx-imgBorder"]
> ![添加应用程序](images/sh-prov-apps.png)

<span data-ttu-id="cafb5-168">你可以在预配包中安装多个通用 Windows 平台 (UWP) 应用。</span><span class="sxs-lookup"><span data-stu-id="cafb5-168">You can install multiple Universal Windows Platform (UWP) apps in a provisioning package.</span></span> <span data-ttu-id="cafb5-169">若要了解更多信息，请参阅 [使用应用预配电脑](/windows/configuration/provisioning-packages/provision-pcs-with-apps)。</span><span class="sxs-lookup"><span data-stu-id="cafb5-169">To learn more, see [Provision PCs with apps](/windows/configuration/provisioning-packages/provision-pcs-with-apps).</span></span>

> [!NOTE]
> <span data-ttu-id="cafb5-170">尽管Windows设计器允许你将经典 Win32 应用添加到预配包，Surface Hub仅接受 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="cafb5-170">Although Windows Configuration Designer lets you add a Classic Win32 app to a provisioning package, Surface Hub only accepts UWP apps.</span></span> <span data-ttu-id="cafb5-171">如果包括经典 Win32 应用，预配将失败。</span><span class="sxs-lookup"><span data-stu-id="cafb5-171">If you include a Classic Win32 app, provisioning will fail.</span></span>

### <a name="add-a-configuration-file"></a><span data-ttu-id="cafb5-172">添加配置文件</span><span class="sxs-lookup"><span data-stu-id="cafb5-172">Add a configuration file</span></span>

<span data-ttu-id="cafb5-173">除了此预配包之外，您还可以使用 Surface Hub 配置文件，以便更轻松地设置设备。</span><span class="sxs-lookup"><span data-stu-id="cafb5-173">In addition to this provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="cafb5-174">一Surface Hub配置文件包含用于连接到 Exchange、Microsoft Teams 或 Skype for Business 的设备帐户列表，以及用于无线投影的"友好名称"。</span><span class="sxs-lookup"><span data-stu-id="cafb5-174">A Surface Hub configuration file contains a list of device accounts for connecting to Exchange, Microsoft Teams, or Skype for Business, as well as "friendly names" for wireless projection.</span></span>

**<span data-ttu-id="cafb5-175">若要创建Surface Hub配置文件：</span><span class="sxs-lookup"><span data-stu-id="cafb5-175">To create a Surface Hub configuration file:</span></span>**

1. <span data-ttu-id="cafb5-176">打开Microsoft Excel (或其他.csv编辑器) ，创建.csv一个名为 SurfaceHubConfiguration.csv</span><span class="sxs-lookup"><span data-stu-id="cafb5-176">Open Microsoft Excel (or other .csv editor), create a .csv file named SurfaceHubConfiguration.csv</span></span>
2. <span data-ttu-id="cafb5-177">按此格式输入设备帐户和友好名称列表：</span><span class="sxs-lookup"><span data-stu-id="cafb5-177">Enter a list of device accounts and friendly names in this format:</span></span>

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > <span data-ttu-id="cafb5-178">配置文件不得包含列标题。</span><span class="sxs-lookup"><span data-stu-id="cafb5-178">The configuration file must not contain column headers.</span></span> <span data-ttu-id="cafb5-179">当包含在应用于设备的预配包Surface Hub，你可以从文件中选择设备的帐户和友好名称。</span><span class="sxs-lookup"><span data-stu-id="cafb5-179">When included in a provisioning package applied to Surface Hub, you can select the account and friendly name for the device from the file.</span></span> <span data-ttu-id="cafb5-180">若要创建.csv文件，请使用 UPN 地址格式 (rainier@contoso.com) 或下层登录名格式 (contoso\用户) 。</span><span class="sxs-lookup"><span data-stu-id="cafb5-180">To create the .csv file,  use either a UPN address format (rainier@contoso.com) or down-level logon name format (contoso\rainier).</span></span>

- <span data-ttu-id="cafb5-181">rainier@contoso.com，password，一Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cafb5-181">rainier@contoso.com,password,Rainier Surface Hub</span></span>

3. <span data-ttu-id="cafb5-182">将文件保存到项目文件夹，然后使用预配包将其复制到 U 盘。</span><span class="sxs-lookup"><span data-stu-id="cafb5-182">Save the file to your project folder and copy it to the USB key with your provisioning package.</span></span>

> [!NOTE]
> <span data-ttu-id="cafb5-183">配置文件只能在首次运行安装期间应用。</span><span class="sxs-lookup"><span data-stu-id="cafb5-183">The configuration file can only be applied during first run setup.</span></span>

### <a name="password-protect-provisioning-package"></a><span data-ttu-id="cafb5-184">密码保护预配包</span><span class="sxs-lookup"><span data-stu-id="cafb5-184">Password protect provisioning package</span></span>

<span data-ttu-id="cafb5-185">如果选择使用密码，则每次将预配包应用到设备时都需要输入密码。</span><span class="sxs-lookup"><span data-stu-id="cafb5-185">If you choose to use a password,  you will need to enter it each time you apply the provisioning package to a device.</span></span>

### <a name="complete-provisioning-wizard"></a><span data-ttu-id="cafb5-186">完成预配向导</span><span class="sxs-lookup"><span data-stu-id="cafb5-186">Complete provisioning wizard</span></span>

<span data-ttu-id="cafb5-187">如果只需要配置常用设置，请选择完成\*\*\*\*  >  **创建**并跳到生成[程序包部分](#build-your-package)。</span><span class="sxs-lookup"><span data-stu-id="cafb5-187">If you only need to configure common settings, select **Finish** > **Create** and skip to the section [Build your package](#build-your-package).</span></span> <span data-ttu-id="cafb5-188">或者通过切换到高级预配继续配置设置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-188">Or continue configuring settings by switching to Advanced provisioning.</span></span>

## <a name="use-advanced-provisioning"></a><span data-ttu-id="cafb5-189">使用高级预配</span><span class="sxs-lookup"><span data-stu-id="cafb5-189">Use Advanced provisioning</span></span>

> [!TIP]
> <span data-ttu-id="cafb5-190">使用向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-190">Use the wizard to create a package with the common settings, then switch to the advanced editor to add other settings.</span></span><br><br> ![切换到高级编辑器](images/icd-simple-edit.png)

1. <span data-ttu-id="cafb5-192">如果继续上一部分，请选择切换到**高级编辑器**，否则Windows**配置设计器**，然后选择**高级预配**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-192">If continuing from the previous section, select **Switch to advanced editor** otherwise open **Windows Configuration Designer** and select **Advanced provisioning**.</span></span><br>
  ![使用高级预配](images/sh-prov-adv.png)

2. <span data-ttu-id="cafb5-194">将项目命名，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-194">Name your project and select **Next**.</span></span>
3. <span data-ttu-id="cafb5-195">选择 **"常用Windows 10 协同版"，** 选择"下\*\*\*\* 一步"，然后选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-195">Select **Common to Windows 10 Team**, select **Next**, and then select **Finish**.</span></span><br>
     ![WCD 新项目](images/icd-new-project.png)

4. <span data-ttu-id="cafb5-197">在项目中的可用 **自定义项下**，选择 **常用团队设置**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-197">In the project, under **Available customizations**, select **Common Team settings**.</span></span><br>
     ![WCD 通用设置](images/icd-common-settings.png)

### <a name="add-a-certificate-to-your-package"></a><span data-ttu-id="cafb5-199">将证书添加到程序包</span><span class="sxs-lookup"><span data-stu-id="cafb5-199">Add a certificate to your package</span></span>

<span data-ttu-id="cafb5-200">可使用设置包安装支持设备验证 Microsoft Exchange 身份的证书。</span><span class="sxs-lookup"><span data-stu-id="cafb5-200">You can use provisioning packages to install certificates that will allow the device to authenticate to Microsoft Exchange.</span></span>

> [!NOTE]
> <span data-ttu-id="cafb5-201">设置包仅可将证书安装到设备（本地计算机）存储，而非用户存储。</span><span class="sxs-lookup"><span data-stu-id="cafb5-201">Provisioning packages can only install certificates to the device (local machine) store, and not to the user store.</span></span> <span data-ttu-id="cafb5-202">如果组织要求将证书安装到用户存储，请使用 Hub**设置**应用 **：Update & Security**  >  **Certificates**  >  **Import Certificate**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-202">If your organization requires that certificates be installed to the user store, use the Hub **Settings** app: **Update & Security** > **Certificates** > **Import Certificate**.</span></span>
<span data-ttu-id="cafb5-203">或者，可以使用 MDM  [**策略**](manage-settings-with-mdm-for-surface-hub.md) 将证书部署到设备存储或用户存储。</span><span class="sxs-lookup"><span data-stu-id="cafb5-203">Alternatively, you can use  [**MDM policies**](manage-settings-with-mdm-for-surface-hub.md) to deploy certificates to either the device store or the user store.</span></span>

> [!TIP]
> <span data-ttu-id="cafb5-204">**ClientCertificates**部分适用于具有私钥的 .pfx 文件;根 CA 的 .cer 文件应放在**RootCertificates**部分，而中间 CA 应放在**CACertificates**部分中。</span><span class="sxs-lookup"><span data-stu-id="cafb5-204">The **ClientCertificates** section is for .pfx files with a private key; .cer files for root CAs should be placed in the **RootCertificates** section and for Intermediate CAs in the **CACertificates** section.</span></span>

1. <span data-ttu-id="cafb5-205">In **Windows Configuration Designer**Available  >  **customizations，** go to Runtime **settings**  >  **Certificates**  >  **ClientCertificates**.</span><span class="sxs-lookup"><span data-stu-id="cafb5-205">In **Windows Configuration Designer** > **Available customizations** , go to **Runtime settings** > **Certificates** > **ClientCertificates**.</span></span>
2. <span data-ttu-id="cafb5-206">输入**CertificateName 的标签，** 然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-206">Enter a label for **CertificateName** and then select **Add**.</span></span>
3. <span data-ttu-id="cafb5-207">输入 **CertificatePassword**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-207">Enter the **CertificatePassword**.</span></span>
4. <span data-ttu-id="cafb5-208">对于 **CertificatePath**，浏览并选择证书。</span><span class="sxs-lookup"><span data-stu-id="cafb5-208">For **CertificatePath**, browse and select the certificate.</span></span>
5. <span data-ttu-id="cafb5-209">将 **ExportCertificate** 设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-209">Set **ExportCertificate** to **False**.</span></span>
6. <span data-ttu-id="cafb5-210">对于 **KeyLocation**，选择**仅软件**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-210">For **KeyLocation**, select **Software only**.</span></span>

### <a name="add-a-uwp-app-to-your-package"></a><span data-ttu-id="cafb5-211">将 UWP 应用添加到程序包</span><span class="sxs-lookup"><span data-stu-id="cafb5-211">Add a UWP app to your package</span></span>

<span data-ttu-id="cafb5-212">若要将 UWP 应用添加到预配包，你将需要应用包 (.appx 或 .appxbundle) 和任何依赖文件。</span><span class="sxs-lookup"><span data-stu-id="cafb5-212">To add a UWP app to a provisioning package, you will need the app package (.appx or .appxbundle files) and any dependency files.</span></span> <span data-ttu-id="cafb5-213">如果已从适用于企业的 Microsoft Store 获取了该应用，还需要*已解码的*应用许可。</span><span class="sxs-lookup"><span data-stu-id="cafb5-213">If you acquired the app from the Microsoft Store for Business, you will also need the *unencoded* app license.</span></span> <span data-ttu-id="cafb5-214">请参阅[分配脱机应用](/microsoft-store/distribute-offline-apps)，了解如何从适用于企业的 Microsoft Store 下载这些项目。</span><span class="sxs-lookup"><span data-stu-id="cafb5-214">See [Distribute offline apps](/microsoft-store/distribute-offline-apps) to learn how to download these items from the Microsoft Store for Business.</span></span>

**<span data-ttu-id="cafb5-215">若要添加 UWP 应用：</span><span class="sxs-lookup"><span data-stu-id="cafb5-215">To add a UWP app:</span></span>**

1. <span data-ttu-id="cafb5-216">在**可用自定义项**窗格中，转到**运行时设置** > **UniversalAppInstall** > **DeviceContextApp**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-216">In the **Available customizations** pane, go to **Runtime settings** > **UniversalAppInstall** > **DeviceContextApp**.</span></span>
2. <span data-ttu-id="cafb5-217">输入应用的**PackageFamilyName，\*\*\*\*然后选择添加**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-217">Enter a **PackageFamilyName** for the app and then select **Add**.</span></span> <span data-ttu-id="cafb5-218">为了保持一致性，请使用应用的程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="cafb5-218">For consistency, use the app's package family name.</span></span> <span data-ttu-id="cafb5-219">如果已从适用于企业的 Microsoft Store 获取了该应用，可在应用许可中查找程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="cafb5-219">If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license.</span></span> <span data-ttu-id="cafb5-220">使用文本编辑器打开许可证文件，并使用 PFM 标记之间的值。</span><span class="sxs-lookup"><span data-stu-id="cafb5-220">Open the license file using a text editor, and use the value between the PFM tags.</span></span>
3. <span data-ttu-id="cafb5-221">对于**ApplicationFile，\*\*\*\*选择"** 浏览"以查找并选择目标应用 ( .appx 或 .appxbundle) 。</span><span class="sxs-lookup"><span data-stu-id="cafb5-221">For **ApplicationFile**, select **Browse** to find and select the target app ( .appx or .appxbundle).</span></span>
4. <span data-ttu-id="cafb5-222">对于 **DependencyAppxFiles，** 选择 **"** 浏览"查找并添加应用的任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="cafb5-222">For **DependencyAppxFiles**, select **Browse** to find and add any dependencies for the app.</span></span> <span data-ttu-id="cafb5-223">对于 Surface Hub，仅需要 x64 版本的依赖项。</span><span class="sxs-lookup"><span data-stu-id="cafb5-223">For Surface Hub, you will only need the x64 versions of these dependencies.</span></span>

<span data-ttu-id="cafb5-224">如果你从应用包适用于企业的 Microsoft Store，则需要将应用许可证添加到预配包。</span><span class="sxs-lookup"><span data-stu-id="cafb5-224">If you acquired the app from the Microsoft Store for Business, you will need to add the app license to your provisioning package.</span></span>

**<span data-ttu-id="cafb5-225">添加应用程序许可证：</span><span class="sxs-lookup"><span data-stu-id="cafb5-225">To add app license:</span></span>**

1. <span data-ttu-id="cafb5-226">制作应用许可的副本，并为其重命名，以使用 **.ms-windows-store-license** 扩展名。</span><span class="sxs-lookup"><span data-stu-id="cafb5-226">Make a copy of the app license, and rename it to use a **.ms-windows-store-license** extension.</span></span> <span data-ttu-id="cafb5-227">例如，将"example.xml"重命名为"example.ms-windows-store-license"。</span><span class="sxs-lookup"><span data-stu-id="cafb5-227">For example, rename "example.xml" to "example.ms-windows-store-license".</span></span>
2. <span data-ttu-id="cafb5-228">In Windows Configuration Designer， go to **Available customizations**  >  **Runtime settings**  >  **UniversalAppInstall**  >  **DeviceContextAppLicense**.</span><span class="sxs-lookup"><span data-stu-id="cafb5-228">In Windows Configuration Designer, go to **Available customizations** > **Runtime settings** > **UniversalAppInstall** > **DeviceContextAppLicense**.</span></span>
3. <span data-ttu-id="cafb5-229">输入**LicenseProductId，** 然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-229">Enter a **LicenseProductId** and then select **Add**.</span></span> <span data-ttu-id="cafb5-230">为了保持一致性，请使用应用许可中的应用许可 ID。</span><span class="sxs-lookup"><span data-stu-id="cafb5-230">For consistency, use the app's license ID from the app license.</span></span> <span data-ttu-id="cafb5-231">使用文本编辑器打开许可文件。</span><span class="sxs-lookup"><span data-stu-id="cafb5-231">Open the license file using a text editor.</span></span> <span data-ttu-id="cafb5-232">然后，在 **License** 标记中，使用 **LicenseID 属性中的** 值。</span><span class="sxs-lookup"><span data-stu-id="cafb5-232">Then, in the **License** tag, use the value in the **LicenseID** attribute.</span></span>
4. <span data-ttu-id="cafb5-233">选择新的 **LicenseProductId** 节点。</span><span class="sxs-lookup"><span data-stu-id="cafb5-233">Select the new **LicenseProductId** node.</span></span> <span data-ttu-id="cafb5-234">对于**LicenseInstall，** 选择"浏览"以查找并选择重命名的许可证文件 (example.ms-windows-store-license) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cafb5-234">For **LicenseInstall**, select **Browse** to find and select your renamed license file (example.ms-windows-store-license).</span></span>

### <a name="add-a-policy-to-your-package"></a><span data-ttu-id="cafb5-235">将策略添加到程序包</span><span class="sxs-lookup"><span data-stu-id="cafb5-235">Add a policy to your package</span></span>

<span data-ttu-id="cafb5-236">Surface Hub 支持[策略配置服务提供程序](/windows/client-management/mdm/policy-configuration-service-provider)中的策略子集。</span><span class="sxs-lookup"><span data-stu-id="cafb5-236">Surface Hub supports a subset of the policies in the [Policy configuration service provider](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="cafb5-237">其中一些策略可以使用配置设计器Windows配置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-237">Some of those policies can be configured with Windows Configuration Designer.</span></span>

 **<span data-ttu-id="cafb5-238">添加 [云解决方案提供商策略](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)：</span><span class="sxs-lookup"><span data-stu-id="cafb5-238">To add [CSP policies](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub):</span></span>**

1. <span data-ttu-id="cafb5-239">转到可用**自定义运行时**  >  **设置**  >  **策略**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-239">Go to  **Available customizations** > **Runtime settings** > **Policies**.</span></span>
2. <span data-ttu-id="cafb5-240">选择想要管理和配置相应策略设置的组件。</span><span class="sxs-lookup"><span data-stu-id="cafb5-240">Select the component you want to manage and configure the policy setting as appropriate.</span></span> <span data-ttu-id="cafb5-241">例如，若要阻止员工使用 InPrivate 网站浏览Surface Hub **AllowInPrivate，** 然后选择"禁用 **"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-241">For example, to prevent employees from using InPrivate website browsing on Surface Hub, select **AllowInPrivate** and then select **Disable**.</span></span>  

    > [!div class="mx-imgBorder"]
    > ![配置策略设置](images/sh-prov-policies.png)

### <a name="add-surface-hub-settings-to-your-package"></a><span data-ttu-id="cafb5-243">将 Surface Hub 设置添加到程序包</span><span class="sxs-lookup"><span data-stu-id="cafb5-243">Add Surface Hub settings to your package</span></span>

<span data-ttu-id="cafb5-244">可将 [SurfaceHub 配置服务提供程序](/windows/client-management/mdm/surfacehub-csp)中的设置添加到设置包。</span><span class="sxs-lookup"><span data-stu-id="cafb5-244">You can add settings from the [SurfaceHub configuration service provider](/windows/client-management/mdm/surfacehub-csp) to your provisioning package.</span></span>

1. <span data-ttu-id="cafb5-245">转到可用**自定义项**  >  **Common Team Edition 设置**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-245">Go to **Available customizations** > **Common Team Edition Settings**.</span></span>
1. <span data-ttu-id="cafb5-246">选择想要管理和配置相应策略设置的组件。</span><span class="sxs-lookup"><span data-stu-id="cafb5-246">Select the component you want to manage and configure the policy setting as appropriate.</span></span>
1. <span data-ttu-id="cafb5-247">配置完预配包后，请选择 **"文件保存**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-247">When you are done configuring the provisioning package, select  **File** > **Save**.</span></span>
1. <span data-ttu-id="cafb5-248">阅读项目文件可能包含敏感信息的警告，然后选择"确定 **"**</span><span class="sxs-lookup"><span data-stu-id="cafb5-248">Read the warning that project files may contain sensitive information, and select **OK**</span></span>

### <a name="build-your-package"></a><span data-ttu-id="cafb5-249">生成程序包</span><span class="sxs-lookup"><span data-stu-id="cafb5-249">Build your package</span></span>

<span data-ttu-id="cafb5-250">生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="cafb5-250">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="cafb5-251">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="cafb5-251">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span>  <span data-ttu-id="cafb5-252">将项目文件存储在安全位置，或删除（如果不再需要）。</span><span class="sxs-lookup"><span data-stu-id="cafb5-252">Store the project files in a secure location or delete if no longer needed.</span></span>

1. <span data-ttu-id="cafb5-253">打开**Windows设计器**  >  **导出**  >  **预配包。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-253">Open **Windows Configuration Designer** > **Export** > **Provisioning package**.</span></span>
2. <span data-ttu-id="cafb5-254">将**所有者\*\*\*\*更改为 IT 管理员**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-254">Change **Owner** to **IT Admin**.</span></span>  
3. <span data-ttu-id="cafb5-255">设置**程序包版本**的值，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-255">Set a value for **Package Version**, and then select **Next.**</span></span>

> [!TIP]
> <span data-ttu-id="cafb5-256">将所有者设置为 IT 管理员可确保包设置保留适当的"优先属性"，并保留在 Surface Hub如果随后从其他源应用了其他预配包。</span><span class="sxs-lookup"><span data-stu-id="cafb5-256">Setting the owner to IT Admin ensures that package settings maintain the appropriate "precedence properties" and remain in effect on Surface Hub if other provisioning packages are subsequently applied from other sources.</span></span>

> [!TIP]
> <span data-ttu-id="cafb5-257">你可以修改现有程序包，并更改版本号以更新以前应用的程序包。</span><span class="sxs-lookup"><span data-stu-id="cafb5-257">You can modify existing packages and change the version number to update previously applied packages.</span></span>

4. <span data-ttu-id="cafb5-258">可选：你可以选择加密程序包并启用程序包签名：</span><span class="sxs-lookup"><span data-stu-id="cafb5-258">Optional: You can choose to encrypt the package and enable package signing:</span></span>

    1. <span data-ttu-id="cafb5-259">选择 **"加密** 程序包"，然后输入密码。</span><span class="sxs-lookup"><span data-stu-id="cafb5-259">Select **Encrypt package** and then enter a password.</span></span>
    1. <span data-ttu-id="cafb5-260">选择 **"对程序包**  >  **签名""** 浏览"，然后选择相应的证书。</span><span class="sxs-lookup"><span data-stu-id="cafb5-260">Select **Sign package** > **Browse** and choose the certificate as appropriate.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cafb5-261">建议将受信任的预配证书包括在预配包中。</span><span class="sxs-lookup"><span data-stu-id="cafb5-261">Including a trusted provisioning certificate in your provisioning package is recommended.</span></span> <span data-ttu-id="cafb5-262">将程序包应用于设备时，证书将添加到系统存储，从而允许以静默方式应用后续程序包。</span><span class="sxs-lookup"><span data-stu-id="cafb5-262">When the package is applied to a device, the certificate is added to the system store, enabling subsequent packages to be applied silently.</span></span>

5. <span data-ttu-id="cafb5-263">选择 **"下** 一步"以指定输出位置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-263">Select **Next** to specify the output location.</span></span> <span data-ttu-id="cafb5-264">默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-264">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="cafb5-265">或者， **选择** "浏览"更改默认输出位置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-265">Or select **Browse** to change the default output location.</span></span> <span data-ttu-id="cafb5-266">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="cafb5-266">Select **Next**.</span></span>
6. <span data-ttu-id="cafb5-267">选择 **"生成** "开始生成程序包。</span><span class="sxs-lookup"><span data-stu-id="cafb5-267">Select **Build** to start building the package.</span></span> <span data-ttu-id="cafb5-268">项目信息显示在生成页面中。</span><span class="sxs-lookup"><span data-stu-id="cafb5-268">The project information is displayed in the build page.</span></span>
7. <span data-ttu-id="cafb5-269">如果生成失败，将显示一条错误消息，并包含指向项目文件夹的链接。</span><span class="sxs-lookup"><span data-stu-id="cafb5-269">If your build fails, an error message appears with a link to the project folder.</span></span> <span data-ttu-id="cafb5-270">查看日志以诊断错误，然后再次尝试生成程序包。</span><span class="sxs-lookup"><span data-stu-id="cafb5-270">Review the logs to diagnose the error and try building the package again.</span></span>
8. <span data-ttu-id="cafb5-271">如果生成成功，将显示预配包的名称、输出目录和项目目录。</span><span class="sxs-lookup"><span data-stu-id="cafb5-271">If your build succeeds, the name of the provisioning package, output directory, and project directory are displayed.</span></span> <span data-ttu-id="cafb5-272">选择 **"** 完成"关闭向导并返回到"自定义"页。</span><span class="sxs-lookup"><span data-stu-id="cafb5-272">Select **Finish** to close the wizard and go back to the Customizations page.</span></span>
9. <span data-ttu-id="cafb5-273">选择  **输出**  位置以转到程序包的位置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-273">Select  **output location**  to go to the location of the package.</span></span> <span data-ttu-id="cafb5-274">将 .ppkg 复制到空 U 盘。</span><span class="sxs-lookup"><span data-stu-id="cafb5-274">Copy the .ppkg to an empty USB flash drive.</span></span>

## <a name="apply-a-provisioning-package-to-surface-hub"></a><span data-ttu-id="cafb5-275">将设置包应用到 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cafb5-275">Apply a provisioning package to Surface Hub</span></span>

<span data-ttu-id="cafb5-276">有两个选项可将设置包部署到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="cafb5-276">There are two options for deploying provisioning packages to a Surface Hub.</span></span> <span data-ttu-id="cafb5-277">[在第一次](#apply-a-provisioning-package-during-first-run)运行向导期间，你可以应用安装证书的预配包，或在首次运行计划完成后，可以使用 设置 应用配置设置、[应用和证书的预配包](#apply-a-provisioning-package-using-settings-app)。</span><span class="sxs-lookup"><span data-stu-id="cafb5-277">[During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-provisioning-package-using-settings-app).</span></span>

### <a name="apply-a-provisioning-package-during-first-run"></a><span data-ttu-id="cafb5-278">在首次运行时应用设置包</span><span class="sxs-lookup"><span data-stu-id="cafb5-278">Apply a provisioning package during first run</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cafb5-279">在首次运行计划期间，只能使用预配包安装证书。</span><span class="sxs-lookup"><span data-stu-id="cafb5-279">During the first-run program, you can only use provisioning packages to install certificates.</span></span> <span data-ttu-id="cafb5-280">使用**设置**应用安装应用和应用其他设置。</span><span class="sxs-lookup"><span data-stu-id="cafb5-280">Use the **Settings** app to install apps and apply other settings.</span></span>

1. <span data-ttu-id="cafb5-281">当你首次打开Surface Hub时，首次运行程序将显示"[**你好"页面**](first-run-program-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="cafb5-281">When you turn on the Surface Hub for the first time, the first-run program displays the [**Hi there page**](first-run-program-surface-hub.md).</span></span> <span data-ttu-id="cafb5-282">确保设置已正确配置，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="cafb5-282">Make sure that the settings are properly configured before proceeding.</span></span>
2. <span data-ttu-id="cafb5-283">将包含 .ppkg 文件的 U 盘插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="cafb5-283">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span> <span data-ttu-id="cafb5-284">如果程序包位于驱动器的根目录中，首次运行程序将识别它，并询问是否要设置设备。</span><span class="sxs-lookup"><span data-stu-id="cafb5-284">If the package is in the root directory of the drive, the first-run program will recognize it and ask if you want to set up the device.</span></span> <span data-ttu-id="cafb5-285">选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-285">Select **Set up**.</span></span>
3. <span data-ttu-id="cafb5-286">下一个屏幕会要求你选择预配源。</span><span class="sxs-lookup"><span data-stu-id="cafb5-286">The next screen asks you to select a provisioning source.</span></span> <span data-ttu-id="cafb5-287">选择“可移动媒体”\*\*\*\*，然后点击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cafb5-287">Select **Removable Media** and tap **Next**.</span></span>
4. <span data-ttu-id="cafb5-288">选择要应用 (*.ppkg) 设置包，然后点击"下一\*\*步"。*\*</span><span class="sxs-lookup"><span data-stu-id="cafb5-288">Select the provisioning package (\*.ppkg) that you want to apply, and tap **Next**.</span></span> <span data-ttu-id="cafb5-289">注意，首次运行期间只能安装一个程序包。</span><span class="sxs-lookup"><span data-stu-id="cafb5-289">Note that you can only install one package during first run.</span></span>
5. <span data-ttu-id="cafb5-290">首次运行程序将显示预配包要应用的更改汇总。</span><span class="sxs-lookup"><span data-stu-id="cafb5-290">The first-run program will show you a summary of the changes that the provisioning package will apply.</span></span> <span data-ttu-id="cafb5-291">选择**是的，添加它**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-291">Select **Yes, add it**.</span></span>
6. <span data-ttu-id="cafb5-292">如果配置文件包含在 U 盘的根目录中，你将看到**选择配置**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-292">If a configuration file is included in the root directory of the USB flash drive, you will see **Select a configuration**.</span></span> <span data-ttu-id="cafb5-293">将显示配置文件中的第一个设备帐户以及将应用到 Surface Hub 的帐户信息摘要。</span><span class="sxs-lookup"><span data-stu-id="cafb5-293">The first device account in the configuration file will be shown with a summary of the account information that will be applied to the Surface Hub.</span></span>
7. <span data-ttu-id="cafb5-294">在 **"选择配置"** 中，选择要应用的设备名称，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="cafb5-294">In **Select a configuration**, select the device name to apply, and then select **Next**.</span></span>

<span data-ttu-id="cafb5-295">预配包中的设置将应用于设备，并将完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="cafb5-295">The settings from the provisioning package will be applied to the device and OOBE will be complete.</span></span> <span data-ttu-id="cafb5-296">设备重启后，你可以删除 U 盘。</span><span class="sxs-lookup"><span data-stu-id="cafb5-296">After the device restarts, you can remove the USB flash drive.</span></span>

### <a name="apply-a-provisioning-package-using-settings-app"></a><span data-ttu-id="cafb5-297">使用应用应用设置包</span><span class="sxs-lookup"><span data-stu-id="cafb5-297">Apply a provisioning package using Settings app</span></span>

1. <span data-ttu-id="cafb5-298">将包含 .ppkg 文件的 U 盘插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="cafb5-298">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span>
2. <span data-ttu-id="cafb5-299">从Surface Hub**开始设置系统**提示时输入管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="cafb5-299">From Surface Hub, start **Settings** and enter the admin credentials when prompted.</span></span>
3. <span data-ttu-id="cafb5-300">导航到 **Surface Hub** > **设备管理**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-300">Navigate to **Surface Hub** > **Device management**.</span></span> <span data-ttu-id="cafb5-301">在**预配包下**，选择**添加或删除预配包**  >  **添加包**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-301">Under **Provisioning packages**, select **Add or remove a provisioning package** > **Add a package**.</span></span>
4. <span data-ttu-id="cafb5-302">选择设置包，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-302">Choose your provisioning package and select **Add**.</span></span>  <span data-ttu-id="cafb5-303">如果系统提示，请再次输入管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="cafb5-303">If prompted, enter your admin credentials again.</span></span>
5. <span data-ttu-id="cafb5-304">你将看到要应用的更改的摘要。</span><span class="sxs-lookup"><span data-stu-id="cafb5-304">You'll see a summary of the changes to be applied.</span></span> <span data-ttu-id="cafb5-305">选择**是的，添加它**。</span><span class="sxs-lookup"><span data-stu-id="cafb5-305">Select **Yes, add it**.</span></span>

## <a name="learn-more"></a><span data-ttu-id="cafb5-306">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="cafb5-306">Learn more</span></span>

- [<span data-ttu-id="cafb5-307">下载Windows配置设计器</span><span class="sxs-lookup"><span data-stu-id="cafb5-307">Download Windows Configuration Designer</span></span>](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [<span data-ttu-id="cafb5-308">为 Windows 10 创建预配包</span><span class="sxs-lookup"><span data-stu-id="cafb5-308">Create a provisioning package for Windows 10</span></span>](/windows/configuration/provisioning-packages/provisioning-create-package)
- [<span data-ttu-id="cafb5-309">通过 MDM 提供商管理 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cafb5-309">Manage Surface Hub with an MDM provider</span></span>](manage-settings-with-mdm-for-surface-hub.md)

---
title: 创建预配包 (Surface Hub)
description: 对于 Windows 10，使用注册表或配置服务提供程序 (CSP) 的设置可通过预配包进行配置。
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: 添加证书, 预配包
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: 9158bec3d2285e5e8d4f9f56e582ff2320a34024
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934872"
---
# <span data-ttu-id="11a27-104">创建预配包 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="11a27-104">Create provisioning packages (Surface Hub)</span></span>

<span data-ttu-id="11a27-105">本主题介绍了如何使用 Windows 配置设计器创建预配包，并将其应用到 Surface Hub 设备。</span><span class="sxs-lookup"><span data-stu-id="11a27-105">This topic explains how to create a provisioning package using the Windows Configuration Designer, and apply it to Surface Hub devices.</span></span> <span data-ttu-id="11a27-106">对于 Surface Hub，可使用预配包添加证书、安装通用 Windows 平台 (UWP) 应用以及自定义策略和设置。</span><span class="sxs-lookup"><span data-stu-id="11a27-106">For Surface Hub, you can use provisioning packages to add certificates, install Universal Windows Platform (UWP) apps, and customize policies and settings.</span></span>

<span data-ttu-id="11a27-107">在首次运行设置时，可使用 U 盘或通过**设置**应用来应用预配包。</span><span class="sxs-lookup"><span data-stu-id="11a27-107">You can apply a provisioning package using a USB stick during first-run setup, or through the **Settings** app.</span></span> 


## <span data-ttu-id="11a27-108">优点</span><span class="sxs-lookup"><span data-stu-id="11a27-108">Advantages</span></span>
-   <span data-ttu-id="11a27-109">使用移动设备管理 (MDM) 提供程序快速配置设备。</span><span class="sxs-lookup"><span data-stu-id="11a27-109">Quickly configure devices without using a mobile device management (MDM) provider.</span></span>

-   <span data-ttu-id="11a27-110">无需网络连接。</span><span class="sxs-lookup"><span data-stu-id="11a27-110">No network connectivity required.</span></span>

-   <span data-ttu-id="11a27-111">易于应用。</span><span class="sxs-lookup"><span data-stu-id="11a27-111">Simple to apply.</span></span>

[<span data-ttu-id="11a27-112">了解有关设置包的优势和用法的详细信息。</span><span class="sxs-lookup"><span data-stu-id="11a27-112">Learn more about the benefits and uses of provisioning packages.</span></span>](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## <span data-ttu-id="11a27-113">要求</span><span class="sxs-lookup"><span data-stu-id="11a27-113">Requirements</span></span> 

<span data-ttu-id="11a27-114">若要创建预配包并将其应用到 Surface Hub，需要以下工具：</span><span class="sxs-lookup"><span data-stu-id="11a27-114">To create and apply a provisioning package to a Surface Hub, you'll need the following:</span></span>

-   <span data-ttu-id="11a27-115">Windows 配置设计器，可从 Microsoft Store 或 Windows 10 评估和部署工具包 (ADK) 中安装此设计器。</span><span class="sxs-lookup"><span data-stu-id="11a27-115">Windows Configuration Designer, which can be installed from Microsoft Store or from the Windows 10 Assessment and Deployment Kit (ADK).</span></span> [<span data-ttu-id="11a27-116">了解如何安装 Windows 配置设计器。</span><span class="sxs-lookup"><span data-stu-id="11a27-116">Learn how to install Windows Configuration Designer.</span></span>](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   <span data-ttu-id="11a27-117">U 盘。</span><span class="sxs-lookup"><span data-stu-id="11a27-117">A USB stick.</span></span>
-   <span data-ttu-id="11a27-118">如果使用**设置**应用来应用程序包，需要设备管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="11a27-118">If you apply the package using the **Settings** app, you'll need device admin credentials.</span></span>

<span data-ttu-id="11a27-119">需要在运行 Windows 10 的电脑上创建预配包、将程序包保存到 U 盘，然后将其部署到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="11a27-119">You create the provisioning package on a PC running Windows 10, save the package to a USB drive, and then deploy it to your Surface Hub.</span></span>


## <span data-ttu-id="11a27-120">Surface Hub 预配包的受支持项目</span><span class="sxs-lookup"><span data-stu-id="11a27-120">Supported items for Surface Hub provisioning packages</span></span>

<span data-ttu-id="11a27-121">使用**预配 Surface Hub 设备**向导，你可以：</span><span class="sxs-lookup"><span data-stu-id="11a27-121">Using the **Provision Surface Hub devices** wizard, you can:</span></span>

- <span data-ttu-id="11a27-122">在 Active Directory、Azure Active Directory 或 MDM 中注册</span><span class="sxs-lookup"><span data-stu-id="11a27-122">Enroll in Active Directory, Azure Active Directory, or MDM</span></span> 
- <span data-ttu-id="11a27-123">创建设备管理员帐户</span><span class="sxs-lookup"><span data-stu-id="11a27-123">Create an device administrator account</span></span> 
- <span data-ttu-id="11a27-124">添加应用程序和证书</span><span class="sxs-lookup"><span data-stu-id="11a27-124">Add applications and certificates</span></span>
- <span data-ttu-id="11a27-125">配置代理设置</span><span class="sxs-lookup"><span data-stu-id="11a27-125">Configure proxy settings</span></span>
- <span data-ttu-id="11a27-126">添加 Surface Hub 配置文件</span><span class="sxs-lookup"><span data-stu-id="11a27-126">Add a Surface Hub configuration file</span></span>

>[!WARNING]
><span data-ttu-id="11a27-127">你必须在 Windows 10 上运行 Windows 配置设计器，才能使用该向导配置 Azure Active Directory 注册。</span><span class="sxs-lookup"><span data-stu-id="11a27-127">You must run Windows Configuration Designer on Windows 10 to configure Azure Active Directory enrollment using the wizard.</span></span>

<span data-ttu-id="11a27-128">使用高级预配编辑器，你可以将这些项目添加到 Surface Hub 预配包：</span><span class="sxs-lookup"><span data-stu-id="11a27-128">Using the advanced provisioning editor, you can add these items to provisioning packages for Surface Hub:</span></span>

- <span data-ttu-id="11a27-129">**策略** - Surface Hub 支持[策略配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies)中的策略子集。</span><span class="sxs-lookup"><span data-stu-id="11a27-129">**Policies** - Surface Hub supports a subset of the policies in the [Policy configuration service provider](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies).</span></span> 
- <span data-ttu-id="11a27-130">**设置** - 可在 [SurfaceHub 配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)中配置任意设置。</span><span class="sxs-lookup"><span data-stu-id="11a27-130">**Settings** - You can configure any setting in the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx).</span></span>

>[!TIP]
> <span data-ttu-id="11a27-131">使用向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置。</span><span class="sxs-lookup"><span data-stu-id="11a27-131">Use the wizard to create a package with the common settings, then switch to the advanced editor to add other settings.</span></span>
>
>![打开高级编辑器](images/icd-simple-edit.png)

## <span data-ttu-id="11a27-133">使用 Surface Hub 预配向导</span><span class="sxs-lookup"><span data-stu-id="11a27-133">Use the Surface Hub provisioning wizard</span></span>

<span data-ttu-id="11a27-134">[安装 Windows 配置设计器](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)后，你可以创建预配包。</span><span class="sxs-lookup"><span data-stu-id="11a27-134">After you [install Windows Configuration Designer](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), you can create a provisioning package.</span></span>

### <span data-ttu-id="11a27-135">创建预配包</span><span class="sxs-lookup"><span data-stu-id="11a27-135">Create the provisioning package</span></span> 

1. <span data-ttu-id="11a27-136">打开 Windows 配置设计器：</span><span class="sxs-lookup"><span data-stu-id="11a27-136">Open Windows Configuration Designer:</span></span>
   - <span data-ttu-id="11a27-137">在“开始”屏幕或“开始”菜单搜索中，键入“Windows 配置设计器”，然后单击 Windows 配置设计器快捷方式，</span><span class="sxs-lookup"><span data-stu-id="11a27-137">From either the Start screen or Start menu search, type 'Windows Configuration Designer' and click on the Windows Configuration Designer shortcut,</span></span> 
    
     <span data-ttu-id="11a27-138">或</span><span class="sxs-lookup"><span data-stu-id="11a27-138">or</span></span>
    
   - <span data-ttu-id="11a27-139">如果 Windows 配置设计器是从 ADK 安装的，请导航到 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86`（在 x64 计算机上）或 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe`（在 x86 计算机上），然后双击 **ICD.exe**。</span><span class="sxs-lookup"><span data-stu-id="11a27-139">If you installed Windows Configuration Designer from the ADK, navigate to `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (on an x64 computer) or `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (on an x86 computer), and then double-click **ICD.exe**.</span></span>

2. <span data-ttu-id="11a27-140">单击**预配 Surface Hub 设备**。</span><span class="sxs-lookup"><span data-stu-id="11a27-140">Click **Provision Surface Hub devices**.</span></span>

3. <span data-ttu-id="11a27-141">为你的项目命名，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="11a27-141">Name your project and click **Next**.</span></span>

### <span data-ttu-id="11a27-142">配置设置</span><span class="sxs-lookup"><span data-stu-id="11a27-142">Configure settings</span></span>

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br><span data-ttu-id="11a27-143">若要使用证书预配设备，请单击<strong>添加证书</strong>。</span><span class="sxs-lookup"><span data-stu-id="11a27-143">To provision the device with a certificate, click <strong>Add a certificate</strong>.</span></span> <span data-ttu-id="11a27-144">输入证书的名称，然后浏览到要使用的证书并将其选中。</span><span class="sxs-lookup"><span data-stu-id="11a27-144">Enter a name for the certificate, and then browse to and select the certificate to be used.</span></span></td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br><span data-ttu-id="11a27-145">对代理设置切换为<strong>是</strong>或<strong>否</strong>。</span><span class="sxs-lookup"><span data-stu-id="11a27-145">Toggle <strong>Yes</strong> or <strong>No</strong> for proxy settings.</span></span> <span data-ttu-id="11a27-146">Surface Hub 的默认配置为自动检测代理设置，以便如果是你想要的设置，你可以选择<strong>否</strong>。</span><span class="sxs-lookup"><span data-stu-id="11a27-146">The default configuration for Surface Hub is to automatically detect proxy settings, so you can select <strong>No</strong> if that is the setting that you want.</span></span> <span data-ttu-id="11a27-147">但是，如果你的基础结构以前需要使用代理服务器，现已更改为不需要代理服务器，你可以使用预配包将你的 Surface Hub 设备恢复为默认设置，方法是依次选择<strong>是</strong>和<strong>自动检测设置</strong>。</span><span class="sxs-lookup"><span data-stu-id="11a27-147">However, if your infrastructure previously required using a proxy server and has changed to not require a proxy server, you can use a provisioning package to revert your Surface Hub devices to the default settings by selecting <strong>Yes</strong> and <strong>Automatically detect settings</strong>.</span></span> </br></br><span data-ttu-id="11a27-148">如果切换为<strong>是</strong>，则可以选择自动检测代理设置，或者可以通过在设置脚本或静态代理服务器地址中输入 URL 手动配置设置。</span><span class="sxs-lookup"><span data-stu-id="11a27-148">If you toggle <strong>Yes</strong>, you can select to automatically detect proxy settings, or you can manually configure the settings by entering a URL to a setup script, or a static proxy server address.</span></span> <span data-ttu-id="11a27-149">你还可以确定是否要使用代理服务器作为本地地址，并输入例外（Surface Hub 无需使用代理服务器直接连接到的地址）。</span><span class="sxs-lookup"><span data-stu-id="11a27-149">You can also identify whether to use the proxy server for local addresses, and enter exceptions (addresses that Surface Hub should connect to directly without using the proxy server).</span></span>  </td><td><img src="images/proxy-details.png" alt="configure proxy settings"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br><span data-ttu-id="11a27-150">你可以在 Active Directory 中注册设备并指定安全组使用设置应用，在 Azure Active Directory 中注册以允许全局管理员使用设置应用，或在该设备上创建本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="11a27-150">You can enroll the device in Active Directory and specify a security group to use the Settings app, enroll in Azure Active Directory to allow global admins to use the Settings app, or create a local administrator account on the device.</span></span></br></br><span data-ttu-id="11a27-151">在 Active Directory 中注册设备，请输入最低特权用户帐户的凭据，以将该设备加入域，并指定安全组在 Surface Hub 上拥有管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="11a27-151">To enroll the device in Active Directory, enter the credentials for a least-privileged user account to join the device to the domain, and specify the security group to have admin credentials on Surface Hub.</span></span> <span data-ttu-id="11a27-152">如果在 Active Directory 中注册设备的预配包将应用于重置的 Surface Hub，则仅当列出的帐户是域管理员或者是最初设置 Surface Hub 的同一帐户时，才能使用同一域帐户。</span><span class="sxs-lookup"><span data-stu-id="11a27-152">If a provisioning package that enrolls a device in Active Directory is going to be applied to a Surface Hub that was reset, the same domain account can only be used if the account listed is a domain administrator or is the same account that set up the Surface Hub initially.</span></span> <span data-ttu-id="11a27-153">否则，必须在预配包中使用不同的域帐户。</span><span class="sxs-lookup"><span data-stu-id="11a27-153">Otherwise, a different domain account must be used in the provisioning package.</span></span></br></br><span data-ttu-id="11a27-154">使用 Windows 配置设计器向导配置 Azure AD 批量注册之前，请<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">在贵组织中设置 Azure AD 加入</a>。</span><span class="sxs-lookup"><span data-stu-id="11a27-154">Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>.</span></span> <span data-ttu-id="11a27-155">Azure AD 租户中的<strong>每个用户的最大设备数</strong>设置用于确定你在该向导中获取的批量令牌可使用的次数。</span><span class="sxs-lookup"><span data-stu-id="11a27-155">The <strong>maximum number of devices per user</strong> setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span> <span data-ttu-id="11a27-156">若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。</span><span class="sxs-lookup"><span data-stu-id="11a27-156">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="11a27-157">设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。</span><span class="sxs-lookup"><span data-stu-id="11a27-157">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="11a27-158">单击<strong>获取批量令牌</strong>。</span><span class="sxs-lookup"><span data-stu-id="11a27-158">Click <strong>Get bulk token</strong>.</span></span> <span data-ttu-id="11a27-159">在 " <strong> 让&#39;s 登录" 窗口中 </strong> ，输入有权将设备加入 Azure AD 的帐户，然后输入密码。</span><span class="sxs-lookup"><span data-stu-id="11a27-159">In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="11a27-160">单击<strong>接受</strong>以向 Windows 配置设计器提供所需的权限。</span><span class="sxs-lookup"><span data-stu-id="11a27-160">Click <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</span></span></br></br><span data-ttu-id="11a27-161">若要创建本地管理员帐户，请选择该选项，然后输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="11a27-161">To create a local administrator account, select that option and enter a user name and password.</span></span> </br></br><strong><span data-ttu-id="11a27-162">重要提示</strong>：如果在预配包中创建本地帐户，则必须每 42 天使用<strong>设置</strong>应用更改密码。</span><span class="sxs-lookup"><span data-stu-id="11a27-162">Important:</strong> If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days.</span></span> <span data-ttu-id="11a27-163">如果在此期限内未更改密码，帐户可能会被锁定而无法登录。</span><span class="sxs-lookup"><span data-stu-id="11a27-163">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br><span data-ttu-id="11a27-164">对 MDM 中的注册切换为<strong>是</strong>或<strong>否</strong>。</span><span class="sxs-lookup"><span data-stu-id="11a27-164">Toggle <strong>Yes</strong> or <strong>No</strong> for enrollment in MDM.</span></span> </br></br><span data-ttu-id="11a27-165">如果切换为<strong>是</strong>，必须提供服务帐户和密码或有权注册设备的证书指纹，并指定身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="11a27-165">If you toggle <strong>Yes</strong>, you must provide a service account and password or certificate thumbprint that is authorized to enroll the device, and also specify the authentication type.</span></span> <span data-ttu-id="11a27-166">如果你的 MDM 提供程序要求，也请为发现服务、注册服务和策略服务输入 URL。</span><span class="sxs-lookup"><span data-stu-id="11a27-166">If required by your MDM provider, also enter the URLs for the discovery service, enrollment service, and policy service.</span></span> <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)"><span data-ttu-id="11a27-167">了解有关使用 MDM 管理 Surface Hub 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="11a27-167">Learn more about managing Surface Hub with MDM.</span></span></a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br><span data-ttu-id="11a27-168">你可以在预配包中安装多个通用 Windows 平台 (UWP) 应用。</span><span class="sxs-lookup"><span data-stu-id="11a27-168">You can install multiple Universal Windows Platform (UWP) apps in a provisioning package.</span></span> <span data-ttu-id="11a27-169">有关这些设置的帮助，请参阅<a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">使用应用预配电脑</a>。</span><span class="sxs-lookup"><span data-stu-id="11a27-169">For help with the settings, see <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">Provision PCs with apps</a>.</span></span> </br></br><strong><span data-ttu-id="11a27-170">重要提示： </strong> 虽然向导界面允许你选择经典 Win32 应用，但仅在将应用于 Surface Hub 的预配包中包含 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="11a27-170">Important:</strong> Although the wizard interface allows you to select a Classic Win32 app, only include UWP apps in a provisioning package that will be applied to Surface Hub.</span></span> <span data-ttu-id="11a27-171">如果包括经典 Win32 应用，预配将失败。</span><span class="sxs-lookup"><span data-stu-id="11a27-171">If you include a Classic Win32 app, provisioning will fail.</span></span> </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br><span data-ttu-id="11a27-172">在此步骤中，你不会&#39;t 配置任何设置。</span><span class="sxs-lookup"><span data-stu-id="11a27-172">You don&#39;t configure any settings in this step.</span></span> <span data-ttu-id="11a27-173">它提供添加包含设备帐户列表的配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="11a27-173">It provides instructions for including a configuration file that contains a list of device accounts.</span></span> <span data-ttu-id="11a27-174">配置文件不得包含列标题。</span><span class="sxs-lookup"><span data-stu-id="11a27-174">The configuration file must not contain column headers.</span></span> <span data-ttu-id="11a27-175">当将预配包应用于 Surface Hub 时，如果 Surface Hub 配置文件包含在 U 盘上，则可以从文件中选择设备帐户和友好名称。</span><span class="sxs-lookup"><span data-stu-id="11a27-175">When you apply the provisioning package to Surface Hub, if a Surface Hub configuration file is included on the USB drive, you can select the account and friendly name for the device from the file.</span></span> <span data-ttu-id="11a27-176">请参阅<a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">样本配置文件</a>了解相关示例。</span><span class="sxs-lookup"><span data-stu-id="11a27-176">See <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">Sample configuration file</a> for an example.</span></span></br></br><strong><span data-ttu-id="11a27-177">重要提示： </strong> 配置文件只能在 (OOBE) 的全新设置体验期间应用，并且只能与使用 windows 10 版本1703发布的 Windows 配置设计器创建的预配程序包一起使用。</span><span class="sxs-lookup"><span data-stu-id="11a27-177">Important:</strong> The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.</span></span>  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish"/></br></br><span data-ttu-id="11a27-178">你可以设置密码，以保护你的预配包。</span><span class="sxs-lookup"><span data-stu-id="11a27-178">You can set a password to protect your provisioning package.</span></span> <span data-ttu-id="11a27-179">你必须在将预配包应用到设备时输入此密码。</span><span class="sxs-lookup"><span data-stu-id="11a27-179">You must enter this password when you apply the provisioning package to a device.</span></span></td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

<span data-ttu-id="11a27-180">完成之后，请单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="11a27-180">After you're done, click **Create**.</span></span> <span data-ttu-id="11a27-181">这只需几秒钟的时间。</span><span class="sxs-lookup"><span data-stu-id="11a27-181">It only takes a few seconds.</span></span> <span data-ttu-id="11a27-182">生成该包之后，其存储位置将在页面底部显示为超链接。</span><span class="sxs-lookup"><span data-stu-id="11a27-182">When the package is built, the location where the package is stored is displayed as a hyperlink at the bottom of the page.</span></span>

## <span data-ttu-id="11a27-183">示例配置文件</span><span class="sxs-lookup"><span data-stu-id="11a27-183">Sample configuration file</span></span>

<span data-ttu-id="11a27-184">Surface Hub 配置文件包含你的设备可用于连接到 Exchange 和 Skype for Business 的设备帐户列表。</span><span class="sxs-lookup"><span data-stu-id="11a27-184">A Surface Hub configuration file contains a list of device accounts that your device can use to connect to Exchange and Skype for Business.</span></span> <span data-ttu-id="11a27-185">当你将预配包应用于 Surface Hub 时，你可以在 U 盘的根目录中包含配置文件，然后选择需要应用于该设备的帐户。</span><span class="sxs-lookup"><span data-stu-id="11a27-185">When you apply a provisioning package to Surface Hub, you can include a configuration file in the root directory of the USB flash drive, and then select the desired account to apply to that device.</span></span> <span data-ttu-id="11a27-186">配置文件仅可以在全新设置体验 (OOBE) 期间应用，并且只能与使用随 Windows 10 版本 1703 发布的 Windows 配置设计器创建的预配包一起使用。</span><span class="sxs-lookup"><span data-stu-id="11a27-186">The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.</span></span>

<span data-ttu-id="11a27-187">使用 Microsoft Excel 或其他 CSV 编辑器创建一个名为 `SurfaceHubConfiguration.csv` 的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="11a27-187">Use Microsoft Excel or other CSV editor to create a CSV file named `SurfaceHubConfiguration.csv`.</span></span> <span data-ttu-id="11a27-188">在该文件中，按以下格式输入设备帐户和友好名称列表：</span><span class="sxs-lookup"><span data-stu-id="11a27-188">In the file, enter a list of device accounts and friendly names in this format:</span></span>

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
><span data-ttu-id="11a27-189">由于配置文件以纯文本形式存储设备帐户密码，因此我们建议你在将预配包应用到你的设备后更新密码。</span><span class="sxs-lookup"><span data-stu-id="11a27-189">Because the configuration file stores the device account passwords in plaintext, we recommend that you update the passwords after you've applied the provisioning package to your devices.</span></span> <span data-ttu-id="11a27-190">你可以使用 [DeviceAccount 节点](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount)（位于 [Surface Hub 配置服务提供程序 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) 中）通过 MDM 更新密码。</span><span class="sxs-lookup"><span data-stu-id="11a27-190">You can use the [DeviceAccount node](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount) in the [Surface Hub configuration service provider (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) to update the passwords via MDM.</span></span>


<span data-ttu-id="11a27-191">下面是 `SurfaceHubConfiguration.csv` 示例。</span><span class="sxs-lookup"><span data-stu-id="11a27-191">The following is an example of `SurfaceHubConfiguration.csv`.</span></span> 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## <span data-ttu-id="11a27-192">使用高级预配</span><span class="sxs-lookup"><span data-stu-id="11a27-192">Use advanced provisioning</span></span>

<span data-ttu-id="11a27-193">[安装 Windows 配置设计器](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)后，你可以创建预配包。</span><span class="sxs-lookup"><span data-stu-id="11a27-193">After you [install Windows Configuration Designer](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), you can create a provisioning package.</span></span>

### <span data-ttu-id="11a27-194">创建预配包（高级）</span><span class="sxs-lookup"><span data-stu-id="11a27-194">Create the provisioning package (advanced)</span></span>

1. <span data-ttu-id="11a27-195">打开 Windows 配置设计器：</span><span class="sxs-lookup"><span data-stu-id="11a27-195">Open Windows Configuration Designer:</span></span>
   - <span data-ttu-id="11a27-196">在“开始”屏幕或“开始”菜单搜索中，键入“Windows 配置设计器”，然后单击 Windows 配置设计器快捷方式，</span><span class="sxs-lookup"><span data-stu-id="11a27-196">From either the Start screen or Start menu search, type 'Windows Configuration Designer' and click on the Windows Configuration Designer shortcut,</span></span> 
    
     <span data-ttu-id="11a27-197">或</span><span class="sxs-lookup"><span data-stu-id="11a27-197">or</span></span>
    
   - <span data-ttu-id="11a27-198">如果 Windows 配置设计器是从 ADK 安装的，请导航到 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86`（在 x64 计算机上）或 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe`（在 x86 计算机上），然后双击 **ICD.exe**。</span><span class="sxs-lookup"><span data-stu-id="11a27-198">If you installed Windows Configuration Designer from the ADK, navigate to `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (on an x64 computer) or `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (on an x86 computer), and then double-click **ICD.exe**.</span></span>

2. <span data-ttu-id="11a27-199">单击**高级预配**。</span><span class="sxs-lookup"><span data-stu-id="11a27-199">Click **Advanced provisioning**.</span></span>
   
3. <span data-ttu-id="11a27-200">为你的项目命名，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="11a27-200">Name your project and click **Next**.</span></span>

4. <span data-ttu-id="11a27-201">选择 " **通用到 Windows 10 团队**"，单击 " **下一步**"，然后单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="11a27-201">Select **Common to Windows 10 Team**, click **Next**, and then click **Finish**.</span></span>

    ![ICD 新项目](images/icd-new-project.png)

5. <span data-ttu-id="11a27-203">在项目中的 " **可用自定义**" 下，选择 " **常用团队设置**"。</span><span class="sxs-lookup"><span data-stu-id="11a27-203">In the project, under **Available customizations**, select **Common Team settings**.</span></span>

    ![ICD 常用设置](images/icd-common-settings.png)


### <span data-ttu-id="11a27-205">将证书添加到程序包</span><span class="sxs-lookup"><span data-stu-id="11a27-205">Add a certificate to your package</span></span>
<span data-ttu-id="11a27-206">可使用设置包安装支持设备验证 Microsoft Exchange 身份的证书。</span><span class="sxs-lookup"><span data-stu-id="11a27-206">You can use provisioning packages to install certificates that will allow the device to authenticate to Microsoft Exchange.</span></span>

> [!NOTE]
> <span data-ttu-id="11a27-207">设置包仅可将证书安装到设备（本地计算机）存储，而非用户存储。</span><span class="sxs-lookup"><span data-stu-id="11a27-207">Provisioning packages can only install certificates to the device (local machine) store, and not to the user store.</span></span> <span data-ttu-id="11a27-208">如果组织要求证书必须安装到用户存储，则必须使用移动设备管理 (MDM) 部署这些证书。</span><span class="sxs-lookup"><span data-stu-id="11a27-208">If your organization requires that certificates must be installed to the user store, use Mobile Device Management (MDM) to deploy these certificates.</span></span> <span data-ttu-id="11a27-209">有关详细信息，请参阅 MDM 解决方案文档。</span><span class="sxs-lookup"><span data-stu-id="11a27-209">See your MDM solution documentation for details.</span></span>

1. <span data-ttu-id="11a27-210">在**可用自定义项**窗格中，转到**运行时设置** > **证书** > **ClientCertificates**。</span><span class="sxs-lookup"><span data-stu-id="11a27-210">In the **Available customizations** pane, go to **Runtime settings** > **Certificates** > **ClientCertificates**.</span></span> 

2. <span data-ttu-id="11a27-211">输入 **CertificateName**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="11a27-211">Enter a **CertificateName** and then click **Add**.</span></span> 

2. <span data-ttu-id="11a27-212">输入 **CertificatePassword**。</span><span class="sxs-lookup"><span data-stu-id="11a27-212">Enter the **CertificatePassword**.</span></span> 

3. <span data-ttu-id="11a27-213">对于 **CertificatePath**，浏览并选择证书。</span><span class="sxs-lookup"><span data-stu-id="11a27-213">For **CertificatePath**, browse and select the certificate.</span></span> 

4. <span data-ttu-id="11a27-214">将 **ExportCertificate** 设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="11a27-214">Set **ExportCertificate** to **False**.</span></span>

5. <span data-ttu-id="11a27-215">对于 **KeyLocation**，选择**仅软件**。</span><span class="sxs-lookup"><span data-stu-id="11a27-215">For **KeyLocation**, select **Software only**.</span></span>


### <span data-ttu-id="11a27-216">将通用 Windows 平台 (UWP) 应用添加到程序包</span><span class="sxs-lookup"><span data-stu-id="11a27-216">Add a Universal Windows Platform (UWP) app to your package</span></span>
<span data-ttu-id="11a27-217">将 UWP 应用添加到设置包前，需要具备应用包（.appx 或 .appxbundle）和任何依赖关系文件。</span><span class="sxs-lookup"><span data-stu-id="11a27-217">Before adding a UWP app to a provisioning package, you need the app package (either an .appx, or .appxbundle) and any dependency files.</span></span> <span data-ttu-id="11a27-218">如果已从适用于企业的 Microsoft Store 获取了该应用，还需要*已解码的*应用许可。</span><span class="sxs-lookup"><span data-stu-id="11a27-218">If you acquired the app from the Microsoft Store for Business, you will also need the *unencoded* app license.</span></span> <span data-ttu-id="11a27-219">请参阅[分配脱机应用](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)，了解如何从适用于企业的 Microsoft Store 下载这些项目。</span><span class="sxs-lookup"><span data-stu-id="11a27-219">See [Distribute offline apps](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app) to learn how to download these items from the Microsoft Store for Business.</span></span>

1. <span data-ttu-id="11a27-220">在**可用自定义项**窗格中，转到**运行时设置** > **UniversalAppInstall** > **DeviceContextApp**。</span><span class="sxs-lookup"><span data-stu-id="11a27-220">In the **Available customizations** pane, go to **Runtime settings** > **UniversalAppInstall** > **DeviceContextApp**.</span></span>

2. <span data-ttu-id="11a27-221">为应用输入 **PackageFamilyName**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="11a27-221">Enter a **PackageFamilyName** for the app and then click **Add**.</span></span> <span data-ttu-id="11a27-222">为了保持一致性，请使用应用的程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="11a27-222">For consistency, use the app's package family name.</span></span> <span data-ttu-id="11a27-223">如果已从适用于企业的 Microsoft Store 获取了该应用，可在应用许可中查找程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="11a27-223">If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license.</span></span> <span data-ttu-id="11a27-224">使用文本编辑器打开许可证文件，并使用 "..." 标记之间的值。 \<PFM\> \</PFM\></span><span class="sxs-lookup"><span data-stu-id="11a27-224">Open the license file using a text editor, and use the value between the \<PFM\>...\</PFM\> tags.</span></span>

3. <span data-ttu-id="11a27-225">对于 **ApplicationFile**，单击**浏览**以查找并选择目标应用（\*.appx 或 \*.appxbundle）。</span><span class="sxs-lookup"><span data-stu-id="11a27-225">For **ApplicationFile**, click **Browse** to find and select the target app (either an \*.appx or \*.appxbundle).</span></span>

4. <span data-ttu-id="11a27-226">对于 **DependencyAppxFiles**，单击**浏览**，为应用查找并添加任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="11a27-226">For **DependencyAppxFiles**, click **Browse** to find and add any dependencies for the app.</span></span> <span data-ttu-id="11a27-227">对于 Surface Hub，仅需要 x64 版本的依赖项。</span><span class="sxs-lookup"><span data-stu-id="11a27-227">For Surface Hub, you will only need the x64 versions of these dependencies.</span></span>

<span data-ttu-id="11a27-228">如果已从适用于企业的 Microsoft Store 获取了该应用，还需要将应用许可添加到设置包。</span><span class="sxs-lookup"><span data-stu-id="11a27-228">If you acquired the app from the Microsoft Store for Business, you will also need to add the app license to your provisioning package.</span></span>

1. <span data-ttu-id="11a27-229">制作应用许可的副本，并为其重命名，以使用 **.ms-windows-store-license** 扩展名。</span><span class="sxs-lookup"><span data-stu-id="11a27-229">Make a copy of the app license, and rename it to use a **.ms-windows-store-license** extension.</span></span> <span data-ttu-id="11a27-230">例如，“example.xml”变为“example.ms-windows-store-license”。</span><span class="sxs-lookup"><span data-stu-id="11a27-230">For example, "example.xml" becomes "example.ms-windows-store-license".</span></span>

2. <span data-ttu-id="11a27-231">在 ICD 的**可用自定义项**窗格中，转到**运行时设置** > **UniversalAppInstall** > **DeviceContextAppLicense**。</span><span class="sxs-lookup"><span data-stu-id="11a27-231">In ICD, in the **Available customizations** pane, go to **Runtime settings** > **UniversalAppInstall** > **DeviceContextAppLicense**.</span></span>

3. <span data-ttu-id="11a27-232">输入 **LicenseProductId**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="11a27-232">Enter a **LicenseProductId** and then click **Add**.</span></span> <span data-ttu-id="11a27-233">为了保持一致性，请使用应用许可中的应用许可 ID。</span><span class="sxs-lookup"><span data-stu-id="11a27-233">For consistency, use the app's license ID from the app license.</span></span> <span data-ttu-id="11a27-234">使用文本编辑器打开许可文件。</span><span class="sxs-lookup"><span data-stu-id="11a27-234">Open the license file using a text editor.</span></span> <span data-ttu-id="11a27-235">然后，在 \<License\> 标记中，使用 **LicenseID** 属性中的值。</span><span class="sxs-lookup"><span data-stu-id="11a27-235">Then, in the \<License\> tag, use the value in the **LicenseID** attribute.</span></span>

4. <span data-ttu-id="11a27-236">选择新的 **LicenseProductId** 节点。</span><span class="sxs-lookup"><span data-stu-id="11a27-236">Select the new **LicenseProductId** node.</span></span> <span data-ttu-id="11a27-237">对于 **LicenseInstall**，单击**浏览**，选择在步骤 1 中重命名的许可文件。</span><span class="sxs-lookup"><span data-stu-id="11a27-237">For **LicenseInstall**, click **Browse** to find and select the license file that you renamed in Step 1.</span></span>


### <span data-ttu-id="11a27-238">将策略添加到程序包</span><span class="sxs-lookup"><span data-stu-id="11a27-238">Add a policy to your package</span></span>
<span data-ttu-id="11a27-239">Surface Hub 支持[策略配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)中的策略子集。</span><span class="sxs-lookup"><span data-stu-id="11a27-239">Surface Hub supports a subset of the policies in the [Policy configuration service provider](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx).</span></span> <span data-ttu-id="11a27-240">某些策略可通过 ICD 配置。</span><span class="sxs-lookup"><span data-stu-id="11a27-240">Some of those policies can be configured with ICD.</span></span>

1. <span data-ttu-id="11a27-241">在**可用自定义项**窗格中，转到**运行时设置** > **策略**。</span><span class="sxs-lookup"><span data-stu-id="11a27-241">In the **Available customizations** pane, go to **Runtime settings** > **Policies**.</span></span>

2. <span data-ttu-id="11a27-242">选择其中一个可用的策略区域。</span><span class="sxs-lookup"><span data-stu-id="11a27-242">Select one of the available policy areas.</span></span>

3. <span data-ttu-id="11a27-243">选择并设置要添加到设置包的策略。</span><span class="sxs-lookup"><span data-stu-id="11a27-243">Select and set the policy you want to add to your provisioning package.</span></span>


### <span data-ttu-id="11a27-244">将 Surface Hub 设置添加到程序包</span><span class="sxs-lookup"><span data-stu-id="11a27-244">Add Surface Hub settings to your package</span></span> 

<span data-ttu-id="11a27-245">可将 [SurfaceHub 配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)中的设置添加到设置包。</span><span class="sxs-lookup"><span data-stu-id="11a27-245">You can add settings from the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) to your provisioning package.</span></span> 

1. <span data-ttu-id="11a27-246">在**可用自定义项**窗格中，转到**运行时设置** > **WindowsTeamSettings**。</span><span class="sxs-lookup"><span data-stu-id="11a27-246">In the **Available customizations** pane, go to **Runtime settings** > **WindowsTeamSettings**.</span></span>

2. <span data-ttu-id="11a27-247">选择其中一个可用的设置区域。</span><span class="sxs-lookup"><span data-stu-id="11a27-247">Select one of the available setting areas.</span></span>

3. <span data-ttu-id="11a27-248">选择并设置要添加到设置包的设置。</span><span class="sxs-lookup"><span data-stu-id="11a27-248">Select and set the setting you want to add to your provisioning package.</span></span> 


## <span data-ttu-id="11a27-249">生成程序包</span><span class="sxs-lookup"><span data-stu-id="11a27-249">Build your package</span></span>

1. <span data-ttu-id="11a27-250">完成预配包的配置后，在**文件**菜单上单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="11a27-250">When you are done configuring the provisioning package, on the **File** menu, click **Save**.</span></span>

2. <span data-ttu-id="11a27-251">阅读项目文件可能包含敏感信息的警告，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="11a27-251">Read the warning that project files may contain sensitive information, and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="11a27-252">生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="11a27-252">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="11a27-253">尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。</span><span class="sxs-lookup"><span data-stu-id="11a27-253">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="11a27-254">应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。</span><span class="sxs-lookup"><span data-stu-id="11a27-254">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>

3. <span data-ttu-id="11a27-255">在**导出**菜单中，单击**预配包**。</span><span class="sxs-lookup"><span data-stu-id="11a27-255">On the **Export** menu, click **Provisioning package**.</span></span>

4. <span data-ttu-id="11a27-256">将**所有者**更改为 **IT 管理员**，这会将此设置包的优先级设置为高于应用于来自其他源的设备的设置包。</span><span class="sxs-lookup"><span data-stu-id="11a27-256">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources.</span></span>

5. <span data-ttu-id="11a27-257">设置**程序包版本**的值，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="11a27-257">Set a value for **Package Version**, and then select **Next.**</span></span>

    > [!TIP]
    > <span data-ttu-id="11a27-258">可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。</span><span class="sxs-lookup"><span data-stu-id="11a27-258">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

6. <span data-ttu-id="11a27-259">可选：可选择加密程序包并启用程序包签名。</span><span class="sxs-lookup"><span data-stu-id="11a27-259">Optional: You can choose to encrypt the package and enable package signing.</span></span>

    -   <span data-ttu-id="11a27-260">**启用程序包加密** - 如果你选择此选项，将在屏幕上显示自动生成的密码。</span><span class="sxs-lookup"><span data-stu-id="11a27-260">**Enable package encryption** - If you select this option, an auto-generated password will be shown on the screen.</span></span>

    -   <span data-ttu-id="11a27-261">**启用程序包签名** - 如果选择此选项，则必须选择一个有效的证书，用于对程序包进行签名。</span><span class="sxs-lookup"><span data-stu-id="11a27-261">**Enable package signing** - If you select this option, you must select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="11a27-262">可以通过单击**浏览...** 并选择要用于对程序包进行签名的证书，指定相关证书。</span><span class="sxs-lookup"><span data-stu-id="11a27-262">You can specify the certificate by clicking **Browse...** and choosing the certificate you want to use to sign the package.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="11a27-263">建议将受信任的设置证书包含在预配包中。</span><span class="sxs-lookup"><span data-stu-id="11a27-263">We recommend that you include a trusted provisioning certificate in your provisioning package.</span></span> <span data-ttu-id="11a27-264">当程序包应用于设备时，该证书将添加到系统存储，然后便可以静默方式应用通过该证书签名的任意程序包。</span><span class="sxs-lookup"><span data-stu-id="11a27-264">When the package is applied to a device, the certificate is added to the system store and any package signed with that certificate thereafter can be applied silently.</span></span> 

7. <span data-ttu-id="11a27-265">单击**下一步**，指定在生成预配包后想要放置的输出位置。</span><span class="sxs-lookup"><span data-stu-id="11a27-265">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="11a27-266">默认情况下，Windows ICD 会使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="11a27-266">By default, Windows ICD uses the project folder as the output location.</span></span><p>
<span data-ttu-id="11a27-267">或者，你还可以单击**浏览**更改默认输出位置。</span><span class="sxs-lookup"><span data-stu-id="11a27-267">Optionally, you can click **Browse** to change the default output location.</span></span>

8. <span data-ttu-id="11a27-268">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11a27-268">Click **Next**.</span></span>

9. <span data-ttu-id="11a27-269">单击**构建**开始构建程序包。</span><span class="sxs-lookup"><span data-stu-id="11a27-269">Click **Build** to start building the package.</span></span> <span data-ttu-id="11a27-270">项目信息会显示在构建页面中，并且进度栏会指示构建状态。</span><span class="sxs-lookup"><span data-stu-id="11a27-270">The project information is displayed in the build page and the progress bar indicates the build status.</span></span><p>
<span data-ttu-id="11a27-271">如果你需要取消构建，请单击“取消” \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11a27-271">If you need to cancel the build, click **Cancel**.</span></span> <span data-ttu-id="11a27-272">这将取消当前的构建过程、关闭向导，并使你返回到“自定义页面” \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11a27-272">This cancels the current build process, closes the wizard, and takes you back to the **Customizations Page**.</span></span>

10. <span data-ttu-id="11a27-273">如果构建失败，则显示一条包含项目文件夹链接的错误消息。</span><span class="sxs-lookup"><span data-stu-id="11a27-273">If your build fails, an error message will show up that includes a link to the project folder.</span></span> <span data-ttu-id="11a27-274">你可以扫描日志以确定导致错误的原因。</span><span class="sxs-lookup"><span data-stu-id="11a27-274">You can scan the logs to determine what caused the error.</span></span> <span data-ttu-id="11a27-275">解决问题后，请尝试重新构建程序包。</span><span class="sxs-lookup"><span data-stu-id="11a27-275">Once you fix the issue, try building the package again.</span></span><p>
<span data-ttu-id="11a27-276">如果构建成功，将显示设置包的名称、输出目录和项目目录。</span><span class="sxs-lookup"><span data-stu-id="11a27-276">If your build is successful, the name of the provisioning package, output directory, and project directory will be shown.</span></span>

    -   <span data-ttu-id="11a27-277">如果要进行选择，你可以重新构建设置包并选择不同的输出程序包路径。</span><span class="sxs-lookup"><span data-stu-id="11a27-277">If you choose, you can build the provisioning package again and pick a different path for the output package.</span></span> <span data-ttu-id="11a27-278">若要执行此操作，请单击“返回”\*\*\*\* 更改输出程序包名称和路径，然后单击“下一步”\*\*\*\* 启动另一次构建。</span><span class="sxs-lookup"><span data-stu-id="11a27-278">To do this, click **Back** to change the output package name and path, and then click **Next** to start another build.</span></span>
    
    -   <span data-ttu-id="11a27-279">如果你已完成，请单击“完成”\*\*\*\* 关闭向导，并返回到“自定义页面”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11a27-279">If you are done, click **Finish** to close the wizard and go back to the **Customizations Page**.</span></span>

11. <span data-ttu-id="11a27-280">选择**输出位置**链接以转到该程序包所在的位置。</span><span class="sxs-lookup"><span data-stu-id="11a27-280">Select the **output location** link to go to the location of the package.</span></span> <span data-ttu-id="11a27-281">将 .ppkg 复制到空 U 盘。</span><span class="sxs-lookup"><span data-stu-id="11a27-281">Copy the .ppkg to an empty USB flash drive.</span></span>


## <span data-ttu-id="11a27-282">将设置包应用到 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="11a27-282">Apply a provisioning package to Surface Hub</span></span>

<span data-ttu-id="11a27-283">有两个选项可将设置包部署到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="11a27-283">There are two options for deploying provisioning packages to a Surface Hub.</span></span> <span data-ttu-id="11a27-284">在[首次运行向导期间](#apply-a-provisioning-package-during-first-run)，你可以应用安装证书的预配包，或者在首次运行程序完成后，你可以通过使用[设置](#apply-a-package-using-settings)来应用配置设置、应用和证书的预配包。</span><span class="sxs-lookup"><span data-stu-id="11a27-284">[During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-package-using-settings).</span></span> 


### <span data-ttu-id="11a27-285">在首次运行时应用设置包</span><span class="sxs-lookup"><span data-stu-id="11a27-285">Apply a provisioning package during first run</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11a27-286">在首次运行程序中，只能使用预配程序包安装证书。</span><span class="sxs-lookup"><span data-stu-id="11a27-286">During the first-run program, you can only use provisioning packages to install certificates.</span></span> <span data-ttu-id="11a27-287">使用**设置**应用安装应用和应用其他设置。</span><span class="sxs-lookup"><span data-stu-id="11a27-287">Use the **Settings** app to install apps and apply other settings.</span></span>

1. <span data-ttu-id="11a27-288">第一次打开 Surface Hub 时，首次运行程序将显示[**“你好”页面**](first-run-program-surface-hub.md#first-page)。</span><span class="sxs-lookup"><span data-stu-id="11a27-288">When you turn on the Surface Hub for the first time, the first-run program will display the [**Hi there page**](first-run-program-surface-hub.md#first-page).</span></span> <span data-ttu-id="11a27-289">确保设置已正确配置，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="11a27-289">Make sure that the settings are properly configured before proceeding.</span></span>

2. <span data-ttu-id="11a27-290">将包含 .ppkg 文件的 U 盘插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="11a27-290">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span> <span data-ttu-id="11a27-291">如果程序包位于驱动器的根目录中，首次运行程序将识别它，并询问是否要设置设备。</span><span class="sxs-lookup"><span data-stu-id="11a27-291">If the package is in the root directory of the drive, the first-run program will recognize it and ask if you want to set up the device.</span></span> <span data-ttu-id="11a27-292">选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="11a27-292">Select **Set up**.</span></span>

    ![设置设备？](images/provisioningpackageoobe-01.png)

3. <span data-ttu-id="11a27-294">下一个屏幕会要求你选择预配源。</span><span class="sxs-lookup"><span data-stu-id="11a27-294">The next screen asks you to select a provisioning source.</span></span> <span data-ttu-id="11a27-295">选择“可移动媒体”\*\*\*\*，然后点击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11a27-295">Select **Removable Media** and tap **Next**.</span></span>

    ![预配此设备](images/provisioningpackageoobe-02.png)
    
4. <span data-ttu-id="11a27-297">选择要应用的设置包 (\*.ppkg)，然后点击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="11a27-297">Select the provisioning package (\*.ppkg) that you want to apply, and tap **Next**.</span></span> <span data-ttu-id="11a27-298">注意，首次运行期间只能安装一个程序包。</span><span class="sxs-lookup"><span data-stu-id="11a27-298">Note that you can only install one package during first run.</span></span>

    ![选择程序包](images/provisioningpackageoobe-03.png)

5. <span data-ttu-id="11a27-300">首次运行程序将显示预配包要应用的更改汇总。</span><span class="sxs-lookup"><span data-stu-id="11a27-300">The first-run program will show you a summary of the changes that the provisioning package will apply.</span></span> <span data-ttu-id="11a27-301">选择**是的，添加它**。</span><span class="sxs-lookup"><span data-stu-id="11a27-301">Select **Yes, add it**.</span></span>  

    ![是否信任此程序包？](images/provisioningpackageoobe-04.png)
    
6. <span data-ttu-id="11a27-303">如果配置文件包含在 U 盘的根目录中，你将看到**选择配置**。</span><span class="sxs-lookup"><span data-stu-id="11a27-303">If a configuration file is included in the root directory of the USB flash drive, you will see **Select a configuration**.</span></span> <span data-ttu-id="11a27-304">将显示配置文件中的第一个设备帐户以及将应用到 Surface Hub 的帐户信息摘要。</span><span class="sxs-lookup"><span data-stu-id="11a27-304">The first device account in the configuration file will be shown with a summary of the account information that will be applied to the Surface Hub.</span></span>

    ![选择配置](images/ppkg-config.png)    

7. <span data-ttu-id="11a27-306">在**选择配置**中，请选择要应用的设备名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="11a27-306">In **Select a configuration**, select the device name to apply, and then click **Next**.</span></span>

    ![选择友好设备名称](images/ppkg-csv.png)
    
<span data-ttu-id="11a27-308">预配包中的设置将应用于设备，并将完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="11a27-308">The settings from the provisioning package will be applied to the device and OOBE will be complete.</span></span> <span data-ttu-id="11a27-309">设备重启后，你可以删除 U 盘。</span><span class="sxs-lookup"><span data-stu-id="11a27-309">After the device restarts, you can remove the USB flash drive.</span></span>

### <span data-ttu-id="11a27-310">使用“设置”应用程序包</span><span class="sxs-lookup"><span data-stu-id="11a27-310">Apply a package using Settings</span></span>

1. <span data-ttu-id="11a27-311">将包含 .ppkg 文件的 U 盘插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="11a27-311">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span>

2. <span data-ttu-id="11a27-312">在 Surface Hub 中，启动**设置**，然后在收到提示时输入管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="11a27-312">From the Surface Hub, start **Settings** and enter the admin credentials when prompted.</span></span>

3. <span data-ttu-id="11a27-313">导航到 **Surface Hub** > **设备管理**。</span><span class="sxs-lookup"><span data-stu-id="11a27-313">Navigate to **Surface Hub** > **Device management**.</span></span> <span data-ttu-id="11a27-314">在**预配包**下，选择**添加或删除预配包**。</span><span class="sxs-lookup"><span data-stu-id="11a27-314">Under **Provisioning packages**, select **Add or remove a provisioning package**.</span></span>

4. <span data-ttu-id="11a27-315">选择**添加程序包**。</span><span class="sxs-lookup"><span data-stu-id="11a27-315">Select **Add a package**.</span></span>

5. <span data-ttu-id="11a27-316">选择设置包，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="11a27-316">Choose your provisioning package and select **Add**.</span></span> <span data-ttu-id="11a27-317">如果系统出现提示，可能需要重新输入管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="11a27-317">You may have to re-enter the admin credentials if prompted.</span></span>

6. <span data-ttu-id="11a27-318">将看到设置包应用的更改汇总。</span><span class="sxs-lookup"><span data-stu-id="11a27-318">You'll see a summary of the changes that the provisioning package will apply.</span></span> <span data-ttu-id="11a27-319">选择**是的，添加它**。</span><span class="sxs-lookup"><span data-stu-id="11a27-319">Select **Yes, add it**.</span></span>



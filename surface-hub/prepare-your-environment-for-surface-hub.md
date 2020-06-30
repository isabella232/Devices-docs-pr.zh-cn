---
title: 为 Microsoft Surface Hub 准备你的环境
description: 本部分包含准备环境所需的步骤概述，以便你可以使用 Microsoft Surface Hub 的所有功能。
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: 准备环境, Surface Hub 的功能, 创建和测试设备帐户, 检查网络可用性
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/04/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0ee406df6d3022f04a80f4ce253bd76f6473f1c8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832051"
---
# <span data-ttu-id="994f0-104">为 Microsoft Surface Hub 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="994f0-104">Prepare your environment for Microsoft Surface Hub</span></span>


<span data-ttu-id="994f0-105">本部分包含设置依赖关系和设置过程的概述。</span><span class="sxs-lookup"><span data-stu-id="994f0-105">This section contains an overview of setup dependencies and the setup process.</span></span> <span data-ttu-id="994f0-106">查看本部分中的信息可帮助你准备环境，并收集设 Surface Hub 所需的信息。</span><span class="sxs-lookup"><span data-stu-id="994f0-106">Review the info in this section to help you prepare your environment and gather information needed to set up your Surface Hub.</span></span>


## <span data-ttu-id="994f0-107">查看基础结构依赖关系</span><span class="sxs-lookup"><span data-stu-id="994f0-107">Review infrastructure dependencies</span></span>
<span data-ttu-id="994f0-108">查看这些依赖关系，以确保 Surface Hub 功能在你的 IT 基础结构中有效。</span><span class="sxs-lookup"><span data-stu-id="994f0-108">Review these dependencies to make sure Surface Hub features will work in your IT infrastructure.</span></span>

| <span data-ttu-id="994f0-109">依赖关系</span><span class="sxs-lookup"><span data-stu-id="994f0-109">Dependency</span></span>        | <span data-ttu-id="994f0-110">用途</span><span class="sxs-lookup"><span data-stu-id="994f0-110">Purpose</span></span>           |
|-------------|------------------|
| <span data-ttu-id="994f0-111">Active Directory 或 Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="994f0-111">Active Directory or Azure Active Directory (Azure AD)</span></span> | <p><span data-ttu-id="994f0-112">Surface Hub 使用 Active Directory 或 Azure AD 帐户（称为 **设备帐户**）访问 Exchange 和 Skype for Business 服务。</span><span class="sxs-lookup"><span data-stu-id="994f0-112">The Surface Hub's uses an Active Directory or Azure AD account (called a **device account**) to access Exchange and Skype for Business services.</span></span> <span data-ttu-id="994f0-113">Surface Hub 必须能够连接到 Active Directory 域控制器或 Azure AD 租户，才可以验证设备帐户的凭据以及访问诸如设备帐户的显示名称、别名、Exchange Server 和会话初始协议 (SIP) 地址等信息。</span><span class="sxs-lookup"><span data-stu-id="994f0-113">The Surface Hub must be able to connect to your Active Directory domain controller or to your Azure AD tenant in order to validate the device account’s credentials, as well as to access information like the device account’s display name, alias, Exchange server, and Session Initiation Protocol (SIP) address.</span></span></p><span data-ttu-id="994f0-114">还可以将域或 Azure AD 与 Surface Hub 结合，以允许一组授权用户在 Surface Hub 上配置设置。</span><span class="sxs-lookup"><span data-stu-id="994f0-114">You can also domain join or Azure AD join your Surface Hub to allow a group of authorized users to configure settings on the Surface Hub.</span></span> |
| <span data-ttu-id="994f0-115">Exchange（Exchange 2013 或更高版本，或者 Exchange Online）和 Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="994f0-115">Exchange (Exchange 2013 or later, or Exchange Online) and Exchange ActiveSync</span></span> | <p><span data-ttu-id="994f0-116">Exchange 用于启用邮件和日历功能，并且还允许使用该设备的用户向 Surface Hub 发送会议请求，以便支持一站式会议加入。</span><span class="sxs-lookup"><span data-stu-id="994f0-116">Exchange is used for enabling mail and calendar features, and also lets people who use the device send meeting requests to the Surface Hub, enabling one-touch meeting join.</span></span></p><span data-ttu-id="994f0-117">ActiveSync 用于将设备帐户的日历和邮件同步到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="994f0-117">ActiveSync is used to sync the device account’s calendar and mail to the Surface Hub.</span></span> <span data-ttu-id="994f0-118">如果该设备不能使用 ActiveSync，则不会在欢迎屏幕上显示会议，并且不支持加入会议和通过电子邮件发送白板。</span><span class="sxs-lookup"><span data-stu-id="994f0-118">If the device cannot use ActiveSync, it will not show meetings on the welcome screen, and joining meetings and emailing whiteboards will not be enabled.</span></span> |
| <span data-ttu-id="994f0-119">Skype for Business（Lync Server 2013 或更高版本，或者 Skype for Business Online）</span><span class="sxs-lookup"><span data-stu-id="994f0-119">Skype for Business (Lync Server 2013 or later, or Skype for Business Online)</span></span>  | <span data-ttu-id="994f0-120">Skype for Business 可用于各种会议功能，例如视频通话、即时消息和屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="994f0-120">Skype for Business is used for various conferencing features, like video calls, instant messaging, and screen sharing.</span></span>|
| <span data-ttu-id="994f0-121">移动设备管理（MDM）解决方案（Microsoft Intune、Microsoft 终结点配置管理器或受支持的第三方 MDM 提供程序）</span><span class="sxs-lookup"><span data-stu-id="994f0-121">Mobile device management (MDM) solution (Microsoft Intune, Microsoft Endpoint Configuration Manager, or supported third-party MDM provider)</span></span> | <span data-ttu-id="994f0-122">如果想要远程应用设置并安装应用，以及一次性将设置应用于多台设备，必须设置 MDM 解决方案并向该解决方案注册设备。</span><span class="sxs-lookup"><span data-stu-id="994f0-122">If you want to apply settings and install apps remotely, and to multiple devices at a time, you must set up a MDM solution and enroll the device to that solution.</span></span> <span data-ttu-id="994f0-123">请参阅[使用 MDM 提供程序管理设置](manage-settings-with-mdm-for-surface-hub.md)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="994f0-123">See [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md) for details.</span></span> |
| <span data-ttu-id="994f0-124">Microsoft Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="994f0-124">Microsoft Operations Management Suite (OMS)</span></span>   | <span data-ttu-id="994f0-125">OMS 用于监视 Surface Hub 设备的运行状况。</span><span class="sxs-lookup"><span data-stu-id="994f0-125">OMS is used to monitor the health of Surface Hub devices.</span></span> <span data-ttu-id="994f0-126">请参阅[监视 Surface Hub](monitor-surface-hub.md)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="994f0-126">See [Monitor your Surface Hub](monitor-surface-hub.md) for details.</span></span> |
| <span data-ttu-id="994f0-127">网络和 Internet 访问权限</span><span class="sxs-lookup"><span data-stu-id="994f0-127">Network and Internet access</span></span>   | <span data-ttu-id="994f0-128">为了能够正常工作，Surface Hub 应有权访问有线网络或无线网络。</span><span class="sxs-lookup"><span data-stu-id="994f0-128">In order to function properly, the Surface Hub should have access to a wired or wireless network.</span></span> <span data-ttu-id="994f0-129">总的来说，有线连接是首选。</span><span class="sxs-lookup"><span data-stu-id="994f0-129">Overall, a wired connection is preferred.</span></span> <span data-ttu-id="994f0-130">有线和无线连接均支持 802.1X 身份验证。</span><span class="sxs-lookup"><span data-stu-id="994f0-130">802.1X Authentication is supported for both wired and wireless connections.</span></span></br></br></br><span data-ttu-id="994f0-131">**802.1X 身份验证：** 在 Windows 10 版本 1703 中，默认情况下，Surface Hub 启用了适用于有线和无线连接的 802.1X 身份验证。</span><span class="sxs-lookup"><span data-stu-id="994f0-131">**802.1X authentication:** In Windows 10, version 1703, 802.1X authentication for wired and wireless connections is enabled by default in Surface Hub.</span></span> <span data-ttu-id="994f0-132">如果你的组织未使用 802.1X 身份验证，则不需要进行配置并且 Surface Hub 将继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="994f0-132">If your organization doesn't use 802.1X authentication, there is no configuration required and Surface Hub will continue to function as normal.</span></span> <span data-ttu-id="994f0-133">如果你使用 802.1X 身份验证，则必须确保 Surface Hub 上安装了身份验证证书。</span><span class="sxs-lookup"><span data-stu-id="994f0-133">If you use 802.1X authentication, you must ensure that the authentication certification is installed on Surface Hub.</span></span> <span data-ttu-id="994f0-134">你可以使用 MDM 中的 [ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp) 向 Surface Hub 提供证书，或者可以[创建预配包](provisioning-packages-for-surface-hub.md)，并在首次运行期间或通过“设置”应用来安装它。</span><span class="sxs-lookup"><span data-stu-id="994f0-134">You can deliver the certificate to Surface Hub using the [ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp) in MDM, or you can [create a provisioning package](provisioning-packages-for-surface-hub.md) and install it during first run or through the Settings app.</span></span> <span data-ttu-id="994f0-135">将证书应用于 Surface Hub 后，802.1X 身份验证将自动开始工作。</span><span class="sxs-lookup"><span data-stu-id="994f0-135">After the certificate is applied to Surface Hub, 802.1X authentication will start working automatically.</span></span></br><span data-ttu-id="994f0-136">**注意**：有关在 Surface Hub 上启用 802.1X 有线身份验证的详细信息，请参阅[启用 802.1x 有线身份验证](enable-8021x-wired-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="994f0-136">**Note:** For more information on enabling 802.1X wired authentication on Surface Hub, see [Enable 802.1x wired authentication](enable-8021x-wired-authentication.md).</span></span></br></br><span data-ttu-id="994f0-137">**动态 IP**：Surface Hub 无法配置为使用静态 IP。</span><span class="sxs-lookup"><span data-stu-id="994f0-137">**Dynamic IP:** The Surface Hub cannot be configured to use a static IP.</span></span> <span data-ttu-id="994f0-138">必须使用 DHCP 才能分配 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="994f0-138">It must use DHCP to assign an IP address.</span></span></br></br><span data-ttu-id="994f0-139">**代理服务器**：如果你的拓扑需要连接到代理服务器才可以访问 Internet 服务，则可以在首次运行期间或在“设置”中对它进行配置。</span><span class="sxs-lookup"><span data-stu-id="994f0-139">**Proxy servers:** If your topology requires a connection to a proxy server to reach Internet services, then you can configure it during first run, or in Settings.</span></span> <span data-ttu-id="994f0-140">代理凭据存储在 Surface Hub 会话中，只需设置一次。</span><span class="sxs-lookup"><span data-stu-id="994f0-140">Proxy credentials are stored across Surface Hub sessions and only need to be set once.</span></span> |

<span data-ttu-id="994f0-141">此外，还请注意 Surface Hub 要求打开以下端口：</span><span class="sxs-lookup"><span data-stu-id="994f0-141">Additionally, note that Surface Hub requires the following open ports:</span></span>
- <span data-ttu-id="994f0-142">HTTPS：443</span><span class="sxs-lookup"><span data-stu-id="994f0-142">HTTPS: 443</span></span>
- <span data-ttu-id="994f0-143">HTTP：80</span><span class="sxs-lookup"><span data-stu-id="994f0-143">HTTP: 80</span></span>
- <span data-ttu-id="994f0-144">NTP：123</span><span class="sxs-lookup"><span data-stu-id="994f0-144">NTP: 123</span></span>

<span data-ttu-id="994f0-145">如果您将 Surface Hub 与 Skype for Business 配合使用，您需要打开其他端口。</span><span class="sxs-lookup"><span data-stu-id="994f0-145">If you are using Surface Hub with Skype for Business, you will need to open additional ports.</span></span> <span data-ttu-id="994f0-146">请按照以下指南操作：</span><span class="sxs-lookup"><span data-stu-id="994f0-146">Please follow the guidance below:</span></span>
- <span data-ttu-id="994f0-147">如果您使用的是 Skype for Business Online，请参阅[Office 365 IP url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="994f0-147">If you use Skype for Business Online, see [Office 365 IP URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US).</span></span>
- <span data-ttu-id="994f0-148">如果您使用的是 Skype for Business 服务器，请参阅[skype For Business 服务器：内部服务器的端口和协议](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols)。</span><span class="sxs-lookup"><span data-stu-id="994f0-148">If you use Skype for Business Server, see [Skype for Business Server: Ports and protocols for internal servers](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols).</span></span> 
- <span data-ttu-id="994f0-149">如果您使用的是 Skype for Business Online 和 Skype for business 服务器的混合，则需要从[Office 365 IP url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)和 skype For business 服务器中打开所有记录的端口[：内部服务器的端口和协议](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="994f0-149">If you use a hybrid of Skype for Business Online and Skype for Business Server, you need to open all documented ports from [Office 365 IP URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US) and [Skype for Business Server: Ports and protocols for internal servers](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="994f0-150">Microsoft 收集诊断数据来帮助改善 Surface Hub 体验。</span><span class="sxs-lookup"><span data-stu-id="994f0-150">Microsoft collects diagnostic data to help improve your Surface Hub experience.</span></span> <span data-ttu-id="994f0-151">请将以下站点添加到允许列表：</span><span class="sxs-lookup"><span data-stu-id="994f0-151">Add these sites to your allow list:</span></span>
- <span data-ttu-id="994f0-152">诊断数据客户端终结点:</span><span class="sxs-lookup"><span data-stu-id="994f0-152">Diagnostic data client endpoint:</span></span> `https://vortex.data.microsoft.com/`
- <span data-ttu-id="994f0-153">诊断数据设置终结点:</span><span class="sxs-lookup"><span data-stu-id="994f0-153">Diagnostic data settings endpoint:</span></span> `https://settings.data.microsoft.com/`

### <span data-ttu-id="994f0-154">代理配置</span><span class="sxs-lookup"><span data-stu-id="994f0-154">Proxy configuration</span></span>

<span data-ttu-id="994f0-155">如果你的组织限制你网络上的计算机连接到 Internet，则需要向设备提供一组 URL 才能使用适用于企业的 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="994f0-155">If your organization restricts computers on your network from connecting to the Internet, there is a set of URLs that need to be available for devices to use Microsoft Store for Business.</span></span> <span data-ttu-id="994f0-156">某些适用于企业的 Microsoft Store 功能使用 Microsoft Store 应用和 Microsoft Store 服务。</span><span class="sxs-lookup"><span data-stu-id="994f0-156">Some of the Store for Business features use Microsoft Store app and Microsoft Store services.</span></span> <span data-ttu-id="994f0-157">设备在使用适用于企业的 Microsoft Store 时，无论是获取、安装还是更新应用，都需要访问这些 URL。</span><span class="sxs-lookup"><span data-stu-id="994f0-157">Devices using Store for Business – either to acquire, install, or update apps – will need access to these URLs.</span></span> <span data-ttu-id="994f0-158">如果使用代理服务器阻止流量，则你的配置需要允许这些 URL：</span><span class="sxs-lookup"><span data-stu-id="994f0-158">If you use a proxy server to block traffic, your configuration needs to allow these URLs:</span></span>

- <span data-ttu-id="994f0-159">login.live.com</span><span class="sxs-lookup"><span data-stu-id="994f0-159">login.live.com</span></span>
- <span data-ttu-id="994f0-160">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="994f0-160">login.windows.net</span></span>
- <span data-ttu-id="994f0-161">account.live.com</span><span class="sxs-lookup"><span data-stu-id="994f0-161">account.live.com</span></span>
- <span data-ttu-id="994f0-162">clientconfig.passport.net</span><span class="sxs-lookup"><span data-stu-id="994f0-162">clientconfig.passport.net</span></span>
- <span data-ttu-id="994f0-163">windowsphone.com</span><span class="sxs-lookup"><span data-stu-id="994f0-163">windowsphone.com</span></span>
- <span data-ttu-id="994f0-164">\*.wns.windows.com</span><span class="sxs-lookup"><span data-stu-id="994f0-164">\*.wns.windows.com</span></span>
- <span data-ttu-id="994f0-165">\*.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="994f0-165">\*.microsoft.com</span></span>
- <span data-ttu-id="994f0-166">www.msftncsi.com（Windows 10 版本 1607 之前的版本）</span><span class="sxs-lookup"><span data-stu-id="994f0-166">www.msftncsi.com (prior to Windows 10, version 1607)</span></span>
- <span data-ttu-id="994f0-167">www.msftconnecttest.com/connecttest.txt（从 Windows 10 版本 1607 开始替换 www.msftncsi.com）</span><span class="sxs-lookup"><span data-stu-id="994f0-167">www.msftconnecttest.com/connecttest.txt (replaces www.msftncsi.com starting with Windows 10, version 1607)</span></span>


## <span data-ttu-id="994f0-168">与其他管理员合作</span><span class="sxs-lookup"><span data-stu-id="994f0-168">Work with other admins</span></span>

<span data-ttu-id="994f0-169">Surface Hub 可与某些其他产品和服务交互。</span><span class="sxs-lookup"><span data-stu-id="994f0-169">Surface Hub interacts with a few different products and services.</span></span> <span data-ttu-id="994f0-170">可能有多人在环境中支持不同的产品，具体取决于组织的规模。</span><span class="sxs-lookup"><span data-stu-id="994f0-170">Depending on the size of your organization, there could be multiple people supporting different products in your environment.</span></span> <span data-ttu-id="994f0-171">你需要将管理 Exchange、Active Directory（或 Azure Active Directory）、移动设备管理 (MDM) 和网络资源的人员纳入 Surface Hub 部署的规划和准备工作中。</span><span class="sxs-lookup"><span data-stu-id="994f0-171">You'll want to include people who manage Exchange, Active Directory (or Azure Active Directory), mobile device management (MDM), and network resources in your planning and prep for Surface Hub deployments.</span></span> 


## <span data-ttu-id="994f0-172">创建和验证设备帐户</span><span class="sxs-lookup"><span data-stu-id="994f0-172">Create and verify device account</span></span>

<span data-ttu-id="994f0-173">设备帐户是 Surface Hub 用于显示其会议日历、加入 Skype for Business 通话、发送电子邮件和验证 Exchange（可选）的 Exchange 资源帐户。</span><span class="sxs-lookup"><span data-stu-id="994f0-173">A device account is an Exchange resource account that Surface Hub uses to display its meeting calendar, join Skype for Business calls, send email, and (optionally) to authenticate to Exchange.</span></span> <span data-ttu-id="994f0-174">有关详细信息，请参阅[创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="994f0-174">See [Create and test a device account](create-and-test-a-device-account-surface-hub.md) for details.</span></span>

<span data-ttu-id="994f0-175">创建设备帐户后，若要验证是否正确设置了该帐户，请运行 Surface Hub 设备帐户验证 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="994f0-175">After you've created your device account, to verify that it's setup correctly, run Surface Hub device account validation PowerShell scripts.</span></span> <span data-ttu-id="994f0-176">有关详细信息，请参阅本指南后面部分的[适用于 Surface Hub 的 PowerShell 脚本](appendix-a-powershell-scripts-for-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="994f0-176">For more information, see [PowerShell scripts for Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md) later in this guide.</span></span> 

 

## <span data-ttu-id="994f0-177">准备首次运行计划</span><span class="sxs-lookup"><span data-stu-id="994f0-177">Prepare for first-run program</span></span> 
<span data-ttu-id="994f0-178">开始[首次运行计划](first-run-program-surface-hub.md)之前，需要考虑几项内容。</span><span class="sxs-lookup"><span data-stu-id="994f0-178">There are a few more item to consider before you start the [first-run program](first-run-program-surface-hub.md).</span></span>  

### <span data-ttu-id="994f0-179">创建设置包（可选）</span><span class="sxs-lookup"><span data-stu-id="994f0-179">Create provisioning packages (optional)</span></span>
<span data-ttu-id="994f0-180">可以使用设置包添加证书、自定义设置和安装应用。</span><span class="sxs-lookup"><span data-stu-id="994f0-180">You can use provisioning packages to add certificates, customize settings and install apps.</span></span> <span data-ttu-id="994f0-181">有关详细信息，请参阅[创建设置包](provisioning-packages-for-certificates-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="994f0-181">See [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md) for details.</span></span> <span data-ttu-id="994f0-182">可以[在首次运行时安装设置包](first-run-program-surface-hub.md#first-page)。</span><span class="sxs-lookup"><span data-stu-id="994f0-182">You can [install provisioning packages at first-run](first-run-program-surface-hub.md#first-page).</span></span>

### <span data-ttu-id="994f0-183">设置管理员组</span><span class="sxs-lookup"><span data-stu-id="994f0-183">Set up admin groups</span></span>
<span data-ttu-id="994f0-184">可使用设备上的“设置”应用在本地配置每个 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="994f0-184">Every Surface Hub can be configured locally using the Settings app on the device.</span></span> <span data-ttu-id="994f0-185">若要防止未经授权的用户更改设置，“设置”应用要求使用管理员凭据打开该应用。</span><span class="sxs-lookup"><span data-stu-id="994f0-185">To prevent unauthorized users from changing settings, the Settings app requires admin credentials to open the app.</span></span> <span data-ttu-id="994f0-186">有关如何设置和管理管理员组的详细信息，请参阅[管理员组管理](admin-group-management-for-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="994f0-186">See [Admin group management](admin-group-management-for-surface-hub.md) for details on how admin groups are set up and managed.</span></span> <span data-ttu-id="994f0-187">你将[在首次运行时为设备设置管理员](first-run-program-surface-hub.md#setup-admins)。</span><span class="sxs-lookup"><span data-stu-id="994f0-187">You will [set up admins for the device at first run](first-run-program-surface-hub.md#setup-admins).</span></span>

### <span data-ttu-id="994f0-188">查看并填写 Surface Hub 设置工作表（可选）</span><span class="sxs-lookup"><span data-stu-id="994f0-188">Review and complete Surface Hub setup worksheet (optional)</span></span>
<span data-ttu-id="994f0-189">在为 Surface Hub 实行首次运行计划时，需要提供一些信息。</span><span class="sxs-lookup"><span data-stu-id="994f0-189">When you go through the first-run program for your Surface Hub, there's some information that you'll need to supply.</span></span> <span data-ttu-id="994f0-190">设置工作表总结了此类信息，并提供要实行首次运行计划所需的特定于环境的信息。</span><span class="sxs-lookup"><span data-stu-id="994f0-190">The setup worksheet summarizes that info, and provides lists of environment-specific info that you'll need when you go through the first-run program.</span></span> <span data-ttu-id="994f0-191">有关详细信息，请参阅[设置工作表](setup-worksheet-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="994f0-191">For more information, see [Setup worksheet](setup-worksheet-surface-hub.md).</span></span>


## <span data-ttu-id="994f0-192">本部分内容</span><span class="sxs-lookup"><span data-stu-id="994f0-192">In this section</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="994f0-193">主题</span><span class="sxs-lookup"><span data-stu-id="994f0-193">Topic</span></span></th>
<th align="left"><span data-ttu-id="994f0-194">描述</span><span class="sxs-lookup"><span data-stu-id="994f0-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="create-and-test-a-device-account-surface-hub.md" data-raw-source="[Create and test a device account](create-and-test-a-device-account-surface-hub.md)"><span data-ttu-id="994f0-195">创建和测试设备帐户</span><span class="sxs-lookup"><span data-stu-id="994f0-195">Create and test a device account</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="994f0-196">本主题介绍了如何创建和测试 Surface Hub 用于与 Skype 进行通信的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="994f0-196">This topic introduces how to create and test the device account that Surface Hub uses to communicate with and Skype.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="provisioning-packages-for-certificates-surface-hub.md" data-raw-source="[Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md)"><span data-ttu-id="994f0-197">创建设置包</span><span class="sxs-lookup"><span data-stu-id="994f0-197">Create provisioning packages</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="994f0-198">对于 Windows 10，使用注册表或内容服务平台 (CSP) 的设置可通过设置包进行配置。</span><span class="sxs-lookup"><span data-stu-id="994f0-198">For Windows 10, settings that use the registry or a content services platform (CSP) can be configured using provisioning packages.</span></span> <span data-ttu-id="994f0-199">也可使用预配在首次运行期间添加证书。</span><span class="sxs-lookup"><span data-stu-id="994f0-199">You can also add certificates during first run using provisioning.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="admin-group-management-for-surface-hub.md" data-raw-source="[Admin group management](admin-group-management-for-surface-hub.md)"><span data-ttu-id="994f0-200">管理员组管理</span><span class="sxs-lookup"><span data-stu-id="994f0-200">Admin group management</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="994f0-201">通过在 Surface Hub 上打开“设置”应用，可分别配置每台设备。</span><span class="sxs-lookup"><span data-stu-id="994f0-201">Every Surface Hub can be configured individually by opening the Settings app on the device.</span></span> <span data-ttu-id="994f0-202">但是，若要防止不是管理员的用户更改设置，“设置”应用需要管理员凭据才可以打开该应用并更改设置。</span><span class="sxs-lookup"><span data-stu-id="994f0-202">However, to prevent people who are not administrators from changing the settings, the Settings app requires administrator credentials to open the app and change settings.</span></span></p>
<p><span data-ttu-id="994f0-203">“设置”应用需要本地管理员凭据才可以打开该应用。</span><span class="sxs-lookup"><span data-stu-id="994f0-203">The Settings app requires local administrator credentials to open the app.</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="994f0-204">详细信息</span><span class="sxs-lookup"><span data-stu-id="994f0-204">More information</span></span>

- [<span data-ttu-id="994f0-205">博客文章：Surface Hub 和 Skype for Business 的受信任域列表</span><span class="sxs-lookup"><span data-stu-id="994f0-205">Blog post: Surface Hub and the Skype for Business Trusted Domain List</span></span>](https://blogs.technet.microsoft.com/y0av/2017/10/25/95/)
- [<span data-ttu-id="994f0-206">博客文章：多域环境中的 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="994f0-206">Blog post: Surface Hub in a Multi-Domain Environment</span></span>](https://blogs.technet.microsoft.com/y0av/2017/11/08/11/)
- [<span data-ttu-id="994f0-207">博客文章：为 Surface Hub 配置代理服务器</span><span class="sxs-lookup"><span data-stu-id="994f0-207">Blog post: Configuring a proxy for your Surface Hub</span></span>](https://blogs.technet.microsoft.com/y0av/2017/12/03/7/)

 

 






---
title: 设置工作表 (Surface Hub)
description: 当你完成预设置并已准备好为你的 Microsoft Surface Hub 启动首次设置时，请确保你拥有本部分中列出的所有信息。
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: 设置工作表, 预设置, 首次设置
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831951"
---
# <span data-ttu-id="5b2e1-104">设置工作表 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="5b2e1-104">Setup worksheet (Surface Hub)</span></span>


<span data-ttu-id="5b2e1-105">当你完成预设置并已准备好为你的 Microsoft Surface Hub 启动首次设置时，请确保你拥有本部分中列出的所有信息。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-105">When you've finished pre-setup and are ready to start first-time setup for your Microsoft Surface Hub, make sure you have all the information listed in this section.</span></span>

<span data-ttu-id="5b2e1-106">应当为需要配置的每个 Surface Hub 都填写一个列表，尽管某些信息（如代理信息或域凭据）可用于所有 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-106">You should fill out one list for each Surface Hub you need to configure, although some information can be used on all Surface Hubs, like the proxy information or domain credentials.</span></span> <span data-ttu-id="5b2e1-107">其中某些信息可能不需要，具体取决于决定配置你的设备的方式或者针对组织的基础结构配置环境的方式。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-107">Some of this information may not be needed, depending on how you've decided to configure your device, or depending on how the environment is configured for your organization's infrastructure.</span></span>

<table>
<tr>
<th><span data-ttu-id="5b2e1-108">属性</span><span class="sxs-lookup"><span data-stu-id="5b2e1-108">Property</span></span></th>
<th><span data-ttu-id="5b2e1-109">用途</span><span class="sxs-lookup"><span data-stu-id="5b2e1-109">What this is used for</span></span></th>
<th><span data-ttu-id="5b2e1-110">示例</span><span class="sxs-lookup"><span data-stu-id="5b2e1-110">Example</span></span></th>
<th><span data-ttu-id="5b2e1-111">实际值</span><span class="sxs-lookup"><span data-stu-id="5b2e1-111">Actual value</span></span></th>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-112">代理信息</span><span class="sxs-lookup"><span data-stu-id="5b2e1-112">Proxy information</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-113">如果你的网络使用代理进行网络和/或 Internet 访问，必须提供脚本或服务器/端口信息。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-113">If your network uses a proxy for network and/or Internet access, you must provide a script or server/port information.</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-114">代理脚本：</span><span class="sxs-lookup"><span data-stu-id="5b2e1-114">Proxy script:</span></span> <code>http://contoso/proxy.pa</code> </br>
- <span data-ttu-id="5b2e1-115">或 -</span><span class="sxs-lookup"><span data-stu-id="5b2e1-115">OR -</span></span> </br>
<span data-ttu-id="5b2e1-116">服务器和端口信息：10.10.10.100，端口 80</span><span class="sxs-lookup"><span data-stu-id="5b2e1-116">Server and port info: 10.10.10.100, port 80</span></span>
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-117">无线网络凭据（用户名和密码）</span><span class="sxs-lookup"><span data-stu-id="5b2e1-117">Wireless network credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-118">如果你决定将设备连接到 WLAN，而无线网络要求用户凭据。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-118">If you decide to connect your device to Wi-Fi, and your wireless network requires user credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-119">admin1@contoso.com，#MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="5b2e1-119">admin1@contoso.com, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-120">设备帐户 UPN 或域\用户名以及设备帐户密码</span><span class="sxs-lookup"><span data-stu-id="5b2e1-120">Device account UPN or Domain\username and device account password</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-121">这是用户主体名称 (UPN) 或域\用户名以及设备帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-121">This is the User Principal Name (UPN) or the domain\username, and the password of the device account.</span></span> <span data-ttu-id="5b2e1-122">邮件、日历和 Skype for Business，具体取决于兼容的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-122">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span></p>
</td>
<td>
<p> <span data-ttu-id="5b2e1-123">UPN：ConfRoom15@contoso.com，#Passw0rd1</span><span class="sxs-lookup"><span data-stu-id="5b2e1-123">UPN: ConfRoom15@contoso.com, #Passw0rd1</span></span> </br>
- <span data-ttu-id="5b2e1-124">或 -</span><span class="sxs-lookup"><span data-stu-id="5b2e1-124">OR -</span></span> <br> 
<span data-ttu-id="5b2e1-125">域和用户名：CONTOSO\ConfRoom15，#Passw0rd1</span><span class="sxs-lookup"><span data-stu-id="5b2e1-125">Domain and username: CONTOSO\ConfRoom15, #Passw0rd1</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-126">设备帐户 Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="5b2e1-126">Device account Microsoft Exchange server</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-127">这是设备帐户的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-127">This is the device account's Exchange server.</span></span>
<span data-ttu-id="5b2e1-128">邮件、日历和 Skype for Business，具体取决于兼容的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-128">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span>
<span data-ttu-id="5b2e1-129">为了使邮件和日历正常工作，设备帐户必须具有有效的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-129">For mail and calendar to work, the device account must have a valid Exchange server.</span></span> <span data-ttu-id="5b2e1-130">设备将尝试自动查找此项。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-130">The device will try to find this automatically.</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-131">outlook.office365.com</span><span class="sxs-lookup"><span data-stu-id="5b2e1-131">outlook.office365.com</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-132">设备帐户会话初始协议 (SIP) 地址</span><span class="sxs-lookup"><span data-stu-id="5b2e1-132">Device account Session Initiation Protocol (SIP) address</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-133">这是设备帐户的 Skype for Business SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-133">This is the device account's Skype for Business SIP address.</span></span>
<span data-ttu-id="5b2e1-134">邮件、日历和 Skype for Business，具体取决于兼容的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-134">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span>
<span data-ttu-id="5b2e1-135">为了使 Skype for Business 正常工作，设备帐户必须具有有效的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-135">For Skype for Business to work, the device account must have a valid SIP address.</span></span> <span data-ttu-id="5b2e1-136">设备将尝试自动查找此项。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-136">The device will try to find this automatically.</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-137">sip：ConfRoom15@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b2e1-137">sip: ConfRoom15@contoso.com</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-138">友好名称</span><span class="sxs-lookup"><span data-stu-id="5b2e1-138">Friendly name</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-139">设备的友好名称是指用户将在尝试以无线方式连接到 Surface Hub 时看到的广播名称。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-139">The friendly name of the device is the broadcast name that people will see when they try to wirelessly connect to the Surface Hub.</span></span> <span data-ttu-id="5b2e1-140">此名称将突出显示在 Surface Hub 的屏幕上。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-140">This name will be displayed prominently on the Surface Hub's screen.</span></span>
<span data-ttu-id="5b2e1-141">我们建议所选的友好名称可识别且唯一，以便用户在尝试连接时可以区分不同的 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-141">We suggest that the friendly name you choose is recognizable and unique so that people can distinguish one Surface Hub from another when trying to connect.</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-142">会议室 15</span><span class="sxs-lookup"><span data-stu-id="5b2e1-142">Conference Room 15</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-143">设备名称</span><span class="sxs-lookup"><span data-stu-id="5b2e1-143">Device name</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-144">设备名称既是将用于域加入的名称，也是你将在设备注册到 MDM 中时在 MDM 提供程序中看到的标识。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-144">The device name is the name that will be used for domain join, and is the identity you will see in your MDM provider if the device is enrolled into MDM.</span></span>
<span data-ttu-id="5b2e1-145">所选的设备名称不得与用户的 Active Directory 域上的任何其他设备同名（如果你决定域加入设备）。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-145">The device name you choose must not be the same name as any other device on the user’s Active Directory domain (if you decide to domain join the device).</span></span> <span data-ttu-id="5b2e1-146">如果设备名称不唯一，该设备将无法加入域。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-146">The device cannot join the domain if its name is not unique.</span></span>
</p>
</td>
<td>
<p><span data-ttu-id="5b2e1-147">confroom15</span><span class="sxs-lookup"><span data-stu-id="5b2e1-147">confroom15</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="5b2e1-148">如果你要加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="5b2e1-148">IF YOU'RE JOINING AZURE AD</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-149">Azure AD 租户用户凭据（用户名和密码）</span><span class="sxs-lookup"><span data-stu-id="5b2e1-149">Azure AD tenant user credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-150">如果你决定让你的 Azure Active Directory (Azure AD) 组织中的用户成为设备管理员，将需要加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-150">If you decide to have people in your Azure Active Directory (Azure AD) organization become admins on the device, then you'll need to join Azure AD.</span></span>
<span data-ttu-id="5b2e1-151">若要加入 Azure AD，将需要有效的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-151">To join Azure AD, you will need valid user credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-152">admin1@contoso.com，#MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="5b2e1-152">admin1@contoso.com, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="5b2e1-153">如果你要加入域</span><span class="sxs-lookup"><span data-stu-id="5b2e1-153">IF YOU'RE JOINING A DOMAIN</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-154">要加入的域</span><span class="sxs-lookup"><span data-stu-id="5b2e1-154">Domain to join</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-155">这是将要加入的域，这样所选的安全组即可成为设备的管理员。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-155">This is the domain you will need to join so that a security group of your choice can be admins for the device.</span></span>
<span data-ttu-id="5b2e1-156">你可能需要完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-156">You may need the fully qualified domain name (FQDN).</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-157">contoso（短名称）或 contoso.corp.com (FQDN)</span><span class="sxs-lookup"><span data-stu-id="5b2e1-157">contoso (short name) OR contoso.corp.com (FQDN)</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-158">域帐户凭据（用户名和密码）</span><span class="sxs-lookup"><span data-stu-id="5b2e1-158">Domain account credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-159">除非你提供足够的帐户凭据来加入域，否则你将无法加入域。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-159">A domain can't be joined unless you provide sufficient account credentials to join the domain.</span></span> <span data-ttu-id="5b2e1-160">在提供要加入的域以及要加入该域所需的凭据后，所选的安全组可以更改设备上的设置。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-160">Once you provide a domain to join and credentials to join the domain, then a security group of your choice can change settings on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-161">admin1，#MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="5b2e1-161">admin1, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-162">管理员安全组别名</span><span class="sxs-lookup"><span data-stu-id="5b2e1-162">Admin security group alias</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-163">这是你的 Active Directory (AD) 中的安全组；此安全组的任何成员都可以更改设备上的设置。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-163">This is a security group in your Active Directory (AD); any members of this security group can change settings on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-164">SurfaceHubAdmins</span><span class="sxs-lookup"><span data-stu-id="5b2e1-164">SurfaceHubAdmins</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="5b2e1-165">如果你使用的是本地管理员</span><span class="sxs-lookup"><span data-stu-id="5b2e1-165">IF YOU'RE USING A LOCAL ADMIN</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-166">本地管理员帐户凭据（用户名和密码）</span><span class="sxs-lookup"><span data-stu-id="5b2e1-166">Local admin account credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-167">如果你决定不加入 AD 域或 Azure AD，你可以在设备上创建本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-167">If you decide not to join an AD domain or Azure AD, you can create a local admin account on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-168">admin1，#MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="5b2e1-168">admin1, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="5b2e1-169">如果你需要安装证书或应用</span><span class="sxs-lookup"><span data-stu-id="5b2e1-169">IF YOU NEED TO INSTALL CERTIFICATES OR APPS</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="5b2e1-170">USB 驱动器</span><span class="sxs-lookup"><span data-stu-id="5b2e1-170">USB drive</span></span></p>
</td>
<td>
<p><span data-ttu-id="5b2e1-171">如果你在首次运行之前知道自己想要安装证书或通用应用，请按照<a href="provisioning-packages-for-certificates-surface-hub.md">创建设置包</a>中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-171">If you know before first run that you want to install certificates or universal apps, follow the steps in <a href="provisioning-packages-for-certificates-surface-hub.md">Create provisioning packages</a>.</span></span> <span data-ttu-id="5b2e1-172">你的设置包将在 USB 驱动器上创建。</span><span class="sxs-lookup"><span data-stu-id="5b2e1-172">Your provisioning packages will be created on a USB drive.</span></span></p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 






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
# 设置工作表 (Surface Hub)


当你完成预设置并已准备好为你的 Microsoft Surface Hub 启动首次设置时，请确保你拥有本部分中列出的所有信息。

应当为需要配置的每个 Surface Hub 都填写一个列表，尽管某些信息（如代理信息或域凭据）可用于所有 Surface Hub。 其中某些信息可能不需要，具体取决于决定配置你的设备的方式或者针对组织的基础结构配置环境的方式。

<table>
<tr>
<th>属性</th>
<th>用途</th>
<th>示例</th>
<th>实际值</th>
</tr>
<tr>
<td>
<p>代理信息</p>
</td>
<td>
<p>如果你的网络使用代理进行网络和/或 Internet 访问，必须提供脚本或服务器/端口信息。</p>
</td>
<td>
<p>代理脚本： <code>http://contoso/proxy.pa</code> </br>
- 或 - </br>
服务器和端口信息：10.10.10.100，端口 80
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>无线网络凭据（用户名和密码）</p>
</td>
<td>
<p>如果你决定将设备连接到 WLAN，而无线网络要求用户凭据。</p>
</td>
<td>
<p>admin1@contoso.com，#MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>设备帐户 UPN 或域\用户名以及设备帐户密码</p>
</td>
<td>
<p>这是用户主体名称 (UPN) 或域\用户名以及设备帐户的密码。 邮件、日历和 Skype for Business，具体取决于兼容的设备帐户。</p>
</td>
<td>
<p> UPN：ConfRoom15@contoso.com，#Passw0rd1 </br>
- 或 - <br> 
域和用户名：CONTOSO\ConfRoom15，#Passw0rd1</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>设备帐户 Microsoft Exchange Server</p>
</td>
<td>
<p>这是设备帐户的 Exchange Server。
邮件、日历和 Skype for Business，具体取决于兼容的设备帐户。
为了使邮件和日历正常工作，设备帐户必须具有有效的 Exchange Server。 设备将尝试自动查找此项。</p>
</td>
<td>
<p>outlook.office365.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>设备帐户会话初始协议 (SIP) 地址</p>
</td>
<td>
<p>这是设备帐户的 Skype for Business SIP 地址。
邮件、日历和 Skype for Business，具体取决于兼容的设备帐户。
为了使 Skype for Business 正常工作，设备帐户必须具有有效的 SIP 地址。 设备将尝试自动查找此项。</p>
</td>
<td>
<p>sip：ConfRoom15@contoso.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>友好名称</p>
</td>
<td>
<p>设备的友好名称是指用户将在尝试以无线方式连接到 Surface Hub 时看到的广播名称。 此名称将突出显示在 Surface Hub 的屏幕上。
我们建议所选的友好名称可识别且唯一，以便用户在尝试连接时可以区分不同的 Surface Hub。</p>
</td>
<td>
<p>会议室 15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>设备名称</p>
</td>
<td>
<p>设备名称既是将用于域加入的名称，也是你将在设备注册到 MDM 中时在 MDM 提供程序中看到的标识。
所选的设备名称不得与用户的 Active Directory 域上的任何其他设备同名（如果你决定域加入设备）。 如果设备名称不唯一，该设备将无法加入域。
</p>
</td>
<td>
<p>confroom15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>如果你要加入 Azure AD</b></p>
</td>
</tr>
<tr>
<td>
<p>Azure AD 租户用户凭据（用户名和密码）</p>
</td>
<td>
<p>如果你决定让你的 Azure Active Directory (Azure AD) 组织中的用户成为设备管理员，将需要加入 Azure AD。
若要加入 Azure AD，将需要有效的用户凭据。</p>
</td>
<td>
<p>admin1@contoso.com，#MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>如果你要加入域</b></p>
</td>
</tr>
<tr>
<td>
<p>要加入的域</p>
</td>
<td>
<p>这是将要加入的域，这样所选的安全组即可成为设备的管理员。
你可能需要完全限定的域名 (FQDN)。</p>
</td>
<td>
<p>contoso（短名称）或 contoso.corp.com (FQDN)</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>域帐户凭据（用户名和密码）</p>
</td>
<td>
<p>除非你提供足够的帐户凭据来加入域，否则你将无法加入域。 在提供要加入的域以及要加入该域所需的凭据后，所选的安全组可以更改设备上的设置。</p>
</td>
<td>
<p>admin1，#MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>管理员安全组别名</p>
</td>
<td>
<p>这是你的 Active Directory (AD) 中的安全组；此安全组的任何成员都可以更改设备上的设置。</p>
</td>
<td>
<p>SurfaceHubAdmins</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>如果你使用的是本地管理员</b></p>
</td>
</tr>
<tr>
<td>
<p>本地管理员帐户凭据（用户名和密码）</p>
</td>
<td>
<p>如果你决定不加入 AD 域或 Azure AD，你可以在设备上创建本地管理员帐户。</p>
</td>
<td>
<p>admin1，#MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>如果你需要安装证书或应用</b></p>
</td>
</tr>
<tr>
<td>
<p>USB 驱动器</p>
</td>
<td>
<p>如果你在首次运行之前知道自己想要安装证书或通用应用，请按照<a href="provisioning-packages-for-certificates-surface-hub.md">创建设置包</a>中的步骤操作。 你的设置包将在 USB 驱动器上创建。</p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 






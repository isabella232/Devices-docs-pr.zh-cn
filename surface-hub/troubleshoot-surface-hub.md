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
# Microsoft Surface Hub 疑难解答


常见问题疑难解答，包括设置问题和 Exchange ActiveSync 错误。

[Surface Hub 硬件诊断工具](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab)包含交互式测试，可确认你的中心的基本功能是否按预期工作。 除了测试硬件，诊断还可测试资源帐户，验证其是否已针对你的环境适当配置。 如果遇到问题，可保存结果并与 Surface Hub 支持团队共享。 若要了解使用情况，请参阅[使用 Surface Hub 硬件诊断工具测试设备帐户](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun)。

下表中列出了常见问题和原因以及可能的修补程序。 [设置疑难解答](#setup-troubleshooting)部分包含设备上的问题列表，以及在首次运行体验期间可能遇到的多种问题类型。 [Exchange ActiveSync 错误](#exchange-activesync-errors)部分列出了设备在尝试与 Microsoft Exchange ActiveSync 服务器同步时可能遇到的常见错误。




## 设置疑难解答


本部分列出了原因和可能的修补程序，以帮助解决在设置 Microsoft Surface Hub 时可能发现的问题。

### 设备上

完成首次运行计划后 Surface Hub 上的问题的可能修补程序。

<table>
<tr>
<th>问题</th>
<th>原因</th>
<th>可能的修补程序</th>
</tr>
<tr>
<td rowspan="2">
<p>未收到自动接受/拒绝消息。</p>
</td>
<td>
<p>设备帐户未配置为自动接受/拒绝消息。</p>
</td>
<td>
<p>使用 PowerShell cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>。</p>
</td>
</tr>
<tr>
<td>
<p>设备帐户未配置为处理外部会议请求。</p>
</td>
<td>
<p>使用 PowerShell cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>。</p>
</td>
</tr>
<tr>
<td>
<p>日历未显示在欢迎屏幕上，或显示消息“约会过期(没有设置帐户)”。</p>
</td>
<td>
<p>此 Surface Hub 上未设置任何设备帐户。</p>
</td>
<td>
<p>通过“设置”预配设备帐户。</p>
</td>
</tr>
<tr>
<td>
<p>日历未显示在欢迎屏幕上，或显示消息“约会过期(预配过度)”。</p>
</td>
<td>
<p>设备帐户在过多的设备上预配。</p>
</td>
<td>
<p>将设备帐户从已预配到的其他设备中删除。 这可以通过使用 Exchange 管理端口来实现。</p>
</td>
</tr>
<tr>
<td>
<p>日历未显示在欢迎屏幕上，或显示消息“约会过期(凭据无效)”。</p>
</td>
<td>
<p>设备帐户的密码已过期，将不再有效。</p>
</td>
<td>
<p>在“设置”中更新帐户密码。 另请参阅<a href="password-management-for-surface-hub-device-accounts.md">密码管理</a>。</p>
</td>
</tr>
<tr>
<td>
<p>日历未显示在欢迎屏幕上，或显示消息“约会过期(帐户策略)”。</p>
</td>
<td>
<p>设备帐户使用的 ActiveSync 策略无效。</p>
</td>
<td>
<p>请确保设备帐户具有 ActiveSync 策略，其中 <code>PasswordEnabled == False</code>。</p>
</td>
</tr>
<tr>
<td>
<p>日历未显示在欢迎屏幕上，或显示消息“约会可能已过期”。</p>
</td>
<td>
<p>未启用 Exchange。</p>
</td>
<td>通过“设置”为 Exchange 服务启用设备帐户。 需确保你不仅拥有正确的 ActiveSync 策略集，而且还已安装 Exchange 服务正常运行所需的所有证书。</td>
</tr>
<tr>
<td>
<p>无法登录 Skype for Business。</p>
</td>
<td>
<p>设备帐户不具有会话初始协议 (SIP) 地址属性。</p>
</td>
<td>
<p>帐户不具有 SIP 地址属性，并且其用户主体名称 (UPN) 与实际的 SIP 地址不匹配。 帐户必须设置其 SIP 地址，或者应使用“设置”应用来添加 SIP 地址。</p>
</td>
</tr>
<tr>
<td>
<p>无法登录 Skype for Business。</p>
</td>
<td>
<p>设备帐户需要证书才能在 Skype for Business 中进行身份验证。</p>
</td>
<td>
<p>使用设置包安装适当的证书。</p>
</td>
</tr>
</table>
 

### 首次运行

Surface Hub 首次运行计划的问题的可能修补程序。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">问题</th>
<th align="left">原因</th>
<th align="left">可能的修补程序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>当系统请求域和用户名时找不到帐户。</p></td>
<td align="left"><p>域需采用完全限定的域名 (FQDN)。</p></td>
<td align="left"><p>应在域字段中提供 FQDN。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a>设备帐户页面，有关新帐户设置的问题

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">问题</th>
<th align="left">原因</th>
<th align="left">可能的修补程序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Azure AD 中找不到提供的帐户。</p></td>
<td align="left"><p>所提供帐户的用户主体名称 (UPN) 具有一个在 Azure AD 中无法访问的租户。</p></td>
<td align="left"><p>确保具有正常的 Internet 连接，并且设备可以访问 Microsoft Online Services。 确保输入的帐户凭据正确。</p></td>
</tr>
<tr class="even">
<td align="left"><p>无法访问指定的目录。</p></td>
<td align="left"><p>无法访问提供的帐户域所指定的域。</p></td>
<td align="left"><p>确保具有正常的网络连接，并且设备可以访问域控制器。 确保输入的帐户凭据正确。 也可以尝试改用 FQDN。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>无法自动发现 Exchange Server。</p></td>
<td align="left"><p>Exchange Server 未配置为自动发现。</p></td>
<td align="left"><p>为设备帐户启用 Exchange Server 的自动发现，或手动输入帐户的 Exchange Server 地址。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在输入帐户凭据后，未发现 SIP 地址。</p></td>
<td align="left"><p>Active Directory 或 Azure AD 中没有 SIP 地址项。</p></td>
<td align="left"><p>确保帐户已通过 Skype for Business 启用并且具有一个 SIP 地址。 如果没有，你可以在文本框中手动输入 SIP 地址。</p></td>
</tr>
</tbody>
</table>

 

### 设备帐户页面，有关现有帐户设置的问题

<table>
<tr>
<th>问题</th>
<th>原因</th>
<th>错误代码</th>
<th>可能的修补程序</th>
</tr>
<tr>
<td>
<p>帐户无法使用指定的凭据进行身份验证。</p>
</td>
<td>
<p>帐户未以 Active Directory (AD) 中的用户身份进行启用，需要密码来进行身份验证，或者密码不正确。</p>
</td>
<td>
<p>无</p>
</td>
<td>
<p>确保输入的凭据正确。 以 AD 中的用户身份启用帐户和添加密码，或设置 RoomMailboxPassword</p>. </td>
</tr>
<tr>
<td>
<p>在提供 Exchange Server 时，显示错误 0x800C0019。</p>
</td>
<td>
<p>设备帐户需要证书才能进行身份验证。</p>
</td>
<td>
<p>0x800C0019</p>
</td>
<td>
<p>使用设置包安装适当的证书。</p>
</td>
</tr>
<tr>
<td>
<p>设备帐户凭据对提供的 Exchange Server 无效。</p>
</td>
<td>
<p>提供的 Exchange Server 不在设备帐户邮箱的托管位置。</p>
</td>
<td>
<p>无</p>
</td>
<td>
<p>确保为设备帐户提供了正确的 Exchange 邮件服务器。</p>
</td>
</tr>
<tr>
<td>
<p>在尝试访问 Exchange Server 时 HTTP 超时。</p>
</td>
<td></td>
<td>
<p>0x80072EE2</p>
</td>
<td></td>
</tr>
<tr>
<td>
<p>找不到提供的 Exchange Server。</p>
</td>
<td>
<p>找不到提供的 Exchange Server。</p>
</td>
<td>
<p>无</p>
</td>
<td>
<p>确保具有正常的网络或 Internet 连接，并且所提供的 Exchange Server 正确。</p>
</td>
</tr>
<tr>
<td>
<p>不支持 http。</p>
</td>
<td>
<p>提供了采用 <i>http://</i>（而不是 <i>https://</i>）的 Exchange Server。</p>
</td>
<td>
<p>无</p>
</td>
<td>
<p>使用采用 https 的 Exchange Server。</p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p>用户登录到标题名为“此帐户有问题”的 ActiveSync 相关页面。</p>
</div>
<div> </div>
</td>
<td>
<p>ActiveSync 策略 PasswordEnabled 设置为 True（或 1）。</p>
</td>
<td>
<p>无</p>
</td>
<td>
<p>创建一个新的 ActiveSync 策略，其中 PasswordEnabled 设置为 False（或 0），然后将该策略应用到帐户。</p>
</td>
</tr>
<tr>
<td>
<p>Surface Hub 未连接到 Exchange。</p>
</td>
<td>
<p>无</p>
</td>
<td>
<p>确保具有正常的网络或 Internet 连接。</p>
</td>
</tr>
<tr>
<td>
<p>Exchange 返回一个指示错误的状态代码。</p>
</td>
<td>
<p>无</p>
</td>
<td>
<p>确保具有正常的网络或 Internet 连接。</p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a>首次运行，域加入页面问题

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">问题</th>
<th align="left">原因</th>
<th align="left">可能的修补程序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在尝试加入域时，错误会显示帐户无法使用指定的凭据进行身份验证。</p></td>
<td align="left"><p>提供的凭据不能加入指定域。</p></td>
<td align="left"><p>针对指定域中存在的帐户输入正确的凭据。</p></td>
</tr>
<tr class="even">
<td align="left"><p>从域指定某个组时，错误会显示在域上找不到该组。</p></td>
<td align="left"><p>该组已删除或不再存在。</p></td>
<td align="left"><p>验证该组是否存在于域中。</p></td>
</tr>
</tbody>
</table>

 

### 首次运行，Exchange Server 页面

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">问题</th>
<th align="left">原因</th>
<th align="left">可能的修补程序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>用户登录到此页面，然后要求提供 Exchange Server 地址。</p></td>
<td align="left"><p>Exchange Server 未配置为自动发现。</p></td>
<td align="left"><p>为设备帐户启用 Exchange Server 的自动发现，或手动输入帐户的 Exchange Server 地址。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a>首次运行，设备上的问题

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">问题</th>
<th align="left">原因</th>
<th align="left">错误代码</th>
<th align="left">可能的修补程序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>无法同步邮件/日历。</p></td>
<td align="left"><p>帐户不允许 Surface Hub 作为允许设备。</p></td>
<td align="left"><p>0x86000C1C</p></td>
<td align="left"><p>通过设置邮箱的 ActiveSyncAllowedDeviceIds 属性，将 Surface Hub 设备 ID 添加到 "允许列表" <strong> </strong> 。</p></td>
</tr>
</tbody>
</table>

 



 

## Exchange ActiveSync 错误


本部分列出了状态代码、映射、用户消息，以及管理员为解决 Exchange ActiveSync 错误可以执行的操作。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">十六进制代码</th>
<th align="left">映射</th>
<th align="left">用户友好消息</th>
<th align="left">管理员应采取的操作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>0x85010002</p></td>
<td align="left"><p>E_HTTP_DENIED</p></td>
<td align="left"><p>必须更新密码。</p></td>
<td align="left"><p>更新密码。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072EFD</p></td>
<td align="left"><p>WININET_E_CANNOT_CONNECT</p></td>
<td align="left"><p>目前无法连接到服务器。 请稍等片刻，然后重试，或检查帐户设置。</p></td>
<td align="left"><p>验证服务器名称是否正确且可访问。 验证设备是否已连接到网络。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C29</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_NOTPROVISIONED （策略不匹配）</p></td>
<td align="left"><p>使用了与 Surface Hub 不兼容的策略配置帐户。</p></td>
<td align="left"><p>为此帐户禁用 <strong>PasswordEnabled</strong> 策略。</p>
<p>如果在策略刷新间隔内帐户未收到任何服务器通知，我们有一个 bug，我们可能会出现策略错误。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C4C</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</p></td>
<td align="left"><p>帐户有过多的设备合作关系。</p></td>
<td align="left"><p>在服务器上删除一个或多个合作关系。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C0A</p></td>
<td align="left"><p>E_NEXUS_STATUS_SERVERERROR_RETRYLATER</p></td>
<td align="left"><p>目前无法连接到服务器。</p></td>
<td align="left"><p>在服务器重新联机之前，请等待。 如果问题仍然存在，请重新预配帐户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050003</p></td>
<td align="left"><p>E_CREDENTIALS_EXPIRED（凭据已过期，因此需要进行更新）</p></td>
<td align="left"><p>必须更新密码。</p></td>
<td align="left"><p>更新密码。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x8505000D</p></td>
<td align="left"><p>E_AIRSYNC_RESET_RETRY</p></td>
<td align="left"><p>目前无法连接到服务器。 等待一段时间，或检查帐户的设置。</p></td>
<td align="left"><p>这通常是一个暂时性错误，但如果问题仍然存在，请检查与帐户关联的设备数目，并删除其中一些设备（如果数目较大）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C16</p></td>
<td align="left"><p>E_NEXUS_STATUS_USER_HASNOMAILBOX</p></td>
<td align="left"><p>邮箱已迁移到其他服务器。</p></td>
<td align="left"><p>你应该从未看到此错误。 如果问题仍然存在，请重新预配帐户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010004</p></td>
<td align="left"><p>E_HTTP_FORBIDDEN</p></td>
<td align="left"><p>目前无法连接到服务器。 请稍后再试，或检查帐户的设置。</p></td>
<td align="left"><p>验证服务器名称，以确保其正确无误。 如果帐户使用基于证书的身份验证，请确保该证书仍有效，并更新它（如果无效）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85030028</p></td>
<td align="left"><p>E_ACTIVESYNC_PASSWORD_OR_GETCERT</p></td>
<td align="left"><p>帐户的密码或客户证书缺失或无效。</p></td>
<td align="left"><p>更新密码和/或部署客户端证书。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C2A</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_POLICYREFRESH</p></td>
<td align="left"><p>使用了与 Surface Hub 不兼容的策略配置帐户。</p></td>
<td align="left"><p>为此帐户禁用 PasswordEnabled 策略。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050002</p></td>
<td align="left"><p>E_CREDENTIALS_UNAVAILABLE</p></td>
<td align="left"><p>必须更新密码。</p></td>
<td align="left"><p>更新密码。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE2</p></td>
<td align="left"><p>WININET_E_TIMEOUT</p></td>
<td align="left"><p>网络不支持接收服务器通知所需的最小空闲超时，或者服务器处于离线状态。</p></td>
<td align="left"><p>验证服务器是否正在运行。 验证 NAT 设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85002004</p></td>
<td align="left"><p>E_FAIL_ABORT</p></td>
<td align="left"><p>此错误用于中断挂起的同步，将不会向用户公开。 该错误将显示在诊断数据中(如果强制执行交互式同步、删除帐户或更新其设置)。</p></td>
<td align="left"><p>无。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010017</p></td>
<td align="left"><p>E_HTTP_SERVICE_UNAVAIL</p></td>
<td align="left"><p>目前无法连接到服务器。 等待一段时间，或检查帐户的设置。</p></td>
<td align="left"><p>验证服务器名称，以确保其正确无误。 在服务器重新联机之前，请等待。 如果问题仍然存在，请重新预配帐户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C0D</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</p></td>
<td align="left"><p>目前无法连接到服务器。 等待一段时间，或检查帐户的设置。</p></td>
<td align="left"><p>验证服务器名称，以确保其正确无误。 在服务器重新联机之前，请等待。 如果问题仍然存在，请重新预配帐户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85030027</p></td>
<td align="left"><p>E_ACTIVESYNC_GETCERT</p></td>
<td align="left"><p>Exchange Server 需要证书。</p></td>
<td align="left"><p>在 Surface Hub 上导入相应的 EAS 证书。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C2B</p></td>
<td align="left"><p>E_NEXUS_STATUS_INVALID_POLICYKEY</p></td>
<td align="left"><p>使用了与 Surface Hub 不兼容的策略配置帐户。</p></td>
<td align="left"><p>为此帐户禁用 PasswordEnabled 策略。</p>
<p>如果在策略刷新间隔内帐户未收到任何服务器通知，我们有一个 bug，我们可能会出现策略错误。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010005</p></td>
<td align="left"><p>E_HTTP_NOT_FOUND</p></td>
<td align="left"><p>服务器名称无效。</p></td>
<td align="left"><p>验证服务器名称，以确保其正确无误。 如果问题仍然存在，请重新预配帐户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85010014</p></td>
<td align="left"><p>E_HTTP_SERVER_ERROR</p></td>
<td align="left"><p>无法连接到服务器。</p></td>
<td align="left"><p>验证服务器名称，以确保其正确无误。 触发同步，如果问题仍然存在，请重新预预配帐户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE7</p></td>
<td align="left"><p>WININET_E_NAME_NOT_RESOLVED</p></td>
<td align="left"><p>无法解析服务器名称或地址。</p></td>
<td align="left"><p>确保输入的服务器名称正确。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x8007052F</p></td>
<td align="left"><p>ERROR_ACCOUNT_RESTRICTION</p></td>
<td align="left"><p>自动发现 Exchange Server 时，应用可阻止登录的用户登录到该服务器的策略。</p></td>
<td align="left"><p>这是一个计时问题。 重新验证帐户凭据。 如果它们正确无误，请尝试重新预配。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x800C0019</p></td>
<td align="left"><p>INET_E_INVALID_CERTIFICATE</p></td>
<td align="left"><p>访问此资源所需的安全证书无效。</p></td>
<td align="left"><p>安装提供的设备帐户所需的正确 ActiveSync 证书。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072F0D</p></td>
<td align="left"><p>ININET_E_INVALID_CA</p></td>
<td align="left"><p>证书颁发机构无效或不正确。 无法自动发现 Exchange Server，因为缺少证书。</p></td>
<td align="left"><p>安装提供的设备帐户所需的正确 ActiveSync 证书。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80004005</p></td>
<td align="left"><p>E_FAIL</p></td>
<td align="left"><p>找不到提供的域。 无法自动发现 Exchange Server，且未在设置中提供它。</p></td>
<td align="left"><p>确保输入的域是 FQDN，且在 Exchange Server 文本框中输入的是 Exchange Server。</p></td>
</tr>
</tbody>
</table>

## 联系支持人员

如果有疑问或需要帮助，您可以[创建支持请求](https://support.microsoft.com/supportforbusiness/productselection)。


 
## 相关内容

- [Surface Hub 的 Miracast 连接疑难解答](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 






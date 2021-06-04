---
title: 更改 Microsoft Surface Hub 设备帐户
description: 可以在“设置”中更改设备帐户，以便添加帐户（如果尚未预配帐户），或更改已预配的帐户的任何属性。
ms.assetid: AFC43043-3319-44BC-9310-29B1F375E672
ms.reviewer: ''
manager: laurawi
keywords: 更改设备帐户, 更改属性, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: b90ef3e208f1e76e4b02fb9f49e3e24030947bc7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832103"
---
# 更改 Microsoft Surface Hub 设备帐户


可以在“设置”中更改设备帐户，以便添加帐户（如果尚未预配帐户），或更改已预配的帐户的任何属性。

##  <a name="details"></a>详细信息


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>用户主体名称</p></td>
<td align="left"><p>设备帐户的用户主体名称 (UPN)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>密码</p></td>
<td align="left"><p>设备帐户的相应密码。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>域</p></td>
<td align="left"><p>设备帐户所属的域。 无需将此字段提供给 Office 365 帐户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>用户名</p></td>
<td align="left"><p>设备帐户的用户名。 无需将此字段提供给 Office 365 帐户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>会话初始协议 (SIP) 地址</p></td>
<td align="left"><p>设备帐户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Exchange Server</p></td>
<td align="left"><p>这是设备帐户的 Exchange Server。 设备帐户的用户名和密码必须能够对指定的 Exchange Server 进行身份验证。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>启用 Exchange 服务</p></td>
<td align="left"><p>选中后，将启用所有 Exchange 服务（例如，欢迎屏幕上的日历，以电子邮件方式发送白板）。 如果未选中，将禁用所有 Exchange 服务且不需要提供 Exchange Server。</p></td>
</tr>
</tbody>
</table>

 

##  <a name="what-happened"></a>会发生什么情况？


UPN 和密码用于验证 AD 或 Azure AD 中的帐户。 如果验证失败，可能需要提供域和用户名。

使用提供的凭据，我们将尝试发现 SIP 地址。 如果找不到 SIP 地址，Skype for Business 会将 UPN 用作 SIP 地址。 如果这不是该帐户的 SIP 地址，将需要提供 SIP 地址。

如果设备找不到与登录凭据相关联的服务器，将需要提供 Exchange Server 地址。 Microsoft Surface Hub 将使用 Exchange Server 与 ActiveSync 进行交互，这会在设备上启用多个关键功能。

##  <a name="related-topics"></a>相关主题


[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)

 

 






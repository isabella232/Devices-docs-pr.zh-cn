---
title: Microsoft Exchange 属性 (Surface Hub)
description: 设备帐户的某些 Microsoft Exchange 属性必须设置为特定值才能在 Microsoft Surface Hub 上获得最佳的会议体验。
ms.assetid: 3E84393B-C425-45BF-95A6-D6502BA1BF29
ms.reviewer: ''
manager: laurawi
keywords: Microsoft Exchange 属性, 设备帐户, Surface Hub, Windows PowerShell cmdlet
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 8879762857146011f3e1a198b72a895bc6bf9473
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831847"
---
# Microsoft Exchange 属性 (Surface Hub)


设备帐户的某些 Microsoft Exchange 属性必须设置为特定值才能在 Microsoft Surface Hub 上获得最佳的会议体验。 下表列出了基于 PowerShell cmdlet 参数的各种 Exchange 属性、其用途以及它们应设置为的值。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
<th align="left">值</th>
<th align="left">影响</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AutomateProcessing</p></td>
<td align="left"><p>AutomateProcessing 参数启用或禁用邮箱上的日历处理。</p></td>
<td align="left"><p>AutoAccept</p></td>
<td align="left"><p>Surface Hub 将能够自动基于其可用性接受或拒绝会议请求。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AddOrganizerToSubject</p></td>
<td align="left"><p>AddOrganizerToSubject 参数指定是否将会议组织者的姓名用作会议请求的主题。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>欢迎屏幕将仅显示会议组织者一次（而不是将其同时显示为组织者和会议主题）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowConflicts</p></td>
<td align="left"><p>AllowConflicts 参数指定是否允许冲突的会议请求。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Surface Hub 将拒绝与另一个会议时间发生冲突的会议请求。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteComments</p></td>
<td align="left"><p>DeleteComments 参数指定是删除还是保留传入会议请求的邮件正文中的任何文本。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>会议的邮件正文可以保留，并且可以从 Surface Hub 中检索（如果你在会议期间需要它）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeleteSubject</p></td>
<td align="left"><p>DeleteSubject 参数指定是删除还是保留传入会议请求的主题。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>会议请求主题将显示在 Surface Hub 上。</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePrivateProperty</p></td>
<td align="left"><p>RemovePrivateProperty 参数指定是否清除传入会议请求的私有标志。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>在欢迎屏幕上，私有会议主题将显示为私有。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AddAdditionalResponse</p></td>
<td align="left"><p>AddAdditionalResponse 参数指定在响应会议请求时是否会从资源邮箱发送其他信息。</p></td>
<td align="left"><p>$True</p></td>
<td align="left"><p>向会议请求发送响应时，自定义文本将在响应中提供。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AdditionalResponse</p></td>
<td align="left"><p>AdditionalResponse 参数指定为响应会议请求而要包含的其他信息。</p>
<div class="alert">
<strong>注意 </strong> 除非将 AddAdditionalResponse 设置为 $True，否则将不会发送此文本。
</div>
<div>
 
</div></td>
<td align="left"><p>（可选）其他响应可用来告知用户如何使用 Surface Hub，或将其指向资源。</p></td>
<td align="left"><p>可通过添加附加响应消息来为用户提供关于如何在会议中使用 Surface Hub 的介绍。</p></td>
</tr>
</tbody>
</table>

 

 

 






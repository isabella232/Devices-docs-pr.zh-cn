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
# <span data-ttu-id="8ef0c-104">Microsoft Exchange 属性 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="8ef0c-104">Microsoft Exchange properties (Surface Hub)</span></span>


<span data-ttu-id="8ef0c-105">设备帐户的某些 Microsoft Exchange 属性必须设置为特定值才能在 Microsoft Surface Hub 上获得最佳的会议体验。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-105">Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub.</span></span> <span data-ttu-id="8ef0c-106">下表列出了基于 PowerShell cmdlet 参数的各种 Exchange 属性、其用途以及它们应设置为的值。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-106">The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8ef0c-107">属性</span><span class="sxs-lookup"><span data-stu-id="8ef0c-107">Property</span></span></th>
<th align="left"><span data-ttu-id="8ef0c-108">描述</span><span class="sxs-lookup"><span data-stu-id="8ef0c-108">Description</span></span></th>
<th align="left"><span data-ttu-id="8ef0c-109">值</span><span class="sxs-lookup"><span data-stu-id="8ef0c-109">Value</span></span></th>
<th align="left"><span data-ttu-id="8ef0c-110">影响</span><span class="sxs-lookup"><span data-stu-id="8ef0c-110">Impact</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8ef0c-111">AutomateProcessing</span><span class="sxs-lookup"><span data-stu-id="8ef0c-111">AutomateProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-112">AutomateProcessing 参数启用或禁用邮箱上的日历处理。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-112">The AutomateProcessing parameter enables or disables calendar processing on the mailbox.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-113">AutoAccept</span><span class="sxs-lookup"><span data-stu-id="8ef0c-113">AutoAccept</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-114">Surface Hub 将能够自动基于其可用性接受或拒绝会议请求。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-114">The Surface Hub will be able to automatically accept or decline meeting requests based on its availability.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8ef0c-115">AddOrganizerToSubject</span><span class="sxs-lookup"><span data-stu-id="8ef0c-115">AddOrganizerToSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-116">AddOrganizerToSubject 参数指定是否将会议组织者的姓名用作会议请求的主题。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-116">The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-117">$False</span><span class="sxs-lookup"><span data-stu-id="8ef0c-117">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-118">欢迎屏幕将仅显示会议组织者一次（而不是将其同时显示为组织者和会议主题）。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-118">The welcome screen will not show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8ef0c-119">AllowConflicts</span><span class="sxs-lookup"><span data-stu-id="8ef0c-119">AllowConflicts</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-120">AllowConflicts 参数指定是否允许冲突的会议请求。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-120">The AllowConflicts parameter specifies whether to allow conflicting meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-121">$False</span><span class="sxs-lookup"><span data-stu-id="8ef0c-121">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-122">Surface Hub 将拒绝与另一个会议时间发生冲突的会议请求。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-122">The Surface Hub will decline meeting requests that conflict with another meeting’s time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8ef0c-123">DeleteComments</span><span class="sxs-lookup"><span data-stu-id="8ef0c-123">DeleteComments</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-124">DeleteComments 参数指定是删除还是保留传入会议请求的邮件正文中的任何文本。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-124">The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-125">$False</span><span class="sxs-lookup"><span data-stu-id="8ef0c-125">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-126">会议的邮件正文可以保留，并且可以从 Surface Hub 中检索（如果你在会议期间需要它）。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-126">The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8ef0c-127">DeleteSubject</span><span class="sxs-lookup"><span data-stu-id="8ef0c-127">DeleteSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-128">DeleteSubject 参数指定是删除还是保留传入会议请求的主题。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-128">The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-129">$False</span><span class="sxs-lookup"><span data-stu-id="8ef0c-129">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-130">会议请求主题将显示在 Surface Hub 上。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-130">Meeting request subjects can be shown on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8ef0c-131">RemovePrivateProperty</span><span class="sxs-lookup"><span data-stu-id="8ef0c-131">RemovePrivateProperty</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-132">RemovePrivateProperty 参数指定是否清除传入会议请求的私有标志。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-132">The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-133">$False</span><span class="sxs-lookup"><span data-stu-id="8ef0c-133">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-134">在欢迎屏幕上，私有会议主题将显示为私有。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-134">Private meeting subjects will show as Private on the welcome screen.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8ef0c-135">AddAdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="8ef0c-135">AddAdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-136">AddAdditionalResponse 参数指定在响应会议请求时是否会从资源邮箱发送其他信息。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-136">The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-137">$True</span><span class="sxs-lookup"><span data-stu-id="8ef0c-137">$True</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-138">向会议请求发送响应时，自定义文本将在响应中提供。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-138">When a response is sent to a meeting request, custom text will be provided in the response.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8ef0c-139">AdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="8ef0c-139">AdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-140">AdditionalResponse 参数指定为响应会议请求而要包含的其他信息。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-140">The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="8ef0c-141">注意 </strong> 除非将 AddAdditionalResponse 设置为 $True，否则将不会发送此文本。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-141">Note</strong>This text will not be sent unless AddAdditionalResponse is set to $True.</span></span>
</div>
<div>
 
</div></td>
<td align="left"><p><span data-ttu-id="8ef0c-142">（可选）其他响应可用来告知用户如何使用 Surface Hub，或将其指向资源。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-142">Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ef0c-143">可通过添加附加响应消息来为用户提供关于如何在会议中使用 Surface Hub 的介绍。</span><span class="sxs-lookup"><span data-stu-id="8ef0c-143">Adding an additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 






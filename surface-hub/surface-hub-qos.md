---
title: 实现 Surface Hub 上的服务质量
ms.reviewer: ''
manager: laurawi
description: 了解如何在 Surface Hub 上配置 QoS。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830910"
---
# <span data-ttu-id="08654-103">在 Surface Hub 上实施服务质量（QoS）</span><span class="sxs-lookup"><span data-stu-id="08654-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="08654-104">服务质量（QoS）是网络技术的组合，允许管理员优化实时音频/视频和应用程序共享通信的体验。</span><span class="sxs-lookup"><span data-stu-id="08654-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="08654-105">在 Surface Hub 上[为 Skype For business 配置 QoS](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)可以使用[移动设备管理（MDM）提供程序](manage-settings-with-mdm-for-surface-hub.md)或通过[预配包](provisioning-packages-for-surface-hub.md)完成。</span><span class="sxs-lookup"><span data-stu-id="08654-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="08654-106">此过程介绍如何使用 Microsoft Intune 配置 Surface Hub 的 QoS。</span><span class="sxs-lookup"><span data-stu-id="08654-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="08654-107">在 Intune 中，[创建自定义策略](https://docs.microsoft.com/intune/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="08654-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    ![Intune 中自定义策略创建对话框的屏幕截图](images/qos-create.png)

2. <span data-ttu-id="08654-109">在 "**自定义 OMA URI 设置**" 中，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="08654-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="08654-110">对于你添加的每个设置，你将输入名称、描述（可选）、数据类型、OMA URI 和值。</span><span class="sxs-lookup"><span data-stu-id="08654-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    ![空白 OMA URI 设置对话框的屏幕截图](images/qos-setting.png)

3. <span data-ttu-id="08654-112">添加以下自定义 OMA URI 设置：</span><span class="sxs-lookup"><span data-stu-id="08654-112">Add the following custom OMA-URI settings:</span></span>

    <span data-ttu-id="08654-113">名称</span><span class="sxs-lookup"><span data-stu-id="08654-113">Name</span></span> | <span data-ttu-id="08654-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="08654-114">Data type</span></span> | <span data-ttu-id="08654-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="08654-115">OMA-URI</span></span><br><span data-ttu-id="08654-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="08654-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="08654-117">值</span><span class="sxs-lookup"><span data-stu-id="08654-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="08654-118">音频源端口</span><span class="sxs-lookup"><span data-stu-id="08654-118">Audio Source Port</span></span> | <span data-ttu-id="08654-119">字符串</span><span class="sxs-lookup"><span data-stu-id="08654-119">String</span></span> |  <span data-ttu-id="08654-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="08654-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="08654-121">从您的 Skype 管理员获取值</span><span class="sxs-lookup"><span data-stu-id="08654-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="08654-122">音频 DSCP</span><span class="sxs-lookup"><span data-stu-id="08654-122">Audio DSCP</span></span> | <span data-ttu-id="08654-123">整型</span><span class="sxs-lookup"><span data-stu-id="08654-123">Integer</span></span> |  <span data-ttu-id="08654-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="08654-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="08654-125">46</span><span class="sxs-lookup"><span data-stu-id="08654-125">46</span></span>
    <span data-ttu-id="08654-126">视频源端口</span><span class="sxs-lookup"><span data-stu-id="08654-126">Video Source Port</span></span> | <span data-ttu-id="08654-127">字符串</span><span class="sxs-lookup"><span data-stu-id="08654-127">String</span></span> |  <span data-ttu-id="08654-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="08654-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="08654-129">从您的 Skype 管理员获取值</span><span class="sxs-lookup"><span data-stu-id="08654-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="08654-130">视频 DSCP</span><span class="sxs-lookup"><span data-stu-id="08654-130">Video DSCP</span></span> | <span data-ttu-id="08654-131">整型</span><span class="sxs-lookup"><span data-stu-id="08654-131">Integer</span></span> |  <span data-ttu-id="08654-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="08654-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="08654-133">34</span><span class="sxs-lookup"><span data-stu-id="08654-133">34</span></span>
    <span data-ttu-id="08654-134">音频流程名称</span><span class="sxs-lookup"><span data-stu-id="08654-134">Audio Process Name</span></span> | <span data-ttu-id="08654-135">字符串</span><span class="sxs-lookup"><span data-stu-id="08654-135">String</span></span> |  <span data-ttu-id="08654-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="08654-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="08654-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="08654-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="08654-138">视频流程名称</span><span class="sxs-lookup"><span data-stu-id="08654-138">Video Process Name</span></span> | <span data-ttu-id="08654-139">字符串</span><span class="sxs-lookup"><span data-stu-id="08654-139">String</span></span> |  <span data-ttu-id="08654-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="08654-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="08654-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="08654-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="08654-142">每个**OMA URI**路径均以开头 `./Device/Vendor/MSFT/NetworkQoSPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="08654-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="08654-143">例如，音频源端口设置的完整路径将为 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 。</span><span class="sxs-lookup"><span data-stu-id="08654-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>




4. <span data-ttu-id="08654-144">创建策略后，将[其部署到 Surface Hub。](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span><span class="sxs-lookup"><span data-stu-id="08654-144">When the policy has been created, [deploy it to the Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span></span>


>[!WARNING]
><span data-ttu-id="08654-145">目前，你不能在[NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)中配置设置**IPProtocolMatchCondition** 。</span><span class="sxs-lookup"><span data-stu-id="08654-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="08654-146">如果配置了此设置，则该策略将无法应用。</span><span class="sxs-lookup"><span data-stu-id="08654-146">If this setting is configured, the policy will fail to apply.</span></span>
 

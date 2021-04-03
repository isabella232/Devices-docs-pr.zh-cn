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
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470480"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a><span data-ttu-id="019cd-103">在 Surface Hub 上 (服务质量) QoS 服务</span><span class="sxs-lookup"><span data-stu-id="019cd-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="019cd-104">QoS (Qo) S (是网络技术的组合，使管理员能够优化实时音频/视频和应用程序共享通信的体验。</span><span class="sxs-lookup"><span data-stu-id="019cd-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="019cd-105">在 Surface Hub 上配置适用于 Skype for Business 的 [QoS](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 可以使用你的移动设备管理 (MDM) [提供商](manage-settings-with-mdm-for-surface-hub.md) 或预配 [包完成](provisioning-packages-for-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="019cd-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="019cd-106">此过程介绍如何使用 Microsoft Intune 为 Surface Hub 配置 QoS。</span><span class="sxs-lookup"><span data-stu-id="019cd-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="019cd-107">在 Intune 中 [，创建自定义策略](https://docs.microsoft.com/intune/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="019cd-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    > [!div class="mx-imgBorder"]
    > ![Intune 中的自定义策略创建对话框的屏幕截图](images/qos-create.png)

2. <span data-ttu-id="019cd-109">在 **"自定义 OMA-URI 设置"中**，选择"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="019cd-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="019cd-110">对于你添加的每个设置，你将输入名称、描述 (可选) 、数据类型、OMA-URI 和值。</span><span class="sxs-lookup"><span data-stu-id="019cd-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    > [!div class="mx-imgBorder"]
    > ![空白 OMA-URI 设置对话框的屏幕截图](images/qos-setting.png)

3. <span data-ttu-id="019cd-112">添加以下自定义 OMA-URI 设置：</span><span class="sxs-lookup"><span data-stu-id="019cd-112">Add the following custom OMA-URI settings:</span></span><br/><br/>

    <span data-ttu-id="019cd-113">名称</span><span class="sxs-lookup"><span data-stu-id="019cd-113">Name</span></span> | <span data-ttu-id="019cd-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="019cd-114">Data type</span></span> | <span data-ttu-id="019cd-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="019cd-115">OMA-URI</span></span><br><span data-ttu-id="019cd-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="019cd-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="019cd-117">值</span><span class="sxs-lookup"><span data-stu-id="019cd-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="019cd-118">音频源端口</span><span class="sxs-lookup"><span data-stu-id="019cd-118">Audio Source Port</span></span> | <span data-ttu-id="019cd-119">字符串</span><span class="sxs-lookup"><span data-stu-id="019cd-119">String</span></span> |  <span data-ttu-id="019cd-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="019cd-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="019cd-121">从 Skype 管理员获取值</span><span class="sxs-lookup"><span data-stu-id="019cd-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="019cd-122">音频 DSCP</span><span class="sxs-lookup"><span data-stu-id="019cd-122">Audio DSCP</span></span> | <span data-ttu-id="019cd-123">整型</span><span class="sxs-lookup"><span data-stu-id="019cd-123">Integer</span></span> |  <span data-ttu-id="019cd-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="019cd-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="019cd-125">46</span><span class="sxs-lookup"><span data-stu-id="019cd-125">46</span></span>
    <span data-ttu-id="019cd-126">视频源端口</span><span class="sxs-lookup"><span data-stu-id="019cd-126">Video Source Port</span></span> | <span data-ttu-id="019cd-127">字符串</span><span class="sxs-lookup"><span data-stu-id="019cd-127">String</span></span> |  <span data-ttu-id="019cd-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="019cd-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="019cd-129">从 Skype 管理员获取值</span><span class="sxs-lookup"><span data-stu-id="019cd-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="019cd-130">视频 DSCP</span><span class="sxs-lookup"><span data-stu-id="019cd-130">Video DSCP</span></span> | <span data-ttu-id="019cd-131">整型</span><span class="sxs-lookup"><span data-stu-id="019cd-131">Integer</span></span> |  <span data-ttu-id="019cd-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="019cd-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="019cd-133">34</span><span class="sxs-lookup"><span data-stu-id="019cd-133">34</span></span>
    <span data-ttu-id="019cd-134">音频进程名称</span><span class="sxs-lookup"><span data-stu-id="019cd-134">Audio Process Name</span></span> | <span data-ttu-id="019cd-135">字符串</span><span class="sxs-lookup"><span data-stu-id="019cd-135">String</span></span> |  <span data-ttu-id="019cd-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="019cd-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="019cd-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="019cd-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="019cd-138">视频进程名称</span><span class="sxs-lookup"><span data-stu-id="019cd-138">Video Process Name</span></span> | <span data-ttu-id="019cd-139">字符串</span><span class="sxs-lookup"><span data-stu-id="019cd-139">String</span></span> |  <span data-ttu-id="019cd-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="019cd-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="019cd-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="019cd-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="019cd-142">每个 **OMA-URI** 路径以 `./Device/Vendor/MSFT/NetworkQoSPolicy` 开头。</span><span class="sxs-lookup"><span data-stu-id="019cd-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="019cd-143">例如，音频源端口设置的完整路径将为 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 。</span><span class="sxs-lookup"><span data-stu-id="019cd-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>

4. <span data-ttu-id="019cd-144">创建策略后，将其部署到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="019cd-144">When the policy has been created, deploy it to Surface Hub.</span></span>


>[!WARNING]
><span data-ttu-id="019cd-145">目前，您无法在[NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)中配置**IPProtocolMatchCondition**设置。</span><span class="sxs-lookup"><span data-stu-id="019cd-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="019cd-146">如果配置了此设置，则策略将无法应用。</span><span class="sxs-lookup"><span data-stu-id="019cd-146">If this setting is configured, the policy will fail to apply.</span></span>
 

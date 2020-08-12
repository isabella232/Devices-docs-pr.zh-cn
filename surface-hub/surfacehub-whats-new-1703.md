---
title: Windows 10 版本 1703 中 Surface Hub 的新增功能
description: Windows 10 版本 1703（创意者更新）为 Microsoft Surface Hub 带来了新功能。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 722309a6b018c32bde329cb7b2cdd68b859fc1ca
ms.sourcegitcommit: 8e809e8481023fe4421abcdaa1e055a6f2f74f5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924938"
---
# <span data-ttu-id="ba0e8-103">Windows 10 版本 1703 中 Microsoft Surface Hub 有哪些新增功能？</span><span class="sxs-lookup"><span data-stu-id="ba0e8-103">What's new in Windows 10, version 1703 for Microsoft Surface Hub?</span></span>

<span data-ttu-id="ba0e8-104">观看 Surface Hub 工程师 Jordan Marchese 介绍 Windows 10 版本 1703（创意者更新）的 Microsoft Surface Hub 更新。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-104">Watch Surface Hub engineer Jordan Marchese present updates to Microsoft Surface Hub with Windows 10, version 1703 (Creators Update).</span></span> 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

<span data-ttu-id="ba0e8-105">Windows 10 版本 1703 (也称为创意者更新)为 Microsoft Surface Hub 带来了以下更改。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-105">Windows 10, version 1703 (also called the Creators Update), introduces the following changes for Microsoft Surface Hub.</span></span>

## <span data-ttu-id="ba0e8-106">新设置</span><span class="sxs-lookup"><span data-stu-id="ba0e8-106">New settings</span></span>

<span data-ttu-id="ba0e8-107">为移动设备管理 (MDM) 和配置服务提供程序 (CSP) 添加了设置，以便扩展 Surface Hub 管理功能。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-107">Settings have been added to mobile device management (MDM) and configuration service providers (CSPs) to expand the Surface Hub management capabilities.</span></span> <span data-ttu-id="ba0e8-108">[新设置包括](manage-settings-with-mdm-for-surface-hub.md)：</span><span class="sxs-lookup"><span data-stu-id="ba0e8-108">[New settings include](manage-settings-with-mdm-for-surface-hub.md):</span></span>

- <span data-ttu-id="ba0e8-109">InBoxApps/SkypeForBusiness/DomainName</span><span class="sxs-lookup"><span data-stu-id="ba0e8-109">InBoxApps/SkypeForBusiness/DomainName</span></span>
- <span data-ttu-id="ba0e8-110">InBoxApps/Connect/AutoLaunch</span><span class="sxs-lookup"><span data-stu-id="ba0e8-110">InBoxApps/Connect/AutoLaunch</span></span>
- <span data-ttu-id="ba0e8-111">Properties/DefaultVolume</span><span class="sxs-lookup"><span data-stu-id="ba0e8-111">Properties/DefaultVolume</span></span>
- <span data-ttu-id="ba0e8-112">Properties/ScreenTimeout</span><span class="sxs-lookup"><span data-stu-id="ba0e8-112">Properties/ScreenTimeout</span></span>
- <span data-ttu-id="ba0e8-113">Properties/SessionTimeout</span><span class="sxs-lookup"><span data-stu-id="ba0e8-113">Properties/SessionTimeout</span></span>
- <span data-ttu-id="ba0e8-114">Properties/SleepTimeout</span><span class="sxs-lookup"><span data-stu-id="ba0e8-114">Properties/SleepTimeout</span></span>
- <span data-ttu-id="ba0e8-115">Properties/AllowSessionResume</span><span class="sxs-lookup"><span data-stu-id="ba0e8-115">Properties/AllowSessionResume</span></span>
- <span data-ttu-id="ba0e8-116">Properties/AllowAutoProxyAuth</span><span class="sxs-lookup"><span data-stu-id="ba0e8-116">Properties/AllowAutoProxyAuth</span></span>
- <span data-ttu-id="ba0e8-117">Properties/DisableSigninSuggestions</span><span class="sxs-lookup"><span data-stu-id="ba0e8-117">Properties/DisableSigninSuggestions</span></span>
- <span data-ttu-id="ba0e8-118">Properties/DoNotShowMyMeetingsAndFiles</span><span class="sxs-lookup"><span data-stu-id="ba0e8-118">Properties/DoNotShowMyMeetingsAndFiles</span></span>
- <span data-ttu-id="ba0e8-119">System/AllowStorageCard</span><span class="sxs-lookup"><span data-stu-id="ba0e8-119">System/AllowStorageCard</span></span>

<span data-ttu-id="ba0e8-120">以及基于新 [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) 和 [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) 的设置。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-120">Plus settings based on the new [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) and [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span></span>
</br>

## <span data-ttu-id="ba0e8-121">预配向导</span><span class="sxs-lookup"><span data-stu-id="ba0e8-121">Provisioning wizard</span></span>

<span data-ttu-id="ba0e8-122">易于使用的向导可帮助快速创建能应用于多个 Surface Hub 设备的预配包，并包括批量加入 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-122">An easy-to-use wizard helps you quickly create provisioning packages that you can apply to multiple Surface Hub devices, and includes bulk join to Azure Active Directory.</span></span> [<span data-ttu-id="ba0e8-123">了解如何为 Surface Hub 创建预配包。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-123">Learn how to create a provisioning package for Surface Hub.</span></span>](provisioning-packages-for-certificates-surface-hub.md)

![预配 Surface Hub 设备向导中的步骤](images/wcd-wizard.png)
    
## <span data-ttu-id="ba0e8-125">现有无线网络或 LAN 上的 Miracast</span><span class="sxs-lookup"><span data-stu-id="ba0e8-125">Miracast on your existing wireless network or LAN</span></span> 

<span data-ttu-id="ba0e8-126">Microsoft 的功能经过扩展，可以[通过本地网络发送 Miracast 流](miracast-over-infrastructure.md)，而不是通过直接无线链接来发送。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-126">Microsoft has extended the ability to [send a Miracast stream over a local network](miracast-over-infrastructure.md) rather than over a direct wireless link.</span></span> 
    
## <span data-ttu-id="ba0e8-127">云恢复</span><span class="sxs-lookup"><span data-stu-id="ba0e8-127">Cloud recovery</span></span>

<span data-ttu-id="ba0e8-128">重置 Surface Hub 设备时，能够立即从云中下载并安装操作系统出厂版本。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-128">When you reset a Surface Hub device, you now have the ability to download and install a factory build of the operating system from the cloud.</span></span> [<span data-ttu-id="ba0e8-129">了解关于云恢复的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-129">Learn more about cloud recovery.</span></span>](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
><span data-ttu-id="ba0e8-130">如果使用代理服务器，云恢复将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-130">Cloud recovery doesn't work if you use proxy servers.</span></span>
    
![重新安装](images/reinstall.png)
    
## <span data-ttu-id="ba0e8-132">结束会话</span><span class="sxs-lookup"><span data-stu-id="ba0e8-132">End session</span></span>

<span data-ttu-id="ba0e8-133">**我已完成**现为**结束会话**。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-133">**I'm done** is now **End session**.</span></span> [<span data-ttu-id="ba0e8-134">了解如何使用“结束会话”。</span><span class="sxs-lookup"><span data-stu-id="ba0e8-134">Learn how to use End session.</span></span>](finishing-your-surface-hub-meeting.md) 

![结束会话](images/end-session.png)



 

 

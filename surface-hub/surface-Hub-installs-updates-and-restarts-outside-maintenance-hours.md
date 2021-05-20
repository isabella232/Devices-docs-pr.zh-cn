---
title: Surface Hub 可能会安装更新，并在维护时间外重启
description: 有关自动更新Surface Hub疑难解答信息
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface hub， 维护窗口， 更新
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/15/2021
ms.openlocfilehash: 7df7857258c1baeedf4ff239eda17c66c93a531c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577022"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a><span data-ttu-id="7c3e9-104">Surface Hub 可能会安装更新，并在维护时间外重启</span><span class="sxs-lookup"><span data-stu-id="7c3e9-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="7c3e9-105">在某些情况下，Surface Hub在工作时间而不是常规维护时段安装更新。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="7c3e9-106">然后，如有必要，设备将重新启动。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="7c3e9-107">在此过程完成之前，无法使用该设备。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="7c3e9-108">对于缺少维护窗口，这不是预期行为。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="7c3e9-109">它仅在设备长时间过期时发生。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <a name="cause"></a><span data-ttu-id="7c3e9-110">原因</span><span class="sxs-lookup"><span data-stu-id="7c3e9-110">Cause</span></span>

<span data-ttu-id="7c3e9-111">为了确保Surface Hub在工作时间可用，Hub 配置为在 设置 (中定义的维护时段内执行管理功能，请参阅下面的"引用) 。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="7c3e9-112">在此维护期间，中心会自动通过 WUfB Windows Windows Update for Business (安装任何) 。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Update for Business (WUfB).</span></span> <span data-ttu-id="7c3e9-113">更新完成后，中心可能会重新启动。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="7c3e9-114">只有在设备打开但没有使用或保留Surface Hub才能在维护时段内安装更新。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="7c3e9-115">例如，如果 Surface Hub安排在持续 24 小时的会议，则计划安装的任何更新都将延迟，直到下次维护时段提供 Hub。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="7c3e9-116">如果 Hub 继续繁忙，并错过多个维护窗口，则 Hub 最终将开始安装和下载更新。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="7c3e9-117">这可在维护时段期间或之外发生。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="7c3e9-118">下载和安装开始后，设备可能会重新启动。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-118">Once the download and installation has begun, the device may restart.</span></span>

## <a name="to-avoid-this-issue"></a><span data-ttu-id="7c3e9-119">避免此问题</span><span class="sxs-lookup"><span data-stu-id="7c3e9-119">To avoid this issue</span></span>

<span data-ttu-id="7c3e9-120">为用户留出维护时间以执行管理功能Surface Hub这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="7c3e9-121">将更新Surface Hub 24 小时，或在维护时段期间使用设备延迟安装更新。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="7c3e9-122">建议您在计划维护期间不使用或保留 Hub。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="7c3e9-123">应保留一个两小时窗口以供更新。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="7c3e9-124">一个可用于控制更新可用性的选项是Windows更新。</span><span class="sxs-lookup"><span data-stu-id="7c3e9-124">One option that you can use to control the availability of updates is Windows Update for Business.</span></span>

## <a name="learn-more"></a><span data-ttu-id="7c3e9-125">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="7c3e9-125">Learn more</span></span>
 
- [<span data-ttu-id="7c3e9-126">更新 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="7c3e9-126">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 
- [<span data-ttu-id="7c3e9-127">维护窗口</span><span class="sxs-lookup"><span data-stu-id="7c3e9-127">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

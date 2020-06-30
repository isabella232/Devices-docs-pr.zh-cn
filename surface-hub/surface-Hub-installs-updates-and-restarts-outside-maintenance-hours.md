---
title: Surface Hub 可能会安装更新，并在维护时间外重启
description: 有关 "自动更新" 的 Surface Hub 的疑难解答信息
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface hub，维护窗口，更新
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831928"
---
# <span data-ttu-id="32ad4-104">Surface Hub 可能会安装更新，并在维护时间外重启</span><span class="sxs-lookup"><span data-stu-id="32ad4-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="32ad4-105">在特定情况下，Surface Hub 在工作时间内（而不是在常规维护窗口期间）安装更新。</span><span class="sxs-lookup"><span data-stu-id="32ad4-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="32ad4-106">如果需要，设备将重新启动。</span><span class="sxs-lookup"><span data-stu-id="32ad4-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="32ad4-107">只有在完成该过程后，才能使用该设备。</span><span class="sxs-lookup"><span data-stu-id="32ad4-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="32ad4-108">缺少维护窗口时，这不是预期的行为。</span><span class="sxs-lookup"><span data-stu-id="32ad4-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="32ad4-109">它仅在设备已过期的情况中发生。</span><span class="sxs-lookup"><span data-stu-id="32ad4-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <span data-ttu-id="32ad4-110">原因</span><span class="sxs-lookup"><span data-stu-id="32ad4-110">Cause</span></span>
<span data-ttu-id="32ad4-111">为了确保 Surface Hub 在工作时间内保持可用，中心配置为在 "设置" 中定义的维护窗口期间执行管理功能（请参阅下面的 "参考"）。</span><span class="sxs-lookup"><span data-stu-id="32ad4-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="32ad4-112">在此维护期内，中心将通过 Windows 更新或 Windows Server 更新服务（WSUS）自动安装任何可用更新。</span><span class="sxs-lookup"><span data-stu-id="32ad4-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="32ad4-113">更新完成后，集线器可能会重启。</span><span class="sxs-lookup"><span data-stu-id="32ad4-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="32ad4-114">仅当 Surface Hub 已打开但未在使用或保留时，才能在维护窗口期间安装更新。</span><span class="sxs-lookup"><span data-stu-id="32ad4-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="32ad4-115">例如，如果为持续24小时的会议安排了 Surface Hub，则计划安装的任何更新都将推迟到下一个维护时段内的中心可用。</span><span class="sxs-lookup"><span data-stu-id="32ad4-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="32ad4-116">如果集线器继续繁忙且错过了多个维护窗口，则中心将最终开始安装和下载更新。</span><span class="sxs-lookup"><span data-stu-id="32ad4-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="32ad4-117">这可能会在维护窗口期间或之外发生。</span><span class="sxs-lookup"><span data-stu-id="32ad4-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="32ad4-118">下载和安装开始后，设备可能会重启。</span><span class="sxs-lookup"><span data-stu-id="32ad4-118">Once the download and installation has begun, the device may restart.</span></span>

## <span data-ttu-id="32ad4-119">若要避免此问题</span><span class="sxs-lookup"><span data-stu-id="32ad4-119">To avoid this issue</span></span>

<span data-ttu-id="32ad4-120">请务必为 Surface Hub 留出维护时间，以执行管理功能。</span><span class="sxs-lookup"><span data-stu-id="32ad4-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="32ad4-121">将 Surface Hub 保留24小时间隔或在维护窗口期间使用设备会延迟安装更新。</span><span class="sxs-lookup"><span data-stu-id="32ad4-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="32ad4-122">我们建议你在计划的维护期内不要使用或保留中心。</span><span class="sxs-lookup"><span data-stu-id="32ad4-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="32ad4-123">应保留两小时的窗口进行更新。</span><span class="sxs-lookup"><span data-stu-id="32ad4-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="32ad4-124">可用于控制更新可用性的一个选项是 "Windows Server 更新服务（WSUS）"。</span><span class="sxs-lookup"><span data-stu-id="32ad4-124">One option that you can use to control the availability of updates is Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="32ad4-125">WSUS 可控制安装哪些更新以及何时安装。</span><span class="sxs-lookup"><span data-stu-id="32ad4-125">WSUS provides control over what updates are installed and when.</span></span>

## <span data-ttu-id="32ad4-126">参考</span><span class="sxs-lookup"><span data-stu-id="32ad4-126">References</span></span> 
 
[<span data-ttu-id="32ad4-127">更新 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="32ad4-127">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 

[<span data-ttu-id="32ad4-128">维护窗口</span><span class="sxs-lookup"><span data-stu-id="32ad4-128">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[<span data-ttu-id="32ad4-129">使用 Windows Server Update Services (WSUS) 部署 Windows 10 更新</span><span class="sxs-lookup"><span data-stu-id="32ad4-129">Deploy Windows 10 updates using Windows Server Update Services (WSUS)</span></span>](/windows/deployment/update/waas-manage-updates-wsus) 



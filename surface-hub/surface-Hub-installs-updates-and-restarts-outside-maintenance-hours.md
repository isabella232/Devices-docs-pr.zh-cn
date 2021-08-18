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
ms.openlocfilehash: 7c023256750ee997ce50d0adcd392207f47a298f
ms.sourcegitcommit: 3810c4310e9f5b5b9ad7b4584eaede2789ccd946
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2021
ms.locfileid: "11902881"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a>Surface Hub 可能会安装更新，并在维护时间外重启

在某些情况下，Surface Hub在工作时间而不是常规维护时段安装更新。 然后，如有必要，设备将重新启动。 在此过程完成之前，无法使用该设备。

> [!NOTE]  
> 对于缺少维护窗口，这不是预期行为。 它仅在设备长时间过期时发生。

## <a name="cause"></a>原因

为了确保Surface Hub在工作时间可用，Hub 配置为在 设置 (中定义的维护时段内执行管理功能，请参阅下面的"引用) 。 在此维护期间，中心会自动通过 WUfB Windows Windows Update for Business (安装任何) 。 更新完成后，中心可能会重新启动。

只有在设备打开但没有使用或保留Surface Hub才能在维护时段内安装更新。 例如，如果 Surface Hub安排了持续 24 小时的会议，则计划安装的任何更新都将延迟，直到下次维护时段提供 Hub。 如果 Hub 继续繁忙，并错过多个维护窗口，则 Hub 最终将开始安装和下载更新。 这可在维护时段期间或之外发生。 下载和安装开始后，设备可能会重新启动。

## <a name="to-avoid-this-issue"></a>避免此问题

为用户留出维护时间以执行管理功能Surface Hub这一点很重要。 将更新Surface Hub 24 小时，或在维护时段期间使用设备延迟安装更新。 建议您在计划维护期间不使用或保留 Hub。 应保留一个两小时窗口以供更新。

可用于控制更新可用性的一个选项是 Windows 更新 for Business。

## <a name="learn-more"></a>了解详细信息
  
- [维护窗口](manage-windows-updates-for-surface-hub.md#maintenance-window) 

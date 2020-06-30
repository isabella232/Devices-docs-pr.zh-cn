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
# Surface Hub 可能会安装更新，并在维护时间外重启

在特定情况下，Surface Hub 在工作时间内（而不是在常规维护窗口期间）安装更新。 如果需要，设备将重新启动。 只有在完成该过程后，才能使用该设备。

> [!NOTE]  
> 缺少维护窗口时，这不是预期的行为。 它仅在设备已过期的情况中发生。

## 原因
为了确保 Surface Hub 在工作时间内保持可用，中心配置为在 "设置" 中定义的维护窗口期间执行管理功能（请参阅下面的 "参考"）。 在此维护期内，中心将通过 Windows 更新或 Windows Server 更新服务（WSUS）自动安装任何可用更新。 更新完成后，集线器可能会重启。

仅当 Surface Hub 已打开但未在使用或保留时，才能在维护窗口期间安装更新。 例如，如果为持续24小时的会议安排了 Surface Hub，则计划安装的任何更新都将推迟到下一个维护时段内的中心可用。 如果集线器继续繁忙且错过了多个维护窗口，则中心将最终开始安装和下载更新。 这可能会在维护窗口期间或之外发生。 下载和安装开始后，设备可能会重启。

## 若要避免此问题

请务必为 Surface Hub 留出维护时间，以执行管理功能。 将 Surface Hub 保留24小时间隔或在维护窗口期间使用设备会延迟安装更新。 我们建议你在计划的维护期内不要使用或保留中心。 应保留两小时的窗口进行更新。

可用于控制更新可用性的一个选项是 "Windows Server 更新服务（WSUS）"。 WSUS 可控制安装哪些更新以及何时安装。

## 参考 
 
[更新 Surface Hub](first-run-program-surface-hub.md#update-the-surface-hub) 

[维护窗口](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[使用 Windows Server Update Services (WSUS) 部署 Windows 10 更新](/windows/deployment/update/waas-manage-updates-wsus) 



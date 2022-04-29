---
title: 管理 Surface Hub 上的 Windows 更新
description: 介绍在 Microsoft Surface Hub 或 Surface Hub 2S 上管理更新的最佳做法。
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: 管理Windows更新、Surface Hub、Windows Server Update Services
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: ecff961e1aaa14ed2af5e6d91ffc2254e4dcfa46
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497775"
---
# <a name="manage-windows-updates-on-surface-hub"></a>管理 Surface Hub 上的 Windows 更新

Surface Hub操作系统的新版本通过Windows 更新发布，就像发布Windows 10或Windows 11一样。 本页介绍管理Surface Hub设备更新的最佳做法。 

## <a name="windows-update-for-business"></a>适用于企业的 Windows 更新

Windows 更新企业版是一组功能，旨在为企业提供对Windows 更新安装版本方式和时间的额外控制，同时降低设备管理成本。 通过使用此方法，Surface Hub 直接连接到 Microsoft 的 Windows 更新服务。

- 直接从 Microsoft 的 Windows 更新服务接收更新，无需其他基础结构。 
- 延迟更新，为测试和评估提供额外时间。 
- 部署更新，选择设备组。 
- 定义安装更新的维护窗口。 

> [!TIP]
> 使用对等内容共享减少更新中的带宽问题。 有关详细信息，请参阅[“优化Windows更新交付](/windows/deployment/do/waas-optimize-windows-10-updates)。

> [!NOTE]
> Surface Hub 当前不支持回退更新。


## <a name="surface-hub-servicing-model"></a>Surface Hub 服务模型

Surface Hub使用Windows服务模型，称为[Windows服务 (WaaS) ](/windows/deployment/update/waas-overview)。 从传统上讲，仅在每隔几年发布的新版 Windows 中添加新功能。 在组织中部署新版本的过程耗时长且成本昂贵。 因此，最终用户和组织经常都享受不到创新带来的好处。 Windows 即服务的目标是在维持高级质量的同时，持续提供新功能。

Microsoft 持续广泛发布两种类型的 Surface Hub 版本：
- **功能更新** - 安装最新特性、体验和功能的更新。 Microsoft 预计每年发布两个新的功能更新。
- **质量更新** - 侧重于安装安全修补程序、驱动程序和其他服务更新的更新。 Microsoft 希望每个月发布一个累积质量更新。

为了提高发布质量和简化部署，Microsoft 为Windows 10或Windows 11（包括Surface Hub）发布的所有新版本都将累积。 这意味着新功能更新和质量更新将包含所有早期版本的有效负载（采用优化的形式减少存储和网络需求），并且在设备上安装该版本将使设备保持最新。 此外，与早期版本的 Windows 不同，Windows10 质量更新内容的子集无法安装。 例如，如果质量更新包含三个安全漏洞和一个可靠性问题的修补程序，部署此更新将安装所有这四个修补程序。

Surface Hub 操作系统接收[半年频道](/windows/deployment/update/waas-overview#naming-changes)上的更新。 与其他版本的Windows 10或Windows 11一样，服务生存期是有限的。 必须在运行这些分支的计算机上安装新功能更新才能继续接收质量更新。

有关 Windows 即服务的详细信息，请参阅 [Windows 即服务概述](/windows/deployment/update/waas-overview)。


## <a name="use-windows-update-for-business"></a>使用适用于企业的 Windows 更新

就像所有的 Windows10 设备一样，Surface Hub 包含**适用于企业的 Windows 更新 (WUfB)**，可控制更新设备的方式。 适用于企业的 Windows 更新有助于持续降低设备管理成本、控制更新部署、更快速地访问安全更新以及访问 Microsoft 的最新创新。 有关详细信息，请参阅[使用适用于企业的 Windows 更新管理更新](/windows/deployment/update/waas-manage-updates-wufb)。

> [!IMPORTANT]
> Microsoft 通常每月发布一个强制性Windows安全更新 (于 2 日发布，通常称为“B”版本) 。 这些更新与带外安全更新一起，是使用 WUfB 向设备提供的唯一更新。 但是，Surface Hub改进通常通过每月第 3 个星期二的可选非安全更新提供， (“C”版本) 。 因此，将 Windows 更新 for Business 与 Surface Hub 配合使用的客户将等待到下个月的“B”版本，以查看这些设备上的最新改进。

**若要设置适用于企业的 Windows 更新：**
1. [将 Surface Hub 分组到部署圈](#group-surface-hub-into-deployment-rings)
2. [配置 Surface Hub 接收更新的时间](#configure-when-surface-hub-receives-updates)。

> [!NOTE]
> 可以使用Microsoft Intune、Microsoft Endpoint Configuration Manager或受支持的第三方 MDM 提供程序来设置 WUfB。 [演练：使用 Microsoft Intune 配置适用于企业的 Windows 更新。](/windows/deployment/update/waas-wufb-intune)


### <a name="group-surface-hub-into-deployment-rings"></a>将 Surface Hub 分组到部署圈

使用部署圈控制向 Surface Hub 推出更新的时间，这可提供验证更新的时间。 例如，可以先小范围更新设备，验证更新质量，然后在更大范围内向组织推出。 根据谁管理组织中的Surface Hub，请考虑将Surface Hub合并到为其他Windows 10或Windows 11设备构建的部署圈中。 有关部署环的详细信息，请参阅[为Windows客户端更新准备服务策略](/windows/deployment/update/waas-servicing-strategy-windows-10-updates)。

有关部署环的示例，请参阅下表。

| 部署圈 | 圈大小 | 服务分支 | 功能更新延迟 | 质量更新延迟（安全修补程序、驱动程序和其他更新） | 验证步骤 |
| --------- | --------- | --------- | --------- | --------- | --------- |
| 评估（例如非关键或测试设备） | 小 | Windows Insider Preview | 无。  | 无。  | 手动测试和评估新功能。 如果出现问题，请暂停更新。 |
| 试用状态（例如所选团队使用的设备） | 中等 | 半年频道  | 无。 | 无。  | 监视设备使用情况和用户反馈。 如果出现问题，请暂停更新。 |
| 广泛部署（例如组织中的大部分设备） | 大 | 半年频道 |  发布后 120 天。 | 发布后 7-14 天。 | 监视设备使用情况和用户反馈。 如果出现问题，请暂停更新。 |
| 任务关键（例如执行会议室的设备） | 小 | 半年频道 |  发布后 180 天（功能更新的最长延迟时间）。 | 发布后 30 天（质量更新的最长延迟时间）。 | 监视设备使用情况和用户反馈。 |


### <a name="configure-when-surface-hub-receives-updates"></a>配置 Surface Hub 接收更新的时间

为 Surface Hub 确定了部署圈后，为每个圈配置更新延迟策略：
- 若要延迟功能更新，请为每个圈设置相应的 [Update/DeferFeatureUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) 策略。
- 若要延迟质量更新，请为每个圈设置相应的 [Update/DeferQualityUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) 策略。

> [!NOTE]
> 如果在推出更新时遇到问题，可使用 [Update/PauseFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) 和 [Update/PauseQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates) 暂停更新。

**如果使用代理服务器或其他方法阻止 URL**

将以下Windows更新受信任的站点 URL 添加到“允许列表”：
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

安装 Windows 10 协同版周年更新后，可以删除这些地址，将 Surface Hub 恢复到之前的状态。

## <a name="maintenance-window"></a>维护窗口

为了确保设备在工作时间内始终可用，Surface Hub 在指定维护窗口期间执行其管理功能。 在维护时段内，Surface Hub通过Windows 更新自动安装更新，并在窗口结束前 20 分钟重新启动设备。

Surface Hub 遵循以下应用更新的指南：
- 在下一个维护窗口期间安装更新。 如果计划在维护窗口期间开始会议，或者如果 Surface Hub 传感器检测到设备已在使用，则挂起的更新将推迟到下一个维护窗口。
- 如果下一个维护窗口超过了更新预先规定的宽限期，设备将使用更新元数据中的预计安装时间在工作时间计算下一个可用槽。 如果会议已计划好，或者 Surface Hub 传感器检测到设备处于使用状态，将继续推迟更新。
- 如果下一个维护时段**未**超过更新的宽限期，则Surface Hub将继续推迟更新。
- 如果需要重启，Surface Hub 将在下一个维护窗口期间自动重启。

> [!NOTE]
> 首次设置 Surface Hub 时腾出更新时间。 例如，可能提供了病毒定义的积压工作，这应该立即安装。

为所有新的 Surface Hub 设置默认维护窗口：
-   **开始时间：** 凌晨 2：00
-   **持续时间：** 2 小时

**若要手动更改维护窗口：**
1.  在 Surface Hub 上，打开**设置**。
2.  导航到**更新和安全** > **Windows 更新** > **高级选项**。
3.  在**维护时间**下，选择**更改**。

若要使用 MDM 更改维护时段，请在 [SurfaceHub 配置服务提供](/windows/client-management/mdm/surfacehub-csp)程序中设置 **MaintenanceHoursSimple 节点**。 请参阅[使用 MDM 提供程序管理设置](manage-settings-with-mdm-for-surface-hub.md)，了解详细信息。


## <a name="more-information"></a>更多信息

- [博客文章：服务，外部测试和管理更新Surface Hub (与Intune，当然！) ](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## <a name="related-topics"></a>相关主题

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)


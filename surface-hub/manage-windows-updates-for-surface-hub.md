---
title: Manage Windows updates on Surface Hub
description: You can manage Windows updates on your Microsoft Surface Hub or Surface Hub 2S by setting the maintenance window, deferring updates, or using Windows Server Update Services (WSUS).
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: manage Windows updates, Surface Hub, Windows Server Update Services, WSUS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 72214ec9436e6ea106d9e42c957664631ee88a0a
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103786"
---
# Manage Windows updates on Surface Hub

New releases of the Surface Hub operating system are published through Windows Update, just like releases of Windows 10. 可使用几种方法管理哪些更新安装在 Surface Hub 上以及应用更新的时间。
- **适用于企业的 Windows 更新** - 作为 Windows10 中的新增功能，适用于企业的 Windows 更新是一组功能，目的是在减少设备管理成本的同时，使企业可以额外控制 Windows 更新安装版本的方式和时间。 通过使用此方法，Surface Hub 直接连接到 Microsoft 的 Windows 更新服务。
- **WindowsServer Update Services (WSUS)** - 使 IT 管理员能够获得 Windows 更新确定适用于其企业中设备的更新、对更新执行其他测试和评估，以及选择希望安装的更新。 Surface Hubs 使用此方法从 WSUS（而非 Windows 更新）接收更新。

还可以将 Surface Hub 配置为同时从适用于企业的 Windows 更新和 WSUS 接收更新。 有关详细信息，请参阅[将适用于企业的 Windows 更新与 WindowsServer Update Services 集成](https://technet.microsoft.com/itpro/windows/manage/waas-integrate-wufb#integrate-windows-update-for-business-with-windows-server-update-services)。

| 功能 | 适用于企业的 Windows 更新 | Windows Server Update Services (WSUS) |
| ------------ | --------------------------- | ------------------------------------- |
| 直接从 Microsoft 的 Windows 更新服务接收更新，无需其他基础结构。  | 是  | 否  |
| 延迟更新，为测试和评估提供额外时间。 | 是  | 是  |
| 部署更新，选择设备组。 | 是 | 是 |
| 定义安装更新的维护窗口。 | 是  | 是  |

> [!TIP]
> 使用对等内容共享减少更新中的带宽问题。 有关详细信息，请参阅[优化 Windows10 更新的更新传递](https://technet.microsoft.com/itpro/windows/manage/waas-optimize-windows-10-updates)。

> [!NOTE]
> Surface Hub 当前不支持回退更新。


## Surface Hub 服务模型

Surface Hub 使用 Windows10 服务模型，称为 [Windows 即服务 (WaaS)](https://docs.microsoft.com/windows/deployment/update/waas-overview)。 从传统上讲，仅在每隔几年发布的新版 Windows 中添加新功能。 在组织中部署新版本的过程耗时长且成本昂贵。 因此，最终用户和组织经常都享受不到创新带来的好处。 Windows 即服务的目标是在维持高级质量的同时，持续提供新功能。

Microsoft 持续广泛发布两种类型的 Surface Hub 版本：
- **Feature updates** - Updates that install the latest new features, experiences, and capabilities. Microsoft expects to publish two new feature updates per year.
- **Quality updates** - Updates that focus on the installation of security fixes, drivers, and other servicing updates. Microsoft 希望每个月发布一个累积质量更新。

为了改善版本质量和简化部署，Microsoft 发布的所有 Windows10 新版本（包括 Surface Hub）将累积在一起。 这意味着新功能更新和质量更新将包含所有早期版本的有效负载（采用优化的形式减少存储和网络需求），并且在设备上安装该版本将使设备保持最新。 此外，与早期版本的 Windows 不同，Windows10 质量更新内容的子集无法安装。 例如，如果质量更新包含三个安全漏洞和一个可靠性问题的修补程序，部署此更新将安装所有这四个修补程序。

The Surface Hub operating system receives updates on the [Semi-Annual Channel](https://docs.microsoft.com/windows/deployment/update/waas-overview#naming-changes). Like other editions of Windows 10, the servicing lifetime is finite. You must install new feature updates on machines running these branches in order to continue receiving quality updates.

有关 Windows 即服务的详细信息，请参阅 [Windows 即服务概述](https://technet.microsoft.com/itpro/windows/manage/waas-overview)。


## 使用适用于企业的 Windows 更新
就像所有的 Windows10 设备一样，Surface Hub 包含**适用于企业的 Windows 更新 (WUfB)**，可控制更新设备的方式。 适用于企业的 Windows 更新有助于持续降低设备管理成本、控制更新部署、更快速地访问安全更新以及访问 Microsoft 的最新创新。 有关详细信息，请参阅[使用适用于企业的 Windows 更新管理更新](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb)。

**若要设置适用于企业的 Windows 更新：**
1. [将 Surface Hub 分组到部署圈](#group-surface-hub-into-deployment-rings)
2. [Configure when Surface Hub receives updates](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> You can use Microsoft Intune, Microsoft Endpoint Configuration Manager, or a supported third-party MDM provider to set up WUfB. [Walkthrough: use Microsoft Intune to configure Windows Update for Business.](https://docs.microsoft.com/windows/deployment/update/waas-wufb-intune)


### 将 Surface Hub 分组到部署圈
使用部署圈控制向 Surface Hub 推出更新的时间，这可提供验证更新的时间。 例如，可以先小范围更新设备，验证更新质量，然后在更大范围内向组织推出。 可考虑将 Surface Hub 并入为其他 Windows10 设备生成的部署圈，具体取决于组织管理 Surface Hub 的人员而定。 有关部署圈的详细信息，请参阅[生成 Windows10 更新的部署圈](https://technet.microsoft.com/itpro/windows/manage/waas-deployment-rings-windows-10-updates)。

此表提供了部署圈示例。

| 部署圈 | 圈大小 | 服务分支 | 功能更新延迟 | 质量更新延迟（安全修补程序、驱动程序和其他更新） | 验证步骤 |
| --------- | --------- | --------- | --------- | --------- | --------- |
| 评估（例如非关键或测试设备） | Small | Windows Insider Preview | None.  | 无。  | 手动测试和评估新功能。 如果出现问题，请暂停更新。 |
| 试用状态（例如所选团队使用的设备） | 中等 | 半年频道  | 无。 | 无。  | 监视设备使用情况和用户反馈。 如果出现问题，请暂停更新。 |
| 广泛部署（例如组织中的大部分设备） | 大 | 半年频道 |  发布后 120 天。 | 发布后 7-14 天。 | 监视设备使用情况和用户反馈。 如果出现问题，请暂停更新。 |
| 任务关键（例如执行会议室的设备） | 小 | 半年频道 |  发布后 180 天（功能更新的最长延迟时间）。 | 发布后 30 天（质量更新的最长延迟时间）。 | 监视设备使用情况和用户反馈。 |





### 配置 Surface Hub 接收更新的时间
为 Surface Hub 确定了部署圈后，为每个圈配置更新延迟策略：
- 若要延迟功能更新，请为每个圈设置相应的 [Update/DeferFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) 策略。
- 若要延迟质量更新，请为每个圈设置相应的 [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) 策略。

> [!NOTE]
> 如果在推出更新时遇到问题，可使用 [Update/PauseFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) 和 [Update/PauseQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates) 暂停更新。


## 使用 Windows Server Update Services

可将 Surface Hub 连接到 Windows Server Update Services (WSUS) 服务器以管理更新。 更新通过在 WSUS 服务器中配置的审核或自动部署规则控制，因此全新更新在选择部署前不会进行部署。

**若要手动将 Surface Hub 连接到 WSUS 服务器：**
1. 在 Surface Hub 上，打开**设置**。
2. 请在系统提示时，输入该设备的管理员凭据。
3. 导航到**更新和安全** > **Windows 更新** > **高级选项** > **配置 WindowsServer Update Services (WSUS) 服务器**。
4. 单击**使用 WSUS 服务器下载更新**并键入 WSUS 服务器的 URL。

若要使用 MDM 将 Surface Hub 连接到 WSUS 服务器，请设置相应的 [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl) 策略。

**如果使用代理服务器或其他方法阻止 URL**

如果使用 WSUS 之外的方法阻止特定 URL 并阻止更新，则需要将以下受 Windows 更新信任的站点 URL 添加到“允许列表”中：
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

安装 Windows 10 协同版周年更新后，可以删除这些地址，将 Surface Hub 恢复到之前的状态。

## 维护窗口

To ensure the device is always available for use during business hours, Surface Hub performs its administrative functions during a specified maintenance window. During the maintenance window, the Surface Hub automatically installs updates through Windows Update or WSUS, and reboots the device 20 minutes before the end of the window.

Surface Hub follows these guidelines to apply updates:
- 在下一个维护窗口期间安装更新。 如果计划在维护窗口期间开始会议，或者如果 Surface Hub 传感器检测到设备已在使用，则挂起的更新将推迟到下一个维护窗口。
- 如果下一个维护窗口超过了更新预先规定的宽限期，设备将使用更新元数据中的预计安装时间在工作时间计算下一个可用槽。 如果会议已计划好，或者 Surface Hub 传感器检测到设备处于使用状态，将继续推迟更新。
- If the next maintenance window is **not** past the update's grace period, the Surface Hub will continue to postpone the update.
- If a reboot is needed, the Surface Hub will automatically reboot during the next maintenance window.

> [!NOTE]
> 首次设置 Surface Hub 时腾出更新时间。 例如，可能提供了病毒定义的积压工作，这应该立即安装。

A default maintenance window is set for all new Surface Hubs:
-   **Start time:** 2:00 AM
-   **Duration:** 2 hours

**To manually change the maintenance window:**
1.  在 Surface Hub 上，打开**设置**。
2.  导航到**更新和安全** > **Windows 更新** > **高级选项**。
3.  在**维护时间**下，选择**更改**。

若要使用 MDM 更改维护窗口，请在 [SurfaceHub 配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)中设置 **MOMAgent** 节点。 See [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md) for more details.


## More information

- [Blog post: Servicing, Flighting, and Managing updates for Surface Hub (With Intune, of course!)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## Related topics

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)


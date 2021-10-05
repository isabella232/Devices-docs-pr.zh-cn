---
title: Surface Hub 上的 Microsoft Teams 会议室
description: 本文概述了有关Microsoft Teams 会议室Surface Hub。
keywords: Teams 会议室、Surface Hub、Intune、QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: dpandre
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: a2f382b1120ba071e7dc709f1464ddb1e5118d28
ms.sourcegitcommit: 7ffb1d2d86a713a3ed4a7faa8ac82cfc49dbd55e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "12068453"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Surface Hub 上的 Microsoft Teams 会议室

Teams 会议室Surface Hub 9 月[30](hub-teams-app.md) Surface Hub Teams 4 周全局推出的一部分，自动替换当前 Surface Hub Teams 应用。 有关新的 Teams 体验的演示（当前可通过 Windows 预览体验计划作为预览版提供，请参阅 Teams 会议室[上的](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-teams-rooms-on-surface-hub/ba-p/2118373)Surface Hub。

## <a name="whats-new"></a>新增功能有哪些？

- 从欢迎屏幕Surface Hub新议程页面加入的会议将加入"边缘到边缘"，以将用户置于前台。
- 熟悉的会议功能包括聊天气泡、反应、桌面和应用程序共享、提供和获得控制权以及音频、PowerPoint实时支持、一起模式和大型库。
- Teams 会议室应用程序Surface Hub其他应用程序并排运行或最小化运行。
- 管理员可以为用户配置协调会议、邻近感应Surface Hub。 [XML 文件](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) 受支持，并且将被迁移到新的设置模型。
- 新的 QoS 选项和网络要求。 若要了解更多信息，请参阅 Microsoft Teams 上的配置网络和服务质量[Surface Hub。](surface-hub-teams-rooms-networking.md)
- 如果还没有默认应用，Teams设置为通话和音频通话的默认设置Surface Hub****  >  ****  >  **通话&应用**。 若要了解有关会议模式和通过 MDM 策略配置会议模式的信息，请参阅使用[MDM Surface Hub管理会议模式](manage-settings-with-mdm-for-surface-hub.md#changing-default-app-for-meetings--calls)。

## <a name="in-meeting-experience"></a>在会议体验中

Teams 会议室会议Surface Hub体验与用户通过针对大屏幕设备进行优化而从个人设备了解的熟悉体验保持一致。 在 Teams 上Surface Hub使用户可以访问主要功能，包括一键式会议加入、立即开会和用于 PSTN 或对等呼叫的拨号盘。

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Teams 会议室议程Surface Hub讨论。":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Teams 会议室会议Surface Hub会议。":::

## <a name="manage-teams-rooms-on-surface-hub"></a>在Teams 会议室管理Surface Hub

 在输入管理Teams后，可以直接从设置菜单自定义体验，包括：

- 配置 [协调会议和](/microsoftteams/rooms/coordinated-meetings) 邻近感应加入。
- 调整默认麦克风、相机和扬声器的设置。
- 检查客户端版本并搜索最新更新。

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Teams 会议室 设置。":::

适用于 Teams 会议室 客户端的新Surface Hub将自动应用通过 XML 文件、预配包或 MDM 提供程序配置的现有设置。 这些方法（在 Surface Hub 上管理[Microsoft Teams](/microsoftteams/rooms/surface-hub-manage-config)配置中介绍）将被新的基于云的解决方案取代，如 Surface Hub 中将介绍的简化 Teams 管理[中所述。](#simplified-management-of-teams-coming-to-surface-hub)

### <a name="prepare-networking-for-teams-rooms"></a>准备网络Teams 会议室

若要优化Teams 会议室请参阅在 Surface Hub 上为会议室配置网络和服务质量中所述Microsoft Teams[要求Surface Hub。](surface-hub-teams-rooms-networking.md)

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>对即将Teams的简化Surface Hub

当Teams 会议室发布Surface Hub，管理员可以利用以下解决方案：

- **Teams管理中心。** Teams管理中心提供了一个全面的自我管理平台，用于监视和管理Teams 会议室设备上Teams体验。 Teams管理中心将可供Microsoft Teams 会议室用户使用，无需额外付费。
- **Microsoft Teams 会议室托管服务。** Microsoft Teams 会议室[托管](/microsoftteams/rooms/microsoft-teams-rooms-premium)服务是一种基于云的 IT 管理和监视服务，可使 Microsoft Teams 会议室 设备及其外围设备保持最新并主动监视，并支持针对出色的用户体验进行优化的环境。


## <a name="support-for-teams-rooms-in-government-community-cloud-high-gcc-h"></a>支持Teams 会议室高政府社区云-H (GCC中的) 

当 Teams 会议室 for Surface Hub 今年晚些时候公开发布时，需要一次手动将客户端更新到版本 1.4.00.25354，以便它能够连接到 GCC-H 租户，然后自动保持自身最新：

 - 确认 Hub 已安装 KB5005611 或更高版本Windows累积更新
 - 使用[Teams_Uninstall_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Uninstall_Win32.ppkg)删除Teams 会议室版本Surface Hub当前版本
 - 重启设备
 - 安装 [Teams_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Win32.ppkg) 以安装版本 1.4.00.25354
 - 再次重启设备

详细步骤：

1. 将两个预配包保存到 USB 驱动器的根目录。
2.  将 USB 驱动器插入Surface Hub。
3.  On your Surface Hub， open the "开始"菜单， select All apps， and then select 设置.
4.  在系统提示时提供中心管理员凭据。
5.  转到 **"Surface Hub**  >  **管理**  >  **添加或删除预配包"，** 然后选择"**添加程序包"。**
6.  在 **"选择程序包"** 下，选择 Teams_Uninstall_win32.ppkg 预配包，然后重新启动Surface Hub。
7.  On your Surface Hub， open the "开始"菜单， select All apps， and then select 设置.
8.  在系统提示时提供中心管理员凭据。
9.  转到 **"Surface Hub**  >  **管理**  >  **添加或删除预配包"，** 然后选择"**添加程序包"。**
10. 在 **"选择程序包"** 下，选择 Teams_win32.ppkg 预配包，然后重新启动Surface Hub。

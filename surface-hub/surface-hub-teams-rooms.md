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
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 05160bc2c1b77843b8ad832452501d7b065a8bc6
ms.sourcegitcommit: 38bde856b6091097d25745f6d080edebf72e3e17
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2021
ms.locfileid: "12030817"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Surface Hub 上的 Microsoft Teams 会议室

Teams 会议室Surface Hub 9 月 30 Surface Hub Teams [](hub-teams-app.md) 4 周全局推出的一部分，自动替换当前 Surface Hub Teams 应用。 有关新体验的Teams（当前可通过 Windows 预览体验计划作为预览版提供）的信息，请参阅 Surface Hub 上的 Teams 会议室[介绍](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-teams-rooms-on-surface-hub/ba-p/2118373)。

## <a name="whats-new"></a>新增功能有哪些？

- 从欢迎屏幕Surface Hub新议程页面加入的会议将加入"边缘到边缘"，以将用户置于前台。
- 熟悉的会议功能包括聊天气泡、反应、桌面和应用程序共享、提供和获得控制权以及音频、PowerPoint实时支持、一起模式和大型库。
- Teams 会议室应用程序Surface Hub其他应用程序并排运行或最小化运行。
- 管理员可以为用户配置协调会议、邻近感应Surface Hub。 [XML 文件](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) 受支持，并且将被迁移到新的设置模型。
- 新的 QoS 选项和网络要求。 若要了解更多信息，请参阅 Surface Hub 上的配置[聊天室的网络Microsoft Teams服务质量](surface-hub-teams-rooms-networking.md)。
- 对会议Teams的更改，将Skype for Business默认协作和会议应用。 若要了解更多信息，请参阅[部署Microsoft Teams for Surface Hub](/MicrosoftTeams/teams-surface-hub)。

## <a name="in-meeting-experience"></a>在会议体验中

Teams 会议室会议Surface Hub体验与用户通过针对大屏幕设备进行优化而从个人设备了解的熟悉体验保持一致。 在 Teams 上Surface Hub使用户可以访问关键功能，包括一键式会议加入、立即开会和用于 PSTN 或对等呼叫的拨号盘。

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Teams 会议室议程Surface Hub讨论。":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Teams 会议室会议Surface Hub会议。":::

## <a name="manage-teams-rooms-on-surface-hub"></a>在Teams 会议室管理Surface Hub

 在输入管理Teams后，可以直接从设置菜单自定义体验，包括：

- 配置 [协调会议和](/microsoftteams/rooms/coordinated-meetings) 邻近感应加入。
- 调整默认麦克风、相机和扬声器的设置。
- 检查客户端版本并搜索最新更新。

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Teams 会议室 设置。":::

适用于 Teams 会议室 客户端的新Surface Hub将自动应用通过 XML 文件、预配包或 MDM 提供程序配置的现有设置。 这些方法（在 Surface Hub 上管理[Microsoft Teams](/microsoftteams/rooms/surface-hub-manage-config)配置中所述）将被新的基于云的解决方案所取代，如 Surface Hub 中简化的 Teams 管理[中所述。](#simplified-management-of-teams-coming-to-surface-hub)

### <a name="prepare-networking-for-teams-rooms"></a>准备网络Teams 会议室

若要优化Teams 会议室请参阅在 Surface Hub 上为 Microsoft Teams 会议室配置网络和服务质量中所述[的要求Surface Hub。](surface-hub-teams-rooms-networking.md)

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>简化对Teams的管理Surface Hub

当Teams 会议室发布Surface Hub，管理员可以利用以下解决方案：

- **Teams管理中心。** Teams管理中心提供了一个全面的自我管理平台，用于监视和管理 Teams 会议室 设备上Teams体验。 Teams管理中心将可供Microsoft Teams 会议室用户使用，无需额外付费。
- **Microsoft Teams 会议室托管服务。** Microsoft Teams 会议室[托管](/microsoftteams/rooms/microsoft-teams-rooms-premium)服务是一种基于云的 IT 管理和监视服务，可使 Microsoft Teams 会议室 设备及其外围设备保持最新并主动监视，并支持针对出色的用户体验进行优化的环境。

---
title: Surface Pen Pen 2 触觉开发笔记
description: 此页面为希望扩展 Surface Pen Pen 2 for Business Windows 11墨迹功能的应用开发人员提供了实施说明。
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/07/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
ms.openlocfilehash: 8a3dbbdde85cfdceaf5674750a68fc21d3fcd877
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338622"
---
# <a name="surface-slim-pen-2-haptics-dev-notes"></a>Surface Pen Pen 2 触觉开发笔记

此页面为希望扩展 Surface Pen Pen 2 for Business Windows 11墨迹功能的应用开发人员提供了[实施说明](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?)。 可自定义的触觉功能包括：

- **模拟笔** 、铅笔和其他书写或绘图工具感觉的墨迹反馈。
- **直接** 响应用户操作（如将鼠标悬停在按钮上、单击按钮或用笔完成任务）的交互反馈。

若要为 Surface Pen 触控笔 2 自定义应用，请参阅笔交互和触觉反馈Windows Ink介绍的 Windows Ink 指南，然后查看以下[](/windows/apps/design/input/pen-haptics)注意事项。

## <a name="implementation-notes"></a>实施说明

Surface Pen Pen 2 符合Windows 11 Ink 指南，但以下例外：

- **交互波形。** 如"发送和停止[](/windows/apps/design/input/pen-haptics#send-and-stop-interaction-feedback)交互反馈"部分所述，播放墨迹波形时发送交互波形将暂时中断墨迹书写波形。 但是，对于当前的 Pen Pen 2 实现，当交互波形停止时，墨迹书写波形可能无法恢复。 因此，如果仍然需要，需要在交互反馈后重新启用墨迹书写波形。 无需等待交互反馈完成。
- **不受支持的功能。** 如触觉反馈自定义"[](/windows/apps/design/input/pen-haptics#haptic-feedback-customizations)部分所述，Surface Pen Pen 2 不支持以下可选功能：播放计数和重播暂停间隔。 尽管这些用法出现在描述符中，但当前不受支持。 因此，以下函数返回一个不正确的值：IsPlayCountSupported、IsPlayDurationSupported、IsReplayPauseIntervalSupported。

## <a name="learn-more"></a>了解详细信息

- [笔在应用中Windows Ink和Windows交互](/windows/apps/design/input/pen-and-stylus-interactions)
- [Surface Slim Pen 2 for Business](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?)
- [Surface 触控笔功能和兼容性](https://support.microsoft.com/surface/identify-your-surface-pen-and-features-c82a0208-2e35-b347-dae0-d7f4922edc77)


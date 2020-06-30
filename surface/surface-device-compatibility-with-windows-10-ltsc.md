---
title: 与 Windows 10 长期服务通道（Surface）的 Surface 设备兼容性
description: 了解运行 Windows 10 企业版 LTSB 版的 Surface 设备的兼容性和限制。
keywords: ltsb、更新、surface 服务选项
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: db3dfd57c3b79fcec507ffd146483915490801b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830685"
---
# 与 Windows 10 长期服务通道（LTSC）的 Surface 设备兼容性

Surface 设备旨在在生产力和通用方案中提供一流的体验。 定期更新使 Surface 设备能够利用由 Windows 10 功能更新提供的新功能，让新的创新变得生动。 仅在通过半年频道（SAC）接收连续更新的 Windows 10 专业版或 Windows 10 企业版中提供功能更新。

与 SAC 服务选项（以前称为 "当前分支（CB）" 或 "当前分支 for Business （CBB）服务选项" 相比），你无法在 Windows 10 设置中选择长期服务通道（LTSC）选项。 若要使用 LTSC 服务选项，必须安装单独的 Windows 10 企业版（称为 Windows 10 企业版 LTSC，以前称为 Windows 10 企业版 LTSB （长期服务分支）。 除了提供扩展的服务模型外，Windows 10 企业版 LTSC 还提供了已删除多个 Windows 组件的环境。 LTSC 影响的核心表面体验包括：

* Windows 功能更新，包括增强功能，如：

  *  对 Windows 10 版本1607（也称为周年纪念更新）中提供的直接墨迹和 palm 拒绝的改进
  *  改进了对 Windows 10 版本1703（也称为创意者更新）中提供的高 DPI 应用程序的支持

* Surface 应用提供的压力敏感度设置

* Windows Ink 工作区

* 关键触摸优化的内置应用程序，包括 Microsoft Edge、OneNote、日历和照相机

在 Surface 设备上使用 Windows 10 企业版 LTSC 环境会产生欠优化的最终用户体验，因此你应该避免在用户希望和期望获得高级的最新用户体验的环境中使用它。

LTSC 服务选项是针对设备类型和方案设计的，其中 key 属性适用于永不改变的功能或功能。 例如，在您的系统中，电源制造或医疗设备或嵌入式系统（如 Atm 或机场票证系统）的系统。

>[!NOTE]
>有关 Windows 服务分支（包括 LTSC）的常规信息，请参阅[windows 服务概述](https://technet.microsoft.com/itpro/windows/update/waas-overview#long-term-servicing-branch)。

通常情况下，满足以下条件的设备被视为通用设备，并且应与 Windows 10 专业版或 Windows 10 企业版结合使用半年度频道服务选项：

* 运行生产力软件（如 Microsoft Office）的设备

* 使用 Microsoft Store 应用程序的设备

* 用于常规 Internet 浏览的设备（例如，对社交媒体进行研究或访问）

在 Surface 设备上选择使用 Windows 10 企业版 LTSC 版之前，请考虑以下限制：

* 不会针对 Windows 10 企业版 LTSC 的版本显式测试驱动程序和固件更新。

* 如果遇到问题，Microsoft 支持将提供疑难解答帮助。 但是，由于 Windows LTSC 的服务性质，问题解决可能需要将设备升级到最新版本的 Windows 10 企业版 LTSC，或者使用 SAC 服务选项升级到 Windows 10 专业版或企业版。

* Surface 设备替换（例如，在保修期内更换的设备）可能会在硬件组件中包含需要更新设备驱动程序和固件的细微变体。 与这些更新的兼容性可能需要使用 SAC 服务选项安装最新版本的 Windows 10 企业版 LTSC 或 Windows 10 专业版或企业版。

>[!NOTE]
>在特定版本的 Windows 10 企业版上实现标准化的组织可能无法采用 surface Pro （如 Surface Pro 7、Surface Pro X 或 Surface）的新代，而无需同时更新到更高版本的 Windows 10 企业版 LTSC 或 Windows 10 专业版或企业版 LTSC。 有关详细信息，请参阅**如何支持 windows 10 LTSBs？** 支持[生命周期策略常见问题（windows 产品）](https://support.microsoft.com/help/18581/lifecycle-policy-faq-windows-products#b4)的**最新处理器和芯片组**的主题。

运行 Windows 10 企业版 LTSC 的 Surface 设备将不会收到新功能。 在许多情况下，客户请求这些功能来提高 Surface 硬件的可用性和功能。 例如，Windows 10 版本1703中的高 DPI 应用程序的新改进。 在 LTSC 配置中使用 Surface 设备的客户将看不到改进，直到它们更新为新的 Windows 10 企业版 LTSC 释放或升级到 Windows 10 的版本，并支持 SAC 服务选项。

可将设备从 Windows 10 企业版 LTSC 更改为 Windows 10 企业的更新版本，并支持 SAC 服务选项，而无需通过执行升级安装来丢失用户数据。 你还可以利用 Microsoft 部署工具包（MDT）和 Microsoft 终结点配置管理器中提供的升级任务序列模板，在多台设备上执行升级安装。 有关详细信息，请参阅[通过 Microsoft 部署工具包将 Surface 设备升级到 Windows 10](https://technet.microsoft.com/itpro/surface/upgrade-surface-devices-to-windows-10-with-mdt)。

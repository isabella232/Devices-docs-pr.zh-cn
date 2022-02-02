---
title: 'Surface 设备与 Surface Windows 10 Long-Term服务频道 (兼容性) '
description: 了解运行 LTSB 版本的 Surface 设备的兼容性Windows 10 企业版限制。
keywords: ltsb， 更新， 图面维护选项
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 07/21/2021
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: 6127685edb0c098235734439ffbffac8c2c508ca
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338438"
---
# <a name="surface-device-compatibility-with-windows-10-long-term-servicing-channel-ltsc"></a>Surface 设备与 LTSC Windows 10 Long-Term服务 (兼容性) 

Surface 设备旨在提供生产力和通用方案中的最佳体验。 通过定期更新，Surface 设备可以带来创新，并借助由功能更新提供的新功能Windows 10发展。 功能更新仅在 Windows 10 专业版 或 Windows 10 企业版 版本中可用，这些版本通过 SAC Semi-Annual 频道 (持续) 。

与 SAC 服务选项（以前称为 Current Branch (CB) 或 Current Branch for Business (CBB) 服务选项）相反，您无法在 Windows 10 设置中选择 Long-Term 服务分支 (LTSC) 选项。 若要使用 LTSC 服务选项，必须安装单独的 Windows 10 企业版 版本（称为 Windows 10 企业版 LTSC，以前称为 Windows 10 企业版 LTSB (Long-Term Servicing Branch）。

>[!TIP]
>有关 LTSC 的最新信息，请参阅以下常见问题解答：下一个 Windows 10 [Long Term Servicing Channel (LTSC) 发行版](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/the-next-windows-10-long-term-servicing-channel-ltsc-release/ba-p/2147232)。

 除了提供扩展的服务模型之外，Windows 10 企业版 LTSC 版本还提供了一个环境，其中删除了Windows组件。 受 LTSC 影响的核心 Surface 体验包括：

* Windows功能更新，包括以下增强功能：

  *  Windows 10 1607 版本 1607 中提供的 Direct Ink 和 (改进也称为周年更新) 
  *  改进了对 Windows 10 版本 1703 中提供的高 DPI (也称为创意者更新) 

* Surface 应用提供压力敏感度设置

* The Windows Ink 工作区

* 键触摸优化的内装应用程序，包括Microsoft Edge、OneNote、日历和相机

在 Surface 设备上使用 Windows 10 企业版 LTSC 环境会导致最佳最终用户体验，你应避免在用户希望并期望获得高级、最新用户体验的环境中使用它。

LTSC 服务选项专为设备类型和方案设计，其中的关键属性用于使特性或功能永不更改。 示例包括为制造或医疗设备提供电源的系统，或者为展台中的嵌入系统（如 ATM 或机场票证系统）提供电源。

>[!NOTE]
>有关服务分支Windows（包括 LTSC）的一般信息，请参阅 [Windows 即服务。](/windows/deployment/update/waas-overview)

作为一般原则，满足以下条件的设备被视为通用设备，并且应该使用 Windows 10 专业版 或 Windows 10 企业版 选项与 Semi-Annual 配对：

* 运行工作效率软件的设备，如Microsoft Office

* 使用应用程序Microsoft Store设备

* 用于常规 Internet 浏览的设备 (例如，研究或访问社交媒体) 

在选择在 Surface 设备上Windows 10 企业版 LTSC 版本之前，请考虑以下限制：

* 未针对 LTSC 版本显式测试驱动程序和固件Windows 10 企业版更新。

* 如果遇到问题，Microsoft 支持人员将提供疑难解答帮助。 但是，由于 Windows LTSC 的服务性质，问题解决可能要求设备升级到最新版本的 Windows 10 企业版 LTSC，或者使用 SAC 服务选项升级到 Windows 10 专业版 或 Enterprise。

* Surface 设备更换 (例如，在) 更换的设备在需要更新的设备驱动程序和固件的硬件组件中可能包含细微的变体。 与这些更新的兼容性可能需要安装较新版本的 Windows 10 企业版 LTSC、Windows 10 专业版 或 Enterprise SAC 服务选项。

>[!NOTE]
>标准化特定版本的 Windows 10 企业版 LTSC 的组织可能无法采用新一代的 Surface 硬件，如 Surface Pro 8、Surface Pro X 或 Surface Laptop 4，同时无法更新到更高版本的 Windows 10 企业版 LTSC 或Windows 10 专业版 或 Enterprise。 有关详细信息，请参阅生命周期[常见问题解答 - Windows](/lifecycle/faq/windows#what-are-the-requirements-for-servicing-and-updating-the-windows-10-long-term-servicing-channel--ltsc--)。

运行 LTSC Windows 10 企业版 Surface 设备将不会收到新功能。 在许多情况下，客户请求这些功能以提高 Surface 硬件的可用性和功能。 例如，新改进的版本 1703 Windows 10高 DPI 应用程序。 在 LTSC 配置中使用 Surface 设备的客户在更新到新的 Windows 10 企业版 LTSC 版本或升级到支持 SAC 服务选项的 Windows 10 版本之前，不会看到这些改进。

设备可以从 Windows 10 企业版 LTSC 更改为更新版本的 Windows 10 企业版，同时支持 SAC 服务选项，而不会因执行升级安装而丢失用户数据。 您还可以利用 Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager 中提供的升级任务序列模板，在多个设备上执行升级安装。 有关详细信息，请参阅将 [Surface 设备升级到Windows 10 Microsoft 部署Toolkit](upgrade-surface-devices-to-windows-10-with-mdt.md)。

---
title: Surface Pro X 应用兼容性
description: 本文介绍基于 Surface Pro X ARM 的电脑的介绍性应用兼容性信息。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/03/2019
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: c236bf066d22cae80f4c0df39cc04450ad57a419
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831004"
---
# Surface Pro X 应用兼容性

应用程序在基于 ARM 的 Windows 10 电脑（如 Surface Pro X）上以不同的方式运行。以下限制包括：

- **硬件、游戏和应用的驱动程序仅适用于适用于基于 Windows 10 ARM 的电脑的硬件**。 有关详细信息，请咨询硬件制造商或开发驱动程序的组织。 驱动程序是与硬件设备通信的软件程序，它们通常用于防病毒软件和反恶意软件、打印或 PDF 软件、辅助技术、CD 和 DVD 实用工具以及虚拟化软件。 如果驱动程序不起作用，则依赖于它的应用或硬件将不起作用（至少不完全）。 仅当设备所依赖的驱动程序内置于 Windows 10 或硬件开发人员为设备发布了 ARM64 驱动程序时，外围设备和设备才可用。
- **64 位（x64）应用不起作用**。 你将需要64位（ARM64）应用、32位（ARM32）应用或32位（x86）应用。 你通常可以找到32位（x86）版本的应用，但某些应用开发人员仅提供64位（x64）应用。
- **某些游戏不起作用**。 如果游戏和应用使用的 OpenGL 版本大于1.1，或者它们依赖于不是针对基于 Windows 10 ARM 的电脑的 "防外观" 驱动程序，则游戏和应用将不起作用。 请与您的游戏发行者联系，了解游戏是否正常工作。
- **自定义 Windows 体验的应用可能有问题**。 这包括一些输入法编辑器（Ime）、辅助技术和云存储应用。 开发应用的组织确定其应用是否可在基于 Windows 10 ARM 的电脑上运行。
- **无法安装某些第三方防病毒软件**。 你将无法在基于 Windows 10 ARM 的电脑上安装某些第三方防病毒软件。 但是，Windows 安全将帮助你保护 Windows 10 设备受支持的生命周期。
- **Windows 传真和扫描不可用**。 此功能在基于 Windows 10 ARM 的电脑上不可用。

有关应用兼容性的详细信息，请参阅[基于 Windows 10 ARM 的电脑常见问题解答](https://support.microsoft.com/en-us/help/4521606)

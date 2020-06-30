---
title: Surface DMA 保护
description: 本文介绍兼容的 Surface 设备上的 DMA 保护
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/10/2020
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: 00994263cd61086ab86996920543a717a63d5078
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830889"
---
# Surface 设备上的 DMA 保护

直接内存访问（DMA）保护旨在减少与使用可移动 SSDs 或外部存储设备相关的潜在安全漏洞。 较新的 Surface 设备在默认情况下启用 DMA 保护。 其中包括 Surface Pro 7、Surface 笔记本3和 Surface Pro X。 若要检查设备上是否存在 DMA 保护功能，请打开 "系统信息" （"**开始**"  >  **msinfo32.exe**），如下图所示。

![显示 DMA 保护已启用的系统信息](images/systeminfodma.png)

如果 Surface 的可移动 SSD 被篡改，设备将关闭电源。 所产生的重启导致 UEFI 擦除内存，以擦除任何残留数据。

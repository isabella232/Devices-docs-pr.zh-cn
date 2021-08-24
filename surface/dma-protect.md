---
title: Surface DMA 保护
description: 本文介绍了兼容 Surface 设备的 DMA 保护
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/14/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.openlocfilehash: d2656b141908ef203f748518ddf49a7fbcbab255
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911347"
---
# <a name="dma-protection-on-surface-devices"></a>Surface 设备上 DMA 保护

直接内存 (DMA) 保护旨在缓解与使用可移动 SSD 或外部存储设备相关的潜在安全漏洞。 较新的 Surface 设备默认支持 DMA 保护。 其中包括 7 Surface Pro 7 及以上。 Surface Pro 7、Surface Laptop 3 和 Surface Pro X。 若要检查设备上是否存在 DMA 保护功能，请打开系统信息 ("msinfo32.exe) "，****  >  **** 如下图所示。

![显示已启用 DMA 保护的系统信息。](images/systeminfodma.png)

如果 Surface 可移动 SSD 遭到篡改，设备将关闭电源。 生成的重启会导致 UEFI 擦除内存，以清除任何剩余数据。

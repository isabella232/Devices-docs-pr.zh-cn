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
ms.date: 12/01/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: a0f04b4dd089309ad44cab12cf738d8203d1526d
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449495"
---
# <a name="dma-protection-on-surface-devices"></a>Surface 设备上 DMA 保护

直接内存 (DMA) 保护旨在缓解与使用可移动 SSD 或外部存储设备相关的潜在安全漏洞。 较新的 Surface 设备默认支持 DMA 保护。 其中包括 Surface Pro 8、Surface Laptop Studio、Surface Go 3、Surface Laptop 标准版、Surface Pro 7+、Surface Pro 7、Surface Laptop 3 和 Surface Pro X. 若要检查设备上是否存在 DMA **** >  保护功能，系统信息 ("msinfo32.exe) "，如下图所示。** **

![显示已启用 DMA 保护的系统信息。](images/systeminfodma.png)

如果 Surface 可移动 SSD 遭到篡改，设备将关闭电源。 生成的重启会导致 UEFI 擦除内存，以清除任何剩余数据。

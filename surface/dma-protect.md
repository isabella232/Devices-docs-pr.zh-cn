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
ms.openlocfilehash: af5187a2b110804a2dff82291f1d5f912ac61a7b
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270617"
---
# <span data-ttu-id="2e12d-103">Surface 设备上 DMA 保护</span><span class="sxs-lookup"><span data-stu-id="2e12d-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="2e12d-104">直接内存 (DMA) 保护旨在缓解与使用可移动 SSD 或外部存储设备相关的潜在安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="2e12d-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="2e12d-105">较新的 Surface 设备默认启用 DMA 保护。</span><span class="sxs-lookup"><span data-stu-id="2e12d-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="2e12d-106">其中包括 Surface Pro 7+。</span><span class="sxs-lookup"><span data-stu-id="2e12d-106">These include Surface Pro 7+.</span></span> <span data-ttu-id="2e12d-107">Surface Pro 7、Surface Laptop 3 和 Surface Pro X。 若要检查设备上是否存在 DMA 保护功能，请打开"系统信息 ("msinfo32.exe) "，如下\*\*\*\*  >  \*\*\*\* 图所示。</span><span class="sxs-lookup"><span data-stu-id="2e12d-107">Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![显示已启用 DMA 保护的系统信息](images/systeminfodma.png)

<span data-ttu-id="2e12d-109">如果 Surface 可移动 SSD 遭到篡改，设备将关闭电源。</span><span class="sxs-lookup"><span data-stu-id="2e12d-109">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="2e12d-110">生成的重新启动会导致 UEFI 擦除内存，以清除任何泄漏的数据。</span><span class="sxs-lookup"><span data-stu-id="2e12d-110">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>

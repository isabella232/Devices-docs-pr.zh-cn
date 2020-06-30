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
# <span data-ttu-id="6fe09-103">Surface 设备上的 DMA 保护</span><span class="sxs-lookup"><span data-stu-id="6fe09-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="6fe09-104">直接内存访问（DMA）保护旨在减少与使用可移动 SSDs 或外部存储设备相关的潜在安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="6fe09-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="6fe09-105">较新的 Surface 设备在默认情况下启用 DMA 保护。</span><span class="sxs-lookup"><span data-stu-id="6fe09-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="6fe09-106">其中包括 Surface Pro 7、Surface 笔记本3和 Surface Pro X。 若要检查设备上是否存在 DMA 保护功能，请打开 "系统信息" （"**开始**"  >  **msinfo32.exe**），如下图所示。</span><span class="sxs-lookup"><span data-stu-id="6fe09-106">These include Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![显示 DMA 保护已启用的系统信息](images/systeminfodma.png)

<span data-ttu-id="6fe09-108">如果 Surface 的可移动 SSD 被篡改，设备将关闭电源。</span><span class="sxs-lookup"><span data-stu-id="6fe09-108">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="6fe09-109">所产生的重启导致 UEFI 擦除内存，以擦除任何残留数据。</span><span class="sxs-lookup"><span data-stu-id="6fe09-109">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>

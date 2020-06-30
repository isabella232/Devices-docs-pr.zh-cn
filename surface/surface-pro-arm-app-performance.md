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
# <span data-ttu-id="ce6cb-103">Surface Pro X 应用兼容性</span><span class="sxs-lookup"><span data-stu-id="ce6cb-103">Surface Pro X app compatibility</span></span>

<span data-ttu-id="ce6cb-104">应用程序在基于 ARM 的 Windows 10 电脑（如 Surface Pro X）上以不同的方式运行。以下限制包括：</span><span class="sxs-lookup"><span data-stu-id="ce6cb-104">Applications run differently on ARM-based Windows 10 PCs such as Surface Pro X. Limitations include the following:</span></span>

- <span data-ttu-id="ce6cb-105">**硬件、游戏和应用的驱动程序仅适用于适用于基于 Windows 10 ARM 的电脑的硬件**。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-105">**Drivers for hardware, games and apps will only work if they're designed for a Windows 10 ARM-based PC**.</span></span> <span data-ttu-id="ce6cb-106">有关详细信息，请咨询硬件制造商或开发驱动程序的组织。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-106">For more info, check with the hardware manufacturer or the organization that developed the driver.</span></span> <span data-ttu-id="ce6cb-107">驱动程序是与硬件设备通信的软件程序，它们通常用于防病毒软件和反恶意软件、打印或 PDF 软件、辅助技术、CD 和 DVD 实用工具以及虚拟化软件。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-107">Drivers are software programs that communicate with hardware devices—they're commonly used for antivirus and antimalware software, printing or PDF software, assistive technologies, CD and DVD utilities, and virtualization software.</span></span> <span data-ttu-id="ce6cb-108">如果驱动程序不起作用，则依赖于它的应用或硬件将不起作用（至少不完全）。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-108">If a driver doesn’t work, the app or hardware that relies on it won’t work either (at least not fully).</span></span> <span data-ttu-id="ce6cb-109">仅当设备所依赖的驱动程序内置于 Windows 10 或硬件开发人员为设备发布了 ARM64 驱动程序时，外围设备和设备才可用。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-109">Peripherals and devices only work if the drivers they depend on are built into Windows 10, or if the hardware developer has released ARM64 drivers for the device.</span></span>
- <span data-ttu-id="ce6cb-110">**64 位（x64）应用不起作用**。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-110">**64-bit (x64) apps won’t work**.</span></span> <span data-ttu-id="ce6cb-111">你将需要64位（ARM64）应用、32位（ARM32）应用或32位（x86）应用。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-111">You'll need 64-bit (ARM64) apps, 32-bit (ARM32) apps, or 32-bit (x86) apps.</span></span> <span data-ttu-id="ce6cb-112">你通常可以找到32位（x86）版本的应用，但某些应用开发人员仅提供64位（x64）应用。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-112">You can usually find 32-bit (x86) versions of apps, but some app developers only offer 64-bit (x64) apps.</span></span>
- <span data-ttu-id="ce6cb-113">**某些游戏不起作用**。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-113">**Certain games won’t work**.</span></span> <span data-ttu-id="ce6cb-114">如果游戏和应用使用的 OpenGL 版本大于1.1，或者它们依赖于不是针对基于 Windows 10 ARM 的电脑的 "防外观" 驱动程序，则游戏和应用将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-114">Games and apps won't work if they use a version of OpenGL greater than 1.1, or if they rely on "anti-cheat" drivers that haven't been made for Windows 10 ARM-based PCs.</span></span> <span data-ttu-id="ce6cb-115">请与您的游戏发行者联系，了解游戏是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-115">Check with your game publisher to see if a game will work.</span></span>
- <span data-ttu-id="ce6cb-116">**自定义 Windows 体验的应用可能有问题**。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-116">**Apps that customize the Windows experience might have problems**.</span></span> <span data-ttu-id="ce6cb-117">这包括一些输入法编辑器（Ime）、辅助技术和云存储应用。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-117">This includes some input method editors (IMEs), assistive technologies, and cloud storage apps.</span></span> <span data-ttu-id="ce6cb-118">开发应用的组织确定其应用是否可在基于 Windows 10 ARM 的电脑上运行。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-118">The organization that develops the app determines whether their app will work on a Windows 10 ARM-based PC.</span></span>
- <span data-ttu-id="ce6cb-119">**无法安装某些第三方防病毒软件**。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-119">**Some third-party antivirus software can’t be installed**.</span></span> <span data-ttu-id="ce6cb-120">你将无法在基于 Windows 10 ARM 的电脑上安装某些第三方防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-120">You won't be able to install some third-party antivirus software on a Windows 10 ARM-based PC.</span></span> <span data-ttu-id="ce6cb-121">但是，Windows 安全将帮助你保护 Windows 10 设备受支持的生命周期。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-121">However, Windows Security will help keep you safe for the supported lifetime of your Windows 10 device.</span></span>
- <span data-ttu-id="ce6cb-122">**Windows 传真和扫描不可用**。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-122">**Windows Fax and Scan isn’t available**.</span></span> <span data-ttu-id="ce6cb-123">此功能在基于 Windows 10 ARM 的电脑上不可用。</span><span class="sxs-lookup"><span data-stu-id="ce6cb-123">This feature isn’t available on a Windows 10 ARM-based PC.</span></span>

<span data-ttu-id="ce6cb-124">有关应用兼容性的详细信息，请参阅[基于 Windows 10 ARM 的电脑常见问题解答](https://support.microsoft.com/en-us/help/4521606)</span><span class="sxs-lookup"><span data-stu-id="ce6cb-124">For more information about app compatibility, refer to [Windows 10 ARM-based PCs FAQ](https://support.microsoft.com/en-us/help/4521606)</span></span>

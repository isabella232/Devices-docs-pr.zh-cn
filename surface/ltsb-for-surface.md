---
title: 面向 Surface 设备（Surface）的长期服务通道
description: LTSB 不支持通用 Surface 设备，因此只能用于专用设备。
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 591ab98e79ea1ea7d373a3cdf8867601c7c0e832
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831551"
---
# <span data-ttu-id="6e3bc-103">面向 Surface 设备的长期服务通道（LTSC）</span><span class="sxs-lookup"><span data-stu-id="6e3bc-103">Long-Term Servicing Channel (LTSC) for Surface devices</span></span>

>[!WARNING]
><span data-ttu-id="6e3bc-104">有关本主题的更新信息，请参阅[与 Windows 10 长期服务通道的 Surface 设备兼容性](surface-device-compatibility-with-windows-10-ltsc.md)。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-104">For updated information on this topic, see [Surface device compatibility with Windows 10 Long-Term Servicing Channel](surface-device-compatibility-with-windows-10-ltsc.md).</span></span> <span data-ttu-id="6e3bc-105">有关此更新的其他信息，请参阅面向 IT 专业人士的面向 surface 博客的[surface 和 Windows 10 LTSB 兼容性公告的文档更新](https://blogs.technet.microsoft.com/surface/2017/04/11/documentation-updates-for-surface-and-windows-10-ltsb-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-105">For additional information on this update, see the [Documentation Updates for Surface and Windows 10 LTSB Compatibility](https://blogs.technet.microsoft.com/surface/2017/04/11/documentation-updates-for-surface-and-windows-10-ltsb-compatibility) post on the Surface Blog for IT Pros.</span></span>

<span data-ttu-id="6e3bc-106">不支持长期服务通道（LTSC）中的常规用途 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-106">General-purpose Surface devices in the Long-Term Servicing Channel (LTSC) are not supported.</span></span> <span data-ttu-id="6e3bc-107">通常情况下，如果 Surface 设备运行生产力软件（如 Microsoft Office），则它是一个一般用途的设备，它不符合 LTSC，而是半年频道。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-107">As a general guideline, if a Surface device runs productivity software, such as Microsoft Office, it is a general-purpose device that does not qualify for LTSC and should instead be on the Semi-Annual Channel.</span></span> 

>[!NOTE]
><span data-ttu-id="6e3bc-108">有关服务分支的详细信息，请参阅[Windows 服务概述](https://technet.microsoft.com/itpro/windows/manage/waas-overview)。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-108">For more information about the servicing branches, see [Overview of Windows as a service](https://technet.microsoft.com/itpro/windows/manage/waas-overview).</span></span>

<span data-ttu-id="6e3bc-109">LTSC 阻止 Surface 设备收到关键的 Windows 10 功能更新和某些非安全服务更新。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-109">LTSC prevents Surface devices from receiving critical Windows 10 feature updates and certain non-security servicing updates.</span></span> <span data-ttu-id="6e3bc-110">在 LTSC 配置中使用 Surface 设备的具有较差体验的客户将被指示切换到半年频道。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-110">Customers with poor experiences using Surface devices in the LTSC configuration will be instructed to switch to the Semi-Annual Channel.</span></span> <span data-ttu-id="6e3bc-111">此外，Windows 10 企业版 LTSB 版删除了 Surface 设备的核心功能，包括无缝的墨迹书写和触摸友好的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-111">Furthermore, the Windows 10 Enterprise LTSB edition removes core features of Surface devices, including seamless inking and touch-friendly applications.</span></span> <span data-ttu-id="6e3bc-112">它不包含关键的内置应用程序，包括 Microsoft Edge、OneNote、日历或相机。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-112">It does not contain key in-box applications including Microsoft Edge, OneNote, Calendar or Camera.</span></span> <span data-ttu-id="6e3bc-113">因此，工作效率受到影响，并且功能受到限制。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-113">Therefore, productivity is impacted and functionality is limited.</span></span> <span data-ttu-id="6e3bc-114">LTSC 不支持用作适用于一般用途 Surface 设备的服务解决方案。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-114">LTSC is not supported as a suitable servicing solution for general-purpose Surface devices.</span></span> 

<span data-ttu-id="6e3bc-115">常规用途 Surface 设备旨在在半年频道上运行，以接收完整的服务和固件更新，并与新的 Surface 功能的引入兼容。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-115">General-purpose Surface devices are intended to run on the Semi-Annual Channel to receive full servicing and firmware updates and forward compatibility with the introduction of new Surface features.</span></span> <span data-ttu-id="6e3bc-116">在半年频道中，只要 Microsoft 发布功能更新即可使用。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-116">In the Semi-Annual Channel, feature updates are available as soon as Microsoft releases them.</span></span>

<span data-ttu-id="6e3bc-117">特定方案中的 Surface 设备-例如控制医疗设备、销售点系统和 Atm 的 Pc-可能会考虑使用 LTSC。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-117">Surface devices in specialized scenarios–such as PCs that control medical equipment, point-of-sale systems, and ATMs–might consider the use of LTSC.</span></span> <span data-ttu-id="6e3bc-118">这些特殊用途的系统通常执行单个任务，并且不需要与组织中的其他设备一样频繁的功能更新。</span><span class="sxs-lookup"><span data-stu-id="6e3bc-118">These special-purpose systems typically perform a single task and do not require feature updates as frequently as other devices in the organization.</span></span> 

## <span data-ttu-id="6e3bc-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="6e3bc-119">Related topics</span></span>

- [<span data-ttu-id="6e3bc-120">Surface IT 专业人员博客</span><span class="sxs-lookup"><span data-stu-id="6e3bc-120">Surface IT Pro Blog</span></span>](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/bg-p/SurfaceITPro)


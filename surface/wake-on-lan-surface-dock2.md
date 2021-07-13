---
title: 通过 Surface Dock 2 LAN 唤醒
description: Surface Dock 2 为 LAN 上的唤醒和 WOL (最佳) 使管理员能够远程唤醒设备并自动执行管理任务。
keywords: 更新， 部署， 驱动程序， wol， lan 上唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 7/02/2021
ms.openlocfilehash: 4a74efb8af776e9805ad3148ea656f0a65d5d09c
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643848"
---
# <a name="wake-on-lan-with-surface-dock-2"></a><span data-ttu-id="ac411-104">通过 Surface Dock 2 LAN 唤醒</span><span class="sxs-lookup"><span data-stu-id="ac411-104">Wake On LAN with Surface Dock 2</span></span>

<span data-ttu-id="ac411-105">若要使设备完全保持最新，IT 管理员需要能够在设备不使用时（通常是夜间维护时段）管理设备。</span><span class="sxs-lookup"><span data-stu-id="ac411-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="ac411-106">Surface Dock 2 为 LAN (WOL 上的唤醒提供最佳支持) 使管理员能够远程唤醒设备，并自动使用 Microsoft Endpoint Manager 或其他第三方解决方案执行管理任务。</span><span class="sxs-lookup"><span data-stu-id="ac411-106">Surface Dock 2 provides the best support for Wake on LAN (WOL) enabling admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or other third party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac411-107">要求</span><span class="sxs-lookup"><span data-stu-id="ac411-107">Requirements</span></span>

<span data-ttu-id="ac411-108">设备必须与 Surface 扩展坞 2 建立有线连接，并持续连接到交流电源。</span><span class="sxs-lookup"><span data-stu-id="ac411-108">Devices must have a wired connection with Surface Dock 2 and stay connected to AC Power.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a><span data-ttu-id="ac411-110">支持的 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="ac411-110">Supported Surface devices</span></span>

- <span data-ttu-id="ac411-111">Surface Laptop 4 (Intel 处理器) </span><span class="sxs-lookup"><span data-stu-id="ac411-111">Surface Laptop 4 (Intel processors)</span></span>
- <span data-ttu-id="ac411-112">Surface Laptop 4 (AMD 处理器) </span><span class="sxs-lookup"><span data-stu-id="ac411-112">Surface Laptop 4 (AMD processors)</span></span>
- <span data-ttu-id="ac411-113">Surface Laptop 3 (Intel 处理器) </span><span class="sxs-lookup"><span data-stu-id="ac411-113">Surface Laptop 3 (Intel processors)</span></span>
- <span data-ttu-id="ac411-114">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="ac411-114">Surface Pro 7+</span></span>
- <span data-ttu-id="ac411-115">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="ac411-115">Surface Pro 7</span></span>
- <span data-ttu-id="ac411-116">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="ac411-116">Surface Pro X</span></span>
- <span data-ttu-id="ac411-117">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="ac411-117">Surface Go 2</span></span>
- <span data-ttu-id="ac411-118">Surface Laptop转到</span><span class="sxs-lookup"><span data-stu-id="ac411-118">Surface Laptop Go</span></span>
- <span data-ttu-id="ac411-119">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="ac411-119">Surface Book 3</span></span>

<span data-ttu-id="ac411-120">Surface Dock 2 为以下电源状态中的设备提供 WOL 支持：</span><span class="sxs-lookup"><span data-stu-id="ac411-120">Surface Dock 2 provides WOL support for devices in the following power states:</span></span>

- <span data-ttu-id="ac411-121">连接待机</span><span class="sxs-lookup"><span data-stu-id="ac411-121">Connected standby</span></span>
- <span data-ttu-id="ac411-122">休眠 (S4 电源状态) </span><span class="sxs-lookup"><span data-stu-id="ac411-122">Hibernation (S4 power state)</span></span>
- <span data-ttu-id="ac411-123">关机 (S5"软关闭"电源状态) </span><span class="sxs-lookup"><span data-stu-id="ac411-123">Shutdown (S5 “soft off” power state)</span></span>

<span data-ttu-id="ac411-124">若要详细了解电源状态，请参阅 [系统电源状态](/windows/win32/power/system-power-states)。</span><span class="sxs-lookup"><span data-stu-id="ac411-124">To learn more about power states, see [System Power States](/windows/win32/power/system-power-states).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="ac411-125">工作原理</span><span class="sxs-lookup"><span data-stu-id="ac411-125">How it works</span></span>

<span data-ttu-id="ac411-126">不使用时，Surface 设备将进入空闲的低电源状态，称为现代待机或连接待机。</span><span class="sxs-lookup"><span data-stu-id="ac411-126">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="ac411-127">IT 管理员可以使用唤醒请求远程触发设备 (包含目标 Surface 设备的媒体访问控制 (MAC) 地址的神奇数据包) 。</span><span class="sxs-lookup"><span data-stu-id="ac411-127">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="ac411-128">许多管理解决方案（Microsoft Endpoint Configuration Manager第三方Microsoft Store应用）都提供对 WOL 的内置支持。</span><span class="sxs-lookup"><span data-stu-id="ac411-128">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span>

<span data-ttu-id="ac411-129">若要在没有 Surface 扩展坞 2 的设备上启用 WOL，请参阅 [Surface 设备的 LAN 唤醒](wake-on-lan-for-surface-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="ac411-129">To enable WOL on devices without Surface Dock 2, see [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="ac411-130">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="ac411-130">Learn more</span></span>

- [<span data-ttu-id="ac411-131">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="ac411-131">Surface Dock 2</span></span>](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [<span data-ttu-id="ac411-132">Surface 设备的 LAN 唤醒</span><span class="sxs-lookup"><span data-stu-id="ac411-132">Wake On LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)
- [<span data-ttu-id="ac411-133">系统电源状态</span><span class="sxs-lookup"><span data-stu-id="ac411-133">System Power States</span></span>](/windows/win32/power/system-power-states)
- [<span data-ttu-id="ac411-134">在 LAN 上配置唤醒 - Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ac411-134">Configure Wake on LAN - Configuration Manager</span></span>](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)

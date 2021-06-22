---
title: Surface 设备的 LAN 唤醒
description: 了解如何使用 LAN 唤醒远程唤醒设备以自动执行管理任务。
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
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613793"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="4f163-104">Surface 设备的 LAN 唤醒</span><span class="sxs-lookup"><span data-stu-id="4f163-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="4f163-105">若要使设备完全保持最新，IT 管理员需要能够在设备不使用时（通常是夜间维护时段）管理设备。</span><span class="sxs-lookup"><span data-stu-id="4f163-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="4f163-106">LAN 唤醒 (WOL) 使管理员能够远程唤醒设备，并自动使用 Microsoft Endpoint Manager 或第三方解决方案执行管理任务。</span><span class="sxs-lookup"><span data-stu-id="4f163-106">Wake on LAN (WOL) enables admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or third-party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="4f163-107">要求</span><span class="sxs-lookup"><span data-stu-id="4f163-107">Requirements</span></span>

<span data-ttu-id="4f163-108">设备必须连接到交流电源，并且具有与以下兼容的以太网适配器之一的有线连接：</span><span class="sxs-lookup"><span data-stu-id="4f163-108">Devices must be connected to AC power and have a wired connection with one of the following compatible Ethernet adapters:</span></span>

- <span data-ttu-id="4f163-109">Surface USB 3.0 千兆位以太网适配器</span><span class="sxs-lookup"><span data-stu-id="4f163-109">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>
- <span data-ttu-id="4f163-110">Surface 以太网适配器</span><span class="sxs-lookup"><span data-stu-id="4f163-110">Surface Ethernet Adapter</span></span>
- <span data-ttu-id="4f163-111">Surface USB-C 到以太网和 USB 适配器</span><span class="sxs-lookup"><span data-stu-id="4f163-111">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="4f163-112">Microsoft USB-C 旅行适配器中心</span><span class="sxs-lookup"><span data-stu-id="4f163-112">Microsoft USB-C Travel Adapter Hub</span></span>
- <span data-ttu-id="4f163-113">Surface 扩展坞</span><span class="sxs-lookup"><span data-stu-id="4f163-113">Surface Dock</span></span>
- <span data-ttu-id="4f163-114">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="4f163-114">Surface Dock 2</span></span>

> [!NOTE]
> <span data-ttu-id="4f163-115">Surface Dock 2 提供了对 LAN 唤醒的最佳支持，无需任何其他 IT 配置。</span><span class="sxs-lookup"><span data-stu-id="4f163-115">Surface Dock 2 provides the best support for Wake on LAN without the need for any additional IT configuration.</span></span> <span data-ttu-id="4f163-116">若要了解更多信息，请参阅 [Surface Dock 2 的 LAN 唤醒](wake-on-lan-surface-dock2.md)</span><span class="sxs-lookup"><span data-stu-id="4f163-116">To learn more, see [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="4f163-117">工作原理</span><span class="sxs-lookup"><span data-stu-id="4f163-117">How it works</span></span>

<span data-ttu-id="4f163-118">不使用时，Surface 设备将进入空闲的低电源状态，称为现代待机或连接待机。</span><span class="sxs-lookup"><span data-stu-id="4f163-118">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="4f163-119">IT 管理员可以使用唤醒请求远程触发设备 (包含目标 Surface 设备的媒体访问控制 (MAC) 地址的神奇数据包) 。</span><span class="sxs-lookup"><span data-stu-id="4f163-119">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="4f163-120">许多管理解决方案（Microsoft Endpoint Configuration Manager第三方Microsoft Store应用）都提供对 WOL 的内置支持。</span><span class="sxs-lookup"><span data-stu-id="4f163-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="4f163-121">若要了解有关使用 Endpoint Configuration Manager 唤醒设备的信息，请参阅[Configure Wake on LAN - Configuration Manager。](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)</span><span class="sxs-lookup"><span data-stu-id="4f163-121">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>

<span data-ttu-id="4f163-122">对 LAN 唤醒的支持因睡眠状态而异：连接待机或休眠 (S4 电源状态) 。</span><span class="sxs-lookup"><span data-stu-id="4f163-122">Support for Wake on LAN varies depending on sleep state:  Connected Standby or Hibernation (S4 power state).</span></span>

## <a name="connected-standby"></a><span data-ttu-id="4f163-123">连接待机</span><span class="sxs-lookup"><span data-stu-id="4f163-123">Connected Standby</span></span>

<span data-ttu-id="4f163-124">默认情况下，Windows 10待机时支持 Surface 设备在 LAN 上唤醒。</span><span class="sxs-lookup"><span data-stu-id="4f163-124">By default, Windows 10 supports Wake on LAN for Surface devices in Connected Standby.</span></span>

### <a name="supported-surface-devices---connected-standby"></a><span data-ttu-id="4f163-125">受支持的 Surface 设备 - 连接待机</span><span class="sxs-lookup"><span data-stu-id="4f163-125">Supported Surface devices - Connected Standby</span></span>

- <span data-ttu-id="4f163-126">Surface Laptop 4 (Intel 处理器) </span><span class="sxs-lookup"><span data-stu-id="4f163-126">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="4f163-127">Surface Laptop 3 (Intel 处理器) </span><span class="sxs-lookup"><span data-stu-id="4f163-127">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="4f163-128">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="4f163-128">Surface Pro 7+</span></span>
- <span data-ttu-id="4f163-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="4f163-129">Surface Pro 7</span></span>
- <span data-ttu-id="4f163-130">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="4f163-130">Surface Pro X</span></span>
- <span data-ttu-id="4f163-131">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="4f163-131">Surface Go 2</span></span>
- <span data-ttu-id="4f163-132">Surface Laptop转到</span><span class="sxs-lookup"><span data-stu-id="4f163-132">Surface Laptop Go</span></span>
- <span data-ttu-id="4f163-133">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="4f163-133">Surface Book 3</span></span>

## <a name="hibernation"></a><span data-ttu-id="4f163-134">休眠</span><span class="sxs-lookup"><span data-stu-id="4f163-134">Hibernation</span></span>

<span data-ttu-id="4f163-135">若要将设备从休眠状态中唤醒，需要为连接到 Surface Dock 2) 的设备启用[Surface Enterprise](surface-enterprise-management-mode.md)管理模式 (SEMM)  (UEFI 策略设置。</span><span class="sxs-lookup"><span data-stu-id="4f163-135">To wake devices out of Hibernation requires enabling a UEFI policy setting via [Surface Enterprise Management Mode](surface-enterprise-management-mode.md) (SEMM) (not required for devices connected to Surface Dock 2).</span></span>

### <a name="supported-surface-devices---hibernation"></a><span data-ttu-id="4f163-136">受支持的 Surface 设备 - 休眠</span><span class="sxs-lookup"><span data-stu-id="4f163-136">Supported Surface devices - Hibernation</span></span>

- <span data-ttu-id="4f163-137">Surface Laptop 4 (Intel 处理器) </span><span class="sxs-lookup"><span data-stu-id="4f163-137">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="4f163-138">Surface Laptop 3 (Intel 处理器) </span><span class="sxs-lookup"><span data-stu-id="4f163-138">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="4f163-139">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="4f163-139">Surface Pro 7+</span></span>
- <span data-ttu-id="4f163-140">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="4f163-140">Surface Pro 7</span></span>
- <span data-ttu-id="4f163-141">Surface Laptop转到</span><span class="sxs-lookup"><span data-stu-id="4f163-141">Surface Laptop Go</span></span>
- <span data-ttu-id="4f163-142">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="4f163-142">Surface Book 3</span></span>

### <a name="to-enable-wake-on-lan-uefi-setting"></a><span data-ttu-id="4f163-143">启用 LAN UEFI 唤醒设置</span><span class="sxs-lookup"><span data-stu-id="4f163-143">To enable Wake on LAN UEFI setting</span></span>

<span data-ttu-id="4f163-144">若要启用 LAN UEFI 唤醒设置，你需要将目标设备注册到 SEMM，创建配置包，然后应用该包到设备。</span><span class="sxs-lookup"><span data-stu-id="4f163-144">To enable the Wake on LAN UEFI setting you need to enroll target devices into SEMM, create a configuration package, and apply the package to the devices.</span></span> <span data-ttu-id="4f163-145">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="4f163-145">For more information, refer to:</span></span>

- [<span data-ttu-id="4f163-146">Surface 企业管理模式</span><span class="sxs-lookup"><span data-stu-id="4f163-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="4f163-147">使用 SEMM 注册并配置 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="4f163-147">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)

1. <span data-ttu-id="4f163-148">下载并安装 [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="4f163-148">Download and install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
2. <span data-ttu-id="4f163-149">选择 **"启动**  >  **配置包**  >  **创建**  > **+ 证书保护"。**</span><span class="sxs-lookup"><span data-stu-id="4f163-149">Select **Start** > **Configuration Package** > **Create** >**+ Certificate Protection**.</span></span>
3. <span data-ttu-id="4f163-150">转到高级**设置，** 将 LAN**上的唤醒切换到\*\*\*\*开**。</span><span class="sxs-lookup"><span data-stu-id="4f163-150">Go to **Advanced settings** and switch **Wake on LAN** to **On**.</span></span>
4. <span data-ttu-id="4f163-151">将程序包应用到目标设备。</span><span class="sxs-lookup"><span data-stu-id="4f163-151">Apply the package to target devices.</span></span>

    > [!div class="mx-imgBorder"]
    > ![启用 LAN UEFI 策略设置唤醒](images/wol-uefi.png)

## <a name="learn-more"></a><span data-ttu-id="4f163-153">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="4f163-153">Learn more</span></span>

- [<span data-ttu-id="4f163-154">Surface 扩展坞 2 的 LAN 唤醒</span><span class="sxs-lookup"><span data-stu-id="4f163-154">Wake on LAN for Surface Dock 2</span></span>](wake-on-lan-surface-dock2.md)
- [<span data-ttu-id="4f163-155">Microsoft Surface USB-C 到以太网和 USB 适配器</span><span class="sxs-lookup"><span data-stu-id="4f163-155">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [<span data-ttu-id="4f163-156">Surface USB 3.0 千兆位以太网适配器</span><span class="sxs-lookup"><span data-stu-id="4f163-156">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)

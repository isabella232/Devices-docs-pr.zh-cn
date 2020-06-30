---
title: 电池限制设置（Surface）
description: 电池限制是一种 UEFI 设置，可更改 Surface 设备电池的充电方式，并可能延长其寿命。
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831720"
---
# <span data-ttu-id="62bf6-103">电池限制设置</span><span class="sxs-lookup"><span data-stu-id="62bf6-103">Battery Limit setting</span></span>

<span data-ttu-id="62bf6-104">电池限制选项是一项 UEFI 设置，可更改 Surface 设备电池的充电方式，并可能延长其寿命。</span><span class="sxs-lookup"><span data-stu-id="62bf6-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="62bf6-105">如果设备持续连接到电源，例如设备已集成到展台解决方案中，则建议使用此设置。</span><span class="sxs-lookup"><span data-stu-id="62bf6-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="62bf6-106">电池限制的工作原理</span><span class="sxs-lookup"><span data-stu-id="62bf6-106">How Battery Limit works</span></span>

<span data-ttu-id="62bf6-107">设置电池限制的设备将更改用于对设备电池充电的协议。</span><span class="sxs-lookup"><span data-stu-id="62bf6-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="62bf6-108">启用电池限制后，电池电量将限制为其最大容量的50%。</span><span class="sxs-lookup"><span data-stu-id="62bf6-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="62bf6-109">Windows 中报告的费用级别将反映此限制。</span><span class="sxs-lookup"><span data-stu-id="62bf6-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="62bf6-110">因此，它将显示将电池费用最高达50%，并且不会超出此限制。</span><span class="sxs-lookup"><span data-stu-id="62bf6-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="62bf6-111">如果在设备超过50% 时启用电池限制，电池图标将显示设备已插入但正在放电，直到设备达到其最大收费容量的50%。</span><span class="sxs-lookup"><span data-stu-id="62bf6-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="62bf6-112">支持的设备</span><span class="sxs-lookup"><span data-stu-id="62bf6-112">Supported devices</span></span>
<span data-ttu-id="62bf6-113">电池限制 UEFI 设置内置于最新的 Surface 设备中，包括 Surface Pro 7 和 Surface 笔记本3。</span><span class="sxs-lookup"><span data-stu-id="62bf6-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7 and Surface Laptop 3.</span></span> <span data-ttu-id="62bf6-114">以前的设备需要[SURFACE UEFI 固件更新](manage-surface-driver-and-firmware-updates.md)，可通过 Windows 更新或通过[Surface 支持网站](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)上的 MSI 驱动程序和固件程序包进行更新。</span><span class="sxs-lookup"><span data-stu-id="62bf6-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="62bf6-115">对于每个受支持的设备所需的特定 Surface UEFI 版本，请选中["为必须插入长时间的 surface 设备启用" 电池限制 "](https://support.microsoft.com/help/4464941) 。</span><span class="sxs-lookup"><span data-stu-id="62bf6-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="62bf6-116">在 Surface UEFI 中启用电池限制（Surface Pro 4 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="62bf6-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="62bf6-117">"Surface UEFI 电池限制" 设置可通过启动到 Surface UEFI （打开设备时为**电源 + 音量**）进行配置。</span><span class="sxs-lookup"><span data-stu-id="62bf6-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="62bf6-118">选择 "**启动配置**"，然后在 "**高级选项**" 下，将 "**启用电池限制模式**" 切换为 **"开"**。</span><span class="sxs-lookup"><span data-stu-id="62bf6-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![高级选项的屏幕截图](images/enable-bl.png) 

## <span data-ttu-id="62bf6-120">在 Surface Go 和 Surface Go 2 上启用电池限制</span><span class="sxs-lookup"><span data-stu-id="62bf6-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="62bf6-121">图面电池限制设置可通过启动到 Surface UEFI （打开设备时为**电源 + 音量**）进行配置。</span><span class="sxs-lookup"><span data-stu-id="62bf6-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="62bf6-122">选择 "**启动配置**"，然后在 "**展台模式**" 下，向右移动滑块以将电池限制设置为 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="62bf6-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![表面上的展台模式电池电量限制的屏幕截图](images/go-batterylimit.png) 

## <span data-ttu-id="62bf6-124">在 Surface UEFI 中启用电池限制（Surface Pro 3）</span><span class="sxs-lookup"><span data-stu-id="62bf6-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="62bf6-125">"Surface UEFI 电池限制" 设置可通过启动到 Surface UEFI （打开设备时为**电源 + 音量**）进行配置。</span><span class="sxs-lookup"><span data-stu-id="62bf6-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="62bf6-126">选择 "**展台模式**"，选择 "**电池限制**"，然后选择 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="62bf6-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![高级选项的屏幕截图](images/enable-bl-sp3.png) 

![高级选项的屏幕截图](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="62bf6-129">使用 Surface Enterprise 管理模式（SEMM）或 Surface Pro 3 固件 PowerShell 脚本启用电池限制</span><span class="sxs-lookup"><span data-stu-id="62bf6-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="62bf6-130">还可通过以下方法配置图面 UEFI 电池限额：</span><span class="sxs-lookup"><span data-stu-id="62bf6-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="62bf6-131">Surface Pro 4 及更高版本</span><span class="sxs-lookup"><span data-stu-id="62bf6-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="62bf6-132">Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="62bf6-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="62bf6-133">Surface UEFI 管理器 Powershell 脚本（SEMM_Powershell.zip）在[IT 下载的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)中</span><span class="sxs-lookup"><span data-stu-id="62bf6-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="62bf6-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="62bf6-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="62bf6-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="62bf6-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="62bf6-136">使用 Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="62bf6-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="62bf6-137">要配置电池限制模式，请在 SEMM （Surface Pro 4 及更高版本）中的 "**高级设置**" 配置页面上设置**展台覆盖**设置。</span><span class="sxs-lookup"><span data-stu-id="62bf6-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![高级设置的屏幕截图](images/semm-bl.png)

### <span data-ttu-id="62bf6-139">使用 Surface UEFI 管理器 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="62bf6-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="62bf6-140">电池限制功能通过以下设置进行控制：</span><span class="sxs-lookup"><span data-stu-id="62bf6-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="62bf6-141">**说明**：电池使用模式的活动管理方案</span><span class="sxs-lookup"><span data-stu-id="62bf6-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="62bf6-142">**默认**：</span><span class="sxs-lookup"><span data-stu-id="62bf6-142">**Default**:</span></span>  `0` 

<span data-ttu-id="62bf6-143">将此设置为 `1` 以启用电池限制。</span><span class="sxs-lookup"><span data-stu-id="62bf6-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="62bf6-144">使用 Surface Pro 3 固件工具</span><span class="sxs-lookup"><span data-stu-id="62bf6-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="62bf6-145">电池限制功能通过以下设置进行控制：</span><span class="sxs-lookup"><span data-stu-id="62bf6-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="62bf6-146">**名称**： BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="62bf6-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="62bf6-147">**说明**： BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="62bf6-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="62bf6-148">**当前值**：</span><span class="sxs-lookup"><span data-stu-id="62bf6-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="62bf6-149">**默认值**：</span><span class="sxs-lookup"><span data-stu-id="62bf6-149">**Default Value**:</span></span> `0`

<span data-ttu-id="62bf6-150">**建议的值**：</span><span class="sxs-lookup"><span data-stu-id="62bf6-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="62bf6-151">将此设置为 `1` 以启用电池限制。</span><span class="sxs-lookup"><span data-stu-id="62bf6-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="62bf6-152">若要配置此设置，必须使用[SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="62bf6-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 


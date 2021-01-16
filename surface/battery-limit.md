---
title: 'Surface (的电池) '
description: 电池限制是 UEFI 设置，可更改 Surface 设备电池的充电情况，并延长其使用时间。
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
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271139"
---
# <span data-ttu-id="ae808-103">电池限制设置</span><span class="sxs-lookup"><span data-stu-id="ae808-103">Battery Limit setting</span></span>

<span data-ttu-id="ae808-104">电池限制选项是 UEFI 设置，可更改 Surface 设备电池的充电方式并延长其使用时间。</span><span class="sxs-lookup"><span data-stu-id="ae808-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="ae808-105">当设备连续连接到电源时（例如，当设备集成到展台解决方案中时）建议使用此设置。</span><span class="sxs-lookup"><span data-stu-id="ae808-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="ae808-106">电池限制的工作原理</span><span class="sxs-lookup"><span data-stu-id="ae808-106">How Battery Limit works</span></span>

<span data-ttu-id="ae808-107">在"电池限制"上设置设备会更改用于为设备电池充电的协议。</span><span class="sxs-lookup"><span data-stu-id="ae808-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="ae808-108">启用电池限制后，电池电量将限制为最大容量的 50%。</span><span class="sxs-lookup"><span data-stu-id="ae808-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="ae808-109">Windows 中报告的费用级别将反映此限制。</span><span class="sxs-lookup"><span data-stu-id="ae808-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="ae808-110">因此，它将显示电池的充电率最高为 50%，并且不会超出此限制。</span><span class="sxs-lookup"><span data-stu-id="ae808-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="ae808-111">如果在设备充电超过 50% 时启用电池限制，电池图标将显示设备已接通电源，但正在等待，直到设备达到最大充电容量的 50%。</span><span class="sxs-lookup"><span data-stu-id="ae808-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="ae808-112">支持的设备</span><span class="sxs-lookup"><span data-stu-id="ae808-112">Supported devices</span></span>

<span data-ttu-id="ae808-113">电池限制 UEFI 设置内置于最新的 Surface 设备中，包括 Surface Pro 7+、Surface Pro 7 和 Surface Laptop 3。</span><span class="sxs-lookup"><span data-stu-id="ae808-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7+, Surface Pro 7, and Surface Laptop 3.</span></span> <span data-ttu-id="ae808-114">较早的设备需要 [Surface UEFI](manage-surface-driver-and-firmware-updates.md)固件更新，可通过 Windows 更新或通过 Surface 支持站点上的 MSI 驱动程序和固件 [包获取](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)。</span><span class="sxs-lookup"><span data-stu-id="ae808-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="ae808-115">选中 ["为必须](https://support.microsoft.com/help/4464941) 长时间插入的 Surface 设备启用"电池限制"，以针对每个受支持的设备所需的特定 Surface UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="ae808-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="ae808-116">在 Surface UEFI (Surface Pro 4 及更高版本中启用电池) </span><span class="sxs-lookup"><span data-stu-id="ae808-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="ae808-117">Surface UEFI 电池限制设置可通过在打开设备时启动到 Surface UEFI (**Power + Vol Up** 来) 。</span><span class="sxs-lookup"><span data-stu-id="ae808-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="ae808-118">选择**启动配置**，然后在"**高级**选项"下，将"**启用电池限制模式"** 切换为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="ae808-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![电池限制高级选项](images/enable-bl.png) 

## <span data-ttu-id="ae808-120">在 Surface Go 和 Surface Go 2 上启用电池限制</span><span class="sxs-lookup"><span data-stu-id="ae808-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="ae808-121">Surface 电池限制设置可通过在打开设备时启动到 Surface UEFI (**Power + Vol Up** 进行) 。</span><span class="sxs-lookup"><span data-stu-id="ae808-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="ae808-122">选择**启动配置**，然后在展台**模式下**，将滑块向右移动以将电池限制设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="ae808-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Surface Go 中的展台模式电池限制](images/go-batterylimit.png) 

## <span data-ttu-id="ae808-124">在 Surface UEFI 中启用 Surface Pro 3 (电池) </span><span class="sxs-lookup"><span data-stu-id="ae808-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="ae808-125">Surface UEFI 电池限制设置可通过在打开设备时启动到 Surface UEFI (**Power + Vol Up** 来) 。</span><span class="sxs-lookup"><span data-stu-id="ae808-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="ae808-126">选择**展台模式**，选择**电池限制**，**然后选择启用。**</span><span class="sxs-lookup"><span data-stu-id="ae808-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![高级选项的屏幕截图](images/enable-bl-sp3.png) 

![高级选项](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="ae808-129">使用 Surface Enterprise Management Mode (SEMM) Surface Pro 3 固件 PowerShell 脚本启用电池限制</span><span class="sxs-lookup"><span data-stu-id="ae808-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="ae808-130">Surface UEFI 电池限制也可通过以下方法进行配置：</span><span class="sxs-lookup"><span data-stu-id="ae808-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="ae808-131">Surface Pro 4 及更高版本</span><span class="sxs-lookup"><span data-stu-id="ae808-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="ae808-132">Microsoft Surface UEFI 配置程序</span><span class="sxs-lookup"><span data-stu-id="ae808-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="ae808-133">Surface UEFI 管理器 Powershell 脚本 (SEMM_Powershell.zip) [适用于 IT 的 Surface Tools 下载](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="ae808-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="ae808-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="ae808-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="ae808-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="ae808-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="ae808-136">使用 Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="ae808-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="ae808-137">若要配置电池限制模式，请设置\*\*\*\* SEMM Surface \*\*\*\* Pro 4 及更高版本中"高级设置"配置 ("展台覆盖) 。</span><span class="sxs-lookup"><span data-stu-id="ae808-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![高级设置的屏幕截图](images/semm-bl.png)

### <span data-ttu-id="ae808-139">使用 Surface UEFI 管理器 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="ae808-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="ae808-140">电池限制功能通过以下设置进行控制：</span><span class="sxs-lookup"><span data-stu-id="ae808-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="ae808-141">**说明**：电池使用模式的活动管理方案</span><span class="sxs-lookup"><span data-stu-id="ae808-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="ae808-142">**默认**：</span><span class="sxs-lookup"><span data-stu-id="ae808-142">**Default**:</span></span>  `0` 

<span data-ttu-id="ae808-143">设置此选项 `1` 以启用电池限制。</span><span class="sxs-lookup"><span data-stu-id="ae808-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="ae808-144">使用 Surface Pro 3 固件工具</span><span class="sxs-lookup"><span data-stu-id="ae808-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="ae808-145">电池限制功能通过以下设置进行控制：</span><span class="sxs-lookup"><span data-stu-id="ae808-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="ae808-146">**名称**：BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="ae808-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="ae808-147">**说明**：BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="ae808-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="ae808-148">**当前值**：</span><span class="sxs-lookup"><span data-stu-id="ae808-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="ae808-149">**默认值：**</span><span class="sxs-lookup"><span data-stu-id="ae808-149">**Default Value**:</span></span> `0`

<span data-ttu-id="ae808-150">**建议的值**：</span><span class="sxs-lookup"><span data-stu-id="ae808-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="ae808-151">设置此选项 `1` 以启用电池限制。</span><span class="sxs-lookup"><span data-stu-id="ae808-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="ae808-152">若要配置此设置，必须使用[SP3_Firmware_Powershell_Scripts.zip。 ](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="ae808-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 


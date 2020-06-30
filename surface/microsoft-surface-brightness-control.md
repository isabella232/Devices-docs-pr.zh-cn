---
title: Surface 亮度控制
description: 本主题介绍了如何使用 Surface 亮度控件应用在销售点和展台方案中管理显示器亮度。
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 197ed9fe1abc880779ad6bb0f85d2970086395f6
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831631"
---
# <span data-ttu-id="e6e1a-103">Surface 亮度控制</span><span class="sxs-lookup"><span data-stu-id="e6e1a-103">Surface Brightness Control</span></span>

<span data-ttu-id="e6e1a-104">当在销售点或其他 "永不开" 的展台方案中部署 Surface 设备时，可以使用新的 Surface 亮度控制应用优化电源管理。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-104">When deploying Surface devices in point of sale or other “always-on” kiosk scenarios, you can optimize power management using the new Surface Brightness Control app.</span></span>

<span data-ttu-id="e6e1a-105">可通过适用于[它的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)下载。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-105">Available for download with [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
<span data-ttu-id="e6e1a-106">Surface 亮度控件旨在帮助减少热量负载，降低部署 Surface 设备的整体碳足迹。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-106">Surface Brightness Control is designed to help reduce thermal load and lower the overall carbon footprint for deployed Surface devices.</span></span>
<span data-ttu-id="e6e1a-107">如果您计划仅从下载页面获取此工具，请在 "可用" 列表中选择文件**Surface_Brightness_Control_v1.16.137.0.msi** 。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-107">If you plan to get only this tool from the download page, select the file **Surface_Brightness_Control_v1.16.137.0.msi** in the available list.</span></span>
<span data-ttu-id="e6e1a-108">此工具在未使用时将自动调暗屏幕，并且包括以下配置选项：</span><span class="sxs-lookup"><span data-stu-id="e6e1a-108">The tool automatically dims the screen when not in use and includes the following configuration options:</span></span>

- <span data-ttu-id="e6e1a-109">屏幕变暗之前的非活动期。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-109">Period of inactivity before dimming the display.</span></span>

- <span data-ttu-id="e6e1a-110">变暗时的亮度级别。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-110">Brightness level when dimmed.</span></span>

- <span data-ttu-id="e6e1a-111">使用时的最大亮度级别。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-111">Maximum brightness level when in use.</span></span>

**<span data-ttu-id="e6e1a-112">运行 Surface 亮度控件：</span><span class="sxs-lookup"><span data-stu-id="e6e1a-112">To run Surface Brightness Control:</span></span>**

- <span data-ttu-id="e6e1a-113">在目标设备上安装 surfacebrightnesscontrol.msi，表面亮度控件将立即开始工作。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-113">Install surfacebrightnesscontrol.msi on the target device and Surface Brightness Control will begin working immediately.</span></span>

## <span data-ttu-id="e6e1a-114">配置 Surface 亮度控件</span><span class="sxs-lookup"><span data-stu-id="e6e1a-114">Configuring Surface Brightness Control</span></span>

<span data-ttu-id="e6e1a-115">你可以通过 Windows 注册表调整默认值。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-115">You can adjust the default values via the Windows Registry.</span></span> <span data-ttu-id="e6e1a-116">有关使用 Windows 注册表的详细信息，请参阅[注册表文档](https://docs.microsoft.com/windows/desktop/sysinfo/registry)。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-116">For more information about using the Windows Registry, refer to the [Registry documentation](https://docs.microsoft.com/windows/desktop/sysinfo/registry).</span></span>

1.  <span data-ttu-id="e6e1a-117">从命令提示符处运行 regedit，打开 Windows 注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-117">Run regedit from a command prompt to open the Windows Registry Editor.</span></span>
    
      - <span data-ttu-id="e6e1a-118">Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\WOW6432Node\Microsoft\Surface\Surface 亮度控件 </span><span class="sxs-lookup"><span data-stu-id="e6e1a-118">Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Surface\Surface Brightness Control</span></span>\ 
    
    <span data-ttu-id="e6e1a-119">如果您运行的是较旧版本的 Surface 亮度控件，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e6e1a-119">If you're running an older version of Surface Brightness control, run the following command instead:</span></span>
    
      - <span data-ttu-id="e6e1a-120">Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\Microsoft\Surface\Surface 亮度控件 </span><span class="sxs-lookup"><span data-stu-id="e6e1a-120">Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Surface\Surface Brightness Control</span></span>\


| <span data-ttu-id="e6e1a-121">注册表设置</span><span class="sxs-lookup"><span data-stu-id="e6e1a-121">Registry Setting</span></span> | <span data-ttu-id="e6e1a-122">数据</span><span class="sxs-lookup"><span data-stu-id="e6e1a-122">Data</span></span>| <span data-ttu-id="e6e1a-123">描述</span><span class="sxs-lookup"><span data-stu-id="e6e1a-123">Description</span></span>  
|-----------|------------|---------------
| <span data-ttu-id="e6e1a-124">已启用亮度控制</span><span class="sxs-lookup"><span data-stu-id="e6e1a-124">Brightness Control Enabled</span></span>  |  <span data-ttu-id="e6e1a-125">默认值：01</span><span class="sxs-lookup"><span data-stu-id="e6e1a-125">Default: 01</span></span>  <br> <span data-ttu-id="e6e1a-126">选项：01，00</span><span class="sxs-lookup"><span data-stu-id="e6e1a-126">Option: 01, 00</span></span> <br> <span data-ttu-id="e6e1a-127">类型： REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="e6e1a-127">Type: REG_BINARY</span></span> |  <span data-ttu-id="e6e1a-128">此设置允许你打开或关闭 Surface 亮度控件。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-128">This setting allows you to turn Surface Brightness Control on or off.</span></span> <span data-ttu-id="e6e1a-129">若要禁用 Surface 亮度控件，请将值设置为00。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-129">To disable Surface Brightness Control, set the value to 00.</span></span> <span data-ttu-id="e6e1a-130">如果未配置此设置，则 "表面亮度" 控件打开。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-130">If you do not configure this setting, Surface Brightness Control is on.</span></span> |
| <span data-ttu-id="e6e1a-131">启用电源上的亮度控制</span><span class="sxs-lookup"><span data-stu-id="e6e1a-131">Brightness Control On Power Enabled</span></span>| <span data-ttu-id="e6e1a-132">默认值：01</span><span class="sxs-lookup"><span data-stu-id="e6e1a-132">Default: 01</span></span> <br> <span data-ttu-id="e6e1a-133">选项：01，00</span><span class="sxs-lookup"><span data-stu-id="e6e1a-133">Options: 01, 00</span></span> <br> <span data-ttu-id="e6e1a-134">类型： REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="e6e1a-134">Type: REG_BINARY</span></span> | <span data-ttu-id="e6e1a-135">此设置允许你在设备直接连接到电源时关闭 Surface 亮度控制。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-135">This setting allows you to turn off Surface Brightness Control when the device is directly connected to power.</span></span> <span data-ttu-id="e6e1a-136">若要在接通电源时禁用 Surface 亮度控件，请将值设置为00。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-136">To disable Surface Brightness Control when power is plugged in, set the value to 00.</span></span> <span data-ttu-id="e6e1a-137">如果未配置此设置，则 "表面亮度" 控件打开。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-137">If you do not configure this setting, Surface Brightness Control is on.</span></span> |
| <span data-ttu-id="e6e1a-138">亮度变暗</span><span class="sxs-lookup"><span data-stu-id="e6e1a-138">Dimmed Brightness</span></span>   | <span data-ttu-id="e6e1a-139">默认值：20</span><span class="sxs-lookup"><span data-stu-id="e6e1a-139">Default: 20</span></span>  <br><span data-ttu-id="e6e1a-140">选项：0-100% 的屏幕亮度范围</span><span class="sxs-lookup"><span data-stu-id="e6e1a-140">Option: Range of 0-100 percent of screen brightness</span></span> <br> <span data-ttu-id="e6e1a-141">数据类型：正整数</span><span class="sxs-lookup"><span data-stu-id="e6e1a-141">Data Type: Positive integer</span></span> <br> <span data-ttu-id="e6e1a-142">类型： REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e6e1a-142">Type: REG_DWORD</span></span> | <span data-ttu-id="e6e1a-143">此设置允许你在不活动期间管理亮度范围。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-143">This setting allows you to manage brightness range during periods of inactivity.</span></span> <span data-ttu-id="e6e1a-144">如果未配置此设置，则亮度级别将下降到30秒的非活动状态后的全部亮度的20%。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-144">If you do not configure this setting, the brightness level will drop to 20 percent of full brightness after 30 seconds of inactivity.</span></span> |
<span data-ttu-id="e6e1a-145">完全亮度</span><span class="sxs-lookup"><span data-stu-id="e6e1a-145">Full Brightness</span></span>   | <span data-ttu-id="e6e1a-146">默认：100</span><span class="sxs-lookup"><span data-stu-id="e6e1a-146">Default: 100</span></span>  <br><span data-ttu-id="e6e1a-147">选项：0-100% 的屏幕亮度范围</span><span class="sxs-lookup"><span data-stu-id="e6e1a-147">Option: Range of 0-100 percent of screen brightness</span></span> <br> <span data-ttu-id="e6e1a-148">数据类型：正整数</span><span class="sxs-lookup"><span data-stu-id="e6e1a-148">Data Type: Positive integer</span></span> <br> <span data-ttu-id="e6e1a-149">类型： REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e6e1a-149">Type: REG_DWORD</span></span>  | <span data-ttu-id="e6e1a-150">此设置允许你管理设备的最大亮度范围。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-150">This setting allows you to manage the maximum brightness range for the device.</span></span> <span data-ttu-id="e6e1a-151">如果未配置此设置，则最大亮度范围为100%。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-151">If you do not configure this setting, the maximum brightness range is 100 percent.</span></span>|  
| <span data-ttu-id="e6e1a-152">不活动超时</span><span class="sxs-lookup"><span data-stu-id="e6e1a-152">Inactivity Timeout</span></span>| <span data-ttu-id="e6e1a-153">默认：30秒</span><span class="sxs-lookup"><span data-stu-id="e6e1a-153">Default: 30 seconds</span></span> <br><span data-ttu-id="e6e1a-154">选项：任何数字值</span><span class="sxs-lookup"><span data-stu-id="e6e1a-154">Option: Any numeric value</span></span>  <br><span data-ttu-id="e6e1a-155">数据类型：整型</span><span class="sxs-lookup"><span data-stu-id="e6e1a-155">Data Type: Integer</span></span>  <br> <span data-ttu-id="e6e1a-156">类型： REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e6e1a-156">Type: REG_DWORD</span></span> | <span data-ttu-id="e6e1a-157">此设置允许你在变暗设备之前管理处于非活动状态的时间段。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-157">This setting allows you to manage the period of inactivity before dimming the device.</span></span> <span data-ttu-id="e6e1a-158">如果未配置此设置，则不活动超时为30秒。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-158">If you do not configure this setting, the inactivity timeout is 30 seconds.</span></span>|
| <span data-ttu-id="e6e1a-159">已启用遥测</span><span class="sxs-lookup"><span data-stu-id="e6e1a-159">Telemetry  Enabled</span></span> | <span data-ttu-id="e6e1a-160">默认值：01</span><span class="sxs-lookup"><span data-stu-id="e6e1a-160">Default: 01</span></span> <br><span data-ttu-id="e6e1a-161">选项：01，00</span><span class="sxs-lookup"><span data-stu-id="e6e1a-161">Option: 01, 00</span></span> <br> <span data-ttu-id="e6e1a-162">类型： REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="e6e1a-162">Type: REG_BINARY</span></span>  | <span data-ttu-id="e6e1a-163">此设置允许你管理应用使用情况信息的共享以改进软件，并提供更好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-163">This setting allows you to manage the sharing of app usage information to improve software and provide better user experience.</span></span> <span data-ttu-id="e6e1a-164">若要禁用遥测，请将值设置为00。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-164">To disable telemetry, set the value to 00.</span></span> <span data-ttu-id="e6e1a-165">如果未配置此设置，则会根据[Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)与 microsoft 共享遥测信息。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-165">If you do not configure this setting, telemetry information is shared with Microsoft in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> |

## <span data-ttu-id="e6e1a-166">更改和更新</span><span class="sxs-lookup"><span data-stu-id="e6e1a-166">Changes and updates</span></span>

### <span data-ttu-id="e6e1a-167">版本1.16.137</span><span class="sxs-lookup"><span data-stu-id="e6e1a-167">Version 1.16.137</span></span><br>
*<span data-ttu-id="e6e1a-168">发布日期：2019年10月22日</span><span class="sxs-lookup"><span data-stu-id="e6e1a-168">Release Date: 22 October 2019</span></span>*<br>
<span data-ttu-id="e6e1a-169">此版本的 Surface 亮度控件增加了对以下各项的支持：-为 x86 重新编译，添加了对 Surface Pro 7、Surface Pro X 和 Surface 笔记本3的支持。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-169">This version of Surface Brightness Control adds support for the following: -Recompiled for x86, adding support for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

### <span data-ttu-id="e6e1a-170">版本1.12.239。0</span><span class="sxs-lookup"><span data-stu-id="e6e1a-170">Version 1.12.239.0</span></span>
*<span data-ttu-id="e6e1a-171">发布日期：2019年4月26日</span><span class="sxs-lookup"><span data-stu-id="e6e1a-171">Release Date: 26 April 2019</span></span>*<br>
<span data-ttu-id="e6e1a-172">此版本的 Surface 亮度控件增加了对以下各项的支持：</span><span class="sxs-lookup"><span data-stu-id="e6e1a-172">This version of Surface Brightness Control adds support for the following:</span></span>
- <span data-ttu-id="e6e1a-173">触摸延迟修复。</span><span class="sxs-lookup"><span data-stu-id="e6e1a-173">Touch delay fixes.</span></span>


## <span data-ttu-id="e6e1a-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="e6e1a-174">Related topics</span></span>

- [<span data-ttu-id="e6e1a-175">电池限制设置</span><span class="sxs-lookup"><span data-stu-id="e6e1a-175">Battery limit setting</span></span>](battery-limit.md)

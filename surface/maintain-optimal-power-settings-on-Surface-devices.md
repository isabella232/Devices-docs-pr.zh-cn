---
title: Surface 设备电源设置的最佳实践
description: 本主题提供了维护最佳电源设置的最佳方案建议，并介绍了 Surface 如何简化电源管理体验。 本文适用于当前支持的所有 Surface 设备，包括 Surface Pro 7+、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 54aff228e8a72d413fc53bd14fe15d8ad7b15ab0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271396"
---
# <span data-ttu-id="1a253-104">Surface 设备电源设置的最佳实践</span><span class="sxs-lookup"><span data-stu-id="1a253-104">Best practice power settings for Surface devices</span></span>

<span data-ttu-id="1a253-105">Surface 设备旨在利用移动设备能耗的最新进展，实现跨工作负载优化的简化体验。</span><span class="sxs-lookup"><span data-stu-id="1a253-105">Surface devices are designed to take advantage of the latest advances in mobile device energy consumption to deliver a streamlined experience optimized across workloads.</span></span> <span data-ttu-id="1a253-106">Surface 会根据你正在执行的任务动态微调电源流向各个硬件组件的方式，在返回到低功率空闲状态 (S0ix) 之前，暂时唤醒系统组件以处理后台任务（如传入电子邮件或网络流量）。</span><span class="sxs-lookup"><span data-stu-id="1a253-106">Depending on what you’re doing, Surface dynamically fine tunes how power flows to individual hardware components, momentarily waking up system components to handle background tasks -- such as an incoming email or network traffic -- before returning to a low power idle state (S0ix).</span></span>

## <a name="summary-of-recommendations-for-it-administrators"></a><span data-ttu-id="1a253-107">针对 IT 管理员的建议摘要</span><span class="sxs-lookup"><span data-stu-id="1a253-107">Summary of recommendations for IT administrators</span></span>

<span data-ttu-id="1a253-108">若要确保整个组织的 Surface 设备完全受益于 Surface 电源优化功能：</span><span class="sxs-lookup"><span data-stu-id="1a253-108">To ensure Surface devices across your organization fully benefit from Surface power optimization features:</span></span>

-  <span data-ttu-id="1a253-109">从 Windows 更新或 Surface 驱动程序和固件 MSI 安装最新的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="1a253-109">Install the latest  drivers and firmware from Windows Update or the Surface Driver and Firmware MSI.</span></span> <span data-ttu-id="1a253-110">这将在默认情况下创建平衡电源 (配置文件) 配置最佳电源设置。</span><span class="sxs-lookup"><span data-stu-id="1a253-110">This creates the balanced power plan (aka power profile) by default and configures optimal power settings.</span></span>  <span data-ttu-id="1a253-111">有关详细信息，请参阅管理和部署 [Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="1a253-111">For more information, refer to [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span>
- <span data-ttu-id="1a253-112">避免创建自定义电源配置文件或调整默认 UI 中不可见的高级电源设置 (**系统**电源&  >  **睡眠) 。**</span><span class="sxs-lookup"><span data-stu-id="1a253-112">Avoid creating custom power profiles or adjusting advanced power settings not visible in the default UI  (**System** > **Power & sleep**).</span></span>
- <span data-ttu-id="1a253-113">如果必须管理整个网络 (（如高度托管的组织) ）中的设备的电源配置文件，请使用 powercfg 命令工具从 Surface 设备的出厂映像导出电源计划，然后将它导入 Surface 设备的预配包中。</span><span class="sxs-lookup"><span data-stu-id="1a253-113">If you must manage the power profile of devices across your network (such as in highly managed organizations), use the powercfg command tool to export the power plan from the factory image of the Surface device and then import it into the provisioning package for your Surface devices.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="1a253-114">你只能在相同类型的 Surface 设备中导出电源计划。</span><span class="sxs-lookup"><span data-stu-id="1a253-114">You can only export a power plan across the same type of Surface device.</span></span>  <span data-ttu-id="1a253-115">例如，你无法从 Surface Laptop 导出电源计划，也无法将其导入 Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="1a253-115">For example, you cannot export a power plan from Surface Laptop and import it on Surface Pro.</span></span>  <span data-ttu-id="1a253-116">有关详细信息，请参阅"[配置电源设置"。](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)</span><span class="sxs-lookup"><span data-stu-id="1a253-116">For more information, refer to [Configure power settings](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings).</span></span>

- <span data-ttu-id="1a253-117">从任何现有的电源管理策略设置中排除 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="1a253-117">Exclude Surface devices from any existing power management policy settings.</span></span> 

## <a name="background"></a><span data-ttu-id="1a253-118">Background</span><span class="sxs-lookup"><span data-stu-id="1a253-118">Background</span></span>

<span data-ttu-id="1a253-119">Surface 实现电源管理的方式与早期操作系统标准（通过一系列睡眠状态逐渐减少和关闭电源）明显不同;例如，循环访问 S1、S2、S3 等。</span><span class="sxs-lookup"><span data-stu-id="1a253-119">The way Surface implements power management differs significantly from the earlier OS standard that gradually reduces and turns off power via a series of sleep states; for example, cycling through S1, S2, S3, and so on.</span></span>

<span data-ttu-id="1a253-120">相反，Surface 使用自定义电源配置文件进行映像，该配置文件将旧睡眠和能耗功能替换为现代待机功能和动态微调。</span><span class="sxs-lookup"><span data-stu-id="1a253-120">Instead, Surface is imaged with a custom power profile that replaces legacy sleep and energy consumption functionality with modern standby features and dynamic fine tuning.</span></span> <span data-ttu-id="1a253-121">此自定义电源配置文件通过 Surface Serial Hub 驱动程序和系统聚合器模块 (SAM) 。</span><span class="sxs-lookup"><span data-stu-id="1a253-121">This custom power profile is implemented via the Surface Serial Hub Driver and the system aggregator module (SAM).</span></span> <span data-ttu-id="1a253-122">SAM 芯片用作 Surface 设备电源策略所有者，使用算法计算最佳电源要求。</span><span class="sxs-lookup"><span data-stu-id="1a253-122">The SAM chip functions as the Surface device power-policy owner, using algorithms to calculate optimal power requirements.</span></span> <span data-ttu-id="1a253-123">它可与 Windows 电源管理器结合使用，以仅分配或限制硬件组件正常运行所需的确切电量。</span><span class="sxs-lookup"><span data-stu-id="1a253-123">It works in conjunction with Windows power manager to allocate or throttle only the exact amount of power required for hardware components to function.</span></span> <span data-ttu-id="1a253-124">本文适用于所有当前受支持的 Surface 设备，包括 Surface Pro 7+、Surface Laptop Go、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。</span><span class="sxs-lookup"><span data-stu-id="1a253-124">This article applies to all currently supported Surface devices including Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>

## <a name="utilizing-the-custom-power-profile-in-surface"></a><span data-ttu-id="1a253-125">利用 Surface 中的自定义电源配置文件</span><span class="sxs-lookup"><span data-stu-id="1a253-125">Utilizing the custom power profile in Surface</span></span>

<span data-ttu-id="1a253-126">如果你转到 Surface 设备的电源选项，你将看到有一个电源计划可用。</span><span class="sxs-lookup"><span data-stu-id="1a253-126">If you go into the power options on a surface device, you'll see that there's a single power plan available.</span></span> <span data-ttu-id="1a253-127">这是自定义电源配置文件。</span><span class="sxs-lookup"><span data-stu-id="1a253-127">This is the custom power profile.</span></span> <span data-ttu-id="1a253-128">如果你转到高级电源设置，你将看到比运行 Windows 10 的通用电脑小得多的电源选项子集。</span><span class="sxs-lookup"><span data-stu-id="1a253-128">And if you go to the advanced power settings, you’ll see a much smaller subset of power options compared to a generic PC running Windows 10.</span></span> <span data-ttu-id="1a253-129">与常规设备不同，Surface 具有固件和自定义组件来管理这些电源选项。</span><span class="sxs-lookup"><span data-stu-id="1a253-129">Unlike generic devices, Surface has firmware and custom components to manage these power options.</span></span>


## <a name="modern-standby"></a><span data-ttu-id="1a253-130">新式待机</span><span class="sxs-lookup"><span data-stu-id="1a253-130">Modern Standby</span></span>

<span data-ttu-id="1a253-131">算法嵌入的自定义电源配置文件通过为智能手机的典型即时开/即时关闭功能保持低功耗状态，为 Surface 实现新式待机连接。</span><span class="sxs-lookup"><span data-stu-id="1a253-131">The algorithmically embedded custom power profile enables modern standby connectivity for Surface by maintaining a low power state for instant on/instant off functionality typical of smartphones.</span></span> <span data-ttu-id="1a253-132">S0ix 也称为"最深运行时空闲平台状态 (或) ，是 Surface 设备的默认电源模式。</span><span class="sxs-lookup"><span data-stu-id="1a253-132">S0ix, also known as Deepest Runtime Idle Platform State (DRIPS), is the default power mode for Surface devices.</span></span> <span data-ttu-id="1a253-133">新式待机有两种模式：</span><span class="sxs-lookup"><span data-stu-id="1a253-133">Modern standby has two modes:</span></span>

- **<span data-ttu-id="1a253-134">连接待机。</span><span class="sxs-lookup"><span data-stu-id="1a253-134">Connected standby.</span></span>** <span data-ttu-id="1a253-135">电子邮件、消息传递和云同步数据即时传递的默认模式，连接待机Wi-Fi保持网络连接。</span><span class="sxs-lookup"><span data-stu-id="1a253-135">The default mode for up-to-the minute delivery of emails, messaging, and cloud-synced data, connected standby keeps Wi-Fi on and maintains network connectivity.</span></span>

- **<span data-ttu-id="1a253-136">断开连接的待机状态。</span><span class="sxs-lookup"><span data-stu-id="1a253-136">Disconnected standby.</span></span>** <span data-ttu-id="1a253-137">对于延长电池使用时间可选模式，断开连接的待机模式提供相同的即时打开体验，并关闭 WLAN、Bluetooth和相关网络连接来节省电源。</span><span class="sxs-lookup"><span data-stu-id="1a253-137">An optional mode for extended battery life, disconnected standby delivers the same instant-on experience and saves power by turning off Wi-Fi, Bluetooth, and related network connectivity.</span></span>

<span data-ttu-id="1a253-138">若要详细了解新式待机，请参阅 [Microsoft 硬件开发人员中心](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)。</span><span class="sxs-lookup"><span data-stu-id="1a253-138">To learn more about modern standby, refer to the [Microsoft Hardware Dev Center](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources).</span></span>

## <a name="how-surface-streamlines-the-power-management-experience"></a><span data-ttu-id="1a253-139">Surface 如何简化电源管理体验</span><span class="sxs-lookup"><span data-stu-id="1a253-139">How Surface streamlines the power management experience</span></span> 

<span data-ttu-id="1a253-140">Surface 集成了以下旨在帮助用户优化电源管理体验的功能：</span><span class="sxs-lookup"><span data-stu-id="1a253-140">Surface integrates the following features designed to help users optimize the power management experience:</span></span>

- [<span data-ttu-id="1a253-141">单数电源计划</span><span class="sxs-lookup"><span data-stu-id="1a253-141">Singular power plan</span></span>](#singular-power-plan)

- [<span data-ttu-id="1a253-142">简化的电源设置用户界面</span><span class="sxs-lookup"><span data-stu-id="1a253-142">Simplified power settings user interface</span></span>](#simplified-power-settings-user-interface)

- [<span data-ttu-id="1a253-143">Windows 性能电源滑块</span><span class="sxs-lookup"><span data-stu-id="1a253-143">Windows performance power slider</span></span>](#windows-performance-power-slider)

### <a name="singular-power-plan"></a><span data-ttu-id="1a253-144">单数电源计划</span><span class="sxs-lookup"><span data-stu-id="1a253-144">Singular power plan</span></span>

<span data-ttu-id="1a253-145">Surface 专为简化的电源管理体验设计，无需创建自定义电源计划或手动配置电源设置。</span><span class="sxs-lookup"><span data-stu-id="1a253-145">Surface is designed for a streamlined power management experience that eliminates the need to create custom power plans or manually configure power settings.</span></span> <span data-ttu-id="1a253-146">Microsoft 通过提供单个电源计划来简化用户体验， (平衡) 替换标准 Windows 版本中的多个电源计划。</span><span class="sxs-lookup"><span data-stu-id="1a253-146">Microsoft streamlines the user experience by delivering a single power plan (balanced) that replaces the multiple power plans from standard Windows builds.</span></span>

### <a name="simplified-power-settings-user-interface"></a><span data-ttu-id="1a253-147">简化的电源设置用户界面</span><span class="sxs-lookup"><span data-stu-id="1a253-147">Simplified power settings user interface</span></span>

<span data-ttu-id="1a253-148">Surface 提供与最佳做法电源设置建议相一致且简化的 UI。</span><span class="sxs-lookup"><span data-stu-id="1a253-148">Surface provides a simplified UI in accord with best practice power setting recommendations.</span></span> <span data-ttu-id="1a253-149">通常，建议仅调整默认用户界面中可见的设置，并避免配置高级电源设置或组策略设置。</span><span class="sxs-lookup"><span data-stu-id="1a253-149">In general, it's recommended to only adjust settings visible in the default user interface and avoid configuring advanced power settings or Group Policy settings.</span></span> <span data-ttu-id="1a253-150">使用默认屏幕和睡眠超时，同时避免最大亮度级别是用户保持延长电池使用时间的最有效方法。</span><span class="sxs-lookup"><span data-stu-id="1a253-150">Using the default screen and sleep timeouts while avoiding maximum brightness levels are the most effective ways for users to maintain extended battery life.</span></span>

![图 1.](images/powerintrofig1.png)

<span data-ttu-id="1a253-153">图 1.</span><span class="sxs-lookup"><span data-stu-id="1a253-153">Figure 1.</span></span> <span data-ttu-id="1a253-154">简化电源和睡眠设置</span><span class="sxs-lookup"><span data-stu-id="1a253-154">Simplified power and sleep settings</span></span>

### <a name="windows-performance-power-slider"></a><span data-ttu-id="1a253-155">Windows 性能电源滑块</span><span class="sxs-lookup"><span data-stu-id="1a253-155">Windows performance power slider</span></span>

<span data-ttu-id="1a253-156">运行 Windows 10 版本 1709 及更高版本的 Surface 设备包括一个电源滑块，可让你根据需要确定电池使用时间优先级或支持性能（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="1a253-156">Surface devices running Windows 10 build 1709 and later include a power slider allowing you to prioritize battery life when needed or favor performance if desired.</span></span> <span data-ttu-id="1a253-157">可以通过单击电池图标从任务栏访问电源滑块。</span><span class="sxs-lookup"><span data-stu-id="1a253-157">You can access the power slider from the taskbar by clicking on the battery icon.</span></span> <span data-ttu-id="1a253-158">使用节电模式向左滑动 (电池使用时间更长，) 向右滑动，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="1a253-158">Slide left for longer battery life (battery saver mode) or slide right for faster performance.</span></span>

![图 2.](images/powerintrofig2a.png)

<span data-ttu-id="1a253-161">图 2.</span><span class="sxs-lookup"><span data-stu-id="1a253-161">Figure 2.</span></span> <span data-ttu-id="1a253-162">电源滑块</span><span class="sxs-lookup"><span data-stu-id="1a253-162">Power slider</span></span>

<span data-ttu-id="1a253-163">电源滑块启用四种状态，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="1a253-163">Power slider enables four states as described in the following table:</span></span>

| <span data-ttu-id="1a253-164">滑块模式</span><span class="sxs-lookup"><span data-stu-id="1a253-164">Slider mode</span></span>| <span data-ttu-id="1a253-165">描述</span><span class="sxs-lookup"><span data-stu-id="1a253-165">Description</span></span> |
|---|---|
| <span data-ttu-id="1a253-166">节电模式</span><span class="sxs-lookup"><span data-stu-id="1a253-166">Battery saver</span></span>| <span data-ttu-id="1a253-167">当系统与电源断开连接时，有助于节省电源并延长电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="1a253-167">Helps conserve power and prolong battery life when the system is disconnected from a power source.</span></span> <span data-ttu-id="1a253-168">节电模式处于打开状态时，某些 Windows 功能将被禁用、限制或行为不同。</span><span class="sxs-lookup"><span data-stu-id="1a253-168">When battery saver is on, some Windows features are disabled, throttled, or behave differently.</span></span> <span data-ttu-id="1a253-169">屏幕亮度也会降低。</span><span class="sxs-lookup"><span data-stu-id="1a253-169">Screen brightness is also reduced.</span></span> <span data-ttu-id="1a253-170">节电模式仅在使用电池电源 (DC) 。</span><span class="sxs-lookup"><span data-stu-id="1a253-170">Battery saver is only available when using battery power (DC).</span></span> <span data-ttu-id="1a253-171">若要了解更多信息，请参阅 [节电模式](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)。</span><span class="sxs-lookup"><span data-stu-id="1a253-171">To learn more, see [Battery Saver](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver).</span></span>|
| <span data-ttu-id="1a253-172">推荐</span><span class="sxs-lookup"><span data-stu-id="1a253-172">Recommended</span></span> | <span data-ttu-id="1a253-173">提供比早期版本的 Windows 中的默认设置更长的电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="1a253-173">Delivers longer battery life than the default settings in earlier versions of Windows.</span></span> |
| <span data-ttu-id="1a253-174">性能更佳</span><span class="sxs-lookup"><span data-stu-id="1a253-174">Better Performance</span></span> | <span data-ttu-id="1a253-175">在电池使用时间上稍微提升性能，用作默认滑块模式。</span><span class="sxs-lookup"><span data-stu-id="1a253-175">Slightly favors performance over battery life, functioning as the default slider mode.</span></span> |
| <span data-ttu-id="1a253-176">最佳性能</span><span class="sxs-lookup"><span data-stu-id="1a253-176">Best Performance</span></span> | <span data-ttu-id="1a253-177">对于需要最大性能和响应速度的工作负荷，无论电池电源消耗如何，都支持性能超过电源。</span><span class="sxs-lookup"><span data-stu-id="1a253-177">Favors performance over power for workloads requiring maximum performance and responsiveness, regardless of battery power consumption.</span></span>|

<span data-ttu-id="1a253-178">电源滑块模式直接控制下表中所示的特定硬件组件。</span><span class="sxs-lookup"><span data-stu-id="1a253-178">Power slider modes directly control specific hardware components shown in the following table.</span></span>

| <span data-ttu-id="1a253-179">组件</span><span class="sxs-lookup"><span data-stu-id="1a253-179">Component</span></span> | <span data-ttu-id="1a253-180">滑块功能</span><span class="sxs-lookup"><span data-stu-id="1a253-180">Slider functionality</span></span> |
|---|---|
| <span data-ttu-id="1a253-181">Intel Speed Shift (CPU 能耗注册) 能耗性能首选项提示。</span><span class="sxs-lookup"><span data-stu-id="1a253-181">Intel Speed Shift (CPU energy registers) and Energy Performance Preference hint.</span></span> | <span data-ttu-id="1a253-182">选择最佳操作频率和频率以获得最佳性能和电源。</span><span class="sxs-lookup"><span data-stu-id="1a253-182">Selects the best operating frequency and voltage for optimal performance and power.</span></span> <span data-ttu-id="1a253-183">PERFEPP (电源) 是 CPU 的全局电源效率提示。</span><span class="sxs-lookup"><span data-stu-id="1a253-183">The Energy Performance Preference (PERFEPP) is a global power efficiency hint to the CPU.</span></span> |
| <span data-ttu-id="1a253-184">扇出 (RPM) </span><span class="sxs-lookup"><span data-stu-id="1a253-184">Fan speed (RPM)</span></span>| <span data-ttu-id="1a253-185">如果适用，可针对更改条件（例如，在节电模式滑块模式下使扇形保持静默）进行调整。</span><span class="sxs-lookup"><span data-stu-id="1a253-185">Where applicable, adjusts for changing conditions such as keeping fan silent in battery saver slider mode.</span></span>|
| <span data-ttu-id="1a253-186">PL1/PL2 (处理器包电源) 。</span><span class="sxs-lookup"><span data-stu-id="1a253-186">Processor package power limits (PL1/PL2).</span></span>| <span data-ttu-id="1a253-187">要求 CPU 管理其频率选择，以适应稳定状态 (PL1) 和 (PL2 负载的运行) 限制。</span><span class="sxs-lookup"><span data-stu-id="1a253-187">Requires the CPU to manage its frequency choices to accommodate a running average power limit for both steady state (PL1) and turbo (PL2) workloads.</span></span>|
| <span data-ttu-id="1a253-188">处理器加速频率限制 (IA 的) 。</span><span class="sxs-lookup"><span data-stu-id="1a253-188">Processor turbo frequency limits (IA turbo limitations).</span></span> | <span data-ttu-id="1a253-189">调整处理器和图形性能，使处理器核心的运行速度快于或慢于已评分的操作系统频率。</span><span class="sxs-lookup"><span data-stu-id="1a253-189">Adjusts processor and graphics performance allowing processor cores to run faster or slower than the rated operating frequency.</span></span>                                                |

>[!NOTE]
><span data-ttu-id="1a253-190">电源滑块完全独立于操作系统电源设置，无论是从控制面板/电源选项、组策略还是相关方法配置。</span><span class="sxs-lookup"><span data-stu-id="1a253-190">The power slider is entirely independent of operating system power settings whether configured from Control Panel/ Power Options, Group Policy, or related methods.</span></span>

<span data-ttu-id="1a253-191">若要了解更多，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1a253-191">To learn more, see:</span></span>

-   [<span data-ttu-id="1a253-192">自定义 Windows 性能电源滑块</span><span class="sxs-lookup"><span data-stu-id="1a253-192">Customize the Windows performance power slider</span></span>](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [<span data-ttu-id="1a253-193">节电模式。</span><span class="sxs-lookup"><span data-stu-id="1a253-193">Battery saver.</span></span>](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## <a name="best-practices-for-extended-battery-life"></a><span data-ttu-id="1a253-194">延长电池使用时间的最佳方案</span><span class="sxs-lookup"><span data-stu-id="1a253-194">Best practices for extended battery life</span></span>


| <span data-ttu-id="1a253-195">最佳做法</span><span class="sxs-lookup"><span data-stu-id="1a253-195">Best practice</span></span> | <span data-ttu-id="1a253-196">转到</span><span class="sxs-lookup"><span data-stu-id="1a253-196">Go to</span></span> | <span data-ttu-id="1a253-197">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1a253-197">Next steps</span></span> |
|---|---|---|                                                                                                                                    
| <span data-ttu-id="1a253-198">确保 Surface 设备是最新的</span><span class="sxs-lookup"><span data-stu-id="1a253-198">Ensure your Surface device is up to date</span></span>| <span data-ttu-id="1a253-199">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="1a253-199">Windows Update</span></span> | <span data-ttu-id="1a253-200">在任务栏搜索框中，键入**Windows 更新**并选择 **"检查更新"。**</span><span class="sxs-lookup"><span data-stu-id="1a253-200">In the taskbar search box, type **Windows Update** and select **Check for updates**.</span></span> |
| <span data-ttu-id="1a253-201">为正在执行的工作选择最佳电源设置</span><span class="sxs-lookup"><span data-stu-id="1a253-201">Choose the best power setting for what you’re doing</span></span> | <span data-ttu-id="1a253-202">电源滑块</span><span class="sxs-lookup"><span data-stu-id="1a253-202">Power slider</span></span> | <span data-ttu-id="1a253-203">在任务栏中，选择电池图标，然后选择 **"最佳性能\*\*\*\*"、"最佳**电池使用时间"或介于两者之间的某个位置。</span><span class="sxs-lookup"><span data-stu-id="1a253-203">In the taskbar, select the battery icon, then choose **Best performance**, **Best battery life**, or somewhere in between.</span></span>|
| <span data-ttu-id="1a253-204">在电量不足时节省电池</span><span class="sxs-lookup"><span data-stu-id="1a253-204">Conserve battery when it’s low</span></span> | <span data-ttu-id="1a253-205">节电模式</span><span class="sxs-lookup"><span data-stu-id="1a253-205">Battery saver</span></span> | <span data-ttu-id="1a253-206">在任务栏中，选择电池图标，然后单击 **"电池设置"。**</span><span class="sxs-lookup"><span data-stu-id="1a253-206">In the taskbar, select the battery icon and click **Battery settings**.</span></span> <span data-ttu-id="1a253-207">如果 **电池电量低于，** 请选择"自动打开节电模式"，然后将滑块进一步向右移动，延长电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="1a253-207">Select **Turn battery saver on automatically if my battery falls below** and then move the slider further to the right for longer battery life.</span></span> |
| <span data-ttu-id="1a253-208">配置最佳屏幕亮度</span><span class="sxs-lookup"><span data-stu-id="1a253-208">Configure optimal screen brightness</span></span> | <span data-ttu-id="1a253-209">节电模式</span><span class="sxs-lookup"><span data-stu-id="1a253-209">Battery saver</span></span> | <span data-ttu-id="1a253-210">在任务栏中，选择电池图标**并单击"** 电池设置"，选择"节电模式时降低**屏幕亮度"。**</span><span class="sxs-lookup"><span data-stu-id="1a253-210">In the taskbar, select the battery icon and click **Battery settings**, select **Lower screen brightness while in battery saver**.</span></span> |
| <span data-ttu-id="1a253-211">在未接通电源时节省电源</span><span class="sxs-lookup"><span data-stu-id="1a253-211">Conserve power whenever you’re not plugged in</span></span> | <span data-ttu-id="1a253-212">节电模式</span><span class="sxs-lookup"><span data-stu-id="1a253-212">Battery saver</span></span>| <span data-ttu-id="1a253-213">选择 **"打开节电模式"状态，直到下一次充电**。</span><span class="sxs-lookup"><span data-stu-id="1a253-213">Select **Turn on battery saver status until next charge**.</span></span>|
| <span data-ttu-id="1a253-214">调查电源设置的问题。</span><span class="sxs-lookup"><span data-stu-id="1a253-214">Investigate problems with your power settings.</span></span> | <span data-ttu-id="1a253-215">电源疑难解答程序</span><span class="sxs-lookup"><span data-stu-id="1a253-215">Power troubleshooter</span></span> | <span data-ttu-id="1a253-216">在任务栏搜索中，选择"疑难\*\*\*\* 解答"，然后选择 **"电源**"并按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="1a253-216">In the Taskbar search for troubleshoot, select **Troubleshoot**, and then select **Power** and follow the instructions.</span></span>|
| <span data-ttu-id="1a253-217">检查应用使用情况</span><span class="sxs-lookup"><span data-stu-id="1a253-217">Check app usage</span></span> | <span data-ttu-id="1a253-218">应用</span><span class="sxs-lookup"><span data-stu-id="1a253-218">Your apps</span></span> | <span data-ttu-id="1a253-219">关闭应用。</span><span class="sxs-lookup"><span data-stu-id="1a253-219">Close apps.</span></span>|
| <span data-ttu-id="1a253-220">检查您的电缆是否损坏。</span><span class="sxs-lookup"><span data-stu-id="1a253-220">Check your power cord for any damage.</span></span>| <span data-ttu-id="1a253-221">您的电缆</span><span class="sxs-lookup"><span data-stu-id="1a253-221">Your power cord</span></span> | <span data-ttu-id="1a253-222">如果断电或损坏，请更换电缆。</span><span class="sxs-lookup"><span data-stu-id="1a253-222">Replace power cord if worn or damaged.</span></span>|

## <a name="learn-more"></a><span data-ttu-id="1a253-223">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="1a253-223">Learn more</span></span> 

- [<span data-ttu-id="1a253-224">新式待机</span><span class="sxs-lookup"><span data-stu-id="1a253-224">Modern   standby</span></span>](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [<span data-ttu-id="1a253-225">自定义 Windows 性能电源滑块</span><span class="sxs-lookup"><span data-stu-id="1a253-225">Customize the Windows performance power   slider</span></span>](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [<span data-ttu-id="1a253-226">节电模式</span><span class="sxs-lookup"><span data-stu-id="1a253-226">Battery   saver</span></span>](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [<span data-ttu-id="1a253-227">管理和部署 Surface 驱动程序和固件更新</span><span class="sxs-lookup"><span data-stu-id="1a253-227">Manage and deploy Surface driver and firmware updates</span></span>](manage-surface-driver-and-firmware-updates.md)

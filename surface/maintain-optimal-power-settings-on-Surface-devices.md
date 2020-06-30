---
title: Surface 设备电源设置的最佳实践
description: 本主题提供了有关维护最佳电源设置的最佳做法建议，并介绍了 Surface 如何简化电源管理体验。 本文适用于所有当前支持的 Surface 设备，包括 Surface Pro 7、Surface Pro X 和 Surface 笔记本3。
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
ms.date: 10/28/2019
ms.openlocfilehash: 73a74dc05a5a6929fa6360e04aac5d342b9c06a8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830777"
---
# <span data-ttu-id="6c6c6-104">Surface 设备电源设置的最佳实践</span><span class="sxs-lookup"><span data-stu-id="6c6c6-104">Best practice power settings for Surface devices</span></span>

<span data-ttu-id="6c6c6-105">Surface 设备旨在充分利用移动设备能源消耗中的最新进展，以提供跨工作负载优化的简化体验。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-105">Surface devices are designed to take advantage of the latest advances in mobile device energy consumption to deliver a streamlined experience optimized across workloads.</span></span> <span data-ttu-id="6c6c6-106">根据你正在执行的操作，Surface 会动态地调整如何处理单个硬件组件的电源，并在返回到低电量空闲状态（S0ix）之前，立即唤醒系统组件以处理后台任务，例如传入的电子邮件或网络流量。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-106">Depending on what you’re doing, Surface dynamically fine tunes how power flows to individual hardware components, momentarily waking up system components to handle background tasks -- such as an incoming email or network traffic -- before returning to a low power idle state (S0ix).</span></span>

## <span data-ttu-id="6c6c6-107">IT 管理员建议摘要</span><span class="sxs-lookup"><span data-stu-id="6c6c6-107">Summary of recommendations for IT administrators</span></span>

<span data-ttu-id="6c6c6-108">若要确保整个组织中的 Surface 设备完全受益于 Surface power 优化功能，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-108">To ensure Surface devices across your organization fully benefit from Surface power optimization features:</span></span>

-  <span data-ttu-id="6c6c6-109">从 Windows 更新或 Surface Driver 和固件 MSI 安装最新的驱动程序和固件。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-109">Install the latest  drivers and firmware from Windows Update or the Surface Driver and Firmware MSI.</span></span> <span data-ttu-id="6c6c6-110">这将默认创建平衡电源计划（亦称为电源配置文件），并配置最佳电源设置。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-110">This creates the balanced power plan (aka power profile) by default and configures optimal power settings.</span></span>  <span data-ttu-id="6c6c6-111">有关详细信息，请参阅[管理和部署 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-111">For more information, refer to [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span>
- <span data-ttu-id="6c6c6-112">避免创建自定义电源配置文件或调整默认 UI （**系统**  >  **power & 睡眠**）中不可见的高级电源设置。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-112">Avoid creating custom power profiles or adjusting advanced power settings not visible in the default UI  (**System** > **Power & sleep**).</span></span>
- <span data-ttu-id="6c6c6-113">如果必须在网络上管理设备的电源配置文件（例如，在高度托管的组织中），请使用 powercfg 命令工具从 Surface 设备的工厂映像中导出电源计划，然后将其导入到 Surface 设备的预配包中。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-113">If you must manage the power profile of devices across your network (such as in highly managed organizations), use the powercfg command tool to export the power plan from the factory image of the Surface device and then import it into the provisioning package for your Surface devices.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="6c6c6-114">您只能在同一类型的 Surface 设备上导出电源计划。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-114">You can only export a power plan across the same type of Surface device.</span></span>  <span data-ttu-id="6c6c6-115">例如，您无法从 Surface 笔记本电脑导出电源计划，并将其导入 Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-115">For example, you cannot export a power plan from Surface Laptop and import it on Surface Pro.</span></span>  <span data-ttu-id="6c6c6-116">有关详细信息，请参阅[配置电源设置](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-116">For more information, refer to [Configure power settings](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings).</span></span>

- <span data-ttu-id="6c6c6-117">从任何现有的电源管理策略设置中排除 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-117">Exclude Surface devices from any existing power management policy settings.</span></span> 

## <span data-ttu-id="6c6c6-118">Background</span><span class="sxs-lookup"><span data-stu-id="6c6c6-118">Background</span></span>

<span data-ttu-id="6c6c6-119">Surface 实现电源管理的方式与早期操作系统标准显著不同，后者通过一系列睡眠状态逐渐降低和关闭电源;例如，通过 S1、S2、S3 等进行循环。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-119">The way Surface implements power management differs significantly from the earlier OS standard that gradually reduces and turns off power via a series of sleep states; for example, cycling through S1, S2, S3, and so on.</span></span>

<span data-ttu-id="6c6c6-120">相反，Surface 是使用自定义电源配置文件的映像，它将旧的睡眠和能源消耗功能替换为新式待机功能和动态微调。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-120">Instead, Surface is imaged with a custom power profile that replaces legacy sleep and energy consumption functionality with modern standby features and dynamic fine tuning.</span></span> <span data-ttu-id="6c6c6-121">此自定义电源配置文件通过 Surface 串行集线器驱动程序和系统聚合器模块（SAM）实现。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-121">This custom power profile is implemented via the Surface Serial Hub Driver and the system aggregator module (SAM).</span></span> <span data-ttu-id="6c6c6-122">SAM 芯片充当 Surface 设备电源策略所有者，使用算法计算最佳电源需求。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-122">The SAM chip functions as the Surface device power-policy owner, using algorithms to calculate optimal power requirements.</span></span> <span data-ttu-id="6c6c6-123">它与 Windows power manager 结合使用，以仅分配或限制硬件组件正常工作所需的确切电量。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-123">It works in conjunction with Windows power manager to allocate or throttle only the exact amount of power required for hardware components to function.</span></span> <span data-ttu-id="6c6c6-124">本文适用于所有当前支持的 Surface 设备，包括 Surface Pro 7、Surface Pro X 和 Surface 笔记本3。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-124">This article applies to all currently supported Surface devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>

## <span data-ttu-id="6c6c6-125">利用图面中的自定义 power profile</span><span class="sxs-lookup"><span data-stu-id="6c6c6-125">Utilizing the custom power profile in Surface</span></span>

<span data-ttu-id="6c6c6-126">如果您进入 surface 设备上的 "电源" 选项，您将看到有一个可用的电源套餐。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-126">If you go into the power options on a  surface device, you'll see that there's a single power plan available.</span></span> <span data-ttu-id="6c6c6-127">这是自定义电源配置文件。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-127">This is the custom power profile.</span></span> <span data-ttu-id="6c6c6-128">如果你转到 "高级" 电源设置，你将看到一个与运行 Windows 10 的通用电脑相比的电源选项的更小子集。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-128">And if you go to the advanced power settings, you’ll see a much smaller subset of power options compared to a generic PC running Windows 10.</span></span> <span data-ttu-id="6c6c6-129">与通用设备不同，Surface 具有用于管理这些电源选项的固件和自定义组件。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-129">Unlike generic devices, Surface has firmware and custom components to manage these power options.</span></span>


## <span data-ttu-id="6c6c6-130">新式备用</span><span class="sxs-lookup"><span data-stu-id="6c6c6-130">Modern Standby</span></span>

<span data-ttu-id="6c6c6-131">Algorithmically 嵌入的自定义 power profile 通过为智能手机的 "即时开启" 和 "即时" 功能保持较低的电源状态，为表面启用新式待机连接。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-131">The algorithmically embedded custom power profile enables modern standby connectivity for Surface by maintaining a low power state for instant on/instant off functionality typical of smartphones.</span></span> <span data-ttu-id="6c6c6-132">S0ix （也称为 "最深的运行时空闲平台状态（DRIPS）"）是 Surface 设备的默认电源模式。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-132">S0ix, also known as Deepest Runtime Idle Platform State (DRIPS), is the default power mode for Surface devices.</span></span> <span data-ttu-id="6c6c6-133">新式备用有两种模式：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-133">Modern standby has two modes:</span></span>

- **<span data-ttu-id="6c6c6-134">已连接待机。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-134">Connected standby.</span></span>** <span data-ttu-id="6c6c6-135">通过电子邮件、消息传递和云同步数据的最新传递的默认模式，已连接的备用设备将保持 Wi-fi 打开并保持网络连接。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-135">The default mode for up-to-the minute delivery of emails, messaging, and cloud-synced data, connected standby keeps Wi-Fi on and maintains network connectivity.</span></span>

- **<span data-ttu-id="6c6c6-136">已断开连接待机。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-136">Disconnected standby.</span></span>** <span data-ttu-id="6c6c6-137">延长电池使用时间的可选模式，已断开的待机功能通过关闭 Wi-fi、蓝牙和相关网络连接来提供相同的即时体验并节省电能。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-137">An optional mode for extended battery life, disconnected standby delivers the same instant-on experience and saves power by turning off Wi-Fi, Bluetooth, and related network connectivity.</span></span>

<span data-ttu-id="6c6c6-138">若要了解有关新式待机的详细信息，请参阅[Microsoft 硬件开发人员中心](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-138">To learn more about modern standby, refer to the [Microsoft Hardware Dev Center](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources).</span></span>

## <span data-ttu-id="6c6c6-139">图面如何简化电源管理体验</span><span class="sxs-lookup"><span data-stu-id="6c6c6-139">How Surface streamlines the power management experience</span></span> 

<span data-ttu-id="6c6c6-140">Surface 集成了以下用于帮助用户优化电源管理体验的功能：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-140">Surface integrates the following features designed to help users optimize the power management experience:</span></span>

- [<span data-ttu-id="6c6c6-141">单数电源计划</span><span class="sxs-lookup"><span data-stu-id="6c6c6-141">Singular power plan</span></span>](#singular-power-plan)

- [<span data-ttu-id="6c6c6-142">简化的电源设置用户界面</span><span class="sxs-lookup"><span data-stu-id="6c6c6-142">Simplified power settings user interface</span></span>](#simplified-power-settings-user-interface)

- [<span data-ttu-id="6c6c6-143">Windows 性能高滑块</span><span class="sxs-lookup"><span data-stu-id="6c6c6-143">Windows performance power slider</span></span>](#windows-performance-power-slider)

### <span data-ttu-id="6c6c6-144">单数电源计划</span><span class="sxs-lookup"><span data-stu-id="6c6c6-144">Singular power plan</span></span>

<span data-ttu-id="6c6c6-145">图面适用于简化的电源管理体验，无需创建自定义电源计划或手动配置电源设置。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-145">Surface is designed for a streamlined power management experience that eliminates the need to create custom power plans or manually configure power settings.</span></span> <span data-ttu-id="6c6c6-146">Microsoft 通过提供单个电源计划（已平衡）来取代标准 Windows 内部版本的多个电源计划，优化了用户体验。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-146">Microsoft streamlines the user experience by delivering a single power plan (balanced) that replaces the multiple power plans from standard Windows builds.</span></span>

### <span data-ttu-id="6c6c6-147">简化的电源设置用户界面</span><span class="sxs-lookup"><span data-stu-id="6c6c6-147">Simplified power settings user interface</span></span>

<span data-ttu-id="6c6c6-148">Surface 按照最佳做法电源设置建议提供简化的 UI。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-148">Surface provides a simplified UI in accord with best practice power setting recommendations.</span></span> <span data-ttu-id="6c6c6-149">通常，建议仅在默认用户界面中调整可见设置，避免配置高级电源设置或组策略设置。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-149">In general, it's recommended to only adjust settings visible in the default user interface and avoid configuring advanced power settings or Group Policy settings.</span></span> <span data-ttu-id="6c6c6-150">使用默认屏幕和睡眠超时，同时避免最高亮度级别是用户保持延长电池寿命的最有效方式。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-150">Using the default screen and sleep timeouts while avoiding maximum brightness levels are the most effective ways for users to maintain extended battery life.</span></span>

![图 1.](images/powerintrofig1.png)

<span data-ttu-id="6c6c6-153">图 1.</span><span class="sxs-lookup"><span data-stu-id="6c6c6-153">Figure 1.</span></span> <span data-ttu-id="6c6c6-154">简化的电源和睡眠设置</span><span class="sxs-lookup"><span data-stu-id="6c6c6-154">Simplified power and sleep settings</span></span>

### <span data-ttu-id="6c6c6-155">Windows 性能高滑块</span><span class="sxs-lookup"><span data-stu-id="6c6c6-155">Windows performance power slider</span></span>

<span data-ttu-id="6c6c6-156">运行 Windows 10 内部版本1709和更高版本的 Surface 设备包括一个 power 滑块，使你能够根据需要设置电池使用时间的优先级，或优选性能（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-156">Surface devices running Windows 10 build 1709 and later include a power slider allowing you to prioritize battery life when needed or favor performance if desired.</span></span> <span data-ttu-id="6c6c6-157">通过单击电池图标，可以从任务栏访问 "电源" 滑块。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-157">You can access the power slider from the taskbar by clicking on the battery icon.</span></span> <span data-ttu-id="6c6c6-158">向左滑动以延长电池使用时间（节电模式）或向右滑动以提高性能。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-158">Slide left for longer battery life (battery saver mode) or slide right for faster performance.</span></span>

![图 2.](images/powerintrofig2a.png)

<span data-ttu-id="6c6c6-161">图 2.</span><span class="sxs-lookup"><span data-stu-id="6c6c6-161">Figure 2.</span></span> <span data-ttu-id="6c6c6-162">Power 滑块</span><span class="sxs-lookup"><span data-stu-id="6c6c6-162">Power slider</span></span>

<span data-ttu-id="6c6c6-163">Power 滑块支持四种状态，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-163">Power slider enables four states as described in the following table:</span></span>

| <span data-ttu-id="6c6c6-164">滑块模式</span><span class="sxs-lookup"><span data-stu-id="6c6c6-164">Slider mode</span></span>| <span data-ttu-id="6c6c6-165">描述</span><span class="sxs-lookup"><span data-stu-id="6c6c6-165">Description</span></span> |
|---|---|
| <span data-ttu-id="6c6c6-166">节电模式</span><span class="sxs-lookup"><span data-stu-id="6c6c6-166">Battery saver</span></span>| <span data-ttu-id="6c6c6-167">当系统断开与电源的连接时，可帮助省电并延长电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-167">Helps conserve power and prolong battery life when the system is disconnected from a power source.</span></span> <span data-ttu-id="6c6c6-168">节电模式处于打开状态时，某些 Windows 功能将被禁用、阻止或行为不同。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-168">When battery saver is on, some Windows features are disabled, throttled, or behave differently.</span></span> <span data-ttu-id="6c6c6-169">屏幕亮度也会减少。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-169">Screen brightness is also reduced.</span></span> <span data-ttu-id="6c6c6-170">只有在使用电池电源（DC）时，节电模式才可用。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-170">Battery saver is only available when using battery power (DC).</span></span> <span data-ttu-id="6c6c6-171">若要了解详细信息，请参阅[节电](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)模式。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-171">To learn more, see [Battery Saver](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver).</span></span>|
| <span data-ttu-id="6c6c6-172">推荐</span><span class="sxs-lookup"><span data-stu-id="6c6c6-172">Recommended</span></span> | <span data-ttu-id="6c6c6-173">比早期版本的 Windows 中的默认设置提供更长的电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-173">Delivers longer battery life than the default settings in earlier versions of Windows.</span></span> |
| <span data-ttu-id="6c6c6-174">提高性能</span><span class="sxs-lookup"><span data-stu-id="6c6c6-174">Better Performance</span></span> | <span data-ttu-id="6c6c6-175">通过电池寿命稍有优先性能，作为默认滑块模式。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-175">Slightly favors performance over battery life, functioning as the default slider mode.</span></span> |
| <span data-ttu-id="6c6c6-176">最佳性能</span><span class="sxs-lookup"><span data-stu-id="6c6c6-176">Best Performance</span></span> | <span data-ttu-id="6c6c6-177">对需要最高性能和响应能力的工作负载，无论电池电量消耗如何，均优先于性能。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-177">Favors performance over power for workloads requiring maximum performance and responsiveness, regardless of battery power consumption.</span></span>|

<span data-ttu-id="6c6c6-178">"电源" 滑块模式直接控制下表中所示的特定硬件组件。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-178">Power slider modes directly control specific hardware components shown in the following table.</span></span>

| <span data-ttu-id="6c6c6-179">组件</span><span class="sxs-lookup"><span data-stu-id="6c6c6-179">Component</span></span> | <span data-ttu-id="6c6c6-180">滑块功能</span><span class="sxs-lookup"><span data-stu-id="6c6c6-180">Slider functionality</span></span> |
|---|---|
| <span data-ttu-id="6c6c6-181">英特尔®速度班次（CPU 能源寄存器）和能源性能首选项提示。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-181">Intel Speed Shift (CPU energy registers) and Energy Performance Preference hint.</span></span> | <span data-ttu-id="6c6c6-182">为获得最佳性能和功率选择最佳运行频率和电压。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-182">Selects the best operating frequency and voltage for optimal performance and power.</span></span> <span data-ttu-id="6c6c6-183">能源性能首选项（PERFEPP）是 CPU 的全局电源效率提示。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-183">The Energy Performance Preference (PERFEPP) is a global power efficiency hint to the CPU.</span></span> |
| <span data-ttu-id="6c6c6-184">风扇速度（RPM）</span><span class="sxs-lookup"><span data-stu-id="6c6c6-184">Fan speed (RPM)</span></span>| <span data-ttu-id="6c6c6-185">如果适用，请调整更改条件，例如在节电模式的 "切换" 滑块模式下保持风扇无提示。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-185">Where applicable, adjusts for changing conditions such as keeping fan silent in battery saver slider mode.</span></span>|
| <span data-ttu-id="6c6c6-186">处理器封装的电源限制（PL1/PL2）。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-186">Processor package power limits (PL1/PL2).</span></span>| <span data-ttu-id="6c6c6-187">需要 CPU 管理其频率选项，以适应适用于稳定状态（PL1）和 turbo （PL2）工作负荷的运行平均功率限制。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-187">Requires the CPU to manage its frequency choices to accommodate a running average power limit for both steady state (PL1) and turbo (PL2) workloads.</span></span>|
| <span data-ttu-id="6c6c6-188">处理器 turbo frequency 限制（IA turbo 限制）。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-188">Processor turbo frequency limits (IA turbo limitations).</span></span> | <span data-ttu-id="6c6c6-189">调整处理器和图形性能，使处理器内核运行速度比额定工作频率更快或更慢。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-189">Adjusts processor and graphics performance allowing processor cores to run faster or slower than the rated operating frequency.</span></span>                                                |

>[!NOTE]
><span data-ttu-id="6c6c6-190">无论是从 "控制面板"/"电源选项"、"组策略" 还是 "相关方法" 配置的，"电源" 滑块都完全独立于操作系统电源设置。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-190">The power slider is entirely independent of operating system power settings whether configured from Control Panel/ Power Options, Group Policy, or related methods.</span></span>

<span data-ttu-id="6c6c6-191">若要了解更多，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-191">To learn more, see:</span></span>

-   [<span data-ttu-id="6c6c6-192">自定义 Windows 性能 "电源" 滑块</span><span class="sxs-lookup"><span data-stu-id="6c6c6-192">Customize the Windows performance power slider</span></span>](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [<span data-ttu-id="6c6c6-193">节电模式。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-193">Battery saver.</span></span>](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## <span data-ttu-id="6c6c6-194">延长电池使用时间的最佳做法</span><span class="sxs-lookup"><span data-stu-id="6c6c6-194">Best practices for extended battery life</span></span>


| <span data-ttu-id="6c6c6-195">最佳做法</span><span class="sxs-lookup"><span data-stu-id="6c6c6-195">Best practice</span></span> | <span data-ttu-id="6c6c6-196">转到</span><span class="sxs-lookup"><span data-stu-id="6c6c6-196">Go to</span></span> | <span data-ttu-id="6c6c6-197">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6c6c6-197">Next steps</span></span> |
|---|---|---|                                                                                                                                    
| <span data-ttu-id="6c6c6-198">确保你的 Surface 设备处于最新状态</span><span class="sxs-lookup"><span data-stu-id="6c6c6-198">Ensure your Surface device is up to date</span></span>| <span data-ttu-id="6c6c6-199">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="6c6c6-199">Windows Update</span></span> | <span data-ttu-id="6c6c6-200">在任务栏搜索框中，键入 " **Windows 更新**"，然后选择 "**检查更新**"。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-200">In the taskbar search box, type **Windows Update** and select **Check for updates**.</span></span> |
| <span data-ttu-id="6c6c6-201">为你正在执行的操作选择最佳电源设置</span><span class="sxs-lookup"><span data-stu-id="6c6c6-201">Choose the best power setting for what you’re doing</span></span> | <span data-ttu-id="6c6c6-202">Power 滑块</span><span class="sxs-lookup"><span data-stu-id="6c6c6-202">Power slider</span></span> | <span data-ttu-id="6c6c6-203">在任务栏中，选择电池图标，然后选择 "**最佳性能**"、"**最佳电池使用**时间" 或 "介于" 之间的某个位置。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-203">In the taskbar, select the battery icon, then choose **Best performance**, **Best battery life**, or somewhere in between.</span></span>|
| <span data-ttu-id="6c6c6-204">节省电池电量不足的情况</span><span class="sxs-lookup"><span data-stu-id="6c6c6-204">Conserve battery when it’s low</span></span> | <span data-ttu-id="6c6c6-205">节电模式</span><span class="sxs-lookup"><span data-stu-id="6c6c6-205">Battery saver</span></span> | <span data-ttu-id="6c6c6-206">在任务栏中，选择电池图标，然后单击 "**电池设置**"。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-206">In the taskbar, select the battery icon and click **Battery settings**.</span></span> <span data-ttu-id="6c6c6-207">**如果我的电池低于以下**时间，请选择 "自动打开节电模式"，然后将滑块向右移动，延长电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-207">Select **Turn battery saver on automatically if my battery falls below** and then move the slider further to the right for longer battery life.</span></span> |
| <span data-ttu-id="6c6c6-208">配置最佳屏幕亮度</span><span class="sxs-lookup"><span data-stu-id="6c6c6-208">Configure optimal screen brightness</span></span> | <span data-ttu-id="6c6c6-209">节电模式</span><span class="sxs-lookup"><span data-stu-id="6c6c6-209">Battery saver</span></span> | <span data-ttu-id="6c6c6-210">在任务栏中，选择电池图标，然后单击 "**电池设置**"，**在节电模式中选择较低的屏幕亮度**。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-210">In the taskbar, select the battery icon and click **Battery settings**, select **Lower screen brightness while in battery saver**.</span></span> |
| <span data-ttu-id="6c6c6-211">在未插入时节省电能</span><span class="sxs-lookup"><span data-stu-id="6c6c6-211">Conserve power whenever you’re not plugged in</span></span> | <span data-ttu-id="6c6c6-212">节电模式</span><span class="sxs-lookup"><span data-stu-id="6c6c6-212">Battery saver</span></span>| <span data-ttu-id="6c6c6-213">选择 **"打开电池保护状态，直到下一次充电"**。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-213">Select **Turn on battery saver status until next charge**.</span></span>|
| <span data-ttu-id="6c6c6-214">调查您的电源设置问题。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-214">Investigate problems with your power settings.</span></span> | <span data-ttu-id="6c6c6-215">Power 疑难解答</span><span class="sxs-lookup"><span data-stu-id="6c6c6-215">Power troubleshooter</span></span> | <span data-ttu-id="6c6c6-216">在任务栏中搜索 "疑难解答"，选择 "**疑难解答**"，然后选择 "**电源**" 并按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-216">In the Taskbar search for troubleshoot, select **Troubleshoot**, and then select **Power** and follow the instructions.</span></span>|
| <span data-ttu-id="6c6c6-217">检查应用使用情况</span><span class="sxs-lookup"><span data-stu-id="6c6c6-217">Check app usage</span></span> | <span data-ttu-id="6c6c6-218">你的应用</span><span class="sxs-lookup"><span data-stu-id="6c6c6-218">Your apps</span></span> | <span data-ttu-id="6c6c6-219">关闭应用。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-219">Close apps.</span></span>|
| <span data-ttu-id="6c6c6-220">检查您的电源线是否有任何损坏。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-220">Check your power cord for any damage.</span></span>| <span data-ttu-id="6c6c6-221">您的电源线</span><span class="sxs-lookup"><span data-stu-id="6c6c6-221">Your power cord</span></span> | <span data-ttu-id="6c6c6-222">如果电源线磨损或损坏，请将其更换。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-222">Replace power cord if worn or damaged.</span></span>|

## <span data-ttu-id="6c6c6-223">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="6c6c6-223">Learn more</span></span> 

- [<span data-ttu-id="6c6c6-224">新式备用</span><span class="sxs-lookup"><span data-stu-id="6c6c6-224">Modern   standby</span></span>](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [<span data-ttu-id="6c6c6-225">自定义 Windows 性能 "电源" 滑块</span><span class="sxs-lookup"><span data-stu-id="6c6c6-225">Customize the Windows performance power   slider</span></span>](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [<span data-ttu-id="6c6c6-226">节电模式</span><span class="sxs-lookup"><span data-stu-id="6c6c6-226">Battery   saver</span></span>](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [<span data-ttu-id="6c6c6-227">管理和部署 Surface 驱动程序和固件更新</span><span class="sxs-lookup"><span data-stu-id="6c6c6-227">Manage and deploy Surface driver and firmware updates</span></span>](manage-surface-driver-and-firmware-updates.md)

---
title: Surface 设备电源设置的最佳做法
description: 本主题提供了维护最佳电源设置的最佳方案建议，并说明了 Surface 如何简化电源管理体验。 本文适用于所有当前受支持的 Surface 设备，包括 Surface Pro 7+、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。
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
ms.openlocfilehash: 23b94c865c43ad92b7ae6f047e980084760e4aed
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911747"
---
# <a name="best-practice-power-settings-for-surface-devices"></a>Surface 设备电源设置的最佳做法

Surface 设备旨在利用移动设备能耗的最新发展，从而提供跨工作负载优化的简化体验。 根据你正在执行的任务，Surface 动态微调电源如何流动到各个硬件组件，在返回到低功耗空闲状态 (S0ix) 之前，暂时唤醒系统组件以处理后台任务（如传入电子邮件或网络流量）。

## <a name="summary-of-recommendations-for-it-administrators"></a>针对 IT 管理员的建议摘要

若要确保整个组织的 Surface 设备完全受益于 Surface 电源优化功能：

-  从更新或 Surface 驱动程序和固件 MSI Windows最新的驱动程序和固件。 这将默认创建平衡电源 (配置文件) 并配置最佳电源设置。  有关详细信息，请参阅管理和部署 [Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)。
- 避免创建自定义电源配置文件或调整默认 UI 中不可见的高级电源设置 (**系统**电源&  >  **睡眠**) 。
- 如果你必须管理整个网络 (（如在高度托管的组织) 中）的设备电源配置文件，请使用 powercfg 命令工具从 Surface 设备的出厂映像导出电源计划，然后将它导入到 Surface 设备的预配包中。 

    >[!NOTE]
    >你只能跨相同类型的 Surface 设备导出电源计划。  例如，不能从系统导出电源Surface Laptop并导入Surface Pro。  有关详细信息，请参阅配置 [电源设置](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)。

- 从任何现有的电源管理策略设置中排除 Surface 设备。 

## <a name="background"></a>Background

Surface 实现电源管理的方式与早期的操作系统标准明显不同，早期操作系统标准通过一系列睡眠状态逐渐减少和关闭电源;例如，循环到 S1、S2、S3 等。

而 Surface 使用自定义电源配置文件进行映像处理，该配置文件将传统睡眠和能耗功能替换为现代待机功能和动态微调。 此自定义电源配置文件通过 Surface Serial Hub 驱动程序和系统聚合器模块和 SAM (实现) 。 SAM 芯片用作 Surface 设备电源策略所有者，使用算法计算最佳电源要求。 它可与硬件Windows结合使用，以仅分配或限制硬件组件正常运行所需的准确电量。 本文适用于所有当前受支持的 Surface 设备，包括 Surface Pro 7+、Surface Laptop Go、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。

## <a name="utilizing-the-custom-power-profile-in-surface"></a>利用 Surface 中的自定义电源配置文件

如果你转到 Surface 设备的电源选项，你将看到有一个电源计划可用。 这是自定义电源配置文件。 如果你转到高级电源设置，你将看到与运行电源选项的通用电脑相比，电源选项的子集要小Windows 10。 与通用设备不同，Surface 具有固件和自定义组件来管理这些电源选项。


## <a name="modern-standby"></a>现代待机

采用算法嵌入的自定义电源配置文件通过为智能手机的典型即时开/即时关闭功能保持低电源状态，为 Surface 实现现代待机连接。 S0ix（也称为最深运行时空闲平台状态 (则) 是 Surface 设备的默认电源模式。 现代待机有两种模式：

- **连接待机。** 电子邮件、邮件传递和云同步数据即时传递的默认模式，连接待机使Wi-Fi保持网络连接。

- **断开连接的待机。** 为延长电池使用时间，断开连接的待机模式提供了相同的即时打开体验，并且通过关闭 WLAN、蓝牙和相关网络连接来节省电源。

若要详细了解新式待机，请参阅[Microsoft](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)硬件开发人员中心。

## <a name="how-surface-streamlines-the-power-management-experience"></a>Surface 如何简化电源管理体验 

Surface 集成了以下旨在帮助用户优化电源管理体验的功能：

- [单数电源计划](#singular-power-plan)

- [简化的电源设置用户界面](#simplified-power-settings-user-interface)

- [Windows性能电源滑块](#windows-performance-power-slider)

### <a name="singular-power-plan"></a>单数电源计划

Surface 专为简化的电源管理体验设计，无需创建自定义电源计划或手动配置电源设置。 Microsoft 通过提供单个电源计划 (平衡) 替换标准内部版本中的多个电源Windows用户体验。

### <a name="simplified-power-settings-user-interface"></a>简化的电源设置用户界面

Surface 提供简化的 UI，与最佳做法电源设置建议一致。 通常，建议仅调整默认用户界面中可见的设置，并避免配置高级电源设置或组策略设置。 使用默认屏幕和睡眠超时，同时避免最大亮度级别是用户保持延长电池使用时间的最有效方法。

![图 1. 简化电源&睡眠设置。](images/powerintrofig1.png)

图 1. 简化电源和睡眠设置

### <a name="windows-performance-power-slider"></a>Windows性能电源滑块

运行 1709 Windows 10版本 1709 及更高版本的 Surface 设备包括一个电源滑块，可让你根据需要确定电池使用时间优先级或支持性能（如果需要）。 可以通过单击电池图标从任务栏访问电源滑块。 向左滑动以延长电池使用时间 (节电模式) 或向右滑动以提高性能。

![图 2. 电源滑块。](images/powerintrofig2a.png)

图 2. 电源滑块

电源滑块启用四种状态，如下表所述：

| 滑块模式| 描述 |
|---|---|
| 节电模式| 当系统与电源断开连接时，有助于节省电源并延长电池使用时间。 节电模式处于打开状态时，Windows禁用、限制或行为方式有所不同。 屏幕亮度也会降低。 节电模式仅在使用电池电源 (DC) 。 若要了解更多信息，请参阅 [节电模式](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)。|
| 推荐 | 与早期版本的 Windows 中的默认设置Windows。 |
| 性能更佳 | 在电池使用时间上稍微提升性能，用作默认滑块模式。 |
| 最佳性能 | 对于需要最高性能和响应速度的工作负荷，无论电池电源消耗如何，都支持性能超过电源。|

电源滑块模式直接控制下表中所示的特定硬件组件。

| 组件 | 滑块功能 |
|---|---|
| Intel Speed Shift (CPU 能耗注册) 和能耗性能首选项提示。 | 选择最佳操作频率和优化性能与电源。 PERFEPP (性能) 是 CPU 的全局电源效率提示。 |
| 扇出 (RPM) | 如果适用，可针对更改条件进行调整，例如，在节电模式滑块模式下使扇形保持无提示。|
| PL1/PL2 (处理器) 。| 要求 CPU 管理其频率选择，以适应稳定状态 (PL1) 和大量 PL2 负载 (的平均) 限制。|
| 处理器的高速频率 (IA 的) 。 | 调整处理器和图形性能，使处理器核心的运行速度比已评分的操作系统频率快或慢。                                                |

>[!NOTE]
>电源滑块完全独立于操作系统电源设置，无论是从控制面板/电源选项、组策略还是相关方法配置。

若要了解更多，请参阅：

-   [自定义Windows性能电源滑块](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [节电模式。](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## <a name="best-practices-for-extended-battery-life"></a>延长电池使用时间的最佳方案


| 最佳做法 | 转到 | 后续步骤 |
|---|---|---|                                                                                                                                    
| 确保 Surface 设备是最新的| Windows 更新 | 在任务栏搜索框中，键入Windows**更新"** 并选择"**检查更新"。** |
| 为正在执行的工作选择最佳电源设置 | 电源滑块 | 在任务栏中，选择电池图标，然后选择 **"最佳性能"、"****最佳**电池使用时间"或介于两者之间的某个位置。|
| 在电量不足时节省电池 | 节电模式 | 在任务栏中，选择电池图标，然后单击 **电池设置**。 如果我 **的电池低于，** 请选择"自动打开节电模式"，然后将滑块进一步向右移动，延长电池使用时间。 |
| 配置最佳屏幕亮度 | 节电模式 | 在任务栏中，选择电池图标，然后单击电池 **设置**，选择节电模式时降低 **屏幕亮度**。 |
| 每次未接通电源时节省电源 | 节电模式| 选择 **打开节电模式状态直到下一次充电**。|
| 调查电源设置的问题。 | 电源疑难解答程序 | 在任务栏搜索中查找疑难解答， **选择疑**难解答 ，然后选择 **电源** 并按照说明进行操作。|
| 检查应用使用情况 | 应用 | 关闭应用。|
| 检查您的电缆是否有损坏。| 您的电缆 | 如果断电或已损坏，则更换电缆。|

## <a name="learn-more"></a>了解详细信息 

- [现代待机](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [自定义Windows性能电源滑块](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [节电模式](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [管理和部署 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)

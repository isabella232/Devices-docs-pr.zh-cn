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
# Surface 设备电源设置的最佳实践

Surface 设备旨在充分利用移动设备能源消耗中的最新进展，以提供跨工作负载优化的简化体验。 根据你正在执行的操作，Surface 会动态地调整如何处理单个硬件组件的电源，并在返回到低电量空闲状态（S0ix）之前，立即唤醒系统组件以处理后台任务，例如传入的电子邮件或网络流量。

## IT 管理员建议摘要

若要确保整个组织中的 Surface 设备完全受益于 Surface power 优化功能，请执行以下操作：

-  从 Windows 更新或 Surface Driver 和固件 MSI 安装最新的驱动程序和固件。 这将默认创建平衡电源计划（亦称为电源配置文件），并配置最佳电源设置。  有关详细信息，请参阅[管理和部署 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)。
- 避免创建自定义电源配置文件或调整默认 UI （**系统**  >  **power & 睡眠**）中不可见的高级电源设置。
- 如果必须在网络上管理设备的电源配置文件（例如，在高度托管的组织中），请使用 powercfg 命令工具从 Surface 设备的工厂映像中导出电源计划，然后将其导入到 Surface 设备的预配包中。 

    >[!NOTE]
    >您只能在同一类型的 Surface 设备上导出电源计划。  例如，您无法从 Surface 笔记本电脑导出电源计划，并将其导入 Surface Pro。  有关详细信息，请参阅[配置电源设置](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)。

- 从任何现有的电源管理策略设置中排除 Surface 设备。 

## Background

Surface 实现电源管理的方式与早期操作系统标准显著不同，后者通过一系列睡眠状态逐渐降低和关闭电源;例如，通过 S1、S2、S3 等进行循环。

相反，Surface 是使用自定义电源配置文件的映像，它将旧的睡眠和能源消耗功能替换为新式待机功能和动态微调。 此自定义电源配置文件通过 Surface 串行集线器驱动程序和系统聚合器模块（SAM）实现。 SAM 芯片充当 Surface 设备电源策略所有者，使用算法计算最佳电源需求。 它与 Windows power manager 结合使用，以仅分配或限制硬件组件正常工作所需的确切电量。 本文适用于所有当前支持的 Surface 设备，包括 Surface Pro 7、Surface Pro X 和 Surface 笔记本3。

## 利用图面中的自定义 power profile

如果您进入 surface 设备上的 "电源" 选项，您将看到有一个可用的电源套餐。 这是自定义电源配置文件。 如果你转到 "高级" 电源设置，你将看到一个与运行 Windows 10 的通用电脑相比的电源选项的更小子集。 与通用设备不同，Surface 具有用于管理这些电源选项的固件和自定义组件。


## 新式备用

Algorithmically 嵌入的自定义 power profile 通过为智能手机的 "即时开启" 和 "即时" 功能保持较低的电源状态，为表面启用新式待机连接。 S0ix （也称为 "最深的运行时空闲平台状态（DRIPS）"）是 Surface 设备的默认电源模式。 新式备用有两种模式：

- **已连接待机。** 通过电子邮件、消息传递和云同步数据的最新传递的默认模式，已连接的备用设备将保持 Wi-fi 打开并保持网络连接。

- **已断开连接待机。** 延长电池使用时间的可选模式，已断开的待机功能通过关闭 Wi-fi、蓝牙和相关网络连接来提供相同的即时体验并节省电能。

若要了解有关新式待机的详细信息，请参阅[Microsoft 硬件开发人员中心](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)。

## 图面如何简化电源管理体验 

Surface 集成了以下用于帮助用户优化电源管理体验的功能：

- [单数电源计划](#singular-power-plan)

- [简化的电源设置用户界面](#simplified-power-settings-user-interface)

- [Windows 性能高滑块](#windows-performance-power-slider)

### 单数电源计划

图面适用于简化的电源管理体验，无需创建自定义电源计划或手动配置电源设置。 Microsoft 通过提供单个电源计划（已平衡）来取代标准 Windows 内部版本的多个电源计划，优化了用户体验。

### 简化的电源设置用户界面

Surface 按照最佳做法电源设置建议提供简化的 UI。 通常，建议仅在默认用户界面中调整可见设置，避免配置高级电源设置或组策略设置。 使用默认屏幕和睡眠超时，同时避免最高亮度级别是用户保持延长电池寿命的最有效方式。

![图 1. 已简化 power & 睡眠设置](images/powerintrofig1.png)

图 1. 简化的电源和睡眠设置

### Windows 性能高滑块

运行 Windows 10 内部版本1709和更高版本的 Surface 设备包括一个 power 滑块，使你能够根据需要设置电池使用时间的优先级，或优选性能（如果需要）。 通过单击电池图标，可以从任务栏访问 "电源" 滑块。 向左滑动以延长电池使用时间（节电模式）或向右滑动以提高性能。

![图 2. Power 滑块](images/powerintrofig2a.png)

图 2. Power 滑块

Power 滑块支持四种状态，如下表所述：

| 滑块模式| 描述 |
|---|---|
| 节电模式| 当系统断开与电源的连接时，可帮助省电并延长电池使用时间。 节电模式处于打开状态时，某些 Windows 功能将被禁用、阻止或行为不同。 屏幕亮度也会减少。 只有在使用电池电源（DC）时，节电模式才可用。 若要了解详细信息，请参阅[节电](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)模式。|
| 推荐 | 比早期版本的 Windows 中的默认设置提供更长的电池使用时间。 |
| 提高性能 | 通过电池寿命稍有优先性能，作为默认滑块模式。 |
| 最佳性能 | 对需要最高性能和响应能力的工作负载，无论电池电量消耗如何，均优先于性能。|

"电源" 滑块模式直接控制下表中所示的特定硬件组件。

| 组件 | 滑块功能 |
|---|---|
| 英特尔®速度班次（CPU 能源寄存器）和能源性能首选项提示。 | 为获得最佳性能和功率选择最佳运行频率和电压。 能源性能首选项（PERFEPP）是 CPU 的全局电源效率提示。 |
| 风扇速度（RPM）| 如果适用，请调整更改条件，例如在节电模式的 "切换" 滑块模式下保持风扇无提示。|
| 处理器封装的电源限制（PL1/PL2）。| 需要 CPU 管理其频率选项，以适应适用于稳定状态（PL1）和 turbo （PL2）工作负荷的运行平均功率限制。|
| 处理器 turbo frequency 限制（IA turbo 限制）。 | 调整处理器和图形性能，使处理器内核运行速度比额定工作频率更快或更慢。                                                |

>[!NOTE]
>无论是从 "控制面板"/"电源选项"、"组策略" 还是 "相关方法" 配置的，"电源" 滑块都完全独立于操作系统电源设置。

若要了解更多，请参阅：

-   [自定义 Windows 性能 "电源" 滑块](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [节电模式。](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## 延长电池使用时间的最佳做法


| 最佳做法 | 转到 | 后续步骤 |
|---|---|---|                                                                                                                                    
| 确保你的 Surface 设备处于最新状态| Windows 更新 | 在任务栏搜索框中，键入 " **Windows 更新**"，然后选择 "**检查更新**"。 |
| 为你正在执行的操作选择最佳电源设置 | Power 滑块 | 在任务栏中，选择电池图标，然后选择 "**最佳性能**"、"**最佳电池使用**时间" 或 "介于" 之间的某个位置。|
| 节省电池电量不足的情况 | 节电模式 | 在任务栏中，选择电池图标，然后单击 "**电池设置**"。 **如果我的电池低于以下**时间，请选择 "自动打开节电模式"，然后将滑块向右移动，延长电池使用时间。 |
| 配置最佳屏幕亮度 | 节电模式 | 在任务栏中，选择电池图标，然后单击 "**电池设置**"，**在节电模式中选择较低的屏幕亮度**。 |
| 在未插入时节省电能 | 节电模式| 选择 **"打开电池保护状态，直到下一次充电"**。|
| 调查您的电源设置问题。 | Power 疑难解答 | 在任务栏中搜索 "疑难解答"，选择 "**疑难解答**"，然后选择 "**电源**" 并按照说明进行操作。|
| 检查应用使用情况 | 你的应用 | 关闭应用。|
| 检查您的电源线是否有任何损坏。| 您的电源线 | 如果电源线磨损或损坏，请将其更换。|

## 了解详细信息 

- [新式备用](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [自定义 Windows 性能 "电源" 滑块](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [节电模式](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [管理和部署 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)

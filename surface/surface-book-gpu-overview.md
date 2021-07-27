---
title: Surface Book 3 GPU 技术概述
description: 本文提供跨 3 种模型对 GPU Surface Book技术评估。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 5/06/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 26a6d49af6010f66ed80d0aba1193ef009c91ff0
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676516"
---
# <a name="surface-book-3-gpu-tech-overview"></a>Surface Book 3 GPU 技术概述

## <a name="introduction"></a>简介

Surface Book 3（功能最强大的 Surface 笔记本电脑）将完全现代化计算和图形功能集成到其强大的可分离外形设备中。  由 15 英寸型号上的四核第 10 代 Intel® Core™ i7 和 NVIDIA® Quadro RTX™ 3000 图形处理单元 (GPU) 引导，Surface Book 3 为消费者、创意专业人员、架构师、工程师和数据工作者提供了各种配置。 本文介绍了 GPU 配置在 13 英寸和 15 英寸 3 种型号之间Surface Book差异。

GPU 配置是Surface Book GPU 配置这三种模型间的重要区别。 除了内置于所有型号的集成 Intel GPU 外，除入口点级别 13.5 英寸核心 i5 设备外，其他所有设备都使用具有 Max-Q 设计的离散 NVIDIA GPU，其中融入了优化移动外形尺寸的节能功能。

其他 NVIDIA GPU 内置于键盘基础中，提供高级图形呈现功能，并附带两个主要配置：GeForce® GTX® 1650/1660 Ti for consumers or creative professionals 和 Quadro RTX 3000 for creative professionals， engineers， and other business professionals who need advanced graphics or deep learning capabilities. 本文还介绍如何通过指定哪些应用应该使用集成 iGPU 而非离散 NVIDIA GPU 来优化 GPU 的应用利用率。

## <a name="surface-book-3-gpus"></a>Surface Book 3 个 GPU

本节介绍跨 3 种模型的集成和离散 GPU Surface Book GPU。 有关所有模型的配置详细信息，请参阅附录[A：Surface Book 3 个 SK。](#)

### <a name="intel-iris-plus-graphics"></a>Intel Iris™ Plus 图形

所有 (3) 集成的 GPU Surface Book 3 模型包含更广泛的图形引擎和重新设计的内存控制器，并支持 LPDDR4X。 作为辅助 GPU 安装在大多数 Surface Book 3 型号上，Intel Iris Plus Graphics 在核心 i5 13.5 英寸模型中用作单数 GPU。 尽管实际上是 Surface Book 3 行中的入口点设备，但它提供高级图形功能，使消费者、爱好家和在线创意者能够运行最新的生产力软件，如 Adobe Creative Cloud 或在 1080p 中享受游戏作品。  

### <a name="nvidia-geforce-gtx-1650"></a>NVIDIA GeForce GTX 1650

NVIDIA GeForce GTX 1650 与 Max-Q 设计提供了核心流式处理多处理器的主要升级，以更有效地处理现代游戏的复杂图形。 它并发执行浮点和整数操作可提升现代游戏计算密集型工作负载中的性能。 新的统一内存体系结构及其前一个缓存的两倍，可以在复杂的现代游戏上实现更好的性能。 新的底纹改进可提高性能、增强图像质量，并提供几何复杂性的新级别。

### <a name="nvidia-geforce-gtx-1660-ti"></a>NVIDIA GeForce GTX 1660 Ti

与 GeForce GTX 1650 相比，更快的 GeForce GTX 1660 Ti 为 Surface Book 3 提供了额外的性能改进，并包括新的和升级的 NVIDIA 编码器，从而更好地供消费者、玩家、实时流处理者和创意专业人员使用。

由于 GDDR6 图形内存为 6 GB，配备了 NVIDIA GeForce GTX 1660 TI 的 Surface Book 3 型号在高级业务生产力软件和热门游戏上提供了出色的速度，尤其是在运行最现代游戏或实时流时。 使用可选的 2 TB SSD (仅适用于美国) ，15 英寸的 GeForce GTX 1660 Ti 型号可提供任何 Surface Book 3 设备最多存储。

### <a name="nvidia-quadro-rtx-3000"></a>NVIDIA Quadro RTX 3000

NVIDIA Quadro RTX 3000 为专业用户解锁了一些关键功能：光线跟踪呈现和 AI 加速，以及高级图形和计算性能。 组合使用 30 个 RT 内核、240 个张量内核和 6 GB 的 GDDR6 图形内存，可实现多种高级工作负载，包括支持 3D 的工作流、3D 内容创建、高级视频编辑、专业广播和多应用工作流。 Enterprise级别的硬件和软件支持集成部署工具，以最大限度地缩短正常运行时间并最大程度减少 IT 支持要求。 Quadro 驱动程序经过认证，适用于专业应用程序，经过调整、测试和验证，可提供应用认证、企业级稳定性、可靠性、可用性以及扩展产品可用性支持。
 

## <a name="comparing-gpus-across-surface-book-3"></a>比较第 3 Surface Book 3 个 GPU

NVIDIA GPU 为用户提供了出色的游戏、实时流和内容创建性能。 GeForce GTX 产品非常适用于玩家和内容创建者。 Quadro RTX 产品面向专业用户，在游戏和内容创建方面提供出色的性能，并添加以下功能：

- 用于光线跟踪和 AI 的 RTX 加速。 这样一来，就能够渲染具有物理精确阴影、反射和反射的影片质量、光真对象和环境。  其硬件加速 AI 功能意味着热门应用程序中基于 AI 的高级功能可以比以往更快地运行。
- Enterprise级硬件、驱动程序和支持以及 ISV 应用认证。
- IT 管理功能，包括用于远程管理的专用企业工具的附加层，可帮助最大化正常运行时间并最大程度减少 IT 支持要求。

 除非你将自己算在高级工程、设计、体系结构或数据科学专业人员的排名中，否则配备 NVIDIA GeForce 图形功能的 Surface Book 3 可能会满足您的需求。 相反，如果你已加入（或正在加入）一项需要高度高级图形功能（可随时随地使用可移植外形设备，Surface Book 3 和 Quadro RTX 3000）的专业值得认真考虑。 若要了解详情，请参阅 Surface Book 3 Quadro RTX 3000 技术概述。
 
**表 1. Surface Book 3 上的离散 GPU**

|                      | **GeForce GTX 1650**                   | **GeForce GTX 1660 Ti**                            | **Quadro RTX 3000**                                                                                       |
| -------------------- | -------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **目标用户**     | 玩家、爱好者和在线创意者  | 玩家、创意专业人员和在线创意者 | 创意专业人员、架构师、工程师、开发人员、数据工作者                                |
| **工作流**        | 图形设计<br>摄影<br>视频 | 图形设计<br>摄影<br>视频             | Al-powered Workflows  <br>应用认证<br>High-res 视频<br>Pro广播<br>多应用工作流 |
| **关键应用**         | Adobe Creative Suite                   | Adobe Creative Suite                               | Adobe Creative Suite<br>自动服务台AutoCAD<br>Dassault Systemes SolidWorks                                  |
| **GPU 加速** | 视频和图像处理             | 视频和图像处理                         | 光线跟踪 + AI + 6K 视频<br>Pro广播功能<br>Enterprise支持                            |


**表 2.  Surface Book 3 上的 GPU 技术规格**

|                                                          | **GeForce GTX 1650** | **GeForce GTX 1660 Ti** | **Quadro RTX 3000** |
| -------------------------------------------------------- | -------------------- | ----------------------- | ------------------- |
| **NVIDIA CUDA 处理内核**                         | 1024                 | 1536                    | 1920                |
| **NVIDIA Tensor Cores**                                  | 否                   | 否                      | 240                 |
| **NVIDIA RT 核心**                                      | 否                   | 否                      | 30                  |
| **GPU 内存**                                           | 4 GB                 | 6 GB                    | 6 GB                |
| **内存带宽 (GB/秒) **                            | 最多 112 个            | 最多 288 个               | 最多 288 个           |
| **内存类型**                                          | GDDR5                | GDDR6                   | GDDR6               |
| **内存接口**                                     | 128 位              | 192 位                 | 192 位             |
| **提高时钟 MHz**                                      | 1245                 | 1425                    | 1305                |
| **基本时钟 (MHz) **                                     | 1020                 | 1245                    | 765                 |
| **实时光线跟踪**                                | 否                   | 否                      | 是                 |
| **AI 硬件加速**                             | 否                   | 否                      | 是                 |
| **硬件编码器**                                     | 是                  | 是                     | 是                 |
| **游戏就绪驱动程序 (GRD) **                              | 是 <sup> 1</sup>                                   | 是  <sup> 1</sup>          |是 <sup> 2</sup> 
| **Studio 驱动程序 (SD) **                                   | 是  <sup> 1</sup>            | 是 <sup> 1</sup>                 | 是  <sup> 1</sup>           |
| **优化 ODE Enterprise (驱动程序) **                  | 否                   | 否                      | 是            |
| **四边形新功能驱动程序 (QNF) **                      | 否                   | 否                      | 是            |
| **Microsoft DirectX 12 API， Vulkan API， Open GL 4.6**    | 是                  | 是                     | 是                 |
| **高带宽数字内容保护 (HDCP) 2.2** | 是                  | 是                     | 是                 |
| **NVIDIA GPU 提升**                                     | 是                  | 是                     | 是                 |


 1. *推荐*
 2.  *支持*

## <a name="optimizing-power-and-performance-on-surface-book-3"></a>优化 3 上的电源Surface Book性能

Windows 10具有性能滑块的节电模式，可让你通过向右滑动应用性能 (或将电池使用时间 () 滑动到左侧) 来保持电池使用时间。 Surface Book 3 以算法方式实现此功能，以优化以下组件中的电源和性能：

- CPU 能源效率 注册 (Intel Speed Shift 技术) 和其他 SoC 调整参数以最大化效率。
- 具有四种模式的最大 RPM：安静、无名、性能和最大值。
- 处理器电源大 (PL1/PL2) 。
- 处理器 IA 的一些限制。

默认情况下，当电池电量低于 20% 时，节电模式将调整设置以延长电池使用时间。 连接电源时，Surface Book 3 默认为"最佳性能"设置，以确保应用在所有 i7 Surface Book 3 系统上存在于辅助 NVIDIA GPU 上以高性能模式运行。

当用作笔记本电脑或在平板电脑或 Studio 模式下分离时，建议使用默认设置以获得最佳性能。 可以通过选择任务栏最右边的电池图标来访问节电模式。

### <a name="game-mode"></a>游戏模式

Surface Book 3 包括一种新的游戏模式，该模式在启动时自动选择最高性能设置。

### <a name="safe-detach"></a>保险箱分离

Surface Book 3 中的新增功能，保险箱分离的应用使你在应用使用 GPU 时断开连接。 对于支持的应用 *（如《世界*世界》），你的工作将移动到 iGPU。

### <a name="modifying-app-settings-to-always-use-a-specific-gpu"></a>修改应用设置以始终使用特定 GPU

你可以切换节能但仍支持内置 Intel 图形和更强大的离散 NVIDIA GPU，并将 GPU 与特定应用关联。 默认情况下，Windows 10选择适当的 GPU，为离散 NVIDIA GPU 分配具有图形要求的应用。 在大多数情况下，无需手动调整这些设置。 但是，如果你在使用图形上要求严格的应用时经常从键盘基础分离和重新连接屏幕，则通常需要在分离之前关闭该应用。 若要启用应用的连续使用，而无需每次分离或重新附加屏幕时都关闭它，你可以将其分配给集成的 GPU，但会丢失图形性能。  

在某些实例中，Windows 10需要图形化的应用分配为 iGPU;例如，如果应用未针对混合图形完全优化。 若要解决此问题，你可以手动将应用分配给离散 NVIDIA GPU。

**若要使用自定义每 GPU 选项配置应用：**  

1. 转到 **"设置**  >  ****  >  **系统显示"，** 然后选择"**图形设置"。**

    1. For a Windows desktop program， choose **Classic App**  >  **Browse** and then locate the program.
    2. 对于 UWP 应用，选择 **通用应用** ，然后从下拉列表中选择该应用。

2. 选择 **"** 添加"为所选程序在列表上创建新条目，选择"选项"打开"图形规范"，然后选择所需选项。

   ![选择节能或高性能 GPU 选项](./images/graphics-settings2.png)

3. 若要验证每个应用使用了哪些 GPU，请打开****"任务管理器"，选择"性能"，然后查看 **"GPU**引擎"列。 ****


## <a name="appendix-a-surface-book-3-skus"></a>附录 A：Surface Book 3 个 SUS

| **显示器**   | **处理器**                     | **GPU**                                                                                              | **RAM**    | **存储** |
| ------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------- | ----------- |
| **13.5 英寸** | 四核第 10 代核心 i5-1035G7 | Intel Iris™ Plus 图形                                                                            | 16 LPDDR4x | 256 GB      |
| **13.5 英寸** | 四核第 10 代核心版 i7-1065G7 | Intel Iris Plus 图形<br>NVIDIA GeForce GTX 1650。 具有 4GB GDDR5 图形内存的 Max-Q 设计    | 16 LPDDR4x | 256 GB      |
| **13.5 英寸** | 四核第 10 代核心版 i7-1065G7 | Intel Iris Plus 图形<br>NVIDIA GeForce GTX 1650。 具有 4GB GDDR5 图形内存的 Max-Q 设计    | 32 LPDDR4x | 512 GB      |
| **13.5 英寸** | 四核第 10 代核心版 i7-1065G7 | Intel Iris Plus 图形<br>NVIDIA GeForce GTX 1650。 具有 4GB GDDR5 图形内存的 Max-Q 设计    | 32 LPDDR4x | 1 TB        |
| **15 英寸**   | 四核第 10 代核心版 i7-1065G7 | Intel Iris Plus 图形<br>NVIDIA GeForce GTX 1660 Ti。 具有 6GB GDDR6 图形内存的 Max-Q 设计 | 16 LPDDR4x | 256 GB      |
| **15 英寸**   | 四核第 10 代核心版 i7-1065G7 | Intel Iris Plus 图形<br>NVIDIA GeForce GTX 1660 Ti。 具有 6GB GDDR6 图形内存的 Max-Q 设计 | 32 LPDDR4x | 512 GB      |
| **15 英寸**   | 四核第 10 代核心版 i7-1065G7 | Intel Iris Plus 图形<br>NVIDIA GeForce GTX 1660 Ti。 具有 6GB GDDR6 图形内存的 Max-Q 设计 | 32 LPDDR4x | 1 TB        |
| **15 英寸**   | 四核第 10 代核心版 i7-1065G7 | Intel Iris Plus 图形<br>NVIDIA GeForce GTX 1660 Ti。 具有 6GB GDDR6 图形内存的 Max-Q 设计 | 32 LPDDR4x | 2 TB        |
| **15 英寸**   | 四核第 10 代核心版 i7-1065G7 | Intel Iris Plus 图形<br>NVIDIA Quadro RTX 3000。 具有 6GB GDDR6 图形内存的 Max-Q 设计     | 32 LPDDR4x | 512 GB      |
| **15 英寸**   | 四核第 10 代核心版 i7-1065G7 | Intel Iris Plus 图形<br>NVIDIA Quadro RTX 3000。 具有 6GB GDDR6 图形内存的 Max-Q 设计     | 32 LPDDR4x | 1 TB        |

> [!NOTE]
> 仅在美国可用的 2TB SSD：Surface Book 3 15" 与 NVIDIA GTX 1660Ti

## <a name="summary"></a>摘要

为了提高性能，Surface Book 3 包括经过优化以满足特定工作负载和使用要求的不同 GPU 配置。 集成的 Intel Iris 图形 GPU 用作入口点 Core i5 设备上的唯一 GPU，以及所有其他型号上的辅助 GPU。 GeForce GTX 1650 对核心流式处理多处理器进行重大升级，以更有效地运行复杂的图形。 更快的 GeForce GTX 1660 Ti 为 Surface Book 3 提供了额外的性能改进，从而更好地供消费者、玩家、实时流处理者和创意专业人员使用。 Quadro RTX 3000 为专业用户解锁多个关键功能：光线跟踪呈现和 AI 加速，以及高级图形和计算性能。


## <a name="learn-more"></a>了解详细信息

- [Surface Book 3 Quadro RTX 3000 技术概述](surface-book-quadro.md)
- [商用 Surface](https://www.microsoft.com/surface/business)

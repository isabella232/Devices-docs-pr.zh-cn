---
title: Surface Book 3 GPU 技术概述
description: 本文提供了 Surface Book 3 模型中的 GPU 功能的技术评估。
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
ms.openlocfilehash: a3bfe6eec313c9cd9a38f966a1bed46fbc1ca92b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830683"
---
# Surface Book 3 GPU 技术概述

## 简介

Surface Book 3 （最强大的 Surface 笔记本电脑）将完全现代化的计算和图形功能集成到其著名的可分离形式因素中。  通过四核第10代英特尔®核心™ i7 和 NVIDIA® Quadro RTX™3000的图形处理单元（GPU）在15英寸模型上，Surface Book 3 为客户、创作专业人员、架构师、工程师和数据科学家提供各种配置。 本文介绍了在 Surface Book 3 的13英寸和15英寸型号的 GPU 配置之间的主要差异。

Surface Book 3 模型的显著优势是 GPU 配置。 除了内置于所有模型中的集成英特尔 GPU 之外，除了入门级13.5 英寸核心 i5 设备还具有最大的 NVIDIA GPU，其中包含可优化移动表单因素能源效率的功能。

在键盘基座中，附加的 NVIDIA GPU 提供了高级图形呈现功能，并提供了两个主要配置： GeForce®1650/1660® GTX 为富有创意的专业人士、工程师和其他需要高级图形或深入学习功能的商业专业人士的 Quadro RTX 3000。 本文还介绍了如何通过指定哪些应用应使用集成的 iGPU 与离散的 NVIDIA GPU 来优化 Gpu 的应用利用率。

## Surface Book 3 Gpu

本部分介绍 Surface Book 3 模型间的集成和离散 Gpu。 有关所有模型的配置详细信息，请参阅[附录 A： Surface Book 3 sku](#)。

### 英特尔虹膜™和图形

所有 Surface Book 3 模型中包含的集成 GPU （iGPU）都包含一个更宽的图形引擎和一个重新设计的内存控制器，支持 LPDDR4X。 作为辅助 GPU 安装在大多数 Surface Book 3 型号上，英特尔虹膜加图形功能作为核心 i5，13.5 英寸模型中的单数 GPU。 虽然 nominally Surface Book 3 行中的入门级设备，但它提供了高级图形功能，使消费者、hobbyists 和联机创建者能够运行 Adobe 创意云之类的最新生产力软件或在1080p 中体验游戏标题。  

### NVIDIA GeForce GTX 1650

NVIDIA GeForce GTX 1650，最大的问答设计提供了核心流多处理器的主要升级，以便更高效地处理新式游戏的复杂图形。 其并行执行浮点和整数运算提高了计算繁重的新式游戏工作负荷的性能。 新的统一内存体系结构，其前置任务的缓存的两倍允许在复杂的新式游戏中获得更好的性能。 新的底纹增强改善了性能，增强了图像质量，并提供了新级别的几何复杂性。

### NVIDIA GeForce GTX 1660 Ti

与 GeForce GTX 1650 相比，更快的 GeForce GTX 1660 Ti 提供了 Surface Book 3，其中提供了更多的性能改进，包括新的和已升级的 NVIDIA 编码器，使其更适合消费者、游戏玩家、实时 streamers 和创造性的专业人士。

由于有 6 GB 的 GDDR6 图形内存，配备有 NVIDIA GeForce GTX 1660 TI 的 Surface Book 3 型号在运行最新式的书名或 livestreaming 时，更高级的商业生产力软件和流行游戏的速度更高。 有了一个可选的 2 TB SSD （仅适用于美国境内），使用 GeForce GTX 1660 Ti 的15英寸机型可提供任何 Surface Book 3 设备的大部分存储空间。

### NVIDIA Quadro RTX 3000

NVIDIA Quadro RTX 3000 为专业用户解锁几项关键功能： ray 跟踪呈现和 AI 加速，以及高级图形和计算性能。 30 RT 核、240 tensor 核心和 6 GB 的 GDDR6 图形内存组合支持多项高级工作负载，包括 Al 工作流、3D 内容创建、高级视频编辑、专业广播和多应用工作流。 企业级硬件和软件支持集成部署工具以最大化运行时间并最大程度地减少 IT 支持需求。 认证适用于世界上最先进的软件，Quadro 驱动程序针对专业应用程序进行了优化，并经过优化、测试和验证，以提供应用认证、企业级稳定性、可靠性、可用性和支持，并提供更高的产品可用性。
 

## 在 Surface Book 3 中比较 Gpu

NVIDIA Gpu 为用户提供了出色的游戏、实时流处理和内容创建性能。 GeForce GTX products 非常适合游戏玩家和内容创建者。 Quadro RTX 产品面向专业用户，在游戏和内容创建方面提供出色的性能，同时还添加以下功能：

- 光线跟踪和 AI 的 RTX 加速。 这样就可以呈现具有实际准确阴影、反射和 refractions 的胶片音质、照片级逼真对象和环境。  及其硬件加速 AI 功能意味着常用应用程序中的高级基于 AI 的功能可以比以往更快的速度运行。
- 企业级硬件、驱动程序和支持，以及 ISV 应用认证。
- IT 管理功能，包括用于远程管理的专用企业工具的附加层，可帮助最大化正常运行时间并最大程度地减少 IT 支持需求。

 除非你在高级工程、设计、体系结构或数据科学专业人士的排名上进行计数，否则配备 NVIDIA GeForce 图形功能的 Surface Book 3 可能会满足你的需求。 相反，如果您已在 aspiring 中加入，则需要高度高级图形功能的专业（可让您从任意位置进行工作），使用 Quadro RTX 3000 的 Surface Book 3 才值得认真考虑。 若要了解详细信息，请参阅 Surface Book 3 Quadro RTX 3000 技术概述。
 
**表 1.  Surface Book 3 上的离散 Gpu**

|                      | **GeForce GTX 1650**                   | **GeForce GTX 1660 Ti**                            | **Quadro RTX 3000**                                                                                       |
| -------------------- | -------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **目标用户**     | 玩家、hobbyists 和联机创建者  | 玩家、创造性的专业人士和在线创建者 | 创作专业人员、架构师、工程师、开发人员、数据科学家                                |
| **流**        | 图形设计<br>摄影<br>视频 | 图形设计<br>摄影<br>视频             | Al.exe 工作的工作流  <br>应用认证<br>高分辨率视频<br>Pro 广播<br>多应用工作流 |
| **关键应用程序**         | Adobe 创意套件                   | Adobe 创意套件                               | Adobe 创意套件<br>Autodesk AutoCAD<br>Dassault Systemes SolidWorks                                  |
| **GPU 加速** | 视频和图像处理             | 视频和图像处理                         | Ray 跟踪 + AI + 6K 视频<br>Pro 广播功能<br>企业支持                            |


**表 2.  Surface Book 3 上的 GPU 技术规格**

|                                                          | **GeForce GTX 1650** | **GeForce GTX 1660 Ti** | **Quadro RTX 3000** |
| -------------------------------------------------------- | -------------------- | ----------------------- | ------------------- |
| **NVIDIA CUDA 处理核心**                         | 1024                 | 1536                    | 1920                |
| **NVIDIA Tensor 核心**                                  | 否                   | 否                      | 240                 |
| **NVIDIA RT 核心**                                      | 否                   | 否                      | 大约                  |
| **GPU 内存**                                           | 4 GB                 | 6 GB                    | 6 GB                |
| **内存带宽（GB/秒）**                            | 最多112            | 最多288               | 最多288           |
| **内存类型**                                          | GDDR5                | GDDR6                   | GDDR6               |
| **内存接口**                                     | 128位              | 192位                 | 192位             |
| **提升时钟 MHz**                                      | 1245                 | 1425                    | 1305                |
| **基本时钟（MHz）**                                     | 1020                 | 1245                    | 765                 |
| **实时计时跟踪**                                | 否                   | 否                      | 是                 |
| **AI 硬件加速**                             | 否                   | 否                      | 是                 |
| **硬件编码器**                                     | 是                  | 是                     | 是                 |
| **游戏准备驱动程序（GRD）**                              | 是 <sup> 1</sup>                                   | 是 <sup> 1</sup>          |是 <sup> 2</sup> 
| **Studio 驱动程序（SD）**                                   | 是 <sup> 1</sup>            | 是 <sup> 1</sup>                 | 是 <sup> 1</sup>           |
| **适用于企业的最佳驱动程序（ODE）**                  | 否                   | 否                      | 是            |
| **Quadro 新功能驱动程序（QNF）**                      | 否                   | 否                      | 是            |
| **Microsoft DirectX 12 API，Vulkan API，开放式总帐4。6**    | 是                  | 是                     | 是                 |
| **高带宽数字内容保护（HDCP）2。2** | 是                  | 是                     | 是                 |
| **NVIDIA GPU 提升**                                     | 是                  | 是                     | 是                 |


 1. *推荐*
 2.  *支持*

## 优化 Surface Book 3 的电源和性能

Windows 10 包括一个具有 "性能" 滑块的节电模式，可让你最大化应用性能（通过向右滑动）或保留电池使用时间（通过向左滑动）。 Surface Book 3 实现此功能 algorithmically 以优化以下组件的电源和性能：

- CPU 能源效率寄存器（英特尔®速度转换技术）和其他 SoC 优化参数以最大限度地提高效率。
- 四种模式的风扇最大 RPM：安静、名义、性能和最大值。
- 处理器电源上限（PL1/PL2）。
- 处理器 IA Turbo 限制。

默认情况下，当电池电量低于20% 时，电池保护程序将调整设置以延长电池使用时间。 当连接到 power 时，Surface Book 3 默认为 "最佳性能" 设置，以确保在所有的 i7 Surface Book 3 系统上提供的辅助 NVIDIA GPU 上以高性能模式运行应用。

当用作便携式计算机或在平板电脑或 studio 模式中分离时，建议使用默认设置以获得最佳性能。 您可以通过选择任务栏最右侧的电池图标来访问节电模式。

### 游戏模式

Surface Book 3 包含一种新的游戏模式，可在启动时自动选择最高性能设置。

### 安全分离

新在 Surface Book 3 中，为安全分离启用的应用允许你在应用使用 GPU 时断开连接。 对于受支持的*Warcraft （如世界各地的*应用），你的工作将被移动到 iGPU。

### 修改应用设置以始终使用特定 GPU

您可以在节能但仍具备内置的英特尔图形和功能更强大的独立 NVIDIA GPU 之间切换，并将 GPU 与特定应用相关联。 默认情况下，Windows 10 会自动选择相应的 GPU，将具有苛刻要求的应用分配给离散的 NVIDIA GPU。 在大多数情况下，无需手动调整这些设置。 但是，如果你在使用图形苛刻的应用时经常从键盘基中分离和重新连接显示，则你通常需要在分离之前关闭该应用。 若要允许连续使用应用，而无需在每次分离或重新连接显示时关闭它，则可以将其分配到集成的 GPU，但不会降低图形性能。  

在某些情况下，Windows 10 可能会将需要图形的苛刻应用分配给 iGPU;例如，如果应用未针对混合图形进行完全优化。 若要解决此情况，可以手动将应用分配到离散的 NVIDIA GPU。

**要使用自定义每个 GPU 选项配置应用，请执行以下操作：**  

1. 转到 "**设置**  >  **系统**  >  **显示**"，然后选择 "**图形设置**"。

    1. 对于 Windows 桌面程序，选择 "**经典应用**  >  **浏览**"，然后找到该程序。
    2. 对于 UWP 应用，选择 "**通用应用**"，然后从下拉列表中选择该应用。

2. 选择 "**添加**"，在列表上为所选程序创建新条目，选择 "选项" 以打开 "图形规格"，然后选择所需的选项。

   ![选择 "节能" 或 "高性能 GPU 选项"](./images/graphics-settings2.png)

3. 若要验证每个应用所使用的 GPU，请打开 "**任务管理器"，** 选择 "**性能"，** 然后查看 " **GPU 引擎**" 列。


## 附录 A： Surface Book 3 Sku

| **显示**   | **处理者**                     | **GPU**                                                                                              | **RAM**    | **存储** |
| ------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------- | ----------- |
| **13.5 英寸** | 四核第10代内核 i5-1035G7 | 英特尔虹膜™和图形                                                                            | 16 LPDDR4x | 256 GB      |
| **13.5 英寸** | 四核第10代内核 i7-1065G7 | 英特尔虹膜 Plus 图形<br>NVIDIA GeForce GTX 1650。 具有 4GB GDDR5 图形内存的最大问答设计    | 16 LPDDR4x | 256 GB      |
| **13.5 英寸** | 四核第10代内核 i7-1065G7 | 英特尔虹膜 Plus 图形<br>NVIDIA GeForce GTX 1650。 具有 4GB GDDR5 图形内存的最大问答设计    | 32 LPDDR4x | 512 GB      |
| **13.5 英寸** | 四核第10代内核 i7-1065G7 | 英特尔虹膜 Plus 图形<br>NVIDIA GeForce GTX 1650。 具有 4GB GDDR5 图形内存的最大问答设计    | 32 LPDDR4x | 1 TB        |
| **15英寸**   | 四核第10代内核 i7-1065G7 | 英特尔虹膜 Plus 图形<br>NVIDIA GeForce GTX 1660 Ti。 具有 6GB GDDR6 图形内存的最大问答设计 | 16 LPDDR4x | 256 GB      |
| **15英寸**   | 四核第10代内核 i7-1065G7 | 英特尔虹膜 Plus 图形<br>NVIDIA GeForce GTX 1660 Ti。 具有 6GB GDDR6 图形内存的最大问答设计 | 32 LPDDR4x | 512 GB      |
| **15英寸**   | 四核第10代内核 i7-1065G7 | 英特尔虹膜 Plus 图形<br>NVIDIA GeForce GTX 1660 Ti。 具有 6GB GDDR6 图形内存的最大问答设计 | 32 LPDDR4x | 1 TB        |
| **15英寸**   | 四核第10代内核 i7-1065G7 | 英特尔虹膜 Plus 图形<br>NVIDIA GeForce GTX 1660 Ti。 具有 6GB GDDR6 图形内存的最大问答设计 | 32 LPDDR4x | 2 TB        |
| **15英寸**   | 四核第10代内核 i7-1065G7 | 英特尔虹膜 Plus 图形<br>NVIDIA Quadro RTX 3000。 具有 6GB GDDR6 图形内存的最大问答设计     | 32 LPDDR4x | 512 GB      |
| **15英寸**   | 四核第10代内核 i7-1065G7 | 英特尔虹膜 Plus 图形<br>NVIDIA Quadro RTX 3000。 具有 6GB GDDR6 图形内存的最大问答设计     | 32 LPDDR4x | 1 TB        |

> [!NOTE]
> 2TB SSD 仅适用于美国： Surface Book 3 15 "NVIDIA GTX 1660Ti

## 摘要

为性能而打造，Surface Book 3 包含针对特定工作负载和使用要求进行了优化的不同 GPU 配置。 集成的 Intel 虹膜图形 GPU 充当入门级核心 i5 设备上的唯一 GPU，另存为所有其他型号的辅助 GPU。 GeForce GTX 1650 具有核心流多处理器的主要升级功能，可更高效地运行复杂的图形。 更快的 GeForce GTX 1660 Ti 提供了 Surface Book 3，增加了性能，让消费者、玩家、实时 streamers 和创造性的专业人士更能更好地提高性能。 Quadro RTX 3000 为专业用户解锁几项关键功能： ray 跟踪呈现和 AI 加速，以及高级图形和计算性能。


## 了解详细信息

- [Surface Book 3 Quadro RTX 3000 技术概述](surface-book-quadro.md)
- [商用 Surface](https://www.microsoft.com/surface/business)

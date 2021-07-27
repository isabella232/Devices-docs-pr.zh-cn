---
title: Surface Book 3 Quadro RTX 3000 技术概述
description: 本文介绍了 Nvidia Quadro RTX 3000 在选择 Surface Book 3 for Business 15 英寸模型中启用的高级功能，并包含有关 ISV 测试的应用程序的信息。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/05/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 3d0eb4460e66bdd94b38d1139b877032e6e60eee
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676426"
---
# <a name="surface-book-3-quadro-rtx-3000-tech-overview"></a>Surface Book 3 Quadro RTX 3000 技术概述

Surface Book 3 商业版（由 NVIDIA® Quadro RTX™ GPU 支持）专为需要实时呈现、AI 加速、高级图形和便携外形设备中的计算性能的专业人员构建。 Quadro RTX 3000 从根本上改变了使用新 Surface Book 3 可以执行哪些工作：

- **光线跟踪** - 使用 30 RT 核心（用于硬件加速光线跟踪）比以往更快地生成令人惊叹的呈现、设计和动画。
- **人工智能** - 删除 GPU 加速 AI 的 240 张核心的冗余繁琐任务和计算密集型工作。
- **高级图形和计算** 技术 - 使用 1，920 个 CUDA 核心和 6GB 的 GDDR6 内存，在计算工作负载中实现最大负担的图形和计算工作负载，体验出色的速度和交互性。

## <a name="enterprise-grade-solution"></a>Enterprise级解决方案

Quadro RTX 3000 对商业客户来说非常重要，它提供了一个完全专业级别的解决方案，它将加速光线跟踪和深度学习功能与集成的企业级管理和支持解决方案相结合。 Quadro 驱动程序通过领先的 ISV 针对 100 多个专业应用程序进行测试和认证，提供另一层质量保证，以验证稳定性、可靠性和性能。
 
Quadro 包括用于远程管理 3 Surface Book Quadro RTX 3000 的专用企业工具。 IT 管理员可以远程配置图形系统、保存/还原配置、持续监视图形系统以及执行远程故障排除（如有必要）。 这些功能以及部署工具有助于最大化正常运行时间并最大程度减少 IT 支持要求。
 
NVIDIA 为 Enterprise (ODE) 开发和维护 Quadro 最优驱动程序，这些驱动程序经过调整、测试和验证，可提供企业级稳定性、可靠性、可用性以及扩展产品可用性支持。 每个驱动程序版本都涉及 2，000 多个人天测试专业应用程序测试套件和测试用例，以及 WHQL 认证。 将持续监视安全威胁，并发布定期安全更新，以抵御新发现的漏洞。 此外，Quadro 驱动程序在通过 Windows Update 发布之前，由 Surface 工程部门进行一层额外的测试。
 

## <a name="built-for-compute-intensive-workloads"></a>针对计算密集型工作负载构建

3 Surface Book Quadro RTX 3000 提供任何 Surface 笔记本电脑的最佳图形性能，使高级专业人员可以随时随地工作。
 
- **创意专业人员，如设计人员和动画员。** Quadro RTX 通过 Turing 优化的光线跟踪 API（如 NVIDIA OptiX、Microsoft DXR 和 Vulkan）实现实时电影质量渲染。
- **架构师和工程师使用大型、复杂的计算机辅助设计 (CAD) 模型和程序集。** RTX 平台具有新的 NGX SDK，以将强大的 AI 增强功能注入可视化应用程序中。 这通过智能操作映像、自动执行重复任务以及优化计算密集型进程来释放时间和资源。
- **制造、媒体与娱乐、医疗和其他行业的软件开发人员。** Quadro RTX 通过行业领先的软件 SDK 和 API 通过光线跟踪、深度学习和光栅化功能加快应用程序开发。
- **使用 Tensor Cores 和 CUDA 核心来加速计算密集型任务和其他深入学习操作的数据。** 通过使用传感器、增强的连接性和深度学习，研究人员和开发人员可以针对从自治车辆到科学研究等所有内容启用 AI 应用程序。

 
**表 1. Quadro RTX 3000 性能功能**

|  组件                                        |  描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RT 内核                                            | 专用基于硬件的光线跟踪技术允许 GPU 使用物理上准确的阴影、反射和光线渲染照片质量、光真对象和环境。  实时光线跟踪引擎与 NVIDIA OptiX、Microsoft DXR 和 Vulkan API 一起工作，可提供远超过使用传统呈现技术可能实现的真实级别。 RT 内核使用通过像素 (的光线转换 (BVH) 遍历和光线转换函数。                                     |
| 增强的张量核心                               | 专为深度学习矩阵算术构建的混合精度核心可提供与上一代相比的 8 倍 TFLOPS 培训。  Quadro RTX 3000 利用 240 个 Tensor Core;每个 Tensor Core 每时钟执行 64 个浮点融合相乘 (FMA) 操作，每个流式多处理器 (SM) 每个时钟总共执行 1，024 个单个浮点运算。 除了支持 FP16/FP32 矩阵操作外，新 Tensor Cores 还添加了 INT8 (2，048 整数运算（每个时钟) 和实验 INT4 和 INT1 (二进制) 精度模式）。 |
| Turing optimized software                           | 深度学习框架（如 Microsoft Cognitive Toolkit (CNTK) 、Caffe2、MXNet、TensorFlow 和其他框架）可显著加快培训时间，提高多节点培训性能。 CUDNN、cuBLAS 和 TensorRT 等 GPU 加速库为深入学习推断和 HPC High-Performance计算 (提供了) 性能。                                                                                                                                                                                           |
| NVIDIA CUDA 并行计算平台             | 本机执行标准编程语言（如 C/C++ 和 Fortran）以及 API（如 OpenCL、OpenACC 和 Direct Compute）以加速光线跟踪、视频和图像处理以及计算流动态等技术。                                                                                                                                                                                                                                                                                                                                        |
| 高级流式处理多处理器 (SM) 体系结构 | 组合的共享内存和 L1 缓存可显著提高性能，同时简化编程并减少实现最佳应用程序性能所需的调整。                                                                                                                                                                                                                                                                                                                                                                                                |
| 高性能 GDDR6 内存             | Quadro RTX 3000 具有 6GB 帧缓冲区，使其成为处理大型数据集和延迟敏感应用程序的理想平台。                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 单指令、多线程 (SIMT)           | 新的独立线程调度功能可在小型作业之间共享资源，从而在并行线程之间实现更精细的同步和协作。                                                                                                                                                                                                                                                                                                                                                                                                             |
| 混合精度计算                           | 利用 16 位浮点精度计算，可以培训和部署更大的神经网络。 借助独立的并行整数和浮点数据路径，Turing SM 可以更高效地处理工作负载，同时使用计算和寻址计算。                                                                                                                                                                                                                                                                                          |
| 动态负载平衡                              | 根据需要为图形和计算任务提供 GPU 资源的动态分配功能，以最大化资源利用率。                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 计算抢占                                  | 指令级别的抢占可以更精细地控制计算任务，以防止长时间运行的应用程序占用系统资源或超时。                                                                                                                                                                                                                                                                                                                                                                                            |
| H.264、H.265 和 HEVC 编码/解码引擎         | 通过两个专用 H.264 和 HEVC 编码引擎以及独立于 3D/compute 管道的专用解码引擎，使转换代码、视频编辑和其他编码应用程序的速度比实时性能更快。                                                                                                                                                                                                                                                                                                                                        |
| NVIDIA GPU 提升 4.0                                |  自动最大化应用程序性能，而不会超出 GPU 的电源和热信封。  允许应用程序在降低至辅助温度设置基准时钟之前，在较高的温度阈值下保持更高的提高时钟状态。                                                                                                                                                                                                                                                                                               |

 **表 2.  Quadro RTX 技术规范**

|  组件                                               |  描述  |
| ---------------------------------------------------------- | --------------- |
| NVIDIA CUDA 处理内核                               | 1,920           |
| NVIDIA RT 核心                                            | 30              |
| Tensor Cores                                               | 240             |
| GPU 内存                                                 | 6 GB            |
| 内存带宽                                           | 288 Gbps        |
| 内存类型                                                | GDDR6           |
| 内存接口                                           | 192 位         |
| TGP 最大电源消耗                                  | 65W             |
| 显示端口                                               | 1.4             |
| OpenGL                                                     | 4.6             |
| 着色器模型                                               | 5.1             |
| DirectX                                                    | 12.1            |
| PCIe 生成                                            | 3               |
| TFLOPS、峰值 (单精度浮点)  | 5.4             |
| TOPS、 (峰值的张量)                             | 42.9            |
| NVIDIA FXAA/TX AA 抗锯性                             | 是             |
| 用于视频的 GPU 直接                                       | 是             |
| Vulkan 支持                                             | 是             |
| NVIDIA 3D 视觉Pro                                       | 是             |
| NVIDIA Optimus                                             | 是             |

 
## <a name="isv-testing--app-acceleration"></a>ISV 测试&应用加速

如表 3 所示，Surface Book 3 与 Quadro RTX 3000 一起经领先 ISV 测试和批准，可显著加快跨专业应用程序的加速速度。 SPECview perf 13 基准测试结果将 Surface Book 3 15 英寸与 NVIDIA Quadro RTX 3000 与使用 NVIDIA GeForce GTX 1060 设备的 Surface Book 2 15 英寸进行比较。

**表 3. ISV 测试& Quadro RTX 3000 Surface Book 3 上的应用加速**

|  应用                                              |  描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Adobe Dimension**                                 | **Adobe-tested and approved for Surface Book 3 with Quadro RTX 3000**<br><br>- RTX 加速的光线跟踪为 2D 艺术家和设计人员提供具有照片效果的 3D 呈现。                                                                                                                                                                                                                                                                                                             |
| **Adobe Illustrator**                               | - 使用 GPU 加速画布更快地平移和缩放，这使图形设计人员和演示者可以流畅和交互地平移和缩放复杂的矢量图形。                                                                                                                                                                                                                                                                                             |
| **Adobe Lightroom**                                 | **Adobe-tested and approved for Surface Book 3 with Quadro RTX 3000**<br><br>- 使用 GPU 加速视口更快地编辑高 res 图像，从而对更大的 3D 场景进行建模，并限制更复杂的动画。<br><br>- GPU 加速图像处理可以显著加快响应速度的调整，尤其是在 4K 或更高分辨率的显示器上。<br><br>- GPU 加速 AI 支持"增强详细信息"，用于优化 RAW 图像的精细颜色细节。 |
| **Adobe Photoshop**                                 | **Adobe-tested and approved for Surface Book 3 with Quadro RTX 3000**<br><br>- CUDA 核心加速通过 30+ GPU 加速功能（如模糊库、化化、智能锐化以及透视纹理）实现更快的编辑速度，使设计师和设计人员能够流畅而快速地修改图像。                                                                                                                                                                              |
| **Adobe**<br>**顶级Pro**                       | **Adobe-tested and approved for Surface Book 3 with Quadro RTX 3000**<br><br>- 使用 GPU 加速效果与 CPU 显著加快编辑和呈现视频的速度。<br><br>- 使用 NVIDIA CUDA 技术实现实时视频编辑和更快最终帧呈现的 GPU 加速效果。<br><br>- 用于智能地将横向视频转换为动态跟踪纵向或方形视频的 GPU 加速 AI 自动重新帧功能。                                           |
| **Adobe一体计划**                       | - 轻松创建和混合材料，采用 RTX 加速 AI。                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Adobe 管理刷**                         | **Adobe-tested and approved for Surface Book 3 with Quadro RTX 3000**<br><br>- 画图材料复制到 3d 模型，采用 RTX 加速立式以及 Iray RTX 呈现，为交互式和批处理呈现工作流生成照片图像。                                                                                                                                                                                                                            |
| **Adobe Substance Designer**                        | - 创作具有 RTX 加速加速系统的程序材料。<br><br>- 使用 NVIDIA Iray 呈现（包括纹理/纹理和位图纹理导出）以与 MDL 兼容的任何 Iray 呈现。<br><br>- DXR 加速光和环境封闭溶解。                                                                                                                                                                                                              |
| **ANSYS**                     | **ANSYS 经测试和批准，适用于 Surface Book 3 和 Quadro RTX 3000**<br><br>- 基于 CUDA 构建的 ANSYS 实时工程模拟工具。                                                                                                                                                                                                                                                                                                                                                                                           |
| **Autodesk**<br>**Revit**                           | **Autodesk-tested and approved for Surface Book 3 with Quadro RTX 3000**<br><br>- GPU 加速视区，实现更流畅、更具交互性的设计体验。<br><br>- 支持第三方 GPU 加速 3D 呈现器，如 V-Ray 和 Enscape。                                                                                                                                                                                                                                        |
| **Autodesk**<br>**AutoCad**                         | **Autodesk-tested and approved for Surface Book 3 with Quadro RTX 3000**<br><br>- 用于快速、交互式 3D 呈现和设计的 GPU 加速视口图形。<br><br>- 使用默认 Arnold 呈现器进行 RTX 加速光线跟踪和 AI 反光。<br><br>- 比 2 Surface Book 15" 快 70% 以上。                                                                                                                                                        |
| **Autodesk**<br>**马来斯**                            | **Autodesk-tested and approved for Surface Book 3 with Quadro RTX 3000**<br><br>- 使用默认 Arnold 呈现器进行 RTX 加速光线跟踪和 AI 反光。<br><br>- OpenGL 视口加速。                                                                                                                                                                                                                                                                                  |
| **为 MicroStation**                            | **通过 Quadro RTX 3000 Surface Book 3 的经测试且批准的第 3 版**                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Dassault 系统**<br>**3D 体验平台** | - CATIA 交互式光线跟踪 (RT) 加速实时呈现。<br><br>- 与 2 Surface Book 15" 相比，Catia 的运行速度快 100% 以上。                                                                                                                                                                                                                                                                                                                                     |
| **Dassault 系统**<br>**Solidworks**             | - Solidworks 交互式光线跟踪 (可视化) RT Core 和 Tensor 核心加速的光线跟踪器;AI 加速青绿色。<br><br>- 运行速度比 2 Surface Book 15" 快 50% 以上。                                                                                                                                                                                                                                                                                             |
| **ImageVis3D**                                      | - 运行速度比 2 Surface Book 15"快 2 倍多。                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Pro**                                     |**使用 Quadro RTX 3000 Surface Book 3 的经测试且批准的 Surface Book 3** <br> <br> 3D 分析和实时可视化工作流的表现优于上一代，并利用 RayTracing 功能实现 Voxel 层可视化                                                                                                                                                                                                                                                                                                                                                                                        |
| **一键快照**                                  | - Solidworks、Creo 和 Rhino 使用的第三方交互式光线跟踪器。 由 RT Cores 加速，OptiX™ AI 加速除光。                                                                                                                                                                                                                                                                                                                                                        |
| **McNeel & Associates**<br>**Rhino 3D**             | **Rhino-tested and approved for Surface Book 3 with Quadro RTX 3000**<br><br>- GPU 加速视区，提供流畅的交互式呈现和设计体验。<br><br>- 支持 GPU 加速 3D 呈现的周期。                                                                                                                                                                                                                                                         |
| **PTC Creo**                                        |**PTC 经过 PTC 测试和批准，适用于 Surface Book 3 和 Quadro RTX 3000**<br><br> - Creo 在 CUDA 上构建 (Creo Simulation Live) 实时模拟工具。<br><br>- 运行速度比 2 Surface Book 15" 快 15%。                                                                                                                                                                                        |
| **SolidEdge 2020**                                        |  **使用 Quadro RTX 3000 Surface Book 3 的经测试并批准的第 3 版**                                                                                                                                                                                 |
| **百分之百 NX**                                      | - 由 RT 核心加速 (Ray Trace Studio) NX 交互式光线跟踪器。<br><br>- 运行速度比 2 Surface Book 15" 快 10 倍。                                                                                                                                                                                                                                                                                                                                    |






## <a name="skus"></a>SKUs

**表 4. Surface Book 3 和 Quadro RTX 3000 SKUs**

|  显示器  |  处理器                      |  GPU                                                                                           |  RAM     |  存储  |
| ----------- | --------------------------------- | ------------------------------------------------------------------------------------------------ | ---------- | ----------- |
| 15 英寸 | 四核第 10 代核心版 i7-1065G7 | Intel Iris™ Plus 图形<br>NVIDIA Quadro RTX 3000。 具有 6GB GDDR6 图形内存的 Max-Q 设计 | 32 LPDDR4x | 512 GB      |
| 15 英寸 | 四核第 10 代核心版 i7-1065G7 | Intel Iris™ Plus 图形<br>NVIDIA Quadro RTX 3000。 具有 6GB GDDR6 图形内存的 Max-Q 设计 | 32 LPDDR4x | 1 TB        |

## <a name="summary"></a>摘要

具有 Quadro RTX 3000 的 Surface Book 3 可提供任何 Surface 笔记本电脑的最佳图形性能，为架构师、工程师、开发人员和数据工作者提供从任何位置高效工作所需的工具：
 
- 跨多个工作流（如设计、动画、视频制作等）的 RTX 加速。
- 移动外形设备中的桌面级性能。
- Enterprise关键项目提供一流的功能、可靠性和支持。

## <a name="learn-more"></a>了解详细信息

- [Surface Book 3 GPU 技术概述](surface-book-GPU-overview.md)
- [商用 Surface](https://www.microsoft.com/surface/business)
- [Microsoft Cognitive Toolkit (CNTK) ](/cognitive-toolkit)

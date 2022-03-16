---
title: Surface Laptop Studio 图形概述
description: 本文重点介绍 Surface Lapto Studio 中的 GPU。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/04/2021
ms.reviewer: brrecord
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: d70ee9f9957ad0981bb967397bbefe6da85a7cf6
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449315"
---
# <a name="surface-laptop-studio-graphics-overview"></a>Surface Laptop Studio 图形概述

Surface Laptop Studio 将完全现代化计算和图形功能集成到了一种新的通用外形设备中。 由四核第 11 代 Intel® Core™ i7 和 NVIDIA® RTX™ A2000 或 NVIDIA® GeForce RTX™ 3050 Ti 领导，Surface Laptop Studio 为架构师、工程师、数据专家和创意专业人员提供了最佳计算能力。
 
GPU 配置是Surface Laptop Studio 模型间的重要区别。 核心 i5 设备外的所有设备都使用离散 NVIDIA RTX GPU，从而实现硬件加速光线跟踪、AI 和视频。 该设计还优化了移动外形因素的能耗效率。 具有 NVIDIA GPU 的模型是 NVIDIA Studio 产品计划的一部分，受益于顶级创意应用中的 RTX 加速、可靠的 NVIDIA Studio 驱动程序，以及有权访问独占 NVIDIA 应用（如 Canvas 或 Broadcast）。 光线跟踪是一种计算密集型技术，可模拟光的物理行为，以在计算机生成的场景中实现更高的真实性。 它同时用于游戏和 3D 呈现。 NVIDIA RTX 还使用 DLSS (深度学习) ，这是一种提高帧速率的 AI 技术。
 
这些高级图形呈现功能有两个主要配置：NVIDIA GeForce RTX 3050 Ti Laptop GPU（适用于消费者或创意专业人员）和 NVIDIA RTX A2000 Laptop GPU（适用于架构师、工程师、创意专业人员以及需要高级图形功能的其他业务专业人员）。
 
## <a name="surface-laptop-studio-gpus"></a>Surface Laptop Studio GPU

本部分介绍跨 Surface Laptop Studio 模型的集成和离散 GPU。

### <a name="intel-iris-xe-graphics"></a>Intel Iris™ Xe 图形

当集成 GPU (iGPU) Surface Laptop Studio 上时，Intel Iris™ Xe Graphics 将用作核心 i5 模型中的单数 GPU。 它支持更丰富的游戏体验，并且为设计人员和创建者提供更高的速度。 借助高级图形功能和 AI 增强体验，Intel Iris Xe 使消费者、娱乐家和在线创意者能够运行最新的生产力软件，如 Adobe Creative Cloud 或在 1080p 中享受游戏作品。 它还将支持的显示器数量从三个增加为总共四个。 现在，你可以将最多三个外部显示器与内部显示器一起使用，或者一次使用四个外部显示器 - 适用于集成的 GPU 和离散 GPU 模型。[[1]](#references)

### <a name="comparing-discrete-gpus"></a>比较离散 GPU

除了许多其他创意任务外，NVIDIA GeForce RTX 30 系列和 RTX 专业 GPU 为游戏、3D 呈现、视频编辑、图形设计和 AI 加速工作流提供了巨大加速。 这要归功于最新的 NVIDIA Ampere 体系结构：

- 第 2 代 RT Core 和 DLSS，在顶部呈现器（包括 Blender 周期、混乱 V-Ray 和 Autodesk Arnold）中提供高达 2 倍的性能提升。
- 加速 AI 功能的第三代 Tensor Cores。 张量核心还将 AI 引入具有 DLSS、AI 去角以及针对选定应用程序的增强编辑等功能的图形。
- 一流的视频编码器 (NVENC) 以及用于光线跟踪运动模糊的新硬件加速（生产呈现中常用的技术）现在最高提升了 5 倍。

### <a name="nvidia-geforce-rtx-3050-ti-laptop-gpu"></a>NVIDIA GeForce RTX 3050 Ti Laptop GPU

GeForce RTX 3050 Ti Laptop GPU 是一款出色的 GPU，适用于玩家和内容创建者。 它由 NVIDIA Studio 驱动程序驱动，用于增强创意者应用中的可靠性和性能。
 
GeForce RTX 3050 Ti 支持：

- 视频编辑和实时流式处理加速，这要归功于专用硬件编码器、增强的 AI 功能以及 Adobe Premiere® Pro、DaVinci Resolve 或 OBS 等应用中的应用加速。
- 图形设计和艺术，在 Adobe Lightroom 或 Photoshop 等应用中具有 AI 加速功能。
- 借助 RTX 和 DLSS 在 Blender 或 Autodesk® Maya 等应用中的加速，超快 3D 呈现。 
- 借助 DLSS 和 NVIDIA Latenc 的超低延迟，具有 RTX 图形和高性能的下一代游戏。

### <a name="nvidia-rtx-a2000-laptop-gpu"></a>NVIDIA RTX A2000 Laptop GPU

NVIDIA RTX A2000 提供专业图形呈现和 AI 功能，用于要求严格的专业工作流，包括制造和产品开发、媒体与娱乐建模、动画和呈现、体系结构、工程和建筑设计。
 
NVIDIA RTX A2000 基于 GeForce RTX 3050 Ti 功能构建，具有以下附加功能：

- Enterprise级可靠性，包括针对针对软件兼容性和稳定性进行调整的专业应用和企业驱动程序的 ISV 认证。
- Enterprise级硬件、驱动程序和支持。
- 用于远程管理的专用 IT 企业工具，有助于最大程度地缩短正常运行时间并最大程度减少 IT 支持要求。
- 使用 Open GL 图形增强对专业应用程序的支持。
 
**表 1. Surface Laptop Studio 上的离散 GPU**

| GPU                                         | NVIDIA GeForce RTX 3050 Ti Laptop GPU | NVIDIA RTX A2000 Laptop GPU |
| ------------------------------------------- | ------------------------------------- | --------------------------- |
| GPU 内存                                  | 4GB GDDR6                             | 4GB GDDR6                   |
| GPU 提升时钟                             | 1035Mhz                               | 1207.5Mhz                   |
| 流式处理多处理器                   | 2x FP32                               | 2x FP32                     |
| NVIDIA CUDA 处理内核                | 2560                                  | 2560                        |
| NVIDIA RT 内核                             | 第 2 代 / 20 号                          | 第 2 代 / 20 号                |
| 张量核心                                | 第三代 / 80 号                          | 第三代 / 80 号                |
| 内存速率                                 | 11 Gbps                               | 11 Gbps                     |
| 内存带宽                            | 192 GB/s                              | 192 GB/s                    |
| 内存接口                            | 128 位                               | 128 位                    |
| 最大图形 ()                   | 50 位                              | 50 位                    |
| DLSS                                        | 是                                   | 是                         |
| 动态提升 2.0                           | 是                                   | 是                         |
| 可调整大小 BAR                               | 是                                   | 是                         |
| NVIDIA Optimus                              | 是                                   | 是                         |
| Nvidia Encoder                              | 第 7 代                               | 第 7 代                     |
| Nvidia 解码器                              | 第五代                               | 第五代                     |
| 张量性能                          | 42.4 TFLOPS，峰值                     | 49.5 TFLOPS，峰值           |
| 单精度浮点性能 | 5.3 TFLOPS，峰值                      | 6.2 TFLOPS，峰值            |
| PCIe 生成                             | 4 (Gen3 配置)                    | 4 (Gen3 配置)          |
| 着色器模型                                | 7.0                                   | 7.0                         |
| Vulkan RT                                   | 1.2                                   | 1.2                         |
| OpenCL                                      | 3.0                                   | 3.0                         |
| OpenGL                                      | 4.6                                   | 4.6                         |
| DirectX                                     | 12 Ultimate                           | 12 Ultimate                 |

 
### <a name="references"></a>参考

1. 受显示连接的限制。 DisplayPort 1.4a over USB-C 允许 4K 显示最多以下配置：1x 4K，120Hz;60Hz 的 2x 4K;1x 4K，60Hz + 2x 4K，30Hz;4x 4K，30Hz。 超过两个显示器的显示配置需要支持显示链接或支持多个显示器的显示适配器。


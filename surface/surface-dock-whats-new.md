---
title: Surface 扩展坞中的新增功能
description: 本文重点介绍下一代 Surface 扩展坞的新增特性和功能。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/2/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 81c224cf6c5232c4cefd4e64889bd2f724d22bac
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271129"
---
# Surface 扩展坞中的新增功能 

Surface 扩展坞 2 是下一代 Surface 扩展坞，允许用户连接外部监视器和多个外围设备，从 Surface 设备获得完全现代化桌面体验。 Surface 扩展坞 2 专为在办公室、灵活工作区或家庭办公时最大程度地提高效率而构建，具有七个端口，包括两个前置 USB-C 端口，具有 15 个快速充电电源（适用于电话和附件）。 

### 完整的设备管理支持

Surface 扩展坞 2 旨在简化 IT 管理，使管理员能够使用 Windows 更新自动执行固件更新，或使用内部软件分发工具集中更新。

- Surface Enterprise Management Mode (SEMM) 使 IT 管理员能够保护 Surface Dock 2 上的端口。 有关详细信息，请参阅使用 [Surface Enterprise 管理模式的安全 Surface 扩展坞 2 端口](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999)。
-  Windows Management Instrumentation (WMI) 支持使 IT 管理员能够跨 Surface Dock 2 设备远程监视和管理最新的固件、策略状态和相关信息。 有关详细信息，请参阅使用[WMI 管理 Surface Dock 2。](surface-dock2-wmi.md)

## 一般系统要求

- Windows 10 版本 1809。 不支持 Windows 7、Windows 8 或非 Surface 主机设备。 Surface 扩展坞 2 适用于以下 Surface 设备：

  - Surface Pro (第五代) 
  - Surface Laptop (第一代) 
  - Surface Pro 6
  - Surface Book 2
  - Surface Laptop 2
  - Surface Go
  - Surface Pro 7
  - Surface Pro X 
  - Surface Laptop 3
  - Surface Book 3
  - Surface Go 2
  - Surface Laptop Go
  - Surface Pro 7+

## Surface 扩展坞 2 组件

![Surface 扩展坞 2 组件](./images/surface-dock2.png)
 
### USB

- 两个前置 USB-C 端口。
- 两个面向后向的 USB-C (第 2 代) 端口。
- 两个后置 USB-A 端口。 

### 视频
    
- 双4K@60hz。 支持以下设备上最多两个显示器：

  - Surface Book 3
  - Surface Go 2
  - Surface Pro 7
  - Surface Pro 7+
  - Surface Pro X
  - Surface Laptop 3

- 双4K@ 4K@30Hz。 支持以下设备上最多两个显示器：

  - Surface Pro 6
  - Surface Pro (第五代) 
  - Surface Laptop 2
  - Surface Laptop (第一代) 
  - Surface Go
  - Surface Book 2。

### 以太网

- 1 GB 以太网端口。 

### 外部电源

- 支持 100V-240V 的 199 个设备。


## 比较 Surface 扩展坞 

**表 1.  Surface 扩展坞和 USB-C 旅行中心**


| 组件                           | Surface 扩展坞                                                | Surface 扩展坞 2                                                                                      | USB-C 旅行中心 |
| ----------------------------------- | ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ---------------- |
| 显示链接                            | 是                                                         | 是                                                                                                 | 否               |
| USB-A                               | 2 个前置 USB 3.1 Gen 1<br>2 个后置 USB 3.1 Gen 1 | 2 个后置 USB 3.2 Gen 2 (7.5W 电源)                                                             | 1 个 USB 3.1 Gen 2  |
| 微型显示端口                   | 2 个后置 (DP1.2)                                        | 无                                                                                                | 无             |
| USB-C                               | 无                                                        | 2 个前置 USB 3.2 Gen 2<br> (15W 电源) <br>2 个后置 USB 3.2 Gen 2 (DP1.4a) <br> (7.5W 电源)  | 1 个 USB 3.2 Gen 2  |
| 3.5 mm 音频输入/输出                 | 是                                                         | 是                                                                                                 | 是              |
| 以太网                            | 是，1 GB                                              | 是 1 GB                                                                                       | 是，1 GB   |
| DC 电源输入                         | 是                                                         | 是                                                                                                 |                  |
| Kensington 锁定                     | 是                                                         | 是                                                                                                 |                  |
| 浮出电缆长度               | 65cm                                                        | 80cm                                                                                                | 20cm             |
| 显示链接主机电源                 | 60W                                                         | 120W                                                                                                | 不适用              |
| USB 负载电源                      | 30W                                                         | 60W                                                                                                 |                  |
| USB 比特率                        | 5 Gbps                                                      | 10 Gbps                                                                                             | 10 Gbps          |
| 监视支持                     | 2 x 4k @30fps，或<br>1 x 4k @ 60fps                         | 2 x 4K @ 60fps                                                                                      | 1 x 4K @ 60fps   |
| LAN 上从连接待机 <sup> 1 唤醒</sup> | 是                                                         | 是                                                                                                 |                  |
| 从 S4/S5 睡眠模式在 LAN 上唤醒  | 否                                                          | 是                                                                                                 |          是        |
| 网络 PXE 启动                    | 是                                                         | 是                                                                                                 |        是          |
| SEMM 主机访问控制            | 否                                                          | 是                                                                                                 | 否               |
| SEMM 端口访问控制 <sup> 2</sup>          | 否                                                          | 是                                                                                                 | 否               |
| 服务支持                   | MSI                                                         | Windows 更新或 MSI                                                                               |                  |

 



1. *设备必须通过 Surface Enterprise Management Mode (SEMM) 或设备固件控制接口 (DFCI) 配置为在 LAN 上唤醒，以从休眠或Power-Off状态。 Surface Pro 7+、Surface Pro 7、Surface Laptop 3、Surface Pro X、Surface Book 3 和 Surface Go 2 支持从休眠或休眠状态唤醒。 Power-Off  某些功能所需的软件许可证。 单独出售。*

2. *某些功能所需的软件许可证。 单独出售。*

## 简化的设备管理

Surface 通过 Windows 更新发布了简化的管理功能，使 IT 管理员能够利用以下企业级功能：

- **无接触更新**。 使用 Windows 更新或 Microsoft Endpoint Configuration Manager、以前 (System Center Configuration Manager - SCCM) 或其他 MSI 部署工具，以静默方式自动更新扩展坞。 
- **从网络唤醒**。 管理和访问公司设备，而无需依赖用户来保持其设备的电源。 即使固定设备进入睡眠、休眠或断电模式，团队也可使用 Endpoint Configuration Manager 或其他企业管理工具从网络唤醒以用于服务和管理。
- **集中式 IT 控制**。 通过打开和关闭端口来控制谁可以连接到 Surface Dock 2。 限制哪些主机设备可以与 Surface 扩展坞 2 一起使用。 限制对单个用户的扩展坞访问或配置扩展坞，以便只有团队中或整个公司中的特定用户访问它们。

## 后续步骤

- [使用 Surface Enterprise 管理模式保护 Surface 扩展坞 2 端口](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999)
- [Surface 企业管理模式](surface-enterprise-management-mode.md)
- [Surface 设备电源设置的最佳实践](maintain-optimal-power-settings-on-Surface-devices.md)

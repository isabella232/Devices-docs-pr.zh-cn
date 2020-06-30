---
title: Surface Dock 2 中的新增功能
description: 本文重点介绍了下一代 Surface Dock 的新增功能和功能。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/25/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 92838599a9d05dbe75f1caad948b97c9cb75bcac
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830684"
---
# Surface Dock 2 中的新增功能

Surface Dock 2，下一代 Surface Dock，允许用户连接外部监视器和多个外围设备，以便从 Surface 设备获取完全现代化的桌面体验。 构建为最大程度地提高 office 的效率，在灵活的工作区，或在家里，Surface Dock 2 有七个端口，包括两个前置 USB 端口，其中15瓦的电话和附件的充电功率为15瓦。 

### 完整设备管理支持

Surface Dock 2 旨在简化 IT 管理，使管理员能够使用 Windows 更新自动执行固件更新或使用内部软件分发工具集中更新。

- Surface Enterprise 管理模式（SEMM）允许 IT 管理员保护 Surface Dock 2 上的端口。 有关详细信息，请参阅[具有 Surface Enterprise 管理模式的安全 Surface Dock 2 端口](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999)。
-  Windows Management Instrumentation （WMI）支持允许 IT 管理员远程监控和管理跨 Surface Dock 2 设备的最新固件、策略状态和相关数据。 有关详细信息，请参阅[用 WMI 管理 Surface Dock 2](surface-dock2-wmi.md)。

## 常规系统要求

- Windows 10 版本1809。 不支持 Windows 7、Windows 8 或非 Surface 主机设备。 Surface Dock 2 与以下 Surface 设备配合使用：

  - Surface Pro （第五代）
  - 具有 LTE 高级版的 Surface Pro （第5代）
  - Surface 笔记本电脑（第1代）
  - Surface Pro 6
  - Surface Book 2
  - Surface Laptop 2
  - Surface Go
  - 带有 LTE Advanced 的 Surface Go 
  - Surface Pro 7
  - Surface 笔记本电脑3
  - Surface Book 3
  - Surface Go 2
  - 带有 LTE 高级的 Surface Go 2


## Surface Dock 2 组件

![Surface Dock 2 组件](./images/surface-dock2.png)
 
### USB

- 两个正面朝上的 USB 端口。
- 两个后部的 USB-C （第2代）端口。
- 两个背面的 USB-A 端口。 

### 视频
    
- 双重4K@60hz。 在以下设备上最多支持两个显示：

  - Surface Book 3
  - Surface Go 2
  - 带有 LTE 高级的 Surface Go 2
  - Surface Pro 7
  - Surface Pro X
  - Surface 笔记本电脑3

- 双 4K@ 4K@30Hz。 在以下设备上最多支持两个显示：

  - Surface Pro 6
  - Surface Pro （第五代）
  - 具有 LTE 高级版的 Surface Pro （第5代）
  - Surface Laptop 2
  - Surface 笔记本电脑（第1代）
  - Surface Go
  - Surface Book 2。

### 以太网

- 1个千兆以太网端口。 

### 外部电源

- 199瓦特，支持100V。


## 比较 Surface Dock 2 

### 表 1.  Surface Dock 2 技术规格比较

|组件|Surface 扩展坞|Surface Dock 2|
|---|---|---|
|Surflink|是|是|
|USB-A|2正面朝 USB 3.1 第1代<br>2背面的 USB 3.1 第1代|2个后部的 USB 3.2 第2代（打开 7.5 W）|
|微型显示端口|2后面（DP 1.2）|无|
|USB-C|无|2正面朝 USB 3.2 第2代<br>（15W power）<br>2背面的 USB 3.2 第2代（DP 1.4 a）<br>（7.5 w w）|
|3.5 毫米音频 in/out|是|是|
|以太网|是，1千兆位|是1千兆位|
|直流电源|是|是|
|Kensington 锁|是|是|
|Surflink 电缆长度|65cm|80cm|
|Surflink 主机电源|60W|120W|
|USB 加载电源|30W|60W|
|USB 比特率|5 Gbps|10 Gbps|
|监视器支持|2 x 4k @30fps 或<br>1 x 4k @ 60fps|2 x 4K @ 60fps|
|已连接备用版1的 LAN 唤醒 <sup></sup>|是|是|
|来自 S4/S5 睡眠模式的 LAN 唤醒|否|是|
|网络 PXE 启动|是|是|
|SEMM 主机访问控制|否|是
|SEMM 端口访问控制 <sup> 2</sup>|否|是|
|服务支持|MSI|Windows 更新或 MSI|
||||

1. *必须将设备配置为通过 Surface Enterprise 管理模式（SEMM）或设备固件控制接口（DFCI）在 LAN 上唤醒，才能从休眠或断电状态唤醒。 在 Surface Pro 7、Surface 笔记本电脑3、Surface Pro X、Surface Book 3 和 Surface Go 2 上支持从休眠或关机中唤醒。  某些功能所需的软件许可证。 单独出售。*

2. *某些功能所需的软件许可证。 单独出售。*

## 简化的设备管理

Surface 通过 Windows 更新发布了简化的管理功能，使 IT 管理员能够利用以下企业级功能：

- **Frictionless 更新**。 通过 Windows 更新或 Microsoft 终结点配置管理器（以前称为 System Center Configuration Manager-SCCM）或其他 MSI 部署工具，自动自动更新你的停靠。 
- **从网络唤醒**。 管理和访问公司设备，而无需依靠用户让设备保持打开状态。 即使固定设备处于睡眠、休眠或关机模式，你的团队也可以使用终结点配置管理器或其他企业管理工具，从网络进行服务和管理。
- **集中式 IT 控制**。 通过打开和关闭端口控制哪些人可以连接到 Surface Dock 2。 限制可以与 Surface Dock 2 配合使用的主机设备。 限制对单个用户的停靠访问权限或配置停靠，以便仅由团队中的特定用户或整个公司访问。

## 后续步骤

- [安全 Surface Dock 2 个具有 Surface Enterprise 管理模式的端口](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999)
- [Surface 企业管理模式](surface-enterprise-management-mode.md)
- [Surface 设备电源设置的最佳实践](maintain-optimal-power-settings-on-Surface-devices.md)

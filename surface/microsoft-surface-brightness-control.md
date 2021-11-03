---
title: Surface 亮度控制
description: 本主题介绍如何使用 Surface Brightness Control 应用在销售点和展台方案中管理显示亮度。
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 518db8ad0070e5e7355ef57b96057c6f4ae45137
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154067"
---
# <a name="surface-brightness-control"></a>Surface 亮度控制

在销售点或其他"始终启用"展台方案中部署 Surface 设备时，可以使用新的 Surface 亮度控制应用优化电源管理。 Surface 亮度控制旨在帮助减少热负载并降低已部署的 Surface 设备的总足迹。 该工具在不使用时自动调暗屏幕，并包括以下配置选项：

- 在变暗屏幕之前处于不活动状态的时间。
- 变暗时亮度级别。
- 使用时的最大亮度级别。

从适用于 IT 的 [Surface Tools 下载它](https://www.microsoft.com/download/details.aspx?id=46703)。 Select the file **Surface_Brightness_Control_v1.16.137.0.msi** in the available list.

## <a name="supported-devices"></a>支持的设备

- Surface Pro 3 及更高版本
- Surface ProX (所有代) 
- Surface 3
- Surface Book (所有代) 
- Surface LaptopStudio
- Surface Studio (所有代) 
- Surface Laptop (所有代) 
- Surface Laptop转到
- Surface Go (所有代) 


## <a name="run-surface-brightness-control"></a>运行 Surface 亮度控制

- 在 **Surface_Brightness_Control_v1.16.137.0.msi** 安装屏幕，Surface 亮度控制将立即开始工作。

## <a name="configure-surface-brightness-control"></a>配置 Surface 亮度控制

 可以通过注册表中调整Windows值。 有关使用注册表Windows，请参阅[注册表文档](/windows/desktop/sysinfo/registry)。

1. 从命令提示符运行 regedit 以打开Windows注册表编辑器。
2. 导航到 Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Surface\Surface Brightness Control。
3. 调整注册表项值，如下表所述。

> [!TIP]
> 如果你运行的是较旧版本的 Surface Brightness 控件，请导航到：Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Surface\Surface Brightness Control\

| 注册表设置 | 数据| 描述  
|-----------|------------|---------------
| 亮度控制已启用  |  默认值：01  <br> 选项：01，00 <br> 类型：REG_BINARY |  此设置允许你打开或关闭 Surface Brightness Control。 若要禁用 Surface 亮度控制，请将其值设置为 00。 如果未配置此设置，Surface 亮度控件将打开。 |
| 启用电源的亮度控制| 默认值：01 <br> 选项：01、00 <br> 类型：REG_BINARY | 此设置允许你在设备直接连接到电源时关闭 Surface 亮度控制。 若要在接通电源时禁用 Surface 亮度控制，请将其值设置为 00。 如果未配置此设置，Surface 亮度控件将打开。 |
| 灰显亮度   | 默认值：20  <br>选项：屏幕亮度的 0- 100% 范围 <br> 数据类型：正整数 <br> 类型：REG_DWORD | 此设置允许你在非活动期间管理亮度范围。 如果未配置此设置，则 30 秒不活动后，亮度级别将下降为完全亮度的 20%。 |
完全亮度   | 默认值：100  <br>选项：屏幕亮度的 0- 100% 范围 <br> 数据类型：正整数 <br> 类型：REG_DWORD  | 此设置允许你管理设备的最大亮度范围。 如果未配置此设置，最大亮度范围为 100%。|  
| 不活动超时| 默认值：30 秒 <br>选项：任何数值  <br>数据类型：Integer  <br> 类型：REG_DWORD | 此设置允许你在使设备变暗之前管理不活动期。 如果未配置此设置，则不活动超时为 30 秒。|
| 已启用遥测 | 默认值：01 <br>选项：01，00 <br> 类型：REG_BINARY  | 此设置允许你管理应用使用情况信息的共享，以改进软件和提供更好的用户体验。 若要禁用遥测，请将其值设置为 00。 如果未配置此设置，遥测信息将按照 Microsoft 隐私声明与 [Microsoft 共享](https://privacy.microsoft.com/privacystatement)。 |

## <a name="changes-and-updates"></a>更改和更新

### <a name="version-116137br"></a>版本 1.16.137<br>

*发布日期：2019 年 10 月 22 日*<br>
此版本的 Surface Brightness Control 增加了对以下内容的支持：-Recompiled for x86，增加了对 Surface Pro 7、Surface Pro X 和 Surface Laptop 3 的支持。

### <a name="version-1122390"></a>版本 1.12.239.0

*发布日期：2019 年 4 月 26 日*<br>
此版本的 Surface Brightness Control 增加了对以下内容的支持：

- 触摸延迟修复。

## <a name="related-topics"></a>相关主题

- [电池限制设置](battery-limit.md)

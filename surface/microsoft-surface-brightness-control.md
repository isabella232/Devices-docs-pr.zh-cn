---
title: Surface 亮度控制
description: 本主题介绍了如何使用 Surface 亮度控件应用在销售点和展台方案中管理显示器亮度。
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
ms.openlocfilehash: 197ed9fe1abc880779ad6bb0f85d2970086395f6
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831631"
---
# Surface 亮度控制

当在销售点或其他 "永不开" 的展台方案中部署 Surface 设备时，可以使用新的 Surface 亮度控制应用优化电源管理。

可通过适用于[它的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)下载。
Surface 亮度控件旨在帮助减少热量负载，降低部署 Surface 设备的整体碳足迹。
如果您计划仅从下载页面获取此工具，请在 "可用" 列表中选择文件**Surface_Brightness_Control_v1.16.137.0.msi** 。
此工具在未使用时将自动调暗屏幕，并且包括以下配置选项：

- 屏幕变暗之前的非活动期。

- 变暗时的亮度级别。

- 使用时的最大亮度级别。

**运行 Surface 亮度控件：**

- 在目标设备上安装 surfacebrightnesscontrol.msi，表面亮度控件将立即开始工作。

##  <a name="configuring-surface-brightness-control"></a>配置 Surface 亮度控件

你可以通过 Windows 注册表调整默认值。 有关使用 Windows 注册表的详细信息，请参阅[注册表文档](https://docs.microsoft.com/windows/desktop/sysinfo/registry)。

1.  从命令提示符处运行 regedit，打开 Windows 注册表编辑器。
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\WOW6432Node\Microsoft\Surface\Surface 亮度控件 \ 
    
    如果您运行的是较旧版本的 Surface 亮度控件，请运行以下命令：
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\Microsoft\Surface\Surface 亮度控件 \


| 注册表设置 | 数据| 描述  
|-----------|------------|---------------
| 已启用亮度控制  |  默认值：01  <br> 选项：01，00 <br> 类型： REG_BINARY |  此设置允许你打开或关闭 Surface 亮度控件。 若要禁用 Surface 亮度控件，请将值设置为00。 如果未配置此设置，则 "表面亮度" 控件打开。 |
| 启用电源上的亮度控制| 默认值：01 <br> 选项：01，00 <br> 类型： REG_BINARY | 此设置允许你在设备直接连接到电源时关闭 Surface 亮度控制。 若要在接通电源时禁用 Surface 亮度控件，请将值设置为00。 如果未配置此设置，则 "表面亮度" 控件打开。 |
| 亮度变暗   | 默认值：20  <br>选项：0-100% 的屏幕亮度范围 <br> 数据类型：正整数 <br> 类型： REG_DWORD | 此设置允许你在不活动期间管理亮度范围。 如果未配置此设置，则亮度级别将下降到30秒的非活动状态后的全部亮度的20%。 |
完全亮度   | 默认：100  <br>选项：0-100% 的屏幕亮度范围 <br> 数据类型：正整数 <br> 类型： REG_DWORD  | 此设置允许你管理设备的最大亮度范围。 如果未配置此设置，则最大亮度范围为100%。|  
| 不活动超时| 默认：30秒 <br>选项：任何数字值  <br>数据类型：整型  <br> 类型： REG_DWORD | 此设置允许你在变暗设备之前管理处于非活动状态的时间段。 如果未配置此设置，则不活动超时为30秒。|
| 已启用遥测 | 默认值：01 <br>选项：01，00 <br> 类型： REG_BINARY  | 此设置允许你管理应用使用情况信息的共享以改进软件，并提供更好的用户体验。 若要禁用遥测，请将值设置为00。 如果未配置此设置，则会根据[Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)与 microsoft 共享遥测信息。 |

##  <a name="changes-and-updates"></a>更改和更新

###  <a name="version-1.16.137"></a>版本1.16.137<br>
*发布日期：2019年10月22日*<br>
此版本的 Surface 亮度控件增加了对以下各项的支持：-为 x86 重新编译，添加了对 Surface Pro 7、Surface Pro X 和 Surface 笔记本3的支持。 

###  <a name="version-1.12.239.0"></a>版本1.12.239。0
*发布日期：2019年4月26日*<br>
此版本的 Surface 亮度控件增加了对以下各项的支持：
- 触摸延迟修复。


##  <a name="related-topics"></a>相关主题

- [电池限制设置](battery-limit.md)

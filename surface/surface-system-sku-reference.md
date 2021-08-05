---
title: Surface 系统 SKU 参考
description: 请参阅所有 Surface 设备的系统模型和系统 SKU 名称参考。
keywords: uefi， 配置， 固件， 安全， semm， Autopilot
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 08/02/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 71ded9892e9dde8de1976a89214ea946e1bd1da4
ms.sourcegitcommit: 657d0d73a51f0dd35ad60740ed523164a55d2e04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2021
ms.locfileid: "11720916"
---
# <a name="surface-system-sku-reference"></a>Surface 系统 SKU 参考

本文档提供了可用于各种 IT 任务的参考，例如向 Windows Autopilot 注册 Surface 设备，或者使用 PowerShell 或 WMI 验证特定设备的机器状态。

系统模型和系统 SKU 是存储在 Surface 设备的 UEFI 层中的系统管理 BIOS (SMBIOS) 表中的变量。 每当需要区分使用相同系统模型名称的设备（如使用 LTE Advanced 的 Surface Pro 和 Surface Pro）时，请使用系统 SKU 名称。

| 设备   | 系统模型 | 系统 SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| 北美 Surface 3 LTE                                  | Surface 3        | Surface_3_NAG                    |
| 北美之外的 Surface 3 LTE 和日本 Y！mobile | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| 带有 LTE Advanced 的 Surface Pro                                 | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13"                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE 商业 | Surface Go | Surface_Go_1825_Commercial |
| Surface Go 消费者                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go 商业                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 消费者                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 商业版                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 消费者                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 商业                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7+                                               | Surface Pro 7+ | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+ | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface ProX（带 SQ2 处理器）                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13" Intel | Surface Laptop 3 | Surface_Laptop_3_1867：1868 |
| Surface Laptop 3 15" Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15" AMD   | Surface Laptop 3 | Surface_Laptop_3_1873      |
| Surface Laptop转到  | Surface Laptop转到 | Surface_Laptop_Go_1943      |
| Surface Laptop 4 13" Intel | Surface Laptop 4 | Surface_Laptop_4_1950：1951 |
| Surface Laptop 4 15" Intel | Surface Laptop 4 | Surface_Laptop_4_1978：1979     |
| Surface Laptop 4 15" AMD   | Surface Laptop 4 | Surface_Laptop_4_1952：1953     |
| Surface Laptop 4 13" AMD   | Surface Laptop 4 | Surface_Laptop_4_1958：1959    |
| Surface Hub 2S 50"  | Surface Hub 2S | Surface Hub 2S   |
| Surface Hub 2S 85"  | Surface Hub 2S | Surface Hub 2S 85   |
| Surface Studio | Surface Studio | Surface_Studio   |
| Surface Studio 2 | Surface Studio 2 | Surface_Studio_2_1707_Commercial   |
|

## <a name="examples"></a>示例

**使用 PowerShell 检索 SKU**  
使用以下 PowerShell 命令拉取系统 SKU 信息：

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**使用方法检索 SKU 系统信息**  
还可以在"配置"中查找设备的系统 SKU**和**系统信息。 为此，请执行下列步骤：

1. 选择 **"开始**"，然后在搜索**框中键入 MSInfo32。**  
1. 选择 **"系统信息"。**

**在任务序列 WMI 条件中使用 SKU**  
可以将 Microsoft Deployment Toolkit (MDT) 或 Microsoft Endpoint Configuration Manager 中的系统 SKU 信息用作任务序列 WMI 条件的一部分。

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ```

## <a name="learn-more"></a>了解详细信息

- [WMI 参考](/windows/win32/wmisdk/wmi-reference)
- [适用于 Windows Autopilot 的 Surface 注册支持](surface-autopilot-registration-support.md)

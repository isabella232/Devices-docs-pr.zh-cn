---
title: 'Surface (的系统 SKU 参考) '
description: 请参阅系统模型和系统 SKU 名称的引用。
keywords: uefi， 配置， 固件， 安全， semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 2140faf346229842bffc4f9348041f4667b94686
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271366"
---
# 系统 SKU 参考

本文档提供系统模型和系统 SKU 名称的参考，您可以使用 PowerShell 或 WMI 快速确定特定设备的机器状态。

系统模型和系统 SKU 是存储在 Surface 设备的 UEFI 层中的系统管理 BIOS (SMBIOS) 表中的变量。 每当需要区分具有相同系统型号名称的设备（如 Surface Pro 和具有 LTE Advanced 的 Surface Pro）时，请使用系统 SKU 名称。

| 设备   | 系统模型 | 系统 SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| 北美 Surface 3 LTE                                  | Surface 3        | Surface_3_NAG                    |
| 北美之外的 Surface 3 LTE 和日本 Y！移动版 | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| 带有 LTE Advanced 的 Surface Pro                                 | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13"                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE Commercial | 系统转到 | Surface_Go_1825_Commercial |
| Surface Go 使用者                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 消费者                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 商业版                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 消费者                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Commercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7+                                               | Surface Pro 7+ | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+ | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| 带 SQ2 处理器的 Surface Pro X                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13" Intel | Surface Laptop 3 | Surface_Laptop_3_1867：1868 |
| Surface Laptop 3 15" Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15" AMD   | Surface Laptop 3 | Surface_Laptop_3_1873      | 
| Surface Laptop Go  | Surface Laptop Go | Surface_Laptop_Go_1943      | 

## 示例 

**使用 PowerShell 检索 SKU**  
使用以下 PowerShell 命令拉取系统 SKU 信息：

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**使用系统信息检索 SKU**  
还可以在系统信息中查找设备的系统 SKU 和 **系统模型**。 为此，请执行下列步骤：

1. 选择 **"** 开始"，然后在搜索框中键入**MSInfo32。**  
1. 选择 **"系统信息"。**

**在任务序列 WMI 条件中使用 SKU**  
可以将 Microsoft Deployment Toolkit (MDT) 中的系统 SKU 信息用作任务序列 WMI 条件的一部分。

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 

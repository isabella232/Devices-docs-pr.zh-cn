---
title: Surface 系统 SKU 参考
description: 本主题提供了可用于快速确定特定设备的计算机状态的系统 SKU 名称的参考。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830888"
---
# Surface System SKU 参考
此文档提供系统 SKU 名称的参考，可用于快速确定特定设备的计算机状态（使用 PowerShell、WMI 和相关工具）。 

系统 SKU 是存储在 Surface 设备的 UEFI 层的系统管理 BIOS （SMBIOS）表中的变量（以及系统模型和其他）。  无论何时需要区分具有相同系统模型名称的设备（如 Surface Pro 和 Surface Pro 和 LTE Advanced），都可以使用系统 SKU 名称。 

| **设备**| **系统型号** | **系统 SKU**|
| --- | ---| --- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| &T 上的 Surface 3 LTE                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE 北美                                  | Surface 3        | Surface_3_NAG                    |
| 在北美和 T 形手机外的第3面 LTE | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| 带有 LTE Advanced 的 Surface Pro                                 | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13inch                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15inch                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Go 消费者                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go 商业版                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 消费者                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 商业版                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface 笔记本电脑2消费者                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface 笔记本电脑2商业版                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |

## 使用系统 SKU 变量 

### PowerShell

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### 系统信息
您还可以在 "系统信息" 中查找设备的系统 SKU 和系统模型。 
- 单击 "**开始**  >   **MSInfo32**"。  

### CIM
你可以使用 Microsoft 部署工具包（MDT）或 Microsoft 终结点配置管理器中的任务序列 WMI 条件中的系统 SKU 变量。 例如： 

    - WMI 命名空间-Root\WMI
    - WQL 查询-从 MS_SystemInformation 中选择 "* SystemSKU =" Surface_Pro_1796 "

 
 
 



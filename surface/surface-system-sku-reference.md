---
title: '系统 SKU 参考 (Surface) '
description: 请参阅系统模型和系统 SKU 名称的参考。
keywords: uefi、配置、固件、安全、semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ec1d53a4bdbcaaf6606dcb0e52fc81de92a2a53b
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114540"
---
# 系统 SKU 参考

此文档提供系统模型和系统 SKU 名称的参考，可用于通过使用 PowerShell 或 WMI 快速确定特定设备的计算机状态。

系统型号和系统 SKU 是存储在系统管理 BIOS 中的变量，在 Surface 设备的 UEFI 层中 (SMBIOS) 表中。 无论何时需要区分具有相同系统模型名称的设备（如 Surface Pro 和 Surface Pro 和 LTE Advanced），都可以使用系统 SKU 名称。

| 设备   | 系统型号 | 系统 SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| &T 上的 Surface 3 LTE                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE 北美                                  | Surface 3        | Surface_3_NAG                    |
| 北美和 Y 外的 Surface 3 LTE！在日本的手机 | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| 带有 LTE Advanced 的 Surface Pro                                 | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13 "                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15 "                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13 "                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15 "                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE 商业版 | 系统前往 | Surface_Go_1825_Commercial |
| Surface Go 消费者                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go 商业版                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 消费者                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 商业版                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface 笔记本电脑2消费者                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface 笔记本电脑2商业版                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X with SQ2 处理器                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface 笔记本电脑 3 13 "英特尔 | Surface 笔记本电脑3 | Surface_Laptop_3_1867：1868 |
| Surface 笔记本电脑 3 15 "英特尔 | Surface 笔记本电脑3 | Surface_Laptop_3_1872      |
| Surface 笔记本电脑 3 15 "AMD   | Surface 笔记本电脑3 | Surface_Laptop_3_1873      | 
| Surface 膝上型电脑 Go  | Surface 膝上型电脑 Go | Surface_Laptop_Go_1943      | 

## 示例 

**使用 PowerShell 检索 SKU**  
使用以下 PowerShell 命令提取系统 SKU 信息：

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**使用系统信息检索 SKU**  
您还可以在 " **系统信息**" 中查找设备的系统 SKU 和系统模型。 为此，请执行下列步骤：

1. 选择 " **开始**"，然后在搜索框中键入 " **MSInfo32** "。  
1. 选择 " **系统信息**"。

**在任务序列中使用 SKU WMI 条件**  
你可以使用 Microsoft 部署工具包中的系统 SKU 信息 (MDT) 或 Microsoft 终结点配置管理器作为任务序列 WMI 条件的一部分。

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 

---
title: 适用于 Windows Autopilot 的 Surface 注册支持
description: 本文介绍了向 Microsoft 支持人员提交 Autopilot 注册请求的要求。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 4ff3803701ffe71e1c5c0c36200c40e833a7fb25
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271386"
---
# 适用于 Windows Autopilot 的 Surface 注册支持

Microsoft 支持现已提供注册 Surface 设备进行 Windows Autopilot 部署的简化过程。 从 2020 年 9 月开始，客户和 Microsoft 云解决方案提供商 (云解决方案提供商) 向 Microsoft 支持人员提交请求来注册 Surface 设备。 此页面概述了以下受支持的 Autopilot 注册方案的要求：
 

- **Surface Device Autopilot Registration**. 提交将 Surface 设备注册到 Windows Autopilot 的请求。
- **Surface 设备硬件哈希请求。** 向 Microsoft 支持人员提交请求，以向您提供客户或 CSP 可用于通过 Microsoft Intune 或 Microsoft 合作伙伴中心自行注册设备的硬件哈希。
- **Surface Device Autopilot Deregistration.** 提交从 Windows Autopilot 删除设备的请求，通常用于设备生命周期结束方案。

有关向 Microsoft 支持人员提交注册请求之前需要收集的信息的详细信息，请参阅下表。
 
**表 1.  Autopilot 注册请求的必需信息**
 

| 所需信息                   | 描述                                                                                                                                                                                                                                                                                    | Autopilot 注册 | 硬件哈希请求 | Autopilot<br>取消注册 |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory 租户 ID**   | Azure Active Directory 租户 ID 是 GUID (全局唯一标识符) 与组织名称或域不同。<br> <br>若要在此处找到你的租户 ID 登录 Azure[门户，](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) | Y                      | N                     | Y                           |
| **Azure Active Directory 域名** | 顶级域名;例如，contoso.com。                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **所有权证明**                 | 通过上载 PDF 格式的原始销售单或发票来验证所有权证明。 不接受屏幕截图。<br> <br>销售单或发票必须包括以下内容：<br>设备序列号。<br>公司名称。                                                           | Y                      | Y                     | Y                           |
| **设备序列号**              | 使用新行中每个设备序列号上传 CSV 格式的 Excel 文件。                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## 提交支持请求

  [![GSurface 的 et Autopilot 注册支持](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## 了解详细信息

- [Windows Autopilot 和 Surface 设备](windows-autopilot-and-surface-devices.md)
- [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Windows Autopilot 概述](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 


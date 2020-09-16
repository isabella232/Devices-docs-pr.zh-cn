---
title: 适用于 Windows 的 Surface 注册支持 Autopilot
description: 本文介绍向 Microsoft 支持提交 Autopilot 注册请求的要求。
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
ms.openlocfilehash: 9a308edb37cc2cfd99490acad16bd2ae6a4d458a
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016464"
---
# 适用于 Windows 的 Surface 注册支持 Autopilot

为 Windows Autopilot 部署注册 Surface 设备的简化过程现已提供 Microsoft 支持。 2020年9月开始，客户和 Microsoft 云解决方案提供商 (Csp) 可以通过向 Microsoft 支持人员提交请求来注册 Surface 设备。 此页面概述了以下受支持的 Autopilot 注册方案的要求：
 

- **Surface Device Autopilot 注册**。 提交向 Windows Autopilot 注册 Surface 设备的请求。
- **Surface 设备硬件哈希请求。** 向 Microsoft 支持人员提交请求，向您提供硬件哈希，客户或 Csp 可通过 Microsoft Intune 或 Microsoft 合作伙伴中心使用这些哈希。
- **Surface 设备 Autopilot 注销。** 提交从 Windows Autopilot 删除设备的请求，通常用于生命周期的设备结束。

有关将注册请求提交到 Microsoft 支持之前需要收集的信息的详细信息，请参阅下表。
 
**表 1.  Autopilot 注册请求所需的信息**
 

| 所需信息                   | 描述                                                                                                                                                                                                                                                                                    | Autopilot 注册 | 硬件哈希请求 | Autopilot<br>注册 |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory 租户 ID**   | 你的 Azure Active Directory 租户 ID 是与你的组织名称或域不同 (GUID) 的全局唯一标识符。<br> <br>在 [此处](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)查找租户 ID 登录到 Azure 门户。 | Y                      | N                     | Y                           |
| **Azure Active Directory 域名** | 顶级域名;例如，contoso.com。                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **所有权证明**                 | 通过以 PDF 格式上载原始帐单或发票，验证所有权证明。 屏幕截图不接受。<br> <br>账单或发票必须包含以下内容：<br>设备序列号。<br>公司名称。                                                           | Y                      | Y                     | Y                           |
| **设备序列号**              | 以 CSV 格式上载 Excel 文件，并在新行中使用每个设备序列号。                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## 提交支持请求

  [![Get Autopilot 注册支持 Surface](images/autopilot-reg-support-surface.png)](https://support.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## 了解详细信息

- [Windows Autopilot 和 Surface 设备](windows-autopilot-and-surface-devices.md)
- [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Windows Autopilot 概述](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 


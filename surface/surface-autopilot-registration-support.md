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
ms.openlocfilehash: 170fdfa9fb85670ec9ed8282f5d264bf2cdbf906
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911977"
---
# <a name="surface-registration-support-for-windows-autopilot"></a>适用于 Windows Autopilot 的 Surface 注册支持

现已从 Microsoft 支持部获得注册 Surface Windows进行 Autopilot 部署的简化过程。 从 2020 年 9 月开始，客户和 Microsoft 云解决方案提供商 (云解决方案提供商) 向 Microsoft 支持人员提交请求来注册 Surface 设备。 本页概述了以下受支持的 Autopilot 注册方案的要求：
 
- **Surface 设备 Autopilot 注册**。 将 Surface 设备注册到 Autopilot Windows请求。
- **Surface 设备硬件哈希请求。** 向 Microsoft 支持提交请求，以向您提供客户或 CSP 可用于通过 microsoft 合作伙伴中心自行注册设备Microsoft Intune哈希。
- **Surface 设备 Autopilot 取消注册。** 提交从 Autopilot Windows设备的请求，通常用于设备生命周期结束方案。

有关在将注册请求提交到 Microsoft 支持之前需要收集的信息的详细信息，请参阅下表。 有关所有 Surface 设备的官方系统型号名称，请参阅 [Surface System SKU 参考](surface-system-sku-reference.md)。
 
**表 1. Autopilot 注册请求的必需信息**
 

| 所需信息                   | 描述                                                                                                                                                                                                                                                                                    | Autopilot 注册 | 硬件哈希请求 | Autopilot<br>取消注册 |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory租户 ID**   | 你的Azure Active Directory租户 ID 是 GUID (全局唯) 标识符，与组织名称或域不同。<br> <br>若要在此处找到租户 ID 登录 Azure[门户，](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) | Y                      | N                     | Y                           |
| **Azure Active Directory域名** | 顶级域名;例如，contoso.com。                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **所有权证明**                 | 通过上载 PDF 格式的原始销售帐单或发票来验证所有权证明。 不接受屏幕截图。<br> <br>销售帐单或发票必须包括以下内容：<br>设备序列号。<br>公司名称。                                                           | Y                      | Y                     | Y                           |
| **设备序列号**              | Upload Excel新行中每个设备序列号的 CSV 格式创建文件。                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## <a name="submit-support-requests"></a>提交支持请求

  [![Get Surface 的 Autopilot 注册支持。](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <a name="learn-more"></a>了解详细信息

- [Windows Autopilot 和 Surface 设备](windows-autopilot-and-surface-devices.md)
- [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Windows Autopilot 概述](https://docs.microsoft.com/mem/autopilot/windows-autopilot)
- [Surface 系统 SKU 参考](surface-system-sku-reference.md)

 
 
 


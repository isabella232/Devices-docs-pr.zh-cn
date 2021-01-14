---
title: 兼容 Surface 设备中的 SSD 删除
description: 本文面向合格的 IT 技术人员，介绍了在 Surface Laptop 3、Surface Pro X 和 Surface Laptop Go 中删除和替换 SSD 的建议最佳做法。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: b65feb24803311aba809819cd6da273ed6934c75
ms.sourcegitcommit: 41124d496abaa38a0d989159f2afec3542d562ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269103"
---
# 从兼容的 Surface 设备删除 SSD 的最佳实践

> [!IMPORTANT]
> 本文仅供企业组织中合格的 IT 技术人员使用。 它介绍了推荐的最佳实践，供合格的 IT 技术人员在删除和替换以下兼容 Surface 设备中的 SSD 时使用： 

- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3

> [!WARNING]
> 打开设备和更换设备组件可能会带来电力损失、设备损坏、火灾和个人损失风险以及其他危险。  执行此类活动时，请始终小心。 按照 [RSSD](https://www.microsoft.com/download/100440)企业版删除指南中确定的安全预防措施和过程操作。 如果无法遵循"rSSD 企业版删除指南"中指定的安全预防措施和过程，我们建议您获得专业协助。

## 必备条件

> [!IMPORTANT]
> 本文假定您了解"适用于企业的 rSSD 删除指南"中所述的一般安全预防措施和安全策略和过程。

## 准备删除 SSD 

### 安装最新更新 

开始之前，请确保你的 Windows 版本已安装最新更新：

1.  转到"**开始**  >  **设置**  >  **更新&安全性**"，然后选择 **"检查更新"。**
2. 安装所有可用更新。
3. 验证访问设备所需的任何密码。  
 
## “管理 BitLocker” 

> [!NOTE]
> 本节包含为硬盘启用 BitLocker 加密的组织的建议。 有关详细信息，请参阅  [BitLocker 恢复指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。 

### 如果在删除和替换 SSD 期间禁用 BitLocker 加密

如果在删除和替换 SSD 之前设备可以未加密，请按照以下步骤关闭 BitLocker：

1.  在 **"设置**"中，键入**BitLocker，** 然后选择 **"管理 BitLocker"。** 
2.  选择 **"关闭 BitLocker"。** 
3.  关闭设备。 

### 如果在删除和替换 SSD 期间启用了 BitLocker 加密

如果在删除和替换 SSD 之前对设备进行了加密，请按照以下步骤生成 BitLocker 恢复密钥并将其保存到 USB 存储：

1.  在 **"设置**"中，键入**BitLocker。**
2. 选择 **"管理 BitLocker**  > **生成 BitLocker 恢复密钥"。**
2.  插入 U 盘。 
4.  将恢复密钥保存到 USB 存储。  
5.  删除 USB 驱动器。  
6.  关闭设备。 

## 删除和替换 SSD 

1.  使用 [RSSD](https://www.microsoft.com/download/100440)企业版删除指南中包含的设备的适当说明删除 SSD。 
2.  将原始 SSD 放入新设备，将新设备连接到有线 Internet 连接。
3.  打开新设备的电源。 设备可能在启动期间完成固件更新。  
 
## 删除和替换 SSD 后

### 管理未加密的 SSD 

如果在传输过程中 SSD 未加密，请按照以下步骤操作： 

1.  转到 **"登录选项**密码 (由左侧按钮图标表示  >  ****) 。  
2.  输入密码并登录，等待双重身份验证 (如果适用) 。
3.  完全登录后，转到"开始****  >  **帐户**  >  **注销"。**  
4.  使用密码重新登录，在系统提示时设置 Windows Hello 和 PIN。 
    - 如果设备已禁用 BitLocker 以便于删除和替换 SSD，并且你想要在替换后启用 BitLocker，请转到**BitLocker**  >  **管理 BitLocker**  >  **Resume BitLocker。**  
6.  运行 [Microsoft Surface Diagnostic Toolkit for Business (](surface-diagnostic-toolkit-for-business-intro.md) SDT) 验证完整的设备功能。  
7.  通过导航到"设置激活"**** 检查 Windows  >  **激活**。  如果看到任何错误消息，请选择"疑难**解答"。** 
8.  通过打开 Office 应用来检查**Office**帐户，导航到"**文件**帐户  >  ****"，然后检查是否有错误消息。  

### 管理加密的 SSD 

> [!NOTE]
> 你必须有第二个设备来读取保存在 USB 驱动器上的 BitLocker 恢复密钥。 

如果在传输过程中对 SSD 进行了加密，请按照以下步骤操作：

1.  将包含 BitLocker 恢复密钥的 USB 驱动器插入第二台设备。 
2.  打开包含 Bitlocker 恢复密钥的 .txt 文件。 
3.  在包含原始 SSD 的新设备上手动输入 BitLocker 恢复密钥。  
4.  成功输入 BitLocker 恢复密钥后，转到"登录**** 选项密码" (左侧按钮图标  >  **** 表示) 。  
5.  输入密码并登录，等待双重身份验证 (（如果适用) ）。
6.  完全登录后，转到"开始****  >  **帐户**  >  **注销"。**  
7.  使用密码重新登录，然后设置 Windows Hello 并添加 PIN。 
8.  如果设备已禁用 BitLocker 以便于删除和替换 SSD，并且如果你想要在替换后启用 BitLocker，请转到"**设置**  >  **BitLocker**管理  >  **BitLocker**  >  **恢复 BitLocker"。**  
9.  运行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以验证完整的设备功能。  
10. 若要检查 Windows 激活，请选择"**设置**  >  **激活"。**  如果看到任何错误消息，请选择"疑难**解答"。**
11. 若要检查 Office 帐户的状态，请打开**Office 应用程序**，然后转到****"文件帐户"  >  **** 以检查是否有错误消息。

## 了解详细信息

- [适用于企业的 rSSD 删除指南](https://www.microsoft.com/download/100440)
- [BitLocker 恢复指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

是否仍需要帮助？ 转到 [Microsoft 社区](https://answers.microsoft.com/)。
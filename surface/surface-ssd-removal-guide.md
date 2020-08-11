---
title: 兼容的 Surface 设备中的 SSD 删除
description: 如何将 SSD 从一个 Surface 设备转移到另一个 Surface 设备。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 66860af06f4fad8f19ca26702350f19cc85ffef1
ms.sourcegitcommit: bad416f04c6877f2200f134a69146bb633155f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919221"
---
# 从兼容的 Surface 设备中删除 SSD 的最佳做法

> [!IMPORTANT]
> 本文仅供企业组织中合格的 IT 技术人员使用。 它介绍了符合条件的 IT 技术人员在具有可移动 SSDs 的 Surface 设备中删除和更换 SSDs 时使用的建议最佳做法。 

> [!WARNING]
> 打开设备和更换设备组件可能会带来电击、设备损坏、火灾和人身伤害风险以及其他危险。  在执行此类活动时，请务必小心。 按照[适用于企业的 RSSD 删除指南](https://www.microsoft.com/download/100440)中标识的安全预防措施和过程进行操作。 如果您无法遵循 "适用于企业的 rSSD 删除指南" 中指定的安全预防措施和过程，我们建议您获得专业帮助。

## 先决条件

> [!IMPORTANT]
> 本文假定你了解 "适用于企业的 rSSD 删除指南" 中介绍的常规安全预防措施和安全策略和过程。

## 准备删除 SSD 

### 安装最新的更新 

开始之前，请确保你的 Windows 版本具有最新的更新 intalled：

1.  转到 "**开始**  >  **设置**  >  "**更新 & 安全**"，然后选择"**检查更新**"。 安装所有可用更新。 
2. 安装所有可用更新。
3. 验证您是否拥有访问设备所必需的任何密码。  
 
## “管理 BitLocker” 

> [!NOTE]
> 本部分包括对硬盘启用了 BitLocker 加密的组织的建议。 有关详细信息，请参阅[BitLocker 恢复指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。 

### 如果在 SSD 删除和替换期间禁用 BitLocker 加密

如果在 SSD 删除和替换之前可以解除对设备的加密，请按照以下步骤关闭 BitLocker：

1.  在 "**设置**" 中，键入 " **bitlocker**"，然后选择 "**管理 bitlocker**"。 
2.  选择 "**关闭 Bitlocker**"。 
3.  关闭设备电源。 

### 如果在 SSD 删除和替换期间启用了 BitLocker 加密

如果设备在 SSD 删除和替换之前已加密，请按照以下步骤生成 BitLocker 恢复密钥并将其保存到 USB 存储：

1.  在 "**设置**" 中，键入**Bitlocker**。
2. 选择 "**管理 bitlocker**  > **生成 bitlocker 恢复密钥**"。
2.  插入 u 盘。 
3.  将恢复密钥保存到 USB 存储。  
4.  删除 USB 驱动器。  
5.  关闭设备电源。 

## 删除并替换 SSD 

1.  使用[适用于企业的 RSSD 删除指南](https://www.microsoft.com/download/100440)中的说明删除 SSD。 
2. 将原始的 SSD 放入新设备中，并将新设备连接到有线 internet 连接。
2.  打开新设备的电源。 设备可能会在启动期间经历固件更新。  
 
## 在 SSD 删除和更换后

### 管理未加密的 SSDs 

如果 SSD 在传输期间保持未加密，请按照下列步骤操作： 

1.  转到 "**登录选项**"  >  **密码** (左侧) 的钥匙图标表示。  
2.  输入密码，如果有两个因素身份验证，请登录 (（如果适用）) 。
3.  完全登录后，转到 "**开始**  >  **帐户**  >  **注销**"。  
4.  使用密码重新登录，并在系统提示时设置 Windows Hello 和 PIN。 
    - 如果设备已禁用 BitLocker 来简化 SSD 删除和替换，并且你希望在替换后启用 bitlocker，请转到**bitlocker**  >  **管理 bitlocker**  >  **恢复 bitlocker**。  
6.  运行适用于 Business (SDT) 的 Microsoft Surface 诊断工具包，以验证完整的设备功能。  
7.  通过导航到 "**设置**激活" 来检查是否有 Windows 激活  >  **Activation**。  如果看到任何错误消息，请选择 "**疑难解答**"。 
8.  通过打开**office 应用**检查 office 帐户，导航到 "**文件**  >  **帐户**"，然后检查是否有任何错误消息。  

### 管理加密的 SSDs 

> [!NOTE]
> 您必须拥有第二台设备才能读取保存在 USB 驱动器上的 BitLocker 恢复密钥。 

如果 SSD 在传输期间保持加密，请按照下列步骤操作：

1.  将包含 Bitlocker 恢复密钥的 USB 驱动器插入到第二个设备中。 
2.  打开包含 Bitlocker 恢复密钥的 .txt 文件。 
3.  在包含原始 SSD 的新设备上手动输入 Bitlocker 恢复密钥。  
4.  成功输入 BitLocker 恢复密钥后，转到左侧) 的钥匙图标中的 "**登录选项**"  >  **密码** (。  
5.  如果适用，请输入密码并登录，等待完成双因素身份验证 (（如果适用）) 。
6.  完全登录后，转到 "**开始**  >  **帐户**  >  **注销**"。  
7.  使用密码重新登录，然后设置 Windows Hello 并添加 PIN 码。 
8.  如果设备已禁用 BitLocker 以促进 SSD 删除和替换，并且如果你希望在更换后启用 bitlocker，请转到**Settings**  >  **bitlocker**  >  **管理 bitlocker**  >  **恢复 bitlocker**的设置。  
9.  运行**SDT**以验证完整的设备功能。  
10. 通过导航到 "**设置**激活" 检查 Windows 激活  >  **Activation**。  如果看到任何错误消息，请选择 "**疑难解答**"。
11. 若要检查 office 帐户的状态，请打开**office 应用**，然后转到 "**文件**  >  **帐户**" 以检查是否有任何错误消息。

## 详细信息 

有关详细信息，请参阅以下文章：

- [适用于企业的 rSSD 删除指南](https://www.microsoft.com/download/100440)
- [BitLocker 恢复指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

是否仍需要帮助？ 转到[Microsoft 社区](https://answers.microsoft.com/)。
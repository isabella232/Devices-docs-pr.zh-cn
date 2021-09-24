---
title: 兼容 Surface 设备中的 SSD 删除
description: 本文面向合格的 IT 技术人员，介绍了有关在 Surface Laptop 4、Surface Laptop 3、Surface Pro 7+、Surface Pro X 和 Surface Laptop Go 中删除和替换 SSD 的建议最佳做法。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop Studio
- Surface Pro 8
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 6df16955eda79d52097fc4f9490b6d1e445b7e26
ms.sourcegitcommit: 760a3bdd2e40ecefe4f588703fa9281dd8f2b4b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2021
ms.locfileid: "12037504"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a>从兼容的 Surface 设备删除 SSD 的最佳实践

> [!IMPORTANT]
> 本文仅供企业组织中合格的 IT 技术人员使用。 它介绍了推荐的最佳实践，供合格的 IT 技术人员在删除和替换以下兼容 Surface 设备中的 SSD 时使用：

- Surface LaptopStudio
- Surface Pro 8
- Surface Pro 7+
- Surface Pro X
- Surface Laptop转到
- Surface Laptop 3
- Surface Laptop 4

> [!WARNING]
> 打开设备和更换设备组件可能会带来电力振动、设备损坏、火灾和个人危害风险以及其他危险。  执行此类活动时始终要谨慎。 按照[rSSD](https://www.microsoft.com/download/100440)删除指南中确定的安全预防措施Enterprise。 如果您无法遵循"rSSD 删除指南 for Enterprise"中指定的安全预防措施和过程，我们建议您获得专业协助。

## <a name="prerequisites"></a>必备条件

> [!IMPORTANT]
> 本文假定您了解"rSSD 删除指南 for Enterprise"中介绍的一般安全预防措施和安全策略和过程。

## <a name="prepare-for-ssd-removal"></a>准备删除 SSD

### <a name="install-the-latest-updates"></a>安装最新更新

开始之前，请确保您的 Windows已安装最新更新：

1. 转到"**开始**  >  **设置**  >  **更新&安全**"，然后选择"**检查更新"。**
2. 安装所有可用更新。
3. 验证访问设备所需的任何密码。  

## <a name="manage-bitlocker"></a>“管理 BitLocker”

> [!NOTE]
> 本部分包含针对为硬盘启用 BitLocker 加密的组织的建议。 有关详细信息，请参阅  [BitLocker 恢复指南](/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a>如果在删除和替换 SSD 期间禁用 BitLocker 加密

如果在删除和替换 SSD 之前设备可以未加密，请按照以下步骤关闭 BitLocker：

1. 在**设置**中，键入**BitLocker，** 然后选择管理**BitLocker**。
2. 选择 **关闭 BitLocker**。
3. 关闭设备电源。

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a>如果在 SSD 删除和替换期间启用了 BitLocker 加密

如果在删除和替换 SSD 之前对设备进行了加密，请按照以下步骤生成 BitLocker 恢复密钥并将其保存到 USB 存储：

1. 在**设置**中，键入**BitLocker**。
2. 选择**管理 BitLocker**  > **生成 BitLocker 恢复密钥**。
2. 插入 USB 驱动器。
4. 将恢复密钥保存到 USB 存储。  
5. 删除 USB 驱动器。  
6. 关闭设备电源。

## <a name="remove-and-replace-ssd"></a>删除和替换 SSD

1. 使用适用于设备的[rSSD](https://www.microsoft.com/download/100440)删除指南中针对设备的适当说明删除 SSD Enterprise。
2. 将原始 SSD 放入新设备，将新设备连接到有线 Internet 连接。
3. 打开新设备电源。 设备可能在启动期间经历固件更新。  

## <a name="after-ssd-removal-and-replacement"></a>删除和替换 SSD 后

### <a name="manage-unencrypted-ssds"></a>管理未加密的 SSD

如果在传输过程中 SSD 未加密，请按照以下步骤操作：

1. 转到**登录选项 密码** (由左侧密钥图标  >  **** 表示的密码) 。  
2. 输入密码并登录，等待双重身份验证 (如果适用) 。
3. 完全登录后，转到开始****  >  **帐户**  >  **注销**。  
4. 系统提示时，使用密码重新登录，Windows Hello设置密码和 PIN。
    - 如果设备已禁用 BitLocker 以方便删除和替换 SSD，并且你想要在替换后启用 BitLocker，请转到**BitLocker**  >  **管理 BitLocker**  >  **Resume BitLocker**。  
6. 运行[Microsoft Surface Diagnostic Toolkit for Business (](surface-diagnostic-toolkit-for-business-intro.md) SDT) 验证完整的设备功能。  
7. 通过导航Windows"激活"来**检查设置**  >  **激活。**  如果看到任何错误消息，请选择"疑难**解答"。**
8. 通过打开 Office App 检查Office**帐户**，导航到"文件""**** 帐户"，  >  **** 然后检查是否有错误消息。  

### <a name="managing-encrypted-ssds"></a>管理加密的 SSD

> [!NOTE]
> 你将必须拥有另一台设备来读取保存在 USB 驱动器上的 BitLocker 恢复密钥。

如果在传输过程中对 SSD 进行了加密，请按照以下步骤操作：

1. 将包含 BitLocker 恢复密钥的 USB 驱动器插入第二台设备。
2. 打开.txt Bitlocker 恢复密钥的密钥文件。
3. 在包含原始 SSD 的新设备上手动输入 BitLocker 恢复密钥。  
4. 成功输入 BitLocker 恢复密钥后，转到登录选项**** 密码 (由左侧密钥图标表示  >  **** 的密码) 。  
5. 输入密码并登录，等待双重身份验证 (如果适用) 。
6. 完全登录后，转到开始****  >  **帐户**  >  **注销**。  
7. 使用密码重新登录，然后设置Windows Hello并添加 PIN。
8. 如果设备已禁用 BitLocker 以方便删除和替换 SSD，并且如果你想要在替换后启用 BitLocker，请转到**设置**  >  **BitLocker**  >  **管理 BitLocker**Resume  >  **BitLocker**。  
9. 运行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以验证完整的设备功能。  
10. To check Windows activation， select**设置**  >  **Activation**.  如果看到任何错误消息，请选择"疑难**解答"。**
11. To check the status of the Office **account，** open the Office App ， then go to **File**  >  **Account** to check for any error messages.

## <a name="learn-more"></a>了解详细信息

- [rSSD 删除指南Enterprise](https://www.microsoft.com/download/100440)
- [BitLocker 恢复指南](/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

是否仍需要帮助？ 转到[Microsoft Community](https://answers.microsoft.com/)。

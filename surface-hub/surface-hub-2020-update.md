---
title: 安装 Windows 10 协同版 2020 更新
description: 获取 Surface Hub 操作系统的最新更新，Windows 10 协同版 2020 年更新。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 7474787351a9371fb09fa10348ac9f6591b81f6b
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497825"
---
# <a name="install-windows-10-team-2020-update"></a>安装 Windows 10 协同版 2020 更新 

基于 Windows 10 版本 **20H2 的新 Surface Hub 操作系统 Windows 10 协同版 2020 Update** 现已可用于 Surface Hub 2S 和原始Surface Hub (v1) 。 

- 另请参阅：[已知问题：Windows 10 协同版 2020 年更新](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>分发

可以使用以下方法之一获取 Windows 2020 更新：

- **Windows 更新企业版**。
- **裸机恢复 (BMR) 映像**。 建议将设备加入到Azure Active Directory或不允许其设备从 Internet 接收更新的客户。 若要开始，请参阅 [下载 Surface 的恢复映像](https://support.microsoft.com/surfacerecoveryimage)。
- **Windows 更新。** 可用性因地区/国家/地区而异，如下表所述：

| 阶段 | 国家/地区                         | 开始          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ、澳大利亚、加拿大、比利时、墨西哥 | 2020 年 10 月  |
| 2     | 英国、日本、瑞士、意大利          | 2020 年 11 月 |
| 3     | 德国、荷兰                   | 2021 年 2 月下旬 |
| 4     | 全局                                 | 2021 年 3 月初 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>使用 Windows 10 协同版 版本 1703 为 Surface Hub 提供服务 

[Windows 10 协同版版本 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) 的完整服务支持计划持续到 2021 年 3 月 16 日。

### <a name="2s-devices"></a>2S 设备 

所有区域中的客户都可以通过 Windows 更新、Windows 更新 for Business 或使用裸机恢复 (BMR) 映像将其 Surface Hub [2S 设备更新到 2020 年更新，如 Surface Hub 2S 的重置和恢复](surface-hub-2s-recover-reset.md)中所述。

### <a name="v1-devices"></a>V1 设备 

所有区域中的客户都可以通过 Windows 更新、Windows 更新 for Business 或[使用 Surface Hub 恢复工具将其Surface Hub](surface-hub-recovery-tool.md) v1 设备更新到 2020 年更新。 必须安装 KB5000749 才能通过无线方式接收更新。 若要了解详细信息，请[参阅 Surface IT Pro博客](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371)。
 
## <a name="whats-new"></a>新增内容

Windows 10 协同版 2020 年更新为设备部署和可管理性以及最新的Windows功能带来了重大改进。 若要了解详细信息，请参阅 [Windows 10 协同版 2020 更新中的新增功能](surface-hub-2020-update-whats-new.md)。
 
## <a name="before-you-begin"></a>在开始之前

在安装 Windows 10 协同版 2020 更新之前，请确保保存与设备关联的 BitLocker 密钥。 

**手动保存 BitLocker 密钥**

1. 将 USB 驱动器插入Surface Hub。
2. 在Surface Hub，打开**设置**并在出现提示时输入管理员凭据。
3. 导航到 **“更新”&** **SecurityRecovery** > 。
4. 在 **BitLocker** 下，选择 **“保存**”。 BitLocker 密钥保存到 USB 驱动器上的文本文件。

若要了解详细信息，请参阅 [保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。

## <a name="learn-more"></a>了解详细信息

- [Windows 10 协同版 2020 更新中的新增功能](surface-hub-2020-update-whats-new.md)
- [Windows 10 协同版推出更新](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)

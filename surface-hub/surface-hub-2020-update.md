---
title: 安装 Windows 10 协同版 2020 更新
description: 获取 Surface Hub 操作系统的最新更新，即 Windows 10 Team 2020 更新。
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
ms.openlocfilehash: 4d68f751bd15ef6529bcd16a6305d8c682970747
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470410"
---
# <a name="install-windows-10-team-2020-update"></a>安装 Windows 10 协同版 2020 更新 

基于 Windows 10 版本 20H2 的新 Surface Hub 操作系统 **Windows 10 Team 2020 Update**现在可用于 Surface Hub 2S 和原始 Surface Hub (v1) 。 

- 另请参阅： [已知问题：Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>分发

可以使用以下方法之一获取 Windows 2020 更新：

- **适用于企业的 Windows 更新**。
- **裸机恢复 (BMR) 映像**。 建议用于将设备加入 Azure Active Directory 或不允许其设备从 Internet 接收更新的客户。 若要开始，请参阅 [下载 Surface 的恢复映像](https://support.microsoft.com/surfacerecoveryimage)。
- **Windows 更新。** 可用性因地区/国家/地区而异，如下表所示：

| 阶段 | 国家/地区                         | 正在启动          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ、澳大利亚、加拿大、比利时、墨西哥 | 2020 年 10 月  |
| 2     | 英国、日本、瑞士、意大利          | 2020 年 11 月 |
| 3     | 德国、荷兰                   | 2021 年 2 月后期 |
| 4     | 全局                                 | 2021 年 3 月早期 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>使用 Windows 10 Team Edition 版本 1703 维护 Surface Hub 

Windows [10 Team Edition 版本 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) 的完整服务支持计划继续到 2021 年 3 月 16 日。

### <a name="2s-devices"></a>2S 设备 

所有地区的客户可以通过 Windows 更新、适用于 Business 的 Windows 更新或通过使用裸机恢复 (BMR) 映像将 Surface Hub 2S 设备更新到 2020 更新，如 [Surface Hub 2S](surface-hub-2s-recover-reset.md)重置和恢复中介绍。

### <a name="v1-devices"></a>V1 设备 

所有地区的客户都可以通过 Windows 更新、适用于企业 Windows 更新或通过使用 Surface Hub 恢复工具将 [Surface Hub](surface-hub-recovery-tool.md)v1 设备更新到 2020 更新。 必须安装 KB5000749 才能通过空机接收更新。 若要了解更多信息，请参阅 [Surface IT 专业人员博客](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371)。
 
## <a name="whats-new"></a>新增内容

Windows 10 Team 2020 Update 对设备部署和可管理性以及最新的 Windows 10 功能进行了重大改进。 若要了解更多信息， [请参阅 Windows 10 Team 2020 Update 中的新增功能](surface-hub-2020-update-whats-new.md)。
 
## <a name="before-you-begin"></a>开始之前

在安装 Windows 10 Team 2020 Update 之前，请确保保存与设备关联的 BitLocker 密钥。 

**手动保存 BitLocker 密钥**

1. 将 U 盘插入 Surface Hub。
2. 在 Surface Hub 上， **打开"设置** "，在出现提示时输入管理员凭据。
3. 导航到 **"更新&安全**  >  **恢复"。**
4. 在**BitLocker 下**，选择"保存 **"。** BitLocker 密钥将保存到 USB 驱动器上的文本文件中。

若要了解更多信息，请参阅 [保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。

## <a name="learn-more"></a>了解详细信息

- [Windows 10 协同版 2020 更新中的新增功能](surface-hub-2020-update-whats-new.md)
- [Windows 10 协同版推出更新](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)

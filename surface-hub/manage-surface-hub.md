---
title: 管理 Microsoft Surface Hub
description: 完成首次运行计划后如何管理 Surface Hub。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/17/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7fa715c679803da460cc1d57bd6e84fa33d30413
ms.sourcegitcommit: d9c413f1c50908a81e5489aca2c6023eab573148
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "12093039"
---
# <a name="manage-microsoft-surface-hub"></a>管理 Microsoft Surface Hub

初始设置设备Microsoft Surface Hub，可以通过多种方式修改或更改设备设置和配置：

- **本地管理** - 可使用设备上的“设置”**** 应用在本地配置每台 Surface Hub。 若要防止未经授权的用户更改设置，“设置”应用要求使用管理员凭据打开该应用。 有关详细信息，请参阅 [Surface Hub 设置的本地管理](local-management-surface-hub-settings.md)。
- 远程管理 **-** Surface Hub IT 管理员使用移动设备管理 (MDM) 提供程序（如 Microsoft Intune、Microsoft Endpoint Configuration Manager 和其他第三方提供程序）管理设置和策略。 此外，管理员可以使用 Azure Monitor 监视 Surface Hub。  有关详细信息，请参阅使用 [MDM](manage-settings-with-mdm-for-surface-hub.md)提供程序管理设置，以及使用 Azure Monitor 监视 [Surface Hub 以跟踪其运行状况](/azure/azure-monitor/insights/surface-hubs)。 

> [!NOTE]
> 这些管理方法互相不排斥。 设备可本地和远程管理，任你选择。 但是，当 MDM 策略和设置与管理服务器Surface Hub时，MDM 策略和设置将覆盖本地更改。 

## <a name="in-this-section"></a>本节内容

了解如何管理和更新 Surface Hub。

| 主题 | 描述 |
| ----- | ----------- |
| [远程 Surface Hub 管理](remote-surface-hub-management.md) |与远程管理 Surface Hub 相关的主题。 包括安装应用、使用 MDM 管理设置以及使用 Operations Management Suite 进行监视。 |
| [管理 Surface Hub 设置](manage-surface-hub-settings.md) |与管理 Surface Hub 设置相关的主题：辅助功能、设备帐户、设备重置、完全限定的域名、Windows 更新设置和无线网络 |
| [在 Surface Hub 上安装应用](install-apps-on-surface-hub.md) | 管理员可以安装来自 Microsoft Store 或适用于企业的 Microsoft Store 的应用。|
[配置 Surface Hub 的“开始”菜单](surface-hub-start-menu.md) | 使用 MDM 可自定义 Surface Hub 的“开始”菜单。
| [设置并使用 Microsoft Whiteboard](whiteboard-collaboration.md)  | Microsoft Whiteboard 的最新更新包括可让两个 Surface Hub 在同一开发板上实时协作的功能。   |
| [使用“结束会话”结束会议](finishing-your-surface-hub-meeting.md) | 在会议结束后，用户可点击**结束会话**，清理任何敏感数据，并为下一场会议准备好设备。|
| [使用 Microsoft Authenticator 登录到 Surface Hub](surface-hub-authenticator-app.md) | 你可以使用 Android 和 iOS 上提供的 Microsoft Authenticator 应用登录到 Surface Hub，而无需使用密码。   |
| [保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md) | 使用 BitLocker 驱动器加密软件自动设置每台 Surface Hub。 Microsoft 强烈建议确保备份 BitLocker 恢复密钥。|
| [连接其他设备并使用 Surface Hub 显示](connect-and-display-with-surface-hub.md) | 可以将其他设备连接到 Surface Hub 来显示内容。|
| [现有无线网络或 LAN 上的 Miracast](miracast-over-infrastructure.md) | 你可以使用无线网络或 LAN 上的 Miracast 连接到 Surface Hub。 |
 [启用 802.1x 有线身份验证](enable-8021x-wired-authentication.md) | 802.1x 有线身份验证 MDM 策略已在 Surface Hub 设备上启用。 
| [使用房间控制系统](use-room-control-system-with-surface-hub.md) | 可以将房间控制系统与 Microsoft Surface Hub 结合使用。|
[使用 Surface Hub 恢复工具](surface-hub-recovery-tool.md) | 使用 Surface Hub 恢复工具对 SSD 进行Surface Hub映像。
[Surface Hub SSD 更换](surface-hub-ssd-replacement.md) | 了解如何删除和替换设备中的固态硬盘Surface Hub。

## <a name="related-topics"></a>相关主题

- [在 Surface Hub 和 Windows 10 上查看 Power BI 的演示模式](https://powerbi.microsoft.com/documentation/powerbi-mobile-win10-app-presentation-mode/)

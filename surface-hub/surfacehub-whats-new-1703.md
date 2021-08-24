---
title: Windows 10 版本 1703 中 Surface Hub 的新增功能
description: Windows 10 版本 1703（创意者更新）为 Microsoft Surface Hub 带来了新功能。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 8edc5bf1da384809e38451c9d164503bfcc10241
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911767"
---
# <a name="whats-new-in-windows-10-version-1703-for-microsoft-surface-hub"></a>Windows 10 版本 1703 中 Microsoft Surface Hub 有哪些新增功能？

观看 Surface Hub 工程师 Jordan Marchese 介绍 Windows 10 版本 1703（创意者更新）的 Microsoft Surface Hub 更新。 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

Windows 10 版本 1703 (也称为创意者更新)为 Microsoft Surface Hub 带来了以下更改。

## <a name="new-settings"></a>新设置

为移动设备管理 (MDM) 和配置服务提供程序 (CSP) 添加了设置，以便扩展 Surface Hub 管理功能。 [新设置包括](manage-settings-with-mdm-for-surface-hub.md)：

- InBoxApps/SkypeForBusiness/DomainName
- InBoxApps/Connect/AutoLaunch
- Properties/DefaultVolume
- Properties/ScreenTimeout
- Properties/SessionTimeout
- Properties/SleepTimeout
- Properties/AllowSessionResume
- Properties/AllowAutoProxyAuth
- Properties/DisableSigninSuggestions
- Properties/DoNotShowMyMeetingsAndFiles
- System/AllowStorageCard

以及基于新 [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) 和 [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) 的设置。
</br>

## <a name="provisioning-wizard"></a>预配向导

易于使用的向导可帮助快速创建能应用于多个 Surface Hub 设备的预配包，并包括批量加入 Azure Active Directory。 [了解如何为 Surface Hub 创建预配包。](provisioning-packages-for-certificates-surface-hub.md)

![预配设备Surface Hub中的步骤。](images/wcd-wizard.png)
    
## <a name="miracast-on-your-existing-wireless-network-or-lan"></a>现有无线网络或 LAN 上的 Miracast 

Microsoft 的功能经过扩展，可以[通过本地网络发送 Miracast 流](miracast-over-infrastructure.md)，而不是通过直接无线链接来发送。 
    
## <a name="cloud-recovery"></a>云恢复

重置 Surface Hub 设备时，能够立即从云中下载并安装操作系统出厂版本。 [了解关于云恢复的详细信息。](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
>如果使用代理服务器，云恢复将不起作用。
    
![重新安装。](images/reinstall.png)
    
## <a name="end-session"></a>结束会话

**我已完成**现为**结束会话**。 [了解如何使用“结束会话”。](finishing-your-surface-hub-meeting.md) 

![结束会话。](images/end-session.png)



 

 

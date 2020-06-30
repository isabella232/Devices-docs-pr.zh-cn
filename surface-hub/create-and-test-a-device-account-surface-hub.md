---
title: 创建和测试设备帐户 (Surface Hub)
description: 本主题介绍了如何创建和测试 Microsoft Surface Hub 用于与 Microsoft Exchange 和 Skype 进行通信的设备帐户。
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: 创建和测试设备帐户, 设备帐户, Surface Hub 和 Microsoft Exchange, Surface Hub 和 Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831896"
---
# 创建和测试设备帐户 (Surface Hub)


本主题介绍了如何创建和测试 Microsoft Surface Hub 用于与 Microsoft Exchange 和 Skype 进行通信的设备帐户。

“设备帐户”**** 是 Surface Hub 用于执行以下操作的 Exchange 资源帐户：

-   显示会议日历
-   加入团队或 Skype for Business 呼叫
-   发送电子邮件（例如以电子邮件形式发送会议的白板内容）

预配了 Surface Hub 的设备帐户后，用户可将此帐户添加到会议邀请，方式与邀请用户加入会议室的方式相同。 

## 配置概述

此表介绍了创建设备帐户时的主要步骤和配置决策。 
 
| 步骤 | 描述                     |  用途                             |
|------|---------------------------------|--------------------------------------|
| raid-1    | 创建支持登录的 Exchange 资源邮箱（Exchange 2013 或更高版本，或者 Exchange Online） | 此资源邮箱允许设备保留会议日历、接收会议请求和发送邮件。 必须支持登录，才能为 Surface Hub 进行预配。 |
| ppls-2    | 配置邮箱属性 | 必须使用正确的属性配置邮箱，才能在 Surface Hub 上获得最佳会议体验。 有关邮箱属性的详细信息，请参阅[邮箱属性](exchange-properties-for-surface-hub-device-accounts.md)。 |
| 三维空间    | 将可兼容的移动设备邮箱策略应用到邮箱 | Surface Hub 使用移动设备管理 (MDM) 进行管理，而非通过移动设备邮箱策略进行管理。 对于兼容性，设备帐户必须具备移动设备邮箱策略，并且 **PasswordEnabled** 设置已设为 False。 否则，Surface Hub 无法同步邮箱和日历信息。 |
| 第    | 通过 Skype for Business 启用邮箱（Lync Server 2013 或更高版本，或者 Skype for Business Online） | 必须启用 Skype for Business 才能使用各种会议功能，例如视频通话、IM 和屏幕共享。  |
| 级    | （可选）将 ActiveSync 设备 ID 加入允许列表 | 组织可能具有全局策略，可阻止设备帐户同步邮件和日历信息。 如果是这样，你需要允许 Surface Hub 的 ActiveSync 设备 ID。 |
| 型    | （可选）禁用密码过期 | 为了简化管理，可以关闭设备帐户的密码过期设置，并允许 Surface Hub 自动轮换设备帐户密码。 有关密码管理的详细信息，请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)。  |

## 详细的配置步骤 

我们建议使用远程 PowerShell 设置设备帐户。 可使用 PowerShell 脚本帮助创建和验证设备帐户。有关 PowerShell 脚本和说明的详细信息，请参阅[附录 A：PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)。 

有关使用 PowerShell 预配设备帐户的详细步骤，请根据组织部署情况，选择表中某个选项。 

| 组织部署             |  描述                  |
|---------------------------------|--------------------------------------|
| [联机部署 (Office 365)](online-deployment-surface-hub-device-accounts.md) | 组织的环境完全在 Office 365 上进行部署。 |
| [本地部署（单林）](on-premises-deployment-surface-hub-device-accounts.md) | 组织具有受其控制并用于在单林环境中托管 Active Directory、Exchange 和 Skype for Business（或 Lync）的服务器。 |
| [本地部署（多林）](on-premises-deployment-surface-hub-multi-forest.md) | 组织具有受其控制并用于在多林环境中托管 Active Directory、Exchange 和 Skype for Business（或 Lync）的服务器。 |
| [混合部署](hybrid-deployment-surface-hub-device-accounts.md) | 组织混合使用多个服务，其中一些服务本地托管，而另一些服务通过 Office 365 联机托管。 |
| [使用 Skype 混合语音环境的联机或混合部署](skype-hybrid-voice.md) | 组织在云中具有 Skype for Business 主池和 Exchange 服务器，并使用 Skype for Business 2015 本地池或通过公用电话交换网 (PSTN) 连接的云连接器版本。 |


如果倾向于使用图形用户界面 (UI)，可使用 UI 而非 PowerShell 执行某些步骤。 有关详细信息，请参阅[使用 UI 创建设备帐户](create-a-device-account-using-office-365.md)。

## 帐户验证和测试

有两种方法可用于验证和测试 Surface Hub 设备帐户: [帐户验证脚本](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)和 [Surface Hub 硬件诊断应用](https://www.microsoft.com/store/apps/9nblggh51f2g)。 帐户验证脚本将使用桌面上的 PowerShell 验证之前创建的设备帐户。 Surface Hub 硬件诊断应用安装在 Surface Hub 上，提供有关登录和通信失败的详细反馈。 两种工具在测试新创建的设备帐户时都非常有用，须用于确保帐户可用性达到最佳。

 

 

 






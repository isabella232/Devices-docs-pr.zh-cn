---
title: 重置或恢复 Surface Hub
description: 介绍 Surface Hub 的重置和恢复过程，并提供相关说明。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重置 Surface Hub，恢复
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: c5cf643d0f4a68344bb098916a909dd66e1dac9b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831868"
---
# 重置或恢复 Surface Hub

本文介绍如何重置或恢复 Microsoft Surface Hub。  

[重置 Surface Hub](#reset-a-surface-hub)会将其操作系统返回到上次累积的 Windows 更新，并删除所有本地用户文件和配置信息。 删除的信息包括以下内容：

- 设备帐户
- 设备的本地管理员的帐户信息
- 域加入或 Azure AD 联接信息
- 移动设备管理（MDM）注册信息
- 使用 MDM 或 "设置" 应用设置的配置信息

[从云恢复 Surface Hub](#recover-a-surface-hub-from-the-cloud)也会删除此信息。 此外，Surface Hub 下载新的操作系统映像并进行安装。 你可以指定恢复过程是否保留存储在 Surface Hub 上的其他信息。

## 重置 Surface Hub

出于以下原因，您可能需要重置 Surface Hub：

- 您为新的会议空间重新安排设备的用途，并希望重新配置它。
- 想要更改本地管理设备的方式。
- 设备帐户或管理员帐户的用户名或密码已丢失。
- 安装更新后，设备性能将减少。

在重置过程中，如果你长时间看到一个空白屏幕，请等待，不要执行任何操作。

> [!WARNING]
> 设备重置过程可能需要长达6小时。 请勿关闭或拔出 Surface Hub，直到该过程完成。 如果中断进程，设备将变为不可操作。 设备需要保修服务才能再次运行。

1. 在 Surface Hub 上，打开**设置**。

   ![显示 Surface Hub 的 "设置" 应用的图像。](images/sh-settings.png)

1. 选择 "**更新 & 安全性**"。

   ![在 Surface Hub 的 "设置" 应用中显示 "更新 & 安全组" 的图像。](images/sh-settings-update-security.png)

1. 选择 "**恢复**"，然后在 "**重置设备**" 下，选择 "**开始**"。

   ![显示 Surface Hub 的 "设置" 应用中的 "重置设备" 选项的图像。](images/sh-settings-reset-device.png)

   重置过程完成后，Surface Hub 将再次启动[第一个 run 程序](first-run-program-surface-hub.md)。 如果重置过程遇到问题，它会将 Surface Hub 回退到以前存在的操作系统映像，然后显示 "欢迎" 屏幕。

<span id="cloud-recovery" />

## 从云中恢复 Surface Hub

如果由于某种原因，Surface Hub 变得不可用，您仍然可以从云中恢复它，而无需 Microsoft 支持部门的帮助。 Surface Hub 可以从云中下载全新的操作系统映像，并使用该映像重新安装操作系统。

在以下情况下，您可能必须使用此类型的恢复过程：

- [Surface Hub 或其相关帐户进入了不稳定状态](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub 已锁定](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>**从云进程恢复**需要打开 internet 连接（无代理或其他身份验证）。 建议使用以太网连接。

### 恢复处于错误状态的 Surface Hub

如果设备帐户处于不稳定状态或管理员帐户遇到问题，则可以使用 "设置" 应用启动云恢复过程。 只有在[设备重置](#reset-a-surface-hub)过程不能解决问题时，才应使用云恢复过程。

1. 在 Surface Hub 上，选择 "**设置** &gt; **更新 & 安全** &gt; **恢复**"。

1. 在 "**从云恢复**" 下，选择 "**立即重启**"。

   ![从云中恢复](images/recover-from-the-cloud.png)

### 恢复锁定的 Surface Hub

在极少数情况下，会话结束后，Surface Hub 在清理用户和应用数据时会遇到错误。 发生这种情况时，设备将自动重新启动，并再次尝试该操作。 但是，如果此操作重复失败，设备将自动锁定以保护用户数据。 若要解除锁定，必须[重置设备](#reset-a-surface-hub)，如果不起作用，请从云恢复它。

1. 找到 Surface Hub 底部的电源开关。 电源开关位于电源线连接旁边。 有关 power 开关的详细信息，请参阅[Surface Hub 网站准备指南（PDF）](surface-hub-site-readiness-guide.md)。

1. 当 Surface Hub 显示 "欢迎" 屏幕时，请使用 power 开关关闭 Surface Hub。

1. 使用 power 开关重新打开 Surface Hub。 设备将启动并显示 Surface Hub 徽标屏幕。 当您在 Surface Hub 徽标下看到旋转点时，请使用 power 开关再次关闭 Surface Hub。  

1. 重复步骤 3 3 时间，或直到 Surface Hub 显示 "正在准备自动修复" 消息。 显示此消息后，Surface Hub 将显示 Windows RE 屏幕。

1. 选择 "**高级选项**"。

1. 选择 **"从云恢复"**。 （可选，您可以选择 "**重置**"。 但是，**从云恢复**是推荐的方法。

   ![从云中恢复](images/recover-from-cloud.png)
1. 如果系统提示您输入 Bitlocker 密钥，请执行下列操作之一：

   - 若要保留 Bitlocker 在 Surface Hub 上保护的信息，请输入 Bitlocker 密钥。
   - 若要放弃受保护的信息，请选择 "**跳过此驱动器**"  

1. 出现提示时，选择 "**重新安装**"。

    ![重新安装](images/reinstall.png)

1. 若要对磁盘进行重新分区，请选择 **"是"**。

   ![重新分区](images/repartition.png)

   首先，恢复过程从云中下载操作系统映像。  

   ![正在下载 97&](images/recover-progress.png)

   下载完成后，恢复过程根据你选择的选项恢复 Surface Hub。
   

## 联系支持人员

如果有疑问或需要帮助，您可以[创建支持请求](https://support.microsoft.com/supportforbusiness/productselection)。


## 相关主题

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)

---
title: 重置或恢复 Surface Hub
description: 介绍 Surface Hub 的重置和恢复过程，并提供说明。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重置 Surface Hub， 恢复
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73c7cf5a387bf7506bb69f62100171df4d94ad2d
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304815"
---
# 重置或恢复 Surface Hub

本文介绍如何重置或恢复 Microsoft Surface Hub。  

[重置 Surface Hub](#reset-a-surface-hub) 会将其操作系统返回到上一次累积 Windows 更新，并删除所有本地用户文件和配置信息。 删除的信息包括：

- 设备帐户
- 设备本地管理员的帐户信息
- 域加入或 Azure AD 加入信息
- 移动设备管理 (MDM) 注册信息
- 使用 MDM 或"设置"应用设置的配置信息

[从云中恢复 Surface Hub](#recover-a-surface-hub-from-the-cloud) 也会删除此信息。 此外，Surface Hub 下载并安装新的操作系统映像。 你可以指定恢复过程是否保留存储在 Surface Hub 上的其他信息。 如果需要恢复 Surface Hub，则 [Surface Hub](surface-hub-recovery-tool.md) 恢复工具会使用相同的操作系统映像，这两个选项均无法用于该 Surface Hub。

## 重置 Surface Hub

出于以下原因，你可能必须重置 Surface Hub：

- 你正在重新设置设备以用于新的会议空间，并且想要重新配置它。
- 想要更改本地管理设备的方式。
- 设备帐户或管理员帐户的用户名或密码已丢失。
- 安装更新后，设备性能会降低。

在重置过程中，如果长时间看到空白屏幕，请稍等，不要执行任何操作。

> [!WARNING]
> 设备重置过程最多可能需要六个小时。 在进程完成之前，不要关闭或拔下 Surface Hub。 如果中断该过程，设备将变得不可操作。 设备需要担保服务才能再次正常工作。

1. 在 Surface Hub 上，打开**设置**。

   ![显示 Surface Hub 的"设置"应用的图像。](images/sh-settings.png)

2. 选择 **"&安全"。**

   ![显示 Surface Hub &"设置"应用中的"更新和安全"组的图像。](images/sh-settings-update-security.png)

3. 选择 **"** 恢复"，然后在"**重置设备**"下选择 **"开始使用"。**

   > [!IMPORTANT]
   > 在重置设备之前，请确保你的 BitLocker 密钥可用，因为稍后会提示你提供它。 若要了解更多信息，请参阅["保存 BitLocker 密钥"。](save-bitlocker-key-surface-hub.md) 当集线器重新启动到恢复分区时，它将提示你输入 BitLocker 密钥。 跳过该提示将导致重置失败。
   
   ![显示 Surface Hub 的"设置"应用中的"重置设备"选项的图像。](images/sh-settings-reset-device.png)

   重置过程完成后，Surface Hub 将再次启动 [第一个运行](first-run-program-surface-hub.md) 程序。 如果重置过程遇到问题，它会将 Surface Hub 回滚到以前存在的操作系统映像，然后显示欢迎屏幕。

<span id="cloud-recovery" />

## 从云中恢复 Surface Hub

如果由于某种原因 Surface Hub 变得不可用，你仍然可以从云中恢复它，而无需 Microsoft 支持人员的帮助。 Surface Hub 可以从云中下载全新的操作系统映像，并使用该映像重新安装其操作系统。

在下列情况下，您可能必须使用此类型的恢复过程：

- [Surface Hub 或其相关帐户已进入不稳定状态](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub 已锁定](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>" **从云恢复"过程** 需要有线连接，该连接提供开放 Internet 连接， (代理或其他身份验证提示) 。

### 恢复处于错误状态的 Surface Hub

如果设备帐户进入不稳定状态或管理员帐户遇到问题，可以使用"设置"应用启动云恢复过程。 只有在设备重置过程无法解决问题时，才应该[](#reset-a-surface-hub)使用云恢复过程。

1. 在 Surface Hub 上，选择 **"** 设置 &gt; **更新&安全** &gt; **恢复"。**

2. 在 **"从云中恢复"下**，选择 **"立即重启"。**

   ![从云中恢复](images/recover-from-the-cloud.png)

### 恢复锁定的 Surface Hub

在极少数情况下，会话结束后，Surface Hub 在清理用户和应用数据时会遇到错误。 发生这种情况时，设备会自动重新启动并再次尝试该操作。 但如果此操作重复失败，设备将自动锁定以保护用户数据。 若要解锁它，你必须 [重置](#reset-a-surface-hub) 设备，如果不起作用，则从云中恢复它。

1. 找到 Surface Hub 底部的电源开关。 电源开关位于电缆连接旁边。 有关电源开关详细信息，请参阅 Surface Hub 站点准备指南 ([PDF) 。 ](surface-hub-site-readiness-guide.md)

2. 当 Surface Hub 显示欢迎屏幕时，使用电源开关关闭 Surface Hub。

3. 使用电源开关重新打开 Surface Hub。 设备启动并显示 Surface Hub 徽标屏幕。 当你在 Surface Hub 徽标下看到旋转点时，请使用电源开关再次关闭 Surface Hub。  

4. 重复步骤 3 三次，或直到 Surface Hub 显示"正在准备自动修复"消息。 显示此消息后，Surface Hub 将显示 Windows RE 屏幕。

5. 选择 **高级选项**。

6. 选择 **"从云中恢复"。**  (，可以选择"重置 **"。** 但是 **，从云中恢复** 是推荐的方法。) 

   ![从云中恢复](images/recover-from-cloud.png)
7. 如果系统提示你输入 Bitlocker 密钥，请执行下列操作之一：

   - 若要在 Surface Hub 上保留 Bitlocker 保护的信息，请输入 Bitlocker 密钥。
   - 若要放弃受保护的信息，请选择" **跳过此驱动器"**  

8. 当系统提示时，选择"重新安装 **"。**

    ![重新安装](images/reinstall.png)

9. 若要重新分区磁盘，请选择"**是"。**

   ![重新分区](images/repartition.png)

   首先，恢复过程从云中下载操作系统映像。  

   ![正在下载 97&](images/recover-progress.png)

   下载完成后，恢复过程会根据所选的选项还原 Surface Hub。
   

## 联系支持人员

如果你有问题或需要帮助，可以创建 [支持请求](https://support.microsoft.com/supportforbusiness/productselection)。


## 相关主题

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)

---
title: 如何在 Surface Hub 上使用 BitLocker 云恢复
description: 如何在 Surface Hub 上使用 BitLocker 云恢复
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: 辅助功能设置, “设置”应用, 轻松使用
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830830"
---
# 摘要

本文介绍当 Surface Hub 设备上的 BitLocker 意外提示时，如何使用云恢复功能。

> [!NOTE]
> 只有当 BitLocker 恢复密钥不可用时，才应执行这些步骤。

> [!WARNING]
> * 此恢复过程将删除内部驱动器的内容。 如果进程失败，则内部驱动器将完全无法使用。 如果出现这种情况，您必须记录 Microsoft 的服务请求以解决问题。
> * 恢复过程完成后，设备将重置为出厂设置，并返回到其 "开箱" 体验状态。
> * 恢复后，必须完全重新配置 Surface Hub。

> [!IMPORTANT]
> 此过程需要打开不使用代理或其他身份验证方法的 Internet 连接。

##  <a name="cloud-recovery-process"></a>云恢复过程

若要执行云恢复，请按照下列步骤操作：

1. 选择**按 Esc 以获取更多恢复选项**。

   ![转义的屏幕截图](images/01-escape.png)

1. 选择 "**跳过此驱动器**"。

   ![跳过此驱动器的屏幕截图](images/02-skip-this-drive.png)

1. 选择 **"从云恢复"**。

   ![从云恢复的屏幕截图](images/03-recover-from-cloud.png)

1. 选择 **"是"**。

   !["是" 的屏幕截图](images/04-yes.png)

1. 选择 "**重新安装**"。

   ![重新安装的屏幕截图](images/05a-reinstall.png)

   ![下载的屏幕截图](images/05b-downloading.png)

1. 完成云恢复过程后，通过使用**全新使用体验**开始重新配置。

   ![现成的屏幕截图](images/06-out-of-box.png)

##  <a name="something-went-wrong-error-message"></a>"出现了错误" 错误消息

此错误通常由恢复下载期间出现的网络问题引起。 如果出现此问题，请不要关闭集线器，因为您无法重新启动它。 如果收到此错误消息，请返回到 "从云恢复" 步骤，然后重新启动恢复过程。

1. 选择 "**取消**"。

   ![取消的屏幕截图](images/07-cancel.png)

1. 选择 "**疑难解答**"。

   ![疑难解答的屏幕截图](images/08-troubleshoot.png)

1. 选择 **"从云恢复"**。

   ![从云恢复的屏幕截图](images/09-recover-from-cloud2.png)

1. 如果出现 "**有线网络未找到**" 错误，请选择 "**取消**"，然后让 Surface Hub 重新发现有线网络。

   ![找不到有线网络的屏幕截图](images/10-cancel.png)
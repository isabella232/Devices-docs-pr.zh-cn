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
ms.openlocfilehash: e220be7d4613fcb6a14180e482dc4f2c66a5ddc8
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911027"
---
# <a name="summary"></a>摘要

本文介绍如何在 BitLocker 在设备上意外提示你使用云Surface Hub函数。

> [!NOTE]
> 只有在 BitLocker 恢复密钥不可用时，才应执行这些步骤。

> [!WARNING]
> * 此恢复过程将删除内部驱动器的内容。 如果进程失败，内部驱动器将变得完全不可用。 如果发生这种情况，您必须向 Microsoft 记录服务请求以解决问题。
> * 恢复过程完成后，设备将重置为出厂设置并返回到其开箱即用体验状态。
> * 恢复后，Surface Hub完全重新配置。

> [!IMPORTANT]
> 此过程需要不使用代理或其他身份验证方法的开放式 Internet 连接。

## <a name="cloud-recovery-process"></a>云恢复过程

若要执行云恢复，请按照以下步骤操作：

1. 选择 **按 Esc 可了解更多恢复选项**。

   ![Escape 的屏幕截图。](images/01-escape.png)

1. 选择 **跳过此驱动器**。

   ![跳过此驱动器的屏幕截图。](images/02-skip-this-drive.png)

1. 选择 **"从云中恢复"。**

   ![从云中恢复的屏幕截图。](images/03-recover-from-cloud.png)

1. 选择 **"是"。**

   !["是"的屏幕截图。](images/04-yes.png)

1. 选择 **重新安装**。

   ![重新安装的屏幕截图。](images/05a-reinstall.png)

   ![下载屏幕截图。](images/05b-downloading.png)

1. 完成云恢复过程后，使用"开箱即用体验" **开始重新配置**。

   ![开箱即用屏幕截图。](images/06-out-of-box.png)

## <a name="something-went-wrong-error-message"></a>"出现错误"错误消息

此错误通常是由恢复下载期间发生的网络问题导致的。 发生此问题时，请勿关闭 Hub，因为无法重新启动它。 如果收到此错误消息，请返回到"从云中恢复"步骤，然后重新启动恢复过程。

1. 选择 **取消**。

   ![Cancel 的屏幕截图。](images/07-cancel.png)

1. 选择 **疑难解答**。

   ![疑难解答的屏幕截图。](images/08-troubleshoot.png)

1. 选择 **"从云中恢复"。**

   ![从云中恢复的屏幕截图。](images/09-recover-from-cloud2.png)

1. 如果**未找到有线网络**错误发生，请选择"取消"，然后**** 让Surface Hub重新发现有线网络。

   ![未找到有线网络的屏幕截图。](images/10-cancel.png)
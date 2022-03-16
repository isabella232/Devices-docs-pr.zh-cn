---
title: 重置和恢复Surface Hub
description: 介绍重置和恢复过程，Surface Hub说明。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重置Surface Hub，恢复
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: f0292d4c2ec599ba620ab87930fbecf3bab9e078
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449275"
---
# <a name="reset-and-recovery-for-surface-hub"></a>重置和恢复Surface Hub

本文介绍如何重置Microsoft Surface Hub。  

[重置Surface Hub会将其](#reset-a-surface-hub)操作系统返回到上一次累积更新Windows，并删除所有本地用户文件和配置信息。 删除的信息包括以下内容：

- 设备帐户
- 设备本地管理员的帐户信息
- 域加入或Azure AD加入信息
- 移动设备管理 (MDM) 注册信息
- 使用 MDM 或 设置 应用设置的配置信息

您可以指定恢复过程是否保留存储在Surface Hub。 如果无法使用重置选项，Surface Hub恢复工具可以直接[](surface-hub-recovery-tool.md)对Surface Hub映像。

## <a name="reset-a-surface-hub"></a>重置Surface Hub

出于以下原因，Surface Hub重置您的密码：

- 你正在将设备重新用于新的会议空间，并且想要重新配置它。
- 想要更改本地管理设备的方式。

在重置过程中，如果长时间看到空白屏幕，请稍等，不要执行任何操作。

> [!WARNING]
> 设备重置过程最多可能需要六个小时。 在进程完成之前，Surface Hub或拔下设备。 如果中断该过程，设备将变得不可操作。 设备需要担保服务才能再次正常运行。

1. 在 Surface Hub 上，打开**设置**。

   > [!div class="mx-imgBorder"]
   > ![显示适用于设置应用Surface Hub。](images/sh-settings.png)

2. 选择 **"更新&安全性"**。

   > [!div class="mx-imgBorder"]
   > ![显示应用更新&安全组设置图像Surface Hub。](images/sh-settings-update-security.png)

3. 选择 **"恢复**"，然后在"重置 **设备"下**，选择 **"开始使用"**。

   > [!IMPORTANT]
   > 在重置设备之前，请确保你的 BitLocker 密钥可用，因为稍后会提示你提供它。 若要了解更多信息，请参阅 [保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。 当集线器重新启动到恢复分区时，它将提示你输入 BitLocker 密钥。 跳过该提示将导致重置失败。
   
   > [!div class="mx-imgBorder"]
   > ![显示"重置设备"选项的图像设置应用Surface Hub。](images/sh-settings-reset-device.png)

   重置过程完成后，Surface Hub再次[启动第一个运行](first-run-program-surface-hub.md)程序。 如果重置过程遇到问题，它会将Surface Hub回滚到以前存在的操作系统映像，然后显示欢迎屏幕。

## <a name="recover-a-locked-surface-hub"></a>恢复锁定的 Surface Hub

如果由于某种原因Surface Hub无法使用，并且无法从 设置 应用启动重置，则如果你拥有 BitLocker 恢复密钥，你仍然可以重置 Surface Hub。

1. 找到电源开关底部的Surface Hub。 电源开关位于电缆连接旁边。 有关电源开关详细信息，请参阅SURFACE HUB[准备情况指南 (PDF) ](surface-hub-site-readiness-guide.md)。

2. 当Surface Hub显示欢迎屏幕时，使用电源开关关闭Surface Hub。

3. 使用电源开关打开Surface Hub电源。 设备启动并显示"Surface Hub徽标"屏幕。 当你在徽标下看到旋转Surface Hub，请使用电源开关再次Surface Hub按钮。  

4. 重复步骤 3 两次，或Surface Hub"正在准备自动修复"消息。 显示此消息后，Surface Hub显示Windows RE屏幕。
 
5. 选择“**重置**”。

6. 选择 **"本地重新安装"。**

7. 选择 **"完全清理驱动器"。**
 
   ![恢复并完全清理驱动器。](images/recover-fully-clean-drive.png)

8. 将询问 **你准备好重置此设备了吗？**。 选择“**重置**”。 
   
   ![恢复并确认重置。](images/recover-confirm-reset.png)


## <a name="contact-support"></a>联系支持人员

如果有任何疑问或需要帮助，可以创建 [支持请求](https://support.microsoft.com/supportforbusiness/productselection)。


## <a name="related-topics"></a>相关主题

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)

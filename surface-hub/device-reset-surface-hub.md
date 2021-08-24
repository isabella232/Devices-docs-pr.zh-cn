---
title: 重置或恢复Surface Hub
description: 介绍用于重置和恢复Surface Hub并提供说明。
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
ms.openlocfilehash: ee8ac1129aab34afeb3be783133681fe80434831
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911017"
---
# <a name="reset-or-recover-a-surface-hub"></a>重置或恢复Surface Hub

本文介绍如何重置或恢复Microsoft Surface Hub。  

[重置Surface Hub](#reset-a-surface-hub)会将其操作系统返回到上一次累积更新Windows，并删除所有本地用户文件和配置信息。 删除的信息包括以下内容：

- 设备帐户
- 设备本地管理员的帐户信息
- 域加入或 Azure AD 加入信息
- 移动设备管理 (MDM) 注册信息
- 使用 MDM 或 设置 应用设置的配置信息

[从云Surface Hub也会](#recover-a-surface-hub-from-the-cloud)删除此信息。 此外，Surface Hub下载并安装新的操作系统映像。 您可以指定恢复过程是否保留存储在Surface Hub。 如果需要恢复两个选项[均](surface-hub-recovery-tool.md)Surface Hub的映像，Surface Hub恢复工具会使用相同的操作系统映像。

## <a name="reset-a-surface-hub"></a>重置Surface Hub

由于以下原因，Surface Hub重置密码：

- 你正在将设备重新用于新的会议空间，并且想要重新配置它。
- 想要更改本地管理设备的方式。
- 设备帐户或管理员帐户的用户名或密码已丢失。
- 安装更新后，设备性能会降低。

在重置过程中，如果长时间看到空白屏幕，请稍等，不要执行任何操作。

> [!WARNING]
> 设备重置过程最多可能需要六个小时。 在进程完成之前，Surface Hub或拔下设备。 如果中断该过程，设备将变得不可操作。 设备需要担保服务才能再次正常运行。

1. 在 Surface Hub 上，打开**设置**。

   > [!div class="mx-imgBorder"]
   > ![显示适用于设置应用Surface Hub。](images/sh-settings.png)

2. 选择 **"更新&安全"。**

   > [!div class="mx-imgBorder"]
   > ![显示应用更新&安全组设置图像Surface Hub。](images/sh-settings-update-security.png)

3. 选择 **"恢复**"，然后在"重置**设备"下**，选择 **"开始使用"。**

   > [!IMPORTANT]
   > 在重置设备之前，请确保你的 BitLocker 密钥可用，因为稍后会提示你提供它。 若要了解更多信息，请参阅 [保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。 当集线器重新启动到恢复分区时，它将提示你输入 BitLocker 密钥。 跳过该提示将导致重置失败。
   
   > [!div class="mx-imgBorder"]
   > ![显示"重置设备"选项的图像设置应用Surface Hub。](images/sh-settings-reset-device.png)

   重置过程完成后，Surface Hub再次[启动第一个运行](first-run-program-surface-hub.md)程序。 如果重置过程遇到问题，它会将Surface Hub回滚到以前存在的操作系统映像，然后显示欢迎屏幕。

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a>从云中恢复 Surface Hub

如果由于某些原因Surface Hub不可用，你仍然可以从云中恢复它，而无需 Microsoft 支持人员的帮助。 用户可以Surface Hub云中下载全新的操作系统映像，然后使用该映像重新安装其操作系统。

在下列情况下，您可能必须使用此类型的恢复过程：

- [Surface Hub帐户已进入不稳定状态](#recover-a-surface-hub-in-a-bad-state)
- [锁定Surface Hub](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>从 **云中恢复过程** 需要有线连接，该连接提供开放 internet 连接 (代理或其他身份验证) 。

### <a name="recover-a-surface-hub-in-a-bad-state"></a>恢复处于错误状态的 Surface Hub

如果设备帐户进入不稳定状态或管理员帐户遇到问题，可以使用 设置 应用启动云恢复过程。 应仅在设备重置过程未解决问题时使用云[](#reset-a-surface-hub)恢复过程。

1. On your Surface Hub， select**设置** &gt; **Update & security** &gt; **Recovery**.

2. 在 **"从云中恢复"下**，选择 **"立即重启"。**

   > [!div class="mx-imgBorder"]
   > ![从云中恢复。](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a>恢复锁定的 Surface Hub

在极少数情况下，会话结束后，Surface Hub 在清理用户和应用数据时会遇到错误。 发生这种情况时，设备将自动重新启动并再次尝试该操作。 但如果此操作重复失败，设备将自动锁定以保护用户数据。 若要解锁它，你必须 [重置设备](#reset-a-surface-hub) ，或者，如果不起作用，则从云中恢复它。

1. 找到电源开关底部的Surface Hub。 电源开关位于电缆连接旁边。 有关电源开关详细信息，请参阅 PDF Surface Hub[站点准备指南 (PDF) 。 ](surface-hub-site-readiness-guide.md)

2. 当Surface Hub显示欢迎屏幕时，使用电源开关关闭Surface Hub。

3. 使用电源开关打开电源Surface Hub电源。 设备将启动并显示Surface Hub徽标屏幕。 当你在徽标下看到旋转Surface Hub，请使用电源开关再次Surface Hub按钮。  

4. 重复步骤 3 三次，或Surface Hub"正在准备自动修复"消息。 显示此消息后，Surface Hub显示Windows RE屏幕。
 
5. 选择“**重置**”。 

6. 如果系统提示你输入 BitLocker 密钥，请执行下列操作之一：
   - 若要在 BitLocker 保护的密钥上保留Surface Hub，请输入 BitLocker 密钥。
   - 若要放弃受保护的信息，请选择跳过此驱动器

7. 选择 **"云下载"。** 

   ![云下载。](images/recover-cloud-download.png)

   >[!IMPORTANT]
   >如果收到指示无法下载的错误消息，**** 请选择"**取消**"，然后**再次**重置。

8. 选择 **"完全清理驱动器"。**
 
   ![恢复并完全清理驱动器。](images/recover-fully-clean-drive.png)

9. 将询问你**准备好重置此设备了吗？。** 选择“**重置**”。 
   
   ![恢复并确认重置。](images/recover-confirm-reset.png)

10. 下载开始，恢复过程指示 **重置此设备**。

    ![恢复。](images/recover-in-progress.png)

## <a name="contact-support"></a>联系支持人员

如果有任何疑问或需要帮助，可以创建 [支持请求](https://support.microsoft.com/supportforbusiness/productselection)。


## <a name="related-topics"></a>相关主题

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)

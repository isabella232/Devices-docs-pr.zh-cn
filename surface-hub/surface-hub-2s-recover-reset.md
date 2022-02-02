---
title: 重置和恢复 Surface Hub 2S
description: 了解如何恢复和重置 Surface Hub 2S。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 6ba5677fabd3d309875cf339ec1432e99529b23b
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338085"
---
# <a name="reset-and-recovery-for-surface-hub-2s"></a>重置和恢复 Surface Hub 2S

如果在使用 2S Surface Hub时遇到问题，可以将设备重置为出厂设置，或者使用 USB 驱动器还原。

首先，使用管理员凭据Surface Hub 2S 登录，打开 **设置** 应用，选择"&**安全**"，然后选择"**恢复"**。

## <a name="reset-the-device"></a>重置设备

   > [!IMPORTANT]
   > 在重置设备之前，请确保你的 BitLocker 密钥可用，因为稍后会提示你提供它。 若要了解更多信息，请参阅 [保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。

1. 若要重置设备，请选择"**入门"**。

2. 当出现 **"准备重置此设备"窗口时** ，选择"重置 **"**。
  
   > [!TIP]
   > 当集线器重新启动到恢复分区时，它将提示你输入 BitLocker 密钥。 跳过该提示将导致重置失败。 输入 BitLocker 密钥后，Hub 会从恢复分区重新安装操作系统。 这可能需要一小时才能完成。
  
3. 若要重新配置设备，请运行第一次安装程序。

4. 如果使用移动设备或其他移动设备Microsoft Intune管理设备，请停用并删除以前的记录，然后重新注册新设备。 有关详细信息，请参阅使用擦除、停用或 [手动取消注册设备来删除设备](/intune/devices-wipe)。

   > [!div class="mx-imgBorder"]
   > ![*重置和恢复 Surface Hub 2S*。](images/sh2-reset.png)
   <br/>*图 1. 重置和恢复 Surface Hub 2S*

## <a name="recover-surface-hub-2s-by-using-a-usb-recovery-drive"></a>使用 usb Surface Hub驱动器恢复 2S

这是 Surface Hub 2S 中的新增功能，现在可以使用恢复映像重新安装设备。

### <a name="recovery-from-a-usb-drive"></a>从 U 盘恢复

使用 Surface Hub 2S，可以使用恢复映像重新安装设备。 通过执行此操作，如果你丢失了 BitLocker 密钥，或者如果你不再拥有该应用的管理员凭据，你可以将设备重新安装到出厂设置设置。

>[!TIP]
>使用存储为 8 GB 或 16 GB、格式为 FAT32 的 USB 3.0 驱动器。

1. 从单独的电脑中，从 surface 恢复.zip下载文件恢复映像，然后返回到[](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s)这些说明。

2. 在任务栏上的搜索框中，输入**恢复驱动器**，然后从结果中选择创建**** 恢复**驱动器或恢复**驱动器。 你可能需要输入管理员密码或确认你的选择。

3. 在" **用户帐户控制"框中** ，选择" **是"**。

4. 确保清除" **将系统文件备份到恢复驱动器** "复选框，然后选择"下一步 **"**。

5. 选择你的 U 盘，然后选择"下一步 **>创建"**。  某些实用程序需要复制到恢复驱动器，因此这可能需要几分钟时间。

6. 恢复驱动器准备就绪后，选择"完成 **"**。

7. 双击之前下载.zip恢复映像文件以打开它。

8. 从恢复映像文件夹中选择所有文件，将它们复制到 USB 驱动器的根目录，然后选择选择 **替换目标中的文件**。

9. 文件复制完成后，选择任务栏上的"安全 **删除硬件** "和"弹出媒体"图标并删除 U 盘。

10. 连接 USB 驱动器连接到 2S 上的任意 USB-C 或 USB-A Surface Hub端口。 关闭集线器，然后从 USB 驱动器启动。

#### <a name="boot-surface-hub-from-usb-drive"></a>从SURFACE HUB U 盘启动文件

>[!NOTE]
>如果设备已拔出或遇到突然断电或断电，请在尝试从 USB 启动之前等待至少 15 秒。

1. 在按"降低音量"按钮时，按"电源"按钮。

2. 继续按这两个按钮，直到看到Windows徽标。

3. 释放电源按钮，但继续按住"降低音量"按钮，直到安装 UI 开始。

   ![*使用音量降低和电源按钮启动恢复*。](images/sh2-keypad.png)
   <br>*图 2. 音量和电源按钮*

4. 在语言选择屏幕上，选择适用于你的 2S Surface Hub语言。

5. 选择 **"从驱动器恢复"和****"完全清理驱动器"**，然后选择"恢复 **"**。 如果系统提示你输入 BitLocker 密钥，请选择跳过 **此驱动器**。 Surface Hub 2S 重新启动多次，可能需要一小时或更完整的时间才能完成恢复过程。

6. 当出现首次设置屏幕时，删除 USB 驱动器。

## <a name="contact-support"></a>联系支持人员

如果有任何疑问或需要帮助，可以创建 [支持请求](https://support.microsoft.com/supportforbusiness/productselection)。

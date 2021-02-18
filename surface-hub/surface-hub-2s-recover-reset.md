---
title: Surface Hub 2S 的重置和恢复
description: 了解如何恢复和重置 Surface Hub 2S。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 64ceee291d3d3e067f581707d9431fa92398c785
ms.sourcegitcommit: ecb4909c091e69b7bdb1faacfc8c34b480dc884b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11342972"
---
# Surface Hub 2S 的重置和恢复

如果 Surface Hub 2S 遇到问题，可以使用 USB 驱动器将设备重置为出厂设置或还原。

若要开始，使用管理员凭据登录 Surface Hub 2S，打开"**** 设置"应用，选择"&**安全**"，然后选择"**恢复"。**

## 重置设备

   > [!IMPORTANT]
   > 在重置设备之前，请确保你的 BitLocker 密钥可用，因为稍后会提示你输入它。 若要了解更多信息，请参阅["保存 BitLocker 密钥"。](save-bitlocker-key-surface-hub.md)

1. 若要重置设备，请选择"**开始使用"。**

2. 当显示 **"准备重置此设备"** 窗口时，选择"**重置"。** 
  
   > [!IMPORTANT]
   > 当集线器重新启动到恢复分区时，它将提示你输入 BitLocker 密钥。 跳过该提示将导致重置失败。 输入 BitLocker 密钥后，Hub 会从恢复分区重新安装操作系统。 这可能需要一个小时才能完成。
  
3. 若要重新配置设备，请运行第一次安装程序。

4. 如果使用 Microsoft Intune 或其他移动设备管理解决方案管理设备，请停用并删除以前的记录，然后重新注册新设备。 有关详细信息，请参阅使用擦除、停用或手动注销设备来 [删除设备](https://docs.microsoft.com/intune/devices-wipe)。

   > [!div class="mx-imgBorder"]
   > ![*Surface Hub 2S 的重置和恢复*](images/sh2-reset.png)
   <br/>*图 1. Surface Hub 2S 的重置和恢复* 

## 使用 USB 恢复驱动器恢复 Surface Hub 2S

Surface Hub 2S 中的新增功能，现在可以使用恢复映像重新安装设备。

### 从 U 盘恢复

使用 Surface Hub 2S，可以使用恢复映像重新安装设备。 通过执行此操作，如果你丢失了 BitLocker 密钥，或者如果你不再具有"设置"应用的管理员凭据，你可以将设备重新安装到出厂设置。

>[!NOTE]
>使用存储大小为 8 GB 或 16 GB 的 USB 3.0 驱动器，格式化为 FAT32。

1. 从单独的电脑中，从 [Surface Recovery](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 网站下载 .zip 文件恢复映像，然后返回到这些说明。 

1. 在任务栏上的搜索框中，输入**恢复驱动器**，然后从结果中选择"创建**** 恢复**驱动器"或**"恢复驱动器"。 你可能需要输入管理员密码或确认你的选择。

1. 在 **"用户帐户控制"框中**，选择 **"是"。**

1. 确保清除"**将系统文件备份到恢复**驱动器"复选框，然后选择"下一**步"。**

1. 选择你的 USB 驱动器，然后选择"下一>**创建"。**  某些实用程序需要复制到恢复驱动器，因此这可能需要几分钟时间。

1. 恢复驱动器准备就绪后，选择"完成 **"。**

1. 双击之前下载的恢复映像 .zip 文件以打开它。

1. 从恢复映像文件夹中选择所有文件，将其复制到 USB 驱动器的根目录，然后选择"选择 **"替换目标中的文件**。

1. 文件复制完成后，选择任务栏上的" **安全删除硬件** 和弹出媒体"图标，然后删除 U 盘。

1. 将 USB 驱动器连接到 Surface Hub 2S 上的任何 USB-C 或 USB-A 端口。

1. 关闭集线器，然后执行以下步骤从 USB 驱动器启动：

   1. 按下"音量"按钮时，按电源按钮。
   1. 继续按这两个按钮，直到看到 Windows 徽标。
   1. 释放电源按钮，但继续按住音量降低按钮，直到安装 UI 开始。

      ![*使用音量降低和电源按钮启动恢复*](images/sh2-keypad.png)
      <br>*图 2. "音量"和"电源"按钮*

1. 在语言选择屏幕上，选择 Surface Hub 2S 的显示语言。

1. 选择 **"从驱动器恢复**并**完全清理驱动器"，** 然后选择"**恢复"。** 如果系统提示你输入 BitLocker 密钥，请选择 **"跳过此驱动器"。** Surface Hub 2S 重新启动多次，大约需要 30 分钟才能完成恢复过程。

首次显示设置屏幕时，删除 USB 驱动器。

## 联系支持人员

如果你有问题或需要帮助，可以创建 [支持请求](https://support.microsoft.com/supportforbusiness/productselection)。

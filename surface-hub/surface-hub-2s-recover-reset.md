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
ms.openlocfilehash: 88f5d912f7505aecaa5bd7ba659acab2d6c4fa1a
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304805"
---
# Surface Hub 2S 的重置和恢复

如果你遇到 Surface Hub 2S 问题，你可以将设备重置为出厂设置，或者使用 USB 驱动器进行还原。

若要开始，使用管理员凭据登录 Surface Hub 2S，打开"**** 设置"应用，选择"&**安全"，** 然后选择"**恢复"。**

## 重置设备

   > [!IMPORTANT]
   > 在重置设备之前，请确保你的 BitLocker 密钥可用，因为稍后会提示你提供它。 若要了解更多信息，请参阅["保存 BitLocker 密钥"。](save-bitlocker-key-surface-hub.md)

1. 若要重置设备，请选择"**开始使用"。**

2. 当显示 **"准备重置此设备"** 窗口时，选择"重置 **"。** 
  
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
>使用具有 8 GB 或 16 GB 存储空间的 USB 3.0 驱动器，格式化为 FAT32。

1. 从单独的电脑上，从 [Surface Recovery](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 网站下载 .zip 文件恢复映像，然后返回到这些说明。 

1. 将下载的文件解压缩到 USB 驱动器的根目录。  

1. 将 USB 驱动器连接到 Surface Hub 2S 上的任何 USB-C 或 USB-A 端口。

1. 关闭设备：

   1. 按下音量降低按钮时，按电源按钮。
   1. 继续按这两个按钮，直到看到 Windows 徽标。
   1. 释放电源按钮，但继续按住音量降低按钮，直到安装 UI 开始。

      ![*使用音量降低和电源按钮启动恢复*](images/sh2-keypad.png)
      <br>*图 2. 音量和电源按钮*

1. 在语言选择屏幕上，选择 Surface Hub 2S 的显示语言。

1. 选择 **"从驱动器恢复"并****完全清理驱动器**，然后选择"**恢复"。** 如果系统提示你输入 BitLocker 密钥，请选择 **"跳过此驱动器"。** Surface Hub 2S 重新启动多次，大约需要 30 分钟才能完成恢复过程。

首次显示设置屏幕时，删除 USB 驱动器。

## 联系支持人员

如果你有问题或需要帮助，可以创建 [支持请求](https://support.microsoft.com/supportforbusiness/productselection)。

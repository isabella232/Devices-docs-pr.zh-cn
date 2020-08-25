---
title: Surface Hub 2 的重置和恢复
description: 了解如何恢复和重置 Surface Hub 2。
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
ms.openlocfilehash: 7d79fab22b62e6ef29832be6241c484e9caf72e0
ms.sourcegitcommit: 537fa38bdd21fcd679af0764e734f4b8efb6a03f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "10959944"
---
# Surface Hub 2 的重置和恢复

如果你遇到 Surface Hub 2 的问题，你可以将设备重置为出厂设置或使用 USB 驱动器还原。

若要开始，请通过管理员凭据登录到 Surface Hub 2，打开 " **设置** " 应用，选择 " **更新 & 安全**"，然后选择 " **恢复**"。

## 重置设备

1. 若要重置设备，请选择 " **开始**"。

2. 出现 " **准备重置此设备** " 窗口时，选择 " **重置**"。 
  
   > [!NOTE]
   > Surface Hub 2 从恢复分区重新安装操作系统。 这可能需要长达一小时才能完成。
  
3. 若要重新配置设备，请运行第一次设置程序。

4. 如果你使用 Microsoft Intune 或其他移动设备管理解决方案管理设备，请停用并删除以前的记录，然后重新注册新设备。 有关详细信息，请参阅 [使用擦除、停用或手动通过设备删除设备](https://docs.microsoft.com/intune/devices-wipe)。

> [!div class="mx-imgBorder"]
> ![* Surface Hub 2 的重置和恢复 *](images/sh2-reset.png)
<br/>*图 1. Surface Hub 2 的重置和恢复* 

## 使用 USB 恢复驱动器恢复 Surface Hub 2

新增在 Surface Hub 2 中，现在可以使用恢复映像重新安装设备。

### 从 USB 驱动器恢复

使用 Surface Hub 2，您可以使用恢复映像重新安装该设备。 通过执行此操作，你可以将设备重新安装到出厂设置（如果你丢失 BitLocker 密钥），或者你不再拥有设置应用的管理员凭据。

>[!NOTE]
>使用具有 8 GB 或 16 GB 存储空间的 USB 3.0 驱动器，格式为 FAT32。

1. 从单独的 PC 上，从 [Surface recovery 网站](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 下载 .zip 文件恢复映像，然后返回这些说明。 

1. 将下载的文件解压缩到 USB 驱动器的根目录。  

1. 将 USB 驱动器连接到 Surface Hub 2 上的任何 USB 或 USB 端口。

1. 关闭设备：

   1. 按 "调高音量" 按钮时，按 "电源" 按钮。
   1. 继续按两个按钮，直到看到 Windows 徽标。
   1. 释放电源按钮，但继续按住音量按钮，直到安装 UI 开始。

   ![* 使用 "音量" 和 "电源" 按钮启动恢复 *](images/sh2-keypad.png) <br>
   **图 2. 音量和电源按钮**

1. 在 "语言选择" 屏幕上，选择 Surface Hub 2 秒的显示语言。

1. 选择 " **从驱动器恢复** " 并 **完全清理驱动器**，然后选择 " **恢复**"。 如果系统提示你输入 BitLocker 密钥，请选择 " **跳过此驱动器**"。 Surface Hub 2 秒重启几次，完成恢复过程大约需要30分钟。

出现首次设置屏幕时，请删除 USB 驱动器。

## 联系支持人员

如果有疑问或需要帮助，您可以 [创建支持请求](https://support.microsoft.com/supportforbusiness/productselection)。

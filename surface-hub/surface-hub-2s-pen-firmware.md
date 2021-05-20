---
title: 更新 Surface Hub 2S 手写笔固件
description: 此页面介绍如何更新 2 个笔Surface Hub固件。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 6f1ca4f05653ec798ed1b47d2e42e974e7f7414d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576952"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>更新 Surface Hub 2S 手写笔固件

你可以从适用于Surface Hub更新Windows 2 触控笔上更新固件，或者将固件更新下载到单独的电脑。 从 2020 年 2 Windows 26 日起更新固件。 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>使用适用于Windows更新更新笔固件

本节介绍如何通过 Windows 更新的自动维护周期来更新笔固件，该更新默认配置为在下午 3 点发生。 在将更新应用到 2 个笔之前，您需要规划两个维护Surface Hub完成。 或者，与任何其他更新一样，您可以使用 Windows Update for Business (WUfB) 应用笔固件。 有关详细信息，请参阅管理Windows[更新Surface Hub。](manage-windows-updates-for-surface-hub.md)

1. 确保将Surface Hub 2 个笔配对Surface Hub 2S：长按顶部按钮，直到白色指示灯**** 开始闪烁。 <br>
![Surface Hub 2 个笔](images/sh2-pen-1.png) <br>
2. On Surface Hub， login as an Admin， open**设置**， and then scan for new 蓝牙 devices.
3. 选择笔以完成配对过程。
4. 按 **笔** 上的顶部按钮应用更新。 可能需要两个小时才能完成。

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>通过下载到单独的电脑更新笔固件

你可以从运行 Surface Hub 2 触控笔的单独电脑上更新Windows 10。 此方法还允许您验证笔固件已成功更新到最新版本。

1. 将 Surface Hub 2 个笔与蓝牙的电脑配对：长按顶部按钮，直到白色指示灯开始**** 闪烁。 <br>
![Surface Hub 2 个笔](images/sh2-pen-1.png) <br>
2. 在电脑上，扫描新的蓝牙设备。
3. 选择笔以完成配对过程。
4. 在开始新Surface Hub之前断开所有其他 2s 笔连接。
3. 将[Surface Hub 2 触控笔固件更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下载到电脑。
4. 运行 **PenCfu.exe。** 安装进度将显示在工具中。 可能需要几分钟才能完成更新。 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>检查 2 个Surface Hub固件版本

1. 运行 **get_version.bat， ** 然后按 **触控笔** 上的顶部按钮。
2. 该工具将报告笔的固件版本。 示例：
    - 旧固件为 468.2727.368
    - 新固件为 468.3347.368

## <a name="command-line-options"></a>命令行选项

你可以从Surface Hub运行 (PenCfu.exe) 2 笔固件更新工具。

1. 将笔与电脑配对，然后单击 **笔** 上的顶部按钮。
2. 双击PenCfu.exe** 启动 ** 固件更新。 请注意，配置文件和固件映像文件必须与工具存储在同一文件夹中。
3. 对于其他选项，PenCfu.exe ** -h** 来显示可用参数，如下表所列。  
    - 示例：PenCfu.exe -h
4. 输入 **Ctrl+C** 可安全关闭该工具。

 

| **命令**    | **描述**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -h 帮助        | 显示工具命令行界面帮助和退出。                                                                                                                                                                                                                                                                                                                                             |
| -v 版本     | 显示工具版本和退出。                                                                                                                                                                                                                                                                                                                                                                 |
| -l log-filter  | 为项目设置筛选日志文件。 日志消息有 4 个可能级别：DEBUG (最低) 、INFO、WARNING 和 ERROR (最高) 。 设置日志筛选器级别将日志消息筛选为仅具有相同级别或更高级别的消息。 例如，如果筛选器级别设置为 WARNING，则只会记录 WARNING 和 ERROR 消息。 默认情况下，此选项设置为 OFF，这将禁用日志记录。 |
| -g get-version | 如果指定，该工具将仅获取与存储在工具同一文件夹中的配置文件匹配的已连接笔的 FW 版本。                                                                                                                                                                                                                                    

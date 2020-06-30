---
title: 更新 Surface Hub 2 上的笔固件
description: 本页介绍如何更新 Surface Hub 2 笔的固件。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c0ad8f275d2476e42c9a5bd3f1130fbca85a5599
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830958"
---
# 更新 Surface Hub 2 上的笔固件

你可以从 Windows 更新 for Business 或将固件更新下载到单独的电脑，从 Surface Hub 2 笔更新固件。 从2020年2月26日开始，Windows 更新提供已更新的固件。 

## 使用 Windows 更新商业版更新笔固件

本部分介绍如何通过 Windows 更新的自动维护周期（默认情况下，默认情况下，在晚上3点）更新笔固件。 在将更新应用到 Surface Hub 2 笔之前，您需要规划两个维护周期才能完成。 或者，也可以使用 Windows Server 更新服务（WSUS）应用笔固件。 有关详细信息，请参阅[管理 Surface Hub 上的 Windows 更新](manage-windows-updates-for-surface-hub.md)。

1. 确保 Surface Hub 2 笔与 Surface Hub 2 配对：长按**顶部**按钮，直到白色指示灯的指示灯开始闪烁。 <br>
![Surface Hub 2 笔](images/sh2-pen-1.png) <br>
2. 在 Surface Hub 上，以管理员身份登录，打开 "**设置**"，然后扫描新的蓝牙设备。
3. 选择笔完成配对过程。
4. 按笔上的**顶部**按钮以应用更新。 最多可能需要两个小时才能完成。

## 通过下载到单独的电脑更新笔固件

你可以从运行 Windows 10 的单独电脑更新 Surface Hub 2 笔上的固件。 此方法还允许你验证笔固件是否已成功更新到最新版本。

1. 将 Surface Hub 2 笔与支持蓝牙功能的电脑配对：按住**顶部**按钮，直到白色指示灯的指示灯开始闪烁。 <br>
![Surface Hub 2 笔](images/sh2-pen-1.png) <br>
2. 在电脑上，扫描新的蓝牙设备。
3. 选择笔完成配对过程。
4. 开始新的更新之前，请断开所有其他 Surface Hub 2 笔连接。
3. 将[Surface Hub 2 笔固件更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下载到你的电脑。
4. 运行**PenCfu.exe。** 安装进度将显示在工具中。 完成更新可能需要几分钟。 


## 检查 Surface Hub 2 笔的固件版本

1. 运行**get_version.bat** ，然后按笔上的**上**一个按钮。
2. 该工具将报告笔的固件版本。 示例：
    - 旧固件为468.2727.368
    - 新固件为468.2863.369

## 命令行选项

你可以从命令行运行 Surface Hub 2 笔固件更新工具（PenCfu.exe）。

1. 将笔与 PC 配对，然后单击笔上的**上**一个按钮。
2. 双击 " **PenCfu.exe** " 以启动固件更新。 请注意，配置文件和固件图像文件必须存储在该工具所在的同一文件夹中。
3. 对于其他选项，请运行**PenCfu.exe-h**以显示可用参数，如下表所示。  
    - 示例： PenCfu.exe-h
4. 输入**Ctrl + C**以安全关闭该工具。

 

| **命令**    | **描述**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -h 帮助        | 显示工具命令行界面帮助和退出。                                                                                                                                                                                                                                                                                                                                             |
| -v 版本     | 显示工具版本并退出。                                                                                                                                                                                                                                                                                                                                                                 |
| -l 记录-筛选器  | 为日志文件设置筛选器级别。 日志消息具有4个可能的级别：调试（最低）、信息、警告和错误（最高）。 设置日志筛选器级别筛选器仅将消息记录到同一级别或更高级别的邮件中。 例如，如果筛选器级别设置为 "警告"，则仅记录警告和错误消息。 默认情况下，此选项设置为 "关闭"，这将禁用日志记录。 |
| -g get 版本 | 如果已指定，该工具将仅获取与工具存储在同一文件夹中的配置文件相匹配的已连接笔的固件版本。                                                                                                                                                                                                                                    
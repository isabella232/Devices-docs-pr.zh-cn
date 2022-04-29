---
title: 更新 Surface Hub 2S 手写笔固件
description: 本页介绍如何更新Surface Hub 2 笔的固件。
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
ms.openlocfilehash: b1955f1806c963ce553d5d2eef99e72e90c5adfe
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497715"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>更新 Surface Hub 2S 手写笔固件

可以通过 Windows 更新 for Business 或将固件更新下载到单独的电脑，在 Surface Hub 2 笔上更新固件。 更新后的固件从 2020 年 2 月 26 日开始Windows 更新提供。 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>使用适用于企业的Windows 更新更新笔固件

本部分介绍如何通过Windows 更新的自动维护周期更新笔固件，默认情况下配置为每晚 3 点进行。 在将更新应用到Surface Hub 2 笔之前，需要规划两个维护周期才能完成。 或者，与任何其他更新一样，可以使用 Windows 更新 for Business (WUfB) 应用笔固件。 有关详细信息，请参阅[管理Surface Hub上的Windows更新](manage-windows-updates-for-surface-hub.md)。

1. 确保Surface Hub 2 笔与 Surface Hub 2S 配对：按住**顶部**按钮，直到白色指示器 LED 灯开始闪烁。

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 支笔。](images/sh2-pen-1.png)

2. 在Surface Hub上，以管理员身份登录，打开**设置**，然后扫描新的蓝牙设备。

3. 选择笔以完成配对过程。

4. 按笔上的 **顶部** 按钮应用更新。 最多可能需要两个小时才能完成。

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>通过下载到单独的电脑更新笔固件

可以从运行Windows 10或Windows 11的单独电脑更新Surface Hub 2 笔上的固件。 此方法还可用于验证笔固件是否已成功更新到最新版本。

1. 将Surface Hub 2 笔配对到支持蓝牙电脑：按住**顶部**按钮，直到白色指示器 LED 灯开始闪烁。

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 支笔。](images/sh2-pen-1.png)

2. 在电脑上，扫描新的蓝牙设备。

3. 选择笔以完成配对过程。

4. 在启动新更新之前，请断开所有其他Surface Hub 2s 笔。

5. 将[Surface Hub 2 笔固件更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下载到电脑。

6. 运行 **PenCfu.exe。** 安装进度显示在工具中。 可能需要几分钟才能完成更新。 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>检查 Surface Hub 2 笔的固件版本

1. 运行 **get_version.bat** 并按笔上的 **顶部** 按钮。

2. 该工具将报告笔的固件版本。 

   示例：
    - 旧固件为 468.2727.368
    - 新固件为 468.3347.368

## <a name="command-line-options"></a>命令行选项

可以从命令行运行Surface Hub 2 笔固件更新工具 (PenCfu.exe) 。

1. 将笔配对到电脑，然后单击笔上的 **顶部** 按钮。

2. 双击 **PenCfu.exe** 启动固件更新。 请注意，配置文件和固件映像文件必须存储在工具所在的同一文件夹中。

3. 对于其他选项， ** 请运行PenCfu.exe -h** 以显示可用参数，如下表中所列。  

   示例： `PenCfu.exe -h`

4. 输入 **Ctrl+C** 安全关闭该工具。


| 命令 | 描述 |
| -------------- |---------------------------- |
| -h 帮助        | 显示工具命令行接口帮助和退出。 |
| -v 版本     | 显示工具版本和退出。 |
| -l log-filter  | 设置日志文件的筛选器级别。 日志消息有 4 个可能级别：调试 (最低) 、信息、警告和错误 (最高) 。 设置日志筛选器级别会将日志消息筛选为仅具有相同级别或更高级别的消息。 例如，如果筛选器级别设置为 WARNING，则只会记录 WARNING 和 ERROR 消息。 默认情况下，此选项设置为 OFF，禁用日志记录。 |
| -g get-version | 如果指定，该工具将仅获取与该工具存储在同一文件夹中的配置文件匹配的连接笔的 FW 版本。  |


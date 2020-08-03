---
title: 如何启用 Surface Power on Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: 介绍如何启用和禁用 Surface 设备的唤醒功能。
keywords: 更新、部署、驱动程序、wol、lan 唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902995"
---
# 对 Surface 设备供电的唤醒

可以在离开桌面时关闭 Surface 设备，也可以设置为休眠模式以节省电池。 为了提高这些设备的可管理性，Power on Power 可使兼容的 Surface 设备在重新连接到 Power 时自动启动。 配置 "在 Power 唤醒" 时，需要通过 Surface UEFI 配置器或 UEFI 管理器使用 Surface Enterprise 管理模式（SEMM）。

在以下设备上可以使用 "Power on" 功能：

- Surface Book 3
- Surface Pro 7
- Surface 笔记本电脑3
- Surface Pro X 

## 概述和先决条件

你可以使用 Surface UEFI 配置器配置单独的 UEFI 设置，这些设置保存在 Windows 安装程序 .msi 程序包中，以便分发到目标设备。 

> [!NOTE]
> 本文假定你熟悉 SEMM 的使用。 有关详细信息，请参阅[Surface Enterprise 管理模式（SEMM）](surface-enterprise-management-mode.md)文档。

## 启用 Power 唤醒

1.  下载最新版本的[SURFACE UEFI 配置](https://www.microsoft.com/download/confirmation.aspx?id=46703)器。
2.  以管理员身份登录 Surface 设备，打开**SURFACE UEFI 配置**器，选择 " **Surface 设备**"，然后选择 "**下一步**"。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="选择 "Surface 设备"，然后选择 "下一步"。":::
3.  选择 "**开始**"，然后在 "**配置包**" 下选择 "**创建**"。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="选择 "创建配置包"。":::
4.  选择 "**证书保护**" 并添加证书 .pfx 文件。 输入密码后，选择 "**下一步**"。 根据需要添加**密码保护**，然后选择 "**下一步**"。
5.  在 "**选择要作为目标的图面类型**" 页面上，根据需要选择目标设备。 例如， **Surface Pro 7**。
6.  在 "**高级功能**" 页面上，选择 **"接通电源"** 并设置为 **"开**"。 选择**下一步** 。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="选择 "接通电源时唤醒"，并设置为 "开"。"::: 
7.  在 "**成功**" 页面上，选择 "**结束**"。 如果你是第一次向设备提供设置，系统将提示你提供证书指纹的最后两个字符。 
8.  保存 .msi 程序包。 

## 应用 MSI 程序包 

你可以使用软件分发工具（如 Microsoft 终结点配置管理器）将 MSI 程序包应用到网络上的设备。 此过程包括在本地计算机上安装程序包的步骤。 

1.  打开提升的命令提示符，输入 .msi 文件的完整路径以运行 .msi 程序包。 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  在 "**警告**" 对话框中，根据需要选择 **"确定" 或 "** 禁用 Bitlocker"。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="根据需要选择 "确定" 或 "禁用 Bitlocker"。":::
3.  在 "欢迎" 页面上，选择 "**下一步**" 以运行程序包并应用新配置的 UEFI 设置。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="一个欢迎页面，选择 "下一步"。":::
4.  重启您的设备。 

现已配置 Power on Power。 要测试设置，请关闭您的设备，断开电源，然后重新连接电源。 设备将自动启动。 

## 详细信息

有关详细信息，请参阅以下文章。 

- [Surface 企业管理模式](surface-enterprise-management-mode.md)
- [面向 Surface 设备的 LAN 唤醒](wake-on-lan-for-surface-devices.md)

是否仍需要帮助？ 转到[Microsoft 社区](https://answers.microsoft.com/)。
---
title: 如何为 Surface 启用电源唤醒
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: 介绍如何为 Surface 设备启用和禁用电源唤醒。
keywords: 更新， 部署， 驱动程序， wol， lan 唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271556"
---
# Surface 设备通电唤醒

当你离开桌面时，Surface 设备可以关闭电源，或者设置为休眠模式以节省电池使用时间。 为了改进这些设备的可管理性，电源唤醒使兼容的 Surface 设备能够在重新连接到电源时自动启动。 若要配置电源唤醒，可以通过 Surface UEFI (UEFI) 或 UEFI 管理器使用 Surface Enterprise Management Mode) SEMM 模式。

电源唤醒功能在下列设备上可用：

- Surface Pro 7+
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Laptop Go
- Surface Pro X 


##  <a name="overview-and-prerequisites"></a>概述和先决条件

Surface UEFI 配置器允许你将单个 UEFI 设置保存在 Windows Installer .msi 程序包中，以分发到目标设备。 

> [!NOTE]
> 本文假定你了解如何使用 SEMM。 有关详细信息，请参阅 [SURFACE Enterprise Management Mode (SEMM) ](surface-enterprise-management-mode.md) 文档。

##  <a name="to-enable-wake-on-power"></a>启用电源唤醒

1.  下载最新版本的[Surface UEFI Configurator。](https://www.microsoft.com/download/confirmation.aspx?id=46703)
2.  以管理员角色登录 Surface 设备，打开**Surface UEFI 配置**器，选择**Surface 设备**，然后选择"下一**步"。**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="选择 Surface 设备并选择下一步。":::
3.  选择 **"** 开始"，然后选择 **"配置包****"下的"创建"。**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="选择创建配置包。":::
4.  选择 **证书保护**，并添加证书 .pfx 文件。 
5. 输入您的密码，选择 **"下**一步****"，根据需要添加密码保护，然后选择"下一**步"。**
6.  在 **"选择要面向的 Surface 类型"** 页上，选择相应的目标设备。 例如，选择**Surface Pro 7。**
7.  在"**高级功能**"页上，选择 **"电源**唤醒"，将功能设置为 **"打开**"，然后选择"下一**步"。**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="选择电源唤醒并设置为打开。"::: 
8.  在"**成功"** 页上，选择"**结束"。**

    > [!NOTE]
    > 如果这是第一次向设备提供设置，系统将提示你提供证书指纹的最后两个字符。 
9.  保存 .msi 包。 

##  <a name="apply-the-msi-package"></a>应用 MSI 程序包 

可以使用软件分发工具（如 Microsoft Endpoint Configuration Manager）将 MSI 程序包应用到整个网络的设备。 此过程包括在本地计算机上安装程序包的步骤。 

1.  在提升的命令提示符下，输入 .msi 文件的完整路径以运行 .msi 包。 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  在 **"警告** "对话框中，选择 **"确定** "或禁用 BitLocker（如果适用）。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="选择确定或在适当时禁用 BitLocker。":::
3.  在"欢迎"页上，选择 **"下** 一步"运行程序包并应用新配置的 UEFI 设置。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="在欢迎页面之一，选择下一步。":::
4.  重新启动设备。 

现在配置了"电源唤醒"。 若要测试设置，请关闭设备，断开电源连接，然后重新连接电源。 设备应自动启动。 

##  <a name="references"></a>参考

有关详细信息，请参阅以下文章。 

- [Surface 企业管理模式](surface-enterprise-management-mode.md)
- [在 LAN 上唤醒 Surface 设备](wake-on-lan-for-surface-devices.md)

是否仍需要帮助？ 转到 [Microsoft 社区](https://answers.microsoft.com/)。
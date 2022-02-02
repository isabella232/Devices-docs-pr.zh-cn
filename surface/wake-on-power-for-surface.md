---
title: Surface 设备通电唤醒
ms.author: greglin
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: 介绍如何为 Surface 设备启用和禁用电源唤醒。
keywords: 更新， 部署， 驱动程序， wol， lan 上唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 12/08/2021
ms.openlocfilehash: e8e4ddbd559fc6aea2d04e61208b911ebef3ec22
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338395"
---
# <a name="wake-on-power-for-surface-devices"></a>Surface 设备通电唤醒

Surface 设备可以在你离开桌面时关闭电源，或者设置为休眠模式以节省电池使用时间。 为了提高这些设备的可管理性，"电源唤醒"允许兼容的 Surface 设备在重新连接到电源时自动启动。 若要配置电源唤醒，可以通过 Surface UEFI Enterprise或 UEFI 管理器 (SEMM) Surface Enterprise 管理模式。

电源唤醒功能在下列设备上可用：

- Surface Pro 8 (商业 SKUs) 
- Surface Pro 7 (商业 SKUs) 
- Surface Pro X (所有 SKUs) 
- Surface Pro 7 (SKUs) 
- Surface Go 3 (商业 SKUs) 
- Surface Laptop Studio (商业 SKUs) 
- Surface Book 3 (SKUs) 
- Surface Laptop 4 (商业 SKUS) 
- Surface Laptop 3 (SKUs) 
- Surface Laptop转到 (所有 SKUS) 


>[!TIP]
> 商业 SKUS (，Surface 商用版) 运行 Windows 10 专业版/Enterprise 或 Windows 11 专业版/Enterprise;消费者 SUS Windows 10/Windows 11 家庭版。 若要了解详细信息，请参阅 [查看系统信息](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00)。 

## <a name="overview-and-prerequisites"></a>概述和先决条件

Surface UEFI 配置器允许你将单个 UEFI 设置保存在 Windows Installer .msi 程序包中，以分发到目标设备。 

> [!NOTE]
> 本文假定你了解如何使用 SEMM。 有关详细信息，请参阅 [Surface Enterprise Management Mode (SEMM) ](surface-enterprise-management-mode.md)文档。

## <a name="to-enable-wake-on-power"></a>启用电源唤醒

1.  下载最新版本的 [Surface UEFI 配置器](https://www.microsoft.com/download/confirmation.aspx?id=46703)。
2.  以管理员方式登录到 Surface 设备，打开 **Surface UEFI 配置**器，选择 **Surface 设备**，然后选择下一 **步**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="选择 Surface 设备，然后选择下一步。":::
3.  选择 **"开始**"，然后选择"**配置包"****下的"创建"**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="选择&quot;创建配置包&quot;。":::
4.  选择 **"证书保护**"，然后添加证书 .pfx 文件。 
5. 输入您的密码，选择" **下**一步 **"，根据需要**添加密码保护，然后选择"下一步 **"**。
6.  在 **"选择要面向的 Surface 类型"页上** ，根据情况选择目标设备。 例如，选择"**Surface Pro 7"**。
7.  在" **高级功能"** 页上，选择 **"电源唤醒"**，将功能设置为 **"打开**"，然后选择"下一步 **"**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="选择&quot;电源唤醒&quot;，并设置为&quot;打开&quot;。"::: 
8.  在" **成功"页上** ，选择" **结束"**。

    > [!NOTE]
    > 如果这是第一次向设备提供设置，系统将提示你提供证书指纹的最后两个字符。 
9.  保存.msi包。 

## <a name="apply-the-msi-package"></a>应用 MSI 程序包 

可以使用软件分发工具（如软件分发工具）将 MSI 程序包应用到整个Microsoft Endpoint Configuration Manager。 此过程包括在本地计算机上安装程序包的步骤。 

1.  在提升的命令提示符下，输入 .msi 文件的完整路径以运行 .msi 包。 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  在" **警告** "对话框中，选择 **"确定"** 或禁用 BitLocker（如果适用）。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="选择&quot;确定&quot;或在适当时禁用 BitLocker。":::
3.  在"欢迎"页上，选择 **"下** 一步"运行程序包并应用新配置的 UEFI 设置。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="在&quot;欢迎&quot;页上，选择&quot;下一步&quot;。":::
4.  重新启动设备。 

现在配置了"唤醒电源"。 若要测试设置，请关闭设备，断开电源连接，然后重新连接电源。 设备应自动启动。 

## <a name="references"></a>参考

有关详细信息，请参阅以下文章。 

- [Surface 企业管理模式](surface-enterprise-management-mode.md)
- [Surface 设备的 LAN 唤醒](wake-on-lan-for-surface-devices.md)

是否仍需要帮助？ 转到 [Microsoft Community](https://answers.microsoft.com/)。
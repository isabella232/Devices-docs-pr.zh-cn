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
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
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
ms.openlocfilehash: dee2a2962cf6b70a1bf11cf597b4d41f4b5568e4
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114570"
---
# Surface 设备通电唤醒

当您离开桌面时，可以关闭 Surface 设备，或设置为休眠模式以节省电池使用时间。 为了提高这些设备的可管理性，Power on Power 启用兼容的 Surface 设备，以便在它们重新连接到电源时自动启动。 若要配置 Power on Power，可以使用 Surface Enterprise 管理模式 (SEMM) 通过 Surface UEFI 配置器或 UEFI 管理器。

以下设备上提供了 Power on Power 功能：

- Surface Book 3
- Surface Pro 7
- Surface 笔记本电脑3
- Surface 膝上型电脑 Go
- Surface Pro X 


## 概述和先决条件

Surface UEFI 配置器允许你将单个 UEFI 设置保存在 Windows Installer 的 .msi 程序包中，以便分发到目标设备。 

> [!NOTE]
> 本文假定你知道如何使用 SEMM。 有关详细信息，请参阅 [Surface Enterprise 管理模式 (SEMM) ](surface-enterprise-management-mode.md) 文档。

## 启用 Power 唤醒

1.  下载最新版本的 [SURFACE UEFI 配置](https://www.microsoft.com/download/confirmation.aspx?id=46703)器。
2.  以管理员身份登录 Surface 设备，打开 **SURFACE UEFI 配置**器，选择 " **Surface 设备**"，然后选择 " **下一步**"。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。&quot;:::
3.  选择 &quot;**开始**&quot;，然后选择 &quot;**配置程序包**" 下的 "**创建**"。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。&quot;:::
3.  选择 &quot;**开始**&quot;，然后选择 &quot;**配置程序包**" **下一步**"。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。&quot;:::
3.  选择 &quot;**开始**&quot;，然后选择 &quot;**配置程序包**" 或 "** 禁用 BitLocker"。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。&quot;:::
3.  选择 &quot;**开始**&quot;，然后选择 &quot;**配置程序包**" 以运行程序包并应用新配置的 UEFI 设置。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。&quot;:::
3.  选择 &quot;**开始**&quot;，然后选择 &quot;**配置程序包**":::
4.  重启您的设备。 

现已配置 Power on Power。 要测试设置，请关闭您的设备，断开电源，然后重新连接电源。 设备应自动启动。 

## 参考

有关详细信息，请参阅以下文章。 

- [Surface 企业管理模式](surface-enterprise-management-mode.md)
- [面向 Surface 设备的 LAN 唤醒](wake-on-lan-for-surface-devices.md)

是否仍需要帮助？ 转到 [Microsoft 社区](https://answers.microsoft.com/)。
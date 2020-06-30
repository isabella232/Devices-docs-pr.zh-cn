---
title: 在 Surface 设备上启用 PEAP、EAP-FAST 和 Cisco LEAP (Surface)
description: 了解如何在你的 Surface 设备上启用对 PEAP、EAP-FAST 或 Cisco LEAP 协议的支持。
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: 网络, 无线, 设备, 部署, 身份验证, 协议
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831712"
---
# 在 Surface 设备上启用 PEAP、EAP-FAST 和 Cisco LEAP


了解如何在你的 Surface 设备上启用对 PEAP、EAP-FAST 或 Cisco LEAP 协议的支持。

如果你在你的企业网络中使用 PEAP、EAP-FAST 或 Cisco LEAP，你可能已经了解这三种无线身份验证协议不受全新 Surface 设备支持。 一些用户在尝试连接到无线网络时可能会发现此情况；另一些用户在无法获取对网络内资源（例如文件共享和内部站点）的访问权限时可能会发现此情况。 有关详细信息，请参阅[可扩展身份验证协议](https://technet.microsoft.com/network/bb643147)。

你可以通过从 U 盘或文件共享执行较小的 MSI 程序包来添加对每个协议的支持。 对于想要在其 Surface 设备上启用 EAP 支持的组织，MSI 程序包格式支持具有许多管理和部署工具（如 Microsoft 部署工具包（MDT）和 Microsoft 终结点配置管理器）的部署。

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a>下载 PEAP、EAP-FAST 或 Cisco LEAP 安装文件


你可以从 Microsoft 下载中心针对单个 zip 存档文件中的 EAP、EAP-FAST 或 Cisco LEAP 下载 MSI 安装文件。 若要下载此文件，请转到 Microsoft 下载中心的[适用于 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)页、单击**下载**，然后选择 **Cisco EAP-Supplicant Installer.zip** 文件。

## 使用 MDT 部署 PEAP、EAP-FAST 或 Cisco LEAP


如果你已在你的组织中执行到 Surface 设备的 Windows 部署，则可以在部署期间快速轻松地将每个协议的安装文件添加到部署共享并配置自动安装。 甚至可以配置用于更新之前已部署的 Surface 设备的任务序列，从而可以使用相同的过程提供对这些协议的支持。

若要在新部署的 Surface 设备上启用对 PEAP、EAP-FAST 或 Cisco LEAP 的支持，请按照以下步骤操作：

1.  下载每个协议的安装文件并将其解压缩到某一可轻松访问的位置中的单个文件夹。

2.  打开 MDT 部署工作台并将部署共享展开到**应用程序**文件夹。

3.  从**操作**窗格中选择**新建应用程序**。

4.  选择**具有源文件的应用程序**以将 MSI 文件复制到部署共享中。

5.  针对所需的协议选择步骤 1 中所创建的文件夹。

6.  对将在其中存储安装文件的部署共享中的文件夹进行命名。

7.  指定要用于部署应用程序的命令行：

    -   对于 PEAP，请使用 **EAP-PEAP.msi /qn /norestart**。

    -   对于 LEAP，请使用 **EAP-LEAP.msi /qn /norestart**。

    -   对于 EAP-FAST，请使用 **EAP-FAST.msi /qn /norestart**。

8.  使用默认选项完成“新建应用程序”向导。

9.  针对每个所需的协议重复步骤 3 到步骤 8。

在执行这些步骤以将三个 MSI 程序包作为应用程序导入到 MDT 后，它们将在 Windows 部署向导的“应用程序”页中可供选择。 尽管在一些简单的部署方案中这足以让技术人员在部署时选择每个程序包，但这并非推荐的做法。 此做法允许技术人员尝试将这些程序包应用到 Surface 设备以外的计算机，或由于人为错误而使得 Surface 设备可以在没有 EAP 支持的情况下进行部署。

若要从“安装应用程序”页中隐藏这些应用程序，请在每个应用程序的属性中选中**在部署向导中隐藏此应用程序**复选框。 在应用程序处于隐藏状态后，它们将不会在部署期间显示为可选应用程序。 若要在 Surface 部署任务序列中部署它们，必须通过任务序列中的单独步骤针对安装进行显式定义。

若要显式指定协议，请按照以下步骤操作：

1.  从 MDT 部署工作台打开你的 Surface 部署任务序列属性。

2.  在**任务序列**选项卡上，在**状态还原**下选择**安装应用程序**步骤。 这通常可以在应用程序安装前和应用程序安装后 Windows 更新步骤之间找到。

3.  使用**添加**按钮，从**常规**类别创建一个新的**安装应用程序**步骤。

4.  在步骤**属性**选项卡中选择**安装单个应用程序**。

5.  从列表中选择所需的 EAP 协议。

6.  针对每个所需的协议重复步骤 2 到步骤 5。

## 使用配置管理器部署 PEAP、EAP-FAST 或 Cisco LEAP


对于使用配置管理器管理 Surface 设备的组织，可以更轻松地将 PEAP、EAP-FAST 或 Cisco LEAP支持部署到 Surface 设备。 只需从软件库导入每个 MSI 文件作为应用程序并将部署配置为你的 Surface 设备集合。

有关如何使用配置管理器部署应用程序的详细信息，请参阅[如何在配置管理器中创建应用程序](https://technet.microsoft.com/library/gg682159.aspx)和[如何在配置管理器中部署应用程序](https://technet.microsoft.com/library/gg682082.aspx)。

 

 






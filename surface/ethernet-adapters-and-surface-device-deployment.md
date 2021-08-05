---
title: 以太网适配器和 Surface 部署 (Surface)
description: 本文提供了可帮助你执行到 Surface 设备的网络部署的指南和方法。
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: ''
manager: laurawi
keywords: 以太网, 部署, 可移动, 网络, 连接性, 启动, 固件, 设备, 适配器, PXE 启动, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 0eb0eb1e1d73852a2131c5aa5d6a7731ce78d54f
ms.sourcegitcommit: 6d531906c36da51cb4032a220d70182e686114a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2021
ms.locfileid: "11721252"
---
# <a name="ethernet-adapters-and-surface-deployment"></a>以太网适配器和 Surface 部署

本文介绍了如何执行最新 Surface 设备（包括 Surface Pro 3 及更高版本）的网络部署。

到 Surface 设备的网络部署可能会给系统管理员带来一些独特的挑战。 由于缺少本机有线以太网适配器，因此管理员必须通过可移动以太网适配器提供连接。

## <a name="select-an-ethernet-adapter-for-surface-devices"></a>针对 Surface 设备选择以太网适配器

在解决将如何启动到部署环境或者设备将如何由部署解决方案标识方面的问题前，必须使用有线网络适配器。

当选择以太网适配器时，主要问题在于该适配器将如何从网络启动 Surface 设备。 如果你是使用 Windows 部署服务 (WDS) 的预暂存客户端，或者如果你使用的是 Microsoft Endpoint Configuration Manager，你可能还需要考虑可移动以太网适配器是专用于特定 Surface 设备还是在多个设备之间共享。 有关与共享适配器的潜在冲突详细信息，请参阅本文稍后介绍的通过可移动以太网适配器管理 [MAC](#manage-mac-addresses) 地址。

仅当使用 Microsoft 提供的以太网适配器或扩展坞时，才支持从网络启动（PXE 启动）。 若要从网络启动，必须检测以太网适配器或扩展坞中的芯片集并将其配置为 Surface 设备的固件中的启动设备。 Microsoft 以太网适配器（如 Surface 以太网适配器和 [Surface 扩展坞](https://www.microsoft.com/surface/accessories/surface-dock)）使用与 Surface 固件兼容的芯片集。

Surface 设备的网络启动支持以下以太网设备：

- Surface USB-C 到以太网和 USB 3.0 适配器
- Surface USB 3.0 到千兆位以太网适配器
- Surface 扩展坞
- Surface Dock 2
- Surface 3 扩展坞
- Surface Pro 3 扩展坞
- 适用于 Surface Pro 和 Surface Pro 2 的扩展坞

第三方以太网适配器还受网络部署支持，尽管它们不支持 PXE 启动。 若要使用第三方以太网适配器，必须将驱动程序加载到部署启动映像中，并且必须从单独的存储设备（如 U 盘）启动该启动映像。

## <a name="boot-surface-devices-from-the-network"></a>从网络启动 Surface 设备

若要从网络或连接的 U 盘启动，必须指示 Surface 设备从备用启动设备中启动。 你可以更改系统固件中的启动顺序以设置 USB 启动设备的优先级，也可以指示它在启动过程中从备用启动设备中启动。

若要从备用启动设备启动 Surface 设备：

1. 确保 Surface 设备的电源已关闭。
2. 长按**降低音量**按钮。
3. 按下并释放**电源**按钮。
4. 在系统开始从 U 盘或以太网适配器启动后，释放**降低音量**按钮。

>[!NOTE]
>除了以太网适配器外，键盘也必须连接到 Surface 设备，以便进入预安装环境并导航部署向导。

对于 Windows 10 版本 1511 和更高版本（包括适用于 Windows 10 版本 1511 的 Windows 评估和部署工具包 (Windows ADK)），默认情况下存在适用于 Microsoft Surface 以太网适配器的驱动程序。 如果你使用的是使用 Windows 预安装环境 (WinPE) 的部署解决方案（如 Microsoft 部署工具包）并且通过 PXE 从网络启动，请确保你的部署解决方案使用最新版本的 Windows ADK。

## <a name="manage-mac-addresses-with-removable-ethernet-adapters"></a><a href="" id="manage-mac-addresses"></a>使用可移动以太网适配器管理 MAC 地址

对于通过网络执行 Windows 部署的管理员而言，另一注意事项是如何在将相同的以太网适配器用于部署到多台计算机时标识计算机。 部署技术所使用的常见标识符是与每个以太网适配器关联的媒体访问控制 (MAC) 地址。 但在将同一以太网适配器用于部署到多台计算机时，你将无法使用可检查 MAC 地址的部署技术，因为在可移动适配器用于不同的计算机时无法区分其 MAC 地址。

避免 MAC 地址冲突的最简单解决方案是为每台 Surface 设备提供专用的可移动以太网适配器。 这在将定期使用以太网适配器或扩展坞的附加功能的大多数情况下可能会有意义。 但是，并非所有方案都要求扩展坞的其他连接或对有线网络的支持。

避免共享适配器时发生冲突的另一可能的解决方案是使用 [Microsoft Deployment Toolkit (MDT)](/mem/configmgr/mdt) 执行到 Surface 设备的部署。 MDT 不使用 MAC 地址来标识个别计算机，因此不受此限制约束。 但是，MDT 会使用 Windows 部署服务来提供 PXE 启动功能，因此受预暂存的客户端方面的限制，这将在本部分的后面部分中进行介绍。

当你将共享的适配器用于部署时，受影响的部署技术的解决方案是使用其他方法来标识唯一系统。 对于可能受此问题影响的配置管理器和 WDS，解决方案是使用由计算机制造商嵌入在计算机固件中的系统通用唯一标识符（系统 UUID）。 对于 Surface 设备，你可以在计算机固件的**设备信息**下看到此项。

若要访问 Surface 设备的固件：

1. 确保 Surface 设备的电源已关闭。
2. 长按**调高音量**按钮。
3. 按下并释放**电源**按钮。
4. 在设备开始启动后，释放**调高音量**按钮。

如果使用 WDS 部署，MAC 地址将仅用于在部署服务器配置为仅响应已知且预暂存的客户端时标识计算机。 当预暂存客户端时，管理员将在 Active Directory 中创建计算机帐户，并根据 MAC 地址或系统 UUID 定义该计算机。 若要避免由共享的以太网适配器引起的标识冲突，应使用[系统 UUID 定义预暂存的客户端](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc742034(v=ws.11))。 或者，可以将 WDS 配置为响应未知客户端，而无需由 MAC 地址或系统 UUID 进行定义，方法是在 **Windows 部署服务器属性**的[**PXE 响应**选项卡](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732360(v=ws.11))上选择**响应所有客户端计算机(已知和未知)** 选项。

与配置管理器相比，与共享的以太网适配发生冲突的可能性要高很多。 在 WDS 仅使用 MAC 地址来定义各个系统（如果将其这样配置）的情况下，只要执行到新的或未知计算机的部署，配置管理器便会使用 MAC 地址来定义各个系统。 这可能导致未正确配置设备，甚至无法使用共享的以太网适配器部署多个系统。 在如何对多个 [SCCM OSD](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374)使用同一外部以太网适配器（核心基础结构和安全博客的博客文章）中详细介绍了针对此情况的几个潜在解决方案。

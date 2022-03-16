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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: ec73d437d2784ffbceb350f38507524e761df8dd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448475"
---
# <a name="ethernet-adapters-and-surface-deployment"></a>以太网适配器和 Surface 部署

本文介绍如何执行最新 Surface 设备的网络部署，包括 Surface Pro 3 及更高版本。

到 Surface 设备的网络部署可能会给系统管理员带来一些独特的挑战。 由于缺少本机有线以太网适配器，因此管理员必须通过可移动以太网适配器提供连接。

## <a name="select-an-ethernet-adapter-for-surface-devices"></a>针对 Surface 设备选择以太网适配器

在解决将如何启动到部署环境或者设备将如何由部署解决方案标识方面的问题前，必须使用有线网络适配器。

选择以太网适配器时，主要关注的是适配器如何从网络启动 Surface 设备。 假设您是预先暂存具有 Windows 部署服务的 (WDS) 或Microsoft Endpoint Configuration Manager。 在这种情况下，你可能还需要考虑可移动以太网适配器是专用于特定 Surface 设备，还是在多个设备之间共享。 有关与共享适配器的潜在冲突详细信息，请参阅本文稍后介绍的通过可移动以太网适配器管理 [MAC](#manage-mac-addresses) 地址。

从网络启动 (PXE) 仅在使用 Microsoft 的以太网适配器或扩展坞时受支持。 必须检测以太网适配器或扩展坞中的芯片集，并配置为 Surface 设备的固件中的启动设备。 Microsoft 以太网适配器（如 Surface 以太网适配器和 [Surface 扩展](https://www.microsoft.com/surface/accessories/surface-dock)坞）使用与 Surface 固件兼容的芯片集。

Surface 设备的网络启动支持以下以太网设备：

- Surface USB-C 到以太网和 USB 3.0 适配器
- Surface USB 3.0 到千兆位以太网适配器
- Microsoft USB-C 旅行中心
- Surface 扩展坞
- Surface 扩展坞 2
- 适用于 Surface 3 的扩展坞
- 适用于 Surface Pro 3 的扩展坞 
- 适用于 Surface Pro 和 Surface Pro 2 的扩展坞

第三方以太网适配器还受网络部署支持，尽管它们不支持 PXE 启动。 若要使用第三方以太网适配器，必须将驱动程序加载到部署启动映像中，并且必须从单独的存储设备（如 U 盘）启动该启动映像。

## <a name="boot-surface-devices-from-the-network"></a>从网络启动 Surface 设备

若要从网络或连接的 U 盘启动，必须指示 Surface 设备从备用启动设备中启动。 你可以更改系统固件中的启动顺序，以设置 USB 启动设备的优先级或在启动过程中从备用启动设备启动。

**从备用启动设备启动：**

1. 确保 Surface 设备的电源已关闭。
2. 长按**降低音量**按钮。
3. 按下并释放**电源**按钮。
4. 在系统开始从 U 盘或以太网适配器启动后，释放**降低音量**按钮。

>[!NOTE]
>除了以太网适配器外，键盘也必须连接到 Surface 设备，以便进入预安装环境并导航部署向导。

对于 Windows 10 版本 1511 和更高版本（包括适用于 Windows 10 版本 1511 的 Windows 评估和部署工具包 (Windows ADK)），默认情况下存在适用于 Microsoft Surface 以太网适配器的驱动程序。 如果你使用的是使用 Windows 预安装环境 (WinPE) 的部署解决方案（如 Microsoft 部署 Toolkit），并使用 PXE 从网络启动，请确保部署解决方案使用 Windows ADK 的最新版本。

## <a name="manage-mac-addresses-with-removable-ethernet-adapters"></a><a href="" id="manage-mac-addresses"></a>使用可移动以太网适配器管理 MAC 地址

对于通过网络执行Windows管理员的另一个注意事项是，在使用相同的以太网适配器部署到多台计算机时标识计算机。 部署技术使用的一个常见标识符是媒体访问控制 (MAC) 与每个以太网适配器关联的地址。 但是，当你使用相同的以太网适配器部署到多台计算机时，你无法使用检查 MAC 地址的部署技术，因为在不同计算机上使用时无法区分可移动适配器的 MAC 地址。

避免 MAC 地址冲突的最简单解决方案是为每台 Surface 设备提供专用的可移动以太网适配器。 这在将定期使用以太网适配器或扩展坞的附加功能的大多数情况下可能会有意义。 但是，并非所有方案都要求扩展坞的其他连接或对有线网络的支持。

避免共享适配器时发生冲突的另一可能的解决方案是使用 [Microsoft Deployment Toolkit (MDT)](/mem/configmgr/mdt) 执行到 Surface 设备的部署。 MDT 不使用 MAC 地址来标识个别计算机，因此不受此限制约束。 但是，MDT 确实Windows部署服务来提供 PXE 启动功能，并且受有关预阶段客户端的限制，如本节稍后所述。

当你将共享的适配器用于部署时，受影响的部署技术的解决方案是使用其他方法来标识唯一系统。 对于 Configuration Manager 和 WDS（这两者都受此问题影响）的解决方案是使用计算机制造商嵌入计算机固件中的系统通用唯一标识符 (系统 UUID) 。 对于 Surface 设备，你可以在计算机固件的**设备信息**下看到此项。

**若要访问 Surface 设备的固件：**

1. 确保 Surface 设备的电源已关闭。
2. 长按**调高音量**按钮。
3. 按下并释放**电源**按钮。
4. 计算机开始启动后，释放 **"调高音量"** 按钮。

如果使用 WDS 部署，MAC 地址将仅用于在部署服务器配置为仅响应已知且预暂存的客户端时标识计算机。 当预暂存客户端时，管理员将在 Active Directory 中创建计算机帐户，并根据 MAC 地址或系统 UUID 定义该计算机。 若要避免由共享的以太网适配器引起的标识冲突，应使用[系统 UUID 定义预暂存的客户端](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc742034(v=ws.11))。 

或者，可以将 WDS 配置为响应不需要通过 MAC 地址或系统 UUID 进行定义的未知客户端。 在"**部署服务器属性**" ("[**PX Windows E**](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732360(v=ws.11)) 响应"选项卡) "响应已知和未知客户端计算机 **"选项**。

与配置管理器相比，与共享的以太网适配发生冲突的可能性要高很多。 在 WDS 仅使用 MAC 地址定义各个系统时，每当部署到新计算机或未知计算机时，Configuration Manager 都会使用 MAC 地址定义单独的系统。 这可能导致未正确配置设备，甚至无法使用共享的以太网适配器部署多个系统。 How [to Use The Same External Ethernet Adapter for Multiple SCCM OSD](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374)中详细介绍了针对此情况的几个潜在解决方案。

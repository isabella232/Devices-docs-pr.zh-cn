---
title: 针对 Surface 部署自定义 OOBE (Surface)
description: 本文将指导你完成面向组织中的最终用户自定义 Surface 全新体验的过程。
ms.assetid: F6910315-9FA9-4297-8FA8-2C284A4B1D87
ms.reviewer: ''
manager: laurawi
keywords: 部署, 自定义, 自动化, 网络, 笔, 配对, 启动
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 97cc262d803875a76427d04c8f9b70547152f895
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831560"
---
# 针对 Surface 部署自定义 OOBE

本文介绍如何为你的组织中的最终用户自定义表面外体验。

Windows 部署中的常见做法是针对已部署计算机的首次启动自定义用户体验，即全新体验（也称为 OOBE）。

>[!NOTE]
>OOBE 也常用于描述阶段，即用户体验显示期间 Windows 设置的配置阶段。 有关设置的 OOBE 阶段的详细信息，请参阅[配置阶段工作原理](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx)。

在某些情况下，你可能想要提供完全自动化以确保在部署结束时计算机可供随时使用，而无需与用户进行任何交互。 在其他情况下，你可能想为用户保留体验的关键元素，以便于执行必要的操作或在重要的选项之间进行选择。 对于部署到 Surface 设备的管理员而言，其中每一种方案都呈现了一个需应对的特殊挑战。

> [!NOTE]
> 本文不适用于 Surface Pro X。有关详细信息，请参阅[部署、管理和维护 Surface Pro X](surface-pro-arm-app-management.md)

本文汇总了部署可能需要附加步骤的方案。 它还提供所需的信息，以确保在任何新部署的 Surface 设备上实现所需的体验。 本文适用于熟悉部署过程以及诸如应答文件和[引用映像](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image)等概念的管理员。

>[!NOTE]
>尽管在使用自动部署解决方案[（如 Microsoft 部署工具包（MDT）](https://go.microsoft.com/fwlink/p/?LinkId=618117)或 Microsoft 终结点配置管理器操作系统部署（OSD））的部署期间，安装程序的 OOBE 阶段仍会运行，但它通过部署向导和任务序列中提供的设置自动运行。 有关详细信息，请参阅：<br/>
>- [使用 Microsoft 部署工具包部署 Windows 10](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)
>- [使用 System Center 2012 R2 Configuration Manager 部署 Windows 10](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-system-center-2012-r2-configuration-manager)

 

## 方案 1：使用 MDT 2013 的 OOBE 中的无线网络


如果在 OOBE 期间存在无线网络适配器，将显示**加入无线网络**页，可提示用户连接到无线网络。 此页面不会自动通过部署技术（包括 MDT 2013）隐藏，因此即使针对完全自动化配置部署也将显示该页面。

若要确保自动部署不会因此页面而停止，必须通过在应答文件 **HideWirelessSetupInOOBE** 中配置附加设置来隐藏该页面。 你可以在[无人参与 Windows 安装程序参考](https://technet.microsoft.com/library/ff716213.aspx)中找到有关 **HideWirelessSetupInOOBE** 设置的其他信息。

## 方案 2：OOBE 中的 Surface 触控笔配对


当你首次从包装中取出 Surface Pro 3、Surface Pro 4、Surface Book 或 Surface Studio 并启动它时，出厂映像的首次运行体验包含一条提示，询问你是否要将随附的 Surface 触控笔与该设备配对。 此提示仅由设备随附的出厂映像提供，不会包含在用于部署的其他映像（例如从批量许可服务中心中下载的 Windows 企业安装媒体）中。 由于配对此体验之外的蓝牙 Surface 触控笔要求你进入控制面板或电脑设置并手动配对蓝牙设备，因此你可能希望用户或技术人员使用此提示来执行配对操作。

若要在 OOBE 中提供出厂 Surface 触控笔配对体验，你必须将出厂 Surface 映像中的四个文件复制到引用映像中。 你可以在捕获引用映像之前将这些文件复制到引用环境中，也可以通过使用部署映像服务和管理 (DISM) 装载映像来稍后添加它们。 四个所需文件如下：

-   %windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png

>[!NOTE]
>应针对旨在要部署到的同一型号 Surface 设备复制出厂映像中的文件。 例如，你应该使用 Surface Pro 7 中的文件部署到 Surface Pro 7 以及 Surface Book 2 中的文件来部署 Surface Book 2，但不应使用 Surface Pro 7 中的文件部署 Surface Book 或 Surface Pro 6。

 

向映像添加这些所需文件的分步过程将在[部署 Surface Pro 3 触控笔和 OneNote 提示](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/)中进行介绍。 这篇博客文章还包括一些提示，确保已安装 Surface 触控笔快速记笔记体验的必要更新，从而允许用户通过一次单击即可将笔记发送到 OneNote。

 

 






---
title: 管理和部署 Surface 驱动程序和固件更新
description: 本文介绍了管理和部署 Surface 设备的固件和驱动程序更新的可用选项。
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, 固件, 更新, 设备, 管理, 部署, 驱动程序, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 10/12/2020
ms.openlocfilehash: afc7b2e82519fb42ca07b107bff73ddea894cfdf
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911637"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>管理和部署 Surface 驱动程序和固件更新

如何管理 Surface 驱动程序和固件更新因环境和组织要求而异。 在 Surface 设备上，固件作为驱动程序向操作系统公开，并且显示在设备管理器中。 这使设备固件和驱动程序能够使用 Windows Update 或 Windows Update for Business 自动更新。 尽管这种简化的方法对于初创公司以及中小型企业可能可行，但大型组织通常需要 IT 管理员在内部分发更新。 这可能涉及全面规划、应用程序兼容性测试，以及在整个网络中最终批准和分发更新之前试验和验证更新。

> [!NOTE]
> 本文面向技术支持代理和 IT 专业人员，仅适用于 Surface 设备。 如果你正在寻找在家庭设备上安装 Surface 更新或固件的帮助，请参阅更新 Surface[固件和](https://support.microsoft.com/help/4023505)Windows 10。

企业级软件分发解决方案不断发展，集中管理更新的业务原理保持不变：维护 Surface 设备的安全性，并使它们通过最新的操作系统和改进功能进行更新。 对于维持稳定的生产环境并确保不会阻止用户提高工作效率至关重要。 本文概述了为大型组织实现这些目标而推荐的工具和流程。

## <a name="central-update-management-in-commercial-environments"></a>商业环境中的中央更新管理

Microsoft 将用于管理设备（包括驱动程序和固件更新）的简化工具转变为名为[Microsoft Endpoint Manager 管理](https://devicemanagement.microsoft.com/)中心且从 devicemanagement.microsoft.com 访问的单个[统一体验](https://devicemanagement.microsoft.com/#home)。

### <a name="manage-updates-with-configuration-manager-and-intune"></a>使用 Configuration Manager 和 Intune 管理更新

Microsoft Endpoint Configuration Manager允许你与 Configuration Manager 客户端同步和部署 Surface 固件和驱动程序更新。 与 Microsoft Intune集成后，可以在一个地方查看所有托管、共同管理和合作伙伴管理的设备。 这是建议大型组织管理 Surface 更新的解决方案。

有关详细步骤，请参阅以下资源：

- [管理 Configuration Manager 中的 Surface 驱动程序更新](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [使用 Configuration Manager 部署应用程序](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Endpoint Configuration Manager 文档](https://docs.microsoft.com/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>使用 Microsoft Deployment Toolkit

Microsoft Deployment Toolkit (MDT) 包含在 Endpoint Configuration Manager 中。 它包含您可能需要使用的可选部署工具，具体取决于您的环境。 其中包括 Windows 评估和部署工具包 (Windows ADK) 、Windows 系统映像管理器 (Windows SIM) 、部署映像服务和管理 (DISM) 以及用户状态迁移工具 (USMT) 。 你可以从 Microsoft Deployment Toolkit[下载最新版本的 MDT。](https://www.microsoft.com/download/details.aspx?id=54259)

有关详细步骤，请参阅以下资源：

- [Microsoft 部署Toolkit文档](https://docs.microsoft.com/configmgr/mdt/)
- [使用 Microsoft 部署工具包部署 Windows 10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [使用 Microsoft Windows 10部署中心将设备部署到 Surface Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Surface 驱动程序和固件更新打包为Windows安装程序 (*.msi) 文件。 若要部署这些Windows安装程序程序包，可以使用 Endpoint Configuration Manager 或 MDT。 有关如何为设备和操作系统选择正确的 .msi 文件的信息，请参阅以下部分中有关下载.msi指南。

有关如何使用 Endpoint Configuration Manager 部署更新的说明，请参阅 [使用 Configuration Manager 部署应用程序](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)。 有关如何使用 MDT 部署更新的说明，请参阅使用[MDT Windows 10部署更新](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)映像。

**WindowsPE 和 Surface 固件和驱动程序**

终结点配置管理器和 MDT 在部署过程中Windows WindowsPE (安装) 预安装环境。 WindowsPE 仅支持一组有限的基本驱动程序，例如用于网络适配器和存储控制器的驱动程序。 非 WindowsPE Windows的组件的驱动程序可能会产生错误。 最佳做法是，可以通过将部署过程配置为在 WindowsPE 阶段仅使用所需驱动程序来防止此类错误。

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

从 Endpoint Configuration Manager 开始，可以使用 Configuration Manager 客户端同步和部署 Microsoft Surface 固件和驱动程序更新。 有关其他信息，请参阅 KB 4098906如何在 Configuration Manager 中管理 [Surface 驱动程序更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)。

## <a name="supported-devices"></a>支持的设备

可.msi文件适用于 Surface Pro 2 (更高版本的设备，Surface Pro X Windows 10运行ARM) 。

## <a name="managing-firmware-with-dfci"></a>使用 DFCI 管理固件

通过使 Intune (中的设备固件配置接口 (DFCI) 配置文件现已在公共 [预览版](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)) 中提供，Surface UEFI 管理将新式管理堆栈向下扩展到 UEFI 硬件级别。 DFCI 支持零接触预配、消除 BIOS 密码、控制安全设置 (包括启动选项和内置外设) ，并在将来为高级安全方案打下基础。 有关详细信息，请参阅以下文章：

- [Surface UEFI 设置的 Intune 管理](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019：宣布从 Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)远程管理 Surface UEFI 设置。

## <a name="best-practices-for-update-deployment-processes"></a>更新部署过程最佳做法

若要维护稳定环境，我们强烈建议您保持与最新版本的 Windows 10。  有关最佳做法建议，请参阅为更新生成[Windows 10圈](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)。

## <a name="downloadable-surface-update-packages"></a>可下载的 Surface 更新程序包

特定版本的 Windows 10具有单独的.msi文件，每个文件都包含 Surface 设备所需的所有累积驱动程序和固件更新。 更新程序包可能包括以下部分或所有组件：

- Wi-Fi 和 LTE
- 视频
- 固态硬盘
- 系统聚合器模块 (SAM) 
- 电池
- 键盘控制器
- EC (嵌入式控制器) 
- 管理引擎 (ME) 
- 统一可扩展固件接口 (UEFI) 

### <a name="downloading-msi-files"></a>下载.msi文件

1. 浏览到 [Microsoft 下载中心上的下载 Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) 的驱动程序和固件。
2. 选择.msi Surface 型号和版本匹配的设备Windows。 the .msi file name includes the minimum supported Windows build number that's required to install the drivers and firmware. 例如，请参阅下图。 若要更新Surface Book版本 18362 的 Windows 10 2，请选择 **"SurfaceBook2_Win10_18362_19.101.13994.msi"。** 对于Surface Book版本 16299 的 Windows 10 2，请选择 **"SurfaceBook2_Win10_16299_1803509_3.msi"。 **

    ![图 1. 下载 Surface 更新。](images/fig1-downloads-msi.png)

    *图 1. 下载 Surface 更新*

### <a name="surface-msi-naming-convention"></a>Surface .msi命名约定

自 2019 年 8 .msi，多个文件都使用下列命名约定：

- *产品*_*Windows版本号Windows*_*版本号*_**_ 版本号 (*通常为零*) 。

**示例**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

此文件名提供以下信息：

- **产品：** SurfacePro6
- **Windows版本：** Win10
- **内部版本** ：18362
- **版本** ：19.073.44195 – 显示文件的创建日期和时间，如下所示：
  - **年份** ：2019 年 1 (19) 
  - **月份和周** ：073 (年 7 月的第三周) 
  - **一个月的分钟数** ：44195
- **版本修订：0** (此版本的第一个版本) 

### <a name="legacy-surface-msi-naming-convention"></a>旧版 Surface .msi命名约定

旧.msi文件 (2019 年 8 月之前构建) 整体命名公式，但使用不同的方法来派生版本号。

**示例**

- SurfacePro6_Win10_16299_1900307_0.msi

此文件名提供以下信息：

- **产品：** SurfacePro6
- **Windows版本：** Win10
- **内部版本** ：16299
- **版本：1900307** – 这显示文件的创建日期及其在发布序列中的位置，如下所示：
  - **年份** ：2019 年 1 (19) 
  - **发布数量** ：003 (年度第三版) 
  - **产品版本号：07** (Surface Pro 6 正式是第七版 Surface Pro) 
- **版本修订：0** (此版本的第一个版本) 

## <a name="learn-more"></a>了解详细信息

- [下载 Surface 的驱动程序和固件](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [如何在 Configuration Manager 中管理 Surface 驱动程序更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [使用 Configuration Manager 部署应用程序](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Endpoint Configuration Manager 文档](https://docs.microsoft.com/configmgr/)
- [Microsoft 部署Toolkit文档](https://docs.microsoft.com/configmgr/mdt/)
- [使用 Microsoft 部署工具包部署 Windows 10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [使用 Microsoft Windows 10将设备部署到 Surface Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Surface UEFI 设置的 Intune 管理](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019：宣布从 Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)远程管理 Surface UEFI 设置。
- [生成 Windows 10 更新的部署圈](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)

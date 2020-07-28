---
title: 管理和部署 Surface 驱动程序和固件更新
description: 本文介绍用于管理和部署 Surface 设备的固件和驱动程序更新的可用选项。
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
ms.openlocfilehash: f41974193d62e4c0cbc1e286976105c20534d906
ms.sourcegitcommit: ed4478dd3c6116a25b1e01a3a0f5ff6c1f940013
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "10897060"
---
# 管理和部署 Surface 驱动程序和固件更新

管理图面驱动程序和固件更新的方式取决于你的环境和组织要求。 在 Surface 设备上，固件作为驱动程序公开给操作系统，并且在设备管理器中可见。 这使设备固件和驱动程序能够使用 Windows 更新或 Windows 更新企业版自动更新。 虽然这种简化的方法对于启动和小型企业或中型企业来说可能是可行的，但是大型组织通常需要 IT 管理员在内部分发更新。 这可能涉及全面规划、应用程序兼容性测试、试验和验证更新，然后再通过网络进行最终批准和分发。

> [!NOTE]
> 本文面向技术支持工程师和 IT 专业人士，仅适用于 Surface 设备。 如果在家庭设备上查找有关安装 Surface 更新或固件的帮助，请参阅[更新 Surface 固件和 Windows 10](https://support.microsoft.com/help/4023505)。

虽然企业级软件分发解决方案继续发展，但集中管理更新的业务基本原理仍保持不变：维护 Surface 设备的安全，并使其在最新操作系统和功能改进中保持更新。 这对于维持稳定的生产环境非常重要，并且确保用户不会被阻止，从而提高工作效率。 本文概述了针对大型组织实现这些目标所推荐的工具和流程。

## 商业环境中的中央更新管理

Microsoft 具有用于管理设备（包括驱动程序和固件更新）的优化工具，以名为[Microsoft 终结点管理器管理中心](https://devicemanagement.microsoft.com/)并从[devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home)访问的单个统一体验。

### 管理配置管理器和 Intune 的更新

Microsoft 终结点配置管理器允许你通过 Configuration Manager 客户端同步和部署 Surface 固件和驱动程序更新。 通过与 Microsoft Intune 的集成，你可以在一个位置查看所有托管、共同管理和合作伙伴管理的设备。 这是适用于大型组织管理图面更新的推荐解决方案。

有关详细步骤，请参阅以下资源：

- [管理 Configuration Manager 中的 Surface 更新](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [通过 Configuration Manager 部署应用程序](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [终结点配置管理器文档](https://docs.microsoft.com/configmgr/)

### 通过 Microsoft 部署工具包管理更新

Microsoft 部署工具包（MDT）包含在终结点配置管理器中。 它包含你可能希望使用的可选部署工具，具体取决于你的环境。 其中包括 Windows 评估和部署工具包（Windows ADK）、Windows 系统映像管理器（Windows SIM）、部署映像服务和管理（DISM）和用户状态迁移工具（USMT）。 您可以从 " [Microsoft 部署工具包下载" 页面](https://www.microsoft.com/download/details.aspx?id=54259)下载最新版本的 MDT。

有关详细步骤，请参阅以下资源：

- [Microsoft 部署工具包文档](https://docs.microsoft.com/configmgr/mdt/)
- [使用 Microsoft 部署工具包部署 Windows 10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [通过 Microsoft 部署工具包将 Windows 10 部署到 Surface 设备](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Surface driver 和固件更新打包为 Windows Installer （* .msi）文件。 若要部署这些 Windows Installer 程序包，可以使用终结点配置管理器或 MDT。 有关如何为设备和操作系统选择正确的 .msi 文件的信息，请参阅以下部分中有关下载 .msi 文件的指南。

有关如何使用终结点配置管理器部署更新的说明，请参阅使用[Configuration Manager 部署应用程序](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)。 有关如何使用 MDT 部署更新的说明，请参阅[使用 Mdt 部署 Windows 10 映像](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)。

**WindowsPE 和 Surface 固件和驱动程序**

终结点配置管理器和 MDT 在部署过程中均使用 Windows 预安装环境（WindowsPE）。 WindowsPE 仅支持一组有限的基本驱动程序，例如用于网络适配器和存储控制器的驱动程序。 不属于 WindowsPE 的 Windows 组件的驱动程序可能会产生错误。 最佳做法是将部署过程配置为仅在 WindowsPE 阶段使用所需的驱动程序，从而阻止此类错误。

### Endpoint Configuration Manager

从终结点配置管理器开始，你可以使用 Configuration Manager 客户端同步和部署 Microsoft Surface 固件和驱动程序更新。 有关其他信息，请参阅 KB 4098906，[如何在 Configuration Manager 中管理 Surface driver 更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)。

## 支持的设备

可下载的 .msi 文件可用于 Surface Pro 2 和更高版本的设备。 有关所有 Surface 设备（如 Surface Pro 7 和 Surface 笔记本电脑3）的 .msi 文件的信息将在此页发布时提供。

## 通过 DFCI 管理固件

通过在 Intune 中内置设备固件配置接口（DFCI）配置文件（现在在[公共预览版](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)中可用），Surface UEFI 管理将新式管理堆栈扩展到 UEFI 硬件级别。 DFCI 支持零接触预配，消除了 BIOS 密码，提供了安全设置（包括启动选项和内置外围设备）的控制权，并为将来的高级安全方案奠定了基础。 有关详细信息，请参阅以下文章：

- [Surface UEFI 设置的 Intune 管理](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019：宣布从 Intune 进行 SURFACE UEFI 设置的远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。

## 更新部署过程的最佳做法

为了保持环境稳定，我们强烈建议你使用最新版本的 Windows 10 保持奇偶校验。  有关最佳做法建议，请参阅[Windows 10 更新的构建部署环](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)。

## 可下载的 Surface 更新程序包

Windows 10 的特定版本具有单独的 .msi 文件，每个文件包含 Surface 设备的所有必需的累积驱动程序和固件更新。 更新程序包可能包含以下部分或所有组件：

- Wi-fi 和 LTE
- 视频
- 固态驱动器
- 系统聚合器模块（SAM）
- 电池
- 键盘控制器
- 嵌入式控制器（EC）
- 管理引擎（ME）
- 统一可扩展固件接口（UEFI）

### 下载 .msi 文件

1. 浏览以下载适用于 Microsoft 下载中心的[驱动程序和固件](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)。
2. 选择与 Surface 模型和 Windows 版本相匹配的 .msi 文件名。 .Msi 文件名包含安装驱动程序和固件所需的最低支持的 Windows 内部版本号。 例如，请参考下图。 若要更新具有 Windows 10 版本18362的 Surface Book 2，请选择 " **SurfaceBook2_Win10_18362_19.101.13994.msi"。** 对于具有 Windows 10 版本16299的 Surface Book 2，请选择 " **SurfaceBook2_Win10_16299_1803509_3.msi**"。

    ![图 1. 下载图面更新](images/fig1-downloads-msi.png)

    *图 1. 下载图面更新*

### Surface 命名约定

自2019年8月起，.msi 文件使用以下命名约定：

- *产品*_*windows 版本*_*windows 内部*_*Version number*_ 版本号版本版本号 *（通常为零）的版本号修订版*。

**示例**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

此文件名提供以下信息：

- **产品：** SurfacePro6
- **Windows 版本：** Win10
- **内部版本：** 18362
- **版本：** 19.073.44195-这将显示创建文件的日期和时间，如下所示：
  - **年份：** 19 （2019）
  - **月份和星期：** 073 （七月的第三周）
  - **月份的分钟数：** 44195
- **版本：0的版本：** 0 （此版本的首次发布）

### 旧式图面。 msi 命名约定

旧版 .msi 文件（在2019年8月之前生成的文件）使用相同的总命名公式，但使用不同的方法派生版本号。

**示例**

- SurfacePro6_Win10_16299_1900307_0.msi

此文件名提供以下信息：

- **产品：** SurfacePro6
- **Windows 版本：** Win10
- **内部版本：** 16299
- **版本：** 1900307-这将显示文件的创建日期及其在发布序列中的位置，如下所示：
  - **年份：** 19 （2019）
  - **发布数：** 003 （年份的第三个版本）
  - **产品版本号：** 07 （surface pro 6 正式是 surface pro 的第7个版本）
- **版本：0的版本：** 0 （此版本的首次发布）

## 了解详细信息

- [下载用于 Surface 的驱动程序和固件](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [如何在 Configuration Manager 中管理 Surface driver 更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [通过 Configuration Manager 部署应用程序](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [终结点配置管理器文档](https://docs.microsoft.com/configmgr/)
- [Microsoft 部署工具包文档](https://docs.microsoft.com/configmgr/mdt/)
- [使用 Microsoft 部署工具包部署 Windows 10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [通过 Microsoft 部署工具包将 Windows 10 部署到 Surface 设备](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Surface UEFI 设置的 Intune 管理](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019：宣布从 Intune 进行 SURFACE UEFI 设置的远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。
- [生成 Windows 10 更新的部署圈](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)

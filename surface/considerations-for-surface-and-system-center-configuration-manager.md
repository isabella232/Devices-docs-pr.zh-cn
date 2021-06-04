---
title: Surface 和 Microsoft 终结点配置管理器的注意事项
description: 通过 Configuration Manager 管理和部署 Surface 设备与任何其他电脑基本相同;本文介绍可能需要其他注意事项的方案。
keywords: 管理、部署、更新、驱动程序、固件
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 4fa62d227deb0b0b07fa0fbc6552ea5b04c1b87b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830795"
---
# Surface 和 Microsoft 终结点配置管理器的注意事项

从根本上讲，将 Surface 设备与 Microsoft 终结点配置管理器的管理和部署与任何其他电脑的管理和部署相同。 与任何其他电脑一样，部署到 Surface 设备包括导入驱动程序、导入 Windows 映像、准备部署任务序列，然后将任务序列部署到集合。 部署后，Surface 设备与任何其他 Windows 客户端一样;若要发布应用、设置和策略，请使用与任何其他设备相同的进程。

你可以在[Microsoft 终结点配置管理器的文档](https://docs.microsoft.com/sccm/index)中找到有关如何使用 Configuration Manager 部署和管理设备的详细信息。

尽管表面设备的部署和管理与任何其他电脑基本相同，但仍有一些可能需要其他注意事项或步骤的方案。 本文提供了这些方案的说明和指南。 本文中所述的解决方案可能也适用于其他设备和制造商。

> [!NOTE]
> 对于 Surface 设备的管理，建议使用 Microsoft 终结点配置管理器的当前分支。

##  <a name="updating-surface-device-drivers-and-firmware"></a>更新 Surface 设备驱动程序和固件

对于通过 Windows 更新接收更新的设备，Surface 组件（甚至固件更新）的驱动程序将自动应用为 Windows 更新过程的一部分。 对于具有托管更新（如通过 Windows Server 更新服务（WSUS）或配置管理器更新）的设备，请参阅[管理 Surface 驱动程序和固件更新](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates/)。

> [!NOTE]
> Surface 设备驱动程序和固件使用 SHA-256 进行了签名，这不是 Windows Server 2008 R2 本身所支持的。 适用于 Windows Server 2008 R2 上运行的 Configuration Manager 环境的解决方法。 有关详细信息，请参阅[无法将驱动程序导入 Microsoft 终结点配置管理器（KB3025419）](https://support.microsoft.com/kb/3025419)。

##  <a name="surface-ethernet-adapters-and-configuration-manager-deployment"></a>Surface 以太网适配器和 Configuration Manager 部署

Configuration Manager 用于在部署期间标识设备的默认机制是媒体访问控制（MAC）地址。 由于 MAC 地址与以太网控制器相关联，因此在多个设备之间共享的以太网适配器将导致 Configuration Manager 仅将每个设备标识为一个设备。 这可能会导致 Windows Configuration Manager 部署不会应用到预期设备。

为了确保在部署期间使用相同以太网适配器的 Surface 设备标识为唯一设备，你可以指示 Configuration Manager 使用其他方法标识设备。 此其他方法可以是无线网络适配器的 MAC 地址或系统通用唯一标识符（系统 UUID）。 你可以使用以下选项指定 Configuration Manager 使用其他标识方法：

* 为 Surface 以太网适配器的 MAC 地址添加排除项，这将强制 Configuration Manager 忽略 System UUID 的首选 MAC 地址，如在[一起终结点配置管理器 OSD 博客文章中重复使用同一 NIC 执行多个 PXE 启动的部署](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/)中所述。

* 按系统 UUID 预安排设备，如在[Microsoft 终结点配置管理器 OSD 博客文章中为多个 PXE 启动的部署重复使用相同的 NIC](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/)中所述。

* 使用脚本通过其无线适配器的 MAC 地址标识新部署的 Surface 设备，如[如何对多个 SCCM OSD 博客文章使用相同的外部以太网适配器](https://blogs.technet.microsoft.com/askpfeplat/2014/07/27/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm-osd/)中所述。

在通过配置管理器部署期间，对 Surface 以太网适配器的另一个考虑是以太网控制器的驱动程序。 从 Windows 10 版本1511开始，Windows 中默认包含 Surface 以太网适配器的驱动程序。 对于想要部署最新版本的 Windows 10 并使用最新版本的 WinPE 的组织，使用 Surface 以太网适配器不需要其他操作。

对于 windows 10 版本1511（包括 Windows 10 RTM 和 Windows 8.1）之前的 Windows 版本，你可能仍然需要安装 Surface 以太网适配器驱动程序，并将该驱动程序包括在 WinPE 启动媒体中。 在 Windows 10 中包含该驱动程序后，从 Microsoft 下载中心下载该驱动程序将不再可用。 若要下载 Surface 以太网适配器驱动程序，请从 Microsoft Update 目录下载，如图中所述。从咨询核心团队博客文章中的 "[以太网驱动程序](https://blogs.technet.microsoft.com/askcore/2016/08/18/surface-ethernet-drivers/)博客文章"。

##  <a name="deploy-surface-app-with-configuration-manager"></a>通过 Configuration Manager 部署 Surface 应用

使用 Microsoft Store for Business 发布后，Surface app 将不再以驱动程序和固件下载的形式提供。 希望将 Surface 应用部署到托管 Surface 设备或在部署期间使用配置管理器的组织必须通过 Microsoft Store for Business 获取 Surface 应用，然后再使用 PowerShell 部署 Surface 应用。 你可以在 TechNet 库中找到部署 surface 应用的 PowerShell 命令、下载 surface 应用的说明，以及 Microsoft [store for business 中的必备](https://technet.microsoft.com/itpro/surface/deploy-surface-app-with-windows-store-for-business)框架。

##  <a name="use-prestaged-media-with-surface-clients"></a>将预留媒体与 Surface 客户端配合使用

如果你的组织在使用配置管理器部署之前使用预留媒体将部署资源预加载到计算机，则作为 UEFI 设备的 Surface 设备的性质可能需要你执行其他步骤。 具体说来，本机 UEFI 环境要求你在系统的启动磁盘上创建多个分区。 如果你与[预留媒体的文档](https://technet.microsoft.com/library/79465d90-4831-4872-96c2-2062d80f5583?f=255&MSPPError=-2147217396#BKMK_CreatePrestagedMedia)一起关注，说明仅提供单个分区启动磁盘，因此在应用到 Surface 设备时将失败。

有关将预置媒体应用于 UEFI 设备（如 Surface 设备）的说明，请参阅[如何在 Microsoft 终结点配置管理器博客文章中的多分区磁盘上应用任务序列预留媒体（适用于 BIOS 或 UEFI 电脑](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2014/04/02/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned-disks-for-bios-or-uefi-pcs-in-system-center-configuration-manager/)）。

##  <a name="licensing-conflicts-with-oem-activation-3.0"></a>与 OEM 激活3.0 的许可冲突

Surface 设备预装了 Windows 的许可副本。 例如，Surface Pro 4 预装了 Windows 10 专业版。 此预安装的 Windows 副本的许可证密钥嵌入在具有 OEM 激活3.0 （OA 3.0）的设备的固件中。 当使用 OA 3.0 密钥在设备上运行 Windows 安装媒体时，Windows 安装程序会自动读取许可证密钥并使用它来安装和激活 Windows。 在大多数情况下，这将简化 Windows 的重新安装，因为用户不必查找或输入许可证密钥。

使用 Windows 企业重新映像设备时，此嵌入式许可证密钥不会导致冲突。 这是因为 Windows 企业版的安装媒体配置为仅安装 Windows 的企业版，因此与系统固件中嵌入的许可证密钥不兼容。 如果未指定产品密钥（例如当你打算使用密钥管理服务（KMS）或基于 Active Directory 的激活）激活时，将使用常规批量许可证密钥（GVLK），直到使用其中一个技术激活 Windows。

但是，当组织希望使用与固件嵌入式密钥兼容的 Windows 版本时，可能会出现问题。 例如，要在最初随 Windows 10 家庭版附带的3个设备上安装 Windows 10 专业版的组织可能会在 Windows 安装程序在安装期间自动读取 Home 版密钥而不是专业版时遇到问题。 若要避免此冲突，你可以使用 Ei 或 Pid.txt 文件显式指示 Windows 安装程序提示输入产品密钥，或者你可以在部署任务序列中输入特定的产品密钥。 有关详细信息，请参阅[Windows 设置版本配置和产品 ID 文件](https://technet.microsoft.com/library/hh824952.aspx)。 如果你没有特定密钥，你可以使用 Windows 的默认产品密钥，你可以在设备合作伙伴中心的[自定义和部署 windows 10 操作系统](https://dpcenter.microsoft.com/en/Windows/Build/cp-Windows-10-build)中找到它。

##  <a name="apply-an-asset-tag-during-deployment"></a>在部署过程中应用资产标签

Surface Studio、Surface Book、Surface Pro 4、Surface Pro 3 和 Surface 3 设备都支持在 UEFI 中应用资产标记。 即使操作系统失败，也可以使用此资产标记从 UEFI 标识设备，也可以从操作系统中查询它。 若要阅读有关 Surface 资产标签功能的详细信息，请参阅[Surface Pro 3](https://blogs.technet.microsoft.com/askcore/2014/10/20/asset-tag-tool-for-surface-pro-3/)博客文章的 "资产标签" 工具。

若要在 Configuration Manager 部署任务序列期间使用[Surface 资产标记 CLI 实用工具](https://www.microsoft.com/download/details.aspx?id=44076)应用资产标签，请使用[Configuration manager 任务序列博客文章期间在设置 Surface 资产标签](https://blogs.technet.microsoft.com/jchalfant/set-surface-pro-3-asset-tag-during-a-configuration-manager-task-sequence/)中找到的脚本和说明。

##  <a name="configure-push-button-reset"></a>配置推送按钮重置

将 Windows 部署到 Surface 设备时，默认情况下会配置 Windows 的按钮重置功能，以将系统恢复到尚未配置环境的状态。 使用 reset 函数时，系统会丢弃任何已安装的应用程序和设置。 尽管在某些情况下，将系统还原为没有应用程序和设置的状态很有用，因为在专业环境中，这会有效地将系统呈现为最终用户不可用。

但是，可以配置推送按钮重置，以将系统配置还原为最终用户可以使用的状态。 按照[部署推拉按钮重置功能](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/deploy-push-button-reset-features)中概述的过程为你的设备自定义按钮重置体验。

---
title: Surface 和 Surface Microsoft Endpoint Configuration Manager
description: 使用 Configuration Manager 管理和部署 Surface 设备基本上与任何其他电脑相同;本文介绍可能需要其他注意事项的方案。
keywords: 管理， 部署， 更新， 驱动程序， 固件
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
ms.date: 08/12/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 88d25786601bdb88c027b689431d1c08c80cb9ec
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448335"
---
# <a name="considerations-for-surface-and-microsoft-endpoint-configuration-manager"></a>Surface 和 Surface Microsoft Endpoint Configuration Manager

从根本上说，使用 Microsoft Endpoint Configuration Manager Surface 设备的管理和部署与任何其他电脑的管理和部署相同。 与任何其他电脑一样，Surface 设备的部署包括导入驱动程序、导入 Windows 映像、准备部署任务序列，然后将任务序列部署到集合。 部署后，Surface 设备与任何其他Windows客户端一样;若要发布应用、设置和策略，请使用与任何其他设备相同的过程。

若要了解更多信息，请参阅[Microsoft Endpoint Configuration Manager文档](/mem/configmgr/)。

虽然 Surface 设备的部署和管理与其他电脑基本类似，但有些方案可能需要执行其他 IT 任务，如本文所述。 

> [!TIP]
> 使用 [Surface 设备的 Current Branch Microsoft Endpoint Configuration Manager](/mem/configmgr/core/servers/manage/updates) Surface 设备。

## <a name="update-surface-device-drivers-and-firmware"></a>更新 Surface 设备驱动程序和固件

若要使用 Configuration Manager 或 WSUS Windows Server Update Services (部署更新设备驱动程序) ，请参阅[管理 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)。

## <a name="surface-ethernet-adapters-and-configuration-manager-deployment"></a>Surface 以太网适配器和 Configuration Manager 部署

Configuration Manager 在部署期间用于标识设备的默认机制是 MAC 地址 (访问控制) 。 由于 MAC 地址与以太网控制器关联，因此在多个设备之间共享的以太网适配器将导致 Configuration Manager 将每个设备标识为一个设备，从而导致部署失败。 

为了确保在部署期间使用同一以太网适配器的 Surface 设备标识为唯一设备，你可以指示 Configuration Manager 使用另一种方法标识设备。 你可以指定 Configuration Manager 使用其他标识方法，如管理重复[的硬件标识符中记录：](/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers)

- 为 Surface 以太网适配器的 MAC 地址添加排除项，这将强制 Configuration Manager 忽略 MAC 地址，而首选系统 UUID。

- 使用脚本通过无线适配器的 MAC 地址标识新部署的 Surface 设备。

### <a name="surface-ethernet-driver"></a>Surface 以太网驱动程序

自 2016 起，Surface 以太网适配器的驱动程序已默认包含在 Windows并且不需要其他 IT 配置。 从驱动程序包含在 Windows 10开始，该驱动程序不再可从 Microsoft 下载中心下载。  (如果你需要部署早期版本的 Windows 10 专业版，可以从 [Microsoft](https://www.catalog.update.microsoft.com/Search.aspx?q=surface%20ethernet%20drivers) 更新目录下载最新) 。

## <a name="deploy-surface-app-with-configuration-manager"></a>使用 Configuration Manager 部署 Surface 应用

随着版本适用于企业的 Microsoft Store，Surface 应用不再作为驱动程序和固件下载提供。 在将 Surface 应用部署到托管的 Surface 设备或通过 Configuration Manager 进行部署期间，组织必须先通过配置管理器获取 Surface 适用于企业的 Microsoft Store。 若要了解更多信息，请参阅[使用 适用于企业的 Microsoft Store 部署 Surface 应用](deploy-surface-app-with-windows-store-for-business.md)。

## <a name="use-prestaged-media-with-surface-clients"></a>将预暂存媒体与 Surface 客户端一同使用

如果你的组织使用预暂存媒体在 Configuration Manager 部署之前将部署资源加载到计算机上，则 Surface 设备作为 UEFI 设备的性质可能需要你执行其他步骤。 具体而言，本机 UEFI 环境要求在系统的启动磁盘上创建多个分区。 如果你遵循有关预暂存媒体[](/mem/configmgr/osd/deploy-use/create-prestaged-media)的文档，则说明仅提供单个分区启动磁盘，因此在应用到 Surface 设备时将失败。

有关将预暂存媒体应用到 UEFI 设备（如 Surface 设备）的说明，请参阅 System 博客文章如何在 [BIOS 或 UEFI](https://techcommunity.microsoft.com/t5/configuration-manager-archive/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned/ba-p/392239) 电脑的多分区磁盘上应用任务序列预暂存媒体。

## <a name="licensing-conflicts-with-oem-activation-30"></a>许可与 OEM 激活 3.0 冲突

Surface 设备预安装有授权Windows。 此预安装副本的 Windows 许可证密钥嵌入到具有 [OEM 激活 3.0](/windows-hardware/manufacture/desktop/oem-activation-3) (OA 3.0) 的设备固件中。 当你在Windows OA 3.0 密钥的设备上运行安装媒体时，Windows安装程序会自动读取许可证密钥，并使用它安装和激活Windows。 在大多数情况下，这简化了Windows，因为用户无需查找或输入许可证密钥。

在使用嵌入式许可证密钥对设备进行Windows Enterprise，此嵌入式许可证密钥不会导致冲突。 这是因为 Windows Enterprise 的安装媒体配置为仅安装 Enterprise 版本的 Windows 因此与系统固件中嵌入的许可证密钥不兼容。 如果未指定产品密钥 (如打算使用密钥管理服务 [KMS] 激活或基于 Active Directory 的激活) ，则使用通用批量许可密钥 (GVLK) ，直到这些技术之一激活 Windows。

但是，当组织打算使用与固件嵌入密钥Windows版本时，可能会出现问题。 例如，想要在最初随 Windows 10 家庭版 一起安装的设备上安装 Windows 10 专业版 的组织在 Windows 安装程序在安装过程中自动读取家庭版密钥并安装为 Windows 10 家庭版 而不是时可能会遇到困难。Windows 10 专业版。 为了避免这种冲突，请使用 Ei.cfg 或 Pid.txt 文件明确指示 Windows 安装程序提示输入产品密钥，或在部署任务序列中输入特定产品密钥。 有关详细信息，请参阅 Windows [安装程序版本配置和产品 ID 文件](/windows-hardware/manufacture/desktop/windows-setup-edition-configuration-and-product-id-files--eicfg-and-pidtxt)。 如果没有特定密钥，可以使用默认产品密钥进行Windows。 有关详细信息，请参阅部署[Windows 10](/windows/deployment/deploy)。

## <a name="apply-an-asset-tag-during-deployment"></a>在部署过程中应用资产标记

使用 [Surface Asset 标记工具](assettag.md)，即使操作系统出现故障，也可以从 UEFI 识别设备。 若要了解有关使用 Configuration Manager 管理资产有关详细信息，请参阅 Configuration [Manager 中的资源智能简介](/mem/configmgr/core/clients/manage/asset-intelligence/introduction-to-asset-intelligence)。

## <a name="configure-push-button-reset"></a>配置一键重置

当你将Windows Surface 设备时，默认情况下，Windows 的一键重置功能配置为将系统恢复为环境尚未配置的状态。 使用 reset 函数时，系统将丢弃任何已安装的应用程序和设置。 尽管在某些情况下，将系统还原到没有应用程序和设置的状态可能很有利，但是，在专业环境中，这会有效地使最终用户无法使用系统。

但是，可以将一键重置配置为将系统配置还原到可供最终用户使用的状态。 按照部署一键重置 [功能](/windows-hardware/manufacture/desktop/deploy-push-button-reset-features) 中概述的过程为设备自定义一键重置体验。

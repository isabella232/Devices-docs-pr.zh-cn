---
title: 管理 Configuration Manager 中的 Surface 驱动程序更新
description: 本文介绍了管理和部署 Surface 设备的固件和驱动程序更新的可用选项。
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, 固件, 更新, 设备, 管理, 部署, 驱动程序, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: da90a0481052d06c2108c8fd096d088bfacdcb87
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910997"
---
# <a name="manage-surface-driver-updates-in-configuration-manager"></a>管理 Configuration Manager 中的 Surface 驱动程序更新

## <a name="summary"></a>摘要

从[Microsoft System Center Configuration Manager版本 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates)开始，你可以直接通过 Configuration Manager 客户端同步和部署 Microsoft Surface 固件和驱动程序更新。 此过程类似于部署定期更新。 但是，需要一些额外的配置才能将 Surface 驱动程序更新放入你的目录中。

## <a name="prerequisites"></a>系统必备

若要管理 Surface 驱动程序更新，必须满足以下先决条件：

- 必须使用 Configuration Manager 版本 1710 或更高版本。
- 所有软件更新点 (SSP) 必须Windows Server 2016或更高版本。 否则，Configuration Manager 将忽略此设置，并且 Surface 驱动程序将不会同步。

> [!NOTE]
> 如果你的环境不满足先决条件，请参阅常见问题部分中用于部署 Surface[](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1)驱动程序和固件更新的[替代方法](#frequently-asked-questions-faq)。

## <a name="useful-log-files"></a>有用的日志文件

当你管理 Surface 驱动程序更新时，以下日志特别有用。

|日志名称|描述|
|---|---|
|WCM.log|记录有关软件更新点配置的详细信息以及订阅的更新类别、分类和语言的 WSUS 服务器连接。|
|WsyncMgr.log|记录有关软件更新同步过程的详细信息。|

这些日志位于管理 SUP 的网站服务器上，或者 SUP 本身（如果直接安装在站点服务器上）。
有关 Configuration Manager 日志的完整列表，请参阅[Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)。

## <a name="enabling-surface-driver-updates-management"></a>启用 Surface 驱动程序更新管理

若要在 Configuration Manager 中启用 Surface 驱动程序更新管理，请按照以下步骤操作：

1. 在 Configuration Manager 控制台中，转到"**管理**  >  **概述**  >  **""站点配置**  >  **站点"。**
1. 选择包含适用于您的环境的顶级 SUP 服务器的网站。
1. 在功能区上，选择 **"配置网站组件"，** 然后选择"**软件更新点"。** 或者，右键单击该网站，然后选择配置**站点组件**  >  **软件更新点**。
1. 在" **分类"** 选项卡上，选中" **包括 Microsoft Surface 驱动程序和固件更新** "复选框。

   ![软件更新点组件属性。](images/manage-surface-driver-updates-1.png)

1. 当出现以下警告消息时，请选择"确定 **"。**

   ![Configuration Manager。](images/manage-surface-driver-updates-2.png)

1. 在"产品"选项卡上，选择要更新的产品，然后选择"确定 **"。**

   大多数驱动程序都属于以下产品组：

   - Windows 10和更高版本的驱动程序
   - Windows 10及更高版本升级&服务驱动程序
   - Windows 10周年更新和更高版本的服务驱动程序
   - Windows 10周年更新和更高版本升级&服务驱动程序
   - Windows 10 创意者更新及更高版本的服务驱动程序
   - Windows 10 创意者更新和更高版本升级&服务驱动程序
   - Windows 10 Fall Creators Update和更高版本的服务驱动程序
   - Windows 10 Fall Creators Update和更高版本升级&服务驱动程序
   - Windows 10S 和更高版本的服务驱动程序
   - Windows 10用于测试的 S 版本 1709 和更高版本的服务驱动程序
   - Windows 10S 版本 1709 和更高版本升级&服务驱动程序进行测试

   > [!NOTE]
   > 大多数 Surface 驱动程序都属于多个Windows 10组。 您可能不需要选择此处列出的所有产品。 为了帮助减少填充更新目录的产品数量，我们建议您仅选择您的环境需要用于同步的产品。

## <a name="verifying-the-configuration"></a>验证配置

若要验证 SUP 是否正确配置，请按照以下步骤操作：

1. 打开 WsyncMgr.log，然后查找以下条目：

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   如果在 WsyncMgr.log 中记录以下任一条目，请重新检查上一节中的步骤 4：

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. 打开 WCM.log，然后查找类似于以下内容的条目：

   ![WCM.log 设置。](images/manage-surface-driver-updates-3.png)

   此项是一个 XML 元素，其中列出了 SUP 服务器当前同步的每种产品组和分类。 例如，您可能会看到类似于以下内容的条目：

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   如果找不到在上一部分的步骤 6 中选定的产品，请仔细检查是否保存 SUP 设置。

   还可以等到下一次同步完成，然后检查 Surface 驱动程序和固件更新是否在 Configuration Manager 控制台的软件更新中列出。 例如，控制台可能会显示以下信息。

   ![所有软件更新搜索结果。](images/manage-surface-driver-updates-4.png)

## <a name="manual-synchronization"></a>手动同步

如果您不想等到下一次同步，请按照以下步骤启动同步：

1. 在 Configuration Manager 控制台中，转到"**软件库**  >  **概述**  >  **""软件更新**  >  **""所有软件更新"。**
1. 在功能区上，选择"**同步软件更新"。** 或者，右键单击 **"所有软件更新"，** 然后选择"**同步软件更新"。**
1. 通过查找 WsyncMgr.log 中的以下条目监视同步进度：

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## <a name="deploying-surface-firmware-and-driver-updates"></a>部署 Surface 固件和驱动程序更新

可以部署 Surface 固件和驱动程序更新的方式与部署其他更新的方式相同。

有关部署详细信息，请参阅[System Center 2012 Configuration Manager–Part7： Software Updates (Deploy) ](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/)。

## <a name="frequently-asked-questions-faq"></a>常见问题解答 (FAQ)

**按照本文中的步骤操作后，我的 Surface 驱动程序仍无法同步。 为什么？**

如果你从上游的 WSUS Windows Server Update Services (服务器（而不是 Microsoft 更新）进行) ，请确保将上游 WSUS 服务器配置为支持和同步 Surface 驱动程序更新。 所有下游服务器都限制为位于上游 WSUS 服务器数据库中的更新。

WSUS 中分类为驱动程序的更新超过 68，000 个。 为了防止非 Surface 相关驱动程序同步到 Configuration Manager，Microsoft 会针对允许列表筛选驱动程序同步。 发布新允许列表并将其合并到 Configuration Manager 后，新驱动程序将添加到下一个同步后的控制台中。 Microsoft 旨在每月将 Surface 驱动程序添加到允许列表中，以与每月更新版本保持一致，使其可用于与 Configuration Manager 同步。

如果 Configuration Manager 环境脱机，则每次将服务更新导入到 Configuration Manager 时都会导入 [新的](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) 允许列表。 在 Configuration Manager 控制台中显示更新之前，还必须导入包含驱动程序的新 [WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) 目录。 由于独立 WSUS 环境包含的驱动程序多于 Configuration Manager SUP，因此我们建议你建立具有联机功能的 Configuration Manager 环境，并对其进行配置以同步 Surface 驱动程序。 这提供了与脱机环境非常类似的较小 WSUS 导出。

如果 Configuration Manager 环境联机且能够检测新更新，则将自动接收列表更新。 如果看不到预期的驱动程序，请查看 WCM.log 和 WsyncMgr.log 文件，了解同步失败情况。

**我的 Configuration Manager 环境处于脱机状态。 我能否将 Surface 驱动程序手动导入 WSUS？**

否。 即使更新已导入 WSUS，如果更新未在允许列表中列出，也不会导入到 Configuration Manager 控制台进行部署。 必须使用服务连接 [工具将](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) 服务更新导入配置管理器以更新允许列表。

**必须采用哪些替代方法来部署 Surface 驱动程序和固件更新？**

若要了解如何通过替代渠道部署 Surface 驱动程序和固件更新，请参阅管理 [Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)。 如果你希望下载 .msi 或 .exe 文件，然后通过传统软件部署通道进行部署，请参阅使用 Configuration Manager 保持 [Surface 固件更新](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager)。

## <a name="additional-information"></a>其他信息

有关 Surface 驱动程序和固件更新详细信息，请参阅以下文章：

- [管理 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)
- [Surface 和 System Center Configuration Manager 的注意事项](considerations-for-surface-and-system-center-configuration-manager.md)

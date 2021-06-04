---
title: 管理 Configuration Manager 中的 Surface 更新
description: 本文介绍用于管理和部署 Surface 设备的固件和驱动程序更新的可用选项。
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
ms.openlocfilehash: be32309b26ff6a873c36927cc39595022c4dbb90
ms.sourcegitcommit: ed4478dd3c6116a25b1e01a3a0f5ff6c1f940013
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "10897070"
---
# 管理 Configuration Manager 中的 Surface 更新

##  <a name="summary"></a>摘要

从[Microsoft System Center Configuration Manager 版本 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates)开始，您可以直接通过 Configuration Manager 客户端同步和部署 Microsoft Surface 固件和驱动程序更新。 该过程类似于部署定期更新。 但是，需要执行一些其他配置才能将 Surface 驱动程序更新到目录中。

##  <a name="prerequisites"></a>必备条件

若要管理 Surface driver 更新，必须满足以下先决条件：

- 您必须使用 Configuration Manager 版本1710或更高版本。
- 所有软件更新点（SUPs）必须运行 Windows Server 2016 或更高版本。 否则，Configuration Manager 忽略此设置，并且不会同步 Surface 驱动程序。

> [!NOTE]
> 如果你的环境不符合先决条件，请参阅 "[常见问题解答](#frequently-asked-questions-faq)" 部分中的用于部署 Surface 驱动程序和固件更新的[备用方法](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1)。

## 有用的日志文件

在管理 Surface driver 更新时，以下日志尤其有用。

|日志名称|描述|
|---|---|
|WCM .log|记录有关已订阅的更新类别、分类和语言的软件更新点配置和到 WSUS 服务器的连接的详细信息。|
|WsyncMgr|记录有关软件更新同步过程的详细信息。|

这些日志位于管理 SUP 的网站服务器或 SUP 本身（如果直接安装在网站服务器上）。
有关 Configuration Manager 日志的完整列表，请参阅[System Center Configuration Manager 中的日志记录文件](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)。

## 启用 Surface driver 更新管理

若要在 Configuration Manager 中启用 Surface driver 更新管理，请按照下列步骤操作：

1. 在 Configuration Manager 控制台中，转到 "**管理**  >  **概述**  >  **网站配置**  >  **网站**"。
1. 选择包含您的环境的顶级 SUP 服务器的网站。
1. 在功能区上，选择 "**配置网站组件**"，然后选择 "**软件更新点**"。 或者，右键单击网站，然后选择 "**配置网站组件**"  >  **软件更新点**。
1. 在 "**分类**" 选项卡上，选中 "**包括 Microsoft Surface 驱动程序和固件更新**" 复选框。

   ![软件更新点组件属性](images/manage-surface-driver-updates-1.png)

1. 当出现以下警告消息时，请选择 **"确定"**。

   ![Configuration Manager](images/manage-surface-driver-updates-2.png)

1. 在 "产品" 选项卡上，选择要更新的产品，然后选择 **"确定"**。

   大多数驱动程序属于以下产品组：

   - Windows 10 和更高版本驱动程序
   - Windows 10 及更高版本升级 & 服务驱动程序
   - Windows 10 周年更新及更高版本服务驱动程序
   - Windows 10 周年更新及更高版本升级 & 服务驱动程序
   - Windows 10 创意者更新及更高版本服务驱动程序
   - Windows 10 创意者更新及更高版本升级 & 服务驱动程序
   - Windows 10 秋季创意者更新及更高版本服务驱动程序
   - Windows 10 秋季创意者更新及更高版本升级 & 服务驱动程序
   - Windows 10 S 和更高版本的服务驱动程序
   - 适用于测试的 Windows 10 S 版本1709和更高版本的服务驱动程序
   - Windows 10 S 版本1709和更高版本升级 & 服务驱动程序以供测试

   > [!NOTE]
   > 大多数 Surface 驱动程序属于多个 Windows 10 产品组。 您可能无需选择此处列出的所有产品。 为了帮助减少填充更新目录的产品数，我们建议你仅选择你的环境同步所需的产品。

## 验证配置

若要验证 SUP 是否配置正确，请按照下列步骤操作：

1. 打开 WsyncMgr，然后查找以下条目：

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   如果在 WsyncMgr 中记录了以下任一条目，请重新选中上一节中的步骤4：

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. 打开 WCM .log，然后查找类似于以下内容的条目：

   ![WCM. 日志设置](images/manage-surface-driver-updates-3.png)

   此条目是一个 XML 元素，其中列出了当前由 SUP 服务器同步的所有产品组和分类。 例如，你可能会看到类似于以下内容的条目：

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   如果您在上一节的步骤6中找不到您选择的产品，请仔细检查 SUP 设置是否已保存。

   您也可以等到下一个同步完成，然后检查 "配置管理器" 控制台的 "软件更新" 中是否列出了 Surface 驱动程序和固件更新。 例如，控制台可能显示以下信息。

   ![所有软件更新搜索结果](images/manage-surface-driver-updates-4.png)

## 手动同步

如果您不想等到下一个同步，请按照以下步骤开始同步：

1. 在 Configuration Manager 控制台中，转到**软件库**  >  **概述**  >  **软件更新**  >  **所有软件更新**。
1. 在功能区上，选择 "**同步软件更新**"。 或者，右键单击 "**所有软件更新**"，然后选择 "**同步软件更新**"。
1. 通过在 WsyncMgr 中查找以下条目来监视同步进度：

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

## 部署 Surface 固件和驱动程序更新

你可以按照部署其他更新的相同方式部署 Surface 固件和驱动程序更新。

有关部署的详细信息，请参阅[System Center 2012 配置管理器-Part7：软件更新（部署）](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/)。

##  <a name="faq"></a>常见问题解答 (FAQ)

**按照本文中的步骤操作后，我的表面驱动程序仍不同步。 为什么？**

如果从上游 Windows Server 更新服务（WSUS）服务器（而不是 Microsoft Update）同步，请确保将上游 WSUS 服务器配置为支持和同步 Surface driver 更新。 所有下游服务器仅限于上游 WSUS 服务器数据库中存在的更新。

有68000个以上的更新被分类为 WSUS 中的驱动程序。 为了防止与非 Surface 相关的驱动程序同步到配置管理器，Microsoft 筛选器驱动程序将针对允许列表进行同步。 新的允许列表发布并合并到 Configuration Manager 后，新的驱动程序将在下一次同步后添加到控制台。 Microsoft 旨在让每月的图面驱动程序与每月更新版本相协调，以使其可用于同步到 Configuration Manager。

如果你的 Configuration Manager 环境处于脱机状态，则每次导入对 Configuration Manager 的[服务更新](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool)时都会导入新的允许列表。 在配置管理器控制台中显示更新之前，你还需要导入包含驱动程序的[新 WSUS 目录](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected)。 由于独立 WSUS 环境包含的驱动程序比配置管理器 SUP 多，因此我们建议你建立具有联机功能的 Configuration Manager 环境，并将其配置为同步 Surface 驱动程序。 这提供了一个与脱机环境非常相似的较小的 WSUS 导出。

如果你的 Configuration Manager 环境处于联机状态，并且能够检测到新的更新，你将自动收到列表的更新。 如果看不到预期的驱动程序，请查看 WCM .log 和 WsyncMgr 文件中是否存在任何同步失败。

**我的 Configuration Manager 环境处于离线状态。 我是否可以手动将 Surface 驱动程序导入到 WSUS？**

否。 即使更新已导入 WSUS，如果 "允许" 列表中未列出更新，则不会将更新导入到 Configuration Manager 控制台进行部署。 你必须使用[服务连接工具将服务](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool)更新导入到 Configuration Manager 以更新允许列表。

**我需要哪些备用方法来部署 Surface 驱动程序和固件更新？**

有关如何通过备选频道部署 Surface 驱动程序和固件更新的信息，请参阅[管理 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)。 如果想要下载 .msi 或 .exe 文件，然后通过传统软件部署通道进行部署，请参阅[使用 Configuration Manager 更新的 "保持 Surface 固件](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager)"。

## 其他信息

有关 Surface 驱动程序和固件更新的详细信息，请参阅以下文章：

- [管理 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)
- [Surface 和 System Center Configuration Manager 的注意事项](considerations-for-surface-and-system-center-configuration-manager.md)

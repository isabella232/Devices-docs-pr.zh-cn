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
# <span data-ttu-id="d142d-104">管理 Configuration Manager 中的 Surface 更新</span><span class="sxs-lookup"><span data-stu-id="d142d-104">Manage Surface driver updates in Configuration Manager</span></span>

## <span data-ttu-id="d142d-105">摘要</span><span class="sxs-lookup"><span data-stu-id="d142d-105">Summary</span></span>

<span data-ttu-id="d142d-106">从[Microsoft System Center Configuration Manager 版本 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates)开始，您可以直接通过 Configuration Manager 客户端同步和部署 Microsoft Surface 固件和驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="d142d-106">Starting in [Microsoft System Center Configuration Manager version 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), you can synchronize and deploy Microsoft Surface firmware and driver updates directly through the Configuration Manager client.</span></span> <span data-ttu-id="d142d-107">该过程类似于部署定期更新。</span><span class="sxs-lookup"><span data-stu-id="d142d-107">The process resembles deploying regular updates.</span></span> <span data-ttu-id="d142d-108">但是，需要执行一些其他配置才能将 Surface 驱动程序更新到目录中。</span><span class="sxs-lookup"><span data-stu-id="d142d-108">However, some additional configurations are required to get the Surface driver updates into your catalog.</span></span>

## <span data-ttu-id="d142d-109">必备条件</span><span class="sxs-lookup"><span data-stu-id="d142d-109">Prerequisites</span></span>

<span data-ttu-id="d142d-110">若要管理 Surface driver 更新，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="d142d-110">To manage Surface driver updates, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d142d-111">您必须使用 Configuration Manager 版本1710或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d142d-111">You must use Configuration Manager version 1710 or a later version.</span></span>
- <span data-ttu-id="d142d-112">所有软件更新点（SUPs）必须运行 Windows Server 2016 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d142d-112">All Software Update Points (SUPs) must run Windows Server 2016 or a later version.</span></span> <span data-ttu-id="d142d-113">否则，Configuration Manager 忽略此设置，并且不会同步 Surface 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="d142d-113">Otherwise, Configuration Manager ignores this setting and Surface drivers won't be synchronized.</span></span>

> [!NOTE]
> <span data-ttu-id="d142d-114">如果你的环境不符合先决条件，请参阅 "[常见问题解答](#frequently-asked-questions-faq)" 部分中的用于部署 Surface 驱动程序和固件更新的[备用方法](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1)。</span><span class="sxs-lookup"><span data-stu-id="d142d-114">If your environment doesn’t meet the prerequisites, refer to the [alternative methods](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) to deploy Surface driver and firmware updates in the [FAQ](#frequently-asked-questions-faq) section.</span></span>

## <span data-ttu-id="d142d-115">有用的日志文件</span><span class="sxs-lookup"><span data-stu-id="d142d-115">Useful log files</span></span>

<span data-ttu-id="d142d-116">在管理 Surface driver 更新时，以下日志尤其有用。</span><span class="sxs-lookup"><span data-stu-id="d142d-116">The following logs are especially useful when you manage Surface driver updates.</span></span>

|<span data-ttu-id="d142d-117">日志名称</span><span class="sxs-lookup"><span data-stu-id="d142d-117">Log name</span></span>|<span data-ttu-id="d142d-118">描述</span><span class="sxs-lookup"><span data-stu-id="d142d-118">Description</span></span>|
|---|---|
|<span data-ttu-id="d142d-119">WCM .log</span><span class="sxs-lookup"><span data-stu-id="d142d-119">WCM.log</span></span>|<span data-ttu-id="d142d-120">记录有关已订阅的更新类别、分类和语言的软件更新点配置和到 WSUS 服务器的连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d142d-120">Records details about the software update point configuration and connections to the WSUS server for subscribed update categories, classifications, and languages.</span></span>|
|<span data-ttu-id="d142d-121">WsyncMgr</span><span class="sxs-lookup"><span data-stu-id="d142d-121">WsyncMgr.log</span></span>|<span data-ttu-id="d142d-122">记录有关软件更新同步过程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d142d-122">Records details about the software updates sync process.</span></span>|

<span data-ttu-id="d142d-123">这些日志位于管理 SUP 的网站服务器或 SUP 本身（如果直接安装在网站服务器上）。</span><span class="sxs-lookup"><span data-stu-id="d142d-123">These logs are located on the site server that manages the SUP, or on the SUP itself if it's installed directly on a site server.</span></span>
<span data-ttu-id="d142d-124">有关 Configuration Manager 日志的完整列表，请参阅[System Center Configuration Manager 中的日志记录文件](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)。</span><span class="sxs-lookup"><span data-stu-id="d142d-124">For a complete list of Configuration Manager logs, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>

## <span data-ttu-id="d142d-125">启用 Surface driver 更新管理</span><span class="sxs-lookup"><span data-stu-id="d142d-125">Enabling Surface driver updates management</span></span>

<span data-ttu-id="d142d-126">若要在 Configuration Manager 中启用 Surface driver 更新管理，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d142d-126">To enable Surface driver updates management in Configuration Manager, follow these steps:</span></span>

1. <span data-ttu-id="d142d-127">在 Configuration Manager 控制台中，转到 "**管理**  >  **概述**  >  **网站配置**  >  **网站**"。</span><span class="sxs-lookup"><span data-stu-id="d142d-127">In the Configuration Manager console, go to **Administration** > **Overview** > **Site Configuration** > **Sites**.</span></span>
1. <span data-ttu-id="d142d-128">选择包含您的环境的顶级 SUP 服务器的网站。</span><span class="sxs-lookup"><span data-stu-id="d142d-128">Select the site that contains the top-level SUP server for your environment.</span></span>
1. <span data-ttu-id="d142d-129">在功能区上，选择 "**配置网站组件**"，然后选择 "**软件更新点**"。</span><span class="sxs-lookup"><span data-stu-id="d142d-129">On the ribbon, select **Configure Site Components**, and then select **Software Update Point**.</span></span> <span data-ttu-id="d142d-130">或者，右键单击网站，然后选择 "**配置网站组件**"  >  **软件更新点**。</span><span class="sxs-lookup"><span data-stu-id="d142d-130">Or, right-click the site, and then select **Configure Site Components** > **Software Update Point**.</span></span>
1. <span data-ttu-id="d142d-131">在 "**分类**" 选项卡上，选中 "**包括 Microsoft Surface 驱动程序和固件更新**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="d142d-131">On the **Classifications** tab, select the **Include Microsoft Surface drivers and firmware updates** check box.</span></span>

   ![软件更新点组件属性](images/manage-surface-driver-updates-1.png)

1. <span data-ttu-id="d142d-133">当出现以下警告消息时，请选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d142d-133">When you're prompted by the following warning message, select **OK**.</span></span>

   ![Configuration Manager](images/manage-surface-driver-updates-2.png)

1. <span data-ttu-id="d142d-135">在 "产品" 选项卡上，选择要更新的产品，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d142d-135">On the Products tab, select the products that you want to update, and then select **OK**.</span></span>

   <span data-ttu-id="d142d-136">大多数驱动程序属于以下产品组：</span><span class="sxs-lookup"><span data-stu-id="d142d-136">Most drivers belong to the following product groups:</span></span>

   - <span data-ttu-id="d142d-137">Windows 10 和更高版本驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-137">Windows 10 and later version drivers</span></span>
   - <span data-ttu-id="d142d-138">Windows 10 及更高版本升级 & 服务驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-138">Windows 10 and later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="d142d-139">Windows 10 周年更新及更高版本服务驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-139">Windows 10 Anniversary Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="d142d-140">Windows 10 周年更新及更高版本升级 & 服务驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-140">Windows 10 Anniversary Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="d142d-141">Windows 10 创意者更新及更高版本服务驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-141">Windows 10 Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="d142d-142">Windows 10 创意者更新及更高版本升级 & 服务驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-142">Windows 10 Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="d142d-143">Windows 10 秋季创意者更新及更高版本服务驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-143">Windows 10 Fall Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="d142d-144">Windows 10 秋季创意者更新及更高版本升级 & 服务驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-144">Windows 10 Fall Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="d142d-145">Windows 10 S 和更高版本的服务驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-145">Windows 10 S and Later Servicing Drivers</span></span>
   - <span data-ttu-id="d142d-146">适用于测试的 Windows 10 S 版本1709和更高版本的服务驱动程序</span><span class="sxs-lookup"><span data-stu-id="d142d-146">Windows 10 S Version 1709 and Later Servicing Drivers for testing</span></span>
   - <span data-ttu-id="d142d-147">Windows 10 S 版本1709和更高版本升级 & 服务驱动程序以供测试</span><span class="sxs-lookup"><span data-stu-id="d142d-147">Windows 10 S Version 1709 and Later Upgrade & Servicing Drivers for testing</span></span>

   > [!NOTE]
   > <span data-ttu-id="d142d-148">大多数 Surface 驱动程序属于多个 Windows 10 产品组。</span><span class="sxs-lookup"><span data-stu-id="d142d-148">Most Surface drivers belong to multiple Windows 10 product groups.</span></span> <span data-ttu-id="d142d-149">您可能无需选择此处列出的所有产品。</span><span class="sxs-lookup"><span data-stu-id="d142d-149">You may not have to select all the products that are listed here.</span></span> <span data-ttu-id="d142d-150">为了帮助减少填充更新目录的产品数，我们建议你仅选择你的环境同步所需的产品。</span><span class="sxs-lookup"><span data-stu-id="d142d-150">To help reduce the number of products that populate your Update Catalog, we recommend that you select only the products that are required by your environment for synchronization.</span></span>

## <span data-ttu-id="d142d-151">验证配置</span><span class="sxs-lookup"><span data-stu-id="d142d-151">Verifying the configuration</span></span>

<span data-ttu-id="d142d-152">若要验证 SUP 是否配置正确，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d142d-152">To verify that the SUP is configured correctly, follow these steps:</span></span>

1. <span data-ttu-id="d142d-153">打开 WsyncMgr，然后查找以下条目：</span><span class="sxs-lookup"><span data-stu-id="d142d-153">Open WsyncMgr.log, and then look for the following entry:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   <span data-ttu-id="d142d-154">如果在 WsyncMgr 中记录了以下任一条目，请重新选中上一节中的步骤4：</span><span class="sxs-lookup"><span data-stu-id="d142d-154">If either of the following entries is logged in WsyncMgr.log, recheck step 4 in the previous section:</span></span>

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. <span data-ttu-id="d142d-155">打开 WCM .log，然后查找类似于以下内容的条目：</span><span class="sxs-lookup"><span data-stu-id="d142d-155">Open WCM.log, and then look for an entry that resembles the following:</span></span>

   ![WCM. 日志设置](images/manage-surface-driver-updates-3.png)

   <span data-ttu-id="d142d-157">此条目是一个 XML 元素，其中列出了当前由 SUP 服务器同步的所有产品组和分类。</span><span class="sxs-lookup"><span data-stu-id="d142d-157">This entry is an XML element that lists every product group and classification that's currently synchronized by your SUP server.</span></span> <span data-ttu-id="d142d-158">例如，你可能会看到类似于以下内容的条目：</span><span class="sxs-lookup"><span data-stu-id="d142d-158">For example, you might see an entry that resembles the following:</span></span>

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   <span data-ttu-id="d142d-159">如果您在上一节的步骤6中找不到您选择的产品，请仔细检查 SUP 设置是否已保存。</span><span class="sxs-lookup"><span data-stu-id="d142d-159">If you can't find the products that you selected in step 6 in the previous section, double-check whether the SUP settings are saved.</span></span>

   <span data-ttu-id="d142d-160">您也可以等到下一个同步完成，然后检查 "配置管理器" 控制台的 "软件更新" 中是否列出了 Surface 驱动程序和固件更新。</span><span class="sxs-lookup"><span data-stu-id="d142d-160">You can also wait until the next synchronization finishes, and then check whether the Surface driver and firmware updates are listed in Software Updates in the Configuration Manager console.</span></span> <span data-ttu-id="d142d-161">例如，控制台可能显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="d142d-161">For example, the console might display the following information.</span></span>

   ![所有软件更新搜索结果](images/manage-surface-driver-updates-4.png)

## <span data-ttu-id="d142d-163">手动同步</span><span class="sxs-lookup"><span data-stu-id="d142d-163">Manual synchronization</span></span>

<span data-ttu-id="d142d-164">如果您不想等到下一个同步，请按照以下步骤开始同步：</span><span class="sxs-lookup"><span data-stu-id="d142d-164">If you don't want to wait until the next synchronization, follow these steps to start a synchronization:</span></span>

1. <span data-ttu-id="d142d-165">在 Configuration Manager 控制台中，转到**软件库**  >  **概述**  >  **软件更新**  >  **所有软件更新**。</span><span class="sxs-lookup"><span data-stu-id="d142d-165">In the Configuration Manager console, go to **Software Library** > **Overview** > **Software Updates** > **All Software Updates**.</span></span>
1. <span data-ttu-id="d142d-166">在功能区上，选择 "**同步软件更新**"。</span><span class="sxs-lookup"><span data-stu-id="d142d-166">On the ribbon, select **Synchronize Software Updates**.</span></span> <span data-ttu-id="d142d-167">或者，右键单击 "**所有软件更新**"，然后选择 "**同步软件更新**"。</span><span class="sxs-lookup"><span data-stu-id="d142d-167">Or, right-click **All Software Update**, and then select **Synchronize Software Update**.</span></span>
1. <span data-ttu-id="d142d-168">通过在 WsyncMgr 中查找以下条目来监视同步进度：</span><span class="sxs-lookup"><span data-stu-id="d142d-168">Monitor the synchronization progress by looking for the following entries in WsyncMgr.log:</span></span>

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

## <span data-ttu-id="d142d-169">部署 Surface 固件和驱动程序更新</span><span class="sxs-lookup"><span data-stu-id="d142d-169">Deploying Surface firmware and driver updates</span></span>

<span data-ttu-id="d142d-170">你可以按照部署其他更新的相同方式部署 Surface 固件和驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="d142d-170">You can deploy Surface firmware and driver updates in the same manner as you deploy other updates.</span></span>

<span data-ttu-id="d142d-171">有关部署的详细信息，请参阅[System Center 2012 配置管理器-Part7：软件更新（部署）](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/)。</span><span class="sxs-lookup"><span data-stu-id="d142d-171">For more information about deployment, see [System Center 2012 Configuration Manager–Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span></span>

## <span data-ttu-id="d142d-172">常见问题解答 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="d142d-172">Frequently asked questions (FAQ)</span></span>

**<span data-ttu-id="d142d-173">按照本文中的步骤操作后，我的表面驱动程序仍不同步。</span><span class="sxs-lookup"><span data-stu-id="d142d-173">After I follow the steps in this article, my Surface drivers are still not synchronized.</span></span> <span data-ttu-id="d142d-174">为什么？</span><span class="sxs-lookup"><span data-stu-id="d142d-174">Why?</span></span>**

<span data-ttu-id="d142d-175">如果从上游 Windows Server 更新服务（WSUS）服务器（而不是 Microsoft Update）同步，请确保将上游 WSUS 服务器配置为支持和同步 Surface driver 更新。</span><span class="sxs-lookup"><span data-stu-id="d142d-175">If you synchronize from an upstream Windows Server Update Services (WSUS) server, instead of Microsoft Update, make sure that the upstream WSUS server is configured to support and synchronize Surface driver updates.</span></span> <span data-ttu-id="d142d-176">所有下游服务器仅限于上游 WSUS 服务器数据库中存在的更新。</span><span class="sxs-lookup"><span data-stu-id="d142d-176">All downstream servers are limited to updates that are present in the upstream WSUS server database.</span></span>

<span data-ttu-id="d142d-177">有68000个以上的更新被分类为 WSUS 中的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="d142d-177">There are more than 68,000 updates that are classified as drivers in WSUS.</span></span> <span data-ttu-id="d142d-178">为了防止与非 Surface 相关的驱动程序同步到配置管理器，Microsoft 筛选器驱动程序将针对允许列表进行同步。</span><span class="sxs-lookup"><span data-stu-id="d142d-178">To prevent non-Surface related drivers from synchronizing to Configuration Manager, Microsoft filters driver synchronization against an allow list.</span></span> <span data-ttu-id="d142d-179">新的允许列表发布并合并到 Configuration Manager 后，新的驱动程序将在下一次同步后添加到控制台。</span><span class="sxs-lookup"><span data-stu-id="d142d-179">After the new allow list is published and incorporated into Configuration Manager, the new drivers are added to the console following the next synchronization.</span></span> <span data-ttu-id="d142d-180">Microsoft 旨在让每月的图面驱动程序与每月更新版本相协调，以使其可用于同步到 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="d142d-180">Microsoft aims to get the Surface drivers added to the allow list each month in alignment with monthly update releases to make them available for synchronization to Configuration Manager.</span></span>

<span data-ttu-id="d142d-181">如果你的 Configuration Manager 环境处于脱机状态，则每次导入对 Configuration Manager 的[服务更新](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool)时都会导入新的允许列表。</span><span class="sxs-lookup"><span data-stu-id="d142d-181">If your Configuration Manager environment is offline, a new allow list is imported every time that you import [servicing updates](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to Configuration Manager.</span></span> <span data-ttu-id="d142d-182">在配置管理器控制台中显示更新之前，你还需要导入包含驱动程序的[新 WSUS 目录](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected)。</span><span class="sxs-lookup"><span data-stu-id="d142d-182">You will also have to import a [new WSUS catalog](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) that contains the drivers before the updates are displayed in the Configuration Manager console.</span></span> <span data-ttu-id="d142d-183">由于独立 WSUS 环境包含的驱动程序比配置管理器 SUP 多，因此我们建议你建立具有联机功能的 Configuration Manager 环境，并将其配置为同步 Surface 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="d142d-183">Because a standalone WSUS environment contains more drivers than a Configuration Manager SUP, we recommend that you establish a Configuration Manager environment that has online capabilities, and that you configure it to synchronize Surface drivers.</span></span> <span data-ttu-id="d142d-184">这提供了一个与脱机环境非常相似的较小的 WSUS 导出。</span><span class="sxs-lookup"><span data-stu-id="d142d-184">This provides a smaller WSUS export that closely resembles the offline environment.</span></span>

<span data-ttu-id="d142d-185">如果你的 Configuration Manager 环境处于联机状态，并且能够检测到新的更新，你将自动收到列表的更新。</span><span class="sxs-lookup"><span data-stu-id="d142d-185">If your Configuration Manager environment is online and able to detect new updates, you will receive updates to the list automatically.</span></span> <span data-ttu-id="d142d-186">如果看不到预期的驱动程序，请查看 WCM .log 和 WsyncMgr 文件中是否存在任何同步失败。</span><span class="sxs-lookup"><span data-stu-id="d142d-186">If you don’t see the expected drivers, please review the WCM.log and WsyncMgr.log files for any synchronization failures.</span></span>

**<span data-ttu-id="d142d-187">我的 Configuration Manager 环境处于离线状态。</span><span class="sxs-lookup"><span data-stu-id="d142d-187">My Configuration Manager environment is offline.</span></span> <span data-ttu-id="d142d-188">我是否可以手动将 Surface 驱动程序导入到 WSUS？</span><span class="sxs-lookup"><span data-stu-id="d142d-188">Can I manually import Surface drivers into WSUS?</span></span>**

<span data-ttu-id="d142d-189">否。</span><span class="sxs-lookup"><span data-stu-id="d142d-189">No.</span></span> <span data-ttu-id="d142d-190">即使更新已导入 WSUS，如果 "允许" 列表中未列出更新，则不会将更新导入到 Configuration Manager 控制台进行部署。</span><span class="sxs-lookup"><span data-stu-id="d142d-190">Even if the update is imported into WSUS, the update won't be imported into the Configuration Manager console for deployment if it isn't listed in the allow list.</span></span> <span data-ttu-id="d142d-191">你必须使用[服务连接工具将服务](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool)更新导入到 Configuration Manager 以更新允许列表。</span><span class="sxs-lookup"><span data-stu-id="d142d-191">You must use the [Service Connection Tool](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to import servicing updates to Configuration Manager to update the allow list.</span></span>

**<span data-ttu-id="d142d-192">我需要哪些备用方法来部署 Surface 驱动程序和固件更新？</span><span class="sxs-lookup"><span data-stu-id="d142d-192">What alternative methods do I have to deploy Surface driver and firmware updates?</span></span>**

<span data-ttu-id="d142d-193">有关如何通过备选频道部署 Surface 驱动程序和固件更新的信息，请参阅[管理 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="d142d-193">For information about how to deploy Surface driver and firmware updates through alternative channels, see [Manage Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span> <span data-ttu-id="d142d-194">如果想要下载 .msi 或 .exe 文件，然后通过传统软件部署通道进行部署，请参阅[使用 Configuration Manager 更新的 "保持 Surface 固件](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager)"。</span><span class="sxs-lookup"><span data-stu-id="d142d-194">If you want to download the .msi or .exe file, and then deploy through traditional software deployment channels, see [Keeping Surface Firmware Updated with Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span></span>

## <span data-ttu-id="d142d-195">其他信息</span><span class="sxs-lookup"><span data-stu-id="d142d-195">Additional Information</span></span>

<span data-ttu-id="d142d-196">有关 Surface 驱动程序和固件更新的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="d142d-196">For more information about Surface driver and firmware updates, see the following articles:</span></span>

- [<span data-ttu-id="d142d-197">管理 Surface 驱动程序和固件更新</span><span class="sxs-lookup"><span data-stu-id="d142d-197">Manage Surface driver and firmware updates</span></span>](manage-surface-driver-and-firmware-updates.md)
- [<span data-ttu-id="d142d-198">Surface 和 System Center Configuration Manager 的注意事项</span><span class="sxs-lookup"><span data-stu-id="d142d-198">Considerations for Surface and System Center Configuration Manager</span></span>](considerations-for-surface-and-system-center-configuration-manager.md)

---
title: Microsoft Surface Dock 1 固件更新
description: 本文介绍了如何使用 Microsoft Surface 扩展坞固件更新在原始 Surface 扩展坞 1 上安装和管理固件。 在 Surface 设备上安装时，它将更新连接到 Surface 设备的 Surface 扩展坞 1 设备。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319206"
---
# <span data-ttu-id="3f764-104">Microsoft Surface 扩展坞固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-104">Microsoft Surface Dock Firmware Update</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f764-105">本文包含适用于 IT 管理员的技术说明。</span><span class="sxs-lookup"><span data-stu-id="3f764-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="3f764-106">如果你是家庭用户，请参阅如何在 Microsoft 支持站点上更新[Surface 扩展](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   坞固件。</span><span class="sxs-lookup"><span data-stu-id="3f764-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="3f764-107">支持站点上的说明与下面的一般安装步骤相同，但本文提供了用于监视、验证更新以及将更新部署到网络上多台设备的其他信息。</span><span class="sxs-lookup"><span data-stu-id="3f764-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="3f764-108">本文介绍了如何使用 Microsoft Surface 扩展坞固件更新在原始 Surface 扩展坞 1 上安装和管理固件。</span><span class="sxs-lookup"><span data-stu-id="3f764-108">This article explains how to use Microsoft Surface Dock Firmware Update to install and manage firmware on the original Surface Dock 1.</span></span> <span data-ttu-id="3f764-109">在 Surface 设备上安装时，它将更新连接到 Surface 设备的 Surface 扩展坞 1 设备。</span><span class="sxs-lookup"><span data-stu-id="3f764-109">When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.</span></span>

> [!NOTE]
> <span data-ttu-id="3f764-110">本文不适用于 Surface Dock 2，它通过 Windows 更新或 Microsoft Endpoint Configuration Manager 或其他 MSI 部署工具自动接收更新。</span><span class="sxs-lookup"><span data-stu-id="3f764-110">This article does not apply to Surface Dock 2, which receives updates automatically via Windows Update or by using Microsoft Endpoint Configuration Manager or other MSI deployment tools.</span></span> <span data-ttu-id="3f764-111">若要了解更多信息，请参阅 Surface 扩展 [坞中的新增功能](surface-dock-whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="3f764-111">To learn more, see [What’s new in Surface Dock](surface-dock-whats-new.md).</span></span>

<span data-ttu-id="3f764-112">此工具取代以前作为适用于 IT 的 Surface Tools 的一部分可供下载的早期的 Microsoft Surface Dock Updater 工具。</span><span class="sxs-lookup"><span data-stu-id="3f764-112">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="3f764-113">之前的工具名为 Surface_Dock_Updater_vx.xx.xxx.x.msi (其中 x 指示版本号) 且不再可供下载，因此不应使用。</span><span class="sxs-lookup"><span data-stu-id="3f764-113">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <a name="install-the-surface-dock-firmware-update"></a><span data-ttu-id="3f764-114">安装 Surface 扩展坞固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-114">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="3f764-115">本节介绍如何手动安装固件更新。</span><span class="sxs-lookup"><span data-stu-id="3f764-115">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="3f764-116">Microsoft 会定期发布新版本的 Surface 扩展坞固件更新。</span><span class="sxs-lookup"><span data-stu-id="3f764-116">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="3f764-117">MSI 文件不是自行更新的。</span><span class="sxs-lookup"><span data-stu-id="3f764-117">The MSI file is not self-updating.</span></span> <span data-ttu-id="3f764-118">如果你已经将 MSI 部署到 Surface 设备并发布了新版本的固件，则需要部署新版本。</span><span class="sxs-lookup"><span data-stu-id="3f764-118">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="3f764-119">下载并安装 [Microsoft Surface 扩展坞固件更新](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="3f764-119">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="3f764-120">更新需要运行 Windows 10 版本 1803 或更高版本的 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="3f764-120">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="3f764-121">安装 MSI 文件可能会提示你重新启动 Surface。</span><span class="sxs-lookup"><span data-stu-id="3f764-121">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="3f764-122">但是，执行更新不需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="3f764-122">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="3f764-123">断开 Surface 设备与 Surface 扩展坞连接，等待约 5 秒，然后重新连接。</span><span class="sxs-lookup"><span data-stu-id="3f764-123">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="3f764-124">Surface 扩展坞固件更新将在后台以静默方式更新扩展坞。</span><span class="sxs-lookup"><span data-stu-id="3f764-124">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="3f764-125">此过程可能需要几分钟才能完成，即使中断，也会继续。</span><span class="sxs-lookup"><span data-stu-id="3f764-125">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <a name="monitor-the-surface-dock-firmware-update"></a><span data-ttu-id="3f764-126">监视 Surface 扩展坞固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-126">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="3f764-127">此部分是可选的，概述了如何监视固件更新的安装。</span><span class="sxs-lookup"><span data-stu-id="3f764-127">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="3f764-128">若要监视更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3f764-128">To monitor the update:</span></span>

1. <span data-ttu-id="3f764-129">打开事件查看器，浏览到 Windows**日志 > 应用程序**，然后在右侧\*\*\*\* 窗格中的操作下单击"筛选当前日志\*\*\*\*"，输入事件源旁边的**SurfaceDockFwUpdate，** 然后单击"**确定**"。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3f764-129">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="3f764-130">在提升的命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="3f764-130">Type the following command at an elevated command prompt:</span></span>

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="3f764-131">安装更新，如本文下 [一节](#install-the-surface-dock-firmware-update) 中所述。</span><span class="sxs-lookup"><span data-stu-id="3f764-131">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>

4. <span data-ttu-id="3f764-132">具有以下文本的事件 2007 表示成功更新：固件**更新已完成。hr=0 DriverTelementry EventCode = 2007。**</span><span class="sxs-lookup"><span data-stu-id="3f764-132">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 

   <span data-ttu-id="3f764-133">如果更新不成功，则事件 ID 2007 将显示为 **错误** 事件而不是 **信息**。</span><span class="sxs-lookup"><span data-stu-id="3f764-133">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="3f764-134">此外，Windows 注册表中报告的版本不是最新的。</span><span class="sxs-lookup"><span data-stu-id="3f764-134">Additionally, the version reported in the Windows Registry will not be current.</span></span>
   
5. <span data-ttu-id="3f764-135">更新完成后，更新后的 DWORD 值将显示在 Windows 注册表中，与该工具的当前版本相对应。</span><span class="sxs-lookup"><span data-stu-id="3f764-135">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="3f764-136">有关详细信息 [，请参阅](#versions-reference) 本文中的版本参考部分。</span><span class="sxs-lookup"><span data-stu-id="3f764-136">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="3f764-137">例如：</span><span class="sxs-lookup"><span data-stu-id="3f764-137">For example:</span></span>

    - <span data-ttu-id="3f764-138">Component10CurrentFwVersion 0x04ac3970 (78395760) </span><span class="sxs-lookup"><span data-stu-id="3f764-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="3f764-139">Component20CurrentFwVersion 0x04915a70 (76634736) </span><span class="sxs-lookup"><span data-stu-id="3f764-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="3f764-140">如果在事件文本中看到"找不到源 SurfaceDockFwUpdate 中的事件 ID xxxx 的说明"，这是预期且可以忽略的。</span><span class="sxs-lookup"><span data-stu-id="3f764-140">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="3f764-141">另请参阅本文中的以下部分：</span><span class="sxs-lookup"><span data-stu-id="3f764-141">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="3f764-142">如何验证固件更新的完成情况</span><span class="sxs-lookup"><span data-stu-id="3f764-142">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="3f764-143">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="3f764-143">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="3f764-144">疑难解答提示</span><span class="sxs-lookup"><span data-stu-id="3f764-144">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="3f764-145">版本参考</span><span class="sxs-lookup"><span data-stu-id="3f764-145">Versions reference</span></span>](#versions-reference)

## <a name="network-deployment"></a><span data-ttu-id="3f764-146">网络部署</span><span class="sxs-lookup"><span data-stu-id="3f764-146">Network deployment</span></span>

<span data-ttu-id="3f764-147">可以使用 Windows Installer (Msiexec.exe) 将 Surface 扩展坞固件更新部署到整个网络的多个设备。</span><span class="sxs-lookup"><span data-stu-id="3f764-147">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="3f764-148">使用 Microsoft Endpoint Configuration Manager 或其他部署工具时，输入以下语法以确保安装是无提示的：</span><span class="sxs-lookup"><span data-stu-id="3f764-148">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="3f764-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span><span class="sxs-lookup"><span data-stu-id="3f764-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

<span data-ttu-id="3f764-150">例如：</span><span class="sxs-lookup"><span data-stu-id="3f764-150">For example:</span></span>

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> <span data-ttu-id="3f764-151">默认情况下日志文件创建一个数据库。</span><span class="sxs-lookup"><span data-stu-id="3f764-151">A log file is not created by default.</span></span> <span data-ttu-id="3f764-152">若要创建一个日志文件，您需要追加"/l*v [path]"。例如：Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span><span class="sxs-lookup"><span data-stu-id="3f764-152">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

<span data-ttu-id="3f764-153">有关详细信息，请参阅 [命令行选项](https://docs.microsoft.com/windows/win32/msi/command-line-options) 文档。</span><span class="sxs-lookup"><span data-stu-id="3f764-153">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f764-154">如果你想要使用任何其他方法更新 Surface 扩展坞，请参阅更新 Surface [扩展](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) 坞了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="3f764-154">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <a name="intune-deployment"></a><span data-ttu-id="3f764-155">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="3f764-155">Intune deployment</span></span>

<span data-ttu-id="3f764-156">可以使用 Intune 将 Surface 扩展坞固件更新分发到设备。</span><span class="sxs-lookup"><span data-stu-id="3f764-156">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="3f764-157">首先，你需要将 MSI 文件转换为 .intunewin 格式，如以下文档所述 [：Intune Standalone - Win32 应用管理](https://docs.microsoft.com/intune/apps/apps-win32-app-management)。</span><span class="sxs-lookup"><span data-stu-id="3f764-157">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="3f764-158">使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="3f764-158">Use the following command:</span></span>
  - **<span data-ttu-id="3f764-159">msiexec /i \<path to msi file\> /quiet /q</span><span class="sxs-lookup"><span data-stu-id="3f764-159">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <a name="how-to-verify-completion-of-the-firmware-update"></a><span data-ttu-id="3f764-160">如何验证固件更新的完成情况</span><span class="sxs-lookup"><span data-stu-id="3f764-160">How to verify completion of the firmware update</span></span>

<span data-ttu-id="3f764-161">Surface 扩展坞固件由两个组件组成：</span><span class="sxs-lookup"><span data-stu-id="3f764-161">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="3f764-162">**Component10：** MCU 控制器固件 (控制器) 单元</span><span class="sxs-lookup"><span data-stu-id="3f764-162">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="3f764-163">**Component20：** 显示 DP (固件) 端口。</span><span class="sxs-lookup"><span data-stu-id="3f764-163">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="3f764-164">成功完成 Surface 扩展坞固件更新会导致这些固件组件获得新的注册表项值。</span><span class="sxs-lookup"><span data-stu-id="3f764-164">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="3f764-165">验证更新：</span><span class="sxs-lookup"><span data-stu-id="3f764-165">To verify updates:</span></span>**

1. <span data-ttu-id="3f764-166">打开 Regedit 并导航到以下注册表路径：</span><span class="sxs-lookup"><span data-stu-id="3f764-166">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="3f764-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="3f764-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="3f764-168">查找注册表项 **：Component10CurrentFwVersion 和 Component20CurrentFwVersion，** 它引用当前位于设备的固件。</span><span class="sxs-lookup"><span data-stu-id="3f764-168">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Surface 扩展坞固件更新安装过程](images/regeditDock.png)

3. <span data-ttu-id="3f764-170">验证新的注册表项值是否与本文档末尾的 Versions 参考中列出的更新的注册表项值匹配。</span><span class="sxs-lookup"><span data-stu-id="3f764-170">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="3f764-171">如果值匹配，则固件已成功更新。</span><span class="sxs-lookup"><span data-stu-id="3f764-171">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="3f764-172">如果无法验证，请查看下一节中的事件日志记录和疑难解答提示。</span><span class="sxs-lookup"><span data-stu-id="3f764-172">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <a name="event-logging"></a><span data-ttu-id="3f764-173">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="3f764-173">Event logging</span></span>

**<span data-ttu-id="3f764-174">表 1. </span><span class="sxs-lookup"><span data-stu-id="3f764-174">Table 1.</span></span> <span data-ttu-id="3f764-175">Surface 扩展坞固件更新的日志文件</span><span class="sxs-lookup"><span data-stu-id="3f764-175">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="3f764-176">Log</span><span class="sxs-lookup"><span data-stu-id="3f764-176">Log</span></span>                              | <span data-ttu-id="3f764-177">位置</span><span class="sxs-lookup"><span data-stu-id="3f764-177">Location</span></span>                               | <span data-ttu-id="3f764-178">注释</span><span class="sxs-lookup"><span data-stu-id="3f764-178">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="3f764-179">Surface 扩展坞固件更新日志</span><span class="sxs-lookup"><span data-stu-id="3f764-179">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="3f764-180">需要指定路径， (注释) </span><span class="sxs-lookup"><span data-stu-id="3f764-180">Path needs to be specified (see note)</span></span> | <span data-ttu-id="3f764-181">此工具的早期版本将事件写到应用程序和服务日志\Microsoft Surface Dock Updater。</span><span class="sxs-lookup"><span data-stu-id="3f764-181">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="3f764-182">Windows 设备安装日志</span><span class="sxs-lookup"><span data-stu-id="3f764-182">Windows Device Install log</span></span>       | <span data-ttu-id="3f764-183">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="3f764-183">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="3f764-184">有关使用设备安装日志的信息，请参阅 [SetupAPI 日志记录](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) 文档。</span><span class="sxs-lookup"><span data-stu-id="3f764-184">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="3f764-185">表 2. </span><span class="sxs-lookup"><span data-stu-id="3f764-185">Table 2.</span></span> <span data-ttu-id="3f764-186">Surface 扩展坞固件更新的事件日志 ID</span><span class="sxs-lookup"><span data-stu-id="3f764-186">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="3f764-187">事件记录在应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="3f764-187">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="3f764-188">注意：此工具的早期版本将事件写到 Applications and Services Logs\Microsoft Surface Dock Updater。</span><span class="sxs-lookup"><span data-stu-id="3f764-188">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="3f764-189">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3f764-189">Event ID</span></span> | <span data-ttu-id="3f764-190">事件类型</span><span class="sxs-lookup"><span data-stu-id="3f764-190">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="3f764-191">2001</span><span class="sxs-lookup"><span data-stu-id="3f764-191">2001</span></span>     | <span data-ttu-id="3f764-192">扩展坞固件更新已启动。</span><span class="sxs-lookup"><span data-stu-id="3f764-192">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="3f764-193">2002</span><span class="sxs-lookup"><span data-stu-id="3f764-193">2002</span></span>     | <span data-ttu-id="3f764-194">扩展坞固件更新已跳过，因为扩展坞已知是最新的。</span><span class="sxs-lookup"><span data-stu-id="3f764-194">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="3f764-195">2003</span><span class="sxs-lookup"><span data-stu-id="3f764-195">2003</span></span>     | <span data-ttu-id="3f764-196">扩展坞固件更新无法获取固件版本。</span><span class="sxs-lookup"><span data-stu-id="3f764-196">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="3f764-197">2004</span><span class="sxs-lookup"><span data-stu-id="3f764-197">2004</span></span>     | <span data-ttu-id="3f764-198">查询固件版本。</span><span class="sxs-lookup"><span data-stu-id="3f764-198">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="3f764-199">2005</span><span class="sxs-lookup"><span data-stu-id="3f764-199">2005</span></span>     | <span data-ttu-id="3f764-200">扩展坞固件无法启动更新。</span><span class="sxs-lookup"><span data-stu-id="3f764-200">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="3f764-201">2006</span><span class="sxs-lookup"><span data-stu-id="3f764-201">2006</span></span>     | <span data-ttu-id="3f764-202">无法发送产品/有效负载对。</span><span class="sxs-lookup"><span data-stu-id="3f764-202">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="3f764-203">2007</span><span class="sxs-lookup"><span data-stu-id="3f764-203">2007</span></span>     | <span data-ttu-id="3f764-204">固件更新已完成。</span><span class="sxs-lookup"><span data-stu-id="3f764-204">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="3f764-205">2008</span><span class="sxs-lookup"><span data-stu-id="3f764-205">2008</span></span>     | <span data-ttu-id="3f764-206">BEGIN 扩展坞遥测。</span><span class="sxs-lookup"><span data-stu-id="3f764-206">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="3f764-207">2011</span><span class="sxs-lookup"><span data-stu-id="3f764-207">2011</span></span>     | <span data-ttu-id="3f764-208">END 扩展坞遥测。</span><span class="sxs-lookup"><span data-stu-id="3f764-208">END dock telemetry.</span></span>                                                  |

## <a name="troubleshooting-tips"></a><span data-ttu-id="3f764-209">疑难解答提示</span><span class="sxs-lookup"><span data-stu-id="3f764-209">Troubleshooting tips</span></span>

- <span data-ttu-id="3f764-210">Surface 扩展坞与交流电源完全断开连接以重置 Surface 扩展坞。</span><span class="sxs-lookup"><span data-stu-id="3f764-210">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="3f764-211">断开除 Surface 扩展坞之外的所有外围设备。</span><span class="sxs-lookup"><span data-stu-id="3f764-211">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="3f764-212">卸载任何当前 Surface 扩展坞固件更新，然后安装最新版本。</span><span class="sxs-lookup"><span data-stu-id="3f764-212">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="3f764-213">确保 Surface 扩展坞已断开连接，然后留出足够的时间，以便更新完成（通过扩展坞的以太网端口中的 LED 进行监视）。</span><span class="sxs-lookup"><span data-stu-id="3f764-213">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="3f764-214">等待 LED 停止闪烁，然后拔下 Surface 扩展坞电源。</span><span class="sxs-lookup"><span data-stu-id="3f764-214">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="3f764-215">将 Surface 扩展坞连接到其他设备，以查看其能否更新扩展坞。</span><span class="sxs-lookup"><span data-stu-id="3f764-215">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <a name="versions-reference"></a><span data-ttu-id="3f764-216">版本参考</span><span class="sxs-lookup"><span data-stu-id="3f764-216">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="3f764-217">安装文件以以下命名格式 \*\* 发布：Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI(\*\* 例如：Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) 并默认安装到 C：\Program Files\SurfaceUpdate。</span><span class="sxs-lookup"><span data-stu-id="3f764-217">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <a name="version-1.53.139.0"></a><span data-ttu-id="3f764-218">版本 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="3f764-218">Version 1.53.139.0</span></span>
*<span data-ttu-id="3f764-219">发布日期：2020 年 8 月 4 日</span><span class="sxs-lookup"><span data-stu-id="3f764-219">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="3f764-220">此版本的 Surface 扩展坞固件更新包括 Bug 修复和支持：</span><span class="sxs-lookup"><span data-stu-id="3f764-220">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="3f764-221">使用 Surface Pro X 更新 Surface 扩展坞 1。</span><span class="sxs-lookup"><span data-stu-id="3f764-221">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="3f764-222">如果你运行的是 Surface Pro X，请下载 。ARM64 内部版本。</span><span class="sxs-lookup"><span data-stu-id="3f764-222">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="3f764-223">对于所有其他设备，请使用 AMD64 版本。</span><span class="sxs-lookup"><span data-stu-id="3f764-223">For all other devices, use the AMD64 build.</span></span> 

#### <span data-ttu-id="3f764-224">注册表项值</span><span class="sxs-lookup"><span data-stu-id="3f764-224">Registry key values</span></span>

<span data-ttu-id="3f764-225">指示固件更新状态的注册表值与此工具的早期版本相同：</span><span class="sxs-lookup"><span data-stu-id="3f764-225">The registry values that indicate the status of firmware updates are unchanged from the previous version of this tool:</span></span> 

- <span data-ttu-id="3f764-226">Component10CurrentFwVersion 更新为 **4ac3970**。</span><span class="sxs-lookup"><span data-stu-id="3f764-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="3f764-227">Component20CurrentFwVersion 更新为 **4a1d570**。</span><span class="sxs-lookup"><span data-stu-id="3f764-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>
 
### <a name="version-1.42.139"></a><span data-ttu-id="3f764-228">版本 1.42.139</span><span class="sxs-lookup"><span data-stu-id="3f764-228">Version 1.42.139</span></span> 
*<span data-ttu-id="3f764-229">发布日期：2019 年 9 月 18 日</span><span class="sxs-lookup"><span data-stu-id="3f764-229">Release Date: September 18 2019</span></span>*

<span data-ttu-id="3f764-230">此版本包含在 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI，可更新后台固件。</span><span class="sxs-lookup"><span data-stu-id="3f764-230">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 

#### <span data-ttu-id="3f764-231">更新了注册表项值</span><span class="sxs-lookup"><span data-stu-id="3f764-231">Updated registry key values</span></span>

- <span data-ttu-id="3f764-232">Component10CurrentFwVersion 更新为 **4ac3970**。</span><span class="sxs-lookup"><span data-stu-id="3f764-232">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="3f764-233">Component20CurrentFwVersion 更新为 **4a1d570**。</span><span class="sxs-lookup"><span data-stu-id="3f764-233">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="3f764-234">它增加了对 Surface Pro 7 和 Surface Laptop 3 的支持。</span><span class="sxs-lookup"><span data-stu-id="3f764-234">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <a name="legacy-versions"></a><span data-ttu-id="3f764-235">旧版本</span><span class="sxs-lookup"><span data-stu-id="3f764-235">Legacy versions</span></span>

### <a name="version-2.23.139.0"></a><span data-ttu-id="3f764-236">版本 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="3f764-236">Version 2.23.139.0</span></span>
*<span data-ttu-id="3f764-237">发布日期：2018 年 10 月 10 日</span><span class="sxs-lookup"><span data-stu-id="3f764-237">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="3f764-238">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="3f764-238">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="3f764-239">添加对 Surface Pro 6 的支持</span><span class="sxs-lookup"><span data-stu-id="3f764-239">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="3f764-240">添加对 Surface Laptop 2 的支持</span><span class="sxs-lookup"><span data-stu-id="3f764-240">Add support for Surface Laptop 2</span></span>


### <a name="version-2.22.139.0"></a><span data-ttu-id="3f764-241">版本 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="3f764-241">Version 2.22.139.0</span></span>
*<span data-ttu-id="3f764-242">发布日期：2018 年 7 月 26 日</span><span class="sxs-lookup"><span data-stu-id="3f764-242">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="3f764-243">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="3f764-243">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="3f764-244">提高更新可靠性</span><span class="sxs-lookup"><span data-stu-id="3f764-244">Increase update reliability</span></span>
- <span data-ttu-id="3f764-245">添加对 Surface Go 的支持</span><span class="sxs-lookup"><span data-stu-id="3f764-245">Add support for Surface Go</span></span>

### <a name="version-2.12.136.0"></a><span data-ttu-id="3f764-246">版本 2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="3f764-246">Version 2.12.136.0</span></span>
*<span data-ttu-id="3f764-247">发布日期：2018 年 1 月 29 日</span><span class="sxs-lookup"><span data-stu-id="3f764-247">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="3f764-248">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="3f764-248">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="3f764-249">Surface 扩展坞主芯片集固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-249">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="3f764-250">Surface 扩展坞 DisplayPort 固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-250">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="3f764-251">改进了使用 Surface Book 或 Surface Book 2 时外部显示器的显示稳定性。</span><span class="sxs-lookup"><span data-stu-id="3f764-251">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="3f764-252">此外，在 Surface Book 设备上安装的此版本 Surface Dock Updater 包括：</span><span class="sxs-lookup"><span data-stu-id="3f764-252">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="3f764-253">Surface Book 底座固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-253">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="3f764-254">增加了 Surface 扩展坞固件更新支持，针对 Surface Book 设备做出了改进</span><span class="sxs-lookup"><span data-stu-id="3f764-254">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <a name="version-2.9.136.0"></a><span data-ttu-id="3f764-255">版本 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="3f764-255">Version 2.9.136.0</span></span>
*<span data-ttu-id="3f764-256">发布日期：2017 年 11 月 3 日</span><span class="sxs-lookup"><span data-stu-id="3f764-256">Release date: November 3, 2017</span></span>*

<span data-ttu-id="3f764-257">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="3f764-257">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3f764-258">Surface 扩展坞 DisplayPort 固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-258">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="3f764-259">通过无源显示端口适配器解决音频问题</span><span class="sxs-lookup"><span data-stu-id="3f764-259">Resolves an issue with audio over passive display port adapters</span></span>

### <a name="version-2.1.15.0"></a><span data-ttu-id="3f764-260">版本 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="3f764-260">Version 2.1.15.0</span></span>
*<span data-ttu-id="3f764-261">发布日期：2017 年 6 月 19 日</span><span class="sxs-lookup"><span data-stu-id="3f764-261">Release date: June 19, 2017</span></span>*

<span data-ttu-id="3f764-262">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="3f764-262">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3f764-263">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="3f764-263">Surface Laptop</span></span>
* <span data-ttu-id="3f764-264">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="3f764-264">Surface Pro</span></span>

### <a name="version-2.1.6.0"></a><span data-ttu-id="3f764-265">版本 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="3f764-265">Version 2.1.6.0</span></span>
*<span data-ttu-id="3f764-266">发布日期：2017 年 4 月 7 日</span><span class="sxs-lookup"><span data-stu-id="3f764-266">Release date: April 7, 2017</span></span>*

<span data-ttu-id="3f764-267">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="3f764-267">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3f764-268">Surface 扩展坞 DisplayPort 固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-268">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="3f764-269">要求使用 Windows 10</span><span class="sxs-lookup"><span data-stu-id="3f764-269">Requires Windows 10</span></span>

### <a name="version-2.0.22.0"></a><span data-ttu-id="3f764-270">版本 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="3f764-270">Version 2.0.22.0</span></span>
*<span data-ttu-id="3f764-271">发布日期：2016 年 10 月 21 日</span><span class="sxs-lookup"><span data-stu-id="3f764-271">Release date: October 21, 2016</span></span>*

<span data-ttu-id="3f764-272">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="3f764-272">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3f764-273">Surface 扩展坞 USB 固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-273">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="3f764-274">提升了以太网、音频和 USB 端口的可靠性</span><span class="sxs-lookup"><span data-stu-id="3f764-274">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <a name="version-1.0.8.0"></a><span data-ttu-id="3f764-275">版本 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="3f764-275">Version 1.0.8.0</span></span>
*<span data-ttu-id="3f764-276">发布日期：2016 年 4 月 26 日</span><span class="sxs-lookup"><span data-stu-id="3f764-276">Release date: April 26, 2016</span></span>*

<span data-ttu-id="3f764-277">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="3f764-277">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="3f764-278">Surface 扩展坞主芯片集固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-278">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="3f764-279">Surface 扩展坞 DisplayPort 固件更新</span><span class="sxs-lookup"><span data-stu-id="3f764-279">Update for Surface Dock DisplayPort firmware</span></span>


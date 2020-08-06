---
title: Microsoft Surface Dock 固件更新-IT 管理员的技术信息
description: 本文介绍了如何使用 Microsoft Surface Dock 固件更新来更新 Surface Dock 固件。 当安装在 Surface 设备上时，它将更新连接到 Surface 设备的任何 Surface Dock。
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
ms.date: 8/05/2020
ms.openlocfilehash: 331d5122c6c64a99dad48ff6e5a90f38ce3d4ed4
ms.sourcegitcommit: 603bcb41dc1b7dd92d3bab1601fa6336480e1218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "10916023"
---
# <span data-ttu-id="05356-104">Microsoft Surface Dock 固件更新： IT 管理员的技术信息</span><span class="sxs-lookup"><span data-stu-id="05356-104">Microsoft Surface Dock Firmware Update: Technical information for IT admins</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05356-105">本文包含适用于 IT 管理员的技术说明。</span><span class="sxs-lookup"><span data-stu-id="05356-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="05356-106">如果您是家庭用户，请参阅如何在 Microsoft 支持网站上[更新 Surface Dock 固件](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   。</span><span class="sxs-lookup"><span data-stu-id="05356-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="05356-107">支持网站上的说明与下面的常规安装步骤相同，但本文提供了有关监视、验证和将更新部署到网络上的多个设备的其他信息。</span><span class="sxs-lookup"><span data-stu-id="05356-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="05356-108">本文介绍了如何使用 Microsoft Surface Dock 固件更新来更新 Surface Dock 固件。</span><span class="sxs-lookup"><span data-stu-id="05356-108">This article explains how to use Microsoft Surface Dock Firmware Update to update Surface Dock firmware.</span></span> <span data-ttu-id="05356-109">当安装在 Surface 设备上时，它将更新连接到 Surface 设备的任何 Surface Dock。</span><span class="sxs-lookup"><span data-stu-id="05356-109">When installed on your Surface device, it will update any Surface Dock attached to your Surface device.</span></span> 

<span data-ttu-id="05356-110">此工具取代了以前的 Microsoft Surface Dock 更新工具，以前可将其作为 Surface 工具的一部分进行下载。</span><span class="sxs-lookup"><span data-stu-id="05356-110">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="05356-111">以前的工具被命名为 Surface_Dock_Updater_vx.xx.xxx.x.msi (其中 x 指示版本号) 且不再可供下载，因此不应使用。</span><span class="sxs-lookup"><span data-stu-id="05356-111">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="05356-112">安装 Surface Dock 固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-112">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="05356-113">本部分介绍如何手动安装固件更新。</span><span class="sxs-lookup"><span data-stu-id="05356-113">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="05356-114">Microsoft 定期发布 Surface Dock 固件更新的新版本。</span><span class="sxs-lookup"><span data-stu-id="05356-114">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="05356-115">MSI 文件不是自我更新。</span><span class="sxs-lookup"><span data-stu-id="05356-115">The MSI file is not self-updating.</span></span> <span data-ttu-id="05356-116">如果你已将 MSI 部署到 Surface 设备，并且新版本的固件已发布，你将需要部署新版本。</span><span class="sxs-lookup"><span data-stu-id="05356-116">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="05356-117">下载并安装[Microsoft Surface Dock 固件更新](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="05356-117">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="05356-118">更新需要运行 Windows 10 版本1803或更高版本的 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="05356-118">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="05356-119">安装 MSI 文件可能会提示你重启 Surface。</span><span class="sxs-lookup"><span data-stu-id="05356-119">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="05356-120">但是，执行更新不需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="05356-120">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="05356-121">将 Surface 设备从 Surface Dock 断开 (使用电源适配器) ，请等待约5秒钟，然后重新连接。</span><span class="sxs-lookup"><span data-stu-id="05356-121">Disconnect your Surface device from the Surface Dock (using the power adapter), wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="05356-122">Surface Dock 固件更新将在后台静默地更新坞站。</span><span class="sxs-lookup"><span data-stu-id="05356-122">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="05356-123">该过程可能需要几分钟才能完成，即使中断，也会继续。</span><span class="sxs-lookup"><span data-stu-id="05356-123">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="05356-124">监视 Surface Dock 固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-124">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="05356-125">本部分是可选的，概述了如何监视固件更新的安装。</span><span class="sxs-lookup"><span data-stu-id="05356-125">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="05356-126">要监视更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="05356-126">To monitor the update:</span></span>

1. <span data-ttu-id="05356-127">打开事件查看器，浏览到**Windows 日志 > 应用程序**，然后在右侧窗格中的 "**操作**" 下单击 "**筛选当前日志**"，在 "**事件源**" 旁边输入 " **SurfaceDockFwUpdate** "，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="05356-127">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="05356-128">在提升的命令提示符处键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="05356-128">Type the following command at an elevated command prompt:</span></span>

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="05356-129">按照本文[下一节](#install-the-surface-dock-firmware-update)中的说明安装更新。</span><span class="sxs-lookup"><span data-stu-id="05356-129">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>
4. <span data-ttu-id="05356-130">事件2007和以下文本表示更新成功：**固件更新已完成。 hr = 0 DriverTelementry EventCode = 2007**。</span><span class="sxs-lookup"><span data-stu-id="05356-130">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 
    - <span data-ttu-id="05356-131">如果更新不成功，则事件 ID 2007 将显示为**错误**事件，而不是**信息**。</span><span class="sxs-lookup"><span data-stu-id="05356-131">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="05356-132">此外，Windows 注册表中报告的版本将不是最新版本。</span><span class="sxs-lookup"><span data-stu-id="05356-132">Additionally, the version reported in the Windows Registry will not be current.</span></span>
5. <span data-ttu-id="05356-133">更新完成后，Windows 注册表中将显示已更新的 DWORD 值，这些值对应于该工具的当前版本。</span><span class="sxs-lookup"><span data-stu-id="05356-133">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="05356-134">有关详细信息，请参阅本文中的[版本参考](#versions-reference)部分。</span><span class="sxs-lookup"><span data-stu-id="05356-134">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="05356-135">例如：</span><span class="sxs-lookup"><span data-stu-id="05356-135">For example:</span></span>
    - <span data-ttu-id="05356-136">Component10CurrentFwVersion 0x04ac3970 (78395760) </span><span class="sxs-lookup"><span data-stu-id="05356-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="05356-137">Component20CurrentFwVersion 0x04915a70 (76634736) </span><span class="sxs-lookup"><span data-stu-id="05356-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="05356-138">如果在事件文本中看到 "无法找到源 SurfaceDockFwUpdate 的事件 ID xxxx 的说明"，则这是预期的，可以忽略。</span><span class="sxs-lookup"><span data-stu-id="05356-138">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="05356-139">另请参阅本文中的以下部分：</span><span class="sxs-lookup"><span data-stu-id="05356-139">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="05356-140">如何验证固件更新已完成</span><span class="sxs-lookup"><span data-stu-id="05356-140">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="05356-141">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="05356-141">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="05356-142">疑难解答提示</span><span class="sxs-lookup"><span data-stu-id="05356-142">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="05356-143">版本参考</span><span class="sxs-lookup"><span data-stu-id="05356-143">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="05356-144">网络部署</span><span class="sxs-lookup"><span data-stu-id="05356-144">Network deployment</span></span>

<span data-ttu-id="05356-145">你可以使用 Windows Installer 命令 ( # A0) 将 Surface Dock 固件更新部署到网络上的多个设备。</span><span class="sxs-lookup"><span data-stu-id="05356-145">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="05356-146">使用 Microsoft 终结点配置管理器或其他部署工具时，请输入以下语法以确保安装静默：</span><span class="sxs-lookup"><span data-stu-id="05356-146">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="05356-147">Msiexec.exe/i \<path to msi file\> /quiet/norestart</span><span class="sxs-lookup"><span data-stu-id="05356-147">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

  <span data-ttu-id="05356-148">例如：</span><span class="sxs-lookup"><span data-stu-id="05356-148">For example:</span></span>
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > <span data-ttu-id="05356-149">默认情况下不创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="05356-149">A log file is not created by default.</span></span> <span data-ttu-id="05356-150">为了创建日志文件，你需要追加 "/l*v [path]"。例如： Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI "</span><span class="sxs-lookup"><span data-stu-id="05356-150">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

  <span data-ttu-id="05356-151">有关详细信息，请参阅[命令行选项](https://docs.microsoft.com/windows/win32/msi/command-line-options)文档。</span><span class="sxs-lookup"><span data-stu-id="05356-151">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05356-152">如果你想要使用任何其他方法更新 Surface Dock，请参阅[更新 Surface dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="05356-152">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="05356-153">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="05356-153">Intune deployment</span></span>

<span data-ttu-id="05356-154">你可以使用 Intune 将 Surface Dock 固件更新分发到你的设备。</span><span class="sxs-lookup"><span data-stu-id="05356-154">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="05356-155">首先，你需要将 MSI 文件转换为 intunewin 格式，如以下文档中所述： [Intune 独立-Win32 应用管理](https://docs.microsoft.com/intune/apps/apps-win32-app-management)。</span><span class="sxs-lookup"><span data-stu-id="05356-155">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="05356-156">使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="05356-156">Use the following command:</span></span>
  - **<span data-ttu-id="05356-157">msiexec/i \<path to msi file\> /quiet/q</span><span class="sxs-lookup"><span data-stu-id="05356-157">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="05356-158">如何验证固件更新的完成</span><span class="sxs-lookup"><span data-stu-id="05356-158">How to verify completion of the firmware update</span></span>

<span data-ttu-id="05356-159">Surface dock 固件包含两个组件：</span><span class="sxs-lookup"><span data-stu-id="05356-159">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="05356-160">**Component10：** (MCU) 固件的微控制器单元</span><span class="sxs-lookup"><span data-stu-id="05356-160">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="05356-161">**Component20：** 显示端口 (DP) 固件。</span><span class="sxs-lookup"><span data-stu-id="05356-161">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="05356-162">成功完成 Surface Dock 固件更新会导致这些固件组件的新注册表项值。</span><span class="sxs-lookup"><span data-stu-id="05356-162">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="05356-163">要验证更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="05356-163">To verify updates:</span></span>**

1. <span data-ttu-id="05356-164">打开注册表编辑器，然后导航到以下注册表路径：</span><span class="sxs-lookup"><span data-stu-id="05356-164">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="05356-165">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="05356-165">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="05356-166">查找注册表项： **Component10CurrentFwVersion 和 Component20CurrentFwVersion**，它指的是当前在设备上的固件。</span><span class="sxs-lookup"><span data-stu-id="05356-166">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Surface Dock 固件更新安装过程](images/regeditDock.png)

3. <span data-ttu-id="05356-168">验证新的注册表项值是否与本文档末尾的版本参考中列出的更新的注册表项值相匹配。</span><span class="sxs-lookup"><span data-stu-id="05356-168">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="05356-169">如果值匹配，则固件已成功更新。</span><span class="sxs-lookup"><span data-stu-id="05356-169">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="05356-170">如果无法验证，请查看下一节中的事件日志记录和疑难解答提示。</span><span class="sxs-lookup"><span data-stu-id="05356-170">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="05356-171">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="05356-171">Event logging</span></span>

**<span data-ttu-id="05356-172">表 1. </span><span class="sxs-lookup"><span data-stu-id="05356-172">Table 1.</span></span> <span data-ttu-id="05356-173">Surface Dock 固件更新的日志文件</span><span class="sxs-lookup"><span data-stu-id="05356-173">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="05356-174">Log</span><span class="sxs-lookup"><span data-stu-id="05356-174">Log</span></span>                              | <span data-ttu-id="05356-175">位置</span><span class="sxs-lookup"><span data-stu-id="05356-175">Location</span></span>                               | <span data-ttu-id="05356-176">注释</span><span class="sxs-lookup"><span data-stu-id="05356-176">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="05356-177">Surface Dock 固件更新日志</span><span class="sxs-lookup"><span data-stu-id="05356-177">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="05356-178">需要指定路径 (请参阅注意) </span><span class="sxs-lookup"><span data-stu-id="05356-178">Path needs to be specified (see note)</span></span> | <span data-ttu-id="05356-179">此工具的早期版本将事件写入应用程序和服务 Logs\Microsoft Surface Dock 更新。</span><span class="sxs-lookup"><span data-stu-id="05356-179">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="05356-180">Windows 设备安装日志</span><span class="sxs-lookup"><span data-stu-id="05356-180">Windows Device Install log</span></span>       | <span data-ttu-id="05356-181">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="05356-181">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="05356-182">有关使用设备安装日志的详细信息，请参阅[SetupAPI 日志记录](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-)文档。</span><span class="sxs-lookup"><span data-stu-id="05356-182">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="05356-183">表 2. </span><span class="sxs-lookup"><span data-stu-id="05356-183">Table 2.</span></span> <span data-ttu-id="05356-184">Surface Dock 固件更新的事件日志 Id</span><span class="sxs-lookup"><span data-stu-id="05356-184">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="05356-185">在应用程序事件日志中记录事件。</span><span class="sxs-lookup"><span data-stu-id="05356-185">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="05356-186">注意：此工具的早期版本向应用程序和服务 Logs\Microsoft Surface Dock 更新程序写入了事件。</span><span class="sxs-lookup"><span data-stu-id="05356-186">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="05356-187">事件 ID</span><span class="sxs-lookup"><span data-stu-id="05356-187">Event ID</span></span> | <span data-ttu-id="05356-188">事件类型</span><span class="sxs-lookup"><span data-stu-id="05356-188">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="05356-189">2001</span><span class="sxs-lookup"><span data-stu-id="05356-189">2001</span></span>     | <span data-ttu-id="05356-190">已开始插接固件更新。</span><span class="sxs-lookup"><span data-stu-id="05356-190">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="05356-191">2002</span><span class="sxs-lookup"><span data-stu-id="05356-191">2002</span></span>     | <span data-ttu-id="05356-192">已跳过插接固件更新，因为插接已被认为是最新的。</span><span class="sxs-lookup"><span data-stu-id="05356-192">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="05356-193">2003</span><span class="sxs-lookup"><span data-stu-id="05356-193">2003</span></span>     | <span data-ttu-id="05356-194">插接固件更新无法获取固件版本。</span><span class="sxs-lookup"><span data-stu-id="05356-194">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="05356-195">2004</span><span class="sxs-lookup"><span data-stu-id="05356-195">2004</span></span>     | <span data-ttu-id="05356-196">查询固件版本。</span><span class="sxs-lookup"><span data-stu-id="05356-196">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="05356-197">2005</span><span class="sxs-lookup"><span data-stu-id="05356-197">2005</span></span>     | <span data-ttu-id="05356-198">Dock 固件无法开始更新。</span><span class="sxs-lookup"><span data-stu-id="05356-198">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="05356-199">2006</span><span class="sxs-lookup"><span data-stu-id="05356-199">2006</span></span>     | <span data-ttu-id="05356-200">无法发送优惠/负载对。</span><span class="sxs-lookup"><span data-stu-id="05356-200">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="05356-201">2007</span><span class="sxs-lookup"><span data-stu-id="05356-201">2007</span></span>     | <span data-ttu-id="05356-202">固件更新已完成。</span><span class="sxs-lookup"><span data-stu-id="05356-202">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="05356-203">2008</span><span class="sxs-lookup"><span data-stu-id="05356-203">2008</span></span>     | <span data-ttu-id="05356-204">开始停靠遥测。</span><span class="sxs-lookup"><span data-stu-id="05356-204">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="05356-205">2011</span><span class="sxs-lookup"><span data-stu-id="05356-205">2011</span></span>     | <span data-ttu-id="05356-206">结束停靠遥测。</span><span class="sxs-lookup"><span data-stu-id="05356-206">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="05356-207">疑难解答提示</span><span class="sxs-lookup"><span data-stu-id="05356-207">Troubleshooting tips</span></span>

- <span data-ttu-id="05356-208">完全断开 Surface dock 与交流电源的连接，以重置 Surface Dock。</span><span class="sxs-lookup"><span data-stu-id="05356-208">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="05356-209">断开除 Surface Dock 之外的所有外围设备。</span><span class="sxs-lookup"><span data-stu-id="05356-209">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="05356-210">卸载任何当前 Surface Dock 固件更新，然后安装最新版本。</span><span class="sxs-lookup"><span data-stu-id="05356-210">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="05356-211">确保 Surface Dock 已断开连接，然后通过 Dock 的以太网端口中的 LED 使更新时间有足够的时间完成更新。</span><span class="sxs-lookup"><span data-stu-id="05356-211">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="05356-212">等待 LED 停止闪烁，然后再从 power 中拔出 Surface Dock。</span><span class="sxs-lookup"><span data-stu-id="05356-212">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="05356-213">将 Surface Dock 连接到其他设备，查看它是否能够更新坞站。</span><span class="sxs-lookup"><span data-stu-id="05356-213">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="05356-214">版本参考</span><span class="sxs-lookup"><span data-stu-id="05356-214">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="05356-215">安装文件以以下命名格式发布： **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex： Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) 并默认安装到 C:\Program Files\SurfaceUpdate。</span><span class="sxs-lookup"><span data-stu-id="05356-215">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="05356-216">版本1.53.139。0</span><span class="sxs-lookup"><span data-stu-id="05356-216">Version 1.53.139.0</span></span>
*<span data-ttu-id="05356-217">发布日期：2020年8月4日</span><span class="sxs-lookup"><span data-stu-id="05356-217">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="05356-218">此版本的 Surface Dock 固件更新包括以下各项的错误修复和支持：</span><span class="sxs-lookup"><span data-stu-id="05356-218">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="05356-219">使用 Surface Pro X 更新 Surface Dock 1。</span><span class="sxs-lookup"><span data-stu-id="05356-219">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="05356-220">如果您运行的是 Surface Pro X，请下载。ARM64 内部版本。</span><span class="sxs-lookup"><span data-stu-id="05356-220">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="05356-221">对于所有其他设备，请使用 AMD64 内部版本。</span><span class="sxs-lookup"><span data-stu-id="05356-221">For all other devices, use the AMD64 build.</span></span> 
 


### <span data-ttu-id="05356-222">版本1.42.139</span><span class="sxs-lookup"><span data-stu-id="05356-222">Version 1.42.139</span></span> 
*<span data-ttu-id="05356-223">发布日期： 18 2019 年9月</span><span class="sxs-lookup"><span data-stu-id="05356-223">Release Date: September 18 2019</span></span>*

<span data-ttu-id="05356-224">此版本（包含在 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI 中）会在后台更新固件。</span><span class="sxs-lookup"><span data-stu-id="05356-224">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 
**<span data-ttu-id="05356-225">已更新注册表项值：</span><span class="sxs-lookup"><span data-stu-id="05356-225">Updated registry key values:</span></span>**<br>

- <span data-ttu-id="05356-226">Component10CurrentFwVersion 更新为**4ac3970**。</span><span class="sxs-lookup"><span data-stu-id="05356-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="05356-227">Component20CurrentFwVersion 更新为**4a1d570**。</span><span class="sxs-lookup"><span data-stu-id="05356-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="05356-228">它添加了对 Surface Pro 7 和 Surface 笔记本电脑3的支持。</span><span class="sxs-lookup"><span data-stu-id="05356-228">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="05356-229">旧版本</span><span class="sxs-lookup"><span data-stu-id="05356-229">Legacy versions</span></span>

### <span data-ttu-id="05356-230">版本2.23.139。0</span><span class="sxs-lookup"><span data-stu-id="05356-230">Version 2.23.139.0</span></span>
*<span data-ttu-id="05356-231">发布日期：2018年10月10日</span><span class="sxs-lookup"><span data-stu-id="05356-231">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="05356-232">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="05356-232">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="05356-233">添加对 Surface Pro 6 的支持</span><span class="sxs-lookup"><span data-stu-id="05356-233">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="05356-234">添加对 Surface 笔记本电脑的支持2</span><span class="sxs-lookup"><span data-stu-id="05356-234">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="05356-235">版本2.22.139。0</span><span class="sxs-lookup"><span data-stu-id="05356-235">Version 2.22.139.0</span></span>
*<span data-ttu-id="05356-236">发布日期：2018年7月26日</span><span class="sxs-lookup"><span data-stu-id="05356-236">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="05356-237">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="05356-237">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="05356-238">提高更新可靠性</span><span class="sxs-lookup"><span data-stu-id="05356-238">Increase update reliability</span></span>
- <span data-ttu-id="05356-239">添加对 Surface Go 的支持</span><span class="sxs-lookup"><span data-stu-id="05356-239">Add support for Surface Go</span></span>

### <span data-ttu-id="05356-240">版本 2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="05356-240">Version 2.12.136.0</span></span>
*<span data-ttu-id="05356-241">发布日期：2018 年 1 月 29 日</span><span class="sxs-lookup"><span data-stu-id="05356-241">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="05356-242">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="05356-242">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="05356-243">Surface 扩展坞主芯片集固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-243">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="05356-244">Surface 扩展坞 DisplayPort 固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-244">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="05356-245">改进了使用 Surface Book 或 Surface Book 2 时外部显示器的显示稳定性。</span><span class="sxs-lookup"><span data-stu-id="05356-245">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="05356-246">此外，在 Surface Book 设备上安装的此版本 Surface Dock Updater 包括：</span><span class="sxs-lookup"><span data-stu-id="05356-246">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="05356-247">Surface Book 底座固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-247">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="05356-248">增加了 Surface 扩展坞固件更新支持，针对 Surface Book 设备做出了改进</span><span class="sxs-lookup"><span data-stu-id="05356-248">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="05356-249">版本 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="05356-249">Version 2.9.136.0</span></span>
*<span data-ttu-id="05356-250">发布日期：2017 年 11 月 3 日</span><span class="sxs-lookup"><span data-stu-id="05356-250">Release date: November 3, 2017</span></span>*

<span data-ttu-id="05356-251">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="05356-251">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="05356-252">Surface 扩展坞 DisplayPort 固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-252">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="05356-253">通过无源显示端口适配器解决音频问题</span><span class="sxs-lookup"><span data-stu-id="05356-253">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="05356-254">版本 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="05356-254">Version 2.1.15.0</span></span>
*<span data-ttu-id="05356-255">发布日期：2017 年 6 月 19 日</span><span class="sxs-lookup"><span data-stu-id="05356-255">Release date: June 19, 2017</span></span>*

<span data-ttu-id="05356-256">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="05356-256">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="05356-257">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="05356-257">Surface Laptop</span></span>
* <span data-ttu-id="05356-258">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="05356-258">Surface Pro</span></span>

### <span data-ttu-id="05356-259">版本 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="05356-259">Version 2.1.6.0</span></span>
*<span data-ttu-id="05356-260">发布日期：2017 年 4 月 7 日</span><span class="sxs-lookup"><span data-stu-id="05356-260">Release date: April 7, 2017</span></span>*

<span data-ttu-id="05356-261">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="05356-261">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="05356-262">Surface 扩展坞 DisplayPort 固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-262">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="05356-263">要求使用 Windows 10</span><span class="sxs-lookup"><span data-stu-id="05356-263">Requires Windows 10</span></span>

### <span data-ttu-id="05356-264">版本 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="05356-264">Version 2.0.22.0</span></span>
*<span data-ttu-id="05356-265">发布日期：2016 年 10 月 21 日</span><span class="sxs-lookup"><span data-stu-id="05356-265">Release date: October 21, 2016</span></span>*

<span data-ttu-id="05356-266">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="05356-266">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="05356-267">Surface 扩展坞 USB 固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-267">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="05356-268">提升了以太网、音频和 USB 端口的可靠性</span><span class="sxs-lookup"><span data-stu-id="05356-268">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="05356-269">版本 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="05356-269">Version 1.0.8.0</span></span>
*<span data-ttu-id="05356-270">发布日期：2016 年 4 月 26 日</span><span class="sxs-lookup"><span data-stu-id="05356-270">Release date: April 26, 2016</span></span>*

<span data-ttu-id="05356-271">此版本的 Surface Dock Updater 添加了以下支持：</span><span class="sxs-lookup"><span data-stu-id="05356-271">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="05356-272">Surface 扩展坞主芯片集固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-272">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="05356-273">Surface 扩展坞 DisplayPort 固件更新</span><span class="sxs-lookup"><span data-stu-id="05356-273">Update for Surface Dock DisplayPort firmware</span></span>


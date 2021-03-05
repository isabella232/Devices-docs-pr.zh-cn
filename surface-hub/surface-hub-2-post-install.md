---
title: 配置 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文包含一些建议，以确保在使用个性化大屏幕触摸和笔计算机时获得最佳体验。
keywords: Surface Hub， Windows 10， 桌面， 安装， 配置
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393594"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a><span data-ttu-id="e19d0-104">配置 Surface Hub 2 上的 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="e19d0-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="e19d0-105">完成迁移到 Windows 10 专业版或企业版安装过程后，可以执行以下步骤在 Surface Hub 2 上配置应用和设置。</span><span class="sxs-lookup"><span data-stu-id="e19d0-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="e19d0-106">建议执行这些步骤以确保使用此个性化大屏幕触摸和笔计算机时获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="e19d0-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="e19d0-107">执行这些步骤时，你可能会发现使用有线或无线键盘和鼠标非常有用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <a name="configure-system-settings"></a><span data-ttu-id="e19d0-108">配置系统设置</span><span class="sxs-lookup"><span data-stu-id="e19d0-108">Configure system settings</span></span>

1. <span data-ttu-id="e19d0-109">使用在设备上具有本地管理员权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e19d0-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="e19d0-110">在加入 Azure AD 的设备上，执行 Azure AD 加入的用户将自动添加到本地管理员组。</span><span class="sxs-lookup"><span data-stu-id="e19d0-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="e19d0-111">Azure AD 全局管理员和 Azure AD 设备管理员 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 也是本地管理员 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="e19d0-112">您可以在命令 **提示符下** 键入 net localgroup 管理员，以列出具有本地管理员权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="e19d0-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="e19d0-113">使用友好名称重命名设备，例如 **：username-SHub-Desktop**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="e19d0-114">选择 **"**  >  **开始**  >  **设置**  >  **帐户同步设置"并**关闭 **"同步设置**"。</span><span class="sxs-lookup"><span data-stu-id="e19d0-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="e19d0-115">此处使用的设置旨在实现最佳的大屏幕触摸体验，因此你可能不希望同步其他设备。</span><span class="sxs-lookup"><span data-stu-id="e19d0-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="e19d0-116">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="e19d0-116">Restart the device.</span></span>

## <a name="enable-the-touch-keyboard-and-touchpad"></a><span data-ttu-id="e19d0-117">启用触摸键盘和触摸板</span><span class="sxs-lookup"><span data-stu-id="e19d0-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="e19d0-118">选择 **"** 开始  >  \*\*\*\*  >  **设置**设备  >  **键入"，** 当\*\*\*\* 未在平板电脑模式下且没有连接键盘时，打开"显示触摸键盘"。</span><span class="sxs-lookup"><span data-stu-id="e19d0-118">Select **Start** > **Settings** > **Devices** > **Typing** and turn **Show the touch keyboard when not in tablet mode and there's no keyboard attached** on.</span></span>

2. <span data-ttu-id="e19d0-119">点击并按住或右键单击任务栏，然后选择" **显示触摸键盘按钮** "和" **显示触摸板"按钮**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="e19d0-120">触摸键盘有助于直接用户输入，虚拟触摸板有助于精确选择、悬停屏幕提示，或者作为点击并按住进行右键单击的替代方法。</span><span class="sxs-lookup"><span data-stu-id="e19d0-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="e19d0-121">请参阅以下示例。</span><span class="sxs-lookup"><span data-stu-id="e19d0-121">See the following example.</span></span>

      ![触摸设置](images/touch.png)

3. <span data-ttu-id="e19d0-123">将触摸键盘配置为 QWERTY 和浮动。</span><span class="sxs-lookup"><span data-stu-id="e19d0-123">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="e19d0-124">选择 **任务栏** 上的键盘图标以显示触摸键盘。</span><span class="sxs-lookup"><span data-stu-id="e19d0-124">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    1. <span data-ttu-id="e19d0-125">在触摸键盘上，选择左上角的键盘图标以打开键盘设置。</span><span class="sxs-lookup"><span data-stu-id="e19d0-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    1. <span data-ttu-id="e19d0-126">选择首行上的最后一个键盘类型以启用 QWERTY，选择第二行的最后一个选项以启用浮动，这在此大屏幕上非常有用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="e19d0-127">请参阅以下示例。</span><span class="sxs-lookup"><span data-stu-id="e19d0-127">See the following examples.</span></span>

       ![键盘设置](images/kbd.png)
 
4. <span data-ttu-id="e19d0-129">配置软键盘设置。</span><span class="sxs-lookup"><span data-stu-id="e19d0-129">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="e19d0-130">选择**触摸**键盘上的"设置"图标或搜索并打开 **"键入设置"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-130">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![软键盘设置](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="e19d0-132">启用拼写、键入和触摸键盘下的所有选项。</span><span class="sxs-lookup"><span data-stu-id="e19d0-132">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="e19d0-133">以下示例显示跟踪板，它可用于导航和选择选项。</span><span class="sxs-lookup"><span data-stu-id="e19d0-133">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="e19d0-134">屏幕键盘用于搜索 Microsoft Store：</span><span class="sxs-lookup"><span data-stu-id="e19d0-134">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![使用跟踪板](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a><span data-ttu-id="e19d0-136">配置Bluetooth键盘和鼠标 (可选) </span><span class="sxs-lookup"><span data-stu-id="e19d0-136">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="e19d0-137">如果你将设备用作主 Windows 设备，或者你经常使用它进行键入或精确工作，请连接键盘和鼠标。</span><span class="sxs-lookup"><span data-stu-id="e19d0-137">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="e19d0-138">如果你的 Surface Hub 设备靠近电脑，可以使用不带边框的鼠标在 Surface Hub 和电脑之间无缝 <a href="https://aka.ms/mm" target="_blank"> </a> 移动。</span><span class="sxs-lookup"><span data-stu-id="e19d0-138">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="e19d0-139">有关详细信息，请参阅 Microsoft 从 Garage <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> 下载：没有边框的鼠标。</span><span class="sxs-lookup"><span data-stu-id="e19d0-139">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <a name="example-of-taskbar-layout"></a><span data-ttu-id="e19d0-140">任务栏布局示例</span><span class="sxs-lookup"><span data-stu-id="e19d0-140">Example of Taskbar layout</span></span>

<span data-ttu-id="e19d0-141">完成以下步骤以设置/配置适用于 Windows 10 专业版或企业版 Surface Hub 2 后，我们建议你利用将最常用的应用程序固定到任务栏，以便快速一键启动每个应用程序。</span><span class="sxs-lookup"><span data-stu-id="e19d0-141">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="e19d0-142">下面是任务栏外观的示例：</span><span class="sxs-lookup"><span data-stu-id="e19d0-142">Below is an example of what your taskbar could look like:</span></span>

 ![任务栏布局](images/taskblyt.png)
### <a name="update-installed-apps"></a><span data-ttu-id="e19d0-144">更新已安装的应用</span><span class="sxs-lookup"><span data-stu-id="e19d0-144">Update installed apps</span></span>

<span data-ttu-id="e19d0-145">更新所有已安装的应用商店应用：</span><span class="sxs-lookup"><span data-stu-id="e19d0-145">To update all installed Store apps:</span></span>

1. <span data-ttu-id="e19d0-146">打开 Microsoft Store 应用 **，然后选择右上角** 的"查看更多省略号"。</span><span class="sxs-lookup"><span data-stu-id="e19d0-146">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="e19d0-147">选择 **"下载和更新"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-147">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="e19d0-148">选择 **"获取更新"**</span><span class="sxs-lookup"><span data-stu-id="e19d0-148">Select **Get updates**</span></span>

### <a name="scan-for-and-install-all-windows-updates"></a><span data-ttu-id="e19d0-149">扫描并安装所有 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="e19d0-149">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="e19d0-150">迁移到 Windows 10 专业版或 Windows 10 企业版后，可能有可供你安装的维护和功能更新。</span><span class="sxs-lookup"><span data-stu-id="e19d0-150">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="e19d0-151">转到 **"设置**  >  **更新&安全**>，然后选择 **"检查更新"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-151">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="e19d0-152">如果存在任何更新，请安装它们，重新启动，然后重复此过程，直到看到以下通知：</span><span class="sxs-lookup"><span data-stu-id="e19d0-152">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Windows 更新"你已更新"通知](images/wustatus.png)


## <a name="onedrive-for-business"></a><span data-ttu-id="e19d0-154">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e19d0-154">OneDrive for Business</span></span>

<span data-ttu-id="e19d0-155">使用 OneDrive for Business 在所有工作设备之间轻松共享工具、日志 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> 和其他文件。</span><span class="sxs-lookup"><span data-stu-id="e19d0-155">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="e19d0-156">OneDrive 使你能够在笔记本电脑、Surface Hub 桌面和 Intune 托管的移动设备之间共享工作文件。</span><span class="sxs-lookup"><span data-stu-id="e19d0-156">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="e19d0-157">可以在任何设备上编辑文件，并且所有网络连接的设备都将随更改一起更新。</span><span class="sxs-lookup"><span data-stu-id="e19d0-157">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="e19d0-158">考虑 Surface Hub SSD (128GB) 的大小，如果在 Surface Hub 桌面版设备上配置 OneDrive，请确保默认配置是使文件保持联机并下载使用的文件。</span><span class="sxs-lookup"><span data-stu-id="e19d0-158">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="e19d0-159">若要将 OneDrive 配置为仅根据需要下载文件，请\*\*\*\* 设置"按需文件"设置以节省空间，并下载使用**时的文件**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-159">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="e19d0-160">有关详细信息，请参阅 Windows 中的查询和 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> 设置文件按需状态 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-160">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![OneDrive 设置](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="e19d0-162">还可以重复这些步骤来配置个人 OneDrive，但请务必节省驱动器空间，并仅根据需要下载文件。</span><span class="sxs-lookup"><span data-stu-id="e19d0-162">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <a name="sharepoint-and-teams"></a><span data-ttu-id="e19d0-163">SharePoint 和 Teams</span><span class="sxs-lookup"><span data-stu-id="e19d0-163">SharePoint and Teams</span></span>

<span data-ttu-id="e19d0-164">SharePoint 和 Teams 频道文件还可使用 OneDrive 同步引擎本地同步到桌面设备，如笔记本电脑和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="e19d0-164">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="e19d0-165">若要使用 OneDrive 同步应用将内部公司文件同步到本地驱动器：</span><span class="sxs-lookup"><span data-stu-id="e19d0-165">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="e19d0-166">转到 SharePoint 网站，并导航到顶级文档目录，了解您在本地设备中查看或编辑的文件。</span><span class="sxs-lookup"><span data-stu-id="e19d0-166">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="e19d0-167">在 SharePoint 功能 **区** 顶部的"同步"按钮上选择。</span><span class="sxs-lookup"><span data-stu-id="e19d0-167">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="e19d0-168">在弹出窗口**中选择**"打开"**此网站正在尝试打开 Microsoft OneDrive。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-168">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="e19d0-169">通过选择任务栏右下角的 OneDrive 图标，验证 SharePoint 文件是否正在同步到本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="e19d0-169">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="e19d0-170">验证配置是否设置为保持文件联机，并仅在使用文件时下载这些文件：</span><span class="sxs-lookup"><span data-stu-id="e19d0-170">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="e19d0-171">打开文件资源管理器。</span><span class="sxs-lookup"><span data-stu-id="e19d0-171">Open file explorer.</span></span>
    
    2. <span data-ttu-id="e19d0-172">导航到 SharePoint 名称并右键单击您的 SharePoint 名称;例如 \*\*，Contoso \ \<SharePoint Document Folder Name\> \*\*。</span><span class="sxs-lookup"><span data-stu-id="e19d0-172">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="e19d0-173">选择 **"释放空间"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-173">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="e19d0-174">"状态"列将显示文件和文件夹的状态。</span><span class="sxs-lookup"><span data-stu-id="e19d0-174">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="e19d0-175">有关详细信息，请参阅将 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> SharePoint 文件与 OneDrive 同步客户端同步 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-175">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="e19d0-176">Teams 频道文件存储在 SharePoint 网站中，具有所有相同的 SharePoint 文档功能，包括版本历史记录和同步到本地桌面设备。</span><span class="sxs-lookup"><span data-stu-id="e19d0-176">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="e19d0-177">同步 Teams 频道文件：</span><span class="sxs-lookup"><span data-stu-id="e19d0-177">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="e19d0-178">导航到感兴趣的 Teams 频道， **然后选择顶部的"** 文件"选项卡。</span><span class="sxs-lookup"><span data-stu-id="e19d0-178">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="e19d0-179">然后选择"**同步"。** 文件将开始同步，并且将在桌面\**\ Contoso \<name of the Teams Channel\> \**文件资源管理器中可见。</span><span class="sxs-lookup"><span data-stu-id="e19d0-179">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="e19d0-180">使用用于同步 SharePoint 网站的过程将文件保留到云中，并且仅在使用这些文件时下载这些文件，方法为点击并按住或右键单击 Teams 频道名称上的文件资源管理器，然后选择"释放空间 **"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-180">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <a name="surface-hub-pen-settings"></a><span data-ttu-id="e19d0-181">Surface Hub 笔设置</span><span class="sxs-lookup"><span data-stu-id="e19d0-181">Surface Hub pen settings</span></span>

**<span data-ttu-id="e19d0-182">将 Bluetooth Surface Hub 触控笔配对</span><span class="sxs-lookup"><span data-stu-id="e19d0-182">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="e19d0-183">配对笔，使笔固件保持最新，设置笔快捷方式，并获取"Bluetooth设置"页面或 Surface 应用中的电池充电信息：</span><span class="sxs-lookup"><span data-stu-id="e19d0-183">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="e19d0-184">选择 **"**  >  **开始设置**  >  **设备"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-184">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="e19d0-185">选择 **"添加Bluetooth或其他设备**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-185">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="e19d0-186">选择 **Bluetooth**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-186">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="e19d0-187">删除笔尾按钮并摇动以断开电池连接。</span><span class="sxs-lookup"><span data-stu-id="e19d0-187">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="e19d0-188">将顶帽重新打开并按住该顶帽，直到配对的 LED 闪烁。</span><span class="sxs-lookup"><span data-stu-id="e19d0-188">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="e19d0-189">在 Surface Hub Bluetooth设置上，选择 **Surface Hub 2 触控笔**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-189">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="e19d0-190">完成配对操作。</span><span class="sxs-lookup"><span data-stu-id="e19d0-190">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="e19d0-191">如果配对失败，可以再次尝试配对笔。</span><span class="sxs-lookup"><span data-stu-id="e19d0-191">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="e19d0-192">如果不起作用，可以通过验证笔在白板应用程序中是否正常工作来测试电池是否充电。</span><span class="sxs-lookup"><span data-stu-id="e19d0-192">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="e19d0-193">如果没有，请更换电池，然后再次尝试配对笔。</span><span class="sxs-lookup"><span data-stu-id="e19d0-193">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="e19d0-194">如有必要，请重新启动设备，然后重试。</span><span class="sxs-lookup"><span data-stu-id="e19d0-194">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="e19d0-195">**设置笔快捷方式** Surface Hub 笔有一个快捷按钮，有时称为"尾部单击"。</span><span class="sxs-lookup"><span data-stu-id="e19d0-195">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="e19d0-196">配置快捷方式需要你先配对笔，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="e19d0-196">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="e19d0-197">搜索笔并选择"笔 **& Windows Ink 设置**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-197">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="e19d0-198">在页面底部附近，选择打开对话框的笔快捷方式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e19d0-198">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![笔快捷方式](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a><span data-ttu-id="e19d0-200">相机配置</span><span class="sxs-lookup"><span data-stu-id="e19d0-200">Camera configuration</span></span>

<span data-ttu-id="e19d0-201">你可以将相机安装在设备顶部或两侧。</span><span class="sxs-lookup"><span data-stu-id="e19d0-201">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="e19d0-202">如果你将 Hub 与桌面台而不是购物车一同使用，或者靠近中心，则将相机装载到一个位置以优化相机角度。</span><span class="sxs-lookup"><span data-stu-id="e19d0-202">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="e19d0-203">相机不自动旋转，因此你需要有一个 2mm 的十六进制密钥来手动旋转相机。</span><span class="sxs-lookup"><span data-stu-id="e19d0-203">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="e19d0-204">若要详细了解如何手动旁装载相机并旋转相机，请参阅 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S 相机镜头方向 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-204">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <a name="windows-hello-configuration"></a><span data-ttu-id="e19d0-205">Windows Hello 配置</span><span class="sxs-lookup"><span data-stu-id="e19d0-205">Windows Hello configuration</span></span>

<span data-ttu-id="e19d0-206">运行 Windows 10 企业版 Surface Hub 2S 允许整套 Win32 桌面应用程序以及生物识别 Windows Hello 选项。</span><span class="sxs-lookup"><span data-stu-id="e19d0-206">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="e19d0-207">Surface Hub 2 指纹读取器附件可以插入设备上的任何 USB-C 端口。</span><span class="sxs-lookup"><span data-stu-id="e19d0-207">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="e19d0-208">若要订购 Surface Hub 2 指纹读取器或查看技术规范，请参阅 (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a> .</span><span class="sxs-lookup"><span data-stu-id="e19d0-208">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="e19d0-209">插入指纹读取器后，选择"**开始**  >  **设置**帐户  >  \*\*\*\*  >  **登录选项**  >  **"Windows Hello 指纹**以注册指纹。</span><span class="sxs-lookup"><span data-stu-id="e19d0-209">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="e19d0-210">使用 Windows Hello 认证的设备进行人脸识别。</span><span class="sxs-lookup"><span data-stu-id="e19d0-210">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="e19d0-211">Surface Hub 2S 相机不支持 Windows Hello 人脸识别。</span><span class="sxs-lookup"><span data-stu-id="e19d0-211">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a><span data-ttu-id="e19d0-212">在任务栏上启用锁屏界面快捷方式图标</span><span class="sxs-lookup"><span data-stu-id="e19d0-212">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="e19d0-213">若要将图标添加到启用一键式屏幕锁定的任务栏，类似于 Windows-L 键盘快捷方式：</span><span class="sxs-lookup"><span data-stu-id="e19d0-213">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="e19d0-214">点击并按住或右键单击桌面，选择 **"新建**  >  **快捷方式**  >  **浏览**  >  **桌面**  >  **确定**  >  **下一步"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-214">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="e19d0-215">提供快捷方式的名称，如 **"锁定我的电脑**"，然后选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-215">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="e19d0-216">右键单击或点击并按住桌面上新建的快捷方式，然后选择"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-216">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="e19d0-217">在 **"快捷方式**"选项卡上，在"目标\*\*\*\*"字段中输入以下内容 **：Rundll32.exe User32.dll、LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="e19d0-217">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="e19d0-218">选择 **"更改** 图标"按钮并浏览 \*\*C:\Windows\System32\imageres.dll并选择要使用 \*\* 图标。</span><span class="sxs-lookup"><span data-stu-id="e19d0-218">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="e19d0-219">请参见以下示例：</span><span class="sxs-lookup"><span data-stu-id="e19d0-219">See the following example:</span></span>

    ![选择图标](images/lock.png)
    
1.  <span data-ttu-id="e19d0-221">选择 **"确定** "保存快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e19d0-221">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="e19d0-222">右键单击或点击并按住快捷方式，然后选择 **"固定到任务栏"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-222">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="e19d0-223">将锁定快捷方式固定到任务栏后，可以从桌面中删除它。</span><span class="sxs-lookup"><span data-stu-id="e19d0-223">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <a name="applications"></a><span data-ttu-id="e19d0-224">应用程序</span><span class="sxs-lookup"><span data-stu-id="e19d0-224">Applications</span></span>


### <a name="microsoft-whiteboard"></a><span data-ttu-id="e19d0-225">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="e19d0-225">Microsoft Whiteboard</span></span>

<span data-ttu-id="e19d0-226">若要安装 Microsoft Whiteboard：</span><span class="sxs-lookup"><span data-stu-id="e19d0-226">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="e19d0-227">选择任务栏右下角的 **Windows Ink 工作区** 图标并下载 **白板**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-227">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![墨迹工作区](images/ink.png) 

<span data-ttu-id="e19d0-229">或者，你可以从 Microsoft Store 安装白板：</span><span class="sxs-lookup"><span data-stu-id="e19d0-229">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="e19d0-230">打开 Microsoft Store 应用并搜索 **白板**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-230">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="e19d0-231">选择 **"否"，** 以感谢登录并跨设备使用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-231">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="e19d0-232">将白板固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="e19d0-232">Pin Whiteboard to the taskbar.</span></span>

### <a name="surface-app"></a><span data-ttu-id="e19d0-233">Surface 应用</span><span class="sxs-lookup"><span data-stu-id="e19d0-233">Surface app</span></span>

1. <span data-ttu-id="e19d0-234">在 Microsoft Store 中，搜索 **Surface**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-234">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="e19d0-235">将**筛选器上的"可用**"设置为 **"所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-235">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="e19d0-236">安装 **Surface** 应用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-236">Install the **Surface** app.</span></span> <span data-ttu-id="e19d0-237">这应该是列出的第一个应用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-237">This should be the first app listed.</span></span> <span data-ttu-id="e19d0-238">你可能需要将 MSA 与应用商店关联才能安装应用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-238">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="e19d0-239">将 **Surface** 应用固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="e19d0-239">Pin the **Surface** app to taskbar.</span></span>

### <a name="snip--sketch"></a><span data-ttu-id="e19d0-240">截图和草图</span><span class="sxs-lookup"><span data-stu-id="e19d0-240">Snip & Sketch</span></span>

1. <span data-ttu-id="e19d0-241">打开 **"Snip &草图** "应用，将其固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="e19d0-241">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="e19d0-242">选择右上角的省略号，然后选择"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-242">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="e19d0-243">在 **"设置\*\*\*\*"中**，打开"自动复制到剪\*\*\*\* 贴板"、"保存剪贴"和"多个**窗口 (** 可选) 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-243">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <a name="microsoft-office"></a><span data-ttu-id="e19d0-244">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="e19d0-244">Microsoft Office</span></span>

1. <span data-ttu-id="e19d0-245">打开 <a href="https://portal.office.com/account#installs" target="_blank"> Office 门户 </a> 并安装所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e19d0-245">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="e19d0-246">将所需的 Office 应用程序固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="e19d0-246">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="e19d0-247">如果安装了 Outlook，请确保将 Outlook OST 设置为仅保存最近两周缓存。</span><span class="sxs-lookup"><span data-stu-id="e19d0-247">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="e19d0-248">这将大大减少磁盘使用率和设置时间。</span><span class="sxs-lookup"><span data-stu-id="e19d0-248">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="e19d0-249">选择\*\*\*\*  >  **"文件帐户设置**"，然后选择您的帐户。</span><span class="sxs-lookup"><span data-stu-id="e19d0-249">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="e19d0-250">选择 **"更改** "，将" **使用缓存 Exchange 模式"** 的滑块设置为 14 天。</span><span class="sxs-lookup"><span data-stu-id="e19d0-250">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="e19d0-251">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e19d0-251">Microsoft Teams</span></span>

1. <span data-ttu-id="e19d0-252">下载并安装 <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft </a> Teams。</span><span class="sxs-lookup"><span data-stu-id="e19d0-252">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="e19d0-253">将设置配置为自动启动应用程序 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-253">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="e19d0-254">将 Teams 固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="e19d0-254">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="e19d0-255">请考虑减少设备上 Teams 通知，以避免干扰 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-255">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Teams 通知](images/teams.png)

### <a name="connect-app"></a><span data-ttu-id="e19d0-257">连接应用</span><span class="sxs-lookup"><span data-stu-id="e19d0-257">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e19d0-258">在 Windows 10 版本 2004 及更高版本中，默认情况下不会安装使用 Miracast 的用于无线投影的 Connect 应用，但作为可选功能提供。</span><span class="sxs-lookup"><span data-stu-id="e19d0-258">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="e19d0-259">如果你已安装 (或更新到) Windows 版本 2004 或更高版本，你可能会在"正在计划到此电脑"屏幕的设置中看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="e19d0-259">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Project to this PC](images/sh2-project.png) 


1. <span data-ttu-id="e19d0-261">若要从"计划到此电脑"设置页安装应用，请选择"可选**功能**添加功能"，然后  >  \*\*\*\* 安装**无线显示**应用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-261">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="e19d0-262">在 **"一些 Windows 和 Android 设备可以在**你说出'确定'时计划到此电脑"下，选择：</span><span class="sxs-lookup"><span data-stu-id="e19d0-262">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="e19d0-263">**如果设备** 不在企业网络上，则可在任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-263">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="e19d0-264">否则，在**安全网络上选择"可用"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-264">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="e19d0-265">在 **"询问到此电脑"下**，选择 **"仅首次"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-265">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="e19d0-266">在 **"需要 PIN 进行配对"下**，选择"**从不"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-266">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="e19d0-267">若要启动应用，将其固定到任务栏，请搜索**Connect。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-267">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="e19d0-268">打开应用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-268">Open the app.</span></span> <span data-ttu-id="e19d0-269">当应用打开时，右键单击任务栏上的 Connect 应用图标，然后选择 **固定到任务栏**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-269">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="e19d0-270">然后关闭 Connect 应用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-270">Then close the Connect app.</span></span> <span data-ttu-id="e19d0-271">**除非应用** 至少运行一次，否则此电脑的项目可能无法运行。</span><span class="sxs-lookup"><span data-stu-id="e19d0-271">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="e19d0-272">当不在企业网络上时，建议配置：</span><span class="sxs-lookup"><span data-stu-id="e19d0-272">Recommended configuration when not on the corporate network:</span></span>

![家庭设置](images/project1.png)

<span data-ttu-id="e19d0-274">企业网络上建议的配置：</span><span class="sxs-lookup"><span data-stu-id="e19d0-274">Recommended configuration on the corporate network:</span></span>

![工作中的设置](images/project2.png)

### <a name="your-phone"></a><span data-ttu-id="e19d0-276">你的手机</span><span class="sxs-lookup"><span data-stu-id="e19d0-276">Your Phone</span></span>

<span data-ttu-id="e19d0-277">默认情况下 **，你的手机** 应用安装在 Windows 10 上。</span><span class="sxs-lookup"><span data-stu-id="e19d0-277">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="e19d0-278">如果不存在，还可以从 Windows 应用商店安装它。</span><span class="sxs-lookup"><span data-stu-id="e19d0-278">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="e19d0-279">有关设置应用的信息，请参阅如何在 Windows 10 上设置你的手机，以及如何在电脑和手机之间同步 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 数据 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-279">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="e19d0-280">另请参阅 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 如何修复 Windows 10 上你的手机应用的常见问题 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-280">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <a name="fancy-zones"></a><span data-ttu-id="e19d0-281">奇特区域</span><span class="sxs-lookup"><span data-stu-id="e19d0-281">Fancy Zones</span></span>


<span data-ttu-id="e19d0-282">**奇特** 区域是 GitHub 上名为 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> 的工具集合的一部分。</span><span class="sxs-lookup"><span data-stu-id="e19d0-282">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="e19d0-283">这是利用 Surface Hub 2 上的屏幕空间的一种好方法，它让你能够在显示器上定义固定布局 ("区域") ，然后选择将在每个区域中运行的应用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-283">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="e19d0-284">[PowerToys Wiki](https://github.com/microsoft/PowerToys/wiki)提供了如何使用和自定义每个工具的说明，包括[奇特Zones。](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)</span><span class="sxs-lookup"><span data-stu-id="e19d0-284">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="e19d0-285">在高级别 – 安装 PowerToys 后，可以选择或创建自定义布局，然后按住 Shift 键，然后拖动或使用键盘键将正在运行的应用移动到特定区域。</span><span class="sxs-lookup"><span data-stu-id="e19d0-285">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="e19d0-286">使用Bluetooth或 USB 键盘和鼠标将对此有所帮助，或者可以使用屏幕触摸键盘和触摸板。</span><span class="sxs-lookup"><span data-stu-id="e19d0-286">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="e19d0-287">Power toys 提示</span><span class="sxs-lookup"><span data-stu-id="e19d0-287">Power toys tips</span></span>**
- <span data-ttu-id="e19d0-288">若要在 GitHub 上接收 PowerToys 发布更新的电子邮件通知，请单击页面顶部的"注册" [按钮](https://github.com/microsoft/PowerToys/releases)。</span><span class="sxs-lookup"><span data-stu-id="e19d0-288">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="e19d0-289">安装 PowerToys 后，可以通过配置 PowerToys 设置自动下载更新来接收 Windows 通知和/或下载\*\*\*\* 并安装最新更新。</span><span class="sxs-lookup"><span data-stu-id="e19d0-289">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="e19d0-290">若要访问 PowerToys 设置，请在任务栏上选择\*\*\*\* 运行应用，然后右键单击或长按 PowerToys 图标，直到菜单显示。</span><span class="sxs-lookup"><span data-stu-id="e19d0-290">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="e19d0-291">选择"设置"。</span><span class="sxs-lookup"><span data-stu-id="e19d0-291">Select “Settings”.</span></span>
- <span data-ttu-id="e19d0-292">在 PowerToys 设置页的底部，将 **下载更新自动打开** 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-292">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="e19d0-293">发布更新后，将显示 Windows 通知，提供安装更新时间的选项。</span><span class="sxs-lookup"><span data-stu-id="e19d0-293">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <a name="edge-chromium-browser"></a><span data-ttu-id="e19d0-294">Edge Chromium 浏览器</span><span class="sxs-lookup"><span data-stu-id="e19d0-294">Edge Chromium browser</span></span>

<span data-ttu-id="e19d0-295">下载并安装新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium 浏览器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-295">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <a name="surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="e19d0-296">Surface Hub 硬件诊断工具</span><span class="sxs-lookup"><span data-stu-id="e19d0-296">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="e19d0-297">可从 Microsoft Store 免费获得 <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub </a> 硬件诊断工具。</span><span class="sxs-lookup"><span data-stu-id="e19d0-297">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="e19d0-298">该工具旨在帮助你确保 Surface Hub 性能最佳。</span><span class="sxs-lookup"><span data-stu-id="e19d0-298">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="e19d0-299">它包含用于确定固件是否为最新且配置正确的测试。</span><span class="sxs-lookup"><span data-stu-id="e19d0-299">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="e19d0-300">交互式测试允许你确认基本功能是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="e19d0-300">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="e19d0-301">如果遇到问题，可保存结果并与 Surface Hub 支持团队共享。</span><span class="sxs-lookup"><span data-stu-id="e19d0-301">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="e19d0-302">单击链接以从 Microsoft Store 安装它，然后将应用程序固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="e19d0-302">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <a name="additional-settings"></a><span data-ttu-id="e19d0-303">其他设置</span><span class="sxs-lookup"><span data-stu-id="e19d0-303">Additional settings</span></span>

### <a name="pen-tail-select-to-launch-whiteboard"></a><span data-ttu-id="e19d0-304">笔尾选择以启动白板</span><span class="sxs-lookup"><span data-stu-id="e19d0-304">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="e19d0-305">搜索笔**并选择\*\*\*\*"笔& Windows Ink 设置**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-305">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="e19d0-306">在页面底部附近，在**笔快捷方式**下将 **"选择**一次"设置为 **"Microsoft Whiteboard"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-306">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <a name="power-management"></a><span data-ttu-id="e19d0-307">电源管理</span><span class="sxs-lookup"><span data-stu-id="e19d0-307">Power management</span></span>

<span data-ttu-id="e19d0-308">有几种电源设置可用于在 Surface Hub 2 上使用 Windows 10 专业版或企业版获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="e19d0-308">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="e19d0-309">这包括屏幕和电脑超时，以及它们如何与内置的人机状态检测 (Doppler) 、屏幕保护程序以及密码保护进行交互，然后在适当时如何传递适用于笔记本电脑/台式机用户的组策略电源设置。</span><span class="sxs-lookup"><span data-stu-id="e19d0-309">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="e19d0-310">Surface Hub 2 上的 Windows 10 专业版或企业版阻止屏幕通过触摸、鼠标和键盘操作以及内置的人体空间检测 (Doppler) 进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="e19d0-310">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="e19d0-311">默认情况下会启用人工占用检测，但如果需要，可以通过切换 Surface UEFI 配置器工具中的设备选项（作为初始迁移的一部分）或在 UEFI 配置包中生成和应用更高版本的 UEFI 配置包，在 UEFI 中禁用它。</span><span class="sxs-lookup"><span data-stu-id="e19d0-311">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="e19d0-312">电源管理：屏幕和电脑睡眠设置</span><span class="sxs-lookup"><span data-stu-id="e19d0-312">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="e19d0-313">选择 **"**  >  **启动设置**  >  **系统**  >  **电源&睡眠。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-313">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="e19d0-314">将电源模式滑块设置为 **最佳性能**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-314">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="e19d0-315">根据你的偏好配置屏幕和睡眠值，同时还负责在检测到移动时唤醒设备的 Doppler 状态检测。</span><span class="sxs-lookup"><span data-stu-id="e19d0-315">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="e19d0-316">因此，作为最佳实践，建议将"屏幕"设置为 **在 2** 小时后关闭，将电脑设置为 **在 4 小时后关闭。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-316">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="e19d0-317">电源管理：屏幕保护程序</span><span class="sxs-lookup"><span data-stu-id="e19d0-317">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="e19d0-318">搜索**锁屏界面并\*\*\*\*打开锁屏界面设置**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-318">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="e19d0-319">根据 **你的偏好配置** 屏幕超时 **设置和** 屏幕保护程序设置。</span><span class="sxs-lookup"><span data-stu-id="e19d0-319">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="e19d0-320">建议的默认值为：</span><span class="sxs-lookup"><span data-stu-id="e19d0-320">Recommended default values are:</span></span>

   - <span data-ttu-id="e19d0-321">屏幕保护 (选择) 选择的任何屏幕保护程序或屏幕保护程序。</span><span class="sxs-lookup"><span data-stu-id="e19d0-321">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="e19d0-322">等待时间到 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="e19d0-322">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="e19d0-323">恢复时，显示登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="e19d0-323">On resume, display logon screen.</span></span>


**<span data-ttu-id="e19d0-324">电源管理：组策略</span><span class="sxs-lookup"><span data-stu-id="e19d0-324">Power Management: Group Policy</span></span>**

<span data-ttu-id="e19d0-325">在执行以下过程之前，请咨询 IT 部门进行审批，以从全局电源管理策略中排除 Surface Hub 2S 设备。</span><span class="sxs-lookup"><span data-stu-id="e19d0-325">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="e19d0-326">某些电源管理设置可能会禁用状态检测功能。</span><span class="sxs-lookup"><span data-stu-id="e19d0-326">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="e19d0-327">搜索 **软件中心并** 打开它。</span><span class="sxs-lookup"><span data-stu-id="e19d0-327">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="e19d0-328">选择 **选项**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-328">Select **Options**.</span></span>

3. <span data-ttu-id="e19d0-329">展开 **"电源管理"，** 然后选择 **"不将我的 IT 部门的电源设置应用到此计算机"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-329">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![软件设置](images/soft-cntr.png)

### <a name="storage-sense"></a><span data-ttu-id="e19d0-331">存储感知</span><span class="sxs-lookup"><span data-stu-id="e19d0-331">Storage Sense</span></span>

<span data-ttu-id="e19d0-332">Surface Hub 2 具有 128GB SSD 用于本地存储，因此必须考虑在正常使用期间使用存储保存措施。</span><span class="sxs-lookup"><span data-stu-id="e19d0-332">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="e19d0-333">配置存储感知：</span><span class="sxs-lookup"><span data-stu-id="e19d0-333">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="e19d0-334">搜索 **"系统设置**"下的存储 **设置**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-334">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="e19d0-335">在 **"** 设置"下， **选择"打开存储感知** "以打开 **"存储设置"** 页。</span><span class="sxs-lookup"><span data-stu-id="e19d0-335">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="e19d0-336">将存储感知功能 **打开**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-336">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="e19d0-337">选择 **"配置存储** 感知"或现在运行它，并配置设置以尽可能使文件保持联机状态 (由于驱动器空间有限) 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-337">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="e19d0-338">推荐设置：</span><span class="sxs-lookup"><span data-stu-id="e19d0-338">Recommended settings:</span></span>

- <span data-ttu-id="e19d0-339">运行存储感知 = 每天。</span><span class="sxs-lookup"><span data-stu-id="e19d0-339">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="e19d0-340">删除我的应用未使用的临时文件 = 至少每 14 天 (一次) 。</span><span class="sxs-lookup"><span data-stu-id="e19d0-340">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="e19d0-341">删除"下载"文件夹中的文件（如果这些文件已保留超过 30 天）。</span><span class="sxs-lookup"><span data-stu-id="e19d0-341">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="e19d0-342">OneDrive：如果超过 30 天未打开内容，内容将变为仅联机状态。</span><span class="sxs-lookup"><span data-stu-id="e19d0-342">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <a name="tablet-mode"></a><span data-ttu-id="e19d0-343">平板电脑模式</span><span class="sxs-lookup"><span data-stu-id="e19d0-343">Tablet mode</span></span>

<span data-ttu-id="e19d0-344">如果需要辅助功能需求，请打开平板电脑模式。</span><span class="sxs-lookup"><span data-stu-id="e19d0-344">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <a name="sound-settings"></a><span data-ttu-id="e19d0-345">声音设置</span><span class="sxs-lookup"><span data-stu-id="e19d0-345">Sound settings</span></span>

1. <span data-ttu-id="e19d0-346">搜索 **"声音"设置** 并打开此页面。</span><span class="sxs-lookup"><span data-stu-id="e19d0-346">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="e19d0-347">选择 **右侧的声音** 控制面板，然后选择" **声音"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e19d0-347">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="e19d0-348">在 **"程序事件"下\*\*\*\*，将"设备连接**和设备**断开连接"\*\*\*\*设置为"无"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-348">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <a name="silence-notifications"></a><span data-ttu-id="e19d0-349">静默通知</span><span class="sxs-lookup"><span data-stu-id="e19d0-349">Silence notifications</span></span>

1. <span data-ttu-id="e19d0-350">搜索 **焦点协助并** 打开此页面。</span><span class="sxs-lookup"><span data-stu-id="e19d0-350">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="e19d0-351">选择 **"仅闹钟"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-351">Select **Alarms Only**.</span></span> <span data-ttu-id="e19d0-352">这将避免常量通知飞出。</span><span class="sxs-lookup"><span data-stu-id="e19d0-352">This will avoid constant notification flyouts.</span></span>

### <a name="disk-cleanup"></a><span data-ttu-id="e19d0-353">磁盘清理</span><span class="sxs-lookup"><span data-stu-id="e19d0-353">Disk Cleanup</span></span>

1. <span data-ttu-id="e19d0-354">搜索磁盘 **清理并** 打开此应用程序。</span><span class="sxs-lookup"><span data-stu-id="e19d0-354">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="e19d0-355">在 **"要删除的文件"下**，选择要删除的文件。</span><span class="sxs-lookup"><span data-stu-id="e19d0-355">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="e19d0-356">此外，**选择"清理系统文件"。**</span><span class="sxs-lookup"><span data-stu-id="e19d0-356">Also select **Clean up system files**.</span></span>

## <a name="complete-and-verify"></a><span data-ttu-id="e19d0-357">完成并验证</span><span class="sxs-lookup"><span data-stu-id="e19d0-357">Complete and verify</span></span>

1. <span data-ttu-id="e19d0-358">扫描并安装所有 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="e19d0-358">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="e19d0-359">更新组策略。</span><span class="sxs-lookup"><span data-stu-id="e19d0-359">Update Group Policy.</span></span>

   1. <span data-ttu-id="e19d0-360">在提升的命令提示符下，输入 **gpupdate /force /boot /wait：0**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-360">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="e19d0-361">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="e19d0-361">Restart the device.</span></span>

4. <span data-ttu-id="e19d0-362">验证任务栏应用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-362">Verify taskbar apps.</span></span>

   - <span data-ttu-id="e19d0-363">连接应用</span><span class="sxs-lookup"><span data-stu-id="e19d0-363">Connect App</span></span>
   - <span data-ttu-id="e19d0-364">锁定图标</span><span class="sxs-lookup"><span data-stu-id="e19d0-364">Lock Icon</span></span>
   - <span data-ttu-id="e19d0-365">截图和草图</span><span class="sxs-lookup"><span data-stu-id="e19d0-365">Snip & Sketch</span></span>
   - <span data-ttu-id="e19d0-366">Teams (（如果适用) </span><span class="sxs-lookup"><span data-stu-id="e19d0-366">Teams (if applicable)</span></span>
   - <span data-ttu-id="e19d0-367">Office Apps (（如果适用) </span><span class="sxs-lookup"><span data-stu-id="e19d0-367">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="e19d0-368">Surface App</span><span class="sxs-lookup"><span data-stu-id="e19d0-368">Surface App</span></span>
   - <span data-ttu-id="e19d0-369">白板</span><span class="sxs-lookup"><span data-stu-id="e19d0-369">Whiteboard</span></span>
    
5. <span data-ttu-id="e19d0-370">验证状态检测。</span><span class="sxs-lookup"><span data-stu-id="e19d0-370">Verify presence detection.</span></span>

   - <span data-ttu-id="e19d0-371">状态检测将是系统托盘中的绿色图标。</span><span class="sxs-lookup"><span data-stu-id="e19d0-371">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="e19d0-372">使用 Connect 应用验证是否已启用对此电脑进行项目规划。</span><span class="sxs-lookup"><span data-stu-id="e19d0-372">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="e19d0-373">将  **Project 配置为此电脑** 设置后，至少运行一次 Connect App。</span><span class="sxs-lookup"><span data-stu-id="e19d0-373">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="e19d0-374"> (，连接应用无需运行，就无需在 Surface Hub.) </span><span class="sxs-lookup"><span data-stu-id="e19d0-374">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="e19d0-375">验证电源和睡眠设置。</span><span class="sxs-lookup"><span data-stu-id="e19d0-375">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="e19d0-376">屏幕保护程序：15 分钟，设置为 (、) 或空白;确保选中了要求密码的复选框。</span><span class="sxs-lookup"><span data-stu-id="e19d0-376">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="e19d0-377">屏幕 **：2 小时后关闭**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-377">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="e19d0-378">电脑  **：4 小时后关闭**。</span><span class="sxs-lookup"><span data-stu-id="e19d0-378">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="e19d0-379">验证 Windows Hello 是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="e19d0-379">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="e19d0-380">验证已禁用同步设置。</span><span class="sxs-lookup"><span data-stu-id="e19d0-380">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="e19d0-381">验证启动应用。</span><span class="sxs-lookup"><span data-stu-id="e19d0-381">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="e19d0-382">安装和配置 Windows 10 后，可以像管理任何其他 Windows 10 设备一样管理 Surface Hub 2S。</span><span class="sxs-lookup"><span data-stu-id="e19d0-382">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e19d0-383">相关主题</span><span class="sxs-lookup"><span data-stu-id="e19d0-383">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="e19d0-384">迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="e19d0-384">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>

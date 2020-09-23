---
title: 配置 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文包含的建议可确保使用个性化的大屏幕触摸和手写笔计算机时获得最佳体验。
keywords: Surface Hub，Windows 10，桌面，安装，配置
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
ms.date: 09/22/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: dd580a3b67ffa7c46ce823765d589fec47fadb44
ms.sourcegitcommit: d7fe059a823b7e5f1daec447d92dac60bdd2a26e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "11072839"
---
# <span data-ttu-id="29d7a-104">配置 Surface Hub 2 上的 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="29d7a-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="29d7a-105">完成迁移到 Windows 10 专业版或企业版的安装过程后，您可以执行以下步骤来配置 Surface Hub 2 上的应用和设置。</span><span class="sxs-lookup"><span data-stu-id="29d7a-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="29d7a-106">建议执行这些步骤，以确保使用此个性化的大屏幕触摸和笔电脑时获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="29d7a-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="29d7a-107">执行这些步骤时，您可能会发现使用有线键盘或无线键盘和鼠标非常有用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="29d7a-108">配置系统设置</span><span class="sxs-lookup"><span data-stu-id="29d7a-108">Configure system settings</span></span>

1. <span data-ttu-id="29d7a-109">使用对设备具有本地管理员权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="29d7a-109">Sign in with an account that has local administrator privileges on the device.</span></span>  
    - <span data-ttu-id="29d7a-110">在 Azure AD 已加入设备上，执行 Azure AD 联接的用户将自动添加到本地管理员组。</span><span class="sxs-lookup"><span data-stu-id="29d7a-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="29d7a-111">Azure AD 全局管理员和 Azure AD 设备管理员 [也是本地管理员](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)。</span><span class="sxs-lookup"><span data-stu-id="29d7a-111">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    - <span data-ttu-id="29d7a-112">您可以在命令提示符下键入 **net localgroup 管理员** ，以列出具有本地管理员权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="29d7a-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
2. <span data-ttu-id="29d7a-113">使用友好名称重命名设备，例如： **username-SHub-Desktop**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>
3. <span data-ttu-id="29d7a-114">选择 "**启动**  >  **设置**  >  **帐户**"  >  **同步你的设置**，并关闭**同步设置**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 
    - <span data-ttu-id="29d7a-115">此处使用的设置旨在启用最佳的屏幕触摸体验，因此你可能不希望同步其他设备。</span><span class="sxs-lookup"><span data-stu-id="29d7a-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
4. <span data-ttu-id="29d7a-116">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="29d7a-116">Reboot the device.</span></span>

## <span data-ttu-id="29d7a-117">启用触摸键盘和触摸板</span><span class="sxs-lookup"><span data-stu-id="29d7a-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="29d7a-118">点击并按住或右键单击任务栏，然后选择 " **显示触摸键盘按钮** " 和 " **显示触摸板" 按钮**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 
    - <span data-ttu-id="29d7a-119">触摸键盘对直接用户输入很有帮助，虚拟触摸板可帮助精确选择、悬停屏幕提示，或者作为点击并按住右键单击的替代方法。</span><span class="sxs-lookup"><span data-stu-id="29d7a-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="29d7a-120">请参阅以下示例。</span><span class="sxs-lookup"><span data-stu-id="29d7a-120">See the following example.</span></span>

     ![触摸设置](images/touch.png)

2. <span data-ttu-id="29d7a-122">将触摸键盘配置为 "标准" 和 "浮动"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-122">Configure the touch keyboard to QWERTY and floating.</span></span>
    1. <span data-ttu-id="29d7a-123">选择任务栏上的键盘图标以显示触摸键盘。</span><span class="sxs-lookup"><span data-stu-id="29d7a-123">Select the keyboard icon on the taskbar to show the touch keyboard.</span></span>
    2. <span data-ttu-id="29d7a-124">在触摸键盘上，选择左上角的键盘图标以打开 "键盘设置"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    3. <span data-ttu-id="29d7a-125">选择顶部行上的 "最后一次键盘类型" 以启用标准，第二行中的最后一个选项启用浮动，这在大屏幕上非常有用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="29d7a-126">请参阅以下示例。</span><span class="sxs-lookup"><span data-stu-id="29d7a-126">See the following examples.</span></span>

     ![键盘设置](images/kbd.png)

3. <span data-ttu-id="29d7a-128">配置软键盘设置。</span><span class="sxs-lookup"><span data-stu-id="29d7a-128">Configure the soft keyboard settings.</span></span>
    1. <span data-ttu-id="29d7a-129">搜索并打开 **键入设置**</span><span class="sxs-lookup"><span data-stu-id="29d7a-129">Search for and open **Typing settings**</span></span> 
    2. <span data-ttu-id="29d7a-130">启用 "拼写检查"、"键入" 和 "触摸键盘" 下的所有选项。</span><span class="sxs-lookup"><span data-stu-id="29d7a-130">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="29d7a-131">以下示例显示了触控板，这对导航和选择选项很有用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-131">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="29d7a-132">屏幕键盘用于搜索 Microsoft Store：</span><span class="sxs-lookup"><span data-stu-id="29d7a-132">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![使用触控板](images/store.png)

## <span data-ttu-id="29d7a-134">配置蓝牙键盘和鼠标 (可选) </span><span class="sxs-lookup"><span data-stu-id="29d7a-134">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="29d7a-135">如果将设备用作主 Windows 设备，则连接键盘和鼠标，或者经常将其用于键入或精度工作。</span><span class="sxs-lookup"><span data-stu-id="29d7a-135">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="29d7a-136">如果 Surface Hub 设备靠近 PC，则可以使用 [没有边框的鼠标](https://aka.ms/mm) 在 Surface HUB 和 PC 之间无缝移动。</span><span class="sxs-lookup"><span data-stu-id="29d7a-136">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="29d7a-137">有关详细信息，请参阅 [Microsoft 从车库下载：不带边框的鼠标](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/)。</span><span class="sxs-lookup"><span data-stu-id="29d7a-137">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="29d7a-138">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="29d7a-138">OneDrive for Business</span></span>

<span data-ttu-id="29d7a-139">使用 [OneDrive For business](https://docs.microsoft.com/onedrive/onedrive) 在所有工作设备之间轻松共享工具、日志和其他文件。</span><span class="sxs-lookup"><span data-stu-id="29d7a-139">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="29d7a-140">OneDrive 使你能够在笔记本电脑、Surface Hub 桌面和你的 Intune 管理的移动设备之间共享你的工作文件。</span><span class="sxs-lookup"><span data-stu-id="29d7a-140">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="29d7a-141">可以在任何设备上编辑文件，并且所有连接网络的设备都将更新为所做的更改。</span><span class="sxs-lookup"><span data-stu-id="29d7a-141">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="29d7a-142">考虑 Surface Hub SSD 的大小 (128GB) ，如果在 Surface Hub 桌面设备上配置 OneDrive，请确保默认配置是在使用文件时保持联机文件和下载文件。</span><span class="sxs-lookup"><span data-stu-id="29d7a-142">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="29d7a-143">若要将 OneDrive 配置为仅在需要时下载文件，请设置 **文件的按需** 设置以在 **使用时节省空间和下载文件**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-143">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="29d7a-144">有关详细信息，请参阅 [在 Windows 中查询和设置文件的按需状态](https://docs.microsoft.com/onedrive/files-on-demand-windows)。</span><span class="sxs-lookup"><span data-stu-id="29d7a-144">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![OneDrive 设置](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="29d7a-146">您也可以重复这些步骤来配置个人 OneDrive，但请确保保留驱动器空间，并且仅在需要时下载文件。</span><span class="sxs-lookup"><span data-stu-id="29d7a-146">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="29d7a-147">SharePoint 和团队</span><span class="sxs-lookup"><span data-stu-id="29d7a-147">SharePoint and Teams</span></span>

<span data-ttu-id="29d7a-148">SharePoint 和团队频道文件也可以使用 OneDrive 同步引擎在本地与桌面设备（如便携式计算机和 Surface Hub）同步。</span><span class="sxs-lookup"><span data-stu-id="29d7a-148">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="29d7a-149">若要将内部公司文件与 OneDrive 同步应用同步到本地驱动器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="29d7a-149">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="29d7a-150">转到 SharePoint 网站，然后导航到要从本地设备查看或编辑的文件的顶级文档目录。</span><span class="sxs-lookup"><span data-stu-id="29d7a-150">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>
2. <span data-ttu-id="29d7a-151">选择 SharePoint 功能区顶部的 " **同步** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="29d7a-151">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>
3. <span data-ttu-id="29d7a-152">在弹出菜单上选择 " **打开** "。 **此网站将尝试打开 Microsoft OneDrive**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-152">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>
4. <span data-ttu-id="29d7a-153">通过选择任务栏右下角的 OneDrive 图标，验证 SharePoint 文件是否同步到本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="29d7a-153">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>
5. <span data-ttu-id="29d7a-154">验证配置是否已设置为保持联机文件，并仅在使用时下载文件：</span><span class="sxs-lookup"><span data-stu-id="29d7a-154">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>
    1. <span data-ttu-id="29d7a-155">打开文件资源管理器。</span><span class="sxs-lookup"><span data-stu-id="29d7a-155">Open file explorer.</span></span>
    2. <span data-ttu-id="29d7a-156">导航到并右键选择\*\*Microsoft \ \<SharePoint Document Folder Name\> \*\*。</span><span class="sxs-lookup"><span data-stu-id="29d7a-156">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="29d7a-157">选择 " **释放空间**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-157">Select **Free up space**.</span></span>
    4. <span data-ttu-id="29d7a-158">"状态" 列将显示文件和文件夹的状态。</span><span class="sxs-lookup"><span data-stu-id="29d7a-158">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="29d7a-159">有关详细信息，请参阅 [与 OneDrive 同步客户端同步 SharePoint 文件](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd)。</span><span class="sxs-lookup"><span data-stu-id="29d7a-159">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
6. <span data-ttu-id="29d7a-160">团队频道文件存储在 SharePoint 网站中，具有所有相同的 SharePoint 文档功能，包括版本历史记录和同步到本地桌面设备。</span><span class="sxs-lookup"><span data-stu-id="29d7a-160">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="29d7a-161">要同步团队频道文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="29d7a-161">To sync Teams Channel files:</span></span>
    1. <span data-ttu-id="29d7a-162">导航到感兴趣的团队频道，然后选择顶部的 " **文件** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="29d7a-162">Navigate to the Teams Channel of interest and select on the **Files** tab at the top.</span></span> <span data-ttu-id="29d7a-163">然后选择 "**同步**"。文件将开始同步，并且将在\*\*桌面 \ Microsoft \ \<name of the Teams Channel\> \*\*的文件资源管理器中可见。</span><span class="sxs-lookup"><span data-stu-id="29d7a-163">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="29d7a-164">使用您用于同步 SharePoint 网站的相同过程将文件保存在云中，并仅在使用它们时下载它们，方法是在 "文件资源管理器" 的 "团队频道名称" 中点击并按住或右键单击，然后选择 " **释放空间**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-164">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="29d7a-165">配对 Surface Hub 笔</span><span class="sxs-lookup"><span data-stu-id="29d7a-165">Pair the Surface Hub pen</span></span>

<span data-ttu-id="29d7a-166">要配对笔设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="29d7a-166">To pair the pen device:</span></span>

1. <span data-ttu-id="29d7a-167">选择 "**开始**  >  **设置**  >  **设备**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-167">Select **Start** > **Settings** > **Devices**.</span></span>
2. <span data-ttu-id="29d7a-168">选择 " **添加蓝牙" 或 "其他设备**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-168">Select **Add Bluetooth or other device**.</span></span>
3. <span data-ttu-id="29d7a-169">选择 " **蓝牙**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-169">Choose **Bluetooth**.</span></span>
4. <span data-ttu-id="29d7a-170">卸下笔尾按钮，然后晃动以断开电池连接。</span><span class="sxs-lookup"><span data-stu-id="29d7a-170">Remove the pen tail button and shake to disconnect the battery connection.</span></span>
5. <span data-ttu-id="29d7a-171">将 cap 放回原位并按住 cap，直到配对指示灯闪烁。</span><span class="sxs-lookup"><span data-stu-id="29d7a-171">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>
6. <span data-ttu-id="29d7a-172">在 Surface Hub 蓝牙设置中，选择 " **Surface hub 2 笔**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-172">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>
7. <span data-ttu-id="29d7a-173">完成配对操作。</span><span class="sxs-lookup"><span data-stu-id="29d7a-173">Complete the pairing operation.</span></span> 
8. <span data-ttu-id="29d7a-174">如果配对不成功，请再次尝试配对笔。</span><span class="sxs-lookup"><span data-stu-id="29d7a-174">If the pairing is not successful, attempt to pair the pen again.</span></span> <span data-ttu-id="29d7a-175">如有必要，请重新启动设备，然后重试。</span><span class="sxs-lookup"><span data-stu-id="29d7a-175">If necessary, reboot the device and then try again.</span></span>

## <span data-ttu-id="29d7a-176">照相机配置</span><span class="sxs-lookup"><span data-stu-id="29d7a-176">Camera configuration</span></span>

<span data-ttu-id="29d7a-177">可以在设备顶部或任意一侧安装相机。</span><span class="sxs-lookup"><span data-stu-id="29d7a-177">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="29d7a-178">如果您使用的是桌面支架而不是 cart，或者在与集线器紧密邻近的位置使用集线器，请将相机装入位置以优化相机角度。</span><span class="sxs-lookup"><span data-stu-id="29d7a-178">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="29d7a-179">摄像头不会自动旋转，因此你需要具有2mm 十六进制密钥才能手动旋转相机。</span><span class="sxs-lookup"><span data-stu-id="29d7a-179">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="29d7a-180">有关如何安装相机以及手动旋转相机的详细信息，请参阅 [Surface Hub 2 相机镜头方向](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation)。</span><span class="sxs-lookup"><span data-stu-id="29d7a-180">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="29d7a-181">Windows Hello 配置</span><span class="sxs-lookup"><span data-stu-id="29d7a-181">Windows Hello configuration</span></span>

<span data-ttu-id="29d7a-182">运行 Windows 10 企业版的 Surface Hub 2 支持完整的 Win32 桌面应用程序和生物识别 Windows Hello 选项。</span><span class="sxs-lookup"><span data-stu-id="29d7a-182">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="29d7a-183">Surface Hub 2 指纹读取器附件可以插入到设备上的任何 USB 端口。</span><span class="sxs-lookup"><span data-stu-id="29d7a-183">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

> <i><span data-ttu-id="29d7a-184">Surface Hub 2 指纹读取器将立即可供购买。</span><span class="sxs-lookup"><span data-stu-id="29d7a-184">The Surface Hub 2 Fingerprint Reader will be available for purchase soon.</span></span> <span data-ttu-id="29d7a-185">有关详细信息，请查看此页面，包括如何购买。</span><span class="sxs-lookup"><span data-stu-id="29d7a-185">Please check back on this page for more information including how to purchase.</span></span></i>

<span data-ttu-id="29d7a-186">插入指纹读取器后，选择 "**开始**  >  **设置**  >  **帐户**"  >  **登录选项**  >  **Windows Hello 指纹**以注册指纹。</span><span class="sxs-lookup"><span data-stu-id="29d7a-186">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="29d7a-187">使用 Windows Hello 认证设备进行面对面认可。</span><span class="sxs-lookup"><span data-stu-id="29d7a-187">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="29d7a-188">Surface Hub 2 摄像头不支持 Windows Hello 人脸识别。</span><span class="sxs-lookup"><span data-stu-id="29d7a-188">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="29d7a-189">在任务栏上启用锁定屏幕快捷方式图标</span><span class="sxs-lookup"><span data-stu-id="29d7a-189">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="29d7a-190">若要将图标添加到任务栏以启用与 Windows-L 键盘快捷方式类似的触摸屏幕锁定，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="29d7a-190">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="29d7a-191">点击并按住或右键单击桌面，选择 "**新建**  >  **快捷方式**  >  **Browse**  >  **Desktop**  >  **"**  >  **下一步**"浏览桌面确定"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-191">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="29d7a-192">为快捷方式提供一个名称，例如 **锁定我的 PC**，然后选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-192">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="29d7a-193">右键单击或点击并按住桌面上新创建的快捷方式，然后选择 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-193">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="29d7a-194">在 " **快捷方式** " 选项卡上，在 " **目标** " 字段中输入以下内容： **Rundll32.exe User32.dll，LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="29d7a-194">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="29d7a-195">选择 " **更改图标** " 按钮，浏览到 **C:\Windows\System32\imageres.dll** 并选择要使用的图标。</span><span class="sxs-lookup"><span data-stu-id="29d7a-195">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="29d7a-196">请参见以下示例：</span><span class="sxs-lookup"><span data-stu-id="29d7a-196">See the following example:</span></span>

    ![选择图标](images/lock.png)
    
1.  <span data-ttu-id="29d7a-198">选择 **"确定"** 保存快捷方式。</span><span class="sxs-lookup"><span data-stu-id="29d7a-198">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="29d7a-199">右键单击或点击并按住快捷方式，然后选择 " **固定到任务栏**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-199">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

## <span data-ttu-id="29d7a-200">应用程序</span><span class="sxs-lookup"><span data-stu-id="29d7a-200">Applications</span></span>

### <span data-ttu-id="29d7a-201">更新已安装的应用</span><span class="sxs-lookup"><span data-stu-id="29d7a-201">Update installed apps</span></span>

<span data-ttu-id="29d7a-202">若要更新安装的所有应用商店应用：</span><span class="sxs-lookup"><span data-stu-id="29d7a-202">To update all installed Store apps:</span></span>

1. <span data-ttu-id="29d7a-203">打开 Microsoft Store 应用，然后在右上角选择 " **查看更多** 省略号"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-203">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="29d7a-204">选择 **下载和更新**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-204">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="29d7a-205">选择**获取更新**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-205">Select **Get updates**.</span></span>

### <span data-ttu-id="29d7a-206">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="29d7a-206">Microsoft Whiteboard</span></span>

<span data-ttu-id="29d7a-207">要安装 Microsoft 白板，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="29d7a-207">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="29d7a-208">选择任务栏右下角的 **Windows Ink 工作区** 图标，然后下载 **白板**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-208">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![墨迹工作区](images/ink.png) 

<span data-ttu-id="29d7a-210">或者，您可以从 Microsoft Store 安装白板：</span><span class="sxs-lookup"><span data-stu-id="29d7a-210">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="29d7a-211">打开 Microsoft Store 应用并搜索 **白板**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-211">Open Microsoft Store app and search for **Whiteboard**.</span></span>
2. <span data-ttu-id="29d7a-212">选择 "无"， **谢谢** 通过设备登录和使用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-212">Choose **No thanks** to sign in and use across devices.</span></span>
3. <span data-ttu-id="29d7a-213">将白板固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="29d7a-213">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="29d7a-214">Surface 应用</span><span class="sxs-lookup"><span data-stu-id="29d7a-214">Surface app</span></span>

1. <span data-ttu-id="29d7a-215">在 Microsoft Store 中，搜索 **Surface**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-215">In the Microsoft Store, search for **Surface**.</span></span>
2. <span data-ttu-id="29d7a-216">将 " **在筛选器中可用** " 设置为 " **所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-216">Set the **Available on** filter to **All devices**.</span></span>
3. <span data-ttu-id="29d7a-217">安装 **Surface** app。</span><span class="sxs-lookup"><span data-stu-id="29d7a-217">Install the **Surface** app.</span></span> <span data-ttu-id="29d7a-218">这应该是列出的第一个应用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-218">This should be the first app listed.</span></span> <span data-ttu-id="29d7a-219">你可能需要将你的 MSA 与应用商店相关联才能安装该应用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-219">You might need to associate your MSA to the Store in order to install the app.</span></span>
4. <span data-ttu-id="29d7a-220">将 **Surface** app 固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="29d7a-220">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="29d7a-221">截图和草图</span><span class="sxs-lookup"><span data-stu-id="29d7a-221">Snip & Sketch</span></span>

1. <span data-ttu-id="29d7a-222">打开 **截图 & "草拟** " 应用，并将其固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="29d7a-222">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>
2. <span data-ttu-id="29d7a-223">选择右上角的省略号，然后选择 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-223">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>
3. <span data-ttu-id="29d7a-224">在 " **设置**" 中，打开 " **自动复制到剪贴板**"、" **保存截图**" 和 " **多个窗口** " (可选) 。</span><span class="sxs-lookup"><span data-stu-id="29d7a-224">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="29d7a-225">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="29d7a-225">Microsoft Office</span></span>

1. <span data-ttu-id="29d7a-226">打开 [Office 门户](https://portal.office.com/account#installs) 并安装所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="29d7a-226">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>
2. <span data-ttu-id="29d7a-227">将所需的 Office 应用程序固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="29d7a-227">Pin desired Office applications to the taskbar.</span></span>
3. <span data-ttu-id="29d7a-228">如果已安装 Outlook，请确保将 Outlook OST 设置为仅保存最近两周的缓存。</span><span class="sxs-lookup"><span data-stu-id="29d7a-228">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="29d7a-229">这将大大减少磁盘使用量和设置时间。</span><span class="sxs-lookup"><span data-stu-id="29d7a-229">This will vastly reduce disk usage and setup time.</span></span>
    - <span data-ttu-id="29d7a-230">选择 "**文件**  >  **帐户设置**"，然后选择您的帐户。</span><span class="sxs-lookup"><span data-stu-id="29d7a-230">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="29d7a-231">选择 " **更改** "，将 " **使用缓存 Exchange 模式** " 滑块设置为14天。</span><span class="sxs-lookup"><span data-stu-id="29d7a-231">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="29d7a-232">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29d7a-232">Microsoft Teams</span></span>

1. <span data-ttu-id="29d7a-233">下载并安装 [Microsoft 团队](https://teams.microsoft.com/downloads)。</span><span class="sxs-lookup"><span data-stu-id="29d7a-233">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>
2. <span data-ttu-id="29d7a-234">将设置配置为自动启动应用程序 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="29d7a-234">Configure settings to Auto-start application (optional).</span></span>
3. <span data-ttu-id="29d7a-235">将团队固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="29d7a-235">Pin Teams to the taskbar.</span></span>
4. <span data-ttu-id="29d7a-236">请考虑减少设备上的团队通知，避免干扰 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="29d7a-236">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

  ![团队通知](images/teams.png)

### <span data-ttu-id="29d7a-238">Connect 应用</span><span class="sxs-lookup"><span data-stu-id="29d7a-238">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29d7a-239">在 Windows 10 版本2004及更高版本中，默认情况下不会安装使用 Miracast 的无线投影的 Connect 应用，但可用作可选功能。</span><span class="sxs-lookup"><span data-stu-id="29d7a-239">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="29d7a-240">若要安装应用，请选择 "**设置**  >  **应用**"  >  **可选功能**  >  **添加功能**，然后安装**无线显示器**应用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-240">To install the app, select on **Settings** > **Apps** > **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

1. <span data-ttu-id="29d7a-241">搜索 **连接**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-241">Search for **Connect**.</span></span>
2. <span data-ttu-id="29d7a-242">打开应用，然后将其关闭 (**Project 到此电脑** 可能无法正常工作，除非该应用至少已运行一次) 。</span><span class="sxs-lookup"><span data-stu-id="29d7a-242">Open the app and then close it (**Project to this PC** might not work unless the app has been run at least once).</span></span>
3. <span data-ttu-id="29d7a-243">点击并按住或右键单击以固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="29d7a-243">Tap and hold or right-click to pin to taskbar.</span></span>
4. <span data-ttu-id="29d7a-244">搜索 **投影设置**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-244">Search for **Projection settings**.</span></span>
5. <span data-ttu-id="29d7a-245">在 **某些 Windows 和 Android 设备**下，如果你认为它是正常的，请选择 "任何地方都可用"，如果设备不在公司网络上，请选择 " **所有地方可用** "。</span><span class="sxs-lookup"><span data-stu-id="29d7a-245">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose **Available everywhere** if the device is not on a corporate network.</span></span> <span data-ttu-id="29d7a-246">否则，您可以选择 **"在安全网络上的所有位置均可用"**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-246">Otherwise, you can choose **Available everywhere on secure networks**.</span></span>
6. <span data-ttu-id="29d7a-247">在 " **要求在这台电脑上投影**" 下，选择 " **仅首次**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-247">Under **Ask to project to this PC**, choose **First time only**.</span></span>
7. <span data-ttu-id="29d7a-248">在 " **需要 PIN 才能进行配对**" 下，选择 " **从不**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-248">Under **Require PIN for pairing**, choose **Never**.</span></span>

<span data-ttu-id="29d7a-249">不在公司网络上时的推荐配置：</span><span class="sxs-lookup"><span data-stu-id="29d7a-249">Recommended configuration when not on the corporate network:</span></span>

  ![家庭设置](images/project1.png)

<span data-ttu-id="29d7a-251">公司网络上的推荐配置：</span><span class="sxs-lookup"><span data-stu-id="29d7a-251">Recommended configuration on the corporate network:</span></span>

  ![工作中的设置](images/project2.png)

### <span data-ttu-id="29d7a-253">你的手机</span><span class="sxs-lookup"><span data-stu-id="29d7a-253">Your Phone</span></span>

<span data-ttu-id="29d7a-254">默认情况下， **您的手机** 应用安装在 Windows 10 上。</span><span class="sxs-lookup"><span data-stu-id="29d7a-254">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="29d7a-255">如果不存在，还可以从 Windows 应用商店安装它。</span><span class="sxs-lookup"><span data-stu-id="29d7a-255">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="29d7a-256">有关设置应用的信息，请参阅 [如何在 Windows 10 上设置你的电话和在电脑和手机之间同步数据](https://www.windowscentral.com/how-set-your-phone-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="29d7a-256">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="29d7a-257">另请参阅 [如何修复 Windows 10 上的手机应用常见问题](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="29d7a-257">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="29d7a-258">超级别致区域</span><span class="sxs-lookup"><span data-stu-id="29d7a-258">Super Fancy Zones</span></span>

<span data-ttu-id="29d7a-259">**Super 别致的区域** 可帮助用户排列窗口以最大化屏幕房地产。</span><span class="sxs-lookup"><span data-stu-id="29d7a-259">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="29d7a-260">它现已包含在 GitHub 上的 [PowerToys](https://github.com/microsoft/PowerToys/releases) 中。</span><span class="sxs-lookup"><span data-stu-id="29d7a-260">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="29d7a-261">Edge Chromium 浏览器</span><span class="sxs-lookup"><span data-stu-id="29d7a-261">Edge Chromium browser</span></span>

<span data-ttu-id="29d7a-262">下载并安装新的 [Edge Chromium 浏览器](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL)。</span><span class="sxs-lookup"><span data-stu-id="29d7a-262">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="29d7a-263">其他设置</span><span class="sxs-lookup"><span data-stu-id="29d7a-263">Additional settings</span></span>

### <span data-ttu-id="29d7a-264">选择 "笔尾" 以启动白板</span><span class="sxs-lookup"><span data-stu-id="29d7a-264">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="29d7a-265">搜索 **笔** 并选择 " **笔" & Windows Ink 设置**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-265">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>
2. <span data-ttu-id="29d7a-266">在页面底部的 " **笔快捷方式** " 下，将 " **选择一次** " 设置为 " **Microsoft 白板**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-266">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="29d7a-267">电源和睡眠设置</span><span class="sxs-lookup"><span data-stu-id="29d7a-267">Power and sleep settings</span></span>

1. <span data-ttu-id="29d7a-268">选择 "**开始**  >  **设置**  >  **系统**  >  **Power & 睡眠**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-268">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>
2. <span data-ttu-id="29d7a-269">将 "电源模式" 滑块设置为 " **最佳性能**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-269">Set the power mode slider to **Best performance**.</span></span>
3. <span data-ttu-id="29d7a-270">将屏幕和睡眠值配置为你的首选项，同时还可以对检测到移动时唤醒设备的 Doppler 状态检测进行评估。</span><span class="sxs-lookup"><span data-stu-id="29d7a-270">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="29d7a-271">因此，最佳做法是，建议在 **2 小时后** 将屏幕设置为关闭，并在 **4 小时后关闭电脑。**</span><span class="sxs-lookup"><span data-stu-id="29d7a-271">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>
### <span data-ttu-id="29d7a-272">屏幕保护程序。</span><span class="sxs-lookup"><span data-stu-id="29d7a-272">Screen saver.</span></span>

1. <span data-ttu-id="29d7a-273">搜索 **锁屏界面** 和打开 **锁定屏幕设置**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-273">Search for **Lock Screen** and open **Lock screen settings**.</span></span>
2. <span data-ttu-id="29d7a-274">将 **屏幕超时设置** 和 **屏幕保护程序设置** 配置为你的首选项。</span><span class="sxs-lookup"><span data-stu-id="29d7a-274">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span>

### <span data-ttu-id="29d7a-275">存储感知</span><span class="sxs-lookup"><span data-stu-id="29d7a-275">Storage Sense</span></span>

<span data-ttu-id="29d7a-276">Surface Hub 2 具有用于本地存储的 128GB SSD，因此在正常使用期间，有必要考虑使用存储保存措施。</span><span class="sxs-lookup"><span data-stu-id="29d7a-276">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="29d7a-277">要配置存储感知，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="29d7a-277">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="29d7a-278">搜索在 "**系统设置**" 下找到的**存储设置**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-278">Search for **storage settings**, which is found under **System settings**.</span></span>
2.  <span data-ttu-id="29d7a-279">在 " **设置**" 下，选择 " **打开存储感知** " 以打开 " **存储** 设置" 页面。</span><span class="sxs-lookup"><span data-stu-id="29d7a-279">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>
3.  <span data-ttu-id="29d7a-280">将 "存储感知 **" 转到 "开"**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-280">Turn Storage Sense to **On**.</span></span>
4.  <span data-ttu-id="29d7a-281">选择 " **配置存储感知" 或 "立即运行** "，并配置设置以尽可能多地使文件联机， (因) 的驱动器空间有限。</span><span class="sxs-lookup"><span data-stu-id="29d7a-281">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="29d7a-282">推荐设置：</span><span class="sxs-lookup"><span data-stu-id="29d7a-282">Recommended settings:</span></span>
- <span data-ttu-id="29d7a-283">每日运行的存储感知。</span><span class="sxs-lookup"><span data-stu-id="29d7a-283">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="29d7a-284">删除我的应用未使用的临时文件 = 每隔14天 (至少) 。</span><span class="sxs-lookup"><span data-stu-id="29d7a-284">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="29d7a-285">如果超过30天，则删除 "我的下载" 文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="29d7a-285">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="29d7a-286">OneDrive：如果未打开超过 = 30 天，内容将转为联机状态。</span><span class="sxs-lookup"><span data-stu-id="29d7a-286">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="29d7a-287">平板电脑模式</span><span class="sxs-lookup"><span data-stu-id="29d7a-287">Tablet mode</span></span>

<span data-ttu-id="29d7a-288">如果需要，请打开平板电脑模式以获得辅助功能需求。</span><span class="sxs-lookup"><span data-stu-id="29d7a-288">Turn on Tablet mode if desired for accessibility needs.</span></span>

### <span data-ttu-id="29d7a-289">电源管理</span><span class="sxs-lookup"><span data-stu-id="29d7a-289">Power management</span></span>

> [!NOTE]
> <span data-ttu-id="29d7a-290">在执行以下过程之前，请与 IT 部门联系以批准从全局电源管理策略中排除 Surface Hub 2 设备。</span><span class="sxs-lookup"><span data-stu-id="29d7a-290">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="29d7a-291">某些电源管理设置可以禁用状态检测功能。</span><span class="sxs-lookup"><span data-stu-id="29d7a-291">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="29d7a-292">搜索 **软件中心** 并将其打开。</span><span class="sxs-lookup"><span data-stu-id="29d7a-292">Search for **Software Center** and open it.</span></span>
2. <span data-ttu-id="29d7a-293">在导航窗格中选择 " **选项** "。</span><span class="sxs-lookup"><span data-stu-id="29d7a-293">Select **Options** in the navigation pane.</span></span>
3. <span data-ttu-id="29d7a-294">展开 " **电源管理** " 部分，然后选择 **"不将 IT 部门的电源设置应用到此计算机"**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-294">Expand the **Power management** section and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![软件设置](images/soft-cntr.png)

### <span data-ttu-id="29d7a-296">声音设置</span><span class="sxs-lookup"><span data-stu-id="29d7a-296">Sound settings</span></span>

1. <span data-ttu-id="29d7a-297">搜索 " **声音设置** " 并打开此页面。</span><span class="sxs-lookup"><span data-stu-id="29d7a-297">Search for **Sounds settings** and open this page.</span></span>
2. <span data-ttu-id="29d7a-298">选择右侧的 **"声音控制面板** "，然后选择 " **声音** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="29d7a-298">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>
3. <span data-ttu-id="29d7a-299">在 " **程序事件** " 下，将 **设备连接** 和 **设备断开** 连接到 " **无**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-299">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="29d7a-300">静音通知</span><span class="sxs-lookup"><span data-stu-id="29d7a-300">Silence notifications</span></span>

1. <span data-ttu-id="29d7a-301">搜索 " **聚焦助手** "，然后打开此页面。</span><span class="sxs-lookup"><span data-stu-id="29d7a-301">Search for **Focus assist** and open this page.</span></span>
2. <span data-ttu-id="29d7a-302">选择 " **仅闹钟**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-302">Select **Alarms Only**.</span></span> <span data-ttu-id="29d7a-303">这将避免持续通知浮出控件。</span><span class="sxs-lookup"><span data-stu-id="29d7a-303">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="29d7a-304">磁盘清理</span><span class="sxs-lookup"><span data-stu-id="29d7a-304">Disk Cleanup</span></span>

1. <span data-ttu-id="29d7a-305">搜索 " **磁盘清理** " 并打开此应用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-305">Search for **Disk Cleanup** and open this app.</span></span>
2. <span data-ttu-id="29d7a-306">在 " **要删除的文件**" 下，选择要删除的文件。</span><span class="sxs-lookup"><span data-stu-id="29d7a-306">Under **Files to delete**, select the files you wish to delete.</span></span> 
3. <span data-ttu-id="29d7a-307">同时选择 " **清理系统文件**"。</span><span class="sxs-lookup"><span data-stu-id="29d7a-307">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="29d7a-308">完成并验证</span><span class="sxs-lookup"><span data-stu-id="29d7a-308">Complete and verify</span></span>

1. <span data-ttu-id="29d7a-309">扫描并安装所有 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="29d7a-309">Scan for and install all Windows Updates.</span></span>
2. <span data-ttu-id="29d7a-310">更新组策略</span><span class="sxs-lookup"><span data-stu-id="29d7a-310">Update Group Policy</span></span>
    1. <span data-ttu-id="29d7a-311">在提升的命令提示符处，输入 **gpupdate/force/boot/wait： 0**。</span><span class="sxs-lookup"><span data-stu-id="29d7a-311">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
3. <span data-ttu-id="29d7a-312">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="29d7a-312">Reboot the device.</span></span>
4. <span data-ttu-id="29d7a-313">验证任务栏应用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-313">Verify taskbar apps.</span></span>
    - <span data-ttu-id="29d7a-314">Connect 应用</span><span class="sxs-lookup"><span data-stu-id="29d7a-314">Connect App</span></span>
    - <span data-ttu-id="29d7a-315">锁定图标</span><span class="sxs-lookup"><span data-stu-id="29d7a-315">Lock Icon</span></span>
    - <span data-ttu-id="29d7a-316">截图和草图</span><span class="sxs-lookup"><span data-stu-id="29d7a-316">Snip & Sketch</span></span>
    - <span data-ttu-id="29d7a-317">团队 (（如果适用）) </span><span class="sxs-lookup"><span data-stu-id="29d7a-317">Teams (if applicable)</span></span>
    - <span data-ttu-id="29d7a-318">Office 应用 (（如果适用）) </span><span class="sxs-lookup"><span data-stu-id="29d7a-318">Office Apps (if applicable)</span></span>
    - <span data-ttu-id="29d7a-319">Surface 应用</span><span class="sxs-lookup"><span data-stu-id="29d7a-319">Surface App</span></span>
    - <span data-ttu-id="29d7a-320">白板</span><span class="sxs-lookup"><span data-stu-id="29d7a-320">Whiteboard</span></span>
5. <span data-ttu-id="29d7a-321">验证状态检测。</span><span class="sxs-lookup"><span data-stu-id="29d7a-321">Verify presence detection.</span></span>
    - <span data-ttu-id="29d7a-322">状态检测将在系统托盘中显示为绿色图标</span><span class="sxs-lookup"><span data-stu-id="29d7a-322">Presence detection will be a green icon in the system tray</span></span>
6. <span data-ttu-id="29d7a-323">验证投影到此电脑已通过 Connect 应用启用 (应用程序无需在连接) 之前运行。</span><span class="sxs-lookup"><span data-stu-id="29d7a-323">Verify projecting to this PC is enabled with the Connect App (the application does not need to be running before connecting).</span></span>
7. <span data-ttu-id="29d7a-324">验证电源和睡眠设置。</span><span class="sxs-lookup"><span data-stu-id="29d7a-324">Verify power and sleep settings.</span></span>
    - <span data-ttu-id="29d7a-325">屏幕保护程序：15分钟，设置为 (none) ，Mystify 或空白;选中 "需要密码的复选框"</span><span class="sxs-lookup"><span data-stu-id="29d7a-325">Screen Saver: 15 minutes, set to (none), Mystify or Blank; check box for requiring password is checked</span></span>
    - <span data-ttu-id="29d7a-326">屏幕： **2 小时后关闭。**</span><span class="sxs-lookup"><span data-stu-id="29d7a-326">Screen: **Turn off after 2 hours.**</span></span>
    - <span data-ttu-id="29d7a-327">PC：  **4 小时后关闭。**</span><span class="sxs-lookup"><span data-stu-id="29d7a-327">PC:  **Turn off after 4 hours.**</span></span>
8. <span data-ttu-id="29d7a-328">验证 Windows Hello 是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="29d7a-328">Verify Windows Hello is working.</span></span>
9. <span data-ttu-id="29d7a-329">验证同步您的设置已禁用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-329">Verify sync your settings is disabled.</span></span>
10. <span data-ttu-id="29d7a-330">验证启动应用。</span><span class="sxs-lookup"><span data-stu-id="29d7a-330">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="29d7a-331">安装和配置 Windows 10 之后，Surface Hub 2 可以像管理任何其他 Windows 10 设备一样进行管理。</span><span class="sxs-lookup"><span data-stu-id="29d7a-331">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="29d7a-332">相关主题</span><span class="sxs-lookup"><span data-stu-id="29d7a-332">Related topics</span></span>

[<span data-ttu-id="29d7a-333">迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版</span><span class="sxs-lookup"><span data-stu-id="29d7a-333">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)

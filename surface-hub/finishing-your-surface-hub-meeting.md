---
title: 结束会话 - 结束 Surface Hub 会议
description: 要结束 Surface Hub 会议，请点击“结束会话”。 Surface Hub 会清除应用程序状态、操作系统状态和用户界面，以便 Surface Hub 为下次会议做好准备。
keywords: 我已完成, 结束 Surface Hub 会议, 完成 Surface Hub 会议, 清除 Surface Hub 会议
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: b18bc4b15b8a3925aeecdd9999b09b61011d1db5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831844"
---
# <span data-ttu-id="9e466-105">使用“结束会话”结束 Surface Hub 会议</span><span class="sxs-lookup"><span data-stu-id="9e466-105">End a Surface Hub meeting with End session</span></span>
<span data-ttu-id="9e466-106">Surface Hub 是用于协作的设备，在会议室中由不同组的用户使用。</span><span class="sxs-lookup"><span data-stu-id="9e466-106">Surface Hub is a collaboration device designed to be used in meeting spaces by different groups of people.</span></span> <span data-ttu-id="9e466-107">在会议结束后，用户可点击**结束会话**，清理任何敏感数据，并为下一场会议准备好设备。</span><span class="sxs-lookup"><span data-stu-id="9e466-107">At the end of a meeting, users can tap **End session** to clean up any sensitive data and prepare the device for the next meeting.</span></span> <span data-ttu-id="9e466-108">Surface Hub 可清理或重置以下状态：</span><span class="sxs-lookup"><span data-stu-id="9e466-108">Surface Hub will clean up, or reset, the following states:</span></span>
- <span data-ttu-id="9e466-109">应用程序</span><span class="sxs-lookup"><span data-stu-id="9e466-109">Applications</span></span>
- <span data-ttu-id="9e466-110">操作系统</span><span class="sxs-lookup"><span data-stu-id="9e466-110">Operating system</span></span>
- <span data-ttu-id="9e466-111">用户界面</span><span class="sxs-lookup"><span data-stu-id="9e466-111">User interface</span></span>

<span data-ttu-id="9e466-112">本主题介绍了**结束会话**为其中每一种状态重置哪些内容。</span><span class="sxs-lookup"><span data-stu-id="9e466-112">This topic explains what **End session** resets for each of these states.</span></span>

## <span data-ttu-id="9e466-113">应用程序</span><span class="sxs-lookup"><span data-stu-id="9e466-113">Applications</span></span>
<span data-ttu-id="9e466-114">当你在 Surface Hub 上启动应用时，它们存储在内存中，并且数据存储在应用程序级别上。</span><span class="sxs-lookup"><span data-stu-id="9e466-114">When you start apps on Surface Hub, they are stored in memory and data is stored at the application level.</span></span> <span data-ttu-id="9e466-115">在该会话（或会议）期间数据对所有用户都可用，直到删除或覆盖数据。</span><span class="sxs-lookup"><span data-stu-id="9e466-115">Data is available to all users during that session (or meeting) until date is removed or overwritten.</span></span> <span data-ttu-id="9e466-116">当选择**结束会话**时，通过关闭应用程序、删除浏览器历史记录、重置应用程序和删除 Skype 日志来清除 Surface Hub 应用程序状态。</span><span class="sxs-lookup"><span data-stu-id="9e466-116">When **End session** is selected, Surface Hub application state is cleared out by closing applications, deleting browser history, resetting applications, and removing Skype logs.</span></span>

### <span data-ttu-id="9e466-117">关闭应用程序</span><span class="sxs-lookup"><span data-stu-id="9e466-117">Close applications</span></span>
<span data-ttu-id="9e466-118">Surface Hub 会关闭所有可见窗口，包括 Win32 和通用 Windows 平台 (UWP) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e466-118">Surface Hub closes all visible windows, including Win32 and Universal Windows Platform (UWP) applications.</span></span> <span data-ttu-id="9e466-119">应用程序关闭阶段会使用多任务视图查询可见窗口。</span><span class="sxs-lookup"><span data-stu-id="9e466-119">The application close stage uses the multitasking view to query the visible windows.</span></span> <span data-ttu-id="9e466-120">不在特定时间范围内关闭的 Win32 窗口将使用 **TerminateProcess** 关闭。</span><span class="sxs-lookup"><span data-stu-id="9e466-120">Win32 windows that do not close within a certain timeframe are closed using **TerminateProcess**.</span></span> 
   
### <span data-ttu-id="9e466-121">删除浏览器历史记录</span><span class="sxs-lookup"><span data-stu-id="9e466-121">Delete browser history</span></span>
<span data-ttu-id="9e466-122">Surface Hub 使用 Edge 中的删除浏览器历史记录 (DBH) 清除 Edge 历史记录和缓存的数据。</span><span class="sxs-lookup"><span data-stu-id="9e466-122">Surface Hub uses Delete Browser History (DBH) in Edge to clear Edge history and cached data.</span></span> <span data-ttu-id="9e466-123">这类似于用户可以手动清除其浏览器历史记录的功能，但**结束会话**还确保在下次会话或会议开始前清除应用程序状态并删除数据。</span><span class="sxs-lookup"><span data-stu-id="9e466-123">This is similar to how a user can clear out their browser history manually, but **End session** also ensures that application states are cleared and data is removed before the next session, or meeting, starts.</span></span> 
 
### <span data-ttu-id="9e466-124">重置应用程序</span><span class="sxs-lookup"><span data-stu-id="9e466-124">Reset applications</span></span>
<span data-ttu-id="9e466-125">**结束会话**会重置安装在 Surface Hub 上的每个应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="9e466-125">**End session** resets the state of each application that is installed on the Surface Hub.</span></span> <span data-ttu-id="9e466-126">重置应用程序可清除所有后台任务、应用程序数据、通知和用户同意对话框。</span><span class="sxs-lookup"><span data-stu-id="9e466-126">Resetting an application clears all background tasks, application data, notifications, and user consent dialogs.</span></span> <span data-ttu-id="9e466-127">应用程序将返回到其首次运行状态，以供使用 Surface Hub 的后续用户使用。</span><span class="sxs-lookup"><span data-stu-id="9e466-127">Applications are returned to their first-run state for the next people that use Surface Hub.</span></span>  
 
### <span data-ttu-id="9e466-128">删除 Skype 日志</span><span class="sxs-lookup"><span data-stu-id="9e466-128">Remove Skype logs</span></span>
<span data-ttu-id="9e466-129">Skype 不会在 Surface Hub 上存储个人身份信息。</span><span class="sxs-lookup"><span data-stu-id="9e466-129">Skype does not store personally-identifiable information on Surface Hub.</span></span> <span data-ttu-id="9e466-130">信息存储在 Skype 服务中，以符合现有 Skype for Business 指南。</span><span class="sxs-lookup"><span data-stu-id="9e466-130">Information is stored in the Skype service to meet existing Skype for Business guidance.</span></span> <span data-ttu-id="9e466-131">本地 Skype 日志记录信息是在选择**结束会话**时删除的唯一数据。</span><span class="sxs-lookup"><span data-stu-id="9e466-131">Local Skype logging information is the only data removed when **End session** is selected.</span></span> <span data-ttu-id="9e466-132">这包括统一通信客户端平台 (UCCP) 日志和媒体日志。</span><span class="sxs-lookup"><span data-stu-id="9e466-132">This includes Unified Communications Client Platform (UCCP) logs and media logs.</span></span>   

## <span data-ttu-id="9e466-133">操作系统</span><span class="sxs-lookup"><span data-stu-id="9e466-133">Operating System</span></span>
<span data-ttu-id="9e466-134">操作系统会托管每次 Surface Hub 会议后需要清除的关于会话状态的各种信息。</span><span class="sxs-lookup"><span data-stu-id="9e466-134">The operating system hosts a variety of information about the state of the sessions that needs to be cleared after each Surface Hub meeting.</span></span> 

### <span data-ttu-id="9e466-135">文件系统</span><span class="sxs-lookup"><span data-stu-id="9e466-135">File System</span></span>
<span data-ttu-id="9e466-136">与会者有权访问 Surface Hub 上的一组受限目录。</span><span class="sxs-lookup"><span data-stu-id="9e466-136">Meeting attendees have access to a limited set of directories on the Surface Hub.</span></span> <span data-ttu-id="9e466-137">当选择**结束会话**时，Surface Hub 会清除以下目录：</span><span class="sxs-lookup"><span data-stu-id="9e466-137">When **End session** is selected, Surface Hub clears these directories:</span></span><br>
- <span data-ttu-id="9e466-138">音乐</span><span class="sxs-lookup"><span data-stu-id="9e466-138">Music</span></span>
- <span data-ttu-id="9e466-139">视频</span><span class="sxs-lookup"><span data-stu-id="9e466-139">Videos</span></span>
- <span data-ttu-id="9e466-140">文档</span><span class="sxs-lookup"><span data-stu-id="9e466-140">Documents</span></span>
- <span data-ttu-id="9e466-141">图片</span><span class="sxs-lookup"><span data-stu-id="9e466-141">Pictures</span></span>
- <span data-ttu-id="9e466-142">下载</span><span class="sxs-lookup"><span data-stu-id="9e466-142">Downloads</span></span>

<span data-ttu-id="9e466-143">Surface Hub 也会清除以下目录，因为许多应用程序通常会写入它们：</span><span class="sxs-lookup"><span data-stu-id="9e466-143">Surface Hub also clears these directories, since many applications often write to them:</span></span>
- <span data-ttu-id="9e466-144">桌面</span><span class="sxs-lookup"><span data-stu-id="9e466-144">Desktop</span></span>
- <span data-ttu-id="9e466-145">收藏夹</span><span class="sxs-lookup"><span data-stu-id="9e466-145">Favorites</span></span>
- <span data-ttu-id="9e466-146">最近</span><span class="sxs-lookup"><span data-stu-id="9e466-146">Recent</span></span>
- <span data-ttu-id="9e466-147">公用文档</span><span class="sxs-lookup"><span data-stu-id="9e466-147">Public Documents</span></span>
- <span data-ttu-id="9e466-148">公用音乐</span><span class="sxs-lookup"><span data-stu-id="9e466-148">Public Music</span></span>
- <span data-ttu-id="9e466-149">公用视频</span><span class="sxs-lookup"><span data-stu-id="9e466-149">Public Videos</span></span>
- <span data-ttu-id="9e466-150">公用下载</span><span class="sxs-lookup"><span data-stu-id="9e466-150">Public Downloads</span></span>

### <span data-ttu-id="9e466-151">凭据</span><span class="sxs-lookup"><span data-stu-id="9e466-151">Credentials</span></span>
<span data-ttu-id="9e466-152">点击**结束会话**时，将清除存储在 **TokenBroker**、**PasswordVault** 或**凭据管理器**中的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="9e466-152">User credentials that are stored in **TokenBroker**, **PasswordVault**, or **Credential Manager** are cleared when you tap **End session**.</span></span>

## <span data-ttu-id="9e466-153">用户界面</span><span class="sxs-lookup"><span data-stu-id="9e466-153">User interface</span></span>
<span data-ttu-id="9e466-154">当选择**结束会话**时，用户界面 (UI) 设置将返回到其默认值。</span><span class="sxs-lookup"><span data-stu-id="9e466-154">User interface (UI) settings are returned to their default values when **End session** is selected.</span></span> 

### <span data-ttu-id="9e466-155">UI 项目</span><span class="sxs-lookup"><span data-stu-id="9e466-155">UI items</span></span>
- <span data-ttu-id="9e466-156">将“快速操作”重置为默认状态</span><span class="sxs-lookup"><span data-stu-id="9e466-156">Reset Quick Actions to default state</span></span>
- <span data-ttu-id="9e466-157">清除 Toast 通知</span><span class="sxs-lookup"><span data-stu-id="9e466-157">Clear Toast notifications</span></span>
- <span data-ttu-id="9e466-158">重置音量级别</span><span class="sxs-lookup"><span data-stu-id="9e466-158">Reset volume levels</span></span>
- <span data-ttu-id="9e466-159">重置边栏宽度</span><span class="sxs-lookup"><span data-stu-id="9e466-159">Reset sidebar width</span></span>
- <span data-ttu-id="9e466-160">重置平板模式布局</span><span class="sxs-lookup"><span data-stu-id="9e466-160">Reset tablet mode layout</span></span>
- <span data-ttu-id="9e466-161">将用户从 Office 365 会议和文件中注销</span><span class="sxs-lookup"><span data-stu-id="9e466-161">Sign user out of Office 365 meetings and files</span></span>

### <span data-ttu-id="9e466-162">辅助功能</span><span class="sxs-lookup"><span data-stu-id="9e466-162">Accessibility</span></span>
<span data-ttu-id="9e466-163">当选择**结束会话**时，辅助功能和应用将返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="9e466-163">Accessibility features and apps are returned to default settings when **End session** is selected.</span></span>
- <span data-ttu-id="9e466-164">筛选键</span><span class="sxs-lookup"><span data-stu-id="9e466-164">Filter keys</span></span>
- <span data-ttu-id="9e466-165">高对比度</span><span class="sxs-lookup"><span data-stu-id="9e466-165">High contrast</span></span>
- <span data-ttu-id="9e466-166">粘滞键</span><span class="sxs-lookup"><span data-stu-id="9e466-166">Sticky keys</span></span>
- <span data-ttu-id="9e466-167">切换键</span><span class="sxs-lookup"><span data-stu-id="9e466-167">Toggle keys</span></span>
- <span data-ttu-id="9e466-168">鼠标键</span><span class="sxs-lookup"><span data-stu-id="9e466-168">Mouse keys</span></span>
- <span data-ttu-id="9e466-169">放大镜</span><span class="sxs-lookup"><span data-stu-id="9e466-169">Magnifier</span></span>
- <span data-ttu-id="9e466-170">讲述人</span><span class="sxs-lookup"><span data-stu-id="9e466-170">Narrator</span></span>

### <span data-ttu-id="9e466-171">剪贴板</span><span class="sxs-lookup"><span data-stu-id="9e466-171">Clipboard</span></span>
<span data-ttu-id="9e466-172">将清除剪贴板以删除曾在会话期间复制到剪贴板的数据。</span><span class="sxs-lookup"><span data-stu-id="9e466-172">The clipboard is cleared to remove data that was copied to the clipboard during the session.</span></span> 

## <span data-ttu-id="9e466-173">常见问题</span><span class="sxs-lookup"><span data-stu-id="9e466-173">Frequently asked questions</span></span>
**<span data-ttu-id="9e466-174">如果我在会议结束时忘记点击“结束会话”，而其他人之后使用了 Surface Hub，会怎么样？</span><span class="sxs-lookup"><span data-stu-id="9e466-174">What happens if I forget to tap End session at the end of a meeting, and someone else uses the Surface Hub later?</span></span>**<br>
<span data-ttu-id="9e466-175">在用户点击**结束会话**后，Surface Hub 仅清理会议内容。</span><span class="sxs-lookup"><span data-stu-id="9e466-175">Surface Hub only cleans up meeting content when users tap **End session**.</span></span> <span data-ttu-id="9e466-176">如果不点击**结束会话**即退出会议，一段时间后，设备将返回欢迎屏幕。</span><span class="sxs-lookup"><span data-stu-id="9e466-176">If you leave the meeting without tapping **End session**, the device will return to the welcome screen after some time.</span></span> <span data-ttu-id="9e466-177">在欢迎屏幕中，用户可选择恢复之前的会话或启动新会话。</span><span class="sxs-lookup"><span data-stu-id="9e466-177">From the welcome screen, users have the option to resume the previous session or start a new one.</span></span> <span data-ttu-id="9e466-178">如果未按下**结束会话**，也可以禁用恢复会话的功能。</span><span class="sxs-lookup"><span data-stu-id="9e466-178">You can also disable the ability to resume a session if **End session** is not pressed.</span></span>

**<span data-ttu-id="9e466-179">文档是否可恢复？</span><span class="sxs-lookup"><span data-stu-id="9e466-179">Are documents recoverable?</span></span>**<br> <span data-ttu-id="9e466-180">在选择**结束会话**时从硬盘驱动器中删除文件和从硬盘驱动器中删除任何其他文件一样。</span><span class="sxs-lookup"><span data-stu-id="9e466-180">Removing files from the hard drive when **End session** is selected is just like any other file deletion from a hard disk drive.</span></span> <span data-ttu-id="9e466-181">第三方软件可能能够从硬盘驱动器中恢复数据，但文件恢复功能在 Surface Hub 上不受支持。</span><span class="sxs-lookup"><span data-stu-id="9e466-181">Third-party software might be able to recover data from the hard disk drive, but file recovery is not a supported feature on Surface Hub.</span></span> <span data-ttu-id="9e466-182">若要防止数据丢失，请在退出会议前始终保存所需数据。</span><span class="sxs-lookup"><span data-stu-id="9e466-182">To prevent data loss, always save the data you need before leaving a meeting.</span></span>

**<span data-ttu-id="9e466-183">“结束会话”的清除操作是否符合美国国防部资料摧毁标准：DoD 5220.22-M？</span><span class="sxs-lookup"><span data-stu-id="9e466-183">Do the clean-up actions from End session comply with the US Department of Defense clearing and sanitizing standard: DoD 5220.22-M?</span></span>**<br>
<span data-ttu-id="9e466-184">不符合。</span><span class="sxs-lookup"><span data-stu-id="9e466-184">No.</span></span> <span data-ttu-id="9e466-185">当前，**结束会话**的清除操作不符合此标准。</span><span class="sxs-lookup"><span data-stu-id="9e466-185">Currently, the clean-up actions from **End session** do not comply with this standard.</span></span>  
  

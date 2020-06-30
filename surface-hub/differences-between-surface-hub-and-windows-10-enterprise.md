---
title: 操作系统基本知识 (Surface Hub)
description: 本主题介绍 Windows 10 团队操作系统的独特方面以及它与 Windows 10 企业的不同之处。
keywords: 更改历史记录
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 92a634e897d3e0c9163fe092aaf7992f625de991
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830988"
---
# <span data-ttu-id="c63be-104">操作系统基本知识 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="c63be-104">Operating system essentials (Surface Hub)</span></span>

<span data-ttu-id="c63be-105">Surface Hub 操作系统 Windows 10 协同版基于 Windows 10 企业版，提供了对企业管理、安全和其他功能的丰富支持。</span><span class="sxs-lookup"><span data-stu-id="c63be-105">The Surface Hub operating system, Windows 10 Team, is based on Windows 10 Enterprise, providing rich support for enterprise management, security, and other features.</span></span> <span data-ttu-id="c63be-106">但是，二者之间存在着重要差异。</span><span class="sxs-lookup"><span data-stu-id="c63be-106">However, there are important differences between them.</span></span> <span data-ttu-id="c63be-107">企业版针对电脑设计，而 Windows 10 协同版针对大屏幕和会议室进行全新设计。</span><span class="sxs-lookup"><span data-stu-id="c63be-107">While the Enterprise edition is designed for PCs, Windows 10 Team is designed from the ground up for large screens and meeting rooms.</span></span> <span data-ttu-id="c63be-108">在评估 Surface Hub 的安全和管理要求时，最好将其视为新的操作系统。</span><span class="sxs-lookup"><span data-stu-id="c63be-108">When you evaluate security and management requirements for Surface Hub, it's best to consider it as a new operating system.</span></span> <span data-ttu-id="c63be-109">本文旨在帮助突出显示 Surface Hub 上的 Windows 10 协同版和 Windows 10 企业版之间的关键差异，以及这些差异对你的组织的影响。</span><span class="sxs-lookup"><span data-stu-id="c63be-109">This article is designed to help highlight the key differences between Windows 10 Team on Surface Hub and Windows 10 Enterprise, and what the differences mean for your organization.</span></span>

## <span data-ttu-id="c63be-110">用户界面</span><span class="sxs-lookup"><span data-stu-id="c63be-110">User interface</span></span>

### <span data-ttu-id="c63be-111">Shell（操作系统用户界面）</span><span class="sxs-lookup"><span data-stu-id="c63be-111">Shell (OS user interface)</span></span>

<span data-ttu-id="c63be-112">Surface Hub 的 Shell 针对大屏幕进行了全新设计，并优化了触摸功能。</span><span class="sxs-lookup"><span data-stu-id="c63be-112">The Surface Hub's shell is designed from the ground up to be large screen and touch optimized.</span></span> <span data-ttu-id="c63be-113">它不会使用与 Windows 10 企业版相同的 Shell。</span><span class="sxs-lookup"><span data-stu-id="c63be-113">It doesn't use the same shell as Windows 10 Enterprise.</span></span>

*<span data-ttu-id="c63be-114">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-114">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-115">与 Windows 10 企业版 Shell 中的控件相关的设置不适用于 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-115">Settings related to controls in the Windows 10 Enterprise shell don't apply for Surface Hub.</span></span>

### <span data-ttu-id="c63be-116">锁屏界面和屏幕保护程序</span><span class="sxs-lookup"><span data-stu-id="c63be-116">Lock screen and screensaver</span></span>

<span data-ttu-id="c63be-117">Surface Hub 没有锁屏界面或屏幕保护程序，但它有一个类似功能（称为欢迎屏幕）。</span><span class="sxs-lookup"><span data-stu-id="c63be-117">Surface Hub doesn't have a lock screen or a screen saver, but it has a similar feature called the welcome screen.</span></span> <span data-ttu-id="c63be-118">欢迎屏幕显示设备帐户日历中的计划会议和访问 Surface Hub 常用应用（Skype for Business、白板和 Connect）的简单入口点。</span><span class="sxs-lookup"><span data-stu-id="c63be-118">The welcome screen shows scheduled meetings from the device account's calendar, and easy entry points to the Surface Hub's top apps - Skype for Business, Whiteboard, and Connect.</span></span>

*<span data-ttu-id="c63be-119">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-119">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-120">锁屏界面、屏幕超时和屏幕保护程序的设置不适用于 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-120">Settings for lock screen, screen timeout, and screen saver don't apply for Surface Hub.</span></span>

### <span data-ttu-id="c63be-121">用户登录</span><span class="sxs-lookup"><span data-stu-id="c63be-121">User sign-in</span></span>

<span data-ttu-id="c63be-122">Surface Hub 设计用于公共场所，例如会议室。</span><span class="sxs-lookup"><span data-stu-id="c63be-122">Surface Hub is designed to be used in communal spaces, such as meeting rooms.</span></span> <span data-ttu-id="c63be-123">与 Windows 电脑不同，任何人都可以访问和使用 Surface Hub，无需用户登录。</span><span class="sxs-lookup"><span data-stu-id="c63be-123">Unlike Windows PCs, anyone can walk up and use a Surface Hub without requiring a user to sign in.</span></span> <span data-ttu-id="c63be-124">为了支持此社区功能，Surface Hub 不支持以与 Windows 10 企业版相同的方式进行 Windows 登录（如让用户登录到操作系统并使用操作系统中的这些凭据）。</span><span class="sxs-lookup"><span data-stu-id="c63be-124">To enable this communal functionality, Surface Hub does not support Windows sign-in the same way that Windows 10 Enterprise does (e.g., signing in a user to the OS and using those credentials throughout the OS).</span></span> <span data-ttu-id="c63be-125">相反，始终是本地、自动登录的低权限用户登录 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-125">Instead, there is always a local, auto signed-in, low-privilege user signed in to the Surface Hub.</span></span> <span data-ttu-id="c63be-126">它不支持登录任何其他用户，包括管理员用户（例如，当管理员登录时，他们不会登录到操作系统）。</span><span class="sxs-lookup"><span data-stu-id="c63be-126">It doesn't support signing in any additional users, including admin users (e.g., when an admin signs in, they are not signed in to the OS).</span></span>

<span data-ttu-id="c63be-127">用户可以登录到 Surface Hub，但他们无法登录到操作系统。</span><span class="sxs-lookup"><span data-stu-id="c63be-127">Users can sign in to a Surface Hub, but they will not be signed in to the OS.</span></span> <span data-ttu-id="c63be-128">例如，当用户登录到“应用”或“我的会议和文件”时，他们只登录到应用或服务，而不是操作系统。</span><span class="sxs-lookup"><span data-stu-id="c63be-128">For example, when a user signs in to Apps or My Meetings and Files, the users is signed in only to the apps or services, not to the OS.</span></span> <span data-ttu-id="c63be-129">因此，登录用户可以检索其云文件和存储在云中的个人会议，并且这些凭据将会在**结束会话**激活时被丢弃。</span><span class="sxs-lookup"><span data-stu-id="c63be-129">As a result, the signed-in user is able to retrieve their cloud files and personal meetings stored in the cloud, and these credentials are discarded when **End session** is activated.</span></span>


*<span data-ttu-id="c63be-130">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-130">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-131">通常情况下，Surface Hub 使用锁定功能（而不是用户访问控制）以强制实施安全性。</span><span class="sxs-lookup"><span data-stu-id="c63be-131">Generally, Surface Hub uses lockdown features rather than user access control to enforce security.</span></span> <span data-ttu-id="c63be-132">与密码要求、交互式登录、用户帐户和访问控制相关的策略不适用于 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-132">Policies related to password requirements, interactive logon, user accounts, and access control don't apply for Surface Hub.</span></span>

### <span data-ttu-id="c63be-133">保存和浏览文件</span><span class="sxs-lookup"><span data-stu-id="c63be-133">Saving and browsing files</span></span>

<span data-ttu-id="c63be-134">用户有权访问 Surface Hub 上的一组受限目录：</span><span class="sxs-lookup"><span data-stu-id="c63be-134">Users have access to a limited set of directories on the Surface Hub:</span></span>
- <span data-ttu-id="c63be-135">音乐</span><span class="sxs-lookup"><span data-stu-id="c63be-135">Music</span></span>
- <span data-ttu-id="c63be-136">视频</span><span class="sxs-lookup"><span data-stu-id="c63be-136">Videos</span></span>
- <span data-ttu-id="c63be-137">文档</span><span class="sxs-lookup"><span data-stu-id="c63be-137">Documents</span></span>
- <span data-ttu-id="c63be-138">图片</span><span class="sxs-lookup"><span data-stu-id="c63be-138">Pictures</span></span>
- <span data-ttu-id="c63be-139">下载</span><span class="sxs-lookup"><span data-stu-id="c63be-139">Downloads</span></span>

<span data-ttu-id="c63be-140">当用户按下**结束会话**时，以本地方式保存在这些目录中的文件会删除。</span><span class="sxs-lookup"><span data-stu-id="c63be-140">Files saved locally in these directories are deleted when users press **End session**.</span></span> <span data-ttu-id="c63be-141">若要保存在会议期间创建的内容，用户应将文件保存到 U 盘或 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="c63be-141">To save content created during a meeting, users should save files to a USB drive or to OneDrive.</span></span>

*<span data-ttu-id="c63be-142">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-142">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-143">与访问权限和文件及文件夹的所有权相关的策略不适用于 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-143">Policies related to access permissions and ownership of files and folders don't apply for Surface Hub.</span></span> <span data-ttu-id="c63be-144">用户不能浏览文件，也不能将文件保存到系统目录和网络文件夹。</span><span class="sxs-lookup"><span data-stu-id="c63be-144">Users can't browse and save files to system directories and network folders.</span></span>

## <span data-ttu-id="c63be-145">应用程序</span><span class="sxs-lookup"><span data-stu-id="c63be-145">Applications</span></span>

### <span data-ttu-id="c63be-146">默认应用程序</span><span class="sxs-lookup"><span data-stu-id="c63be-146">Default applications</span></span>

<span data-ttu-id="c63be-147">除少数情况外，Surface Hub 上的默认通用 Windows 平台 (UWP) 应用也可用于 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="c63be-147">With few exceptions, the default Universal Windows Platform (UWP) apps on Surface Hub are also available on Windows 10 PCs.</span></span>

<span data-ttu-id="c63be-148">在 Surface Hub 上预安装的 UWP 应用：</span><span class="sxs-lookup"><span data-stu-id="c63be-148">UWP apps pre-installed on Surface Hub:</span></span>
- <span data-ttu-id="c63be-149">闹钟和时钟</span><span class="sxs-lookup"><span data-stu-id="c63be-149">Alarms & Clock</span></span>
- <span data-ttu-id="c63be-150">计算器</span><span class="sxs-lookup"><span data-stu-id="c63be-150">Calculator</span></span>
- <span data-ttu-id="c63be-151">Connect</span><span class="sxs-lookup"><span data-stu-id="c63be-151">Connect</span></span>
- <span data-ttu-id="c63be-152">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="c63be-152">Excel Mobile</span></span>
- <span data-ttu-id="c63be-153">反馈中心</span><span class="sxs-lookup"><span data-stu-id="c63be-153">Feedback Hub</span></span>
- <span data-ttu-id="c63be-154">文件资源管理器\*</span><span class="sxs-lookup"><span data-stu-id="c63be-154">File Explorer\*</span></span>
- <span data-ttu-id="c63be-155">入门</span><span class="sxs-lookup"><span data-stu-id="c63be-155">Get Started</span></span>
- <span data-ttu-id="c63be-156">地图</span><span class="sxs-lookup"><span data-stu-id="c63be-156">Maps</span></span>
- <span data-ttu-id="c63be-157">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c63be-157">Microsoft Edge</span></span>
- <span data-ttu-id="c63be-158">Microsoft Power BI</span><span class="sxs-lookup"><span data-stu-id="c63be-158">Microsoft Power BI</span></span>
- <span data-ttu-id="c63be-159">OneDrive</span><span class="sxs-lookup"><span data-stu-id="c63be-159">OneDrive</span></span>
- <span data-ttu-id="c63be-160">照片</span><span class="sxs-lookup"><span data-stu-id="c63be-160">Photos</span></span>
- <span data-ttu-id="c63be-161">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="c63be-161">PowerPoint Mobile</span></span>
- <span data-ttu-id="c63be-162">设置\*</span><span class="sxs-lookup"><span data-stu-id="c63be-162">Settings\*</span></span>
- <span data-ttu-id="c63be-163">Skype for Business\*</span><span class="sxs-lookup"><span data-stu-id="c63be-163">Skype for Business\*</span></span>
- <span data-ttu-id="c63be-164">应用商店</span><span class="sxs-lookup"><span data-stu-id="c63be-164">Store</span></span>
- <span data-ttu-id="c63be-165">白板\*</span><span class="sxs-lookup"><span data-stu-id="c63be-165">Whiteboard\*</span></span>
- <span data-ttu-id="c63be-166">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="c63be-166">Word Mobile</span></span>

*<span data-ttu-id="c63be-167">带有星号 (&ast;) 的应用专用于 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="c63be-167">Apps with an asterisk (&ast;) are unique to Surface Hub</span></span>*

*<span data-ttu-id="c63be-168">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-168">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-169">使用适用于 Windows 10 企业版的指南，确定 Surface Hub 上的默认应用的功能和网络要求。</span><span class="sxs-lookup"><span data-stu-id="c63be-169">Use guidelines for Windows 10 Enterprise to determine the features and network requirements for default apps on the Surface Hub.</span></span>

### <span data-ttu-id="c63be-170">安装应用、驱动程序和服务</span><span class="sxs-lookup"><span data-stu-id="c63be-170">Installing apps, drivers, and services</span></span>

<span data-ttu-id="c63be-171">若要帮助保留该设备的类似设备性质，Surface Hub 仅支持安装通用 Windows 平台 (UWP) 应用，不支持安装经典 Win32 应用、服务和驱动程序。</span><span class="sxs-lookup"><span data-stu-id="c63be-171">To help preserve the appliance-like nature of the device, Surface Hub only supports installing Universal Windows Platform (UWP) apps, and does not support installing classic Win32 apps, services and drivers.</span></span> <span data-ttu-id="c63be-172">此外，只有管理员有权安装 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="c63be-172">Furthermore, only admins have access to install UWP apps.</span></span>

*<span data-ttu-id="c63be-173">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-173">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-174">员工只能使用管理员已经安装的应用，这有助于缓解意外使用风险。</span><span class="sxs-lookup"><span data-stu-id="c63be-174">Employees can only use the apps that have been installed by admins, helping mitigate against unintended use.</span></span> <span data-ttu-id="c63be-175">Surface Hub 不支持安装大多数传统电脑管理和监视工具所需的 Win32 代理。</span><span class="sxs-lookup"><span data-stu-id="c63be-175">Surface Hub doesn't support installing Win32 agents required by most traditional PC management and monitoring tools.</span></span>

## <span data-ttu-id="c63be-176">安全和锁定</span><span class="sxs-lookup"><span data-stu-id="c63be-176">Security and lockdown</span></span>

<span data-ttu-id="c63be-177">要在公共场所（如会议室）使用的 Surface Hub 的自定义操作系统，可实现在 Windows 10 中提供的许多安全和锁定功能。</span><span class="sxs-lookup"><span data-stu-id="c63be-177">For Surface Hub to be used in communal spaces, such as meeting rooms, its custom OS implements many of the security and lockdown features available in Windows 10.</span></span>

<span data-ttu-id="c63be-178">Surface Hub 可实现这些 Windows 10 安全功能：</span><span class="sxs-lookup"><span data-stu-id="c63be-178">Surface Hub implements these Windows 10 security features:</span></span>
- [<span data-ttu-id="c63be-179">UEFI 安全启动</span><span class="sxs-lookup"><span data-stu-id="c63be-179">UEFI Secure Boot</span></span>](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)
- [<span data-ttu-id="c63be-180">用户模式代码完整性 (UMCI) 与 Device Guard</span><span class="sxs-lookup"><span data-stu-id="c63be-180">User Mode Code Integrity (UMCI) with Device Guard</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/introduction-to-device-guard-virtualization-based-security-and-code-integrity-policies)
- [<span data-ttu-id="c63be-181">使用 AppLocker 的应用程序限制策略</span><span class="sxs-lookup"><span data-stu-id="c63be-181">Application restriction policies using AppLocker</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/applocker-overview)
- [<span data-ttu-id="c63be-182">BitLocker 驱动器加密</span><span class="sxs-lookup"><span data-stu-id="c63be-182">BitLocker Drive Encryption</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/bitlocker-overview)
- [<span data-ttu-id="c63be-183">受信任的平台模块 (TPM)</span><span class="sxs-lookup"><span data-stu-id="c63be-183">Trusted Platform Module (TPM)</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/trusted-platform-module-overview)
- [<span data-ttu-id="c63be-184">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="c63be-184">Windows Defender</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/windows-defender-in-windows-10)
- <span data-ttu-id="c63be-185">对“设置”应用的访问权限的[用户帐户控制 (UAC)](https://technet.microsoft.com/itpro/windows/keep-secure/user-account-control-overview)</span><span class="sxs-lookup"><span data-stu-id="c63be-185">[User Account Control (UAC)](https://technet.microsoft.com/itpro/windows/keep-secure/user-account-control-overview) for access to the Settings app</span></span>

<span data-ttu-id="c63be-186">这些 Surface Hub 功能提供额外安全：</span><span class="sxs-lookup"><span data-stu-id="c63be-186">These Surface Hub features provide additional security:</span></span>
- <span data-ttu-id="c63be-187">自定义 UEFI 固件</span><span class="sxs-lookup"><span data-stu-id="c63be-187">Custom UEFI firmware</span></span>
- <span data-ttu-id="c63be-188">自定义 Shell 和“开始”菜单限制设备使用会议功能</span><span class="sxs-lookup"><span data-stu-id="c63be-188">Custom shell and Start menu limits device to meeting functions</span></span>
- <span data-ttu-id="c63be-189">自定义文件资源管理器仅授予对“我的文档”下的文件和文件夹的访问权限</span><span class="sxs-lookup"><span data-stu-id="c63be-189">Custom File Explorer only grants access to files and folders under My Documents</span></span>
- <span data-ttu-id="c63be-190">自定义设置应用仅允许管理员修改设备设置</span><span class="sxs-lookup"><span data-stu-id="c63be-190">Custom Settings app only allows admins to modify device settings</span></span>
- <span data-ttu-id="c63be-191">下载高级即插即用驱动程序处于禁用状态</span><span class="sxs-lookup"><span data-stu-id="c63be-191">Downloading advanced Plug and Play drivers is disabled</span></span>

*<span data-ttu-id="c63be-192">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-192">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-193">在对 Surface Hub 执行安全评估时，考虑以下功能。</span><span class="sxs-lookup"><span data-stu-id="c63be-193">Consider these features when performing your security assessment for Surface Hub.</span></span>

## <span data-ttu-id="c63be-194">管理</span><span class="sxs-lookup"><span data-stu-id="c63be-194">Management</span></span>

### <span data-ttu-id="c63be-195">设备设置</span><span class="sxs-lookup"><span data-stu-id="c63be-195">Device settings</span></span>

<span data-ttu-id="c63be-196">设备设置可通过“设置”应用进行配置。</span><span class="sxs-lookup"><span data-stu-id="c63be-196">Device settings can be configured through the Settings app.</span></span> <span data-ttu-id="c63be-197">“设置”应用针对 Surface Hub 自定义，但还包含 Windows 10 桌面版中的许多熟悉设置。</span><span class="sxs-lookup"><span data-stu-id="c63be-197">The Settings app is customized for Surface Hub, but also contains many familiar settings from Windows 10 Desktop.</span></span> <span data-ttu-id="c63be-198">当打开“设置”应用验证管理员凭据（但这不是登录管理员）时，将显示用户帐户控制 (UAC) 提示符。</span><span class="sxs-lookup"><span data-stu-id="c63be-198">A User Accounts Control (UAC) prompt appears when opening up the Settings app to verify the admin's credentials, but this does not sign in the admin.</span></span>

*<span data-ttu-id="c63be-199">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-199">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-200">员工可以使用 Surface Hub 开展会议，但不能修改任何设备设置。</span><span class="sxs-lookup"><span data-stu-id="c63be-200">Employees can use the Surface Hub for meetings, but cannot modify any device settings.</span></span> <span data-ttu-id="c63be-201">这可确保员工仅使用设备中的会议功能（锁定功能除外）。</span><span class="sxs-lookup"><span data-stu-id="c63be-201">In addition to lockdown features, this ensures that employees only use the device for meeting functions.</span></span>

### <span data-ttu-id="c63be-202">管理功能</span><span class="sxs-lookup"><span data-stu-id="c63be-202">Administrative features</span></span>

<span data-ttu-id="c63be-203">Windows 10 企业版中的管理功能（例如 Microsoft 管理控制台、运行、命令提示符、PowerShell、注册表编辑器、事件查看器和任务管理器）在 Surface Hub 上不受支持。</span><span class="sxs-lookup"><span data-stu-id="c63be-203">The administrative features in Windows 10 Enterprise, such as the Microsoft Management Console, Run, Command Prompt, PowerShell, registry editor, event viewer, and task manager are not supported on Surface Hub.</span></span> <span data-ttu-id="c63be-204">“设置”应用包含在 Surface Hub 上本地提供的所有管理功能。</span><span class="sxs-lookup"><span data-stu-id="c63be-204">The Settings app contains all of the administrative features locally available on Surface Hub.</span></span>

*<span data-ttu-id="c63be-205">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-205">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-206">Surface Hub 的管理方式与传统电脑不同。</span><span class="sxs-lookup"><span data-stu-id="c63be-206">Surface Hubs are not managed like traditional PCs.</span></span> <span data-ttu-id="c63be-207">使用 MDM 配置设置和 OMS 以监视 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-207">Use MDM to configure settings and OMS to monitor your Surface Hub.</span></span>

### <span data-ttu-id="c63be-208">远程管理和监视</span><span class="sxs-lookup"><span data-stu-id="c63be-208">Remote management and monitoring</span></span>

<span data-ttu-id="c63be-209">Surface Hub 通过移动设备管理（MDM）解决方案（如[Microsoft Intune](https://docs.microsoft.com/intune/)和通过[Azure 监视器](https://azure.microsoft.com/services/monitor/)监视）支持远程管理。</span><span class="sxs-lookup"><span data-stu-id="c63be-209">Surface Hub supports remote management through mobile device management (MDM) solutions such as [Microsoft Intune](https://docs.microsoft.com/intune/) and monitoring through [Azure Monitor](https://azure.microsoft.com/services/monitor/).</span></span> 

*<span data-ttu-id="c63be-210">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-210">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-211">Surface Hub 不支持安装大多数传统电脑管理和监视工具（例如 System Center Operations Manager）所需的 Win32 代理。</span><span class="sxs-lookup"><span data-stu-id="c63be-211">Surface Hub doesn't support installing Win32 agents required by most traditional PC management and monitoring tools, such as System Center Operations Manager.</span></span>

### <span data-ttu-id="c63be-212">组策略</span><span class="sxs-lookup"><span data-stu-id="c63be-212">Group Policy</span></span>

<span data-ttu-id="c63be-213">Surface Hub 不支持 Windows 组策略，包括审核。</span><span class="sxs-lookup"><span data-stu-id="c63be-213">Surface Hub does not support Windows Group Policy, including auditing.</span></span> <span data-ttu-id="c63be-214">改用 MDM 将策略应用到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-214">Instead, use MDM to apply policies to your Surface Hub.</span></span> <span data-ttu-id="c63be-215">有关 MDM 的详细信息，请参阅[使用 MDM 提供程序管理设置](manage-settings-with-mdm-for-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="c63be-215">For more information about MDM, see [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md).</span></span>

*<span data-ttu-id="c63be-216">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-216">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-217">使用 MDM（而非组策略）管理 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-217">Use MDM to manage Surface Hub rather than group policy.</span></span>

### <span data-ttu-id="c63be-218">远程协助</span><span class="sxs-lookup"><span data-stu-id="c63be-218">Remote assistance</span></span>

<span data-ttu-id="c63be-219">Surface Hub 不支持远程协助。</span><span class="sxs-lookup"><span data-stu-id="c63be-219">Surface Hub does not support remote assistance.</span></span>

*<span data-ttu-id="c63be-220">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-220">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-221">与远程协助相关的策略不适用于 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-221">Policies related to remote assistance don't apply for Surface Hub.</span></span>

## <span data-ttu-id="c63be-222">网络</span><span class="sxs-lookup"><span data-stu-id="c63be-222">Network</span></span>

### <span data-ttu-id="c63be-223">域加入和 Azure Active Directory (Azure AD) 加入</span><span class="sxs-lookup"><span data-stu-id="c63be-223">Domain join and Azure Active Directory (Azure AD) join</span></span> 

<span data-ttu-id="c63be-224">Surface Hub 主要使用域加入和 Azure AD 加入提供目录备份的管理员组。</span><span class="sxs-lookup"><span data-stu-id="c63be-224">Surface Hub uses domain join and Azure AD join primarily to provide a directory-backed admin group.</span></span> <span data-ttu-id="c63be-225">用户不能使用域帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c63be-225">Users can't sign in with a domain account.</span></span> <span data-ttu-id="c63be-226">有关详细信息，请参阅[管理员组管理](admin-group-management-for-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="c63be-226">For more information, see [Admin group management](admin-group-management-for-surface-hub.md).</span></span>

*<span data-ttu-id="c63be-227">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-227">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-228">Surface Hub 加入域时，不应用组策略。</span><span class="sxs-lookup"><span data-stu-id="c63be-228">Group policies are not applied when a Surface Hub is joined to your domain.</span></span> <span data-ttu-id="c63be-229">与域成员身份相关的策略不适用于 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-229">Policies related to domain membership don't apply for Surface Hub.</span></span>

### <span data-ttu-id="c63be-230">访问域资源</span><span class="sxs-lookup"><span data-stu-id="c63be-230">Accessing domain resources</span></span>

<span data-ttu-id="c63be-231">用户可以登录到 Microsoft Edge，访问 Intranet 站点和联机资源（例如 Office 365）。</span><span class="sxs-lookup"><span data-stu-id="c63be-231">Users can sign in to Microsoft Edge to access intranet sites and online resources (such as Office 365).</span></span> <span data-ttu-id="c63be-232">如果使用设备帐户配置 Surface Hub，系统将使用它访问 Exchange 和 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="c63be-232">If your Surface Hub is configured with a device account, the system uses it to access Exchange and Skype for Business.</span></span> <span data-ttu-id="c63be-233">但是，Surface Hub 不支持访问文件共享和打印机等域资源。</span><span class="sxs-lookup"><span data-stu-id="c63be-233">However, Surface Hub doesn't support accessing domain resources such as file shares and printers.</span></span>

*<span data-ttu-id="c63be-234">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-234">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-235">与访问域对象相关的策略不适用于 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c63be-235">Policies related to accessing domain objects don't apply for Surface Hub.</span></span>

<!--
### Endpoints



*Organization policies that this may affect:* <br> 
-->

### <span data-ttu-id="c63be-236">诊断数据</span><span class="sxs-lookup"><span data-stu-id="c63be-236">Diagnostic data</span></span>

<span data-ttu-id="c63be-237">Surface Hub 操作系统使用 Windows 10 的“已连接用户体验和遥测”组件收集和传输诊断数据。</span><span class="sxs-lookup"><span data-stu-id="c63be-237">The Surface Hub OS uses the Windows 10 Connected User Experience and Telemetry component to gather and transmit diagnostic data.</span></span> <span data-ttu-id="c63be-238">有关详细信息，请参阅[在组织中配置 Windows 诊断数据](https://technet.microsoft.com/itpro/windows/manage/configure-windows-diagnostic-data-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="c63be-238">For more information, see [Configure Windows diagnostic data in your organization](https://technet.microsoft.com/itpro/windows/manage/configure-windows-diagnostic-data-in-your-organization).</span></span>

*<span data-ttu-id="c63be-239">这可能影响的组织策略：</span><span class="sxs-lookup"><span data-stu-id="c63be-239">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="c63be-240">为 Surface Hub 配置诊断数据级别的方式与为 Windows 10 企业版配置相同。</span><span class="sxs-lookup"><span data-stu-id="c63be-240">Configure diagnostic data levels for Surface Hub in the same way as you do for Windows 10 Enterprise.</span></span>

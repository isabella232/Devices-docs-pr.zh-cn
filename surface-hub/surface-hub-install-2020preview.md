---
title: 安装 Windows 10 Team 2020 Update Preview 内部版本
description: 目前提供了 Surface Hub 操作系统、Windows 10 团队2020更新的最新更新。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894108"
---
# <span data-ttu-id="0dfcc-104">安装 Windows 10 Team 2020 Update Preview 内部版本</span><span class="sxs-lookup"><span data-stu-id="0dfcc-104">Install Windows 10 Team 2020 Update Preview Build</span></span> 

<span data-ttu-id="0dfcc-105">目前，Surface hub 操作系统、 **windows 10 Team 2020 更新**的最新更新现在可通过[Windows 预览体验计划](https://insider.windows.com)中的 surface Hub 50 英寸和 surface Hub 2 55 英寸设备免费获得额外费用。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-105">The latest update of the Surface Hub operating system, **Windows 10 Team 2020 Update**, is now available at no additional cost for the Surface Hub 50-inch and Surface Hub 2S 55-inch devices from the [Windows Insider Program](https://insider.windows.com).</span></span> <span data-ttu-id="0dfcc-106">Windows 10 Team 2020 更新的最终版本中将支持 Surface Hub 84 英寸模型。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-106">The Surface Hub 84-inch model will be supported in the final release of Windows 10 Team 2020 Update.</span></span>

<span data-ttu-id="0dfcc-107">Windows 10 Team 2020 更新通过最新的 Windows 10 功能提升了设备部署和可管理性的主要改进。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-107">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> <span data-ttu-id="0dfcc-108">若要了解有关新增功能的详细信息，请参阅以下博客文章：已[发布用于公共预览版的新 Surface HUB 操作系统更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span><span class="sxs-lookup"><span data-stu-id="0dfcc-108">To learn more about what's new, see the following blog post: [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span></span> <span data-ttu-id="0dfcc-109">对于已知问题，请参阅下面的 "已知问题" 部分。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-109">For known issues, refer to the "Known issues" section below.</span></span>
 
## <span data-ttu-id="0dfcc-110">必备条件</span><span class="sxs-lookup"><span data-stu-id="0dfcc-110">Prerequisites</span></span>

- <span data-ttu-id="0dfcc-111">注册到[Windows 预览体验计划](https://insider.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-111">Register with the [Windows Insider Program](https://insider.windows.com/).</span></span>
- <span data-ttu-id="0dfcc-112">从 Windows 预览体验计划快速频道下载 Windows 10 Team 2020 更新预览版。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-112">Download the Windows 10 Team 2020 Update Preview Build from the Windows Insider Program Fast Channel.</span></span>
- <span data-ttu-id="0dfcc-113">安装预览版本后，下载所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-113">After you install the Preview build, download the required firmware updates.</span></span> <span data-ttu-id="0dfcc-114">注意：即使你决定离开 Windows 预览体验计划，也无法卸载固件更新。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-114">Note: Firmware updates cannot be uninstalled even if you decide to leave the Windows Insider Program.</span></span>

## <span data-ttu-id="0dfcc-115">准备 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="0dfcc-115">Prepare your Surface Hub</span></span>

<span data-ttu-id="0dfcc-116">开始之前，请检查 Surface Hub 是否具有来自 Windows 更新的最新更新，并确保保存与设备关联的 BitLocker 密钥。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-116">Before you begin, check that your Surface Hub has the latest updates from Windows Update and make sure you save the BitLocker key associated with your device.</span></span>

**<span data-ttu-id="0dfcc-117">若要手动检查更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0dfcc-117">To manually check for updates:</span></span>**

1. <span data-ttu-id="0dfcc-118">在 Surface Hub 上，打开 "**设置**"，然后在出现提示时输入您的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-118">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="0dfcc-119">导航到 "**更新安全**  >  **Windows 更新**&"，然后选择 "**检查更新**"。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-119">Navigate to **Update & Security** > **Windows Update** and then select **Check for updates**.</span></span>

<span data-ttu-id="0dfcc-120">有关详细信息，请参阅[管理 Surface Hub 上的 Windows 更新](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-120">For more information, see [Manage Windows updates on Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).</span></span>

**<span data-ttu-id="0dfcc-121">要手动保存 BitLocker 密钥，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0dfcc-121">To manually save your BitLocker key:</span></span>**

1. <span data-ttu-id="0dfcc-122">将 USB 驱动器插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-122">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="0dfcc-123">在 Surface Hub 上，打开 "**设置**"，然后在出现提示时输入您的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-123">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="0dfcc-124">导航到 "**更新 & 安全**  >  **恢复**"。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-124">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="0dfcc-125">在 " **BitLocker**" 下，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-125">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="0dfcc-126">将 BitLocker 密钥保存到 USB 驱动器上的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-126">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="0dfcc-127">有关详细信息，请参阅[保存 BitLocker 密钥](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-127">For more information, see [Save your BitLocker key](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).</span></span>
 
## <span data-ttu-id="0dfcc-128">安装 Windows 10 Team 2020 Update Preview 内部版本</span><span class="sxs-lookup"><span data-stu-id="0dfcc-128">Install the Windows 10 Team 2020 Update Preview Build</span></span>

1. <span data-ttu-id="0dfcc-129">在 Surface Hub 上，打开 "**设置**"，然后在出现提示时输入您的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-129">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="0dfcc-130">导航到 "**更新**  >  **Windows 预览体验计划**" & 的 "更新"，然后选择 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-130">Navigate to **Update & Security** > **Windows Insider Program** and then select **Get started**.</span></span>
3. <span data-ttu-id="0dfcc-131">按照提示，使用你的工作帐户（推荐）或你的个人 Microsoft 帐户注册为 Windows 预览体验成员。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-131">Follow the prompts to register as a Windows Insider using either your work account (recommended) or your personal Microsoft account.</span></span> <span data-ttu-id="0dfcc-132">有关向工作帐户注册的好处的详细信息，请参阅[注册 Windows 预览体验计划 For Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-132">For details on the benefits of registering with your work account, see [Register for the Windows Insider Program for Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).</span></span>
4. <span data-ttu-id="0dfcc-133">在 "**选择预览体验成员设置**" 下，选择 "**快速**"。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-133">Under **Pick your Insider settings**, select **Fast**.</span></span>
5. <span data-ttu-id="0dfcc-134">允许 Surface Hub 在接下来的3到4天内自动安装预览构建和所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-134">Allow the Surface Hub to automatically install the Preview Build and the required firmware updates over the next 3 to 4 days.</span></span> <span data-ttu-id="0dfcc-135">设备将在日常[维护窗口](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)中自动下载并安装更新。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-135">The device will automatically download and install the updates during daily [maintenance windows](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window).</span></span> <span data-ttu-id="0dfcc-136">例如：</span><span class="sxs-lookup"><span data-stu-id="0dfcc-136">For example:</span></span>

- <span data-ttu-id="0dfcc-137">在第一个维护窗口中，Surface Hub 从 "Windows 更新" 开始下载预览版本。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-137">During the first maintenance window, Surface Hub starts downloading the Preview Build from Windows Update.</span></span>
- <span data-ttu-id="0dfcc-138">在第二个维护窗口中，设备将重新启动以完成更新。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-138">During a second maintenance window, the device restarts to complete the update.</span></span>
- <span data-ttu-id="0dfcc-139">在第三个维护窗口中，设备将下载并安装所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-139">During a third maintenance window, the device downloads and installs the required firmware updates.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dfcc-140">Microsoft 建议为3-4 天保留 Surface Hub，以允许设备完成预览版和所需固件更新的安装。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-140">Microsoft recommends reserving the Surface Hub for 3-4 days to allow the device to finish installing the Preview Build and the required firmware updates.</span></span> <span data-ttu-id="0dfcc-141">如果在此过程中使用设备，你可能会遇到图形、音频和用户界面问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-141">You may experience graphics, audio, and user interface issues if you use the device during this process.</span></span>

### <span data-ttu-id="0dfcc-142">如果你选择手动安装预览版和必需的固件更新：</span><span class="sxs-lookup"><span data-stu-id="0dfcc-142">If you choose to manually install the Preview Build and required firmware updates:</span></span>

1. <span data-ttu-id="0dfcc-143">注册到 Windows 预览体验计划后，请转到 "**设置**  >  **更新 & 安全**  >  **Windows 更新**"，然后选择 "**检查更新**" 以安装预览版本。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-143">After you've registered with the Windows Insider Program, go to **Settings** > **Update & Security** > **Windows Update** and select **Check for updates** to install the Preview Build.</span></span>
2. <span data-ttu-id="0dfcc-144">预览生成安装（可能需要长达14小时），请选择 "**立即重启**" 以完成安装。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-144">Once the Preview Build installs (it may take up to 14 hours), select **Restart now** to complete the installation.</span></span>
3. <span data-ttu-id="0dfcc-145">重新启动设备后，转到 "**设置**  >  "**更新 "& 安全**  >  **Windows 更新**"，然后选择 "**检查更新" 以安装所需的固件更新**。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-145">After the device restarts, go to **Settings** > **Update & Security** > **Windows Update**, and select **Check for updates to install required firmware updates**.</span></span>
4. <span data-ttu-id="0dfcc-146">固件安装后，选择 "**立即重启**"。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-146">Once the firmware installs, select **Restart now**.</span></span>

> [!WARNING]
> <span data-ttu-id="0dfcc-147">如果在未安装所需固件更新的情况下安装预览内部版本，则可能会看到图形、音频和用户界面问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-147">You may see graphics, audio, and user interface issues if you install the Preview Build without installing the required firmware updates.</span></span>

> [!NOTE]
> <span data-ttu-id="0dfcc-148">如果你选择退出 Windows 预览体验计划并将 Surface Hub 还原到较早版本的操作系统，则必须首先[重置你的设备](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-148">If you choose to leave the Windows Insider Program and revert your Surface Hub to an older version of the operating system, you must first [reset your device](https://docs.microsoft.com/surface-hub/device-reset-surface-hub).</span></span> <span data-ttu-id="0dfcc-149">之后，你需要转到[第一个 run 程序](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub)来重新配置你的设备。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-149">Afterwards, you will need to go through the [first run program](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) to re-configure your device.</span></span>
 
## <span data-ttu-id="0dfcc-150">已知问题： Windows 10 Team 2020 更新预览版</span><span class="sxs-lookup"><span data-stu-id="0dfcc-150">Known issues: Windows 10 Team 2020 Update Preview Build</span></span>

### <span data-ttu-id="0dfcc-151">图形、音频和用户界面问题</span><span class="sxs-lookup"><span data-stu-id="0dfcc-151">Graphics, audio, and user interface issues</span></span> 

<span data-ttu-id="0dfcc-152">如果安装了预览版，则可能会遇到各种图形和用户界面问题，但以后不会立即安装所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-152">You may experience various graphics and user interface issues if you install the Preview Build, but do not immediately install the required firmware updates afterward.</span></span> <span data-ttu-id="0dfcc-153">Microsoft 计划在 Windows 10 Team 2020 更新的版本内部版本中修复这些问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-153">Microsoft plans to fix these issues in the release build of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="0dfcc-154">Surface Hub 84-英寸：图形和用户界面问题</span><span class="sxs-lookup"><span data-stu-id="0dfcc-154">Surface Hub 84-inch: graphics and user interface issues</span></span>

<span data-ttu-id="0dfcc-155">如果在第一代 Surface Hub 84 英寸设备上安装预览版，则可能会遇到各种图形和用户界面问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-155">You may experience various graphics and user interface issues if you install the Preview Build on a first-generation Surface Hub 84-inch device.</span></span> <span data-ttu-id="0dfcc-156">Windows 10 Team 2020 更新的最终版本中将支持 Surface Hub 84 英寸。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-156">The Surface Hub 84-inch will be supported in the final release of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="0dfcc-157">应用条件访问策略时，登录会受到影响</span><span class="sxs-lookup"><span data-stu-id="0dfcc-157">Sign in is impacted when Conditional Access policies are applied</span></span>

- <span data-ttu-id="0dfcc-158">尝试登录应用（如 Microsoft 白板）时，登录失败。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-158">Sign in fails when attempting to sign into apps such as Microsoft Whiteboard.</span></span> <span data-ttu-id="0dfcc-159">用户必须先从 "开始" 菜单中的["我的会议" 和 "文件](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)" 登录。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-159">Users must first sign in from [My meetings and files](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) from the Start menu.</span></span>

- <span data-ttu-id="0dfcc-160">如果你的用户帐户注册到不同于 Surface Hub 使用的 Azure ad 加入的 Azure AD 租户，登录失败。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-160">Sign in fails if your user account is registered to a different Azure AD tenant than the one used by Surface Hub to Azure AD join.</span></span>

<span data-ttu-id="0dfcc-161">Microsoft 计划在 Windows 10 Team 2020 更新的版本内部版本中修复这些问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-161">Microsoft plans to fix these issues in the release build of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="0dfcc-162">Windows 更新提示安装没有可用的新驱动程序</span><span class="sxs-lookup"><span data-stu-id="0dfcc-162">Windows Update prompts to install new drivers when none are available</span></span>

<span data-ttu-id="0dfcc-163">转到 "**设置**  >  "**更新时 & 安全**  >  **windows 更新**安装了 windows 10 Team 2020 更新以及所需的固件更新后，可能会看到以下错误：</span><span class="sxs-lookup"><span data-stu-id="0dfcc-163">When you go to **Settings** > **Update & Security** > **Windows Update** after you’ve installed Windows 10 Team 2020 Update and the required firmware updates, you may see the following error:</span></span> 

- <span data-ttu-id="0dfcc-164">"电脑上的当前驱动程序可能比我们尝试安装的驱动程序更好。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-164">“A current driver on your PC may be better than the driver we’re trying to install.</span></span> <span data-ttu-id="0dfcc-165">我们将继续尝试安装。 "</span><span class="sxs-lookup"><span data-stu-id="0dfcc-165">We’ll keep trying to install.”</span></span> 

<span data-ttu-id="0dfcc-166">可以安全地忽略此错误。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-166">This error can be safely ignored.</span></span> <span data-ttu-id="0dfcc-167">Microsoft 正在积极调查此问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-167">Microsoft is actively investigating this issue.</span></span>

### <span data-ttu-id="0dfcc-168">无法使用预配程序包安装 Surface Hub 策略</span><span class="sxs-lookup"><span data-stu-id="0dfcc-168">Unable to install Surface Hub policies using provisioning packages</span></span>

<span data-ttu-id="0dfcc-169">预配使用 Surface Hub 配置服务提供商（CSP）中的策略的程序包安装失败。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-169">Provisioning packages that use policies from the Surface Hub Configuration Service Provider (CSP) fail to install.</span></span> <span data-ttu-id="0dfcc-170">现在，请使用 Microsoft Intune 或其他移动设备管理（MDM）提供程序应用 Surface Hub 策略。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-170">For now, use Microsoft Intune or another mobile device management (MDM) provider to apply Surface Hub policies.</span></span> <span data-ttu-id="0dfcc-171">Microsoft 计划在 Windows 10 Team 2020 更新的版本内部版本中修复此问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-171">Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="0dfcc-172">首次运行时，系统提示提前删除 USB 驱动器</span><span class="sxs-lookup"><span data-stu-id="0dfcc-172">Prompt to remove USB drive prematurely during first run</span></span>

<span data-ttu-id="0dfcc-173">在首次运行时使用预配包安装 Surface Hub 时，系统会提示你删除 USB 驱动器，然后设备才能读取 Surface Hub 配置文件。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-173">When using a provisioning package to setup Surface Hub during first run, you’re prompted to remove the USB drive before the device is able to read the Surface Hub configuration file.</span></span> <span data-ttu-id="0dfcc-174">如果您使用配置文件设置您的设备帐户，请忽略该消息。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-174">Ignore the message if you’re using a configure file to setup your device account.</span></span> <span data-ttu-id="0dfcc-175">Microsoft 正在积极调查此问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-175">Microsoft is actively investigating this issue.</span></span>
 
### <span data-ttu-id="0dfcc-176">无法在首次运行时设置代理设置</span><span class="sxs-lookup"><span data-stu-id="0dfcc-176">Unable to set up proxy settings during first run</span></span>

<span data-ttu-id="0dfcc-177">如果你使用代理连接到 Internet，则你的首次运行程序中可能具有有限的 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-177">If you use a proxy to connect to the Internet, you may have limited Internet connectivity during the first run program.</span></span> <span data-ttu-id="0dfcc-178">Microsoft 计划在 Windows 10 Team 2020 更新的版本内部版本中修复此问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-178">Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.</span></span>
 
### <span data-ttu-id="0dfcc-179">从 Microsoft Store 下载应用时出现错误</span><span class="sxs-lookup"><span data-stu-id="0dfcc-179">An error appears when you download apps from Microsoft Store</span></span>

<span data-ttu-id="0dfcc-180">若要从 Microsoft Store 下载应用，您将看到登录提示。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-180">To download an app from the Microsoft Store, you will see a prompt to sign in.</span></span> <span data-ttu-id="0dfcc-181">已知问题导致在登录期间出现错误，但这不会影响你下载应用的能力。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-181">A known issue causes an error to appear during sign-in, but this doesn't affect your ability to download apps.</span></span> <span data-ttu-id="0dfcc-182">Microsoft 正在积极调查此问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-182">Microsoft is actively investigating this issue.</span></span>

### <span data-ttu-id="0dfcc-183">Surface Hub 2 间歇性地失去 Wlan 连接</span><span class="sxs-lookup"><span data-stu-id="0dfcc-183">Surface Hub 2S intermittently loses Wi-Fi connection</span></span>

<span data-ttu-id="0dfcc-184">尝试拔出设备并将其重新插入，或使用以太网电缆连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-184">Try unplugging your device and plugging it back in, or using an Ethernet cable to connect to the Internet.</span></span> <span data-ttu-id="0dfcc-185">Microsoft 正在积极调查此问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-185">Microsoft is actively investigating this issue.</span></span>

### <span data-ttu-id="0dfcc-186">Surface Hub 2 间歇性无法从睡眠状态恢复</span><span class="sxs-lookup"><span data-stu-id="0dfcc-186">Surface Hub 2S intermittently fails to resume from sleep</span></span>

<span data-ttu-id="0dfcc-187">Surface Hub 2 可能间歇性地无法从睡眠中完全恢复，并且在显示 Microsoft 徽标的屏幕上看起来停止响应。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-187">Surface Hub 2S may intermittently fail to fully resume from sleep and appear to stop responding on a screen showing the Microsoft logo.</span></span> <span data-ttu-id="0dfcc-188">请尝试拨出设备，然后再将其插入。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-188">Try unplugging your device and plugging it back in.</span></span> 

<span data-ttu-id="0dfcc-189">若要防止此问题：</span><span class="sxs-lookup"><span data-stu-id="0dfcc-189">To prevent this issue:</span></span>

1. <span data-ttu-id="0dfcc-190">在 Surface Hub 上，打开 "**设置**"，然后在出现提示时输入您的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-190">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="0dfcc-191">导航到**Surface Hub**  >  **会话 & "电源**"。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-191">Navigate to **Surface Hub** > **Session & power**.</span></span> 
3. <span data-ttu-id="0dfcc-192">在 **"当设备进入睡眠状态时" 下，使用此电源设置**，选择 "**已连接待机"。**</span><span class="sxs-lookup"><span data-stu-id="0dfcc-192">Under **When the device goes to sleep, use this power setting**, select **Connected Standby.**</span></span>
4. <span data-ttu-id="0dfcc-193">在 "**无人出现时，将设备置于睡眠状态**" 下，选择 "**从不"。**</span><span class="sxs-lookup"><span data-stu-id="0dfcc-193">Under **When no one is present, put the device to sleep after**, select **Never.**</span></span>

<span data-ttu-id="0dfcc-194">Microsoft 计划在 Windows 10 Team 2020 更新的最终版本之前修复固件更新中的此问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-194">Microsoft plans to fix this issue in a firmware update prior to the final release of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="0dfcc-195">当 Connect 应用不在视图中时的投影问题</span><span class="sxs-lookup"><span data-stu-id="0dfcc-195">Projection issues when the Connect app is not in view</span></span>

- <span data-ttu-id="0dfcc-196">使用电缆投影到 Surface Hub 时，如果你离开 Connect 应用，touchback 将停止工作。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-196">When you use a cable to project to Surface Hub, touchback stops working if you navigate away from the Connect app.</span></span>
- <span data-ttu-id="0dfcc-197">使用 Miracast 投影到 Surface Hub 时，无线连接会在你离开连接应用后立即断开。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-197">When you project to Surface Hub using Miracast, the wireless connection drops soon after you navigate away from the Connect app.</span></span>

<span data-ttu-id="0dfcc-198">Microsoft 正在积极调查这些问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-198">Microsoft is actively investigating these issues.</span></span>

### <span data-ttu-id="0dfcc-199">Skype for Business 未使用用于媒体流量的代理</span><span class="sxs-lookup"><span data-stu-id="0dfcc-199">Skype for Business isn't using proxy for media traffic</span></span>

<span data-ttu-id="0dfcc-200">对于使用代理的某些设备，Skype for Business 可以登录，但不会将代理服务器用于媒体流量。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-200">For some devices that use a proxy, Skype for Business can sign in, but will not use the proxy server for media traffic.</span></span> <span data-ttu-id="0dfcc-201">Microsoft 正在积极调查此问题。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-201">Microsoft is actively investigating this issue.</span></span>

<span data-ttu-id="0dfcc-202">我们邀请您与 Microsoft 支持部门分享您的见解和建议。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-202">We invite you to share your insights and suggestions with Microsoft Support.</span></span>

## <span data-ttu-id="0dfcc-203">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="0dfcc-203">Learn more</span></span>

- [<span data-ttu-id="0dfcc-204">已发布用于公共预览版的新 Surface Hub 操作系统更新。</span><span class="sxs-lookup"><span data-stu-id="0dfcc-204">New Surface Hub OS update released for public preview.</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [<span data-ttu-id="0dfcc-205">Windows 预览体验计划企业版入门</span><span class="sxs-lookup"><span data-stu-id="0dfcc-205">Getting started with the Windows Insider Program for Business</span></span>](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)
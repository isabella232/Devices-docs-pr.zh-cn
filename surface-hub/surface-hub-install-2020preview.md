---
title: 安装 Windows 10 协同版 2020 更新预览版本
description: 目前提供了 Surface Hub 操作系统、Windows 10 团队2020更新的最新更新。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/13/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 51d6b9169b0074eb474ddc89b6fe9b43a921bb07
ms.sourcegitcommit: feb81137d009d9b7c743aabd7d02615e89842200
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929759"
---
# <span data-ttu-id="50e2b-104">安装 Windows 10 协同版 2020 更新预览版本</span><span class="sxs-lookup"><span data-stu-id="50e2b-104">Install Windows 10 Team 2020 Update Preview Build</span></span> 

<span data-ttu-id="50e2b-105">目前，Surface hub 操作系统、 **windows 10 Team 2020 更新**的最新更新现在可通过 [Windows 预览体验计划](https://insider.windows.com)中的 surface Hub 50 英寸和 surface Hub 2 55 英寸设备免费获得额外费用。</span><span class="sxs-lookup"><span data-stu-id="50e2b-105">The latest update of the Surface Hub operating system, **Windows 10 Team 2020 Update**, is now available at no additional cost for the Surface Hub 50-inch and Surface Hub 2S 55-inch devices from the [Windows Insider Program](https://insider.windows.com).</span></span> <span data-ttu-id="50e2b-106">Windows 10 Team 2020 更新的最终版本中将支持 Surface Hub 84 英寸模型。</span><span class="sxs-lookup"><span data-stu-id="50e2b-106">The Surface Hub 84-inch model will be supported in the final release of Windows 10 Team 2020 Update.</span></span>

<span data-ttu-id="50e2b-107">Windows 10 Team 2020 更新通过最新的 Windows 10 功能提升了设备部署和可管理性的主要改进。</span><span class="sxs-lookup"><span data-stu-id="50e2b-107">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> <span data-ttu-id="50e2b-108">若要了解有关新增功能的详细信息，请参阅以下博客文章：已 [发布用于公共预览版的新 Surface HUB 操作系统更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span><span class="sxs-lookup"><span data-stu-id="50e2b-108">To learn more about what's new, see the following blog post: [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span></span> <span data-ttu-id="50e2b-109">对于已知问题，请参阅下面的 "已知问题" 部分。</span><span class="sxs-lookup"><span data-stu-id="50e2b-109">For known issues, refer to the "Known issues" section below.</span></span>
 
## <span data-ttu-id="50e2b-110">必备条件</span><span class="sxs-lookup"><span data-stu-id="50e2b-110">Prerequisites</span></span>

- <span data-ttu-id="50e2b-111">注册到 [Windows 预览体验计划](https://insider.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="50e2b-111">Register with the [Windows Insider Program](https://insider.windows.com/).</span></span>
- <span data-ttu-id="50e2b-112">从 Windows 预览体验计划快速频道下载 Windows 10 Team 2020 更新预览版。</span><span class="sxs-lookup"><span data-stu-id="50e2b-112">Download the Windows 10 Team 2020 Update Preview Build from the Windows Insider Program Fast Channel.</span></span>
- <span data-ttu-id="50e2b-113">安装预览版本后，下载所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="50e2b-113">After you install the Preview build, download the required firmware updates.</span></span> <span data-ttu-id="50e2b-114">注意：即使你决定离开 Windows 预览体验计划，也无法卸载固件更新。</span><span class="sxs-lookup"><span data-stu-id="50e2b-114">Note: Firmware updates cannot be uninstalled even if you decide to leave the Windows Insider Program.</span></span>

## <span data-ttu-id="50e2b-115">准备 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="50e2b-115">Prepare your Surface Hub</span></span>

<span data-ttu-id="50e2b-116">开始之前，请检查 Surface Hub 是否具有来自 Windows 更新的最新更新，并确保保存与设备关联的 BitLocker 密钥。</span><span class="sxs-lookup"><span data-stu-id="50e2b-116">Before you begin, check that your Surface Hub has the latest updates from Windows Update and make sure you save the BitLocker key associated with your device.</span></span>

**<span data-ttu-id="50e2b-117">若要手动检查更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="50e2b-117">To manually check for updates:</span></span>**

1. <span data-ttu-id="50e2b-118">在 Surface Hub 上，打开 " **设置** "，然后在出现提示时输入您的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="50e2b-118">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="50e2b-119">导航到 "**更新安全**  >  **Windows 更新**&"，然后选择 "**检查更新**"。</span><span class="sxs-lookup"><span data-stu-id="50e2b-119">Navigate to **Update & Security** > **Windows Update** and then select **Check for updates**.</span></span>

<span data-ttu-id="50e2b-120">有关详细信息，请参阅 [管理 Surface Hub 上的 Windows 更新](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="50e2b-120">For more information, see [Manage Windows updates on Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).</span></span>

**<span data-ttu-id="50e2b-121">要手动保存 BitLocker 密钥，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="50e2b-121">To manually save your BitLocker key:</span></span>**

1. <span data-ttu-id="50e2b-122">将 USB 驱动器插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="50e2b-122">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="50e2b-123">在 Surface Hub 上，打开 " **设置** "，然后在出现提示时输入您的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="50e2b-123">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="50e2b-124">导航到 "**更新 & 安全**  >  **恢复**"。</span><span class="sxs-lookup"><span data-stu-id="50e2b-124">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="50e2b-125">在 " **BitLocker**" 下，选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="50e2b-125">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="50e2b-126">将 BitLocker 密钥保存到 USB 驱动器上的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="50e2b-126">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="50e2b-127">有关详细信息，请参阅 [保存 BitLocker 密钥](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="50e2b-127">For more information, see [Save your BitLocker key](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).</span></span>
 
## <span data-ttu-id="50e2b-128">安装 Windows 10 Team 2020 Update Preview 内部版本</span><span class="sxs-lookup"><span data-stu-id="50e2b-128">Install the Windows 10 Team 2020 Update Preview Build</span></span>

1. <span data-ttu-id="50e2b-129">在 Surface Hub 上，打开 " **设置** "，然后在出现提示时输入您的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="50e2b-129">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="50e2b-130">导航到 **隐私 > 诊断 & 反馈** ，并将诊断数据设置为 "已 **满**"。</span><span class="sxs-lookup"><span data-stu-id="50e2b-130">Navigate to **Privacy > Diagnostics & feedback** and set Diagnostic data to **Full**.</span></span> <span data-ttu-id="50e2b-131">某些区域或组织可能需要通过 MDM policy 或 PPKG 文件应用此设置：</span><span class="sxs-lookup"><span data-stu-id="50e2b-131">Some regions or organizations may need to apply this setting via MDM policy or PPKG file:</span></span>
   - <span data-ttu-id="50e2b-132">**对于 MDM：** 设置以下策略：。**/Vendor/MSFT/Policy/System/AllowTelemetry** 的整数值为3：</span><span class="sxs-lookup"><span data-stu-id="50e2b-132">**For MDM:** Set the following policy: .**/Vendor/MSFT/Policy/System/AllowTelemetry** with the integer value of 3:</span></span>
    
        ![将 AllowTelemetry 设置为3](images/hub-2020-allow-telemetry.png)

    - <span data-ttu-id="50e2b-134">**对于 PPKG：** 下载 [PPKG 文件](https://aka.ms/HubTltmtry)。</span><span class="sxs-lookup"><span data-stu-id="50e2b-134">**For PPKG:** Download the [PPKG file](https://aka.ms/HubTltmtry).</span></span>

3. <span data-ttu-id="50e2b-135">导航到 "**更新**  >  **Windows 预览体验计划**& 安全"，然后选择 "**开始**注册"。</span><span class="sxs-lookup"><span data-stu-id="50e2b-135">Navigate to **Update & Security** > **Windows Insider Program** and then select **Get started** to enroll.</span></span>
4. <span data-ttu-id="50e2b-136">按照提示，使用你的工作帐户注册到 Windows 预览体验 () 或你的个人 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="50e2b-136">Follow the prompts to register as a Windows Insider using either your work account (recommended) or your personal Microsoft account.</span></span> <span data-ttu-id="50e2b-137">有关向工作帐户注册的好处的详细信息，请参阅 [注册 Windows 预览体验计划 For Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)。</span><span class="sxs-lookup"><span data-stu-id="50e2b-137">For details on the benefits of registering with your work account, see [Register for the Windows Insider Program for Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).</span></span>
5. <span data-ttu-id="50e2b-138">在 " **选择预览体验成员设置**" 下，选择 " **快速**"。</span><span class="sxs-lookup"><span data-stu-id="50e2b-138">Under **Pick your Insider settings**, select **Fast**.</span></span>
6. <span data-ttu-id="50e2b-139">允许 Surface Hub 在接下来的3到4天内自动安装预览构建和所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="50e2b-139">Allow the Surface Hub to automatically install the Preview Build and the required firmware updates over the next 3 to 4 days.</span></span> <span data-ttu-id="50e2b-140">设备将在日常 [维护窗口](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)中自动下载并安装更新。</span><span class="sxs-lookup"><span data-stu-id="50e2b-140">The device will automatically download and install the updates during daily [maintenance windows](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window).</span></span> <span data-ttu-id="50e2b-141">例如：</span><span class="sxs-lookup"><span data-stu-id="50e2b-141">For example:</span></span>

- <span data-ttu-id="50e2b-142">在第一个维护窗口中，Surface Hub 从 "Windows 更新" 开始下载预览版本。</span><span class="sxs-lookup"><span data-stu-id="50e2b-142">During the first maintenance window, Surface Hub starts downloading the Preview Build from Windows Update.</span></span>
- <span data-ttu-id="50e2b-143">在第二个维护窗口中，设备将重新启动以完成更新。</span><span class="sxs-lookup"><span data-stu-id="50e2b-143">During a second maintenance window, the device restarts to complete the update.</span></span>
- <span data-ttu-id="50e2b-144">在第三个维护窗口中，设备将下载并安装所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="50e2b-144">During a third maintenance window, the device downloads and installs the required firmware updates.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50e2b-145">Microsoft 建议为3-4 天保留 Surface Hub，以允许设备完成预览版和所需固件更新的安装。</span><span class="sxs-lookup"><span data-stu-id="50e2b-145">Microsoft recommends reserving the Surface Hub for 3-4 days to allow the device to finish installing the Preview Build and the required firmware updates.</span></span> <span data-ttu-id="50e2b-146">如果在此过程中使用设备，你可能会遇到图形、音频和用户界面问题。</span><span class="sxs-lookup"><span data-stu-id="50e2b-146">You may experience graphics, audio, and user interface issues if you use the device during this process.</span></span>

### <span data-ttu-id="50e2b-147">如果你选择手动安装预览版和必需的固件更新：</span><span class="sxs-lookup"><span data-stu-id="50e2b-147">If you choose to manually install the Preview Build and required firmware updates:</span></span>

1. <span data-ttu-id="50e2b-148">注册到 Windows 预览体验计划后，请转到 "**设置**  >  **更新 & 安全**  >  **Windows 更新**"，然后选择 "**检查更新**" 以安装预览版本。</span><span class="sxs-lookup"><span data-stu-id="50e2b-148">After you've registered with the Windows Insider Program, go to **Settings** > **Update & Security** > **Windows Update** and select **Check for updates** to install the Preview Build.</span></span>
2. <span data-ttu-id="50e2b-149">一旦预览生成安装 (可能需要长达14小时) ，请选择 " **立即重启** " 以完成安装。</span><span class="sxs-lookup"><span data-stu-id="50e2b-149">Once the Preview Build installs (it may take up to 14 hours), select **Restart now** to complete the installation.</span></span>
3. <span data-ttu-id="50e2b-150">重新启动设备后，转到 "**设置**  >  "**更新 "& 安全**  >  **Windows 更新**"，然后选择 "**检查更新" 以安装所需的固件更新**。</span><span class="sxs-lookup"><span data-stu-id="50e2b-150">After the device restarts, go to **Settings** > **Update & Security** > **Windows Update**, and select **Check for updates to install required firmware updates**.</span></span>
4. <span data-ttu-id="50e2b-151">固件安装后，选择 " **立即重启**"。</span><span class="sxs-lookup"><span data-stu-id="50e2b-151">Once the firmware installs, select **Restart now**.</span></span>

> [!WARNING]
> <span data-ttu-id="50e2b-152">如果在未安装所需固件更新的情况下安装预览内部版本，则可能会看到图形、音频和用户界面问题。</span><span class="sxs-lookup"><span data-stu-id="50e2b-152">You may see graphics, audio, and user interface issues if you install the Preview Build without installing the required firmware updates.</span></span>

> [!NOTE]
> <span data-ttu-id="50e2b-153">如果你选择退出 Windows 预览体验计划并将 Surface Hub 还原到较早版本的操作系统，则必须首先 [重置你的设备](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="50e2b-153">If you choose to leave the Windows Insider Program and revert your Surface Hub to an older version of the operating system, you must first [reset your device](https://docs.microsoft.com/surface-hub/device-reset-surface-hub).</span></span> <span data-ttu-id="50e2b-154">之后，你需要转到 [第一个 run 程序](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) 来重新配置你的设备。</span><span class="sxs-lookup"><span data-stu-id="50e2b-154">Afterwards, you will need to go through the [first run program](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) to re-configure your device.</span></span>
 

## <span data-ttu-id="50e2b-155">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="50e2b-155">Learn more</span></span>

- [<span data-ttu-id="50e2b-156">已知问题： Windows 10 Team 2020 更新</span><span class="sxs-lookup"><span data-stu-id="50e2b-156">Known issues: Windows 10 Team 2020 Update</span></span>](surface-hub-2020-team-update-known-issues.md)
- [<span data-ttu-id="50e2b-157">已发布用于公共预览版的新 Surface Hub 操作系统更新。</span><span class="sxs-lookup"><span data-stu-id="50e2b-157">New Surface Hub OS update released for public preview.</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [<span data-ttu-id="50e2b-158">Windows 预览体验计划企业版入门</span><span class="sxs-lookup"><span data-stu-id="50e2b-158">Getting started with the Windows Insider Program for Business</span></span>](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)
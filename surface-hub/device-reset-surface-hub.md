---
title: 重置或恢复 Surface Hub
description: 介绍 Surface Hub 的重置和恢复过程，并提供说明。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重置 Surface Hub， 恢复
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406610"
---
# <a name="reset-or-recover-a-surface-hub"></a><span data-ttu-id="1d061-104">重置或恢复 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1d061-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="1d061-105">本文介绍如何重置或恢复 Microsoft Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="1d061-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="1d061-106">[重置 Surface Hub 会](#reset-a-surface-hub) 将其操作系统返回到上一次累积 Windows 更新，并删除所有本地用户文件和配置信息。</span><span class="sxs-lookup"><span data-stu-id="1d061-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="1d061-107">删除的信息包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="1d061-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="1d061-108">设备帐户</span><span class="sxs-lookup"><span data-stu-id="1d061-108">The device account</span></span>
- <span data-ttu-id="1d061-109">设备本地管理员的帐户信息</span><span class="sxs-lookup"><span data-stu-id="1d061-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="1d061-110">域加入或 Azure AD 加入信息</span><span class="sxs-lookup"><span data-stu-id="1d061-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="1d061-111">移动设备管理 (MDM) 注册信息</span><span class="sxs-lookup"><span data-stu-id="1d061-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="1d061-112">使用 MDM 或"设置"应用设置的配置信息</span><span class="sxs-lookup"><span data-stu-id="1d061-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="1d061-113">[从云中恢复 Surface Hub](#recover-a-surface-hub-from-the-cloud) 也会删除此信息。</span><span class="sxs-lookup"><span data-stu-id="1d061-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="1d061-114">此外，Surface Hub 下载并安装新的操作系统映像。</span><span class="sxs-lookup"><span data-stu-id="1d061-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="1d061-115">你可以指定恢复过程是否保留存储在 Surface Hub 上的其他信息。</span><span class="sxs-lookup"><span data-stu-id="1d061-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="1d061-116">如果需要恢复 Surface Hub，则 [Surface Hub](surface-hub-recovery-tool.md) 恢复工具会使用相同的操作系统映像，而其中两个选项均无法用于该 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="1d061-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <a name="reset-a-surface-hub"></a><span data-ttu-id="1d061-117">重置 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1d061-117">Reset a Surface Hub</span></span>

<span data-ttu-id="1d061-118">出于以下原因，你可能必须重置 Surface Hub：</span><span class="sxs-lookup"><span data-stu-id="1d061-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="1d061-119">你正在重新设置设备以用于新的会议空间，并且想要重新配置它。</span><span class="sxs-lookup"><span data-stu-id="1d061-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="1d061-120">想要更改本地管理设备的方式。</span><span class="sxs-lookup"><span data-stu-id="1d061-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="1d061-121">设备帐户或管理员帐户的用户名或密码已丢失。</span><span class="sxs-lookup"><span data-stu-id="1d061-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="1d061-122">安装更新后，设备性能会降低。</span><span class="sxs-lookup"><span data-stu-id="1d061-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="1d061-123">在重置过程中，如果长时间看到空白屏幕，请稍等，不要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="1d061-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="1d061-124">设备重置过程最多可能需要六个小时。</span><span class="sxs-lookup"><span data-stu-id="1d061-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="1d061-125">在进程完成之前，不要关闭或拔下 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="1d061-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="1d061-126">如果中断该过程，设备将变得不可操作。</span><span class="sxs-lookup"><span data-stu-id="1d061-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="1d061-127">设备需要担保服务才能再次正常运行。</span><span class="sxs-lookup"><span data-stu-id="1d061-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="1d061-128">在 Surface Hub 上，打开**设置**。</span><span class="sxs-lookup"><span data-stu-id="1d061-128">On your Surface Hub, open **Settings**.</span></span>

   ![显示 Surface Hub 的"设置"应用的图像。](images/sh-settings.png)

2. <span data-ttu-id="1d061-130">选择 **"更新&安全"。**</span><span class="sxs-lookup"><span data-stu-id="1d061-130">Select **Update & Security**.</span></span>

   ![显示 Surface Hub &"应用中的"更新和安全"组的图像。](images/sh-settings-update-security.png)

3. <span data-ttu-id="1d061-132">选择 **"恢复**"，然后在"重置**设备"下**，选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="1d061-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1d061-133">在重置设备之前，请确保你的 BitLocker 密钥可用，因为稍后会提示你提供它。</span><span class="sxs-lookup"><span data-stu-id="1d061-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="1d061-134">若要了解更多信息，请参阅 [保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="1d061-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="1d061-135">当集线器重新启动到恢复分区时，它将提示你输入 BitLocker 密钥。</span><span class="sxs-lookup"><span data-stu-id="1d061-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="1d061-136">跳过该提示将导致重置失败。</span><span class="sxs-lookup"><span data-stu-id="1d061-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![显示 Surface Hub 的"设置"应用中的"重置设备"选项的图像。](images/sh-settings-reset-device.png)

   <span data-ttu-id="1d061-138">重置过程完成后，Surface Hub 将再次 [启动首次运行](first-run-program-surface-hub.md) 计划。</span><span class="sxs-lookup"><span data-stu-id="1d061-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="1d061-139">如果重置过程遇到问题，它会将 Surface Hub 回滚到以前存在的操作系统映像，然后显示欢迎屏幕。</span><span class="sxs-lookup"><span data-stu-id="1d061-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a><span data-ttu-id="1d061-140">从云中恢复 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1d061-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="1d061-141">如果由于某种原因 Surface Hub 变得不可用，你仍然可以从云中恢复它，而无需 Microsoft 支持人员的帮助。</span><span class="sxs-lookup"><span data-stu-id="1d061-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="1d061-142">Surface Hub 可以从云中下载全新的操作系统映像，并使用该映像重新安装其操作系统。</span><span class="sxs-lookup"><span data-stu-id="1d061-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="1d061-143">在下列情况下，您可能必须使用此类型的恢复过程：</span><span class="sxs-lookup"><span data-stu-id="1d061-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="1d061-144">Surface Hub 及其相关帐户已进入不稳定状态</span><span class="sxs-lookup"><span data-stu-id="1d061-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="1d061-145">Surface Hub 已锁定</span><span class="sxs-lookup"><span data-stu-id="1d061-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="1d061-146">" **从云恢复"** 过程需要有线连接，该连接提供开放 internet 连接， (代理或其他身份验证) 。</span><span class="sxs-lookup"><span data-stu-id="1d061-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <a name="recover-a-surface-hub-in-a-bad-state"></a><span data-ttu-id="1d061-147">恢复处于错误状态的 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1d061-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="1d061-148">如果设备帐户进入不稳定状态或管理员帐户遇到问题，可以使用"设置"应用启动云恢复过程。</span><span class="sxs-lookup"><span data-stu-id="1d061-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="1d061-149">应仅在设备重置过程未解决问题时使用云[](#reset-a-surface-hub)恢复过程。</span><span class="sxs-lookup"><span data-stu-id="1d061-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="1d061-150">在 Surface Hub 上 **，选择"** 设置 &gt; **""&安全** &gt; **恢复"。**</span><span class="sxs-lookup"><span data-stu-id="1d061-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="1d061-151">在 **"从云中恢复"下**，选择 **"立即重启"。**</span><span class="sxs-lookup"><span data-stu-id="1d061-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![从云中恢复](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a><span data-ttu-id="1d061-153">恢复锁定的 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1d061-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="1d061-154">在极少数情况下，会话结束后，Surface Hub 在清理用户和应用数据时会遇到错误。</span><span class="sxs-lookup"><span data-stu-id="1d061-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="1d061-155">发生这种情况时，设备将自动重新启动并再次尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="1d061-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="1d061-156">但如果此操作重复失败，设备将自动锁定以保护用户数据。</span><span class="sxs-lookup"><span data-stu-id="1d061-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="1d061-157">若要解锁它，你必须 [重置设备](#reset-a-surface-hub) ，或者，如果不起作用，请从云中恢复它。</span><span class="sxs-lookup"><span data-stu-id="1d061-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="1d061-158">找到 Surface Hub 底部的电源开关。</span><span class="sxs-lookup"><span data-stu-id="1d061-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="1d061-159">电源开关位于电缆连接旁边。</span><span class="sxs-lookup"><span data-stu-id="1d061-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="1d061-160">有关电源开关详细信息，请参阅 Surface Hub 站点准备指南[ (PDF) 。 ](surface-hub-site-readiness-guide.md)</span><span class="sxs-lookup"><span data-stu-id="1d061-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="1d061-161">当 Surface Hub 显示欢迎屏幕时，使用电源开关关闭 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="1d061-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="1d061-162">使用电源开关重新打开 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="1d061-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="1d061-163">设备启动并显示 Surface Hub 徽标屏幕。</span><span class="sxs-lookup"><span data-stu-id="1d061-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="1d061-164">当你在 Surface Hub 徽标下看到旋转的点时，请使用电源开关再次关闭 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="1d061-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="1d061-165">重复步骤 3 三次，或直到 Surface Hub 显示"正在准备自动修复"消息。</span><span class="sxs-lookup"><span data-stu-id="1d061-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="1d061-166">显示此消息后，Surface Hub 将显示 Windows RE 屏幕。</span><span class="sxs-lookup"><span data-stu-id="1d061-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

 
5. <span data-ttu-id="1d061-167">选择 **重置以重新安装 Windows**。</span><span class="sxs-lookup"><span data-stu-id="1d061-167">Select **Reset to re-install Windows**.</span></span> 
![重置为重新安装](images/recover-from-cloud.png)

8. <span data-ttu-id="1d061-169">选择 **"云下载"。**</span><span class="sxs-lookup"><span data-stu-id="1d061-169">Select **Cloud download.**</span></span> 

   ![云下载](images/recover-cloud-download.png)

>[!IMPORTANT]
><span data-ttu-id="1d061-171">如果收到指示无法下载 **的错误消息，** 请选择" **取消** "，然后重试。</span><span class="sxs-lookup"><span data-stu-id="1d061-171">If you get an error message indicating **Unable to Download**, select **Cancel** and try again.</span></span>

9. <span data-ttu-id="1d061-172">选择 **"完全清理驱动器"。**  
![恢复和完全清理驱动器</span><span class="sxs-lookup"><span data-stu-id="1d061-172">Select **Fully clean the drive.** 
![recover and fully clean drive</span></span>](images/recover-fully-clean-drive.png)

10. <span data-ttu-id="1d061-173">将询问你**准备好重置此设备了吗？。**</span><span class="sxs-lookup"><span data-stu-id="1d061-173">You will be asked **Are you ready to reset this device?**.</span></span> <span data-ttu-id="1d061-174">选择 **“重置”**。</span><span class="sxs-lookup"><span data-stu-id="1d061-174">Select **Reset**.</span></span> 
![恢复并确认重置](images/recover-confirm-reset.png)

11. <span data-ttu-id="1d061-176">下载开始，恢复过程指示 **重置此设备**。</span><span class="sxs-lookup"><span data-stu-id="1d061-176">The download begins and the recovery process indicates **Resetting this device**.</span></span> 
![正在显示的恢复](images/recover-in-progress.png)

## <a name="contact-support"></a><span data-ttu-id="1d061-178">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="1d061-178">Contact Support</span></span>

<span data-ttu-id="1d061-179">如果有任何疑问或需要帮助，可以创建 [支持请求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="1d061-179">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <a name="related-topics"></a><span data-ttu-id="1d061-180">相关主题</span><span class="sxs-lookup"><span data-stu-id="1d061-180">Related topics</span></span>

[<span data-ttu-id="1d061-181">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1d061-181">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="1d061-182">Microsoft Surface Hub 管理员指南</span><span class="sxs-lookup"><span data-stu-id="1d061-182">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

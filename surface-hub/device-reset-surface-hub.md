---
title: 重置或恢复 Surface Hub
description: 介绍 Surface Hub 的重置和恢复过程，并提供相关说明。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重置 Surface Hub，恢复
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 1c8d8b6d89ec1a20550b7aa13c82c73a239c3965
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104814"
---
# <span data-ttu-id="082eb-104">重置或恢复 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="082eb-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="082eb-105">本文介绍如何重置或恢复 Microsoft Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="082eb-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="082eb-106">[重置 Surface Hub](#reset-a-surface-hub) 会将其操作系统返回到上次累积的 Windows 更新，并删除所有本地用户文件和配置信息。</span><span class="sxs-lookup"><span data-stu-id="082eb-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="082eb-107">删除的信息包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="082eb-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="082eb-108">设备帐户</span><span class="sxs-lookup"><span data-stu-id="082eb-108">The device account</span></span>
- <span data-ttu-id="082eb-109">设备的本地管理员的帐户信息</span><span class="sxs-lookup"><span data-stu-id="082eb-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="082eb-110">域加入或 Azure AD 联接信息</span><span class="sxs-lookup"><span data-stu-id="082eb-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="082eb-111"> (MDM) 注册信息的移动设备管理</span><span class="sxs-lookup"><span data-stu-id="082eb-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="082eb-112">使用 MDM 或 "设置" 应用设置的配置信息</span><span class="sxs-lookup"><span data-stu-id="082eb-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="082eb-113">[从云恢复 Surface Hub](#recover-a-surface-hub-from-the-cloud) 也会删除此信息。</span><span class="sxs-lookup"><span data-stu-id="082eb-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="082eb-114">此外，Surface Hub 下载新的操作系统映像并进行安装。</span><span class="sxs-lookup"><span data-stu-id="082eb-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="082eb-115">你可以指定恢复过程是否保留存储在 Surface Hub 上的其他信息。</span><span class="sxs-lookup"><span data-stu-id="082eb-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span>

## <span data-ttu-id="082eb-116">重置 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="082eb-116">Reset a Surface Hub</span></span>

<span data-ttu-id="082eb-117">出于以下原因，您可能需要重置 Surface Hub：</span><span class="sxs-lookup"><span data-stu-id="082eb-117">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="082eb-118">您为新的会议空间重新安排设备的用途，并希望重新配置它。</span><span class="sxs-lookup"><span data-stu-id="082eb-118">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="082eb-119">想要更改本地管理设备的方式。</span><span class="sxs-lookup"><span data-stu-id="082eb-119">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="082eb-120">设备帐户或管理员帐户的用户名或密码已丢失。</span><span class="sxs-lookup"><span data-stu-id="082eb-120">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="082eb-121">安装更新后，设备性能将减少。</span><span class="sxs-lookup"><span data-stu-id="082eb-121">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="082eb-122">在重置过程中，如果你长时间看到一个空白屏幕，请等待，不要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="082eb-122">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="082eb-123">设备重置过程可能需要长达6小时。</span><span class="sxs-lookup"><span data-stu-id="082eb-123">The device reset process may take up to six hours.</span></span> <span data-ttu-id="082eb-124">请勿关闭或拔出 Surface Hub，直到该过程完成。</span><span class="sxs-lookup"><span data-stu-id="082eb-124">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="082eb-125">如果中断进程，设备将变为不可操作。</span><span class="sxs-lookup"><span data-stu-id="082eb-125">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="082eb-126">设备需要保修服务才能再次运行。</span><span class="sxs-lookup"><span data-stu-id="082eb-126">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="082eb-127">在 Surface Hub 上，打开**设置**。</span><span class="sxs-lookup"><span data-stu-id="082eb-127">On your Surface Hub, open **Settings**.</span></span>

   ![显示 Surface Hub 的 "设置" 应用的图像。](images/sh-settings.png)

1. <span data-ttu-id="082eb-129">选择 " **更新 & 安全性**"。</span><span class="sxs-lookup"><span data-stu-id="082eb-129">Select **Update & Security**.</span></span>

   ![在 Surface Hub 的 "设置" 应用中显示 "更新 & 安全组" 的图像。](images/sh-settings-update-security.png)

1. <span data-ttu-id="082eb-131">选择 " **恢复**"，然后在 " **重置设备**" 下，选择 " **开始**"。</span><span class="sxs-lookup"><span data-stu-id="082eb-131">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   ![显示 Surface Hub 的 "设置" 应用中的 "重置设备" 选项的图像。](images/sh-settings-reset-device.png)

   <span data-ttu-id="082eb-133">重置过程完成后，Surface Hub 将再次启动 [第一个 run 程序](first-run-program-surface-hub.md) 。</span><span class="sxs-lookup"><span data-stu-id="082eb-133">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="082eb-134">如果重置过程遇到问题，它会将 Surface Hub 回退到以前存在的操作系统映像，然后显示 "欢迎" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="082eb-134">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="082eb-135">从云中恢复 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="082eb-135">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="082eb-136">如果由于某种原因，Surface Hub 变得不可用，您仍然可以从云中恢复它，而无需 Microsoft 支持部门的帮助。</span><span class="sxs-lookup"><span data-stu-id="082eb-136">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="082eb-137">Surface Hub 可以从云中下载全新的操作系统映像，并使用该映像重新安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="082eb-137">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="082eb-138">在以下情况下，您可能必须使用此类型的恢复过程：</span><span class="sxs-lookup"><span data-stu-id="082eb-138">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="082eb-139">Surface Hub 或其相关帐户进入了不稳定状态</span><span class="sxs-lookup"><span data-stu-id="082eb-139">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="082eb-140">Surface Hub 已锁定</span><span class="sxs-lookup"><span data-stu-id="082eb-140">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="082eb-141">**从云进程恢复**需要有线连接，该连接提供开放的 internet 连接 (没有代理或其他身份验证提示) 。</span><span class="sxs-lookup"><span data-stu-id="082eb-141">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <span data-ttu-id="082eb-142">恢复处于错误状态的 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="082eb-142">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="082eb-143">如果设备帐户处于不稳定状态或管理员帐户遇到问题，则可以使用 "设置" 应用启动云恢复过程。</span><span class="sxs-lookup"><span data-stu-id="082eb-143">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="082eb-144">只有在 [设备重置](#reset-a-surface-hub) 过程不能解决问题时，才应使用云恢复过程。</span><span class="sxs-lookup"><span data-stu-id="082eb-144">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="082eb-145">在 Surface Hub 上，选择 " **设置** &gt; **更新 & 安全** &gt; **恢复**"。</span><span class="sxs-lookup"><span data-stu-id="082eb-145">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

1. <span data-ttu-id="082eb-146">在 " **从云恢复**" 下，选择 " **立即重启**"。</span><span class="sxs-lookup"><span data-stu-id="082eb-146">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![从云中恢复](images/recover-from-the-cloud.png)

### <span data-ttu-id="082eb-148">恢复锁定的 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="082eb-148">Recover a locked Surface Hub</span></span>

<span data-ttu-id="082eb-149">在极少数情况下，会话结束后，Surface Hub 在清理用户和应用数据时会遇到错误。</span><span class="sxs-lookup"><span data-stu-id="082eb-149">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="082eb-150">发生这种情况时，设备将自动重新启动，并再次尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="082eb-150">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="082eb-151">但是，如果此操作重复失败，设备将自动锁定以保护用户数据。</span><span class="sxs-lookup"><span data-stu-id="082eb-151">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="082eb-152">若要解除锁定，必须 [重置设备](#reset-a-surface-hub) ，如果不起作用，请从云恢复它。</span><span class="sxs-lookup"><span data-stu-id="082eb-152">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="082eb-153">找到 Surface Hub 底部的电源开关。</span><span class="sxs-lookup"><span data-stu-id="082eb-153">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="082eb-154">电源开关位于电源线连接旁边。</span><span class="sxs-lookup"><span data-stu-id="082eb-154">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="082eb-155">有关 power 开关的详细信息，请参阅 [Surface Hub 网站准备指南 (PDF) ](surface-hub-site-readiness-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="082eb-155">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

1. <span data-ttu-id="082eb-156">当 Surface Hub 显示 "欢迎" 屏幕时，请使用 power 开关关闭 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="082eb-156">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

1. <span data-ttu-id="082eb-157">使用 power 开关重新打开 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="082eb-157">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="082eb-158">设备将启动并显示 Surface Hub 徽标屏幕。</span><span class="sxs-lookup"><span data-stu-id="082eb-158">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="082eb-159">当您在 Surface Hub 徽标下看到旋转点时，请使用 power 开关再次关闭 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="082eb-159">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

1. <span data-ttu-id="082eb-160">重复步骤 3 3 时间，或直到 Surface Hub 显示 "正在准备自动修复" 消息。</span><span class="sxs-lookup"><span data-stu-id="082eb-160">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="082eb-161">显示此消息后，Surface Hub 将显示 Windows RE 屏幕。</span><span class="sxs-lookup"><span data-stu-id="082eb-161">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

1. <span data-ttu-id="082eb-162">选择 " **高级选项**"。</span><span class="sxs-lookup"><span data-stu-id="082eb-162">Select **Advanced Options**.</span></span>

1. <span data-ttu-id="082eb-163">选择 **"从云恢复"**。</span><span class="sxs-lookup"><span data-stu-id="082eb-163">Select **Recover from the cloud**.</span></span> <span data-ttu-id="082eb-164"> (也可以选择 " **重置**"。</span><span class="sxs-lookup"><span data-stu-id="082eb-164">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="082eb-165">但是， **从云恢复** 是推荐的方法。 ) </span><span class="sxs-lookup"><span data-stu-id="082eb-165">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![从云中恢复](images/recover-from-cloud.png)
1. <span data-ttu-id="082eb-167">如果系统提示您输入 Bitlocker 密钥，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="082eb-167">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="082eb-168">若要保留 Bitlocker 在 Surface Hub 上保护的信息，请输入 Bitlocker 密钥。</span><span class="sxs-lookup"><span data-stu-id="082eb-168">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="082eb-169">若要放弃受保护的信息，请选择 "**跳过此驱动器**"</span><span class="sxs-lookup"><span data-stu-id="082eb-169">To discard the protected information, select **Skip this drive**</span></span>  

1. <span data-ttu-id="082eb-170">出现提示时，选择 " **重新安装**"。</span><span class="sxs-lookup"><span data-stu-id="082eb-170">When you are prompted, select **Reinstall**.</span></span>

    ![重新安装](images/reinstall.png)

1. <span data-ttu-id="082eb-172">若要对磁盘进行重新分区，请选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="082eb-172">To repartition the disk, select **Yes**.</span></span>

   ![重新分区](images/repartition.png)

   <span data-ttu-id="082eb-174">首先，恢复过程从云中下载操作系统映像。</span><span class="sxs-lookup"><span data-stu-id="082eb-174">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![正在下载 97&](images/recover-progress.png)

   <span data-ttu-id="082eb-176">下载完成后，恢复过程根据你选择的选项恢复 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="082eb-176">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="082eb-177">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="082eb-177">Contact Support</span></span>

<span data-ttu-id="082eb-178">如果有疑问或需要帮助，您可以 [创建支持请求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="082eb-178">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="082eb-179">相关主题</span><span class="sxs-lookup"><span data-stu-id="082eb-179">Related topics</span></span>

[<span data-ttu-id="082eb-180">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="082eb-180">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="082eb-181">Microsoft Surface Hub 管理员指南</span><span class="sxs-lookup"><span data-stu-id="082eb-181">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

---
title: 兼容的 Surface 设备中的 SSD 删除
description: 如何将 SSD 从一个 Surface 设备转移到另一个 Surface 设备。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 00109e4e1bb3873fc2914b2044f58e6fa3b6c211
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104804"
---
# <span data-ttu-id="14b0f-103">从兼容的 Surface 设备中删除 SSD 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="14b0f-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14b0f-104">本文仅供企业组织中合格的 IT 技术人员使用。</span><span class="sxs-lookup"><span data-stu-id="14b0f-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="14b0f-105">它介绍了合格的 IT 技术人员在 Surface 笔记本电脑3或 Surface Pro X 中删除和替换 SSDs 时所推荐的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="14b0f-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in Surface Laptop 3 or Surface Pro X only.</span></span> 

> [!WARNING]
> <span data-ttu-id="14b0f-106">打开设备和更换设备组件可能会带来电击、设备损坏、火灾和人身伤害风险以及其他危险。</span><span class="sxs-lookup"><span data-stu-id="14b0f-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="14b0f-107">在执行此类活动时，请务必小心。</span><span class="sxs-lookup"><span data-stu-id="14b0f-107">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="14b0f-108">按照 [适用于企业的 RSSD 删除指南](https://www.microsoft.com/download/100440)中标识的安全预防措施和过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="14b0f-108">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="14b0f-109">如果您无法遵循 "适用于企业的 rSSD 删除指南" 中指定的安全预防措施和过程，我们建议您获得专业帮助。</span><span class="sxs-lookup"><span data-stu-id="14b0f-109">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="14b0f-110">必备条件</span><span class="sxs-lookup"><span data-stu-id="14b0f-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14b0f-111">本文假定你了解 "适用于企业的 rSSD 删除指南" 中介绍的常规安全预防措施和安全策略和过程。</span><span class="sxs-lookup"><span data-stu-id="14b0f-111">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="14b0f-112">准备删除 SSD</span><span class="sxs-lookup"><span data-stu-id="14b0f-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="14b0f-113">安装最新的更新</span><span class="sxs-lookup"><span data-stu-id="14b0f-113">Install the latest updates</span></span> 

<span data-ttu-id="14b0f-114">开始之前，请确保你的 Windows 版本具有最新的更新 intalled：</span><span class="sxs-lookup"><span data-stu-id="14b0f-114">Before you begin, make sure that your version of Windows has the latest updates intalled:</span></span>

1.  <span data-ttu-id="14b0f-115">转到 "**开始**  >  **设置**  >  "**更新 & 安全**"，然后选择"**检查更新**"。</span><span class="sxs-lookup"><span data-stu-id="14b0f-115">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span> <span data-ttu-id="14b0f-116">安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="14b0f-116">Install all available updates.</span></span> 
2. <span data-ttu-id="14b0f-117">安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="14b0f-117">Install all available updates.</span></span>
3. <span data-ttu-id="14b0f-118">验证您是否拥有访问设备所必需的任何密码。</span><span class="sxs-lookup"><span data-stu-id="14b0f-118">Verify that you have any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="14b0f-119">“管理 BitLocker”</span><span class="sxs-lookup"><span data-stu-id="14b0f-119">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="14b0f-120">本部分包括对硬盘启用了 BitLocker 加密的组织的建议。</span><span class="sxs-lookup"><span data-stu-id="14b0f-120">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="14b0f-121">有关详细信息，请参阅 [BitLocker 恢复指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="14b0f-121">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="14b0f-122">如果在 SSD 删除和替换期间禁用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="14b0f-122">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="14b0f-123">如果在 SSD 删除和替换之前可以解除对设备的加密，请按照以下步骤关闭 BitLocker：</span><span class="sxs-lookup"><span data-stu-id="14b0f-123">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="14b0f-124">在 " **设置**" 中，键入 " **bitlocker**"，然后选择 " **管理 bitlocker**"。</span><span class="sxs-lookup"><span data-stu-id="14b0f-124">In **Settings**, type **Bitlocker**, and then select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="14b0f-125">选择 " **关闭 Bitlocker**"。</span><span class="sxs-lookup"><span data-stu-id="14b0f-125">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="14b0f-126">关闭设备电源。</span><span class="sxs-lookup"><span data-stu-id="14b0f-126">Power down the device.</span></span> 

### <span data-ttu-id="14b0f-127">如果在 SSD 删除和替换期间启用了 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="14b0f-127">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="14b0f-128">如果设备在 SSD 删除和替换之前已加密，请按照以下步骤生成 BitLocker 恢复密钥并将其保存到 USB 存储：</span><span class="sxs-lookup"><span data-stu-id="14b0f-128">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="14b0f-129">在 " **设置**" 中，键入 **Bitlocker**。</span><span class="sxs-lookup"><span data-stu-id="14b0f-129">In **Settings**, type **Bitlocker**.</span></span>
2. <span data-ttu-id="14b0f-130">选择 "**管理 bitlocker**  > **生成 bitlocker 恢复密钥**"。</span><span class="sxs-lookup"><span data-stu-id="14b0f-130">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="14b0f-131">插入 u 盘。</span><span class="sxs-lookup"><span data-stu-id="14b0f-131">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="14b0f-132">将恢复密钥保存到 USB 存储。</span><span class="sxs-lookup"><span data-stu-id="14b0f-132">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="14b0f-133">删除 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="14b0f-133">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="14b0f-134">关闭设备电源。</span><span class="sxs-lookup"><span data-stu-id="14b0f-134">Power down the device.</span></span> 

## <span data-ttu-id="14b0f-135">删除并替换 SSD</span><span class="sxs-lookup"><span data-stu-id="14b0f-135">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="14b0f-136">使用 [适用于企业的 RSSD 删除指南](https://www.microsoft.com/download/100440)中的说明删除 SSD。</span><span class="sxs-lookup"><span data-stu-id="14b0f-136">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="14b0f-137">将原始的 SSD 放入新设备中，并将新设备连接到有线 internet 连接。</span><span class="sxs-lookup"><span data-stu-id="14b0f-137">Put the original SSD into a new device, and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="14b0f-138">打开新设备的电源。</span><span class="sxs-lookup"><span data-stu-id="14b0f-138">Power on the new device.</span></span> <span data-ttu-id="14b0f-139">设备可能会在启动期间经历固件更新。</span><span class="sxs-lookup"><span data-stu-id="14b0f-139">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="14b0f-140">在 SSD 删除和更换后</span><span class="sxs-lookup"><span data-stu-id="14b0f-140">After SSD removal and replacement</span></span>

### <span data-ttu-id="14b0f-141">管理未加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="14b0f-141">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="14b0f-142">如果 SSD 在传输期间保持未加密，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="14b0f-142">If the SSD remains unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="14b0f-143">转到 "**登录选项**"  >  **密码** (左侧) 的钥匙图标表示。</span><span class="sxs-lookup"><span data-stu-id="14b0f-143">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="14b0f-144">输入密码，如果有两个因素身份验证，请登录 (（如果适用）) 。</span><span class="sxs-lookup"><span data-stu-id="14b0f-144">Enter the password, and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="14b0f-145">完全登录后，转到 "**开始**  >  **帐户**  >  **注销**"。</span><span class="sxs-lookup"><span data-stu-id="14b0f-145">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="14b0f-146">使用密码重新登录，并在系统提示时设置 Windows Hello 和 PIN。</span><span class="sxs-lookup"><span data-stu-id="14b0f-146">Sign back in by using the password, and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="14b0f-147">如果设备已禁用 BitLocker 来简化 SSD 删除和替换，并且你希望在替换后启用 bitlocker，请转到**bitlocker**  >  **管理 bitlocker**  >  **恢复 bitlocker**。</span><span class="sxs-lookup"><span data-stu-id="14b0f-147">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="14b0f-148">运行适用于 Business (SDT) 的 Microsoft Surface 诊断工具包，以验证完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="14b0f-148">Run the Microsoft Surface Diagnostic Toolkit for Business (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="14b0f-149">通过导航到 "**设置**激活" 来检查是否有 Windows 激活  >  **Activation**。</span><span class="sxs-lookup"><span data-stu-id="14b0f-149">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="14b0f-150">如果看到任何错误消息，请选择 " **疑难解答**"。</span><span class="sxs-lookup"><span data-stu-id="14b0f-150">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="14b0f-151">通过打开**office 应用**检查 office 帐户，导航到 "**文件**  >  **帐户**"，然后检查是否有任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="14b0f-151">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="14b0f-152">管理加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="14b0f-152">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="14b0f-153">您必须拥有第二台设备才能读取保存在 USB 驱动器上的 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="14b0f-153">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="14b0f-154">如果 SSD 在传输期间保持加密，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="14b0f-154">If the SSD remained encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="14b0f-155">将包含 Bitlocker 恢复密钥的 USB 驱动器插入到第二个设备中。</span><span class="sxs-lookup"><span data-stu-id="14b0f-155">Insert the USB drive that contains the Bitlocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="14b0f-156">打开包含 Bitlocker 恢复密钥的 .txt 文件。</span><span class="sxs-lookup"><span data-stu-id="14b0f-156">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="14b0f-157">在包含原始 SSD 的新设备上手动输入 Bitlocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="14b0f-157">Manually enter the Bitlocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="14b0f-158">成功输入 BitLocker 恢复密钥后，转到左侧) 的钥匙图标中的 "**登录选项**"  >  **密码** (。</span><span class="sxs-lookup"><span data-stu-id="14b0f-158">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="14b0f-159">如果适用，请输入密码并登录，等待完成双因素身份验证 (（如果适用）) 。</span><span class="sxs-lookup"><span data-stu-id="14b0f-159">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="14b0f-160">完全登录后，转到 "**开始**  >  **帐户**  >  **注销**"。</span><span class="sxs-lookup"><span data-stu-id="14b0f-160">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="14b0f-161">使用密码重新登录，然后设置 Windows Hello 并添加 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="14b0f-161">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="14b0f-162">如果设备已禁用 BitLocker 以促进 SSD 删除和替换，并且如果你希望在更换后启用 bitlocker，请转到**Settings**  >  **bitlocker**  >  **管理 bitlocker**  >  **恢复 bitlocker**的设置。</span><span class="sxs-lookup"><span data-stu-id="14b0f-162">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="14b0f-163">运行 **SDT** 以验证完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="14b0f-163">Run **SDT** to verify full device functionality.</span></span>  
10. <span data-ttu-id="14b0f-164">通过导航到 "**设置**激活" 检查 Windows 激活  >  **Activation**。</span><span class="sxs-lookup"><span data-stu-id="14b0f-164">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="14b0f-165">如果看到任何错误消息，请选择 " **疑难解答**"。</span><span class="sxs-lookup"><span data-stu-id="14b0f-165">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="14b0f-166">若要检查 office 帐户的状态，请打开**office 应用**，然后转到 "**文件**  >  **帐户**" 以检查是否有任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="14b0f-166">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="14b0f-167">详细信息</span><span class="sxs-lookup"><span data-stu-id="14b0f-167">More information</span></span> 

<span data-ttu-id="14b0f-168">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="14b0f-168">For more information, see the following articles:</span></span>

- [<span data-ttu-id="14b0f-169">适用于企业的 rSSD 删除指南</span><span class="sxs-lookup"><span data-stu-id="14b0f-169">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="14b0f-170">BitLocker 恢复指南</span><span class="sxs-lookup"><span data-stu-id="14b0f-170">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="14b0f-171">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="14b0f-171">Still need help?</span></span> <span data-ttu-id="14b0f-172">转到 [Microsoft 社区](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="14b0f-172">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
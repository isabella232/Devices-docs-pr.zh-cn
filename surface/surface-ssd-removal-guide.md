---
title: 兼容的 Surface 设备中的 SSD 删除
description: 本文适用于合格的 IT 技术人员，介绍了在 Surface 笔记本电脑3、Surface Pro X 和 Surface 笔记本电脑中删除和替换 SSDs 的建议最佳做法。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/21/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 56c740b39d86ea3fab386e88efa6932e050bb957
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133167"
---
# <span data-ttu-id="ff533-103">从兼容的 Surface 设备中删除 SSD 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="ff533-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff533-104">本文仅供企业组织中合格的 IT 技术人员使用。</span><span class="sxs-lookup"><span data-stu-id="ff533-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="ff533-105">它介绍了由合格的 IT 技术人员在以下兼容的 Surface 设备中删除和替换 SSDs 时使用的建议最佳做法：</span><span class="sxs-lookup"><span data-stu-id="ff533-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="ff533-106">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="ff533-106">Surface Laptop 3</span></span> 
- <span data-ttu-id="ff533-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="ff533-107">Surface Pro X</span></span> 
- <span data-ttu-id="ff533-108">Surface 膝上型电脑 Go</span><span class="sxs-lookup"><span data-stu-id="ff533-108">Surface Laptop Go</span></span>

> [!WARNING]
> <span data-ttu-id="ff533-109">打开设备和更换设备组件可能会带来电击、设备损坏、火灾和人身伤害风险以及其他危险。</span><span class="sxs-lookup"><span data-stu-id="ff533-109">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="ff533-110">在执行此类活动时，请务必小心。</span><span class="sxs-lookup"><span data-stu-id="ff533-110">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="ff533-111">按照 [适用于企业的 RSSD 删除指南](https://www.microsoft.com/download/100440)中标识的安全预防措施和过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="ff533-111">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="ff533-112">如果您无法遵循 "适用于企业的 rSSD 删除指南" 中指定的安全预防措施和过程，我们建议您获得专业帮助。</span><span class="sxs-lookup"><span data-stu-id="ff533-112">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="ff533-113">必备条件</span><span class="sxs-lookup"><span data-stu-id="ff533-113">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff533-114">本文假定你了解 "适用于企业的 rSSD 删除指南" 中介绍的常规安全预防措施和安全策略和过程。</span><span class="sxs-lookup"><span data-stu-id="ff533-114">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="ff533-115">准备删除 SSD</span><span class="sxs-lookup"><span data-stu-id="ff533-115">Prepare for SSD removal</span></span> 

### <span data-ttu-id="ff533-116">安装最新的更新</span><span class="sxs-lookup"><span data-stu-id="ff533-116">Install the latest updates</span></span> 

<span data-ttu-id="ff533-117">开始之前，请确保你的 Windows 版本已安装最新的更新：</span><span class="sxs-lookup"><span data-stu-id="ff533-117">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="ff533-118">转到 "**开始**  >  **设置**  >  "**更新 & 安全**"，然后选择"**检查更新**"。</span><span class="sxs-lookup"><span data-stu-id="ff533-118">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="ff533-119">安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="ff533-119">Install all available updates.</span></span>
3. <span data-ttu-id="ff533-120">验证访问设备所需的任何密码。</span><span class="sxs-lookup"><span data-stu-id="ff533-120">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="ff533-121">“管理 BitLocker”</span><span class="sxs-lookup"><span data-stu-id="ff533-121">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="ff533-122">本部分包括对硬盘启用了 BitLocker 加密的组织的建议。</span><span class="sxs-lookup"><span data-stu-id="ff533-122">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="ff533-123">有关详细信息，请参阅  [BitLocker 恢复指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="ff533-123">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="ff533-124">如果在 SSD 删除和替换期间禁用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="ff533-124">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="ff533-125">如果在 SSD 删除和替换之前可以解除对设备的加密，请按照以下步骤关闭 BitLocker：</span><span class="sxs-lookup"><span data-stu-id="ff533-125">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="ff533-126">在 " **设置**" 中，键入 **bitlocker** ，然后选择 " **管理 bitlocker**"。</span><span class="sxs-lookup"><span data-stu-id="ff533-126">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="ff533-127">选择 " **关闭 BitLocker**"。</span><span class="sxs-lookup"><span data-stu-id="ff533-127">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="ff533-128">关闭设备电源。</span><span class="sxs-lookup"><span data-stu-id="ff533-128">Power down the device.</span></span> 

### <span data-ttu-id="ff533-129">如果在 SSD 删除和替换期间启用了 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="ff533-129">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="ff533-130">如果设备在 SSD 删除和替换之前已加密，请按照以下步骤生成 BitLocker 恢复密钥并将其保存到 USB 存储：</span><span class="sxs-lookup"><span data-stu-id="ff533-130">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="ff533-131">在 " **设置**" 中，键入 **BitLocker**。</span><span class="sxs-lookup"><span data-stu-id="ff533-131">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="ff533-132">选择 "**管理 bitlocker**  > **生成 bitlocker 恢复密钥**"。</span><span class="sxs-lookup"><span data-stu-id="ff533-132">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="ff533-133">插入 u 盘。</span><span class="sxs-lookup"><span data-stu-id="ff533-133">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="ff533-134">将恢复密钥保存到 USB 存储。</span><span class="sxs-lookup"><span data-stu-id="ff533-134">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="ff533-135">删除 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="ff533-135">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="ff533-136">关闭设备电源。</span><span class="sxs-lookup"><span data-stu-id="ff533-136">Power down the device.</span></span> 

## <span data-ttu-id="ff533-137">删除并替换 SSD</span><span class="sxs-lookup"><span data-stu-id="ff533-137">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="ff533-138">使用 [适用于企业的 RSSD 删除指南](https://www.microsoft.com/download/100440)中的说明删除 SSD。</span><span class="sxs-lookup"><span data-stu-id="ff533-138">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="ff533-139">将原始的 SSD 放入新设备中，并将新设备连接到有线 internet 连接。</span><span class="sxs-lookup"><span data-stu-id="ff533-139">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="ff533-140">打开新设备的电源。</span><span class="sxs-lookup"><span data-stu-id="ff533-140">Power on the new device.</span></span> <span data-ttu-id="ff533-141">设备可能会在启动期间经历固件更新。</span><span class="sxs-lookup"><span data-stu-id="ff533-141">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="ff533-142">在 SSD 删除和更换后</span><span class="sxs-lookup"><span data-stu-id="ff533-142">After SSD removal and replacement</span></span>

### <span data-ttu-id="ff533-143">管理未加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="ff533-143">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="ff533-144">如果 SSD 在传输期间未加密，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ff533-144">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="ff533-145">转到 "**登录选项**"  >  **密码** (左侧) 的钥匙图标表示。</span><span class="sxs-lookup"><span data-stu-id="ff533-145">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="ff533-146">如果适用，请输入密码并登录待完成的双因素身份验证 (（如果适用）) 。</span><span class="sxs-lookup"><span data-stu-id="ff533-146">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="ff533-147">完全登录后，转到 "**开始**  >  **帐户**  >  **注销**"。</span><span class="sxs-lookup"><span data-stu-id="ff533-147">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="ff533-148">使用密码重新登录，并在出现提示时设置 Windows Hello 和 PIN。</span><span class="sxs-lookup"><span data-stu-id="ff533-148">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="ff533-149">如果设备已禁用 BitLocker 来简化 SSD 删除和替换，并且你希望在替换后启用 bitlocker，请转到**bitlocker**  >  **管理 bitlocker**  >  **恢复 bitlocker**。</span><span class="sxs-lookup"><span data-stu-id="ff533-149">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="ff533-150">运行适用于 Business (SDT) 的 [Microsoft Surface 诊断工具包](surface-diagnostic-toolkit-for-business-intro.md) ，以验证完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="ff533-150">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="ff533-151">通过导航到 "**设置**激活" 来检查是否有 Windows 激活  >  **Activation**。</span><span class="sxs-lookup"><span data-stu-id="ff533-151">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="ff533-152">如果看到任何错误消息，请选择 " **疑难解答**"。</span><span class="sxs-lookup"><span data-stu-id="ff533-152">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="ff533-153">通过打开**office 应用**检查 office 帐户，导航到 "**文件**  >  **帐户**"，然后检查是否有任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="ff533-153">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="ff533-154">管理加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="ff533-154">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="ff533-155">您必须拥有第二台设备才能读取保存在 USB 驱动器上的 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="ff533-155">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="ff533-156">如果 SSD 在转移期间已加密，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ff533-156">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="ff533-157">将包含 BitLocker 恢复密钥的 USB 驱动器插入到第二个设备中。</span><span class="sxs-lookup"><span data-stu-id="ff533-157">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="ff533-158">打开包含 Bitlocker 恢复密钥的 .txt 文件。</span><span class="sxs-lookup"><span data-stu-id="ff533-158">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="ff533-159">在包含原始 SSD 的新设备上手动输入 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="ff533-159">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="ff533-160">成功输入 BitLocker 恢复密钥后，转到左侧) 的钥匙图标中的 "**登录选项**"  >  **密码** (。</span><span class="sxs-lookup"><span data-stu-id="ff533-160">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="ff533-161">如果适用，请输入密码并登录，等待完成双因素身份验证 (（如果适用）) 。</span><span class="sxs-lookup"><span data-stu-id="ff533-161">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="ff533-162">完全登录后，转到 "**开始**  >  **帐户**  >  **注销**"。</span><span class="sxs-lookup"><span data-stu-id="ff533-162">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="ff533-163">使用密码重新登录，然后设置 Windows Hello 并添加 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="ff533-163">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="ff533-164">如果设备已禁用 BitLocker 以促进 SSD 删除和替换，并且如果你希望在更换后启用 bitlocker，请转到**Settings**  >  **bitlocker**  >  **管理 bitlocker**  >  **恢复 bitlocker**的设置。</span><span class="sxs-lookup"><span data-stu-id="ff533-164">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="ff533-165">运行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以验证完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="ff533-165">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="ff533-166">若要检查 Windows 激活，请选择 "**设置**  >  **激活**"。</span><span class="sxs-lookup"><span data-stu-id="ff533-166">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="ff533-167">如果看到任何错误消息，请选择 " **疑难解答**"。</span><span class="sxs-lookup"><span data-stu-id="ff533-167">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="ff533-168">若要检查 office 帐户的状态，请打开**office 应用**，然后转到 "**文件**  >  **帐户**" 以检查是否有任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="ff533-168">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="ff533-169">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="ff533-169">Learn more</span></span>

- [<span data-ttu-id="ff533-170">适用于企业的 rSSD 删除指南</span><span class="sxs-lookup"><span data-stu-id="ff533-170">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="ff533-171">BitLocker 恢复指南</span><span class="sxs-lookup"><span data-stu-id="ff533-171">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="ff533-172">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="ff533-172">Still need help?</span></span> <span data-ttu-id="ff533-173">转到 [Microsoft 社区](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="ff533-173">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
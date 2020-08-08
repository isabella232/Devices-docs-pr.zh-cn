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
ms.date: 8/7/2020
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
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918944"
---
# <span data-ttu-id="e3fcb-103">兼容 Surface 设备中的 SSD 删除的最佳做法</span><span class="sxs-lookup"><span data-stu-id="e3fcb-103">Best practices for SSD removal in compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3fcb-104">本文仅供企业组织中合格的 IT 技术人员使用。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="e3fcb-105">它介绍了通过可移动的 SSDs 在 Surface 设备中删除和替换 SSDs 时，合格的 IT 技术人员使用的建议最佳做法。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-105">It describes the recommended best practices for use by qualified IT technicians when removing and replacing SSDs in Surface devices with removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="e3fcb-106">打开设备和更换设备组件可能会带来电击、设备损坏、火灾和人身伤害风险以及其他危险。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="e3fcb-107">在执行此类活动时，请务必小心。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-107">Always use caution when undertaking such activities.</span></span> <span data-ttu-id="e3fcb-108">按照适用于企业的 rSSD 删除指南中标识的安全预防措施和过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-108">Follow the safety precautions and procedures identified in the rSSD Removal Guide for Enterprise.</span></span> <span data-ttu-id="e3fcb-109">如果您无法遵守企业的 rSSD 删除指南中指定的安全预防措施和过程，Microsoft 建议您寻求专业帮助。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-109">Microsoft recommends that you seek professional assistance if you are unable to follow the safety precautions and procedures specified in the rSSD Removal Guide for Enterprise.</span></span> 

## <span data-ttu-id="e3fcb-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="e3fcb-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3fcb-111">本文假定你了解[企业的 RSSD 删除指南](https://www.microsoft.com/download/100440)中所述的常规安全预防措施和安全策略和过程。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-111">This article assumes you understand the General Safety Precautions and Safety policies and procedures described in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span>

## <span data-ttu-id="e3fcb-112">准备删除 SSD</span><span class="sxs-lookup"><span data-stu-id="e3fcb-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="e3fcb-113">安装最新的更新</span><span class="sxs-lookup"><span data-stu-id="e3fcb-113">Install the latest updates</span></span> 

<span data-ttu-id="e3fcb-114">开始之前，请确保你的 Windows 版本具有最新的更新。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-114">Before you begin, make sure your version of Windows has the latest updates.</span></span>

1.  <span data-ttu-id="e3fcb-115">转到 "**开始**  >  **设置**"  >  **更新 & 安全**"，然后选择"**检查更新**"。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-115">Go to **Start** > **Settings** > **Update & Security** and select **Check for updates**.</span></span> <span data-ttu-id="e3fcb-116">安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-116">Install all available updates.</span></span>  

2.  <span data-ttu-id="e3fcb-117">确认你有权访问设备所需的任何密码。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-117">Confirm that you have any passwords needed to access the device.</span></span>  
 
## <span data-ttu-id="e3fcb-118">管理 Bitlocker</span><span class="sxs-lookup"><span data-stu-id="e3fcb-118">Manage Bitlocker</span></span> 

> [!NOTE]
> <span data-ttu-id="e3fcb-119">本部分包括对硬驱启用了 BitLocker 加密的组织的建议。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-119">This section includes recommendations for organizations that have enabled BitLocker encryption for hard drives.</span></span> <span data-ttu-id="e3fcb-120">有关详细信息，请参阅[BitLocker 恢复指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-120">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="e3fcb-121">如果在 SSD 删除和替换期间禁用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="e3fcb-121">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="e3fcb-122">如果在 SSD 删除和替换之前可以解除对设备的加密，请按照以下步骤关闭 BitLocker：</span><span class="sxs-lookup"><span data-stu-id="e3fcb-122">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="e3fcb-123">在 "**设置**" 中，键入**bitlocker** ，然后选择 "**管理 bitlocker**"。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-123">In **Settings**, type **Bitlocker** and select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="e3fcb-124">选择 "**关闭 Bitlocker**"。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-124">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="e3fcb-125">关闭设备电源。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-125">Power down the device.</span></span> 

### <span data-ttu-id="e3fcb-126">如果在 SSD 删除和替换期间启用了 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="e3fcb-126">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="e3fcb-127">如果设备在 SSD 删除和替换之前已加密，请按照以下步骤生成 BitLocker 恢复密钥并将其保存到 USB 存储：</span><span class="sxs-lookup"><span data-stu-id="e3fcb-127">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="e3fcb-128">转到 "**设置**"，然后键入 " **Bitlocker**"。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-128">Go to **Settings** and type **Bitlocker**.</span></span>
2. <span data-ttu-id="e3fcb-129">选择 "**管理 bitlocker**  > **生成 bitlocker 恢复密钥**"。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-129">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="e3fcb-130">插入 u 盘。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-130">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="e3fcb-131">将恢复密钥保存到 USB 存储。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-131">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="e3fcb-132">删除 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-132">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="e3fcb-133">关闭设备电源。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-133">Power down the device.</span></span> 

## <span data-ttu-id="e3fcb-134">删除并替换 SSD</span><span class="sxs-lookup"><span data-stu-id="e3fcb-134">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="e3fcb-135">使用[适用于企业的 RSSD 删除指南](https://www.microsoft.com/download/100440)中的说明删除 SSD。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-135">Remove the SSD using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="e3fcb-136">将原始的 SSD 放入新设备中，并将新设备连接到有线 internet 连接。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-136">Place the original SSD in a new device and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="e3fcb-137">打开新设备的电源。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-137">Power on the new device.</span></span> <span data-ttu-id="e3fcb-138">设备可能会在启动期间经历固件更新。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-138">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="e3fcb-139">在 SSD 删除和更换后</span><span class="sxs-lookup"><span data-stu-id="e3fcb-139">After SSD removal and replacement</span></span>

### <span data-ttu-id="e3fcb-140">管理未加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="e3fcb-140">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="e3fcb-141">如果 SSD 在传输期间保持未加密，请完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="e3fcb-141">If the SSD remains unencrypted during the transfer, complete the following:</span></span> 

1.  <span data-ttu-id="e3fcb-142">转到 "**登录选项**"  >  **密码** (表示为左侧) 的钥匙图标。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-142">Go to **Sign-In Options** > **Password** (represented as the key icon on the left side).</span></span>  
2.  <span data-ttu-id="e3fcb-143">如果适用，请输入密码并登录待完成的双因素身份验证 (（如果适用）) 。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-143">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="e3fcb-144">完全登录后，转到 "**开始**  >  **帐户**  >  **注销**"。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-144">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="e3fcb-145">出现提示时，请使用密码重新登录，并设置 Windows Hello 和 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-145">Sign back in with the password and set up Windows Hello and a PIN when prompted.</span></span> 
    - <span data-ttu-id="e3fcb-146">如果设备已禁用 BitLocker 以简化 SSD 删除和替换，并且你希望在替换后启用 bitlocker，请转到**bitlocker**  >  **管理 bitlocker**  >  **恢复 bitlocker**。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-146">If the device was BitLocker-disabled to facilitate SSD removal and replacement and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="e3fcb-147">运行**SDT**以确认完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-147">Run **SDT** to confirm full device functionality.</span></span>  
7.  <span data-ttu-id="e3fcb-148">通过导航到 "**设置**激活" 来检查是否有 Windows 激活  >  **Activation**。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-148">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="e3fcb-149">如果出现任何错误消息，请选择 "**疑难解答**"。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-149">If there are any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="e3fcb-150">通过打开**office 应用**检查 office 帐户，然后导航到 "**文件**  >  **帐户**"，检查是否有任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-150">Check the Office account by opening the **Office App**, then navigate to **File** > **Account** and check for any error messages.</span></span>  

### <span data-ttu-id="e3fcb-151">管理加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="e3fcb-151">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="e3fcb-152">你需要使用第二个设备来读取在 USB 驱动器上保存的 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-152">You will need a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="e3fcb-153">如果 SSD 在传输期间保持加密，请完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="e3fcb-153">If the SSD remained encrypted during the transfer, complete the following:</span></span>

1.  <span data-ttu-id="e3fcb-154">将包含 Bitlocker 恢复密钥的 USB 驱动器插入到第二个设备中。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-154">Insert the USB drive containing the Bitlocker Recovery key into the second device.</span></span> 
2.  <span data-ttu-id="e3fcb-155">打开包含 Bitlocker 恢复密钥的 .txt 文件。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-155">Open the .txt file containing the Bitlocker Recovery key.</span></span> 
3.  <span data-ttu-id="e3fcb-156">手动将 Bitlocker 恢复密钥输入到包含原始 SSD 的新设备中。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-156">Manually enter the Bitlocker Recovery key into the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="e3fcb-157">成功输入 BitLocker 恢复密钥后，转到左侧) 的钥匙图标中的 "**登录选项**"  >  **密码** (。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-157">After you have successfully entered the BitLocker Recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="e3fcb-158">输入密码并登录，等待完成双因素身份验证 (（如果适用）) </span><span class="sxs-lookup"><span data-stu-id="e3fcb-158">Enter the password and sign in, pending completion of two-factor authentication (if applicable)</span></span> 
6.  <span data-ttu-id="e3fcb-159">完全登录后，转到 "**开始**  >  **帐户**  >  **注销**"。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-159">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="e3fcb-160">使用密码重新登录，并设置 Windows Hello 并添加 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-160">Sign back in with the password and set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="e3fcb-161">如果设备已禁用 BitLocker 来简化 SSD 删除和替换，并且你希望在替换后启用 bitlocker，请转到**设置**  >  **bitlocker**  >  **管理 bitlocker**  >  **恢复 bitlocker**。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-161">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="e3fcb-162">运行**SDT**以确认完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-162">Run **SDT** to confirm full device functionality.</span></span>  
10. <span data-ttu-id="e3fcb-163">通过导航到 "**设置**激活" 检查 Windows 激活  >  **Activation**。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-163">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="e3fcb-164">如果出现任何错误消息，请选择 "**疑难解答**"。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-164">If there are any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="e3fcb-165">若要检查 office 帐户，请打开**office 应用**，然后转到 "**文件**  >  **帐户**"，检查是否有任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-165">To check the Office Account, open the **Office App**, then go to **File** > **Account** and check for any error messages.</span></span>

## <span data-ttu-id="e3fcb-166">详细信息</span><span class="sxs-lookup"><span data-stu-id="e3fcb-166">More information</span></span> 

<span data-ttu-id="e3fcb-167">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e3fcb-167">For more information, see the following articles:</span></span>

- [<span data-ttu-id="e3fcb-168">适用于企业的 rSSD 删除指南</span><span class="sxs-lookup"><span data-stu-id="e3fcb-168">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="e3fcb-169">BitLocker 恢复指南</span><span class="sxs-lookup"><span data-stu-id="e3fcb-169">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="e3fcb-170">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="e3fcb-170">Still need help?</span></span> <span data-ttu-id="e3fcb-171">转到[Microsoft 社区](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="e3fcb-171">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
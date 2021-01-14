---
title: 兼容 Surface 设备中的 SSD 删除
description: 本文面向合格的 IT 技术人员，介绍了在 Surface Laptop 3、Surface Pro X 和 Surface Laptop Go 中删除和替换 SSD 的建议最佳做法。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: b65feb24803311aba809819cd6da273ed6934c75
ms.sourcegitcommit: 41124d496abaa38a0d989159f2afec3542d562ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269103"
---
# <span data-ttu-id="5d69d-103">从兼容的 Surface 设备删除 SSD 的最佳实践</span><span class="sxs-lookup"><span data-stu-id="5d69d-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d69d-104">本文仅供企业组织中合格的 IT 技术人员使用。</span><span class="sxs-lookup"><span data-stu-id="5d69d-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="5d69d-105">它介绍了推荐的最佳实践，供合格的 IT 技术人员在删除和替换以下兼容 Surface 设备中的 SSD 时使用：</span><span class="sxs-lookup"><span data-stu-id="5d69d-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="5d69d-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="5d69d-106">Surface Pro 7+</span></span>
- <span data-ttu-id="5d69d-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="5d69d-107">Surface Pro X</span></span>
- <span data-ttu-id="5d69d-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="5d69d-108">Surface Laptop Go</span></span>
- <span data-ttu-id="5d69d-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="5d69d-109">Surface Laptop 3</span></span>

> [!WARNING]
> <span data-ttu-id="5d69d-110">打开设备和更换设备组件可能会带来电力损失、设备损坏、火灾和个人损失风险以及其他危险。</span><span class="sxs-lookup"><span data-stu-id="5d69d-110">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="5d69d-111">执行此类活动时，请始终小心。</span><span class="sxs-lookup"><span data-stu-id="5d69d-111">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="5d69d-112">按照 [RSSD](https://www.microsoft.com/download/100440)企业版删除指南中确定的安全预防措施和过程操作。</span><span class="sxs-lookup"><span data-stu-id="5d69d-112">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="5d69d-113">如果无法遵循"rSSD 企业版删除指南"中指定的安全预防措施和过程，我们建议您获得专业协助。</span><span class="sxs-lookup"><span data-stu-id="5d69d-113">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="5d69d-114">必备条件</span><span class="sxs-lookup"><span data-stu-id="5d69d-114">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d69d-115">本文假定您了解"适用于企业的 rSSD 删除指南"中所述的一般安全预防措施和安全策略和过程。</span><span class="sxs-lookup"><span data-stu-id="5d69d-115">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="5d69d-116">准备删除 SSD</span><span class="sxs-lookup"><span data-stu-id="5d69d-116">Prepare for SSD removal</span></span> 

### <span data-ttu-id="5d69d-117">安装最新更新</span><span class="sxs-lookup"><span data-stu-id="5d69d-117">Install the latest updates</span></span> 

<span data-ttu-id="5d69d-118">开始之前，请确保你的 Windows 版本已安装最新更新：</span><span class="sxs-lookup"><span data-stu-id="5d69d-118">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="5d69d-119">转到"**开始**  >  **设置**  >  **更新&安全性**"，然后选择 **"检查更新"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-119">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="5d69d-120">安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="5d69d-120">Install all available updates.</span></span>
3. <span data-ttu-id="5d69d-121">验证访问设备所需的任何密码。</span><span class="sxs-lookup"><span data-stu-id="5d69d-121">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="5d69d-122">“管理 BitLocker”</span><span class="sxs-lookup"><span data-stu-id="5d69d-122">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="5d69d-123">本节包含为硬盘启用 BitLocker 加密的组织的建议。</span><span class="sxs-lookup"><span data-stu-id="5d69d-123">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="5d69d-124">有关详细信息，请参阅  [BitLocker 恢复指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="5d69d-124">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="5d69d-125">如果在删除和替换 SSD 期间禁用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="5d69d-125">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="5d69d-126">如果在删除和替换 SSD 之前设备可以未加密，请按照以下步骤关闭 BitLocker：</span><span class="sxs-lookup"><span data-stu-id="5d69d-126">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="5d69d-127">在 **"设置**"中，键入**BitLocker，** 然后选择 **"管理 BitLocker"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-127">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="5d69d-128">选择 **"关闭 BitLocker"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-128">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="5d69d-129">关闭设备。</span><span class="sxs-lookup"><span data-stu-id="5d69d-129">Power down the device.</span></span> 

### <span data-ttu-id="5d69d-130">如果在删除和替换 SSD 期间启用了 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="5d69d-130">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="5d69d-131">如果在删除和替换 SSD 之前对设备进行了加密，请按照以下步骤生成 BitLocker 恢复密钥并将其保存到 USB 存储：</span><span class="sxs-lookup"><span data-stu-id="5d69d-131">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="5d69d-132">在 **"设置**"中，键入**BitLocker。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-132">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="5d69d-133">选择 **"管理 BitLocker**  > **生成 BitLocker 恢复密钥"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-133">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="5d69d-134">插入 U 盘。</span><span class="sxs-lookup"><span data-stu-id="5d69d-134">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="5d69d-135">将恢复密钥保存到 USB 存储。</span><span class="sxs-lookup"><span data-stu-id="5d69d-135">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="5d69d-136">删除 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="5d69d-136">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="5d69d-137">关闭设备。</span><span class="sxs-lookup"><span data-stu-id="5d69d-137">Power down the device.</span></span> 

## <span data-ttu-id="5d69d-138">删除和替换 SSD</span><span class="sxs-lookup"><span data-stu-id="5d69d-138">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="5d69d-139">使用 [RSSD](https://www.microsoft.com/download/100440)企业版删除指南中包含的设备的适当说明删除 SSD。</span><span class="sxs-lookup"><span data-stu-id="5d69d-139">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="5d69d-140">将原始 SSD 放入新设备，将新设备连接到有线 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="5d69d-140">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="5d69d-141">打开新设备的电源。</span><span class="sxs-lookup"><span data-stu-id="5d69d-141">Power on the new device.</span></span> <span data-ttu-id="5d69d-142">设备可能在启动期间完成固件更新。</span><span class="sxs-lookup"><span data-stu-id="5d69d-142">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="5d69d-143">删除和替换 SSD 后</span><span class="sxs-lookup"><span data-stu-id="5d69d-143">After SSD removal and replacement</span></span>

### <span data-ttu-id="5d69d-144">管理未加密的 SSD</span><span class="sxs-lookup"><span data-stu-id="5d69d-144">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="5d69d-145">如果在传输过程中 SSD 未加密，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5d69d-145">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="5d69d-146">转到 **"登录选项**密码 (由左侧按钮图标表示  >  \*\*\*\*) 。</span><span class="sxs-lookup"><span data-stu-id="5d69d-146">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="5d69d-147">输入密码并登录，等待双重身份验证 (如果适用) 。</span><span class="sxs-lookup"><span data-stu-id="5d69d-147">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="5d69d-148">完全登录后，转到"开始\*\*\*\*  >  **帐户**  >  **注销"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-148">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="5d69d-149">使用密码重新登录，在系统提示时设置 Windows Hello 和 PIN。</span><span class="sxs-lookup"><span data-stu-id="5d69d-149">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="5d69d-150">如果设备已禁用 BitLocker 以便于删除和替换 SSD，并且你想要在替换后启用 BitLocker，请转到**BitLocker**  >  **管理 BitLocker**  >  **Resume BitLocker。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-150">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="5d69d-151">运行 [Microsoft Surface Diagnostic Toolkit for Business (](surface-diagnostic-toolkit-for-business-intro.md) SDT) 验证完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="5d69d-151">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="5d69d-152">通过导航到"设置激活"\*\*\*\* 检查 Windows  >  **激活**。</span><span class="sxs-lookup"><span data-stu-id="5d69d-152">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="5d69d-153">如果看到任何错误消息，请选择"疑难**解答"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-153">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="5d69d-154">通过打开 Office 应用来检查**Office**帐户，导航到"**文件**帐户  >  \*\*\*\*"，然后检查是否有错误消息。</span><span class="sxs-lookup"><span data-stu-id="5d69d-154">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="5d69d-155">管理加密的 SSD</span><span class="sxs-lookup"><span data-stu-id="5d69d-155">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="5d69d-156">你必须有第二个设备来读取保存在 USB 驱动器上的 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="5d69d-156">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="5d69d-157">如果在传输过程中对 SSD 进行了加密，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5d69d-157">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="5d69d-158">将包含 BitLocker 恢复密钥的 USB 驱动器插入第二台设备。</span><span class="sxs-lookup"><span data-stu-id="5d69d-158">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="5d69d-159">打开包含 Bitlocker 恢复密钥的 .txt 文件。</span><span class="sxs-lookup"><span data-stu-id="5d69d-159">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="5d69d-160">在包含原始 SSD 的新设备上手动输入 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="5d69d-160">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="5d69d-161">成功输入 BitLocker 恢复密钥后，转到"登录\*\*\*\* 选项密码" (左侧按钮图标  >  \*\*\*\* 表示) 。</span><span class="sxs-lookup"><span data-stu-id="5d69d-161">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="5d69d-162">输入密码并登录，等待双重身份验证 (（如果适用) ）。</span><span class="sxs-lookup"><span data-stu-id="5d69d-162">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="5d69d-163">完全登录后，转到"开始\*\*\*\*  >  **帐户**  >  **注销"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-163">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="5d69d-164">使用密码重新登录，然后设置 Windows Hello 并添加 PIN。</span><span class="sxs-lookup"><span data-stu-id="5d69d-164">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="5d69d-165">如果设备已禁用 BitLocker 以便于删除和替换 SSD，并且如果你想要在替换后启用 BitLocker，请转到"**设置**  >  **BitLocker**管理  >  **BitLocker**  >  **恢复 BitLocker"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-165">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="5d69d-166">运行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以验证完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="5d69d-166">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="5d69d-167">若要检查 Windows 激活，请选择"**设置**  >  **激活"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-167">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="5d69d-168">如果看到任何错误消息，请选择"疑难**解答"。**</span><span class="sxs-lookup"><span data-stu-id="5d69d-168">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="5d69d-169">若要检查 Office 帐户的状态，请打开**Office 应用程序**，然后转到\*\*\*\*"文件帐户"  >  \*\*\*\* 以检查是否有错误消息。</span><span class="sxs-lookup"><span data-stu-id="5d69d-169">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="5d69d-170">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="5d69d-170">Learn more</span></span>

- [<span data-ttu-id="5d69d-171">适用于企业的 rSSD 删除指南</span><span class="sxs-lookup"><span data-stu-id="5d69d-171">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="5d69d-172">BitLocker 恢复指南</span><span class="sxs-lookup"><span data-stu-id="5d69d-172">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="5d69d-173">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="5d69d-173">Still need help?</span></span> <span data-ttu-id="5d69d-174">转到 [Microsoft 社区](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="5d69d-174">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
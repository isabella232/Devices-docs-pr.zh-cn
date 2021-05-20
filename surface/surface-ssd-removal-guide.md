---
title: 兼容 Surface 设备中的 SSD 删除
description: 本文面向合格的 IT 技术人员，介绍了有关在 Surface Laptop 4、Surface Laptop 3、Surface Pro 7+、Surface Pro X 和 Surface Laptop Go 中删除和替换 SSD 的建议最佳做法。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576902"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a><span data-ttu-id="dc487-103">从兼容的 Surface 设备删除 SSD 的最佳实践</span><span class="sxs-lookup"><span data-stu-id="dc487-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc487-104">本文仅供企业组织中合格的 IT 技术人员使用。</span><span class="sxs-lookup"><span data-stu-id="dc487-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="dc487-105">它介绍了推荐的最佳实践，供合格的 IT 技术人员在删除和替换以下兼容 Surface 设备中的 SSD 时使用：</span><span class="sxs-lookup"><span data-stu-id="dc487-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="dc487-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="dc487-106">Surface Pro 7+</span></span>
- <span data-ttu-id="dc487-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="dc487-107">Surface Pro X</span></span>
- <span data-ttu-id="dc487-108">Surface Laptop转到</span><span class="sxs-lookup"><span data-stu-id="dc487-108">Surface Laptop Go</span></span>
- <span data-ttu-id="dc487-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="dc487-109">Surface Laptop 3</span></span>
- <span data-ttu-id="dc487-110">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="dc487-110">Surface Laptop 4</span></span>

> [!WARNING]
> <span data-ttu-id="dc487-111">打开设备和更换设备组件可能会带来电力振动、设备损坏、火灾和个人危害风险以及其他危险。</span><span class="sxs-lookup"><span data-stu-id="dc487-111">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="dc487-112">执行此类活动时始终要谨慎。</span><span class="sxs-lookup"><span data-stu-id="dc487-112">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="dc487-113">请按照[rSSD](https://www.microsoft.com/download/100440)删除指南中确定的安全预防措施Enterprise。</span><span class="sxs-lookup"><span data-stu-id="dc487-113">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="dc487-114">如果您无法遵循"rSSD 删除指南 for Enterprise"中指定的安全预防措施和过程，建议您获得专业协助。</span><span class="sxs-lookup"><span data-stu-id="dc487-114">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc487-115">必备条件</span><span class="sxs-lookup"><span data-stu-id="dc487-115">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc487-116">本文假定您了解"rSSD 删除指南 for Enterprise"中介绍的一般安全预防措施和安全策略和过程。</span><span class="sxs-lookup"><span data-stu-id="dc487-116">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prepare-for-ssd-removal"></a><span data-ttu-id="dc487-117">准备删除 SSD</span><span class="sxs-lookup"><span data-stu-id="dc487-117">Prepare for SSD removal</span></span> 

### <a name="install-the-latest-updates"></a><span data-ttu-id="dc487-118">安装最新更新</span><span class="sxs-lookup"><span data-stu-id="dc487-118">Install the latest updates</span></span> 

<span data-ttu-id="dc487-119">开始之前，请确保您的 Windows已安装最新更新：</span><span class="sxs-lookup"><span data-stu-id="dc487-119">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="dc487-120">转到"**开始**  >  **设置**  >  **更新&安全"，** 然后选择"**检查更新"。**</span><span class="sxs-lookup"><span data-stu-id="dc487-120">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="dc487-121">安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="dc487-121">Install all available updates.</span></span>
3. <span data-ttu-id="dc487-122">验证访问设备所需的任何密码。</span><span class="sxs-lookup"><span data-stu-id="dc487-122">Verify any passwords that are necessary to access the device.</span></span>  
 
## <a name="manage-bitlocker"></a><span data-ttu-id="dc487-123">“管理 BitLocker”</span><span class="sxs-lookup"><span data-stu-id="dc487-123">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="dc487-124">本节包含针对已启用硬盘加密BitLocker组织的建议。</span><span class="sxs-lookup"><span data-stu-id="dc487-124">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="dc487-125">有关详细信息，请参阅恢复[BitLocker指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="dc487-125">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="dc487-126">如果在BitLocker和替换 SSD 期间禁用加密</span><span class="sxs-lookup"><span data-stu-id="dc487-126">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="dc487-127">如果在删除和替换 SSD 之前设备可以未加密，请按照以下步骤关闭BitLocker：</span><span class="sxs-lookup"><span data-stu-id="dc487-127">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="dc487-128">在**设置**中，键入 **"BitLocker"，** 然后选择"管理**BitLocker"。**</span><span class="sxs-lookup"><span data-stu-id="dc487-128">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="dc487-129">选择 **"关闭BitLocker"。**</span><span class="sxs-lookup"><span data-stu-id="dc487-129">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="dc487-130">关闭设备电源。</span><span class="sxs-lookup"><span data-stu-id="dc487-130">Power down the device.</span></span> 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="dc487-131">如果在BitLocker和替换 SSD 期间启用加密</span><span class="sxs-lookup"><span data-stu-id="dc487-131">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="dc487-132">如果在删除和替换 SSD 之前对设备进行了加密，请按照以下步骤生成一个BitLocker密钥并将其保存到 USB 存储：</span><span class="sxs-lookup"><span data-stu-id="dc487-132">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="dc487-133">在**设置**中，键入**BitLocker**。</span><span class="sxs-lookup"><span data-stu-id="dc487-133">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="dc487-134">选择 **"管理BitLocker**  > **生成BitLocker密钥"。**</span><span class="sxs-lookup"><span data-stu-id="dc487-134">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="dc487-135">插入 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="dc487-135">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="dc487-136">将恢复密钥保存到 USB 存储。</span><span class="sxs-lookup"><span data-stu-id="dc487-136">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="dc487-137">删除 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="dc487-137">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="dc487-138">关闭设备电源。</span><span class="sxs-lookup"><span data-stu-id="dc487-138">Power down the device.</span></span> 

## <a name="remove-and-replace-ssd"></a><span data-ttu-id="dc487-139">删除和替换 SSD</span><span class="sxs-lookup"><span data-stu-id="dc487-139">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="dc487-140">使用 rSSD 删除指南中针对你的设备（适用于[Enterprise）删除 SSD。](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="dc487-140">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="dc487-141">将原始 SSD 放入新设备，将新设备连接到有线 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="dc487-141">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="dc487-142">打开新设备电源。</span><span class="sxs-lookup"><span data-stu-id="dc487-142">Power on the new device.</span></span> <span data-ttu-id="dc487-143">设备可能在启动期间经历固件更新。</span><span class="sxs-lookup"><span data-stu-id="dc487-143">The device may go through a firmware update during startup.</span></span>  
 
## <a name="after-ssd-removal-and-replacement"></a><span data-ttu-id="dc487-144">删除和替换 SSD 后</span><span class="sxs-lookup"><span data-stu-id="dc487-144">After SSD removal and replacement</span></span>

### <a name="manage-unencrypted-ssds"></a><span data-ttu-id="dc487-145">管理未加密的 SSD</span><span class="sxs-lookup"><span data-stu-id="dc487-145">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="dc487-146">如果在传输过程中 SSD 未加密，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="dc487-146">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="dc487-147">转到**登录选项 密码** (由左侧密钥图标  >  \*\*\*\* 表示) 。</span><span class="sxs-lookup"><span data-stu-id="dc487-147">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="dc487-148">输入密码并登录，等待双重身份验证 (如果适用) 。</span><span class="sxs-lookup"><span data-stu-id="dc487-148">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="dc487-149">完全登录后，转到开始\*\*\*\*  >  **帐户**  >  **注销**。</span><span class="sxs-lookup"><span data-stu-id="dc487-149">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="dc487-150">使用密码重新登录，并设置Windows Hello 和 PIN。</span><span class="sxs-lookup"><span data-stu-id="dc487-150">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="dc487-151">如果设备已BitLocker，以方便删除和替换 SSD，并且你想要在替换后启用 BitLocker，请转到 BitLocker\*\*\*\* 管理 BitLocker Resume  >  \*\*\*\*  >  **BitLocker**。</span><span class="sxs-lookup"><span data-stu-id="dc487-151">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="dc487-152">运行[Microsoft Surface Diagnostic Toolkit for Business (](surface-diagnostic-toolkit-for-business-intro.md) SDT) 验证完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="dc487-152">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="dc487-153">通过导航Windows"激活"**来检查设置**  >  **激活。**</span><span class="sxs-lookup"><span data-stu-id="dc487-153">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="dc487-154">如果看到任何错误消息，请选择"疑难**解答"。**</span><span class="sxs-lookup"><span data-stu-id="dc487-154">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="dc487-155">通过打开 Office App 检查 Office**帐户，导航**到"文件""帐户"，\*\*\*\*  >  \*\*\*\* 然后检查是否有错误消息。</span><span class="sxs-lookup"><span data-stu-id="dc487-155">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <a name="managing-encrypted-ssds"></a><span data-ttu-id="dc487-156">管理加密的 SSD</span><span class="sxs-lookup"><span data-stu-id="dc487-156">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="dc487-157">你将必须拥有另一台设备来读取BitLocker U 盘上保存的恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="dc487-157">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="dc487-158">如果在传输过程中对 SSD 进行了加密，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="dc487-158">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="dc487-159">将包含恢复密钥BitLocker U 盘插入第二台设备。</span><span class="sxs-lookup"><span data-stu-id="dc487-159">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="dc487-160">打开.txt Bitlocker 恢复密钥的密钥文件。</span><span class="sxs-lookup"><span data-stu-id="dc487-160">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="dc487-161">在包含BitLocker SSD 的新设备上手动输入恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="dc487-161">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="dc487-162">成功输入恢复密钥BitLocker，转到"登录选项""密码" (\*\*\*\* 左侧的密钥图标  >  \*\*\*\* 表示) 。</span><span class="sxs-lookup"><span data-stu-id="dc487-162">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="dc487-163">输入密码并登录，等待双重身份验证 (如果适用) 。</span><span class="sxs-lookup"><span data-stu-id="dc487-163">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="dc487-164">完全登录后，转到开始\*\*\*\*  >  **帐户**  >  **注销**。</span><span class="sxs-lookup"><span data-stu-id="dc487-164">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="dc487-165">使用密码重新登录，然后设置 Windows Hello 并添加 PIN。</span><span class="sxs-lookup"><span data-stu-id="dc487-165">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="dc487-166">如果设备已禁用BitLocker以便删除和替换 SSD，并且如果你想要在替换后启用 BitLocker，请转到 设置\*\*\*\*  >  **BitLocker**  >  **管理**BitLocker  >  **Resume BitLocker**。</span><span class="sxs-lookup"><span data-stu-id="dc487-166">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="dc487-167">运行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以验证完整的设备功能。</span><span class="sxs-lookup"><span data-stu-id="dc487-167">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="dc487-168">若要检查Windows激活 **，请选择"设置**  >  **激活"。**</span><span class="sxs-lookup"><span data-stu-id="dc487-168">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="dc487-169">如果看到任何错误消息，请选择"疑难**解答"。**</span><span class="sxs-lookup"><span data-stu-id="dc487-169">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="dc487-170">To check the status of the Office account， open the **Office App**， then go to **File**  >  **Account** to check for any error messages.</span><span class="sxs-lookup"><span data-stu-id="dc487-170">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <a name="learn-more"></a><span data-ttu-id="dc487-171">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="dc487-171">Learn more</span></span>

- [<span data-ttu-id="dc487-172">rSSD 删除指南Enterprise</span><span class="sxs-lookup"><span data-stu-id="dc487-172">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="dc487-173">BitLocker 恢复指南</span><span class="sxs-lookup"><span data-stu-id="dc487-173">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="dc487-174">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="dc487-174">Still need help?</span></span> <span data-ttu-id="dc487-175">转到[Microsoft Community](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="dc487-175">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
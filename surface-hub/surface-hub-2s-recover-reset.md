---
title: Surface Hub 2S 的重置和恢复
description: 了解如何恢复和重置 Surface Hub 2S。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 64ceee291d3d3e067f581707d9431fa92398c785
ms.sourcegitcommit: ecb4909c091e69b7bdb1faacfc8c34b480dc884b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11342972"
---
# <span data-ttu-id="8cd5e-104">Surface Hub 2S 的重置和恢复</span><span class="sxs-lookup"><span data-stu-id="8cd5e-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="8cd5e-105">如果 Surface Hub 2S 遇到问题，可以使用 USB 驱动器将设备重置为出厂设置或还原。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="8cd5e-106">若要开始，使用管理员凭据登录 Surface Hub 2S，打开"\*\*\*\* 设置"应用，选择"&**安全**"，然后选择"**恢复"。**</span><span class="sxs-lookup"><span data-stu-id="8cd5e-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="8cd5e-107">重置设备</span><span class="sxs-lookup"><span data-stu-id="8cd5e-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="8cd5e-108">在重置设备之前，请确保你的 BitLocker 密钥可用，因为稍后会提示你输入它。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="8cd5e-109">若要了解更多信息，请参阅["保存 BitLocker 密钥"。](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="8cd5e-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="8cd5e-110">若要重置设备，请选择"**开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="8cd5e-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="8cd5e-111">当显示 **"准备重置此设备"** 窗口时，选择"**重置"。**</span><span class="sxs-lookup"><span data-stu-id="8cd5e-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="8cd5e-112">当集线器重新启动到恢复分区时，它将提示你输入 BitLocker 密钥。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="8cd5e-113">跳过该提示将导致重置失败。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="8cd5e-114">输入 BitLocker 密钥后，Hub 会从恢复分区重新安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="8cd5e-115">这可能需要一个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="8cd5e-116">若要重新配置设备，请运行第一次安装程序。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="8cd5e-117">如果使用 Microsoft Intune 或其他移动设备管理解决方案管理设备，请停用并删除以前的记录，然后重新注册新设备。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="8cd5e-118">有关详细信息，请参阅使用擦除、停用或手动注销设备来 [删除设备](https://docs.microsoft.com/intune/devices-wipe)。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Surface Hub 2S 的重置和恢复*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="8cd5e-120">图 1.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-120">Figure 1.</span></span> <span data-ttu-id="8cd5e-121">Surface Hub 2S 的重置和恢复</span><span class="sxs-lookup"><span data-stu-id="8cd5e-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="8cd5e-122">使用 USB 恢复驱动器恢复 Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="8cd5e-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="8cd5e-123">Surface Hub 2S 中的新增功能，现在可以使用恢复映像重新安装设备。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="8cd5e-124">从 U 盘恢复</span><span class="sxs-lookup"><span data-stu-id="8cd5e-124">Recovery from a USB drive</span></span>

<span data-ttu-id="8cd5e-125">使用 Surface Hub 2S，可以使用恢复映像重新安装设备。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="8cd5e-126">通过执行此操作，如果你丢失了 BitLocker 密钥，或者如果你不再具有"设置"应用的管理员凭据，你可以将设备重新安装到出厂设置。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="8cd5e-127">使用存储大小为 8 GB 或 16 GB 的 USB 3.0 驱动器，格式化为 FAT32。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="8cd5e-128">从单独的电脑中，从 [Surface Recovery](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 网站下载 .zip 文件恢复映像，然后返回到这些说明。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="8cd5e-129">在任务栏上的搜索框中，输入**恢复驱动器**，然后从结果中选择"创建\*\*\*\* 恢复**驱动器"或**"恢复驱动器"。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-129">In the search box on the taskbar, enter **recovery drive**, and then select **Create a recovery drive** or **Recovery Drive** from the results.</span></span> <span data-ttu-id="8cd5e-130">你可能需要输入管理员密码或确认你的选择。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-130">You may need to enter an admin password or confirm your choice.</span></span>

1. <span data-ttu-id="8cd5e-131">在 **"用户帐户控制"框中**，选择 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="8cd5e-131">In the **User Account Control** box, select **Yes**.</span></span>

1. <span data-ttu-id="8cd5e-132">确保清除"**将系统文件备份到恢复**驱动器"复选框，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="8cd5e-132">Make sure to clear the **Back up system files to the recovery drive** check box and then select **Next**.</span></span>

1. <span data-ttu-id="8cd5e-133">选择你的 USB 驱动器，然后选择"下一>**创建"。**</span><span class="sxs-lookup"><span data-stu-id="8cd5e-133">Select your USB drive, and then select **Next > Create**.</span></span>  <span data-ttu-id="8cd5e-134">某些实用程序需要复制到恢复驱动器，因此这可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-134">Some utilities need to be copied to the recovery drive, so this might take a few minutes.</span></span>

1. <span data-ttu-id="8cd5e-135">恢复驱动器准备就绪后，选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="8cd5e-135">When the recovery drive is ready, select **Finish**.</span></span>

1. <span data-ttu-id="8cd5e-136">双击之前下载的恢复映像 .zip 文件以打开它。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-136">Double-click the recovery image .zip file that you previously downloaded to open it.</span></span>

1. <span data-ttu-id="8cd5e-137">从恢复映像文件夹中选择所有文件，将其复制到 USB 驱动器的根目录，然后选择"选择 **"替换目标中的文件**。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-137">Select all the files from the recovery image folder, copy them to the root of your USB drive, and then select **Choose to replace the files in the destination**.</span></span>

1. <span data-ttu-id="8cd5e-138">文件复制完成后，选择任务栏上的" **安全删除硬件** 和弹出媒体"图标，然后删除 U 盘。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-138">Once the files have finished copying, select the **Safely Remove Hardware and Eject Media** icon on the taskbar, and remove your USB drive.</span></span>

1. <span data-ttu-id="8cd5e-139">将 USB 驱动器连接到 Surface Hub 2S 上的任何 USB-C 或 USB-A 端口。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-139">Connect the USB drive to any USB-C or USB-A port on the Surface Hub 2S.</span></span>

1. <span data-ttu-id="8cd5e-140">关闭集线器，然后执行以下步骤从 USB 驱动器启动：</span><span class="sxs-lookup"><span data-stu-id="8cd5e-140">Turn off the Hub and then take these steps to boot from the USB drive:</span></span>

   1. <span data-ttu-id="8cd5e-141">按下"音量"按钮时，按电源按钮。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-141">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="8cd5e-142">继续按这两个按钮，直到看到 Windows 徽标。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-142">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="8cd5e-143">释放电源按钮，但继续按住音量降低按钮，直到安装 UI 开始。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-143">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*使用音量降低和电源按钮启动恢复*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="8cd5e-145">图 2.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-145">Figure 2.</span></span> <span data-ttu-id="8cd5e-146">"音量"和"电源"按钮</span><span class="sxs-lookup"><span data-stu-id="8cd5e-146">Volume and Power buttons</span></span>*

1. <span data-ttu-id="8cd5e-147">在语言选择屏幕上，选择 Surface Hub 2S 的显示语言。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-147">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="8cd5e-148">选择 **"从驱动器恢复**并**完全清理驱动器"，** 然后选择"**恢复"。**</span><span class="sxs-lookup"><span data-stu-id="8cd5e-148">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="8cd5e-149">如果系统提示你输入 BitLocker 密钥，请选择 **"跳过此驱动器"。**</span><span class="sxs-lookup"><span data-stu-id="8cd5e-149">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="8cd5e-150">Surface Hub 2S 重新启动多次，大约需要 30 分钟才能完成恢复过程。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-150">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="8cd5e-151">首次显示设置屏幕时，删除 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-151">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="8cd5e-152">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="8cd5e-152">Contact Support</span></span>

<span data-ttu-id="8cd5e-153">如果你有问题或需要帮助，可以创建 [支持请求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="8cd5e-153">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>

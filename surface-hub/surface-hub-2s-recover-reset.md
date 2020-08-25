---
title: Surface Hub 2 的重置和恢复
description: 了解如何恢复和重置 Surface Hub 2。
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
ms.openlocfilehash: 7d79fab22b62e6ef29832be6241c484e9caf72e0
ms.sourcegitcommit: 537fa38bdd21fcd679af0764e734f4b8efb6a03f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "10959944"
---
# <span data-ttu-id="e8131-104">Surface Hub 2 的重置和恢复</span><span class="sxs-lookup"><span data-stu-id="e8131-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="e8131-105">如果你遇到 Surface Hub 2 的问题，你可以将设备重置为出厂设置或使用 USB 驱动器还原。</span><span class="sxs-lookup"><span data-stu-id="e8131-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="e8131-106">若要开始，请通过管理员凭据登录到 Surface Hub 2，打开 " **设置** " 应用，选择 " **更新 & 安全**"，然后选择 " **恢复**"。</span><span class="sxs-lookup"><span data-stu-id="e8131-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="e8131-107">重置设备</span><span class="sxs-lookup"><span data-stu-id="e8131-107">Reset the device</span></span>

1. <span data-ttu-id="e8131-108">若要重置设备，请选择 " **开始**"。</span><span class="sxs-lookup"><span data-stu-id="e8131-108">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="e8131-109">出现 " **准备重置此设备** " 窗口时，选择 " **重置**"。</span><span class="sxs-lookup"><span data-stu-id="e8131-109">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!NOTE]
   > <span data-ttu-id="e8131-110">Surface Hub 2 从恢复分区重新安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="e8131-110">Surface Hub 2S reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="e8131-111">这可能需要长达一小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="e8131-111">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="e8131-112">若要重新配置设备，请运行第一次设置程序。</span><span class="sxs-lookup"><span data-stu-id="e8131-112">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="e8131-113">如果你使用 Microsoft Intune 或其他移动设备管理解决方案管理设备，请停用并删除以前的记录，然后重新注册新设备。</span><span class="sxs-lookup"><span data-stu-id="e8131-113">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="e8131-114">有关详细信息，请参阅 [使用擦除、停用或手动通过设备删除设备](https://docs.microsoft.com/intune/devices-wipe)。</span><span class="sxs-lookup"><span data-stu-id="e8131-114">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

> [!div class="mx-imgBorder"]
> ![\* Surface Hub 2 的重置和恢复 \*](images/sh2-reset.png)
<br/>*<span data-ttu-id="e8131-116">图 1.</span><span class="sxs-lookup"><span data-stu-id="e8131-116">Figure 1.</span></span> <span data-ttu-id="e8131-117">Surface Hub 2 的重置和恢复</span><span class="sxs-lookup"><span data-stu-id="e8131-117">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="e8131-118">使用 USB 恢复驱动器恢复 Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="e8131-118">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="e8131-119">新增在 Surface Hub 2 中，现在可以使用恢复映像重新安装设备。</span><span class="sxs-lookup"><span data-stu-id="e8131-119">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="e8131-120">从 USB 驱动器恢复</span><span class="sxs-lookup"><span data-stu-id="e8131-120">Recovery from a USB drive</span></span>

<span data-ttu-id="e8131-121">使用 Surface Hub 2，您可以使用恢复映像重新安装该设备。</span><span class="sxs-lookup"><span data-stu-id="e8131-121">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="e8131-122">通过执行此操作，你可以将设备重新安装到出厂设置（如果你丢失 BitLocker 密钥），或者你不再拥有设置应用的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="e8131-122">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="e8131-123">使用具有 8 GB 或 16 GB 存储空间的 USB 3.0 驱动器，格式为 FAT32。</span><span class="sxs-lookup"><span data-stu-id="e8131-123">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="e8131-124">从单独的 PC 上，从 [Surface recovery 网站](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 下载 .zip 文件恢复映像，然后返回这些说明。</span><span class="sxs-lookup"><span data-stu-id="e8131-124">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="e8131-125">将下载的文件解压缩到 USB 驱动器的根目录。</span><span class="sxs-lookup"><span data-stu-id="e8131-125">Unzip the downloaded file onto the root of the USB drive.</span></span>  

1. <span data-ttu-id="e8131-126">将 USB 驱动器连接到 Surface Hub 2 上的任何 USB 或 USB 端口。</span><span class="sxs-lookup"><span data-stu-id="e8131-126">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>

1. <span data-ttu-id="e8131-127">关闭设备：</span><span class="sxs-lookup"><span data-stu-id="e8131-127">Turn off the device:</span></span>

   1. <span data-ttu-id="e8131-128">按 "调高音量" 按钮时，按 "电源" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e8131-128">While pressing the Volume up button, press the Power button.</span></span>
   1. <span data-ttu-id="e8131-129">继续按两个按钮，直到看到 Windows 徽标。</span><span class="sxs-lookup"><span data-stu-id="e8131-129">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="e8131-130">释放电源按钮，但继续按住音量按钮，直到安装 UI 开始。</span><span class="sxs-lookup"><span data-stu-id="e8131-130">Release the Power button but continue to hold the Volume up button until the Install UI begins.</span></span>

   ![\* 使用 "音量" 和 "电源" 按钮启动恢复 \*](images/sh2-keypad.png) <br>
   **<span data-ttu-id="e8131-132">图 2.</span><span class="sxs-lookup"><span data-stu-id="e8131-132">Figure 2.</span></span> <span data-ttu-id="e8131-133">音量和电源按钮</span><span class="sxs-lookup"><span data-stu-id="e8131-133">Volume and Power buttons</span></span>**

1. <span data-ttu-id="e8131-134">在 "语言选择" 屏幕上，选择 Surface Hub 2 秒的显示语言。</span><span class="sxs-lookup"><span data-stu-id="e8131-134">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="e8131-135">选择 " **从驱动器恢复** " 并 **完全清理驱动器**，然后选择 " **恢复**"。</span><span class="sxs-lookup"><span data-stu-id="e8131-135">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="e8131-136">如果系统提示你输入 BitLocker 密钥，请选择 " **跳过此驱动器**"。</span><span class="sxs-lookup"><span data-stu-id="e8131-136">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="e8131-137">Surface Hub 2 秒重启几次，完成恢复过程大约需要30分钟。</span><span class="sxs-lookup"><span data-stu-id="e8131-137">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="e8131-138">出现首次设置屏幕时，请删除 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="e8131-138">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="e8131-139">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="e8131-139">Contact Support</span></span>

<span data-ttu-id="e8131-140">如果有疑问或需要帮助，您可以 [创建支持请求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="e8131-140">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>

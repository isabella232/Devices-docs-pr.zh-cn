---
title: 适用于 Surface Pro 3 (Surface) 的高级 UEFI 安全功能
description: 本文介绍了如何安装和配置 v3.11.760.0 UEFI 更新，以便针对 Surface Pro 3 设备启用其他安全选项。
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: 安全, 功能, 配置, 硬件, 设备, 自定义, 脚本, 更新
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 6a5c53c3e161bd4c49069a0665896762ce587618
ms.sourcegitcommit: e9190a6fe68b8a7cd9b024aea4be9f885f0de388
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163185"
---
# <span data-ttu-id="90f09-104">适用于 Surface Pro 3 的高级 UEFI 安全功能</span><span class="sxs-lookup"><span data-stu-id="90f09-104">Advanced UEFI security features for Surface Pro 3</span></span>


<span data-ttu-id="90f09-105">本文介绍了如何安装和配置 v3.11.760.0 UEFI 更新，以便针对 Surface Pro 3 设备启用其他安全选项。</span><span class="sxs-lookup"><span data-stu-id="90f09-105">This article describes how to install and configure the v3.11.760.0 UEFI update to enable additional security options for Surface Pro 3 devices.</span></span>

<span data-ttu-id="90f09-106">为了解决对 Surface 设备安全的更细化的控制，v3.11.760.0 UEF 更新提供了其他安全选项，可使你禁用特定的硬件设备或阻止这些设备启动。</span><span class="sxs-lookup"><span data-stu-id="90f09-106">To address more granular control over the security of Surface devices, the v3.11.760.0 UEFI update provides additional security options that allow you to disable specific hardware devices or to prevent starting from those devices.</span></span> <span data-ttu-id="90f09-107">在设备上安装 UEFI 更新后，你可以手动配置它，也可以通过运行脚本自动进行配置。</span><span class="sxs-lookup"><span data-stu-id="90f09-107">After the UEFI update is installed on a device, you can configure it manually or automatically by running a script.</span></span>

## <span data-ttu-id="90f09-108">手动安装 UEFI 更新</span><span class="sxs-lookup"><span data-stu-id="90f09-108">Manually install the UEFI update</span></span>


<span data-ttu-id="90f09-109">必须先安装 v3.11.760.0 UEFI 更新，然后你才可以配置你的 Surface 设备的高级安全功能。</span><span class="sxs-lookup"><span data-stu-id="90f09-109">Before you can configure the advanced security features of your Surface device, you must first install the v3.11.760.0 UEFI update.</span></span> <span data-ttu-id="90f09-110">如果你从 Windows 更新接收更新，此更新将自动安装。</span><span class="sxs-lookup"><span data-stu-id="90f09-110">This update is installed automatically if you receive your updates from Windows Update.</span></span> <span data-ttu-id="90f09-111">有关如何将 Windows 配置为使用 Windows 更新自动更新的详细信息，请参阅[如何配置和使用 Windows 中的自动更新](https://support.microsoft.com/kb/306525)。</span><span class="sxs-lookup"><span data-stu-id="90f09-111">For more information about how to configure Windows to update automatically by using Windows Update, see [How to configure and use Automatic Updates in Windows](https://support.microsoft.com/kb/306525).</span></span>

<span data-ttu-id="90f09-112">若要更新 Surface Pro 3 上的 UEFI，你可以下载并安装作为 Surface Pro 3 固件和驱动程序包一部分的 Surface UEFI 更新。</span><span class="sxs-lookup"><span data-stu-id="90f09-112">To update the UEFI on Surface Pro 3, you can download and install the Surface UEFI updates as part of the Surface Pro 3 Firmware and Driver Pack.</span></span> <span data-ttu-id="90f09-113">可以从 Microsoft 下载中心上的[Surface Pro 3 页面](https://www.microsoft.com/download/details.aspx?id=38826)获取这些固件和驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="90f09-113">These firmware and driver packs are available from the [Surface Pro 3 page](https://www.microsoft.com/download/details.aspx?id=38826) on the Microsoft Download Center.</span></span> <span data-ttu-id="90f09-114">你可以在[为 Surface 设备下载最新的固件和驱动程序](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)中了解有关固件和驱动程序包的详细信息。</span><span class="sxs-lookup"><span data-stu-id="90f09-114">You can find out more about the firmware and driver packs at [Download the latest firmware and drivers for Surface devices](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span> <span data-ttu-id="90f09-115">将以独立的 Windows Installer (.msi) 和存档 (.zip) 格式提供这些固件和驱动程序包。</span><span class="sxs-lookup"><span data-stu-id="90f09-115">The firmware and driver packs are available as both self-contained Windows Installer (.msi) and archive (.zip) formats.</span></span> <span data-ttu-id="90f09-116">你可以在[管理 Surface 驱动程序和固件更新](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates)中了解有关这两种格式的详细信息以及如何使用它们更新驱动程序。</span><span class="sxs-lookup"><span data-stu-id="90f09-116">You can find out more about these two formats and how you can use them to update your drivers at [Manage Surface driver and firmware updates](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span></span>

## <span data-ttu-id="90f09-117">手动配置其他安全设置</span><span class="sxs-lookup"><span data-stu-id="90f09-117">Manually configure additional security settings</span></span>


>[!NOTE]
><span data-ttu-id="90f09-118">若要进入 Surface 设备上的固件设置，请先关闭设备电源、长按“提高音量”\*\*\*\* 按钮、按下并释放“电源”\*\*\*\* 按钮，然后在设备开始启动后释放“提高音量”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="90f09-118">To enter firmware setup on a Surface device, begin with the device powered off, press and hold the **Volume Up** button, then press and release the **Power** button, then release the **Volume Up** button after the device has begun to boot.</span></span>

<span data-ttu-id="90f09-119">在 Surface 设备上安装 v3.11.760.0 UEFI 更新后，一个名为“高级设备安全”\*\*\*\* 的附加 UEFI 菜单将变为可用。</span><span class="sxs-lookup"><span data-stu-id="90f09-119">After the v3.11.760.0 UEFI update is installed on a Surface device, an additional UEFI menu named **Advanced Device Security** becomes available.</span></span> <span data-ttu-id="90f09-120">如果你单击此菜单，将显示以下选项：</span><span class="sxs-lookup"><span data-stu-id="90f09-120">If you click this menu, the following options are displayed:</span></span>

| <span data-ttu-id="90f09-121">选项</span><span class="sxs-lookup"><span data-stu-id="90f09-121">Option</span></span>         | <span data-ttu-id="90f09-122">描述</span><span class="sxs-lookup"><span data-stu-id="90f09-122">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="90f09-123">可用设置（默认设置以粗体列出）</span><span class="sxs-lookup"><span data-stu-id="90f09-123">Available settings (default listed in bold)</span></span> |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="90f09-124">网络启动</span><span class="sxs-lookup"><span data-stu-id="90f09-124">Network Boot</span></span>   | <span data-ttu-id="90f09-125">启用或禁用从网络启动 Surface 设备的能力（也称为 PXE 启动）。</span><span class="sxs-lookup"><span data-stu-id="90f09-125">Enables or disables the ability of your Surface device to boot from the network (also known as PXE boot).</span></span>                                                                            | <span data-ttu-id="90f09-126">**已启用**、不可启动</span><span class="sxs-lookup"><span data-stu-id="90f09-126">**Enabled**, Not Bootable</span></span>                   |
| <span data-ttu-id="90f09-127">侧 USB</span><span class="sxs-lookup"><span data-stu-id="90f09-127">Side USB</span></span>       | <span data-ttu-id="90f09-128">启用或禁用 Surface 设备一侧的 USB 端口。</span><span class="sxs-lookup"><span data-stu-id="90f09-128">Enables or disables the USB port on the side of the Surface device.</span></span> <span data-ttu-id="90f09-129">此外，USB 端口可启用，但不允许启动。</span><span class="sxs-lookup"><span data-stu-id="90f09-129">Additionally, the USB port can be enabled, but not allow booting.</span></span>                                                | <span data-ttu-id="90f09-130">**已启用**、不可启动、已禁用</span><span class="sxs-lookup"><span data-stu-id="90f09-130">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="90f09-131">插接端口</span><span class="sxs-lookup"><span data-stu-id="90f09-131">Docking Port</span></span>   | <span data-ttu-id="90f09-132">启用或禁用 Surface 扩展坞上的端口。</span><span class="sxs-lookup"><span data-stu-id="90f09-132">Enables or disables the ports on the Surface docking station.</span></span> <span data-ttu-id="90f09-133">此外，插接端口可启用，但阻止从扩展坞中的任何 USB 或以太网端口启动。</span><span class="sxs-lookup"><span data-stu-id="90f09-133">Additionally, the docking port can be enabled, but block booting from any USB or Ethernet port in the docking station.</span></span> | <span data-ttu-id="90f09-134">**已启用**、不可启动、已禁用</span><span class="sxs-lookup"><span data-stu-id="90f09-134">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="90f09-135">前置摄像头</span><span class="sxs-lookup"><span data-stu-id="90f09-135">Front Camera</span></span>   | <span data-ttu-id="90f09-136">启用或禁用 Surface 设备前端的摄像头。</span><span class="sxs-lookup"><span data-stu-id="90f09-136">Enables or disables the camera on the front of the Surface device.</span></span>                                                                                                                   | <span data-ttu-id="90f09-137">**已启用**、已禁用</span><span class="sxs-lookup"><span data-stu-id="90f09-137">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="90f09-138">后置摄像头</span><span class="sxs-lookup"><span data-stu-id="90f09-138">Rear Camera</span></span>    | <span data-ttu-id="90f09-139">启用或禁用 Surface 设备后端的摄像头。</span><span class="sxs-lookup"><span data-stu-id="90f09-139">Enables or disables the camera on the rear of the Surface device.</span></span>                                                                                                                    | <span data-ttu-id="90f09-140">**已启用**、已禁用</span><span class="sxs-lookup"><span data-stu-id="90f09-140">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="90f09-141">板载音频</span><span class="sxs-lookup"><span data-stu-id="90f09-141">On Board Audio</span></span> | <span data-ttu-id="90f09-142">启用或禁用 Surface 设备上的音频。</span><span class="sxs-lookup"><span data-stu-id="90f09-142">Enables or disables audio on the Surface device.</span></span>                                                                                                                                     | <span data-ttu-id="90f09-143">**已启用**、已禁用</span><span class="sxs-lookup"><span data-stu-id="90f09-143">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="90f09-144">microSD</span><span class="sxs-lookup"><span data-stu-id="90f09-144">microSD</span></span>        | <span data-ttu-id="90f09-145">启用或禁用 Surface 设备上的 microSD 卡槽。</span><span class="sxs-lookup"><span data-stu-id="90f09-145">Enables or disables the microSD slot on the Surface device.</span></span>                                                                                                                          | <span data-ttu-id="90f09-146">**已启用**、已禁用</span><span class="sxs-lookup"><span data-stu-id="90f09-146">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="90f09-147">WLAN</span><span class="sxs-lookup"><span data-stu-id="90f09-147">WiFi</span></span>           | <span data-ttu-id="90f09-148">启用或禁用 Surface 设备中的内置 WLAN 收发器。</span><span class="sxs-lookup"><span data-stu-id="90f09-148">Enables or disables the built-in Wi-Fi transceiver in the Surface device.</span></span> <span data-ttu-id="90f09-149">这也将禁用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="90f09-149">This also disables Bluetooth.</span></span>                                                                              | <span data-ttu-id="90f09-150">**已启用**、已禁用</span><span class="sxs-lookup"><span data-stu-id="90f09-150">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="90f09-151">蓝牙</span><span class="sxs-lookup"><span data-stu-id="90f09-151">Bluetooth</span></span>      | <span data-ttu-id="90f09-152">启用或禁用 Surface 设备中的内置蓝牙无线收发器。</span><span class="sxs-lookup"><span data-stu-id="90f09-152">Enables or disables the built-in Bluetooth transceiver in the Surface device.</span></span>                                                                                                        | <span data-ttu-id="90f09-153">**已启用**、已禁用</span><span class="sxs-lookup"><span data-stu-id="90f09-153">**Enabled**, Disabled</span></span>                       |

 

## <span data-ttu-id="90f09-154">自动化其他安全设置</span><span class="sxs-lookup"><span data-stu-id="90f09-154">Automate additional security settings</span></span>


<span data-ttu-id="90f09-155">作为一名具有管理权限的 IT 专业人员，你可以通过利用 Microsoft 下载中心中提供的 [Surface Pro 3 固件工具 (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) 来自动化 UEFI 设置的配置。</span><span class="sxs-lookup"><span data-stu-id="90f09-155">As an IT professional with administrative privileges, you can automate the configuration of UEFI settings by leveraging [Surface Pro 3 Firmware Tools (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) available from the Microsoft Download Center.</span></span> <span data-ttu-id="90f09-156">这些工具将安装可从任何自定义应用程序或脚本调用的 .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="90f09-156">These tools install a .NET assembly that can be called from any custom application or script.</span></span>

**<span data-ttu-id="90f09-157">先决条件</span><span class="sxs-lookup"><span data-stu-id="90f09-157">Prerequisites</span></span>**

-   <span data-ttu-id="90f09-158">下面的示例脚本利用前面提到的扩展，因此假定工具已安装在正在管理的设备上。</span><span class="sxs-lookup"><span data-stu-id="90f09-158">The sample scripts below leverage the previously mentioned extension and therefore assume that the tool has been installed on the device being managed.</span></span>
-   <span data-ttu-id="90f09-159">这些脚本必须使用管理权限进行运行。</span><span class="sxs-lookup"><span data-stu-id="90f09-159">The scripts must be run with administrative privilege.</span></span>
-   <span data-ttu-id="90f09-160">必须先调用 Windows PowerShell 命令 [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx)，然后再运行示例脚本（如果未对它们进行数字签名）。</span><span class="sxs-lookup"><span data-stu-id="90f09-160">The Windows PowerShell command [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) must be called prior to running sample scripts if they are not digitally signed.</span></span>

**<span data-ttu-id="90f09-161">示例脚本</span><span class="sxs-lookup"><span data-stu-id="90f09-161">Sample scripts</span></span>**

> [!NOTE]
> <span data-ttu-id="90f09-162">以下示例脚本中使用的 UEFI 密码将以明文形式提供。</span><span class="sxs-lookup"><span data-stu-id="90f09-162">The UEFI password used in the sample scripts below is presented in clear text.</span></span> <span data-ttu-id="90f09-163">我们强烈建议将脚本保存在受保护的位置中并在受控环境中运行它们。</span><span class="sxs-lookup"><span data-stu-id="90f09-163">We strongly recommend saving the scripts in a protected location and running them in a controlled environment.</span></span>


<span data-ttu-id="90f09-164">显示所有可配置选项：</span><span class="sxs-lookup"><span data-stu-id="90f09-164">Show all configurable options:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

<span data-ttu-id="90f09-165">设置或更改 UEFI 密码：</span><span class="sxs-lookup"><span data-stu-id="90f09-165">Set or change UEFI password:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

<span data-ttu-id="90f09-166">检查建议的更改的状态：</span><span class="sxs-lookup"><span data-stu-id="90f09-166">Check status of proposed changes:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

<span data-ttu-id="90f09-167">将 UEFI 还原为默认值：</span><span class="sxs-lookup"><span data-stu-id="90f09-167">Revert UEFI to default values:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

<span data-ttu-id="90f09-168">状态代码解释</span><span class="sxs-lookup"><span data-stu-id="90f09-168">Status code interpretation</span></span>

-   <span data-ttu-id="90f09-169">00 - 建议的更新成功</span><span class="sxs-lookup"><span data-stu-id="90f09-169">00 - The proposed update was a success</span></span>
-   <span data-ttu-id="90f09-170">02 - 其中一个建议的值具有无效的值</span><span class="sxs-lookup"><span data-stu-id="90f09-170">02 - One of the proposed values had an invalid value</span></span>
-   <span data-ttu-id="90f09-171">03 - 有一个无法识别的建议值集</span><span class="sxs-lookup"><span data-stu-id="90f09-171">03 - There was a proposed value set that was not recognized</span></span>
-   <span data-ttu-id="90f09-172">0F - 解锁密码与当前设置密码不匹配</span><span class="sxs-lookup"><span data-stu-id="90f09-172">0F - The unlock password did not match currently set password</span></span>

 

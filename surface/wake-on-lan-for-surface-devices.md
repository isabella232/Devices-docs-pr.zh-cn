---
title: 'LAN 唤醒 Surface 设备 (Surface) '
description: 了解如何使用 LAN 唤醒 远程唤醒设备以执行管理或维护任务，或自动启用管理解决方案 ，即使设备已断电。
keywords: 更新， 部署， 驱动程序， wol， lan 唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271119"
---
# <span data-ttu-id="d6cfc-104">Surface 设备的 LAN 唤醒</span><span class="sxs-lookup"><span data-stu-id="d6cfc-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="d6cfc-105">运行 Windows 10 版本 1607 (也称为 Windows 10 周年更新) 或更高版本并使用 Surface 以太网适配器连接到有线网络的 Surface 设备能够从连接待机状态LAN 唤醒 (WOL) 。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="d6cfc-106">使用 WOL，你可以远程唤醒设备以执行管理或维护任务，或启用管理解决方案 (如 Microsoft Endpoint Configuration Manager) 自动。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="d6cfc-107">例如，你可以将应用程序部署到与 Surface 扩展坞或 Surface Pro 3 扩展坞一起停靠的 Surface 设备，通过使用 Microsoft Endpoint Configuration Manager 在夜间窗口（当办公室为空时）使用 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="d6cfc-108">Surface 设备必须连接到交流电源，并且处于连接待机模式 (睡眠) WOL。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="d6cfc-109">在休眠或关机的设备中无法使用 WOL。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="d6cfc-110">支持的设备</span><span class="sxs-lookup"><span data-stu-id="d6cfc-110">Supported devices</span></span>

<span data-ttu-id="d6cfc-111">WOL 支持以下设备：</span><span class="sxs-lookup"><span data-stu-id="d6cfc-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="d6cfc-112">Surface 以太网适配器</span><span class="sxs-lookup"><span data-stu-id="d6cfc-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="d6cfc-113">Surface USB-C 到以太网和 USB 适配器</span><span class="sxs-lookup"><span data-stu-id="d6cfc-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="d6cfc-114">Surface 扩展坞</span><span class="sxs-lookup"><span data-stu-id="d6cfc-114">Surface Dock</span></span>
* <span data-ttu-id="d6cfc-115">Surface Pro 3 的 Surface 扩展坞</span><span class="sxs-lookup"><span data-stu-id="d6cfc-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="d6cfc-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="d6cfc-116">Surface 3</span></span>
* <span data-ttu-id="d6cfc-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d6cfc-117">Surface Pro 3</span></span>
* <span data-ttu-id="d6cfc-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="d6cfc-118">Surface Pro 4</span></span>
* <span data-ttu-id="d6cfc-119">Surface Pro (第五代) </span><span class="sxs-lookup"><span data-stu-id="d6cfc-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="d6cfc-120">Surface Pro (第五代) LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="d6cfc-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="d6cfc-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="d6cfc-121">Surface Book</span></span>
* <span data-ttu-id="d6cfc-122">Surface Laptop (第一代) </span><span class="sxs-lookup"><span data-stu-id="d6cfc-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="d6cfc-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="d6cfc-123">Surface Pro 6</span></span>
* <span data-ttu-id="d6cfc-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="d6cfc-124">Surface Book 2</span></span>
* <span data-ttu-id="d6cfc-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="d6cfc-125">Surface Laptop 2</span></span>
* <span data-ttu-id="d6cfc-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="d6cfc-126">Surface Go</span></span>
* <span data-ttu-id="d6cfc-127">带有 LTE Advanced 的 Surface Go</span><span class="sxs-lookup"><span data-stu-id="d6cfc-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="d6cfc-128">Surface Studio 2 (请参阅下面的 Surface Studio 2) </span><span class="sxs-lookup"><span data-stu-id="d6cfc-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="d6cfc-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="d6cfc-129">Surface Pro 7</span></span>
* <span data-ttu-id="d6cfc-130">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="d6cfc-130">Surface Laptop 3</span></span>
* <span data-ttu-id="d6cfc-131">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="d6cfc-131">Surface Laptop Go</span></span>
* <span data-ttu-id="d6cfc-132">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="d6cfc-132">Surface Pro 7+</span></span>

## <span data-ttu-id="d6cfc-133">WOL 驱动程序</span><span class="sxs-lookup"><span data-stu-id="d6cfc-133">WOL driver</span></span>

<span data-ttu-id="d6cfc-134">若要在 Surface 设备上启用 WOL 支持，需要 Surface 以太网适配器的特定驱动程序。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-134">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="d6cfc-135">此驱动程序不包含在 Surface 设备的标准驱动程序和固件包中 ， 你必须单独下载并安装它。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-135">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="d6cfc-136">你可以从 Microsoft 下载中心的 Surface Tools (SurfaceWOL.msi) [下载 Surface](https://www.microsoft.com/download/details.aspx?id=46703) WOL 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-136">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="d6cfc-137">可以在 Surface 设备上运行此 Microsoft Windows Installer (.msi) 文件以安装 Surface WOL 驱动程序，或者可以使用应用程序部署解决方案（如 Microsoft Endpoint Configuration Manager）将其分发到 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-137">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="d6cfc-138">若要在部署过程中包括 Surface WOL 驱动程序，可以在部署过程中将 .msi 文件安装为应用程序。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-138">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="d6cfc-139">还可以提取 Surface WOL 驱动程序文件，以将其包括在部署过程中。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-139">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="d6cfc-140">例如，你可以将它们包括在 Microsoft Deployment Toolkit (MDT) 共享中。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-140">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="d6cfc-141">你可以阅读有关 Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit。](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)</span><span class="sxs-lookup"><span data-stu-id="d6cfc-141">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="d6cfc-142">在安装 SurfaceWOL.msi 时，以下注册表项设置为值 1，这便于识别已安装 WOL 驱动程序的系统。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-142">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="d6cfc-143">如果选择在部署过程中单独提取和安装这些驱动程序，将不会配置此注册表项，并且必须手动或使用脚本进行配置。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-143">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="d6cfc-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="d6cfc-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="d6cfc-145">若要提取 SurfaceWOL.msi 的内容，请使用 MSIExec 管理安装选项 (**/a**) ，如以下示例所示，将内容提取到 C：\WOL\ 文件夹：</span><span class="sxs-lookup"><span data-stu-id="d6cfc-145">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="d6cfc-146">Surface Studio 2 说明</span><span class="sxs-lookup"><span data-stu-id="d6cfc-146">Surface Studio 2 instructions</span></span>

<span data-ttu-id="d6cfc-147">若要在 Surface Studio 2 上启用 WOL，你必须使用以下过程</span><span class="sxs-lookup"><span data-stu-id="d6cfc-147">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="d6cfc-148">创建以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="d6cfc-148">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="d6cfc-149">运行以下命令</span><span class="sxs-lookup"><span data-stu-id="d6cfc-149">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="d6cfc-150">使用 Surface WOL</span><span class="sxs-lookup"><span data-stu-id="d6cfc-150">Using Surface WOL</span></span>

<span data-ttu-id="d6cfc-151">Surface WOL 驱动程序符合 WOL 标准，即设备由称为神奇数据包的特殊网络通信所驱动。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-151">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="d6cfc-152">神奇数据包包含 6 个字节（255 (或 FF，以十六进制) 后跟目标计算机的 MAC 地址的 16 个重复。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-152">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="d6cfc-153">可以在 Wikipedia 上阅读有关神奇数据包和 WOL 标准 [的内容](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-153">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="d6cfc-154">若要发送一个神奇数据包，然后使用 WOL 唤醒设备，必须知道目标设备和以太网适配器的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-154">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="d6cfc-155">由于神奇数据包不使用 IP 网络协议，因此不可能使用设备的 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-155">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="d6cfc-156">许多管理解决方案（如 Configuration Manager）都提供对 WOL 的内置支持。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-156">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="d6cfc-157">还有许多解决方案，包括 Microsoft Store 应用、PowerShell 模块、第三方应用程序和第三方管理解决方案，它们允许你发送神奇数据包来唤醒设备。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-157">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="d6cfc-158">例如，可以从 [TechNet 脚本LAN 唤醒 PowerShell](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) 模块。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-158">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="d6cfc-159">在设备被一个神奇数据包丢弃后，如果应用程序未主动阻止系统睡眠，或者 AllowSystemRequiredPowerRequests 注册表项未配置为 1，则设备将返回到睡眠状态，这将允许应用程序阻止睡眠。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-159">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="d6cfc-160">有关此注册表项详细信息，请参阅本文的 [WOL](#wol-driver) 驱动程序部分。</span><span class="sxs-lookup"><span data-stu-id="d6cfc-160">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>

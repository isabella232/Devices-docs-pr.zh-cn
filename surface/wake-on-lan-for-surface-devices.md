---
title: " (Surface) 上的 Surface 设备唤醒"
description: 了解如何使用 LAN 唤醒远程唤醒设备以执行管理或维护任务，或自动启用管理解决方案-即使设备已断电。
keywords: 更新、部署、驱动程序、wol、lan 唤醒
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
ms.openlocfilehash: a56f6e01a4d7bf1cc40d73f34c3abf8e04443989
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114610"
---
# <span data-ttu-id="8a6b8-104">Surface 设备的 LAN 唤醒</span><span class="sxs-lookup"><span data-stu-id="8a6b8-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="8a6b8-105">运行 Windows 10 版本1607的 Surface 设备 (也称为 Windows 10 周年更新) 或更高版本，并使用 Surface 以太网适配器连接到有线网络，可以从连接待机 (WOL) 唤醒 LAN。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="8a6b8-106">使用 WOL，您可以远程唤醒设备以执行管理或维护任务，或启用管理解决方案 (如 Microsoft 终结点配置管理器) 自动启用。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="8a6b8-107">例如，当 office 为空时，你可以使用 Microsoft 终结点配置管理器将应用程序部署到与 Surface Dock 或 Surface Pro 3 扩展坞一起停靠的 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="8a6b8-108">Surface 设备必须连接到交流电源和连接待机 (睡眠) 以支持 WOL。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="8a6b8-109">在休眠或关闭电源的设备中不能进行 WOL。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="8a6b8-110">支持的设备</span><span class="sxs-lookup"><span data-stu-id="8a6b8-110">Supported devices</span></span>

<span data-ttu-id="8a6b8-111">WOL 支持以下设备：</span><span class="sxs-lookup"><span data-stu-id="8a6b8-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="8a6b8-112">Surface 以太网适配器</span><span class="sxs-lookup"><span data-stu-id="8a6b8-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="8a6b8-113">Surface USB-C 至以太网和 USB 适配器</span><span class="sxs-lookup"><span data-stu-id="8a6b8-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="8a6b8-114">Surface 扩展坞</span><span class="sxs-lookup"><span data-stu-id="8a6b8-114">Surface Dock</span></span>
* <span data-ttu-id="8a6b8-115">Surface Pro 的 surface 插接站 Pro 3</span><span class="sxs-lookup"><span data-stu-id="8a6b8-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="8a6b8-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="8a6b8-116">Surface 3</span></span>
* <span data-ttu-id="8a6b8-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="8a6b8-117">Surface Pro 3</span></span>
* <span data-ttu-id="8a6b8-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8a6b8-118">Surface Pro 4</span></span>
* <span data-ttu-id="8a6b8-119">Surface Pro (第5代) </span><span class="sxs-lookup"><span data-stu-id="8a6b8-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="8a6b8-120">Surface Pro (第5代) LTE 高级</span><span class="sxs-lookup"><span data-stu-id="8a6b8-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="8a6b8-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="8a6b8-121">Surface Book</span></span>
* <span data-ttu-id="8a6b8-122">Surface 笔记本电脑 (第一代) </span><span class="sxs-lookup"><span data-stu-id="8a6b8-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="8a6b8-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="8a6b8-123">Surface Pro 6</span></span>
* <span data-ttu-id="8a6b8-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="8a6b8-124">Surface Book 2</span></span>
* <span data-ttu-id="8a6b8-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="8a6b8-125">Surface Laptop 2</span></span>
* <span data-ttu-id="8a6b8-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="8a6b8-126">Surface Go</span></span>
* <span data-ttu-id="8a6b8-127">带有 LTE Advanced 的 Surface Go</span><span class="sxs-lookup"><span data-stu-id="8a6b8-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="8a6b8-128">Surface Studio 2 (参阅下面的 Surface Studio 2 说明) </span><span class="sxs-lookup"><span data-stu-id="8a6b8-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="8a6b8-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="8a6b8-129">Surface Pro 7</span></span>
* <span data-ttu-id="8a6b8-130">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="8a6b8-130">Surface Laptop 3</span></span>
* <span data-ttu-id="8a6b8-131">Surface 膝上型电脑 Go</span><span class="sxs-lookup"><span data-stu-id="8a6b8-131">Surface Laptop Go</span></span>

## <span data-ttu-id="8a6b8-132">WOL 驱动程序</span><span class="sxs-lookup"><span data-stu-id="8a6b8-132">WOL driver</span></span>

<span data-ttu-id="8a6b8-133">要在 Surface 设备上启用 WOL 支持，需要使用 Surface 以太网适配器的特定驱动程序。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-133">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="8a6b8-134">此驱动程序未包含在 Surface 设备的标准驱动程序和固件包中-必须单独下载并安装。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-134">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="8a6b8-135">您可以从 Microsoft 下载中心的 " [Surface Tools FOR IT](https://www.microsoft.com/download/details.aspx?id=46703) " 页面下载 surface WOL 驱动程序 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-135">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="8a6b8-136">你可以在 Surface 设备上运行此 Microsoft Windows Installer ( .msi) 文件以安装 Surface WOL 驱动程序，也可以使用应用程序部署解决方案（如 Microsoft 终结点配置管理器）将其分发到 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-136">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="8a6b8-137">若要在部署期间包括 Surface WOL 驱动程序，你可以在部署过程中将 .msi 文件作为应用程序进行安装。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-137">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="8a6b8-138">你还可以提取 Surface WOL 驱动程序文件以将它们包含在部署过程中。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-138">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="8a6b8-139">例如，你可以将它们包含在 Microsoft 部署工具包中 (MDT) 部署共享。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-139">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="8a6b8-140">在 [将 Windows 10 部署到 surface 设备（包含 Microsoft 部署工具包](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)）时，你可以通过 MDT 阅读有关 surface 部署的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-140">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="8a6b8-141">在 SurfaceWOL.msi 安装期间，将以下注册表项设置为值1，这样就可以轻松地识别已安装 WOL 驱动程序的系统。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-141">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="8a6b8-142">如果你选择在部署期间单独提取和安装这些驱动程序，则不会配置此注册表项，并且必须手动配置或使用脚本进行配置。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-142">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="8a6b8-143">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="8a6b8-143">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="8a6b8-144">若要提取 SurfaceWOL.msi 的内容，请使用 MSIExec 管理员安装选项 (**/a**) ，如以下示例中所示，将内容提取到 C:\WOL\ 文件夹：</span><span class="sxs-lookup"><span data-stu-id="8a6b8-144">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="8a6b8-145">Surface Studio 2 说明</span><span class="sxs-lookup"><span data-stu-id="8a6b8-145">Surface Studio 2 instructions</span></span>

<span data-ttu-id="8a6b8-146">若要在 Surface Studio 2 上启用 WOL，必须使用以下过程</span><span class="sxs-lookup"><span data-stu-id="8a6b8-146">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="8a6b8-147">创建以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="8a6b8-147">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="8a6b8-148">运行以下命令</span><span class="sxs-lookup"><span data-stu-id="8a6b8-148">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="8a6b8-149">使用 Surface WOL</span><span class="sxs-lookup"><span data-stu-id="8a6b8-149">Using Surface WOL</span></span>

<span data-ttu-id="8a6b8-150">Surface WOL 驱动程序符合 WOL 标准，由此设备通过称为幻数据包的特殊网络通信 woken。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-150">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="8a6b8-151">幻数据包包含6个字节的 255 (或十六进制) 中的 FF，后跟目标计算机的 MAC 地址的16个重复项。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-151">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="8a6b8-152">你可以在 [维基百科](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)上阅读有关幻数据包和 WOL 标准的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-152">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="8a6b8-153">若要通过使用 WOL 发送幻数据包并唤醒设备，您必须知道目标设备和以太网适配器的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-153">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="8a6b8-154">由于幻数据包不使用 IP 网络协议，因此不能使用设备的 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-154">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="8a6b8-155">许多管理解决方案（如配置管理器）提供对 WOL 的内置支持。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-155">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="8a6b8-156">还有许多解决方案，包括 Microsoft Store 应用、PowerShell 模块、第三方应用程序和第三方管理解决方案，这些解决方案允许你发送幻数据包以唤醒设备。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-156">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="8a6b8-157">例如，您可以使用 TechNet 脚本中心的 [LAN 上的唤醒模块](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) 。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-157">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="8a6b8-158">使用幻数据包 woken 设备后，如果应用程序未在系统上主动阻止睡眠，或者 AllowSystemRequiredPowerRequests 注册表项未配置为1，则设备将返回睡眠状态，从而允许应用程序阻止睡眠。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-158">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="8a6b8-159">有关此注册表项的详细信息，请参阅本文的 [WOL 驱动程序](#wol-driver) 部分。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-159">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>

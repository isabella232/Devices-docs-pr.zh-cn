---
title: 管理 Surface UEFI 设置
description: 使用 Surface UEFI 设置启用或者禁用设备或组件、配置安全设置以及调整 Surface 设备启动设置。
keywords: 固件, 安全, 功能, 配置, 硬件
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 01/15/2021
ms.openlocfilehash: d8d47db3bd6f69783670b285a797337373e02d72
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271426"
---
# <span data-ttu-id="fe23e-104">管理 Surface UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="fe23e-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="fe23e-105">所有当前和将来的 Surface 设备都使用 Microsoft 专门为这些设备 (UEFI) 唯一的统一可扩展固件接口。</span><span class="sxs-lookup"><span data-stu-id="fe23e-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="fe23e-106">Surface UEFI 设置提供启用或禁用内置设备和组件、防止更改 UEFI 设置以及调整 Surface 设备启动设置的能力。</span><span class="sxs-lookup"><span data-stu-id="fe23e-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="fe23e-107">支持的产品</span><span class="sxs-lookup"><span data-stu-id="fe23e-107">Supported products</span></span>

<span data-ttu-id="fe23e-108">以下各项支持 UEFI 管理：</span><span class="sxs-lookup"><span data-stu-id="fe23e-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="fe23e-109">Surface Pro 4、Surface Pro (第五代) 、Surface Pro 6、Surface Pro 7、Surface Pro 7+、Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="fe23e-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span></span>
- <span data-ttu-id="fe23e-110">Surface Laptop (第一代) 、Surface Laptop 2、Surface Laptop 3、Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="fe23e-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span></span>
- <span data-ttu-id="fe23e-111">Surface Studio (1 代) Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="fe23e-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="fe23e-112">Surface Book、Surface Book 2、Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="fe23e-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="fe23e-113">Surface Go、Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="fe23e-113">Surface Go, Surface Go 2</span></span>

## <span data-ttu-id="fe23e-114">支持基于云的管理</span><span class="sxs-lookup"><span data-stu-id="fe23e-114">Support for cloud-based management</span></span>

<span data-ttu-id="fe23e-115">借助内置于 Microsoft Intune (中的设备固件配置接口 (DFCI) 配置文件) ，Surface UEFI 管理可将新式管理堆栈向下扩展到 UEFI 硬件级别。</span><span class="sxs-lookup"><span data-stu-id="fe23e-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="fe23e-116">DFCI 支持零接触预配、消除 BIOS 密码、控制安全设置（包括启动选项和内置外设）并在将来为高级安全方案打下基础。</span><span class="sxs-lookup"><span data-stu-id="fe23e-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="fe23e-117">DFCI 目前可用于 Surface Pro 7+、Surface Laptop Go、Surface Book 3、Surface Laptop 3、Surface Pro 7 和 Surface Pro X。 有关详细信息，请参阅 Surface [UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="fe23e-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="fe23e-118">打开 Surface UEFI 菜单</span><span class="sxs-lookup"><span data-stu-id="fe23e-118">Open Surface UEFI menu</span></span>

<span data-ttu-id="fe23e-119">在系统启动期间调整 UEFI 设置：</span><span class="sxs-lookup"><span data-stu-id="fe23e-119">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="fe23e-120">关闭 Surface 并等待大约 10 秒以确保其关闭。</span><span class="sxs-lookup"><span data-stu-id="fe23e-120">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="fe23e-121">长按 **"调高音量** "按钮，同时按下并释放 **电源按钮。**</span><span class="sxs-lookup"><span data-stu-id="fe23e-121">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="fe23e-122">当 Microsoft 或 Surface 徽标显示在屏幕上时，请继续\*\*\*\* 按住"调高"按钮，直到出现 UEFI 屏幕。</span><span class="sxs-lookup"><span data-stu-id="fe23e-122">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="fe23e-123">UEFI 电脑信息页</span><span class="sxs-lookup"><span data-stu-id="fe23e-123">UEFI PC information page</span></span>

<span data-ttu-id="fe23e-124">电脑信息页包含有关 Surface 设备的详细信息：</span><span class="sxs-lookup"><span data-stu-id="fe23e-124">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="fe23e-125">**型号** – Surface 设备的型号将在此处显示，例如 Surface Book 2 或 Surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="fe23e-125">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="fe23e-126">不会显示设备的具体配置（例如处理器、磁盘大小或内存大小）。</span><span class="sxs-lookup"><span data-stu-id="fe23e-126">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="fe23e-127">**UUID** - 此通用唯一标识号特定于设备，用于在部署或管理期间标识设备。</span><span class="sxs-lookup"><span data-stu-id="fe23e-127">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="fe23e-128">**序列号** - 此编号用于标识资源标记和支持场景的特定 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="fe23e-128">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="fe23e-129">**资源标记** - 资源标记通过[资源标记工具](https://docs.microsoft.com/surface/assettag)分配到 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="fe23e-129">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="fe23e-130">还可以找到关于 Surface 设备固件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe23e-130">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="fe23e-131">Surface 设备具有多个内部组件，每个组件运行不同版本的固件。</span><span class="sxs-lookup"><span data-stu-id="fe23e-131">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="fe23e-132">以下所有设备的固件版本显示在**电脑信息**页上（如图 1 所示）：</span><span class="sxs-lookup"><span data-stu-id="fe23e-132">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="fe23e-133">系统 UEFI</span><span class="sxs-lookup"><span data-stu-id="fe23e-133">System UEFI</span></span> 

- <span data-ttu-id="fe23e-134">SAM 控制器</span><span class="sxs-lookup"><span data-stu-id="fe23e-134">SAM Controller</span></span> 

- <span data-ttu-id="fe23e-135">Intel 管理引擎</span><span class="sxs-lookup"><span data-stu-id="fe23e-135">Intel Management Engine</span></span> 

- <span data-ttu-id="fe23e-136">系统嵌入式控制器</span><span class="sxs-lookup"><span data-stu-id="fe23e-136">System Embedded Controller</span></span> 

- <span data-ttu-id="fe23e-137">触摸固件</span><span class="sxs-lookup"><span data-stu-id="fe23e-137">Touch Firmware</span></span> 

![系统信息和固件版本信息](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="fe23e-139">图 1.</span><span class="sxs-lookup"><span data-stu-id="fe23e-139">Figure 1.</span></span> <span data-ttu-id="fe23e-140">系统信息和固件版本信息</span><span class="sxs-lookup"><span data-stu-id="fe23e-140">System information and firmware version information</span></span>*

<span data-ttu-id="fe23e-141">在设备的 [Surface 更新历史记录](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)中可以找到有关 Surface 设备最新固件版本的最新信息。</span><span class="sxs-lookup"><span data-stu-id="fe23e-141">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="fe23e-142">"UEFI 安全性"页</span><span class="sxs-lookup"><span data-stu-id="fe23e-142">UEFI Security page</span></span> 

![配置 Surface UEFI 安全设置](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="fe23e-144">图 2.</span><span class="sxs-lookup"><span data-stu-id="fe23e-144">Figure 2.</span></span> <span data-ttu-id="fe23e-145">配置 Surface UEFI 安全设置</span><span class="sxs-lookup"><span data-stu-id="fe23e-145">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="fe23e-146">"安全"页允许你设置密码以保护 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="fe23e-146">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="fe23e-147">在将 Surface 设备启动到 UEFI 时，必须输入此密码。</span><span class="sxs-lookup"><span data-stu-id="fe23e-147">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="fe23e-148">密码可以包含以下字符 (如图) 3 所示：</span><span class="sxs-lookup"><span data-stu-id="fe23e-148">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="fe23e-149">大写字母：A-Z</span><span class="sxs-lookup"><span data-stu-id="fe23e-149">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="fe23e-150">小写字母：a-z</span><span class="sxs-lookup"><span data-stu-id="fe23e-150">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="fe23e-151">数字：1-0</span><span class="sxs-lookup"><span data-stu-id="fe23e-151">Numbers: 1-0</span></span> 

- <span data-ttu-id="fe23e-152">特殊字符：！@#$%^&\* () ？<>{} []-_=+|.，;：''"</span><span class="sxs-lookup"><span data-stu-id="fe23e-152">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="fe23e-153">密码必须最少为 6 个字符，并且区分大小写。</span><span class="sxs-lookup"><span data-stu-id="fe23e-153">The password must be at least 6 characters and is case sensitive.</span></span> 

![添加保护 Surface UEFI 设置的密码](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="fe23e-155">图 3.</span><span class="sxs-lookup"><span data-stu-id="fe23e-155">Figure 3.</span></span> <span data-ttu-id="fe23e-156">添加保护 Surface UEFI 设置的密码</span><span class="sxs-lookup"><span data-stu-id="fe23e-156">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="fe23e-157">在安全页上，还可以更改 Surface 设备的安全启动配置。</span><span class="sxs-lookup"><span data-stu-id="fe23e-157">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="fe23e-158">安全启动技术可阻止未经授权的启动代码启动 Surface 设备，这可防御 bootkit 和 rootkit 类型的恶意软件感染。</span><span class="sxs-lookup"><span data-stu-id="fe23e-158">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="fe23e-159">可以禁用安全启动，从而允许 Surface 设备启动第三方操作系统或可启动媒体。</span><span class="sxs-lookup"><span data-stu-id="fe23e-159">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="fe23e-160">还可以配置安全启动以使用第三方证书，如图 4 所示。</span><span class="sxs-lookup"><span data-stu-id="fe23e-160">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="fe23e-161">在 TechNet 库中阅读有关[安全启动](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe23e-161">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![配置安全启动](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="fe23e-163">图 4.</span><span class="sxs-lookup"><span data-stu-id="fe23e-163">Figure 4.</span></span> <span data-ttu-id="fe23e-164">配置安全启动</span><span class="sxs-lookup"><span data-stu-id="fe23e-164">Configure Secure Boot</span></span>*

<span data-ttu-id="fe23e-165">根据你的设备，你可能还能够查看你的 TPM 是已启用还是已禁用。</span><span class="sxs-lookup"><span data-stu-id="fe23e-165">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="fe23e-166">如果看不到"启用 **TPM"**  设置，请在 Windows 中打开 tpm.msc 以检查状态，如图 5 所示。</span><span class="sxs-lookup"><span data-stu-id="fe23e-166">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="fe23e-167">TPM 用于与 BitLocker 一起验证设备数据的加密情况。</span><span class="sxs-lookup"><span data-stu-id="fe23e-167">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="fe23e-168">若要了解更多信息，请参阅 [BitLocker 概述](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。</span><span class="sxs-lookup"><span data-stu-id="fe23e-168">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![TPM 控制台](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="fe23e-170">图 5.</span><span class="sxs-lookup"><span data-stu-id="fe23e-170">Figure 5.</span></span> <span data-ttu-id="fe23e-171">TPM 控制台</span><span class="sxs-lookup"><span data-stu-id="fe23e-171">TPM console</span></span>*


## <span data-ttu-id="fe23e-172">UEFI 菜单：设备</span><span class="sxs-lookup"><span data-stu-id="fe23e-172">UEFI menu: Devices</span></span> 

<span data-ttu-id="fe23e-173">"设备"页允许你启用或禁用特定设备和组件，包括：</span><span class="sxs-lookup"><span data-stu-id="fe23e-173">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="fe23e-174">扩展坞和 USB 端口</span><span class="sxs-lookup"><span data-stu-id="fe23e-174">Docking and USB Ports</span></span> 

- <span data-ttu-id="fe23e-175">MicroSD 或 SD 卡槽</span><span class="sxs-lookup"><span data-stu-id="fe23e-175">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="fe23e-176">后置摄像头</span><span class="sxs-lookup"><span data-stu-id="fe23e-176">Rear Camera</span></span> 

- <span data-ttu-id="fe23e-177">前置摄像头</span><span class="sxs-lookup"><span data-stu-id="fe23e-177">Front Camera</span></span> 

- <span data-ttu-id="fe23e-178">红外 (IR) 相机</span><span class="sxs-lookup"><span data-stu-id="fe23e-178">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="fe23e-179">WLAN 和蓝牙</span><span class="sxs-lookup"><span data-stu-id="fe23e-179">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="fe23e-180">板载音频（扬声器和麦克风）</span><span class="sxs-lookup"><span data-stu-id="fe23e-180">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="fe23e-181">每个设备都列出一个滑块按钮，你可以将其移动到 (\*\*\*\* 启用 **) 或 (** 禁用) 位置，如图 6 所示。</span><span class="sxs-lookup"><span data-stu-id="fe23e-181">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![启用和禁用特定设备](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="fe23e-183">图 6.</span><span class="sxs-lookup"><span data-stu-id="fe23e-183">Figure 6.</span></span> <span data-ttu-id="fe23e-184">启用和禁用特定设备</span><span class="sxs-lookup"><span data-stu-id="fe23e-184">Enable and disable specific devices</span></span>*

## <span data-ttu-id="fe23e-185">UEFI 菜单：启动配置</span><span class="sxs-lookup"><span data-stu-id="fe23e-185">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="fe23e-186">"启动配置"页允许你更改启动设备的顺序，以及启用或禁用以下设备的启动：</span><span class="sxs-lookup"><span data-stu-id="fe23e-186">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="fe23e-187">Windows 启动管理器</span><span class="sxs-lookup"><span data-stu-id="fe23e-187">Windows Boot Manager</span></span> 

- <span data-ttu-id="fe23e-188">USB 存储</span><span class="sxs-lookup"><span data-stu-id="fe23e-188">USB Storage</span></span> 

- <span data-ttu-id="fe23e-189">PXE 网络</span><span class="sxs-lookup"><span data-stu-id="fe23e-189">PXE Network</span></span> 

- <span data-ttu-id="fe23e-190">内部存储</span><span class="sxs-lookup"><span data-stu-id="fe23e-190">Internal Storage</span></span> 

<span data-ttu-id="fe23e-191">可以立即启动特定设备，或使用触摸屏在列表中向左滑动该设备项。</span><span class="sxs-lookup"><span data-stu-id="fe23e-191">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="fe23e-192">还可以在关闭 Surface 设备电源时，同时按**调低音量**按钮和**电源**按钮，立即启动到 USB 设备或 USB 以太网适配器。</span><span class="sxs-lookup"><span data-stu-id="fe23e-192">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="fe23e-193">若要使指定的启动顺序生效，必须将"启用 **备用** 启动序列"选项设置为 **"打开**"，如图 7 所示。</span><span class="sxs-lookup"><span data-stu-id="fe23e-193">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![配置 Surface 设备的启动顺序](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="fe23e-195">图 7.</span><span class="sxs-lookup"><span data-stu-id="fe23e-195">Figure 7.</span></span> <span data-ttu-id="fe23e-196">配置 Surface 设备的启动顺序</span><span class="sxs-lookup"><span data-stu-id="fe23e-196">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="fe23e-197">在使用 PXE 服务器仅为 IPv4 配置的 PXE 部署 Windows 时，还可以使用**启用用于 PXE 网络启动的 IPv6** 选项来打开和关闭对 PXE 的 IPv6 支持。</span><span class="sxs-lookup"><span data-stu-id="fe23e-197">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="fe23e-198">UEFI 菜单：管理</span><span class="sxs-lookup"><span data-stu-id="fe23e-198">UEFI menu: Management</span></span>
<span data-ttu-id="fe23e-199">"管理"页允许你在符合条件的设备（包括 Surface Pro 7、Surface Pro X 和 Surface Laptop 3）上管理零接触 UEFI 管理和其他功能的使用。</span><span class="sxs-lookup"><span data-stu-id="fe23e-199">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="fe23e-200">管理对零接触 UEFI 管理和其他功能的访问权限 ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *图 8。管理对零接触 UEFI 管理和其他功能的访问权限*</span><span class="sxs-lookup"><span data-stu-id="fe23e-200">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="fe23e-201">零接触 UEFI 管理允许你使用 Intune 中的设备配置文件（称为设备固件配置接口 (DFCI) ） 远程管理 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="fe23e-201">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="fe23e-202">如果未配置此设置，则使用 DFCI 管理符合条件的设备的能力设置为 **"就绪"。**</span><span class="sxs-lookup"><span data-stu-id="fe23e-202">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="fe23e-203">若要阻止 DFCI，请选择 **"选择退出"。**</span><span class="sxs-lookup"><span data-stu-id="fe23e-203">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="fe23e-204">UEFI 管理设置页和 DFCI 的使用目前适用于 Surface Pro 7+、Surface Laptop Go、Surface Book 3、Surface Laptop 3、Surface Pro 7 和 Surface Pro X。若要了解更多信息，请参阅 [Surface UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="fe23e-204">The UEFI Management settings page and use of DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X. To learn more, see [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="fe23e-205">UEFI 菜单：退出</span><span class="sxs-lookup"><span data-stu-id="fe23e-205">UEFI menu: Exit</span></span> 

<span data-ttu-id="fe23e-206">使用"**退出"** 页上的"\*\*\*\* 立即重启"按钮退出 UEFI 设置，如图 9 所示。</span><span class="sxs-lookup"><span data-stu-id="fe23e-206">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![退出 Surface UEFI，并重启设备](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="fe23e-208">图 9.</span><span class="sxs-lookup"><span data-stu-id="fe23e-208">Figure 9.</span></span> <span data-ttu-id="fe23e-209">单击“立即重启”退出 Surface UEFI，并重启设备</span><span class="sxs-lookup"><span data-stu-id="fe23e-209">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="fe23e-210">Surface UEFI 启动屏幕</span><span class="sxs-lookup"><span data-stu-id="fe23e-210">Surface UEFI boot screens</span></span>

<span data-ttu-id="fe23e-211">当你通过 Windows 更新或手动安装更新 Surface 设备固件时，更新不会立即适用于设备，而是在下个重新启动周期应用。</span><span class="sxs-lookup"><span data-stu-id="fe23e-211">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="fe23e-212">你可以在[管理 Surface 驱动程序和固件更新](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)中了解有关 Surface 固件更新过程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe23e-212">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="fe23e-213">固件更新的进度会在屏幕上显示为具有不同颜色的进度栏，以指示每个组件的固件。</span><span class="sxs-lookup"><span data-stu-id="fe23e-213">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="fe23e-214">图 9 至 18 中显示了每个组件的进度栏。</span><span class="sxs-lookup"><span data-stu-id="fe23e-214">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![带有蓝色进度栏的 Surface UEFI 固件更新](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="fe23e-216">图 10.</span><span class="sxs-lookup"><span data-stu-id="fe23e-216">Figure 10.</span></span> <span data-ttu-id="fe23e-217">Surface UEFI 固件更新显示蓝色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-217">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![带有绿色进度栏的系统嵌入式控制器固件](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="fe23e-219">图 11.</span><span class="sxs-lookup"><span data-stu-id="fe23e-219">Figure 11.</span></span> <span data-ttu-id="fe23e-220">系统嵌入式控制器固件更新显示绿色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-220">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![带有橙色进度栏的 SAM 控制器固件更新](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="fe23e-222">图 12.</span><span class="sxs-lookup"><span data-stu-id="fe23e-222">Figure 12.</span></span> <span data-ttu-id="fe23e-223">SAM 控制器固件更新显示橙色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-223">The SAM Controller firmware update displays an orange progress bar</span></span>*

![带有红色进度栏的 Intel 管理引擎固件](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="fe23e-225">图 13.</span><span class="sxs-lookup"><span data-stu-id="fe23e-225">Figure 13.</span></span> <span data-ttu-id="fe23e-226">Intel 管理引擎固件更新显示红色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-226">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![带有灰色进度栏的 Surface 触摸固件](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="fe23e-228">图 14.</span><span class="sxs-lookup"><span data-stu-id="fe23e-228">Figure 14.</span></span> <span data-ttu-id="fe23e-229">Surface 触摸固件更新显示灰色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-229">The Surface touch firmware update displays a gray progress bar</span></span>*

![带浅绿色进度栏的 Surface KIP 固件](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="fe23e-231">图 15.</span><span class="sxs-lookup"><span data-stu-id="fe23e-231">Figure 15.</span></span> <span data-ttu-id="fe23e-232">Surface KIP 固件更新显示浅绿色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-232">The Surface KIP firmware update displays a light green progress bar</span></span>*

![带粉色进度栏的 Surface ISH 固件](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="fe23e-234">图 16 Surface ISH 固件更新显示浅粉色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![带灰色进度栏的 Surface Trackpad 固件](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="fe23e-236">图 17.</span><span class="sxs-lookup"><span data-stu-id="fe23e-236">Figure 17.</span></span> <span data-ttu-id="fe23e-237">Surface Trackpad 固件更新显示一个粉色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-237">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![带浅灰色进度栏的 Surface TCON 固件](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="fe23e-239">图 18.</span><span class="sxs-lookup"><span data-stu-id="fe23e-239">Figure 18.</span></span> <span data-ttu-id="fe23e-240">Surface TCON 固件更新显示浅灰色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-240">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![带淡紫色进度栏的 Surface TPM 固件](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="fe23e-242">图 19.</span><span class="sxs-lookup"><span data-stu-id="fe23e-242">Figure 19.</span></span> <span data-ttu-id="fe23e-243">Surface TPM 固件更新显示紫色进度栏</span><span class="sxs-lookup"><span data-stu-id="fe23e-243">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="fe23e-244">将显示一条额外的警告消息，指示安全启动已禁用，如图 19 所示。</span><span class="sxs-lookup"><span data-stu-id="fe23e-244">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![指示安全启动已禁用的 Surface 启动屏幕](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="fe23e-246">图 20.</span><span class="sxs-lookup"><span data-stu-id="fe23e-246">Figure 20.</span></span> <span data-ttu-id="fe23e-247">指示安全启动已在 Surface UEFI 设置中禁用的安全启动屏幕</span><span class="sxs-lookup"><span data-stu-id="fe23e-247">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="fe23e-248">相关主题</span><span class="sxs-lookup"><span data-stu-id="fe23e-248">Related topics</span></span>

- [<span data-ttu-id="fe23e-249">Surface UEFI 设置的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="fe23e-249">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="fe23e-250">Surface 企业管理模式</span><span class="sxs-lookup"><span data-stu-id="fe23e-250">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)

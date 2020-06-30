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
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831655"
---
# <span data-ttu-id="8635f-104">管理 Surface UEFI 设置</span><span class="sxs-lookup"><span data-stu-id="8635f-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="8635f-105">所有当前和未来的 Surface 设备代都使用专为这些设备设计的独特的统一可扩展固件接口（UEFI）。</span><span class="sxs-lookup"><span data-stu-id="8635f-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="8635f-106">Surface UEFI 设置提供启用或禁用内置设备和组件、保护 UEFI 设置不被更改以及调整 Surface 设备启动设置的功能。</span><span class="sxs-lookup"><span data-stu-id="8635f-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="8635f-107">支持基于云的管理</span><span class="sxs-lookup"><span data-stu-id="8635f-107">Support for cloud-based management</span></span>

<span data-ttu-id="8635f-108">使用内置于 Microsoft Intune 的设备固件配置接口（DFCI）配置文件（现在在公共预览版中可用），Surface UEFI 管理将新式管理堆栈扩展到 UEFI 硬件级别。</span><span class="sxs-lookup"><span data-stu-id="8635f-108">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="8635f-109">DFCI 支持零接触预配，消除了 BIOS 密码，提供了安全设置（包括启动选项和内置外围设备）的控制权，并为将来的高级安全方案奠定了基础。</span><span class="sxs-lookup"><span data-stu-id="8635f-109">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="8635f-110">DFCI 当前可用于 Surface Pro 7、Surface Pro X 和 Surface 笔记本电脑3。</span><span class="sxs-lookup"><span data-stu-id="8635f-110">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="8635f-111">有关详细信息，请参阅[SURFACE UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="8635f-111">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="8635f-112">打开 Surface UEFI 菜单</span><span class="sxs-lookup"><span data-stu-id="8635f-112">Open Surface UEFI menu</span></span>

<span data-ttu-id="8635f-113">要在系统启动期间调整 UEFI 设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8635f-113">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="8635f-114">关闭你的 Surface，等待大约10秒钟，确保它处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="8635f-114">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="8635f-115">同时按住**调高音量**按钮，同时按下并松开**电源按钮。**</span><span class="sxs-lookup"><span data-stu-id="8635f-115">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="8635f-116">由于 Microsoft 或 Surface 徽标显示在你的屏幕上，因此继续保持**音量向上**键，直到出现 UEFI 屏幕。</span><span class="sxs-lookup"><span data-stu-id="8635f-116">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="8635f-117">UEFI 电脑信息页面</span><span class="sxs-lookup"><span data-stu-id="8635f-117">UEFI PC information page</span></span>

<span data-ttu-id="8635f-118">PC 信息页面包括有关 Surface 设备的详细信息：</span><span class="sxs-lookup"><span data-stu-id="8635f-118">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="8635f-119">**模型**-你的 surface 设备模型将在此处显示，如 surface Book 2 或 surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="8635f-119">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="8635f-120">不会显示设备的具体配置（例如处理器、磁盘大小或内存大小）。</span><span class="sxs-lookup"><span data-stu-id="8635f-120">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="8635f-121">**UUID** - 此通用唯一标识号特定于设备，用于在部署或管理期间标识设备。</span><span class="sxs-lookup"><span data-stu-id="8635f-121">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="8635f-122">**序列号** - 此编号用于标识资源标记和支持场景的特定 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="8635f-122">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="8635f-123">**资源标记** - 资源标记通过[资源标记工具](https://docs.microsoft.com/surface/assettag)分配到 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="8635f-123">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="8635f-124">还可以找到关于 Surface 设备固件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8635f-124">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="8635f-125">Surface 设备具有多个内部组件，每个组件运行不同版本的固件。</span><span class="sxs-lookup"><span data-stu-id="8635f-125">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="8635f-126">以下所有设备的固件版本显示在**电脑信息**页上（如图 1 所示）：</span><span class="sxs-lookup"><span data-stu-id="8635f-126">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="8635f-127">系统 UEFI</span><span class="sxs-lookup"><span data-stu-id="8635f-127">System UEFI</span></span> 

- <span data-ttu-id="8635f-128">SAM 控制器</span><span class="sxs-lookup"><span data-stu-id="8635f-128">SAM Controller</span></span> 

- <span data-ttu-id="8635f-129">Intel 管理引擎</span><span class="sxs-lookup"><span data-stu-id="8635f-129">Intel Management Engine</span></span> 

- <span data-ttu-id="8635f-130">系统嵌入式控制器</span><span class="sxs-lookup"><span data-stu-id="8635f-130">System Embedded Controller</span></span> 

- <span data-ttu-id="8635f-131">触摸固件</span><span class="sxs-lookup"><span data-stu-id="8635f-131">Touch Firmware</span></span> 

![系统信息和固件版本信息](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="8635f-133">图 1.</span><span class="sxs-lookup"><span data-stu-id="8635f-133">Figure 1.</span></span> <span data-ttu-id="8635f-134">系统信息和固件版本信息</span><span class="sxs-lookup"><span data-stu-id="8635f-134">System information and firmware version information</span></span>*

<span data-ttu-id="8635f-135">在设备的 [Surface 更新历史记录](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)中可以找到有关 Surface 设备最新固件版本的最新信息。</span><span class="sxs-lookup"><span data-stu-id="8635f-135">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="8635f-136">UEFI 安全页面</span><span class="sxs-lookup"><span data-stu-id="8635f-136">UEFI Security page</span></span> 

![配置 Surface UEFI 安全设置](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="8635f-138">图 2.</span><span class="sxs-lookup"><span data-stu-id="8635f-138">Figure 2.</span></span> <span data-ttu-id="8635f-139">配置 Surface UEFI 安全设置</span><span class="sxs-lookup"><span data-stu-id="8635f-139">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="8635f-140">"安全" 页面允许您设置密码以保护 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="8635f-140">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="8635f-141">在将 Surface 设备启动到 UEFI 时，必须输入此密码。</span><span class="sxs-lookup"><span data-stu-id="8635f-141">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="8635f-142">密码可以包含以下字符（如图3所示）：</span><span class="sxs-lookup"><span data-stu-id="8635f-142">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="8635f-143">大写字母：A-Z</span><span class="sxs-lookup"><span data-stu-id="8635f-143">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="8635f-144">小写字母：a-z</span><span class="sxs-lookup"><span data-stu-id="8635f-144">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="8635f-145">数字：1-0</span><span class="sxs-lookup"><span data-stu-id="8635f-145">Numbers: 1-0</span></span> 

- <span data-ttu-id="8635f-146">特殊字符：！ @ # $% ^& \* （）？ <>{} [] – _ = + |;，;： "'"</span><span class="sxs-lookup"><span data-stu-id="8635f-146">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="8635f-147">密码必须最少为 6 个字符，并且区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8635f-147">The password must be at least 6 characters and is case sensitive.</span></span> 

![添加保护 Surface UEFI 设置的密码](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="8635f-149">图 3.</span><span class="sxs-lookup"><span data-stu-id="8635f-149">Figure 3.</span></span> <span data-ttu-id="8635f-150">添加保护 Surface UEFI 设置的密码</span><span class="sxs-lookup"><span data-stu-id="8635f-150">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="8635f-151">在安全页上，还可以更改 Surface 设备的安全启动配置。</span><span class="sxs-lookup"><span data-stu-id="8635f-151">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="8635f-152">安全启动技术可阻止未经授权的启动代码启动 Surface 设备，这可防御 bootkit 和 rootkit 类型的恶意软件感染。</span><span class="sxs-lookup"><span data-stu-id="8635f-152">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="8635f-153">可以禁用安全启动，从而允许 Surface 设备启动第三方操作系统或可启动媒体。</span><span class="sxs-lookup"><span data-stu-id="8635f-153">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="8635f-154">您还可以配置 "安全启动" 以处理第三方证书，如图4所示。</span><span class="sxs-lookup"><span data-stu-id="8635f-154">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="8635f-155">在 TechNet 库中阅读有关[安全启动](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8635f-155">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![配置安全启动](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="8635f-157">图 4.</span><span class="sxs-lookup"><span data-stu-id="8635f-157">Figure 4.</span></span> <span data-ttu-id="8635f-158">配置安全启动</span><span class="sxs-lookup"><span data-stu-id="8635f-158">Configure Secure Boot</span></span>*

<span data-ttu-id="8635f-159">根据你的设备，你还可以查看你的 TPM 是否已启用或已禁用。</span><span class="sxs-lookup"><span data-stu-id="8635f-159">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="8635f-160">如果看不到 "**启用 TPM** " 设置，请在 Windows 中打开 "services.msc" 以检查状态，如图5所示。</span><span class="sxs-lookup"><span data-stu-id="8635f-160">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="8635f-161">TPM 用于与 BitLocker 一起验证设备数据的加密情况。</span><span class="sxs-lookup"><span data-stu-id="8635f-161">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="8635f-162">若要了解详细信息，请参阅[BitLocker 概述](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。</span><span class="sxs-lookup"><span data-stu-id="8635f-162">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![TPM 控制台](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="8635f-164">图 5.</span><span class="sxs-lookup"><span data-stu-id="8635f-164">Figure 5.</span></span> <span data-ttu-id="8635f-165">TPM 控制台</span><span class="sxs-lookup"><span data-stu-id="8635f-165">TPM console</span></span>*


## <span data-ttu-id="8635f-166">UEFI 菜单：设备</span><span class="sxs-lookup"><span data-stu-id="8635f-166">UEFI menu: Devices</span></span> 

<span data-ttu-id="8635f-167">"设备" 页面允许你启用或禁用特定设备和组件，包括：</span><span class="sxs-lookup"><span data-stu-id="8635f-167">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="8635f-168">扩展坞和 USB 端口</span><span class="sxs-lookup"><span data-stu-id="8635f-168">Docking and USB Ports</span></span> 

- <span data-ttu-id="8635f-169">MicroSD 或 SD 卡槽</span><span class="sxs-lookup"><span data-stu-id="8635f-169">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="8635f-170">后置摄像头</span><span class="sxs-lookup"><span data-stu-id="8635f-170">Rear Camera</span></span> 

- <span data-ttu-id="8635f-171">前置摄像头</span><span class="sxs-lookup"><span data-stu-id="8635f-171">Front Camera</span></span> 

- <span data-ttu-id="8635f-172">红外 (IR) 相机</span><span class="sxs-lookup"><span data-stu-id="8635f-172">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="8635f-173">WLAN 和蓝牙</span><span class="sxs-lookup"><span data-stu-id="8635f-173">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="8635f-174">板载音频（扬声器和麦克风）</span><span class="sxs-lookup"><span data-stu-id="8635f-174">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="8635f-175">列出的每个设备带有一个滑块按钮，您可以将该按钮移动到 **"打开"** （已启用）或 "**关闭**" （禁用）位置，如图6所示。</span><span class="sxs-lookup"><span data-stu-id="8635f-175">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![启用和禁用特定设备](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="8635f-177">图 6.</span><span class="sxs-lookup"><span data-stu-id="8635f-177">Figure 6.</span></span> <span data-ttu-id="8635f-178">启用和禁用特定设备</span><span class="sxs-lookup"><span data-stu-id="8635f-178">Enable and disable specific devices</span></span>*

## <span data-ttu-id="8635f-179">UEFI 菜单：启动配置</span><span class="sxs-lookup"><span data-stu-id="8635f-179">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="8635f-180">"启动配置" 页面允许你更改启动设备的顺序以及启用或禁用以下设备的启动：</span><span class="sxs-lookup"><span data-stu-id="8635f-180">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="8635f-181">Windows 启动管理器</span><span class="sxs-lookup"><span data-stu-id="8635f-181">Windows Boot Manager</span></span> 

- <span data-ttu-id="8635f-182">USB 存储</span><span class="sxs-lookup"><span data-stu-id="8635f-182">USB Storage</span></span> 

- <span data-ttu-id="8635f-183">PXE 网络</span><span class="sxs-lookup"><span data-stu-id="8635f-183">PXE Network</span></span> 

- <span data-ttu-id="8635f-184">内部存储</span><span class="sxs-lookup"><span data-stu-id="8635f-184">Internal Storage</span></span> 

<span data-ttu-id="8635f-185">可以立即启动特定设备，或使用触摸屏在列表中向左滑动该设备项。</span><span class="sxs-lookup"><span data-stu-id="8635f-185">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="8635f-186">还可以在关闭 Surface 设备电源时，同时按**调低音量**按钮和**电源**按钮，立即启动到 USB 设备或 USB 以太网适配器。</span><span class="sxs-lookup"><span data-stu-id="8635f-186">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="8635f-187">为使指定的启动顺序生效，必须将 "**启用备用启动序列**" 选项设置为 **"打开**"，如图7所示。</span><span class="sxs-lookup"><span data-stu-id="8635f-187">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![配置 Surface 设备的启动顺序](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="8635f-189">图 7.</span><span class="sxs-lookup"><span data-stu-id="8635f-189">Figure 7.</span></span> <span data-ttu-id="8635f-190">配置 Surface 设备的启动顺序</span><span class="sxs-lookup"><span data-stu-id="8635f-190">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="8635f-191">在使用 PXE 服务器仅为 IPv4 配置的 PXE 部署 Windows 时，还可以使用**启用用于 PXE 网络启动的 IPv6** 选项来打开和关闭对 PXE 的 IPv6 支持。</span><span class="sxs-lookup"><span data-stu-id="8635f-191">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="8635f-192">UEFI 菜单：管理</span><span class="sxs-lookup"><span data-stu-id="8635f-192">UEFI menu: Management</span></span>
<span data-ttu-id="8635f-193">通过 "管理" 页面，你可以在符合条件的设备（包括 Surface Pro 7、Surface Pro X 和 Surface 笔记本3）上管理零接触 UEFI 管理和其他功能的使用。</span><span class="sxs-lookup"><span data-stu-id="8635f-193">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="8635f-194">管理对零接触 UEFI 管理和其他功能的访问 ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *图8。管理对零接触 UEFI 管理和其他功能的访问*</span><span class="sxs-lookup"><span data-stu-id="8635f-194">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="8635f-195">零接触 UEFI 管理允许你通过使用名为 "设备固件配置" 界面（DFCI）的 Intune 内的设备配置文件来远程管理 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="8635f-195">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="8635f-196">如果不配置此设置，将具有 DFCI 的符合条件的设备的功能设置为 "**就绪**"。</span><span class="sxs-lookup"><span data-stu-id="8635f-196">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="8635f-197">若要防止 DFCI，**请选择 "选择退出**"。</span><span class="sxs-lookup"><span data-stu-id="8635f-197">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="8635f-198">只有 Surface Pro 7、Surface Pro X 和 Surface 笔记本电脑3提供了 UEFI 管理设置页面和使用 DFCI。</span><span class="sxs-lookup"><span data-stu-id="8635f-198">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="8635f-199">有关详细信息，请参阅[SURFACE UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="8635f-199">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="8635f-200">UEFI 菜单：退出</span><span class="sxs-lookup"><span data-stu-id="8635f-200">UEFI menu: Exit</span></span> 

<span data-ttu-id="8635f-201">使用 "**退出**" 页面上的 "**立即重启**" 按钮退出 UEFI 设置，如图9所示。</span><span class="sxs-lookup"><span data-stu-id="8635f-201">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![退出 Surface UEFI，并重启设备](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="8635f-203">图 9.</span><span class="sxs-lookup"><span data-stu-id="8635f-203">Figure 9.</span></span> <span data-ttu-id="8635f-204">单击“立即重启”退出 Surface UEFI，并重启设备</span><span class="sxs-lookup"><span data-stu-id="8635f-204">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="8635f-205">Surface UEFI 启动屏幕</span><span class="sxs-lookup"><span data-stu-id="8635f-205">Surface UEFI boot screens</span></span>

<span data-ttu-id="8635f-206">当你通过 Windows 更新或手动安装更新 Surface 设备固件时，更新不会立即适用于设备，而是在下个重新启动周期应用。</span><span class="sxs-lookup"><span data-stu-id="8635f-206">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="8635f-207">你可以在[管理 Surface 驱动程序和固件更新](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)中了解有关 Surface 固件更新过程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8635f-207">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="8635f-208">固件更新的进度会在屏幕上显示为具有不同颜色的进度栏，以指示每个组件的固件。</span><span class="sxs-lookup"><span data-stu-id="8635f-208">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="8635f-209">每个组件的进度条都显示在第9和第18图中。</span><span class="sxs-lookup"><span data-stu-id="8635f-209">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![带有蓝色进度栏的 Surface UEFI 固件更新](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="8635f-211">图 10.</span><span class="sxs-lookup"><span data-stu-id="8635f-211">Figure 10.</span></span> <span data-ttu-id="8635f-212">Surface UEFI 固件更新显示蓝色进度栏</span><span class="sxs-lookup"><span data-stu-id="8635f-212">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![带有绿色进度栏的系统嵌入式控制器固件](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="8635f-214">图 11.</span><span class="sxs-lookup"><span data-stu-id="8635f-214">Figure 11.</span></span> <span data-ttu-id="8635f-215">系统嵌入式控制器固件更新显示绿色进度栏</span><span class="sxs-lookup"><span data-stu-id="8635f-215">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![带有橙色进度栏的 SAM 控制器固件更新](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="8635f-217">图 12.</span><span class="sxs-lookup"><span data-stu-id="8635f-217">Figure 12.</span></span> <span data-ttu-id="8635f-218">SAM 控制器固件更新显示橙色进度栏</span><span class="sxs-lookup"><span data-stu-id="8635f-218">The SAM Controller firmware update displays an orange progress bar</span></span>*

![带有红色进度栏的 Intel 管理引擎固件](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="8635f-220">图 13.</span><span class="sxs-lookup"><span data-stu-id="8635f-220">Figure 13.</span></span> <span data-ttu-id="8635f-221">Intel 管理引擎固件更新显示红色进度栏</span><span class="sxs-lookup"><span data-stu-id="8635f-221">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![带有灰色进度栏的 Surface 触摸固件](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="8635f-223">图 14.</span><span class="sxs-lookup"><span data-stu-id="8635f-223">Figure 14.</span></span> <span data-ttu-id="8635f-224">Surface 触摸固件更新显示灰色进度栏</span><span class="sxs-lookup"><span data-stu-id="8635f-224">The Surface touch firmware update displays a gray progress bar</span></span>*

![带有浅绿色进度栏的 Surface KIP 固件](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="8635f-226">图 15.</span><span class="sxs-lookup"><span data-stu-id="8635f-226">Figure 15.</span></span> <span data-ttu-id="8635f-227">Surface KIP 固件更新显示浅绿色进度栏</span><span class="sxs-lookup"><span data-stu-id="8635f-227">The Surface KIP firmware update displays a light green progress bar</span></span>*

![具有粉红色进度栏的 Surface ISH 固件](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="8635f-229">图 16 Surface ISH 固件更新显示浅粉色进度条</span><span class="sxs-lookup"><span data-stu-id="8635f-229">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![具有灰色进度栏的 Surface 触控板固件](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="8635f-231">图 17.</span><span class="sxs-lookup"><span data-stu-id="8635f-231">Figure 17.</span></span> <span data-ttu-id="8635f-232">Surface 触控板固件更新显示粉红色进度条</span><span class="sxs-lookup"><span data-stu-id="8635f-232">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![具有浅灰色进度栏的 Surface TCON 固件](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="8635f-234">图 18.</span><span class="sxs-lookup"><span data-stu-id="8635f-234">Figure 18.</span></span> <span data-ttu-id="8635f-235">Surface TCON 固件更新显示浅灰色进度栏</span><span class="sxs-lookup"><span data-stu-id="8635f-235">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![具有浅紫色进度栏的 Surface TPM 固件](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="8635f-237">图 19.</span><span class="sxs-lookup"><span data-stu-id="8635f-237">Figure 19.</span></span> <span data-ttu-id="8635f-238">Surface TPM 固件更新显示紫色进度栏</span><span class="sxs-lookup"><span data-stu-id="8635f-238">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="8635f-239">将显示一个指示安全启动已禁用的其他警告消息，如图19所示。</span><span class="sxs-lookup"><span data-stu-id="8635f-239">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![指示安全启动已禁用的 Surface 启动屏幕](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="8635f-241">图 20.</span><span class="sxs-lookup"><span data-stu-id="8635f-241">Figure 20.</span></span> <span data-ttu-id="8635f-242">指示安全启动已在 Surface UEFI 设置中禁用的安全启动屏幕</span><span class="sxs-lookup"><span data-stu-id="8635f-242">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="8635f-243">相关主题</span><span class="sxs-lookup"><span data-stu-id="8635f-243">Related topics</span></span>

- [<span data-ttu-id="8635f-244">Surface UEFI 设置的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="8635f-244">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="8635f-245">Surface 企业管理模式</span><span class="sxs-lookup"><span data-stu-id="8635f-245">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)

---
title: 'Surface Enterprise Management Mode (Surface) '
description: 了解 Surface 设备的此功能与 Surface UEFI 如何帮助你保护和管理组织的固件设置。
keywords: uefi， 配置， 固件， 安全， semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
audience: itpro
ms.date: 03/18/2021
ms.openlocfilehash: 011f4d0270c47b976e10dbece2adb70559222b79
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442180"
---
# <a name="microsoft-surface-enterprise-management-mode"></a><span data-ttu-id="c3602-104">Microsoft Surface Enterprise 管理模式</span><span class="sxs-lookup"><span data-stu-id="c3602-104">Microsoft Surface Enterprise Management Mode</span></span>

<span data-ttu-id="c3602-105">Microsoft Surface Enterprise Management Mode (SEMM) 是具有 Surface UEFI 的 Surface 设备的一项功能，允许你保护和管理贵组织的固件设置。</span><span class="sxs-lookup"><span data-stu-id="c3602-105">Microsoft Surface Enterprise Management Mode (SEMM) is a feature of Surface devices with Surface UEFI that allows you to secure and manage firmware settings within your organization.</span></span> <span data-ttu-id="c3602-106">借助 SEMM，IT 专业人员可以准备 UEFI 设置的配置，并安装在 Surface 设备上。</span><span class="sxs-lookup"><span data-stu-id="c3602-106">With SEMM, IT professionals can prepare configurations of UEFI settings and install them on a Surface device.</span></span> <span data-ttu-id="c3602-107">除了能够配置 UEFI 设置之外，SEMM 还使用证书来保护配置，防止未经授权的篡改或删除。</span><span class="sxs-lookup"><span data-stu-id="c3602-107">In addition to the ability to configure UEFI settings, SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal.</span></span> <span data-ttu-id="c3602-108">需要 SEMM 才能将 Surface Hub 2S 迁移到 Windows 10 专业版和企业版。</span><span class="sxs-lookup"><span data-stu-id="c3602-108">SEMM is a requirement to be able to migrate a Surface Hub 2S to Windows 10 Pro and Enterprise.</span></span>

>[!NOTE]
><span data-ttu-id="c3602-109">SEMM 仅在具有 Surface UEFI 固件的设备上可用。</span><span class="sxs-lookup"><span data-stu-id="c3602-109">SEMM is only available on devices with Surface UEFI firmware.</span></span> <span data-ttu-id="c3602-110">这包括大多数 Surface 设备，包括 Surface Pro 7+、Surface Pro 7、Surface Pro X、Surface Hub 2S、带 Intel 处理器的 Surface Laptop 3 商业 SK 和 Surface Laptop Go。</span><span class="sxs-lookup"><span data-stu-id="c3602-110">This includes most Surface devices including Surface Pro 7+, Surface Pro 7, Surface Pro X, Surface Hub 2S, Surface Laptop 3 commercial SKUs with an Intel processor, and Surface Laptop Go.</span></span> <span data-ttu-id="c3602-111">带 AMD 处理器的 15" Surface Laptop 3 SKU 不支持 SEMM (仅作为零售 SKU) 。</span><span class="sxs-lookup"><span data-stu-id="c3602-111">SEMM is not supported on the 15" Surface Laptop 3 SKU with AMD processor (only available as a retail SKU).</span></span> 

<span data-ttu-id="c3602-112">当 Surface 设备由 SEMM 配置且使用 SEMM 证书进行保护时，它们将被视为 *在* SEMM 中注册。</span><span class="sxs-lookup"><span data-stu-id="c3602-112">When Surface devices are configured by SEMM and secured with the SEMM certificate, they are considered *enrolled* in SEMM.</span></span> <span data-ttu-id="c3602-113">当删除 SEMM 证书并控制 UEFI 设置时，将 Surface 设备视为在 SEMM\*\* 中注销。</span><span class="sxs-lookup"><span data-stu-id="c3602-113">When the SEMM certificate is removed and control of UEFI settings is returned to the user of the device, the Surface device is considered *unenrolled* in SEMM.</span></span>

<span data-ttu-id="c3602-114">有两个管理选项可用于管理 SEMM 和注册 Surface 设备 - 独立工具或与 Microsoft Endpoint Configuration Manager 集成。</span><span class="sxs-lookup"><span data-stu-id="c3602-114">There are two administrative options you can use to manage SEMM and enroll Surface devices – a standalone tool or integration with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="c3602-115">本文介绍 SEMM 独立工具（称为 Microsoft Surface UEFI 配置器）。</span><span class="sxs-lookup"><span data-stu-id="c3602-115">The SEMM standalone tool, called the Microsoft Surface UEFI Configurator, is described in this article.</span></span> <span data-ttu-id="c3602-116">有关如何使用 Microsoft Endpoint Configuration Manager 管理 SEMM 的信息，请参阅使用 Microsoft Endpoint Configuration Manager 通过 [SEMM 管理设备](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)。</span><span class="sxs-lookup"><span data-stu-id="c3602-116">For more information about how to manage SEMM with Microsoft Endpoint Configuration Manager, see [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).</span></span>

> [!NOTE]
> <span data-ttu-id="c3602-117">仅在 Surface Pro X 上通过 UEFI 管理器支持 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c3602-117">SEMM is supported on Surface Pro X via the UEFI Manager only.</span></span> <span data-ttu-id="c3602-118">你可以从适用于 IT 的 [Surface Tools 下载](https://www.microsoft.com/download/details.aspx?id=46703)UEFI 管理器。</span><span class="sxs-lookup"><span data-stu-id="c3602-118">You can download UEFI Manager from [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="c3602-119">有关详细信息，请参阅[部署、管理和维护 Surface Pro X。](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="c3602-119">For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>


## <a name="microsoft-surface-uefi-configurator"></a><span data-ttu-id="c3602-120">Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="c3602-120">Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="c3602-121">SEMM 的主要工作区是 Microsoft Surface UEFI 配置器，如图 1 所示。</span><span class="sxs-lookup"><span data-stu-id="c3602-121">The primary workspace of SEMM is Microsoft Surface UEFI Configurator, as shown in Figure 1.</span></span> <span data-ttu-id="c3602-122">Microsoft Surface UEFI 配置器是用于创建 Windows Installer (.msi) 程序包或 WinPE 映像的工具，用于在 Surface 设备上注册、配置和注销 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c3602-122">Microsoft Surface UEFI Configurator is a tool used to create Windows Installer (.msi) packages or WinPE images used to enroll, configure, and unenroll SEMM on a Surface device.</span></span> <span data-ttu-id="c3602-123">这些程序包包含一个配置文件，其中指定了 UEFI 的设置。</span><span class="sxs-lookup"><span data-stu-id="c3602-123">These packages contain a configuration file where the settings for UEFI are specified.</span></span> <span data-ttu-id="c3602-124">SEMM 包还包含一个证书，该证书已安装并存储在固件中，用于在应用 UEFI 设置之前验证配置文件的签名。</span><span class="sxs-lookup"><span data-stu-id="c3602-124">SEMM packages also contain a certificate, which is installed and stored in firmware and used to verify the signature of configuration files before UEFI settings are applied.</span></span>

>[!TIP]
><span data-ttu-id="c3602-125">你现在可以使用 Surface UEFI 配置器和 SEMM 管理 Surface 扩展坞 2 上的端口。</span><span class="sxs-lookup"><span data-stu-id="c3602-125">You can now use Surface UEFI Configurator and SEMM to manage ports on Surface Dock 2.</span></span> <span data-ttu-id="c3602-126">若要了解更多信息，请参阅使用 SEMM 保护 [Surface Dock 2 端口](secure-surface-dock-ports-semm.md)。</span><span class="sxs-lookup"><span data-stu-id="c3602-126">To learn more, see [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).</span></span>

![Microsoft Surface UEFI 配置器](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*<span data-ttu-id="c3602-128">图 1.</span><span class="sxs-lookup"><span data-stu-id="c3602-128">Figure 1.</span></span> <span data-ttu-id="c3602-129">Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="c3602-129">Microsoft Surface UEFI Configurator</span></span>*


<span data-ttu-id="c3602-130">可以在三种模式下使用 Microsoft Surface UEFI 配置器工具：</span><span class="sxs-lookup"><span data-stu-id="c3602-130">You can use the Microsoft Surface UEFI Configurator tool in three modes:</span></span>

* <span data-ttu-id="c3602-131">[Surface UEFI 配置包](#configuration-package)。</span><span class="sxs-lookup"><span data-stu-id="c3602-131">[Surface UEFI Configuration Package](#configuration-package).</span></span> <span data-ttu-id="c3602-132">使用此模式创建 Surface UEFI 配置包，以在 SEMM 中注册 Surface 设备，并配置已注册设备的 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="c3602-132">Use this mode to create a Surface UEFI configuration package to enroll a Surface device in SEMM and to configure UEFI settings on enrolled devices.</span></span>
* <span data-ttu-id="c3602-133">[Surface UEFI 重置程序包](#reset-package)。</span><span class="sxs-lookup"><span data-stu-id="c3602-133">[Surface UEFI Reset Package](#reset-package).</span></span> <span data-ttu-id="c3602-134">使用此模式从 SEMM 注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="c3602-134">Use this mode to unenroll a Surface device from SEMM.</span></span>
* <span data-ttu-id="c3602-135">[Surface UEFI 恢复请求](#recovery-request)。</span><span class="sxs-lookup"><span data-stu-id="c3602-135">[Surface UEFI Recovery Request](#recovery-request).</span></span> <span data-ttu-id="c3602-136">使用此模式响应恢复请求，以从重置程序包操作未成功的 SEMM 注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="c3602-136">Use this mode to respond to a recovery request to unenroll a Surface device from SEMM where a Reset Package operation is not successful.</span></span>


#### <a name="download-microsoft-surface-uefi-configurator"></a><span data-ttu-id="c3602-137">下载 Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="c3602-137">Download Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="c3602-138">你可以从 Microsoft 下载中心的 Surface Tools [for IT 页面](https://www.microsoft.com/download/details.aspx?id=46703) 下载 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="c3602-138">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

### <a name="configuration-package"></a><span data-ttu-id="c3602-139">配置包</span><span class="sxs-lookup"><span data-stu-id="c3602-139">Configuration package</span></span>

<span data-ttu-id="c3602-140">Surface UEFI 配置包是 Surface 设备上实现和管理 SEMM 的主要机制。</span><span class="sxs-lookup"><span data-stu-id="c3602-140">Surface UEFI configuration packages are the primary mechanism to implement and manage SEMM on Surface devices.</span></span> <span data-ttu-id="c3602-141">这些程序包包含 Microsoft Surface UEFI 配置器中程序包创建期间指定的 UEFI 设置的配置文件和证书文件，如图 2 所示。</span><span class="sxs-lookup"><span data-stu-id="c3602-141">These packages contain a configuration file of UEFI settings specified during creation of the package in Microsoft Surface UEFI Configurator and a certificate file, as shown in Figure 2.</span></span> <span data-ttu-id="c3602-142">当配置包首次在尚未在 SEMM 中注册的 Surface 设备上运行时，它会在设备的固件中设置证书文件，并注册 SEMM 中的设备。</span><span class="sxs-lookup"><span data-stu-id="c3602-142">When a configuration package is run for the first time on a Surface device that is not already enrolled in SEMM, it provisions the certificate file in the device’s firmware and enrolls the device in SEMM.</span></span> <span data-ttu-id="c3602-143">在 SEMM 中注册设备时，系统会提示你确认操作，在存储证书文件并完成注册之前，提供 SEMM 证书指纹的最后两位数。</span><span class="sxs-lookup"><span data-stu-id="c3602-143">When enrolling a device in SEMM, you will be prompted to confirm the operation by providing the last two digits of the SEMM certificate thumbprint before the certificate file is stored and the enrollment can complete.</span></span> <span data-ttu-id="c3602-144">此确认要求用户在注册时在设备上实际存在以执行确认。</span><span class="sxs-lookup"><span data-stu-id="c3602-144">This confirmation requires a user be physically present at the device at the time of enrollment to perform the confirmation.</span></span>

![使用证书保护 SEMM 配置包](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*<span data-ttu-id="c3602-146">图 2.</span><span class="sxs-lookup"><span data-stu-id="c3602-146">Figure 2.</span></span> <span data-ttu-id="c3602-147">使用证书保护 SEMM 配置包</span><span class="sxs-lookup"><span data-stu-id="c3602-147">Secure a SEMM configuration package with a certificate</span></span>*

<span data-ttu-id="c3602-148">有关 [SEMM](#surface-enterprise-management-mode-certificate-requirements) 证书要求详细信息，请参阅本文的 Surface Enterprise Management Mode certificate requirements一节。</span><span class="sxs-lookup"><span data-stu-id="c3602-148">See the [Surface Enterprise Management Mode certificate requirements](#surface-enterprise-management-mode-certificate-requirements) section of this article for more information about the requirements for the SEMM certificate.</span></span>

>[!TIP]
><span data-ttu-id="c3602-149">还可以使用 SEMM 指定查看 Surface UEFI 的安全、设备\*\*\*\*、启动\*\*\*\* 配置或企业管理\*\*\*\* 页面所需的 UEFI 密码。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c3602-149">You can also specify a UEFI password with SEMM that is required to view the **Security**, **Devices**, **Boot Configuration**, or **Enterprise Management** pages of Surface UEFI.</span></span>

<span data-ttu-id="c3602-150">在 SEMM 中注册设备后，将读取配置文件，并且该文件中指定的设置将应用于 UEFI。</span><span class="sxs-lookup"><span data-stu-id="c3602-150">After a device is enrolled in SEMM, the configuration file is read and the settings specified in the file are applied to UEFI.</span></span> <span data-ttu-id="c3602-151">当你在已在 SEMM 中注册的设备上运行配置包时，将针对存储在设备固件中的证书检查配置文件的签名。</span><span class="sxs-lookup"><span data-stu-id="c3602-151">When you run a configuration package on a device that is already enrolled in SEMM, the signature of the configuration file is checked against the certificate that is stored in the device firmware.</span></span> <span data-ttu-id="c3602-152">如果签名不匹配，则不向设备应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="c3602-152">If the signature does not match, no changes are applied to the device.</span></span>

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a><span data-ttu-id="c3602-153">使用 SEMM 启用或禁用 Surface UEFI 中的设备</span><span class="sxs-lookup"><span data-stu-id="c3602-153">Enable or disable devices in Surface UEFI with SEMM</span></span>

<span data-ttu-id="c3602-154">以下列表显示了可在 SEMM 中管理的所有可用设备：</span><span class="sxs-lookup"><span data-stu-id="c3602-154">The following list shows all the available devices you can manage in SEMM:</span></span>

* <span data-ttu-id="c3602-155">扩展 USB 端口</span><span class="sxs-lookup"><span data-stu-id="c3602-155">Docking USB Port</span></span>
* <span data-ttu-id="c3602-156">板载音频</span><span class="sxs-lookup"><span data-stu-id="c3602-156">On-board Audio</span></span>
* <span data-ttu-id="c3602-157">DGPU</span><span class="sxs-lookup"><span data-stu-id="c3602-157">DGPU</span></span>
* <span data-ttu-id="c3602-158">Type Cover</span><span class="sxs-lookup"><span data-stu-id="c3602-158">Type Cover</span></span>
* <span data-ttu-id="c3602-159">微型 SD 卡</span><span class="sxs-lookup"><span data-stu-id="c3602-159">Micro SD Card</span></span>
* <span data-ttu-id="c3602-160">前置摄像头</span><span class="sxs-lookup"><span data-stu-id="c3602-160">Front Camera</span></span>
* <span data-ttu-id="c3602-161">后置摄像头</span><span class="sxs-lookup"><span data-stu-id="c3602-161">Rear Camera</span></span>
* <span data-ttu-id="c3602-162">红外相机，适用于 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="c3602-162">Infrared Camera, for Windows Hello</span></span>
* <span data-ttu-id="c3602-163">Bluetooth仅</span><span class="sxs-lookup"><span data-stu-id="c3602-163">Bluetooth Only</span></span>
* <span data-ttu-id="c3602-164">WLAN 和蓝牙</span><span class="sxs-lookup"><span data-stu-id="c3602-164">Wi-Fi and Bluetooth</span></span>
* <span data-ttu-id="c3602-165">             LTE           </span><span class="sxs-lookup"><span data-stu-id="c3602-165">LTE</span></span>

 >[!NOTE]
><span data-ttu-id="c3602-166">显示在 UEFI 设备页面中的内置设备可能因设备或公司环境而异。</span><span class="sxs-lookup"><span data-stu-id="c3602-166">The built-in devices that appear in the UEFI Devices page may vary depending on your device or corporate environment.</span></span> <span data-ttu-id="c3602-167">例如，Surface Pro X 不支持 UEFI 设备页面;LTE 仅在配备 LTE 的设备上显示。</span><span class="sxs-lookup"><span data-stu-id="c3602-167">For example, the UEFI Devices page is not supported on Surface Pro X; LTE only appears on LTE-equipped devices.</span></span> 
### <a name="configure-advanced-settings-with-semm"></a><span data-ttu-id="c3602-168">使用 SEMM 配置高级设置</span><span class="sxs-lookup"><span data-stu-id="c3602-168">Configure advanced settings with SEMM</span></span>
**<span data-ttu-id="c3602-169">表 1.</span><span class="sxs-lookup"><span data-stu-id="c3602-169">Table 1.</span></span> <span data-ttu-id="c3602-170">高级设置</span><span class="sxs-lookup"><span data-stu-id="c3602-170">Advanced settings</span></span>**

| <span data-ttu-id="c3602-171">设置</span><span class="sxs-lookup"><span data-stu-id="c3602-171">Setting</span></span>                            | <span data-ttu-id="c3602-172">描述</span><span class="sxs-lookup"><span data-stu-id="c3602-172">Description</span></span>                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c3602-173">用于 PXE 启动的 IPv6</span><span class="sxs-lookup"><span data-stu-id="c3602-173">IPv6 for PXE Boot</span></span>                  | <span data-ttu-id="c3602-174">允许你管理对 PXE 启动的 IPv6 支持。</span><span class="sxs-lookup"><span data-stu-id="c3602-174">Allows you to manage IPv6 support for PXE boot.</span></span> <span data-ttu-id="c3602-175">如果未配置此设置，则禁用对 PXE 启动的 IPv6 支持。</span><span class="sxs-lookup"><span data-stu-id="c3602-175">If you do not configure this setting, IPv6 support for PXE boot is disabled.</span></span>                                                                               |
| <span data-ttu-id="c3602-176">备用启动</span><span class="sxs-lookup"><span data-stu-id="c3602-176">Alternate Boot</span></span>                     | <span data-ttu-id="c3602-177">允许你管理备用启动顺序的使用，以便通过启动期间同时按"降低音量"按钮和"电源"按钮，直接启动到 USB 或以太网设备。</span><span class="sxs-lookup"><span data-stu-id="c3602-177">Allows you to manage use of an Alternate boot order to boot directly to a USB or Ethernet device by pressing both the Volume Down button and Power button during boot.</span></span> <span data-ttu-id="c3602-178">如果未配置此设置，则启用备用启动。</span><span class="sxs-lookup"><span data-stu-id="c3602-178">If you do not configure this setting, Alternate boot is enabled.</span></span> |
| <span data-ttu-id="c3602-179">启动顺序锁</span><span class="sxs-lookup"><span data-stu-id="c3602-179">Boot Order Lock</span></span>                    | <span data-ttu-id="c3602-180">允许你锁定启动顺序以防止更改。</span><span class="sxs-lookup"><span data-stu-id="c3602-180">Allows you to lock the boot order to prevent changes.</span></span> <span data-ttu-id="c3602-181">如果未配置此设置，则启动顺序锁定处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="c3602-181">If you do not configure this setting, Boot Order Lock is disabled.</span></span>                                                                                                        |
| <span data-ttu-id="c3602-182">USB 启动</span><span class="sxs-lookup"><span data-stu-id="c3602-182">USB Boot</span></span>                           | <span data-ttu-id="c3602-183">允许你管理到 USB 设备的启动。</span><span class="sxs-lookup"><span data-stu-id="c3602-183">Allows you to manage booting to USB devices.</span></span> <span data-ttu-id="c3602-184">如果未配置此设置，将启用 USB 启动。</span><span class="sxs-lookup"><span data-stu-id="c3602-184">If you do not configure this setting, USB Boot is enabled.</span></span>                                                                                                                 |
| <span data-ttu-id="c3602-185">网络堆栈</span><span class="sxs-lookup"><span data-stu-id="c3602-185">Network Stack</span></span>                      | <span data-ttu-id="c3602-186">允许你管理网络堆栈启动设置。</span><span class="sxs-lookup"><span data-stu-id="c3602-186">Allows you to manage Network Stack boot settings.</span></span> <span data-ttu-id="c3602-187">如果未配置此设置，将禁用管理网络堆栈启动设置的能力。</span><span class="sxs-lookup"><span data-stu-id="c3602-187">If you do not configure this setting,  the ability to manage Network Stack boot settings is disabled.</span></span>                                                                                                           |
| <span data-ttu-id="c3602-188">自动打开电源</span><span class="sxs-lookup"><span data-stu-id="c3602-188">Auto Power On</span></span>                      | <span data-ttu-id="c3602-189">允许你管理"自动打开电源"启动设置。</span><span class="sxs-lookup"><span data-stu-id="c3602-189">Allows you to manage Auto Power On boot settings.</span></span> <span data-ttu-id="c3602-190">如果未配置此设置，则启用"自动打开"。</span><span class="sxs-lookup"><span data-stu-id="c3602-190">If you do not configure this setting, Auto Power on is enabled.</span></span>                                                                                                        |
| <span data-ttu-id="c3602-191">同时多线程 (SMT) </span><span class="sxs-lookup"><span data-stu-id="c3602-191">Simultaneous Multi-Threading (SMT)</span></span> | <span data-ttu-id="c3602-192">允许你管理同时多线程 (SMT) 启用或禁用超线程。</span><span class="sxs-lookup"><span data-stu-id="c3602-192">Allows you to manage Simultaneous Multi-Threading (SMT) to enable or disable hyperthreading.</span></span> <span data-ttu-id="c3602-193">如果未配置此设置，则启用 SMT。</span><span class="sxs-lookup"><span data-stu-id="c3602-193">If you do not configure this setting, SMT is enabled.</span></span>                                                  |
|<span data-ttu-id="c3602-194">启用电池限制</span><span class="sxs-lookup"><span data-stu-id="c3602-194">Enable Battery limit</span></span>| <span data-ttu-id="c3602-195">允许你管理电池限制功能。</span><span class="sxs-lookup"><span data-stu-id="c3602-195">Allows you to manage Battery limit functionality.</span></span> <span data-ttu-id="c3602-196">如果未配置此设置，则启用电池限制</span><span class="sxs-lookup"><span data-stu-id="c3602-196">If you do not configure this setting, Battery limit is enabled</span></span> |
| <span data-ttu-id="c3602-197">安全</span><span class="sxs-lookup"><span data-stu-id="c3602-197">Security</span></span>                           | <span data-ttu-id="c3602-198">显示 Surface UEFI **安全** 页。</span><span class="sxs-lookup"><span data-stu-id="c3602-198">Displays the Surface UEFI **Security** page.</span></span> <span data-ttu-id="c3602-199">如果未配置此设置，将显示"安全"页。</span><span class="sxs-lookup"><span data-stu-id="c3602-199">If you do not configure this setting, the Security page is displayed.</span></span>                                                                                                                 |
| <span data-ttu-id="c3602-200">设备</span><span class="sxs-lookup"><span data-stu-id="c3602-200">Devices</span></span>                            | <span data-ttu-id="c3602-201">显示 Surface UEFI **设备** 页面。</span><span class="sxs-lookup"><span data-stu-id="c3602-201">Displays the Surface UEFI **Devices** page.</span></span> <span data-ttu-id="c3602-202">如果未配置此设置，将显示"设备"页。</span><span class="sxs-lookup"><span data-stu-id="c3602-202">If you do not configure this setting,  the Devices page is displayed.</span></span>                                                                                                                     |
| <span data-ttu-id="c3602-203">靴子</span><span class="sxs-lookup"><span data-stu-id="c3602-203">Boot</span></span>                               | <span data-ttu-id="c3602-204">显示 Surface UEFI **启动** 页面。</span><span class="sxs-lookup"><span data-stu-id="c3602-204">Displays the Surface UEFI **Boot** page.</span></span> <span data-ttu-id="c3602-205">如果未配置此设置，将显示"启动"页。</span><span class="sxs-lookup"><span data-stu-id="c3602-205">If you do not configure this setting, the Boot page is displayed.</span></span>                                                                                                                                                            |
| <span data-ttu-id="c3602-206">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3602-206">DateTime</span></span>                           | <span data-ttu-id="c3602-207">显示 Surface UEFI **DateTime** 页。</span><span class="sxs-lookup"><span data-stu-id="c3602-207">Displays the Surface UEFI **DateTime** page.</span></span> <span data-ttu-id="c3602-208">如果未配置此设置，将显示 DateTime 页。</span><span class="sxs-lookup"><span data-stu-id="c3602-208">If you do not configure this setting, the DateTime page is displayed.</span></span>                                                                                                                |
| <span data-ttu-id="c3602-209">EnableOSMigration</span><span class="sxs-lookup"><span data-stu-id="c3602-209">EnableOSMigration</span></span>                          | <span data-ttu-id="c3602-210">允许你将 Surface Hub 2 从 Windows 10 团队迁移到 Windows 10 专业版或企业版。</span><span class="sxs-lookup"><span data-stu-id="c3602-210">Allows you to migrate Surface Hub 2 from Windows 10 Team to Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="c3602-211">如果未配置此设置，Surface Hub 2 设备只能运行 Windows 10 团队操作系统。</span><span class="sxs-lookup"><span data-stu-id="c3602-211">If you do not configure this setting, Surface Hub 2 devices can only run Windows 10 Team OS.</span></span>   <span data-ttu-id="c3602-212">注意：Surface Hub 2 上未提供 Windows 10 团队和 Windows 10 专业/企业版之间的双重启动。</span><span class="sxs-lookup"><span data-stu-id="c3602-212">Note: Dual booting between Windows 10 Team and Windows 10 Pro/Enterprise  is not available on Surface Hub 2.</span></span>                                                                                                           |


>[!NOTE]
><span data-ttu-id="c3602-213">创建 SEMM 配置包时，成功页面上会显示两个字符，\*\*\*\* 如图 3 所示。</span><span class="sxs-lookup"><span data-stu-id="c3602-213">When you create a SEMM configuration package, two characters are shown on the **Successful** page, as shown in Figure 3.</span></span>

![证书指纹显示](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*<span data-ttu-id="c3602-215">图 3.</span><span class="sxs-lookup"><span data-stu-id="c3602-215">Figure 3.</span></span> <span data-ttu-id="c3602-216">在"成功"页上显示证书指纹的最后两个字符</span><span class="sxs-lookup"><span data-stu-id="c3602-216">Display of the last two characters of the certificate thumbprint on the Successful page</span></span>*

<span data-ttu-id="c3602-217">这些字符是证书指纹的最后两个字符，应该记下或记录它们。</span><span class="sxs-lookup"><span data-stu-id="c3602-217">These characters are the last two characters of the certificate thumbprint and should be written down or recorded.</span></span> <span data-ttu-id="c3602-218">确认在 Surface 设备上注册 SEMM 时需要这些字符，如图 4 所示。</span><span class="sxs-lookup"><span data-stu-id="c3602-218">The characters are required to confirm enrollment in SEMM on a Surface device, as shown in Figure 4.</span></span>

![SEMM 中的注册确认](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*<span data-ttu-id="c3602-220">图 4.</span><span class="sxs-lookup"><span data-stu-id="c3602-220">Figure 4.</span></span> <span data-ttu-id="c3602-221">SEMM 中具有 SEMM 证书指纹的注册确认</span><span class="sxs-lookup"><span data-stu-id="c3602-221">Enrollment confirmation in SEMM with the SEMM certificate thumbprint</span></span>*

>[!NOTE]
><span data-ttu-id="c3602-222">有权访问证书文件 (.pfx) 可通过在 CertMgr 中打开 .pfx 文件来随时读取指纹。</span><span class="sxs-lookup"><span data-stu-id="c3602-222">Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr.</span></span> <span data-ttu-id="c3602-223">若要使用 CertMgr 查看指纹：</span><span class="sxs-lookup"><span data-stu-id="c3602-223">To view the thumbprint with CertMgr:</span></span> 
>1. <span data-ttu-id="c3602-224">右键单击 .pfx 文件，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="c3602-224">Right-click the .pfx file, and then click **Open**.</span></span>
>2. <span data-ttu-id="c3602-225">展开导航窗格中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3602-225">Expand the folder in the navigation pane.</span></span>
>3. <span data-ttu-id="c3602-226">单击“**证书**”。</span><span class="sxs-lookup"><span data-stu-id="c3602-226">Click **Certificates**.</span></span>
>4. <span data-ttu-id="c3602-227">右键单击主窗格中的证书，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="c3602-227">Right-click your certificate in the main pane, and then click **Open**.</span></span>
>5. <span data-ttu-id="c3602-228">单击" **详细信息"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c3602-228">Click the **Details** tab.</span></span>
>6. <span data-ttu-id="c3602-229">**必须在** " **显示"** 下拉菜单中选择"全部"或 **"仅属性** "。</span><span class="sxs-lookup"><span data-stu-id="c3602-229">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
>7. <span data-ttu-id="c3602-230">选择字段 **Thumbprint**。</span><span class="sxs-lookup"><span data-stu-id="c3602-230">Select the field **Thumbprint**.</span></span>

<span data-ttu-id="c3602-231">若要在 SEMM 中注册 Surface 设备或应用配置包中的 UEFI 配置，只需在预期的 Surface 设备上使用管理权限运行 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="c3602-231">To enroll a Surface device in SEMM or to apply the UEFI configuration from a configuration package, all you need to do is run the .msi file with administrative privileges on the intended Surface device.</span></span> <span data-ttu-id="c3602-232">可以使用应用程序部署或操作系统部署技术，例如[Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023)或 Microsoft Deployment [Toolkit。](https://technet.microsoft.com/windows/dn475741)</span><span class="sxs-lookup"><span data-stu-id="c3602-232">You can use application deployment or operating system deployment technologies such as [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) or the [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741).</span></span> <span data-ttu-id="c3602-233">在 SEMM 中注册设备时，必须实际存在以确认在设备上注册。</span><span class="sxs-lookup"><span data-stu-id="c3602-233">When you enroll a device in SEMM you must be physically present to confirm the enrollment on the device.</span></span> <span data-ttu-id="c3602-234">将配置应用于已在 SEMM 中注册的设备时，不需要用户交互。</span><span class="sxs-lookup"><span data-stu-id="c3602-234">User interaction is not required when you apply a configuration to devices that are already enrolled in SEMM.</span></span>

<span data-ttu-id="c3602-235">有关如何在 SEMM 中注册 Surface 设备或向 SEMM 应用 Surface UEFI 配置的分步演练，请参阅使用 [SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)注册和配置 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="c3602-235">For a step-by-step walkthrough of how to enroll a Surface device in SEMM or apply a Surface UEFI configuration with SEMM, see [Enroll and configure Surface devices with SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).</span></span>

### <a name="reset-package"></a><span data-ttu-id="c3602-236">重置程序包</span><span class="sxs-lookup"><span data-stu-id="c3602-236">Reset package</span></span>

<span data-ttu-id="c3602-237">Surface UEFI 重置程序包仅用于执行一项任务 - 从 SEMM 注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="c3602-237">A Surface UEFI reset package is used to perform only one task — to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="c3602-238">重置程序包包含从设备固件中删除 SEMM 证书以及将 UEFI 设置重置为出厂默认设置的签名说明。</span><span class="sxs-lookup"><span data-stu-id="c3602-238">The reset package contains signed instructions to remove the SEMM certificate from the device’s firmware and to reset UEFI settings to factory default.</span></span> <span data-ttu-id="c3602-239">与 Surface UEFI 配置包一样，必须使用在 Surface 设备上预配的相同 SEMM 证书对重置程序包进行签名。</span><span class="sxs-lookup"><span data-stu-id="c3602-239">Like a Surface UEFI configuration package, a reset package must be signed with the same SEMM certificate that is provisioned on the Surface device.</span></span> <span data-ttu-id="c3602-240">创建 SEMM 重置程序包时，需要提供要重置的 Surface 设备的序列号。</span><span class="sxs-lookup"><span data-stu-id="c3602-240">When you create a SEMM reset package, you are required to supply the serial number of the Surface device you intend to reset.</span></span> <span data-ttu-id="c3602-241">SEMM 重置程序包不是通用的，并且特定于一台设备。</span><span class="sxs-lookup"><span data-stu-id="c3602-241">SEMM reset packages are not universal and are specific to one device.</span></span>

### <a name="recovery-request"></a><span data-ttu-id="c3602-242">恢复请求</span><span class="sxs-lookup"><span data-stu-id="c3602-242">Recovery request</span></span>

<span data-ttu-id="c3602-243">在某些情况下，可能无法使用 Surface UEFI 重置程序包。</span><span class="sxs-lookup"><span data-stu-id="c3602-243">In some scenarios, it may be impossible to use a Surface UEFI reset package.</span></span> <span data-ttu-id="c3602-244"> (例如，如果 Windows 在 Surface 设备上变得不可用。) 在这些情况下，可以通过 Surface UEFI (的"企业管理"页从 SEM\M\*\*\** 注销 Surface 设备，如图 5) 中的"恢复请求"操作所示。</span><span class="sxs-lookup"><span data-stu-id="c3602-244">(For example, if Windows becomes unusable on the Surface device.) In these scenarios you can unenroll the Surface device from SEMM through the **Enterprise Management** page of Surface UEFI (shown in Figure 5) with a Recovery Request operation.</span></span>

> [!div class="mx-imgBorder"]
> ![启动 SEMM 恢复请求](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*<span data-ttu-id="c3602-246">图 5.</span><span class="sxs-lookup"><span data-stu-id="c3602-246">Figure 5.</span></span> <span data-ttu-id="c3602-247">在"企业管理"页上启动 SEMM 恢复请求</span><span class="sxs-lookup"><span data-stu-id="c3602-247">Initiate a SEMM recovery request on the Enterprise Management page</span></span>*

<span data-ttu-id="c3602-248">当你使用"企业管理"页上的过程\*\*\*\* 在 Surface 设备上重置 SEMM 时，会提供重置请求。</span><span class="sxs-lookup"><span data-stu-id="c3602-248">When you use the process on the **Enterprise Management** page to reset SEMM on a Surface device, you are provided with a Reset Request.</span></span> <span data-ttu-id="c3602-249">此重置请求可以另存为文件到 U 盘、复制为文本，或读取为 QR 码（通过移动设备轻松通过电子邮件发送或发送消息）。</span><span class="sxs-lookup"><span data-stu-id="c3602-249">This Reset Request can be saved as a file to a USB drive, copied as text, or read as a QR Code with a mobile device to be easily emailed or messaged.</span></span> <span data-ttu-id="c3602-250">使用 Microsoft Surface UEFI 配置程序重置请求选项加载重置请求文件或输入重置请求文本或 QR 代码。</span><span class="sxs-lookup"><span data-stu-id="c3602-250">Use the Microsoft Surface UEFI Configurator Reset Request option to load a Reset Request file or enter the Reset Request text or QR Code.</span></span> <span data-ttu-id="c3602-251">Microsoft Surface UEFI 配置器将生成可在 Surface 设备上输入的验证码。</span><span class="sxs-lookup"><span data-stu-id="c3602-251">Microsoft Surface UEFI Configurator will generate a verification code that can be entered on the Surface device.</span></span> <span data-ttu-id="c3602-252">如果你在 Surface 设备上输入代码并单击 **重启，该设备**将注销 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c3602-252">If you enter the code on the Surface device and click **Restart**, the device will be unenrolled from SEMM.</span></span> 

>[!NOTE]
><span data-ttu-id="c3602-253">重置请求将在创建后的两小时后过期。</span><span class="sxs-lookup"><span data-stu-id="c3602-253">A Reset Request expires two hours after it is created.</span></span>

<span data-ttu-id="c3602-254">有关如何从 SEMM 取消注册 Surface 设备的分步演练，请参阅从 SEMM 注销 [Surface 设备](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)。</span><span class="sxs-lookup"><span data-stu-id="c3602-254">For a step-by-step walkthrough of how to unenroll Surface devices from SEMM, see [Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).</span></span>

## <a name="surface-enterprise-management-mode-certificate-requirements"></a><span data-ttu-id="c3602-255">Surface 企业管理模式证书要求</span><span class="sxs-lookup"><span data-stu-id="c3602-255">Surface Enterprise Management Mode certificate requirements</span></span>
<span data-ttu-id="c3602-256">将 SEMM 与 Microsoft Surface UEFI 配置器一同使用需要一个证书来验证配置文件的签名，然后才能应用 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="c3602-256">Using SEMM with Microsoft Surface UEFI Configurator requires a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="c3602-257">此证书可确保在 SEMM 中注册设备后，只有使用已批准证书创建的程序包可用于修改 UEFI 的设置。</span><span class="sxs-lookup"><span data-stu-id="c3602-257">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span>

>[!NOTE]
><span data-ttu-id="c3602-258">在已注册的 Surface 设备上执行对 SEMM 或 Surface UEFI 设置的任何修改时，需要 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="c3602-258">The SEMM certificate is required to perform any modification to SEMM or Surface UEFI settings on enrolled Surface devices.</span></span> <span data-ttu-id="c3602-259">如果 SEMM 证书已损坏或丢失，则不能删除或重置 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c3602-259">If the SEMM certificate is corrupted or lost, SEMM cannot be removed or reset.</span></span> <span data-ttu-id="c3602-260">使用相应的备份和恢复解决方案相应地管理 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="c3602-260">Manage your SEMM certificate accordingly with an appropriate solution for backup and recovery.</span></span>

<span data-ttu-id="c3602-261">使用 Microsoft Surface UEFI 配置器工具创建的程序包使用证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="c3602-261">Packages created with the Microsoft Surface UEFI Configurator tool are signed with a certificate.</span></span> <span data-ttu-id="c3602-262">此证书可确保在 SEMM 中注册设备后，只有使用已批准证书创建的程序包可用于修改 UEFI 的设置。</span><span class="sxs-lookup"><span data-stu-id="c3602-262">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span> 
### <a name="recommended-certificate-settings"></a><span data-ttu-id="c3602-263">建议的证书设置</span><span class="sxs-lookup"><span data-stu-id="c3602-263">Recommended certificate settings</span></span>
<span data-ttu-id="c3602-264">对于 SEMM 证书，建议使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="c3602-264">The following settings are recommended for the SEMM certificate:</span></span>

* <span data-ttu-id="c3602-265">**密钥算法** – RSA</span><span class="sxs-lookup"><span data-stu-id="c3602-265">**Key Algorithm** – RSA</span></span> 
* <span data-ttu-id="c3602-266">**密钥长度** – 2048</span><span class="sxs-lookup"><span data-stu-id="c3602-266">**Key Length** – 2048</span></span>
* <span data-ttu-id="c3602-267">**哈希算法** – SHA-256</span><span class="sxs-lookup"><span data-stu-id="c3602-267">**Hash Algorithm** – SHA-256</span></span>
* <span data-ttu-id="c3602-268">**类型** – SSL 服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="c3602-268">**Type** – SSL Server Authentication</span></span>
* <span data-ttu-id="c3602-269">**密钥用法** – 数字签名、密钥加密</span><span class="sxs-lookup"><span data-stu-id="c3602-269">**Key Usage** – Digital signature, Key Encipherment</span></span>
* <span data-ttu-id="c3602-270">**提供程序** – Microsoft 增强 RSA 和 AES 加密提供程序</span><span class="sxs-lookup"><span data-stu-id="c3602-270">**Provider** – Microsoft Enhanced RSA and AES Cryptographic Provider</span></span>
* <span data-ttu-id="c3602-271">**到期日期** – 自证书创建起 15 个月</span><span class="sxs-lookup"><span data-stu-id="c3602-271">**Expiration Date** – 15 Months from certificate creation</span></span>
* <span data-ttu-id="c3602-272">**密钥导出策略** – 可导出</span><span class="sxs-lookup"><span data-stu-id="c3602-272">**Key Export Policy** – Exportable</span></span>

<span data-ttu-id="c3602-273">还建议在两层公钥基础结构 (PKI) 体系结构中对 SEMM 证书进行身份验证，其中中间证书颁发机构 (CA) 专用于 SEMM，从而启用证书吊销。</span><span class="sxs-lookup"><span data-stu-id="c3602-273">It is also recommended that the SEMM certificate be authenticated in a two-tier public key infrastructure (PKI) architecture where the intermediate certification authority (CA) is dedicated to SEMM, enabling certificate revocation.</span></span> <span data-ttu-id="c3602-274">有关两层 PKI 配置详细信息，请参阅测试实验室指南：部署 [AD CS](https://technet.microsoft.com/library/hh831348)Two-Tier PKI 层次结构。</span><span class="sxs-lookup"><span data-stu-id="c3602-274">For more information about a two-tier PKI configuration, see [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).</span></span>

### <a name="self-signed-certificate"></a><span data-ttu-id="c3602-275">自签名证书</span><span class="sxs-lookup"><span data-stu-id="c3602-275">Self-signed certificate</span></span> 
<span data-ttu-id="c3602-276">可以使用以下示例 PowerShell 脚本创建自签名证书，以用于概念证明方案。</span><span class="sxs-lookup"><span data-stu-id="c3602-276">You can use the following example PowerShell script to create a self-signed certificate for use in proof-of-concept scenarios.</span></span>
<span data-ttu-id="c3602-277">若要使用此脚本，请复制以下文本到记事本，将文件另存为 PowerShell 脚本 (.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="c3602-277">To use this script, copy the following text into Notepad and save the file as a PowerShell script (.ps1).</span></span> 

> [!NOTE]
> <span data-ttu-id="c3602-278">此脚本创建密码为 的证书 `12345678` 。不建议在生产环境中使用此脚本生成的证书。</span><span class="sxs-lookup"><span data-stu-id="c3602-278">This script creates a certificate with a password of `12345678`.The certificate generated by this script is not recommended for production environments.</span></span>
  
```powershell
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
```

>[!IMPORTANT]
><span data-ttu-id="c3602-279">要与 SEMM 和 Microsoft Surface UEFI 配置器一起使用，必须使用私钥和密码保护导出证书。</span><span class="sxs-lookup"><span data-stu-id="c3602-279">For use with SEMM and Microsoft Surface UEFI Configurator, the certificate must be exported with the private key and with password protection.</span></span> <span data-ttu-id="c3602-280">Microsoft Surface UEFI 配置器将提示你选择 SEMM 证书文件 (.pfx) 和证书密码（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="c3602-280">Microsoft Surface UEFI Configurator will prompt you to select the SEMM certificate file (.pfx) and certificate password when it is required.</span></span>

1.  <span data-ttu-id="c3602-281">在 C： 驱动器上创建一个保存脚本的文件夹;例如，C：\SEMM。</span><span class="sxs-lookup"><span data-stu-id="c3602-281">Create a folder on your C: drive where you will save the script; for example, C:\SEMM.</span></span>
2.  <span data-ttu-id="c3602-282">将示例脚本复制到记事本或等效文本编辑器中，将文件另存为 PowerShell 脚本 (.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="c3602-282">Copy the example script into Notepad or equivalent text editor and save the file as a PowerShell script (.ps1).</span></span>
3.  <span data-ttu-id="c3602-283">使用管理员凭据登录电脑并打开提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="c3602-283">Sign into your PC with administrator credentials and open an elevated PowerShell session.</span></span>
4.  <span data-ttu-id="c3602-284">确保将权限设置为允许脚本运行。</span><span class="sxs-lookup"><span data-stu-id="c3602-284">Ensure your permissions are set to allow scripts to run.</span></span> <span data-ttu-id="c3602-285">默认情况下，除非修改执行策略，否则将阻止脚本运行。</span><span class="sxs-lookup"><span data-stu-id="c3602-285">By default, scripts are blocked from running unless you modify the execution policy.</span></span> <span data-ttu-id="c3602-286">若要了解更多信息，请参阅关于 [执行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)。</span><span class="sxs-lookup"><span data-stu-id="c3602-286">To learn more, see [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
5.  <span data-ttu-id="c3602-287">在命令提示符下，输入脚本的完整路径，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="c3602-287">At the command prompt, enter the full path of the script and then press Enter.</span></span> <span data-ttu-id="c3602-288">该脚本将创建一个名为 TempOwner.pfx 的演示证书。</span><span class="sxs-lookup"><span data-stu-id="c3602-288">The script creates a Demo Certificate named TempOwner.pfx.</span></span>

<span data-ttu-id="c3602-289">或者，您可以使用 PowerShell 创建自己的自签名证书。</span><span class="sxs-lookup"><span data-stu-id="c3602-289">Alternatively, you can create your own self-signed certificate using PowerShell.</span></span> <span data-ttu-id="c3602-290">有关详细信息，请参阅以下 PowerShell 文档 [：New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)。</span><span class="sxs-lookup"><span data-stu-id="c3602-290">For more information, see the following PowerShell documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>




>[!NOTE]
><span data-ttu-id="c3602-291">对于在 PKI 基础结构中使用脱机根的组织，Microsoft Surface UEFI 配置器必须在连接到根 CA 的环境中运行，以对 SEMM 证书进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c3602-291">For organizations that use an offline root in their PKI infrastructure, Microsoft Surface UEFI Configurator must be run in an environment connected to the root CA to authenticate the SEMM certificate.</span></span> <span data-ttu-id="c3602-292">Microsoft Surface UEFI 配置器生成的程序包可以文件传输，因此可以使用可移动存储（如 U 盘）在脱机网络环境外部传输。</span><span class="sxs-lookup"><span data-stu-id="c3602-292">The packages generated by Microsoft Surface UEFI Configurator can be transferred as files and therefore can be transferred outside the offline network environment with removable storage, such as a USB stick.</span></span>

### <a name="managing-certificates-faq"></a><span data-ttu-id="c3602-293">管理证书常见问题解答</span><span class="sxs-lookup"><span data-stu-id="c3602-293">Managing certificates FAQ</span></span>

<span data-ttu-id="c3602-294">建议 *的最小长度* 为 15 个月。</span><span class="sxs-lookup"><span data-stu-id="c3602-294">The recommended *minimum* length is 15 months.</span></span> <span data-ttu-id="c3602-295">您可以使用在 15 个月内过期的证书，或使用有效期超过 15 个月的证书。</span><span class="sxs-lookup"><span data-stu-id="c3602-295">You can use a certificate that expires in less than 15 months or use a certificate that expires in longer than 15 months.</span></span>

>[!NOTE] 
><span data-ttu-id="c3602-296">当证书过期时，它不会自动续订。</span><span class="sxs-lookup"><span data-stu-id="c3602-296">When a certificate expires, it does not automatically renew.</span></span> 


**<span data-ttu-id="c3602-297">过期的证书是否会影响 SEMM 注册设备的功能？</span><span class="sxs-lookup"><span data-stu-id="c3602-297">Will an expired certificate affect the functionality of SEMM-enrolled devices?</span></span>**<br><br>
<span data-ttu-id="c3602-298">否，证书仅影响 SEMM 中的 IT 管理员管理任务，在证书过期时不会影响设备功能。</span><span class="sxs-lookup"><span data-stu-id="c3602-298">No, a certificate only impacts IT admin management tasks in SEMM and has no effect on device functionality when it expires.</span></span>


**<span data-ttu-id="c3602-299">是否需要在所有拥有 SEMM 程序包和证书的计算机上进行更新？</span><span class="sxs-lookup"><span data-stu-id="c3602-299">Will the SEMM package and certificate need to be updated on all machines that have it?</span></span>**

<span data-ttu-id="c3602-300">如果希望 SEMM 重置或恢复正常工作，证书必须有效且不会过期。</span><span class="sxs-lookup"><span data-stu-id="c3602-300">If you want SEMM reset or recovery to work, the certificate needs to be valid and not expired.</span></span> 

**<span data-ttu-id="c3602-301">能否为订购的每个图面创建批量重置程序包？</span><span class="sxs-lookup"><span data-stu-id="c3602-301">Can bulk reset packages be created for each surface that we order?</span></span> <span data-ttu-id="c3602-302">能否生成可重置环境中所有计算机的计算机？</span><span class="sxs-lookup"><span data-stu-id="c3602-302">Can one be built that resets all machines in our environment?</span></span>**

<span data-ttu-id="c3602-303">为特定设备类型创建配置包的 PowerShell 示例还可用于创建独立于序列号的重置程序包。</span><span class="sxs-lookup"><span data-stu-id="c3602-303">The PowerShell samples that create a config package for a specific device type can also be used to create a reset package that is serial-number independent.</span></span> <span data-ttu-id="c3602-304">如果证书仍然有效，可以使用 PowerShell 创建重置程序包以重置 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c3602-304">If the certificate is still valid, you can create a reset package using PowerShell to reset SEMM.</span></span>

## <a name="version-history"></a><span data-ttu-id="c3602-305">版本历史记录</span><span class="sxs-lookup"><span data-stu-id="c3602-305">Version History</span></span>

### <a name="version-2791390"></a><span data-ttu-id="c3602-306">版本 2.79.139.0</span><span class="sxs-lookup"><span data-stu-id="c3602-306">Version 2.79.139.0</span></span>

<span data-ttu-id="c3602-307">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c3602-307">This version of SEMM includes:</span></span>
- <span data-ttu-id="c3602-308">支持 Surface Pro 7 及以上</span><span class="sxs-lookup"><span data-stu-id="c3602-308">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="c3602-309">用户体验改进</span><span class="sxs-lookup"><span data-stu-id="c3602-309">User experience improvements</span></span>


### <a name="version-2781390"></a><span data-ttu-id="c3602-310">版本 2.78.139.0</span><span class="sxs-lookup"><span data-stu-id="c3602-310">Version 2.78.139.0</span></span>

<span data-ttu-id="c3602-311">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c3602-311">This version of SEMM includes:</span></span>

- <span data-ttu-id="c3602-312">支持 Surface Laptop Go 和 Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="c3602-312">Support for Surface Laptop Go and Surface Pro X</span></span>
- <span data-ttu-id="c3602-313">新版本发布的通知</span><span class="sxs-lookup"><span data-stu-id="c3602-313">Notifications for new version release</span></span>
- <span data-ttu-id="c3602-314">创建自定义程序包以更改所有权的能力</span><span class="sxs-lookup"><span data-stu-id="c3602-314">Ability to create custom packages to change ownership</span></span>
- <span data-ttu-id="c3602-315">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="c3602-315">Bug fixes</span></span>

### <a name="version-2731360"></a><span data-ttu-id="c3602-316">版本 2.73.136.0</span><span class="sxs-lookup"><span data-stu-id="c3602-316">Version 2.73.136.0</span></span>

<span data-ttu-id="c3602-317">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c3602-317">This version of SEMM includes:</span></span>

- <span data-ttu-id="c3602-318">现在可以使用 SEMM 在 Surface Hub2S 上禁用音频</span><span class="sxs-lookup"><span data-stu-id="c3602-318">Audio can now be disabled on Surface Hub2S using SEMM</span></span>
- <span data-ttu-id="c3602-319">支持适用于扩展坞 2 的 Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="c3602-319">Support to Surface Pro X for Dock 2</span></span>
- <span data-ttu-id="c3602-320">支持 UEFI 管理器执行扩展坞 2 相关操作</span><span class="sxs-lookup"><span data-stu-id="c3602-320">Support to UEFI Manager for Dock 2 related operations</span></span>
- <span data-ttu-id="c3602-321">Surface Go 重置程序包 Bug 修复</span><span class="sxs-lookup"><span data-stu-id="c3602-321">Surface Go reset package bug fix</span></span>
- <span data-ttu-id="c3602-322">支持将 Surface Hub 2 设备从 Windows 10 团队操作系统迁移到 Windows 10 专业版或企业版。</span><span class="sxs-lookup"><span data-stu-id="c3602-322">Support for migrating Surface Hub 2 devices from Windows 10 Team OS to Windows 10 Pro or Enterprise.</span></span>

### <a name="version-2711390"></a><span data-ttu-id="c3602-323">版本 2.71.139.0</span><span class="sxs-lookup"><span data-stu-id="c3602-323">Version 2.71.139.0</span></span>

<span data-ttu-id="c3602-324">此版本的 SEMM 增加了对 Surface Book 3、Surface Laptop 3 和 Surface Pro 7 的 Surface Dock 2 管理功能的支持，包括：</span><span class="sxs-lookup"><span data-stu-id="c3602-324">This version of SEMM adds support for Surface Dock 2 management features  for Surface Book 3, Surface Laptop 3, and Surface Pro 7 including:</span></span>

- <span data-ttu-id="c3602-325">启用音频 (/解锁) 、以太网和 USB 端口</span><span class="sxs-lookup"><span data-stu-id="c3602-325">Enabling audio (locking/unlocking), Ethernet and USB ports</span></span>
- <span data-ttu-id="c3602-326">为经过身份验证和未经身份验证的主机创建扩展坞包的能力</span><span class="sxs-lookup"><span data-stu-id="c3602-326">Ability to create dock packages for both authenticated and unauthenticated hosts</span></span>

### <a name="version-2701300"></a><span data-ttu-id="c3602-327">版本 2.70.130.0</span><span class="sxs-lookup"><span data-stu-id="c3602-327">Version 2.70.130.0</span></span>

<span data-ttu-id="c3602-328">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c3602-328">This version of SEMM includes:</span></span>

- <span data-ttu-id="c3602-329">支持 Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="c3602-329">Support for Surface Go 2</span></span>
- <span data-ttu-id="c3602-330">支持 Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="c3602-330">Support for Surface Book 3</span></span>
- <span data-ttu-id="c3602-331">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="c3602-331">Bug fixes</span></span>


### <a name="version-2591390"></a><span data-ttu-id="c3602-332">版本 2.59.139.0</span><span class="sxs-lookup"><span data-stu-id="c3602-332">Version 2.59.139.0</span></span>

* <span data-ttu-id="c3602-333">支持使用 Intel 处理器的 Surface Pro 7、Surface Pro X 和 Surface Laptop 3 13.5" 和 15"型号。</span><span class="sxs-lookup"><span data-stu-id="c3602-333">Support for Surface Pro 7, Surface Pro X,  and Surface Laptop 3 13.5" and 15" models with Intel processor.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c3602-334">Surface Laptop 3 15" AMD 处理器不受支持。</span><span class="sxs-lookup"><span data-stu-id="c3602-334">Surface Laptop 3 15" AMD processor is not supported.</span></span>

- <span data-ttu-id="c3602-335">支持电源唤醒功能</span><span class="sxs-lookup"><span data-stu-id="c3602-335">Support for Wake on Power feature</span></span>

### <a name="version-2541390"></a><span data-ttu-id="c3602-336">版本 2.54.139.0</span><span class="sxs-lookup"><span data-stu-id="c3602-336">Version 2.54.139.0</span></span>
* <span data-ttu-id="c3602-337">支持 Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="c3602-337">Support to Surface Hub 2S</span></span>
* <span data-ttu-id="c3602-338">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="c3602-338">Bug fixes</span></span>

### <a name="version-2431360"></a><span data-ttu-id="c3602-339">版本 2.43.136.0</span><span class="sxs-lookup"><span data-stu-id="c3602-339">Version 2.43.136.0</span></span>
* <span data-ttu-id="c3602-340">支持启用/禁用模拟多线程</span><span class="sxs-lookup"><span data-stu-id="c3602-340">Support to enable/disable simulatenous multithreating</span></span> 
* <span data-ttu-id="c3602-341">某些设备的 WiFi 和 Bluetooth选项</span><span class="sxs-lookup"><span data-stu-id="c3602-341">Separate options for WiFi and Bluetooth for some devices</span></span> 
* <span data-ttu-id="c3602-342">已删除 Surface Studio 的电池限制</span><span class="sxs-lookup"><span data-stu-id="c3602-342">Battery Limit removed for Surface Studio</span></span> 

### <a name="version-2261360"></a><span data-ttu-id="c3602-343">版本 2.26.136.0</span><span class="sxs-lookup"><span data-stu-id="c3602-343">Version 2.26.136.0</span></span>
* <span data-ttu-id="c3602-344">添加对 Surface Studio 2 的支持</span><span class="sxs-lookup"><span data-stu-id="c3602-344">Add support to Surface Studio 2</span></span>
* <span data-ttu-id="c3602-345">电池限制功能</span><span class="sxs-lookup"><span data-stu-id="c3602-345">Battery Limit feature</span></span>

### <a name="version-2211360"></a><span data-ttu-id="c3602-346">版本 2.21.136.0</span><span class="sxs-lookup"><span data-stu-id="c3602-346">Version 2.21.136.0</span></span>
* <span data-ttu-id="c3602-347">添加对 Surface Pro 6 的支持</span><span class="sxs-lookup"><span data-stu-id="c3602-347">Add support to Surface Pro 6</span></span>
* <span data-ttu-id="c3602-348">添加对 Surface Laptop 2 的支持</span><span class="sxs-lookup"><span data-stu-id="c3602-348">Add support to Surface Laptop 2</span></span>

### <a name="version-2141360"></a><span data-ttu-id="c3602-349">版本 2.14.136.0</span><span class="sxs-lookup"><span data-stu-id="c3602-349">Version 2.14.136.0</span></span>
* <span data-ttu-id="c3602-350">向 Surface Go 添加支持</span><span class="sxs-lookup"><span data-stu-id="c3602-350">Add support to Surface Go</span></span>

### <a name="version-291360"></a><span data-ttu-id="c3602-351">版本 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="c3602-351">Version 2.9.136.0</span></span>
* <span data-ttu-id="c3602-352">添加对 Surface Book 2 的支持</span><span class="sxs-lookup"><span data-stu-id="c3602-352">Add support to Surface Book 2</span></span>
* <span data-ttu-id="c3602-353">添加对 Surface Pro LTE 的支持</span><span class="sxs-lookup"><span data-stu-id="c3602-353">Add support to Surface Pro LTE</span></span>
* <span data-ttu-id="c3602-354">辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="c3602-354">Accessibility improvements</span></span>

### <a name="version-10740"></a><span data-ttu-id="c3602-355">版本 1.0.74.0</span><span class="sxs-lookup"><span data-stu-id="c3602-355">Version 1.0.74.0</span></span>
* <span data-ttu-id="c3602-356">向 Surface Laptop 添加支持</span><span class="sxs-lookup"><span data-stu-id="c3602-356">Add support to Surface Laptop</span></span>
* <span data-ttu-id="c3602-357">向 Surface Pro 添加支持</span><span class="sxs-lookup"><span data-stu-id="c3602-357">Add support to Surface Pro</span></span>
* <span data-ttu-id="c3602-358">Bug 修复和常规改进</span><span class="sxs-lookup"><span data-stu-id="c3602-358">Bug fixes and general improvement</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3602-359">相关主题</span><span class="sxs-lookup"><span data-stu-id="c3602-359">Related topics</span></span>

- [<span data-ttu-id="c3602-360">使用 SEMM 注册并配置 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="c3602-360">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)
- [<span data-ttu-id="c3602-361">从 SEMM 取消注册 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="c3602-361">Unenroll Surface devices from SEMM</span></span>](unenroll-surface-devices-from-semm.md)
- [<span data-ttu-id="c3602-362">使用 SEMM 保护 Surface Dock 2 端口</span><span class="sxs-lookup"><span data-stu-id="c3602-362">Secure Surface Dock 2 ports with SEMM</span></span>](secure-surface-dock-ports-semm.md)

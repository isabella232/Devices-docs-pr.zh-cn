---
title: 'Surface Enterprise 管理模式 (Surface) '
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
ms.date: 04/16/2021
ms.openlocfilehash: 3c7eea524daa3210a329c41536f4c47a2c012bcf
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576582"
---
# <a name="microsoft-surface-enterprise-management-mode"></a><span data-ttu-id="02212-104">Microsoft Surface Enterprise 管理模式</span><span class="sxs-lookup"><span data-stu-id="02212-104">Microsoft Surface Enterprise Management Mode</span></span>

<span data-ttu-id="02212-105">Microsoft Surface Enterprise Management Mode (SEMM) 是 Surface 统一可扩展固件接口与 UEFI () 的功能。</span><span class="sxs-lookup"><span data-stu-id="02212-105">Microsoft Surface Enterprise Management Mode (SEMM) is a feature of Surface devices with Surface Unified Extensible Firmware Interface (UEFI).</span></span> <span data-ttu-id="02212-106">可以使用 SEMM：</span><span class="sxs-lookup"><span data-stu-id="02212-106">You can use SEMM to:</span></span>

- <span data-ttu-id="02212-107">保护和管理贵组织的固件设置。</span><span class="sxs-lookup"><span data-stu-id="02212-107">Secure and manage firmware settings in your organization.</span></span>
- <span data-ttu-id="02212-108">准备 UEFI 设置配置，然后将它们安装在 Surface 设备上。</span><span class="sxs-lookup"><span data-stu-id="02212-108">Prepare UEFI settings configurations and install them on a Surface device.</span></span> 

<span data-ttu-id="02212-109">SEMM 还使用证书保护配置免受未经授权的篡改或删除。</span><span class="sxs-lookup"><span data-stu-id="02212-109">SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal.</span></span> <span data-ttu-id="02212-110">若要将 Surface Hub 2S 迁移到 Windows 10 专业版 或 Windows Enterprise，需要 SEMM。</span><span class="sxs-lookup"><span data-stu-id="02212-110">To migrate a Surface Hub 2S to Windows 10 Pro or Windows Enterprise, SEMM is required.</span></span>

>[!NOTE]
><span data-ttu-id="02212-111">SEMM 仅在具有 Surface UEFI 固件的设备上可用。</span><span class="sxs-lookup"><span data-stu-id="02212-111">SEMM is only available on devices with Surface UEFI firmware.</span></span> <span data-ttu-id="02212-112">这包括大多数其他 Surface 设备，包括带 Intel 处理器的 Surface Pro 7+、Surface Pro X、Surface Hub 2S、Surface Laptop 4 商业 S CPU、Surface Laptop 4 台商业 S CPU 和 AMD 处理器、Surface Laptop 3 台商业 SK（含 Intel 处理器）和 Surface Laptop Go。</span><span class="sxs-lookup"><span data-stu-id="02212-112">This includes most other Surface devices including Surface Pro 7+, Surface Pro X, Surface Hub 2S, Surface Laptop 4 commercial SKUs with an Intel processor, Surface Laptop 4 commercial SKUs with AMD processor, Surface Laptop 3 commercial SKUs with an Intel processor, and Surface Laptop Go.</span></span> <span data-ttu-id="02212-113">带 AMD 处理器的 15" Surface Laptop 3 SKU 不支持 SEMM (仅作为零售 SKU) 。</span><span class="sxs-lookup"><span data-stu-id="02212-113">SEMM is not supported on the 15" Surface Laptop 3 SKU with AMD processor (available only as a retail SKU).</span></span> 

<span data-ttu-id="02212-114">当 Surface 设备由 SEMM 配置且使用 SEMM 证书进行保护时，它们将被视为 *在* SEMM 中注册。</span><span class="sxs-lookup"><span data-stu-id="02212-114">When Surface devices are configured by SEMM and secured with the SEMM certificate, they're considered *enrolled* in SEMM.</span></span> <span data-ttu-id="02212-115">当删除 SEMM 证书并控制 UEFI 设置时，将 Surface 设备视为在 SEMM\*\* 中注销。</span><span class="sxs-lookup"><span data-stu-id="02212-115">When the SEMM certificate is removed and control of UEFI settings is returned to the user of the device, the Surface device is considered *unenrolled* in SEMM.</span></span>

<span data-ttu-id="02212-116">有两个管理选项可用于管理 SEMM 和注册 Surface 设备：</span><span class="sxs-lookup"><span data-stu-id="02212-116">There are two administrative options that you can use to manage SEMM and enroll Surface devices:</span></span>

- <span data-ttu-id="02212-117">本文介绍了 SEMM 独立工具 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="02212-117">SEMM standalone tool, Microsoft Surface UEFI Configurator, is described in this article.</span></span> 

- <span data-ttu-id="02212-118">与 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="02212-118">Integration with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="02212-119">有关信息，请参阅[使用Microsoft Endpoint Configuration Manager SEMM 管理设备](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)。</span><span class="sxs-lookup"><span data-stu-id="02212-119">For information, see [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).</span></span>

> [!NOTE]
> <span data-ttu-id="02212-120">仅通过 UEFI Surface Pro X 支持 SEMM。</span><span class="sxs-lookup"><span data-stu-id="02212-120">SEMM is supported on Surface Pro X via the UEFI Manager only.</span></span> <span data-ttu-id="02212-121">你可以从适用于 IT 的 [Surface Tools 下载](https://www.microsoft.com/download/details.aspx?id=46703)UEFI 管理器。</span><span class="sxs-lookup"><span data-stu-id="02212-121">You can download UEFI Manager from [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="02212-122">有关详细信息，请参阅部署[、管理和维护 Surface Pro X。](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="02212-122">For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>


## <a name="microsoft-surface-uefi-configurator"></a><span data-ttu-id="02212-123">Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="02212-123">Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="02212-124">SEMM 的主要工作区是 Microsoft Surface UEFI 配置器，如图 1 所示。</span><span class="sxs-lookup"><span data-stu-id="02212-124">The primary workspace of SEMM is Microsoft Surface UEFI Configurator, as shown in Figure 1.</span></span> 

<span data-ttu-id="02212-125">可以使用 Microsoft Surface UEFI 配置器：</span><span class="sxs-lookup"><span data-stu-id="02212-125">You can use Microsoft Surface UEFI Configurator to:</span></span>

- <span data-ttu-id="02212-126">创建Windows安装程序 (.msi) 程序包。</span><span class="sxs-lookup"><span data-stu-id="02212-126">Create Windows Installer (.msi) packages.</span></span>
- <span data-ttu-id="02212-127">使用 WinPE 映像在 Surface 设备上注册、配置和注销 SEMM。</span><span class="sxs-lookup"><span data-stu-id="02212-127">Use WinPE images to enroll, configure, and unenroll SEMM on a Surface device.</span></span> 

<span data-ttu-id="02212-128">这些程序包包含指定 UEFI 设置的配置文件。</span><span class="sxs-lookup"><span data-stu-id="02212-128">These packages contain a configuration file that specifies the UEFI settings.</span></span> <span data-ttu-id="02212-129">SEMM 包还包含在固件中安装并存储的证书，用于在应用 UEFI 设置之前验证配置文件的签名。</span><span class="sxs-lookup"><span data-stu-id="02212-129">SEMM packages also contain a certificate that's installed and stored in firmware and is used to verify the signature of configuration files before UEFI settings are applied.</span></span>

>[!TIP]
><span data-ttu-id="02212-130">你现在可以使用 Surface UEFI 配置器和 SEMM 管理 Surface 扩展坞 2 上的端口。</span><span class="sxs-lookup"><span data-stu-id="02212-130">You can now use Surface UEFI Configurator and SEMM to manage ports on Surface Dock 2.</span></span> <span data-ttu-id="02212-131">若要了解更多信息，请参阅使用 SEMM 保护 [Surface Dock 2 端口](secure-surface-dock-ports-semm.md)。</span><span class="sxs-lookup"><span data-stu-id="02212-131">To learn more, see [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).</span></span>

![Microsoft Surface UEFI 配置器](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*<span data-ttu-id="02212-133">图 1.</span><span class="sxs-lookup"><span data-stu-id="02212-133">Figure 1.</span></span> <span data-ttu-id="02212-134">Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="02212-134">Microsoft Surface UEFI Configurator</span></span>*

<span data-ttu-id="02212-135">可以在三种模式下使用 Microsoft Surface UEFI 配置器工具：</span><span class="sxs-lookup"><span data-stu-id="02212-135">You can use the Microsoft Surface UEFI Configurator tool in three modes:</span></span>

- <span data-ttu-id="02212-136">[Surface UEFI 配置包](#configuration-package)。</span><span class="sxs-lookup"><span data-stu-id="02212-136">[Surface UEFI Configuration Package](#configuration-package).</span></span> <span data-ttu-id="02212-137">使用此模式创建 Surface UEFI 配置包，以在 SEMM 中注册 Surface 设备，并配置已注册设备的 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="02212-137">Use this mode to create a Surface UEFI configuration package to enroll a Surface device in SEMM and to configure UEFI settings on enrolled devices.</span></span>
- <span data-ttu-id="02212-138">[Surface UEFI 重置程序包](#reset-package)。</span><span class="sxs-lookup"><span data-stu-id="02212-138">[Surface UEFI Reset Package](#reset-package).</span></span> <span data-ttu-id="02212-139">使用此模式从 SEMM 注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="02212-139">Use this mode to unenroll a Surface device from SEMM.</span></span>
- <span data-ttu-id="02212-140">[Surface UEFI 恢复请求](#recovery-request)。</span><span class="sxs-lookup"><span data-stu-id="02212-140">[Surface UEFI Recovery Request](#recovery-request).</span></span> <span data-ttu-id="02212-141">使用此模式响应恢复请求，以从重置程序包操作未成功的 SEMM 注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="02212-141">Use this mode to respond to a recovery request to unenroll a Surface device from SEMM where a Reset Package operation is not successful.</span></span>

#### <a name="download-microsoft-surface-uefi-configurator"></a><span data-ttu-id="02212-142">下载 Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="02212-142">Download Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="02212-143">你可以从 Microsoft 下载中心的 Surface Tools [for IT 页面](https://www.microsoft.com/download/details.aspx?id=46703) 下载 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="02212-143">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

### <a name="configuration-package"></a><span data-ttu-id="02212-144">配置包</span><span class="sxs-lookup"><span data-stu-id="02212-144">Configuration package</span></span>

<span data-ttu-id="02212-145">Surface UEFI 配置包是 Surface 设备上实现和管理 SEMM 的主要机制。</span><span class="sxs-lookup"><span data-stu-id="02212-145">Surface UEFI configuration packages are the primary mechanism to implement and manage SEMM on Surface devices.</span></span> <span data-ttu-id="02212-146">这些包包含配置文件和证书文件，如图 2 所示。</span><span class="sxs-lookup"><span data-stu-id="02212-146">These packages contain a configuration file and a certificate file, as shown in Figure 2.</span></span> <span data-ttu-id="02212-147">配置文件包含在 Microsoft Surface UEFI 配置器中创建程序包时指定的 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="02212-147">The configuration file contains UEFI settings that are specified when the package is created in Microsoft Surface UEFI Configurator.</span></span> <span data-ttu-id="02212-148">当配置包首次在尚未在 SEMM 中注册的 Surface 设备上运行时，它会在设备的固件中设置证书文件，并注册 SEMM 中的设备。</span><span class="sxs-lookup"><span data-stu-id="02212-148">When a configuration package runs for the first time on a Surface device that's not already enrolled in SEMM, it provisions the certificate file in the device’s firmware and enrolls the device in SEMM.</span></span> <span data-ttu-id="02212-149">在 SEMM 中注册设备时，在存储证书并完成注册之前，系统会提示你通过提供 SEMM 证书指纹的最后两位数来确认操作。</span><span class="sxs-lookup"><span data-stu-id="02212-149">When enrolling a device in SEMM, and before the certificate is stored and the enrollment finishes, you're prompted to confirm the operation by providing the last two digits of the SEMM certificate thumbprint.</span></span> <span data-ttu-id="02212-150">此确认要求用户在注册期间实际存在于设备上才能执行确认。</span><span class="sxs-lookup"><span data-stu-id="02212-150">This confirmation requires a user to be physically present at the device during enrollment to perform the confirmation.</span></span>

![使用证书保护 SEMM 配置包](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*<span data-ttu-id="02212-152">图 2.</span><span class="sxs-lookup"><span data-stu-id="02212-152">Figure 2.</span></span> <span data-ttu-id="02212-153">使用证书保护 SEMM 配置包</span><span class="sxs-lookup"><span data-stu-id="02212-153">Secure a SEMM configuration package with a certificate</span></span>*

<span data-ttu-id="02212-154">有关 SEMM 证书的要求详细信息，请参阅本文稍后介绍的[Surface Enterprise 管理](#surface-enterprise-management-mode-certificate-requirements)模式证书要求部分。</span><span class="sxs-lookup"><span data-stu-id="02212-154">For more information about the requirements for the SEMM certificate, see the [Surface Enterprise Management Mode certificate requirements](#surface-enterprise-management-mode-certificate-requirements) section later in this article.</span></span>

>[!TIP]
><span data-ttu-id="02212-155">可以选择要求使用 SEMM 输入 UEFI 密码。</span><span class="sxs-lookup"><span data-stu-id="02212-155">You have the option to require a UEFI password with SEMM.</span></span> <span data-ttu-id="02212-156">如果你这样做，需要密码才能查看 Surface UEFI\*\*\*\* 的安全、\*\*\*\* 设备、启动配置**Enterprise**管理"页面。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="02212-156">If you do, the password is required to view the **Security**, **Devices**, **Boot Configuration**, and **Enterprise Management** pages of Surface UEFI.</span></span>

<span data-ttu-id="02212-157">在 SEMM 中注册设备后，将读取配置文件，并且该文件中指定的设置将应用于 UEFI。</span><span class="sxs-lookup"><span data-stu-id="02212-157">After a device is enrolled in SEMM, the configuration file is read, and the settings specified in the file are applied to UEFI.</span></span> <span data-ttu-id="02212-158">当你在已在 SEMM 中注册的设备上运行配置包时，将针对存储在设备固件中的证书检查配置文件的签名。</span><span class="sxs-lookup"><span data-stu-id="02212-158">When you run a configuration package on a device that's already enrolled in SEMM, the signature of the configuration file is checked against the certificate that's stored in the device firmware.</span></span> <span data-ttu-id="02212-159">如果签名不匹配，则不对设备应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="02212-159">If the signature doesn't match, no changes are applied to the device.</span></span>

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a><span data-ttu-id="02212-160">使用 SEMM 启用或禁用 Surface UEFI 中的设备</span><span class="sxs-lookup"><span data-stu-id="02212-160">Enable or disable devices in Surface UEFI with SEMM</span></span>

<span data-ttu-id="02212-161">以下列表显示了可在 SEMM 中管理的所有可用设备：</span><span class="sxs-lookup"><span data-stu-id="02212-161">The following list shows all the available devices that you can manage in SEMM:</span></span>

- <span data-ttu-id="02212-162">扩展 USB 端口</span><span class="sxs-lookup"><span data-stu-id="02212-162">Docking USB port</span></span>
- <span data-ttu-id="02212-163">板载音频</span><span class="sxs-lookup"><span data-stu-id="02212-163">On-board audio</span></span>
- <span data-ttu-id="02212-164">数字图形处理单元</span><span class="sxs-lookup"><span data-stu-id="02212-164">Digital graphics processing unit</span></span>
- <span data-ttu-id="02212-165">类型覆盖</span><span class="sxs-lookup"><span data-stu-id="02212-165">Type cover</span></span>
- <span data-ttu-id="02212-166">微型 SD 卡</span><span class="sxs-lookup"><span data-stu-id="02212-166">Micro SD card</span></span>
- <span data-ttu-id="02212-167">前置摄像头</span><span class="sxs-lookup"><span data-stu-id="02212-167">Front camera</span></span>
- <span data-ttu-id="02212-168">后置摄像头</span><span class="sxs-lookup"><span data-stu-id="02212-168">Rear camera</span></span>
- <span data-ttu-id="02212-169"> (Hello Windows红外) </span><span class="sxs-lookup"><span data-stu-id="02212-169">Infrared camera (for Windows Hello)</span></span>
- <span data-ttu-id="02212-170">仅蓝牙</span><span class="sxs-lookup"><span data-stu-id="02212-170">Bluetooth only</span></span>
- <span data-ttu-id="02212-171">无线网络和蓝牙</span><span class="sxs-lookup"><span data-stu-id="02212-171">Wireless network and Bluetooth</span></span>
- <span data-ttu-id="02212-172">LTE (长期) </span><span class="sxs-lookup"><span data-stu-id="02212-172">Long-term evolution (LTE)</span></span>

 >[!NOTE]
><span data-ttu-id="02212-173">在"UEFI 设备"页上，内置设备可能会有所不同，具体取决于设备或公司环境。</span><span class="sxs-lookup"><span data-stu-id="02212-173">On the UEFI Devices page, the built-in devices might vary, depending on your device or corporate environment.</span></span> <span data-ttu-id="02212-174">例如，UEFI 设备页面在 X 上不受Surface Pro支持;LTE 仅在配备了 LTE 的设备上显示。</span><span class="sxs-lookup"><span data-stu-id="02212-174">For example, the UEFI Devices page isn't supported on Surface Pro X; LTE appears only on LTE-equipped devices.</span></span> 
### <a name="configure-advanced-settings-with-semm"></a><span data-ttu-id="02212-175">使用 SEMM 配置高级设置</span><span class="sxs-lookup"><span data-stu-id="02212-175">Configure advanced settings with SEMM</span></span>
**<span data-ttu-id="02212-176">表 1.</span><span class="sxs-lookup"><span data-stu-id="02212-176">Table 1.</span></span> <span data-ttu-id="02212-177">高级设置</span><span class="sxs-lookup"><span data-stu-id="02212-177">Advanced settings</span></span>**

| <span data-ttu-id="02212-178">设置</span><span class="sxs-lookup"><span data-stu-id="02212-178">Setting</span></span>                            | <span data-ttu-id="02212-179">描述</span><span class="sxs-lookup"><span data-stu-id="02212-179">Description</span></span>                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="02212-180">用于 PXE 启动的 IPv6</span><span class="sxs-lookup"><span data-stu-id="02212-180">IPv6 for PXE Boot</span></span>                  | <span data-ttu-id="02212-181">允许你管理对 PXE 启动的 IPv6 支持。</span><span class="sxs-lookup"><span data-stu-id="02212-181">Allows you to manage IPv6 support for PXE boot.</span></span> <span data-ttu-id="02212-182">如果未配置此设置，则禁用对 PXE 启动的 IPv6 支持。</span><span class="sxs-lookup"><span data-stu-id="02212-182">If you don't configure this setting, IPv6 support for PXE boot is disabled.</span></span>                                                                               |
| <span data-ttu-id="02212-183">备用启动</span><span class="sxs-lookup"><span data-stu-id="02212-183">Alternate Boot</span></span>                     | <span data-ttu-id="02212-184">允许你管理备用启动顺序的使用，以便通过启动期间同时按"降低音量"按钮和"电源"按钮，直接启动到 USB 或以太网设备。</span><span class="sxs-lookup"><span data-stu-id="02212-184">Allows you to manage the use of an Alternate boot order to boot directly to a USB or Ethernet device by pressing both the Volume Down button and Power button during boot.</span></span> <span data-ttu-id="02212-185">如果未配置此设置，则启用备用启动。</span><span class="sxs-lookup"><span data-stu-id="02212-185">If you don't configure this setting, Alternate boot is enabled.</span></span> |
| <span data-ttu-id="02212-186">启动顺序锁</span><span class="sxs-lookup"><span data-stu-id="02212-186">Boot Order Lock</span></span>                    | <span data-ttu-id="02212-187">允许你锁定启动顺序以防止更改。</span><span class="sxs-lookup"><span data-stu-id="02212-187">Allows you to lock the boot order to prevent changes.</span></span> <span data-ttu-id="02212-188">如果未配置此设置，则启动顺序锁定处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="02212-188">If you don't configure this setting, Boot Order Lock is disabled.</span></span>                                                                                                        |
| <span data-ttu-id="02212-189">USB 启动</span><span class="sxs-lookup"><span data-stu-id="02212-189">USB Boot</span></span>                           | <span data-ttu-id="02212-190">允许你管理到 USB 设备的启动。</span><span class="sxs-lookup"><span data-stu-id="02212-190">Allows you to manage booting to USB devices.</span></span> <span data-ttu-id="02212-191">如果未配置此设置，将启用 USB 启动。</span><span class="sxs-lookup"><span data-stu-id="02212-191">If you don't configure this setting, USB Boot is enabled.</span></span>                                                                                                                 |
| <span data-ttu-id="02212-192">网络堆栈</span><span class="sxs-lookup"><span data-stu-id="02212-192">Network Stack</span></span>                      | <span data-ttu-id="02212-193">允许你管理网络堆栈启动设置。</span><span class="sxs-lookup"><span data-stu-id="02212-193">Allows you to manage Network Stack boot settings.</span></span> <span data-ttu-id="02212-194">如果未配置此设置，将禁用管理网络堆栈启动设置的能力。</span><span class="sxs-lookup"><span data-stu-id="02212-194">If you don't configure this setting,  the ability to manage Network Stack boot settings is disabled.</span></span>                                                                                                           |
| <span data-ttu-id="02212-195">自动打开电源</span><span class="sxs-lookup"><span data-stu-id="02212-195">Auto Power On</span></span>                      | <span data-ttu-id="02212-196">允许你管理"自动打开电源"启动设置。</span><span class="sxs-lookup"><span data-stu-id="02212-196">Allows you to manage Auto Power On boot settings.</span></span> <span data-ttu-id="02212-197">如果未配置此设置，则启用"自动打开"。</span><span class="sxs-lookup"><span data-stu-id="02212-197">If you don't configure this setting, Auto Power on is enabled.</span></span>                                                                                                        |
| <span data-ttu-id="02212-198">同时多线程 (SMT) </span><span class="sxs-lookup"><span data-stu-id="02212-198">Simultaneous Multi-Threading (SMT)</span></span> | <span data-ttu-id="02212-199">允许你管理同时多线程 (SMT) 启用或禁用超线程。</span><span class="sxs-lookup"><span data-stu-id="02212-199">Allows you to manage Simultaneous Multi-Threading (SMT) to enable or disable hyperthreading.</span></span> <span data-ttu-id="02212-200">如果未配置此设置，则启用 SMT。</span><span class="sxs-lookup"><span data-stu-id="02212-200">If you don't configure this setting, SMT is enabled.</span></span>                                                  |
|<span data-ttu-id="02212-201">启用电池限制</span><span class="sxs-lookup"><span data-stu-id="02212-201">Enable Battery limit</span></span>| <span data-ttu-id="02212-202">允许你管理电池限制功能。</span><span class="sxs-lookup"><span data-stu-id="02212-202">Allows you to manage Battery limit functionality.</span></span> <span data-ttu-id="02212-203">如果未配置此设置，则启用电池限制</span><span class="sxs-lookup"><span data-stu-id="02212-203">If you don't configure this setting, Battery limit is enabled</span></span> |
| <span data-ttu-id="02212-204">安全性</span><span class="sxs-lookup"><span data-stu-id="02212-204">Security</span></span>                           | <span data-ttu-id="02212-205">显示 Surface UEFI **安全** 页。</span><span class="sxs-lookup"><span data-stu-id="02212-205">Displays the Surface UEFI **Security** page.</span></span> <span data-ttu-id="02212-206">如果未配置此设置，将显示"安全"页。</span><span class="sxs-lookup"><span data-stu-id="02212-206">If you don't configure this setting, the Security page is displayed.</span></span>                                                                                                                 |
| <span data-ttu-id="02212-207">设备</span><span class="sxs-lookup"><span data-stu-id="02212-207">Devices</span></span>                            | <span data-ttu-id="02212-208">显示 Surface UEFI **设备** 页面。</span><span class="sxs-lookup"><span data-stu-id="02212-208">Displays the Surface UEFI **Devices** page.</span></span> <span data-ttu-id="02212-209">如果未配置此设置，将显示"设备"页。</span><span class="sxs-lookup"><span data-stu-id="02212-209">If you don't configure this setting,  the Devices page is displayed.</span></span>                                                                                                                     |
| <span data-ttu-id="02212-210">靴子</span><span class="sxs-lookup"><span data-stu-id="02212-210">Boot</span></span>                               | <span data-ttu-id="02212-211">显示 Surface UEFI **启动** 页面。</span><span class="sxs-lookup"><span data-stu-id="02212-211">Displays the Surface UEFI **Boot** page.</span></span> <span data-ttu-id="02212-212">如果未配置此设置，将显示"启动"页。</span><span class="sxs-lookup"><span data-stu-id="02212-212">If you don't configure this setting, the Boot page is displayed.</span></span>                                                                                                                                                            |
| <span data-ttu-id="02212-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="02212-213">DateTime</span></span>                           | <span data-ttu-id="02212-214">显示 Surface UEFI **DateTime** 页。</span><span class="sxs-lookup"><span data-stu-id="02212-214">Displays the Surface UEFI **DateTime** page.</span></span> <span data-ttu-id="02212-215">如果未配置此设置，将显示 DateTime 页。</span><span class="sxs-lookup"><span data-stu-id="02212-215">If you don't configure this setting, the DateTime page is displayed.</span></span>                                                                                                                |
| <span data-ttu-id="02212-216">EnableOSMigration</span><span class="sxs-lookup"><span data-stu-id="02212-216">EnableOSMigration</span></span>                          | <span data-ttu-id="02212-217">允许您将 Surface Hub 2 从 Windows 10 协同版 迁移到 Windows 10 专业版 或 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="02212-217">Allows you to migrate Surface Hub 2 from Windows 10 Team to Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="02212-218">如果未配置此设置，则 Surface Hub 2 台设备只能运行Windows 10 协同版操作系统。</span><span class="sxs-lookup"><span data-stu-id="02212-218">If you don't configure this setting, Surface Hub 2 devices can run only the Windows 10 Team OS.</span></span> <span data-ttu-id="02212-219">注意：Windows 10 协同版 2 Windows 10 专业版/Enterprise之间的双Surface Hub启动。</span><span class="sxs-lookup"><span data-stu-id="02212-219">Note: Dual booting between Windows 10 Team and Windows 10 Pro/Enterprise isn't available on Surface Hub 2.</span></span>                                                                                                           |


>[!NOTE]
><span data-ttu-id="02212-220">创建 SEMM 配置包时，成功页面上会显示两个字符，\*\*\*\* 如图 3 所示。</span><span class="sxs-lookup"><span data-stu-id="02212-220">When you create a SEMM configuration package, two characters are shown on the **Successful** page, as shown in Figure 3.</span></span>

![证书指纹显示](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*<span data-ttu-id="02212-222">图 3.</span><span class="sxs-lookup"><span data-stu-id="02212-222">Figure 3.</span></span> <span data-ttu-id="02212-223">在"成功"页上显示证书指纹的最后两个字符</span><span class="sxs-lookup"><span data-stu-id="02212-223">Display of the last two characters of the certificate thumbprint on the Successful page</span></span>*

<span data-ttu-id="02212-224">这些字符是证书指纹的最后两个字符，应该记下或记录它们。</span><span class="sxs-lookup"><span data-stu-id="02212-224">These characters are the last two characters of the certificate thumbprint and should be written down or recorded.</span></span> <span data-ttu-id="02212-225">确认在 Surface 设备上注册 SEMM 时需要这些字符，如图 4 所示。</span><span class="sxs-lookup"><span data-stu-id="02212-225">The characters are required to confirm enrollment in SEMM on a Surface device, as shown in Figure 4.</span></span>

![SEMM 中的注册确认](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*<span data-ttu-id="02212-227">图 4.</span><span class="sxs-lookup"><span data-stu-id="02212-227">Figure 4.</span></span> <span data-ttu-id="02212-228">SEMM 中具有 SEMM 证书指纹的注册确认</span><span class="sxs-lookup"><span data-stu-id="02212-228">Enrollment confirmation in SEMM with the SEMM certificate thumbprint</span></span>*

>[!NOTE]
><span data-ttu-id="02212-229">有权访问证书文件 (.pfx) 可通过在 CertMgr 中打开 .pfx 文件来随时读取指纹。</span><span class="sxs-lookup"><span data-stu-id="02212-229">Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr.</span></span> <span data-ttu-id="02212-230">若要使用 CertMgr 查看指纹：</span><span class="sxs-lookup"><span data-stu-id="02212-230">To view the thumbprint with CertMgr:</span></span>
>1. <span data-ttu-id="02212-231">选择并按住 (或右键) .pfx 文件，然后选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="02212-231">Select and hold (or right-click) the .pfx file, and then select **Open**.</span></span>
>2. <span data-ttu-id="02212-232">在导航窗格中，展开文件夹。</span><span class="sxs-lookup"><span data-stu-id="02212-232">In the navigation pane, expand the folder.</span></span>
>3. <span data-ttu-id="02212-233">选择 **"证书"。**</span><span class="sxs-lookup"><span data-stu-id="02212-233">Select **Certificates**.</span></span>
>4. <span data-ttu-id="02212-234">在主窗格中，选择并按住 (或右键单击) 证书"，然后选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="02212-234">In the main pane, select and hold (or right-click) your certificate, and then select **Open**.</span></span>
>5. <span data-ttu-id="02212-235">选择" **详细信息"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="02212-235">Select the **Details** tab.</span></span>
>6. <span data-ttu-id="02212-236">在" **显示** "下拉菜单中， **必须选择"全部** "或" **仅** 属性"。</span><span class="sxs-lookup"><span data-stu-id="02212-236">In the **Show** drop-down menu, **All** or **Properties Only** must be selected.</span></span>
>7. <span data-ttu-id="02212-237">选择" **指纹"** 字段。</span><span class="sxs-lookup"><span data-stu-id="02212-237">Select the **Thumbprint** field.</span></span>

<span data-ttu-id="02212-238">若要在 SEMM 中注册 Surface 设备或从配置包应用 UEFI 配置，请对预期的 Surface 设备使用管理权限运行 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="02212-238">To enroll a Surface device in SEMM or apply the UEFI configuration from a configuration package, run the .msi file with administrative privileges on the intended Surface device.</span></span> <span data-ttu-id="02212-239">可以使用应用程序部署或操作系统部署技术，如 Microsoft Endpoint Configuration Manager 或[](https://technet.microsoft.com/library/mt346023) [Microsoft Deployment Toolkit。](https://technet.microsoft.com/windows/dn475741)</span><span class="sxs-lookup"><span data-stu-id="02212-239">You can use application deployment or operating system deployment technologies, like [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) or the [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741).</span></span> <span data-ttu-id="02212-240">在 SEMM 中注册设备时，必须实际存在以确认在设备上注册。</span><span class="sxs-lookup"><span data-stu-id="02212-240">When you enroll a device in SEMM, you must be physically present to confirm the enrollment on the device.</span></span> <span data-ttu-id="02212-241">将配置应用于已在 SEMM 中注册的设备时，不需要用户交互。</span><span class="sxs-lookup"><span data-stu-id="02212-241">When you apply a configuration to devices that are already enrolled in SEMM, user interaction isn’t required.</span></span>

<span data-ttu-id="02212-242">有关如何在 SEMM 中注册 Surface 设备或向 SEMM 应用 Surface UEFI 配置的分步演练，请参阅使用 [SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)注册和配置 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="02212-242">For a step-by-step walkthrough of how to enroll a Surface device in SEMM or apply a Surface UEFI configuration with SEMM, see [Enroll and configure Surface devices with SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).</span></span>

### <a name="reset-package"></a><span data-ttu-id="02212-243">重置程序包</span><span class="sxs-lookup"><span data-stu-id="02212-243">Reset package</span></span>

<span data-ttu-id="02212-244">Surface UEFI 重置程序包仅用于执行一项任务 - 从 SEMM 注销 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="02212-244">A Surface UEFI reset package is used to perform only one task — to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="02212-245">重置程序包包含从设备固件中删除 SEMM 证书以及将 UEFI 设置重置为出厂默认设置的签名说明。</span><span class="sxs-lookup"><span data-stu-id="02212-245">The reset package contains signed instructions to remove the SEMM certificate from the device’s firmware and to reset UEFI settings to the factory default settings.</span></span> <span data-ttu-id="02212-246">与 Surface UEFI 配置包一样，必须使用在 Surface 设备上预配的相同 SEMM 证书对重置程序包进行签名。</span><span class="sxs-lookup"><span data-stu-id="02212-246">Like a Surface UEFI configuration package, a reset package must be signed with the same SEMM certificate that’s provisioned on the Surface device.</span></span> <span data-ttu-id="02212-247">创建 SEMM 重置程序包时，需要提供要重置的 Surface 设备的序列号。</span><span class="sxs-lookup"><span data-stu-id="02212-247">When you create a SEMM reset package, you’re required to supply the serial number of the Surface device that you intend to reset.</span></span> <span data-ttu-id="02212-248">SEMM 重置程序包并不通用，它们特定于一台设备。</span><span class="sxs-lookup"><span data-stu-id="02212-248">SEMM reset packages aren’t universal — they’re specific to one device.</span></span>

### <a name="recovery-request"></a><span data-ttu-id="02212-249">恢复请求</span><span class="sxs-lookup"><span data-stu-id="02212-249">Recovery request</span></span>

<span data-ttu-id="02212-250">在某些情况下，可能无法使用 Surface UEFI 重置程序包。</span><span class="sxs-lookup"><span data-stu-id="02212-250">In some scenarios, it might be impossible to use a Surface UEFI reset package.</span></span> <span data-ttu-id="02212-251"> (例如，如果 Windows 在 Surface 设备上变得不可用。) 在这些情况下，可以通过 Surface UEFI (的**Enterprise**管理"页从 SEMM 注销 Surface 设备，如图 5) 中的"恢复请求"操作所示。</span><span class="sxs-lookup"><span data-stu-id="02212-251">(For example, if Windows becomes unusable on the Surface device.) In these scenarios you can unenroll the Surface device from SEMM through the **Enterprise Management** page of Surface UEFI (shown in Figure 5) with a Recovery Request operation.</span></span>

> [!div class="mx-imgBorder"]
> ![启动 SEMM 恢复请求](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*<span data-ttu-id="02212-253">图 5.</span><span class="sxs-lookup"><span data-stu-id="02212-253">Figure 5.</span></span> <span data-ttu-id="02212-254">在"管理"页上Enterprise SEMM 恢复请求</span><span class="sxs-lookup"><span data-stu-id="02212-254">Initiate a SEMM recovery request on the Enterprise Management page</span></span>*

<span data-ttu-id="02212-255">当你使用"Enterprise管理"页上\*\*\*\* 的过程在 Surface 设备上重置 SEMM 时，你获得重置请求。</span><span class="sxs-lookup"><span data-stu-id="02212-255">When you use the process on the **Enterprise Management** page to reset SEMM on a Surface device, you’re given a Reset Request.</span></span> <span data-ttu-id="02212-256">此重置请求可以另存为文件到 U 盘、复制为文本，或读取为 QR 码（通过移动设备轻松通过电子邮件发送或发送消息）。</span><span class="sxs-lookup"><span data-stu-id="02212-256">This Reset Request can be saved as a file to a USB drive, copied as text, or read as a QR Code with a mobile device to be easily emailed or messaged.</span></span> <span data-ttu-id="02212-257">使用 Microsoft Surface UEFI 配置程序重置请求选项加载重置请求文件或输入重置请求文本或 QR 代码。</span><span class="sxs-lookup"><span data-stu-id="02212-257">Use the Microsoft Surface UEFI Configurator Reset Request option to load a Reset Request file or to enter the Reset Request text or QR Code.</span></span> <span data-ttu-id="02212-258">Microsoft Surface UEFI 配置器生成可在 Surface 设备上输入的验证码。</span><span class="sxs-lookup"><span data-stu-id="02212-258">Microsoft Surface UEFI Configurator generates a verification code that can be entered on the Surface device.</span></span> <span data-ttu-id="02212-259">如果你在 Surface 设备上输入代码并选择重启，则\*\*\*\* 设备从 SEMM 注销。</span><span class="sxs-lookup"><span data-stu-id="02212-259">If you enter the code on the Surface device and select **Restart**, the device is unenrolled from SEMM.</span></span> 

>[!NOTE]
><span data-ttu-id="02212-260">重置请求将在创建后的两小时后过期。</span><span class="sxs-lookup"><span data-stu-id="02212-260">A Reset Request expires two hours after it's created.</span></span>

<span data-ttu-id="02212-261">有关如何从 SEMM 取消注册 Surface 设备的分步演练，请参阅从 SEMM 注销 [Surface 设备](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)。</span><span class="sxs-lookup"><span data-stu-id="02212-261">For a step-by-step walkthrough of how to unenroll Surface devices from SEMM, see [Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).</span></span>

## <a name="surface-enterprise-management-mode-certificate-requirements"></a><span data-ttu-id="02212-262">Surface Enterprise 管理模式证书要求</span><span class="sxs-lookup"><span data-stu-id="02212-262">Surface Enterprise Management Mode certificate requirements</span></span>
<span data-ttu-id="02212-263">当你将 SEMM 与 Microsoft Surface UEFI 配置器一同使用，并且想要应用 UEFI 设置时，需要证书来验证配置文件的签名。</span><span class="sxs-lookup"><span data-stu-id="02212-263">When you use SEMM with Microsoft Surface UEFI Configurator and want to apply UEFI settings, a certificate is required to verify the signature of configuration files.</span></span> <span data-ttu-id="02212-264">此证书可确保在设备注册 SEMM 后，只有使用已批准证书创建的程序包可用于修改 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="02212-264">This certificate ensures that after a device enrolls in SEMM, only packages created with the approved certificate can be used to modify the UEFI settings.</span></span>

>[!NOTE]
><span data-ttu-id="02212-265">若要在已注册的 Surface 设备上对 SEMM 或 Surface UEFI 设置进行任何修改，需要 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="02212-265">To make any modification to SEMM or Surface UEFI settings on enrolled Surface devices, the SEMM certificate is required.</span></span> <span data-ttu-id="02212-266">如果 SEMM 证书已损坏或丢失，则不能删除或重置 SEMM。</span><span class="sxs-lookup"><span data-stu-id="02212-266">If the SEMM certificate is corrupt or lost, SEMM can’t be removed or reset.</span></span> <span data-ttu-id="02212-267">使用相应的备份和恢复解决方案相应地管理 SEMM 证书</span><span class="sxs-lookup"><span data-stu-id="02212-267">Manage your SEMM certificate accordingly with an appropriate solution for backup and recovery</span></span>

<span data-ttu-id="02212-268">使用 Microsoft Surface UEFI 配置器工具创建的程序包使用证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="02212-268">Packages created with the Microsoft Surface UEFI Configurator tool are signed with a certificate.</span></span> <span data-ttu-id="02212-269">此证书可确保在 SEMM 中注册设备后，只有使用已批准证书创建的程序包可用于修改 UEFI 的设置。</span><span class="sxs-lookup"><span data-stu-id="02212-269">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span> 
### <a name="recommended-certificate-settings"></a><span data-ttu-id="02212-270">建议的证书设置</span><span class="sxs-lookup"><span data-stu-id="02212-270">Recommended certificate settings</span></span>
<span data-ttu-id="02212-271">对于 SEMM 证书，建议使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="02212-271">The following settings are recommended for the SEMM certificate:</span></span>

- <span data-ttu-id="02212-272">**密钥算法** – RSA</span><span class="sxs-lookup"><span data-stu-id="02212-272">**Key Algorithm** – RSA</span></span> 
- <span data-ttu-id="02212-273">**密钥长度** – 2048</span><span class="sxs-lookup"><span data-stu-id="02212-273">**Key Length** – 2048</span></span>
- <span data-ttu-id="02212-274">**哈希算法** – SHA-256</span><span class="sxs-lookup"><span data-stu-id="02212-274">**Hash Algorithm** – SHA-256</span></span>
- <span data-ttu-id="02212-275">**类型** – SSL 服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="02212-275">**Type** – SSL Server Authentication</span></span>
- <span data-ttu-id="02212-276">**密钥用法** – 数字签名、密钥加密</span><span class="sxs-lookup"><span data-stu-id="02212-276">**Key Usage** – Digital signature, Key Encipherment</span></span>
- <span data-ttu-id="02212-277">**提供程序** – Microsoft 增强 RSA 和 AES 加密提供程序</span><span class="sxs-lookup"><span data-stu-id="02212-277">**Provider** – Microsoft Enhanced RSA and AES Cryptographic Provider</span></span>
- <span data-ttu-id="02212-278">**到期日期** – 自证书创建起 15 个月</span><span class="sxs-lookup"><span data-stu-id="02212-278">**Expiration Date** – 15 Months from certificate creation</span></span>
- <span data-ttu-id="02212-279">**密钥导出策略** – 可导出</span><span class="sxs-lookup"><span data-stu-id="02212-279">**Key Export Policy** – Exportable</span></span>

<span data-ttu-id="02212-280">还建议在两层公钥基础结构 (PKI) 体系结构中对 SEMM 证书进行身份验证，其中中间证书颁发机构 (CA) 专用于 SEMM，从而启用证书吊销。</span><span class="sxs-lookup"><span data-stu-id="02212-280">It's also recommended that the SEMM certificate be authenticated in a two-tier public key infrastructure (PKI) architecture where the intermediate certification authority (CA) is dedicated to SEMM, enabling certificate revocation.</span></span> <span data-ttu-id="02212-281">有关两层 PKI 配置详细信息，请参阅测试实验室指南：部署 [AD CS](https://technet.microsoft.com/library/hh831348)Two-Tier PKI 层次结构。</span><span class="sxs-lookup"><span data-stu-id="02212-281">For more information about a two-tier PKI configuration, see [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).</span></span>

### <a name="self-signed-certificate"></a><span data-ttu-id="02212-282">自签名证书</span><span class="sxs-lookup"><span data-stu-id="02212-282">Self-signed certificate</span></span> 
<span data-ttu-id="02212-283">可以使用以下示例 PowerShell 脚本创建自签名证书，以用于概念证明方案。</span><span class="sxs-lookup"><span data-stu-id="02212-283">You can use the following example PowerShell script to create a self-signed certificate for use in proof-of-concept scenarios.</span></span>
<span data-ttu-id="02212-284">若要使用此脚本，将以下文本复制到 记事本，然后将文件另存为 PowerShell 脚本 (.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="02212-284">To use this script, copy the following text into Notepad, and then save the file as a PowerShell script (.ps1).</span></span> 

> [!NOTE]
> <span data-ttu-id="02212-285">此脚本创建密码为 的证书 `12345678` 。</span><span class="sxs-lookup"><span data-stu-id="02212-285">This script creates a certificate with a password of `12345678`.</span></span> <span data-ttu-id="02212-286">不建议在生产环境中使用此脚本生成的证书。</span><span class="sxs-lookup"><span data-stu-id="02212-286">The certificate generated by this script isn't recommended for production environments.</span></span>
  
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
><span data-ttu-id="02212-287">要与 SEMM 和 Microsoft Surface UEFI 配置器一起使用，必须使用私钥和密码保护导出证书。</span><span class="sxs-lookup"><span data-stu-id="02212-287">For use with SEMM and Microsoft Surface UEFI Configurator, the certificate must be exported with the private key and with password protection.</span></span> <span data-ttu-id="02212-288">Microsoft Surface UEFI 配置器会提示你选择 SEMM 证书文件 (.pfx) 密码。</span><span class="sxs-lookup"><span data-stu-id="02212-288">Microsoft Surface UEFI Configurator prompts you to select the SEMM certificate file (.pfx) and certificate password.</span></span>

<span data-ttu-id="02212-289">创建自签名证书：</span><span class="sxs-lookup"><span data-stu-id="02212-289">To create a self-signed certificate:</span></span>
1.  <span data-ttu-id="02212-290">在 C： 驱动器上，创建用于保存脚本的文件夹;例如，C：\SEMM。</span><span class="sxs-lookup"><span data-stu-id="02212-290">On your C: drive, create the folder where you'll save the script; for example, C:\SEMM.</span></span>
2.  <span data-ttu-id="02212-291">将示例脚本复制到记事本 (或等效文本编辑器) ，然后将文件另存为 PowerShell 脚本 (.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="02212-291">Copy the example script into Notepad (or equivalent text editor), and then save the file as a PowerShell script (.ps1).</span></span>
3.  <span data-ttu-id="02212-292">使用管理员凭据登录计算机，然后打开提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="02212-292">Sign in to your computer with administrator credentials, and then open an elevated PowerShell session.</span></span>
4.  <span data-ttu-id="02212-293">请确保将权限设置为允许脚本运行。</span><span class="sxs-lookup"><span data-stu-id="02212-293">Make sure that your permissions are set to allow scripts to run.</span></span> <span data-ttu-id="02212-294">默认情况下，除非修改执行策略，否则将阻止脚本运行。</span><span class="sxs-lookup"><span data-stu-id="02212-294">By default, scripts are blocked from running unless you modify the execution policy.</span></span> <span data-ttu-id="02212-295">若要了解更多信息，请参阅关于 [执行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)。</span><span class="sxs-lookup"><span data-stu-id="02212-295">To learn more, see [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
5.  <span data-ttu-id="02212-296">在命令提示符下，输入脚本的完整路径，然后按**Enter。**</span><span class="sxs-lookup"><span data-stu-id="02212-296">At the command prompt, enter the full path of the script and then press **Enter**.</span></span> <span data-ttu-id="02212-297">该脚本将创建一个名为 TempOwner.pfx 的演示证书。</span><span class="sxs-lookup"><span data-stu-id="02212-297">The script creates a Demo Certificate named TempOwner.pfx.</span></span>

<span data-ttu-id="02212-298">或者，您可以使用 PowerShell 创建自己的自签名证书。</span><span class="sxs-lookup"><span data-stu-id="02212-298">Alternatively, you can create your own self-signed certificate using PowerShell.</span></span> <span data-ttu-id="02212-299">有关详细信息，请参阅 [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)。</span><span class="sxs-lookup"><span data-stu-id="02212-299">For more information, see [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>

>[!NOTE]
><span data-ttu-id="02212-300">对于在 PKI 基础结构中使用脱机根的组织，Microsoft Surface UEFI 配置器必须在连接到根 CA 的环境中运行，以对 SEMM 证书进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="02212-300">For organizations that use an offline root in their PKI infrastructure, Microsoft Surface UEFI Configurator must be run in an environment connected to the root CA to authenticate the SEMM certificate.</span></span> <span data-ttu-id="02212-301">Microsoft Surface UEFI 配置器生成的程序包可以文件传输，因此可以使用可移动存储（如 U 盘）在脱机网络环境外部传输。</span><span class="sxs-lookup"><span data-stu-id="02212-301">The packages generated by Microsoft Surface UEFI Configurator can be transferred as files, so they can be transferred outside the offline network environment with removable storage, such as a USB stick.</span></span>

### <a name="managing-certificates-faq"></a><span data-ttu-id="02212-302">管理证书常见问题解答</span><span class="sxs-lookup"><span data-stu-id="02212-302">Managing certificates FAQ</span></span>

<span data-ttu-id="02212-303">建议 *的最小长度* 为 15 个月。</span><span class="sxs-lookup"><span data-stu-id="02212-303">The recommended *minimum* length is 15 months.</span></span> <span data-ttu-id="02212-304">您可以使用在 15 个月内过期的证书，或使用有效期超过 15 个月的证书。</span><span class="sxs-lookup"><span data-stu-id="02212-304">You can use a certificate that expires in less than 15 months or use a certificate that expires in longer than 15 months.</span></span>

>[!NOTE] 
><span data-ttu-id="02212-305">当证书过期时，它不会自动续订。</span><span class="sxs-lookup"><span data-stu-id="02212-305">When a certificate expires, it doesn't automatically renew.</span></span> 

**<span data-ttu-id="02212-306">过期的证书是否会影响 SEMM 注册设备的功能？</span><span class="sxs-lookup"><span data-stu-id="02212-306">Will an expired certificate affect the functionality of SEMM-enrolled devices?</span></span>**<br><br>
<span data-ttu-id="02212-307">否，证书仅影响 SEMM 中的 IT 管理员管理任务，在证书过期时不会影响设备功能。</span><span class="sxs-lookup"><span data-stu-id="02212-307">No, a certificate only impacts IT admin management tasks in SEMM and has no effect on device functionality when it expires.</span></span>

**<span data-ttu-id="02212-308">是否需要在所有拥有 SEMM 程序包和证书的计算机上进行更新？</span><span class="sxs-lookup"><span data-stu-id="02212-308">Will the SEMM package and certificate need to be updated on all machines that have it?</span></span>**<br><br>
<span data-ttu-id="02212-309">如果希望 SEMM 重置或恢复正常工作，证书必须有效且不会过期。</span><span class="sxs-lookup"><span data-stu-id="02212-309">If you want SEMM reset or recovery to work, the certificate needs to be valid and not expired.</span></span> 

**<span data-ttu-id="02212-310">能否为订购的每个图面创建批量重置程序包？</span><span class="sxs-lookup"><span data-stu-id="02212-310">Can bulk reset packages be created for each surface that we order?</span></span> <span data-ttu-id="02212-311">能否生成可重置环境中所有计算机的计算机？</span><span class="sxs-lookup"><span data-stu-id="02212-311">Can one be built that resets all machines in our environment?</span></span>**<br><br>
<span data-ttu-id="02212-312">为特定设备类型创建配置包的 PowerShell 示例还可用于创建独立于序列号的重置程序包。</span><span class="sxs-lookup"><span data-stu-id="02212-312">The PowerShell samples that create a config package for a specific device type can also be used to create a reset package that's serial-number independent.</span></span> <span data-ttu-id="02212-313">如果证书仍然有效，可以使用 PowerShell 创建重置程序包以重置 SEMM。</span><span class="sxs-lookup"><span data-stu-id="02212-313">If the certificate is still valid, you can create a reset package using PowerShell to reset SEMM.</span></span>

## <a name="version-history"></a><span data-ttu-id="02212-314">版本历史记录</span><span class="sxs-lookup"><span data-stu-id="02212-314">Version history</span></span>


### <a name="version-2831390"></a><span data-ttu-id="02212-315">版本 2.83.139.0</span><span class="sxs-lookup"><span data-stu-id="02212-315">Version 2.83.139.0</span></span>

<span data-ttu-id="02212-316">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-316">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-317">支持 Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="02212-317">Support for Surface Laptop 4</span></span>
- <span data-ttu-id="02212-318">支持用于 7 的并发多线程Surface Pro选项</span><span class="sxs-lookup"><span data-stu-id="02212-318">Support for simultaneous multithreading option for Surface Pro 7</span></span>
- <span data-ttu-id="02212-319">删除过时的 SEMM 设置</span><span class="sxs-lookup"><span data-stu-id="02212-319">Removal of obsolete SEMM settings</span></span>  
- <span data-ttu-id="02212-320">改进的 MSI 签名</span><span class="sxs-lookup"><span data-stu-id="02212-320">Improved MSI signing</span></span> 

### <a name="version-2791390"></a><span data-ttu-id="02212-321">版本 2.79.139.0</span><span class="sxs-lookup"><span data-stu-id="02212-321">Version 2.79.139.0</span></span>

<span data-ttu-id="02212-322">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-322">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-323">支持 Surface Pro 7 及以上。</span><span class="sxs-lookup"><span data-stu-id="02212-323">Support for Surface Pro 7+.</span></span>
- <span data-ttu-id="02212-324">用户体验改进。</span><span class="sxs-lookup"><span data-stu-id="02212-324">User experience improvements.</span></span>

### <a name="version-2781390"></a><span data-ttu-id="02212-325">版本 2.78.139.0</span><span class="sxs-lookup"><span data-stu-id="02212-325">Version 2.78.139.0</span></span>

<span data-ttu-id="02212-326">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-326">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-327">支持 Surface Laptop Go 和 Surface Pro X。</span><span class="sxs-lookup"><span data-stu-id="02212-327">Support for Surface Laptop Go and Surface Pro X.</span></span>
- <span data-ttu-id="02212-328">新版本发布的通知。</span><span class="sxs-lookup"><span data-stu-id="02212-328">Notifications for new version releases.</span></span>
- <span data-ttu-id="02212-329">创建自定义程序包以更改所有权的能力。</span><span class="sxs-lookup"><span data-stu-id="02212-329">The ability to create custom packages to change ownership.</span></span>
- <span data-ttu-id="02212-330">Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="02212-330">Bug fixes.</span></span>

### <a name="version-2731360"></a><span data-ttu-id="02212-331">版本 2.73.136.0</span><span class="sxs-lookup"><span data-stu-id="02212-331">Version 2.73.136.0</span></span>

<span data-ttu-id="02212-332">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-332">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-333">使用 SEMM 在 Surface Hub2S 上禁用音频的能力。</span><span class="sxs-lookup"><span data-stu-id="02212-333">The ability for audio to be disabled on Surface Hub2S using SEMM.</span></span>
- <span data-ttu-id="02212-334">支持扩展Surface Pro 2 的 X。</span><span class="sxs-lookup"><span data-stu-id="02212-334">Support for Surface Pro X for Dock 2.</span></span>
- <span data-ttu-id="02212-335">支持 UEFI 管理器执行与扩展坞 2 相关的操作。</span><span class="sxs-lookup"><span data-stu-id="02212-335">Support for UEFI Manager for Dock 2-related operations.</span></span>
- <span data-ttu-id="02212-336">Surface Go 重置程序包 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="02212-336">A Surface Go reset package bug fix.</span></span>
- <span data-ttu-id="02212-337">支持将 Surface Hub 2 Windows 10 协同版操作系统迁移到 Windows 10 专业版 或 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="02212-337">Support for migrating Surface Hub 2 devices from Windows 10 Team OS to Windows 10 Pro or Enterprise.</span></span>

### <a name="version-2711390"></a><span data-ttu-id="02212-338">版本 2.71.139.0</span><span class="sxs-lookup"><span data-stu-id="02212-338">Version 2.71.139.0</span></span>

<span data-ttu-id="02212-339">此版本的 SEMM 增加了对适用于 Surface Book 3、Surface Laptop 3 和 Surface Pro 7 的 Surface Dock 2 管理功能的支持。</span><span class="sxs-lookup"><span data-stu-id="02212-339">This version of SEMM adds support for Surface Dock 2 management features for Surface Book 3, Surface Laptop 3, and Surface Pro 7.</span></span> <span data-ttu-id="02212-340">其中包括：</span><span class="sxs-lookup"><span data-stu-id="02212-340">It includes:</span></span>

- <span data-ttu-id="02212-341">能够启用音频端口 (/解锁) 以太网和 USB 端口。</span><span class="sxs-lookup"><span data-stu-id="02212-341">The ability to enable audio (lock/unlock), and Ethernet and USB ports.</span></span>
- <span data-ttu-id="02212-342">为经过身份验证和未经身份验证的主机创建扩展坞包的能力。</span><span class="sxs-lookup"><span data-stu-id="02212-342">The ability to create dock packages for both authenticated and unauthenticated hosts.</span></span>

### <a name="version-2701300"></a><span data-ttu-id="02212-343">版本 2.70.130.0</span><span class="sxs-lookup"><span data-stu-id="02212-343">Version 2.70.130.0</span></span>

<span data-ttu-id="02212-344">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-344">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-345">支持 Surface Go 2。</span><span class="sxs-lookup"><span data-stu-id="02212-345">Support for Surface Go 2.</span></span>
- <span data-ttu-id="02212-346">支持 Surface Book 3。</span><span class="sxs-lookup"><span data-stu-id="02212-346">Support for Surface Book 3.</span></span>
- <span data-ttu-id="02212-347">Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="02212-347">Bug fixes.</span></span>

### <a name="version-2591390"></a><span data-ttu-id="02212-348">版本 2.59.139.0</span><span class="sxs-lookup"><span data-stu-id="02212-348">Version 2.59.139.0</span></span>

<span data-ttu-id="02212-349">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-349">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-350">支持Surface Pro Intel 处理器Surface Pro 7、Surface Pro X 和 Surface Laptop 3 13.5" 和 15" 型号。</span><span class="sxs-lookup"><span data-stu-id="02212-350">Support for Surface Pro 7, Surface Pro X, and Surface Laptop 3 13.5" and 15" models with Intel processor.</span></span> 
    >[!NOTE]
    ><span data-ttu-id="02212-351">Surface Laptop不支持 3 个 15" AMD 处理器。</span><span class="sxs-lookup"><span data-stu-id="02212-351">Surface Laptop 3 15" AMD processor isn't supported.</span></span>
- <span data-ttu-id="02212-352">支持电源唤醒功能。</span><span class="sxs-lookup"><span data-stu-id="02212-352">Support for the Wake on Power feature.</span></span>

### <a name="version-2541390"></a><span data-ttu-id="02212-353">版本 2.54.139.0</span><span class="sxs-lookup"><span data-stu-id="02212-353">Version 2.54.139.0</span></span>

<span data-ttu-id="02212-354">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-354">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-355">支持 Surface Hub 2S。</span><span class="sxs-lookup"><span data-stu-id="02212-355">Support for Surface Hub 2S.</span></span>
- <span data-ttu-id="02212-356">Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="02212-356">Bug fixes.</span></span>

### <a name="version-2431360"></a><span data-ttu-id="02212-357">版本 2.43.136.0</span><span class="sxs-lookup"><span data-stu-id="02212-357">Version 2.43.136.0</span></span>

<span data-ttu-id="02212-358">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-358">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-359">支持启用/禁用同时多线程。</span><span class="sxs-lookup"><span data-stu-id="02212-359">Support to enable/disable simultaneous multithreading.</span></span>
- <span data-ttu-id="02212-360">用于某些设备的无线网络和蓝牙选项。</span><span class="sxs-lookup"><span data-stu-id="02212-360">Separate options for wireless networking and Bluetooth for some devices.</span></span>
- <span data-ttu-id="02212-361">已删除电池Surface Studio。</span><span class="sxs-lookup"><span data-stu-id="02212-361">Battery Limit removed for Surface Studio.</span></span>

### <a name="version-2261360"></a><span data-ttu-id="02212-362">版本 2.26.136.0</span><span class="sxs-lookup"><span data-stu-id="02212-362">Version 2.26.136.0</span></span>

<span data-ttu-id="02212-363">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-363">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-364">支持 Surface Studio 2。</span><span class="sxs-lookup"><span data-stu-id="02212-364">Support for Surface Studio 2.</span></span>
- <span data-ttu-id="02212-365">电池限制功能。</span><span class="sxs-lookup"><span data-stu-id="02212-365">Battery Limit feature.</span></span>

### <a name="version-2211360"></a><span data-ttu-id="02212-366">版本 2.21.136.0</span><span class="sxs-lookup"><span data-stu-id="02212-366">Version 2.21.136.0</span></span>

<span data-ttu-id="02212-367">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-367">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-368">支持 Surface Pro 6.</span><span class="sxs-lookup"><span data-stu-id="02212-368">Support for Surface Pro 6.</span></span>
- <span data-ttu-id="02212-369">支持 Surface Laptop 2。</span><span class="sxs-lookup"><span data-stu-id="02212-369">Support for Surface Laptop 2.</span></span>

### <a name="version-2141360"></a><span data-ttu-id="02212-370">版本 2.14.136.0</span><span class="sxs-lookup"><span data-stu-id="02212-370">Version 2.14.136.0</span></span>

<span data-ttu-id="02212-371">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-371">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-372">支持 Surface Go。</span><span class="sxs-lookup"><span data-stu-id="02212-372">Support for Surface Go.</span></span>

### <a name="version-291360"></a><span data-ttu-id="02212-373">版本 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="02212-373">Version 2.9.136.0</span></span>

<span data-ttu-id="02212-374">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-374">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-375">支持 Surface Book 2。</span><span class="sxs-lookup"><span data-stu-id="02212-375">Support for Surface Book 2.</span></span>
- <span data-ttu-id="02212-376">支持 Surface Pro LTE。</span><span class="sxs-lookup"><span data-stu-id="02212-376">Support for Surface Pro LTE.</span></span>
- <span data-ttu-id="02212-377">辅助功能改进。</span><span class="sxs-lookup"><span data-stu-id="02212-377">Accessibility improvements.</span></span>

### <a name="version-10740"></a><span data-ttu-id="02212-378">版本 1.0.74.0</span><span class="sxs-lookup"><span data-stu-id="02212-378">Version 1.0.74.0</span></span>

<span data-ttu-id="02212-379">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="02212-379">This version of SEMM includes:</span></span>

- <span data-ttu-id="02212-380">支持Surface Laptop。</span><span class="sxs-lookup"><span data-stu-id="02212-380">Support for Surface Laptop.</span></span>
- <span data-ttu-id="02212-381">支持Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="02212-381">Support for Surface Pro.</span></span>
- <span data-ttu-id="02212-382">Bug 修复和常规改进。</span><span class="sxs-lookup"><span data-stu-id="02212-382">Bug fixes and general improvements.</span></span>

## <a name="related-topics"></a><span data-ttu-id="02212-383">相关主题</span><span class="sxs-lookup"><span data-stu-id="02212-383">Related topics</span></span>

- [<span data-ttu-id="02212-384">使用 SEMM 注册并配置 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="02212-384">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)
- [<span data-ttu-id="02212-385">从 SEMM 取消注册 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="02212-385">Unenroll Surface devices from SEMM</span></span>](unenroll-surface-devices-from-semm.md)
- [<span data-ttu-id="02212-386">使用 SEMM 保护 Surface Dock 2 端口</span><span class="sxs-lookup"><span data-stu-id="02212-386">Secure Surface Dock 2 ports with SEMM</span></span>](secure-surface-dock-ports-semm.md)

---
title: Surface 安全性概述
description: 本文概述了 Surface 设备安全性
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/01/2021
ms.reviewer: brrecord
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 1cd6c1917e426163d2469bb1b1cdf6bfb8a56dbf
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449575"
---
# <a name="surface-security-overview"></a>Surface 安全性概述

最近安全研究的发展表明，随着操作系统和连接服务中内置了更多保护，攻击者正在寻找其他利用方式，将固件作为首要目标出现。

如今，管理设备固件是一种不一致的体验，并且通常涉及第三方提供商，使固件难以监控且维护复杂。 最终，这会限制硬件制造商检测和推送及时更新以响应威胁的能力。

自 2015 以来，Microsoft Surface 通过硬件设计的完整端到端所有权、内部固件开发以及设备更新和管理的整体方法，一直使用统一的固件保护和设备安全方法。

对于 Surface，我们的统一可扩展固件接口 (UEFI) <sup>[1](#references)</sup> 在内部进行维护，通过 Windows 更新定期更新，并通过 Windows Autopilot 无缝部署以用于管理，从而在设备启动前将风险最小化并最大限度地提高固件级别的控制。 Microsoft 通过 Open Source [Project Mu](https://microsoft.github.io/mu/) on GitHub，在我们的 UEFI 中提供代码库的完全Microsoft Endpoint Manager。

## <a name="microsoft-designed-and-built-components"></a>Microsoft 设计和构建的组件

从芯片到云的每一层 Surface 都由 Microsoft 进行维护，从而提供最终控制、主动保护，并且无论在哪里以及在何处完成工作，都大有希望。 Surface 设备随 Microsoft 提供的最强安全协议提供，可实现简化管理，从而降低 IT 复杂性并帮助用户专注于工作。

Surface 利用独立防御子组件的分层，通过深度防御方法提高安全性。 从芯片到云，或确保受 AI 支持 Microsoft Defender for Endpoint 的信任根的 UEFI（用于防止、检测、调查和响应高级威胁）时，Surface 强制执行 Microsoft 内置比固定位置更好的位置。

<br/>

| 功能 | 说明 | 了解详细信息 |
| ------- | ----------- | ---------- |
| Microsoft Built UEFI            | 配置设备并启动设备Windows 10<br>控制设备和设备的初始Windows 10，然后向操作系统提供固件运行时服务。 通过 SEMM on-prem management和 DFCI cloud-based management 通过 Microsoft Endpoint Manager | [管理 Surface UEFI 设置](manage-surface-uefi-settings.md)                                                                        |
| 物理 TPM 2.0                | 受信任的平台模块 - 专用于通过集成的加密密钥保护硬件。<br>加密和存储 BitLocker (、Windows Hello、AD 凭据、) <br>PCR - 平台配置注册，用于保护测量和相关指标，以检测对以前的配置所做的更改  | [受信任的平台模块技术概述](/windows/security/information-protection/tpm/trusted-platform-module-overview)                 |
| Windows Hello 企业版      | 将密码替换为电脑和移动设备上的强双因素身份验证。 此生物识别身份验证包含绑定到设备的新类型的用户凭据。                                                                                                                   | [企业Windows Hello工作原理 - Microsoft 365安全性](/windows/security/identity-protection/hello-for-business/hello-how-it-works) |
| 集成加密           | 集成加密由 BitLocker 启用，用于对数据进行安全和加密，Windows Hello启用无密码登录，并结合物理 TPM 和 UEFI。                                                                                                                                                                 | [BitLocker (Windows 10) - Microsoft 365安全性](/windows/security/information-protection/bitlocker/bitlocker-overview)                     |
| Microsoft Defender for Endpoint | 提供旨在帮助网络预防、检测、调查和响应高级威胁的企业终结点安全平台。                                                                                                                                                                               | [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)                 |

## <a name="factory-level-security-protocols-and-inspection"></a>工厂级安全协议和检查

从固件到操作系统以及最终程序集之前的每一个硬件组件，Surface 设备在我们的物理安全开发和制造设施中可安全受到供应链攻击。

根据定义，安全的供应链提供满足质量、性能和操作目标的已完成产品。 简单地说，安全的供应链可确保所有组件都是正版组件，并且没有未经授权的或恶意的操作或破坏。 我们在高度安全工厂中制造设备，从 UEFI 固件到操作系统的所有设备都直接来自 Microsoft。 不参与任何第三方 BIOS 供应商。 这是我们防止 Surface 产品的供应链攻击的一个强大部分。 我们通过删除任何未使用的代码（包括设备不需要的系统管理模式 SMM 函数）减少了 UEFI 中的攻击 Surface。

保护设施免受基于 Internet 的外部攻击、入侵和其他威胁，需要跨关键领域持续投资，包括：

- 对最终程序集位置的所有组件进行严格检查和测试。
- 在工厂中维护高级别的物理安全。
- 仅使用 Microsoft 维护的固件、驱动程序和操作系统。
- 直接发到 Microsoft 经销商的 Surface 设备的安全后勤和受信任的运营商交付。

离开工厂后，Surface 商用版设备在整个生命周期Windows更新进行保护。

## <a name="advanced-windows-security-features"></a>高级Windows安全功能

特权升级攻击是恶意操作者的最佳好友，它们通常以存储在内存中的敏感信息为目标。 这些类型的攻击可能会将次要用户模式泄露转换为对操作系统和设备的总危害。 为了防范这些类型的攻击，Microsoft 开发了基于虚拟化的安全 (VBS) 和虚拟机监控程序保护的代码完整性 (HVCI，通常也称为内存完整性) 。 VBS 和 HVCI 使用虚拟化等硬件功能的功能，在隔离环境中执行敏感安全操作，以更好地抵御常见和复杂的恶意软件。

Surface 附带Windows开箱即用增强的硬件安全功能，为客户提供内置且默认打开的更可靠安全性。

## <a name="virtualization-based-security"></a>基于虚拟化的安全功能

基于虚拟化的安全性（即 VBS）使用硬件虚拟化功能创建安全的内存区域并将其与常规操作系统隔离。 Windows"虚拟安全模式"可以托管大量安全解决方案，从而显著增强对操作系统中漏洞的保护，并阻止使用恶意攻击来破坏保护。

### <a name="hypervisor-enforced-code-integrity-hvci"></a>Hypervisor-Enforced HVCI (代码完整性) 

HVCI 使用 VBS 显著加强代码完整性策略实施。 内核模式代码完整性在启动之前检查所有内核模式驱动程序和二进制文件，并防止未签名的驱动程序或系统文件加载到系统内存中。 如下图所示，HVCI 在独立的执行环境中运行，根据内核签名策略验证内核代码的完整性。

VBS 和 HVCI 均在下列 Surface 设备中开箱启用：

- Surface Pro 8
- Surface Laptop Studio
- Surface Go 3
- Surface Laptop 4
- Surface Pro 7+
- Surface Book 3
- Surface Laptop Go
- Surface Pro X

## <a name="secure-boot-and-boot-guard"></a>安全启动和启动保护

Surface 设备的"信任根"检查签名和测量，以确保每个阶段都安全且可信，然后再允许下一阶段的启动继续。 安全启动由 UEFI 和 TPM 2.0 启用，可确保只有已签名、测量和正确实现的代码才能在 Surface 设备上执行。

如下图所示，从按电源按钮到运行操作系统，每个阶段都检查固件的完整性。

:::image type="content" source="images/secboot.png" alt-text="图 1. Surface 设备的安全启动":::
*图 1. Surface 设备的安全启动*

<br/>

| 步骤  | 安全启动阶段 |
| ----- | ----------------- |
| **1** | 每次从 TPM 提供的信任根按下电源按钮时，都会实例化安全性。 首次打开设备时，系统将运行一系列安全检查，以确保设备固件未被篡改或损坏。 |
| **2** | 启用后，SoC 将使用芯片集供应商密钥，在基于 Intel 的设备上使用经过身份验证的代码模块 (ACM)  (验证和启动微代码) 。                                                                              |
| **3** | ACM 在加载之前测量 UEFI 代码，并将其与 TPM 的平台配置注册 [PCR] 中的已知度量进行比较，以确保 UEFI 代码未改变。                                                                |
| **4** | 在允许 UEFI 运行之前，启动防护会检查 UEFI 是否使用 Surface OEM 密钥进行签名。 最初检查的 UEFI 模块是图表中所示的 SEC 安全部分和"使用前进行安装"的"功能"部分。                                                |
| **5** | 在加载驱动程序执行环境（DXE 模块）时，"更新"部分会检查 Surface 签名。 DXE 模块包括启动设备选择阶段。                                                                          |
| **6** | 选择启动设备后，UEFI 将读取启动设备，并检查操作系统启动加载程序签名，然后再允许它执行。                                                                                                             |
| **7** | 操作系统随后在打开操作系统时检查其主组件上的签名。

### <a name="malware-protection"></a>恶意软件保护

为了帮助保护设备免受恶意软件攻击，Surface 支持安全启动，以确保启动真实版本的 Windows 10，并确保固件与离开工厂时一样正版。

Surface 设备上 SoC 具有独立于其他每个内核的安全处理器。 首次启动 Surface 设备时，只有安全处理器才能加载任何其他内容。 安全启动用于验证启动过程组件（包括驱动程序和操作系统）是否针对有效和已知签名的数据库进行了验证。 这有助于防止来自克隆或修改的系统的攻击，该系统运行的恶意代码隐藏在看似日常用户体验中。 有关详细信息，请参阅[安全启动概述](/windows-hardware/design/device-experiences/oem-secure-boot)。

在操作系统被验证为来自 Microsoft 并且 Surface 设备完成启动过程后，设备会检查可执行代码。 我们保护操作系统的方法涉及识别所有可执行文件的代码签名，只允许那些通过我们的限制的文件加载到运行时中。 此代码签名方法使操作系统能够在设备上运行之前验证作者并确认代码未更改。

## <a name="drtm-protection-in-amd-devices"></a>AMD 设备中的 DRTM 保护

包含 AMD 处理器的 Surface 设备等效实现安全启动。 Surface Laptop 4 与 AMD Ryzen Microsoft Surface Edition 处理器一起使用受信任测量的动态根和 DRTM) 保护固件免受初始电源 (。DRTM 控制所有 CPU，强制沿测量路径执行，并重建各个阶段的信任，以验证系统固件/软件的完整性。 提前过渡到此受信任状态可增强针对启动阶段中的潜在攻击的保护。

DRTM 使用 TSME 加密和 TSME 加密对测量进行 (加密) 。 设置 TSME 后，除非系统重置，否则无法清除它。 每次重置的新加密密钥可确保一次使用加密的安全性。

对系统管理模式的运行时 (SMM) 在最高级别执行，如果 SMM 代码有任何问题，则可能会存在风险。 Surface Laptop 4 WITH AMD Ryzen 通过截获系统管理中断 (SMI) 并调度 SMM 代码执行到较低级别的 (用户) 来保护系统免受代码和数据无效访问。 SMM 保护使用硬件保护来限制可以访问的代码、数据和系统资源，从而进一步强制执行针对无意或恶意事件的保护。

Surface Laptop 4 与 AMD Ryzen 一起支持 [NIST 800-193](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-193.pdf) 平台固件复原指南，以及强大的固件更新支持。 启动固件的复原更新机制使用 A-B 恢复机制，该机制在启动期间检测到固件的损坏副本时自动恢复固件的备份副本。

若要了解有关 DRTM 和 SMM 的更多信息，请参阅 Windows Defender [System Guard 如何帮助保护Windows 10](/windows/security/threat-protection/windows-defender-system-guard/how-hardware-based-root-of-trust-helps-protect-windows)。

## <a name="remote-device-management-control"></a>远程设备管理控制

IT 管理员可以远程管理 Surface 设备，而无需实际触摸每个设备。 Microsoft Endpoint Manager Intune 和 Windows Autopilot 支持从 Azure 云对 Surface 设备进行完全远程管理，从而在启动时为用户提供完全配置的设备。 擦除和停用功能使 IT 可以轻松地为新的远程用户重新利用设备，并擦除被盗的设备。 这样，在 Surface 设备丢失或被盗时，可快速、安全地响应功能，使你能够远程删除所有公司数据，将 Surface 重新配置为全新的设备。

<br/>

| 功能 | 说明 | 了解详细信息 |
| ------- | ----------- | ---------- |
| DCFI (设备固件配置接口)  | 通过零接触设备预配提供云规模的远程固件管理。 Microsoft 的 UEFI 允许更强的 DCFI 实现，使组织能够禁用硬件元素，并能够使用 Intune 远程锁定 UEFI。 ¹                                                                                                                                                                          | [Surface UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)<br> <br>[管理 Surface UEFI 设置](manage-surface-uefi-settings.md)                                          |
| SEMM (Surface Enterprise 管理模式)       | 实现跨本地、混合和云环境的 UEFI 固件设置的集中企业参与。¹                                                                                                                                                                                                                                                                                           | [Surface 企业管理模式](surface-enterprise-management-mode.md)                                                                                                                                                       |
| 适用于企业的 Windows 更新                    | 使 IT 管理员通过直接将Windows 10连接到 Windows 更新服务，使 IT 管理员能够使用最新的安全防护、Windows 功能和 Surface 固件持续更新其组织的 Windows 设备。 可以使用组策略或 MDM 解决方案（如 Microsoft Intune）配置Windows Surface 设备更新方式和时间的适用于企业的更新设置。 | [适用于企业的 Windows 更新](/windows/deployment/update/waas-manage-updates-wufb)<br> <br>[管理和部署 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md) |

## <a name="references"></a>参考

1. Surface Go 和 Surface Go 2 使用第三方 UEFI，不支持 DFCI。 DFCI 目前可用于 Surface Laptop 标准版、Surface Laptop Studio、Surface Pro 8、Surface Go 3、Surface Laptop 4、Surface Laptop Go、Surface Book 3、Surface Laptop 3，Surface Pro 7+、Surface Pro 7 和 Surface Pro X。

## <a name="learn-more"></a>了解详细信息

- [默认情况下，新的 Surface 电脑支持基于虚拟化 (VBS) ，以让客户安全地执行更多操作](https://www.microsoft.com/security/blog/2021/01/11/new-surface-pcs-enable-virtualization-based-security-vbs-by-default-to-empower-customers-to-do-more-securely/)
- [研究重点介绍 Surface 固件保护的重要作用](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/study-highlights-critical-role-of-surface-firmware-protection/ba-p/2245244)
- [增强 Microsoft Surface 和 Microsoft 365](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/enhancing-security-and-compliance-with-microsoft-surface-and/ba-p/2283062)
- [管理 Surface UEFI 设置](manage-surface-uefi-settings.md)
- [Surface UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)
- [Project Mu](https://microsoft.github.io/mu/)

---
title: Surface Hub 安全性概述
description: 本页将解释说明 Surface Hub 的深度防御设计，并介绍 Surface Hub 2S 中的安全增强功能以及无线安全防护和相关功能。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: coveminer
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/27/2020
ms.localizationpriority: High
ms.openlocfilehash: f6022c4fd16cd8afbbea892e73ad831f12b10eaa
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934852"
---
# Surface Hub 安全性概述

Surface Hub 通过运行 Windows 10 团队操作系统的自定义平台固件提供锁定的计算装置。 由此产生的设备采用传统的“单一用途”安全网亭，融入“仅运行所需内容”的理念，并提供一种现代化的风格。 Surface Hub 是为支持丰富的协作用户体验而构建的，可抵御不断演变的安全威胁。

以 Windows 10 为基础，Surface Hub 可提供企业级现代安全性，支持 IT 管理员利用 BitLocker、受信任的平台模块 2.0 (TPM) 以及通过 Windows Defender（也称为 Microsoft Defender）实现的云驱动安全性实施数据保护。

## 深度防御安全性

打开 Surface Hub 后，安全协议将立即启动。 从固件级别开始，Surface Hub 将仅加载操作系统及其组件，以响应多个安全检查。 Surface Hub 采用一种称为深度防御的策略，该策略涉及对独立的防护子组件进行分层，可在发生局部故障时保护整个系统。 事实证明，这一行业实践在缓解子组件中潜在的单边利用和弱点方面非常有效。

当今的统一可扩展固件接口 (UEFI) 由 Microsoft 静态且安全地配置为仅从内部存储启动经过身份验证的 Windows 10 团队操作系统。  在 Surface Hub 上运行的每一行代码都将在执行前完成签名验证。 只有由 Microsoft 签署的应用程序（无论是操作系统的一部分还是通过 Microsoft Store 安装的）才能在 Surface Hub 上运行。 不符合这些要求的代码或应用将会被阻止。

Surface Hub 安全系统包括以下各项：

- **启动时间防御。** 仅加载受信任的 Surface Hub 操作系统组件。
- **操作系统防御。** 防止意外或恶意软件或代码的执行。
- **用户界面防御。** 提供对最终用户而言安全的用户界面，阻止访问有可能存在风险的活动，例如从命令行运行可执行文件。

### 启动时间防御

该 SoC 有一个安全处理器，它与其他各个内核都是分开的。 第一次启动 Surface Hub 时，只有安全处理器最先启动，之后才能加载其他内容。

![显示安全处理器保护的 Hub 启动过程启动阶段](images/hub-sec-1.png)

#### 安全启动

安全启动用于验证启动过程的组件（包括驱动程序和操作系统）是否针对有效且已知签名的数据库进行了验证。 在 Surface Hub 上，必须先验证特定于平台的签名，然后才能加载获得授权的 Windows 协同版操作系统。 这有助于防止来自克隆或被修改的系统的攻击，这种系统运行的恶意代码隐藏在看似正常的用户体验中。  有关详细信息，请参阅[安全启动概述](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。

### 操作系统防御

在验证操作系统来自 Microsoft 并且 Surface Hub 成功完成启动过程后，设备会仔细检查可执行代码。 我们保护操作系统的方法涉及识别所有可执行文件的代码签名，只允许那些通过我们的限制的文件加载到运行时中。 通过此代码签名方法，操作系统可以验证作者，并在设备上运行代码之前先确认其未被修改。

Surface Hub 在 Windows 应用程序控制（以前称为 Device Guard）中使用一种称为用户模式代码完整性 (UMCI) 的代码签名功能。 我们将策略设置配置为仅允许使用符合以下任一要求的应用：

- [得到官方认证](https://docs.microsoft.com/windows/uwp/publish/the-app-certification-process)的通用 Windows 平台 (Microsoft Store) 应用。
- 使用唯一的 Microsoft 生产根证书颁发机构 (CA) 签署的应用，只有具有这些证书的授权访问权限的 Microsoft 员工才能对其进行签名。
- 使用唯一的 Surface Hub 生产根 CA 签署的应用。

配置文件是使用 Microsoft 生产根 CA 签署的，旨在防止第三方删除或修改限制。 此时，所有其他可执行文件直接在操作系统运行时级别被阻止，并且无法获得处理能力。 这种攻击面的减少可提供以下保护：

- 无旧版文档模式
- 无旧版脚本引擎
- 无矢量标记语言
- 无浏览器帮助程序对象
- 无 ActiveX 控件

除了通过 UMCI 阻止未签名或签名不当的代码之外，Surface Hub 还使用 Windows 应用程序控制功能来阻止 Windows 组件，如命令提示符、PowerShell 和任务管理器。 这些安全措施反映了 Surface Hub 作为安全计算设备的一个关键设计特性。 有关详细信息，请参阅以下内容：

- [应用程序控制概述](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender 应用程序控制和对代码完整性的基于虚拟化的保护](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

### 用户界面防御

虽然启动时间防御和操作系统锁定保护机制提供了基础的安全性，但用户界面又提供了一个额外的保护层，旨在进一步降低风险。 为了防止恶意代码通过驱动程序到达设备，Surface Hub 不下载用于即插即用 (PnP) 设备的高级驱动程序。 U 盘或经认证的 Surface Hub 外设（扬声器、麦克风、摄像头）等利用基本驱动程序的设备可按预期工作，但高级系统（如打印机）将不能正常工作。

用户界面防御还简化了 UI，可进一步阻止恶意软件或代码的执行。 以下 Surface Hub UI 元素对代码签名提供的核心安全性进行了分层：

- **文件资源管理器。** Surface Hub 有一个自定义的文件资源管理器，可快速访问“音乐”、“视频”、“文档”、“图片”和“下载”文件夹，无需向用户呈现系统或程序文件。 本地硬盘上的其他位置无法通过文件资源管理器访问。 此外，许多运行 .exe 和 .msi 等安装文件的文件类型无法运行，从而针对潜在的恶意可执行文件提供了另一层保护。

- **“开始”和“所有应用”。** Surface Hub 的“开始”和“所有应用”组件不提供对命令提示符、PowerShell 或其他通过应用程序控制阻止的 Windows 组件的访问。 此外，在 Surface Hub 上，通常从电脑上的搜索框访问的 Windows 运行功能将处于关闭状态。

## Surface Hub 2S 中的安全增强功能

尽管 Surface Hub 和 Surface Hub 2 均运行相同的操作系统软件，但 Surface Hub 2 独有的一些功能提供了额外的管理和安全功能，使 IT 管理员能够执行以下任务：

- 使用 SEMM 管理 UEFI 设置
- 使用可启动的 USB 恢复 Hub
- 通过密码轮换强化设备帐户

### 使用 SEMM 管理 UEFI 设置

UEFI 是基础硬件平台部件和操作系统之间的接口。 在 Surface Hub 上，自定义 UEFI 的实现使你可以精细控制这些设置，并阻止任何非 Microsoft 实体更改设备的 UEFI 设置 — 或启动到可移动驱动器以修改或更改操作系统。

在较高级别上，我们在出厂预配过程中将 Surface Hub UEFI 预配置为启用安全启动，并将其设置为仅从内部固态硬盘 (SSD) 启动，同时锁定对 UEFI 菜单的访问并删除快捷方式。 这将封装 UEFI 访问，并确保设备只能启动到安装在 Surface Hub 上的 Windows 协同版操作系统。

通过 Microsoft Surface 企业管理模式 (SEMM) 进行管理时，IT 管理员可在整个组织内的 Hub 设备上部署 UEFI 设置。 这包括以下功能：启用或禁用内置硬件组件、防止未经授权的用户更改 UEFI 设置，以及调整启动设置。

![Surface Hub UEFI 设置](images/hub-sec-2.png)

管理员可以使用可下载的 [Microsoft Surface UEFI 配置器](https://www.microsoft.com/download/details.aspx?id=46703)来实现 SEMM 和注册 Surface Hub 2 设备。 有关详细信息，请参阅[使用 SEMM 和 UEFI 来保护和管理 Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm)。
通过使用证书来保护配置不受未经授权的篡改或删除，SEMM 支持管理以下组件：

- 有线局域网
- 相机
- 蓝牙
- WLAN
- 占用传感器
- 用于 PXE 启动的 IPv6
- 备用启动
- 启动顺序锁
- USB 启动
- UEFI 首页界面
    - 设备
    - 靴子
    - 日期/时间

    
### 使用可启动的 USB 恢复 Hub

Surface Hub 2S 允许管理员使用恢复映像在 20 分钟内将设备重新安装到出厂设置。 通常，只有在 Surface Hub 无法再正常工作时，才需要执行此操作。 此外，如果丢失了 Bitlocker 密钥或不再拥有“设置”应用的管理员凭据，则恢复操作也将很有用。

### 通过密码轮换强化设备帐户

Surface Hub 使用设备帐户（也称为“房间帐户”）来对 Exchange、Microsoft Teams 和其他服务进行身份验证。 启用密码轮换后，Hub 2S 每 7 天便会自动生成一个由 15-32 个字符组成的新密码，其中包括大写和小写字母、数字和特殊字符。 由于没有人知道密码，因此设备帐户密码轮换可有效地降低人为错误和潜在的社会工程安全攻击带来的相关风险。

## Windows 10 企业级安全性

除了本文中所提及的 Surface Hub 所特有的配置和功能之外，Surface Hub 还使用了 Windows 10 的标准安全功能。 这些地方包括：

- **BitLocker**。 Surface Hub SSD 配有 BitLocker，以保护设备上的数据。 其配置符合行业标准。 有关详细信息，请参阅 [BitLocker 概述](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。
- **Windows Defender。** Windows Defender 反恶意软件引擎在 Surface Hub 上持续运行，可自动修复在 Surface Hub 上发现的威胁。 Windows Defender 引擎将自动接收更新，且可通过面向 IT 管理员的远程管理工具进行管理。 Windows Defender 引擎是我们的深度防御方法的一个完美示例：如果恶意软件能够找到一种方法来绕过我们基于核心代码签名的安全解决方案，它将在此处被捕获。 有关详细信息，请参阅 [Windows Defender 应用程序控制和对代码完整性的基于虚拟化的保护](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)。
- **即插即用驱动程序。** 为了防止恶意代码通过驱动程序到达设备，Surface Hub 不下载用于 PnP 设备的高级驱动程序。 因此，U 盘等利用基本驱动程序的设备可按预期工作，但打印机等高级系统则会被阻止。
- **受信任的平台模块 2.0。** Surface Hub 有一个行业标准的离散受信任平台模块 (dTPM)，可生成和存储加密密钥和哈希代码。 dTPM 可保护用于启动阶段验证的密钥、BitLocker 主密钥、无密码登录密钥等。 dTPM 满足 [FIPS 140-2 级别 2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation) 认证（美国政府计算机安全标准）条件，且符合全球范围使用的[通用标准](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria)认证条件。

## Surface Hub 的无线安全性

Surface Hub 采用了 Wi-Fi Direct/Miracast 技术以及关联的 802.11、Wi-Fi 保护访问 2 (WPA2) 和无线保护设置 (WPS) 标准。 由于本设备仅支持 WPS（与 WPA2 预共享密钥 (PSK) 或 WPA2 企业相反），因此，问题通常与 802.11 密钥的设计进行过简化有关。

Miracast 是 WLAN 显示标准的一部分，本身受 WLAN Direct 协议的支持。 这些标准受用于屏幕共享和协作的现代移动设备的支持。

Wi-Fi Direct 或 Wi-Fi 对等 (P2P) 是 Wi-Fi 联盟针对“临时”网络发布的标准。 此标准允许受支持的设备直接通信和创建网络组，无需传统的 WLAN 接入点或 Internet 连接。

WLAN Direct 的安全性由 WPA2 使用 WPS 标准提供。 设备的身份验证机制包括数字 PIN 码、物理或虚拟“推送”按钮以及使用近场通信的带外消息。 Surface Hub 支持“推送”按钮（默认方式）和 PIN 方法。 有关详细信息，请参阅 [Surface Hub 如何解决 Wi-fi Direct 安全问题](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct)。

## 了解详细信息

- [安全启动概述](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

- [Bitlocker 概述](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)

- [应用程序控制概述](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [使用 SEMM 和 UEFI 保护 Surface Hub 2S 的安全并进行管理](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm)

- [Surface Hub 如何解决 Wi-Fi Direct 的安全问题](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct)

- [Windows Defender 应用程序控制和对代码完整性的基于虚拟化的保护](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

- [适合 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)

- [FIPS 140-2 级别 2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)

- [通用标准认证](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria)

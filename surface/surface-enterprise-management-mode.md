---
title: 'Surface Enterprise Management Mode (Surface) '
description: 了解 Surface 设备与 Surface UEFI 的此功能如何帮助你保护和管理组织的固件设置。
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
ms.date: 01/15/2021
ms.openlocfilehash: e6f81639253c646f5d3956243a80f4d61c91028a
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271416"
---
# Microsoft Surface Enterprise 管理模式

Microsoft Surface Enterprise Management Mode (SEMM) 是 Surface UEFI 的 Surface 设备的一项功能，允许你在组织中保护和管理固件设置。 借助 SEMM，IT 专业人员可以准备 UEFI 设置的配置，并安装在 Surface 设备上。 除了能够配置 UEFI 设置外，SEMM 还使用证书来保护配置，防止未经授权的篡改或删除。 SEMM 是能够将 Surface Hub 2S 迁移到 Windows 10 专业版和企业版的要求。

>[!NOTE]
>SEMM 仅在具有 Surface UEFI 固件的设备上可用。 这包括大多数其他 Surface 设备，包括 Surface Pro 7+、Surface Pro X、Surface Hub 2S 和 Surface Laptop 3 商业 SUS（带 Intel 处理器）和 Surface Laptop Go。 带 AMD 处理器的 15" Surface Laptop 3 SKU 不支持 SEMM (仅作为零售 SKU) 。 

当 Surface 设备由 SEMM 配置且使用 SEMM 证书进行保护时，它们将被视为 *在* SEMM 中注册。 删除 SEMM 证书并控制 UEFI 设置后，将 UEFI 设置返回到设备用户，Surface** 设备将被视为在 SEMM 中注销。

有两个管理选项可用于管理 SEMM 和注册 Surface 设备 - 独立工具或与 Microsoft Endpoint Configuration Manager 集成。 本文介绍 SEMM 独立工具（称为 Microsoft Surface UEFI 配置器）。 有关如何使用 Microsoft Endpoint Configuration Manager 管理 SEMM 的信息，请参阅使用 Microsoft Endpoint Configuration Manager 通过 [SEMM 管理设备](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)。


## Microsoft Surface UEFI 配置程序

SEMM 的主要工作区是 Microsoft Surface UEFI 配置器，如图 1 所示。 Microsoft Surface UEFI 配置器是用于创建 Windows Installer (.msi) 程序包或 WinPE 映像的工具，用于在 Surface 设备上注册、配置和注销 SEMM。 这些包包含一个配置文件，其中指定了 UEFI 的设置。 SEMM 包还包含一个证书，该证书已安装并存储在固件中，用于在应用 UEFI 设置之前验证配置文件的签名。

>[!NOTE]
>你现在可以使用 Surface UEFI 配置器和 SEMM 管理 Surface 扩展坞 2 上的端口。 若要了解更多信息，请参阅 [使用 SEMM](secure-surface-dock-ports-semm.md)的安全 Surface 扩展坞 2 端口。

![Microsoft Surface UEFI 配置程序](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*图 1. Microsoft Surface UEFI 配置程序*


可以在三种模式下使用 Microsoft Surface UEFI 配置器工具：

* [Surface UEFI 配置包](#configuration-package)。 使用此模式创建 Surface UEFI 配置包以在 SEMM 中注册 Surface 设备，并配置已注册设备的 UEFI 设置。
* [Surface UEFI 重置程序包](#reset-package)。 使用此模式从 SEMM 注销 Surface 设备。
* [Surface UEFI 恢复请求](#recovery-request)。 使用此模式响应恢复请求，以从 SEMM 注销 Surface 设备，其中重置程序包操作未成功。


#### 下载 Microsoft Surface UEFI 配置程序

你可以从 Microsoft 下载中心的 Surface Tools [for IT](https://www.microsoft.com/download/details.aspx?id=46703) 页面下载 Microsoft Surface UEFI 配置程序。

### 配置包

Surface UEFI 配置包是实现和管理 Surface 设备上 SEMM 的主要机制。 这些包包含 Microsoft Surface UEFI 配置器中程序包创建期间指定的 UEFI 设置的配置文件和证书文件，如图 2 所示。 当配置包首次在尚未在 SEMM 中注册的 Surface 设备上运行时，它将在设备的固件中设置证书文件，并注册 SEMM 中的设备。 在 SEMM 中注册设备时，系统会提示你确认操作，在存储证书文件并完成注册之前，提供 SEMM 证书指纹的最后两位数。 此确认要求用户在注册时实际存在于设备中以执行确认。

![使用证书保护 SEMM 配置包](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*图 2. 使用证书保护 SEMM 配置包*

有关 [SEMM](#surface-enterprise-management-mode-certificate-requirements) 证书要求详细信息，请参阅本文的 Surface Enterprise Management Mode 证书要求部分。

>[!NOTE]
>还可以使用 SEMM 指定查看 Surface UEFI 的安全、设备****、启动**** 配置或企业管理******页所需的**UEFI 密码。

在 SEMM 中注册设备后，将读取配置文件，并且该文件中指定的设置将应用于 UEFI。 当你在已在 SEMM 中注册的设备上运行配置包时，将针对存储在设备固件中的证书检查配置文件的签名。 如果签名不匹配，则不对设备应用任何更改。

### 使用 SEMM 启用或禁用 Surface UEFI 中的设备

以下列表显示了可在 SEMM 中管理的所有可用设备：

* 扩展 USB 端口
* 板载音频
* DGPU
* Type Cover
* 微型 SD 卡
* 前置摄像头
* 后置摄像头
* 红外相机，适用于 Windows Hello
* Bluetooth仅
* WLAN 和蓝牙
*              LTE           

 >[!NOTE]
>显示在 UEFI 设备页面中的内置设备可能因设备或公司环境而异。 例如，Surface Pro X 不支持 UEFI 设备页面;LTE 仅在配备了 LTE 的设备上显示。 
### 使用 SEMM 配置高级设置
**表 1.  高级设置**

| 设置                            | 描述                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 用于 PXE 启动的 IPv6                  | 允许你管理对 PXE 启动的 IPv6 支持。 如果未配置此设置，则禁用对 PXE 启动的 IPv6 支持。                                                                               |
| 备用启动                     | 允许你管理备用启动顺序的使用，以在启动期间通过按"降低音量"按钮和电源按钮直接启动到 USB 或以太网设备。 如果未配置此设置，则启用备用启动。 |
| 启动顺序锁                    | 允许你锁定启动顺序以防止更改。 如果未配置此设置，则启动顺序锁定处于禁用状态。                                                                                                        |
| USB 启动                           | 允许你管理到 USB 设备的启动。 如果未配置此设置，将启用 USB 启动。                                                                                                                 |
| 网络堆栈                      | 允许你管理网络堆栈启动设置。 如果未配置此设置，将禁用管理网络堆栈启动设置的能力。                                                                                                           |
| 自动打开电源                      | 允许你管理自动打开电源启动设置。 如果未配置此设置，则启用"自动打开"功能。                                                                                                        |
| 同时多线程 (SMT)  | 允许你管理同时多线程 (SMT) 启用或禁用超线程。 如果未配置此设置，则启用 SMT。                                                  |
|启用电池限制| 允许你管理电池限制功能。 如果未配置此设置，则启用电池限制 |
| 安全性                           | 显示 Surface UEFI **安全** 页。 如果未配置此设置，将显示"安全"页。                                                                                                                 |
| 设备                            | 显示 Surface UEFI **设备** 页。 如果未配置此设置，将显示"设备"页。                                                                                                                     |
| 靴子                               | 显示 Surface UEFI **启动** 页面。 如果未配置此设置，将显示"启动"页。                                                                                                                                                            |
| DateTime                           | 显示 Surface UEFI **DateTime** 页。 如果未配置此设置，将显示 DateTime 页。                                                                                                                |
| EnableOSMigration                          | 允许你将 Surface Hub 2 从 Windows 10 团队迁移到 Windows 10 专业版或企业版。 如果未配置此设置，Surface Hub 2 设备只能运行 Windows 10 团队操作系统。   注意：Windows 10 团队和 Windows 10 专业/企业版之间的双启动在 Surface Hub 2 上不可用。                                                                                                           |


>[!NOTE]
>创建 SEMM 配置包时，成功页面上会显示两个字符，**** 如图 3 所示。

![证书指纹显示](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*图 3. 在"成功"页上显示证书指纹的最后两个字符*

这些字符是证书指纹的最后两个字符，应该记下或记录它们。 需要这些字符才能确认在 Surface 设备上注册 SEMM，如图 4 所示。

![SEMM 中的注册确认](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*图 4. SEMM 中具有 SEMM 证书指纹的注册确认*

>[!NOTE]
>有权访问证书文件 (.pfx) 管理员可通过在 CertMgr 中打开 .pfx 文件随时读取指纹。 若要使用 CertMgr 查看指纹，请按照以下过程操作：
>1. 右键单击 .pfx 文件，然后单击"打开 **"。**
>2. 展开导航窗格中的文件夹。
>3. 单击“**证书**”。
>4. 右键单击主窗格中的证书，然后单击"打开 **"。**
>5. 单击 **"详细信息"** 选项卡。
>6. **必须在**"**显示**"下拉菜单中选择"全部****"或"仅属性"。
>7. 选择字段 **Thumbprint**。

若要在 SEMM 中注册 Surface 设备或应用配置包中的 UEFI 配置，只需在预期的 Surface 设备上使用管理权限运行 .msi 文件。 可以使用应用程序部署或操作系统部署技术，如[Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023)或 Microsoft Deployment [Toolkit。](https://technet.microsoft.com/windows/dn475741) 在 SEMM 中注册设备时，必须实际存在以确认在设备上注册。 将配置应用于已在 SEMM 中注册的设备时，不需要用户交互。

有关如何在 SEMM 中注册 Surface 设备或使用 SEMM 应用 Surface UEFI 配置的分步演练，请参阅使用 [SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)注册和配置 Surface 设备。

### 重置程序包

Surface UEFI 重置程序包仅用于执行一项任务- 从 SEMM 注销 Surface 设备。 重置程序包包含从设备固件中删除 SEMM 证书以及将 UEFI 设置重置为出厂默认设置的已签名说明。 与 Surface UEFI 配置包一样，必须使用 Surface 设备上预配的相同 SEMM 证书对重置程序包进行签名。 创建 SEMM 重置程序包时，需要提供要重置的 Surface 设备的序列号。 SEMM 重置程序包不是通用的，并且特定于一台设备。

### 恢复请求

在某些情况下，可能无法使用 Surface UEFI 重置程序包。  (例如，如果 Windows 在 Surface 设备上不可用。) 在这些情况下，可以通过图 5) 通过 Surface UEFI (的"**** 企业管理"页从 SEMM 注销 Surface 设备（使用恢复请求操作）。

![启动 SEMM 恢复请求](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*图 5. 在"企业管理"页上启动 SEMM 恢复请求*

当你使用"企业管理"页上的过程**** 在 Surface 设备上重置 SEMM 时，会提供重置请求。 此重置请求可以另存为文件到 USB 驱动器、以文本格式复制，或者通过移动设备以 QR 代码进行读取，以轻松地通过电子邮件发送或发送消息。 使用 Microsoft Surface UEFI 配置程序重置请求选项加载重置请求文件或输入重置请求文本或 QR 代码。 Microsoft Surface UEFI 配置器将生成可在 Surface 设备上输入的验证码。 如果在 Surface 设备上输入代码 **并单击"** 重启"，该设备将注销 SEMM。 

>[!NOTE]
>重置请求将在创建两小时后过期。

有关如何从 SEMM 取消注册 Surface 设备的分步演练，请参阅从 SEMM 注销 [Surface 设备](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)。

## Surface 企业管理模式证书要求
将 SEMM 与 Microsoft Surface UEFI 配置器一起使用需要证书来验证配置文件的签名，然后才能应用 UEFI 设置。 此证书可确保在 SEMM 中注册设备后，只有使用批准的证书创建的程序包才能用于修改 UEFI 的设置。

>[!NOTE]
>需要 SEMM 证书才能在已注册的 Surface 设备上对 SEMM 或 Surface UEFI 设置执行任何修改。 如果 SEMM 证书已损坏或丢失，则不能删除或重置 SEMM。 使用相应的备份和恢复解决方案相应地管理 SEMM 证书。

使用 Microsoft Surface UEFI Configurator 工具创建的程序包使用证书进行签名。 此证书可确保在 SEMM 中注册设备后，只有使用批准的证书创建的程序包才能用于修改 UEFI 的设置。 
### 建议的证书设置
建议为 SEMM 证书设置以下设置：

* **密钥算法** – RSA 
* **密钥长度** – 2048
* **哈希算法** – SHA-256
* **类型** – SSL 服务器身份验证
* **密钥用法** – 数字签名、密钥加密
* **提供程序** – Microsoft 增强 RSA 和 AES 加密提供程序
* **到期日期** – 自证书创建起 15 个月
* **密钥导出策略** – 可导出

还建议在两层公钥基础结构 (PKI) 体系结构中对 SEMM 证书进行身份验证，其中中间证书颁发机构 (CA) 专用于 SEMM，从而实现证书吊销。 有关两层 PKI 配置的信息，请参阅测试实验室指南：部署 [AD CS Two-Tier PKI 层次结构](https://technet.microsoft.com/library/hh831348)。

### 自签名证书 
可以使用以下示例 PowerShell 脚本创建自签名证书，以用于概念证明方案。
若要使用此脚本，请将以下文本复制到记事本，并将其另存为 PowerShell 脚本 (.ps1) 。 

> [!NOTE]
> 此脚本创建密码为 .的证书 `12345678` 。不建议在生产环境中使用此脚本生成的证书。
  
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
>要与 SEMM 和 Microsoft Surface UEFI 配置器一起使用，必须使用私钥和密码保护导出证书。 如果需要，Microsoft Surface UEFI 配置器将提示你选择 SEMM 证书文件 (.pfx) 和证书密码。

1.  在 C： 驱动器上创建一个文件夹，用于保存脚本;例如，C：\SEMM。
2.  将示例脚本复制到记事本或等效文本编辑器中，将文件另存为 PowerShell 脚本 (.ps1) 。
3.  使用管理员凭据登录电脑并打开提升的 PowerShell 会话。
4.  确保将权限设置为允许脚本运行。 默认情况下，除非修改执行策略，否则将阻止脚本运行。 若要了解更多信息，请参阅["关于执行策略"。](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)
5.  在命令提示符下，输入脚本的完整路径，然后按 Enter。 该脚本创建一个名为 TempOwner.pfx 的演示证书。

或者，您可以使用 PowerShell 创建自己的自签名证书。 有关详细信息，请参阅以下 PowerShell 文档 [：New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)。




>[!NOTE]
>对于在 PKI 基础结构中使用脱机根的组织，Microsoft Surface UEFI 配置程序必须在连接到根 CA 的环境中运行，以对 SEMM 证书进行身份验证。 Microsoft Surface UEFI 配置程序生成的程序包可以文件传输，因此可以使用可移动存储（如 U 盘）在脱机网络环境外部传输。

### 管理证书常见问题解答

建议 *的最小长度* 为 15 个月。 您可以使用在 15 个月内过期的证书，或使用过期时间超过 15 个月的证书。

>[!NOTE] 
>当证书过期时，它不会自动续订。 


**过期的证书是否会影响 SEMM 注册的设备的功能？**<br><br>
否，证书仅影响 SEMM 中的 IT 管理员管理任务，在到期时不会影响设备功能。


**在拥有 SEMM 程序包和证书的所有计算机上是否需要更新它？**

如果希望 SEMM 重置或恢复正常工作，证书必须有效且不会过期。 

**能否为订购的每个图面创建批量重置程序包？ 能否生成一个可重置环境中的所有计算机？**

为特定设备类型创建配置包的 PowerShell 示例还可用于创建独立于序列号的重置程序包。 如果证书仍然有效，可以使用 PowerShell 创建重置程序包以重置 SEMM。

## 版本历史记录

### 版本 2.79.139.0

此版本的 SEMM 包括：
- 支持 Surface Pro 7+
- 用户体验改进


### 版本 2.78.139.0

此版本的 SEMM 包括：

- 支持 Surface Laptop Go 和 Surface Pro X
- 新版本发布的通知
- 创建自定义程序包以更改所有权的能力
- Bug 修复

### 版本 2.73.136.0

此版本的 SEMM 包括：

- 现在可以使用 SEMM 在 Surface Hub2S 上禁用音频
- 支持适用于扩展坞 2 的 Surface Pro X
- 支持 UEFI Manager 执行与扩展坞 2 相关的操作
- Surface Go 重置程序包 bug 修复
- 支持将 Surface Hub 2 设备从 Windows 10 团队操作系统迁移到 Windows 10 专业版或企业版。

### 版本 2.71.139.0

此版本的 SEMM 增加了对 Surface Book 3、Surface Laptop 3 和 Surface Pro 7 的 Surface Dock 2 管理功能的支持，包括：

- 启用音频 (锁定/解锁) 以太网和 USB 端口
- 为经过身份验证和未经身份验证的主机创建扩展坞包的能力

### 版本 2.70.130.0

此版本的 SEMM 包括：

- 支持 Surface Go 2
- 支持 Surface Book 3
- Bug 修复


### 版本 2.59.139.0

* 支持使用 Intel 处理器的 Surface Pro 7、Surface Pro X 和 Surface Laptop 3 13.5" 和 15" 型号。 注意：Surface Laptop 3 15" AMD 处理器不受支持。

- 支持电源唤醒功能

### 版本 2.54.139.0
* 支持 Surface Hub 2S
* Bug 修复

### 版本 2.43.136.0
* 支持启用/禁用模拟多线程 
* 适用于某些Bluetooth WiFi 和移动设备的单独选项 
* 已删除 Surface Studio 的电池限制 

### 版本 2.26.136.0
* 添加对 Surface Studio 2 的支持
* 电池限制功能

### 版本 2.21.136.0
* 向 Surface Pro 6 添加支持
* 添加对 Surface Laptop 2 的支持

### 版本 2.14.136.0
* 向 Surface Go 添加支持

### 版本 2.9.136.0
* 添加对 Surface Book 2 的支持
* 添加对 Surface Pro LTE 的支持
* 辅助功能改进

### 版本 1.0.74.0
* 向 Surface Laptop 添加支持
* 向 Surface Pro 添加支持
* Bug 修复和常规改进

## 相关主题

- [使用 SEMM 注册并配置 Surface 设备](enroll-and-configure-surface-devices-with-semm.md)
- [从 SEMM 取消注册 Surface 设备](unenroll-surface-devices-from-semm.md)
- [使用 SEMM 保护 Surface Dock 2 端口](secure-surface-dock-ports-semm.md)

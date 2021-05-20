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
# <a name="microsoft-surface-enterprise-management-mode"></a>Microsoft Surface Enterprise 管理模式

Microsoft Surface Enterprise Management Mode (SEMM) 是 Surface 统一可扩展固件接口与 UEFI () 的功能。 可以使用 SEMM：

- 保护和管理贵组织的固件设置。
- 准备 UEFI 设置配置，然后将它们安装在 Surface 设备上。 

SEMM 还使用证书保护配置免受未经授权的篡改或删除。 若要将 Surface Hub 2S 迁移到 Windows 10 专业版 或 Windows Enterprise，需要 SEMM。

>[!NOTE]
>SEMM 仅在具有 Surface UEFI 固件的设备上可用。 这包括大多数其他 Surface 设备，包括带 Intel 处理器的 Surface Pro 7+、Surface Pro X、Surface Hub 2S、Surface Laptop 4 商业 S CPU、Surface Laptop 4 台商业 S CPU 和 AMD 处理器、Surface Laptop 3 台商业 SK（含 Intel 处理器）和 Surface Laptop Go。 带 AMD 处理器的 15" Surface Laptop 3 SKU 不支持 SEMM (仅作为零售 SKU) 。 

当 Surface 设备由 SEMM 配置且使用 SEMM 证书进行保护时，它们将被视为 *在* SEMM 中注册。 当删除 SEMM 证书并控制 UEFI 设置时，将 Surface 设备视为在 SEMM** 中注销。

有两个管理选项可用于管理 SEMM 和注册 Surface 设备：

- 本文介绍了 SEMM 独立工具 Microsoft Surface UEFI 配置器。 

- 与 Microsoft Endpoint Configuration Manager。 有关信息，请参阅[使用Microsoft Endpoint Configuration Manager SEMM 管理设备](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)。

> [!NOTE]
> 仅通过 UEFI Surface Pro X 支持 SEMM。 你可以从适用于 IT 的 [Surface Tools 下载](https://www.microsoft.com/download/details.aspx?id=46703)UEFI 管理器。 有关详细信息，请参阅部署[、管理和维护 Surface Pro X。](surface-pro-arm-app-management.md)


## <a name="microsoft-surface-uefi-configurator"></a>Microsoft Surface UEFI 配置器

SEMM 的主要工作区是 Microsoft Surface UEFI 配置器，如图 1 所示。 

可以使用 Microsoft Surface UEFI 配置器：

- 创建Windows安装程序 (.msi) 程序包。
- 使用 WinPE 映像在 Surface 设备上注册、配置和注销 SEMM。 

这些程序包包含指定 UEFI 设置的配置文件。 SEMM 包还包含在固件中安装并存储的证书，用于在应用 UEFI 设置之前验证配置文件的签名。

>[!TIP]
>你现在可以使用 Surface UEFI 配置器和 SEMM 管理 Surface 扩展坞 2 上的端口。 若要了解更多信息，请参阅使用 SEMM 保护 [Surface Dock 2 端口](secure-surface-dock-ports-semm.md)。

![Microsoft Surface UEFI 配置器](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*图 1. Microsoft Surface UEFI 配置器*

可以在三种模式下使用 Microsoft Surface UEFI 配置器工具：

- [Surface UEFI 配置包](#configuration-package)。 使用此模式创建 Surface UEFI 配置包，以在 SEMM 中注册 Surface 设备，并配置已注册设备的 UEFI 设置。
- [Surface UEFI 重置程序包](#reset-package)。 使用此模式从 SEMM 注销 Surface 设备。
- [Surface UEFI 恢复请求](#recovery-request)。 使用此模式响应恢复请求，以从重置程序包操作未成功的 SEMM 注销 Surface 设备。

#### <a name="download-microsoft-surface-uefi-configurator"></a>下载 Microsoft Surface UEFI 配置器

你可以从 Microsoft 下载中心的 Surface Tools [for IT 页面](https://www.microsoft.com/download/details.aspx?id=46703) 下载 Microsoft Surface UEFI 配置器。

### <a name="configuration-package"></a>配置包

Surface UEFI 配置包是 Surface 设备上实现和管理 SEMM 的主要机制。 这些包包含配置文件和证书文件，如图 2 所示。 配置文件包含在 Microsoft Surface UEFI 配置器中创建程序包时指定的 UEFI 设置。 当配置包首次在尚未在 SEMM 中注册的 Surface 设备上运行时，它会在设备的固件中设置证书文件，并注册 SEMM 中的设备。 在 SEMM 中注册设备时，在存储证书并完成注册之前，系统会提示你通过提供 SEMM 证书指纹的最后两位数来确认操作。 此确认要求用户在注册期间实际存在于设备上才能执行确认。

![使用证书保护 SEMM 配置包](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*图 2. 使用证书保护 SEMM 配置包*

有关 SEMM 证书的要求详细信息，请参阅本文稍后介绍的[Surface Enterprise 管理](#surface-enterprise-management-mode-certificate-requirements)模式证书要求部分。

>[!TIP]
>可以选择要求使用 SEMM 输入 UEFI 密码。 如果你这样做，需要密码才能查看 Surface UEFI**** 的安全、**** 设备、启动配置**Enterprise**管理"页面。 ****

在 SEMM 中注册设备后，将读取配置文件，并且该文件中指定的设置将应用于 UEFI。 当你在已在 SEMM 中注册的设备上运行配置包时，将针对存储在设备固件中的证书检查配置文件的签名。 如果签名不匹配，则不对设备应用任何更改。

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a>使用 SEMM 启用或禁用 Surface UEFI 中的设备

以下列表显示了可在 SEMM 中管理的所有可用设备：

- 扩展 USB 端口
- 板载音频
- 数字图形处理单元
- 类型覆盖
- 微型 SD 卡
- 前置摄像头
- 后置摄像头
-  (Hello Windows红外) 
- 仅蓝牙
- 无线网络和蓝牙
- LTE (长期) 

 >[!NOTE]
>在"UEFI 设备"页上，内置设备可能会有所不同，具体取决于设备或公司环境。 例如，UEFI 设备页面在 X 上不受Surface Pro支持;LTE 仅在配备了 LTE 的设备上显示。 
### <a name="configure-advanced-settings-with-semm"></a>使用 SEMM 配置高级设置
**表 1. 高级设置**

| 设置                            | 描述                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 用于 PXE 启动的 IPv6                  | 允许你管理对 PXE 启动的 IPv6 支持。 如果未配置此设置，则禁用对 PXE 启动的 IPv6 支持。                                                                               |
| 备用启动                     | 允许你管理备用启动顺序的使用，以便通过启动期间同时按"降低音量"按钮和"电源"按钮，直接启动到 USB 或以太网设备。 如果未配置此设置，则启用备用启动。 |
| 启动顺序锁                    | 允许你锁定启动顺序以防止更改。 如果未配置此设置，则启动顺序锁定处于禁用状态。                                                                                                        |
| USB 启动                           | 允许你管理到 USB 设备的启动。 如果未配置此设置，将启用 USB 启动。                                                                                                                 |
| 网络堆栈                      | 允许你管理网络堆栈启动设置。 如果未配置此设置，将禁用管理网络堆栈启动设置的能力。                                                                                                           |
| 自动打开电源                      | 允许你管理"自动打开电源"启动设置。 如果未配置此设置，则启用"自动打开"。                                                                                                        |
| 同时多线程 (SMT)  | 允许你管理同时多线程 (SMT) 启用或禁用超线程。 如果未配置此设置，则启用 SMT。                                                  |
|启用电池限制| 允许你管理电池限制功能。 如果未配置此设置，则启用电池限制 |
| 安全性                           | 显示 Surface UEFI **安全** 页。 如果未配置此设置，将显示"安全"页。                                                                                                                 |
| 设备                            | 显示 Surface UEFI **设备** 页面。 如果未配置此设置，将显示"设备"页。                                                                                                                     |
| 靴子                               | 显示 Surface UEFI **启动** 页面。 如果未配置此设置，将显示"启动"页。                                                                                                                                                            |
| DateTime                           | 显示 Surface UEFI **DateTime** 页。 如果未配置此设置，将显示 DateTime 页。                                                                                                                |
| EnableOSMigration                          | 允许您将 Surface Hub 2 从 Windows 10 协同版 迁移到 Windows 10 专业版 或 Enterprise。 如果未配置此设置，则 Surface Hub 2 台设备只能运行Windows 10 协同版操作系统。 注意：Windows 10 协同版 2 Windows 10 专业版/Enterprise之间的双Surface Hub启动。                                                                                                           |


>[!NOTE]
>创建 SEMM 配置包时，成功页面上会显示两个字符，**** 如图 3 所示。

![证书指纹显示](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*图 3. 在"成功"页上显示证书指纹的最后两个字符*

这些字符是证书指纹的最后两个字符，应该记下或记录它们。 确认在 Surface 设备上注册 SEMM 时需要这些字符，如图 4 所示。

![SEMM 中的注册确认](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*图 4. SEMM 中具有 SEMM 证书指纹的注册确认*

>[!NOTE]
>有权访问证书文件 (.pfx) 可通过在 CertMgr 中打开 .pfx 文件来随时读取指纹。 若要使用 CertMgr 查看指纹：
>1. 选择并按住 (或右键) .pfx 文件，然后选择"打开 **"。**
>2. 在导航窗格中，展开文件夹。
>3. 选择 **"证书"。**
>4. 在主窗格中，选择并按住 (或右键单击) 证书"，然后选择"打开 **"。**
>5. 选择" **详细信息"** 选项卡。
>6. 在" **显示** "下拉菜单中， **必须选择"全部** "或" **仅** 属性"。
>7. 选择" **指纹"** 字段。

若要在 SEMM 中注册 Surface 设备或从配置包应用 UEFI 配置，请对预期的 Surface 设备使用管理权限运行 .msi 文件。 可以使用应用程序部署或操作系统部署技术，如 Microsoft Endpoint Configuration Manager 或[](https://technet.microsoft.com/library/mt346023) [Microsoft Deployment Toolkit。](https://technet.microsoft.com/windows/dn475741) 在 SEMM 中注册设备时，必须实际存在以确认在设备上注册。 将配置应用于已在 SEMM 中注册的设备时，不需要用户交互。

有关如何在 SEMM 中注册 Surface 设备或向 SEMM 应用 Surface UEFI 配置的分步演练，请参阅使用 [SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)注册和配置 Surface 设备。

### <a name="reset-package"></a>重置程序包

Surface UEFI 重置程序包仅用于执行一项任务 - 从 SEMM 注销 Surface 设备。 重置程序包包含从设备固件中删除 SEMM 证书以及将 UEFI 设置重置为出厂默认设置的签名说明。 与 Surface UEFI 配置包一样，必须使用在 Surface 设备上预配的相同 SEMM 证书对重置程序包进行签名。 创建 SEMM 重置程序包时，需要提供要重置的 Surface 设备的序列号。 SEMM 重置程序包并不通用，它们特定于一台设备。

### <a name="recovery-request"></a>恢复请求

在某些情况下，可能无法使用 Surface UEFI 重置程序包。  (例如，如果 Windows 在 Surface 设备上变得不可用。) 在这些情况下，可以通过 Surface UEFI (的**Enterprise**管理"页从 SEMM 注销 Surface 设备，如图 5) 中的"恢复请求"操作所示。

> [!div class="mx-imgBorder"]
> ![启动 SEMM 恢复请求](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*图 5. 在"管理"页上Enterprise SEMM 恢复请求*

当你使用"Enterprise管理"页上**** 的过程在 Surface 设备上重置 SEMM 时，你获得重置请求。 此重置请求可以另存为文件到 U 盘、复制为文本，或读取为 QR 码（通过移动设备轻松通过电子邮件发送或发送消息）。 使用 Microsoft Surface UEFI 配置程序重置请求选项加载重置请求文件或输入重置请求文本或 QR 代码。 Microsoft Surface UEFI 配置器生成可在 Surface 设备上输入的验证码。 如果你在 Surface 设备上输入代码并选择重启，则**** 设备从 SEMM 注销。 

>[!NOTE]
>重置请求将在创建后的两小时后过期。

有关如何从 SEMM 取消注册 Surface 设备的分步演练，请参阅从 SEMM 注销 [Surface 设备](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)。

## <a name="surface-enterprise-management-mode-certificate-requirements"></a>Surface Enterprise 管理模式证书要求
当你将 SEMM 与 Microsoft Surface UEFI 配置器一同使用，并且想要应用 UEFI 设置时，需要证书来验证配置文件的签名。 此证书可确保在设备注册 SEMM 后，只有使用已批准证书创建的程序包可用于修改 UEFI 设置。

>[!NOTE]
>若要在已注册的 Surface 设备上对 SEMM 或 Surface UEFI 设置进行任何修改，需要 SEMM 证书。 如果 SEMM 证书已损坏或丢失，则不能删除或重置 SEMM。 使用相应的备份和恢复解决方案相应地管理 SEMM 证书

使用 Microsoft Surface UEFI 配置器工具创建的程序包使用证书进行签名。 此证书可确保在 SEMM 中注册设备后，只有使用已批准证书创建的程序包可用于修改 UEFI 的设置。 
### <a name="recommended-certificate-settings"></a>建议的证书设置
对于 SEMM 证书，建议使用以下设置：

- **密钥算法** – RSA 
- **密钥长度** – 2048
- **哈希算法** – SHA-256
- **类型** – SSL 服务器身份验证
- **密钥用法** – 数字签名、密钥加密
- **提供程序** – Microsoft 增强 RSA 和 AES 加密提供程序
- **到期日期** – 自证书创建起 15 个月
- **密钥导出策略** – 可导出

还建议在两层公钥基础结构 (PKI) 体系结构中对 SEMM 证书进行身份验证，其中中间证书颁发机构 (CA) 专用于 SEMM，从而启用证书吊销。 有关两层 PKI 配置详细信息，请参阅测试实验室指南：部署 [AD CS](https://technet.microsoft.com/library/hh831348)Two-Tier PKI 层次结构。

### <a name="self-signed-certificate"></a>自签名证书 
可以使用以下示例 PowerShell 脚本创建自签名证书，以用于概念证明方案。
若要使用此脚本，将以下文本复制到 记事本，然后将文件另存为 PowerShell 脚本 (.ps1) 。 

> [!NOTE]
> 此脚本创建密码为 的证书 `12345678` 。 不建议在生产环境中使用此脚本生成的证书。
  
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
>要与 SEMM 和 Microsoft Surface UEFI 配置器一起使用，必须使用私钥和密码保护导出证书。 Microsoft Surface UEFI 配置器会提示你选择 SEMM 证书文件 (.pfx) 密码。

创建自签名证书：
1.  在 C： 驱动器上，创建用于保存脚本的文件夹;例如，C：\SEMM。
2.  将示例脚本复制到记事本 (或等效文本编辑器) ，然后将文件另存为 PowerShell 脚本 (.ps1) 。
3.  使用管理员凭据登录计算机，然后打开提升的 PowerShell 会话。
4.  请确保将权限设置为允许脚本运行。 默认情况下，除非修改执行策略，否则将阻止脚本运行。 若要了解更多信息，请参阅关于 [执行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)。
5.  在命令提示符下，输入脚本的完整路径，然后按**Enter。** 该脚本将创建一个名为 TempOwner.pfx 的演示证书。

或者，您可以使用 PowerShell 创建自己的自签名证书。 有关详细信息，请参阅 [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)。

>[!NOTE]
>对于在 PKI 基础结构中使用脱机根的组织，Microsoft Surface UEFI 配置器必须在连接到根 CA 的环境中运行，以对 SEMM 证书进行身份验证。 Microsoft Surface UEFI 配置器生成的程序包可以文件传输，因此可以使用可移动存储（如 U 盘）在脱机网络环境外部传输。

### <a name="managing-certificates-faq"></a>管理证书常见问题解答

建议 *的最小长度* 为 15 个月。 您可以使用在 15 个月内过期的证书，或使用有效期超过 15 个月的证书。

>[!NOTE] 
>当证书过期时，它不会自动续订。 

**过期的证书是否会影响 SEMM 注册设备的功能？**<br><br>
否，证书仅影响 SEMM 中的 IT 管理员管理任务，在证书过期时不会影响设备功能。

**是否需要在所有拥有 SEMM 程序包和证书的计算机上进行更新？**<br><br>
如果希望 SEMM 重置或恢复正常工作，证书必须有效且不会过期。 

**能否为订购的每个图面创建批量重置程序包？ 能否生成可重置环境中所有计算机的计算机？**<br><br>
为特定设备类型创建配置包的 PowerShell 示例还可用于创建独立于序列号的重置程序包。 如果证书仍然有效，可以使用 PowerShell 创建重置程序包以重置 SEMM。

## <a name="version-history"></a>版本历史记录


### <a name="version-2831390"></a>版本 2.83.139.0

此版本的 SEMM 包括：

- 支持 Surface Laptop 4
- 支持用于 7 的并发多线程Surface Pro选项
- 删除过时的 SEMM 设置  
- 改进的 MSI 签名 

### <a name="version-2791390"></a>版本 2.79.139.0

此版本的 SEMM 包括：

- 支持 Surface Pro 7 及以上。
- 用户体验改进。

### <a name="version-2781390"></a>版本 2.78.139.0

此版本的 SEMM 包括：

- 支持 Surface Laptop Go 和 Surface Pro X。
- 新版本发布的通知。
- 创建自定义程序包以更改所有权的能力。
- Bug 修复。

### <a name="version-2731360"></a>版本 2.73.136.0

此版本的 SEMM 包括：

- 使用 SEMM 在 Surface Hub2S 上禁用音频的能力。
- 支持扩展Surface Pro 2 的 X。
- 支持 UEFI 管理器执行与扩展坞 2 相关的操作。
- Surface Go 重置程序包 Bug 修复。
- 支持将 Surface Hub 2 Windows 10 协同版操作系统迁移到 Windows 10 专业版 或 Enterprise。

### <a name="version-2711390"></a>版本 2.71.139.0

此版本的 SEMM 增加了对适用于 Surface Book 3、Surface Laptop 3 和 Surface Pro 7 的 Surface Dock 2 管理功能的支持。 其中包括：

- 能够启用音频端口 (/解锁) 以太网和 USB 端口。
- 为经过身份验证和未经身份验证的主机创建扩展坞包的能力。

### <a name="version-2701300"></a>版本 2.70.130.0

此版本的 SEMM 包括：

- 支持 Surface Go 2。
- 支持 Surface Book 3。
- Bug 修复。

### <a name="version-2591390"></a>版本 2.59.139.0

此版本的 SEMM 包括：

- 支持Surface Pro Intel 处理器Surface Pro 7、Surface Pro X 和 Surface Laptop 3 13.5" 和 15" 型号。 
    >[!NOTE]
    >Surface Laptop不支持 3 个 15" AMD 处理器。
- 支持电源唤醒功能。

### <a name="version-2541390"></a>版本 2.54.139.0

此版本的 SEMM 包括：

- 支持 Surface Hub 2S。
- Bug 修复。

### <a name="version-2431360"></a>版本 2.43.136.0

此版本的 SEMM 包括：

- 支持启用/禁用同时多线程。
- 用于某些设备的无线网络和蓝牙选项。
- 已删除电池Surface Studio。

### <a name="version-2261360"></a>版本 2.26.136.0

此版本的 SEMM 包括：

- 支持 Surface Studio 2。
- 电池限制功能。

### <a name="version-2211360"></a>版本 2.21.136.0

此版本的 SEMM 包括：

- 支持 Surface Pro 6.
- 支持 Surface Laptop 2。

### <a name="version-2141360"></a>版本 2.14.136.0

此版本的 SEMM 包括：

- 支持 Surface Go。

### <a name="version-291360"></a>版本 2.9.136.0

此版本的 SEMM 包括：

- 支持 Surface Book 2。
- 支持 Surface Pro LTE。
- 辅助功能改进。

### <a name="version-10740"></a>版本 1.0.74.0

此版本的 SEMM 包括：

- 支持Surface Laptop。
- 支持Surface Pro。
- Bug 修复和常规改进。

## <a name="related-topics"></a>相关主题

- [使用 SEMM 注册并配置 Surface 设备](enroll-and-configure-surface-devices-with-semm.md)
- [从 SEMM 取消注册 Surface 设备](unenroll-surface-devices-from-semm.md)
- [使用 SEMM 保护 Surface Dock 2 端口](secure-surface-dock-ports-semm.md)

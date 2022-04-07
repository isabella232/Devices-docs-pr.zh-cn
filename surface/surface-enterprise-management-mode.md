---
title: Surface 企业管理模式 (SEMM)
description: 了解使用 Surface UEFI 的 Surface 设备的此功能如何帮助你保护和管理组织中的固件设置。
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
ms.date: 12/08/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 9e08b3dd804b8b4ac6e2ee4dd4041ed2e684d5d7
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472641"
---
# <a name="microsoft-surface-enterprise-management-mode-semm"></a>MICROSOFT Surface Enterprise管理模式 (SEMM) 

Microsoft Surface Enterprise管理模式 (SEMM) 是 Surface 设备的一项功能，具有 Surface Unified Unified Extensible 固件接口 (UEFI) 。 可以使用 SEMM 执行以下操作：

- 保护和管理组织中的固件设置。
- 准备 UEFI 设置配置并将其安装在 Surface 设备上。

SEMM 还使用证书保护配置免受未经授权的篡改或删除。 若要将Surface Hub 2S 迁移到Windows 10 专业版或Windows Enterprise，需要 SEMM。

## <a name="supported-devices"></a>支持的设备

SEMM 仅在具有 Surface UEFI 固件的设备上可用，包括： 

- Surface Pro 8 (商业 SKU 仅) 
- Surface Pro 4及更高版本 (所有 SKU) 
- Surface Pro X (所有 SKU) 
- Surface Laptop 标准版 (所有 SKU) 
- Surface Laptop工作室仅 (商业 SKU)  
- Surface Hub 2S
- Surface Laptop 4 (商业 SKU 仅) 
- Surface Laptop 3 (Intel 处理器仅) 
- Surface Laptop Go 
- Surface Book (所有世代) 
- Surface Go，Surface Go 2
- Surface Go 3 (商业 SKU 仅) 
- Surface Studio 

>[!TIP]
> 商业 SKU (又名Surface 商用版) 运行Windows 10 专业版/Enterprise或Windows 11 专业版/Enterprise;使用者 SKU 运行Windows 10/Windows 11 家庭版。 若要了解详细信息， [请参阅查看系统信息](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00)。 


## <a name="getting-started"></a>入门 

当 Surface 设备由 SEMM 配置并使用 SEMM 证书进行保护时，它们被视为已在 SEMM 中 *注册* 。 删除 SEMM 证书并将 UEFI 设置的控制返回给设备用户时，Surface 设备在 SEMM 中被视为 *未注册* 。

有两个管理选项可用于管理 SEMM 和注册 Surface 设备：

- 本文介绍了 SEMM 独立工具 Microsoft Surface UEFI 配置器。

- 与Microsoft Endpoint Configuration Manager集成。 有关信息，请参阅[使用Microsoft Endpoint Configuration Manager使用 SEMM 管理设备](use-system-center-configuration-manager-to-manage-devices-with-semm.md)。

## <a name="microsoft-surface-uefi-configurator"></a>Microsoft Surface UEFI 配置器

SEMM 的主要工作区是 Microsoft Surface UEFI 配置器，如图 1 所示。

可以使用 Microsoft Surface UEFI 配置器执行以下操作：

- 创建Windows安装程序 (.msi) 包。
- 使用 WinPE 映像在 Surface 设备上注册、配置和取消注册 SEMM。

这些包包含指定 UEFI 设置的配置文件。 SEMM 包还包含安装并存储在固件中的证书，用于在应用 UEFI 设置之前验证配置文件的签名。

>[!TIP]
>现在可以使用 Surface UEFI 配置器和 SEMM 管理 Surface Dock 2 上的端口。 若要了解详细信息，请参阅 [使用 SEMM 的安全 Surface Dock 2 端口](secure-surface-dock-ports-semm.md)。

![Microsoft Surface UEFI 配置器。](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*图 1. Microsoft Surface UEFI 配置器*

可以在三种模式下使用 Microsoft Surface UEFI 配置器工具：

- [Surface UEFI 配置包](#configuration-package)。 使用此模式创建 Surface UEFI 配置包，以在 SEMM 中注册 Surface 设备，并在已注册的设备上配置 UEFI 设置。
- [Surface UEFI 重置包](#reset-package)。 使用此模式从 SEMM 取消注册 Surface 设备。
- [Surface UEFI 恢复请求](#recovery-request)。 使用此模式响应恢复请求，以便从重置包操作不成功的 SEMM 取消注册 Surface 设备。

### <a name="download-microsoft-surface-uefi-configurator"></a>下载 Microsoft Surface UEFI 配置器

可以从 Microsoft 下载中心的 [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) 页面下载 Microsoft Surface UEFI 配置器。

- 对于 Intel/AMD 设备，请下载： **SurfaceUEFI_Configurator_v2.94.139.0_x64.msi**
- 对于 ARM 设备，请下载： **SurfaceUEFI_Configurator_v2.94.139.0_x86.msi。**

### <a name="configuration-package"></a>配置包

Surface UEFI 配置包是实现和管理 Surface 设备上的 SEMM 的主要机制。 这些包包含配置文件和证书文件，如图 2 所示。 配置文件包含在 Microsoft Surface UEFI 配置器中创建包时指定的 UEFI 设置。 当配置包首次在尚未在 SEMM 中注册的 Surface 设备上运行时，它会在设备的固件中预配证书文件并在 SEMM 中注册该设备。 在 SEMM 中注册设备时，以及在证书存储和注册完成之前，系统会提示你通过提供 SEMM 证书指纹的最后两位数字来确认操作。 此确认要求用户在注册期间在设备上实际存在以执行确认。

![使用证书保护 SEMM 配置包。](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*图 2. 使用证书保护 SEMM 配置包*

有关 SEMM 证书要求的详细信息，请参阅本文后面的 [Surface Enterprise管理模式证书要求](#surface-enterprise-management-mode-certificate-requirements)部分。

>[!TIP]
>可以选择使用 SEMM 要求使用 UEFI 密码。 如果这样做，则需要密码才能查看 Surface UEFI **的安全**性、**设备**、**启动配置**和**Enterprise管理**页。

在 SEMM 中注册设备后，将读取配置文件，并在文件中指定的设置应用于 UEFI。 在已在 SEMM 中注册的设备上运行配置包时，会根据存储在设备固件中的证书检查配置文件的签名。 如果签名不匹配，则不会对设备应用任何更改。

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a>使用 SEMM 在 Surface UEFI 中启用或禁用设备

以下列表显示可以在 SEMM 中管理的所有可用设备：

- 停靠 USB 端口
- 载入式音频
- 数字图形处理单元
- 类型封面
- 微 SD 卡
- 前置摄像头
- 后置相机
- 用于Windows Hello) 的红外相机 (
- 仅蓝牙
- 无线网络和蓝牙
- LTE)  (长期演变

 >[!NOTE]
>在"UEFI 设备"页上，内置设备可能会有所不同，具体取决于设备或公司环境。 例如，Surface Pro X 上不支持 UEFI 设备页;LTE 仅出现在装有 LTE 的设备上。

### <a name="configure-advanced-settings-with-semm"></a>使用 SEMM 配置高级设置

**表 1. 高级设置**

| 设置                            | 描述                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 用于 PXE 启动的 IPv6                  | 允许你管理对 PXE 启动的 IPv6 支持。 如果不配置此设置，将禁用对 PXE 启动的 IPv6 支持。                                                                               |
| 备用启动                     | 通过在启动期间按"下卷"按钮和"电源"按钮，可以管理备用启动订单的使用，以直接启动到 USB 或以太网设备。 如果未配置此设置，则启用备用启动。 |
| 启动顺序锁                    | 允许锁定启动顺序以防止更改。 如果未配置此设置，将禁用启动订单锁定。                                                                                                        |
| USB 启动                           | 允许你管理到 USB 设备的启动。 如果未配置此设置，则会启用 USB 启动。                                                                                                                 |
| 网络堆栈                      | 允许你管理网络堆栈启动设置。 如果未配置此设置，则会禁用管理网络堆栈启动设置的功能。                                                                                                           |
| 自动打开电源                      | 允许你管理自动启用启动设置。 如果未配置此设置，则启用自动启用电源。                                                                                                        |
| 同步多线程 (SMT)  | 允许管理同步多线程 (SMT) 以启用或禁用超线程。 如果未配置此设置，则启用 SMT。                                                  |
|启用电池限制| 允许你管理电池限制功能。 如果未配置此设置，则启用电池限制 |
| 安全性                           | 显示 Surface UEFI **安全** 页。 如果未配置此设置，则会显示"安全"页。                                                                                                                 |
| 设备                            | 显示 Surface UEFI **设备** 页。 如果未配置此设置，则会显示"设备"页。                                                                                                                     |
| 靴子                               | 显示 Surface UEFI **启动** 页。 如果未配置此设置，则会显示"启动"页。                                                                                                                                                            |
| DateTime                           | 显示 Surface UEFI **DateTime** 页面。 如果未配置此设置，则会显示 DateTime 页面。                                                                                                                |
| EnableOSMigration                          | 允许将 Surface Hub 2 从Windows 10 协同版迁移到 Windows 10/11 Pro或Enterprise。 如果未配置此设置，Surface Hub 2 台设备只能运行Windows 10 协同版 OS。 注意：Windows 10 协同版和Windows 10/11 Pro/Enterprise之间的双重启动在 Surface Hub 2 上不可用。                                                                                                           |

>[!TIP]
>创建 SEMM 配置包时，" **成功** "页上会显示两个字符，如图 3 所示。

![证书指纹显示。](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*图 3. 在"成功"页上显示证书指纹的最后两个字符*

这些字符是证书指纹的最后两个字符，应记下或记录。 在 Surface 设备上确认 SEMM 中的注册需要字符，如图 4 所示。

![SEMM 中的注册确认。](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*图 4. 使用 SEMM 证书指纹在 SEMM 中注册确认*

>[!TIP]
>有权访问证书文件 (.pfx) 管理员可以通过在 CertMgr 中打开 .pfx 文件随时读取指纹。 若要使用 CertMgr 查看指纹，请执行以下操作：
>
>1. 选择并按住 (或右键单击 .pfx 文件) ，然后选择 **"打开**"。
>2. 在导航窗格中，展开文件夹。
>3. 选择 **"证书**"。
>4. 在主窗格中，选择并按住 (或右键单击证书) ，然后选择 **"打开**"。
>5. 选择" **详细信息"** 选项卡。
>6. 在 **"显示**"下拉菜单中，必须**选择"全部"或"仅限属性**"。 ****
>7. 选择 **"指纹"** 字段。

若要在 SEMM 中注册 Surface 设备或从配置包应用 UEFI 配置，请在预期的 Surface 设备上运行具有管理权限的.msi文件。 可以使用应用程序部署或操作系统部署技术，例如[Microsoft Endpoint Configuration Manager](/mem/configmgr)或 [Microsoft 部署Toolkit](/mem/configmgr/mdt)。 在 SEMM 中注册设备时，必须实际存在才能确认设备上的注册。 将配置应用到已在 SEMM 中注册的设备时，不需要用户交互。

有关如何在 SEMM 中注册 Surface 设备或使用 SEMM 应用 Surface UEFI 配置的分步演练，请参阅 [使用 SEMM 注册和配置 Surface 设备](enroll-and-configure-surface-devices-with-semm.md)。

### <a name="reset-package"></a>重置包

Surface UEFI 重置包仅用于执行一项任务 - 从 SEMM 取消注册 Surface 设备。 重置包包含已签名的说明，用于从设备固件中删除 SEMM 证书，并将 UEFI 设置重置为出厂默认设置。 与 Surface UEFI 配置包一样，重置包必须使用 Surface 设备上预配的相同 SEMM 证书进行签名。 创建 SEMM 重置包时，需要提供要重置的 Surface 设备的序列号。 SEMM 重置包不是通用的， 它们特定于一个设备。

### <a name="recovery-request"></a>恢复请求

在某些情况下，可能无法使用 Surface UEFI 重置包。  (例如，如果 Surface 设备上Windows不可用。) 在这些情况下，可以通过 Surface UEFI **Enterprise (** 图 5 中所示的 Surface UEFI (页取消注册 Surface 设备。) 使用恢复请求操作。

> [!div class="mx-imgBorder"]
> ![启动 SEMM 恢复请求。](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*图 5. 在"Enterprise管理"页上启动 SEMM 恢复请求*

在**Enterprise管理**页上使用此过程在 Surface 设备上重置 SEMM 时，系统会收到重置请求。 此重置请求可以作为文件保存到 USB 驱动器，复制为文本，或使用移动设备读取为 QR 代码，以便轻松通过电子邮件或发送消息。 使用 Microsoft Surface UEFI 配置器重置请求选项加载重置请求文件或输入重置请求文本或 QR 代码。 Microsoft Surface UEFI 配置器生成可在 Surface 设备上输入的验证码。 如果在 Surface 设备上输入代码并选择 **"重启**"，则会从 SEMM 取消注册设备。

>[!NOTE]
>重置请求在创建两小时后过期。

有关如何从 SEMM 取消注册 Surface 设备的分步演练，请参阅 [SEMM 取消注册 Surface 设备](unenroll-surface-devices-from-semm.md)。

## <a name="surface-enterprise-management-mode-certificate-requirements"></a>Surface Enterprise管理模式证书要求

将 SEMM 与 Microsoft Surface UEFI 配置器配合使用并想要应用 UEFI 设置时，需要证书来验证配置文件的签名。 此证书可确保在设备注册 SEMM 后，只能使用使用已批准证书创建的包来修改 UEFI 设置。

>[!NOTE]
>若要对已注册的 Surface 设备上的 SEMM 或 Surface UEFI 设置进行任何修改，需要 SEMM 证书。 如果 SEMM 证书损坏或丢失，则无法删除或重置 SEMM。 使用适当的备份和恢复解决方案相应地管理 SEMM 证书

使用 Microsoft Surface UEFI 配置器工具创建的包使用证书进行签名。 此证书可确保在 SEMM 中注册设备后，只能使用使用已批准证书创建的包来修改 UEFI 的设置。

### <a name="recommended-certificate-settings"></a>建议的证书设置

对于 SEMM 证书，建议使用以下设置：

- **密钥算法** - RSA
- **密钥长度** - 2048
- **哈希算法** - SHA-256
- **类型** - SSL 服务器身份验证
- **密钥用法** – 数字签名、密钥加密
- **提供程序** - Microsoft 增强的 RSA 和 AES 加密提供程序
- **到期日期** - 证书创建后的 15 个月
- **密钥导出策略** – 可导出

还建议在两层公钥基础结构 (PKI) 体系结构中对 SEMM 证书进行身份验证，其中中间证书颁发机构 (CA) 专用于 SEMM，从而启用证书吊销。 有关双层 PKI 配置的详细信息，请参阅 [测试实验室指南：部署 AD CS Two-Tier PKI 层次结构](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831348(v=ws.11))。

### <a name="self-signed-certificate"></a>自签名证书

可以使用以下示例 PowerShell 脚本创建自签名证书，以便在概念证明方案中使用。
若要使用此脚本，请将以下文本复制到记事本，然后将文件另存为 PowerShell 脚本 (.ps1) 。

> [!NOTE]
> 此脚本创建密码为 >a0/a0> 的 `12345678`证书。 不建议针对生产环境使用此脚本生成的证书。
  
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
>若要与 SEMM 和 Microsoft Surface UEFI 配置器一起使用，必须使用私钥和密码保护导出证书。 Microsoft Surface UEFI 配置器提示你选择 SEMM 证书文件 (.pfx) 和证书密码。

若要创建自签名证书，请执行以下操作：

1. 在 C：驱动器上，创建要在其中保存脚本的文件夹;例如，C：\SEMM。
2. 将示例脚本复制到记事本 (或等效文本编辑器) ，然后将文件另存为 PowerShell 脚本 (.ps1) 。
3. 使用管理员凭据登录到计算机，然后打开提升的 PowerShell 会话。
4. 确保将权限设置为允许运行脚本。 默认情况下，除非修改执行策略，否则脚本将被阻止运行。 若要了解详细信息， [请参阅"关于执行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)"。
5. 在命令提示符下，输入脚本的完整路径，然后按 **Enter**。 该脚本创建名为 TempOwner.pfx 的演示证书。

或者，可以使用 PowerShell 创建自己的自签名证书。 有关详细信息，请参阅 [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate)。

>[!NOTE]
>对于在其 PKI 基础结构中使用脱机根的组织，必须在连接到根 CA 的环境中运行 Microsoft Surface UEFI 配置器以对 SEMM 证书进行身份验证。 Microsoft Surface UEFI 配置器生成的包可以作为文件传输，因此可以使用可移动存储（如 USB 摇杆）在脱机网络环境外部传输它们。

### <a name="managing-certificates-faq"></a>管理证书常见问题解答

建议 *的最小* 长度为 15 个月。 可以使用在 15 个月内过期的证书，或使用超过 15 个月的过期证书。

>[!NOTE]
>证书过期时，不会自动续订。

**过期的证书是否会影响已注册 SEMM 的设备的功能？**<br><br>
否，证书仅影响 SEMM 中的 IT 管理员管理任务，过期时对设备功能没有影响。

**是否需要在拥有 SEMM 包和证书的所有计算机上更新 SEMM 包和证书？**<br><br>
如果希望 SEMM 重置或恢复有效，则证书必须有效且未过期。

**是否可以为我们订购的每个图面创建批量重置包？ 可以生成一个可重置环境中所有计算机的计算机吗？**<br><br>
为特定设备类型创建配置包的 PowerShell 示例还可用于创建与序列号无关的重置包。 如果证书仍然有效，则可以使用 PowerShell 创建重置包以重置 SEMM。

## <a name="version-history"></a>版本历史记录

### <a name="version-2941390"></a>版本 2.94.139.0

此版本的 SEMM 包括：

- 支持 Surface Laptop Studio、Surface Pro 8 和 Surface Go 3

### <a name="version-2831390"></a>版本 2.83.139.0

此版本的 SEMM 包括：

- 支持Surface Laptop 4
- 支持Surface Pro 7 的同步多线程选项
- 删除过时的 SEMM 设置  
- 改进了 MSI 签名

### <a name="version-2791390"></a>版本 2.79.139.0

此版本的 SEMM 包括：

- 支持Surface Pro 7+。
- 用户体验改进。

### <a name="version-2781390"></a>版本 2.78.139.0

此版本的 SEMM 包括：

- 支持 Surface Laptop Go 和 Surface Pro X。
- 新版本版本的通知。
- 创建自定义包以更改所有权的能力。
- Bug 修复。

### <a name="version-2731360"></a>版本 2.73.136.0

此版本的 SEMM 包括：

- 使用 SEMM 在 Surface Hub2S 上禁用音频的功能。
- 支持 Surface Pro X for Dock 2。
- 支持 UEFI Manager 进行与 Dock 2 相关的操作。
- Surface Go 重置包 bug 修复。
- 支持将 Surface Hub 2 台设备从Windows 10 协同版 OS 迁移到Windows 10 专业版或Enterprise。

### <a name="version-2711390"></a>版本 2.71.139.0

此版本的 SEMM 为 Surface Book 3、Surface Laptop 3 和 Surface Pro 7 添加了对 Surface Dock 2 管理功能的支持。 其中包括：

- 启用音频 (锁定/解锁) 以及以太网和 USB 端口的功能。
- 能够为经过身份验证的主机和未经身份验证的主机创建停靠包。

### <a name="version-2701300"></a>版本 2.70.130.0

此版本的 SEMM 包括：

- 支持 Surface Go 2。
- 支持Surface Book 3。
- Bug 修复。

### <a name="version-2591390"></a>版本 2.59.139.0

此版本的 SEMM 包括：

- 支持使用 Intel 处理器Surface Pro 7、Surface Pro X 和 Surface Laptop 3 13.5"和 15" 模型。
    >[!NOTE]
    >Surface Laptop 3 15" AMD 处理器不受支持。
- 支持"唤醒 Power"功能。

### <a name="version-2541390"></a>版本 2.54.139.0

此版本的 SEMM 包括：

- 支持Surface Hub 2S。
- Bug 修复。

### <a name="version-2431360"></a>版本 2.43.136.0

此版本的 SEMM 包括：

- 支持启用/禁用同时进行多线程处理。
- 适用于某些设备的无线网络和蓝牙的单独选项。
- 为Surface Studio删除了电池限制。

### <a name="version-2261360"></a>版本 2.26.136.0

此版本的 SEMM 包括：

- 支持Surface Studio 2。
- 电池限制功能。

### <a name="version-2211360"></a>版本 2.21.136.0

此版本的 SEMM 包括：

- 支持Surface Pro 6。
- 支持Surface Laptop 2。

### <a name="version-2141360"></a>版本 2.14.136.0

此版本的 SEMM 包括：

- 支持 Surface Go。

### <a name="version-291360"></a>版本 2.9.136.0

此版本的 SEMM 包括：

- 支持Surface Book 2。
- 支持Surface Pro LTE。
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

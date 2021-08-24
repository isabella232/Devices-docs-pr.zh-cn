---
title: '使用 Surface Enterprise 管理模式的安全 Surface 扩展坞 2 端口 (SEMM) '
description: 本文档提供有关在连接到兼容的 Surface 设备（包括 Surface Book 3、Surface Laptop 3 和 Surface Pro 7）时为 Surface Dock 2 配置 UEFI 端口设置的指导。
ms.assetid: 2808a8be-e2d4-4cb6-bd53-9d10c0d3e1d6
ms.reviewer: ''
manager: laurawi
keywords: 常见问题、设置问题疑难解答
ms.prod: w10
ms.mktglfcycl: support
ms.sitesec: library
ms.pagetype: surfacehub
author: v-miegge
ms.author: jesko
ms.topic: article
ms.date: 08/02/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: a6b1dcdb3cf0ff8fe2f6485520c6b6301f5d2b2f
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911997"
---
# <a name="secure-surface-dock-2-ports-with-surface-enterprise-management-mode-semm"></a>使用 Surface Enterprise 管理模式的安全 Surface 扩展坞 2 端口 (SEMM) 

## <a name="introduction"></a>简介

Surface Enterprise 管理模式 (SEMM) 使 IT 管理员能够保护和管理 Surface Dock 2 端口，方法为在部署到企业环境中兼容的 Surface 设备的 Windows 安装程序配置包 (.msi 文件) 中配置 UEFI 设置。

### <a name="supported-devices"></a>支持的设备

使用 SEMM 管理 Surface 扩展坞 2 适用于连接到 Surface Book 3、Surface Laptop 4、Surface Laptop 3、Surface Laptop Go、Surface Pro 7+、Surface Pro 7 和 Surface Pro X 的扩展坞。这些兼容的 Surface 设备通常称为**主机设备**。 程序包根据主机设备是否经过身份验证或未经身份验证而应用于**主机设备**。 **** 配置的设置驻留在主机设备的 UEFI 层，使 IT 管理员能够像管理任何其他内置外围设备（如相机）一样管理 Surface Dock 2。

>[!NOTE]
>只有当该扩展坞连接到以下兼容设备之一时，才能管理 Surface Dock 2 端口：Surface Book 3、Surface Laptop 4、Surface Laptop 3、Surface Pro 7+和 Surface Pro 7。 任何未接收 UEFI 身份验证策略设置的设备本质上都是未经身份验证的设备。

### <a name="scenarios"></a>方案

将 Surface Dock 2 限制为登录到公司主机设备的授权人员可提供另一层数据保护。 这种锁定 Surface 扩展坞 2 的功能对于高度安全的环境中的特定客户至关重要，这些客户需要扩展坞的功能和工作效率优势，同时维持严格的安全协议合规性。 我们预计与 Surface 扩展坞 2 一起使用的 SEMM 在开放式办公室和共享空间中将特别有用，特别是对于出于安全原因需要锁定 USB 端口的客户。 有关视频演示，请查看适用于[Surface Dock 2 的 SEMM。](https://youtu.be/VLV19ISvq_s)

## <a name="configuring-and-deploying-uefi-settings-for-surface-dock-2"></a>配置和部署 Surface Dock 2 的 UEFI 设置

本节提供以下任务的分步指南：

1. 从适用于 IT 的 Surface Tools 安装 **Surface UEFI** [配置器](https://www.microsoft.com/download/details.aspx?id=46703)。
1. 创建或获取公钥证书。
1. 创建.msi配置包。
   1. 添加证书。
   1. 输入 Surface Dock 2 设备的 16 位 RN 号码。
   1. 配置 UEFI 设置。
1. 生成配置包，并应用到 7. (Surface Book 3、Surface Laptop 3 或 Surface Pro 7.) 

>[!NOTE]
>随机 **数字 (RN) ** 是一个唯一的 16 位十六进制代码标识符，该标识符在工厂中设置，在扩展坞的下面以小字体打印。 RN 与大多数序列号的一个区别是，它不能通过电子方式读取。 这可确保主要仅在以物理形式访问设备时读取 RN 来建立所有权证明。 还可以在购买交易期间获取 RN，并记录在 Microsoft 库存系统中。

### <a name="install-semm-and-surface-uefi-configurator"></a>安装 SEMM 和 Surface UEFI 配置器

通过运行系统安装 ** SEMMSurfaceUEFI_Configurator_v2.83.139.0.msi。** 这是一个独立的安装程序，包含为 Surface Dock 2 创建和分发配置包所需的一切内容。

- 从适用于 IT 的 Surface 工具下载 **Surface UEFI** [配置器](https://www.microsoft.com/download/details.aspx?id=46703)。

## <a name="create-public-key-certificates"></a>创建公钥证书

本部分提供用于创建管理 Surface 扩展坞 2 的端口所需的证书的规范。

### <a name="prerequisites"></a>系统必备

本文假定你要么从第三方提供商获取证书，要么你已经具有 PKI 证书服务方面的专业知识，并且知道如何创建自己的证书。  你应该熟悉并按照[Surface Enterprise Management Mode (SEMM](surface-enterprise-management-mode.md)) 中所述创建证书的一般建议，但一个例外。 此页上记录证书需要扩展坞证书颁发机构过期期限为 30**** 年，主机身份验证证书的有效期为 20**年**。

有关详细信息，请参阅证书服务[体系结构](/windows/win32/seccrypto/certificate-services-architecture)文档并查看[Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)或 Windows Server [2008 PKI](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)和 Microsoft Press 提供的证书安全性中的相应章节。

### <a name="root-and-host-certificate-requirements"></a>根证书和主机证书要求

在创建配置包之前，你需要准备公钥证书，以验证 Surface Dock 2 的所有权，并加快设备生命周期内所有权的任何后续更改。 主机和预配证书需要输入 EKU ID，也称为客户端身份验证增强型密钥使用 (EKU) 对象标识符 (**OIDs) **。

表 1 和表 2 中列出了所需的 EKU 值。

#### <a name="table-1-root-and-dock-certificate-requirements"></a>表 1. 根证书和扩展坞证书要求

|证书|算法|描述|到期|EKU OID|
|---|---|---|---|---|
|根证书颁发机构|ECDSA_P384|- 使用 384 位主要省略号曲线数字签名算法的根证书 (ECDSA) <br>- SHA 256 密钥用法：<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>- CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30 年|不适用
|扩展坞证书颁发机构|ECC P256 曲线|- 具有 256 位省略号曲线加密的主机证书 (ECC) <br>- SHA 256 密钥用法：<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>- 路径长度约束 = 0|20 年|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >扩展坞 CA 必须导出为 .p7b 文件。

### <a name="provisioning-administration-certificate-requirements"></a>设置管理证书要求

每台主机设备必须具有文档 CA 和两个证书，如表 2 所示。

#### <a name="table-2-provisioning-administration-certificate-requirements"></a>表 2.  设置管理证书要求

|证书|算法|描述|EKU OID|
|---|---|---|---|
|主机身份验证证书|ECC P256<br>SHA 256|证明主机设备的标识。|1.3.6.1.4.1.311.76.9.21.2|
|设置管理证书|ECC P256<br>SHA256|通过允许替换当前安装在扩展坞上的 CA，可以更改扩展坞所有权和/或策略设置。|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >主机身份验证和设置证书必须导出为 .pfx 文件。

### <a name="create-configuration-package"></a>创建配置包

获取或创建证书后，你已准备好生成将应用于.msi Surface 设备的设备配置包。

1. 运行 Surface **UEFI 配置器**。

   ![运行 Surface UEFI 配置器。](images/secure-surface-dock-ports-semm-1.png)

1. 选择 **Surface 扩展坞**。

   ![选择 Surface 扩展坞。](images/secure-surface-dock-ports-semm-2.png)

1. 在证书 **页面上**  输入相应的证书。 演示证书可从 [Surface Tools for IT：](https://www.microsoft.com/download/details.aspx?id=46703)Download **SEMM_PowerShell.zip** and refer to **CreateSurfaceDock2Certificates.ps1**. 在运行演示 **脚本SurfaceDock2_WmiInstanceProvider** 安装此脚本。

   ![输入相应的证书。](images/secure-surface-dock-ports-semm-3.png)

1. 将相应的扩展坞 NS 添加到列表中。

   >[!TIP]
   >为多个 Surface Dock 2 设备创建配置包时，可以使用包含 RN 列表的 .csv 文件，而不是手动输入每个 RN。

1. 指定 USB 数据、以太网和音频端口的策略设置。 UEFI 配置器允许你为通过身份验证 (策略) 身份验证的用户和未经身份验证 (用户配置策略) 。 下图显示了为经过身份验证的用户打开的端口访问，并且为未经身份验证的用户关闭端口访问。

   ![选择要激活或停用的组件。](images/secure-surface-dock-ports-semm-4.png)

   - 经过身份验证的用户指的是安装了相应证书的 Surface 设备，.msi应用到目标设备的配置包中配置。 它适用于登录设备的任何经过用户身份验证的用户。
   - 未经身份验证的用户是指任何其他设备。
   - 选择 **"** 重置"以创建一个特殊的"重置"程序包，该程序包将删除扩展坞接受的任何以前的配置包。

1. 选择 **"生成** "以按指定创建程序包。

### <a name="apply-the-configuration-package-to-a-surface-dock-2"></a>将配置包应用到 Surface Dock 2

1. 使用.msi Surface UEFI 配置器生成的文件，并安装在 Surface 主机设备上。 兼容的主机设备Surface Book 3、Surface Laptop 3 或 Surface Pro 7。
1. 连接设备连接到 Surface 扩展坞 2。 连接扩展坞时，将应用 UEFI 策略设置。

## <a name="verify-managed-state-using-the-surface-app"></a>使用 Surface App 验证托管状态

应用配置包后，你可以直接从 Surface 应用（默认情况下在所有 Surface 设备上安装）快速验证扩展坞的结果策略状态。 如果 Surface App 不在设备上，你可以从设备下载并Microsoft Store。

### <a name="test-scenario"></a>测试方案

目标：配置策略设置以仅允许经过身份验证的用户访问端口。

1. 为经过身份验证的用户打开所有端口，然后为未经身份验证的用户关闭这些端口。

   ![为经过身份验证的用户启用端口。](images/secure-surface-dock-ports-semm-4.png)

1. 将配置包应用到目标设备，然后连接 Surface Dock 2。

1. 打开 **Surface 应用** ，然后选择 Surface **扩展** 坞以查看 Surface 扩展坞的结果策略状态。 如果应用了策略设置，Surface App 将指示端口可用。

   ![Surface 应用显示所有端口均可供经过身份验证的用户使用。](images/secure-surface-dock-ports-semm-5.png)

1. 现在您需要验证策略设置是否成功关闭未经身份验证的用户的所有端口。 连接Surface Dock 2 到非托管设备，即任何超出所创建配置包管理范围的 Surface 设备。

1. 打开 **Surface 应用，** 然后选择 **Surface 扩展坞**。 结果策略状态将指示端口已关闭。

   ![显示为未经身份验证的用户关闭的端口的 Surface 应用。](images/secure-surface-dock-ports-semm-6.png)

>[!TIP]
>如果你想要保留设备的所有权，但允许所有用户完全访问，你可以制作一个打开所有内容的新程序包。 如果你想要完全删除设备 (使其非托管) ，请选择 Surface UEFI 配置器中的重置以创建要应用于目标**** 设备的程序包。

恭喜。 你已成功在目标主机设备上管理 Surface Dock 2 端口。

## <a name="learn-more"></a>了解详细信息

- [Surface Enterprise 管理模式 (SEMM) 文档](surface-enterprise-management-mode.md)
- [证书服务体系结构](/windows/win32/seccrypto/certificate-services-architecture)
- [Windows服务器 2019 内部](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [WindowsServer 2008 PKI 和证书安全性](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)

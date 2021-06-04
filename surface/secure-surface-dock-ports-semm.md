---
title: '安全 Surface Dock 2 个具有 Surface Enterprise 管理模式的端口 (SEMM) '
description: 本文档提供了在连接到兼容的 Surface 设备（包括 Surface Book 3、Surface 笔记本3和 Surface Pro 7）的情况下配置 Surface Dock 2 的 UEFI 端口设置的指南。
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
ms.date: 06/08/2020
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 641d023b59426582130dcfb7e0d86c6f3af456e8
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114690"
---
# 安全 Surface Dock 2 个具有 Surface Enterprise 管理模式的端口 (SEMM) 

##  <a name="introduction"></a>简介

Surface Enterprise 管理模式 (SEMM) 使 IT 管理员可以通过在 Windows 安装程序配置包 ( 中配置 UEFI 设置来保护和管理 Surface Dock 2 端口。MSI 文件) 在企业环境中部署到兼容的 Surface 设备。

###  <a name="supported-devices"></a>支持的设备

使用 SEMM 管理 Surface Dock 2 适用于连接到 Surface Book 3、Surface 笔记本电脑3、Surface 笔记本电脑 Go、Surface Pro 7 和 Surface Pro X 的坞站。这些兼容的 Surface 设备通常称为 **主机设备**。 根据主机设备是否 **经过身份验证** 或 **未经身份**验证，将程序包应用于主机设备。 已配置的设置驻留在主机设备上的 UEFI 层中，使你（IT 管理员）可以管理 Surface Dock 2，就像任何其他内置外围设备（如相机）一样。

>[!NOTE]
>只有当插接连接到以下兼容设备之一时，才能管理 Surface Dock 2 端口： Surface Book 3、Surface 笔记本3和 Surface Pro 7。 任何未接收到 UEFI 身份验证策略设置的设备本身就是未经身份验证的设备。

###  <a name="scenarios"></a>方案

对登录到企业主机设备的授权人员限制 Surface Dock 2，提供另一层数据保护。 这种锁定 Surface Dock 2 的能力对于高度安全的环境中的特定客户非常重要，这些客户希望在保持遵守严格的安全协议的同时获得固定的功能和生产力。 我们预计使用 Surface Dock 的 SEMM 在开放办公和共享空间中尤其有用，特别是出于安全原因希望锁定 USB 端口的客户。 对于视频演示，请查看 [Surface Dock 2 的 SEMM](https://youtu.be/VLV19ISvq_s)。

##  <a name="configuring-and-deploying-uefi-settings-for-surface-dock-2"></a>配置和部署 Surface Dock 的 UEFI 设置2

本部分提供以下任务的分步指南：

1. 安装 [**SURFACE UEFI 配置**](https://www.microsoft.com/download/details.aspx?id=46703)器。
1. 创建或获取公钥证书。
1. 创建。MSI 配置程序包。
   1. 添加您的证书。
   1. 输入 Surface Dock 2 设备的16位 RN 号码。
   1. 配置 UEFI 设置。
1. 构建配置包并将其应用到目标 Surface 设备 (Surface Book 3、Surface 笔记本电脑3或 Surface Pro 7。 ) 

>[!NOTE]
>** (RN) 的随机数字**是一个唯一的16位十六进制代码标识符，在工厂预配，并且在 dock 的底部以较小的类型打印。 RN 与大多数序列号不同，因为它无法以电子方式读取。 这确保了所有权证明主要是通过在物理上访问设备时读取 RN 来确定的。 RN 也可以在购买交易期间获取，并记录在 Microsoft 库存系统中。

###  <a name="install-semm-and-surface-uefi-configurator"></a>安装 SEMM 和 Surface UEFI 配置器

通过运行 **SurfaceUEFI_Configurator_v2.71.139.0.msi**安装 SEMM。 这是一个独立安装程序，包含创建和分发 Surface Dock 2 的配置包所需的所有内容。

- 从[Surface Tools FOR IT](https://www.microsoft.com/en-us/download/details.aspx?id=46703)下载**surface UEFI 配置**器。

##  <a name="create-public-key-certificates"></a>创建公钥证书

本部分提供了创建管理 Surface Dock 的端口所需证书的规范。

###  <a name="prerequisites"></a>必备条件

本文假定你从第三方提供商获取证书，或者你已经拥有 PKI 证书服务的专业知识，并知道如何创建自己的证书。  你应该熟悉并按照 [图面企业管理模式 (SEMM) ](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 文档中所述的常规建议创建证书，但有一个例外。 此页面上记录的证书要求为 **Dock 证书颁发机构**提供30年的有效期，以及用于 **主机身份验证证书**的20年。

有关详细信息，请参阅 [证书服务体系结构](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) 文档，并在 [windows server 2019 中查看 windows server](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)中的相应章节，以及 Microsoft 新闻可用的 [Windows Server 2008 PKI 和证书安全](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) 。

###  <a name="root-and-host-certificate-requirements"></a>根和主机证书要求

在创建配置程序包之前，你需要准备验证 Surface Dock 的所有权的公钥证书，并在设备生命周期内帮助所有权的任何后续更改。 主机和预配证书需要输入 EKU Id （也称为 **客户端身份验证增强密钥用法）， (EKU) 对象标识符 (oid) **。

表1和表2中列出了所需的 EKU 值。

####  <a name="surface-hub-2-fingerprint-reader-tech-specs"></a>表 1.  根和插接证书要求

|证书|算法|描述|到期|EKU OID|
|---|---|---|---|---|
|根证书颁发机构|ECDSA_P384|-具有384位质数椭圆曲线数字签名算法 (ECDSA) 的根证书<br>-SHA 256 密钥用法：<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>-CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30年|不适用
|插接证书颁发机构|ECC P256 曲线|-具有256位椭圆曲线加密 (ECC) 的主机证书<br>-SHA 256 密钥用法：<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>-路径长度约束 = 0|20年|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >必须将 dock CA 导出为 p7b 文件。

###  <a name="provisioning-administration-certificate-requirements"></a>预配管理证书要求

每台主机设备都必须具有 doc CA 和两个证书，如表2中所示。

#### 表 2.  预配管理证书要求

|证书|算法|描述|EKU OID|
|---|---|---|---|
|主机身份验证证书|ECC P256<br>SHA 256|证明主机设备的身份。|1.3.6.1.4.1.311.76.9.21.2|
|预配管理证书|ECC P256<br>SHA256|使你可以通过允许替换当前安装在 dock 上的 CA 来更改 dock 所有权和/或策略设置。|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >必须以 .pfx 文件的形式导出主机身份验证和预配证书。

###  <a name="create-configuration-package"></a>创建配置包

获取或创建证书后，即可创建将应用于目标 Surface 设备的 MSI 配置包。

1. 运行 Surface **UEFI 配置**器。

   ![运行 Surface UEFI 配置器](images/secure-surface-dock-ports-semm-1.png)

1. 选择 " **Surface Dock**"。

   ![选择 Surface Dock](images/secure-surface-dock-ports-semm-2.png)

1. 在 "证书" 页面上，输入相应的 **证书**。

   ![输入相应的证书](images/secure-surface-dock-ports-semm-3.png)

1. 将相应的 dock RNs 添加到列表中。

   >[!NOTE]
   >为多个 Surface Dock 2 设备创建配置包时，不必手动输入每个 RN，而是可以使用包含 RNs 列表的 .csv 文件。

1. 为 USB 数据、以太网和音频端口指定策略设置。 UEFI 配置器允许你为已验证身份的 (用户配置策略设置) 和未经身份验证的用户 (未验证的策略) 。 下图显示了为经过身份验证的用户打开的端口访问和为未经授权的用户关闭的端口访问。

   ![选择要激活或停用的组件。](images/secure-surface-dock-ports-semm-4.png)

   - 经身份验证的用户指安装了相应证书的 Surface 设备，如中所述。您应用到目标设备的 MSI 配置程序包。 它适用于登录设备的任何用户已验证用户。 
   - 未经身份验证的用户指任何其他设备。
   - 选择 " **重置** " 以创建特殊的 "reset" 程序包，该程序包将删除任何以前已接受的任何以前配置的程序包。

1. 选择 " **生成** " 以创建指定的程序包。

###  <a name="apply-the-configuration-package-to-a-surface-dock-2"></a>将配置包应用于 Surface Dock 2

1. 获取 Surface UEFI 配置器生成的 MSI 文件，并将其安装在 Surface host 设备上。 兼容的主机设备是 Surface Book 3、Surface 笔记本3或 Surface Pro 7。
1. 将主机设备连接到 Surface Dock 2。 当你连接时，将应用停靠的 UEFI 策略设置。

##  <a name="verify-managed-state-using-the-surface-app"></a>使用 Surface App 验证托管状态

应用配置包后，您可以直接从 Surface App （默认情况下在所有 Surface 设备上安装）快速验证 dock 的最终策略状态。 如果设备上不存在 Surface 应用，则可以从 Microsoft Store 下载并安装它。

###  <a name="test-scenario"></a>测试方案

目标：将策略设置配置为仅允许经过身份验证的用户访问端口。

1. 为经过身份验证的用户打开所有端口，并为未经身份验证的用户关闭它们。

   ![为经过身份验证的用户启用端口](images/secure-surface-dock-ports-semm-4.png)

1. 将配置包应用到目标设备，然后连接 Surface Dock 2。

1. 打开 **Surface App** ，然后选择 " **surface dock** " 以查看 surface dock 的最终策略状态。 如果应用了策略设置，Surface App 将指示端口可用。

   ![Surface app 显示所有端口均可用于经过身份验证的用户](images/secure-surface-dock-ports-semm-5.png)

1. 现在，你需要验证策略设置是否已成功为未经身份验证的用户关闭所有端口。 将 Surface Dock 2 连接到非托管设备，即你创建的配置包的管理范围之外的任何 Surface 设备。

1. "打开 **surface" 应用** ，然后选择 " **surface Dock**"。 结果策略状态将指示端口已关闭。

   ![显示未经身份验证的用户关闭端口的 Surface 应用 ](images/secure-surface-dock-ports-semm-6.png)

>[!NOTE]
>如果你想要保留设备的所有权，但允许所有用户拥有完全访问权限，你可以创建一个新的程序包，其中所有内容均已打开。 如果你希望完全删除设备的限制和所有权 (使其非托管) ，请在 Surface UEFI 配置器中选择 " **重置** " 以创建要应用到目标设备的程序包。

得到. 你已在目标主机设备上成功管理 Surface Dock 2 端口。

##  <a name="learn-more"></a>了解详细信息

- [ (SEMM) 文档的 Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
- [证书服务体系结构](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Server 2019 内部](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Windows Server 2008 PKI 和证书安全](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)

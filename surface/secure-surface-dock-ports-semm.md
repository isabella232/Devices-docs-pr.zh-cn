---
title: 安全 Surface Dock 2 个具有 Surface Enterprise 管理模式（SEMM）的端口
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
ms.openlocfilehash: de16d76581926a90585b2c6beb2a7bf3b7a695bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830698"
---
# <span data-ttu-id="59270-104">安全 Surface Dock 2 个具有 Surface Enterprise 管理模式（SEMM）的端口</span><span class="sxs-lookup"><span data-stu-id="59270-104">Secure Surface Dock 2 ports with Surface Enterprise Management Mode (SEMM)</span></span>

## <span data-ttu-id="59270-105">简介</span><span class="sxs-lookup"><span data-stu-id="59270-105">Introduction</span></span>

<span data-ttu-id="59270-106">Surface Enterprise 管理模式（SEMM）允许 IT 管理员通过在 Windows 安装程序配置程序包（）中配置 UEFI 设置来保护和管理 Surface Dock 2 端口。MSI 文件）在企业环境中部署到兼容的 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="59270-106">Surface Enterprise Management Mode (SEMM) enables IT admins to secure and manage Surface Dock 2 ports by configuring UEFI settings in a Windows installer configuration package (.MSI file) deployed to compatible Surface devices across a corporate environment.</span></span>

### <span data-ttu-id="59270-107">支持的设备</span><span class="sxs-lookup"><span data-stu-id="59270-107">Supported devices</span></span>

<span data-ttu-id="59270-108">使用 SEMM 管理 Surface Dock 2 适用于连接到 Surface Book 3、Surface 笔记本3和 Surface Pro 7 的坞站。</span><span class="sxs-lookup"><span data-stu-id="59270-108">Managing Surface Dock 2 with SEMM is available for docks connected to Surface Book 3, Surface Laptop 3, and Surface Pro 7.</span></span> <span data-ttu-id="59270-109">这些兼容的 Surface 设备通常称为**主机设备**。</span><span class="sxs-lookup"><span data-stu-id="59270-109">These compatible Surface devices are commonly referred to as **host devices**.</span></span> <span data-ttu-id="59270-110">根据主机设备是否**经过身份验证**或**未经身份**验证，将程序包应用于主机设备。</span><span class="sxs-lookup"><span data-stu-id="59270-110">A package is applied to host devices based on if a host device is **authenticated** or **unauthenticated**.</span></span> <span data-ttu-id="59270-111">已配置的设置驻留在主机设备上的 UEFI 层中，使你（IT 管理员）可以管理 Surface Dock 2，就像任何其他内置外围设备（如相机）一样。</span><span class="sxs-lookup"><span data-stu-id="59270-111">Configured settings reside in the UEFI layer on host devices enabling you — the IT admin — to manage Surface Dock 2 just like any other built-in peripheral such as the camera.</span></span>

>[!NOTE]
><span data-ttu-id="59270-112">只有当插接连接到以下兼容设备之一时，才能管理 Surface Dock 2 端口： Surface Book 3、Surface 笔记本3和 Surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="59270-112">You can manage Surface Dock 2 ports only when the dock is connected to one of the following compatible devices:  Surface Book 3, Surface Laptop 3, and Surface Pro 7.</span></span> <span data-ttu-id="59270-113">任何未接收到 UEFI 身份验证策略设置的设备本身就是未经身份验证的设备。</span><span class="sxs-lookup"><span data-stu-id="59270-113">Any device that doesn't receive the UEFI Authenticated policy settings is inherently an unauthenticated device.</span></span>

### <span data-ttu-id="59270-114">场景</span><span class="sxs-lookup"><span data-stu-id="59270-114">Scenarios</span></span>

<span data-ttu-id="59270-115">对登录到企业主机设备的授权人员限制 Surface Dock 2，提供另一层数据保护。</span><span class="sxs-lookup"><span data-stu-id="59270-115">Restricting Surface Dock 2 to authorized persons signed into a corporate host device provides another layer of data protection.</span></span> <span data-ttu-id="59270-116">这种锁定 Surface Dock 2 的能力对于高度安全的环境中的特定客户非常重要，这些客户希望在保持遵守严格的安全协议的同时获得固定的功能和生产力。</span><span class="sxs-lookup"><span data-stu-id="59270-116">This ability to lock down Surface Dock 2 is critical for specific customers in highly secure environments who want the functionality and productivity benefits of the dock while maintaining compliance with strict security protocols.</span></span> <span data-ttu-id="59270-117">我们预计使用 Surface Dock 的 SEMM 在开放办公和共享空间中尤其有用，特别是出于安全原因希望锁定 USB 端口的客户。</span><span class="sxs-lookup"><span data-stu-id="59270-117">We anticipate SEMM used with Surface Dock 2 will be particularly useful in open offices and shared spaces especially for customers who want to lock USB ports for security reasons.</span></span> <span data-ttu-id="59270-118">对于视频演示，请查看[Surface Dock 2 的 SEMM](https://youtu.be/VLV19ISvq_s)。</span><span class="sxs-lookup"><span data-stu-id="59270-118">For a video demo, check out [SEMM for Surface Dock 2](https://youtu.be/VLV19ISvq_s).</span></span>

## <span data-ttu-id="59270-119">配置和部署 Surface Dock 的 UEFI 设置2</span><span class="sxs-lookup"><span data-stu-id="59270-119">Configuring and deploying UEFI settings for Surface Dock 2</span></span>

<span data-ttu-id="59270-120">本部分提供以下任务的分步指南：</span><span class="sxs-lookup"><span data-stu-id="59270-120">This section provides step-by-step guidance for the following tasks:</span></span>

1. <span data-ttu-id="59270-121">安装[**SURFACE UEFI 配置**](https://www.microsoft.com/download/details.aspx?id=46703)器。</span><span class="sxs-lookup"><span data-stu-id="59270-121">Install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
1. <span data-ttu-id="59270-122">创建或获取公钥证书。</span><span class="sxs-lookup"><span data-stu-id="59270-122">Create or obtain public key certificates.</span></span>
1. <span data-ttu-id="59270-123">创建。MSI 配置程序包。</span><span class="sxs-lookup"><span data-stu-id="59270-123">Create an .MSI configuration package.</span></span>
   1. <span data-ttu-id="59270-124">添加您的证书。</span><span class="sxs-lookup"><span data-stu-id="59270-124">Add your certificates.</span></span>
   1. <span data-ttu-id="59270-125">输入 Surface Dock 2 设备的16位 RN 号码。</span><span class="sxs-lookup"><span data-stu-id="59270-125">Enter the 16-digit RN number for your Surface Dock 2 devices.</span></span>
   1. <span data-ttu-id="59270-126">配置 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="59270-126">Configure UEFI settings.</span></span>
1. <span data-ttu-id="59270-127">构建配置包并将其应用到目标 Surface 设备（Surface Book 3、Surface 笔记本电脑3或 Surface Pro 7。）</span><span class="sxs-lookup"><span data-stu-id="59270-127">Build and apply the configuration package to targeted Surface devices (Surface Book 3, Surface Laptop 3, or Surface Pro 7.)</span></span>

>[!NOTE]
><span data-ttu-id="59270-128">**Random （RN）** 是一个唯一的16位十六进制代码标识符，在工厂预配，并且在 dock 的底部以较小的类型打印。</span><span class="sxs-lookup"><span data-stu-id="59270-128">The **Random Number (RN)** is a unique 16-digit hex code identifier which is provisioned at the factory, and printed in small type on the underside of the dock.</span></span> <span data-ttu-id="59270-129">RN 与大多数序列号不同，因为它无法以电子方式读取。</span><span class="sxs-lookup"><span data-stu-id="59270-129">The RN differs from most serial numbers in that it can't be read electronically.</span></span> <span data-ttu-id="59270-130">这确保了所有权证明主要是通过在物理上访问设备时读取 RN 来确定的。</span><span class="sxs-lookup"><span data-stu-id="59270-130">This ensures proof of ownership is primarily established only by reading the RN when physically accessing the device.</span></span> <span data-ttu-id="59270-131">RN 也可以在购买交易期间获取，并记录在 Microsoft 库存系统中。</span><span class="sxs-lookup"><span data-stu-id="59270-131">The RN may also be obtained during the purchase transaction and is recorded in Microsoft inventory systems.</span></span>

### <span data-ttu-id="59270-132">安装 SEMM 和 Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="59270-132">Install SEMM and Surface UEFI Configurator</span></span>

<span data-ttu-id="59270-133">通过运行**SurfaceUEFI_Configurator_v2.71.139.0.msi**安装 SEMM。</span><span class="sxs-lookup"><span data-stu-id="59270-133">Install SEMM by running **SurfaceUEFI_Configurator_v2.71.139.0.msi**.</span></span> <span data-ttu-id="59270-134">这是一个独立安装程序，包含创建和分发 Surface Dock 2 的配置包所需的所有内容。</span><span class="sxs-lookup"><span data-stu-id="59270-134">This is a standalone installer and contains everything you need to create and distribute configuration packages for Surface Dock 2.</span></span>

- <span data-ttu-id="59270-135">从[Surface Tools FOR IT](https://www.microsoft.com/en-us/download/details.aspx?id=46703)下载**surface UEFI 配置**器。</span><span class="sxs-lookup"><span data-stu-id="59270-135">Download **Surface UEFI Configurator** from [Surface Tools for IT](https://www.microsoft.com/en-us/download/details.aspx?id=46703).</span></span>

## <span data-ttu-id="59270-136">创建公钥证书</span><span class="sxs-lookup"><span data-stu-id="59270-136">Create public key certificates</span></span>

<span data-ttu-id="59270-137">本部分提供了创建管理 Surface Dock 的端口所需证书的规范。</span><span class="sxs-lookup"><span data-stu-id="59270-137">This section provides specifications for creating the certificates needed to manage ports for Surface Dock 2.</span></span>

### <span data-ttu-id="59270-138">必备条件</span><span class="sxs-lookup"><span data-stu-id="59270-138">Prerequisites</span></span>

<span data-ttu-id="59270-139">本文假定你从第三方提供商获取证书，或者你已经拥有 PKI 证书服务的专业知识，并知道如何创建自己的证书。</span><span class="sxs-lookup"><span data-stu-id="59270-139">This article assumes that you either obtain certificates from a third-party provider or you already have expertise in PKI certificate services and know how to create your own.</span></span>  <span data-ttu-id="59270-140">你应该熟悉并按照[图面企业管理模式（SEMM）](https://docs.microsoft.com/surface/surface-enterprise-management-mode)文档中所述创建证书的常规建议，但有一个例外。</span><span class="sxs-lookup"><span data-stu-id="59270-140">You should be familiar with and follow the general recommendations for creating certificates as described in [Surface Enterprise Management Mode (SEMM)](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation, with one exception.</span></span> <span data-ttu-id="59270-141">此页面上记录的证书要求为**Dock 证书颁发机构**提供30年的有效期，以及用于**主机身份验证证书**的20年。</span><span class="sxs-lookup"><span data-stu-id="59270-141">The certificates documented on this page require expiration terms of 30 years for the **Dock Certificate Authority**, and 20 years for the **Host Authentication Certificate**.</span></span>

<span data-ttu-id="59270-142">有关详细信息，请参阅[证书服务体系结构](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)文档，并在[windows server 2019 中查看 windows server](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)中的相应章节，以及 Microsoft 新闻可用的[Windows Server 2008 PKI 和证书安全](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)。</span><span class="sxs-lookup"><span data-stu-id="59270-142">For more information, see [Certificate Services Architecture](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) documentation and review the appropriate chapters in [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277), or [Windows Server 2008 PKI and Certificate Security](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) available from Microsoft Press.</span></span>

### <span data-ttu-id="59270-143">根和主机证书要求</span><span class="sxs-lookup"><span data-stu-id="59270-143">Root and host certificate requirements</span></span>

<span data-ttu-id="59270-144">在创建配置程序包之前，你需要准备验证 Surface Dock 的所有权的公钥证书，并在设备生命周期内帮助所有权的任何后续更改。</span><span class="sxs-lookup"><span data-stu-id="59270-144">Prior to creating the configuration package, you need to prepare public key certificates that authenticate ownership of Surface Dock 2 and facilitate any subsequent changes in ownership during the device lifecycle.</span></span> <span data-ttu-id="59270-145">主机和预配证书要求输入 EKU Id，否则称为**客户端身份验证增强型密钥用法（EKU）对象标识符（oid**）。</span><span class="sxs-lookup"><span data-stu-id="59270-145">The host and provisioning certificates require entering EKU IDs otherwise known as **Client Authentication Enhanced Key Usage (EKU) object identifiers (OIDs)**.</span></span>

<span data-ttu-id="59270-146">表1和表2中列出了所需的 EKU 值。</span><span class="sxs-lookup"><span data-stu-id="59270-146">The required EKU values are listed in Table 1 and Table 2.</span></span>

#### <span data-ttu-id="59270-147">表 1. </span><span class="sxs-lookup"><span data-stu-id="59270-147">Table 1.</span></span> <span data-ttu-id="59270-148">根和插接证书要求</span><span class="sxs-lookup"><span data-stu-id="59270-148">Root and Dock Certificate requirements</span></span>

|<span data-ttu-id="59270-149">证书</span><span class="sxs-lookup"><span data-stu-id="59270-149">Certificate</span></span>|<span data-ttu-id="59270-150">算法</span><span class="sxs-lookup"><span data-stu-id="59270-150">Algorithm</span></span>|<span data-ttu-id="59270-151">描述</span><span class="sxs-lookup"><span data-stu-id="59270-151">Description</span></span>|<span data-ttu-id="59270-152">到期</span><span class="sxs-lookup"><span data-stu-id="59270-152">Expiration</span></span>|<span data-ttu-id="59270-153">EKU OID</span><span class="sxs-lookup"><span data-stu-id="59270-153">EKU OID</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="59270-154">根证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="59270-154">Root Certificate Authority</span></span>|<span data-ttu-id="59270-155">ECDSA_P384</span><span class="sxs-lookup"><span data-stu-id="59270-155">ECDSA_P384</span></span>|<span data-ttu-id="59270-156">-具有384位质数椭圆曲线数字签名算法（ECDSA）的根证书</span><span class="sxs-lookup"><span data-stu-id="59270-156">- Root certificate with 384-bit prime elliptic curve digital signature algorithm (ECDSA)</span></span><br><span data-ttu-id="59270-157">-SHA 256 密钥用法：</span><span class="sxs-lookup"><span data-stu-id="59270-157">- SHA 256 Key Usage:</span></span><br><span data-ttu-id="59270-158">CERT_DIGITAL_SIGNATURE_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="59270-158">CERT_DIGITAL_SIGNATURE_KEY_USAGE</span></span><br><span data-ttu-id="59270-159">-CERT_KEY_CERT_SIGN_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="59270-159">- CERT_KEY_CERT_SIGN_KEY_USAGE</span></span><br><span data-ttu-id="59270-160">CERT_CRL_SIGN_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="59270-160">CERT_CRL_SIGN_KEY_USAGE</span></span>|<span data-ttu-id="59270-161">30年</span><span class="sxs-lookup"><span data-stu-id="59270-161">30 years</span></span>|<span data-ttu-id="59270-162">不适用</span><span class="sxs-lookup"><span data-stu-id="59270-162">N/A</span></span>
|<span data-ttu-id="59270-163">插接证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="59270-163">Dock Certificate Authority</span></span>|<span data-ttu-id="59270-164">ECC P256 曲线</span><span class="sxs-lookup"><span data-stu-id="59270-164">ECC P256 curve</span></span>|<span data-ttu-id="59270-165">-具有256位椭圆曲线加密（ECC）的主机证书</span><span class="sxs-lookup"><span data-stu-id="59270-165">- Host certificate with 256-bit elliptic-curve cryptography (ECC)</span></span><br><span data-ttu-id="59270-166">-SHA 256 密钥用法：</span><span class="sxs-lookup"><span data-stu-id="59270-166">- SHA 256 Key Usage:</span></span><br><span data-ttu-id="59270-167">CERT_KEY_CERT_SIGN_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="59270-167">CERT_KEY_CERT_SIGN_KEY_USAGE</span></span><br><span data-ttu-id="59270-168">-路径长度约束 = 0</span><span class="sxs-lookup"><span data-stu-id="59270-168">- Path Length Constraint = 0</span></span>|<span data-ttu-id="59270-169">20年</span><span class="sxs-lookup"><span data-stu-id="59270-169">20 years</span></span>|<span data-ttu-id="59270-170">1.3.6.1.4.1.311.76.9.21.2</span><span class="sxs-lookup"><span data-stu-id="59270-170">1.3.6.1.4.1.311.76.9.21.2</span></span><br><span data-ttu-id="59270-171">1.3.6.1.4.1.311.76.9.21.3</span><span class="sxs-lookup"><span data-stu-id="59270-171">1.3.6.1.4.1.311.76.9.21.3</span></span>|

   >[!NOTE]
   ><span data-ttu-id="59270-172">必须将 dock CA 导出为 p7b 文件。</span><span class="sxs-lookup"><span data-stu-id="59270-172">The dock CA must be exported as a .p7b file.</span></span>

### <span data-ttu-id="59270-173">预配管理证书要求</span><span class="sxs-lookup"><span data-stu-id="59270-173">Provisioning Administration Certificate requirements</span></span>

<span data-ttu-id="59270-174">每台主机设备都必须具有 doc CA 和两个证书，如表2中所示。</span><span class="sxs-lookup"><span data-stu-id="59270-174">Each host device must have the doc CA and two certificates as shown in Table 2.</span></span>

#### <span data-ttu-id="59270-175">表 2. </span><span class="sxs-lookup"><span data-stu-id="59270-175">Table 2.</span></span> <span data-ttu-id="59270-176">预配管理证书要求</span><span class="sxs-lookup"><span data-stu-id="59270-176">Provisioning administration certificate requirements</span></span>

|<span data-ttu-id="59270-177">证书</span><span class="sxs-lookup"><span data-stu-id="59270-177">Certificate</span></span>|<span data-ttu-id="59270-178">算法</span><span class="sxs-lookup"><span data-stu-id="59270-178">Algorithm</span></span>|<span data-ttu-id="59270-179">描述</span><span class="sxs-lookup"><span data-stu-id="59270-179">Description</span></span>|<span data-ttu-id="59270-180">EKU OID</span><span class="sxs-lookup"><span data-stu-id="59270-180">EKU OID</span></span>|
|---|---|---|---|
|<span data-ttu-id="59270-181">主机身份验证证书</span><span class="sxs-lookup"><span data-stu-id="59270-181">Host authentication certificate</span></span>|<span data-ttu-id="59270-182">ECC P256</span><span class="sxs-lookup"><span data-stu-id="59270-182">ECC P256</span></span><br><span data-ttu-id="59270-183">SHA 256</span><span class="sxs-lookup"><span data-stu-id="59270-183">SHA 256</span></span>|<span data-ttu-id="59270-184">证明主机设备的身份。</span><span class="sxs-lookup"><span data-stu-id="59270-184">Proves the identity of the host device.</span></span>|<span data-ttu-id="59270-185">1.3.6.1.4.1.311.76.9.21.2</span><span class="sxs-lookup"><span data-stu-id="59270-185">1.3.6.1.4.1.311.76.9.21.2</span></span>|
|<span data-ttu-id="59270-186">预配管理证书</span><span class="sxs-lookup"><span data-stu-id="59270-186">Provisioning administration certificate</span></span>|<span data-ttu-id="59270-187">ECC P256</span><span class="sxs-lookup"><span data-stu-id="59270-187">ECC P256</span></span><br><span data-ttu-id="59270-188">SHA256</span><span class="sxs-lookup"><span data-stu-id="59270-188">SHA256</span></span>|<span data-ttu-id="59270-189">使你可以通过允许替换当前安装在 dock 上的 CA 来更改 dock 所有权和/或策略设置。</span><span class="sxs-lookup"><span data-stu-id="59270-189">Enables you to change dock ownership and/or policy settings by allowing you to replace the CA that's currently installed on the dock.</span></span>|<span data-ttu-id="59270-190">1.3.6.1.4.1.311.76.9.21.3</span><span class="sxs-lookup"><span data-stu-id="59270-190">1.3.6.1.4.1.311.76.9.21.3</span></span><br><span data-ttu-id="59270-191">1.3.6.1.4.1.311.76.9.21.4</span><span class="sxs-lookup"><span data-stu-id="59270-191">1.3.6.1.4.1.311.76.9.21.4</span></span>|

   >[!NOTE]
   ><span data-ttu-id="59270-192">必须以 .pfx 文件的形式导出主机身份验证和预配证书。</span><span class="sxs-lookup"><span data-stu-id="59270-192">The host authentication and provisioning certificates must be exported as .pfx files.</span></span>

### <span data-ttu-id="59270-193">创建配置包</span><span class="sxs-lookup"><span data-stu-id="59270-193">Create configuration package</span></span>

<span data-ttu-id="59270-194">获取或创建证书后，即可创建将应用于目标 Surface 设备的 MSI 配置包。</span><span class="sxs-lookup"><span data-stu-id="59270-194">When you have obtained or created the certificates, you’re ready to build the MSI configuration package that will be applied to target Surface devices.</span></span>

1. <span data-ttu-id="59270-195">运行 Surface **UEFI 配置**器。</span><span class="sxs-lookup"><span data-stu-id="59270-195">Run Surface **UEFI Configurator**.</span></span>

   ![运行 Surface UEFI 配置器](images/secure-surface-dock-ports-semm-1.png)

1. <span data-ttu-id="59270-197">选择 " **Surface Dock**"。</span><span class="sxs-lookup"><span data-stu-id="59270-197">Select **Surface Dock**.</span></span>

   ![选择 Surface Dock](images/secure-surface-dock-ports-semm-2.png)

1. <span data-ttu-id="59270-199">在 "证书" 页面上，输入相应的**证书**。</span><span class="sxs-lookup"><span data-stu-id="59270-199">On the certificate page, enter the appropriate **certificates**.</span></span>

   ![输入相应的证书](images/secure-surface-dock-ports-semm-3.png)

1. <span data-ttu-id="59270-201">将相应的 dock RNs 添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="59270-201">Add appropriate dock RNs to the list.</span></span>

   >[!NOTE]
   ><span data-ttu-id="59270-202">为多个 Surface Dock 2 设备创建配置包时，不必手动输入每个 RN，而是可以使用包含 RNs 列表的 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="59270-202">When creating a configuration package for multiple Surface Dock 2 devices, instead of entering each RN manually, you can use a .csv file that contains a list of RNs.</span></span>

1. <span data-ttu-id="59270-203">为 USB 数据、以太网和音频端口指定策略设置。</span><span class="sxs-lookup"><span data-stu-id="59270-203">Specify your policy settings for USB data, Ethernet, and Audio ports.</span></span> <span data-ttu-id="59270-204">UEFI 配置器允许你为经过身份验证的用户（经过身份验证的策略）和未经身份验证的用户（未经验证的策略）配置策略</span><span class="sxs-lookup"><span data-stu-id="59270-204">UEFI Configurator lets you configure policy settings for authenticated users (Authenticated Policy) and unauthenticated users (Unauthenticated Policy).</span></span> <span data-ttu-id="59270-205">下图显示了为经过身份验证的用户打开的端口访问和为未经授权的用户关闭的端口访问。</span><span class="sxs-lookup"><span data-stu-id="59270-205">The following figure shows port access turned on for authenticated users and turned off for unauthenticated users.</span></span>

   ![选择要激活或停用的组件。](images/secure-surface-dock-ports-semm-4.png)

   - <span data-ttu-id="59270-207">经身份验证的用户指安装了相应证书的 Surface 设备，如中所述。您应用到目标设备的 MSI 配置程序包。</span><span class="sxs-lookup"><span data-stu-id="59270-207">Authenticated user refers to a Surface Device that has the appropriate certificates installed, as configured in the .MSI configuration package that you applied to target devices.</span></span> <span data-ttu-id="59270-208">它适用于登录设备的任何用户已验证用户。</span><span class="sxs-lookup"><span data-stu-id="59270-208">It applies to any user authenticated user who signs into the device.</span></span> 
   - <span data-ttu-id="59270-209">未经身份验证的用户指任何其他设备。</span><span class="sxs-lookup"><span data-stu-id="59270-209">Unauthenticated user refers to any other device.</span></span>
   - <span data-ttu-id="59270-210">选择 "**重置**" 以创建特殊的 "reset" 程序包，该程序包将删除任何以前已接受的任何以前配置的程序包。</span><span class="sxs-lookup"><span data-stu-id="59270-210">Select **Reset** to create a special “Reset” package that will remove any previous configuration package that the dock had accepted.</span></span>

1. <span data-ttu-id="59270-211">选择 "**生成**" 以创建指定的程序包。</span><span class="sxs-lookup"><span data-stu-id="59270-211">Select **Build** to create the package as specified.</span></span>

### <span data-ttu-id="59270-212">将配置包应用于 Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="59270-212">Apply the configuration package to a Surface Dock 2</span></span>

1. <span data-ttu-id="59270-213">获取 Surface UEFI 配置器生成的 MSI 文件，并将其安装在 Surface host 设备上。</span><span class="sxs-lookup"><span data-stu-id="59270-213">Take the MSI file that the Surface UEFI Configurator generated and install it on a Surface host device.</span></span> <span data-ttu-id="59270-214">兼容的主机设备是 Surface Book 3、Surface 笔记本3或 Surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="59270-214">Compatible host devices are Surface Book 3, Surface Laptop 3, or Surface Pro 7.</span></span>
1. <span data-ttu-id="59270-215">将主机设备连接到 Surface Dock 2。</span><span class="sxs-lookup"><span data-stu-id="59270-215">Connect the host device to the Surface Dock 2.</span></span> <span data-ttu-id="59270-216">当你连接时，将应用停靠的 UEFI 策略设置。</span><span class="sxs-lookup"><span data-stu-id="59270-216">When you connect the dock UEFI policy settings are applied.</span></span>

## <span data-ttu-id="59270-217">使用 Surface App 验证托管状态</span><span class="sxs-lookup"><span data-stu-id="59270-217">Verify managed state using the Surface App</span></span>

<span data-ttu-id="59270-218">应用配置包后，您可以直接从 Surface App （默认情况下在所有 Surface 设备上安装）快速验证 dock 的最终策略状态。</span><span class="sxs-lookup"><span data-stu-id="59270-218">Once you have applied the configuration package, you can quickly verify the resultant policy state of the dock directly from the Surface App, installed by default on all Surface devices.</span></span> <span data-ttu-id="59270-219">如果设备上不存在 Surface 应用，则可以从 Microsoft Store 下载并安装它。</span><span class="sxs-lookup"><span data-stu-id="59270-219">If Surface App isn't present on the device, you can download and install it from the Microsoft Store.</span></span>

### <span data-ttu-id="59270-220">测试方案</span><span class="sxs-lookup"><span data-stu-id="59270-220">Test scenario</span></span>

<span data-ttu-id="59270-221">目标：将策略设置配置为仅允许经过身份验证的用户访问端口。</span><span class="sxs-lookup"><span data-stu-id="59270-221">Objective: Configure policy settings to allow port access by authenticated users only.</span></span>

1. <span data-ttu-id="59270-222">为经过身份验证的用户打开所有端口，并为未经身份验证的用户关闭它们。</span><span class="sxs-lookup"><span data-stu-id="59270-222">Turn on all ports for authenticated users and turn them off for unauthenticated users.</span></span>

   ![为经过身份验证的用户启用端口](images/secure-surface-dock-ports-semm-4.png)

1. <span data-ttu-id="59270-224">将配置包应用到目标设备，然后连接 Surface Dock 2。</span><span class="sxs-lookup"><span data-stu-id="59270-224">Apply the configuration package to your target device and then connect Surface Dock 2.</span></span>

1. <span data-ttu-id="59270-225">打开**Surface App** ，然后选择 " **surface dock** " 以查看 surface dock 的最终策略状态。</span><span class="sxs-lookup"><span data-stu-id="59270-225">Open **Surface App** and select **Surface Dock** to view the resultant policy state of your Surface Dock.</span></span> <span data-ttu-id="59270-226">如果应用了策略设置，Surface App 将指示端口可用。</span><span class="sxs-lookup"><span data-stu-id="59270-226">If the policy settings are applied, Surface App will indicate that ports are available.</span></span>

   ![Surface app 显示所有端口均可用于经过身份验证的用户](images/secure-surface-dock-ports-semm-5.png)

1. <span data-ttu-id="59270-228">现在，你需要验证策略设置是否已成功为未经身份验证的用户关闭所有端口。</span><span class="sxs-lookup"><span data-stu-id="59270-228">Now you need to verify that the policy settings have successfully turned off all ports for unauthenticated users.</span></span> <span data-ttu-id="59270-229">将 Surface Dock 2 连接到非托管设备，即你创建的配置包的管理范围之外的任何 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="59270-229">Connect Surface Dock 2 to an unmanaged device, i.e., any Surface device outside the scope of management for the configuration package you created.</span></span>

1. <span data-ttu-id="59270-230">"打开**surface" 应用**，然后选择 " **surface Dock**"。</span><span class="sxs-lookup"><span data-stu-id="59270-230">Open **Surface App** and select **Surface Dock**.</span></span> <span data-ttu-id="59270-231">结果策略状态将指示端口已关闭。</span><span class="sxs-lookup"><span data-stu-id="59270-231">The resultant policy state will indicate ports are turned off.</span></span>

   ![<span data-ttu-id="59270-232">显示未经身份验证的用户关闭端口的 Surface 应用</span><span class="sxs-lookup"><span data-stu-id="59270-232">Surface app showing ports turned off for unauthenticated users</span></span> ](images/secure-surface-dock-ports-semm-6.png)

>[!NOTE]
><span data-ttu-id="59270-233">如果你想要保留设备的所有权，但允许所有用户拥有完全访问权限，你可以创建一个新的程序包，其中所有内容均已打开。</span><span class="sxs-lookup"><span data-stu-id="59270-233">If you want to keep ownership of the device, but allow all users full access, you can make a new package with everything turned on.</span></span> <span data-ttu-id="59270-234">如果你希望完全删除设备的限制和所有权（使其处于非托管状态），请在 Surface UEFI 配置器中选择 "**重置**" 以创建要应用到目标设备的程序包。</span><span class="sxs-lookup"><span data-stu-id="59270-234">If you wish to completely remove the restrictions and ownership of the device (make it unmanaged), select **Reset** in Surface UEFI Configurator to create a package to apply to target devices.</span></span>

<span data-ttu-id="59270-235">得到.</span><span class="sxs-lookup"><span data-stu-id="59270-235">Congratulations.</span></span> <span data-ttu-id="59270-236">你已在目标主机设备上成功管理 Surface Dock 2 端口。</span><span class="sxs-lookup"><span data-stu-id="59270-236">You have successfully managed Surface Dock 2 ports on targeted host devices.</span></span>

## <span data-ttu-id="59270-237">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="59270-237">Learn more</span></span>

- [<span data-ttu-id="59270-238">Surface Enterprise 管理模式（SEMM）文档</span><span class="sxs-lookup"><span data-stu-id="59270-238">Surface Enterprise Management Mode (SEMM) documentation</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
- [<span data-ttu-id="59270-239">证书服务体系结构</span><span class="sxs-lookup"><span data-stu-id="59270-239">Certificate Services Architecture</span></span>](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)
- [<span data-ttu-id="59270-240">Windows Server 2019 内部</span><span class="sxs-lookup"><span data-stu-id="59270-240">Windows Server 2019 Inside Out</span></span>](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [<span data-ttu-id="59270-241">Windows Server 2008 PKI 和证书安全</span><span class="sxs-lookup"><span data-stu-id="59270-241">Windows Server 2008 PKI and Certificate Security</span></span>](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)

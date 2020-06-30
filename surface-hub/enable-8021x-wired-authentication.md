---
title: 启用 802.1x 有线身份验证
description: 802.1x 有线身份验证 MDM 策略已在 Surface Hub 设备上启用。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831852"
---
# <span data-ttu-id="ef52a-103">启用 802.1x 有线身份验证</span><span class="sxs-lookup"><span data-stu-id="ef52a-103">Enable 802.1x wired authentication</span></span>

<span data-ttu-id="ef52a-104">[Windows 10 的 2017 年 11 月 14 日更新](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954)（版本 15063.726）在 Surface Hub 设备上启用 802.1x 有线身份验证 MDM 策略。</span><span class="sxs-lookup"><span data-stu-id="ef52a-104">The [November 14, 2017 update to Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build 15063.726) enables 802.1x wired authentication MDM policies on Surface Hub devices.</span></span> <span data-ttu-id="ef52a-105">该功能允许组织使用 [IEEE 802.1x 身份验证协议](http://www.ieee802.org/1/pages/802.1x-2010.html) 强制执行标准化有线网络身份验证。</span><span class="sxs-lookup"><span data-stu-id="ef52a-105">The feature allows organizations to enforce standardized wired network authentication using the [IEEE 802.1x authentication protocol](http://www.ieee802.org/1/pages/802.1x-2010.html).</span></span> <span data-ttu-id="ef52a-106">这已经适用于通过 MDM 使用 WLAN 配置文件的无线身份验证。</span><span class="sxs-lookup"><span data-stu-id="ef52a-106">This is already available for wireless authentication using WLAN profiles via MDM.</span></span> <span data-ttu-id="ef52a-107">本主题介绍如何配置用于有线身份验证的 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="ef52a-107">This topic explains how to  configure a Surface Hub for use with wired authentication.</span></span> 

<span data-ttu-id="ef52a-108">可以通过 MDM [OMA-URI 定义](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings) 在 Surface Hub 上强制执行和启用 802.1x 有线身份验证。</span><span class="sxs-lookup"><span data-stu-id="ef52a-108">Enforcement and enablement of 802.1x wired authentication on Surface Hub can be done through MDM [OMA-URI definition](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span></span> 

<span data-ttu-id="ef52a-109">主要配置设置为 **LanProfile** 策略。</span><span class="sxs-lookup"><span data-stu-id="ef52a-109">The primary configuration to set is the **LanProfile** policy.</span></span> <span data-ttu-id="ef52a-110">根据所选的身份验证方法，可能需要其他策略，**EapUserData** 策略，或通过用于添加用户或计算证书的 MDM 策略（例如用户用户/设备证书的 [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) 或用于设备证书的 [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp)）。</span><span class="sxs-lookup"><span data-stu-id="ef52a-110">Depending on the authentication method selected, other policies may be required, either the **EapUserData** policy or through MDM policies for adding user or machine certificates (such as [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) for user/device certificates or [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) for device certificates).</span></span> 

## <span data-ttu-id="ef52a-111">LanProfile 策略元素</span><span class="sxs-lookup"><span data-stu-id="ef52a-111">LanProfile policy element</span></span>

<span data-ttu-id="ef52a-112">若要将 Surface Hub 配置为使用受支持的 802.1x 身份验证方法之一，请使用以下 OMA URI。</span><span class="sxs-lookup"><span data-stu-id="ef52a-112">To configure Surface Hub to use one of the supported 802.1x authentication methods, utilize the following OMA-URI.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

<span data-ttu-id="ef52a-113">此 OMA-URI 节点采用 XML 文本字符串作为参数。</span><span class="sxs-lookup"><span data-stu-id="ef52a-113">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="ef52a-114">作为参数提供的 XML 应符合包括 [802.1X 架构](https://msdn.microsoft.com/library/cc233003.aspx)中的元素的[有线 LAN 配置文件架构](https://msdn.microsoft.com/library/cc233002.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ef52a-114">The XML provided as a parameter should conform to the [Wired LAN Profile Schema](https://msdn.microsoft.com/library/cc233002.aspx) including elements from the [802.1X schema](https://msdn.microsoft.com/library/cc233003.aspx).</span></span> 

<span data-ttu-id="ef52a-115">在大多数情况下，管理员或用户可以使用以下 NETSH 命令，从已在网络上针对 802.1X 配置的现有电脑中导出 LanProfile XML。</span><span class="sxs-lookup"><span data-stu-id="ef52a-115">In most instances, an administrator or user can export the LanProfile XML from an existing PC that is already configured on the network for 802.1X using this following NETSH command.</span></span> 

```
netsh lan export profile folder=.
```

<span data-ttu-id="ef52a-116">运行此命令将提供以下输出，并将标题为 **Ethernet.xml** 的文件放在当前目录中。</span><span class="sxs-lookup"><span data-stu-id="ef52a-116">Running this command will give the following output and place a file titled **Ethernet.xml** in the current directory.</span></span> 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <span data-ttu-id="ef52a-117">EapUserData 策略元素</span><span class="sxs-lookup"><span data-stu-id="ef52a-117">EapUserData policy element</span></span>

<span data-ttu-id="ef52a-118">如果所选的身份验证方法需要用户名和密码而不是证书，则可以使用 **EapUserData** 元素指定供设备用于身份验证到网络的凭据。</span><span class="sxs-lookup"><span data-stu-id="ef52a-118">If your selected authentication method requires a username and password as opposed to a certificate, you can use the **EapUserData** element to specify credentials for the device to use to authenticate to the network.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

<span data-ttu-id="ef52a-119">此 OMA-URI 节点采用 XML 文本字符串作为参数。</span><span class="sxs-lookup"><span data-stu-id="ef52a-119">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="ef52a-120">作为参数提供的 XML 应符合 [PEAP MS-CHAPv2 用户属性示例](https://msdn.microsoft.com/library/windows/desktop/bb891979)。</span><span class="sxs-lookup"><span data-stu-id="ef52a-120">The XML provided as a parameter should conform to the [PEAP MS-CHAPv2 User Properties example](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span></span> <span data-ttu-id="ef52a-121">在此示例中，将需要使用信息替换 *test* 和 *ias-domain*。</span><span class="sxs-lookup"><span data-stu-id="ef52a-121">In the example, you will need to replace all instances of *test* and *ias-domain* with your information.</span></span>



## <span data-ttu-id="ef52a-122">添加证书</span><span class="sxs-lookup"><span data-stu-id="ef52a-122">Adding certificates</span></span>

<span data-ttu-id="ef52a-123">如果所选身份验证方法是基于证书的，则需要[创建预配包](provisioning-packages-for-surface-hub.md)、[利用 MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)或从设置（**设置**  >  **更新和安全**  >  **证书**）导入证书，以将这些证书部署到相应证书存储中的 Surface Hub 设备。</span><span class="sxs-lookup"><span data-stu-id="ef52a-123">If your selected authentication method is certificate-based, you will need to [create a provisioning package](provisioning-packages-for-surface-hub.md), [utilize MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp), or import a certificate from settings (**Settings** > **Update and Security** > **Certificates**) to deploy those certificates to your Surface Hub device in the appropriate Certificate Store.</span></span> <span data-ttu-id="ef52a-124">添加证书时，每个 PFX 必须只包含一个证书（一个PFX 不能具有多个证书）。</span><span class="sxs-lookup"><span data-stu-id="ef52a-124">When adding certificates, each PFX must contain only one certificate (a PFX cannot have multiple certificates).</span></span>


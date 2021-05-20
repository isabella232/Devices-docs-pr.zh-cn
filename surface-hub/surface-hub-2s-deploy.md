---
title: 创建 Surface Hub 2S 的预配程序包
description: 此页面介绍如何使用预配包Surface Hub部署 2S。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576862"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a><span data-ttu-id="58b24-104">创建 Surface Hub 2S 的预配程序包</span><span class="sxs-lookup"><span data-stu-id="58b24-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="58b24-105">可以使用配置设计器Windows WCD (WCD) 创建预配包，以自动部署 Surface Hub 2S。</span><span class="sxs-lookup"><span data-stu-id="58b24-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate deployment of Surface Hub 2S.</span></span> <span data-ttu-id="58b24-106">使用预配包添加证书、配置代理、设置设备管理员和设备帐户。</span><span class="sxs-lookup"><span data-stu-id="58b24-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="58b24-107">还可以将预配包与配置文件一起用于部署具有单个 U 盘的多个 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="58b24-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <a name="install-windows-configuration-designer"></a><span data-ttu-id="58b24-108">安装 Windows 配置设计器</span><span class="sxs-lookup"><span data-stu-id="58b24-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="58b24-109">从Windows ADK Windows部署工具包 (配置) 配置Windows 10。</span><span class="sxs-lookup"><span data-stu-id="58b24-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="58b24-110">下载并安装适用于 Windows 10[版本 1703 的 ADK。](https://go.microsoft.com/fwlink/p/?LinkId=845542)</span><span class="sxs-lookup"><span data-stu-id="58b24-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="58b24-111">有关详细信息，请参阅“[下载并安装 Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)”。</span><span class="sxs-lookup"><span data-stu-id="58b24-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <a name="add-certificates"></a><span data-ttu-id="58b24-112">添加证书</span><span class="sxs-lookup"><span data-stu-id="58b24-112">Add certificates</span></span>

<span data-ttu-id="58b24-113">可以将证书颁发机构证书导入 Surface Hub 2S。</span><span class="sxs-lookup"><span data-stu-id="58b24-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="58b24-114">若要将证书添加到 Surface Hub 2S，您需要每个证书的副本为 X.509，格式为 .cer。</span><span class="sxs-lookup"><span data-stu-id="58b24-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="58b24-115">不能导入 .crt、.pfx 或其他容器格式。</span><span class="sxs-lookup"><span data-stu-id="58b24-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="58b24-116">证书必须导入到Windows设计器中，并按层次结构排列：</span><span class="sxs-lookup"><span data-stu-id="58b24-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

> [!div class="mx-imgBorder"]
> ![添加证书](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a><span data-ttu-id="58b24-118">在 OOBE 期间配置代理</span><span class="sxs-lookup"><span data-stu-id="58b24-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="58b24-119">In Windows Configuration Designer， go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span><span class="sxs-lookup"><span data-stu-id="58b24-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

> [!div class="mx-imgBorder"]
> ![配置代理设置](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="58b24-121">配置代理设置时，如果您打算使用\*\*\*\* 安装脚本或代理服务器，请关闭"自动检测设置"。</span><span class="sxs-lookup"><span data-stu-id="58b24-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="58b24-122">您可以使用安装程序 *脚本或代理服务器* ，而不是同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="58b24-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a><span data-ttu-id="58b24-123">关联Surface Hub 2S 与 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="58b24-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="58b24-124">可以使用预配包将 Surface Hub 2S 与 Azure Active Directory 关联：作为 Azure Active Directory 全局管理员，可以使用批量令牌将大量新的 Windows 设备加入 Azure Active Directory 和 Intune。</span><span class="sxs-lookup"><span data-stu-id="58b24-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="58b24-125">若要创建批量令牌，请为它指定一个友好名称，将到期日期配置为 (最长 30 天) 并使用管理员凭据获取令牌，如下所示：</span><span class="sxs-lookup"><span data-stu-id="58b24-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

> [!div class="mx-imgBorder"]
> ![设置设备管理员示例 1](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![设置设备管理员示例 2](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![设置设备管理员示例 3](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a><span data-ttu-id="58b24-129">预配多个设备 (.csv文件) </span><span class="sxs-lookup"><span data-stu-id="58b24-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="58b24-130">除了预配包之外，您还可以使用 Surface Hub 配置文件，以便更轻松地设置设备。</span><span class="sxs-lookup"><span data-stu-id="58b24-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="58b24-131">一Surface Hub配置文件包含无线投影的设备帐户和友好名称的列表。</span><span class="sxs-lookup"><span data-stu-id="58b24-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="58b24-132">首次运行时，你可以选择从配置文件中选择设备帐户和友好名称。</span><span class="sxs-lookup"><span data-stu-id="58b24-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <a name="to-create-a-surface-hub-configuration-file"></a><span data-ttu-id="58b24-133">创建Surface Hub配置文件</span><span class="sxs-lookup"><span data-stu-id="58b24-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="58b24-134">使用Microsoft Excel或其他 CSV 编辑器，创建**名为：SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="58b24-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>

2. <span data-ttu-id="58b24-135">按此格式输入设备帐户和友好名称列表：</span><span class="sxs-lookup"><span data-stu-id="58b24-135">Enter a list of device accounts and friendly names in this format:</span></span>

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. <span data-ttu-id="58b24-136">将文件保存到你复制 PPKG 文件的 U 盘的根目录。</span><span class="sxs-lookup"><span data-stu-id="58b24-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    > [!div class="mx-imgBorder"]
    > ![配置文件示例](images/sh2-config-file.png)

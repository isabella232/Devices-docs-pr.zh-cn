---
title: 创建 Surface Hub 2S 的预配程序包
description: 本页介绍如何使用预配包和其他工具部署 Surface Hub 2。
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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832187"
---
# <span data-ttu-id="5d63d-104">创建 Surface Hub 2S 的预配程序包</span><span class="sxs-lookup"><span data-stu-id="5d63d-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="5d63d-105">你可以使用 Windows 配置设计器（WCD）创建预配程序包，以自动执行 Surface Hub 2 的部署过程。</span><span class="sxs-lookup"><span data-stu-id="5d63d-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate the deployment process of Surface Hub 2S.</span></span> <span data-ttu-id="5d63d-106">使用预配程序包添加证书、配置代理、设置设备管理员和设备帐户。</span><span class="sxs-lookup"><span data-stu-id="5d63d-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="5d63d-107">你还可以使用预配包和配置文件来部署具有单个 USB 拇指驱动器的多个 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="5d63d-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <span data-ttu-id="5d63d-108">安装 Windows 配置设计器</span><span class="sxs-lookup"><span data-stu-id="5d63d-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="5d63d-109">从 windows 10 的 Windows 评估和部署工具包（ADK）安装 Windows 配置设计器。</span><span class="sxs-lookup"><span data-stu-id="5d63d-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="5d63d-110">下载并安装[适用于 Windows 10 版本1703的 ADK](https://go.microsoft.com/fwlink/p/?LinkId=845542)。</span><span class="sxs-lookup"><span data-stu-id="5d63d-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="5d63d-111">有关详细信息，请参阅[下载并安装 WINDOWS ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)。</span><span class="sxs-lookup"><span data-stu-id="5d63d-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <span data-ttu-id="5d63d-112">添加证书</span><span class="sxs-lookup"><span data-stu-id="5d63d-112">Add certificates</span></span>

<span data-ttu-id="5d63d-113">您可以将证书颁发机构证书导入到 Surface Hub 2。</span><span class="sxs-lookup"><span data-stu-id="5d63d-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="5d63d-114">若要向 Surface Hub 2 添加证书，你需要将每个证书的副本作为 x.509 格式。</span><span class="sxs-lookup"><span data-stu-id="5d63d-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="5d63d-115">不能导入 .crt、.pfx 或其他容器格式。</span><span class="sxs-lookup"><span data-stu-id="5d63d-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="5d63d-116">必须将证书导入 Windows 配置设计器并按层次结构排列：</span><span class="sxs-lookup"><span data-stu-id="5d63d-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

 ![添加证书](images/sh2-wcd.png)

### <span data-ttu-id="5d63d-118">在 OOBE 期间配置代理</span><span class="sxs-lookup"><span data-stu-id="5d63d-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="5d63d-119">在 Windows 配置设计器中，转到 "配置代理服务器设置" 选项卡，然后输入相应的设置，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5d63d-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

 ![配置代理设置](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="5d63d-121">配置代理服务器设置时，如果打算使用安装脚本或代理服务器，请关闭 "**自动检测设置**"。</span><span class="sxs-lookup"><span data-stu-id="5d63d-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="5d63d-122">你可以使用设置脚本*或*代理服务器，而不是同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="5d63d-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <span data-ttu-id="5d63d-123">Azure Active Directory 的关联 Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="5d63d-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="5d63d-124">你可以使用预配包将 Surface Hub 2 与 Azure Active Directory 关联：作为 Azure Active Directory 全局管理员，你可以使用批量令牌将大量新的 Windows 设备加入到 Azure Active Directory 和 Intune。</span><span class="sxs-lookup"><span data-stu-id="5d63d-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="5d63d-125">若要创建批量令牌，请为其指定一个友好名称，配置过期日期（最多30天），并使用管理员凭据获取令牌，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5d63d-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

 ![设置设备管理员](images/sh2-token.png) <br><br>
 ![设置设备管理员](images/sh2-token2.png) <br><br>
 ![设置设备管理员](images/sh2-token3.png) <br><br>

### <span data-ttu-id="5d63d-129">预配多个设备（.csv 文件）</span><span class="sxs-lookup"><span data-stu-id="5d63d-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="5d63d-130">除了预配包之外，你还可以使用 Surface Hub 配置文件，以便更轻松地设置你的设备。</span><span class="sxs-lookup"><span data-stu-id="5d63d-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="5d63d-131">Surface Hub 配置文件包含设备帐户列表和用于无线投影的友好名称。</span><span class="sxs-lookup"><span data-stu-id="5d63d-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="5d63d-132">首次运行时，你可以从配置文件获取选择设备帐户和友好名称的选项。</span><span class="sxs-lookup"><span data-stu-id="5d63d-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <span data-ttu-id="5d63d-133">创建 Surface Hub 配置文件</span><span class="sxs-lookup"><span data-stu-id="5d63d-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="5d63d-134">使用 Microsoft Excel 或其他 CSV 编辑器，创建名为： **SurfaceHubConfiguration.csv**的 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="5d63d-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>
2. <span data-ttu-id="5d63d-135">按以下格式输入设备帐户和友好名称的列表：</span><span class="sxs-lookup"><span data-stu-id="5d63d-135">Enter a list of device accounts and friendly names in this format:</span></span>

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. <span data-ttu-id="5d63d-136">将文件保存到您复制了 PPKG 文件的 USB 拇指驱动器的根。</span><span class="sxs-lookup"><span data-stu-id="5d63d-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    ![配置文件示例](images/sh2-config-file.png)

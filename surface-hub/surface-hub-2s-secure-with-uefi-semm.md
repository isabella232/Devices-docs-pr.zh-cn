---
title: 通过 SEMM 保护和管理 Surface Hub 2
description: 了解有关通过 SEMM 保护 Surface Hub 的详细信息。
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
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830930"
---
# <span data-ttu-id="edcbc-104">使用 SEMM 和 UEFI 保护 Surface Hub 2S 的安全并进行管理</span><span class="sxs-lookup"><span data-stu-id="edcbc-104">Secure and manage Surface Hub 2S with SEMM and UEFI</span></span>

<span data-ttu-id="edcbc-105">新的 Surface Hub 2，您可以使用 SEMM 管理设备的 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="edcbc-105">New in Surface Hub 2S, you can use SEMM to manage the UEFI setting of the device.</span></span>
<span data-ttu-id="edcbc-106">使用 Microsoft Surface UEFI 配置器控制以下组件：</span><span class="sxs-lookup"><span data-stu-id="edcbc-106">Use the Microsoft Surface UEFI Configurator to control the following components:</span></span>

- <span data-ttu-id="edcbc-107">有线局域网</span><span class="sxs-lookup"><span data-stu-id="edcbc-107">Wired LAN</span></span>
- <span data-ttu-id="edcbc-108">相机</span><span class="sxs-lookup"><span data-stu-id="edcbc-108">Cameras</span></span>
- <span data-ttu-id="edcbc-109">蓝牙</span><span class="sxs-lookup"><span data-stu-id="edcbc-109">Bluetooth</span></span>
- <span data-ttu-id="edcbc-110">WLAN</span><span class="sxs-lookup"><span data-stu-id="edcbc-110">Wi-Fi</span></span>
- <span data-ttu-id="edcbc-111">占用传感器</span><span class="sxs-lookup"><span data-stu-id="edcbc-111">Occupancy sensor</span></span>

<span data-ttu-id="edcbc-112">使用 Microsoft Surface UEFI 配置器打开或关闭以下 UEFI 设置：</span><span class="sxs-lookup"><span data-stu-id="edcbc-112">Use the Microsoft Surface UEFI Configurator to turn on or off the following UEFI settings:</span></span>

- <span data-ttu-id="edcbc-113">靴子</span><span class="sxs-lookup"><span data-stu-id="edcbc-113">Boot</span></span>

    - <span data-ttu-id="edcbc-114">用于 PXE 启动的 IPv6</span><span class="sxs-lookup"><span data-stu-id="edcbc-114">IPv6 for PXE Boot</span></span>
    - <span data-ttu-id="edcbc-115">备用启动</span><span class="sxs-lookup"><span data-stu-id="edcbc-115">Alternate Boot</span></span>
    - <span data-ttu-id="edcbc-116">启动顺序锁</span><span class="sxs-lookup"><span data-stu-id="edcbc-116">Boot Order Lock</span></span>
    - <span data-ttu-id="edcbc-117">USB 启动</span><span class="sxs-lookup"><span data-stu-id="edcbc-117">USB Boot</span></span>
- <span data-ttu-id="edcbc-118">UEFI 前页</span><span class="sxs-lookup"><span data-stu-id="edcbc-118">UEFI Front Page</span></span>

    - <span data-ttu-id="edcbc-119">设备</span><span class="sxs-lookup"><span data-stu-id="edcbc-119">Devices</span></span>
    - <span data-ttu-id="edcbc-120">靴子</span><span class="sxs-lookup"><span data-stu-id="edcbc-120">Boot</span></span>
    - <span data-ttu-id="edcbc-121">日期/时间</span><span class="sxs-lookup"><span data-stu-id="edcbc-121">Date/Time</span></span>

## <span data-ttu-id="edcbc-122">创建 UEFI 配置图像</span><span class="sxs-lookup"><span data-stu-id="edcbc-122">Create UEFI configuration image</span></span>

<span data-ttu-id="edcbc-123">与其他 Surface 设备不同，您不能使用 MSI 文件或 Win PE 映像在 Surface Hub 2 秒上应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="edcbc-123">Unlike other Surface devices, you cannot use an MSI file or a Win PE image to apply these settings on Surface Hub 2S.</span></span> <span data-ttu-id="edcbc-124">相反，你需要创建一个 USB 图像以加载到设备中。</span><span class="sxs-lookup"><span data-stu-id="edcbc-124">Instead, you need to create a USB image to load into the device.</span></span> <span data-ttu-id="edcbc-125">若要创建 Surface Hub 2 UEFI 配置映像，请从 Microsoft 下载中心的 " [Surface Tools FOR IT](https://www.microsoft.com/download/details.aspx?id=46703) " 页面下载并安装最新版本的 MICROSOFT Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="edcbc-125">To create a Surface Hub 2S UEFI configuration image, download and install the latest version of the Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span> <span data-ttu-id="edcbc-126">有关使用 UEFI 和 SEMM 的详细信息，请参阅[Microsoft Surface 企业管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="edcbc-126">For more information about using UEFI and SEMM, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="edcbc-127">在 Surface Hub 2 上配置 UEFI</span><span class="sxs-lookup"><span data-stu-id="edcbc-127">To configure UEFI on Surface Hub 2S</span></span>

1. <span data-ttu-id="edcbc-128">启动 UEFI 配置器，在第一个屏幕上，选择 "**配置包**"。</span><span class="sxs-lookup"><span data-stu-id="edcbc-128">Start the UEFI Configurator and on the first screen, choose **Configuration Package**.</span></span><br><br>
![\* 启动 UEFI 配置器并选择 "配置包" \*](images/sh2-uefi1.png) <br> <br>
2. <span data-ttu-id="edcbc-130">若要将证书添加到你的程序包，你必须拥有一个 .pfx 文件格式的私钥的有效证书，才能对包进行签名和保护。</span><span class="sxs-lookup"><span data-stu-id="edcbc-130">To add the certificate to your package, you must have a valid certificate with the private key in a .pfx file format to sign and protect the package.</span></span> <span data-ttu-id="edcbc-131">选择 " **+ 证书保护"。**</span><span class="sxs-lookup"><span data-stu-id="edcbc-131">Select **+ Certificate Protection.**</span></span> <br>
![\* 选择 + 证书保护 \*](images/sh2-uefi2.png) <br><br>
3. <span data-ttu-id="edcbc-133">输入证书的专用密钥密码。</span><span class="sxs-lookup"><span data-stu-id="edcbc-133">Enter the certificate’s private key’s password.</span></span><br>
![\* 输入证书的专用密钥的密码 \*](images/sh2-uefi3.png) <br><br>
4. <span data-ttu-id="edcbc-135">导入私钥后，继续创建程序包。</span><span class="sxs-lookup"><span data-stu-id="edcbc-135">After importing the private key, continue creating the package.</span></span><br>
![\* 继续创建程序包 \*](images/sh2-uefi4.png) <br><br>
5. <span data-ttu-id="edcbc-137">选择 "**中心**" 和 " **Surface hub** 2" 作为 UEFI 配置包的目标。</span><span class="sxs-lookup"><span data-stu-id="edcbc-137">Choose **Hub** and **Surface Hub 2S** as the target for the UEFI configuration package.</span></span><br>
![\* 选择 "中心" 和 "Surface Hub 2" 作为 UEFI 配置包的目标 \*](images/sh2-uefi5.png) <br><br>
6. <span data-ttu-id="edcbc-139">选择要在 Surface Hub 2 秒上激活或停用的组件和设置。</span><span class="sxs-lookup"><span data-stu-id="edcbc-139">Choose the components and settings you want to activate or deactivate on Surface Hub 2S.</span></span><br>
![\* 选择要激活或停用的组件和设置 \*](images/sh2-uefi6.png) <br><br>
7. <span data-ttu-id="edcbc-141">使用 USB 选项导出文件。</span><span class="sxs-lookup"><span data-stu-id="edcbc-141">Use the USB option to export the file.</span></span><br>
![\* 使用 USB 选项导出文件 \*](images/sh2-uefi8.png) <br><br>
8. <span data-ttu-id="edcbc-143">插入并选择要用于此程序包的 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="edcbc-143">Insert and choose the USB drive you’d like to use for this package.</span></span> <span data-ttu-id="edcbc-144">将设置 USB 驱动器的格式，并丢失您所拥有的任何信息。</span><span class="sxs-lookup"><span data-stu-id="edcbc-144">The USB drive will be formatted and you lose any information you have on it.</span></span><br>
![\* 插入并选择软件包的 USB 驱动器 \*](images/sh2-uefi9.png) <br><br>
9. <span data-ttu-id="edcbc-146">成功创建程序包后，配置器将显示你的证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="edcbc-146">Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint.</span></span> <span data-ttu-id="edcbc-147">当你将配置导入到 Surface Hub 2 的配置时，你需要这些字符。</span><span class="sxs-lookup"><span data-stu-id="edcbc-147">You need these characters when you import to the configuration to Surface Hub 2S.</span></span><br>
![\* 程序包的成功配置 \*](images/sh2-uefi10.png) <br>

## <span data-ttu-id="edcbc-149">启动到 UEFI</span><span class="sxs-lookup"><span data-stu-id="edcbc-149">To boot into UEFI</span></span>

<span data-ttu-id="edcbc-150">关闭 Surface Hub 2。</span><span class="sxs-lookup"><span data-stu-id="edcbc-150">Turn off Surface Hub 2S.</span></span> <span data-ttu-id="edcbc-151">长按**音量**按钮并按**电源**按钮。</span><span class="sxs-lookup"><span data-stu-id="edcbc-151">Press and hold the **Volume Up** button and press the **Power** Button.</span></span> <span data-ttu-id="edcbc-152">一直按住音量按钮，直到 UEFI 菜单出现。</span><span class="sxs-lookup"><span data-stu-id="edcbc-152">Keep holding the Volume Up button until the UEFI menu appears.</span></span>

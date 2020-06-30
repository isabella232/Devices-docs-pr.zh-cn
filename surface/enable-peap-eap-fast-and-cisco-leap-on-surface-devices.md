---
title: 在 Surface 设备上启用 PEAP、EAP-FAST 和 Cisco LEAP (Surface)
description: 了解如何在你的 Surface 设备上启用对 PEAP、EAP-FAST 或 Cisco LEAP 协议的支持。
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: 网络, 无线, 设备, 部署, 身份验证, 协议
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831712"
---
# <span data-ttu-id="3ad7b-104">在 Surface 设备上启用 PEAP、EAP-FAST 和 Cisco LEAP</span><span class="sxs-lookup"><span data-stu-id="3ad7b-104">Enable PEAP, EAP-FAST, and Cisco LEAP on Surface devices</span></span>


<span data-ttu-id="3ad7b-105">了解如何在你的 Surface 设备上启用对 PEAP、EAP-FAST 或 Cisco LEAP 协议的支持。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-105">Find out how to enable support for PEAP, EAP-FAST, or Cisco LEAP protocols on your Surface device.</span></span>

<span data-ttu-id="3ad7b-106">如果你在你的企业网络中使用 PEAP、EAP-FAST 或 Cisco LEAP，你可能已经了解这三种无线身份验证协议不受全新 Surface 设备支持。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-106">If you use PEAP, EAP-FAST, or Cisco LEAP in your enterprise network, you probably already know that these three wireless authentication protocols are not supported by Surface devices out of the box.</span></span> <span data-ttu-id="3ad7b-107">一些用户在尝试连接到无线网络时可能会发现此情况；另一些用户在无法获取对网络内资源（例如文件共享和内部站点）的访问权限时可能会发现此情况。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-107">Some users may discover this when they attempt to connect to your wireless network; others may discover it when they are unable to gain access to resources inside the network, like file shares and internal sites.</span></span> <span data-ttu-id="3ad7b-108">有关详细信息，请参阅[可扩展身份验证协议](https://technet.microsoft.com/network/bb643147)。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-108">For more information, see [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).</span></span>

<span data-ttu-id="3ad7b-109">你可以通过从 U 盘或文件共享执行较小的 MSI 程序包来添加对每个协议的支持。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-109">You can add support for each protocol by executing a small MSI package from a USB stick or from a file share.</span></span> <span data-ttu-id="3ad7b-110">对于想要在其 Surface 设备上启用 EAP 支持的组织，MSI 程序包格式支持具有许多管理和部署工具（如 Microsoft 部署工具包（MDT）和 Microsoft 终结点配置管理器）的部署。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-110">For organizations that want to enable EAP support on their Surface devices, the MSI package format supports deployment with many management and deployment tools, like the Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager.</span></span>

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a><span data-ttu-id="3ad7b-111">下载 PEAP、EAP-FAST 或 Cisco LEAP 安装文件</span><span class="sxs-lookup"><span data-stu-id="3ad7b-111">Download PEAP, EAP-FAST, or Cisco LEAP installation files</span></span>


<span data-ttu-id="3ad7b-112">你可以从 Microsoft 下载中心针对单个 zip 存档文件中的 EAP、EAP-FAST 或 Cisco LEAP 下载 MSI 安装文件。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-112">You can download the MSI installation files for PEAP, EAP-FAST, or Cisco LEAP in a single zip archive file from the Microsoft Download Center.</span></span> <span data-ttu-id="3ad7b-113">若要下载此文件，请转到 Microsoft 下载中心的[适用于 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)页、单击**下载**，然后选择 **Cisco EAP-Supplicant Installer.zip** 文件。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-113">To download this file, go to the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center, click **Download**, and then select the **Cisco EAP-Supplicant Installer.zip** file.</span></span>

## <span data-ttu-id="3ad7b-114">使用 MDT 部署 PEAP、EAP-FAST 或 Cisco LEAP</span><span class="sxs-lookup"><span data-stu-id="3ad7b-114">Deploy PEAP, EAP-FAST, or Cisco LEAP with MDT</span></span>


<span data-ttu-id="3ad7b-115">如果你已在你的组织中执行到 Surface 设备的 Windows 部署，则可以在部署期间快速轻松地将每个协议的安装文件添加到部署共享并配置自动安装。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-115">If you are already performing a Windows deployment to Surface devices in your organization, it is quick and easy to add the installation files for each protocol to your deployment share and configure automatic installation during deployment.</span></span> <span data-ttu-id="3ad7b-116">甚至可以配置用于更新之前已部署的 Surface 设备的任务序列，从而可以使用相同的过程提供对这些协议的支持。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-116">You can even configure a task sequence that updates previously deployed Surface devices to provide support for these protocols using the same process.</span></span>

<span data-ttu-id="3ad7b-117">若要在新部署的 Surface 设备上启用对 PEAP、EAP-FAST 或 Cisco LEAP 的支持，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="3ad7b-117">To enable support for PEAP, EAP-FAST, or Cisco LEAP on newly deployed Surface devices, follow these steps:</span></span>

1.  <span data-ttu-id="3ad7b-118">下载每个协议的安装文件并将其解压缩到某一可轻松访问的位置中的单个文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-118">Download and extract the installation files for each protocol to separate folders in an easily accessible location.</span></span>

2.  <span data-ttu-id="3ad7b-119">打开 MDT 部署工作台并将部署共享展开到**应用程序**文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-119">Open the MDT Deployment Workbench and expand your deployment share to the **Applications** folder.</span></span>

3.  <span data-ttu-id="3ad7b-120">从**操作**窗格中选择**新建应用程序**。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-120">Select **New Application** from the **Action** pane.</span></span>

4.  <span data-ttu-id="3ad7b-121">选择**具有源文件的应用程序**以将 MSI 文件复制到部署共享中。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-121">Choose **Application with source files** to copy the MSI files into the Deployment Share.</span></span>

5.  <span data-ttu-id="3ad7b-122">针对所需的协议选择步骤 1 中所创建的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-122">Select the folder you created in step 1 for the desired protocol.</span></span>

6.  <span data-ttu-id="3ad7b-123">对将在其中存储安装文件的部署共享中的文件夹进行命名。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-123">Name the folder in the deployment share where the installation files will be stored.</span></span>

7.  <span data-ttu-id="3ad7b-124">指定要用于部署应用程序的命令行：</span><span class="sxs-lookup"><span data-stu-id="3ad7b-124">Specify the command line to deploy the application:</span></span>

    -   <span data-ttu-id="3ad7b-125">对于 PEAP，请使用 **EAP-PEAP.msi /qn /norestart**。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-125">For PEAP use **EAP-PEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="3ad7b-126">对于 LEAP，请使用 **EAP-LEAP.msi /qn /norestart**。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-126">For LEAP use **EAP-LEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="3ad7b-127">对于 EAP-FAST，请使用 **EAP-FAST.msi /qn /norestart**。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-127">For EAP-FAST use **EAP-FAST.msi /qn /norestart**.</span></span>

8.  <span data-ttu-id="3ad7b-128">使用默认选项完成“新建应用程序”向导。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-128">Use the default options to complete the New Application Wizard.</span></span>

9.  <span data-ttu-id="3ad7b-129">针对每个所需的协议重复步骤 3 到步骤 8。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-129">Repeat steps 3 through 8 for each desired protocol.</span></span>

<span data-ttu-id="3ad7b-130">在执行这些步骤以将三个 MSI 程序包作为应用程序导入到 MDT 后，它们将在 Windows 部署向导的“应用程序”页中可供选择。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-130">After you’ve performed these steps to import the three MSI packages as applications into MDT, they will be available for selection in the Applications page of the Windows Deployment Wizard.</span></span> <span data-ttu-id="3ad7b-131">尽管在一些简单的部署方案中这足以让技术人员在部署时选择每个程序包，但这并非推荐的做法。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-131">Although in some simple deployment scenarios it might be sufficient to have technicians select each package at the time of deployment, it is not recommended.</span></span> <span data-ttu-id="3ad7b-132">此做法允许技术人员尝试将这些程序包应用到 Surface 设备以外的计算机，或由于人为错误而使得 Surface 设备可以在没有 EAP 支持的情况下进行部署。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-132">This practice introduces the possibility that a technician could attempt to apply these packages to computers other than Surface devices, or that a Surface device could be deployed without EAP support due to human error.</span></span>

<span data-ttu-id="3ad7b-133">若要从“安装应用程序”页中隐藏这些应用程序，请在每个应用程序的属性中选中**在部署向导中隐藏此应用程序**复选框。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-133">To hide these applications from the Install Applications page, select the **Hide this application in the Deployment Wizard** checkbox in the properties of each application.</span></span> <span data-ttu-id="3ad7b-134">在应用程序处于隐藏状态后，它们将不会在部署期间显示为可选应用程序。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-134">After the applications are hidden, they will not be displayed as optional applications during deployment.</span></span> <span data-ttu-id="3ad7b-135">若要在 Surface 部署任务序列中部署它们，必须通过任务序列中的单独步骤针对安装进行显式定义。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-135">To deploy them in your Surface deployment task sequence, they must be explicitly defined for installation through a separate step in the task sequence.</span></span>

<span data-ttu-id="3ad7b-136">若要显式指定协议，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="3ad7b-136">To specify the protocol(s) explicitly, follow these steps:</span></span>

1.  <span data-ttu-id="3ad7b-137">从 MDT 部署工作台打开你的 Surface 部署任务序列属性。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-137">Open your Surface deployment task sequence properties from the MDT Deployment Workbench.</span></span>

2.  <span data-ttu-id="3ad7b-138">在**任务序列**选项卡上，在**状态还原**下选择**安装应用程序**步骤。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-138">On the **Task Sequence** tab, select the **Install Applications** step under **State Restore**.</span></span> <span data-ttu-id="3ad7b-139">这通常可以在应用程序安装前和应用程序安装后 Windows 更新步骤之间找到。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-139">This is typically found between the pre-application and post-application Windows Update steps.</span></span>

3.  <span data-ttu-id="3ad7b-140">使用**添加**按钮，从**常规**类别创建一个新的**安装应用程序**步骤。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-140">Use the **Add** button to create a new **Install Application** step from the **General** category.</span></span>

4.  <span data-ttu-id="3ad7b-141">在步骤**属性**选项卡中选择**安装单个应用程序**。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-141">Select **Install a single application** in the step **Properties** tab.</span></span>

5.  <span data-ttu-id="3ad7b-142">从列表中选择所需的 EAP 协议。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-142">Select the desired EAP protocol from the list.</span></span>

6.  <span data-ttu-id="3ad7b-143">针对每个所需的协议重复步骤 2 到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-143">Repeat steps 2 through 5 for each desired protocol.</span></span>

## <span data-ttu-id="3ad7b-144">使用配置管理器部署 PEAP、EAP-FAST 或 Cisco LEAP</span><span class="sxs-lookup"><span data-stu-id="3ad7b-144">Deploy PEAP, EAP-FAST, or Cisco LEAP with Configuration Manager</span></span>


<span data-ttu-id="3ad7b-145">对于使用配置管理器管理 Surface 设备的组织，可以更轻松地将 PEAP、EAP-FAST 或 Cisco LEAP支持部署到 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-145">For organizations that manage Surface devices with Configuration Manager, it is even easier to deploy PEAP, EAP-FAST, or Cisco LEAP support to Surface devices.</span></span> <span data-ttu-id="3ad7b-146">只需从软件库导入每个 MSI 文件作为应用程序并将部署配置为你的 Surface 设备集合。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-146">Simply import each MSI file as an application from the Software Library and configure a deployment to your Surface device collection.</span></span>

<span data-ttu-id="3ad7b-147">有关如何使用配置管理器部署应用程序的详细信息，请参阅[如何在配置管理器中创建应用程序](https://technet.microsoft.com/library/gg682159.aspx)和[如何在配置管理器中部署应用程序](https://technet.microsoft.com/library/gg682082.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3ad7b-147">For more information on how to deploy applications with Configuration Manager see [How to Create Applications in Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) and [How to Deploy Applications in Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span></span>

 

 






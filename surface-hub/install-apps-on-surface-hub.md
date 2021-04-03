---
title: 在 Microsoft Surface Hub 上安装应用
description: 管理员可以安装来自 Microsoft Store 或适用于企业的 Microsoft 应用商店的应用。
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: 安装应用, Microsoft Store, 适用于企业的 Microsoft 应用商店
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: a6e791defed4970b9a1940580b5f80bbe4f006a4
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470470"
---
# <a name="install-apps-on-your-microsoft-surface-hub"></a><span data-ttu-id="3b8d1-104">在 Microsoft Surface Hub 上安装应用</span><span class="sxs-lookup"><span data-stu-id="3b8d1-104">Install apps on your Microsoft Surface Hub</span></span>

<span data-ttu-id="3b8d1-105">可在 Surface Hub 上安装其他应用，以满足团队或组织需要。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-105">You can install additional apps on your Surface Hub to fit your team or organization's needs.</span></span> <span data-ttu-id="3b8d1-106">可使用不同方法安装应用，具体取决于是否在开发和测试应用，或者是否在部署已发布的应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-106">There are different methods for installing apps depending on whether you are developing and testing an app, or deploying a released app.</span></span> <span data-ttu-id="3b8d1-107">本主题介绍为其中一种方案安装应用的方法。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-107">This topic describes methods for installing apps for either scenario.</span></span>

<span data-ttu-id="3b8d1-108">了解以下有关 Surface Hub 应用的一些事项：</span><span class="sxs-lookup"><span data-stu-id="3b8d1-108">A few things to know about apps on Surface Hub:</span></span>
- <span data-ttu-id="3b8d1-109">Surface Hub 仅运行[通用 Windows 平台 (UWP) 应用](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-109">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="3b8d1-110">无法在 Surface Hub 上运行使用 [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) 创建的应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-110">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="3b8d1-111">应用必须面向[通用设备系列](https://msdn.microsoft.com/library/windows/apps/dn894631)或 Windows 团队设备系列。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-111">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="3b8d1-112">Surface Hub 仅支持来自适用于企业 [Microsoft](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) [Store 的离线授权应用](https://businessstore.microsoft.com/store)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-112">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="3b8d1-113">默认情况下，应用必须经过应用商店签名才能安装。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-113">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="3b8d1-114">在测试和开发时，还可以选择运行开发人员签名的 UWP 应用，使设备进入开发人员模式即可。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-114">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="3b8d1-115">将应用提交到 Microsoft Store 时，开发人员需要设置设备系列可用性和组织许可选项，以确保应用可在 Surface Hub 上运行。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-115">When submitting an app to the Microsoft Store, developers need to set Device family availability and Organizational licensing options to make sure an app will be available to run on Surface Hub.</span></span>
- <span data-ttu-id="3b8d1-116">在 Surface Hub 上安装应用需要管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-116">You need admin credentials to install apps on your Surface Hub.</span></span> <span data-ttu-id="3b8d1-117">由于设备要在公用空间（例如会议室）中使用，用户无法访问 Microsoft Store 以下载和安装应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-117">Since the device is designed to be used in communal spaces like meeting rooms, people can't access the Microsoft Store to download and install apps.</span></span>


## <a name="develop-and-test-apps"></a><span data-ttu-id="3b8d1-118">开发和测试应用</span><span class="sxs-lookup"><span data-stu-id="3b8d1-118">Develop and test apps</span></span>
<span data-ttu-id="3b8d1-119">开发自己的应用时，有几种在 Surface Hub 上测试应用的选项。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-119">While you're developing your own app, there are a few options for testing apps on Surface Hub.</span></span>

### <a name="developer-mode"></a><span data-ttu-id="3b8d1-120">开发人员模式</span><span class="sxs-lookup"><span data-stu-id="3b8d1-120">Developer Mode</span></span>
<span data-ttu-id="3b8d1-121">默认情况下，Surface Hub 仅运行发布到 Microsoft Store 并由其进行签名的 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-121">By default, Surface Hub only runs UWP apps that have been published to and signed by the Microsoft Store.</span></span> <span data-ttu-id="3b8d1-122">作为[应用认证过程](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process)的一部分，提交到 Microsoft Store 的应用将进行安全和合规性测试，这可有助于保护 Surface Hub 不受恶意应用的攻击。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-122">Apps submitted to the Microsoft Store go through security and compliance tests as part of the [app certification process](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process), so this helps safeguard your Surface Hub against malicious apps.</span></span>
 
<span data-ttu-id="3b8d1-123">启用开发人员模式还可安装开发人员签名的 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-123">By enabling developer mode, you can also install developer-signed UWP apps.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="3b8d1-124">在启用开发人员模式后，需要重置 Surface Hub 才能禁用该模式。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-124">After developer mode has been enabled, you will need to reset the Surface Hub to disable it.</span></span> <span data-ttu-id="3b8d1-125">重置设备将删除所有本地用户文件和配置，然后重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-125">Resetting the device removes all local user files and configurations and then reinstalls Windows.</span></span>

**<span data-ttu-id="3b8d1-126">打开开发人员模式</span><span class="sxs-lookup"><span data-stu-id="3b8d1-126">To turn on developer mode</span></span>** 
1. <span data-ttu-id="3b8d1-127">在 Surface Hub 中，启动“设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-127">From your Surface Hub, start **Settings**.</span></span>
2. <span data-ttu-id="3b8d1-128">请在系统提示时，键入该设备的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-128">Type the device admin credentials when prompted.</span></span>
3. <span data-ttu-id="3b8d1-129">导航到“更新和安全”\*\*\*\* > “对于开发人员”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-129">Navigate to **Update & security** > **For developers**.</span></span>
4. <span data-ttu-id="3b8d1-130">选择“开发人员模式”\*\*\*\* 并接受警告提示。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-130">Select **Developer mode** and accept the warning prompt.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="3b8d1-131">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3b8d1-131">Visual Studio</span></span>
<span data-ttu-id="3b8d1-132">开发时，在 Surface Hub 上测试应用的最简方法是使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-132">During development, the easiest way to test your app on a Surface Hub is using Visual Studio.</span></span> <span data-ttu-id="3b8d1-133">Visual Studio 的远程调试功能有助于在应用广泛部署之前发现其中的问题。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-133">Visual Studio's remote debugging feature helps you discover issues in your app before deploying it broadly.</span></span> <span data-ttu-id="3b8d1-134">有关详细信息，请参阅[使用 Visual Studio 测试 Surface Hub 应用](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-134">For more information, see [Test Surface Hub apps using Visual Studio](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio).</span></span>

### <a name="provisioning-package"></a><span data-ttu-id="3b8d1-135">设置包</span><span class="sxs-lookup"><span data-stu-id="3b8d1-135">Provisioning package</span></span>
<span data-ttu-id="3b8d1-136">使用 Visual Studio 为 UWP 应用[创建应用包](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx)，并且使用测试证书签名。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-136">Use Visual Studio to [create an app package](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx) for your UWP app, signed using a test certificate.</span></span> <span data-ttu-id="3b8d1-137">然后使用 Windows 映像和配置设计器 (ICD) 创建包含该应用包的设置包。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-137">Then use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package.</span></span> <span data-ttu-id="3b8d1-138">有关详细信息，请参阅[创建设置包](provisioning-packages-for-certificates-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-138">For more information, see [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md).</span></span>


## <a name="submit-apps-to-the-microsoft-store"></a><span data-ttu-id="3b8d1-139">向 Microsoft Store 提交应用</span><span class="sxs-lookup"><span data-stu-id="3b8d1-139">Submit apps to the Microsoft Store</span></span>
<span data-ttu-id="3b8d1-140">在准备好发布应用后，开发人员需要将其提交并发布到 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-140">Once an app is ready for release, developers need to submit and publish it to the Microsoft Store.</span></span> <span data-ttu-id="3b8d1-141">有关详细信息，请参阅[发布 Windows 应用](https://developer.microsoft.com/store/publish-apps)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-141">For more information, see [Publish Windows apps](https://developer.microsoft.com/store/publish-apps).</span></span>

<span data-ttu-id="3b8d1-142">提交应用时，开发人员需要设置**设备系列可用性**和**组织授权**选项，确保该应用可在 Surface Hub 上运行。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-142">During app submission, developers need to set **Device family availability** and **Organizational licensing** options to make sure the app will be available to run on Surface Hub.</span></span>

**<span data-ttu-id="3b8d1-143">设置设备系列可用性</span><span class="sxs-lookup"><span data-stu-id="3b8d1-143">To set device family availability</span></span>**

1. <span data-ttu-id="3b8d1-144">在 [Windows 开发人员中心](https://developer.microsoft.com)上，导航到应用提交页面。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-144">On the [Windows Dev Center](https://developer.microsoft.com), navigate to your app submission page.</span></span>

2. <span data-ttu-id="3b8d1-145">选择“程序包”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-145">Select **Packages**.</span></span>
3. <span data-ttu-id="3b8d1-146">在**设备系列可用性**下，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="3b8d1-146">Under **Device family availability**, select these options:</span></span>
    
    - **<span data-ttu-id="3b8d1-147">Windows 10 协同版</span><span class="sxs-lookup"><span data-stu-id="3b8d1-147">Windows 10 Team</span></span>**
    - **<span data-ttu-id="3b8d1-148">让 Microsoft 决定是否使应用可用于以后任何设备系列</span><span class="sxs-lookup"><span data-stu-id="3b8d1-148">Let Microsoft decide whether to make the app available to any future device families</span></span>**
  
   ![显示“设备系列可用性”页面的图像 - Microsoft Store 应用提交过程的一部分。](images/device-family.png)  
    
   <span data-ttu-id="3b8d1-150">有关详细信息，请参阅[设备系列可用性](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-150">For more information, see [Device family availability](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability).</span></span>

**<span data-ttu-id="3b8d1-151">设置组织授权</span><span class="sxs-lookup"><span data-stu-id="3b8d1-151">To set organizational licensing</span></span>**

1. <span data-ttu-id="3b8d1-152">在 [Windows 开发人员中心](https://developer.microsoft.com)上，导航到应用提交页面。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-152">On the [Windows Dev Center](https://developer.microsoft.com), navigate to your app submission page.</span></span>

2. <span data-ttu-id="3b8d1-153">选择“定价和可用性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-153">Select **Pricing and availability**.</span></span>

3. <span data-ttu-id="3b8d1-154">在“组织授权”下，选择**允许组织断开连接(脱机)授权**。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-154">Under Organizational licensing, select **Allow disconnected (offline) licensing for organizations**.</span></span>

   ![显示“组织授权”页面的图像 - Microsoft Store 应用提交过程的一部分。](images/sh-org-licensing.png)

   > [!NOTE]
   > <span data-ttu-id="3b8d1-156">默认情况下，**使我的应用可用于带有应用商店托管(联机)许可和分发的组织**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-156">**Make my app available to organizations with Store-managed (online) licensing and distribution** is selected by default.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3b8d1-157">开发人员还可直接将业务线应用发布到企业，无需在应用商店中广泛提供。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-157">Developers can also publish line-of-business apps directly to enterprises without making them broadly available in the Store.</span></span> <span data-ttu-id="3b8d1-158">有关详细信息，请参阅[向企业分配 LOB 应用](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-158">For more information, see [Distribute LOB apps to enterprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises).</span></span>

   <span data-ttu-id="3b8d1-159">有关详细信息，请参阅[组织授权选项](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-159">For more information, see [Organizational licensing options](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing).</span></span>


## <a name="deploy-released-apps"></a><span data-ttu-id="3b8d1-160">部署发布的应用</span><span class="sxs-lookup"><span data-stu-id="3b8d1-160">Deploy released apps</span></span>

<span data-ttu-id="3b8d1-161">有几种选项可安装已发布到 Microsoft Store 的应用，具体取决于是否要在几台设备上评估它们，或者是否要将它们广泛部署到组织。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-161">There are several options for installing apps that have been released to the Microsoft Store, depending on whether you want to evaluate them on a few devices, or deploy them broadly to your organization.</span></span>

<span data-ttu-id="3b8d1-162">若要安装发布的应用：</span><span class="sxs-lookup"><span data-stu-id="3b8d1-162">To install released apps:</span></span>
- <span data-ttu-id="3b8d1-163">使用 Microsoft Store 应用下载应用，或者</span><span class="sxs-lookup"><span data-stu-id="3b8d1-163">Download the app using the Microsoft Store app, or</span></span>
- <span data-ttu-id="3b8d1-164">从适用于企业的 Microsoft 应用商店中下载应用包，并使用设置包或受支持的 MDM 提供程序分配。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-164">Download the app package from the Microsoft Store for Business, and distribute it using a provisioning package or a supported MDM provider.</span></span>

### <a name="microsoft-store-app"></a><span data-ttu-id="3b8d1-165">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="3b8d1-165">Microsoft Store app</span></span>
<span data-ttu-id="3b8d1-166">若要评估在 Microsoft Store 中发布的应用，请在 Surface Hub 上使用 Microsoft Store 应用浏览和下载应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-166">To evaluate apps released on the Microsoft Store, use the Microsoft Store app on the Surface Hub to browse and download apps.</span></span>

> [!NOTE]
> <span data-ttu-id="3b8d1-167">将应用大规模部署到组织时不推荐使用 Microsoft Store 应用：</span><span class="sxs-lookup"><span data-stu-id="3b8d1-167">Using the Microsoft Store app is not the recommended method of deploying apps at scale to your organization:</span></span>
> - <span data-ttu-id="3b8d1-168">若要下载应用，必须使用 Microsoft 帐户或组织帐户登录 Microsoft Store 应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-168">To download apps, you must sign in to the Microsoft Store app with a Microsoft account or organizational account.</span></span> <span data-ttu-id="3b8d1-169">但是，一个帐户同一时间只能连接最多 10 台设备。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-169">However, you can only connect an account to a maximum of 10 devices at once.</span></span> <span data-ttu-id="3b8d1-170">如果拥有超过 10 台 Surface Hub，则需要创建多个帐户，或者在安装应用间隙从帐户中删除设备。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-170">If you have more than 10 Surface Hubs, you will need to create multiple accounts or remove devices from your account between app installations.</span></span>
> - <span data-ttu-id="3b8d1-171">若要安装应用，需要在拥有的每台 Surface Hub 上手动登录 Microsoft Store 应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-171">To install apps, you will need to manually sign in to the Microsoft Store app on each Surface Hub you own.</span></span>

**<span data-ttu-id="3b8d1-172">在 Surface Hub 上浏览 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="3b8d1-172">To browse the Microsoft Store on Surface Hub</span></span>** 
1. <span data-ttu-id="3b8d1-173">在 Surface Hub 中，启动**设置**。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-173">From your Surface Hub, start **Settings**.</span></span>
2. <span data-ttu-id="3b8d1-174">请在系统提示时，键入该设备的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-174">Type the device admin credentials when prompted.</span></span>
3. <span data-ttu-id="3b8d1-175">导航到“此设备”\*\*\*\* > “应用和功能”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-175">Navigate to **This device** > **Apps & features**.</span></span>
4. <span data-ttu-id="3b8d1-176">选择**打开应用商店**。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-176">Select **Open Store**.</span></span>

### <a name="download-app-packages-from-microsoft-store-for-business"></a><span data-ttu-id="3b8d1-177">从适用于企业的 Microsoft 应用商店中下载应用包</span><span class="sxs-lookup"><span data-stu-id="3b8d1-177">Download app packages from Microsoft Store for Business</span></span>
<span data-ttu-id="3b8d1-178">若要下载在 Surface Hub 上安装应用所需的应用包，请访问[适用于企业的 Microsoft 应用商店](https://www.microsoft.com/business-store)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-178">To download the app package you need to install apps on your Surface Hub, visit the [Microsoft Store for Business](https://www.microsoft.com/business-store).</span></span> <span data-ttu-id="3b8d1-179">可在适用于企业的应用商店中为组织的 Windows10 设备（包括 Surface Hub）查找、获取和管理应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-179">The Store for Business is where you can find, acquire, and manage apps for the Windows 10 devices in your organization, including Surface Hub.</span></span>
 
> [!NOTE]
> <span data-ttu-id="3b8d1-180">Surface Hub 当前仅支持通过适用于企业的应用商店获取的脱机授权应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-180">Currently, Surface Hub only supports offline-licensed apps available through the Store for Business.</span></span> <span data-ttu-id="3b8d1-181">应用开发人员在提交应用时设置脱机授权可用性。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-181">App developers set offline-license availability when they submit apps.</span></span>

<span data-ttu-id="3b8d1-182">查找并获取所需应用，然后下载：</span><span class="sxs-lookup"><span data-stu-id="3b8d1-182">Find and acquire the app you want, then download:</span></span>
- <span data-ttu-id="3b8d1-183">脱机授权的应用包（.appx 或 .appxbundle）</span><span class="sxs-lookup"><span data-stu-id="3b8d1-183">The offline-licensed app package (either an .appx or an .appxbundle)</span></span>
- <span data-ttu-id="3b8d1-184">*解码*许可文件（如果当前使用设置包安装应用）</span><span class="sxs-lookup"><span data-stu-id="3b8d1-184">The *unencoded* license file (if you're using provisioning packages to install the app)</span></span>
- <span data-ttu-id="3b8d1-185">*编码*许可文件（如果当前使用 MDM 分配应用）</span><span class="sxs-lookup"><span data-stu-id="3b8d1-185">The *encoded* license file (if you're using MDM to distribute the app)</span></span>
- <span data-ttu-id="3b8d1-186">任何必要的依赖关系文件</span><span class="sxs-lookup"><span data-stu-id="3b8d1-186">Any necessary dependency files</span></span>

<span data-ttu-id="3b8d1-187">有关详细信息，请参阅[下载脱机授权的应用](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-187">For more information, see [Download an offline-licensed app](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).</span></span>

### <a name="provisioning-package"></a><span data-ttu-id="3b8d1-188">设置包</span><span class="sxs-lookup"><span data-stu-id="3b8d1-188">Provisioning package</span></span>
<span data-ttu-id="3b8d1-189">在一些 Surface Hub 上可使用设置包手动安装从适用于企业的应用商店下载的脱机授权应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-189">You can manually install the offline-licensed apps that you downloaded from the Store for Business on a few Surface Hubs using provisioning packages.</span></span> <span data-ttu-id="3b8d1-190">使用 Windows 映像和配置设计器 (ICD) 创建设置包，该设置包含有应用包和从适用于企业的应用商店中下载的*已解码*许可文件。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-190">Use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package and *unencoded* license file that you downloaded from the Store for Business.</span></span> <span data-ttu-id="3b8d1-191">有关详细信息，请参阅[创建设置包](provisioning-packages-for-certificates-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-191">For more information, see [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md).</span></span>

### <a name="supported-mdm-provider"></a><span data-ttu-id="3b8d1-192">受支持的 MDM 提供程序</span><span class="sxs-lookup"><span data-stu-id="3b8d1-192">Supported MDM provider</span></span>
<span data-ttu-id="3b8d1-193">若要将应用部署到组织中的大量 Surface Hub，请使用受支持的 MDM 提供程序。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-193">To deploy apps to a large number of Surface Hubs in your organization, use a supported MDM provider.</span></span> <span data-ttu-id="3b8d1-194">下表显示支持部署脱机许可的应用包的 MDM 提供程序。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-194">The table below shows which MDM providers support deploying offline-licensed app packages.</span></span>

| <span data-ttu-id="3b8d1-195">MDM 提供程序</span><span class="sxs-lookup"><span data-stu-id="3b8d1-195">MDM provider</span></span>                | <span data-ttu-id="3b8d1-196">支持脱机授权的应用包</span><span class="sxs-lookup"><span data-stu-id="3b8d1-196">Supports offline-licensed app packages</span></span> |
|-----------------------------|----------------------------------------|
| <span data-ttu-id="3b8d1-197">从版本 1602 版本 (配置管理器本地 MDM) </span><span class="sxs-lookup"><span data-stu-id="3b8d1-197">On-premises MDM with  Configuration Manager (beginning in version 1602)</span></span> | <span data-ttu-id="3b8d1-198">是</span><span class="sxs-lookup"><span data-stu-id="3b8d1-198">Yes</span></span> |
|
| <span data-ttu-id="3b8d1-199">第三方 MDM 提供程序</span><span class="sxs-lookup"><span data-stu-id="3b8d1-199">Third-party MDM provider</span></span>    | <span data-ttu-id="3b8d1-200">查看以确保 MDM 提供程序支持部署脱机许可的应用包。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-200">Check to make sure your MDM provider supports deploying offline-licensed app packages.</span></span> |

**<span data-ttu-id="3b8d1-201">使用 Microsoft Endpoint Configuration Manager 远程部署应用</span><span class="sxs-lookup"><span data-stu-id="3b8d1-201">To deploy apps remotely using Microsoft Endpoint Configuration Manager</span></span>**

> [!NOTE]
> <span data-ttu-id="3b8d1-202">这些说明基于 Microsoft Endpoint Configuration Manager 的当前分支。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-202">These instructions are based on the current branch of Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="3b8d1-203">将 Surface Hub 注册到 MDM 管理中。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-203">Enroll your Surface Hubs into MDM management.</span></span> <span data-ttu-id="3b8d1-204">有关详细信息，请参阅使用[MDM 提供程序管理 Surface Hub。](manage-settings-with-mdm-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="3b8d1-204">For more information, see [Manage Surface Hub with an MDM provider](manage-settings-with-mdm-for-surface-hub.md).</span></span>

2. <span data-ttu-id="3b8d1-205">从适用于企业的应用商店下载脱机授权的应用包、*已编码的*许可文件以及任何所需依赖关系文件。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-205">Download the offline-licensed app package, the *encoded* license file, and any necessary dependency files from the Store for Business.</span></span> <span data-ttu-id="3b8d1-206">有关详细信息，请参阅[下载脱机授权的应用](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-206">For more information, see [Download an offline-licensed app](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).</span></span> <span data-ttu-id="3b8d1-207">将下载的文件放入网络共享上的相同文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-207">Place the downloaded files in the same folder on a network share.</span></span>

3. <span data-ttu-id="3b8d1-208">在 Configuration Manager 控制台的“软件库”\*\*\*\* 工作区中，单击“概述”\*\*\*\* > “应用程序管理”\*\*\*\* > “应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-208">In the **Software Library** workspace of the Configuration Manager console, click **Overview** > **Application Management** > **Applications**.</span></span>

4. <span data-ttu-id="3b8d1-209">在“主页”\*\*\*\* 选项卡的“创建”\*\*\*\* 组中，单击“创建应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-209">On the **Home** tab, in the **Create** group, click **Create Application**.</span></span>

5. <span data-ttu-id="3b8d1-210">在“创建应用程序向导”\*\*\*\* 的“常规”\*\*\*\* 页上，选中“自动检测安装文件中有关此应用程序的信息”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-210">On the **General** page of the **Create Application Wizard**, select the **Automatically detect information about this application from installation files** check box.</span></span>

6. <span data-ttu-id="3b8d1-211">在“类型”\*\*\*\* 下拉列表中，选择“Windows 应用包(\*.appx, \*.appxbundle)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-211">In the **Type** drop-down list, select **Windows app package (\*.appx, \*.appxbundle)**.</span></span>

7. <span data-ttu-id="3b8d1-212">在“位置”\*\*\*\* 字段中，为从适用于企业的应用商店中下载的脱机许可应用包指定 UNC 路径（形式为 \\server\share\\filename）。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-212">In the **Location** field, specify the UNC path in the form \\server\share\\filename for the offline-licensed app package that you downloaded from the Store for Business.</span></span> <span data-ttu-id="3b8d1-213">或者，单击“浏览”\*\*\*\*，浏览到应用包。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-213">Alternatively, click **Browse** to browse to the app package.</span></span>

8. <span data-ttu-id="3b8d1-214">在“导入信息”\*\*\*\* 页面上，查看导入的信息，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-214">On the **Import Information** page, review the information that was imported, and then click **Next**.</span></span> <span data-ttu-id="3b8d1-215">如果需要，可单击“上一步”\*\*\*\* 返回并更正任何错误。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-215">If necessary, you can click **Previous** to go back and correct any errors.</span></span>

9. <span data-ttu-id="3b8d1-216">在“常规信息”\*\*\*\* 页上，完成填写有关应用的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-216">On the **General Information** page, complete additional details about the app.</span></span> <span data-ttu-id="3b8d1-217">如果有些信息是自动从应用包中获取，则可能已经填充完成。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-217">Some of this information might already be populated if it was automatically obtained from the app package.</span></span>

10. <span data-ttu-id="3b8d1-218">单击“下一步”\*\*\*\*、在“摘要”页上查看应用程序信息，然后完成“创建应用程序向导”。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-218">Click **Next**, review the application information on the Summary page, and then complete the Create Application Wizard.</span></span> 

11. <span data-ttu-id="3b8d1-219">为应用程序创建部署类型。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-219">Create a deployment type for the application.</span></span> <span data-ttu-id="3b8d1-220">有关详细信息，请参阅[为应用程序创建部署类型](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-220">For more information, see [Create deployment types for the application](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application).</span></span>

12. <span data-ttu-id="3b8d1-221">将应用程序部署到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-221">Deploy the application to your Surface Hubs.</span></span> <span data-ttu-id="3b8d1-222">有关详细信息，请参阅使用 [Microsoft Endpoint Configuration Manager 部署应用程序](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-222">For more information, see [Deploy applications with Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications).</span></span>

13. <span data-ttu-id="3b8d1-223">根据需要更新应用，方法是从适用于企业的应用商店下载新程序包，然后在 Configuration Manager 中发布应用程序修订。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-223">As needed, update the app by downloading a new package from the Store for Business, and publishing an application revision in Configuration Manager.</span></span> <span data-ttu-id="3b8d1-224">有关详细信息，请参阅使用 [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt595704.aspx)更新和停用应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-224">For more information, see [Update and retire applications with Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt595704.aspx).</span></span> 

> [!NOTE] 
> <span data-ttu-id="3b8d1-225">如果你使用 Microsoft Endpoint Configuration Manager (当前分支) ，可以通过将适用于企业应用商店的应用商店连接到 Configuration Manager 来绕过上述步骤。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-225">If you are using Microsoft Endpoint Configuration Manager (current branch), you can bypass the above steps by connecting the Store for Business to Configuration Manager.</span></span> <span data-ttu-id="3b8d1-226">通过执行此操作，你可以同步使用 Configuration Manager 购买的应用列表，在 Configuration Manager 控制台中查看这些应用，并像部署任何其他应用一样部署它们。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-226">By doing so, you can synchronize the list of apps you've purchased with Configuration Manager, view these in the Configuration Manager console, and deploy them like you would any other app.</span></span> <span data-ttu-id="3b8d1-227">有关详细信息，请参阅使用 Configuration Manager 管理 [适用于企业](https://technet.microsoft.com/library/mt740630.aspx)Microsoft Store 的应用。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-227">For more information, see [Manage apps from the Microsoft Store for Business with Configuration Manager](https://technet.microsoft.com/library/mt740630.aspx).</span></span>


## <a name="summary"></a><span data-ttu-id="3b8d1-228">摘要</span><span class="sxs-lookup"><span data-stu-id="3b8d1-228">Summary</span></span>

<span data-ttu-id="3b8d1-229">有几种不同的方法在 Surface Hub 上安装应用，具体取决于你是在开发应用、在少量设备上评估应用，还是将应用广泛部署到你的组织。</span><span class="sxs-lookup"><span data-stu-id="3b8d1-229">There are a few different ways to install apps on your Surface Hub depending on whether you are developing apps, evaluating apps on a small number of devices, or deploying apps broadly to your organization.</span></span> <span data-ttu-id="3b8d1-230">此表总结了受支持的方法：</span><span class="sxs-lookup"><span data-stu-id="3b8d1-230">This table summarizes the supported methods:</span></span>

| <span data-ttu-id="3b8d1-231">安装方法</span><span class="sxs-lookup"><span data-stu-id="3b8d1-231">Install method</span></span>             | <span data-ttu-id="3b8d1-232">开发应用</span><span class="sxs-lookup"><span data-stu-id="3b8d1-232">Developing apps</span></span> | <span data-ttu-id="3b8d1-233">评估</span><span class="sxs-lookup"><span data-stu-id="3b8d1-233">Evaluating apps on</span></span> <br> <span data-ttu-id="3b8d1-234">几台设备上的应用</span><span class="sxs-lookup"><span data-stu-id="3b8d1-234">a few devices</span></span> | <span data-ttu-id="3b8d1-235">将应用广泛部署到</span><span class="sxs-lookup"><span data-stu-id="3b8d1-235">Deploying apps broadly</span></span> <br> <span data-ttu-id="3b8d1-236">组织</span><span class="sxs-lookup"><span data-stu-id="3b8d1-236">to your organization</span></span> |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| <span data-ttu-id="3b8d1-237">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3b8d1-237">Visual Studio</span></span>              | <span data-ttu-id="3b8d1-238">X</span><span class="sxs-lookup"><span data-stu-id="3b8d1-238">X</span></span> |   |   |
| <span data-ttu-id="3b8d1-239">设置包</span><span class="sxs-lookup"><span data-stu-id="3b8d1-239">Provisioning package</span></span>       | <span data-ttu-id="3b8d1-240">X</span><span class="sxs-lookup"><span data-stu-id="3b8d1-240">X</span></span> | <span data-ttu-id="3b8d1-241">X</span><span class="sxs-lookup"><span data-stu-id="3b8d1-241">X</span></span> |   |
| <span data-ttu-id="3b8d1-242">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="3b8d1-242">Microsoft Store app</span></span>          |   | <span data-ttu-id="3b8d1-243">X</span><span class="sxs-lookup"><span data-stu-id="3b8d1-243">X</span></span> |   |
| <span data-ttu-id="3b8d1-244">受支持的 MDM 提供程序</span><span class="sxs-lookup"><span data-stu-id="3b8d1-244">Supported MDM provider</span></span>     |   |   | <span data-ttu-id="3b8d1-245">X</span><span class="sxs-lookup"><span data-stu-id="3b8d1-245">X</span></span> |

## <a name="more-information"></a><span data-ttu-id="3b8d1-246">详细信息</span><span class="sxs-lookup"><span data-stu-id="3b8d1-246">More information</span></span>

- [<span data-ttu-id="3b8d1-247">博客文章: 使用 Intune 将 Microsoft Store 应用部署到 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="3b8d1-247">Blog post:  Deploy Windows Store apps to Surface Hub using Intune</span></span>](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## <a name="related-topics"></a><span data-ttu-id="3b8d1-248">相关主题</span><span class="sxs-lookup"><span data-stu-id="3b8d1-248">Related topics</span></span>

[<span data-ttu-id="3b8d1-249">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="3b8d1-249">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="3b8d1-250">Microsoft Surface Hub 管理员指南</span><span class="sxs-lookup"><span data-stu-id="3b8d1-250">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 






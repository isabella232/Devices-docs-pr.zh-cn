---
title: 将 Surface 应用部署到 Microsoft Store for Business 或 Microsoft Store for 教育版（Surface）
description: 了解如何在 Microsoft Store for Business 或 Microsoft Store for 教育中添加和下载 Surface 应用，以及安装具有 PowerShell 和 MDT 的 Surface 应用。
keywords: surface 应用、应用、部署、自定义
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830893"
---
# <span data-ttu-id="bc70f-104">将 Surface 应用部署到 Microsoft Store for Business 和教育版</span><span class="sxs-lookup"><span data-stu-id="bc70f-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="bc70f-105">适用范围</span><span class="sxs-lookup"><span data-stu-id="bc70f-105">Applies to</span></span>**

- <span data-ttu-id="bc70f-106">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="bc70f-106">Surface Pro 7</span></span>
- <span data-ttu-id="bc70f-107">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="bc70f-107">Surface Laptop 3</span></span>
- <span data-ttu-id="bc70f-108">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="bc70f-108">Surface Pro 6</span></span>
- <span data-ttu-id="bc70f-109">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="bc70f-109">Surface Laptop 2</span></span>
- <span data-ttu-id="bc70f-110">Surface Go</span><span class="sxs-lookup"><span data-stu-id="bc70f-110">Surface Go</span></span>
- <span data-ttu-id="bc70f-111">带有 LTE 的 Surface Go</span><span class="sxs-lookup"><span data-stu-id="bc70f-111">Surface Go with LTE</span></span>
- <span data-ttu-id="bc70f-112">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="bc70f-112">Surface Book 2</span></span>
- <span data-ttu-id="bc70f-113">带有 LTE Advanced 的 Surface Pro（型号 1807）</span><span class="sxs-lookup"><span data-stu-id="bc70f-113">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="bc70f-114">Surface Pro（型号 1796）</span><span class="sxs-lookup"><span data-stu-id="bc70f-114">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="bc70f-115">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="bc70f-115">Surface Laptop</span></span>
- <span data-ttu-id="bc70f-116">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="bc70f-116">Surface Studio</span></span>
- <span data-ttu-id="bc70f-117">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="bc70f-117">Surface Studio 2</span></span>
- <span data-ttu-id="bc70f-118">Surface Book</span><span class="sxs-lookup"><span data-stu-id="bc70f-118">Surface Book</span></span>
- <span data-ttu-id="bc70f-119">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="bc70f-119">Surface Pro 4</span></span>
- <span data-ttu-id="bc70f-120">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="bc70f-120">Surface 3 LTE</span></span>
- <span data-ttu-id="bc70f-121">Surface 3</span><span class="sxs-lookup"><span data-stu-id="bc70f-121">Surface 3</span></span>
- <span data-ttu-id="bc70f-122">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="bc70f-122">Surface Pro 3</span></span>


<span data-ttu-id="bc70f-123">Surface 应用是一种轻型 Microsoft Store 应用，可提供对许多特定于图面的设置和选项的控制，包括：</span><span class="sxs-lookup"><span data-stu-id="bc70f-123">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="bc70f-124">启用或禁用 Surface 设备上的 Windows 按钮</span><span class="sxs-lookup"><span data-stu-id="bc70f-124">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="bc70f-125">调整 Surface 触控笔的灵敏度</span><span class="sxs-lookup"><span data-stu-id="bc70f-125">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="bc70f-126">自定义 Surface 触控笔按钮操作</span><span class="sxs-lookup"><span data-stu-id="bc70f-126">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="bc70f-127">启用或禁用 Surface 音频增强功能</span><span class="sxs-lookup"><span data-stu-id="bc70f-127">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="bc70f-128">快速访问你的设备的支持文档和信息</span><span class="sxs-lookup"><span data-stu-id="bc70f-128">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="bc70f-129">使用 Windows 更新的客户通常会接收 Surface app 作为自动更新的一部分。</span><span class="sxs-lookup"><span data-stu-id="bc70f-129">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="bc70f-130">但是，如果你的组织准备将映像部署到 Surface 设备，你可能希望在你的映像和部署过程中包括 Surface 应用（以前称为 Surface Hub），而不是需要每个人设备的用户从 Microsoft Store 或 Microsoft Store for Business 下载和安装应用。</span><span class="sxs-lookup"><span data-stu-id="bc70f-130">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="bc70f-131">本文不适用于 Surface Pro X。有关详细信息，请参阅[部署、管理和维护 Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="bc70f-131">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="bc70f-132">Surface 应用概述</span><span class="sxs-lookup"><span data-stu-id="bc70f-132">Surface app overview</span></span>

<span data-ttu-id="bc70f-133">Surface app 可从[Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)免费下载。</span><span class="sxs-lookup"><span data-stu-id="bc70f-133">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="bc70f-134">用户可以从 Microsoft Store 下载并安装它，但如果您的组织使用的是 Microsoft store for Business，则需要将其添加到你的应用商店的库存，并且可能将应用包括在 Windows 部署过程中。</span><span class="sxs-lookup"><span data-stu-id="bc70f-134">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="bc70f-135">本文将讨论这些过程。</span><span class="sxs-lookup"><span data-stu-id="bc70f-135">These processes are discussed throughout this article.</span></span> <span data-ttu-id="bc70f-136">有关 Microsoft Store for Business 的详细信息，请参阅 Windows 技术中心中的[Microsoft store For business](https://docs.microsoft.com/microsoft-store/) 。</span><span class="sxs-lookup"><span data-stu-id="bc70f-136">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="bc70f-137">将 Surface 应用添加到 Microsoft Store for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="bc70f-137">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="bc70f-138">在用户可以从公司的 Microsoft Store for Business 帐户安装或部署应用之前，所需的应用首先必须提供，并授权给企业用户。</span><span class="sxs-lookup"><span data-stu-id="bc70f-138">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="bc70f-139">如果尚未执行此操作，请创建[Microsoft Store For Business 帐户](https://www.microsoft.com/business-store)。</span><span class="sxs-lookup"><span data-stu-id="bc70f-139">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="bc70f-140">登录到门户。</span><span class="sxs-lookup"><span data-stu-id="bc70f-140">Log on to the portal.</span></span> 

3. <span data-ttu-id="bc70f-141">启用脱机授权：单击 "**管理->存储设置**"，然后选择 "**向在应用商店中购物的用户显示脱机许可的应用**" 复选框，如图1所示。</span><span class="sxs-lookup"><span data-stu-id="bc70f-141">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="bc70f-142">有关 Microsoft Store for Business 应用许可模型的详细信息，请参阅[Microsoft store For business 和教育版中的应用](https://docs.microsoft.com/microsoft-store/)。</span><span class="sxs-lookup"><span data-stu-id="bc70f-142">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span><br/> <br/>
   !["显示脱机许可证应用" 复选框](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="bc70f-144">图 1.</span><span class="sxs-lookup"><span data-stu-id="bc70f-144">Figure 1.</span></span> <span data-ttu-id="bc70f-145">允许应用脱机使用</span><span class="sxs-lookup"><span data-stu-id="bc70f-145">Enable apps for offline use</span></span>*

4. <span data-ttu-id="bc70f-146">通过执行以下过程，将 Surface 应用添加到 Microsoft Store for Business 帐户：</span><span class="sxs-lookup"><span data-stu-id="bc70f-146">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>
    * <span data-ttu-id="bc70f-147">单击 "**商店**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="bc70f-147">Click the **Shop** menu.</span></span>
    * <span data-ttu-id="bc70f-148">在 "搜索" 框中，键入 " **Surface app**"，然后单击 "搜索" 图标。</span><span class="sxs-lookup"><span data-stu-id="bc70f-148">In the search box, type **Surface app**, and then click the search icon.</span></span>
    * <span data-ttu-id="bc70f-149">在搜索结果中显示 Surface 应用后，单击应用的图标。</span><span class="sxs-lookup"><span data-stu-id="bc70f-149">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    * <span data-ttu-id="bc70f-150">将显示一个选项（选择 "**联机**" 或 "**脱机**"），如图2所示。</span><span class="sxs-lookup"><span data-stu-id="bc70f-150">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span><br/><br/>
    
    ![选择脱机授权模式并将应用添加到你的库存](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *<span data-ttu-id="bc70f-152">图 2.</span><span class="sxs-lookup"><span data-stu-id="bc70f-152">Figure 2.</span></span> <span data-ttu-id="bc70f-153">选择脱机授权模式并将应用添加到你的库存</span><span class="sxs-lookup"><span data-stu-id="bc70f-153">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="bc70f-154">单击 "**脱机**" 以选择脱机授权模式。</span><span class="sxs-lookup"><span data-stu-id="bc70f-154">Click **Offline** to select the Offline licensing mode.</span></span>
    * <span data-ttu-id="bc70f-155">单击 **"获取应用**" 以将应用添加到 Microsoft Store for Business 库存。</span><span class="sxs-lookup"><span data-stu-id="bc70f-155">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="bc70f-156">如图3所示，你将看到一个对话框，提示你确认可以使用管理工具部署脱机应用，或者从其私人存储中的公司的库存页面下载。</span><span class="sxs-lookup"><span data-stu-id="bc70f-156">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
    ![脱机许可的应用确认窗口](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *<span data-ttu-id="bc70f-158">图 3.</span><span class="sxs-lookup"><span data-stu-id="bc70f-158">Figure 3.</span></span> <span data-ttu-id="bc70f-159">脱机授权应用确认</span><span class="sxs-lookup"><span data-stu-id="bc70f-159">Offline-licensed app acknowledgement</span></span>*
    * <span data-ttu-id="bc70f-160">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bc70f-160">Click **OK**.</span></span>

## <span data-ttu-id="bc70f-161">从 Microsoft Store for Business 帐户下载 Surface 应用</span><span class="sxs-lookup"><span data-stu-id="bc70f-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="bc70f-162">在脱机模式下将应用添加到 Microsoft Store for Business 帐户之后，你可以将该应用作为 .Appxbundle 下载并添加到部署共享。</span><span class="sxs-lookup"><span data-stu-id="bc70f-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>
1. <span data-ttu-id="bc70f-163">登录到 Microsoft Store for Business 帐户 https://businessstore.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="bc70f-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>
2. <span data-ttu-id="bc70f-164">单击 "**管理->应用 & 软件**"。</span><span class="sxs-lookup"><span data-stu-id="bc70f-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="bc70f-165">将显示公司的所有应用的列表，包括您在 "添加 Surface 应用" 中添加的 Surface 应用，以及本文的 " [Microsoft Store For Business 帐户](#add-surface-app-to-a-microsoft-store-for-business-account)" 部分。</span><span class="sxs-lookup"><span data-stu-id="bc70f-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>
3. <span data-ttu-id="bc70f-166">在 "**操作**" 下，单击省略号（**...**），然后单击 "下载" 以供 Surface 应用**脱机使用**。</span><span class="sxs-lookup"><span data-stu-id="bc70f-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>
4. <span data-ttu-id="bc70f-167">从所选应用的可用选项中选择所需的**平台**和**体系结构**选项，如图4所示。</span><span class="sxs-lookup"><span data-stu-id="bc70f-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    ![.Appxbundle 程序包的示例](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *<span data-ttu-id="bc70f-169">图 4.</span><span class="sxs-lookup"><span data-stu-id="bc70f-169">Figure 4.</span></span> <span data-ttu-id="bc70f-170">下载应用的 .Appxbundle 程序包</span><span class="sxs-lookup"><span data-stu-id="bc70f-170">Download the AppxBundle package for an app</span></span>*
5. <span data-ttu-id="bc70f-171">单击 "**下载**"。</span><span class="sxs-lookup"><span data-stu-id="bc70f-171">Click **Download**.</span></span> <span data-ttu-id="bc70f-172">将下载 .Appxbundle 程序包。</span><span class="sxs-lookup"><span data-stu-id="bc70f-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="bc70f-173">请确保记下下载文件的路径，因为本文后面的内容将需要。</span><span class="sxs-lookup"><span data-stu-id="bc70f-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>
6. <span data-ttu-id="bc70f-174">单击 "已**编码的许可证**" 或 "未**编码的许可证**" 选项。</span><span class="sxs-lookup"><span data-stu-id="bc70f-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="bc70f-175">将编码的许可证选项与 Microsoft 终结点配置管理器等管理工具一起使用，或者在使用 Windows 配置设计器创建预配包时使用。</span><span class="sxs-lookup"><span data-stu-id="bc70f-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="bc70f-176">使用部署映像服务和管理（DISM）或基于映像的部署解决方案（包括 Microsoft 部署工具包（MDT））时，选择 "未编码的许可证" 选项。</span><span class="sxs-lookup"><span data-stu-id="bc70f-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>
7. <span data-ttu-id="bc70f-177">单击 "**生成**" 以生成并下载应用的许可证。</span><span class="sxs-lookup"><span data-stu-id="bc70f-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="bc70f-178">请务必记下许可证文件的路径，因为本文后面的内容将需要。</span><span class="sxs-lookup"><span data-stu-id="bc70f-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="bc70f-179">下载应用以供脱机使用（如 Surface app）时，你可能会注意到页面底部的 "**所需框架**" 部分中有一个分区。</span><span class="sxs-lookup"><span data-stu-id="bc70f-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="bc70f-180">目标计算机必须安装要运行的应用程序的框架，因此你可能需要为你的体系结构（x86 或 x64）的每个所需框架重复下载过程，并将其包含在本文后面部分中讨论的 Windows 部署中。</span><span class="sxs-lookup"><span data-stu-id="bc70f-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="bc70f-181">图5显示了 Surface 应用所需的框架。</span><span class="sxs-lookup"><span data-stu-id="bc70f-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

![Surface 应用所需的框架](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*<span data-ttu-id="bc70f-183">图 5.</span><span class="sxs-lookup"><span data-stu-id="bc70f-183">Figure 5.</span></span> <span data-ttu-id="bc70f-184">Surface 应用所需的框架</span><span class="sxs-lookup"><span data-stu-id="bc70f-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="bc70f-185">当应用更新时，Surface 应用和所需框架的版本号将会更改。</span><span class="sxs-lookup"><span data-stu-id="bc70f-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="bc70f-186">在 Microsoft Store for Business 中检查最新版本的 Surface 应用和每个框架。</span><span class="sxs-lookup"><span data-stu-id="bc70f-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="bc70f-187">始终使用由 Microsoft Store for Business 提供的 Surface 应用和推荐的框架版本。</span><span class="sxs-lookup"><span data-stu-id="bc70f-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="bc70f-188">使用过时的框架或不正确的版本可能会导致错误或应用程序崩溃。</span><span class="sxs-lookup"><span data-stu-id="bc70f-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="bc70f-189">若要下载 Surface 应用所需的框架，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bc70f-189">To download the required frameworks for the Surface app, follow these steps:</span></span>
1. <span data-ttu-id="bc70f-190">单击 " **VCLibs" 0_x64__8wekyb3d8bbwe 14.0.23816**下的 "**下载**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="bc70f-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="bc70f-191">这将下载 14.0.23816 0_x64__8wekyb3d8bbwe。Appx 文件复制到你的指定文件夹。</span><span class="sxs-lookup"><span data-stu-id="bc70f-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>
2. <span data-ttu-id="bc70f-192">单击 " **Microsoft 0_x64__8wekyb3d8bbwe 1.1.23406**" 下的 "**下载**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="bc70f-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="bc70f-193">这会将 0_x64__8wekyb3d8bbwe 1.1.23406 文件下载到你的指定文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="bc70f-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="bc70f-194">对于 Surface 设备，仅需要每个框架的64位（x64）版本。</span><span class="sxs-lookup"><span data-stu-id="bc70f-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="bc70f-195">Surface 设备是本机64位 UEFI 设备，与需要32位框架的 Windows 32 位（x86）版本不兼容。</span><span class="sxs-lookup"><span data-stu-id="bc70f-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="bc70f-196">通过 PowerShell 在计算机上安装 Surface app</span><span class="sxs-lookup"><span data-stu-id="bc70f-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="bc70f-197">下面的过程将 Surface 应用设置到你的计算机上，并使其可用于以后在计算机上创建的任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bc70f-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>
1. <span data-ttu-id="bc70f-198">有关本文中的 "[如何从 Microsoft Store For Business 帐户下载 surface 应用](#download-surface-app-from-a-microsoft-store-for-business-account)" 部分中所述的过程，请下载 Surface app 和许可证文件。</span><span class="sxs-lookup"><span data-stu-id="bc70f-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 
2. <span data-ttu-id="bc70f-199">开始提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="bc70f-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="bc70f-200">如果不以管理员身份运行 PowerShell，则会话将不具有安装应用所需的权限。</span><span class="sxs-lookup"><span data-stu-id="bc70f-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="bc70f-201">在提升的 PowerShell 会话中，复制并粘贴以下命令：</span><span class="sxs-lookup"><span data-stu-id="bc70f-201">In the elevated PowerShell session, copy and paste the following command:</span></span>
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="bc70f-202">其中 `<DownloadPath>` 是你从 Microsoft Store For Business 帐户下载了 .appxbundle 和许可证文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bc70f-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="bc70f-203">例如，如果您将文件下载到 C：\Temp，则您运行的命令是：</span><span class="sxs-lookup"><span data-stu-id="bc70f-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).

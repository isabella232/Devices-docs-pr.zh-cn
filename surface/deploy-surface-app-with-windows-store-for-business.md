---
title: '将 Surface 应用部署到 Microsoft Store for Business 或 Microsoft Store for 教育版 (Surface) '
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
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114710"
---
# <span data-ttu-id="bd2c6-104">将 Surface 应用部署到 Microsoft Store for Business 和教育版</span><span class="sxs-lookup"><span data-stu-id="bd2c6-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="bd2c6-105">适用于</span><span class="sxs-lookup"><span data-stu-id="bd2c6-105">Applies to</span></span>**

- <span data-ttu-id="bd2c6-106">Surface 膝上型电脑 Go</span><span class="sxs-lookup"><span data-stu-id="bd2c6-106">Surface Laptop Go</span></span>
- <span data-ttu-id="bd2c6-107">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="bd2c6-107">Surface Pro 7</span></span>
- <span data-ttu-id="bd2c6-108">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="bd2c6-108">Surface Laptop 3</span></span>
- <span data-ttu-id="bd2c6-109">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="bd2c6-109">Surface Pro 6</span></span>
- <span data-ttu-id="bd2c6-110">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="bd2c6-110">Surface Laptop 2</span></span>
- <span data-ttu-id="bd2c6-111">Surface Go</span><span class="sxs-lookup"><span data-stu-id="bd2c6-111">Surface Go</span></span>
- <span data-ttu-id="bd2c6-112">带有 LTE 的 Surface Go</span><span class="sxs-lookup"><span data-stu-id="bd2c6-112">Surface Go with LTE</span></span>
- <span data-ttu-id="bd2c6-113">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="bd2c6-113">Surface Book 2</span></span>
- <span data-ttu-id="bd2c6-114">带有 LTE Advanced 的 Surface Pro（型号 1807）</span><span class="sxs-lookup"><span data-stu-id="bd2c6-114">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="bd2c6-115">Surface Pro（型号 1796）</span><span class="sxs-lookup"><span data-stu-id="bd2c6-115">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="bd2c6-116">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="bd2c6-116">Surface Laptop</span></span>
- <span data-ttu-id="bd2c6-117">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="bd2c6-117">Surface Studio</span></span>
- <span data-ttu-id="bd2c6-118">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="bd2c6-118">Surface Studio 2</span></span>
- <span data-ttu-id="bd2c6-119">Surface Book</span><span class="sxs-lookup"><span data-stu-id="bd2c6-119">Surface Book</span></span>
- <span data-ttu-id="bd2c6-120">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="bd2c6-120">Surface Pro 4</span></span>
- <span data-ttu-id="bd2c6-121">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="bd2c6-121">Surface 3 LTE</span></span>
- <span data-ttu-id="bd2c6-122">Surface 3</span><span class="sxs-lookup"><span data-stu-id="bd2c6-122">Surface 3</span></span>
- <span data-ttu-id="bd2c6-123">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="bd2c6-123">Surface Pro 3</span></span>


<span data-ttu-id="bd2c6-124">Surface 应用是一种轻型 Microsoft Store 应用，可提供对许多特定于图面的设置和选项的控制，包括：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-124">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="bd2c6-125">启用或禁用 Surface 设备上的 Windows 按钮</span><span class="sxs-lookup"><span data-stu-id="bd2c6-125">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="bd2c6-126">调整 Surface 触控笔的灵敏度</span><span class="sxs-lookup"><span data-stu-id="bd2c6-126">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="bd2c6-127">自定义 Surface 触控笔按钮操作</span><span class="sxs-lookup"><span data-stu-id="bd2c6-127">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="bd2c6-128">启用或禁用 Surface 音频增强功能</span><span class="sxs-lookup"><span data-stu-id="bd2c6-128">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="bd2c6-129">快速访问你的设备的支持文档和信息</span><span class="sxs-lookup"><span data-stu-id="bd2c6-129">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="bd2c6-130">使用 Windows 更新的客户通常会接收 Surface app 作为自动更新的一部分。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-130">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="bd2c6-131">但是，如果你的组织准备将映像部署到 Surface 设备，你可能需要在你的映像和部署过程中包含 Surface app (以前称为 Surface Hub) ，而不是需要每个人设备的用户从 Microsoft Store 或 Microsoft Store for Business 下载和安装应用。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-131">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="bd2c6-132">本文不适用于 Surface Pro X。有关详细信息，请参阅 [部署、管理和维护 Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="bd2c6-132">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="bd2c6-133">Surface 应用概述</span><span class="sxs-lookup"><span data-stu-id="bd2c6-133">Surface app overview</span></span>

<span data-ttu-id="bd2c6-134">Surface app 可从 [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)免费下载。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-134">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="bd2c6-135">用户可以从 Microsoft Store 下载并安装它，但如果您的组织使用的是 Microsoft store for Business，则需要将其添加到你的应用商店的库存，并且可能将应用包括在 Windows 部署过程中。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-135">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="bd2c6-136">本文将讨论这些过程。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-136">These processes are discussed throughout this article.</span></span> <span data-ttu-id="bd2c6-137">有关 Microsoft Store for Business 的详细信息，请参阅 Windows 技术中心中的 [Microsoft store For business](https://docs.microsoft.com/microsoft-store/) 。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-137">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="bd2c6-138">将 Surface 应用添加到 Microsoft Store for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="bd2c6-138">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="bd2c6-139">在用户可以从公司的 Microsoft Store for Business 帐户安装或部署应用之前，所需的应用 (s) 必须首先向企业用户提供和授权。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-139">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="bd2c6-140">如果尚未执行此操作，请创建 [Microsoft Store For Business 帐户](https://www.microsoft.com/business-store)。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-140">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="bd2c6-141">登录到门户。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-141">Log on to the portal.</span></span> 

3. <span data-ttu-id="bd2c6-142">启用脱机授权：单击 " **管理->存储设置**"，然后选择 " **向在应用商店中购物的用户显示脱机许可的应用** " 复选框，如图1所示。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-142">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="bd2c6-143">有关 Microsoft Store for Business 应用许可模型的详细信息，请参阅 [Microsoft store For business 和教育版中的应用](https://docs.microsoft.com/microsoft-store/)。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-143">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > !["显示脱机许可证应用" 复选框](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="bd2c6-145">图 1.</span><span class="sxs-lookup"><span data-stu-id="bd2c6-145">Figure 1.</span></span> <span data-ttu-id="bd2c6-146">允许应用脱机使用</span><span class="sxs-lookup"><span data-stu-id="bd2c6-146">Enable apps for offline use</span></span>*

4. <span data-ttu-id="bd2c6-147">通过执行以下过程，将 Surface 应用添加到 Microsoft Store for Business 帐户：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-147">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="bd2c6-148">单击 " **商店** " 菜单。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-148">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="bd2c6-149">在 "搜索" 框中，键入 " **Surface app**"，然后单击 "搜索" 图标。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-149">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="bd2c6-150">在搜索结果中显示 Surface 应用后，单击应用的图标。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-150">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="bd2c6-151">将显示一个选项 (选择 " **联机** " 或 " **脱机** ") ，如图2所示。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-151">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![选择脱机授权模式并将应用添加到你的库存](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="bd2c6-153">图 2.</span><span class="sxs-lookup"><span data-stu-id="bd2c6-153">Figure 2.</span></span> <span data-ttu-id="bd2c6-154">选择脱机授权模式并将应用添加到你的库存</span><span class="sxs-lookup"><span data-stu-id="bd2c6-154">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="bd2c6-155">单击 " **脱机** " 以选择脱机授权模式。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-155">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="bd2c6-156">单击 **"获取应用** " 以将应用添加到 Microsoft Store for Business 库存。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-156">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="bd2c6-157">如图3所示，你将看到一个对话框，提示你确认可以使用管理工具部署脱机应用，或者从其私人存储中的公司的库存页面下载。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-157">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="bd2c6-158">脱机许可的应用确认窗口 ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *图3。脱机授权应用确认*</span><span class="sxs-lookup"><span data-stu-id="bd2c6-158">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="bd2c6-159">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-159">Click **OK**.</span></span>

## <span data-ttu-id="bd2c6-160">从 Microsoft Store for Business 帐户下载 Surface 应用</span><span class="sxs-lookup"><span data-stu-id="bd2c6-160">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="bd2c6-161">在脱机模式下将应用添加到 Microsoft Store for Business 帐户之后，你可以将该应用作为 .Appxbundle 下载并添加到部署共享。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-161">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="bd2c6-162">登录到 Microsoft Store for Business 帐户 https://businessstore.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-162">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="bd2c6-163">单击 " **管理->应用 & 软件**"。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-163">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="bd2c6-164">将显示公司的所有应用的列表，包括您在 "添加 Surface 应用" 中添加的 Surface 应用，以及本文的 " [Microsoft Store For Business 帐户](#add-surface-app-to-a-microsoft-store-for-business-account) " 部分。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-164">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="bd2c6-165">在 " **操作**" 下，单击省略号 (**...** ") ，然后单击" 下载 "以供 Surface 应用 **脱机使用** 。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-165">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="bd2c6-166">从所选应用的可用选项中选择所需的 **平台** 和 **体系结构** 选项，如图4所示。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-166">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![.Appxbundle 程序包的示例](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="bd2c6-168">图 4.</span><span class="sxs-lookup"><span data-stu-id="bd2c6-168">Figure 4.</span></span> <span data-ttu-id="bd2c6-169">下载应用的 .Appxbundle 程序包</span><span class="sxs-lookup"><span data-stu-id="bd2c6-169">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="bd2c6-170">单击 " **下载**"。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-170">Click **Download**.</span></span> <span data-ttu-id="bd2c6-171">将下载 .Appxbundle 程序包。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-171">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="bd2c6-172">请确保记下下载文件的路径，因为本文后面的内容将需要。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-172">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="bd2c6-173">单击 "已 **编码的许可证** " 或 "未 **编码的许可证** " 选项。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-173">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="bd2c6-174">将编码的许可证选项与 Microsoft 终结点配置管理器等管理工具一起使用，或者在使用 Windows 配置设计器创建预配包时使用。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-174">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="bd2c6-175">当你使用部署映像服务和管理 (DISM) 或基于映像的部署解决方案（包括 Microsoft 部署工具包 (MDT) ）时，请选择 "未编码的许可证" 选项。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-175">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="bd2c6-176">单击 " **生成** " 以生成并下载应用的许可证。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-176">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="bd2c6-177">请务必记下许可证文件的路径，因为本文后面的内容将需要。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-177">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="bd2c6-178">下载应用以供脱机使用（如 Surface app）时，你可能会注意到页面底部的 " **所需框架**" 部分中有一个分区。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-178">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="bd2c6-179">目标计算机必须安装要运行的应用程序框架，因此你可能需要为你的体系结构的每个所需框架重复下载过程 (x86 或 x64) ，并将其包含在本文后面部分中讨论的 Windows 部署中。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-179">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="bd2c6-180">图5显示了 Surface 应用所需的框架。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-180">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface 应用所需的框架](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="bd2c6-182">图 5.</span><span class="sxs-lookup"><span data-stu-id="bd2c6-182">Figure 5.</span></span> <span data-ttu-id="bd2c6-183">Surface 应用所需的框架</span><span class="sxs-lookup"><span data-stu-id="bd2c6-183">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="bd2c6-184">当应用更新时，Surface 应用和所需框架的版本号将会更改。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-184">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="bd2c6-185">在 Microsoft Store for Business 中检查最新版本的 Surface 应用和每个框架。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-185">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="bd2c6-186">始终使用由 Microsoft Store for Business 提供的 Surface 应用和推荐的框架版本。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-186">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="bd2c6-187">使用过时的框架或不正确的版本可能会导致错误或应用程序崩溃。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-187">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="bd2c6-188">若要下载 Surface 应用所需的框架，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-188">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="bd2c6-189">单击 "VCLibs" 下的 " **下载** " 按钮。 **140.00 _14. 0 23816 _x64__8wekyb3d8bbwe**。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-189">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="bd2c6-190">此操作将下载 VCLibs 140.00 _14. 0 _x64__8wekyb3d8bbwe。Appx 文件复制到你的指定文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-190">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="bd2c6-191">单击 "Microsoft _x64__8wekyb3d8bbwe" 下的 " **下载** " 按钮。 **23406**。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-191">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="bd2c6-192">此操作会将 23406 _x64__8wekyb3d8bbwe 文件下载到指定的文件夹中，然后将其下载到你的指定文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-192">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="bd2c6-193">对于 Surface 设备，仅需要每个框架的64位 (x64) 版本。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-193">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="bd2c6-194">Surface 设备是本机64位 UEFI 设备，与32位 (x86) 版本的 Windows 不兼容，这些版本需要32位框架。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-194">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="bd2c6-195">通过 PowerShell 在计算机上安装 Surface app</span><span class="sxs-lookup"><span data-stu-id="bd2c6-195">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="bd2c6-196">下面的过程将 Surface 应用设置到你的计算机上，并使其可用于以后在计算机上创建的任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-196">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="bd2c6-197">有关本文中的 " [如何从 Microsoft Store For Business 帐户下载 surface 应用](#download-surface-app-from-a-microsoft-store-for-business-account) " 部分中所述的过程，请下载 Surface app 和许可证文件。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-197">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="bd2c6-198">开始提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-198">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="bd2c6-199">如果不以管理员身份运行 PowerShell，则会话将不具有安装应用所需的权限。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-199">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="bd2c6-200">在提升的 PowerShell 会话中，复制并粘贴以下命令：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-200">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="bd2c6-201">其中 `<DownloadPath>` 是你从 Microsoft Store For Business 帐户下载了 .appxbundle 和许可证文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-201">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="bd2c6-202">例如，如果您将文件下载到 C：\Temp，则您运行的命令是：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-202">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="bd2c6-203">现在，Surface 应用将在你的当前 Windows 计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-203">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="bd2c6-204">如果 Surface 应用在预配的计算机上运行正常，则还必须预配本文前面所述的框架。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-204">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="bd2c6-205">若要设置这些框架，请在用于设置 Surface 应用的提升的 PowerShell 会话中使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-205">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="bd2c6-206">在提升的 PowerShell 会话中，复制并粘贴以下命令：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-206">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="bd2c6-207">在提升的 PowerShell 会话中，复制并粘贴以下命令：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="bd2c6-208">通过 MDT 安装 Surface 应用</span><span class="sxs-lookup"><span data-stu-id="bd2c6-208">Install Surface app with MDT</span></span>
<span data-ttu-id="bd2c6-209">以下过程使用 MDT 在部署时自动安装 Surface 应用。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-209">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="bd2c6-210">该应用程序在部署期间自动由 MDT 预配，因此可将该过程用于现有映像。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-210">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="bd2c6-211">建议使用此过程将 Surface 应用部署为 Surface 设备的 Windows 部署的一部分，因为它不会减少 Windows 映像的跨平台兼容性。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-211">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="bd2c6-212">使用 [本文前面](#download-surface-app-from-a-microsoft-store-for-business-account)所述的过程，下载 Surface app 和许可证文件。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-212">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="bd2c6-213">使用 MDT 部署工作台中的 "新建应用程序" 向导，将下载的文件作为 **具有源文件的新应用程序**导入。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-213">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="bd2c6-214">在 "新建应用程序" 向导的 " **命令详细信息** " 页面上，指定默认 **工作目录** 和 **命令** 指定 .appxbundle 的文件名，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-214">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="bd2c6-215">命令</span><span class="sxs-lookup"><span data-stu-id="bd2c6-215">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="bd2c6-216">工作目录：%DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="bd2c6-216">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="bd2c6-217">要使 Surface 应用在目标计算机上运行，还需要本文前面所述的框架。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-217">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="bd2c6-218">使用以下过程将 Surface 应用所需的框架导入到 MDT，并将其配置为依赖关系。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-218">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="bd2c6-219">使用本文前面所述的过程下载框架文件。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-219">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="bd2c6-220">将每个框架存储在单独的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-220">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="bd2c6-221">使用 MDT 部署工作台中的 "新建应用程序" 向导，将下载的文件作为 **具有源文件的新应用程序**导入。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-221">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="bd2c6-222">在 " **命令详细信息** " 页上，在 " **命令** " 字段中键入您下载的每个应用程序的文件名和默认工作目录。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-222">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="bd2c6-223">若要将框架配置为 Surface 应用的依赖关系，请使用此过程：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-223">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="bd2c6-224">在 MDT 部署工作台中打开 Surface 应用的属性。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-224">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="bd2c6-225">单击 " **相关性** " 选项卡，然后单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-225">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="bd2c6-226">使用在 "新建应用程序" 向导中提供的名称，选中每个框架对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-226">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="bd2c6-227">导入后，Surface app 将在 Windows 部署向导的 **应用程序** 步骤中供选择。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-227">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="bd2c6-228">也可以通过遵循此过程在部署任务序列中指定应用程序来自动安装该应用程序：</span><span class="sxs-lookup"><span data-stu-id="bd2c6-228">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="bd2c6-229">在 MDT 部署工作台中打开你的部署任务序列。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-229">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="bd2c6-230">在部署的“状态还原”\*\*\*\* 部分中添加一个新的“安装应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-230">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="bd2c6-231">选择 " **安装单个应用程序** "，然后将 **Surface App** 指定为 **要安装的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-231">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="bd2c6-232">有关将应用包括在 Windows 部署中的详细信息，请参阅 [通过 Microsoft 部署工具包部署 Windows 10](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)。</span><span class="sxs-lookup"><span data-stu-id="bd2c6-232">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>

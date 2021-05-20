---
title: '使用 Surface 适用于企业的 Microsoft Store 或 适用于教育的 Microsoft Store (Surface) '
description: 了解如何使用 适用于企业的 Microsoft Store 或 适用于教育的 Microsoft Store 添加和下载 Surface 应用，以及如何使用 PowerShell 和 MDT 安装 Surface 应用。
keywords: surface 应用， 应用， 部署， 自定义
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
ms.date: 4/16/2021
ms.openlocfilehash: c7a882859339ff3d7feeb685c62672bc57c301ec
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576522"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a><span data-ttu-id="16475-104">使用应用和教育适用于企业的 Microsoft Store Surface 应用</span><span class="sxs-lookup"><span data-stu-id="16475-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="16475-105">适用范围</span><span class="sxs-lookup"><span data-stu-id="16475-105">Applies to</span></span>**

- <span data-ttu-id="16475-106">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="16475-106">Surface Laptop 4</span></span>
- <span data-ttu-id="16475-107">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="16475-107">Surface Pro 7+</span></span>
- <span data-ttu-id="16475-108">Surface Laptop转到</span><span class="sxs-lookup"><span data-stu-id="16475-108">Surface Laptop Go</span></span>
- <span data-ttu-id="16475-109">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="16475-109">Surface Pro 7</span></span>
- <span data-ttu-id="16475-110">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="16475-110">Surface Laptop 3</span></span>
- <span data-ttu-id="16475-111">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="16475-111">Surface Pro 6</span></span>
- <span data-ttu-id="16475-112">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="16475-112">Surface Laptop 2</span></span>
- <span data-ttu-id="16475-113">Surface Go</span><span class="sxs-lookup"><span data-stu-id="16475-113">Surface Go</span></span>
- <span data-ttu-id="16475-114">带 LTE 的 Surface Go</span><span class="sxs-lookup"><span data-stu-id="16475-114">Surface Go with LTE</span></span>
- <span data-ttu-id="16475-115">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="16475-115">Surface Book 2</span></span>
- <span data-ttu-id="16475-116">带有 LTE Advanced 的 Surface Pro（型号 1807）</span><span class="sxs-lookup"><span data-stu-id="16475-116">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="16475-117">Surface Pro（型号 1796）</span><span class="sxs-lookup"><span data-stu-id="16475-117">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="16475-118">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="16475-118">Surface Laptop</span></span>
- <span data-ttu-id="16475-119">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="16475-119">Surface Studio</span></span>
- <span data-ttu-id="16475-120">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="16475-120">Surface Studio 2</span></span>
- <span data-ttu-id="16475-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="16475-121">Surface Book</span></span>
- <span data-ttu-id="16475-122">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="16475-122">Surface Pro 4</span></span>
- <span data-ttu-id="16475-123">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="16475-123">Surface 3 LTE</span></span>
- <span data-ttu-id="16475-124">Surface 3</span><span class="sxs-lookup"><span data-stu-id="16475-124">Surface 3</span></span>
- <span data-ttu-id="16475-125">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="16475-125">Surface Pro 3</span></span>


<span data-ttu-id="16475-126">Surface 应用是轻型Microsoft Store应用，可控制许多特定于 Surface 的设置和选项，包括：</span><span class="sxs-lookup"><span data-stu-id="16475-126">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="16475-127">启用或禁用 Surface 设备上的 Windows 按钮</span><span class="sxs-lookup"><span data-stu-id="16475-127">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="16475-128">调整 Surface 触控笔的灵敏度</span><span class="sxs-lookup"><span data-stu-id="16475-128">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="16475-129">自定义 Surface 触控笔按钮操作</span><span class="sxs-lookup"><span data-stu-id="16475-129">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="16475-130">启用或禁用 Surface 音频增强功能</span><span class="sxs-lookup"><span data-stu-id="16475-130">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="16475-131">快速访问设备的支持文档和信息</span><span class="sxs-lookup"><span data-stu-id="16475-131">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="16475-132">使用 Windows 更新的客户通常会收到 Surface 应用作为自动更新的一部分。</span><span class="sxs-lookup"><span data-stu-id="16475-132">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="16475-133">但是，如果你的组织准备映像以部署到 Surface 设备，你可能希望将 Surface 应用 (以前称为 Surface Hub) 包括在映像和部署过程中，而不是要求每个设备的用户从 Microsoft Store 或 适用于企业的 Microsoft Store 下载和安装该应用。</span><span class="sxs-lookup"><span data-stu-id="16475-133">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="16475-134">本文不适用于 Surface Pro X。有关详细信息，请参阅部署[、管理和](surface-pro-arm-app-management.md)维护 Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="16475-134">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <a name="surface-app-overview"></a><span data-ttu-id="16475-135">Surface 应用概述</span><span class="sxs-lookup"><span data-stu-id="16475-135">Surface app overview</span></span>

<span data-ttu-id="16475-136">Surface 应用可从应用商店免费下载[Microsoft Store。](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)</span><span class="sxs-lookup"><span data-stu-id="16475-136">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="16475-137">用户可以从 Microsoft Store 下载并安装它，但如果你的组织改为使用 适用于企业的 Microsoft Store，你将需要将其添加到应用商店的清单中，并可能在 Windows 部署过程中包括该应用。</span><span class="sxs-lookup"><span data-stu-id="16475-137">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="16475-138">本文将讨论这些过程。</span><span class="sxs-lookup"><span data-stu-id="16475-138">These processes are discussed throughout this article.</span></span> <span data-ttu-id="16475-139">有关此适用于企业的 Microsoft Store，[请参阅](https://docs.microsoft.com/microsoft-store/)适用于企业的 Microsoft Store TechCenter Windows。</span><span class="sxs-lookup"><span data-stu-id="16475-139">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a><span data-ttu-id="16475-140">将 Surface 应用添加到适用于企业的 Microsoft Store帐户</span><span class="sxs-lookup"><span data-stu-id="16475-140">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="16475-141">在用户可以通过公司的 适用于企业的 Microsoft Store 帐户安装或部署应用之前，必须先向企业用户 (所需的应用) 并授予其许可。</span><span class="sxs-lookup"><span data-stu-id="16475-141">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="16475-142">如果尚未创建，请创建一个适用于企业的 Microsoft Store[帐户](https://www.microsoft.com/business-store)。</span><span class="sxs-lookup"><span data-stu-id="16475-142">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="16475-143">登录到门户。</span><span class="sxs-lookup"><span data-stu-id="16475-143">Log on to the portal.</span></span> 

3. <span data-ttu-id="16475-144">启用离线许可 **：单击**">应用商店设置"，然后选中"向在应用商店中\*\*\*\* 购物的用户显示离线许可应用"复选框，如图 1 所示。</span><span class="sxs-lookup"><span data-stu-id="16475-144">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="16475-145">有关应用许可模型适用于企业的 Microsoft Store，请参阅应用[适用于企业的 Microsoft Store和教育。](https://docs.microsoft.com/microsoft-store/)</span><span class="sxs-lookup"><span data-stu-id="16475-145">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![显示离线许可证应用复选框](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="16475-147">图 1.</span><span class="sxs-lookup"><span data-stu-id="16475-147">Figure 1.</span></span> <span data-ttu-id="16475-148">启用应用以便脱机使用</span><span class="sxs-lookup"><span data-stu-id="16475-148">Enable apps for offline use</span></span>*

4. <span data-ttu-id="16475-149">按照以下过程适用于企业的 Microsoft Store Surface 应用添加到你的应用帐户：</span><span class="sxs-lookup"><span data-stu-id="16475-149">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="16475-150">单击购买 **菜单** 。</span><span class="sxs-lookup"><span data-stu-id="16475-150">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="16475-151">在搜索框中，键入 **Surface 应用**，然后单击搜索图标。</span><span class="sxs-lookup"><span data-stu-id="16475-151">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="16475-152">在搜索结果中显示 Surface 应用后，单击该应用的图标。</span><span class="sxs-lookup"><span data-stu-id="16475-152">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="16475-153">可以选择"联机 (脱机) ，如图 2\*\*\*\* 所示\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16475-153">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![选择离线许可模式，将应用添加到清单](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="16475-155">图 2.</span><span class="sxs-lookup"><span data-stu-id="16475-155">Figure 2.</span></span> <span data-ttu-id="16475-156">选择离线许可模式，将应用添加到清单</span><span class="sxs-lookup"><span data-stu-id="16475-156">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="16475-157">单击 **"** 脱机"以选择脱机许可模式。</span><span class="sxs-lookup"><span data-stu-id="16475-157">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="16475-158">单击 **"获取应用**"将应用添加到你的适用于企业的 Microsoft Store清单。</span><span class="sxs-lookup"><span data-stu-id="16475-158">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="16475-159">如图 3 所示，你将看到一个对话框，提示你确认离线应用可以使用管理工具部署，也可以从公司的专用应用商店的清单页面下载。</span><span class="sxs-lookup"><span data-stu-id="16475-159">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="16475-160">脱机授权的应用确认窗口 ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *图 3.离线授权的应用确认*</span><span class="sxs-lookup"><span data-stu-id="16475-160">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="16475-161">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16475-161">Click **OK**.</span></span>

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a><span data-ttu-id="16475-162">从应用帐户适用于企业的 Microsoft Store Surface 应用</span><span class="sxs-lookup"><span data-stu-id="16475-162">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="16475-163">在脱机模式下将应用添加到 适用于企业的 Microsoft Store 帐户后，你可以下载该应用，并作为 AppxBundle 添加到部署共享。</span><span class="sxs-lookup"><span data-stu-id="16475-163">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="16475-164">登录到位于 的 适用于企业的 Microsoft Store 帐户 https://businessstore.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="16475-164">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="16475-165">单击 **"管理>应用&软件"。**</span><span class="sxs-lookup"><span data-stu-id="16475-165">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="16475-166">将显示你公司的所有应用的列表，包括你在本文的将 Surface 应用添加到 适用于企业的 Microsoft Store 帐户部分添加的[Surface](#add-surface-app-to-a-microsoft-store-for-business-account)应用。</span><span class="sxs-lookup"><span data-stu-id="16475-166">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="16475-167">在 **操作**下，单击省略号 (**...**) ，然后单击下载 **以脱机使用** Surface 应用。</span><span class="sxs-lookup"><span data-stu-id="16475-167">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="16475-168">从选定 **应用的** 可用选项 **中选择** 所需的平台和体系结构选项，如图 4 所示。</span><span class="sxs-lookup"><span data-stu-id="16475-168">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![AppxBundle 包的示例](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="16475-170">图 4.</span><span class="sxs-lookup"><span data-stu-id="16475-170">Figure 4.</span></span> <span data-ttu-id="16475-171">下载应用的 AppxBundle 程序包</span><span class="sxs-lookup"><span data-stu-id="16475-171">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="16475-172">单击"**下载"。**</span><span class="sxs-lookup"><span data-stu-id="16475-172">Click **Download**.</span></span> <span data-ttu-id="16475-173">将下载 AppxBundle 程序包。</span><span class="sxs-lookup"><span data-stu-id="16475-173">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="16475-174">请务必记下已下载文件的路径，因为本文稍后将对此进行介绍。</span><span class="sxs-lookup"><span data-stu-id="16475-174">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="16475-175">单击" **编码的许可证"** 或 **"未编码的许可证"** 选项。</span><span class="sxs-lookup"><span data-stu-id="16475-175">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="16475-176">将"编码的许可证"选项与管理工具（如 Microsoft Endpoint Configuration Manager）或当你使用Windows设计器创建预配包时一同使用。</span><span class="sxs-lookup"><span data-stu-id="16475-176">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="16475-177">在使用部署映像服务和管理 (DISM) 或基于映像的部署解决方案（包括 Microsoft Deployment Toolkit (MDT) ）时，请选择"未编码的许可证"选项。</span><span class="sxs-lookup"><span data-stu-id="16475-177">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="16475-178">单击 **"** 生成"生成并下载应用的许可证。</span><span class="sxs-lookup"><span data-stu-id="16475-178">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="16475-179">请务必记下许可证文件的路径，因为本文稍后将对此进行介绍。</span><span class="sxs-lookup"><span data-stu-id="16475-179">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="16475-180">当你下载离线使用的应用（如 Surface 应用）时，你可能会注意到页面底部标记为"所需框架" **的一部分**。</span><span class="sxs-lookup"><span data-stu-id="16475-180">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="16475-181">目标计算机必须安装框架，应用才能运行，因此可能需要为体系结构 (（x86 或 x64) ）的每个必需框架重复下载过程，并且将它们包括在本文稍后将讨论的 Windows 部署中。</span><span class="sxs-lookup"><span data-stu-id="16475-181">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="16475-182">图 5 显示了 Surface 应用所需的框架。</span><span class="sxs-lookup"><span data-stu-id="16475-182">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface 应用所需的框架](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="16475-184">图 5.</span><span class="sxs-lookup"><span data-stu-id="16475-184">Figure 5.</span></span> <span data-ttu-id="16475-185">Surface 应用所需的框架</span><span class="sxs-lookup"><span data-stu-id="16475-185">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="16475-186">Surface 应用的版本号和所需框架将随着应用更新而更改。</span><span class="sxs-lookup"><span data-stu-id="16475-186">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="16475-187">检查 Surface 应用的最新版本以及每个框架适用于企业的 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="16475-187">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="16475-188">始终使用 Surface 应用和推荐框架版本，适用于企业的 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="16475-188">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="16475-189">使用过时的框架或不正确的版本可能会导致错误或应用程序崩溃。</span><span class="sxs-lookup"><span data-stu-id="16475-189">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="16475-190">若要下载 Surface 应用所需的框架，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="16475-190">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="16475-191">单击\*\*\*\*\*\*Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe 下的"下载"按钮\*\*。</span><span class="sxs-lookup"><span data-stu-id="16475-191">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="16475-192">这将下载 Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe。指定文件夹的 Appx 文件。</span><span class="sxs-lookup"><span data-stu-id="16475-192">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="16475-193">单击\*\*\*\*\*\*Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe 下的"下载"按钮\*\*。</span><span class="sxs-lookup"><span data-stu-id="16475-193">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="16475-194">这会将 Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx 文件下载到指定的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="16475-194">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="16475-195">Surface 设备只需要每个框架 (64) x64 版本。</span><span class="sxs-lookup"><span data-stu-id="16475-195">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="16475-196">Surface 设备是本机 64 位 UEFI 设备，与需要 32 位框架的 Windows 的 32 位 (x86) 版本不兼容。</span><span class="sxs-lookup"><span data-stu-id="16475-196">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <a name="install-surface-app-on-your-computer-with-powershell"></a><span data-ttu-id="16475-197">使用 PowerShell 在计算机上安装 Surface 应用</span><span class="sxs-lookup"><span data-stu-id="16475-197">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="16475-198">以下过程将 Surface 应用设置在计算机上，然后使其可用于以后在计算机上创建的任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="16475-198">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="16475-199">使用本文中如何从 适用于企业的 Microsoft Store 帐户下载[Surface](#download-surface-app-from-a-microsoft-store-for-business-account)应用部分中介绍的过程，下载 Surface 应用 AppxBundle 和许可证文件。</span><span class="sxs-lookup"><span data-stu-id="16475-199">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="16475-200">开始提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="16475-200">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="16475-201">如果不以管理员角色运行 PowerShell，会话将没有安装应用所需的权限。</span><span class="sxs-lookup"><span data-stu-id="16475-201">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="16475-202">在提升的 PowerShell 会话中，复制并粘贴以下命令：</span><span class="sxs-lookup"><span data-stu-id="16475-202">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="16475-203">其中 `<DownloadPath>` ，是从应用程序帐户下载 AppxBundle 和许可证适用于企业的 Microsoft Store文件夹。</span><span class="sxs-lookup"><span data-stu-id="16475-203">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="16475-204">例如，如果将文件下载到 c：\Temp，则运行的命令为：</span><span class="sxs-lookup"><span data-stu-id="16475-204">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="16475-205">现在，Surface 应用将在你的当前 Windows 计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="16475-205">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="16475-206">在 Surface 应用在已预配它的计算机上正常运行之前，你还必须预配本文前面所述的框架。</span><span class="sxs-lookup"><span data-stu-id="16475-206">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="16475-207">若要预配这些框架，请使用你用于预配 Surface 应用的提升的 PowerShell 会话中的以下过程。</span><span class="sxs-lookup"><span data-stu-id="16475-207">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="16475-208">在提升的 PowerShell 会话中，复制并粘贴以下命令：</span><span class="sxs-lookup"><span data-stu-id="16475-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="16475-209">在提升的 PowerShell 会话中，复制并粘贴以下命令：</span><span class="sxs-lookup"><span data-stu-id="16475-209">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <a name="install-surface-app-with-mdt"></a><span data-ttu-id="16475-210">使用 MDT 安装 Surface 应用</span><span class="sxs-lookup"><span data-stu-id="16475-210">Install Surface app with MDT</span></span>
<span data-ttu-id="16475-211">以下过程使用 MDT 在部署时自动安装 Surface 应用。</span><span class="sxs-lookup"><span data-stu-id="16475-211">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="16475-212">该应用程序在部署期间自动由 MDT 预配，因此可将该过程用于现有映像。</span><span class="sxs-lookup"><span data-stu-id="16475-212">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="16475-213">这是将 Surface 应用作为 Windows 部署到 Surface 设备的一部分的建议过程，因为它不会降低 Windows 映像的跨平台兼容性。</span><span class="sxs-lookup"><span data-stu-id="16475-213">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="16475-214">使用本文前面 [介绍的过程](#download-surface-app-from-a-microsoft-store-for-business-account)下载 Surface app AppxBundle 和许可证文件。</span><span class="sxs-lookup"><span data-stu-id="16475-214">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="16475-215">使用 MDT 部署工作台中的"新建应用程序向导"，将下载的文件作为包含源文件 **的新应用程序导入**。</span><span class="sxs-lookup"><span data-stu-id="16475-215">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="16475-216">在"**新建**应用程序向导"的"命令详细信息"页上，指定\*\*\*\* 默认的"工作目录"，为 **"** 命令"指定 AppxBundle 的文件名，如下所示：</span><span class="sxs-lookup"><span data-stu-id="16475-216">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="16475-217">命令：</span><span class="sxs-lookup"><span data-stu-id="16475-217">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="16475-218">工作目录：%DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="16475-218">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="16475-219">若要使 Surface 应用在目标计算机上运行，还需要使用本文前面介绍的框架。</span><span class="sxs-lookup"><span data-stu-id="16475-219">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="16475-220">使用以下过程将 Surface 应用所需的框架导入 MDT，并配置它们作为依赖项。</span><span class="sxs-lookup"><span data-stu-id="16475-220">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="16475-221">使用本文前面介绍的过程下载框架文件。</span><span class="sxs-lookup"><span data-stu-id="16475-221">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="16475-222">将每个框架存储在单独的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="16475-222">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="16475-223">使用 MDT 部署工作台中的"新建应用程序向导"，将下载的文件作为包含源文件 **的新应用程序导入**。</span><span class="sxs-lookup"><span data-stu-id="16475-223">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="16475-224">在"**命令详细信息**"页上，在"命令"字段中键入下载的每个应用程序的文件名和\*\*\*\* 默认工作目录。</span><span class="sxs-lookup"><span data-stu-id="16475-224">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="16475-225">若要将框架配置为 Surface 应用的依赖项，请使用此过程：</span><span class="sxs-lookup"><span data-stu-id="16475-225">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="16475-226">在 MDT 部署工作台中打开 Surface 应用的属性。</span><span class="sxs-lookup"><span data-stu-id="16475-226">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="16475-227">单击 **"依赖项"** 选项卡，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="16475-227">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="16475-228">使用"新建应用程序向导"中提供的名称选中每个框架的复选框。</span><span class="sxs-lookup"><span data-stu-id="16475-228">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="16475-229">导入后，Surface 应用将在"部署向导"的"\*\*\*\* 应用程序"步骤中Windows选择。</span><span class="sxs-lookup"><span data-stu-id="16475-229">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="16475-230">也可以通过遵循此过程在部署任务序列中指定应用程序来自动安装该应用程序：</span><span class="sxs-lookup"><span data-stu-id="16475-230">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="16475-231">在 MDT 部署工作台中打开你的部署任务序列。</span><span class="sxs-lookup"><span data-stu-id="16475-231">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="16475-232">在部署的“状态还原”\*\*\*\* 部分中添加一个新的“安装应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16475-232">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="16475-233">选择 **"安装单个应用程序** "，将 **Surface App** 指定为 **要安装的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="16475-233">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="16475-234">有关将应用包括到 Windows 部署中[Windows 10，](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)请参阅使用 Microsoft 部署Toolkit。</span><span class="sxs-lookup"><span data-stu-id="16475-234">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>

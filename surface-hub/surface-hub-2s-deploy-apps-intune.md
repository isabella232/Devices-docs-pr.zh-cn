---
title: 使用 Intune 将应用部署到 Surface Hub 2S
description: 了解如何使用 Intune 将应用部署到 Surface Hub 2。
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
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831571"
---
# <span data-ttu-id="8cfc3-104">使用 Intune 将应用部署到 Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="8cfc3-104">Deploy apps to Surface Hub 2S using Intune</span></span>

<span data-ttu-id="8cfc3-105">你可以安装其他应用以满足你的团队或组织的需求。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-105">You can install additional apps to fit your team or organization's needs.</span></span>

## <span data-ttu-id="8cfc3-106">开发人员指南</span><span class="sxs-lookup"><span data-stu-id="8cfc3-106">Developer guidelines</span></span>

- <span data-ttu-id="8cfc3-107">Surface Hub 仅运行[通用 Windows 平台 (UWP) 应用](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-107">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="8cfc3-108">无法在 Surface Hub 上运行使用 [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) 创建的应用。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-108">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="8cfc3-109">应用必须面向[通用设备系列](https://msdn.microsoft.com/library/windows/apps/dn894631)或 Windows 团队设备系列。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-109">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="8cfc3-110">Surface Hub 仅支持[Microsoft Store For Business](https://businessstore.microsoft.com/store)中的[脱机许可应用](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-110">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="8cfc3-111">默认情况下，应用必须经过应用商店签名才能安装。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-111">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="8cfc3-112">在测试和开发时，还可以选择运行开发人员签名的 UWP 应用，使设备进入开发人员模式即可。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-112">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="8cfc3-113">在向 Microsoft Store 开发应用和提交应用时，请设置设备系列可用性和组织授权选项以确保应用可以在 Surface Hub 上运行。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-113">When developing and submitting apps to the Microsoft Store, set Device family availability and Organizational licensing options to ensure that apps are available to run on Surface Hub.</span></span>
- <span data-ttu-id="8cfc3-114">需要管理员凭据才能在 Surface Hub 上安装应用。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-114">You need admin credentials to install apps on Surface Hub.</span></span> <span data-ttu-id="8cfc3-115">为了在会议室和其他共享空间中使用，Surface Hub 阻止常规用户访问 Microsoft Store 以下载和安装应用。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-115">Designed for use in meeting rooms and other shared spaces, Surface Hub prevents regular users from accessing the Microsoft Store to download and install apps.</span></span>

## <span data-ttu-id="8cfc3-116">部署指南</span><span class="sxs-lookup"><span data-stu-id="8cfc3-116">Deployment guidelines</span></span>

<span data-ttu-id="8cfc3-117">你可以使用 Intune 将通用 Windows 平台（UWP）应用部署到 Surface Hub 2，从而使应用部署更易于使用设备。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-117">You can deploy Universal Windows Platform (UWP) apps to Surface Hub 2S using Intune, easing app deployment to devices.</span></span>

1. <span data-ttu-id="8cfc3-118">若要部署应用，请为你的组织启用 MDM。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-118">To deploy apps, enable MDM for your organization.</span></span> <span data-ttu-id="8cfc3-119">在 Intune 门户中，选择 " **Intune** " 作为你的 MDM 机构（推荐）。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-119">In the Intune portal, select **Intune** as your MDM Authority (recommended).</span></span> <br>

    ![选择 "MDM 机构"](images/sh2-set-intune5.png)

2. <span data-ttu-id="8cfc3-121">在 Intune 中启用 Microsoft Store for Business。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-121">Enable the Microsoft Store for Business in Intune.</span></span> <span data-ttu-id="8cfc3-122">打开 Intune，选择 "**客户端应用**  >  **Microsoft Store for Business"。**</span><span class="sxs-lookup"><span data-stu-id="8cfc3-122">Open Intune, select **Client apps** > **Microsoft Store for Business.**</span></span> <br>

    ![启用企业应用商店](images/sh2-deploy-apps-sync.png)

3. <span data-ttu-id="8cfc3-124">在 Intune 中打开**Microsoft Store for Business** ，然后选择 "**设置**  >  **分发**  >  **管理工具**"。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-124">In Intune open **Microsoft Store for Business** and select **Settings** > **Distribute** > **Management tools**.</span></span> <span data-ttu-id="8cfc3-125">选择 " **Microsoft Intune**作为你的管理工具"。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-125">Choose **Microsoft Intune** as your management tool.</span></span> <br>

    ![将 Intune 添加为你的管理工具](images/sh2-set-intune8.png)

4. <span data-ttu-id="8cfc3-127">在 Microsoft Store for Business 中，选择 "**设置**  >  **车间**  >  **购物体验**"，然后选择 "**显示脱机应用**"。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-127">In Microsoft Store for Business, select **Settings** > **Shop** > **Shopping Experience**, and then select **Show offline apps**.</span></span> <span data-ttu-id="8cfc3-128">脱机应用指可同步到 Intune 并集中部署到设备的应用。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-128">Offline apps refer to apps that can be synced to Intune and centrally deployed to a device.</span></span>
5. <span data-ttu-id="8cfc3-129">启用脱机购物后，你可以为可同步到 Intune 并部署为设备授权的应用获取脱机许可证。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-129">After enabling Offline shopping, you can acquire offline licenses for apps that you can sync to Intune and deploy as Device licensing.</span></span>
6. <span data-ttu-id="8cfc3-130">在**Intune**  >  **客户端应用**  >  **Microsoft Store for Business**中，选择 "**同步**"。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-130">In **Intune** > **Client apps** > **Microsoft Store for Business**, select **Sync**.</span></span>
7. <span data-ttu-id="8cfc3-131">在 "客户端应用" 页面中，在 "应用" 列表中搜索应用。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-131">In the Client apps page, search for the app in the apps list.</span></span> <span data-ttu-id="8cfc3-132">将应用分配到所需的设备组。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-132">Assign the apps to the desired device group or groups.</span></span> <span data-ttu-id="8cfc3-133">选择 "**作业**  >  **添加组**"。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-133">Select **Assignments** > **Add group**.</span></span> <br>

![\* 将应用分配给组 \*](images/sh2-assign-group.png) <br>

8. <span data-ttu-id="8cfc3-135">在 "作业类型" 下，选择 "**必需**"。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-135">Under assignment type, choose **Required**.</span></span> <br>

![\* 将应用分配给组 \*](images/sh2-add-group.png) <br>

9. <span data-ttu-id="8cfc3-137">对于选定的组，请选择 "**设备授权**"，然后选择 **"确定"** 并保存作业。</span><span class="sxs-lookup"><span data-stu-id="8cfc3-137">For the selected groups, choose **Device licensing** and then select **OK** and save the assignment.</span></span> <br>
 
![\* 将应用分配给组 \*](images/sh2-apps-assign.png)

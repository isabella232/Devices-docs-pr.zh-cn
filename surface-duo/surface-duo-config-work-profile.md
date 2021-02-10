---
title: 为 Surface Duo 配置 Android 企业版工作配置文件
description: 本文介绍了如何在 Surface Duo 上设置工作配置文件。
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 393844a4e4f0f06f16d11d1313ec9aacfa109d57
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326121"
---
# <span data-ttu-id="baa61-103">为 Surface Duo 配置 Android 企业版工作配置文件</span><span class="sxs-lookup"><span data-stu-id="baa61-103">Configure Android Enterprise Work Profile for Surface Duo</span></span>

<span data-ttu-id="baa61-104">工作配置文件面向 BYOD 部署，在 Duo 上为工作应用和数据提供了单独的空间，使组织可以完全控制其数据、应用和安全策略，而不会阻止员工将设备用于个人应用和数据。</span><span class="sxs-lookup"><span data-stu-id="baa61-104">Targeted at  BYOD deployments, work profiles provide a separate space on Duo for work apps and data, giving organizations full control of their data, apps, and security policies without preventing employees from using their device for personal apps and data.</span></span>

### <span data-ttu-id="baa61-105">设置 Android 企业版工作配置文件</span><span class="sxs-lookup"><span data-stu-id="baa61-105">Set up Android Enterprise Work Profile</span></span>

<span data-ttu-id="baa61-106">使用工作配置文件在用户拥有的 Android 设备上管理公司数据和应用。</span><span class="sxs-lookup"><span data-stu-id="baa61-106">Use work profiles to manage corporate data and apps on user-owned Android devices.</span></span> <span data-ttu-id="baa61-107">默认情况下，将启用对个人拥有的工作配置文件设备的注册，并且不需要进一步管理员配置。</span><span class="sxs-lookup"><span data-stu-id="baa61-107">By default, enrollment of personally owned work profile devices is enabled and requires no further admin configuration.</span></span>  

**<span data-ttu-id="baa61-108">若要启用企业工作配置文件，</span><span class="sxs-lookup"><span data-stu-id="baa61-108">To enable Enterprise Work Profile:</span></span>**

- <span data-ttu-id="baa61-109">在 Endpoint Manager 中，**选择设备**Android Android 注册，然后选择  >  \*\*\*\*  >  \*\*\*\*\*\*具有工作配置文件的个人设备\*\*。</span><span class="sxs-lookup"><span data-stu-id="baa61-109">In Endpoint Manager, select **Devices** > **Android** > **Android enrollment** and then select **Personal devices with work profile**.</span></span>
<br><br>
 ![启用企业工作配置文件](images/enroll-start.png)

 
**<span data-ttu-id="baa61-111">使用 Android 企业版工作配置文件登录到 Surface Duo</span><span class="sxs-lookup"><span data-stu-id="baa61-111">Sign into Surface Duo with Android Enterprise Work Profile</span></span>**

1. <span data-ttu-id="baa61-112">从 Google Play 应用商店安装公司门户应用，然后使用 Microsoft 工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="baa61-112">Install the Company Portal app from Google Play Store and sign in with your Microsoft work or school account.</span></span><br><br>
![登录到 Surface Duo](images/duo-wp-1.png)
 
2. <span data-ttu-id="baa61-114">在"Access 安装程序"页上，选择"**开始"。**</span><span class="sxs-lookup"><span data-stu-id="baa61-114">On the Access Setup page, select **Begin**.</span></span><br><br>
![Begin](images/duo-wp-2.png)

3. <span data-ttu-id="baa61-116">查看隐私页面上的信息，然后选择"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="baa61-116">Review the information on the privacy page and select **Continue**.</span></span><br><br>
 ![继续](images/duo-wp-3.png)
<br><br>
 ![选择"继续"](images/duo-wp-4.png)
 
4. <span data-ttu-id="baa61-119">工作配置文件设置完成后，选择 **"继续** 激活并注册设备"。</span><span class="sxs-lookup"><span data-stu-id="baa61-119">When the work profile setup completes, select **Continue** to activate and register the device.</span></span><br><br>
 ![选择"继续激活并注册设备"](images/duo-wp-5.png)

5. <span data-ttu-id="baa61-121">选择**继续**。</span><span class="sxs-lookup"><span data-stu-id="baa61-121">Select **Continue**.</span></span><br><br>
 ![再次选择"继续"](images/duo-wp-6.png)

6. <span data-ttu-id="baa61-123">激活工作配置文件后，选择" **继续** 更新设备设置"。</span><span class="sxs-lookup"><span data-stu-id="baa61-123">When you have activated the work profile, select **Continue** to update device settings.</span></span> <span data-ttu-id="baa61-124">本示例中，工作配置文件应用 MDM 设置，要求使用更强大的 6 位字母数字密码。</span><span class="sxs-lookup"><span data-stu-id="baa61-124">In this example, the work profile applies an MDM setting to require a stronger 6-digit alphanumeric password.</span></span> <br><br>

     ![字母数字密码示例](images/duo-wp-7.png)<br><br>
7. <span data-ttu-id="baa61-126">选择 **"** 解析"以输入所需的身份验证，然后选择" **继续** 完成工作配置文件设置"。</span><span class="sxs-lookup"><span data-stu-id="baa61-126">Select **Resolve** to enter the required authentication and then select **Continue** to complete Work Profile setup.</span></span> <br><br>
     ![选择"继续完成设置"](images/duo-wp-8.png)<br><br>
     ![完成设置](images/duo-wp-9.png)<br><br>

## <span data-ttu-id="baa61-129">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="baa61-129">Learn more</span></span>

- [<span data-ttu-id="baa61-130">设置 Android 企业版工作配置文件设备的注册</span><span class="sxs-lookup"><span data-stu-id="baa61-130">Set up enrollment of Android Enterprise work profile devices</span></span>](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)


---
title: 适用于 Windows 的 Surface 注册支持 Autopilot
description: 本文介绍向 Microsoft 支持提交 Autopilot 注册请求的要求。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 9a308edb37cc2cfd99490acad16bd2ae6a4d458a
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016464"
---
# <span data-ttu-id="50816-103">适用于 Windows 的 Surface 注册支持 Autopilot</span><span class="sxs-lookup"><span data-stu-id="50816-103">Surface Registration Support for Windows Autopilot</span></span>

<span data-ttu-id="50816-104">为 Windows Autopilot 部署注册 Surface 设备的简化过程现已提供 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="50816-104">A simplified process of registering Surface devices for Windows Autopilot deployment is now available from Microsoft Support.</span></span> <span data-ttu-id="50816-105">2020年9月开始，客户和 Microsoft 云解决方案提供商 (Csp) 可以通过向 Microsoft 支持人员提交请求来注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="50816-105">Beginning September 2020, customers and Microsoft Cloud Solution Providers (CSPs) can register Surface devices by submitting requests to Microsoft Support.</span></span> <span data-ttu-id="50816-106">此页面概述了以下受支持的 Autopilot 注册方案的要求：</span><span class="sxs-lookup"><span data-stu-id="50816-106">This page outlines the requirements for the following supported Autopilot registration scenarios:</span></span>
 

- <span data-ttu-id="50816-107">**Surface Device Autopilot 注册**。</span><span class="sxs-lookup"><span data-stu-id="50816-107">**Surface Device Autopilot Registration**.</span></span> <span data-ttu-id="50816-108">提交向 Windows Autopilot 注册 Surface 设备的请求。</span><span class="sxs-lookup"><span data-stu-id="50816-108">Submits request to register Surface devices into Windows Autopilot.</span></span>
- **<span data-ttu-id="50816-109">Surface 设备硬件哈希请求。</span><span class="sxs-lookup"><span data-stu-id="50816-109">Surface Device Hardware Hash Request.</span></span>** <span data-ttu-id="50816-110">向 Microsoft 支持人员提交请求，向您提供硬件哈希，客户或 Csp 可通过 Microsoft Intune 或 Microsoft 合作伙伴中心使用这些哈希。</span><span class="sxs-lookup"><span data-stu-id="50816-110">Submits request to Microsoft Support to provide you with hardware hashes that customers or CSPs can use to self-register devices via Microsoft Intune or the Microsoft Partner Center.</span></span>
- **<span data-ttu-id="50816-111">Surface 设备 Autopilot 注销。</span><span class="sxs-lookup"><span data-stu-id="50816-111">Surface Device Autopilot Deregistration.</span></span>** <span data-ttu-id="50816-112">提交从 Windows Autopilot 删除设备的请求，通常用于生命周期的设备结束。</span><span class="sxs-lookup"><span data-stu-id="50816-112">Submits request to delete devices from Windows Autopilot, typically used in device end of life scenarios.</span></span>

<span data-ttu-id="50816-113">有关将注册请求提交到 Microsoft 支持之前需要收集的信息的详细信息，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="50816-113">See the following table for details of the information you will need to collect prior to submitting registration requests to Microsoft Support.</span></span>
 
**<span data-ttu-id="50816-114">表 1. </span><span class="sxs-lookup"><span data-stu-id="50816-114">Table 1.</span></span> <span data-ttu-id="50816-115">Autopilot 注册请求所需的信息</span><span class="sxs-lookup"><span data-stu-id="50816-115">Required information for Autopilot registration requests</span></span>**
 

| <span data-ttu-id="50816-116">所需信息</span><span class="sxs-lookup"><span data-stu-id="50816-116">Required information</span></span>                   | <span data-ttu-id="50816-117">描述</span><span class="sxs-lookup"><span data-stu-id="50816-117">Description</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="50816-118">Autopilot 注册</span><span class="sxs-lookup"><span data-stu-id="50816-118">Autopilot Registration</span></span> | <span data-ttu-id="50816-119">硬件哈希请求</span><span class="sxs-lookup"><span data-stu-id="50816-119">Hardware Hash Request</span></span> | <span data-ttu-id="50816-120">Autopilot</span><span class="sxs-lookup"><span data-stu-id="50816-120">Autopilot</span></span><br><span data-ttu-id="50816-121">注册</span><span class="sxs-lookup"><span data-stu-id="50816-121">Deregistration</span></span> |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **<span data-ttu-id="50816-122">Azure Active Directory 租户 ID</span><span class="sxs-lookup"><span data-stu-id="50816-122">Azure Active Directory Tenant ID</span></span>**   | <span data-ttu-id="50816-123">你的 Azure Active Directory 租户 ID 是与你的组织名称或域不同 (GUID) 的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="50816-123">Your Azure Active Directory tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain.</span></span><br> <br><span data-ttu-id="50816-124">在 [此处](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)查找租户 ID 登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="50816-124">To find your Tenant ID sign into the Azure Portal [here](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> | <span data-ttu-id="50816-125">Y</span><span class="sxs-lookup"><span data-stu-id="50816-125">Y</span></span>                      | <span data-ttu-id="50816-126">N</span><span class="sxs-lookup"><span data-stu-id="50816-126">N</span></span>                     | <span data-ttu-id="50816-127">Y</span><span class="sxs-lookup"><span data-stu-id="50816-127">Y</span></span>                           |
| **<span data-ttu-id="50816-128">Azure Active Directory 域名</span><span class="sxs-lookup"><span data-stu-id="50816-128">Azure Active Directory Domain Name</span></span>** | <span data-ttu-id="50816-129">顶级域名;例如，contoso.com。</span><span class="sxs-lookup"><span data-stu-id="50816-129">Your top-level domain name; for example, contoso.com.</span></span>                                                                                                                                                                                                                                          | <span data-ttu-id="50816-130">Y</span><span class="sxs-lookup"><span data-stu-id="50816-130">Y</span></span>                      | <span data-ttu-id="50816-131">N</span><span class="sxs-lookup"><span data-stu-id="50816-131">N</span></span>                     | <span data-ttu-id="50816-132">Y</span><span class="sxs-lookup"><span data-stu-id="50816-132">Y</span></span>                           |
| **<span data-ttu-id="50816-133">所有权证明</span><span class="sxs-lookup"><span data-stu-id="50816-133">Proof of ownership</span></span>**                 | <span data-ttu-id="50816-134">通过以 PDF 格式上载原始帐单或发票，验证所有权证明。</span><span class="sxs-lookup"><span data-stu-id="50816-134">Verify proof of ownership by uploading the original bill of sale or invoice in PDF format.</span></span> <span data-ttu-id="50816-135">屏幕截图不接受。</span><span class="sxs-lookup"><span data-stu-id="50816-135">Screenshots are not accepted.</span></span><br> <br><span data-ttu-id="50816-136">账单或发票必须包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="50816-136">The bill of sale or invoice  must include the following:</span></span><br><span data-ttu-id="50816-137">设备序列号。</span><span class="sxs-lookup"><span data-stu-id="50816-137">Device serial numbers.</span></span><br><span data-ttu-id="50816-138">公司名称。</span><span class="sxs-lookup"><span data-stu-id="50816-138">Company name.</span></span>                                                           | <span data-ttu-id="50816-139">Y</span><span class="sxs-lookup"><span data-stu-id="50816-139">Y</span></span>                      | <span data-ttu-id="50816-140">Y</span><span class="sxs-lookup"><span data-stu-id="50816-140">Y</span></span>                     | <span data-ttu-id="50816-141">Y</span><span class="sxs-lookup"><span data-stu-id="50816-141">Y</span></span>                           |
| **<span data-ttu-id="50816-142">设备序列号</span><span class="sxs-lookup"><span data-stu-id="50816-142">Device serial numbers</span></span>**              | <span data-ttu-id="50816-143">以 CSV 格式上载 Excel 文件，并在新行中使用每个设备序列号。</span><span class="sxs-lookup"><span data-stu-id="50816-143">Upload Excel file in CSV format with each device serial number in a new line.</span></span>                                                                                                                                                                                                                  | <span data-ttu-id="50816-144">Y</span><span class="sxs-lookup"><span data-stu-id="50816-144">Y</span></span>                      | <span data-ttu-id="50816-145">Y</span><span class="sxs-lookup"><span data-stu-id="50816-145">Y</span></span>                     | <span data-ttu-id="50816-146">Y</span><span class="sxs-lookup"><span data-stu-id="50816-146">Y</span></span>                           |

 

## <span data-ttu-id="50816-147">提交支持请求</span><span class="sxs-lookup"><span data-stu-id="50816-147">Submit support requests</span></span>

  [![G<span data-ttu-id="50816-148">et Autopilot 注册支持 Surface]</span><span class="sxs-lookup"><span data-stu-id="50816-148">et Autopilot Registration Support for Surface]</span></span>(images/autopilot-reg-support-surface.png)](https://support.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <span data-ttu-id="50816-149">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="50816-149">Learn more</span></span>

- [<span data-ttu-id="50816-150">Windows Autopilot 和 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="50816-150">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md)
- [<span data-ttu-id="50816-151">使用 Windows Autopilot 在 Intune 中注册 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="50816-151">Enroll Windows devices in Intune by using Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [<span data-ttu-id="50816-152">Windows Autopilot 概述</span><span class="sxs-lookup"><span data-stu-id="50816-152">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 


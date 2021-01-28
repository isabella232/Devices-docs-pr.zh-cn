---
title: 适用于 Windows Autopilot 的 Surface 注册支持
description: 本文介绍了向 Microsoft 支持人员提交 Autopilot 注册请求的要求。
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
ms.openlocfilehash: b31cacad5a744dcb29fc3dd2822c656d528fcd40
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304835"
---
# <span data-ttu-id="5bb74-103">适用于 Windows Autopilot 的 Surface 注册支持</span><span class="sxs-lookup"><span data-stu-id="5bb74-103">Surface Registration Support for Windows Autopilot</span></span>

<span data-ttu-id="5bb74-104">Microsoft 支持现已提供注册 Surface 设备进行 Windows Autopilot 部署的简化过程。</span><span class="sxs-lookup"><span data-stu-id="5bb74-104">A simplified process of registering Surface devices for Windows Autopilot deployment is now available from Microsoft Support.</span></span> <span data-ttu-id="5bb74-105">从 2020 年 9 月开始，客户和 Microsoft 云解决方案提供商 (云解决方案提供商) 向 Microsoft 支持人员提交请求来注册 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="5bb74-105">Beginning September 2020, customers and Microsoft Cloud Solution Providers (CSPs) can register Surface devices by submitting requests to Microsoft Support.</span></span> <span data-ttu-id="5bb74-106">此页面概述了以下受支持的 Autopilot 注册方案的要求：</span><span class="sxs-lookup"><span data-stu-id="5bb74-106">This page outlines the requirements for the following supported Autopilot registration scenarios:</span></span>
 
- <span data-ttu-id="5bb74-107">**Surface Device Autopilot Registration**.</span><span class="sxs-lookup"><span data-stu-id="5bb74-107">**Surface Device Autopilot Registration**.</span></span> <span data-ttu-id="5bb74-108">提交将 Surface 设备注册到 Windows Autopilot 的请求。</span><span class="sxs-lookup"><span data-stu-id="5bb74-108">Submits request to register Surface devices into Windows Autopilot.</span></span>
- **<span data-ttu-id="5bb74-109">Surface 设备硬件哈希请求。</span><span class="sxs-lookup"><span data-stu-id="5bb74-109">Surface Device Hardware Hash Request.</span></span>** <span data-ttu-id="5bb74-110">向 Microsoft 支持人员提交请求，以向您提供客户或 CSP 可用于通过 Microsoft Intune 或 Microsoft 合作伙伴中心自行注册设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="5bb74-110">Submits request to Microsoft Support to provide you with hardware hashes that customers or CSPs can use to self-register devices via Microsoft Intune or the Microsoft Partner Center.</span></span>
- **<span data-ttu-id="5bb74-111">Surface Device Autopilot Deregistration。</span><span class="sxs-lookup"><span data-stu-id="5bb74-111">Surface Device Autopilot Deregistration.</span></span>** <span data-ttu-id="5bb74-112">提交从 Windows Autopilot 删除设备的请求，通常用于设备生命周期结束方案。</span><span class="sxs-lookup"><span data-stu-id="5bb74-112">Submits request to delete devices from Windows Autopilot, typically used in device end of life scenarios.</span></span>

<span data-ttu-id="5bb74-113">有关向 Microsoft 支持人员提交注册请求之前需要收集的信息的详细信息，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5bb74-113">See the following table for details of the information you will need to collect prior to submitting registration requests to Microsoft Support.</span></span> <span data-ttu-id="5bb74-114">有关所有 Surface 设备的官方系统型号名称，请参阅 [Surface System SKU 参考](surface-system-sku-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="5bb74-114">For the official System Model names of all Surface devices, refer to [Surface System SKU reference](surface-system-sku-reference.md).</span></span>
 
**<span data-ttu-id="5bb74-115">表 1. </span><span class="sxs-lookup"><span data-stu-id="5bb74-115">Table 1.</span></span> <span data-ttu-id="5bb74-116">Autopilot 注册请求的必需信息</span><span class="sxs-lookup"><span data-stu-id="5bb74-116">Required information for Autopilot registration requests</span></span>**
 

| <span data-ttu-id="5bb74-117">所需信息</span><span class="sxs-lookup"><span data-stu-id="5bb74-117">Required information</span></span>                   | <span data-ttu-id="5bb74-118">描述</span><span class="sxs-lookup"><span data-stu-id="5bb74-118">Description</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="5bb74-119">Autopilot 注册</span><span class="sxs-lookup"><span data-stu-id="5bb74-119">Autopilot Registration</span></span> | <span data-ttu-id="5bb74-120">硬件哈希请求</span><span class="sxs-lookup"><span data-stu-id="5bb74-120">Hardware Hash Request</span></span> | <span data-ttu-id="5bb74-121">Autopilot</span><span class="sxs-lookup"><span data-stu-id="5bb74-121">Autopilot</span></span><br><span data-ttu-id="5bb74-122">取消注册</span><span class="sxs-lookup"><span data-stu-id="5bb74-122">Deregistration</span></span> |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **<span data-ttu-id="5bb74-123">Azure Active Directory 租户 ID</span><span class="sxs-lookup"><span data-stu-id="5bb74-123">Azure Active Directory Tenant ID</span></span>**   | <span data-ttu-id="5bb74-124">Azure Active Directory 租户 ID 是 GUID (全局唯一标识符) 与组织名称或域不同。</span><span class="sxs-lookup"><span data-stu-id="5bb74-124">Your Azure Active Directory tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain.</span></span><br> <br><span data-ttu-id="5bb74-125">若要在此处找到你的租户 ID 登录 Azure[门户，](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="5bb74-125">To find your Tenant ID sign into the Azure Portal [here](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> | <span data-ttu-id="5bb74-126">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-126">Y</span></span>                      | <span data-ttu-id="5bb74-127">N</span><span class="sxs-lookup"><span data-stu-id="5bb74-127">N</span></span>                     | <span data-ttu-id="5bb74-128">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-128">Y</span></span>                           |
| **<span data-ttu-id="5bb74-129">Azure Active Directory 域名</span><span class="sxs-lookup"><span data-stu-id="5bb74-129">Azure Active Directory Domain Name</span></span>** | <span data-ttu-id="5bb74-130">顶级域名;例如，contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5bb74-130">Your top-level domain name; for example, contoso.com.</span></span>                                                                                                                                                                                                                                          | <span data-ttu-id="5bb74-131">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-131">Y</span></span>                      | <span data-ttu-id="5bb74-132">N</span><span class="sxs-lookup"><span data-stu-id="5bb74-132">N</span></span>                     | <span data-ttu-id="5bb74-133">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-133">Y</span></span>                           |
| **<span data-ttu-id="5bb74-134">所有权证明</span><span class="sxs-lookup"><span data-stu-id="5bb74-134">Proof of ownership</span></span>**                 | <span data-ttu-id="5bb74-135">通过上载 PDF 格式的原始销售单或发票来验证所有权证明。</span><span class="sxs-lookup"><span data-stu-id="5bb74-135">Verify proof of ownership by uploading the original bill of sale or invoice in PDF format.</span></span> <span data-ttu-id="5bb74-136">不接受屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="5bb74-136">Screenshots are not accepted.</span></span><br> <br><span data-ttu-id="5bb74-137">销售单或发票必须包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="5bb74-137">The bill of sale or invoice  must include the following:</span></span><br><span data-ttu-id="5bb74-138">设备序列号。</span><span class="sxs-lookup"><span data-stu-id="5bb74-138">Device serial numbers.</span></span><br><span data-ttu-id="5bb74-139">公司名称。</span><span class="sxs-lookup"><span data-stu-id="5bb74-139">Company name.</span></span>                                                           | <span data-ttu-id="5bb74-140">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-140">Y</span></span>                      | <span data-ttu-id="5bb74-141">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-141">Y</span></span>                     | <span data-ttu-id="5bb74-142">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-142">Y</span></span>                           |
| **<span data-ttu-id="5bb74-143">设备序列号</span><span class="sxs-lookup"><span data-stu-id="5bb74-143">Device serial numbers</span></span>**              | <span data-ttu-id="5bb74-144">使用新行中每个设备序列号上传 CSV 格式的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="5bb74-144">Upload Excel file in CSV format with each device serial number in a new line.</span></span>                                                                                                                                                                                                                  | <span data-ttu-id="5bb74-145">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-145">Y</span></span>                      | <span data-ttu-id="5bb74-146">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-146">Y</span></span>                     | <span data-ttu-id="5bb74-147">Y</span><span class="sxs-lookup"><span data-stu-id="5bb74-147">Y</span></span>                           |

 

## <span data-ttu-id="5bb74-148">提交支持请求</span><span class="sxs-lookup"><span data-stu-id="5bb74-148">Submit support requests</span></span>

  [![G<span data-ttu-id="5bb74-149">Surface 的 et Autopilot 注册支持]</span><span class="sxs-lookup"><span data-stu-id="5bb74-149">et Autopilot Registration Support for Surface]</span></span>(images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <span data-ttu-id="5bb74-150">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="5bb74-150">Learn more</span></span>

- [<span data-ttu-id="5bb74-151">Windows Autopilot 和 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="5bb74-151">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md)
- [<span data-ttu-id="5bb74-152">使用 Windows Autopilot 在 Intune 中注册 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="5bb74-152">Enroll Windows devices in Intune by using Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [<span data-ttu-id="5bb74-153">Windows Autopilot 概述</span><span class="sxs-lookup"><span data-stu-id="5bb74-153">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/windows-autopilot)
- [<span data-ttu-id="5bb74-154">Surface 系统 SKU 参考</span><span class="sxs-lookup"><span data-stu-id="5bb74-154">Surface System SKU reference</span></span>](surface-system-sku-reference.md)

 
 
 


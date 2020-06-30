---
title: Surface 系统 SKU 参考
description: 本主题提供了可用于快速确定特定设备的计算机状态的系统 SKU 名称的参考。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830888"
---
# <span data-ttu-id="38fc5-103">Surface System SKU 参考</span><span class="sxs-lookup"><span data-stu-id="38fc5-103">Surface System SKU Reference</span></span>
<span data-ttu-id="38fc5-104">此文档提供系统 SKU 名称的参考，可用于快速确定特定设备的计算机状态（使用 PowerShell、WMI 和相关工具）。</span><span class="sxs-lookup"><span data-stu-id="38fc5-104">This document provides a reference of System SKU names that you can use to quickly determine the machine state of a specific device using PowerShell, WMI, and related tools.</span></span> 

<span data-ttu-id="38fc5-105">系统 SKU 是存储在 Surface 设备的 UEFI 层的系统管理 BIOS （SMBIOS）表中的变量（以及系统模型和其他）。</span><span class="sxs-lookup"><span data-stu-id="38fc5-105">System SKU is a variable (along with System Model and others) stored in System Management BIOS (SMBIOS) tables in the UEFI layer of Surface devices.</span></span>  <span data-ttu-id="38fc5-106">无论何时需要区分具有相同系统模型名称的设备（如 Surface Pro 和 Surface Pro 和 LTE Advanced），都可以使用系统 SKU 名称。</span><span class="sxs-lookup"><span data-stu-id="38fc5-106">Use the System SKU name whenever you need to differentiate between devices with the same System Model name, such as Surface Pro and Surface Pro with LTE Advanced.</span></span> 

| **<span data-ttu-id="38fc5-107">设备</span><span class="sxs-lookup"><span data-stu-id="38fc5-107">Device</span></span>**| **<span data-ttu-id="38fc5-108">系统型号</span><span class="sxs-lookup"><span data-stu-id="38fc5-108">System Model</span></span>** | **<span data-ttu-id="38fc5-109">系统 SKU</span><span class="sxs-lookup"><span data-stu-id="38fc5-109">System SKU</span></span>**|
| --- | ---| --- |
| <span data-ttu-id="38fc5-110">Surface 3 WiFI</span><span class="sxs-lookup"><span data-stu-id="38fc5-110">Surface 3 WiFI</span></span>                                               | <span data-ttu-id="38fc5-111">Surface 3</span><span class="sxs-lookup"><span data-stu-id="38fc5-111">Surface 3</span></span>        | <span data-ttu-id="38fc5-112">Surface_3</span><span class="sxs-lookup"><span data-stu-id="38fc5-112">Surface_3</span></span>                        |
| <span data-ttu-id="38fc5-113">&T 上的 Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="38fc5-113">Surface 3 LTE AT&T</span></span>                                           | <span data-ttu-id="38fc5-114">Surface 3</span><span class="sxs-lookup"><span data-stu-id="38fc5-114">Surface 3</span></span>        | <span data-ttu-id="38fc5-115">Surface_3_US1</span><span class="sxs-lookup"><span data-stu-id="38fc5-115">Surface_3_US1</span></span>                    |
| <span data-ttu-id="38fc5-116">Surface 3 LTE Verizon</span><span class="sxs-lookup"><span data-stu-id="38fc5-116">Surface 3 LTE Verizon</span></span>                                        | <span data-ttu-id="38fc5-117">Surface 3</span><span class="sxs-lookup"><span data-stu-id="38fc5-117">Surface 3</span></span>        | <span data-ttu-id="38fc5-118">Surface_3_US2</span><span class="sxs-lookup"><span data-stu-id="38fc5-118">Surface_3_US2</span></span>                    |
| <span data-ttu-id="38fc5-119">Surface 3 LTE 北美</span><span class="sxs-lookup"><span data-stu-id="38fc5-119">Surface 3 LTE North America</span></span>                                  | <span data-ttu-id="38fc5-120">Surface 3</span><span class="sxs-lookup"><span data-stu-id="38fc5-120">Surface 3</span></span>        | <span data-ttu-id="38fc5-121">Surface_3_NAG</span><span class="sxs-lookup"><span data-stu-id="38fc5-121">Surface_3_NAG</span></span>                    |
| <span data-ttu-id="38fc5-122">在北美和 T 形手机外的第3面 LTE</span><span class="sxs-lookup"><span data-stu-id="38fc5-122">Surface 3 LTE Outside of North America and T-Mobile In Japan</span></span> | <span data-ttu-id="38fc5-123">Surface 3</span><span class="sxs-lookup"><span data-stu-id="38fc5-123">Surface 3</span></span>        | <span data-ttu-id="38fc5-124">Surface_3_ROW</span><span class="sxs-lookup"><span data-stu-id="38fc5-124">Surface_3_ROW</span></span>                    |
| <span data-ttu-id="38fc5-125">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="38fc5-125">Surface Pro</span></span>                                                  | <span data-ttu-id="38fc5-126">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="38fc5-126">Surface Pro</span></span>      | <span data-ttu-id="38fc5-127">Surface_Pro_1796</span><span class="sxs-lookup"><span data-stu-id="38fc5-127">Surface_Pro_1796</span></span>                 |
| <span data-ttu-id="38fc5-128">带有 LTE Advanced 的 Surface Pro </span><span class="sxs-lookup"><span data-stu-id="38fc5-128">Surface Pro with LTE Advanced</span></span>                                | <span data-ttu-id="38fc5-129">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="38fc5-129">Surface Pro</span></span>      | <span data-ttu-id="38fc5-130">Surface_Pro_1807</span><span class="sxs-lookup"><span data-stu-id="38fc5-130">Surface_Pro_1807</span></span>                 |
| <span data-ttu-id="38fc5-131">Surface Book 2 13inch</span><span class="sxs-lookup"><span data-stu-id="38fc5-131">Surface Book 2 13inch</span></span>                                        | <span data-ttu-id="38fc5-132">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="38fc5-132">Surface Book 2</span></span>   | <span data-ttu-id="38fc5-133">Surface_Book_1832</span><span class="sxs-lookup"><span data-stu-id="38fc5-133">Surface_Book_1832</span></span>                |
| <span data-ttu-id="38fc5-134">Surface Book 2 15inch</span><span class="sxs-lookup"><span data-stu-id="38fc5-134">Surface Book 2 15inch</span></span>                                        | <span data-ttu-id="38fc5-135">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="38fc5-135">Surface Book 2</span></span>   | <span data-ttu-id="38fc5-136">Surface_Book_1793</span><span class="sxs-lookup"><span data-stu-id="38fc5-136">Surface_Book_1793</span></span>                |
| <span data-ttu-id="38fc5-137">Surface Go 消费者</span><span class="sxs-lookup"><span data-stu-id="38fc5-137">Surface Go Consumer</span></span>                                          | <span data-ttu-id="38fc5-138">Surface Go</span><span class="sxs-lookup"><span data-stu-id="38fc5-138">Surface Go</span></span>       | <span data-ttu-id="38fc5-139">Surface_Go_1824_Consumer</span><span class="sxs-lookup"><span data-stu-id="38fc5-139">Surface_Go_1824_Consumer</span></span>         |
| <span data-ttu-id="38fc5-140">Surface Go 商业版</span><span class="sxs-lookup"><span data-stu-id="38fc5-140">Surface Go Commercial</span></span>                                        | <span data-ttu-id="38fc5-141">Surface Go</span><span class="sxs-lookup"><span data-stu-id="38fc5-141">Surface Go</span></span>       | <span data-ttu-id="38fc5-142">Surface_Go_1824_Commercial</span><span class="sxs-lookup"><span data-stu-id="38fc5-142">Surface_Go_1824_Commercial</span></span>       |
| <span data-ttu-id="38fc5-143">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="38fc5-143">Surface Go 2</span></span>                                                 | <span data-ttu-id="38fc5-144">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="38fc5-144">Surface Go 2</span></span>     | <span data-ttu-id="38fc5-145">Surface_Go_2_1927</span><span class="sxs-lookup"><span data-stu-id="38fc5-145">Surface_Go_2_1927</span></span>                |
| <span data-ttu-id="38fc5-146">Surface Pro 6 消费者</span><span class="sxs-lookup"><span data-stu-id="38fc5-146">Surface Pro 6 Consumer</span></span>                                       | <span data-ttu-id="38fc5-147">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="38fc5-147">Surface Pro 6</span></span>    | <span data-ttu-id="38fc5-148">Surface_Pro_6_1796_Consumer</span><span class="sxs-lookup"><span data-stu-id="38fc5-148">Surface_Pro_6_1796_Consumer</span></span>      |
| <span data-ttu-id="38fc5-149">Surface Pro 6 商业版</span><span class="sxs-lookup"><span data-stu-id="38fc5-149">Surface Pro 6 Commercial</span></span>                                     | <span data-ttu-id="38fc5-150">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="38fc5-150">Surface Pro 6</span></span>    | <span data-ttu-id="38fc5-151">Surface_Pro_6_1796_Commercial</span><span class="sxs-lookup"><span data-stu-id="38fc5-151">Surface_Pro_6_1796_Commercial</span></span>    |
| <span data-ttu-id="38fc5-152">Surface 笔记本电脑2消费者</span><span class="sxs-lookup"><span data-stu-id="38fc5-152">Surface Laptop 2 Consumer</span></span>                                    | <span data-ttu-id="38fc5-153">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="38fc5-153">Surface Laptop 2</span></span> | <span data-ttu-id="38fc5-154">Surface_Laptop_2_1769_Consumer</span><span class="sxs-lookup"><span data-stu-id="38fc5-154">Surface_Laptop_2_1769_Consumer</span></span>   |
| <span data-ttu-id="38fc5-155">Surface 笔记本电脑2商业版</span><span class="sxs-lookup"><span data-stu-id="38fc5-155">Surface Laptop 2 Commercial</span></span>                                  | <span data-ttu-id="38fc5-156">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="38fc5-156">Surface Laptop 2</span></span> | <span data-ttu-id="38fc5-157">Surface_Laptop_2_1769_Commercial</span><span class="sxs-lookup"><span data-stu-id="38fc5-157">Surface_Laptop_2_1769_Commercial</span></span> |

## <span data-ttu-id="38fc5-158">使用系统 SKU 变量</span><span class="sxs-lookup"><span data-stu-id="38fc5-158">Using System SKU variables</span></span> 

### <span data-ttu-id="38fc5-159">PowerShell</span><span class="sxs-lookup"><span data-stu-id="38fc5-159">PowerShell</span></span>

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### <span data-ttu-id="38fc5-160">系统信息</span><span class="sxs-lookup"><span data-stu-id="38fc5-160">System Information</span></span>
<span data-ttu-id="38fc5-161">您还可以在 "系统信息" 中查找设备的系统 SKU 和系统模型。</span><span class="sxs-lookup"><span data-stu-id="38fc5-161">You can also find the System SKU and System Model for a device in System Information.</span></span> 
- <span data-ttu-id="38fc5-162">单击 "**开始**  >   **MSInfo32**"。</span><span class="sxs-lookup"><span data-stu-id="38fc5-162">Click **Start** >  **MSInfo32**.</span></span>  

### <span data-ttu-id="38fc5-163">CIM</span><span class="sxs-lookup"><span data-stu-id="38fc5-163">WMI</span></span>
<span data-ttu-id="38fc5-164">你可以使用 Microsoft 部署工具包（MDT）或 Microsoft 终结点配置管理器中的任务序列 WMI 条件中的系统 SKU 变量。</span><span class="sxs-lookup"><span data-stu-id="38fc5-164">You can use System SKU variables in a Task Sequence WMI Condition in the Microsoft Deployment Toolkit (MDT) or Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="38fc5-165">例如：</span><span class="sxs-lookup"><span data-stu-id="38fc5-165">For example:</span></span> 

    - <span data-ttu-id="38fc5-166">WMI 命名空间-Root\WMI</span><span class="sxs-lookup"><span data-stu-id="38fc5-166">WMI Namespace – Root\WMI</span></span>
    - <span data-ttu-id="38fc5-167">WQL 查询-从 MS_SystemInformation 中选择 "\* SystemSKU =" Surface_Pro_1796 "</span><span class="sxs-lookup"><span data-stu-id="38fc5-167">WQL Query – SELECT \* FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"</span></span>

 
 
 



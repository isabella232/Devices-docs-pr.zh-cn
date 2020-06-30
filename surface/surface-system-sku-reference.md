---
title: 系统 SKU 参考（Surface）
description: 请参阅系统模型和系统 SKU 名称的参考。
keywords: uefi、配置、固件、安全、semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 03/09/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 1fa192902b17ca811d4ecc8eac65abe1655ce370
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831003"
---
# <span data-ttu-id="ce049-104">系统 SKU 参考</span><span class="sxs-lookup"><span data-stu-id="ce049-104">System SKU reference</span></span>

<span data-ttu-id="ce049-105">此文档提供系统模型和系统 SKU 名称的参考，可用于通过使用 PowerShell 或 WMI 快速确定特定设备的计算机状态。</span><span class="sxs-lookup"><span data-stu-id="ce049-105">This document provides a reference of System Model and System SKU names that you can use to quickly determine the machine state of a specific device by using PowerShell or WMI.</span></span>

<span data-ttu-id="ce049-106">系统型号和系统 SKU 是存储在 Surface 设备的 UEFI 层的系统管理 BIOS （SMBIOS）表中的变量。</span><span class="sxs-lookup"><span data-stu-id="ce049-106">System Model and System SKU are variables that are stored in the System Management BIOS (SMBIOS) tables in the UEFI layer of Surface devices.</span></span> <span data-ttu-id="ce049-107">需要使用系统 SKU 名称来区分具有相同系统模型名称的设备，例如 Surface Pro 和 Surface Pro 和 LTE Advanced。</span><span class="sxs-lookup"><span data-stu-id="ce049-107">The System SKU name is required to differentiate between devices that have the same System Model name, such as Surface Pro and Surface Pro with LTE Advanced.</span></span> 

| <span data-ttu-id="ce049-108">设备</span><span class="sxs-lookup"><span data-stu-id="ce049-108">Device</span></span>   | <span data-ttu-id="ce049-109">系统型号</span><span class="sxs-lookup"><span data-stu-id="ce049-109">System Model</span></span> | <span data-ttu-id="ce049-110">系统 SKU</span><span class="sxs-lookup"><span data-stu-id="ce049-110">System SKU</span></span>       |
| ---------- | ----------- | -------------- |
| <span data-ttu-id="ce049-111">Surface 3 WiFI</span><span class="sxs-lookup"><span data-stu-id="ce049-111">Surface 3 WiFI</span></span>                                               | <span data-ttu-id="ce049-112">Surface 3</span><span class="sxs-lookup"><span data-stu-id="ce049-112">Surface 3</span></span>        | <span data-ttu-id="ce049-113">Surface_3</span><span class="sxs-lookup"><span data-stu-id="ce049-113">Surface_3</span></span>                        |
| <span data-ttu-id="ce049-114">&T 上的 Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="ce049-114">Surface 3 LTE AT&T</span></span>                                           | <span data-ttu-id="ce049-115">Surface 3</span><span class="sxs-lookup"><span data-stu-id="ce049-115">Surface 3</span></span>        | <span data-ttu-id="ce049-116">Surface_3_US1</span><span class="sxs-lookup"><span data-stu-id="ce049-116">Surface_3_US1</span></span>                    |
| <span data-ttu-id="ce049-117">Surface 3 LTE Verizon</span><span class="sxs-lookup"><span data-stu-id="ce049-117">Surface 3 LTE Verizon</span></span>                                        | <span data-ttu-id="ce049-118">Surface 3</span><span class="sxs-lookup"><span data-stu-id="ce049-118">Surface 3</span></span>        | <span data-ttu-id="ce049-119">Surface_3_US2</span><span class="sxs-lookup"><span data-stu-id="ce049-119">Surface_3_US2</span></span>                    |
| <span data-ttu-id="ce049-120">Surface 3 LTE 北美</span><span class="sxs-lookup"><span data-stu-id="ce049-120">Surface 3 LTE North America</span></span>                                  | <span data-ttu-id="ce049-121">Surface 3</span><span class="sxs-lookup"><span data-stu-id="ce049-121">Surface 3</span></span>        | <span data-ttu-id="ce049-122">Surface_3_NAG</span><span class="sxs-lookup"><span data-stu-id="ce049-122">Surface_3_NAG</span></span>                    |
| <span data-ttu-id="ce049-123">北美和 Y 外的 Surface 3 LTE！在日本的手机</span><span class="sxs-lookup"><span data-stu-id="ce049-123">Surface 3 LTE outside of North America and Y!mobile in Japan</span></span> | <span data-ttu-id="ce049-124">Surface 3</span><span class="sxs-lookup"><span data-stu-id="ce049-124">Surface 3</span></span>        | <span data-ttu-id="ce049-125">Surface_3_ROW</span><span class="sxs-lookup"><span data-stu-id="ce049-125">Surface_3_ROW</span></span>                    |
| <span data-ttu-id="ce049-126">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="ce049-126">Surface Pro</span></span>                                                  | <span data-ttu-id="ce049-127">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="ce049-127">Surface Pro</span></span>      | <span data-ttu-id="ce049-128">Surface_Pro_1796</span><span class="sxs-lookup"><span data-stu-id="ce049-128">Surface_Pro_1796</span></span>                 |
| <span data-ttu-id="ce049-129">带有 LTE Advanced 的 Surface Pro </span><span class="sxs-lookup"><span data-stu-id="ce049-129">Surface Pro with LTE Advanced</span></span>                                | <span data-ttu-id="ce049-130">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="ce049-130">Surface Pro</span></span>      | <span data-ttu-id="ce049-131">Surface_Pro_1807</span><span class="sxs-lookup"><span data-stu-id="ce049-131">Surface_Pro_1807</span></span>                 |
| <span data-ttu-id="ce049-132">Surface Book 2 13 "</span><span class="sxs-lookup"><span data-stu-id="ce049-132">Surface Book 2 13"</span></span>                                        | <span data-ttu-id="ce049-133">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="ce049-133">Surface Book 2</span></span>   | <span data-ttu-id="ce049-134">Surface_Book_1832</span><span class="sxs-lookup"><span data-stu-id="ce049-134">Surface_Book_1832</span></span>                |
| <span data-ttu-id="ce049-135">Surface Book 2 15 "</span><span class="sxs-lookup"><span data-stu-id="ce049-135">Surface Book 2 15"</span></span>                                        | <span data-ttu-id="ce049-136">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="ce049-136">Surface Book 2</span></span>   | <span data-ttu-id="ce049-137">Surface_Book_1793</span><span class="sxs-lookup"><span data-stu-id="ce049-137">Surface_Book_1793</span></span>                |
| <span data-ttu-id="ce049-138">Surface Go LTE 消费者</span><span class="sxs-lookup"><span data-stu-id="ce049-138">Surface Go LTE Consumer</span></span>  | <span data-ttu-id="ce049-139">Surface Go</span><span class="sxs-lookup"><span data-stu-id="ce049-139">Surface Go</span></span> | <span data-ttu-id="ce049-140">Surface_Go_1825_Consumer</span><span class="sxs-lookup"><span data-stu-id="ce049-140">Surface_Go_1825_Consumer</span></span> |
| <span data-ttu-id="ce049-141">Surface Go LTE 商业版</span><span class="sxs-lookup"><span data-stu-id="ce049-141">Surface Go LTE Commercial</span></span> | <span data-ttu-id="ce049-142">系统前往</span><span class="sxs-lookup"><span data-stu-id="ce049-142">System Go</span></span> | <span data-ttu-id="ce049-143">Surface_Go_1825_Commercial</span><span class="sxs-lookup"><span data-stu-id="ce049-143">Surface_Go_1825_Commercial</span></span> |
| <span data-ttu-id="ce049-144">Surface Go 消费者</span><span class="sxs-lookup"><span data-stu-id="ce049-144">Surface Go Consumer</span></span>                                          | <span data-ttu-id="ce049-145">Surface Go</span><span class="sxs-lookup"><span data-stu-id="ce049-145">Surface Go</span></span>       | <span data-ttu-id="ce049-146">Surface_Go_1824_Consumer</span><span class="sxs-lookup"><span data-stu-id="ce049-146">Surface_Go_1824_Consumer</span></span>         |
| <span data-ttu-id="ce049-147">Surface Go 商业版</span><span class="sxs-lookup"><span data-stu-id="ce049-147">Surface Go Commercial</span></span>                                        | <span data-ttu-id="ce049-148">Surface Go</span><span class="sxs-lookup"><span data-stu-id="ce049-148">Surface Go</span></span>       | <span data-ttu-id="ce049-149">Surface_Go_1824_Commercial</span><span class="sxs-lookup"><span data-stu-id="ce049-149">Surface_Go_1824_Commercial</span></span>       |
| <span data-ttu-id="ce049-150">Surface Pro 6 消费者</span><span class="sxs-lookup"><span data-stu-id="ce049-150">Surface Pro 6 Consumer</span></span>                                       | <span data-ttu-id="ce049-151">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="ce049-151">Surface Pro 6</span></span>    | <span data-ttu-id="ce049-152">Surface_Pro_6_1796_Consumer</span><span class="sxs-lookup"><span data-stu-id="ce049-152">Surface_Pro_6_1796_Consumer</span></span>      |
| <span data-ttu-id="ce049-153">Surface Pro 6 商业版</span><span class="sxs-lookup"><span data-stu-id="ce049-153">Surface Pro 6 Commercial</span></span>                                     | <span data-ttu-id="ce049-154">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="ce049-154">Surface Pro 6</span></span>    | <span data-ttu-id="ce049-155">Surface_Pro_6_1796_Commercial</span><span class="sxs-lookup"><span data-stu-id="ce049-155">Surface_Pro_6_1796_Commercial</span></span>    |
| <span data-ttu-id="ce049-156">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="ce049-156">Surface Laptop</span></span>                                               | <span data-ttu-id="ce049-157">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="ce049-157">Surface Laptop</span></span>   | <span data-ttu-id="ce049-158">Surface_Laptop</span><span class="sxs-lookup"><span data-stu-id="ce049-158">Surface_Laptop</span></span>                   |
| <span data-ttu-id="ce049-159">Surface 笔记本电脑2消费者</span><span class="sxs-lookup"><span data-stu-id="ce049-159">Surface Laptop 2 Consumer</span></span>                                    | <span data-ttu-id="ce049-160">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="ce049-160">Surface Laptop 2</span></span> | <span data-ttu-id="ce049-161">Surface_Laptop_2_1769_Consumer</span><span class="sxs-lookup"><span data-stu-id="ce049-161">Surface_Laptop_2_1769_Consumer</span></span>   |
| <span data-ttu-id="ce049-162">Surface 笔记本电脑2商业版</span><span class="sxs-lookup"><span data-stu-id="ce049-162">Surface Laptop 2 Commercial</span></span>                                  | <span data-ttu-id="ce049-163">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="ce049-163">Surface Laptop 2</span></span> | <span data-ttu-id="ce049-164">Surface_Laptop_2_1769_Commercial</span><span class="sxs-lookup"><span data-stu-id="ce049-164">Surface_Laptop_2_1769_Commercial</span></span> |
| <span data-ttu-id="ce049-165">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="ce049-165">Surface Pro 7</span></span>                 | <span data-ttu-id="ce049-166">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="ce049-166">Surface Pro 7</span></span>    | <span data-ttu-id="ce049-167">Surface_Pro_7_1866</span><span class="sxs-lookup"><span data-stu-id="ce049-167">Surface_Pro_7_1866</span></span>         |
| <span data-ttu-id="ce049-168">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="ce049-168">Surface Pro X</span></span>                 | <span data-ttu-id="ce049-169">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="ce049-169">Surface Pro X</span></span>    | <span data-ttu-id="ce049-170">Surface_Pro_X_1876</span><span class="sxs-lookup"><span data-stu-id="ce049-170">Surface_Pro_X_1876</span></span>         |
| <span data-ttu-id="ce049-171">Surface 笔记本电脑 3 13 "英特尔</span><span class="sxs-lookup"><span data-stu-id="ce049-171">Surface Laptop 3 13" Intel</span></span> | <span data-ttu-id="ce049-172">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="ce049-172">Surface Laptop 3</span></span> | <span data-ttu-id="ce049-173">Surface_Laptop_3_1867：1868</span><span class="sxs-lookup"><span data-stu-id="ce049-173">Surface_Laptop_3_1867:1868</span></span> |
| <span data-ttu-id="ce049-174">Surface 笔记本电脑 3 15 "英特尔</span><span class="sxs-lookup"><span data-stu-id="ce049-174">Surface Laptop 3 15" Intel</span></span> | <span data-ttu-id="ce049-175">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="ce049-175">Surface Laptop 3</span></span> | <span data-ttu-id="ce049-176">Surface_Laptop_3_1872</span><span class="sxs-lookup"><span data-stu-id="ce049-176">Surface_Laptop_3_1872</span></span>      |
| <span data-ttu-id="ce049-177">Surface 笔记本电脑 3 15 "AMD</span><span class="sxs-lookup"><span data-stu-id="ce049-177">Surface Laptop 3 15" AMD</span></span>   | <span data-ttu-id="ce049-178">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="ce049-178">Surface Laptop 3</span></span> | <span data-ttu-id="ce049-179">Surface_Laptop_3_1873</span><span class="sxs-lookup"><span data-stu-id="ce049-179">Surface_Laptop_3_1873</span></span>      | 

## <span data-ttu-id="ce049-180">示例</span><span class="sxs-lookup"><span data-stu-id="ce049-180">Examples</span></span> 

**<span data-ttu-id="ce049-181">使用 PowerShell 检索 SKU</span><span class="sxs-lookup"><span data-stu-id="ce049-181">Retrieving the SKU by using PowerShell</span></span>**  
<span data-ttu-id="ce049-182">使用以下 PowerShell 命令提取系统 SKU 信息：</span><span class="sxs-lookup"><span data-stu-id="ce049-182">Use the following PowerShell command to pull the System SKU information:</span></span>

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**<span data-ttu-id="ce049-183">使用系统信息检索 SKU</span><span class="sxs-lookup"><span data-stu-id="ce049-183">Retrieving the SKU by using System Information</span></span>**  
<span data-ttu-id="ce049-184">您还可以在 "**系统信息**" 中查找设备的系统 SKU 和系统模型。</span><span class="sxs-lookup"><span data-stu-id="ce049-184">You can also find the System SKU and System Model for a device in **System Information**.</span></span> <span data-ttu-id="ce049-185">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ce049-185">To do this, follow these steps:</span></span>

1. <span data-ttu-id="ce049-186">选择 "**开始**"，然后在搜索框中键入 " **MSInfo32** "。</span><span class="sxs-lookup"><span data-stu-id="ce049-186">Select **Start**, and then type **MSInfo32** in the search box.</span></span>  
1. <span data-ttu-id="ce049-187">选择 "**系统信息**"。</span><span class="sxs-lookup"><span data-stu-id="ce049-187">Select **System Information**.</span></span>

**<span data-ttu-id="ce049-188">在任务序列中使用 SKU WMI 条件</span><span class="sxs-lookup"><span data-stu-id="ce049-188">Using the SKU in a task sequence WMI condition</span></span>**  
<span data-ttu-id="ce049-189">你可以使用 Microsoft 部署工具包（MDT）或 Microsoft 终结点配置管理器中的系统 SKU 信息作为任务序列 WMI 条件的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce049-189">You can use the System SKU information in the Microsoft Deployment Toolkit (MDT) or Microsoft Endpoint Configuration Manager as part of a task sequence WMI condition.</span></span>

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 

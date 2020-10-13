---
title: 通过 Microsoft 部署工具包 (Surface) 将 Windows 10 部署到 Surface 设备
description: 浏览建议的有关如何使用 Microsoft 部署工具包将 Windows 10 部署到 Surface 设备的过程。
keywords: windows 10 surface，自动化，自定义，mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 10/12/2020
ms.openlocfilehash: 858b6726f1127e3c439864f8946274ed0ea1edd3
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114560"
---
# <span data-ttu-id="88f8c-104">通过 Microsoft 部署工具包将 Windows 10 部署到 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="88f8c-104">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>

**<span data-ttu-id="88f8c-105">适用于</span><span class="sxs-lookup"><span data-stu-id="88f8c-105">Applies to</span></span>**

- <span data-ttu-id="88f8c-106">Surface Studio 及更高版本</span><span class="sxs-lookup"><span data-stu-id="88f8c-106">Surface Studio and later</span></span>
- <span data-ttu-id="88f8c-107">Surface Pro 4 及更高版本</span><span class="sxs-lookup"><span data-stu-id="88f8c-107">Surface Pro 4 and later</span></span>
- <span data-ttu-id="88f8c-108">Surface Book 及更高版本</span><span class="sxs-lookup"><span data-stu-id="88f8c-108">Surface Book and later</span></span>
- <span data-ttu-id="88f8c-109">Surface 笔记本电脑及更高版本</span><span class="sxs-lookup"><span data-stu-id="88f8c-109">Surface Laptop and later</span></span>
- <span data-ttu-id="88f8c-110">Surface 膝上型电脑 Go</span><span class="sxs-lookup"><span data-stu-id="88f8c-110">Surface Laptop Go</span></span>
- <span data-ttu-id="88f8c-111">Surface Go</span><span class="sxs-lookup"><span data-stu-id="88f8c-111">Surface Go</span></span>
- <span data-ttu-id="88f8c-112">Surface 3</span><span class="sxs-lookup"><span data-stu-id="88f8c-112">Surface 3</span></span>
- <span data-ttu-id="88f8c-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="88f8c-113">Windows 10</span></span>

> [!NOTE]
> <span data-ttu-id="88f8c-114">Surface Pro X 不支持 MDT。有关详细信息，请参阅 [部署、管理和维护 Surface Pro X](surface-pro-arm-app-management.md)。</span><span class="sxs-lookup"><span data-stu-id="88f8c-114">MDT is not supported on Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>

<span data-ttu-id="88f8c-115">有关使用 MDT 的最新信息，请参阅 [使用 Mdt 部署 Windows 10 映像](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)。</span><span class="sxs-lookup"><span data-stu-id="88f8c-115">For the latest information about using MDT, refer to [Deploy a Windows 10 image using MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).</span></span>


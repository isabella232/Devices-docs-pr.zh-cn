---
title: 通过 Microsoft 部署工具包（Surface）将 Surface 设备升级到 Windows 10
description: 了解如何向 Surface 设备执行 Windows 10 升级部署。
keywords: windows 10 surface、upgrade、自定义、mdt
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
ms.date: 04/24/2020
ms.openlocfilehash: e1a1d34c4d32c5e6f95c985e335e405c0d9e59e4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830996"
---
# <span data-ttu-id="c0495-104">通过 Microsoft 部署工具包将 Surface 设备升级到 Windows 10</span><span class="sxs-lookup"><span data-stu-id="c0495-104">Upgrade Surface devices to Windows 10 with Microsoft Deployment Toolkit</span></span>

#### <span data-ttu-id="c0495-105">适用范围</span><span class="sxs-lookup"><span data-stu-id="c0495-105">Applies to</span></span>
- <span data-ttu-id="c0495-106">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="c0495-106">Surface Pro 6</span></span>
- <span data-ttu-id="c0495-107">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="c0495-107">Surface Laptop 2</span></span>
- <span data-ttu-id="c0495-108">Surface Go</span><span class="sxs-lookup"><span data-stu-id="c0495-108">Surface Go</span></span>
- <span data-ttu-id="c0495-109">带有 LTE 的 Surface Go</span><span class="sxs-lookup"><span data-stu-id="c0495-109">Surface Go with LTE</span></span>
- <span data-ttu-id="c0495-110">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="c0495-110">Surface Book 2</span></span>
- <span data-ttu-id="c0495-111">带有 LTE Advanced 的 Surface Pro（型号 1807）</span><span class="sxs-lookup"><span data-stu-id="c0495-111">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="c0495-112">Surface Pro（型号 1796）</span><span class="sxs-lookup"><span data-stu-id="c0495-112">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="c0495-113">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="c0495-113">Surface Laptop</span></span>
- <span data-ttu-id="c0495-114">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="c0495-114">Surface Studio</span></span>
- <span data-ttu-id="c0495-115">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="c0495-115">Surface Studio 2</span></span>
- <span data-ttu-id="c0495-116">Surface Book</span><span class="sxs-lookup"><span data-stu-id="c0495-116">Surface Book</span></span>
- <span data-ttu-id="c0495-117">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="c0495-117">Surface Pro 4</span></span>
- <span data-ttu-id="c0495-118">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="c0495-118">Surface 3 LTE</span></span>
- <span data-ttu-id="c0495-119">Surface 3</span><span class="sxs-lookup"><span data-stu-id="c0495-119">Surface 3</span></span>
- <span data-ttu-id="c0495-120">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="c0495-120">Surface Pro 3</span></span>
- <span data-ttu-id="c0495-121">Surface Pro 2</span><span class="sxs-lookup"><span data-stu-id="c0495-121">Surface Pro 2</span></span>
- <span data-ttu-id="c0495-122">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="c0495-122">Surface Pro</span></span>
- <span data-ttu-id="c0495-123">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c0495-123">Windows 10</span></span>

<span data-ttu-id="c0495-124">除了重置设备的传统部署方法外，想要升级运行 Windows 8.1 或 Windows 10 的 Surface 设备的管理员可以选择部署升级。</span><span class="sxs-lookup"><span data-stu-id="c0495-124">In addition to the traditional deployment method of reimaging devices, administrators who want to upgrade Surface devices that are running Windows 8.1 or Windows 10 have the option of deploying upgrades.</span></span> <span data-ttu-id="c0495-125">通过执行升级部署，可以在设备上应用 Windows 10，而无需删除用户、应用或配置。</span><span class="sxs-lookup"><span data-stu-id="c0495-125">By performing an upgrade deployment, Windows 10 can be applied to devices without removing users, apps, or configuration.</span></span> <span data-ttu-id="c0495-126">已部署的设备的用户只需继续使用具有在升级之前使用的相同应用和设置的设备即可。</span><span class="sxs-lookup"><span data-stu-id="c0495-126">The users of the deployed devices can simply continue using the devices with the same apps and settings that they used prior to the upgrade.</span></span> 

<span data-ttu-id="c0495-127">有关使用 MDT 升级 surface 设备的最新信息，请参阅[使用 Mdt 执行到 Windows 10 的就地升级](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit)。</span><span class="sxs-lookup"><span data-stu-id="c0495-127">For the latest information about upgrading surface devices using MDT, refer to [Perform an in-place upgrade to Windows 10 with MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span></span>


---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator 为组织提供一种简单快速的部署机制，以用于重置 Surface 设备的映像。
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: 部署, 安装, 工具
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 32d8fded8c325766f7ab6bbc750ba7fe13e01d70
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830710"
---
# <span data-ttu-id="4ecb8-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="4ecb8-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="4ecb8-105">Microsoft Surface 部署加速器（SDA）通过使用免费的 Microsoft 部署工具，自动创建和配置 Microsoft 推荐的部署体验。</span><span class="sxs-lookup"><span data-stu-id="4ecb8-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="4ecb8-106">在2020年4月重新设计，可在企业环境中简化和自动化图面图像的部署，SDA 工具允许你构建一个 "工厂式" Windows 映像，你可以自定义此类 Windows 映像，以便你的组织要求进行自定义。</span><span class="sxs-lookup"><span data-stu-id="4ecb8-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="4ecb8-107">开放源代码、脚本驱动的 SDA 工具利用 windows 10 的 Windows 评估和部署工具包（ADK），从而有助于在测试或生产环境中创建 Windows 映像（WIM）。</span><span class="sxs-lookup"><span data-stu-id="4ecb8-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="4ecb8-108">如果尚未安装最新的 ADK，将在运行 SDA 工具时下载并安装它。</span><span class="sxs-lookup"><span data-stu-id="4ecb8-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="4ecb8-109">生成的图像与裸机恢复（BMR）映像的配置非常相似，没有任何预安装的应用程序（如 Microsoft Office 或 Surface UWP 应用程序）。</span><span class="sxs-lookup"><span data-stu-id="4ecb8-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

**<span data-ttu-id="4ecb8-110">要运行 SDA，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4ecb8-110">To run SDA:</span></span>**

1. <span data-ttu-id="4ecb8-111">转到 GitHub 上的[SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 。</span><span class="sxs-lookup"><span data-stu-id="4ecb8-111">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="4ecb8-112">选择 "**复制" 或 "下载**并查看自述文件"。</span><span class="sxs-lookup"><span data-stu-id="4ecb8-112">Select **Clone or Download** and review the Readme file.</span></span>
3. <span data-ttu-id="4ecb8-113">根据你的环境的相应变量编辑脚本（如自述中所述），并在测试环境中运行它之前进行检查。</span><span class="sxs-lookup"><span data-stu-id="4ecb8-113">Edit the script with the appropriate variables for your environment, as documented in the Readme, and review before running it in your test environment.</span></span> 

   ![运行 Surface 部署加速器工具](images/surface-deployment-accelerator.png)

## <span data-ttu-id="4ecb8-115">相关链接</span><span class="sxs-lookup"><span data-stu-id="4ecb8-115">Related links</span></span>

 - [<span data-ttu-id="4ecb8-116">在 GitHub 上发布的 "打开源映像部署工具"</span><span class="sxs-lookup"><span data-stu-id="4ecb8-116">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [<span data-ttu-id="4ecb8-117">下载并安装 Windows ADK</span><span class="sxs-lookup"><span data-stu-id="4ecb8-117">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

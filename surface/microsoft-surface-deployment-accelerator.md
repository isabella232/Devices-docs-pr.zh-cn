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
# Microsoft Surface Deployment Accelerator

Microsoft Surface 部署加速器（SDA）通过使用免费的 Microsoft 部署工具，自动创建和配置 Microsoft 推荐的部署体验。

在2020年4月重新设计，可在企业环境中简化和自动化图面图像的部署，SDA 工具允许你构建一个 "工厂式" Windows 映像，你可以自定义此类 Windows 映像，以便你的组织要求进行自定义。

开放源代码、脚本驱动的 SDA 工具利用 windows 10 的 Windows 评估和部署工具包（ADK），从而有助于在测试或生产环境中创建 Windows 映像（WIM）。 如果尚未安装最新的 ADK，将在运行 SDA 工具时下载并安装它。

生成的图像与裸机恢复（BMR）映像的配置非常相似，没有任何预安装的应用程序（如 Microsoft Office 或 Surface UWP 应用程序）。

**要运行 SDA，请执行以下操作：**

1. 转到 GitHub 上的[SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 。 
2. 选择 "**复制" 或 "下载**并查看自述文件"。
3. 根据你的环境的相应变量编辑脚本（如自述中所述），并在测试环境中运行它之前进行检查。 

   ![运行 Surface 部署加速器工具](images/surface-deployment-accelerator.png)

## 相关链接

 - [在 GitHub 上发布的 "打开源映像部署工具"](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [下载并安装 Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

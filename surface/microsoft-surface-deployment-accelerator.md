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
ms.openlocfilehash: 3ede7311289dc4bc720735c0142ff3a46fbb69e7
ms.sourcegitcommit: 582c5a79881c58c4f1aa66cfcab46db966ca9f24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016553"
---
# Microsoft Surface Deployment Accelerator

Microsoft Surface 部署加速器 (SDA) 通过使用免费的 Microsoft 部署工具自动创建和配置 Microsoft 推荐的部署体验。

在2020年4月重新设计，可在企业环境中简化和自动化图面图像的部署，SDA 工具允许你构建一个 "工厂式" Windows 映像，你可以自定义此类 Windows 映像，以便你的组织要求进行自定义。

开放源代码、脚本驱动的 SDA 工具利用 Windows for Windows 10 (ADK) 的 Windows 评估和部署工具包，从而有助于在测试或生产环境中创建 Windows 映像 (WIM) 。 如果尚未安装最新的 ADK，将在运行 SDA 工具时下载并安装它。

生成的图像与裸机恢复 (BMR) 图像的配置紧密匹配，没有任何预安装的应用程序（如 Microsoft Office 或 Surface UWP 应用程序）。

## 要求

1. USB 拇指驱动器的大小至少为 16 GB。 将格式化 USB 驱动器。
2. 带有 Windows 10 专业版或 Windows 10 企业版的 .iso 文件。 媒体创建工具可用于下载 Windows 10 并创建一个 .iso 文件。 有关详细信息，请参阅 [下载 Windows 10](https://www.microsoft.com/software-download/windows10)。
3. 运行 Windows 10 版本2004或更高版本且具有 Internet 访问权限的设备。

有关要求的详细列表，请参阅自述文档的 " [先决条件](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) " 部分。

## 如何运行 SDA

**要运行 SDA，请执行以下操作：**

1. 转到 GitHub 上的 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 。 
2. 查看 [自述](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) 文档。
3. 在 " [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) " 页面上，单击 " **代码** " 按钮，然后选择 " **下载 ZIP** " 将文件本地保存到计算机上。
4. 右键单击 .zip 文件，然后单击 " **属性**"。
5. 在 " **常规** " 选项卡上，选中 " **取消阻止** " 复选框，然后单击 **"确定"**。
6. 将 .zip 文件解压缩到硬盘上的某个位置 (ex： C:\SDA) 。
7. 打开提升了权限的 Windows PowerShell 提示，并将当前会话的 Set-executionpolicy 设置为 "无限制"。

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. 运行用于为你的环境指定参数的 SDA 脚本。 该脚本可用于创建在各种 Surface 设备上安装 Windows 10 的映像。 有关受支持的设备的完整列表，请参阅 SDA 自述文章中的 [设备参数说明](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) 。 

    例如，以下命令将创建可用于 [在 Surface Hub 2 上安装 Windows 10](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os)的可启动 USB 驱动器：

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    示例脚本输出如下所示。

   ![运行 Surface 部署加速器工具](images/sda1.png)

    脚本将需要大约45分钟才能运行，但可能需要较长时间，具体取决于可用的 CPU 和磁盘资源。 

    创建 Windows 映像后，脚本将要求您插入并确认您的 USB 驱动器的驱动器号。 然后，将格式化 USB 驱动器，将其配置为可启动，并复制文件以允许安装适用于 Surface 设备的自定义 Windows 10 映像。

9. 将 USB 驱动器插入要在其中安装 Windows 10 的设备，然后重新启动以开始安装 Windows 10。 必须在 BIOS 中启用 USB 引导，这可能需要暂时禁用安全启动。

> [!IMPORTANT]
> 从 USB 驱动器启动将立即开始安装 Windows 10。 在插入 USB 并重新启动之前，请确保你的设备已准备就绪。 

## 相关链接

 - [在 GitHub 上发布的 "打开源映像部署工具"](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [下载并安装 Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

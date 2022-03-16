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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 0ececf7a21b4870c4fb6db2403d9a5e34a67fdba
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449465"
---
# <a name="microsoft-surface-deployment-accelerator"></a>Microsoft Surface Deployment Accelerator

Microsoft Surface Deployment Accelerator (SDA) 使用免费的 Microsoft 部署工具自动创建和配置 Microsoft 推荐的部署体验。

SDA 工具在 2020 年 4 月重新设计，以简化和自动化在企业环境中部署 Surface 映像，可让你生成"工厂式"Windows映像，你可以根据组织要求自定义该映像。

开源脚本驱动的 SDA 工具利用适用于 Windows 10 的 Windows 评估和部署工具包 (ADK) ，便于在测试或生产环境中创建 Windows 映像 (WIM) 。 如果尚未安装最新的 ADK，将在运行 SDA 工具时下载并安装它。

生成的映像与裸机恢复 (BMR) 映像的配置非常匹配，无需任何预安装的应用程序Microsoft Office或 Surface UWP 应用程序。

## <a name="requirements"></a>要求

1. U 盘大小至少为 16 GB。 将格式化 USB 驱动器。
2. Windows 10/11 或 Pro/11 Windows 10 .iso Enterprise。 媒体创建工具可用于下载Windows 10或Windows 11 .iso 文件。 有关详细信息，请参阅下载[Windows 10](https://www.microsoft.com/software-download/windows10)。
3. 运行具有 internet Windows 10版本 2004 或更高版本的设备。

有关 [详细要求列表](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) ，请参阅自述文档的先决条件部分。

## <a name="how-to-run-the-sda"></a>如何运行 SDA

**若要运行 SDA：**

1. 转到 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub。 
2. 查看 [自述文件](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) 文档。
3. 在 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 页上，单击"代码****"按钮，然后选择"下载 **ZIP**"以本地保存您的计算机上的文件。
4. 右键单击.zip文件，然后单击"属性 **"**。
5. 在" **常规"** 选项卡上，选中 **"取消阻止"复选框** ，然后单击"确定 **"**。
6. 将.zip文件解压缩到硬盘驱动器上的 (：C：\SDA) 。
7. 打开提升的 Windows PowerShell 提示符，将当前会话的 ExecutionPolicy 设置为 Unrestricted。

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. 运行指定环境参数的 SDA 脚本。 该脚本可用于创建映像，以Windows 10或Windows 11 Surface 设备上安装脚本。 有关受支持的设备的完整列表，请参阅 SDA 自述文章中的 [Device](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) 参数说明。 

    例如，以下命令将创建一个可启动 USB 驱动器，可用于在 [Windows 10 2 Surface Hub驱动器](/surface-hub/surface-hub-2s-migrate-os)：

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    示例脚本输出如下所示。

   ![运行 Surface Deployment Accelerator 工具。](images/sda1.png)

    脚本将需要大约 45 分钟才能运行，但可能需要更长时间，具体取决于可用的 CPU 和磁盘资源。 

    创建 U 盘Windows，脚本会要求你插入并确认 USB 驱动器的驱动器号。 然后，将格式化 U 盘，配置为可启动，并复制文件以启用 Surface 设备的自定义 Windows 10 或 Windows 11 映像安装。

9. 将 USB 驱动器插入你想要安装驱动器Windows 10或Windows 11重启以开始安装。 必须在 BIOS 中启用 USB 启动，这可能需要你暂时禁用安全启动。

> [!IMPORTANT]
> 从 USB 驱动器启动将立即开始安装操作系统。 在插入 USB 并重新启动之前，请确保你的设备已准备就绪。 

## <a name="related-links"></a>相关链接

 - [GitHub 上发布的开放源映像部署GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [下载并安装 Windows ADK](/windows-hardware/get-started/adk-install)

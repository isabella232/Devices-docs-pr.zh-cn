---
title: 将 Surface 应用部署到 Microsoft Store for Business 或 Microsoft Store for 教育版（Surface）
description: 了解如何在 Microsoft Store for Business 或 Microsoft Store for 教育中添加和下载 Surface 应用，以及安装具有 PowerShell 和 MDT 的 Surface 应用。
keywords: surface 应用、应用、部署、自定义
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830893"
---
# 将 Surface 应用部署到 Microsoft Store for Business 和教育版

**适用范围**

- Surface Pro 7
- Surface 笔记本电脑3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- 带有 LTE 的 Surface Go
- Surface Book 2
- 带有 LTE Advanced 的 Surface Pro（型号 1807）
- Surface Pro（型号 1796）
- Surface Laptop
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3


Surface 应用是一种轻型 Microsoft Store 应用，可提供对许多特定于图面的设置和选项的控制，包括： 

* 启用或禁用 Surface 设备上的 Windows 按钮 

* 调整 Surface 触控笔的灵敏度 

* 自定义 Surface 触控笔按钮操作 

* 启用或禁用 Surface 音频增强功能 

* 快速访问你的设备的支持文档和信息

使用 Windows 更新的客户通常会接收 Surface app 作为自动更新的一部分。 但是，如果你的组织准备将映像部署到 Surface 设备，你可能希望在你的映像和部署过程中包括 Surface 应用（以前称为 Surface Hub），而不是需要每个人设备的用户从 Microsoft Store 或 Microsoft Store for Business 下载和安装应用。 

> [!NOTE]
> 本文不适用于 Surface Pro X。有关详细信息，请参阅[部署、管理和维护 Surface Pro X](surface-pro-arm-app-management.md)

## Surface 应用概述

Surface app 可从[Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)免费下载。 用户可以从 Microsoft Store 下载并安装它，但如果您的组织使用的是 Microsoft store for Business，则需要将其添加到你的应用商店的库存，并且可能将应用包括在 Windows 部署过程中。 本文将讨论这些过程。 有关 Microsoft Store for Business 的详细信息，请参阅 Windows 技术中心中的[Microsoft store For business](https://docs.microsoft.com/microsoft-store/) 。 

## 将 Surface 应用添加到 Microsoft Store for Business 帐户 

在用户可以从公司的 Microsoft Store for Business 帐户安装或部署应用之前，所需的应用首先必须提供，并授权给企业用户。 

1. 如果尚未执行此操作，请创建[Microsoft Store For Business 帐户](https://www.microsoft.com/business-store)。 

2. 登录到门户。 

3. 启用脱机授权：单击 "**管理->存储设置**"，然后选择 "**向在应用商店中购物的用户显示脱机许可的应用**" 复选框，如图1所示。 有关 Microsoft Store for Business 应用许可模型的详细信息，请参阅[Microsoft store For business 和教育版中的应用](https://docs.microsoft.com/microsoft-store/)。<br/> <br/>
   !["显示脱机许可证应用" 复选框](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *图 1. 允许应用脱机使用*

4. 通过执行以下过程，将 Surface 应用添加到 Microsoft Store for Business 帐户：
    * 单击 "**商店**" 菜单。
    * 在 "搜索" 框中，键入 " **Surface app**"，然后单击 "搜索" 图标。
    * 在搜索结果中显示 Surface 应用后，单击应用的图标。
    * 将显示一个选项（选择 "**联机**" 或 "**脱机**"），如图2所示。<br/><br/>
    
    ![选择脱机授权模式并将应用添加到你的库存](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *图 2. 选择脱机授权模式并将应用添加到你的库存*
    
    * 单击 "**脱机**" 以选择脱机授权模式。
    * 单击 **"获取应用**" 以将应用添加到 Microsoft Store for Business 库存。 如图3所示，你将看到一个对话框，提示你确认可以使用管理工具部署脱机应用，或者从其私人存储中的公司的库存页面下载。
    
    ![脱机许可的应用确认窗口](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *图 3. 脱机授权应用确认*
    * 单击“确定”****。

## 从 Microsoft Store for Business 帐户下载 Surface 应用
在脱机模式下将应用添加到 Microsoft Store for Business 帐户之后，你可以将该应用作为 .Appxbundle 下载并添加到部署共享。
1. 登录到 Microsoft Store for Business 帐户 https://businessstore.microsoft.com 。
2. 单击 "**管理->应用 & 软件**"。 将显示公司的所有应用的列表，包括您在 "添加 Surface 应用" 中添加的 Surface 应用，以及本文的 " [Microsoft Store For Business 帐户](#add-surface-app-to-a-microsoft-store-for-business-account)" 部分。
3. 在 "**操作**" 下，单击省略号（**...**），然后单击 "下载" 以供 Surface 应用**脱机使用**。
4. 从所选应用的可用选项中选择所需的**平台**和**体系结构**选项，如图4所示。

    ![.Appxbundle 程序包的示例](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *图 4. 下载应用的 .Appxbundle 程序包*
5. 单击 "**下载**"。 将下载 .Appxbundle 程序包。 请确保记下下载文件的路径，因为本文后面的内容将需要。
6. 单击 "已**编码的许可证**" 或 "未**编码的许可证**" 选项。 将编码的许可证选项与 Microsoft 终结点配置管理器等管理工具一起使用，或者在使用 Windows 配置设计器创建预配包时使用。 使用部署映像服务和管理（DISM）或基于映像的部署解决方案（包括 Microsoft 部署工具包（MDT））时，选择 "未编码的许可证" 选项。
7. 单击 "**生成**" 以生成并下载应用的许可证。 请务必记下许可证文件的路径，因为本文后面的内容将需要。

>[!NOTE]
>下载应用以供脱机使用（如 Surface app）时，你可能会注意到页面底部的 "**所需框架**" 部分中有一个分区。 目标计算机必须安装要运行的应用程序的框架，因此你可能需要为你的体系结构（x86 或 x64）的每个所需框架重复下载过程，并将其包含在本文后面部分中讨论的 Windows 部署中。

图5显示了 Surface 应用所需的框架。

![Surface 应用所需的框架](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*图 5. Surface 应用所需的框架*

>[!NOTE]
>当应用更新时，Surface 应用和所需框架的版本号将会更改。 在 Microsoft Store for Business 中检查最新版本的 Surface 应用和每个框架。 始终使用由 Microsoft Store for Business 提供的 Surface 应用和推荐的框架版本。 使用过时的框架或不正确的版本可能会导致错误或应用程序崩溃。

若要下载 Surface 应用所需的框架，请按照下列步骤操作：
1. 单击 " **VCLibs" 0_x64__8wekyb3d8bbwe 14.0.23816**下的 "**下载**" 按钮。 这将下载 14.0.23816 0_x64__8wekyb3d8bbwe。Appx 文件复制到你的指定文件夹。
2. 单击 " **Microsoft 0_x64__8wekyb3d8bbwe 1.1.23406**" 下的 "**下载**" 按钮。 这会将 0_x64__8wekyb3d8bbwe 1.1.23406 文件下载到你的指定文件夹中的文件。

>[!NOTE]
>对于 Surface 设备，仅需要每个框架的64位（x64）版本。 Surface 设备是本机64位 UEFI 设备，与需要32位框架的 Windows 32 位（x86）版本不兼容。 

## 通过 PowerShell 在计算机上安装 Surface app
下面的过程将 Surface 应用设置到你的计算机上，并使其可用于以后在计算机上创建的任何用户帐户。
1. 有关本文中的 "[如何从 Microsoft Store For Business 帐户下载 surface 应用](#download-surface-app-from-a-microsoft-store-for-business-account)" 部分中所述的过程，请下载 Surface app 和许可证文件。 
2. 开始提升的 PowerShell 会话。

    >[!NOTE]
    >如果不以管理员身份运行 PowerShell，则会话将不具有安装应用所需的权限。
    
3. 在提升的 PowerShell 会话中，复制并粘贴以下命令：
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    其中 `<DownloadPath>` 是你从 Microsoft Store For Business 帐户下载了 .appxbundle 和许可证文件的文件夹。

    例如，如果您将文件下载到 C：\Temp，则您运行的命令是：
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).

---
title: '将 Surface 应用部署到 Microsoft Store for Business 或 Microsoft Store for 教育版 (Surface) '
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
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114710"
---
# 将 Surface 应用部署到 Microsoft Store for Business 和教育版

**适用于**

- Surface 膝上型电脑 Go
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

使用 Windows 更新的客户通常会接收 Surface app 作为自动更新的一部分。 但是，如果你的组织准备将映像部署到 Surface 设备，你可能需要在你的映像和部署过程中包含 Surface app (以前称为 Surface Hub) ，而不是需要每个人设备的用户从 Microsoft Store 或 Microsoft Store for Business 下载和安装应用。 

> [!NOTE]
> 本文不适用于 Surface Pro X。有关详细信息，请参阅 [部署、管理和维护 Surface Pro X](surface-pro-arm-app-management.md)

## Surface 应用概述

Surface app 可从 [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)免费下载。 用户可以从 Microsoft Store 下载并安装它，但如果您的组织使用的是 Microsoft store for Business，则需要将其添加到你的应用商店的库存，并且可能将应用包括在 Windows 部署过程中。 本文将讨论这些过程。 有关 Microsoft Store for Business 的详细信息，请参阅 Windows 技术中心中的 [Microsoft store For business](https://docs.microsoft.com/microsoft-store/) 。 

## 将 Surface 应用添加到 Microsoft Store for Business 帐户 

在用户可以从公司的 Microsoft Store for Business 帐户安装或部署应用之前，所需的应用 (s) 必须首先向企业用户提供和授权。 

1. 如果尚未执行此操作，请创建 [Microsoft Store For Business 帐户](https://www.microsoft.com/business-store)。 

2. 登录到门户。 

3. 启用脱机授权：单击 " **管理->存储设置**"，然后选择 " **向在应用商店中购物的用户显示脱机许可的应用** " 复选框，如图1所示。 有关 Microsoft Store for Business 应用许可模型的详细信息，请参阅 [Microsoft store For business 和教育版中的应用](https://docs.microsoft.com/microsoft-store/)。

   > [!div class="mx-imgBorder"]
   > !["显示脱机许可证应用" 复选框](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *图 1. 允许应用脱机使用*

4. 通过执行以下过程，将 Surface 应用添加到 Microsoft Store for Business 帐户：

    * 单击 " **商店** " 菜单。
    
    * 在 "搜索" 框中，键入 " **Surface app**"，然后单击 "搜索" 图标。
    
    * 在搜索结果中显示 Surface 应用后，单击应用的图标。
    
    * 将显示一个选项 (选择 " **联机** " 或 " **脱机** ") ，如图2所示。
    
      > [!div class="mx-imgBorder"]
      > ![选择脱机授权模式并将应用添加到你的库存](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *图 2. 选择脱机授权模式并将应用添加到你的库存*
    
    * 单击 " **脱机** " 以选择脱机授权模式。
    
    * 单击 **"获取应用** " 以将应用添加到 Microsoft Store for Business 库存。 如图3所示，你将看到一个对话框，提示你确认可以使用管理工具部署脱机应用，或者从其私人存储中的公司的库存页面下载。
    
      > [!div class="mx-imgBorder"]
      > ![脱机许可的应用确认窗口 ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *图3。脱机授权应用确认*
      
    * 单击“确定”****。

## 从 Microsoft Store for Business 帐户下载 Surface 应用
在脱机模式下将应用添加到 Microsoft Store for Business 帐户之后，你可以将该应用作为 .Appxbundle 下载并添加到部署共享。

1. 登录到 Microsoft Store for Business 帐户 https://businessstore.microsoft.com 。

2. 单击 " **管理->应用 & 软件**"。 将显示公司的所有应用的列表，包括您在 "添加 Surface 应用" 中添加的 Surface 应用，以及本文的 " [Microsoft Store For Business 帐户](#add-surface-app-to-a-microsoft-store-for-business-account) " 部分。

3. 在 " **操作**" 下，单击省略号 (**...** ") ，然后单击" 下载 "以供 Surface 应用 **脱机使用** 。

4. 从所选应用的可用选项中选择所需的 **平台** 和 **体系结构** 选项，如图4所示。

    > [!div class="mx-imgBorder"]
    > ![.Appxbundle 程序包的示例](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *图 4. 下载应用的 .Appxbundle 程序包*
    
5. 单击 " **下载**"。 将下载 .Appxbundle 程序包。 请确保记下下载文件的路径，因为本文后面的内容将需要。

6. 单击 "已 **编码的许可证** " 或 "未 **编码的许可证** " 选项。 将编码的许可证选项与 Microsoft 终结点配置管理器等管理工具一起使用，或者在使用 Windows 配置设计器创建预配包时使用。 当你使用部署映像服务和管理 (DISM) 或基于映像的部署解决方案（包括 Microsoft 部署工具包 (MDT) ）时，请选择 "未编码的许可证" 选项。

7. 单击 " **生成** " 以生成并下载应用的许可证。 请务必记下许可证文件的路径，因为本文后面的内容将需要。

>[!NOTE]
>下载应用以供脱机使用（如 Surface app）时，你可能会注意到页面底部的 " **所需框架**" 部分中有一个分区。 目标计算机必须安装要运行的应用程序框架，因此你可能需要为你的体系结构的每个所需框架重复下载过程 (x86 或 x64) ，并将其包含在本文后面部分中讨论的 Windows 部署中。

图5显示了 Surface 应用所需的框架。

> [!div class="mx-imgBorder"]
> ![Surface 应用所需的框架](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*图 5. Surface 应用所需的框架*

>[!NOTE]
>当应用更新时，Surface 应用和所需框架的版本号将会更改。 在 Microsoft Store for Business 中检查最新版本的 Surface 应用和每个框架。 始终使用由 Microsoft Store for Business 提供的 Surface 应用和推荐的框架版本。 使用过时的框架或不正确的版本可能会导致错误或应用程序崩溃。

若要下载 Surface 应用所需的框架，请按照下列步骤操作：

1. 单击 "VCLibs" 下的 " **下载** " 按钮。 **140.00 _14. 0 23816 _x64__8wekyb3d8bbwe**。 此操作将下载 VCLibs 140.00 _14. 0 _x64__8wekyb3d8bbwe。Appx 文件复制到你的指定文件夹。

2. 单击 "Microsoft _x64__8wekyb3d8bbwe" 下的 " **下载** " 按钮。 **23406**。 此操作会将 23406 _x64__8wekyb3d8bbwe 文件下载到指定的文件夹中，然后将其下载到你的指定文件夹。

>[!NOTE]
>对于 Surface 设备，仅需要每个框架的64位 (x64) 版本。 Surface 设备是本机64位 UEFI 设备，与32位 (x86) 版本的 Windows 不兼容，这些版本需要32位框架。 

## 通过 PowerShell 在计算机上安装 Surface app
下面的过程将 Surface 应用设置到你的计算机上，并使其可用于以后在计算机上创建的任何用户帐户。

1. 有关本文中的 " [如何从 Microsoft Store For Business 帐户下载 surface 应用](#download-surface-app-from-a-microsoft-store-for-business-account) " 部分中所述的过程，请下载 Surface app 和许可证文件。 

2. 开始提升的 PowerShell 会话。

    >[!NOTE]
    >如果不以管理员身份运行 PowerShell，则会话将不具有安装应用所需的权限。
    
3. 在提升的 PowerShell 会话中，复制并粘贴以下命令：

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    其中 `<DownloadPath>` 是你从 Microsoft Store For Business 帐户下载了 .appxbundle 和许可证文件的文件夹。

    例如，如果您将文件下载到 C：\Temp，则您运行的命令是：
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. 现在，Surface 应用将在你的当前 Windows 计算机上可用。 

   如果 Surface 应用在预配的计算机上运行正常，则还必须预配本文前面所述的框架。 若要设置这些框架，请在用于设置 Surface 应用的提升的 PowerShell 会话中使用以下过程。

5. 在提升的 PowerShell 会话中，复制并粘贴以下命令：

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. 在提升的 PowerShell 会话中，复制并粘贴以下命令：

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## 通过 MDT 安装 Surface 应用
以下过程使用 MDT 在部署时自动安装 Surface 应用。 该应用程序在部署期间自动由 MDT 预配，因此可将该过程用于现有映像。 建议使用此过程将 Surface 应用部署为 Surface 设备的 Windows 部署的一部分，因为它不会减少 Windows 映像的跨平台兼容性。

1. 使用 [本文前面](#download-surface-app-from-a-microsoft-store-for-business-account)所述的过程，下载 Surface app 和许可证文件。 

2. 使用 MDT 部署工作台中的 "新建应用程序" 向导，将下载的文件作为 **具有源文件的新应用程序**导入。

3. 在 "新建应用程序" 向导的 " **命令详细信息** " 页面上，指定默认 **工作目录** 和 **命令** 指定 .appxbundle 的文件名，如下所示：

   * 命令
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * 工作目录：%DEPLOYROOT%\Applications\SurfaceApp

要使 Surface 应用在目标计算机上运行，还需要本文前面所述的框架。 使用以下过程将 Surface 应用所需的框架导入到 MDT，并将其配置为依赖关系。

1. 使用本文前面所述的过程下载框架文件。 将每个框架存储在单独的文件夹中。

2. 使用 MDT 部署工作台中的 "新建应用程序" 向导，将下载的文件作为 **具有源文件的新应用程序**导入。

3. 在 " **命令详细信息** " 页上，在 " **命令** " 字段中键入您下载的每个应用程序的文件名和默认工作目录。

若要将框架配置为 Surface 应用的依赖关系，请使用此过程：

1. 在 MDT 部署工作台中打开 Surface 应用的属性。

2. 单击 " **相关性** " 选项卡，然后单击 " **添加**"。

3. 使用在 "新建应用程序" 向导中提供的名称，选中每个框架对应的复选框。

导入后，Surface app 将在 Windows 部署向导的 **应用程序** 步骤中供选择。 也可以通过遵循此过程在部署任务序列中指定应用程序来自动安装该应用程序：

1. 在 MDT 部署工作台中打开你的部署任务序列。

2. 在部署的“状态还原”**** 部分中添加一个新的“安装应用程序”****。

3. 选择 " **安装单个应用程序** "，然后将 **Surface App** 指定为 **要安装的应用程序**。

有关将应用包括在 Windows 部署中的详细信息，请参阅 [通过 Microsoft 部署工具包部署 Windows 10](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)。

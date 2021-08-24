---
title: '使用 Surface 适用于企业的 Microsoft Store 或 适用于教育的 Microsoft Store (Surface) '
description: 了解如何使用 适用于企业的 Microsoft Store 或 适用于教育的 Microsoft Store 添加和下载 Surface 应用，以及如何使用 PowerShell 和 MDT 安装 Surface 应用。
keywords: surface 应用， 应用， 部署， 自定义
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
ms.date: 4/16/2021
ms.openlocfilehash: 463f5670c5e2b7eac9ac7a41b5b2b04da3ebb83e
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911177"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a>使用应用和教育适用于企业的 Microsoft Store Surface 应用

**适用范围**

- Surface Laptop 4
- Surface Pro 7+
- Surface Laptop转到
- Surface Pro 7
- Surface Laptop 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- 带 LTE 的 Surface Go
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


Surface 应用是轻型 Microsoft Store应用，可控制许多特定于 Surface 的设置和选项，并快速访问设备信息，包括序列号、Surface 型号名称、UEFI 版本和相关驱动程序。  

使用 Windows 更新的客户通常会收到 Surface 应用作为自动更新的一部分。 但是，如果你的组织准备映像以部署到 Surface 设备，你可能希望将 Surface 应用 (以前称为 Surface Hub) 包括在映像和部署过程中，而不是要求每个单台设备的用户从 Microsoft Store 或 适用于企业的 Microsoft Store 下载和安装该应用。 

> [!NOTE]
> 本文不适用于 Surface Pro X。有关详细信息，请参阅[部署、管理和维护Surface Pro X](surface-pro-arm-app-management.md)

## <a name="surface-app-overview"></a>Surface 应用概述

Surface 应用可从应用商店免费下载[Microsoft Store。](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P) 用户可以从 Microsoft Store 下载并安装它，但如果你的组织改为使用 适用于企业的 Microsoft Store，你将需要将其添加到应用商店的清单中，并且可能需要在 Windows 部署过程中包括该应用。 本文将讨论这些过程。 有关此适用于企业的 Microsoft Store，[请参阅适用于企业的 Microsoft Store](/microsoft-store/)。 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a>将 Surface 应用添加到适用于企业的 Microsoft Store帐户 

在用户可以通过公司的 适用于企业的 Microsoft Store 帐户安装或部署应用之前，必须先向企业用户提供所需的 () 并授予其许可。 

1. 如果尚未创建，请创建一个适用于企业的 Microsoft Store[帐户。](https://www.microsoft.com/business-store) 

2. 登录到门户。 

3. 启用离线许可 **：单击**  >  **"设置"，** 然后选中"向在**** 应用商店中购物的用户显示离线许可应用"复选框，如图 1 所示。 有关应用许可模型适用于企业的 Microsoft Store，请参阅应用[适用于企业的 Microsoft Store和教育。](/microsoft-store/)

   > [!div class="mx-imgBorder"]
   > ![显示离线许可证应用复选框。](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *图 1. 启用应用以便脱机使用*

4. 将 Surface 应用添加到你的适用于企业的 Microsoft Store帐户：

    * 在应用商店中搜索 **Surface 应用** 
    
    * 在搜索结果中显示 Surface 应用后，单击该应用的图标。
    
    * 可以选择"联机 (脱机) ，如图 2**** 所示****。
    
      > [!div class="mx-imgBorder"]
      > ![选择离线许可模式，将应用添加到清单。](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *图 2. 选择离线许可模式，将应用添加到清单*
    
    * 单击 **"** 脱机"以选择脱机许可模式。
    
    * 单击 **"获取应用**"将应用添加到你的适用于企业的 Microsoft Store清单。 如图 3 所示，你将看到一个对话框，提示你确认离线应用可以使用管理工具部署，也可以从公司的专用应用商店的清单页面下载。
    
      > [!div class="mx-imgBorder"]
      > ![离线授权的应用确认窗口。 ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
      *图 3.离线授权的应用确认*
      
    * 单击“确定”****。

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a>从应用帐户适用于企业的 Microsoft Store Surface 应用
在脱机模式下将应用添加到 适用于企业的 Microsoft Store 帐户后，你可以下载该应用，并作为 AppxBundle 添加到部署共享。

1. 登录到位于 的 适用于企业的 Microsoft Store 帐户 https://businessstore.microsoft.com 。

2. 单击 **"管理>应用&软件"。** 将显示你公司的所有应用的列表，包括你在本文的将 Surface 应用添加到 适用于企业的 Microsoft Store 帐户部分添加的[Surface](#add-surface-app-to-a-microsoft-store-for-business-account)应用。

3. 在 **操作**下，单击省略号 (**...**) ，然后单击下载 **以脱机使用** Surface 应用。

4. 从所选 **应用的** 可用选项 **中选择** 所需的平台和体系结构选项，如图 4 所示。

    > [!div class="mx-imgBorder"]
    > ![AppxBundle 程序包的示例。](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *图 4. 下载应用的 AppxBundle 程序包*
    
5. 单击"**下载"。** 将下载 AppxBundle 程序包。 请务必记下已下载文件的路径，因为本文稍后将对此进行介绍。

6. 单击" **编码的许可证"** 或 **"未编码的许可证"** 选项。 将"编码的许可证"选项与管理工具（如 Microsoft Endpoint Configuration Manager）一Windows配置设计器创建预配包时。 在使用部署映像服务和管理 (DISM) 或基于映像的部署解决方案（包括 Microsoft Deployment Toolkit (MDT) ）时，选择"未编码的许可证"选项。

7. 单击 **"** 生成"生成并下载应用的许可证。 请务必记下许可证文件的路径，因为本文稍后将对此进行介绍。

>[!NOTE]
>当你下载离线使用的应用（如 Surface 应用）时，你可能会注意到页面底部标记为"所需框架" **的一部分**。 目标计算机必须安装框架，应用才能运行，因此可能需要为体系结构 (（x86 或 x64) ）的每个必需框架重复下载过程，并且将它们包括在本文稍后讨论的 Windows 部署中。

图 5 显示了 Surface 应用所需的框架。

> [!div class="mx-imgBorder"]
> ![Surface 应用所需的框架。](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*图 5. Surface 应用所需的框架*

>[!NOTE]
>Surface 应用的版本号和所需框架将随着应用更新而更改。 检查 Surface 应用的最新版本以及 适用于企业的 Microsoft Store。 始终使用 Surface 应用和推荐框架版本，适用于企业的 Microsoft Store。 使用过时的框架或不正确的版本可能会导致错误或应用程序崩溃。

若要下载 Surface 应用所需的框架，请按照以下步骤操作：

1. 单击******Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe 下的"下载"按钮**。 这将下载 Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe。指定文件夹的 Appx 文件。

2. 单击******Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe 下的"下载"按钮**。 这会将 Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx 文件下载到指定的文件夹中。

>[!NOTE]
>Surface 设备只需要每个 (x64) 64 位版本。 Surface 设备是本机 64 位 UEFI 设备，与需要 32 位框架的 32 位 (x86) Windows 版本不兼容。 

## <a name="install-surface-app-on-your-computer-with-powershell"></a>使用 PowerShell 在计算机上安装 Surface 应用
以下过程将 Surface 应用设置在计算机上，然后使其可用于以后在计算机上创建的任何用户帐户。

1. 使用本文中如何从 适用于企业的 Microsoft Store帐户下载[Surface](#download-surface-app-from-a-microsoft-store-for-business-account)应用部分中介绍的过程，下载 Surface 应用 AppxBundle 和许可证文件。 

2. 开始提升的 PowerShell 会话。

    >[!NOTE]
    >如果不以管理员角色运行 PowerShell，会话将没有安装应用所需的权限。
    
3. 在提升的 PowerShell 会话中，复制并粘贴以下命令：

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    其中 `<DownloadPath>` ，是从应用程序帐户下载 AppxBundle 和许可证适用于企业的 Microsoft Store文件夹。

    例如，如果将文件下载到 c：\Temp，则运行的命令为：
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. 现在，Surface 应用将在你的当前 Windows 计算机上可用。 

   在 Surface 应用在已预配它的计算机上正常运行之前，你还必须预配本文前面所述的框架。 若要预配这些框架，请使用你用于预配 Surface 应用的提升的 PowerShell 会话中的以下过程。

5. 在提升的 PowerShell 会话中，复制并粘贴以下命令：

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. 在提升的 PowerShell 会话中，复制并粘贴以下命令：

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <a name="install-surface-app-with-mdt"></a>使用 MDT 安装 Surface 应用
以下过程使用 MDT 在部署时自动安装 Surface 应用。 该应用程序在部署期间自动由 MDT 预配，因此可将该过程用于现有映像。 这是将 Surface 应用作为 Windows 部署到 Surface 设备的一部分的建议过程，因为它不会降低 Windows 映像的跨平台兼容性。

1. 使用本文前面 [介绍的过程](#download-surface-app-from-a-microsoft-store-for-business-account)下载 Surface app AppxBundle 和许可证文件。 

2. 使用 MDT 部署工作台中的"新建应用程序向导"，将下载的文件作为包含源文件 **的新应用程序导入**。

3. 在"**新建**应用程序向导"的"命令详细信息"页上，指定**** 默认的"工作目录"，为 **"** 命令"指定 AppxBundle 的文件名，如下所示：

   * 命令：
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * 工作目录：%DEPLOYROOT%\Applications\SurfaceApp

若要使 Surface 应用在目标计算机上运行，还需要使用本文前面介绍的框架。 使用以下过程将 Surface 应用所需的框架导入 MDT，并配置它们作为依赖项。

1. 使用本文前面介绍的过程下载框架文件。 将每个框架存储在单独的文件夹中。

2. 使用 MDT 部署工作台中的"新建应用程序向导"，将下载的文件作为包含源文件 **的新应用程序导入**。

3. 在"**命令详细信息**"页上，在"命令"字段中键入下载的每个应用程序的文件名和**** 默认工作目录。

若要将框架配置为 Surface 应用的依赖项，请使用此过程：

1. 在 MDT 部署工作台中打开 Surface 应用的属性。

2. 单击 **"依赖项"** 选项卡，然后单击"添加 **"。**

3. 使用"新建应用程序向导"中提供的名称，选中每个框架的复选框。

导入后，Surface 应用将在"部署向导"的"**** 应用程序"步骤中Windows选择。 也可以通过遵循此过程在部署任务序列中指定应用程序来自动安装该应用程序：

1. 在 MDT 部署工作台中打开你的部署任务序列。

2. 在部署的“状态还原”**** 部分中添加一个新的“安装应用程序”****。

3. 选择 **"安装单个应用程序** "，将 **Surface App** 指定为 **要安装的应用程序**。

有关将应用包括到你的 Windows 部署中，请参阅使用[MDT 准备部署](/windows/deployment/deploy-windows-mdt/prepare-for-windows-deployment-with-mdt)。

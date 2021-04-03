---
title: 在 Microsoft Surface Hub 上安装应用
description: 管理员可以安装来自 Microsoft Store 或适用于企业的 Microsoft 应用商店的应用。
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: 安装应用, Microsoft Store, 适用于企业的 Microsoft 应用商店
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: a6e791defed4970b9a1940580b5f80bbe4f006a4
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470470"
---
# <a name="install-apps-on-your-microsoft-surface-hub"></a>在 Microsoft Surface Hub 上安装应用

可在 Surface Hub 上安装其他应用，以满足团队或组织需要。 可使用不同方法安装应用，具体取决于是否在开发和测试应用，或者是否在部署已发布的应用。 本主题介绍为其中一种方案安装应用的方法。

了解以下有关 Surface Hub 应用的一些事项：
- Surface Hub 仅运行[通用 Windows 平台 (UWP) 应用](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)。 无法在 Surface Hub 上运行使用 [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) 创建的应用。
- 应用必须面向[通用设备系列](https://msdn.microsoft.com/library/windows/apps/dn894631)或 Windows 团队设备系列。
- Surface Hub 仅支持来自适用于企业 [Microsoft](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) [Store 的离线授权应用](https://businessstore.microsoft.com/store)。
- 默认情况下，应用必须经过应用商店签名才能安装。 在测试和开发时，还可以选择运行开发人员签名的 UWP 应用，使设备进入开发人员模式即可。
- 将应用提交到 Microsoft Store 时，开发人员需要设置设备系列可用性和组织许可选项，以确保应用可在 Surface Hub 上运行。
- 在 Surface Hub 上安装应用需要管理员凭据。 由于设备要在公用空间（例如会议室）中使用，用户无法访问 Microsoft Store 以下载和安装应用。


## <a name="develop-and-test-apps"></a>开发和测试应用
开发自己的应用时，有几种在 Surface Hub 上测试应用的选项。

### <a name="developer-mode"></a>开发人员模式
默认情况下，Surface Hub 仅运行发布到 Microsoft Store 并由其进行签名的 UWP 应用。 作为[应用认证过程](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process)的一部分，提交到 Microsoft Store 的应用将进行安全和合规性测试，这可有助于保护 Surface Hub 不受恶意应用的攻击。
 
启用开发人员模式还可安装开发人员签名的 UWP 应用。
 
> [!IMPORTANT]
> 在启用开发人员模式后，需要重置 Surface Hub 才能禁用该模式。 重置设备将删除所有本地用户文件和配置，然后重新安装 Windows。

**打开开发人员模式** 
1. 在 Surface Hub 中，启动“设置”****。
2. 请在系统提示时，键入该设备的管理员凭据。
3. 导航到“更新和安全”**** > “对于开发人员”****。
4. 选择“开发人员模式”**** 并接受警告提示。

### <a name="visual-studio"></a>Visual Studio
开发时，在 Surface Hub 上测试应用的最简方法是使用 Visual Studio。 Visual Studio 的远程调试功能有助于在应用广泛部署之前发现其中的问题。 有关详细信息，请参阅[使用 Visual Studio 测试 Surface Hub 应用](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio)。

### <a name="provisioning-package"></a>设置包
使用 Visual Studio 为 UWP 应用[创建应用包](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx)，并且使用测试证书签名。 然后使用 Windows 映像和配置设计器 (ICD) 创建包含该应用包的设置包。 有关详细信息，请参阅[创建设置包](provisioning-packages-for-certificates-surface-hub.md)。


## <a name="submit-apps-to-the-microsoft-store"></a>向 Microsoft Store 提交应用
在准备好发布应用后，开发人员需要将其提交并发布到 Microsoft Store。 有关详细信息，请参阅[发布 Windows 应用](https://developer.microsoft.com/store/publish-apps)。

提交应用时，开发人员需要设置**设备系列可用性**和**组织授权**选项，确保该应用可在 Surface Hub 上运行。

**设置设备系列可用性**

1. 在 [Windows 开发人员中心](https://developer.microsoft.com)上，导航到应用提交页面。

2. 选择“程序包”****。
3. 在**设备系列可用性**下，选择以下选项：
    
    - **Windows 10 协同版**
    - **让 Microsoft 决定是否使应用可用于以后任何设备系列**
  
   ![显示“设备系列可用性”页面的图像 - Microsoft Store 应用提交过程的一部分。](images/device-family.png)  
    
   有关详细信息，请参阅[设备系列可用性](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability)。

**设置组织授权**

1. 在 [Windows 开发人员中心](https://developer.microsoft.com)上，导航到应用提交页面。

2. 选择“定价和可用性”****。

3. 在“组织授权”下，选择**允许组织断开连接(脱机)授权**。

   ![显示“组织授权”页面的图像 - Microsoft Store 应用提交过程的一部分。](images/sh-org-licensing.png)

   > [!NOTE]
   > 默认情况下，**使我的应用可用于带有应用商店托管(联机)许可和分发的组织**处于选中状态。

   > [!NOTE]
   > 开发人员还可直接将业务线应用发布到企业，无需在应用商店中广泛提供。 有关详细信息，请参阅[向企业分配 LOB 应用](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises)。

   有关详细信息，请参阅[组织授权选项](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing)。


## <a name="deploy-released-apps"></a>部署发布的应用

有几种选项可安装已发布到 Microsoft Store 的应用，具体取决于是否要在几台设备上评估它们，或者是否要将它们广泛部署到组织。

若要安装发布的应用：
- 使用 Microsoft Store 应用下载应用，或者
- 从适用于企业的 Microsoft 应用商店中下载应用包，并使用设置包或受支持的 MDM 提供程序分配。

### <a name="microsoft-store-app"></a>Microsoft Store 应用
若要评估在 Microsoft Store 中发布的应用，请在 Surface Hub 上使用 Microsoft Store 应用浏览和下载应用。

> [!NOTE]
> 将应用大规模部署到组织时不推荐使用 Microsoft Store 应用：
> - 若要下载应用，必须使用 Microsoft 帐户或组织帐户登录 Microsoft Store 应用。 但是，一个帐户同一时间只能连接最多 10 台设备。 如果拥有超过 10 台 Surface Hub，则需要创建多个帐户，或者在安装应用间隙从帐户中删除设备。
> - 若要安装应用，需要在拥有的每台 Surface Hub 上手动登录 Microsoft Store 应用。

**在 Surface Hub 上浏览 Microsoft Store** 
1. 在 Surface Hub 中，启动**设置**。
2. 请在系统提示时，键入该设备的管理员凭据。
3. 导航到“此设备”**** > “应用和功能”****。
4. 选择**打开应用商店**。

### <a name="download-app-packages-from-microsoft-store-for-business"></a>从适用于企业的 Microsoft 应用商店中下载应用包
若要下载在 Surface Hub 上安装应用所需的应用包，请访问[适用于企业的 Microsoft 应用商店](https://www.microsoft.com/business-store)。 可在适用于企业的应用商店中为组织的 Windows10 设备（包括 Surface Hub）查找、获取和管理应用。
 
> [!NOTE]
> Surface Hub 当前仅支持通过适用于企业的应用商店获取的脱机授权应用。 应用开发人员在提交应用时设置脱机授权可用性。

查找并获取所需应用，然后下载：
- 脱机授权的应用包（.appx 或 .appxbundle）
- *解码*许可文件（如果当前使用设置包安装应用）
- *编码*许可文件（如果当前使用 MDM 分配应用）
- 任何必要的依赖关系文件

有关详细信息，请参阅[下载脱机授权的应用](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)。

### <a name="provisioning-package"></a>设置包
在一些 Surface Hub 上可使用设置包手动安装从适用于企业的应用商店下载的脱机授权应用。 使用 Windows 映像和配置设计器 (ICD) 创建设置包，该设置包含有应用包和从适用于企业的应用商店中下载的*已解码*许可文件。 有关详细信息，请参阅[创建设置包](provisioning-packages-for-certificates-surface-hub.md)。

### <a name="supported-mdm-provider"></a>受支持的 MDM 提供程序
若要将应用部署到组织中的大量 Surface Hub，请使用受支持的 MDM 提供程序。 下表显示支持部署脱机许可的应用包的 MDM 提供程序。

| MDM 提供程序                | 支持脱机授权的应用包 |
|-----------------------------|----------------------------------------|
| 从版本 1602 版本 (配置管理器本地 MDM)  | 是 |
|
| 第三方 MDM 提供程序    | 查看以确保 MDM 提供程序支持部署脱机许可的应用包。 |

**使用 Microsoft Endpoint Configuration Manager 远程部署应用**

> [!NOTE]
> 这些说明基于 Microsoft Endpoint Configuration Manager 的当前分支。

1. 将 Surface Hub 注册到 MDM 管理中。 有关详细信息，请参阅使用[MDM 提供程序管理 Surface Hub。](manage-settings-with-mdm-for-surface-hub.md)

2. 从适用于企业的应用商店下载脱机授权的应用包、*已编码的*许可文件以及任何所需依赖关系文件。 有关详细信息，请参阅[下载脱机授权的应用](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)。 将下载的文件放入网络共享上的相同文件夹中。

3. 在 Configuration Manager 控制台的“软件库”**** 工作区中，单击“概述”**** > “应用程序管理”**** > “应用程序”****。

4. 在“主页”**** 选项卡的“创建”**** 组中，单击“创建应用程序”****。

5. 在“创建应用程序向导”**** 的“常规”**** 页上，选中“自动检测安装文件中有关此应用程序的信息”**** 复选框。

6. 在“类型”**** 下拉列表中，选择“Windows 应用包(\*.appx, \*.appxbundle)”****。

7. 在“位置”**** 字段中，为从适用于企业的应用商店中下载的脱机许可应用包指定 UNC 路径（形式为 \\server\share\\filename）。 或者，单击“浏览”****，浏览到应用包。

8. 在“导入信息”**** 页面上，查看导入的信息，然后单击“下一步”****。 如果需要，可单击“上一步”**** 返回并更正任何错误。

9. 在“常规信息”**** 页上，完成填写有关应用的其他详细信息。 如果有些信息是自动从应用包中获取，则可能已经填充完成。

10. 单击“下一步”****、在“摘要”页上查看应用程序信息，然后完成“创建应用程序向导”。 

11. 为应用程序创建部署类型。 有关详细信息，请参阅[为应用程序创建部署类型](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application)。

12. 将应用程序部署到 Surface Hub。 有关详细信息，请参阅使用 [Microsoft Endpoint Configuration Manager 部署应用程序](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)。

13. 根据需要更新应用，方法是从适用于企业的应用商店下载新程序包，然后在 Configuration Manager 中发布应用程序修订。 有关详细信息，请参阅使用 [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt595704.aspx)更新和停用应用程序。 

> [!NOTE] 
> 如果你使用 Microsoft Endpoint Configuration Manager (当前分支) ，可以通过将适用于企业应用商店的应用商店连接到 Configuration Manager 来绕过上述步骤。 通过执行此操作，你可以同步使用 Configuration Manager 购买的应用列表，在 Configuration Manager 控制台中查看这些应用，并像部署任何其他应用一样部署它们。 有关详细信息，请参阅使用 Configuration Manager 管理 [适用于企业](https://technet.microsoft.com/library/mt740630.aspx)Microsoft Store 的应用。


## <a name="summary"></a>摘要

有几种不同的方法在 Surface Hub 上安装应用，具体取决于你是在开发应用、在少量设备上评估应用，还是将应用广泛部署到你的组织。 此表总结了受支持的方法：

| 安装方法             | 开发应用 | 评估 <br> 几台设备上的应用 | 将应用广泛部署到 <br> 组织 |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| Visual Studio              | X |   |   |
| 设置包       | X | X |   |
| Microsoft Store 应用          |   | X |   |
| 受支持的 MDM 提供程序     |   |   | X |

## <a name="more-information"></a>详细信息

- [博客文章: 使用 Intune 将 Microsoft Store 应用部署到 Surface Hub](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## <a name="related-topics"></a>相关主题

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)

 

 






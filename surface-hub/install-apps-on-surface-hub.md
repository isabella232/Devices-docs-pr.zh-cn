---
title: 在 Microsoft Surface Hub 上安装应用
description: 管理员可以安装来自 Microsoft Store 或适用于企业的 Microsoft 应用商店的应用。
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: dpandre
manager: laurawi
keywords: 安装应用, Microsoft Store, 适用于企业的 Microsoft 应用商店
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/16/2021
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: a8c11406c7786e379999ff32f482815d6b180b24
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676656"
---
# <a name="install-apps-on-your-microsoft-surface-hub"></a>在 Microsoft Surface Hub 上安装应用

可在 Surface Hub 上安装其他应用，以满足团队或组织需要。 可使用不同方法安装应用，具体取决于是否在开发和测试应用，或者是否在部署已发布的应用。 本主题介绍为其中一种方案安装应用的方法。

## <a name="supported-app-guidelines"></a>支持的应用指南

- Surface Hub 仅运行[通用 Windows 平台 (UWP) 应用](/windows/uwp/get-started/universal-application-platform-guide)。 使用[MSIX 打包工具创建的应用](/windows/msix/packaging-tool/tool-overview)不会在 Surface Hub。
- 应用必须面向[通用设备系列](/windows/uwp/get-started/universal-application-platform-guide)或 Windows 团队设备系列。
- Surface Hub仅支持来自[适用于企业的 Microsoft Store](/microsoft-store/distribute-offline-apps)的离线[授权适用于企业的 Microsoft Store。](https://businessstore.microsoft.com/store/private-store)
- 默认情况下，应用必须经过应用商店签名才能安装。 在测试和开发时，还可以选择运行开发人员签名的 UWP 应用，使设备进入开发人员模式即可。
- 将应用提交到Microsoft Store时，开发人员需要设置设备系列可用性和组织许可选项，以确保应用可在 Surface Hub 上运行。
- 在 Surface Hub 上安装应用需要管理员凭据。 由于设备要在公用空间（例如会议室）中使用，用户无法访问 Microsoft Store 以下载和安装应用。

## <a name="deploy-released-apps"></a>部署发布的应用

有几种选项可安装已发布到 Microsoft Store 的应用，具体取决于是否要在几台设备上评估它们，或者是否要将它们广泛部署到组织。

若要安装发布的应用：

- 使用 Microsoft Store 应用下载应用，或者
- 从适用于企业的 Microsoft 应用商店中下载应用包，并使用设置包或受支持的 MDM 提供程序分配。

### <a name="microsoft-store-app"></a>Microsoft Store 应用

若要评估在 Microsoft Store 中发布的应用，请在 Surface Hub 上使用 Microsoft Store 应用浏览和下载应用。

> [!NOTE]
> 将应用大规模部署到组织时不推荐使用 Microsoft Store 应用：
>
> - 若要下载应用，必须使用 Microsoft 帐户或组织帐户登录 Microsoft Store 应用。 但是，一个帐户同一时间只能连接最多 10 台设备。 如果拥有超过 10 台 Surface Hub，则需要创建多个帐户，或者在安装应用间隙从帐户中删除设备。
> - 若要安装应用，需要在拥有的每台 Surface Hub 上手动登录 Microsoft Store 应用。

#### <a name="to-browse-the-microsoft-store-on-surface-hub"></a>在 Surface Hub 上浏览 Microsoft Store

1. 在 Surface Hub 中，启动**设置**。
2. 请在系统提示时，键入该设备的管理员凭据。
3. 导航到**Surface Hub**  >  **应用&功能。**
4. 选择 **"打开** 应用商店"并搜索要查找的应用。

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

### <a name="install-offline-licensed-apps-via-provisioning-package"></a>通过预配包安装离线授权的应用

在一些 Surface Hub 上可使用设置包手动安装从适用于企业的应用商店下载的脱机授权应用。 使用 Windows 映像和配置设计器 (ICD) 创建设置包，该设置包含有应用包和从适用于企业的应用商店中下载的*已解码*许可文件。 有关详细信息，请参阅[创建设置包](provisioning-packages-for-certificates-surface-hub.md)。

### <a name="supported-mdm-provider"></a>受支持的 MDM 提供程序

若要将应用部署到组织中的大量 Surface Hub，请使用受支持的 MDM 提供程序。 下表显示支持部署脱机许可的应用包的 MDM 提供程序。

| MDM 提供程序                | 支持脱机授权的应用包 |
|-----------------------------|----------------------------------------|
| 从版本 1602 版本 (配置管理器本地 MDM)  | 是 |
|
| 第三方 MDM 提供程序    | 查看以确保 MDM 提供程序支持部署脱机许可的应用包。 |

> [!NOTE]
> 若要使用 Microsoft Intune 远程部署离线应用，请参阅从 适用于企业的 Microsoft Store[管理 VPP 应用](/mem/intune/apps/windows-store-for-business)。 Surface Hub应用部署仅支持分配给设备组并使用设备许可证类型的离线应用。

## <a name="develop-and-test-apps"></a>开发和测试应用

本部分为应用开发人员提供有关在应用程序上测试应用Surface Hub。

### <a name="developer-mode"></a>开发人员模式

默认情况下，Surface Hub 仅运行发布到 Microsoft Store 并由其进行签名的 UWP 应用。 作为[应用认证过程](/windows/uwp/publish/the-app-certification-process)的一部分，提交到 Microsoft Store 的应用将进行安全和合规性测试，这可有助于保护 Surface Hub 不受恶意应用的攻击。

启用开发人员模式还可安装开发人员签名的 UWP 应用。

> [!IMPORTANT]
> 在启用开发人员模式后，需要重置 Surface Hub 才能禁用该模式。 重置设备将删除所有本地用户文件和配置，然后重新安装 Windows。

#### <a name="to-turn-on-developer-mode"></a>打开开发人员模式

1. 在 Surface Hub 中，启动“设置”****。
2. 请在系统提示时，键入该设备的管理员凭据。
3. 导航到“更新和安全”**** > “对于开发人员”****。
4. 选择“开发人员模式”**** 并接受警告提示。

### <a name="visual-studio"></a>Visual Studio

开发时，在 Surface Hub 上测试应用的最简方法是使用 Visual Studio。 Visual Studio 的远程调试功能有助于在应用广泛部署之前发现其中的问题。 有关详细信息，请参阅[使用 Visual Studio 测试 Surface Hub 应用](/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio)。

#### <a name="create-provisioning-package"></a>创建预配包

使用 Visual Studio 为 UWP 应用创建应用包，并且使用测试证书签名。 然后使用 Windows 映像和配置设计器 (ICD) 创建包含该应用包的设置包。 有关详细信息，请参阅[创建设置包](provisioning-packages-for-certificates-surface-hub.md)。

## <a name="submit-apps-to-the-microsoft-store"></a>向 Microsoft Store 提交应用

在准备好发布应用后，开发人员需要将其提交并发布到 Microsoft Store。 有关详细信息，请参阅发布[Windows应用和游戏](/windows/uwp/publish)。

提交应用时，开发人员需要设置**设备系列可用性**和**组织授权**选项，确保该应用可在 Surface Hub 上运行。

### <a name="to-set-device-family-availability"></a>设置设备系列可用性

1. 在 [Windows 开发人员中心](https://developer.microsoft.com/windows)上，导航到应用提交页面。
2. 选择“程序包”****。
3. 在**设备系列可用性**下，选择以下选项：

    - **Windows 10 协同版**
    - **让 Microsoft 决定是否使应用可用于以后任何设备系列**
  
   ![显示“设备系列可用性”页面的图像 - Microsoft Store 应用提交过程的一部分。](images/device-family.png)  

   有关详细信息，请参阅[设备系列可用性](/windows/uwp/publish/upload-app-packages#device-family-availability)。

### <a name="to-set-organizational-licensing"></a>设置组织授权

1. 在 [Windows 开发人员中心](https://developer.microsoft.com/windows)上，导航到应用提交页面。

2. 选择“定价和可用性”****。

3. 在“组织授权”下，选择**允许组织断开连接(脱机)授权**。

   ![显示“组织授权”页面的图像 - Microsoft Store 应用提交过程的一部分。](images/sh-org-licensing.png)

   > [!NOTE]
   > 默认情况下，**使我的应用可用于带有应用商店托管(联机)许可和分发的组织**处于选中状态。

   > [!NOTE]
   > 开发人员还可直接将业务线应用发布到企业，无需在应用商店中广泛提供。 有关详细信息，请参阅[向企业分配 LOB 应用](/windows/uwp/publish/distribute-lob-apps-to-enterprises)。

   有关详细信息，请参阅[组织授权选项](/windows/uwp/publish/organizational-licensing)。

## <a name="summary"></a>摘要

根据你是在开发应用、在少量设备上评估应用还是将应用广泛部署到组织，Surface Hub在设备上安装应用有几种不同的方法。 此表总结了受支持的方法：

| 安装方法             | 开发应用 | 评估 <br> 几台设备上的应用 | 将应用广泛部署到 <br> 组织 |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| Visual Studio              | X |   |   |
| 设置包       | X | X |   |
| Microsoft Store 应用          |   | X |   |
| 受支持的 MDM 提供程序     |   |   | X |

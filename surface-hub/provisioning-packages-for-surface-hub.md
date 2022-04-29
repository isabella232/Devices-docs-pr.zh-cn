---
title: 创建设置包
description: 对于Windows 10或Windows 11，可以使用预配包配置使用注册表或配置服务提供程序 (CSP) 的设置。
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: 添加证书, 预配包
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/20/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 1f1e084b8be0ab44c853fe003236ba7f25b4ff4c
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497635"
---
# <a name="create-provisioning-packages-for-surface-hub"></a>创建 Surface Hub 的预配程序包

通过预配包，可以自动部署关键功能，帮助在组织中的所有 Surface Hub 中提供一致的体验。  使用Windows配置设计器 (单独电脑上的 WCD) ，可以完成以下任务：

- 注册 Active Directory 或 Azure Active Directory
- 创建设备管理员帐户
- 添加应用程序和证书
- 配置代理设置
- 添加 Surface Hub 配置文件
- 配置 [配置服务提供程序 (CSP) 设置](/windows/client-management/mdm/surfacehub-csp)

## <a name="overview"></a>概述

1. 在运行Windows 10或Windows 11的单独电脑上，从[Microsoft Store安装Windows配置设计](https://www.microsoft.com/store/apps/9nblggh4tx22)器。
1. 选择[**“预配Surface Hub设备**](#use-surface-hub-provisioning-wizard)以使用向导配置常用设置。 或者选择 [“高级预配](#use-advanced-provisioning) ”以查看和配置所有可能的设置。
1. 创建预配包并将其保存到 USB 驱动器。
1. 在首次运行设置期间或通过设置应用将包部署到Surface Hub。 若要了解详细信息，请参阅 [“创建预配包](/windows/configuration/provisioning-packages/provisioning-create-package)”。

## <a name="use-surface-hub-provisioning-wizard"></a>使用Surface Hub预配向导

1. 打开Windows配置设计器，然后选择 **“预配Surface Hub设备**。<br>
    ![使用Surface Hub预配向导。](images/sh-prov-start.png)
    
2. 为项目命名，然后选择 **“下一步**”。

### <a name="add-certificates"></a>添加证书

> [!div class="mx-imgBorder"]
> ![添加证书。](images/sh-prov-cert.png)

若要使用证书预配设备，请选择 **“添加证书**”。 输入证书的名称，然后浏览以选择要使用的证书。  有关高级预配选项，请参阅以下部分， [向包添加证书](#add-a-certificate-to-your-package)。

### <a name="configure-proxy-settings"></a>配置代理设置

> [!div class="mx-imgBorder"]
> ![配置代理设置。](images/sh-prov-proxy.png)

1. 对代理设置切换为**是**或**否**。 默认情况下，Surface Hub会自动检测代理设置。 但是，如果你的基础结构以前需要使用代理服务器，现已更改为不需要代理服务器，你可以使用预配包将你的 Surface Hub 设备恢复为默认设置，方法是依次选择**是**和**自动检测设置**。
2. 如果切换 **为“是**”，可以选择通过输入下列设置之一来自动检测代理设置或手动配置设置：

    - 设置脚本的 URL。
    - 静态代理服务器地址和端口信息。

3. 如果打算使用安装脚本或代理服务器，请关闭 **自动检测设置**。 可以使用安装脚本 *或* 代理服务器，而不能同时使用两者。
4. 输入异常 (Surface Hub应直接连接到的地址，而无需使用代理服务器) 。 **示例：** *.office365.com
5. 确定是否将代理服务器用于本地地址。

### <a name="set-up-device-admins"></a>设置设备管理员

 > [!div class="mx-imgBorder"]
 > ![加入 Active Directory、Azure AD 或创建本地管理员帐户。](images/sh2-wcd.png)

你可以在 Active Directory 中注册设备并指定安全组使用设置应用，在 Azure Active Directory 中注册以允许全局管理员使用设置应用，或在该设备上创建本地管理员帐户。

1. 在 Active Directory 中注册设备，请输入最低特权用户帐户的凭据，以将该设备加入域，并指定安全组在 Surface Hub 上拥有管理员凭据。 如果将包应用到重置Surface Hub，则可以使用同一个域帐户，前提是它是最初设置Surface Hub的同一帐户。 否则，必须在预配包中使用不同的域帐户。
2. 在使用Windows配置设计器配置批量Azure AD注册之前，[请计划Azure AD加入实现](/azure/active-directory/devices/azureadjoin-plan)。 Azure AD 租户中的**每个用户的最大设备数**设置用于确定你在该向导中获取的批量令牌可使用的次数。
3. 若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。 设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。 选择 **“获取批量令牌**”。 在**让我们帮你登录**窗口中，输入有权限将设备加入 Azure AD 的帐户，然后再输入密码。 选择 **“接受**”可向Windows配置设计器授予必要的权限。
4. 若要创建本地管理员帐户，请选择该选项，然后输入用户名和密码。

> [!IMPORTANT]
> 如果在预配包中创建本地帐户，则必须每 42 天使用**设置**应用更改密码。 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。

### <a name="enroll-in-third-party-mdm-provider"></a>注册第三方 MDM 提供程序

> [!div class="mx-imgBorder"]
> ![注册第三方移动设备管理。](images/sh-prov-mdm.png)

如果使用第三方移动设备管理 (MDM) 提供程序，则可以使用本部分注册Surface Hub。 若要注册Intune，请按照上一部分中所述Azure AD联接设置，并按照以下Intune文档中的说明进行操作：[快速入门：为Windows 10/11 设备设置自动注册](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

1. 为第三方 MDM 中的注册切换 **“是** ”或 **“否** ”。
2. 如果切换 **为“是**”，请提供授权注册设备并指定身份验证类型的服务帐户、密码或证书指纹。
3. 如果 MDM 提供程序需要，请输入发现服务、注册服务和策略服务的 URL。

 若要了解详细信息，请参阅[使用 MDM 提供程序管理Surface Hub。](manage-settings-with-mdm-for-surface-hub.md)

### <a name="add-applications"></a>添加应用程序

> [!div class="mx-imgBorder"]
> ![添加应用程序。](images/sh-prov-apps.png)

你可以在预配包中安装多个通用 Windows 平台 (UWP) 应用。 若要了解详细信息，请参阅 [使用应用预配电脑](/windows/configuration/provisioning-packages/provision-pcs-with-apps)。

> [!NOTE]
> 尽管Windows配置设计器允许将经典 Win32 应用添加到预配包，但Surface Hub只接受 UWP 应用。 如果包括经典 Win32 应用，预配将失败。

### <a name="add-a-configuration-file"></a>添加配置文件

除了此预配包，还可以使用Surface Hub配置文件来更轻松地设置设备。 Surface Hub配置文件包含用于连接到Exchange、Microsoft Teams或Skype for Business的设备帐户列表，以及用于无线投影的“友好名称”。

**若要创建Surface Hub配置文件：**

1. 打开Microsoft Excel (或其他.csv编辑器) ，创建名为_SurfaceHubConfiguration.csv的.csv_文件。

2. 输入以下格式的设备帐户和友好名称列表：

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > 配置文件不得包含列标题。 当包含在应用于Surface Hub的预配包中时，可以从文件中选择设备的帐户和友好名称。 若要创建.csv文件，请使用 UPN 地址格式 (rainier@contoso.com) 或下级登录名称格式 (contoso\rainier) 。

    rainier@contoso.com，password，Rainier Surface Hub

3. 将文件保存到项目文件夹，并使用预配包将其复制到 USB 密钥。

> [!NOTE]
> 配置文件只能在第一次运行设置期间应用。

### <a name="password-protect-provisioning-package"></a>密码保护预配包

如果选择使用密码，则每次将预配包应用到设备时都需要输入密码。

### <a name="complete-provisioning-wizard"></a>完整预配向导

如果只需要配置常用设置，请选择 **“****FinishCreate** > ”并跳到[“生成包](#build-your-package)”部分。 或者通过切换到高级预配继续配置设置。

## <a name="use-advanced-provisioning"></a>使用高级预配

> [!TIP]
> 使用向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置。<br><br> ![切换到高级编辑器。](images/icd-simple-edit.png)

1. 如果从上一部分继续，请选择 **“切换到高级编辑器**”，否则**Windows配置设计器**打开，然后选择 **“高级预配**”。

   ![使用高级预配。](images/sh-prov-adv.png)

2. 为项目命名，然后选择 **“下一步**”。

3. 选择 **“通用”以Windows 10 协同版**，选择 **“下一步**”，然后选择 **“完成**”。

   ![WCD 新项目。](images/icd-new-project.png)

4. 在项目中，在 **“可用自定义”** 下，选择 **“通用团队”设置**。

   :::image type="content" alt-text="WCD 常见设置。" source="images/icd-common-settings.png":::

### <a name="add-a-certificate-to-your-package"></a>将证书添加到程序包

可使用设置包安装支持设备验证 Microsoft Exchange 身份的证书。

> [!NOTE]
> 设置包仅可将证书安装到设备（本地计算机）存储，而非用户存储。 如果组织要求将证书安装到用户存储，请使用中心**设置**应用：**更新 &** **SecurityCertificatesImport** >  >  **证书**。
或者，可以使用  [**MDM**](manage-settings-with-mdm-for-surface-hub.md) 策略将证书部署到设备存储或用户存储。

> [!TIP]
> **ClientCertificates** 部分适用于具有私钥的 .pfx 文件;根 CA 的 .cer 文件应放置在 **RootCertificates** 部分和 **CACertificates** 部分的中间 CA 中。

1. 在**Windows配置 DesignerAvailable** >  **自定义项**中，转到 **Runtime settingsCertificatesClientCertificates** > **** > 。****
2. 输入 **CertificateName** 的标签，然后选择 **“添加**”。
3. 输入 **CertificatePassword**。
4. 对于 **CertificatePath**，浏览并选择证书。
5. 将 **ExportCertificate** 设置为 **False**。
6. 对于 **KeyLocation**，选择**仅软件**。

### <a name="add-a-uwp-app-to-your-package"></a>将 UWP 应用添加到包

若要将 UWP 应用添加到预配包，需要应用包 (.appx 或 .appxbundle 文件) 和任何依赖项文件。 如果已从适用于企业的 Microsoft Store 获取了该应用，还需要*已解码的*应用许可。 请参阅[分配脱机应用](/microsoft-store/distribute-offline-apps)，了解如何从适用于企业的 Microsoft Store 下载这些项目。

**若要添加 UWP 应用，请执行以下操作：**

1. 在**可用自定义项**窗格中，转到**运行时设置** > **UniversalAppInstall** > **DeviceContextApp**。

2. 输入应用的 **PackageFamilyName** ，然后选择 **“添加**”。 为了保持一致性，请使用应用的程序包系列名称。 如果已从适用于企业的 Microsoft Store 获取了该应用，可在应用许可中查找程序包系列名称。 使用文本编辑器打开许可证文件，并使用 PFM 标记之间的值。

3. 对于 **ApplicationFile**，请选择 **“浏览”** 查找目标应用 ( .appx 或 .appxbundle) 。

4. 对于 **DependencyAppxFiles**，请选择 **“浏览”** 以查找并添加应用的任何依赖项。 对于 Surface Hub，仅需要 x64 版本的依赖项。

如果从适用于企业的 Microsoft Store获取了应用，则需要将应用许可证添加到预配包。

**若要添加应用许可证，请执行以下操作：**

1. 制作应用许可的副本，并为其重命名，以使用 **.ms-windows-store-license** 扩展名。 例如，将“example.xml”重命名为“example.ms-windows-store-license”。

2. 在Windows配置设计器中，转到 **Available customizationsRuntime** >  settingsUniversalAppInstallDeviceContextAppLicense**** > **** > 。****

3. 输入 **LicenseProductId** ，然后选择 **“添加**”。 为了保持一致性，请使用应用许可中的应用许可 ID。 使用文本编辑器打开许可文件。 然后，在 **License** 标记中，使用 **LicenseID** 属性中的值。

4. 选择新的 **LicenseProductId** 节点。 对于 **LicenseInstall**，请选择 **“浏览”** 查找并选择已重命名的许可证文件 (example.ms-windows-store-license) 。

### <a name="add-a-policy-to-your-package"></a>将策略添加到程序包

Surface Hub 支持[策略配置服务提供程序](/windows/client-management/mdm/policy-configuration-service-provider)中的策略子集。 其中一些策略可以使用Windows配置设计器进行配置。

 **若要添加 [CSP 策略](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)，请执行以下操作：**

1. 转到 **Available customizationsRuntime** >  **settingsPolicies****** > 。
2. 根据需要选择要管理和配置策略设置的组件。 例如，若要防止员工在Surface Hub上使用 InPrivate 网站浏览，请选择 **AllowInPrivate**，然后选择 **“禁用**”。  

   :::image type="content" alt-text="配置策略设置。" source="images/sh-prov-policies.png" lightbox="images/sh-prov-policies.png":::

### <a name="add-surface-hub-settings-to-your-package"></a>将 Surface Hub 设置添加到程序包

可将 [SurfaceHub 配置服务提供程序](/windows/client-management/mdm/surfacehub-csp)中的设置添加到设置包。

1. 转到 **“可用自定义项** > **Common Team Edition”设置**。
1. 根据需要选择要管理和配置策略设置的组件。
1. 配置完预配包后，选择 **“****FileSave** > ”。
1. 读取项目文件可能包含敏感信息的警告，然后选择 **“确定”**

### <a name="build-your-package"></a>生成程序包

生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。  将项目文件存储在安全位置，如果不再需要，则将其删除。

1. 打开**Windows Configuration** **DesignerExportProvisioning** >  >  **包**。

2. 将 **所有者** 更改为 **IT 管理员**。  

3. 设置**程序包版本**的值，然后选择**下一步**。

   > [!TIP]
   > 将所有者设置为 IT 管理员可确保包设置保持适当的“优先属性”，如果随后从其他源应用其他预配包，则在Surface Hub保持有效状态。

   > [!TIP]
   > 可以修改现有包并更改版本号以更新以前应用的包。

4. 可选：可以选择加密包并启用包签名：

    1. 选择 **“加密”包** ，然后输入密码。
    1. 选择 **“对** **packageBrowse** >  签名”，并根据需要选择证书。

    > [!IMPORTANT]
    > 建议在预配包中包含受信任的预配证书。 将包应用到设备时，证书将添加到系统存储中，使后续包能够以无提示方式应用。

5. 选择 **“下一步** ”以指定输出位置。 默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。 或者选择 **“浏览”** 以更改默认输出位置。 选择**下一步** 。

6. 选择 **“生成** ”以开始生成包。 项目信息显示在生成页中。

7. 如果生成失败，则会显示一条错误消息，其中包含指向项目文件夹的链接。 查看日志以诊断错误，然后再次尝试生成包。

8. 如果生成成功，则会显示预配包、输出目录和项目目录的名称。 选择 **“完成** ”以关闭向导并返回到“自定义”页。

9. 选择  **输出位置**  以转到包的位置。 将 .ppkg 复制到空 U 盘。

## <a name="apply-a-provisioning-package-to-surface-hub"></a>将设置包应用到 Surface Hub

可通过两种方式将预配包部署到Surface Hub：

- [首次运行设置。](#apply-a-provisioning-package-during-first-run) 可以应用预配包来自定义多个选项，包括Wi-Fi设置、代理设置、设备帐户详细信息、Azure AD联接和相关设置。  
- [设置应用。](#apply-a-provisioning-package-using-settings-app) 首次运行安装程序后，可以通过设置应用应用预配包。 

### <a name="apply-a-provisioning-package-during-first-run"></a>在首次运行时应用设置包

1. 首次打开Surface Hub时，首次运行的程序将显示[**“Hi there”页面**](first-run-program-surface-hub.md)。 确保设置已正确配置，然后再继续。

2. 将包含 .ppkg 文件的 U 盘插入 Surface Hub。 如果程序包位于驱动器的根目录中，首次运行程序将识别它，并询问是否要设置设备。 选择**设置**。

3. 下一个屏幕会要求你选择预配源。 选择“可移动媒体”****，然后点击“下一步”****。

4. 选择要应用的预配包 (*.ppkg) ，然后点击 **“下一步**”。 注意，首次运行期间只能安装一个程序包。

5. 首次运行程序将显示预配包要应用的更改汇总。 选择**是的，添加它**。

6. 如果配置文件包含在 U 盘的根目录中，你将看到**选择配置**。 将显示配置文件中的第一个设备帐户以及将应用到 Surface Hub 的帐户信息摘要。

7. 在 **“选择配置**”中，选择要应用的设备名称，然后选择 **“下一步**”。

预配包中的设置将应用于设备，并将完成 OOBE。 设备重启后，你可以删除 U 盘。

### <a name="apply-a-provisioning-package-using-settings-app"></a>使用设置应用应用预配包

1. 将包含 .ppkg 文件的 U 盘插入 Surface Hub。
2. 从Surface Hub开始**设置**并在出现提示时输入管理员凭据。
3. 导航到 **Surface Hub** > **设备管理**。 在 **“预配包**”下，选择 **“添加或删除预配包** > **”。**
4. 选择设置包，然后选择**添加**。  如果出现提示，请再次输入管理员凭据。
5. 你将看到要应用的更改摘要。 选择**是的，添加它**。

## <a name="learn-more"></a>了解详细信息

- [下载Windows配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [创建预配包](/windows/configuration/provisioning-packages/provisioning-create-package)
- [通过 MDM 提供商管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md)

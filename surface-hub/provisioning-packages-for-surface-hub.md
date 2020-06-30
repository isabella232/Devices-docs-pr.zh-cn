---
title: 创建预配包 (Surface Hub)
description: 对于 Windows 10，使用注册表或配置服务提供程序 (CSP) 的设置可通过预配包进行配置。
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: 添加证书, 预配包
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: 0ce77122aecfc9a30ac9dc52dfea7e0b0ccf7e1f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831980"
---
# 创建预配包 (Surface Hub)

本主题介绍了如何使用 Windows 配置设计器创建预配包，并将其应用到 Surface Hub 设备。 对于 Surface Hub，可使用预配包添加证书、安装通用 Windows 平台 (UWP) 应用以及自定义策略和设置。

在首次运行设置时，可使用 U 盘或通过**设置**应用来应用预配包。 


## 优点
-   使用移动设备管理 (MDM) 提供程序快速配置设备。

-   无需网络连接。

-   易于应用。

[了解有关设置包的优势和用法的详细信息。](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## 要求 

若要创建预配包并将其应用到 Surface Hub，需要以下工具：

-   Windows 配置设计器，可从 Microsoft Store 或 Windows 10 评估和部署工具包 (ADK) 中安装此设计器。 [了解如何安装 Windows 配置设计器。](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   U 盘。
-   如果使用**设置**应用来应用程序包，需要设备管理员凭据。

需要在运行 Windows 10 的电脑上创建预配包、将程序包保存到 U 盘，然后将其部署到 Surface Hub。


## Surface Hub 预配包的受支持项目

使用**预配 Surface Hub 设备**向导，你可以：

- 在 Active Directory、Azure Active Directory 或 MDM 中注册 
- 创建设备管理员帐户 
- 添加应用程序和证书
- 配置代理设置
- 添加 Surface Hub 配置文件

>[!WARNING]
>你必须在 Windows 10 上运行 Windows 配置设计器，才能使用该向导配置 Azure Active Directory 注册。

使用高级预配编辑器，你可以将这些项目添加到 Surface Hub 预配包：

- **策略** - Surface Hub 支持[策略配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies)中的策略子集。 
- **设置** - 可在 [SurfaceHub 配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)中配置任意设置。

>[!TIP]
> 使用向导创建带有通用设置的程序包，然后切换到高级编辑器以添加其他设置。
>
>![打开高级编辑器](images/icd-simple-edit.png)

## 使用 Surface Hub 预配向导

[安装 Windows 配置设计器](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)后，你可以创建预配包。

### 创建预配包 

1. 打开 Windows 配置设计器：
   - 在“开始”屏幕或“开始”菜单搜索中，键入“Windows 配置设计器”，然后单击 Windows 配置设计器快捷方式， 
    
     或
    
   - 如果 Windows 配置设计器是从 ADK 安装的，请导航到 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86`（在 x64 计算机上）或 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe`（在 x86 计算机上），然后双击 **ICD.exe**。

2. 单击**预配 Surface Hub 设备**。

3. 为你的项目命名，然后单击**下一步**。

### 配置设置

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>若要使用证书预配设备，请单击<strong>添加证书</strong>。 输入证书的名称，然后浏览到要使用的证书并将其选中。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br>对代理设置切换为<strong>是</strong>或<strong>否</strong>。 Surface Hub 的默认配置为自动检测代理设置，以便如果是你想要的设置，你可以选择<strong>否</strong>。 但是，如果你的基础结构以前需要使用代理服务器，现已更改为不需要代理服务器，你可以使用预配包将你的 Surface Hub 设备恢复为默认设置，方法是依次选择<strong>是</strong>和<strong>自动检测设置</strong>。 </br></br>如果切换为<strong>是</strong>，则可以选择自动检测代理设置，或者可以通过在设置脚本或静态代理服务器地址中输入 URL 手动配置设置。 你还可以确定是否要使用代理服务器作为本地地址，并输入例外（Surface Hub 无需使用代理服务器直接连接到的地址）。  </td><td><img src="images/proxy-details.png" alt="configure proxy settings"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br>你可以在 Active Directory 中注册设备并指定安全组使用设置应用，在 Azure Active Directory 中注册以允许全局管理员使用设置应用，或在该设备上创建本地管理员帐户。</br></br>在 Active Directory 中注册设备，请输入最低特权用户帐户的凭据，以将该设备加入域，并指定安全组在 Surface Hub 上拥有管理员凭据。 如果在 Active Directory 中注册设备的预配包将应用于重置的 Surface Hub，则仅当列出的帐户是域管理员或者是最初设置 Surface Hub 的同一帐户时，才能使用同一域帐户。 否则，必须在预配包中使用不同的域帐户。</br></br>使用 Windows 配置设计器向导配置 Azure AD 批量注册之前，请<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">在贵组织中设置 Azure AD 加入</a>。 Azure AD 租户中的<strong>每个用户的最大设备数</strong>设置用于确定你在该向导中获取的批量令牌可使用的次数。 若要在 Azure AD 中注册设备，请选择该选项，并输入你要使用向导获取的批量令牌的友好名称。 设置令牌的到期日期（从获取该令牌之日算起最多 30 天）。 单击<strong>获取批量令牌</strong>。 在 " <strong> 让&#39;s 登录" 窗口中 </strong> ，输入有权将设备加入 Azure AD 的帐户，然后输入密码。 单击<strong>接受</strong>以向 Windows 配置设计器提供所需的权限。</br></br>若要创建本地管理员帐户，请选择该选项，然后输入用户名和密码。 </br></br><strong>重要提示</strong>：如果在预配包中创建本地帐户，则必须每 42 天使用<strong>设置</strong>应用更改密码。 如果在此期限内未更改密码，帐户可能会被锁定而无法登录。  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br>对 MDM 中的注册切换为<strong>是</strong>或<strong>否</strong>。 </br></br>如果切换为<strong>是</strong>，必须提供服务帐户和密码或有权注册设备的证书指纹，并指定身份验证类型。 如果你的 MDM 提供程序要求，也请为发现服务、注册服务和策略服务输入 URL。 <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)">了解有关使用 MDM 管理 Surface Hub 的更多信息。</a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br>你可以在预配包中安装多个通用 Windows 平台 (UWP) 应用。 有关这些设置的帮助，请参阅<a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">使用应用预配电脑</a>。 </br></br><strong>重要提示： </strong> 虽然向导界面允许你选择经典 Win32 应用，但仅在将应用于 Surface Hub 的预配包中包含 UWP 应用。 如果包括经典 Win32 应用，预配将失败。 </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br>在此步骤中，你不会&#39;t 配置任何设置。 它提供添加包含设备帐户列表的配置文件的说明。 配置文件不得包含列标题。 当将预配包应用于 Surface Hub 时，如果 Surface Hub 配置文件包含在 U 盘上，则可以从文件中选择设备帐户和友好名称。 请参阅<a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">样本配置文件</a>了解相关示例。</br></br><strong>重要提示： </strong> 配置文件只能在全新安装体验（OOBE）期间应用，并且只能与使用 windows 10 版本1703发布的 Windows 配置设计器创建的预配程序包一起使用。  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish"/></br></br>你可以设置密码，以保护你的预配包。 你必须在将预配包应用到设备时输入此密码。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完成之后，请单击**创建**。 这只需几秒钟的时间。 生成该包之后，其存储位置将在页面底部显示为超链接。

## 示例配置文件

Surface Hub 配置文件包含你的设备可用于连接到 Exchange 和 Skype for Business 的设备帐户列表。 当你将预配包应用于 Surface Hub 时，你可以在 U 盘的根目录中包含配置文件，然后选择需要应用于该设备的帐户。 配置文件仅可以在全新设置体验 (OOBE) 期间应用，并且只能与使用随 Windows 10 版本 1703 发布的 Windows 配置设计器创建的预配包一起使用。

使用 Microsoft Excel 或其他 CSV 编辑器创建一个名为 `SurfaceHubConfiguration.csv` 的 CSV 文件。 在该文件中，按以下格式输入设备帐户和友好名称列表：

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
>由于配置文件以纯文本形式存储设备帐户密码，因此我们建议你在将预配包应用到你的设备后更新密码。 你可以使用 [DeviceAccount 节点](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount)（位于 [Surface Hub 配置服务提供程序 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) 中）通过 MDM 更新密码。


下面是 `SurfaceHubConfiguration.csv` 示例。 

```
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## 使用高级预配

[安装 Windows 配置设计器](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)后，你可以创建预配包。

### 创建预配包（高级）

1. 打开 Windows 配置设计器：
   - 在“开始”屏幕或“开始”菜单搜索中，键入“Windows 配置设计器”，然后单击 Windows 配置设计器快捷方式， 
    
     或
    
   - 如果 Windows 配置设计器是从 ADK 安装的，请导航到 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86`（在 x64 计算机上）或 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe`（在 x86 计算机上），然后双击 **ICD.exe**。

2. 单击**高级预配**。
   
3. 为你的项目命名，然后单击**下一步**。

4. 选择**通用于 Windows 10 协同版**、单击**下一步**，然后单击**完成**。

    ![ICD 新项目](images/icd-new-project.png)

5. 在项目的**可用自定义项**下，选择**常用协同版设置**。

    ![ICD 常用设置](images/icd-common-settings.png)


### 将证书添加到程序包
可使用设置包安装支持设备验证 Microsoft Exchange 身份的证书。

> [!NOTE]
> 设置包仅可将证书安装到设备（本地计算机）存储，而非用户存储。 如果组织要求证书必须安装到用户存储，则必须使用移动设备管理 (MDM) 部署这些证书。 有关详细信息，请参阅 MDM 解决方案文档。

1. 在**可用自定义项**窗格中，转到**运行时设置** > **证书** > **ClientCertificates**。 

2. 输入 **CertificateName**，然后单击**添加**。 

2. 输入 **CertificatePassword**。 

3. 对于 **CertificatePath**，浏览并选择证书。 

4. 将 **ExportCertificate** 设置为 **False**。

5. 对于 **KeyLocation**，选择**仅软件**。


### 将通用 Windows 平台 (UWP) 应用添加到程序包
将 UWP 应用添加到设置包前，需要具备应用包（.appx 或 .appxbundle）和任何依赖关系文件。 如果已从适用于企业的 Microsoft Store 获取了该应用，还需要*已解码的*应用许可。 请参阅[分配脱机应用](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)，了解如何从适用于企业的 Microsoft Store 下载这些项目。

1. 在**可用自定义项**窗格中，转到**运行时设置** > **UniversalAppInstall** > **DeviceContextApp**。

2. 为应用输入 **PackageFamilyName**，然后单击**添加**。 为了保持一致性，请使用应用的程序包系列名称。 如果已从适用于企业的 Microsoft Store 获取了该应用，可在应用许可中查找程序包系列名称。 使用文本编辑器打开许可证文件，并使用 "..." 标记之间的值。 \<PFM\> \</PFM\>

3. 对于 **ApplicationFile**，单击**浏览**以查找并选择目标应用（\*.appx 或 \*.appxbundle）。

4. 对于 **DependencyAppxFiles**，单击**浏览**，为应用查找并添加任何依赖项。 对于 Surface Hub，仅需要 x64 版本的依赖项。

如果已从适用于企业的 Microsoft Store 获取了该应用，还需要将应用许可添加到设置包。

1. 制作应用许可的副本，并为其重命名，以使用 **.ms-windows-store-license** 扩展名。 例如，“example.xml”变为“example.ms-windows-store-license”。

2. 在 ICD 的**可用自定义项**窗格中，转到**运行时设置** > **UniversalAppInstall** > **DeviceContextAppLicense**。

3. 输入 **LicenseProductId**，然后单击**添加**。 为了保持一致性，请使用应用许可中的应用许可 ID。 使用文本编辑器打开许可文件。 然后，在 \<License\> 标记中，使用**LicenseID**属性中的值。

4. 选择新的 **LicenseProductId** 节点。 对于 **LicenseInstall**，单击**浏览**，选择在步骤 1 中重命名的许可文件。


### 将策略添加到程序包
Surface Hub 支持[策略配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)中的策略子集。 某些策略可通过 ICD 配置。

1. 在**可用自定义项**窗格中，转到**运行时设置** > **策略**。

2. 选择其中一个可用的策略区域。

3. 选择并设置要添加到设置包的策略。


### 将 Surface Hub 设置添加到程序包 

可将 [SurfaceHub 配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)中的设置添加到设置包。 

1. 在**可用自定义项**窗格中，转到**运行时设置** > **WindowsTeamSettings**。

2. 选择其中一个可用的设置区域。

3. 选择并设置要添加到设置包的设置。 


## 生成程序包

1. 完成预配包的配置后，在**文件**菜单上单击**保存**。

2. 阅读项目文件可能包含敏感信息的警告，然后单击**确定**。

    > [!IMPORTANT]
    > 生成预配包时，可能会在项目文件和预配包 (.ppkg) 文件中包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应将项目文件存储在安全位置，并在不再需要它们时删除项目文件。

3. 在**导出**菜单中，单击**预配包**。

4. 将**所有者**更改为 **IT 管理员**，这会将此设置包的优先级设置为高于应用于来自其他源的设备的设置包。

5. 设置**程序包版本**的值，然后选择**下一步**。

    > [!TIP]
    > 可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。

6. 可选：可选择加密程序包并启用程序包签名。

    -   **启用程序包加密** - 如果你选择此选项，将在屏幕上显示自动生成的密码。

    -   **启用程序包签名** - 如果选择此选项，则必须选择一个有效的证书，用于对程序包进行签名。 可以通过单击**浏览...** 并选择要用于对程序包进行签名的证书，指定相关证书。

        > [!IMPORTANT]
        > 建议将受信任的设置证书包含在预配包中。 当程序包应用于设备时，该证书将添加到系统存储，然后便可以静默方式应用通过该证书签名的任意程序包。 

7. 单击**下一步**，指定在生成预配包后想要放置的输出位置。 默认情况下，Windows ICD 会使用项目文件夹作为输出位置。<p>
或者，你还可以单击**浏览**更改默认输出位置。

8. 单击“下一步”****。

9. 单击**构建**开始构建程序包。 项目信息会显示在构建页面中，并且进度栏会指示构建状态。<p>
如果你需要取消构建，请单击“取消” ****。 这将取消当前的构建过程、关闭向导，并使你返回到“自定义页面” ****。

10. 如果构建失败，则显示一条包含项目文件夹链接的错误消息。 你可以扫描日志以确定导致错误的原因。 解决问题后，请尝试重新构建程序包。<p>
如果构建成功，将显示设置包的名称、输出目录和项目目录。

    -   如果要进行选择，你可以重新构建设置包并选择不同的输出程序包路径。 若要执行此操作，请单击“返回”**** 更改输出程序包名称和路径，然后单击“下一步”**** 启动另一次构建。
    
    -   如果你已完成，请单击“完成”**** 关闭向导，并返回到“自定义页面”****。

11. 选择**输出位置**链接以转到该程序包所在的位置。 将 .ppkg 复制到空 U 盘。


## 将设置包应用到 Surface Hub

有两个选项可将设置包部署到 Surface Hub。 在[首次运行向导期间](#apply-a-provisioning-package-during-first-run)，你可以应用安装证书的预配包，或者在首次运行程序完成后，你可以通过使用[设置](#apply-a-package-using-settings)来应用配置设置、应用和证书的预配包。 


### 在首次运行时应用设置包

> [!IMPORTANT]
> 在首次运行程序中，只能使用预配程序包安装证书。 使用**设置**应用安装应用和应用其他设置。

1. 第一次打开 Surface Hub 时，首次运行程序将显示[**“你好”页面**](first-run-program-surface-hub.md#first-page)。 确保设置已正确配置，然后再继续。

2. 将包含 .ppkg 文件的 U 盘插入 Surface Hub。 如果程序包位于驱动器的根目录中，首次运行程序将识别它，并询问是否要设置设备。 选择**设置**。

    ![设置设备？](images/provisioningpackageoobe-01.png)

3. 下一个屏幕会要求你选择预配源。 选择“可移动媒体”****，然后点击“下一步”****。

    ![预配此设备](images/provisioningpackageoobe-02.png)
    
4. 选择要应用的设置包 (\*.ppkg)，然后点击**下一步**。 注意，首次运行期间只能安装一个程序包。

    ![选择程序包](images/provisioningpackageoobe-03.png)

5. 首次运行程序将显示预配包要应用的更改汇总。 选择**是的，添加它**。  

    ![是否信任此程序包？](images/provisioningpackageoobe-04.png)
    
6. 如果配置文件包含在 U 盘的根目录中，你将看到**选择配置**。 将显示配置文件中的第一个设备帐户以及将应用到 Surface Hub 的帐户信息摘要。

    ![选择配置](images/ppkg-config.png)    

7. 在**选择配置**中，请选择要应用的设备名称，然后单击**下一步**。

    ![选择友好设备名称](images/ppkg-csv.png)
    
预配包中的设置将应用于设备，并将完成 OOBE。 设备重启后，你可以删除 U 盘。

### 使用“设置”应用程序包

1. 将包含 .ppkg 文件的 U 盘插入 Surface Hub。

2. 在 Surface Hub 中，启动**设置**，然后在收到提示时输入管理员凭据。

3. 导航到 **Surface Hub** > **设备管理**。 在**预配包**下，选择**添加或删除预配包**。

4. 选择**添加程序包**。

5. 选择设置包，然后选择**添加**。 如果系统出现提示，可能需要重新输入管理员凭据。

6. 将看到设置包应用的更改汇总。 选择**是的，添加它**。



---
title: 在 Surface Hub 上安装渐进式 Web 应用
description: 说明管理员如何通过Intune或预配包在Surface Hub上安装渐进式Web 应用 (PVA) 。
keywords: Surface Hub、PVA、应用
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/27/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 687dd85d3490d420133edc5b7de3b2af0c0433ef
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497532"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>在 Surface Hub 上安装渐进式 Web 应用

渐进式 Web 应用 (PWA) 支持打开了丰富的新应用源，可显著扩展可在 Suface Hub 上运行的可用应用库。  用户可以访问Microsoft Store之外的大量应用程序，并直接从“应用”菜单运行这些应用程序。  与网页相比，PVA 的行为更像是具有脱机功能、后台更新功能和其他独特功能的本机应用。 大多数网站都可以安装为 PVA，并利用 Web 开发人员启用的任何其他功能。

管理员可以通过移动设备管理 (MDM) 提供程序（如 Microsoft Intune）在 Surface Hub 上远程安装 PVA。 也可以使用预配包。 本文介绍这两种方法，其中包含用于安装 YouTube、WebEx、Zoom 和 Uber 的示例代码，以及安装自己的 PVA 的说明。 若要了解详细信息，请参阅[渐进式Web 应用概述](/microsoft-edge/progressive-web-apps-chromium/)。

> [!IMPORTANT]
> 安装 PVA 之前，请确保Surface Hub已安装 [KB5011543](https://support.microsoft.com/help/5011543) (或后续Windows更新) 。 若要详细了解最新Windows 10 协同版更新，请参阅[Surface Hub更新历史记录](surface-hub-update-history.md)。

- [通过 Intune 在 Surface Hub 上安装 PVA](#install-pwas-via-intune)
- [通过预配包在Surface Hub上安装 PVA](#install-pwas-via-provisioning-package)

用户还可以安装 PVA 以在中心会话期间使用。 会话结束时，将删除 PVA。 若要了解详细信息，请参阅[Microsoft Edge中安装、管理或卸载应用](https://support.microsoft.com/topic/install-manage-or-uninstall-apps-in-microsoft-edge-0c156575-a94a-45e4-a54f-3a84846f6113)

## <a name="install-pwas-via-intune"></a>通过 Intune 安装 PVA

使用Intune或其他 MDM 提供程序在 Surface Hub 上安装 PVA。 若要了解详细信息，请参阅 [使用 MDM 提供程序管理设置](manage-settings-with-mdm-for-surface-hub.md)。

### <a name="get-started"></a>入门

1. 在Microsoft Endpoint Manager[**管理中心登录到Intune**](https://endpoint.microsoft.com/)门户。

2. 转到 **DevicesConfiguration** **** > **PoliciesCreate** >  **配置文件**。

3. 在“平台”下，选择**Windows 10及更高版本**。 在“配置文件”类型下，选择 **“模板**”。 在“模板名称”下，选择 **“管理模板”。**

4. 选择 **“创建”。**

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="创建Intune配置文件" lightbox="images/pwa-hubpwainstall.png":::

5. 命名配置文件，输入可选说明，然后选择 **“下一步**”。

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="名称配置文件" lightbox="images/pwa-hubwebappscreateprofile.png":::

### <a name="configure-force-installed-web-apps-policy-intune"></a>配置强制安装的Web 应用策略 (Intune) 

1. 在 **“所有设置** > **计算机配置**”下，选择 **“Microsoft Edge**”，然后在“搜索”框中输入**强制安装**，选择**强制安装的Web 应用**，然后选择 **“启用**”。

    :::image type="content" source="images/pwa-enable-force-install.png" alt-text="启用强制安装的 Web 应用" lightbox="images/pwa-enable-force-install.png":::

2. 在静**默安装Web 应用的 URL** 下，复制并输入以下代码片段，以安装适用于 YouTube、Webex、Zoom 和 Uber 的 PVA。 或者跳到下一步安装其他 PVA。

    :::image type="content" source="images/hub-pwa-install-enable.png" alt-text="输入强制安装的 Web 应用列表" lightbox="images/hub-pwa-install-enable.png":::

    ```json
    [
    { "url": "https://www.youtube.com/",       "default_launch_container": "window" },
    { "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
    { "url": "https://zoom.us/join",           "default_launch_container": "window" },
    { "url": "https://www.uber.com/",          "default_launch_container": "tab"}
    ]
    ```

3. 或者，可以从以下语法创建 JSON 代码片段来安装其他 PVA。

    ```json
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  } ]
    ```

4. 在“作用域标记”页上，选择 **“下一步** ”以跳过。

5. 在“分配”页上的 **“包含的组**”下，选择 **“添加组**”。

    :::image type="content" source="images/pwa-add-groups.png" alt-text="添加组" lightbox="images/pwa-add-groups.png" :::

6. 在 **“选择要包含的组**”下，输入包含要面向的 Surface Hub 的组的名称，选择 **“选择**”，然后单击 **“下一步**”。 若要详细了解如何向组分配配置文件，请 [参阅“添加组”来组织用户和设备](/mem/intune/fundamentals/groups-add)。

    :::image type="content" source="images/pwa-select-groups.png" alt-text="选择组" lightbox="images/pwa-select-groups.png":::

7. 查看，然后选择 **“创建**”。

    :::image type="content" source="images/pwa-create-profile.png" alt-text="创建配置文件" lightbox="images/pwa-create-profile.png" :::

8. 若要以身临其境的方式应用配置文件，请选择 **DevicesAll** >  **设备**并查找目标设备。 打开其“概述”窗格，然后选择 **“同步**”。

    :::image type="content" source="images/pwa-sync-tenant.png" alt-text="同步租户" lightbox="images/pwa-select-groups.png":::

 > [!IMPORTANT]
 > 若要完成 PVA 安装，请转到Surface Hub并启动 Edge。 PVA 已安装并显示在“所有应用"开始"菜单列表中。

 ### <a name="troubleshooting-intune-managed-pwas"></a>Intune管理的 PVA 疑难解答
 
如果看不到**所有应用**下列出的 PVA：

- 请确保Surface Hub具有最新的更新，特别是 [KB5011543](https://support.microsoft.com/help/5011543) (或后续Windows更新) 。 若要详细了解最新Windows 10 协同版更新，请参阅[Surface Hub更新历史记录](surface-hub-update-history.md)。
- 检查以确保配置文件已成功应用，并且与其他设置没有冲突。 
- 检查以确保配置文件面向包含Surface Hub的安全组。 
- 请记得在Surface Hub上一次启动 Edge，这是成功安装Intune托管的 PVA 所必需的。

## <a name="install-pwas-via-provisioning-package"></a>通过预配包安装 PVA

可以通过使用 USB 驱动器将预配包应用到 Surface Hub 来安装 PVA。 若要了解详细信息，请参阅 [“创建预配包](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard)”。

### <a name="get-started-with-provisioning"></a>开始预配

1. 在运行Windows 10或Windows 11的单独电脑上，[从Microsoft Store安装Windows配置设计](https://www.microsoft.com/store/apps/9nblggh4tx22)器 (WCD) 。

2. 在 WCD 中，创建新的Project。 选择 **“预配桌面设备”，** 为项目提供名称，然后选择 **“完成”。**

3. 选择 **“切换到高级编辑器** ”，然后选择 **“是** ”进行确认。

### <a name="configure-msedgepolicy"></a>配置 MSEdgePolicy

1. 在 WCD 中的“可用自定义项”窗格中，转到 **\Runtime 设置\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**

2. 在自定义编辑窗格中，输入 **MSEdgePolicy** 的应用名称，然后选择 **“添加**”。

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="输入应用名称作为 MSEdgePolicy" lightbox="images/pwa-add-edge-policy.png" :::

3. 在“可用自定义项”窗格中，选择 **“AppName： MSEdgePolicy”** ，然后在编辑窗格中，将 **SettingType** 更改为 **“策略** ”，然后选择 **“添加**”。

4. 在“可用自定义项”窗格中，选择 **“设置类型：策略** ”，然后在编辑窗格中将 **AdmxFileUid** 设置为 **MSEdgePolicy，** 然后选择 **“添加**”。

5. 在“可用自定义项”窗格中，选择 **“AdmxFileUid：MSEdgePolicy** ”，并在编辑窗格中，将以下代码作为单行文本输入来设置 **MSEdgePolicy** ：

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="输入 MSEdgePolicy 的代码" lightbox="images/pwa-enter-edge-policy.png" :::

    ```xml
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```

### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>配置强制安装的Web 应用策略 (预配包) 

1. 在 WCD 中的“可用自定义项”窗格中，转到：**\Runtime 设置\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**

2. 在“自定义编辑”窗格中，输入“Areaname 作为 **MSEdgePolicy~Policy~microsoft_edge”，** 选择 **“添加**”。

3. 在“可用自定义项”窗格中，选择 **“区域名称：MSEdgePolicy~Policy~microsoft_edge** ”，在编辑窗格中，将 **策略名称** 设置为 **WebAppInstallForceList** ，然后选择 **“添加**”。

4. 在“可用自定义项”窗格中，选择 **PolicyName： WebAppInstallForceList**，在 **WebAppInstallForceList** 的编辑窗格中，将[PWA代码](#ppkg-code-samples)作为单行文本输入。

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="输入强制安装Web 应用策略的代码" lightbox="images/pwa-force-web-app-install.png":::

### <a name="ppkg-code-samples"></a>PPKG 代码示例

- YouTube PWA：

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- 多个 PVA，包括 YouTube、Webex、Zoom 和 Uber：

    ```xml
     <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.signin.webex.com/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://zoom.us/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.uber.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- 或者，可以从以下语法创建 JSON 代码片段来安装其他 PVA：

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.contoso.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>导出预配包并应用于 Surface Hub

1. 在菜单栏中，选择“ **导出**”，选择 **“预配包** ”，然后按照提示生成 .ppkg 文件。

2. 插入空 USB 闪存驱动器。 选择输出位置以转到包的位置。 将 .ppkg 文件复制到 USB 驱动器。

3. 通过设置应用或首次运行设置期间应用预配包。 若要了解详细信息，请参阅 [“创建预配包”](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

 ### <a name="troubleshooting-provisioning-package-pwas"></a>排查预配包 PVA 问题
 
如果看不到 **所有应用**下列出的 PVA：

- 请确保Surface Hub具有最新的更新，特别是 [KB5011543](https://support.microsoft.com/help/5011543) (或后续Windows更新) 。 若要详细了解最新Windows 10 协同版更新，请参阅[Surface Hub更新历史记录](surface-hub-update-history.md)。

## <a name="learn-more"></a>了解详细信息

- [WCD 参考：ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [渐进式 Web 应用 （PWA） 概述](/microsoft-edge/progressive-web-apps-chromium/)

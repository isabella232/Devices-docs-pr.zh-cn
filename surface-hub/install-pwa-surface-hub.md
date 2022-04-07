---
title: 在Surface Hub上安装渐进式Web 应用
description: 说明管理员如何通过Intune或预配包在Surface Hub上安装渐进式Web 应用 (PVA) 。
keywords: Surface Hub、PVA、应用
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/22/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: ea30f25451b0be54bd2b6eaa2552036e0d78ff27
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472685"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>在Surface Hub上安装渐进式Web 应用

管理员可以使用移动设备管理提供商[ (MDM) ](/microsoft-edge/progressive-web-apps-chromium/)（例如Microsoft Intune或预配包）远程安装 Surface Hub 上的渐进式Web 应用 (PVA) 。 PVA 函数，例如在受支持的平台上安装的本机应用，以及与其他浏览器上的常规网站一样的函数。 当管理员在 Surface Hub 上安装 PVA 时，用户可以直接从"应用"菜单运行它们。 

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
3. 在"平台"下，选择**Windows 10及更高版本**。 在"配置文件"类型下，选择 **"模板**"。 在"模板名称"下，选择 **"管理模板"。**
4. 选择 **"创建"。**

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="创建Intune配置文件" :::

5. 命名配置文件，输入可选说明，然后选择 **"下一步**"。

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="名称配置文件" :::

### <a name="configure-force-installed-web-apps-policy-intune"></a>配置强制安装的Web 应用策略 (Intune) 

1. 选择**Microsoft Edge配置**，然后在搜索框中输入**强制安装**，选择**强制安装Web 应用**，然后选择 **"启用**"。

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="配置强制安装的Web 应用" :::

2. 在**静默安装Web 应用 URL** 下，从以下语法创建 XML 代码片段，或从下面的[示例](#example-pwas)复制。 

    ```
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  }, ]
    ```
    
#### <a name="example-pwas"></a>示例 PVA

本示例安装适用于 YoutTube、Webex、Zoom 和 Uber 的 PVA。

```
    [
{ "url": "https://www.youtube.com/",       "default_launch_container": "window" },
{ "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
{ "url": "https://zoom.us/join",           "default_launch_container": "window" },
{ "url": "https://www.uber.com/",          "default_launch_container": "tab"}
]
```

3. 输入包含要安装的应用的 URL 的代码片段。
4. 根据需要输入可选范围标记，然后选择 **"下一步"。**
5. 根据需要分配给用户。
6. 分配给包含要面向的 Surface Hub 的组。 若要了解详细信息，请参阅 ["添加组"以组织用户和设备](/mem/intune/fundamentals/groups-add)
7. 查看，然后选择 **"创建**"。

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="创建配置文件" :::
    

8. 根据需要同步目标设备。
9. 在Surface Hub上，启动 Edge。 PVA 已安装并显示在"所有应用"开始"菜单列表中。

## <a name="install-pwas-via-provisioning-package"></a>通过预配包安装 PVA

可以通过使用 USB 驱动器将预配包应用到 Surface Hub 来安装 PVA。 若要了解详细信息，请参阅 ["创建预配包](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard)"。

### <a name="get-started-with-provisioning"></a>开始预配

1. 在运行Windows 10或Windows 11的单独电脑上，[从Microsoft Store安装Windows配置设计](https://www.microsoft.com/store/apps/9nblggh4tx22)器 (WCD) 。
2. 在 WCD 中，创建新的Project。 选择 **"预配桌面设备"，** 为项目提供名称，然后选择 **"完成"。**
3. 选择 **"切换到高级编辑器** "，然后选择 **"是** "进行确认。

### <a name="configure-msedgepolicy"></a>配置 MSEdgePolicy

1. 在 WCD 中的"可用自定义项"窗格中，转到 **\Runtime 设置\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**
2. 在自定义编辑窗格中，输入 **MSEdgePolicy** 的应用名称，然后选择 **"添加**"。

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="输入应用名称作为 MSEdgePolicy" :::

3. 在"可用自定义项"窗格中，选择 **"AppName： MSEdgePolicy"** ，然后在编辑窗格中，将 **SettingType** 更改为 **"策略** "，然后选择 **"添加**"。
4. 在"可用自定义项"窗格中，选择 **"设置类型：策略** "，然后在编辑窗格中将 **AdmxFileUid** 设置为 **MSEdgePolicy，** 然后选择 **"添加**"。
5. 在"可用自定义项"窗格中，选择 **"AdmxFileUid：MSEdgePolicy** "，并在编辑窗格中，将以下代码作为单行文本输入来设置 **MSEdgePolicy** ：

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="输入 MSEdgePolicy 的代码" :::   
   
    ```
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```
 
### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>配置强制安装的Web 应用策略 (预配包) 

1. 在 WCD 中的"可用自定义项"窗格中，转到：**\Runtime 设置\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**
2. 在"自定义编辑"窗格中，输入"Areaname 作为 **MSEdgePolicy~Policy~microsoft_edge"，** 选择 **"添加**"。
3. 在"可用自定义项"窗格中，选择 **"区域名称：MSEdgePolicy~Policy~microsoft_edge** "，在编辑窗格中，将 **策略名称** 设置为 **WebAppInstallForceList** ，然后选择 **"添加**"。
4. 在"可用自定义项"窗格中，选择" **PolicyName： WebAppInstallForceList** "，在 **WebAppInstallForceList** 的编辑窗格中，将以下代码作为单行文本输入。

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="输入强制安装Web 应用策略的代码" :::   

 > [!TIP]
 > 本示例将 You Tube 安装为PWA。 根据需要替换 URL。 

```
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
```    

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>导出预配包并应用于 Surface Hub

1. 在菜单栏中，选择" **导出**"，选择 **"预配包** "，然后按照提示生成 .ppkg 文件。
2. 插入空 USB 闪存驱动器。 选择输出位置以转到包的位置。 将 .ppkg 文件复制到 USB 驱动器。
3. 通过设置应用或首次运行设置期间应用预配包。 若要了解详细信息，请参阅 ["创建预配包"](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

## <a name="learn-more"></a>了解详细信息

- [WCD 参考：ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [渐进式 Web 应用 （PWA） 概述](/microsoft-edge/progressive-web-apps-chromium/)

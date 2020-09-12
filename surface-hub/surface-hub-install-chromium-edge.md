---
title: 在 Surface Hub 上安装和配置新版 Microsoft Edge
description: 在 Surface Hub 上安装和配置新的 Microsoft Edge。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/11/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 6de949c7341f9d9bee60f808dab77770377acefc
ms.sourcegitcommit: a64f5f375ebc0611e5735c63afd9540db0f807c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2020
ms.locfileid: "11013693"
---
# 在 Surface Hub 上安装和配置新版 Microsoft Edge

Windows 10 Team 2020 更新支持基于 Chromium (85 和更高版本的新 Microsoft Edge，) 为 Surface Hub 的推荐浏览器。 你可以使用预配包手动安装 Microsoft Edge，或使用 Microsoft Intune 或你的首选移动设备管理 (MDM) 提供程序进行远程安装。

默认情况下，Surface Hub 设备预装了 Microsoft Edge 旧版 (版本 44) 。
 
> [!NOTE]
> 如果已安装了 Edge 开发，请完成以下步骤：
>
>1. 如果您不知道您的版本或想要确认，请打开您的 Edge 浏览器并转到 edge://version。
>2. 导航到 **Surface Hub > 设备管理**"。 在 " **预配程序包**" 下，选择 " **添加或删除预配包"。**
>3. 如果已使用早期安装程序将 Microsoft Edge 开发人员固定到 "开始" 菜单上，请从列表中单击 " **自定义开始菜单** "，然后单击 " **删除"。**
>4. 如果您使用自定义 "开始" 布局策略，则需要使用最新的边缘路径对其进行修改，如下一节中所述：在 [Surface Hub "开始" 菜单中显示 Microsoft Edge](#display-microsoft-edge-in-the-surface-hub-start-menu)。
>5. 现在，你可以预配 MicrosoftEdgeDevUninstaller ppkg。
>6. 从 **所有应用**中删除 Edge 开发人员后，请先删除 "MicrosoftEdgeDevInstaller"，然后删除 "MicrosoftEdgeDevUninstaller"。
>7. 这将成功卸载 Microsoft Edge 开发。 现在，你可以安装标准版本。

 
 
## 安装 Microsoft Edge

### 使用预配包安装 Microsoft Edge

1. 从电脑下载 [Microsoft Edge 预配包](https://aka.ms/HubEdge) ， (MicrosoftEdgeInstaller ppkg) 到 USB 驱动器的根文件夹。
2. 将 USB 驱动器插入 Surface Hub。
3. 在 "Surface Hub" 中，打开 " **设置** "，然后在出现提示时输入管理员凭据。
4. 导航到 **Surface Hub** > **设备管理**。 在**预配包**下，选择**添加或删除预配包**。
5. 选择**添加程序包**。
6. 选择 "Microsoft Edge 预配" 程序包，然后选择 " **添加**"。
7. 你将看到预配包所应用的更改的摘要。 选择**是的，添加它**。
8. 等待 Microsoft Edge 安装完成。 安装后，导航到 Surface Hub "开始" 菜单以访问新的 Microsoft Edge。              

> [!NOTE]
> 如果有较新版本的可用 Microsoft Edge，它将自动更新。
 
### 使用 Intune 安装 Microsoft Edge
 
> [!NOTE]
> Surface Hub 设备必须使用 Intune 进行注册和管理。 有关详细信息，请参阅 [通过 Microsoft Intune 管理 Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)2。
 

1. [从 Microsoft 下载 Microsoft Edge 安装程序](https://www.microsoft.com/edge/business/download)。
    - 使用来自 [稳定频道](https://docs.microsoft.com/deployedge/microsoft-edge-channels)的当前版本 ** (版本 85) **
    - 选择 **Windows 64 位**
2. [将 Microsoft Edge 安装程序添加到 Microsoft Intune 的业务线应用](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)中。
    - 如果你选择使用 Microsoft Edge 更新处理 Microsoft Edge 的自动更新，请确保配置 "**应用信息**" 窗格的 "**忽略应用版本**" 设置。 当你将此设置切换到 **"是"** 时，Microsoft Intune 将不会强制实施 Surface Hub 设备上安装的应用版本。

 
### 使用移动设备管理安装 Microsoft Edge

1. [从 Microsoft 下载 Microsoft Edge 安装程序](https://www.microsoft.com/edge/business/download)。
    - 使用来自 [稳定频道](https://docs.microsoft.com/deployedge/microsoft-edge-channels)的当前版本 ** (版本 85) **
    - 选择 **Windows 64 位**
2. 在托管位置（如本地文件共享 ( # A0) ）暂存 Microsoft Edge 安装程序。 Surface Hub 设备必须具有访问托管位置的权限。
3. 使用 [EnterpriseDesktopAppManagement 配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) 通过 MDM 提供程序安装 Microsoft Edge。

 

## 配置 Microsoft Edge

### Surface Hub 的默认 Microsoft Edge 策略
Microsoft Edge 预配置了以下策略，以提供 Surface Hub 的优化体验。
 
> [!NOTE]
>  我们建议为这些策略保留默认值。
 

| Microsoft Edge 策略                                                                                                    | 推荐的体验                                                                                                                                                                                                                                               | 默认值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 不要自动从 Microsoft Edge 旧版中导入数据类型和设置。 这可避免通过 Surface Hub 中的共享设置更改登录用户的配置文件。                                                                                                 | 第                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允许 Microsoft Edge 进程继续在后台运行，即使在最后一个浏览器窗口关闭后，在会话期间允许更快地访问 web 应用。                                                                                                      | raid-1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 不允许用户在 Microsoft Edge 中创建新的配置文件。 这将简化浏览和登录体验。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 仅允许一个用户登录到 Microsoft Edge。 这简化了浏览和登录体验                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | 使用户可以在 Microsoft Edge 中体验单一登录 (SSO) 。 当用户登录到 Surface Hub 时，其凭据可以流向受支持的网站，而无需重新进行身份验证。  | raid-1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 防止非管理员用户在 Microsoft Edge 中安装新的扩展。 若要配置默认安装的扩展列表，请使用 [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist)。 | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 隐藏用户首次运行 Microsoft Edge 时通常显示的首次运行体验和初始屏幕。 由于 Surface Hub 是共享设备，因此可简化用户体验。                                                                      | raid-1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 禁用 InPrivate 模式。 由于结束会话已清除浏览数据，因此这简化了浏览和登录体验。                                                                                                                                          | raid-1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 显示新选项卡页上的 Office 365 源体验。 当用户登录 Surface Hub 时，这将允许快速访问 Office 365 上的文件和内容。                                                                                                        | raid-1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 当用户登录到 Surface Hub 时，将使用其组织帐户创建一个非移动配置文件。 这将简化单一登录 (SSO) 体验。                                                                                                 | raid-1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | 在 Microsoft Edge 中禁用打印。 Surface Hub 不支持打印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 使 Microsoft Edge 能够通过 Microsoft 服务主动对登录用户进行身份验证。 这将简化单一登录 (SSO) 体验。                                                                                                                         | raid-1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自动将文件保存到 "下载" 文件夹，而不是询问用户保存文件的位置。 这将简化浏览体验。                                                                                                                             | 0                 |

> [!IMPORTANT]
> Windows 10 Team 操作系统目前不支持 (PWAs) 的可部署渐进式 web 应用。  另请注意，在 Surface Hub 上不支持 Microsoft Edge 策略设置 [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) 。 

### 配置 Microsoft Edge 策略设置

使用 [Microsoft edge 浏览器策略](https://docs.microsoft.com/deployedge/microsoft-edge-policies) 配置 microsoft edge 中的浏览器设置。 可以使用以下策略应用这些策略：

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)，
- [你的首选移动设备管理 (支持 ADMX 摄取的 MDM) 提供程序](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)，或者
- [使用 Windows 配置设计器中的 ADMX 摄取预配程序包](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)。

 
### 配置 Microsoft Edge 更新

默认情况下，Microsoft Edge 会自动更新。 使用 [Microsoft edge 更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) 配置 Microsoft edge 更新的设置。
请注意，Surface Hub 不支持以下 Microsoft Edge 更新策略：

- **Allowsxs** -在 Surface Hub 上，Microsoft edge 稳定通道始终替换 Microsoft edge 旧版。
- **CreateDesktopShortcut** – Surface Hub 不使用桌面快捷方式。

> [!NOTE]
>  Microsoft Edge 需要连接到 Internet 以支持其功能。 确保将 [必要的域 url](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) 添加到允许列表，以确保通过防火墙和其他安全机制进行通信。
 
### 在 Surface Hub "开始" 菜单中显示 Microsoft Edge

如果使用默认的 "开始" 菜单布局，则可以将 "开始" 菜单与 Microsoft Edge 预配包一起安装，以将 Microsoft Edge 添加为固定的应用。
如果要应用自定义的 "开始" 菜单布局，请使用以下 XML 添加适用于 Microsoft Edge 的固定磁贴。

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

有关详细信息，请参阅 [配置 Surface Hub "开始" 菜单](https://docs.microsoft.com/surface-hub/surface-hub-start-menu)。
 
> [!NOTE]
> 新的 Microsoft Edge 不支持使用 SecondaryTiles 的已固定网站和链接。

## 相关链接

- [Microsoft Edge 文档](https://docs.microsoft.com/microsoft-edge/)。


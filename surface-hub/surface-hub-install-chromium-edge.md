---
title: 在 Surface Hub 上安装和配置新版 Microsoft Edge
description: 安装并配置Microsoft Edge新Surface Hub。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 93f76cadafe2570197fbe70db88540b6be90c3f1
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576722"
---
# <a name="install-and-configure-the-new-microsoft-edge-on-surface-hub"></a>在 Surface Hub 上安装和配置新版 Microsoft Edge

Windows 10 协同版 2020 Update 支持基于 Chromium (版本 85 及以上) 的新 Microsoft Edge 作为 Surface Hub 2S 和 Surface Hub (v1) 的推荐浏览器。 本文介绍如何使用以下三种方法之一安装浏览器：预配包、Microsoft Intune 或 MDM (第三) 提供程序。

> [!IMPORTANT]
> 默认情况下，Surface Hub设备预安装Microsoft Edge 旧版 (版本 44) 。 安装[2020 Update](surface-hub-2020-update.md)后，建议切换到新Microsoft Edge浏览器;对[Microsoft Edge 旧版的支持](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0)将于 2021 年 3 月 9 日结束。

> [!NOTE]
> 从屏幕手势顶部向下轻扫以退出全屏模式需要使用两根手指和新的Microsoft Edge。 在长按触摸后显示的上下文菜单中也提供退出全屏操作。


## <a name="install-microsoft-edge-using-a-provisioning-package"></a>使用Microsoft Edge包安装预配包

1. 从电脑中，将[Microsoft Edge](https://aka.ms/HubEdge)预配包 (MicrosoftEdgeInstaller.ppkg) U 盘的根文件夹。
2. 将 USB 驱动器插入Surface Hub。
3. 在Surface Hub中 **，设置**系统提示时输入管理员凭据。
4. 导航到 **Surface Hub** > **设备管理**。 在**预配包**下，选择**添加或删除预配包**。
5. 选择**添加程序包**。
6. 选择"Microsoft Edge预配包"，然后选择"添加 **"。**
7. 你将看到预配包所应用更改的摘要。 选择**是的，添加它**。
8. 等待Microsoft Edge安装完成。 安装后，导航到"Surface Hub"菜单以访问新Microsoft Edge。              

> [!NOTE]
> 如果有较新版本的 Microsoft Edge，它将自动更新。
 
## <a name="install-microsoft-edge-using-intune"></a>使用 Intune Microsoft Edge安装应用程序
 
> [!NOTE]
> 若要使用此安装方法，Surface Hub Intune 注册和管理设备。 有关详细信息，请参阅使用[MDM Surface Hub 2S。](manage-settings-with-mdm-for-surface-hub.md)
 

1. [下载Microsoft Edge安装程序](https://www.microsoft.com/edge/business/download)。
    - 使用 Stable 渠道[版本](https://docs.microsoft.com/deployedge/microsoft-edge-channels)**85 (中的当前) **
    - 选择**Windows 64 位**
2. [将 Microsoft Edge 安装程序作为业务线应用添加到 Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)。
    - 如果你选择使用Microsoft Edge 更新自动更新来处理应用程序Microsoft Edge，请确保配置"忽略应用版本"设置"应用**信息"** 窗格。 **** 将此设置**切换为"** 是Microsoft Intune时，Microsoft Intune不会强制应用设备上安装的应用Surface Hub版本。

## <a name="install-microsoft-edge-using-third-party-mdm-provider"></a>使用Microsoft Edge MDM 提供程序安装客户端

1. [从 Microsoft Microsoft Edge安装程序](https://www.microsoft.com/edge/business/download)。
    - 使用 Stable 渠道[版本](https://docs.microsoft.com/deployedge/microsoft-edge-channels)**85 (中的当前) **
    - 选择**Windows 64 位**
2. 将Microsoft Edge安装程序放在托管位置，例如本地文件共享 (\\server\share\MicrosoftEdgeEnterpriseX64.msi) 。 Surface Hub设备必须具有访问托管位置的权限。
3. 通过 MDM 提供程序使用[EnterpriseDesktopAppManagement](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) Configuration Service Provider (CSP) 安装Microsoft Edge。

## <a name="configure-microsoft-edge"></a>配置 Microsoft Edge

### <a name="default-microsoft-edge-policies-for-surface-hub"></a>默认Microsoft Edge策略Surface Hub

Microsoft Edge预配置以下策略设置，以提供针对 Surface Hub 的优化体验。
 
> [!TIP]
> 建议保留这些策略设置的默认值。
 

| 策略设置                                                                                                   | 推荐体验                                                                                                                                                                                                                                               | 默认值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 不要自动从数据库导入数据类型和Microsoft Edge 旧版。 这可以避免使用共享设置更改登录用户的配置文件，Surface Hub。                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允许Microsoft Edge进程即使在最后一个浏览器窗口关闭后也在后台继续运行，从而在会话期间更快地访问 Web 应用。                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 不允许用户在网站中创建新Microsoft Edge。 这简化了浏览和登录体验。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 仅允许一个用户登录Microsoft Edge。 这简化了浏览和登录体验                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | 使用户能够在 Sign-On (中) 单Microsoft Edge SSO Microsoft Edge。 当用户登录到网站Surface Hub，其凭据可以流向受支持的网站，而无需重新进行身份验证。  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 阻止非管理员用户在 Microsoft Edge 中安装新Microsoft Edge。 若要配置默认安装的扩展的列表，请使用 [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist)。 | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 隐藏首次运行体验和初始屏幕，通常在用户首次Microsoft Edge运行时显示。 由于Surface Hub是共享设备，因此简化了用户体验。                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 禁用 InPrivate 模式。 由于结束会话已清除浏览数据，这简化了浏览和登录体验。                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 显示Office 365选项卡页上的源体验。 当用户登录到网站Surface Hub，可快速访问其文件和Office 365。                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 当用户登录到 Surface Hub，将使用其组织帐户创建不可删除的配置文件。 这简化了单一Sign-On (SSO) 体验。                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | 禁止在Microsoft Edge。 Surface Hub不支持打印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 使Microsoft Edge用户能够主动验证登录用户Microsoft 服务。 这简化了单一Sign-On (SSO) 体验。                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自动将文件保存到"下载"文件夹，而不是询问用户在何处保存文件。 这简化了浏览体验。                                                                                                                             | 0                 |

> [!IMPORTANT]
>  (操作系统) 可部署渐进式 web Windows 10 协同版 PBA。  另请注意，Microsoft Edge策略设置[WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist)在 Surface Hub。 

### <a name="configure-microsoft-edge-policy-settings"></a>配置Microsoft Edge策略设置

使用[Microsoft Edge浏览器策略](https://docs.microsoft.com/deployedge/microsoft-edge-policies)在浏览器中配置Microsoft Edge。 可以使用以下方法应用这些策略：

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)、
- [你首选的移动设备 (MDM) 支持 ADMX Ingestion](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)的提供程序，或
- [在配置设计器中，使用 ADMX](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)Windows包。

 
### <a name="configure-microsoft-edge-updates"></a>配置Microsoft Edge更新

默认情况下，Microsoft Edge自动更新。 使用[Microsoft Edge 更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)配置 Microsoft Edge 更新。
请注意，Surface Hub不支持以下Microsoft Edge策略：

- **Allowsxs** – 在Surface Hub，Microsoft Edge Stable 渠道始终Microsoft Edge 旧版。
- **CreateDesktopShortcut** – Surface Hub桌面快捷方式。

> [!TIP]
>  Microsoft Edge 需要连接到 Internet 以支持其功能。 确保必要的 [域 URL](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) 添加到允许列表中，以确保通过防火墙和其他安全机制通信。

## <a name="related-links"></a>相关链接

- [Microsoft Edge 文档](https://docs.microsoft.com/microsoft-edge/)


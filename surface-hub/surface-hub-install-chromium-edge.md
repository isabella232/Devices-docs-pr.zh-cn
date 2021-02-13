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
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 2bc11fb18137ce21cba27368e0c12bbb9e73a4c2
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327306"
---
# 在 Surface Hub 上安装和配置新版 Microsoft Edge

Windows 10 Team 2020 Update 支持基于 Chromium (版本 85 及以上版本) 的新 Microsoft Edge 作为 Surface Hub 2S 和 Surface Hub (v1) 的推荐浏览器。 本文介绍如何使用以下三种方法之一安装浏览器：预配包、Microsoft Intune 或 MDM (第三方移动设备) 提供程序。

> [!IMPORTANT]
> 默认情况下，Surface Hub 设备预安装 Microsoft Edge 旧版 (版本 44) 。 安装 [2020 更新](surface-hub-2020-update.md)后，建议切换到新的 Microsoft Edge 浏览器;Microsoft [Edge 旧版](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) 支持将于 2021 年 3 月 9 日结束。

## 使用预配包安装 Microsoft Edge

1. 从电脑中，将 [Microsoft Edge 预配](https://aka.ms/HubEdge) 包 (MicrosoftEdgeInstaller.ppkg) U 盘的根文件夹。
2. 将 USB 驱动器插入 Surface Hub。
3. 在 Surface Hub 中，打开 **"设置** "，在出现提示时输入管理员凭据。
4. 导航到 **Surface Hub** > **设备管理**。 在**预配包**下，选择**添加或删除预配包**。
5. 选择**添加程序包**。
6. 选择 Microsoft Edge 预配包，然后选择"**添加"。**
7. 你将看到预配包应用更改的摘要。 选择**是的，添加它**。
8. 等待 Microsoft Edge 安装完成。 安装后，导航到 Surface Hub"开始"菜单以访问新的 Microsoft Edge。              

> [!NOTE]
> 如果有较新版本的 Microsoft Edge 可用，它将自动更新。
 
## 使用 Intune 安装 Microsoft Edge
 
> [!NOTE]
> Surface Hub 设备必须使用 Intune 注册和管理。 有关详细信息，请参阅使用[Microsoft Intune 管理 Surface Hub 2S。](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)
 

1. [下载 Microsoft Edge 安装程序](https://www.microsoft.com/edge/business/download)。
    - 使用 Stable 渠道版本**85 (中的当前) ** [](https://docs.microsoft.com/deployedge/microsoft-edge-channels)
    - 选择 **Windows 64 位**
2. [将 Microsoft Edge 安装程序作为业务线应用添加到 Microsoft Intune。](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
    - 如果选择使用 Microsoft Edge 更新来处理 Microsoft Edge 的自动更新，请务必配置"忽略 **应用版本** "设置" **应用信息"** 窗格。 将此设置切换为 **"是**"时，Microsoft Intune 不会强制执行 Surface Hub 设备上安装的应用版本。

## 使用第三方 MDM 提供程序安装 Microsoft Edge

1. [从 Microsoft 下载 Microsoft Edge 安装程序](https://www.microsoft.com/edge/business/download)。
    - 使用 Stable 渠道版本**85 (中的当前) ** [](https://docs.microsoft.com/deployedge/microsoft-edge-channels)
    - 选择 **Windows 64 位**
2. 将 Microsoft Edge 安装程序放在托管位置，例如本地文件共享 (\\server\share\MicrosoftEdgeEnterpriseX64.msi) 。 Surface Hub 设备必须具有访问托管位置的权限。
3. 通过 MDM 提供程序使用 [EnterpriseDesktopAppManagement ](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) (CSP) 安装 Microsoft Edge。

## 配置 Microsoft Edge

### Surface Hub 的默认 Microsoft Edge 策略

Microsoft Edge 预配置了以下策略设置，以提供 Surface Hub 的优化体验。
 
> [!TIP]
> 建议保留这些策略设置的默认值。
 

| 策略设置                                                                                                   | 推荐体验                                                                                                                                                                                                                                               | 默认值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 不要自动从旧版 Microsoft Edge 导入数据类型和设置。 这可避免使用 Surface Hub 中的共享设置更改已登录用户的配置文件。                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允许 Microsoft Edge 进程在关闭最后一个浏览器窗口后继续在后台运行，从而在会话期间更快地访问 Web 应用。                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 不允许用户在 Microsoft Edge 中创建新配置文件。 这简化了浏览和登录体验。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 仅允许一个用户登录到 Microsoft Edge。 这简化了浏览和登录体验                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | 使用户能够在 Microsoft Edge Sign-On (单一) SSO 服务。 当用户登录到 Surface Hub 时，其凭据可以流动到支持的网站，而无需重新进行身份验证。  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 阻止非管理员用户在 Microsoft Edge 中安装新扩展。 若要配置默认安装的扩展的列表，请使用[ExtensionInstallForcelist。](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist) | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 隐藏用户首次运行 Microsoft Edge 时通常显示的首次运行体验和初始屏幕。 由于 Surface Hub 是共享设备，因此可简化用户体验。                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 禁用 InPrivate 模式。 由于结束会话已清除浏览数据，因此这简化了浏览和登录体验。                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 显示新选项卡页上的 Office 365 源体验。 当用户登录到 Surface Hub 时，这将允许快速访问 Office 365 上的文件和内容。                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 当用户登录到 Surface Hub 时，将使用其组织帐户创建不可删除的配置文件。 这简化了单一Sign-On (SSO) 体验。                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | 禁止在 Microsoft Edge 中打印。 Surface Hub 不支持打印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 使 Microsoft Edge 能够主动使用 Microsoft 服务对登录用户进行身份验证。 这简化了单一Sign-On (SSO) 体验。                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自动将文件保存到"下载"文件夹，而不是询问用户在何处保存文件。 这简化了浏览体验。                                                                                                                             | 0                 |

> [!IMPORTANT]
> Windows 10 团队 (当前) 可部署渐进式 Web 应用) 使用 PWA。  另请注意，Surface Hub 不支持 Microsoft Edge 策略设置[WebAppInstallForceList。](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) 

### 配置 Microsoft Edge 策略设置

使用 [Microsoft Edge 浏览器策略](https://docs.microsoft.com/deployedge/microsoft-edge-policies) 在 Microsoft Edge 中配置浏览器设置。 可以使用以下方法应用这些策略：

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)，
- [支持 ADMX (MDM) ](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)首选移动设备管理提供程序，或者
- [在 Windows 配置设计器中使用 ADMX Ingestion 预配包](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)。

 
### 配置 Microsoft Edge 更新

默认情况下，Microsoft Edge 将自动更新。 使用 [Microsoft Edge 更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) 配置 Microsoft Edge 更新的设置。
请注意，Surface Hub 不支持以下 Microsoft Edge 更新策略：

- **Allowsxs** – 在 Surface Hub 上，Microsoft Edge Stable 渠道始终替换旧版 Microsoft Edge。
- **CreateDesktopShortcut** – Surface Hub 不使用桌面快捷方式。

> [!TIP]
>  Microsoft Edge 需要连接到 Internet 以支持其功能。 确保必要的 [域 URL](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) 已添加到允许列表中，以确保通过防火墙和其他安全机制通信。

## 相关链接

- [Microsoft Edge 文档](https://docs.microsoft.com/microsoft-edge/)


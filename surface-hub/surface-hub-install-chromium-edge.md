---
title: 在Microsoft Edge管理Surface Hub
description: 本文介绍用于Microsoft Edge浏览器设置的默认策略设置和工具。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 80e861fd575324db21be458f7b82cd5fdb538b50
ms.sourcegitcommit: 68b6e86919d6e29155bf9386d05279866e1157e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2021
ms.locfileid: "12100710"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>在Microsoft Edge管理Surface Hub

使用[Microsoft Edge浏览器](/deployedge/microsoft-edge-policies)策略，通过以下Microsoft Edge之一在浏览器中配置浏览器设置：

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [支持 ADMX (MDM) 首选移动设备管理提供程序](/deployedge/configure-edge-with-mdm)
- [在配置设计器中使用 ADMX Windows包](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> 从屏幕手势顶部向下轻扫以退出全屏模式需要使用两根手指和新的Microsoft Edge。 在长按触摸后显示的上下文菜单中也提供退出全屏操作。

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>默认Microsoft Edge策略Surface Hub

Microsoft Edge预配置以下策略设置，以提供针对 Surface Hub 的优化体验。


> [!TIP]
> 建议保留这些策略设置的默认值。

| 策略设置                                                                                                   | 推荐体验                                                                                                                                                                                                                                               | 默认值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 不要自动从数据库导入数据类型和Microsoft Edge 旧版。 这可以避免使用共享设置更改登录用户的配置文件Surface Hub。                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允许Microsoft Edge在关闭最后一个浏览器窗口后继续在后台运行，从而在会话期间更快地访问 Web 应用。                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 不允许用户在网站中创建新Microsoft Edge。 这简化了浏览和登录体验。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 仅允许一个用户登录Microsoft Edge。 这简化了浏览和登录体验                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | 使用户能够在 Microsoft Edge 中Sign-On (单一) SSO Microsoft Edge。 当用户登录到 Surface Hub时，其凭据可以流向受支持的网站，而无需重新进行身份验证。  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 阻止非管理员用户在 Microsoft Edge 中安装新Microsoft Edge。 若要配置默认安装的扩展的列表，请使用 [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist)。 | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 隐藏首次运行体验和初始屏幕，通常在用户首次Microsoft Edge运行时显示。 由于Surface Hub是共享设备，因此简化了用户体验。                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 禁用 InPrivate 模式。 由于结束会话已清除浏览数据，这简化了浏览和登录体验。                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 显示新Office 365页上的源体验。 当用户登录到网站时Surface Hub，可快速访问其文件和Office 365。                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 当用户登录到 Surface Hub，将使用其组织帐户创建不可删除的配置文件。 这简化了单一Sign-On (SSO) 体验。                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | 禁止在打印Microsoft Edge。 Surface Hub不支持打印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 允许Microsoft Edge登录用户主动进行身份验证Microsoft 服务。 这简化了单一Sign-On (SSO) 体验。                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自动将文件保存到"下载"文件夹，而不是询问用户在何处保存文件。 这简化了浏览体验。                                                                                                                             | 0                 |

> [!IMPORTANT]
>  (操作系统) 可部署渐进式 Web) PBA Windows 10 协同版支持。  另请注意，Microsoft Edge [WebAppInstallForceList](/deployedge/microsoft-edge-policies#webappinstallforcelist)的策略设置不受 Surface Hub。

### <a name="configure-microsoft-edge-updates"></a>配置Microsoft Edge更新

默认情况下，Microsoft Edge自动更新。 使用[Microsoft Edge 更新策略](/deployedge/microsoft-edge-update-policies)配置 Microsoft Edge 更新。 请注意，Surface Hub**不支持 CreateDesktopShortcut**策略设置，Surface Hub桌面快捷方式。

> [!TIP]
> Microsoft Edge 需要连接到 Internet 以支持其功能。 将 [必要的域 URL 添加到](/deployedge/microsoft-edge-security-endpoints) 允许列表中，以确保通过防火墙和其他安全机制通信。

## <a name="related-links"></a>相关链接

- [Microsoft Edge 文档](/microsoft-edge/)
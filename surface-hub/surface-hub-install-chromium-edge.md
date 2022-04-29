---
title: 在 Surface Hub 上管理 Microsoft Edge
description: 本文介绍用于配置浏览器设置的默认Microsoft Edge策略设置和工具。
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
ms.openlocfilehash: b652b990ce798d807ff2a27e87d212d01f3c23a2
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497725"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>在 Surface Hub 上管理 Microsoft Edge

使用[Microsoft Edge浏览器策略](/deployedge/microsoft-edge-policies)通过以下任一方法在Microsoft Edge中配置浏览器设置：

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [首选的移动设备管理 (MDM) 支持 ADMX 引入的提供商](/deployedge/configure-edge-with-mdm)
- [在 Windows配置设计器中使用 ADMX 引入预配包](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> 从屏幕手势顶部向下轻扫以退出全屏模式需要两根手指和新Microsoft Edge。 退出全屏操作在长时间按下触摸后显示的上下文菜单中也可用。

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Surface Hub的默认Microsoft Edge策略

Microsoft Edge预配置了以下策略设置，为Surface Hub提供优化体验。


> [!TIP]
> 建议保留这些策略设置的默认值。

| 策略设置                                                                                                   | 建议的体验                                                                                                                                                                                                                                               | 默认值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 不要自动从Microsoft Edge 旧版导入数据类型和设置。 这可避免使用Surface Hub中的共享设置更改已登录用户的配置文件。                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允许Microsoft Edge进程即使在最后一个浏览器窗口关闭后仍可在后台继续运行，从而在会话期间更快地访问 Web 应用。                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 不允许用户在Microsoft Edge中创建新配置文件。 这简化了浏览和登录体验。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 仅允许一个用户登录到Microsoft Edge。 这简化了浏览和登录体验                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | 使用户能够在Microsoft Edge中享受单Sign-On (SSO) 。 当用户登录到Surface Hub时，其凭据可以流向受支持的网站，而无需他们重新进行身份验证。  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 防止非管理员用户在Microsoft Edge中安装新扩展。 若要配置默认安装的扩展列表，请使用 [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist)。 | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 隐藏用户首次Microsoft Edge运行时通常显示的第一个运行体验和初始屏幕。 由于Surface Hub是共享设备，因此这简化了用户体验。                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 禁用 InPrivate 模式。 由于结束会话已清除浏览数据，这简化了浏览和登录体验。                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 在新选项卡页上显示Office 365源体验。 当用户登录到Surface Hub时，这可在Office 365上快速访问其文件和内容。                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 当用户登录到Surface Hub时，将使用其组织帐户创建不可移动配置文件。 这简化了单Sign-On (SSO) 体验。                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | 在Microsoft Edge中禁用打印。 Surface Hub不支持打印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 使Microsoft Edge能够使用Microsoft 服务主动对已登录用户进行身份验证。 这简化了单Sign-On (SSO) 体验。                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自动将文件保存到下载文件夹，而不是询问用户将文件保存到何处。 这简化了浏览体验。                                                                                                                             | 0                 |

> [!TIP]
> Windows 10 协同版操作系统现在支持可部署的渐进式 Web 应用 (PVA) 。 若要了解详细信息，请参阅[在Surface Hub上安装渐进式Web 应用](install-pwa-surface-hub.md)。 

### <a name="configure-microsoft-edge-updates"></a>配置Microsoft Edge更新

默认情况下，会自动更新Microsoft Edge。 使用[Microsoft Edge更新策略](/deployedge/microsoft-edge-update-policies)为Microsoft Edge 更新配置设置。 请注意，Surface Hub不支持 **CreateDesktopShortcut** 策略设置，因为Surface Hub不使用桌面快捷方式。

> [!TIP]
> Microsoft Edge 需要连接到 Internet 以支持其功能。 将 [必要的域 URL](/deployedge/microsoft-edge-security-endpoints) 添加到允许列表，以确保通过防火墙和其他安全机制进行通信。

## <a name="related-links"></a>相关链接

- [Microsoft Edge 文档](/microsoft-edge/)
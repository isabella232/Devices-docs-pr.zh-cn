---
title: 操作系统基本知识 (Surface Hub)
description: 本主题介绍操作系统的独特Windows 10 协同版及其与操作系统Windows 10 企业版。
keywords: 更改历史记录
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/23/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 54fe39fe35a63d27447fb0b4a01642f249475afc
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613811"
---
# <a name="operating-system-essentials-surface-hub"></a>操作系统基本知识 (Surface Hub)

Surface Hub 操作系统 Windows 10 协同版基于 Windows 10 企业版，提供了对企业管理、安全和其他功能的丰富支持。 但是，二者之间存在着重要差异。 企业版针对电脑设计，而 Windows 10 协同版针对大屏幕和会议室进行全新设计。 在评估 Surface Hub 的安全和管理要求时，最好将其视为新的操作系统。 本文旨在帮助突出显示 Surface Hub 上的 Windows 10 协同版和 Windows 10 企业版之间的关键差异，以及这些差异对你的组织的影响。

从 2020 年 9 月开始，客户可以选择在 Windows 10 专业版 2S Enterprise迁移Surface Hub迁移。 若要了解详细信息，请参阅以下内容：

- [宣布在 2 Windows 10 专业版 2 Enterprise发布Surface Hub计划](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107)。

- [迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版](surface-hub-2s-migrate-os.md)

## <a name="user-interface"></a>用户界面

### <a name="shell-os-user-interface"></a>Shell（操作系统用户界面）

Surface Hub 的 Shell 针对大屏幕进行了全新设计，并优化了触摸功能。 它不会使用与 Windows 10 企业版相同的 Shell。

*这可能影响的组织策略：* <br> 与 Windows 10 企业版 Shell 中的控件相关的设置不适用于 Surface Hub。

### <a name="lock-screen-and-screensaver"></a>锁屏界面和屏幕保护程序

Surface Hub 没有锁屏界面或屏幕保护程序，但它有一个类似功能（称为欢迎屏幕）。 欢迎屏幕显示设备帐户日历中的计划会议和访问 Surface Hub 常用应用（Skype for Business、白板和 Connect）的简单入口点。

*这可能影响的组织策略：* <br> 锁屏界面、屏幕超时和屏幕保护程序的设置不适用于 Surface Hub。

### <a name="user-sign-in"></a>用户登录

Surface Hub 设计用于公共场所，例如会议室。 与 Windows 电脑不同，任何人都可以访问和使用 Surface Hub，无需用户登录。 为了支持此社区功能，Surface Hub 不支持以与 Windows 10 企业版相同的方式进行 Windows 登录（如让用户登录到操作系统并使用操作系统中的这些凭据）。 相反，始终是本地、自动登录的低权限用户登录 Surface Hub。 它不支持登录任何其他用户，包括管理员用户（例如，当管理员登录时，他们不会登录到操作系统）。

用户可以登录到 Surface Hub，但他们无法登录到操作系统。 例如，当用户登录到“应用”或“我的会议和文件”时，他们只登录到应用或服务，而不是操作系统。 因此，登录用户可以检索其云文件和存储在云中的个人会议，并且这些凭据将会在**结束会话**激活时被丢弃。


*这可能影响的组织策略：* <br> 通常情况下，Surface Hub 使用锁定功能（而不是用户访问控制）以强制实施安全性。 与密码要求、交互式登录、用户帐户和访问控制相关的策略不适用于 Surface Hub。

### <a name="saving-and-browsing-files"></a>保存和浏览文件

用户有权访问 Surface Hub 上的一组受限目录：
- 音乐
- 视频
- 文档
- 图片
- 下载

当用户按下**结束会话**时，以本地方式保存在这些目录中的文件会删除。 若要保存在会议期间创建的内容，用户应将文件保存到 U 盘或 OneDrive。

*这可能影响的组织策略：* <br> 与访问权限和文件及文件夹的所有权相关的策略不适用于 Surface Hub。 用户不能浏览文件，也不能将文件保存到系统目录和网络文件夹。

## <a name="applications"></a>应用程序

### <a name="default-applications"></a>默认应用程序

除少数情况外，Surface Hub 上的默认通用 Windows 平台 (UWP) 应用也可用于 Windows 10 电脑。

在 Surface Hub 上预安装的 UWP 应用：

- 闹钟和时钟
- 计算器
- Connect
- Excel Mobile
- 反馈中心
- 文件资源管理器
- 入门
- 地图
- Microsoft Edge
- Microsoft Power BI
- Microsoft Teams
- Microsoft Whiteboard
- OneDrive
- 照片
- PowerPoint Mobile
- “设置”
- 应用商店
- 提示
- Word Mobile

*这可能影响的组织策略：* <br> 使用适用于 Windows 10 企业版的指南，确定 Surface Hub 上的默认应用的功能和网络要求。

### <a name="installing-apps-drivers-and-services"></a>安装应用、驱动程序和服务

若要帮助保留该设备的类似设备性质，Surface Hub 仅支持安装通用 Windows 平台 (UWP) 应用，不支持安装经典 Win32 应用、服务和驱动程序。 此外，只有管理员有权安装 UWP 应用。

*这可能影响的组织策略：* <br> 员工只能使用管理员已经安装的应用，这有助于缓解意外使用风险。 Surface Hub 不支持安装大多数传统电脑管理和监视工具所需的 Win32 代理。

## <a name="security-and-lockdown"></a>安全和锁定

要在公共场所（如会议室）使用的 Surface Hub 的自定义操作系统，可实现在 Windows 10 中提供的许多安全和锁定功能。

Surface Hub 可实现这些 Windows 10 安全功能：
- [UEFI 安全启动](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)
- [Windows Defender 应用程序控制和对代码完整性的基于虚拟化的保护](https://technet.microsoft.com/itpro/windows/keep-secure/introduction-to-device-guard-virtualization-based-security-and-code-integrity-policies)
- [使用 AppLocker 的应用程序限制策略](https://technet.microsoft.com/itpro/windows/keep-secure/applocker-overview)
- [BitLocker 驱动器加密](https://technet.microsoft.com/itpro/windows/keep-secure/bitlocker-overview)
- [受信任的平台模块 (TPM)](https://technet.microsoft.com/itpro/windows/keep-secure/trusted-platform-module-overview)
- [Microsoft Defender](https://technet.microsoft.com/itpro/windows/keep-secure/windows-defender-in-windows-10)
- 对“设置”应用的访问权限的[用户帐户控制 (UAC)](https://technet.microsoft.com/itpro/windows/keep-secure/user-account-control-overview)

这些 Surface Hub 功能提供额外安全：
- 自定义 UEFI 固件
- 自定义 Shell 和“开始”菜单限制设备使用会议功能
- 自定义文件资源管理器仅授予对“我的文档”下的文件和文件夹的访问权限
- 自定义设置应用仅允许管理员修改设备设置
- 下载高级即插即用驱动程序处于禁用状态

*这可能影响的组织策略：* <br> 在对 Surface Hub 执行安全评估时，考虑以下功能。

若要了解更多信息，请参阅[Surface Hub安全概述](surface-hub-security.md)

## <a name="management"></a>管理

### <a name="device-settings"></a>设备设置

设备设置可通过“设置”应用进行配置。 “设置”应用针对 Surface Hub 自定义，但还包含 Windows 10 桌面版中的许多熟悉设置。 当打开“设置”应用验证管理员凭据（但这不是登录管理员）时，将显示用户帐户控制 (UAC) 提示符。

*这可能影响的组织策略：* <br> 员工可以使用 Surface Hub 开展会议，但不能修改任何设备设置。 这可确保员工仅使用设备中的会议功能（锁定功能除外）。

### <a name="administrative-features"></a>管理功能

Windows 10 企业版中的管理功能（例如 Microsoft 管理控制台、运行、命令提示符、PowerShell、注册表编辑器、事件查看器和任务管理器）在 Surface Hub 上不受支持。 “设置”应用包含在 Surface Hub 上本地提供的所有管理功能。

### <a name="remote-management-and-monitoring"></a>远程管理和监视

Surface Hub通过移动设备管理支持远程管理 (MDM) 解决方案，例如Microsoft Intune [Azure Monitor](/azure/azure-monitor/)监视和[](/mem/intune/)监视。 

*这可能影响的组织策略：* <br> Surface Hub 不支持安装大多数传统电脑管理和监视工具（例如 System Center Operations Manager）所需的 Win32 代理。

### <a name="group-policy"></a>组策略

Surface Hub组策略Windows，包括审核。 改用 MDM 将策略应用到 Surface Hub。 有关 MDM 的详细信息，请参阅[使用 MDM 提供程序管理设置](manage-settings-with-mdm-for-surface-hub.md)。

*这可能影响的组织策略：* <br> 使用 MDM（而非组策略）管理 Surface Hub。

### <a name="remote-assistance"></a>远程协助

Surface Hub 不支持远程协助。

*这可能影响的组织策略：* <br> 与远程协助相关的策略不适用于 Surface Hub。

## <a name="network"></a>网络

### <a name="domain-join-and-azure-active-directory-azure-ad-join"></a>域加入和 Azure Active Directory (Azure AD) 加入 

Surface Hub 主要使用域加入和 Azure AD 加入提供目录备份的管理员组。 不支持混合加入。 用户不能使用域帐户登录。 有关详细信息，请参阅[管理员组管理](admin-group-management-for-surface-hub.md)。

*这可能影响的组织策略：* <br> Surface Hub 加入域时，不应用组策略。 与域成员身份相关的策略不适用于 Surface Hub。

### <a name="accessing-domain-resources"></a>访问域资源

用户可以登录到 Microsoft Edge，访问 Intranet 站点和联机资源（例如 Office 365）。 如果使用设备帐户配置 Surface Hub，系统将使用它访问 Exchange 和 Skype for Business。 但是，Surface Hub 不支持访问文件共享和打印机等域资源。

*这可能影响的组织策略：* <br> 与访问域对象相关的策略不适用于 Surface Hub。

<!--
### Endpoints



*Organization policies that this may affect:* <br> 
-->

### <a name="diagnostic-data"></a>诊断数据

Surface Hub 操作系统使用 Windows 10 的“已连接用户体验和遥测”组件收集和传输诊断数据。 有关详细信息，请参阅[在组织中配置 Windows 诊断数据](https://technet.microsoft.com/itpro/windows/manage/configure-windows-diagnostic-data-in-your-organization)。

*这可能影响的组织策略：* <br> 为 Surface Hub 配置诊断数据级别的方式与为 Windows 10 企业版配置相同。

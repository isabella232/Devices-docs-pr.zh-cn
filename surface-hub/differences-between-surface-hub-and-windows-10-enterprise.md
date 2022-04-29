---
title: 操作系统基本知识 (Surface Hub)
description: 本主题介绍Surface Hub上Windows团队操作系统的独特方面，以及它与Windows 10或Windows 11 企业版有何不同。
keywords: 更改历史记录
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/15/2022
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 5be9c0ba3f23832d2e3d9b66a746e9f1f0772e63
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497335"
---
# <a name="operating-system-essentials-surface-hub"></a>操作系统基本知识 (Surface Hub)

Surface Hub操作系统Windows 10 协同版源于Windows 10 企业版，为企业管理、安全和其他功能提供了丰富的支持。 但是，二者之间存在着重要差异。 企业版针对电脑设计，而 Windows 10 协同版针对大屏幕和会议室进行全新设计。 评估Surface Hub的安全和管理要求时，建议将其视为新的操作系统。 本文重点介绍了Windows 10 协同版Surface Hub版本与企业版Windows 10或Windows 11的主要区别。

## <a name="convert-surface-hub-to-run-pro-or-enterprise-desktop"></a>将Surface Hub转换为运行Pro或Enterprise桌面

可以通过迁移到Windows 10或Windows 11 专业版/Enterprise来更改 Surface Hub 2S 上的 OS。 若要了解详细信息，请参阅以下内容：

- [宣布在Surface Hub 2 上提供Windows 10 专业版和Enterprise](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107)。

- [在 Surface Hub 2 上迁移到Windows 10、Windows 11 专业版或Enterprise](surface-hub-2s-migrate-os.md)

## <a name="user-interface"></a>用户界面

### <a name="shell-os-user-interface"></a>Shell（操作系统用户界面）

Surface Hub 的 Shell 针对大屏幕进行了全新设计，并优化了触摸功能。 它不使用与Windows 10或Windows 11 企业版相同的 shell。

*这可能影响的组织策略：* 

- 与 Windows 10 或 Windows 11 企业版 shell 中的控件相关的设置不适用于Surface Hub。

### <a name="lock-screen-and-screensaver"></a>锁屏界面和屏幕保护程序

Surface Hub 没有锁屏界面或屏幕保护程序，但它有一个类似功能（称为欢迎屏幕）。 欢迎屏幕显示设备帐户日历中的计划会议和访问 Surface Hub 常用应用（Skype for Business、白板和 Connect）的简单入口点。

*这可能影响的组织策略：* 

- 锁屏界面、屏幕超时和屏幕保护程序的设置不适用于 Surface Hub。

### <a name="user-sign-in"></a>用户登录

Surface Hub 设计用于公共场所，例如会议室。 与 Windows 电脑不同，任何人都可以访问和使用 Surface Hub，无需用户登录。 若要启用此公共功能，Surface Hub不支持Windows登录，就像Windows 10或Windows 11 企业版 (一样，例如，在整个 OS) 中登录用户和使用这些凭据。 相反，始终是本地、自动登录的低权限用户登录 Surface Hub。 它不支持登录任何其他用户，包括管理员用户（例如，当管理员登录时，他们不会登录到操作系统）。

用户可以登录到 Surface Hub，但他们无法登录到操作系统。 例如，当用户登录到“应用”或“我的会议和文件”时，他们只登录到应用或服务，而不是操作系统。 因此，登录用户可以检索其云文件和存储在云中的个人会议，并且这些凭据将会在**结束会话**激活时被丢弃。

*这可能影响的组织策略：* 

- 通常情况下，Surface Hub 使用锁定功能（而不是用户访问控制）以强制实施安全性。 与密码要求、交互式登录、用户帐户和访问控制相关的策略不适用于 Surface Hub。

### <a name="saving-and-browsing-files"></a>保存和浏览文件

用户有权访问 Surface Hub 上的一组受限目录：
- 音乐
- 视频
- 文档
- 图片
- 下载

当用户按下**结束会话**时，以本地方式保存在这些目录中的文件会删除。 若要保存在会议期间创建的内容，用户应将文件保存到 U 盘或 OneDrive。

*可能会影响的组织策略：* - 与文件和文件夹的访问权限和所有权相关的策略不适用于Surface Hub。 用户不能浏览文件，也不能将文件保存到系统目录和网络文件夹。

## <a name="applications"></a>应用程序

### <a name="default-applications"></a>默认应用程序

除了少数例外情况，Surface Hub上的默认通用 Windows 平台 (UWP) 应用也可用于Windows 10或Windows 11电脑。

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

*这可能影响的组织策略：* 

- 使用Windows 10或Windows 11 企业版指南确定Surface Hub上默认应用的功能和网络要求。

### <a name="installing-apps-drivers-and-services"></a>安装应用、驱动程序和服务

若要帮助保留该设备的类似设备性质，Surface Hub 仅支持安装通用 Windows 平台 (UWP) 应用，不支持安装经典 Win32 应用、服务和驱动程序。 此外，只有管理员有权安装 UWP 应用。

*这可能影响的组织策略：* 

- 员工只能使用管理员已经安装的应用，这有助于缓解意外使用风险。 Surface Hub 不支持安装大多数传统电脑管理和监视工具所需的 Win32 代理。

## <a name="security-and-lockdown"></a>安全和锁定

若要在会议室等公共空间中使用Surface Hub，其自定义 OS 可实现Windows 10或Windows 11中提供的许多安全和锁定功能。 若要了解详细信息，请参阅[Surface Hub安全概述](surface-hub-security.md)

Surface Hub实现以下Windows安全功能：

- [安全启动](/windows-hardware/design/device-experiences/oem-secure-boot)
- [Windows Defender 应用程序控制和基于虚拟化的代码完整性保护](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [使用 AppLocker 的应用程序限制策略](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)
- [BitLocker 驱动器加密](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [受信任的平台模块 (TPM)](/windows/security/information-protection/tpm/trusted-platform-module-top-node)
- [Windows中的Microsoft Defender 防病毒](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)
- 对“设置”应用的访问权限的[用户帐户控制 (UAC)](/windows/security/identity-protection/user-account-control/user-account-control-overview)

这些 Surface Hub 功能提供额外安全：

- 自定义 UEFI 固件
- 自定义 Shell 和“开始”菜单限制设备使用会议功能
- 自定义文件资源管理器仅授予对“我的文档”下的文件和文件夹的访问权限
- 自定义设置应用仅允许管理员修改设备设置
- 下载高级即插即用驱动程序处于禁用状态

*这可能影响的组织策略：*

- 在对 Surface Hub 执行安全评估时，考虑以下功能。

## <a name="management"></a>管理

### <a name="device-settings"></a>设备设置

设备设置可通过“设置”应用进行配置。 设置应用是为Surface Hub自定义的，但也包含许多熟悉的设置，从Windows 10或Windows 11桌面。 当打开“设置”应用验证管理员凭据（但这不是登录管理员）时，将显示用户帐户控制 (UAC) 提示符。

*这可能影响的组织策略：* 

- 员工可以使用 Surface Hub 开展会议，但不能修改任何设备设置。 这可确保员工仅使用设备中的会议功能（锁定功能除外）。

### <a name="administrative-features"></a>管理功能

Surface Hub不支持Windows 10或Windows 11 企业版中的管理功能，例如 Microsoft 管理控制台、运行、命令提示符、PowerShell、注册表编辑器和任务管理器。 “设置”应用包含在 Surface Hub 上本地提供的所有管理功能。

#### <a name="event-viewer"></a>事件查看器

Windows 10 协同版 2020 Update 2 添加了对Windows 事件查看器的支持，这与Windows 10 专业版或[Windows 10 企业版](/host-integration-server/core/windows-event-viewer1)上安装的事件查看器相同。 

**若要打开事件查看器，请执行下列操作：**

1. 使用管理员凭据登录到**设置**应用。
2. 选择 **“更新”&** **SecurityLogs** > ，然后在事件查看器下选择 **“打开**”。 

若要了解详细信息，请参阅[Windows 事件查看器](/host-integration-server/core/windows-event-viewer1)。

### <a name="remote-management-and-monitoring"></a>远程管理和监视

Surface Hub支持通过移动设备管理 (MDM) 解决方案（如通过 [Azure Monitor](/azure/azure-monitor/) [进行Microsoft Intune](/mem/intune/)和监视）进行远程管理。 

*这可能影响的组织策略：* 

- Surface Hub 不支持安装大多数传统电脑管理和监视工具（例如 System Center Operations Manager）所需的 Win32 代理。

### <a name="group-policy"></a>组策略

Surface Hub不支持Windows 组策略，包括审核。 改用 MDM 将策略应用到 Surface Hub。 有关 MDM 的详细信息，请参阅[使用 MDM 提供程序管理设置](manage-settings-with-mdm-for-surface-hub.md)。

*这可能影响的组织策略：* 

- 使用 MDM（而非组策略）管理 Surface Hub。

### <a name="remote-assistance"></a>远程协助

Surface Hub 不支持远程协助。

*这可能影响的组织策略：* 

- 与远程协助相关的策略不适用于 Surface Hub。

## <a name="network"></a>网络

### <a name="domain-join-and-azure-active-directory-azure-ad-join"></a>域加入和 Azure Active Directory (Azure AD) 加入 

Surface Hub 主要使用域加入和 Azure AD 加入提供目录备份的管理员组。 不支持混合联接。 用户不能使用域帐户登录。 有关详细信息，请参阅[管理员组管理](admin-group-management-for-surface-hub.md)。

*这可能影响的组织策略：* 

- 将Surface Hub加入域时，不会应用组策略设置。 与域成员身份相关的策略设置不适用于Surface Hub。

### <a name="accessing-domain-resources"></a>访问域资源

用户可以登录到 Microsoft Edge，访问 Intranet 站点和联机资源（例如 Office 365）。 如果使用设备帐户配置 Surface Hub，系统将使用它访问 Exchange 和 Skype for Business。 但是，Surface Hub 不支持访问文件共享和打印机等域资源。

*这可能影响的组织策略：* 

- 与访问域对象相关的策略不适用于 Surface Hub。

### <a name="diagnostic-data"></a>诊断数据

Surface Hub OS 使用Windows连接的用户体验和遥测组件来收集和传输诊断数据。 有关详细信息，请参阅[在组织中配置 Windows 诊断数据](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)。

*这可能影响的组织策略：* 

- 为Surface Hub配置诊断数据级别的方式与为Windows 10或Windows 11 企业版配置诊断数据级别的方式相同。

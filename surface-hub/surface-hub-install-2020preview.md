---
title: 安装 Windows 10 Team 2020 Update Preview 内部版本
description: 目前提供了 Surface Hub 操作系统、Windows 10 团队2020更新的最新更新。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894108"
---
# 安装 Windows 10 Team 2020 Update Preview 内部版本 

目前，Surface hub 操作系统、 **windows 10 Team 2020 更新**的最新更新现在可通过[Windows 预览体验计划](https://insider.windows.com)中的 surface Hub 50 英寸和 surface Hub 2 55 英寸设备免费获得额外费用。 Windows 10 Team 2020 更新的最终版本中将支持 Surface Hub 84 英寸模型。

Windows 10 Team 2020 更新通过最新的 Windows 10 功能提升了设备部署和可管理性的主要改进。 若要了解有关新增功能的详细信息，请参阅以下博客文章：已[发布用于公共预览版的新 Surface HUB 操作系统更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) 对于已知问题，请参阅下面的 "已知问题" 部分。
 
## 必备条件

- 注册到[Windows 预览体验计划](https://insider.windows.com/)。
- 从 Windows 预览体验计划快速频道下载 Windows 10 Team 2020 更新预览版。
- 安装预览版本后，下载所需的固件更新。 注意：即使你决定离开 Windows 预览体验计划，也无法卸载固件更新。

## 准备 Surface Hub

开始之前，请检查 Surface Hub 是否具有来自 Windows 更新的最新更新，并确保保存与设备关联的 BitLocker 密钥。

**若要手动检查更新，请执行以下操作：**

1. 在 Surface Hub 上，打开 "**设置**"，然后在出现提示时输入您的管理员凭据。
2. 导航到 "**更新安全**  >  **Windows 更新**&"，然后选择 "**检查更新**"。

有关详细信息，请参阅[管理 Surface Hub 上的 Windows 更新](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)。

**要手动保存 BitLocker 密钥，请执行以下操作：**

1. 将 USB 驱动器插入 Surface Hub。
2. 在 Surface Hub 上，打开 "**设置**"，然后在出现提示时输入您的管理员凭据。
3. 导航到 "**更新 & 安全**  >  **恢复**"。
4. 在 " **BitLocker**" 下，选择 "**保存**"。 将 BitLocker 密钥保存到 USB 驱动器上的文本文件中。

有关详细信息，请参阅[保存 BitLocker 密钥](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)。
 
## 安装 Windows 10 Team 2020 Update Preview 内部版本

1. 在 Surface Hub 上，打开 "**设置**"，然后在出现提示时输入您的管理员凭据。
2. 导航到 "**更新**  >  **Windows 预览体验计划**" & 的 "更新"，然后选择 "**开始**"。
3. 按照提示，使用你的工作帐户（推荐）或你的个人 Microsoft 帐户注册为 Windows 预览体验成员。 有关向工作帐户注册的好处的详细信息，请参阅[注册 Windows 预览体验计划 For Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)。
4. 在 "**选择预览体验成员设置**" 下，选择 "**快速**"。
5. 允许 Surface Hub 在接下来的3到4天内自动安装预览构建和所需的固件更新。 设备将在日常[维护窗口](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)中自动下载并安装更新。 例如：

- 在第一个维护窗口中，Surface Hub 从 "Windows 更新" 开始下载预览版本。
- 在第二个维护窗口中，设备将重新启动以完成更新。
- 在第三个维护窗口中，设备将下载并安装所需的固件更新。

> [!IMPORTANT]
> Microsoft 建议为3-4 天保留 Surface Hub，以允许设备完成预览版和所需固件更新的安装。 如果在此过程中使用设备，你可能会遇到图形、音频和用户界面问题。

### 如果你选择手动安装预览版和必需的固件更新：

1. 注册到 Windows 预览体验计划后，请转到 "**设置**  >  **更新 & 安全**  >  **Windows 更新**"，然后选择 "**检查更新**" 以安装预览版本。
2. 预览生成安装（可能需要长达14小时），请选择 "**立即重启**" 以完成安装。
3. 重新启动设备后，转到 "**设置**  >  "**更新 "& 安全**  >  **Windows 更新**"，然后选择 "**检查更新" 以安装所需的固件更新**。
4. 固件安装后，选择 "**立即重启**"。

> [!WARNING]
> 如果在未安装所需固件更新的情况下安装预览内部版本，则可能会看到图形、音频和用户界面问题。

> [!NOTE]
> 如果你选择退出 Windows 预览体验计划并将 Surface Hub 还原到较早版本的操作系统，则必须首先[重置你的设备](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)。 之后，你需要转到[第一个 run 程序](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub)来重新配置你的设备。
 
## 已知问题： Windows 10 Team 2020 更新预览版

### 图形、音频和用户界面问题 

如果安装了预览版，则可能会遇到各种图形和用户界面问题，但以后不会立即安装所需的固件更新。 Microsoft 计划在 Windows 10 Team 2020 更新的版本内部版本中修复这些问题。

### Surface Hub 84-英寸：图形和用户界面问题

如果在第一代 Surface Hub 84 英寸设备上安装预览版，则可能会遇到各种图形和用户界面问题。 Windows 10 Team 2020 更新的最终版本中将支持 Surface Hub 84 英寸。

### 应用条件访问策略时，登录会受到影响

- 尝试登录应用（如 Microsoft 白板）时，登录失败。 用户必须先从 "开始" 菜单中的["我的会议" 和 "文件](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)" 登录。

- 如果你的用户帐户注册到不同于 Surface Hub 使用的 Azure ad 加入的 Azure AD 租户，登录失败。

Microsoft 计划在 Windows 10 Team 2020 更新的版本内部版本中修复这些问题。

### Windows 更新提示安装没有可用的新驱动程序

转到 "**设置**  >  "**更新时 & 安全**  >  **windows 更新**安装了 windows 10 Team 2020 更新以及所需的固件更新后，可能会看到以下错误： 

- "电脑上的当前驱动程序可能比我们尝试安装的驱动程序更好。 我们将继续尝试安装。 " 

可以安全地忽略此错误。 Microsoft 正在积极调查此问题。

### 无法使用预配程序包安装 Surface Hub 策略

预配使用 Surface Hub 配置服务提供商（CSP）中的策略的程序包安装失败。 现在，请使用 Microsoft Intune 或其他移动设备管理（MDM）提供程序应用 Surface Hub 策略。 Microsoft 计划在 Windows 10 Team 2020 更新的版本内部版本中修复此问题。

### 首次运行时，系统提示提前删除 USB 驱动器

在首次运行时使用预配包安装 Surface Hub 时，系统会提示你删除 USB 驱动器，然后设备才能读取 Surface Hub 配置文件。 如果您使用配置文件设置您的设备帐户，请忽略该消息。 Microsoft 正在积极调查此问题。
 
### 无法在首次运行时设置代理设置

如果你使用代理连接到 Internet，则你的首次运行程序中可能具有有限的 Internet 连接。 Microsoft 计划在 Windows 10 Team 2020 更新的版本内部版本中修复此问题。
 
### 从 Microsoft Store 下载应用时出现错误

若要从 Microsoft Store 下载应用，您将看到登录提示。 已知问题导致在登录期间出现错误，但这不会影响你下载应用的能力。 Microsoft 正在积极调查此问题。

### Surface Hub 2 间歇性地失去 Wlan 连接

尝试拔出设备并将其重新插入，或使用以太网电缆连接到 Internet。 Microsoft 正在积极调查此问题。

### Surface Hub 2 间歇性无法从睡眠状态恢复

Surface Hub 2 可能间歇性地无法从睡眠中完全恢复，并且在显示 Microsoft 徽标的屏幕上看起来停止响应。 请尝试拨出设备，然后再将其插入。 

若要防止此问题：

1. 在 Surface Hub 上，打开 "**设置**"，然后在出现提示时输入您的管理员凭据。
2. 导航到**Surface Hub**  >  **会话 & "电源**"。 
3. 在 **"当设备进入睡眠状态时" 下，使用此电源设置**，选择 "**已连接待机"。**
4. 在 "**无人出现时，将设备置于睡眠状态**" 下，选择 "**从不"。**

Microsoft 计划在 Windows 10 Team 2020 更新的最终版本之前修复固件更新中的此问题。

### 当 Connect 应用不在视图中时的投影问题

- 使用电缆投影到 Surface Hub 时，如果你离开 Connect 应用，touchback 将停止工作。
- 使用 Miracast 投影到 Surface Hub 时，无线连接会在你离开连接应用后立即断开。

Microsoft 正在积极调查这些问题。

### Skype for Business 未使用用于媒体流量的代理

对于使用代理的某些设备，Skype for Business 可以登录，但不会将代理服务器用于媒体流量。 Microsoft 正在积极调查此问题。

我们邀请您与 Microsoft 支持部门分享您的见解和建议。

## 了解详细信息

- [已发布用于公共预览版的新 Surface Hub 操作系统更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Windows 预览体验计划企业版入门](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)
---
title: 安装 Windows 10 协同版 2020 更新预览版
description: 目前提供了 Surface Hub 操作系统、Windows 10 团队2020更新的最新更新。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 79e6c35deba5c4635945c3b376a1069e3df324d9
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918912"
---
# 安装 Windows 10 协同版 2020 更新预览版 

目前，Surface hub 操作系统、 **windows 10 Team 2020 更新**的最新更新现在可通过[Windows 预览体验计划](https://insider.windows.com)中的 surface Hub 50 英寸和 surface Hub 2 55 英寸设备免费获得额外费用。 Windows 10 Team 2020 更新的最终版本中将支持 Surface Hub 84 英寸模型。

Windows 10 Team 2020 更新通过最新的 Windows 10 功能提升了设备部署和可管理性的主要改进。 若要了解有关新增功能的详细信息，请参阅以下博客文章：已[发布用于公共预览版的新 Surface HUB 操作系统更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) 对于已知问题，请参阅下面的 "已知问题" 部分。
 
## 先决条件

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
2. 导航到**隐私 > 诊断 & 反馈**和**完整**的诊断数据。 
3. 导航到 "**更新**  >  **Windows 预览体验计划**" & 的 "更新"，然后选择 "**开始**"。
4. 按照提示，使用你的工作帐户注册到 Windows 预览体验 () 或你的个人 Microsoft 帐户。 有关向工作帐户注册的好处的详细信息，请参阅[注册 Windows 预览体验计划 For Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)。
5. 在 "**选择预览体验成员设置**" 下，选择 "**快速**"。
6. 允许 Surface Hub 在接下来的3到4天内自动安装预览构建和所需的固件更新。 设备将在日常[维护窗口](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)中自动下载并安装更新。 例如：

- 在第一个维护窗口中，Surface Hub 从 "Windows 更新" 开始下载预览版本。
- 在第二个维护窗口中，设备将重新启动以完成更新。
- 在第三个维护窗口中，设备将下载并安装所需的固件更新。

> [!IMPORTANT]
> Microsoft 建议为3-4 天保留 Surface Hub，以允许设备完成预览版和所需固件更新的安装。 如果在此过程中使用设备，你可能会遇到图形、音频和用户界面问题。

### 如果你选择手动安装预览版和必需的固件更新：

1. 注册到 Windows 预览体验计划后，请转到 "**设置**  >  **更新 & 安全**  >  **Windows 更新**"，然后选择 "**检查更新**" 以安装预览版本。
2. 一旦预览生成安装 (可能需要长达14小时) ，请选择 "**立即重启**" 以完成安装。
3. 重新启动设备后，转到 "**设置**  >  "**更新 "& 安全**  >  **Windows 更新**"，然后选择 "**检查更新" 以安装所需的固件更新**。
4. 固件安装后，选择 "**立即重启**"。

> [!WARNING]
> 如果在未安装所需固件更新的情况下安装预览内部版本，则可能会看到图形、音频和用户界面问题。

> [!NOTE]
> 如果你选择退出 Windows 预览体验计划并将 Surface Hub 还原到较早版本的操作系统，则必须首先[重置你的设备](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)。 之后，你需要转到[第一个 run 程序](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub)来重新配置你的设备。
 

## 了解详细信息

- [已知问题： Windows 10 Team 2020 更新](surface-hub-2020-team-update-known-issues.md)
- [已发布用于公共预览版的新 Surface Hub 操作系统更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Windows 预览体验计划企业版入门](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)
---
title: 已知问题：Surface Hub
description: 此页提供 Surface Hub 的已知问题列表
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/09/2021
ms.localizationpriority: Medium
ms.openlocfilehash: a9435db1de48b33d062d5e79d0d622f1d17815f0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497482"
---
# <a name="known-issues-surface-hub"></a>已知问题：Surface Hub

本文列出了运行当前操作系统的 Surface Hub 的已知问题，Windows 10 协同版 2020 年更新。

若要确保Surface Hub接收最新更新，请使用管理员帐户登录，然后选择 **“所有应用** > **设置** > **更新和安全** > **性Windows 更新**，然后安装所有更新。

| 问题               | 描述           | 补救方法                 |
|---------------------|-----------------------|------------------------|
| 在Surface Hub设备上使用 Whiteboard 应用程序时，无法通过电子邮件共享内容。 | “Easy Share”功能已从 Whiteboard 应用的新版本中删除。 | 保存 Whiteboard 内容的建议方法是登录到应用。 如果无法登录，则图像文件可以保存到本地存储，然后通过 Edge 浏览器通过用户首选服务共享。 “Easy Share”功能将在 Whiteboard 的未来版本中返回。 [详细了解 Whiteboard 共享方案。](https://support.microsoft.com/office/enable-microsoft-whiteboard-for-your-organization-1caaa2e2-5c18-4bdf-b878-2d98f1da4b24) |
| 当用户选择“结束会话”时，某些 Surface Hub 正在重启。  | 当Surface Hub设备用户选择“结束会话”功能以清除用户数据时，Surface Hub设备可能会错误地检测到清理失败，从而强制重启Windows以确保成功进行清理。  | Microsoft 已了解并正在积极调查此问题。  Microsoft 将尽快提供有关解决方法的其他信息。|
| 在高GCC环境中使用 Surface Hub 时，欢迎屏幕日历中的一键式会议加入不起作用。 | 在GCC高环境下单击Teams会议的Surface Hub日历中的“加入”不会自动启动会议。 | 若要加入会议，请启动Teams，然后从Teams客户端显示的议程中加入会议。 <br></br>Microsoft 也在积极调查此问题，并将尽快提供有关解决方法的其他信息。 |
| 服务质量 (QoS) 设置无法按预期工作 | 通过 MDM 策略或预配包配置 QoS 设置后，DSCP 标记不会应用于Teams或Skype for Business (SfB) 媒体流量。 | Microsoft 已了解并正在积极调查此问题。  Microsoft 将尽快提供有关解决方法的其他信息。 |
| 使用本地邮箱的混合设备帐户的日历同步失败。 | Surface Hub设备默认为对Azure AD中存在的帐户使用新式身份验证，即使它们在本地环境中有未启用[混合新式身份验证](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication)的邮箱。 在此方案中，Exchange停止将会议同步到设备。 因此，设备不会接收或显示新的会议。 | [安装 KB4598291](https://support.microsoft.com/help/4598291) (或后续Windows CU) 后，[SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp) 具有新的 ExchangeModernAuthEnabled 参数，可用于切换新式身份验证的使用。 这可以通过 MDM 策略或 [预配包](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/ExchangeModernAuthDisabled.ppkg) 设置为 false，以防止中心使用新式身份验证。 |
| 一小部分 v1 Surface Hub设备无法自动升级到 Windows 10 协同版 2020 更新。 | 这一小部分 v1 Surface Hub设备处于阻止通过Windows 更新直接升级兼容的状态。 | [使用 Surface Hub 恢复工具](surface-hub-recovery-tool.md)将设备手动重新映像到 Windows 10 协同版 2020 更新。 |
| Surface Hub尝试安装 Windows 10 协同版 2020 更新后显示“没有可启动的设备”消息。 | 在 Windows 10 协同版 2020 的Windows 更新过程中，某些中心 v1 设备将进入无法启动的状态。 | [使用 Surface Hub 恢复工具](surface-hub-recovery-tool.md)将设备手动重新映像到 Windows 10 协同版 2020 更新。 |
| 中心 2S 设备无法使用 WSUS 接收驱动程序更新。 | Surface Hub 2S 支持业务Windows 更新和Windows 更新来分发驱动程序;不支持通过 Windows Server Update Services (WSUS) 进行分发。 | 如果使用 WSUS，请迁移到 Windows 更新 for Business。<br> <br>**了解详细信息**：[业务Windows更新是什么？](/windows/deployment/update/waas-manage-updates-wufb) |
| 操作中心有一个不可点击的设置链接。 | 此链接不应出现在Windows 10 协同版中，并可能导致混淆。 | 该功能与 2020 年更新之前相同;"开始"菜单的“应用”部分应用于启动设置应用。  |
| 会话结束后会保留一些易于访问的设置| 当用户打开“快速操作”菜单或设置应用中的“高对比度”切换时，此切换会在用户会话结束后保留。 同样，如果用户将通知显示更改为指示 7 秒与管理员定义的 5 秒，则仍保留 7 秒，即使其他设置重置为管理员定义的值。 | 在中心启动会话后不久，用户可以从快速操作关闭高对比度切换 (在任务栏上可访问的) 菜单。 下一个用户可以通过设置应用将通知的显示持续时间设置为不同的值 - 所有用户都可以访问此设置。 Microsoft 正积极寻求解决此问题的方法。| 

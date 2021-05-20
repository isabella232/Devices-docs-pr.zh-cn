---
title: 已知问题：Surface Hub
description: 此页面提供 Surface Hub 的已知问题列表
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
ms.openlocfilehash: 172495530c4799ea59bf218dc1411bb4b230eef2
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576892"
---
# <a name="known-issues-surface-hub"></a>已知问题：Surface Hub

本文列出了运行当前操作系统的 Surface Hub 的已知问题，Windows 10 协同版 2020 更新。

若要确保Surface Hub最新更新，请通过管理员帐户登录并选择"所有应用**** 设置 更新和安全 Windows 更新"，然后安装  >  ****  >  ****  >  **** 所有更新。




| 问题                                                                                                   | 描述                                                                                                                                                                                                                                                                                                                                                                                                                             | 补救方法                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 在设备上使用白板Surface Hub时，无法通过电子邮件共享内容。             | 当通过白板导出流以电子邮件方式发送白板应用程序的内容时，Surface Hub设备当前显示"你的设备未设置电子邮件"。  因此，无法通过电子邮件共享白板内容。                                                                                                                                                                                                                   | Microsoft 已注意到并正在积极调查此问题。  Microsoft 将尽快提供有关解决方案的其他信息。                                                                                                                                                                                                                                                                                                                                                                   |
| 某些 Surface Hub 遇到其 Azure Log Analytics (以前称为 OMS) 连接问题。                                                                        | 对于受影响的Surface Hub，在使用 Azure Monitor 时，不会向工作区报告任何数据。                                                                                                                                                                                                                                      | Microsoft 已注意到并正在积极调查此问题。  Microsoft 将尽快提供有关解决方案的其他信息。                                                                                                                                                                                                                                                                                                                                                                   |
| v1 Surface Hub的一小部分设备无法自动升级到 Windows 10 协同版 2020 更新。                                            | v1 Surface Hub的这一小部分设备的状态阻止通过 Windows 更新与直接升级兼容。                                                                                                                                          | 使用 Surface Hub 工具将设备手动重新映像到 Windows 10 协同版 2020[更新](surface-hub-recovery-tool.md)。                                                                                                                                                                                 |
| Surface Hub 2020 更新后，系统会显示"Windows 10 协同版设备"消息。                                                                        | 在 Windows 2020 Windows 10 协同版更新过程中，某些 Hub v1 设备将进入不可启动的状态。                                                                                                                                                                                                                                       | 使用 Surface Hub 工具将设备手动重新映像到 Windows 10 协同版 2020[更新](surface-hub-recovery-tool.md)。                                                                                                                                                          |
| 混合设备帐户与本地邮箱的日历同步失败。   | Surface Hub设备默认对 Azure AD 中的帐户使用新式验证，即使它们具有无法与此功能一起使用本地邮箱。 在此方案中，Exchange停止将会议同步到设备。 因此，设备不会接收或显示新会议。                                                                                                    | 在[安装 KB4598291](https://support.microsoft.com/help/4598291) (或后续 Windows CU) 后[，SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)具有新的 ExchangeModernAuthEnabled 参数，可用于切换新式验证的使用。 这可以通过 MDM 策略或预配包设置为[](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/ExchangeModernAuthDisabled.ppkg)false，以防止中心使用新式验证。                                                                                                |
| 中心 2S 设备无法使用 WSUS 接收驱动程序更新。                                             | Surface Hub 2S 支持Windows更新Windows更新来分发驱动程序;不支持通过 Windows Server Update Services (WSUS) 分发。                                                                                                                                                                                                                                                                      | 如果使用 WSUS，请迁移到 Windows Update for Business。<br> <br>**了解更多信息**[：什么是Windows更新？](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)                                                                                                                                                                                                                                                                                                                            |
| 使用 Edge 旧版浏览器时，无法通过电子邮件共享旧版浏览器 Web 笔记。 | 创建 Web 笔记并浏览共享流以通过电子邮件发送便笺后，不显示"发送"按钮。 因此，无法通过电子邮件共享便笺。 | 已安装 2020 更新的 Surface Hub 可以升级到新的 Microsoft Edge 浏览器，并且通过电子邮件共享笔记适用于该浏览器。<br> <br>**了解更多信息**[：在 Microsoft Edge 安装Surface Hub](surface-hub-install-chromium-edge.md) |
| 操作中心具有一个不可设置链接。 | 此链接不应显示在Windows 10 协同版中，并可能导致混淆。   | 该功能与 2020 更新之前相同;"开始"菜单的"应用"部分应该用于启动设置应用。    |

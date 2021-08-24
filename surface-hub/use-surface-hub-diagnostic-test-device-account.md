---
title: 使用 Surface Hub 硬件诊断工具测试设备帐户
description: 使用 Surface Hub 硬件诊断工具测试设备帐户
ms.assetid: a87b7d41-d0a7-4acc-bfa6-b9070f99bc9c
keywords: 辅助功能设置, “设置”应用, 轻松使用
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 0a9914f5c07a33306cc8a3ef87de85df47a05a20
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911427"
---
# <a name="using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-account"></a>使用 Surface Hub 硬件诊断工具测试设备帐户

## <a name="introduction"></a>简介

> [!NOTE]
> 设置诊断工具的"帐户Surface Hub"部分不会收集任何信息。 作为输入输入输入的电子邮件和密码仅在环境中直接使用，不会收集或传输到任何人。 登录信息仅在应用程序关闭或结束当前会话之前Surface Hub。

> [!IMPORTANT]
> * 运行此应用程序不需要管理员权限。
> * 在向 Microsoft 打开服务调用之前，应该与本地管理员讨论诊断结果。

### <a name="surface-hub-hardware-diagnostic"></a>Surface Hub硬件诊断

默认情况下[，Surface Hub](https://www.microsoft.com/store/apps/9nblggh51f2g)诊断应用程序未安装在早期版本的 Surface Hub 系统中。 应用程序可从应用程序中免费Microsoft Store。 安装应用程序需要管理员权限。

   ![硬件诊断的屏幕截图。](images/01-diagnostic.png)

## <a name="about-the-surface-hub-hardware-diagnostic-tool"></a>关于 Surface Hub 诊断工具

Surface Hub硬件诊断工具是一种易于导航的工具，它允许用户测试 Surface Hub 设备中的许多硬件组件。 此工具还可以测试和验证Surface Hub帐户。 本文介绍如何在硬件诊断工具设置帐户Surface Hub测试。

> [!NOTE]
> 应先创建Surface Hub帐户，然后再完成任何测试。 The Surface Hub Administrator Guide provides instructions and PowerShell scripts to help you create on-premises， online (Office365) ， or hybrid device accounts. 有关详细信息，请转到指南[中的创建和测试设备帐户 (Surface Hub) ](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub)主题。

### <a name="device-account-testing-process"></a>设备帐户测试过程

1. 导航到 **"所有应用"，** 然后找到Surface Hub诊断应用程序。

    ![所有应用的屏幕截图。](images/02-all-apps.png)

1. 应用程序启动时，欢迎页面提供**** 一个文本窗口，用于记录测试 Hub 的原因。 在测试结束时，可以将此笔记与诊断结果一起保存到 USB。 输入便笺后，选择"继续 **"** 按钮。

    >[!NOTE]
    >保存诊断结果时，不要更改默认路径或选择子目录。 稍后可通过文件资源管理器应用复制这些文件。

    ![欢迎屏幕截图。](images/03-welcome.png)

1. 下一个屏幕提供了测试所有或部分组件Surface Hub选项。 若要开始测试设备帐户， **请选择测试结果图标** 。

    ![测试选项的屏幕截图。](images/04-test-results-1.png)

    ![测试结果屏幕截图。](images/05-test-results-2.png)

1. 选择**帐户设置。**  

    ![帐户帐户设置。](images/06-account-settings.png)

    "设置"屏幕用于测试设备帐户。

    ![帐户和设置屏幕截图。](images/07-account-settings-details.png)

1. 输入设备帐户的电子邮件地址。 密码是可选的，但建议这样做。 准备好 **继续时** ，选择"测试帐户"按钮。

    ![测试帐户的屏幕截图。](images/08-test-account.png)

1. 测试完成后，查看四个测试区域的结果。 通过选择每个主题旁边的加号或减号，可以展开或折叠每个部分。

    **网络**

    ![网络屏幕截图。](images/09-network.png)

    **环境**

    ![环境屏幕截图。](images/10-environment.png)

    **证书**

    ![证书的屏幕截图。](images/11-certificates.png)

    **信任模型**

    ![信任模型的屏幕截图。](images/12-trust-model.png)

## <a name="appendix"></a>附录

### <a name="field-messages-and-resolution"></a>字段消息和解析

#### <a name="network"></a>网络

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
Internet 连接 |设备确实具有 Internet 连接 |设备没有 Internet 连接 |验证 Internet 连接，包括代理连接 |
HTTP 版本 |1.1 |1.0 |如果找到 HTTP 1.0，则会导致 WU 和 Store 出问题 |
直接 Internet 连接 |设备已配置代理 设备未配置代理 |不适用 |信息性。 你的设备是否位于代理后面？ |
代理地址 | | |如果配置，则返回代理地址。 |
代理身份验证 |代理不需要身份验证 |代理需要代理身份验证 |如果用户在 Edge 中已有打开的会话，并且已通过代理身份验证，则结果可能是误报。 |
代理身份验证类型 | | |如果使用代理身份验证，则返回代理播发的 Authentication 方法。  |

#### <a name="environment"></a>环境

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
SIP 域 | | |信息性。  |
Skype环境 |Skype for Business联机、Skype for Business OnPrem、Skype for Business 混合 |信息性。 |检测到的环境类型。 注意：只有在输入密码后才能检测到混合。
LyncDiscover FQDN | | |信息性。 显示 LyncDiscover DNS 结果 |
LyncDiscover URI | | |信息性。 显示用于在环境中执行 LyncDiscover 的 URL。|
LyncDiscover |连接成功 |连接失败 |来自 LyncDiscover Web 服务的响应。 |
SIP 池主机名 | | |信息性。 显示从 LyncDiscover 发现的 SIP 池名称 |

#### <a name="certificates-in-premises-hybrid-only"></a>证书 (内部部署混合) 

LyncDiscover 证书

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
LyncDiscover Cert CN | | |信息性。 显示 LD 证书公用名 |
LyncDiscover Cert CA | | |信息性。 显示 LD Cert CA |
LyncDiscover 证书根 CA | | |信息性。 显示 LD 证书根 CA（如果可用）。 |
LD 信任状态 |证书为受信任证书。 |证书不可信，请添加根 CA。 |针对本地证书存储验证证书。 如果计算机信任证书，则返回正数。|[使用 PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / Skype for Business和部署证书[支持用于Surface Hub包的项目](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

SIP 池认证

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
SIP 池证书 CN | | | (内容)  |
SIP 池证书 CA | | | (内容)  |
SIP 池信任状态 |证书为受信任证书。 |证书不可信，请添加根 CA。 |针对本地证书存储验证证书，如果设备信任证书，则返回正数。 |
SIP 池证书根 CA | | |信息。 显示 SIP 池证书根 CA（如果可用）。 |

#### <a name="trust-model-on-premises-hybrid-only"></a>仅 (混合部署信任模型) 

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
信任模型状态 |未检测到信任模型问题。 |SIP 域和服务器域不同，请添加以下域。 |检查 LD FQDN/ LD 服务器名称/池服务器名称，了解信任模型问题。 
域名 (域名)  | | |返回应该为 SFB 进行连接的域列表。 |

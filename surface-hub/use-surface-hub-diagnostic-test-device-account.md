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
ms.openlocfilehash: 127be0a5f320418d8a1086aec3de62e3ef54e42a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830833"
---
# 使用 Surface Hub 硬件诊断工具测试设备帐户

## 简介

> [!NOTE]
> Surface Hub 硬件诊断工具的 "帐户设置" 部分不会收集任何信息。 输入的电子邮件和密码仅直接在你的环境中使用，不会收集或转移给任何人。 只有在关闭应用程序或结束 Surface Hub 上的当前会话之前，登录信息才会保持。

> [!IMPORTANT]
> * 运行此应用程序不需要管理员权限。
> * 在使用 Microsoft 打开服务呼叫之前，应与本地管理员讨论诊断结果。

### Surface Hub 硬件诊断

默认情况下，Surface hub 系统的早期版本中不会安装[Surface Hub 硬件诊断](https://www.microsoft.com/store/apps/9nblggh51f2g)应用程序。 可从 Microsoft Store 免费获取该应用程序。 安装应用程序需要管理员权限。

   ![硬件诊断的屏幕截图](images/01-diagnostic.png)

## 关于 Surface Hub 硬件诊断工具

Surface Hub 硬件诊断工具是一种易于导航的工具，可让用户在 Surface Hub 设备中测试许多硬件组件。 此工具还可测试和验证 Surface Hub 设备帐户。 本文介绍如何使用 Surface Hub 硬件诊断工具中的 "帐户设置" 测试。

> [!NOTE]
> 在完成任何测试之前，应创建 Surface Hub 的设备帐户。 Surface Hub 管理员指南提供说明和 PowerShell 脚本，可帮助你创建本地、联机（Office365）或混合设备帐户。 有关详细信息，请转到指南中的 "[创建和测试设备帐户（Surface Hub）](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) " 主题。

### 设备帐户测试过程

1. 导航到 "**所有应用**"，然后找到 Surface Hub 硬件诊断应用程序。

    ![所有应用的屏幕截图](images/02-all-apps.png)

1. 当应用程序启动时，"**欢迎**" 页面提供一个文本窗口，用于记录测试中心的原因。 在测试结束时，可以将此笔记与诊断结果一起保存到 USB。 完成笔记的输入后，选择 "**继续**" 按钮。

    ![欢迎屏幕截图](images/03-welcome.png)

1. 下一个屏幕提供了测试所有或部分 Surface Hub 组件的选项。 若要开始测试设备帐户，请选择 "**测试结果**" 图标。

    ![测试结果的屏幕截图](images/04-test-results-1.png)

    ![测试结果的屏幕截图](images/05-test-results-2.png)

1. 选择 "**帐户设置**"。  

    ![帐户设置的屏幕截图](images/06-account-settings.png)

    "帐户设置" 屏幕用于测试你的设备帐户。

    ![帐户设置详细信息的屏幕截图](images/07-account-settings-details.png)

1. 输入设备帐户的电子邮件地址。 密码是可选的，但建议使用。 准备好继续时，请选择 "**测试帐户**" 按钮。

    ![测试帐户的屏幕截图](images/08-test-account.png)

1. 测试完成后，请查看四个测试区域的结果。 每个部分都可以通过选择每个主题旁边的加号或减号来展开或折叠。

    **Network**

    ![网络的屏幕截图](images/09-network.png)

    **环境**

    ![环境的屏幕截图](images/10-environment.png)

    **证书**

    ![证书的屏幕截图](images/11-certificates.png)

    **信任模型**

    ![信任模型的屏幕截图](images/12-trust-model.png)

## 附录

### 域消息和解决方案

#### Network

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
互联网连接 |设备有互联网连接 |设备没有互联网连接 |验证 internet 连接，包括代理连接 |
HTTP 版本 |1.1 |1.0 |如果发现 HTTP 1.0，将导致 WU 和应用商店出现问题 |
直接互联网连接 |设备配置的代理设备没有配置代理 |不适用 |信息. 您的设备是否位于代理后？ |
代理地址 | | |如果已配置，则返回代理地址。 |
代理身份验证 |代理不需要身份验证 |代理服务器需要代理身份验证 |如果用户已在 Edge 中打开了一个会话，并且通过代理进行了身份验证，则结果可能为假正值。 |
代理身份验证类型 | | |如果使用代理身份验证，则返回由代理播发的身份验证方法。  |

#### 环境

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
SIP 域 | | |信息.  |
Skype 环境 |Skype for business Online，Skype for business 本地，Skype for business 混合 |信息. |检测到何种类型的环境。 注意：只有在输入密码时才能检测混合。
LyncDiscover FQDN | | |信息. 显示 LyncDiscover DNS 结果 |
LyncDiscover URI | | |信息. 显示用于在你的环境上执行 LyncDiscover 的 URL。|
LyncDiscover |连接成功 |连接失败 |来自 LyncDiscover web 服务的响应。 |
SIP 池主机名 | | |信息. 显示从 LyncDiscover 发现的 SIP 池名称 |

#### 证书（仅限本地混合）

LyncDiscover 证书

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
LyncDiscover Cert CN | | |信息. 显示 LD 证书公用名 |
LyncDiscover Cert CA | | |信息. 显示 LD 证书颁发机构 |
LyncDiscover 证书根 CA | | |信息. 显示 LD 证书根 CA （如果可用）。 |
LD 信任状态 |证书受信任。 |证书不受信任，请添加根 CA。 |根据本地证书存储验证证书。 如果计算机信任证书，则返回正值。|[使用 PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / 下载和部署 Skype for business 证书[Surface Hub 预配程序包支持的项目](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

SIP 池认证

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
SIP 池证书 CN | | |内容 |
SIP 池证书 CA | | |内容 |
SIP 池信任状态 |证书受信任。 |证书不受信任，请添加根 CA。 |验证证书是否针对本地证书存储，如果设备信任证书，则返回正值。 |
SIP 池证书根 CA | | |信息. 显示 SIP 池证书根 CA （如果可用）。 |

#### 信任模型（仅限本地混合）

字段 |成功 |失败 |评论 |参考
|------|------|------|------|------|
信任模型状态 |未检测到信任模型问题。 |SIP 域和服务器域不同请添加以下域。 |检查 "LD FQDN/LD 服务器名称/池服务器名称是否有信任模型问题。 
域名 | | |返回应添加到 SFB 的域的列表以进行连接。 |

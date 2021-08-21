---
title: 为会议室配置网络Microsoft Teams服务质量Surface Hub
description: 本文介绍网络和服务质量的要求和建议，以优化Microsoft Teams 会议室Surface Hub。
keywords: Teams 会议室、Surface Hub、Intune、QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d06a69d89d94839c3a9616a29ff1be12badec76e
ms.sourcegitcommit: b5e7ea8118b848846cf1fb332ed7bf96c4583d20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2021
ms.locfileid: "11909957"
---
# <a name="configure-networking-and-quality-of-service-for-microsoft-teams-rooms-on-surface-hub"></a>为用户配置网络连接Microsoft Teams 会议室服务质量Surface Hub

本文介绍如何准备环境以优化Microsoft Teams 会议室Surface Hub。

## <a name="create-and-test-a-device-account"></a>创建和测试设备帐户

设备帐户是一个帐户，Microsoft Teams 会议室客户端使用它从日历Exchange访问功能，并启用Skype for Business。 [请参阅创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md)

## <a name="check-network-availability"></a>检查网络可用性

> [!TIP]
> 我们强烈建议对网络连接原则中列出的网络配置[Microsoft 365做法](https://aka.ms/pnc)

Teams 会议室Surface Hub用户必须能够访问满足这些要求的网络：

- 访问 Active Directory 或 Azure AD Azure Active Directory (实例) Azure AD
- 访问可以使用 DHCP 提供 IP 地址的服务器。 Microsoft Teams 会议室Surface Hub静态 IP 地址配置连接。
- 访问 HTTP 端口 80 和 443。
- TCP 和 UDP 端口的配置，如 Microsoft 365 和 Office 365 [URL](/microsoft-365/enterprise/urls-and-ip-address-ranges)的端口和协议要求以及 Microsoft Teams。

> [!IMPORTANT]
> Microsoft Teams 会议室不支持代理身份验证，因为它可能会干扰 Teams。 在Surface Hub上Microsoft 365设备或服务终结点进入生产之前，请确保已Teams 会议室或Surface Hub。

## <a name="implement-quality-of-service-qos-on-surface-hub"></a>在服务上 (服务质量) QoS Surface Hub

QoS (服务质量) 是网络技术的组合，使管理员能够优化实时音频/视频和应用程序共享通信的体验。
通过使用移动设备Microsoft Teams MDM Surface Hub提供程序或预配包， (为) [QoS](manage-settings-with-mdm-for-surface-hub.md)配置[QoS。](provisioning-packages-for-surface-hub.md)

若要使用 Surface Hub配置 qoS Microsoft Intune：

1. 在 Intune 中 [，创建自定义策略](/intune/custom-settings-configure)。

2. 在**自定义 OMA-URI 设置，****选择添加**。 对于你添加的每个设置，你将输入名称、描述 (可选) 、数据类型、OMA-URI 和值。

3. 若要确保最佳视频和音频质量Surface Hub，请向设备添加以下 QoS 设置。

    | 名称                  | 描述           | OMA-URI                                                                        | 类型    | 值       |
    | --------------------- | --------------------- | ------------------------------------------------------------------------------ | ------- | ----------- |
    | **音频端口**       | 音频端口范围      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/SourcePortMatchCondition      | 字符串  | 50000-50019 |
    | **音频 DSCP**        | 音频端口标记   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction                    | 整型 | 46          |
    | **视频端口**        | 视频端口范围      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/SourcePortMatchCondition      | 字符串  | 50020-50039 |
    | **视频 DSCP**        | 视频端口标记   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction                    | 整型 | 34          |
    | **共享端口**      | 共享端口范围    | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/SourcePortMatchCondition    | 字符串  | 50040-50059 |
    | **共享 DSCP**      | 共享端口标记 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction                  | 整型 | 18          |

4. 创建策略后，将其部署到Surface Hub。

## <a name="learn-more"></a>了解详细信息

- [在 Microsoft Teams 中 (服务质量) QoS Microsoft Teams](/microsoftteams/qos-in-teams)

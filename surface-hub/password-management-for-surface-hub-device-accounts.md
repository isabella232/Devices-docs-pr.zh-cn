---
title: 密码管理 (Surface Hub)
description: 每个 Microsoft Surface Hub 设备帐户都需要密码才能进行身份验证并启用设备上的功能。
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: 密码, 密码管理, 密码轮换, 设备帐户
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832067"
---
# 密码管理 (Surface Hub)

每个 Microsoft Surface Hub 设备帐户都需要密码才能进行身份验证并启用设备上的功能。 出于安全原因，你可能想要定期更改（或“轮换”）此密码。 但是，如果更改了设备帐户密码，之前存储在 Surface Hub 上的密码将失效，并且依赖该设备帐户的所有功能都将禁用。 可通过“设置”应用更新 Surface Hub 上的设备帐户密码，以便重新启用这些功能。

有两个选项可简化 Surface Hub 设备帐户密码的管理事宜：

1.  关闭设备帐户密码过期。
2.  允许 Surface Hub 自动轮换设备帐户密码。


## 为设备帐户关闭密码轮换

将设备帐户的 **PasswordNeverExpires** 属性设置为 True。 应验证此操作是否满足组织的安全要求。


## 允许 Surface Hub 自动轮换设备帐户密码

Surface Hub 可通过经常更改设备帐户密码来对其进行管理，无需手动更新设备帐户信息。 可在“设置” **** 中启用此功能。 启用后，设备帐户密码在维护时间内将每周进行更改。

注意设备帐户的密码发生更改时，将不会向用户显示新密码。 如果用户需要登录帐户或重新提供密码（例如，如果希望更改 Surface Hub 上的设备帐户设置），需要使用 Active Directory 或 Office 365 管理员门户重置密码。

> [!IMPORTANT]
> 如果组织使用混合拓扑（某些服务是本地托管，而某些是通过 Office 365 联机托管），则必须按“域\用户名”**** 格式设置设备帐户。 否则，密码轮换将没有效果。

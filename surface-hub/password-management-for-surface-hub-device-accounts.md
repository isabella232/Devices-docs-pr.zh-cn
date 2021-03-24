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
ms.openlocfilehash: 215736527121306c712932f57a5a3a853fb3bb20
ms.sourcegitcommit: 366eedceb9f859f5e87ba032b161f248360cb895
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445578"
---
# <a name="password-management-surface-hub"></a>密码管理 (Surface Hub)

每个 Microsoft Surface Hub 设备帐户都需要密码才能进行身份验证并启用设备上的功能。 出于安全原因，你可能想要定期更改（或“轮换”）此密码。 但是，如果更改了设备帐户密码，之前存储在 Surface Hub 上的密码将失效，并且依赖该设备帐户的所有功能都将禁用。 可通过“设置”应用更新 Surface Hub 上的设备帐户密码，以便重新启用这些功能。

有两个选项可简化 Surface Hub 设备帐户密码的管理事宜：

1.  关闭设备帐户密码过期。
2.  允许 Surface Hub 自动轮换设备帐户密码。


## <a name="turn-off-password-rotation-for-the-device-account"></a>为设备帐户关闭密码轮换

将设备帐户的 **PasswordNeverExpires** 属性设置为 True。 应验证此操作是否满足组织的安全要求。


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a>允许 Surface Hub 自动轮换设备帐户密码

Surface Hub 可以自动更改设备帐户的密码，而无需手动更新它。 可以在设置 Surface Hub 帐户**中**  >  **启用**  >  **此功能**。 如果打开"密码轮换"，Surface Hub 将尝试在维护期间每 7 天更改一次密码。 会议期间不会更改密码。 如果自上次密码轮换以来已过去 7 天，但 Surface Hub 已关闭，它将尝试在打开后立即更改密码，或者每隔 10 分钟更改一次密码，直到成功。

自动生成的密码包含 15-32 个字符，包括大写和小写字母、数字和特殊字符的组合。 请注意，当设备帐户的密码更改时，不会显示新密码。 如果你需要登录帐户，或再次提供密码 (例如，如果你想要更改 Surface Hub) 上的设备帐户设置，则需要使用 Active Directory 或 Microsoft 365 管理门户重置密码。

> [!IMPORTANT]
> 将设备帐户添加到 Surface Hub 时所使用的格式会影响必须使用哪个设备附属[](prepare-your-environment-for-surface-hub.md)选项才能使密码旋转正常工作。 如果以 **域\用户名格式** 添加帐户，则初始设置期间将中心与本地 Active Directory 关联。 如果以格式添加帐户，在初始设置期间将中心与 `username@domain.com` Azure Active Directory 关联。 否则，密码轮换将没有效果。

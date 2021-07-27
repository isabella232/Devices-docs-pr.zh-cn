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
ms.openlocfilehash: ab2726577201157ed9a7ff4d265e826c063cf477
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676606"
---
# <a name="password-management-surface-hub"></a>密码管理 (Surface Hub)

每个 Microsoft Surface Hub 设备帐户都需要密码才能进行身份验证并启用设备上的功能。 出于安全原因，你可能想要定期更改（或“轮换”）此密码。 但是，如果更改了设备帐户密码，之前存储在 Surface Hub 上的密码将失效，并且依赖该设备帐户的所有功能都将禁用。 可通过“设置”应用更新 Surface Hub 上的设备帐户密码，以便重新启用这些功能。

有两个选项可简化 Surface Hub 设备帐户密码的管理事宜：

1.  关闭设备帐户密码过期。
2.  允许 Surface Hub 自动轮换设备帐户密码。


## <a name="turn-off-password-rotation-for-the-device-account"></a>为设备帐户关闭密码轮换

将设备帐户的 **PasswordNeverExpires** 属性设置为 True。 应验证此操作是否满足组织的安全要求。


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a>允许 Surface Hub 自动轮换设备帐户密码

用户可以Surface Hub更改设备帐户的密码，而无需手动更新密码。 可以在"帐户 **"设置Surface Hub**  >  ****  >  **此功能**。 如果打开"密码轮换"，Surface Hub将尝试在维护期间每 7 天更改一次密码。 会议期间不会更改密码。 如果自上次密码轮换以来已过去 7 天，但 Surface Hub已关闭，它将尝试在打开后立即更改密码，或每 10 分钟更改一次密码，直到成功。

自动生成的密码包含 15-32 个字符，包括大写和小写字母、数字和特殊字符的组合。 请注意，当设备帐户的密码更改时，不会显示新密码。 如果需要登录帐户，或再次提供密码 (例如，如果要更改 Surface Hub) 上的设备帐户设置，则需要使用 Active Directory 或 Microsoft 365 管理门户重置密码。

> [!IMPORTANT]
> 在[设置密码](prepare-your-environment-for-surface-hub.md)时选择的设备附属Surface Hub会影响哪些设备帐户格式可用于密码轮换。 与本地 Active Directory 附属的集线器只能轮换以 **域\用户名** 格式输入的设备帐户的密码。 与 Azure Active Directory 附属的集线器只能轮换以格式输入的设备帐户的密码，但只有在帐户为仅云帐户或 `username@domain.com` AAD[](/azure/active-directory/hybrid/choose-ad-authn#cloud-authentication)[](/azure/active-directory/authentication/concept-sspr-writeback)域配置为进行云身份验证和密码写回时。

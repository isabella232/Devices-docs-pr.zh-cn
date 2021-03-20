---
title: Surface Hub 2S 首次设置
description: 了解如何完成 Surface Hub 2S 的首次设置。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 9cbce8bf0cc9c729af4cd052167fef016197274f
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442190"
---
# <a name="first-time-setup-for-surface-hub-2s"></a>Surface Hub 2S 首次设置

首次启动 Surface Hub 2S 时，设备会自动进入首次设置模式，以指导你完成帐户配置和相关设置。

## <a name="configuring-surface-hub-2s-account"></a>配置 Surface Hub 2S 帐户

1. **配置区域设置。** 输入区域、语言、键盘布局和时区信息。 选择**下一步** 。

   ![* 配置区域设置 *](images/sh2-run1.png)

1. **连接到无线网络。** 选择首选无线网络，然后选择"下一 **步"。**

   - 如果使用以太网电缆进行连接，则不显示此选项。

   - 你无法连接到热点的无线网络 (强制门户) 将登录请求重定向到提供商的网站。

3. **输入设备帐户信息。** 将 **domain\user** 用于内部部署和混合环境，将 **user\@example.com** 用于联机环境。 选择"下 **一步"。**

   ![* 输入设备帐户信息 *](images/sh2-run2.png)

1. **输入其他信息。** 如果需要，请提供 Exchange 服务器地址，然后选择"下一步 **"。**

   ![* 输入详细信息;例如，Exchange 服务器名称*](images/sh2-run3.png)

1. **为此设备命名。** 输入设备名称或使用基于帐户名称和用户原则名称 [UPN] 显示名称建议的名称。 **选择"下一步"。**

   - 友好 **名称** 显示在 Surface Hub 2S 的左下角，在计划到设备时显示。

   - 设备 **名称** 标识与 Active Directory 或 Azure Active Directory 关联时的设备，以及向 Intune 注册设备时。

   ![* 为此设备命名*](images/sh2-run4.png)
 

## <a name="configuring-device-admin-accounts"></a>配置设备管理员帐户

只能在第一次安装期间设置设备管理员。 有关详细信息，请参阅 Surface [Hub 2S 设备附属关系](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)。

在 **"此设备的安装管理员** "窗口中，选择以下选项之一：Active Directory 域服务、Azure Active Directory 或本地管理员。

![* 此设备的安装程序管理员 *](images/sh2-run5.png)

### <a name="active-directory-domain-services"></a>Active Directory 域服务

1. 输入有权将设备加入 Active Directory 的用户的凭据。

    ![* 使用域加入设置管理员 *](images/sh2-run6.png)

2. 选择 Active Directory 安全组，其中包含允许登录到 Surface Hub 2S 上的"设置"应用的成员。

   ![* 输入安全组 *](images/sh2-run7.png)

1. 选择"**完成"。** 设备将启动。

### <a name="azure-active-directory"></a>Azure Active Directory

选择将设备与 Azure Active Directory 关联时，设备将立即重新启动并显示以下页面。

![* 如果你的组织使用 Office 365 或 Microsoft 的其他商业服务，我们将向你的组织注册此设备*](images/sh2-run8.png)

1. 选择**下一步** 。

1. 输入具有 Intune 计划 **1** 或更大应用的帐户的电子邮件地址或 UPN，然后选择"下一步 **"。**

   ![* 输入工作或学校帐户*](images/sh2-run9.png)

1. 如果重定向，则使用组织的登录页进行身份验证，并提供其他登录信息（如果需要）。 设备将启动。

## <a name="local-administrator-account"></a>本地管理员帐户

- 输入本地管理员的用户名和密码。设备将重新启动。

  ![* 设置管理员帐户*](images/sh2-run10.png)
 
## <a name="using-provisioning-packages"></a>使用预配包

如果在启动 Surface Hub 2S 时将包含预配包的 U 盘插入其中一个 USB 端口，设备将显示以下页面。

1. 输入请求的设置，然后选择"**设置"。**

   ![* 输入预配包的区域设置*](images/sh2-run11.png)

   ![* 从可移动媒体预配此设备*](images/sh2-run12.png)

2. 选择你要使用的预配包。

   ![* 选择要使用的预配包*](images/sh2-run13.png)

3. 如果你创建了多台设备 CSV 文件，你将可以选择设备配置。 有关详细信息，请参阅创建 [Surface Hub 2S 的预配包](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file)。

   ![* 从配置文件中选择设备帐户和友好名称*](images/sh2-run14.png)

4. 按照说明完成首次安装。

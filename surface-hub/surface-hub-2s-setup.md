---
title: 第一次设置 Surface Hub 2
description: 了解如何第一次完成 Surface Hub 2 的设置。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 47a393944c1b524931a6ac56962cc2cd60786007
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831788"
---
# 第一次设置 Surface Hub 2

第一次启动 Surface Hub 2 时，设备将自动进入 "首次设置" 模式，指导你完成帐户配置和相关设置。

## 配置 Surface Hub 2 帐户

1. **配置你的区域设置。** 输入区域、语言、键盘布局和时区信息。 选择**下一步** 。

   ![* 配置你的区域设置 *](images/sh2-run1.png) <br>
1. **连接到无线网络。** 选择您的首选无线网络，然后选择 "**下一步"。**

- 如果使用以太网电缆连接，则不会显示此选项。
- 无法在将登录请求重定向到提供商网站的热点（固定门户）中连接到无线网络。

3. **输入设备帐户信息。** 将**域 \**用户用于本地和混合环境，以及针对在线环境的**用户 \ @example .com** 。 选择 "**下一步"。**

   ![* 输入设备帐户信息 *](images/sh2-run2.png) <br>
1. **输入其他信息。** 如果需要，请提供您的 Exchange 服务器地址，然后选择 "**下一步"。**

    ![* 输入详细信息;例如，Exchange 服务器名称 *](images/sh2-run3.png) <br>

1. **为此设备命名。** 为你的设备输入一个名称，或根据你的帐户的显示名称和用户主体名称 [UPN] 使用推荐的名称。 **选择 "下一步**"。

- **友好名称**在 Surface Hub 2 的左下角可见，并在投影到设备时显示。

- **设备名称**标识与 Active Directory 或 Azure Active directory 关联的设备，以及何时向 Intune 注册设备。

  ![* 命名此设备 *](images/sh2-run4.png) <br>
 
## 配置设备管理员帐户

您在首次设置时只能设置设备管理员。 有关详细信息，请参阅[Surface Hub 2 设备从属关系](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation)。

 在 "**为此设备设置管理员**" 窗口中，选择下列选项之一： Active Directory 域服务、Azure Active Directory 或本地管理员。

   ![* 设置此设备的管理员 *](images/sh2-run5.png) <br>

### Active Directory 域服务

1. 输入具有将设备加入到 Active Directory 的权限的用户的凭据。

    ![* 使用加入域的设置管理员 *](images/sh2-run6.png) <br>

2. 选择包含允许登录到 Surface Hub 2 上的 "设置" 应用的成员的 Active Directory 安全组。

    ![* 输入安全组 *](images/sh2-run7.png) <br>
1. 选择 "**完成**"。 设备将重新启动。

### Azure Active Directory

选择将你的设备与 Azure Active Directory 关联时，设备将立即重启并显示以下页面。 选择**下一步** 。

![* 如果你的组织使用 Office 365 或 Microsoft 的其他业务服务，我们将向你的组织 enrolll 此设备 *](images/sh2-run8.png) <br>

1. **使用 Intune 计划 1**或更高版本输入帐户的电子邮件地址或 UPN，然后选择 "**下一步"。**

    ![* 输入工作或学校帐户 *](images/sh2-run9.png) <br>

2. 如果已重定向，请使用组织的登录页面进行身份验证，并提供其他登录信息（如果需要）。 设备将重新启动。

## 本地管理员帐户

- 输入本地管理员的用户名和密码。设备将重新启动。

     ![* 设置管理员帐户 *](images/sh2-run10.png) <br>
 
## 使用预配程序包

如果在启动 Surface Hub 2 时将带有预配包的 USB 拇指驱动器插入到其中一个 USB 端口中，设备将显示以下页面。

1. 输入所需的设置，然后选择 "**设置**"。

    ![* 为预配程序包输入区域设置 *](images/sh2-run11.png) <br>

    ![* 从可移动媒体预配此设备 *](images/sh2-run12.png) <br>
2. 选择要使用的预配包。

   ![* 选择要使用的预配包 *](images/sh2-run13.png) <br>

3. 如果你创建了多个设备 CSV 文件，你将能够选择设备配置。 有关详细信息，请参阅[创建 Surface Hub 2 版的预配包](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file)。


    ![* 从配置文件中选择设备帐户和友好名称 *](images/sh2-run14.png) <br>

4. 按照说明完成首次设置。

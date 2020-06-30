---
title: 使用 Microsoft Authenticator 登录到 Surface Hub
description: 使用移动设备上的 Microsoft Authenticator 登录到 Surface Hub。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/28/2017
ms.reviewer: ''
manager: laurawi
localizationpriority: medium
ms.openlocfilehash: 11768488d2ef7509af6a592b9e4ac945a7e35650
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830926"
---
# 使用 Microsoft Authenticator 登录到 Surface Hub

组织中的人员可以使用 Android 和 iOS 上提供的 Microsoft Authenticator 应用登录到 Surface Hub，而无需使用密码。

## 组织先决条件

若要让组织中的人员利用其手机和其他设备登录到 Surface Hub，而不是利用密码登录，你将需要确保组织满足以下先决条件： 

- 你的组织必须是 Azure Active Directory (Azure AD) 支持的混合组织或仅限于云的组织。 有关详细信息，请参阅[什么是 Azure Active Directory？](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)

- 请确保至少具有 Office 365 E3 订阅。 

- [配置多重身份验证](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings)。 请确保已选择**通过移动应用发送的通知**。 

    ![多重身份验证选项](images/mfa-options.png)

- 启用在 Azure AD 服务（如 Office、SharePoint 等）上托管的内容。 

- Surface Hub 必须运行 Windows 10 版本 1703 或更高版本。

- 使用本地或已加入域的帐户设置 Surface Hub。

目前无法使用 Microsoft Authenticator 登录已加入 Azure AD 的 Surface Hub。

## 单个先决条件

- 运行 6.0 或更高版本的 Android 手机，或者运行 iOS9 或更高版本的 iPhone 或 iPad 

- 相应应用商店中最新版本的 Microsoft Authenticator 应用

    >[!NOTE]
    >在 iOS 上，应用版本必须是 5.4.0 或更高版本。
    >
    >运行 Windows 操作系统的手机上的 Microsoft Authenticator 应用不能用于登录到 Surface Hub。

- 设备上的密码或屏幕锁定已启用

- 标准 SMTP 电子邮件地址（示例：joe@contoso.com）。 非标准或虚 SMTP 电子邮件地址（示例：firstname.lastname@contoso.com）目前无效。

## 如何设置 Microsoft Authenticator 应用

>[!NOTE]
>如果在 Android 设备上安装了公司门户，请在设置 Microsoft Authenticator 之前卸载此门户。 设置应用后，你可以重新安装公司门户。
>
>如果你已在手机上设置了 Microsoft Authenticator 并注册了你的设备，请转到登录说明。

1. 将你的工作或学校帐户添加到 Microsoft Authenticator 中以进行多重身份验证。 你将需要 IT 部门提供的 QR 代码。 如需帮助，请参阅 [Microsoft Authenticator 应用入门](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。
2. 转到**设置**并注册你的设备。
3. 返回到帐户页面，然后从帐户下拉菜单中选择**启用电话登录**。

## 如何在会议期间登录 Surface Hub

1. 在设置会议后，转到 Surface Hub 并选择**登录即可查看你的会议和文件**。

    >[!NOTE]
    >如果你不确定如何在 Surface Hub 上计划会议，请参阅[在 Surface Hub 上计划会议](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting)。

    ![Surface Hub 上“登录”选项的屏幕截图](images/sign-in.png)

2. 你将看到被邀请参加会议的人员的列表。 选择你自己（或者想要登录的人员 - 确保此人在会议之前已经完成了设置设备的步骤），然后选择**继续**。

    ![会议中与会者列表的屏幕截图](images/attendees.png)

    你将在 Surface Hub 上看到一个代码。

    ![“批准登录”的代码屏幕截图](images/approve-signin.png)

3. 若要批准登录，请打开 Authenticator 应用，输入 Surface Hub 上显示的四位数代码，然后选择**批准**。 然后，系统将请你输入 PIN，或者使用你的指纹完成登录。 

    ![Microsoft Authenticator 中“批准登录”屏幕的屏幕截图](images/approve-signin2.png)

现在，你可以通过 OneDrive 应用访问所有文件。
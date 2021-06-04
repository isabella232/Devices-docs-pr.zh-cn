---
title: 在 Surface Hub 上配置不带密码的登录
description: 了解如何简化登录 Surface Hub。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893044"
---
# 配置 Surface Hub 上的 passwordless 登录

 
Passwordless 登录简化了对你的应用、会议和文件的访问。 Surface Hub 支持使用 Microsoft 身份验证器应用和你的组织提供的 FIDO2 安全密钥登录。

**重要提示：** 此内容适用于用户。 若要使用 passwordless 登录，你的 IT 管理员必须为你的组织启用 passwordless 身份验证。 有关详细信息，请参阅：

- [启用 passwordless 手机登录](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [启用 passwordless 安全密钥登录](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


##  <a name="configure-sign-in-using-microsoft-authenticator-app"></a>使用 Microsoft 身份验证器应用配置登录

**注意：** 从 Windows 10 Team 2020 更新开始，用户可以在 Azure AD 中使用其首选电子邮件别名以及其用户主体名称（UPN），使用 Microsoft 身份验证器登录。 例如，用户可以使用其首选别名（John.Doe@contoso.com）或其 UPN （jdoe@contoso.com）登录。
 
Microsoft 身份验证器应用可帮助你使用移动设备登录 Surface Hub。 若要使用 Microsoft 身份验证器配置登录，请执行以下操作：


1. 在移动设备上，下载 Microsoft 身份验证器应用。
    - Google Android：在 Android 设备上，转到 "Google Play"[下载并安装 Microsoft 身份验证器应用](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)。
    - Apple iOS：在 Apple iOS 设备上，转到应用商店[下载并安装 Microsoft 身份验证器应用](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)。
2. 在你的电脑上，从你的工作或学校帐户[的 "安全信息" 页面设置 Microsoft 身份验证器应用](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page)。
3. 从你的移动设备上的 Microsoft 身份验证程序应用，为你的工作或学校帐户[打开并使用手机登录](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account)。

 
##  <a name="configure-sign-in-using-fido2-security-keys"></a>使用 FIDO2 安全密钥配置登录

> [!NOTE]
>  使用 FIDO2 安全密钥的 Passwordless 登录 Surface Hub 需要 Windows 10 Team 2020 更新。

> [!IMPORTANT]
> Surface Hub 仅支持 USB 安全密钥。
 
您也可以使用由您的组织提供的 FIDO2 安全密钥登录 Surface Hub。 

###  <a name="to-configure-sign-in-using-a-security-key"></a>若要使用安全密钥配置登录，请执行以下操作：


1. 在你的电脑上，转到你的 [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) 页面并登录到你的工作或学校帐户。
2. 从左侧导航窗格中选择 "安全信息"，或从**安全信息**块中的链接中选择 "**安全信息**"，然后从 "**安全信息**" 页面中选择 "**添加方法**"。
3. 在 "**添加方法**" 页面上，从下拉列表中选择 "**安全密钥**"，然后选择 "**添加**"。
4. 在 "**安全密钥**" 页面上，选择 " **USB 设备**"。
5. 准备好您的安全密钥，然后选择 "**下一步**"。
6. 在出现的对话框中，按照说明插入安全密钥、创建或输入 PIN，并执行所需的手势（生物识别或触摸）。
7. 在 "**安全密钥**" 页面上，为安全密钥提供一个名称，然后选择 "**下一步**"。
8. 选择 "**完成**" 以完成该过程。

##  <a name="sign-in-to-surface-hub"></a>登录 Surface Hub

配置 passwordless 登录后，你可以使用它让你更轻松地在 Surface Hub 上访问你的应用、会议和文件：

- 快速加入你的会议并打开最近的 Microsoft 365 文件。 有关详细信息，请参阅[**登录以查看你的会议和文件**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)。
- 快速登录 Microsoft 应用，如白板、PowerPoint、Word、Excel、OneDrive 和 Power BI。
- 快速登录到新的 Microsoft Edge 以访问你的 "收藏夹" 和 "浏览" 首选项。 有关详细信息，请参阅[安装和配置新的 Microsoft Edge](surface-hub-install-chromium-edge.md)。
- 登录 Surface Hub 后，您可以使用其他应用，而无需再次登录，直到选择 "**结束会话**"。 选择 "**结束会话**" 将从设备中删除您的凭据、文件和个人数据。 有关详细信息，请参阅[结束会话](finishing-your-surface-hub-meeting.md)。


##  <a name="learn-more"></a>了解详细信息

- [Azure Active Directory 的 Passwordless 身份验证选项](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [Microsoft 身份验证应用的 Passwordless 登录](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Passwordless 使用 FIDO2 安全密钥登录](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)


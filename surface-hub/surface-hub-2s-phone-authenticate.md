---
title: 配置无密码登录 Surface Hub
description: 了解如何简化登录Surface Hub。
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
ms.openlocfilehash: 5449a3a168821c61b7c8969bfe445db91f357a2b
ms.sourcegitcommit: 4012a9499f658799197fedc7ea1a0c35d6127ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2021
ms.locfileid: "12101170"
---
# <a name="configure-passwordless-sign-in-on-surface-hub"></a>配置无密码登录 Surface Hub

 
无密码登录简化了对应用、会议和文件的访问。 Surface Hub支持使用组织提供的 Microsoft Authenticator 应用和 FIDO2 安全密钥登录。

**重要提示：** 此内容适用于用户。 若要使用无密码登录，IT 管理员必须为组织启用无密码身份验证。 有关详细信息，请参阅：

- [启用无密码电话登录](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [启用无密码安全密钥登录](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <a name="configure-sign-in-using-microsoft-authenticator-app"></a>使用应用配置Microsoft Authenticator登录

**注意：** 从 Windows 10 协同版 2020 Update 开始，用户可以使用 Azure AD 中的首选电子邮件别名以及用户主体名称 (UPN) 使用 Microsoft Authenticator 登录。 例如，用户可以使用首选别名 (John.Doe@contoso.com) UPN (jdoe@contoso.com) 登录。
 
Microsoft Authenticator应用可帮助你使用移动设备Surface Hub登录。 若要配置使用登录Microsoft Authenticator：


1. 在移动设备上，下载Microsoft Authenticator应用。
    - Google Android：在 Android 设备上，转到 Google Play 下载并[安装Microsoft Authenticator应用](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)。
    - Apple iOS：在 Apple iOS 设备上，转到应用商店下载并安装 Microsoft Authenticator[应用](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)。
2. 在你的电脑上，[从Microsoft Authenticator或学校帐户的安全信息页面](/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page)设置应用。
3. 在Microsoft Authenticator应用中，为工作或学校帐户打开并使用[](/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account)电话登录。

 
## <a name="configure-sign-in-using-fido2-security-keys"></a>使用 FIDO2 安全密钥配置登录

> [!NOTE]
>  使用 FIDO2 安全密钥Surface Hub密码登录需要 Windows 10 协同版 2020 更新。

> [!IMPORTANT]
> Surface Hub仅支持 USB 安全密钥。
 
您还可以使用Surface Hub提供的 FIDO2 安全密钥登录安全密钥。 

### <a name="to-configure-sign-in-using-a-security-key"></a>若要使用安全密钥配置登录，


1. 在电脑上，转到你的 [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) 页面并登录到你的工作或学校帐户。
2. 从**左侧导航**窗格或安全信息块中的链接中选择"安全信息****"，然后从"安全信息****"页中选择"**添加方法**"。
3. 在"**添加方法"页上**，从**** 下拉列表中选择"安全密钥"，然后选择"添加 **"。**
4. 在"**安全密钥"** 页上，选择 **"USB 设备"。**
5. 准备好你的安全密钥，然后选择下一 **步**。
6. 在出现的对话框中，按照说明插入安全密钥、创建或输入 PIN，并执行所需的手势 (生物识别或触摸) 。
7. 在"**安全密钥"** 页上，为安全密钥命名，然后选择"下一步 **"。**
8. 选择 **"** 完成"以完成此过程。

## <a name="sign-in-to-surface-hub"></a>登录Surface Hub

配置无密码登录后，可以使用它更轻松地访问应用中的应用、会议和Surface Hub：

- 快速加入会议并打开最近Microsoft 365文件。 有关详细信息，请参阅 [**登录以查看会议和文件**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)。
- 快速登录到 Microsoft 应用，如白板、PowerPoint、Word、Excel、OneDrive 和 Power BI。
- 快速登录到新Microsoft Edge访问收藏夹和浏览首选项。 有关详细信息，请参阅安装和[配置新的Microsoft Edge。](surface-hub-install-chromium-edge.md)
- 登录会话后Surface Hub，无需再次登录即可使用其他应用，直到选择结束**会话**。 选择 **"** 结束会话"将从设备中删除凭据、文件和个人数据。 有关详细信息，请参阅结束 [会话](finishing-your-surface-hub-meeting.md)。


## <a name="learn-more"></a>了解详细信息

- [用于身份验证的无密码Azure Active Directory](/azure/active-directory/authentication/concept-authentication-passwordless)
- [无密码登录应用Microsoft Authenticator登录](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [使用 FIDO2 安全密钥进行无密码登录](/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)


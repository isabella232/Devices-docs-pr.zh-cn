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
# <span data-ttu-id="56815-104">配置 Surface Hub 上的 passwordless 登录</span><span class="sxs-lookup"><span data-stu-id="56815-104">Configure passwordless sign-in on Surface Hub</span></span>

 
<span data-ttu-id="56815-105">Passwordless 登录简化了对你的应用、会议和文件的访问。</span><span class="sxs-lookup"><span data-stu-id="56815-105">Passwordless sign-in simplifies access to your apps, meetings, and files.</span></span> <span data-ttu-id="56815-106">Surface Hub 支持使用 Microsoft 身份验证器应用和你的组织提供的 FIDO2 安全密钥登录。</span><span class="sxs-lookup"><span data-stu-id="56815-106">Surface Hub supports signing in using the Microsoft Authenticator app and FIDO2 security keys provided by your organization.</span></span>

<span data-ttu-id="56815-107">**重要提示：** 此内容适用于用户。</span><span class="sxs-lookup"><span data-stu-id="56815-107">**Important:** This content is intended for users.</span></span> <span data-ttu-id="56815-108">若要使用 passwordless 登录，你的 IT 管理员必须为你的组织启用 passwordless 身份验证。</span><span class="sxs-lookup"><span data-stu-id="56815-108">To use passwordless sign-in, your IT admin must enable passwordless authentication for your organization.</span></span> <span data-ttu-id="56815-109">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="56815-109">For more information, see:</span></span>

- [<span data-ttu-id="56815-110">启用 passwordless 手机登录</span><span class="sxs-lookup"><span data-stu-id="56815-110">Enable passwordless phone sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="56815-111">启用 passwordless 安全密钥登录</span><span class="sxs-lookup"><span data-stu-id="56815-111">Enable passwordless security key sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <span data-ttu-id="56815-112">使用 Microsoft 身份验证器应用配置登录</span><span class="sxs-lookup"><span data-stu-id="56815-112">Configure sign-in using Microsoft Authenticator app</span></span>

<span data-ttu-id="56815-113">**注意：** 从 Windows 10 Team 2020 更新开始，用户可以在 Azure AD 中使用其首选电子邮件别名以及其用户主体名称（UPN），使用 Microsoft 身份验证器登录。</span><span class="sxs-lookup"><span data-stu-id="56815-113">**Note:** Starting with Windows 10 Team 2020 Update, users can use their preferred email aliases in Azure AD, as well as their User Principal Name (UPN), to sign in using Microsoft Authenticator.</span></span> <span data-ttu-id="56815-114">例如，用户可以使用其首选别名（John.Doe@contoso.com）或其 UPN （jdoe@contoso.com）登录。</span><span class="sxs-lookup"><span data-stu-id="56815-114">For example, a user can use either their preferred alias (John.Doe@contoso.com) or their UPN (jdoe@contoso.com) to sign in.</span></span>
 
<span data-ttu-id="56815-115">Microsoft 身份验证器应用可帮助你使用移动设备登录 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="56815-115">The Microsoft Authenticator app helps you sign-in to Surface Hub using your mobile device.</span></span> <span data-ttu-id="56815-116">若要使用 Microsoft 身份验证器配置登录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="56815-116">To configure sign-in using Microsoft Authenticator:</span></span>


1. <span data-ttu-id="56815-117">在移动设备上，下载 Microsoft 身份验证器应用。</span><span class="sxs-lookup"><span data-stu-id="56815-117">On your mobile device, download the Microsoft Authenticator app.</span></span>
    - <span data-ttu-id="56815-118">Google Android：在 Android 设备上，转到 "Google Play"[下载并安装 Microsoft 身份验证器应用](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)。</span><span class="sxs-lookup"><span data-stu-id="56815-118">Google Android: On your Android device, go to Google Play to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span></span>
    - <span data-ttu-id="56815-119">Apple iOS：在 Apple iOS 设备上，转到应用商店[下载并安装 Microsoft 身份验证器应用](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)。</span><span class="sxs-lookup"><span data-stu-id="56815-119">Apple iOS: On your Apple iOS device, go to the App Store to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span></span>
2. <span data-ttu-id="56815-120">在你的电脑上，从你的工作或学校帐户[的 "安全信息" 页面设置 Microsoft 身份验证器应用](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page)。</span><span class="sxs-lookup"><span data-stu-id="56815-120">On your PC, [setup the Microsoft Authenticator app from the Security info page](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) for your work or school account.</span></span>
3. <span data-ttu-id="56815-121">从你的移动设备上的 Microsoft 身份验证程序应用，为你的工作或学校帐户[打开并使用手机登录](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account)。</span><span class="sxs-lookup"><span data-stu-id="56815-121">From the Microsoft Authenticator app on your mobile device, [turn on and use phone sign-in](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) for your work or school account.</span></span>

 
## <span data-ttu-id="56815-122">使用 FIDO2 安全密钥配置登录</span><span class="sxs-lookup"><span data-stu-id="56815-122">Configure sign-in using FIDO2 security keys</span></span>

> [!NOTE]
>  <span data-ttu-id="56815-123">使用 FIDO2 安全密钥的 Passwordless 登录 Surface Hub 需要 Windows 10 Team 2020 更新。</span><span class="sxs-lookup"><span data-stu-id="56815-123">Passwordless sign-in on Surface Hub using FIDO2 security keys requires the Windows 10 Team 2020 Update.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56815-124">Surface Hub 仅支持 USB 安全密钥。</span><span class="sxs-lookup"><span data-stu-id="56815-124">Surface Hub only supports USB security keys.</span></span>
 
<span data-ttu-id="56815-125">您也可以使用由您的组织提供的 FIDO2 安全密钥登录 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="56815-125">You can also sign into Surface Hub using a FIDO2 security key provided by your organization.</span></span> 

### <span data-ttu-id="56815-126">若要使用安全密钥配置登录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="56815-126">To configure sign-in using a security key:</span></span>


1. <span data-ttu-id="56815-127">在你的电脑上，转到你的 [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) 页面并登录到你的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="56815-127">On your PC, go to your [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page and sign in to your work or school account.</span></span>
2. <span data-ttu-id="56815-128">从左侧导航窗格中选择 "安全信息"，或从**安全信息**块中的链接中选择 "**安全信息**"，然后从 "**安全信息**" 页面中选择 "**添加方法**"。</span><span class="sxs-lookup"><span data-stu-id="56815-128">Select **Security info** from the left navigation pane or from the link in the **Security info** block, and then select **Add method** from the **Security info** page.</span></span>
3. <span data-ttu-id="56815-129">在 "**添加方法**" 页面上，从下拉列表中选择 "**安全密钥**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="56815-129">On the **Add a method** page, select **Security key** from the drop-down list, and then select **Add**.</span></span>
4. <span data-ttu-id="56815-130">在 "**安全密钥**" 页面上，选择 " **USB 设备**"。</span><span class="sxs-lookup"><span data-stu-id="56815-130">On the **Security key** page, choose **USB device**.</span></span>
5. <span data-ttu-id="56815-131">准备好您的安全密钥，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="56815-131">Have your security key ready and select **Next**.</span></span>
6. <span data-ttu-id="56815-132">在出现的对话框中，按照说明插入安全密钥、创建或输入 PIN，并执行所需的手势（生物识别或触摸）。</span><span class="sxs-lookup"><span data-stu-id="56815-132">In the dialog box that appears, follow the instructions to insert the security key, create or enter a PIN, and perform the required gesture (either biometric or touch).</span></span>
7. <span data-ttu-id="56815-133">在 "**安全密钥**" 页面上，为安全密钥提供一个名称，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="56815-133">On the **Security key** page, give your security key a name, then select **Next**.</span></span>
8. <span data-ttu-id="56815-134">选择 "**完成**" 以完成该过程。</span><span class="sxs-lookup"><span data-stu-id="56815-134">Select **Done** to complete the process.</span></span>

## <span data-ttu-id="56815-135">登录 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="56815-135">Sign-in to Surface Hub</span></span>

<span data-ttu-id="56815-136">配置 passwordless 登录后，你可以使用它让你更轻松地在 Surface Hub 上访问你的应用、会议和文件：</span><span class="sxs-lookup"><span data-stu-id="56815-136">Once you've configured passwordless sign-in, you can use it to make it easier to access your apps, meetings, and files on the Surface Hub:</span></span>

- <span data-ttu-id="56815-137">快速加入你的会议并打开最近的 Microsoft 365 文件。</span><span class="sxs-lookup"><span data-stu-id="56815-137">Quickly join your meetings and open recent Microsoft 365 files.</span></span> <span data-ttu-id="56815-138">有关详细信息，请参阅[**登录以查看你的会议和文件**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="56815-138">For more information, see [**Sign in to see your meetings and files**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span></span>
- <span data-ttu-id="56815-139">快速登录 Microsoft 应用，如白板、PowerPoint、Word、Excel、OneDrive 和 Power BI。</span><span class="sxs-lookup"><span data-stu-id="56815-139">Quickly sign in to Microsoft apps like Whiteboard, PowerPoint, Word, Excel, OneDrive, and Power BI.</span></span>
- <span data-ttu-id="56815-140">快速登录到新的 Microsoft Edge 以访问你的 "收藏夹" 和 "浏览" 首选项。</span><span class="sxs-lookup"><span data-stu-id="56815-140">Quickly sign in to the new Microsoft Edge to access your favorites and browsing preferences.</span></span> <span data-ttu-id="56815-141">有关详细信息，请参阅[安装和配置新的 Microsoft Edge](surface-hub-install-chromium-edge.md)。</span><span class="sxs-lookup"><span data-stu-id="56815-141">For more information, see [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).</span></span>
- <span data-ttu-id="56815-142">登录 Surface Hub 后，您可以使用其他应用，而无需再次登录，直到选择 "**结束会话**"。</span><span class="sxs-lookup"><span data-stu-id="56815-142">Once you've signed into Surface Hub, you can use other apps without having to sign in again until you select **End session**.</span></span> <span data-ttu-id="56815-143">选择 "**结束会话**" 将从设备中删除您的凭据、文件和个人数据。</span><span class="sxs-lookup"><span data-stu-id="56815-143">Selecting **End session** deletes your credentials, files, and personal data from the device.</span></span> <span data-ttu-id="56815-144">有关详细信息，请参阅[结束会话](finishing-your-surface-hub-meeting.md)。</span><span class="sxs-lookup"><span data-stu-id="56815-144">For more information, see [End session](finishing-your-surface-hub-meeting.md).</span></span>


## <span data-ttu-id="56815-145">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="56815-145">Learn more</span></span>

- [<span data-ttu-id="56815-146">Azure Active Directory 的 Passwordless 身份验证选项</span><span class="sxs-lookup"><span data-stu-id="56815-146">Passwordless authentication options for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [<span data-ttu-id="56815-147">Microsoft 身份验证应用的 Passwordless 登录</span><span class="sxs-lookup"><span data-stu-id="56815-147">Passwordless sign-in with the Microsoft Authenticator app</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="56815-148">Passwordless 使用 FIDO2 安全密钥登录</span><span class="sxs-lookup"><span data-stu-id="56815-148">Passwordless sign-in using FIDO2 security keys</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)


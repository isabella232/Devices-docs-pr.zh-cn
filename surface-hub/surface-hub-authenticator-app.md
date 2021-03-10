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
ms.openlocfilehash: f8a2bf8ddb75ca6dd3ff89e16fe0d37e099be29d
ms.sourcegitcommit: 85f5a2e67b34fe073ec588ed441ebee239ab0ac6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400733"
---
# <a name="sign-in-to-surface-hub-with-microsoft-authenticator"></a><span data-ttu-id="ee76c-103">使用 Microsoft Authenticator 登录到 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="ee76c-103">Sign in to Surface Hub with Microsoft Authenticator</span></span>

<span data-ttu-id="ee76c-104">组织中的人员可以使用 Android 和 iOS 上提供的 Microsoft Authenticator 应用登录到 Surface Hub，而无需使用密码。</span><span class="sxs-lookup"><span data-stu-id="ee76c-104">People in your organization can sign in to a Surface Hub  without a password using the Microsoft Authenticator app, available on Android and iOS.</span></span>

## <a name="organization-prerequisites"></a><span data-ttu-id="ee76c-105">组织先决条件</span><span class="sxs-lookup"><span data-stu-id="ee76c-105">Organization prerequisites</span></span>

<span data-ttu-id="ee76c-106">若要让组织中的人员利用其手机和其他设备登录到 Surface Hub，而不是利用密码登录，你将需要确保组织满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="ee76c-106">To let people in your organization sign in to Surface Hub with their phones and other devices instead of a password, you’ll need to make sure that your organization meets these prerequisites:</span></span> 

- <span data-ttu-id="ee76c-107">你的组织必须是 Azure Active Directory (Azure AD) 支持的混合组织或仅限于云的组织。</span><span class="sxs-lookup"><span data-stu-id="ee76c-107">Your organization must be a hybrid or cloud-only organization, backed by Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="ee76c-108">有关详细信息，请参阅[什么是 Azure Active Directory？](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="ee76c-108">For more information, see [What is Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span></span>

- <span data-ttu-id="ee76c-109">请确保至少具有 Office 365 E3 订阅。</span><span class="sxs-lookup"><span data-stu-id="ee76c-109">Make sure you have at minimum an Office 365 E3 subscription.</span></span> 

- <span data-ttu-id="ee76c-110">[配置多重身份验证](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings)。</span><span class="sxs-lookup"><span data-stu-id="ee76c-110">[Configure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span></span> <span data-ttu-id="ee76c-111">请确保已选择**通过移动应用发送的通知**。</span><span class="sxs-lookup"><span data-stu-id="ee76c-111">Make sure **Notification through mobile app** is selected.</span></span> 

    ![多重身份验证选项](images/mfa-options.png)

- <span data-ttu-id="ee76c-113">在 Azure AD 服务（如 Office、SharePoint 等）上启用内容托管。</span><span class="sxs-lookup"><span data-stu-id="ee76c-113">Enable content hosting on Azure AD services such as Office, SharePoint, etc.</span></span> 

- <span data-ttu-id="ee76c-114">Surface Hub 必须运行 Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ee76c-114">Surface Hub must be running Windows 10, version 1703 or later.</span></span>

- <span data-ttu-id="ee76c-115">使用本地或已加入域的帐户设置 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="ee76c-115">Surface Hub is set up with either a local or domain-joined account.</span></span>

## <a name="individual-prerequisites"></a><span data-ttu-id="ee76c-116">单个先决条件</span><span class="sxs-lookup"><span data-stu-id="ee76c-116">Individual prerequisites</span></span>

- <span data-ttu-id="ee76c-117">运行 6.0 或更高版本的 Android 手机，或者运行 iOS9 或更高版本的 iPhone 或 iPad</span><span class="sxs-lookup"><span data-stu-id="ee76c-117">An Android phone running 6.0 or later, or an iPhone or iPad running iOS9 or later</span></span> 

- <span data-ttu-id="ee76c-118">相应应用商店中最新版本的 Microsoft Authenticator 应用</span><span class="sxs-lookup"><span data-stu-id="ee76c-118">The most recent version of the Microsoft Authenticator app from the appropriate app store</span></span>

    >[!NOTE]
    ><span data-ttu-id="ee76c-119">在 iOS 上，应用版本必须是 5.4.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ee76c-119">On iOS, the app version must be 5.4.0 or higher.</span></span>
    >
    ><span data-ttu-id="ee76c-120">运行 Windows 操作系统的手机上的 Microsoft Authenticator 应用不能用于登录到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="ee76c-120">The Microsoft Authenticator app on phones running a Windows operating system can't be used to sign in to Surface Hub.</span></span>

- <span data-ttu-id="ee76c-121">设备上的密码或屏幕锁定已启用</span><span class="sxs-lookup"><span data-stu-id="ee76c-121">Passcode or screen lock on your device is enabled</span></span>

## <a name="how-to-set-up-the-microsoft-authenticator-app"></a><span data-ttu-id="ee76c-122">如何设置 Microsoft Authenticator 应用</span><span class="sxs-lookup"><span data-stu-id="ee76c-122">How to set up the Microsoft Authenticator app</span></span>

>[!NOTE]
><span data-ttu-id="ee76c-123">如果在 Android 设备上安装了公司门户，请在设置 Microsoft Authenticator 之前卸载此门户。</span><span class="sxs-lookup"><span data-stu-id="ee76c-123">If Company Portal is installed on your Android device, uninstall it before you set up Microsoft Authenticator.</span></span> <span data-ttu-id="ee76c-124">设置应用后，你可以重新安装公司门户。</span><span class="sxs-lookup"><span data-stu-id="ee76c-124">After you set up the app, you can reinstall Company Portal.</span></span>
>
><span data-ttu-id="ee76c-125">如果你已在手机上设置了 Microsoft Authenticator 并注册了你的设备，请转到登录说明。</span><span class="sxs-lookup"><span data-stu-id="ee76c-125">If you have already set up Microsoft Authenticator on your phone and registered your device, go to the sign-in instructions.</span></span>

1. <span data-ttu-id="ee76c-126">将你的工作或学校帐户添加到 Microsoft Authenticator 中以进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="ee76c-126">Add your work or school account to Microsoft Authenticator for Multi-Factor Authentication.</span></span> <span data-ttu-id="ee76c-127">你将需要 IT 部门提供的 QR 代码。</span><span class="sxs-lookup"><span data-stu-id="ee76c-127">You will need a QR code provided by your IT department.</span></span> <span data-ttu-id="ee76c-128">如需帮助，请参阅 [Microsoft Authenticator 应用入门](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。</span><span class="sxs-lookup"><span data-stu-id="ee76c-128">For help, see [Get started with the Microsoft Authenticator app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span></span>
2. <span data-ttu-id="ee76c-129">转到**设置**并注册你的设备。</span><span class="sxs-lookup"><span data-stu-id="ee76c-129">Go to **Settings** and register your device.</span></span>
3. <span data-ttu-id="ee76c-130">返回到帐户页面，然后从帐户下拉菜单中选择**启用电话登录**。</span><span class="sxs-lookup"><span data-stu-id="ee76c-130">Return to the accounts page and choose **Enable phone sign-in** from the account dropdown menu.</span></span>

## <a name="how-to-sign-in-to-surface-hub-during-a-meeting"></a><span data-ttu-id="ee76c-131">如何在会议期间登录 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="ee76c-131">How to sign in to Surface Hub during a meeting</span></span>

1. <span data-ttu-id="ee76c-132">在设置会议后，转到 Surface Hub 并选择**登录即可查看你的会议和文件**。</span><span class="sxs-lookup"><span data-stu-id="ee76c-132">After you’ve set up a meeting, go to the Surface Hub and select **Sign in to see your meetings and files**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="ee76c-133">如果你不确定如何在 Surface Hub 上计划会议，请参阅[在 Surface Hub 上计划会议](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting)。</span><span class="sxs-lookup"><span data-stu-id="ee76c-133">If you’re not sure how to schedule a meeting on a Surface Hub, see [Schedule a meeting on Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span></span>

    ![Surface Hub 上“登录”选项的屏幕截图](images/sign-in.png)

2. <span data-ttu-id="ee76c-135">你将看到被邀请参加会议的人员的列表。</span><span class="sxs-lookup"><span data-stu-id="ee76c-135">You’ll see a list of the people invited to the meeting.</span></span> <span data-ttu-id="ee76c-136">选择你自己（或者想要登录的人员 - 确保此人在会议之前已经完成了设置设备的步骤），然后选择**继续**。</span><span class="sxs-lookup"><span data-stu-id="ee76c-136">Select yourself (or the person who wants to sign in – make sure this person has gone through the steps to set up their device before your meeting), and then select **Continue**.</span></span>

    ![会议中与会者列表的屏幕截图](images/attendees.png)

    <span data-ttu-id="ee76c-138">你将在 Surface Hub 上看到一个代码。</span><span class="sxs-lookup"><span data-stu-id="ee76c-138">You'll see a code on the Surface Hub.</span></span>

    ![“批准登录”的代码屏幕截图](images/approve-signin.png)

3. <span data-ttu-id="ee76c-140">若要批准登录，请打开 Authenticator 应用，输入 Surface Hub 上显示的四位数代码，然后选择**批准**。</span><span class="sxs-lookup"><span data-stu-id="ee76c-140">To approve the sign-in, open the Authenticator app, enter the four-digit code that’s displayed on the Surface Hub, and select **Approve**.</span></span> <span data-ttu-id="ee76c-141">然后，系统将请你输入 PIN，或者使用你的指纹完成登录。</span><span class="sxs-lookup"><span data-stu-id="ee76c-141">You will then be asked to enter the PIN or use your fingerprint to complete the sign in.</span></span> 

    ![Microsoft Authenticator 中“批准登录”屏幕的屏幕截图](images/approve-signin2.png)

<span data-ttu-id="ee76c-143">现在，你可以通过 OneDrive 应用访问所有文件。</span><span class="sxs-lookup"><span data-stu-id="ee76c-143">You can now access all files through the OneDrive app.</span></span>

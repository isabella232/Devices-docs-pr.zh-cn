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
# <a name="first-time-setup-for-surface-hub-2s"></a><span data-ttu-id="af533-104">Surface Hub 2S 首次设置</span><span class="sxs-lookup"><span data-stu-id="af533-104">First time Setup for Surface Hub 2S</span></span>

<span data-ttu-id="af533-105">首次启动 Surface Hub 2S 时，设备会自动进入首次设置模式，以指导你完成帐户配置和相关设置。</span><span class="sxs-lookup"><span data-stu-id="af533-105">When you first start Surface Hub 2S, the device automatically enters first time Setup mode to guide you through account configuration and related settings.</span></span>

## <a name="configuring-surface-hub-2s-account"></a><span data-ttu-id="af533-106">配置 Surface Hub 2S 帐户</span><span class="sxs-lookup"><span data-stu-id="af533-106">Configuring Surface Hub 2S account</span></span>

1. **<span data-ttu-id="af533-107">配置区域设置。</span><span class="sxs-lookup"><span data-stu-id="af533-107">Configure your locale.</span></span>** <span data-ttu-id="af533-108">输入区域、语言、键盘布局和时区信息。</span><span class="sxs-lookup"><span data-stu-id="af533-108">Enter region, language, keyboard layout and time zone information.</span></span> <span data-ttu-id="af533-109">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="af533-109">Select **Next**.</span></span>

   ![\* 配置区域设置 \*](images/sh2-run1.png)

1. **<span data-ttu-id="af533-111">连接到无线网络。</span><span class="sxs-lookup"><span data-stu-id="af533-111">Connect  to a wireless network.</span></span>** <span data-ttu-id="af533-112">选择首选无线网络，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="af533-112">Choose your preferred wireless network and select **Next.**</span></span>

   - <span data-ttu-id="af533-113">如果使用以太网电缆进行连接，则不显示此选项。</span><span class="sxs-lookup"><span data-stu-id="af533-113">This option is not shown if connected using an Ethernet cable.</span></span>

   - <span data-ttu-id="af533-114">你无法连接到热点的无线网络 (强制门户) 将登录请求重定向到提供商的网站。</span><span class="sxs-lookup"><span data-stu-id="af533-114">You cannot connect to a wireless network in hotspots (captive portals) that redirect sign-in requests to a provider's website.</span></span>

3. **<span data-ttu-id="af533-115">输入设备帐户信息。</span><span class="sxs-lookup"><span data-stu-id="af533-115">Enter device account info.</span></span>** <span data-ttu-id="af533-116">将 **domain\user** 用于内部部署和混合环境，将 **user\@example.com** 用于联机环境。</span><span class="sxs-lookup"><span data-stu-id="af533-116">Use **domain\user** for on-premises and hybrid environments and **user\@example.com** for online environments.</span></span> <span data-ttu-id="af533-117">选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="af533-117">Select **Next.**</span></span>

   ![\* 输入设备帐户信息 \*](images/sh2-run2.png)

1. **<span data-ttu-id="af533-119">输入其他信息。</span><span class="sxs-lookup"><span data-stu-id="af533-119">Enter additional info.</span></span>** <span data-ttu-id="af533-120">如果需要，请提供 Exchange 服务器地址，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="af533-120">If requested, provide your Exchange server address and then select **Next.**</span></span>

   ![\* 输入详细信息;例如，Exchange 服务器名称\*](images/sh2-run3.png)

1. **<span data-ttu-id="af533-122">为此设备命名。</span><span class="sxs-lookup"><span data-stu-id="af533-122">Name this device.</span></span>** <span data-ttu-id="af533-123">输入设备名称或使用基于帐户名称和用户原则名称 [UPN] 显示名称建议的名称。</span><span class="sxs-lookup"><span data-stu-id="af533-123">Enter a name for your device or use the suggested one based on your account’s display name and user principle name [UPN].</span></span> <span data-ttu-id="af533-124">**选择"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="af533-124">**Select Next**.</span></span>

   - <span data-ttu-id="af533-125">友好 **名称** 显示在 Surface Hub 2S 的左下角，在计划到设备时显示。</span><span class="sxs-lookup"><span data-stu-id="af533-125">The **Friendly name** is visible on the bottom left corner of Surface Hub 2S and is shown when projecting to the device.</span></span>

   - <span data-ttu-id="af533-126">设备 **名称** 标识与 Active Directory 或 Azure Active Directory 关联时的设备，以及向 Intune 注册设备时。</span><span class="sxs-lookup"><span data-stu-id="af533-126">The **Device name** identifies the device when affiliated with Active Directory or Azure Active Directory, and when enrolling the device with Intune.</span></span>

   ![\* 为此设备命名\*](images/sh2-run4.png)
 

## <a name="configuring-device-admin-accounts"></a><span data-ttu-id="af533-128">配置设备管理员帐户</span><span class="sxs-lookup"><span data-stu-id="af533-128">Configuring device admin accounts</span></span>

<span data-ttu-id="af533-129">只能在第一次安装期间设置设备管理员。</span><span class="sxs-lookup"><span data-stu-id="af533-129">You can only set up device admins during first time Setup.</span></span> <span data-ttu-id="af533-130">有关详细信息，请参阅 Surface [Hub 2S 设备附属关系](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)。</span><span class="sxs-lookup"><span data-stu-id="af533-130">For more information, refer to [Surface Hub 2S device affiliation](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation).</span></span>

<span data-ttu-id="af533-131">在 **"此设备的安装管理员** "窗口中，选择以下选项之一：Active Directory 域服务、Azure Active Directory 或本地管理员。</span><span class="sxs-lookup"><span data-stu-id="af533-131">In the **Setup admins for this device** window, select one of the following options: Active Directory Domain Services, Azure Active Directory, or Local admin.</span></span>

![\* 此设备的安装程序管理员 \*](images/sh2-run5.png)

### <a name="active-directory-domain-services"></a><span data-ttu-id="af533-133">Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="af533-133">Active Directory Domain Services</span></span>

1. <span data-ttu-id="af533-134">输入有权将设备加入 Active Directory 的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="af533-134">Enter the credentials of a user who has permissions to join the device to Active Directory.</span></span>

    ![\* 使用域加入设置管理员 \*](images/sh2-run6.png)

2. <span data-ttu-id="af533-136">选择 Active Directory 安全组，其中包含允许登录到 Surface Hub 2S 上的"设置"应用的成员。</span><span class="sxs-lookup"><span data-stu-id="af533-136">Select the Active Directory Security Group containing members allowed to log on to the Settings app on Surface Hub 2S.</span></span>

   ![\* 输入安全组 \*](images/sh2-run7.png)

1. <span data-ttu-id="af533-138">选择"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="af533-138">Select **Finish**.</span></span> <span data-ttu-id="af533-139">设备将启动。</span><span class="sxs-lookup"><span data-stu-id="af533-139">The device will restart.</span></span>

### <a name="azure-active-directory"></a><span data-ttu-id="af533-140">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="af533-140">Azure Active Directory</span></span>

<span data-ttu-id="af533-141">选择将设备与 Azure Active Directory 关联时，设备将立即重新启动并显示以下页面。</span><span class="sxs-lookup"><span data-stu-id="af533-141">When choosing to affiliate your device with Azure Active Directory, the device will immediately restart and display the following page.</span></span>

![\* 如果你的组织使用 Office 365 或 Microsoft 的其他商业服务，我们将向你的组织注册此设备\*](images/sh2-run8.png)

1. <span data-ttu-id="af533-143">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="af533-143">Select **Next**.</span></span>

1. <span data-ttu-id="af533-144">输入具有 Intune 计划 **1** 或更大应用的帐户的电子邮件地址或 UPN，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="af533-144">Enter the email address or UPN of an account **with Intune Plan 1** or greater and then select **Next.**</span></span>

   ![\* 输入工作或学校帐户\*](images/sh2-run9.png)

1. <span data-ttu-id="af533-146">如果重定向，则使用组织的登录页进行身份验证，并提供其他登录信息（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="af533-146">If redirected, authenticate using your organization’s sign-in page and provide additional logon information if requested.</span></span> <span data-ttu-id="af533-147">设备将启动。</span><span class="sxs-lookup"><span data-stu-id="af533-147">The device will restart.</span></span>

## <a name="local-administrator-account"></a><span data-ttu-id="af533-148">本地管理员帐户</span><span class="sxs-lookup"><span data-stu-id="af533-148">Local Administrator account</span></span>

- <span data-ttu-id="af533-149">输入本地管理员的用户名和密码。设备将重新启动。</span><span class="sxs-lookup"><span data-stu-id="af533-149">Enter a username and password for your local admin. The device will restart.</span></span>

  ![\* 设置管理员帐户\*](images/sh2-run10.png)
 
## <a name="using-provisioning-packages"></a><span data-ttu-id="af533-151">使用预配包</span><span class="sxs-lookup"><span data-stu-id="af533-151">Using provisioning packages</span></span>

<span data-ttu-id="af533-152">如果在启动 Surface Hub 2S 时将包含预配包的 U 盘插入其中一个 USB 端口，设备将显示以下页面。</span><span class="sxs-lookup"><span data-stu-id="af533-152">If you insert a USB thumb drive with a provisioning package into one of the USB ports when you start Surface Hub 2S, the device displays the following page.</span></span>

1. <span data-ttu-id="af533-153">输入请求的设置，然后选择"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="af533-153">Enter the requested settings and select **Set up**.</span></span>

   ![\* 输入预配包的区域设置\*](images/sh2-run11.png)

   ![\* 从可移动媒体预配此设备\*](images/sh2-run12.png)

2. <span data-ttu-id="af533-156">选择你要使用的预配包。</span><span class="sxs-lookup"><span data-stu-id="af533-156">Choose the provisioning package you’d like to use.</span></span>

   ![\* 选择要使用的预配包\*](images/sh2-run13.png)

3. <span data-ttu-id="af533-158">如果你创建了多台设备 CSV 文件，你将可以选择设备配置。</span><span class="sxs-lookup"><span data-stu-id="af533-158">If you created a multiple devices CSV file, you will be able to choose a device configuration.</span></span> <span data-ttu-id="af533-159">有关详细信息，请参阅创建 [Surface Hub 2S 的预配包](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file)。</span><span class="sxs-lookup"><span data-stu-id="af533-159">For more information, refer to [Create provisioning packages for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).</span></span>

   ![\* 从配置文件中选择设备帐户和友好名称\*](images/sh2-run14.png)

4. <span data-ttu-id="af533-161">按照说明完成首次安装。</span><span class="sxs-lookup"><span data-stu-id="af533-161">Follow the instructions to complete first time Setup.</span></span>

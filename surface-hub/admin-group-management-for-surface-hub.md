---
title: 管理员组管理
description: 通过在 Microsoft Surface Hub 上打开“设置”应用，可分别配置每台设备。
ms.assetid: FA67209E-B355-4333-B903-482C4A3BDCCE
ms.reviewer: ''
manager: laurawi
keywords: 管理员组管理, “设置”应用, 配置 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: medium
ms.openlocfilehash: 36c6010307603b36b8798a09aed26f8b337b2c1b
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "11311948"
---
# <span data-ttu-id="61f54-104">Surface Hub 的管理员组管理</span><span class="sxs-lookup"><span data-stu-id="61f54-104">Admin group management for Surface Hub</span></span>


<span data-ttu-id="61f54-105">可使用设备上的“设置”应用在本地配置每个 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="61f54-105">Every Surface Hub can be configured locally using the Settings app on the device.</span></span> <span data-ttu-id="61f54-106">若要防止未经授权的用户更改设置，“设置”应用要求使用管理员凭据打开该应用。</span><span class="sxs-lookup"><span data-stu-id="61f54-106">To prevent unauthorized users from changing settings, the Settings app requires admin credentials to open the app.</span></span>


## <span data-ttu-id="61f54-107">管理员组管理</span><span class="sxs-lookup"><span data-stu-id="61f54-107">Admin Group Management</span></span>

<span data-ttu-id="61f54-108">可以通过以下方式为设备设置管理员帐户：</span><span class="sxs-lookup"><span data-stu-id="61f54-108">You can set up administrator accounts for the device in the following ways:</span></span>

- [<span data-ttu-id="61f54-109">创建本地管理员帐户</span><span class="sxs-lookup"><span data-stu-id="61f54-109">Create a local admin account</span></span>](#create-a-local-admin-account)
- [<span data-ttu-id="61f54-110">将设备加入 Active Directory 的域</span><span class="sxs-lookup"><span data-stu-id="61f54-110">Domain join the device to Active Directory</span></span>](#domain-join-the-device-to-active-directory)
- [<span data-ttu-id="61f54-111">Azure AD 加入设备</span><span class="sxs-lookup"><span data-stu-id="61f54-111">Azure AD join the device</span></span>](#azure-ad-join-the-device)
- [<span data-ttu-id="61f54-112">在已加入 Azure AD 的设备上配置非全局管理员帐户 (Surface Hub 2S) </span><span class="sxs-lookup"><span data-stu-id="61f54-112">Configure non Global admin accounts on Azure AD joined devices (Surface Hub 2S)</span></span>](#configure-non-global-admin-accounts-on-azure-ad-joined-devices)


### <span data-ttu-id="61f54-113">创建本地管理员帐户</span><span class="sxs-lookup"><span data-stu-id="61f54-113">Create a local admin account</span></span>

<span data-ttu-id="61f54-114">若要创建本地管理员，[请在首次运行期间选择使用本地管理员](first-run-program-surface-hub.md#use-a-local-admin)。</span><span class="sxs-lookup"><span data-stu-id="61f54-114">To create a local admin, [choose to use a local admin during first run](first-run-program-surface-hub.md#use-a-local-admin).</span></span> <span data-ttu-id="61f54-115">这将使用所选的用户名和密码在 Surface Hub 上创建一个本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="61f54-115">This will create a single local admin account on the Surface Hub with the username and password of your choice.</span></span> <span data-ttu-id="61f54-116">使用这些凭据打开“设置”应用。 </span><span class="sxs-lookup"><span data-stu-id="61f54-116">Use these credentials to open the Settings app.</span></span>

<span data-ttu-id="61f54-117">注意：任何目录服务都不会备份本地管理员帐户信息。</span><span class="sxs-lookup"><span data-stu-id="61f54-117">Note that the local admin account information is not backed by any directory service.</span></span> <span data-ttu-id="61f54-118">我们建议你仅当设备无权访问 Active Directory (AD) 或 Azure Active Directory (Azure AD) 时，才选择本地管理员。</span><span class="sxs-lookup"><span data-stu-id="61f54-118">We recommend you only choose a local admin if the device does not have access to Active Directory (AD) or Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="61f54-119">如果决定更改本地管理员的密码，可在“设置”中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="61f54-119">If you decide to change the local admin’s password, you can do so in Settings.</span></span> <span data-ttu-id="61f54-120">但是，如果想要从使用本地管理员帐户更改为使用域或 Azure AD 租户的组，则需要[重置该设备](device-reset-surface-hub.md)，并再次完成首次计划。</span><span class="sxs-lookup"><span data-stu-id="61f54-120">However, if you want to change from using the local admin account to using a group from your domain or Azure AD tenant, then you’ll need to [reset the device](device-reset-surface-hub.md) and go through the first-time program again.</span></span>

### <span data-ttu-id="61f54-121">将设备加入 Active Directory 的域</span><span class="sxs-lookup"><span data-stu-id="61f54-121">Domain join the device to Active Directory</span></span>

<span data-ttu-id="61f54-122">可将 Surface Hub 加入 AD 域，支持指定安全组的用户配置设置。</span><span class="sxs-lookup"><span data-stu-id="61f54-122">You can domain join the Surface Hub to your AD domain to allow users from a specified security group to configure settings.</span></span> <span data-ttu-id="61f54-123">在首次运行时，选择使用[Active Directory 域服务](first-run-program-surface-hub.md#use-active-directory-domain-services)。</span><span class="sxs-lookup"><span data-stu-id="61f54-123">During first run, choose to use [Active Directory Domain Services](first-run-program-surface-hub.md#use-active-directory-domain-services).</span></span> <span data-ttu-id="61f54-124">需要提供可加入所选域的凭据以及现有安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="61f54-124">You'll need to provide credentials that are capable of joining the domain of your choice, and the name of an existing security group.</span></span> <span data-ttu-id="61f54-125">属于该安全组成员的任何人都可以输入其凭据并解锁“设置”。</span><span class="sxs-lookup"><span data-stu-id="61f54-125">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>

#### <span data-ttu-id="61f54-126">将 Surface Hub 加入域时会发生什么？</span><span class="sxs-lookup"><span data-stu-id="61f54-126">What happens when you domain join your Surface Hub?</span></span>
<span data-ttu-id="61f54-127">将 Surface Hub 加入域可：</span><span class="sxs-lookup"><span data-stu-id="61f54-127">Surface Hubs use domain join to:</span></span>
- <span data-ttu-id="61f54-128">将管理员权限授予 AD 中指定安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="61f54-128">Grant admin rights to members of a specified security group in AD.</span></span>
- <span data-ttu-id="61f54-129">将设备的 BitLocker 恢复密钥存储在 AD 中的计算机对象下，备份该密钥。</span><span class="sxs-lookup"><span data-stu-id="61f54-129">Backup the device's BitLocker recovery key by storing it under the computer object in AD.</span></span> <span data-ttu-id="61f54-130">有关详细信息，请参阅[保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="61f54-130">See [Save your BitLocker key](save-bitlocker-key-surface-hub.md) for details.</span></span>
- <span data-ttu-id="61f54-131">同步系统时钟和域控制器，进行加密通信</span><span class="sxs-lookup"><span data-stu-id="61f54-131">Synchronize the system clock with the domain controller for encrypted communication</span></span>

<span data-ttu-id="61f54-132">Surface Hub 不支持在域控制器中应用组策略或证书。</span><span class="sxs-lookup"><span data-stu-id="61f54-132">Surface Hub does not support applying group policies or certificates from the domain controller.</span></span>

> [!NOTE]
> <span data-ttu-id="61f54-133">如果 Surface Hub 失去与域的信任（例如，如果在 Surface Hub 加入域后，将其从该域中删除），将无法对设备进行身份验证并打开“设置”。</span><span class="sxs-lookup"><span data-stu-id="61f54-133">If your Surface Hub loses trust with the domain (for example, if you remove the Surface Hub from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="61f54-134">当决定删除 Surface Hub 与域的信任关系时，首先要[重置设备](device-reset-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="61f54-134">If you decide to remove the trust relationship of the Surface Hub with your domain, [reset the device](device-reset-surface-hub.md) first.</span></span>


### <span data-ttu-id="61f54-135">Azure AD 加入设备</span><span class="sxs-lookup"><span data-stu-id="61f54-135">Azure AD join the device</span></span>

<span data-ttu-id="61f54-136">你可以将 Azure Active Directory (Azure AD) Surface Hub，以允许来自 Azure AD 租户的 IT 专业人员配置设置。</span><span class="sxs-lookup"><span data-stu-id="61f54-136">You can Azure Active Directory (Azure AD) to join the Surface Hub to allow IT pros from your Azure AD tenant to configure settings.</span></span> <span data-ttu-id="61f54-137">在首次运行时，选择使用[Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="61f54-137">During first run, choose to use [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory).</span></span> <span data-ttu-id="61f54-138">将需要提供能够加入所选 Azure AD 租户的凭据。</span><span class="sxs-lookup"><span data-stu-id="61f54-138">You will need to provide credentials that are capable of joining the Azure AD tenant of your choice.</span></span> <span data-ttu-id="61f54-139">成功加入 Azure AD 后，将授予相应用户该设备的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="61f54-139">After you successfully Azure AD join, the appropriate people will be granted admin rights on the device.</span></span>

<span data-ttu-id="61f54-140">默认情况下，所有**全局管理员**都将授予加入 Azure AD 的 Surface Hub 的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="61f54-140">By default, all **global administrators** will be given admin rights on an Azure AD joined Surface Hub.</span></span> <span data-ttu-id="61f54-141">凭借 **Azure AD Premium** 或 **Enterprise Mobility Suite (EMS)** 可添加其他管理员：</span><span class="sxs-lookup"><span data-stu-id="61f54-141">With **Azure AD Premium** or **Enterprise Mobility Suite (EMS)**, you can add additional administrators:</span></span>
1.  <span data-ttu-id="61f54-142">在 [Azure 经典门户](https://manage.windowsazure.com/)中，单击“Active Directory”\*\*\*\*，然后单击组织目录的名称。</span><span class="sxs-lookup"><span data-stu-id="61f54-142">In the [Azure classic portal](https://manage.windowsazure.com/), click **Active Directory**, and then click the name of your organization's directory.</span></span>
2.  <span data-ttu-id="61f54-143">在“配置”\*\*\*\* 页面的“设备”\*\*\*\* > “Azure AD 联接设备上的其他管理员”\*\*\*\* 下，单击“已选定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="61f54-143">On the **Configure** page, under **Devices** > **Additional administrators on Azure AD joined devices**, click **Selected**.</span></span>
3.  <span data-ttu-id="61f54-144">单击“添加”\*\*\*\*，选择在 Surface Hub 和其他 Azure AD 联结设备上以管理员身份希望添加的用户。</span><span class="sxs-lookup"><span data-stu-id="61f54-144">Click **Add**, and select the users you want to add as administrators on your Surface Hub and other Azure AD joined devices.</span></span>
4.  <span data-ttu-id="61f54-145">结束后，单击复选标记按钮，保存更改。</span><span class="sxs-lookup"><span data-stu-id="61f54-145">When you have finished, click the checkmark button to save your change.</span></span>

#### <span data-ttu-id="61f54-146">将 Surface Hub 加入 Azure AD 时会发生什么？</span><span class="sxs-lookup"><span data-stu-id="61f54-146">What happens when you Azure AD join your Surface Hub?</span></span>
<span data-ttu-id="61f54-147">Surface Hub 加入 Azure AD 可：</span><span class="sxs-lookup"><span data-stu-id="61f54-147">Surface Hubs use Azure AD join to:</span></span>
- <span data-ttu-id="61f54-148">将管理员权限授予 Azure AD 租户中的相应用户。</span><span class="sxs-lookup"><span data-stu-id="61f54-148">Grant admin rights to the appropriate users in your Azure AD tenant.</span></span>
- <span data-ttu-id="61f54-149">将设备的 BitLocker 恢复密钥存储在加入 Azure AD 的设备帐户下，备份该密钥。</span><span class="sxs-lookup"><span data-stu-id="61f54-149">Backup the device's BitLocker recovery key by storing it under the account that was used to Azure AD join the device.</span></span> <span data-ttu-id="61f54-150">有关详细信息，请参阅[保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="61f54-150">See [Save your BitLocker key](save-bitlocker-key-surface-hub.md) for details.</span></span>

#### <span data-ttu-id="61f54-151">通过 Azure Active Directory 加入自动注册</span><span class="sxs-lookup"><span data-stu-id="61f54-151">Automatic enrollment via Azure Active Directory join</span></span>

<span data-ttu-id="61f54-152">Surface Hub 现在支持通过将设备加入 Azure Active Directory 在 Intune 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="61f54-152">Surface Hub now supports the ability to automatically enroll in Intune by joining the device to Azure Active Directory.</span></span> 

<span data-ttu-id="61f54-153">有关详细信息，请参阅启用 [Windows 10 自动注册](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="61f54-153">For more information, see [Enable Windows 10 automatic enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>

#### <span data-ttu-id="61f54-154">我应该选择哪一个？</span><span class="sxs-lookup"><span data-stu-id="61f54-154">Which should I choose?</span></span>

<span data-ttu-id="61f54-155">如果组织使用的是 AD 或 Azure AD，我们建议选择“域加入”或“Azure AD 加入”，这主要是出于安全方面的原因。</span><span class="sxs-lookup"><span data-stu-id="61f54-155">If your organization is using AD or Azure AD, we recommend you either domain join or Azure AD join, primarily for security reasons.</span></span> <span data-ttu-id="61f54-156">用户将能够使用自己的凭据进行身份验证和解锁“设置”，并且可移入或移出与域相关联的安全组。</span><span class="sxs-lookup"><span data-stu-id="61f54-156">People will be able to authenticate and unlock Settings with their own credentials, and can be moved in or out of the security groups associated with your domain.</span></span>

| <span data-ttu-id="61f54-157">选项</span><span class="sxs-lookup"><span data-stu-id="61f54-157">Option</span></span>                                            | <span data-ttu-id="61f54-158">要求</span><span class="sxs-lookup"><span data-stu-id="61f54-158">Requirements</span></span>                            | <span data-ttu-id="61f54-159">哪些凭据可用于访问“设置”应用？</span><span class="sxs-lookup"><span data-stu-id="61f54-159">Which credentials can be used to access the Settings app?</span></span>  |
|---------------------------------------------------|-----------------------------------------|-------|
| <span data-ttu-id="61f54-160">创建本地管理员帐户</span><span class="sxs-lookup"><span data-stu-id="61f54-160">Create a local admin account</span></span>                      | <span data-ttu-id="61f54-161">无</span><span class="sxs-lookup"><span data-stu-id="61f54-161">None</span></span>                                    | <span data-ttu-id="61f54-162">首次运行时指定的用户名和密码</span><span class="sxs-lookup"><span data-stu-id="61f54-162">The user name and password specified during first run</span></span> |
| <span data-ttu-id="61f54-163">加入 Active Directory (AD) 域</span><span class="sxs-lookup"><span data-stu-id="61f54-163">Domain join to Active Directory (AD)</span></span>              | <span data-ttu-id="61f54-164">组织使用 AD</span><span class="sxs-lookup"><span data-stu-id="61f54-164">Your organization uses AD</span></span>               | <span data-ttu-id="61f54-165">域中特定安全组的任意 AD 用户</span><span class="sxs-lookup"><span data-stu-id="61f54-165">Any AD user from a specific security group in your domain</span></span> |
| <span data-ttu-id="61f54-166">将设备加入 Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="61f54-166">Azure Active Directory (Azure AD) join the device</span></span> | <span data-ttu-id="61f54-167">组织使用 Azure AD Basic</span><span class="sxs-lookup"><span data-stu-id="61f54-167">Your organization uses Azure AD Basic</span></span>   | <span data-ttu-id="61f54-168">仅限全局管理员</span><span class="sxs-lookup"><span data-stu-id="61f54-168">Global administrators only</span></span> |
| &nbsp;                                            | <span data-ttu-id="61f54-169">组织使用 Azure AD Premium 或 Enterprise Mobility Suite (EMS)</span><span class="sxs-lookup"><span data-stu-id="61f54-169">Your organization uses Azure AD Premium or Enterprise Mobility Suite (EMS)</span></span> | <span data-ttu-id="61f54-170">全局管理员和其他管理员</span><span class="sxs-lookup"><span data-stu-id="61f54-170">Global administrators and additional administrators</span></span> |


### <span data-ttu-id="61f54-171">在加入 Azure AD 的设备上配置非全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="61f54-171">Configure non Global admin accounts on Azure AD-joined devices</span></span>

<span data-ttu-id="61f54-172">对于加入 Azure AD 的 Surface Hub 2S 设备，Windows 10 Team 2020 更新允许你将管理员权限限制为在 Surface Hub 2S 上管理"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="61f54-172">For Surface Hub 2S devices joined to Azure AD, Windows 10 Team 2020 Update lets you limit admin permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="61f54-173">这使你能够仅作用域 Surface Hub 2S 的管理员权限，并阻止可能不需要的管理员访问整个 Azure AD 域。</span><span class="sxs-lookup"><span data-stu-id="61f54-173">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access an entire Azure AD domain.</span></span> <span data-ttu-id="61f54-174">若要了解更多信息，请参阅 [在 Surface Hub 2S 上配置非全局管理员帐户](surface-hub-2s-nonglobal-admin.md)。</span><span class="sxs-lookup"><span data-stu-id="61f54-174">To learn more, see [Configure non Global admin accounts on Surface Hub 2S](surface-hub-2s-nonglobal-admin.md).</span></span>
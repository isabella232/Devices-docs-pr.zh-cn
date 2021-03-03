---
title: 配置 Surface Hub 2 上的非全局管理员帐户
description: 本文介绍如何配置非全局管理员帐户以管理 Surface Hub 2S。
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: e16e4f8bd4b2b253233fa9790987287cf17966c7
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385170"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub-2s"></a><span data-ttu-id="a1ae0-104">配置 Surface Hub 2 上的非全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="a1ae0-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="a1ae0-105">将 Surface Hub 2S 加入 Azure AD 域时，可以配置非全局管理员帐户，这些帐户限制对 Surface Hub 2S 上"设置"应用的管理权限。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="a1ae0-106">这使你能够仅确定 Surface Hub 2S 的管理员权限范围，并在整个 Azure AD 域中阻止可能不需要的管理员访问权限。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="a1ae0-107">开始之前，请确保 Surface Hub 2S 已加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="a1ae0-108">如果没有，则需要重置 Surface Hub 2S，并完成首次、开箱即用 (OOBE) 安装程序，选择加入 Azure AD 的选项。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="a1ae0-109">摘要</span><span class="sxs-lookup"><span data-stu-id="a1ae0-109">Summary</span></span> 

<span data-ttu-id="a1ae0-110">创建非全局管理员帐户的过程包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a1ae0-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="a1ae0-111">在 Microsoft Intune 中，创建一个安全组，其中包含指定为管理 Surface Hub 2S 的管理员。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="a1ae0-112">使用 PowerShell 获取 Azure AD 组 SID。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="a1ae0-113">创建包含 Azure AD 组 SID 的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="a1ae0-114">创建一个安全组，其中包含由非全局管理员安全组管理的 Surface Hub 2S 设备。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="a1ae0-115">创建自定义配置文件，以包含 Surface Hub 2S 设备的安全组为目标。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="a1ae0-116">创建 Azure AD 安全组</span><span class="sxs-lookup"><span data-stu-id="a1ae0-116">Create Azure AD security groups</span></span>

<span data-ttu-id="a1ae0-117">首先创建一个包含管理员帐户的安全组。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="a1ae0-118">然后为 Surface Hub 设备创建另一个安全组。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="a1ae0-119">为管理员帐户创建安全组</span><span class="sxs-lookup"><span data-stu-id="a1ae0-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="a1ae0-120">通过 Microsoft Endpoint [Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心登录 Intune，**选择组**新组>组类型下，选择  >  \*\*\*\*\*\*"安全"。\*\*</span><span class="sxs-lookup"><span data-stu-id="a1ae0-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="a1ae0-121">输入组名称（例如 Surface **Hub 本地管理员** ）然后选择" **创建"。**</span><span class="sxs-lookup"><span data-stu-id="a1ae0-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![为中心管理员创建安全组](images/sh-create-sec-group.png)

3. <span data-ttu-id="a1ae0-123">打开组，选择 **"成员**"，然后选择"\*\*\*\* 添加成员"以输入你希望在 Surface Hub 2S 上指定为非全局管理员的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="a1ae0-124">若要了解有关在 Intune 中创建组的信息，请参阅"  [添加组"以组织用户和设备](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-2s-devices"></a><span data-ttu-id="a1ae0-125">为 Surface Hub 2S 设备创建安全组</span><span class="sxs-lookup"><span data-stu-id="a1ae0-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="a1ae0-126">重复上述过程，为集线器设备创建单独的安全组;例如 **，Surface Hub 设备**。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![为集线器设备创建安全组](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="a1ae0-128">使用 PowerShell 获取 Azure AD 组 SID</span><span class="sxs-lookup"><span data-stu-id="a1ae0-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="a1ae0-129">使用提升的帐户权限启动 PowerShell (**以** 管理员) ，并确保系统配置为运行 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="a1ae0-130">若要了解详情，请参阅"[关于执行策略"。](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)</span><span class="sxs-lookup"><span data-stu-id="a1ae0-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="a1ae0-131">[安装 Azure PowerShell 模块](https://docs.microsoft.com/powershell/azure/install-az-ps)。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="a1ae0-132">登录到 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="a1ae0-133">登录租户后，运行以下命令let。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="a1ae0-134">它将提示你"请键入 Azure AD 组的对象 ID"。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="a1ae0-135">在 Intune 中，选择之前创建的组并复制对象 ID，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![复制安全组的对象 ID](images/sh-objectid.png)

6. <span data-ttu-id="a1ae0-137">运行以下命令let 获取安全组的 SID：</span><span class="sxs-lookup"><span data-stu-id="a1ae0-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="a1ae0-138">将对象 ID 粘贴到 PowerShell 命令let 中，按 **Enter，** 然后将 **Azure AD 组 SID** 复制到文本编辑器中。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="a1ae0-139">创建包含 Azure AD 组 SID 的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="a1ae0-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="a1ae0-140">将以下内容复制到文本编辑器中：</span><span class="sxs-lookup"><span data-stu-id="a1ae0-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="a1ae0-141">将占位符 SID (S-1-12-1) **Azure AD 组 SID，** 然后将文件另存为 XML;例如 \*\* ，aad-local-admin.xml\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="a1ae0-142">创建自定义配置文件</span><span class="sxs-lookup"><span data-stu-id="a1ae0-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="a1ae0-143">在终结点管理器中，**选择"设备**  >  **配置文件创建**  >  **配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="a1ae0-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="a1ae0-144">在"平台" **下选择 Windows 10 及更高版本。**</span><span class="sxs-lookup"><span data-stu-id="a1ae0-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="a1ae0-145">在"配置文件"下 **，选择"** 自定义"，然后选择" **创建"。**</span><span class="sxs-lookup"><span data-stu-id="a1ae0-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="a1ae0-146">添加名称和说明，然后选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="a1ae0-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="a1ae0-147">在 **"配置设置**  >  **OMA-URI 设置**"下，选择 **"添加"。**</span><span class="sxs-lookup"><span data-stu-id="a1ae0-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="a1ae0-148">在"添加行"窗格中，添加名称，在     **OMA-URI**下添加以下字符串：</span><span class="sxs-lookup"><span data-stu-id="a1ae0-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="a1ae0-149">在"数据类型"下，选择 **字符串 XML** 并浏览以打开在上一步中创建的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![上载本地管理员 xml 配置文件](images/sh-local-admin-config.png)

7. <span data-ttu-id="a1ae0-151">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-151">Click **Save**.</span></span>
8. <span data-ttu-id="a1ae0-152">单击 **"选择要包含的安全组**"，[](#create-security-group-for-surface-hub-2s-devices)然后选择之前在 Surface Hub (**创建) 。**</span><span class="sxs-lookup"><span data-stu-id="a1ae0-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="a1ae0-153">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-153">Click **Next.**</span></span>
9. <span data-ttu-id="a1ae0-154">在"适用性规则"下，根据需要添加规则。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="a1ae0-155">否则，请选择 **"下一步**"，然后选择"**创建"。**</span><span class="sxs-lookup"><span data-stu-id="a1ae0-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="a1ae0-156">若要了解有关使用 OMA-URI 字符串的自定义配置文件，请参阅 Intune 中的 [Windows 10 设备的自定义设置](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub-2s"></a><span data-ttu-id="a1ae0-157">管理 Surface Hub 2S 的非全局管理员</span><span class="sxs-lookup"><span data-stu-id="a1ae0-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="a1ae0-158">Surface **Hub Local Admins** Security 组的成员现在可以登录到 Surface Hub 2S 上的"设置"应用并管理设置。</span><span class="sxs-lookup"><span data-stu-id="a1ae0-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>

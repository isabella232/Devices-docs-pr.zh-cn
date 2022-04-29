---
title: 配置 Surface Hub 上的非全局管理员帐户
description: 本文介绍如何配置非全局管理员帐户来管理Surface Hub和Surface Hub 2S。
keywords: Surface Hub、Surface Hub v1、Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: be6a6c75155b3c45ae9dda9dd2726033411100c4
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497689"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>配置 Surface Hub 上的非全局管理员帐户

Windows 10 协同版 2020 更新添加了对配置非全局管理员帐户的支持，这些帐户限制Surface Hub已加入Azure AD域的设备上管理设置应用的权限。 这使你能够仅限Surface Hub的管理员权限范围，并防止整个Azure AD域中可能不需要的管理员访问权限。 在开始之前，请确保Surface Hub已加入Azure AD并Intune自动注册。 如果没有，则需要重置Surface Hub并完成首次现 (OOBE) 安装程序，并选择加入Azure AD的选项。

Windows 10 协同版 2020 Update 2 添加了对 [LocalUsersAndGroups 配置服务提供程序](/windows/client-management/mdm/policy-csp-localusersandgroups)的支持。 这将替换 [RestrictedGroups CSP，该 CSP](/windows/client-management/mdm/policy-csp-restrictedgroups) 仍可用，但不再建议使用，如下所述。

## <a name="summary"></a>摘要

创建非全局管理员帐户的过程涉及以下步骤：

1. 在Microsoft Intune中，创建一个安全组，其中包含指定用于管理Surface Hub的管理员。
2. 使用 PowerShell 获取Azure AD组 SID。
3. 创建包含 Azure AD 组 SID 的 XML 文件。
4. 创建包含非全局管理员安全组将管理的Surface Hub设备的安全组。 
5. 创建面向包含Surface Hub设备的安全组的自定义配置文件。

## <a name="create-azure-ad-security-groups"></a>创建Azure AD安全组

首先，创建包含管理员帐户的安全组。 然后为Surface Hub设备创建另一个安全组。  

### <a name="create-security-group-for-admin-accounts"></a>为管理员帐户创建安全组

1. 通过Microsoft Endpoint Manager[管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)登录到Intune，选择 **GroupsNew** **** >  Group >，然后在“组”类型下选择 **“安全性”。**
2. 输入组名称（例如 **，Surface Hub本地管理员**），然后选择 **“创建”。**

     ![为中心管理员创建安全组。](images/sh-create-sec-group.png)

3. 打开组，选择 **“成员**”，然后选择 **“添加成员**”以输入要在Surface Hub上指定为非全局管理员的管理员帐户。 若要详细了解如何在Intune中创建组，请[参阅“添加组”来组织用户和设备](/mem/intune/fundamentals/groups-add)。

### <a name="create-security-group-for-surface-hub-devices"></a>为Surface Hub设备创建安全组

1. 重复上述过程，为中心设备创建单独的安全组;例如，**Surface Hub设备**。

     ![为中心设备创建安全组。](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>使用 PowerShell 获取Azure AD组 SID

1. 使用提升的帐户权限启动 PowerShell (**以管理员身份运行**) 并确保系统配置为运行 PowerShell 脚本。 若要了解详细信息，请参阅 [“关于执行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies?)”。
2. [安装Azure PowerShell模块](/powershell/azure/install-az-ps)。
3. 登录到Azure AD租户。

    ```powershell
    Connect-AzureAD
    ```

4. 登录到租户时，请运行以下命令。 它会提示你“请键入Azure AD组的对象 ID”。

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. 在Intune中，选择之前创建的组并复制对象 ID，如下图所示。

     ![复制安全组的对象 ID。](images/sh-objectid.png)

6. 运行以下命令，获取安全组的 SID：

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. 将对象 ID 粘贴到 PowerShell 命令栏中，按 **Enter**，并将**Azure AD组 SID** 复制到文本编辑器中。

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>创建包含 Azure AD 组 SID 的 XML 文件

1. 将以下内容复制到文本编辑器中：

    ```xml
    <GroupConfiguration>
    <accessgroup desc = "S-1-5-32-544">
        <group action = "U" />
        <add member = "AzureAD\bob@contoso.com"/>
        <add member = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX"/>
    </accessgroup>
    </GroupConfiguration>
    ```
2. 将占位符 SID (从 S-1-12-1) 开始替换**为Azure AD组 SID**，然后将文件保存为 XML;例如 ** ，aad-local-admin.xml**。

      > [!NOTE]
      > 虽然应通过其 SID 指定组，但如果要直接添加 Azure 用户，请使用以下格式指定其用户主体名称 (UPN) ： `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>创建自定义配置文件

1. 在Endpoint Manager中，选择 **“****DevicesConfiguration** >  **profilesCreate** >  配置文件”。
2. 在“平台”下选择**Windows 10及更高版本。** 在“配置文件”下，选择 **“TemplatesCustomCreate** > **** > **”。**
3. 添加名称和说明，然后选择 **“下一步”。**
4. 在**配置设置** > **OMA-URI设置**下，选择 **“添加**”。
5. 在“添加行”窗格中，添加名称并在     **OMA-URI** 下添加以下字符串：

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

   > [!NOTE]
   > **RestrictedGroups/ConfigureGroupMembership** 策略设置还允许你配置成员 (用户或AAD组) 到Windows 10本地组。 但是，它只允许使用新成员完全替换现有组。 不能有选择地添加或删除成员。  在 Windows 10 协同版 2020 Update 2 中提供，建议使用 **LocalUsersandGroups** 策略设置，而不是 RestrictedGroups 策略设置。 将这两个策略设置应用于Surface Hub不受支持，可能会产生不可预知的结果。

6. 在“数据类型”下，选择 **“字符串 XML** ”并浏览以打开在上一步中创建的 XML 文件。

     ![上传本地管理员 xml 配置文件。](images/sh-local-admin-config.png)

7. 单击 **“保存”**。
8. 单击 **“选择组”以包括**之前[创建的安全组](#create-security-group-for-surface-hub-devices) (**Surface Hub设备**) 。 单击“下一步”****。
9. 根据适用性规则，根据需要添加规则。 否则，请选择 **“下一步** ”，然后选择 **“创建**”。

若要了解有关使用 OMA-URI 字符串的自定义配置文件的详细信息，请参阅[Intune中Windows 10设备使用自定义设置](/mem/intune/configuration/custom-settings-windows-10)。

## <a name="non-global-admins-managing-surface-hub"></a>管理Surface Hub的非全局管理员

**Surface Hub本地管理员**安全组的成员现在可以在Surface Hub上登录到设置应用并管理设置。

> [!IMPORTANT]
>  (删除全局管理员对设置应用的默认访问权限，除非他们也是此新安全组) 的成员。

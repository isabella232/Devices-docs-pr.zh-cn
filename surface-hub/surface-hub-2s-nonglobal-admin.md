---
title: 配置 Surface Hub 上的非全局管理员帐户
description: 本文介绍如何配置非全局管理员帐户以管理 Surface Hub 和 Surface Hub 2S。
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
ms.openlocfilehash: 429a7c84605167aa5129999f516c18d17ee30e65
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449295"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>配置 Surface Hub 上的非全局管理员帐户

Windows 10 协同版 2020 更新增加了对配置非全局管理员帐户的支持，这些帐户限制加入 Surface Hub 域的 设置 设备上管理 Azure AD 应用的权限。 这使您能够仅作用域管理员权限Surface Hub并阻止整个域中可能不需要的管理员Azure AD访问。 在开始之前，请确保你的Surface Hub已加入Azure AD和 Intune 自动注册。 如果没有，则需要重置 Surface Hub 并完成首次、开箱即用 (OOBE) 安装程序，选择加入 Azure AD。

Windows 10 协同版 2020 Update 2 增加了对 [LocalUsersAndGroups 配置服务提供程序的支持](/windows/client-management/mdm/policy-csp-localusersandgroups)。 这将替换 [RestrictedGroups CSP](/windows/client-management/mdm/policy-csp-restrictedgroups)，它仍然可用，但不再推荐使用，如下所述。

## <a name="summary"></a>摘要

创建非全局管理员帐户的过程包括以下步骤：

1. 在Microsoft Intune中，创建一个安全组，其中包含指定用于管理Surface Hub。
2. 使用 Azure AD获取组 SID。
3. 创建包含组 SID Azure AD XML 文件。
4. 创建一个安全组Surface Hub非全局管理员安全组将管理的设备。 
5. 创建一个面向包含你的设备的安全组的Surface Hub配置文件。

## <a name="create-azure-ad-security-groups"></a>创建Azure AD安全组

首先，创建一个包含管理员帐户的安全组。 然后为这些设备创建另一Surface Hub组。  

### <a name="create-security-group-for-admin-accounts"></a>为管理员帐户创建安全组

1. 通过管理中心登录 Intune，[Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)**** > 组 **"**"新组">"组类型"下，选择"安全 **"。**
2. 输入组名称（例如，**Surface Hub本地管理员**）然后选择"创建 **"。**

     ![为中心管理员创建安全组。](images/sh-create-sec-group.png)

3. 打开组，选择"**成员**"，然后选择****"添加成员"以输入要指定为非全局管理员的管理员帐户Surface Hub。 若要了解有关在 Intune 中创建组的信息，请参阅添加  [组以组织用户和设备](/mem/intune/fundamentals/groups-add)。

### <a name="create-security-group-for-surface-hub-devices"></a>为设备创建Surface Hub组

1. 重复上述过程，为集线器设备创建单独的安全组;例如，**Surface Hub设备**。

     ![为 Hub 设备创建安全组。](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>使用 powerShell Azure AD组 SID

1. 使用提升的帐户权限启动 PowerShell (**以** 管理员) 并确保系统配置为运行 PowerShell 脚本。 若要了解详情，请参阅关于 [执行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。
2. [安装Azure PowerShell模块](/powershell/azure/install-az-ps)。
3. 登录到你的 Azure AD 租户。

    ```powershell
    Connect-AzureAD
    ```

4. 登录租户后，运行以下命令let。 它将提示你"请键入你的组Azure AD ID"。

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. 在 Intune 中，选择之前创建的组并复制对象 ID，如下图所示。

     ![复制安全组的对象 ID。](images/sh-objectid.png)

6. 运行以下命令let 获取安全组的 SID：

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. 将对象 ID 粘贴到 PowerShell 命令let 中，按 **Enter**，然后将Azure AD **SID** 复制到文本编辑器中。

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>创建包含组 SID Azure AD XML 文件

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
2. 将占位符 SID (S-1-12-1) 替换为 **Azure AD 组 SID**，然后将文件另存为 XML;例如， **aad-local-admin.xml。 **

      > [!NOTE]
      > 虽然组应该通过 SID 指定，但如果你想要直接添加 Azure 用户，请采用此格式 (UPN) 用户主体名称： `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>创建自定义配置文件

1. In Endpoint Manager， select **DevicesConfiguration****** >  **profilesCreate** >  profile.
2. 在"平台"**下Windows 10选择"应用和更高版本"。** 在"配置文件"下 **，选择"自定义**"，然后选择" **创建"。**
3. 添加名称和说明，然后选择"下一 **步"。**
4. 在**配置设置** > **OMA-URI 设置**下 **，选择添加**。
5. 在"添加行"窗格中，添加名称，在     **OMA-URI** 下添加以下字符串：

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

> [!NOTE]
> **RestrictedGroups/ConfigureGroupMembership** 策略设置还允许你配置成员 (用户或 AAD 组) 到Windows 10组。 但是，它只允许将现有组完全替换为新成员。 不能有选择地添加或删除成员。  在 Windows 10 协同版 2020 Update 2 中可用，建议使用 **LocalUsersandGroups** 策略设置，而不是 RestrictedGroups 策略设置。 不支持将两个策略设置Surface Hub策略设置，并可能导致不可预知的结果。

6. 在"数据类型"下，选择 **"字符串 XML** "并浏览以打开在上一步中创建的 XML 文件。

     ![上传本地管理员 xml 配置文件。](images/sh-local-admin-config.png)

7. 单击 **“保存”**。
8. 单击 **"选择要包含的组**"，然后选择之前[在](#create-security-group-for-surface-hub-devices) (Surface Hub**创建) **。 单击“下一步”****。
9. 在"适用性规则"下，根据需要添加"规则"。 否则，请选择 **"下一** 步"，然后选择" **创建"**。

若要详细了解使用 OMA-URI 字符串的自定义配置文件，请参阅在 [Intune Windows 10自定义设置](/mem/intune/configuration/custom-settings-windows-10)。

## <a name="non-global-admins-managing-surface-hub"></a>非全局管理员管理Surface Hub

现在，**Surface Hub本地管理员**安全组的成员可以登录到 设置 应用并Surface Hub设置。

> [!IMPORTANT]
> 全局管理员对 设置 应用的默认访问权限将 (，除非他们也是此新安全组) 。

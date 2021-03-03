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
# <a name="configure-non-global-admin-accounts-on-surface-hub-2s"></a>配置 Surface Hub 2 上的非全局管理员帐户

将 Surface Hub 2S 加入 Azure AD 域时，可以配置非全局管理员帐户，这些帐户限制对 Surface Hub 2S 上"设置"应用的管理权限。 这使你能够仅确定 Surface Hub 2S 的管理员权限范围，并在整个 Azure AD 域中阻止可能不需要的管理员访问权限。 开始之前，请确保 Surface Hub 2S 已加入 Azure AD。 如果没有，则需要重置 Surface Hub 2S，并完成首次、开箱即用 (OOBE) 安装程序，选择加入 Azure AD 的选项。

## <a name="summary"></a>摘要 

创建非全局管理员帐户的过程包括以下步骤： 

1. 在 Microsoft Intune 中，创建一个安全组，其中包含指定为管理 Surface Hub 2S 的管理员。
2. 使用 PowerShell 获取 Azure AD 组 SID。
3. 创建包含 Azure AD 组 SID 的 XML 文件。
4. 创建一个安全组，其中包含由非全局管理员安全组管理的 Surface Hub 2S 设备。
5. 创建自定义配置文件，以包含 Surface Hub 2S 设备的安全组为目标。 


## <a name="create-azure-ad-security-groups"></a>创建 Azure AD 安全组

首先创建一个包含管理员帐户的安全组。 然后为 Surface Hub 设备创建另一个安全组。  

### <a name="create-security-group-for-admin-accounts"></a>为管理员帐户创建安全组

1. 通过 Microsoft Endpoint [Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心登录 Intune，**选择组**新组>组类型下，选择  >  ******"安全"。** 
2. 输入组名称（例如 Surface **Hub 本地管理员** ）然后选择" **创建"。** 

     ![为中心管理员创建安全组](images/sh-create-sec-group.png)

3. 打开组，选择 **"成员**"，然后选择"**** 添加成员"以输入你希望在 Surface Hub 2S 上指定为非全局管理员的管理员帐户。 若要了解有关在 Intune 中创建组的信息，请参阅"  [添加组"以组织用户和设备](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。

### <a name="create-security-group-for-surface-hub-2s-devices"></a>为 Surface Hub 2S 设备创建安全组

1. 重复上述过程，为集线器设备创建单独的安全组;例如 **，Surface Hub 设备**。 

     ![为集线器设备创建安全组](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>使用 PowerShell 获取 Azure AD 组 SID

1. 使用提升的帐户权限启动 PowerShell (**以** 管理员) ，并确保系统配置为运行 PowerShell 脚本。 若要了解详情，请参阅"[关于执行策略"。](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?) 
2. [安装 Azure PowerShell 模块](https://docs.microsoft.com/powershell/azure/install-az-ps)。
3. 登录到 Azure AD 租户。

    ```powershell
    Connect-AzureAD
    ```

4. 登录租户后，运行以下命令let。 它将提示你"请键入 Azure AD 组的对象 ID"。

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. 在 Intune 中，选择之前创建的组并复制对象 ID，如下图所示。 

     ![复制安全组的对象 ID](images/sh-objectid.png)

6. 运行以下命令let 获取安全组的 SID：

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. 将对象 ID 粘贴到 PowerShell 命令let 中，按 **Enter，** 然后将 **Azure AD 组 SID** 复制到文本编辑器中。 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>创建包含 Azure AD 组 SID 的 XML 文件

1. 将以下内容复制到文本编辑器中： 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. 将占位符 SID (S-1-12-1) **Azure AD 组 SID，** 然后将文件另存为 XML;例如 ** ，aad-local-admin.xml**。 

## <a name="create-custom-configuration-profile"></a>创建自定义配置文件

1. 在终结点管理器中，**选择"设备**  >  **配置文件创建**  >  **配置文件"。** 
2. 在"平台" **下选择 Windows 10 及更高版本。** 在"配置文件"下 **，选择"** 自定义"，然后选择" **创建"。**
3. 添加名称和说明，然后选择"下 **一步"。**
4. 在 **"配置设置**  >  **OMA-URI 设置**"下，选择 **"添加"。**
5. 在"添加行"窗格中，添加名称，在     **OMA-URI**下添加以下字符串： 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. 在"数据类型"下，选择 **字符串 XML** 并浏览以打开在上一步中创建的 XML 文件。 

     ![上载本地管理员 xml 配置文件](images/sh-local-admin-config.png)

7. 单击 **“保存”**。
8. 单击 **"选择要包含的安全组**"，[](#create-security-group-for-surface-hub-2s-devices)然后选择之前在 Surface Hub (**创建) 。** 单击“下一步”****。
9. 在"适用性规则"下，根据需要添加规则。 否则，请选择 **"下一步**"，然后选择"**创建"。**

若要了解有关使用 OMA-URI 字符串的自定义配置文件，请参阅 Intune 中的 [Windows 10 设备的自定义设置](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。


## <a name="non-global-admins-managing-surface-hub-2s"></a>管理 Surface Hub 2S 的非全局管理员

Surface **Hub Local Admins** Security 组的成员现在可以登录到 Surface Hub 2S 上的"设置"应用并管理设置。

---
title: 配置 Surface Hub 2 上的非全局管理员帐户
description: 本文介绍如何配置非全局管理员帐户以管理 Surface Hub 2。
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
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196786"
---
# 配置 Surface Hub 2 上的非全局管理员帐户

当你将 Surface Hub 2 联接到 Azure AD 域时，你可以配置非全局管理员帐户，该帐户限制对 Surface Hub 2 上的 "设置" 应用的管理权限。 这使你能够限定 Surface Hub 2 秒的管理员权限，并防止可能不需要的管理员访问整个 Azure AD 域。 开始之前，请确保 Surface Hub 的2秒已加入 Azure AD。 如果不是，你将需要重置 Surface Hub 2 和完成第一次 (OOBE) 设置程序，选择用于加入 Azure AD 的选项。

## 摘要 

创建非全局管理员帐户的过程包括以下步骤： 

1. 在 Microsoft Intune 中，创建包含指定用于管理 Surface Hub 2/2 的管理员的安全组。
2. 使用 PowerShell 获取 Azure AD 组 SID。
3. 创建包含 Azure AD 组 SID 的 XML 文件。
4. 创建包含将由非全局管理员安全组管理的 Surface Hub 2 设备的安全组。
5. 创建面向包含 Surface Hub 2 设备的安全组的自定义配置文件。 


## 创建 Azure AD 安全组

首先创建包含管理员帐户的安全组。 然后为 Surface Hub 设备创建另一个安全组。  

### 为管理员帐户创建安全组

1. 通过[Microsoft 终结点管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)登录到 Intune，选择 "**组**  >  **新组**" >，然后在 "组类型" 下，选择 "**安全"。** 
2. 输入组名称（如 **Surface Hub 本地管理员** ），然后选择 " **创建"。** 

     ![为中心管理员创建安全组](images/sh-create-sec-group.png)

3. 打开组，选择 " **成员**"，然后选择 " **添加成员** " 以输入您希望在 Surface Hub 2 上为非全局管理员指定的管理员帐户。 若要了解有关在 Intune 中创建组的详细信息，请参阅  [添加组以组织用户和设备](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。

### 创建 Surface Hub 2 设备的安全组

1. 重复上述过程，为中心设备创建单独的安全组;例如， **Surface Hub 设备**。 

     ![为中心设备创建安全组](images/sh-create-sec-group-devices.png) 

## 使用 PowerShell 获取 Azure AD 组 SID

1. 以提升的帐户权限启动 PowerShell (**以管理员身份运行**) 并确保系统配置为运行 PowerShell 脚本。 若要了解详细信息，请参阅 [关于执行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。 
2. [安装 Azure PowerShell 模块](https://docs.microsoft.com/powershell/azure/install-az-ps)。
3. 登录到你的 Azure AD 租户。

    ```powershell
    Connect-AzureAD
    ```

4. 登录租户时，请运行以下 commandlet。 它将提示你 "请键入 Azure AD 组的对象 ID"。

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. 在 Intune 中，选择之前创建的组并复制对象 id，如下图所示。 

     ![复制安全组的对象 id](images/sh-objectid.png)

6. 运行以下 commandlet 获取安全组的 SID：

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. 将对象 id 粘贴到 PowerShell commandlet 中，按 **enter**，然后将 **AZURE AD 组 SID** 复制到文本编辑器中。 

## 创建包含 Azure AD 组 SID 的 XML 文件

1. 将以下内容复制到文本编辑器中： 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. 将占位符 SID 替换为以 S-1-12-1) 开头的 **AZURE AD 组 sid** (，然后将该文件另存为 XML;例如， **aad-local-admin.xml**。 

## 创建自定义配置文件

1. 在终结点管理器中，选择 "**设备**  >  **配置文件**"  >  **创建配置文件**。 
2. 在 "平台" 下 **，选择 Windows 10 和更高版本。** 在 "配置文件" 下，选择 " **自定义**"，然后选择 " **创建"。**
3. 添加名称和说明，然后选择 " **下一步"。**
4. 在**配置设置**  >  **OMA URI 设置**下，选择**添加**。
5. 在 "添加行" 窗格中，添加一个名称，然后在 "     **oma-uri**" 下添加以下字符串： 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. 在 "数据类型" 下，选择 " **字符串 XML** "，然后单击 "浏览" 打开您在上一步中创建的 XML 文件。 

     ![上载本地管理员 xml 配置文件](images/sh-local-admin-config.png)

7. 单击 **“保存”**。
8. 单击 "**选择要包含的组**"，然后选择先前 (**Surface Hub 设备**) 中创建的[安全组](#create-security-group-for-surface-hub-2s-devices)。 单击“下一步”****。
9. 在 "适用性规则" 下，根据需要添加规则。 否则，选择 " **下一步** "，然后选择 " **创建**"。

若要了解有关使用 OMA-URI 字符串的自定义配置文件的详细信息，请参阅 [在 Intune 中使用适用于 Windows 10 设备的自定义设置](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。


## 管理 Surface Hub 2 的非全局管理员

**Surface Hub 本地管理员**安全组的成员现在可以登录 Surface hub 2 和管理设置上的 "设置" 应用。

---
title: 为 Microsoft Surface Hub 准备你的环境
description: 此页面介绍在 v1 或 Surface Hub 2S Surface Hub依赖项。
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: 准备环境， Surface Hub， 设备帐户， 网络可用性， M365 终结点， Intune
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: b5e5b9e72b71a539a6140aa4fbd7bce2b166f125
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576972"
---
# <a name="prepare-your-environment-for-microsoft-surface-hub"></a>为 Microsoft Surface Hub 准备环境

 
此页面介绍在 v1 或 Surface Hub 2S Surface Hub依赖项。
 

## <a name="infrastructure-dependencies"></a>基础结构依赖关系

查看这些依赖关系，以确保 Surface Hub 功能在你的 IT 基础结构中有效。
 
 
| 依赖关系                                                                                                                                  | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | 了解详细信息                                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 本地服务和 Active Directory 或 M365                                                                                           |  Surface Hub Active Directory 或 Azure AD 帐户 (**设备**帐户) 访问 Exchange Teams (或 Skype for Business) 服务。 Surface Hub 必须能够连接到 Active Directory 域控制器或 Azure AD 租户，才可以验证设备帐户的凭据以及访问诸如设备帐户的显示名称、别名、Exchange Server 和会话初始协议 (SIP) 地址等信息。  <br><br>**注意：Surface Hub 可Microsoft Teams 2019 Skype for Business Server 2015 Skype for Business Server 2015 或 Skype for Business Online。 不支持早期平台，如 Lync Server 2013。 Surface Hub 在高GCC DoD 环境中不受支持。**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | [Microsoft 365终结点](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-endpoints) <br> <br> [创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md)                                                                                                                                                    |
| Windows更新、存储和诊断                                                                                                       | 若要Windows操作系统功能和质量Windows，需要访问 Surface Hub 更新或适用于企业的更新。 需要访问Microsoft Store才能维护应用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | [管理 Windows 10 企业版版本 20H2 的连接终结点](https://docs.microsoft.com/windows/privacy/manage-windows-20h2-endpoints)<br> <br>[管理 Surface Hub 上的 Windows 更新](manage-windows-updates-for-surface-hub.md) |
| 移动设备管理 (MDM) 解决方案 (Microsoft Intune、Microsoft Endpoint Configuration Manager或受支持的第三方 MDM 提供程序)  | 如果想要远程应用设置并安装应用，以及一次性将设置应用于多台设备，必须设置 MDM 解决方案并向该解决方案注册设备。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | [Microsoft Intune 网络终结点](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)<br> <br>[使用 MDM 提供程序管理设置](manage-settings-with-mdm-for-surface-hub.md)                                  |
| Azure Monitor                                                                                                                               | Azure Monitor 可用于监视设备Surface Hub运行状况。 <br><br>**注意：Surface Hub 当前不支持使用代理服务器与 Azure Monitor 利用的 Log Analytics 服务进行通信。**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | [Log Analytics 终结点](https://docs.microsoft.com/azure/azure-monitor/agents/log-analytics-agent#firewall-requirements)<br> <br> [使用 Azure Monitor 监视 Surface Hub 以跟踪其运行状况](https://docs.microsoft.com/azure/azure-monitor/insights/surface-hubs)。                                                                                                                                               |
| 网络访问                                                                                                                              |  Surface Hub 支持有线或无线连接 (有线连接是首选) 。 <br> <br>**802.1X 身份验证**<br>在 Windows 10 协同版 20H2 中，尽管默认情况下为有线和无线连接启用 802.1X 身份验证，但您需要确保 Surface Hub 上也安装了 802.1x 网络配置文件和身份验证证书。 如果你使用 intune Surface Hub或其他移动设备管理解决方案管理证书，可以使用[ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp)传递证书。 否则，[你可以创建预配包，在](provisioning-packages-for-surface-hub.md)首次运行安装期间或通过使用预配包设置安装。 应用证书后，将自动开始 802.1X 身份验证。<br> <br>**动态 IP**<br>Surface Hub 无法配置为使用静态 IP。 必须通过 DHCP 为其分配 IP 地址。<br> <br>**端口**<br>该Surface Hub需要以下打开的端口：<br><br>HTTPS：443<br>HTTP：80<br>NTP：123 | [启用 802.1x 有线身份验证](enable-8021x-wired-authentication.md)  <br><br>[创建 Surface Hub 2S 的预配程序包](surface-hub-2s-deploy.md)                                                                                 |

## <a name="device-affiliation"></a>设备附属关系

使用设备附属关系管理用户对 设置 应用的访问权限Surface Hub。 使用Windows 10 协同版运行 (操作系统Surface Hub) ，只有授权用户可以使用 设置 应用调整设置。 由于选择附属关系可能会影响功能可用性，请进行相应的规划以确保用户可以访问预期的功能。
 
 
> [!NOTE]
> 在 OOBE 设置的初始开箱即用体验期间，你 (设备) 关联。 如果需要重置设备附属关系，必须重复 OOBE 设置。
 

### <a name="no-affiliation"></a>无附属关系

没有任何附属关系Surface Hub在每个工作组上使用不同的本地管理员帐户在工作组中Surface Hub。 如果选择"无附属关系"，则必须本地将BitLocker[密钥保存到 U 盘](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)。 你仍可使用 Intune 注册设备;但是，只有本地管理员设置 OOBE 期间配置的帐户凭据访问应用。 可以从管理应用程序更改管理员设置密码。
 

### <a name="active-directory-domain-services"></a>Active Directory 域服务

如果关联Surface Hub Active Directory 域服务，则需要使用域中的安全组管理对 设置 应用的访问权限。 这有助于确保所有安全组的成员都有权更改Surface Hub。 另请注意以下事项：Surface Hub Active Directory 域服务关联时，BitLocker密钥可以保存在 Active Directory 架构中。 有关详细信息，请参阅[为组织准备BitLocker：规划和策略](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。
 
组织的受信任根证书将推送到 Surface Hub 中的同一容器，这意味着你无需使用预配包导入它们。
 
你仍可使用 Intune 注册设备，以集中管理设备上Surface Hub。
 

### <a name="azure-active-directory"></a>Azure Active Directory

当你选择将你的 Surface Hub与 Azure Active Directory (Azure AD) 关联时，具有全局管理员角色的任何用户都可以登录到 Surface Hub 上的 设置 应用。 还可以配置非全局管理员帐户，以限制对 设置 应用的管理Surface Hub。 这使你能够仅作用域 Surface Hub 的管理员权限，并在整个 Azure AD 域中阻止可能不需要的管理员访问权限。

如果你为组织[启用了 Intune](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)自动注册，Surface Hub将自动向 Intune 注册;在此方案中，在设置期间用于 Azure AD 附属关系的帐户必须获得 Intune 的许可，并且有权在设备上Windows帐户。 设置过程完成后，设备密钥BitLocker自动保存在 Azure AD 中。

若要了解有关使用 Azure AD Surface Hub管理应用程序的信息，请参阅：

- [管理员组管理](admin-group-management-for-surface-hub.md)
- [配置 Surface Hub 上的非全局管理员帐户](surface-hub-2s-nonglobal-admin.md)

### <a name="review-and-complete-surface-hub-setup-worksheet-optional"></a>查看并填写 Surface Hub 设置工作表（可选）

在为 Surface Hub 实行首次运行计划时，需要提供一些信息。 设置工作表总结了此类信息，并提供要实行首次运行计划所需的特定于环境的信息。 有关详细信息，请参阅[设置工作表](setup-worksheet-surface-hub.md)。


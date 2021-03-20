---
title: 为 Microsoft Surface Hub 准备你的环境
description: 此页面介绍设置和管理 Surface Hub v1 或 Surface Hub 2S 的依赖项。
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
ms.openlocfilehash: 33724f84171cb9485bd20ff5c437ad8b3f60a463
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442120"
---
# <a name="prepare-your-environment-for-microsoft-surface-hub"></a>为 Microsoft Surface Hub 准备环境

 
此页面介绍设置和管理 Surface Hub v1 或 Surface Hub 2S 的依赖项。
 

## <a name="infrastructure-dependencies"></a>基础结构依赖关系

查看这些依赖关系，以确保 Surface Hub 功能在你的 IT 基础结构中有效。
 
 
| 依赖关系                                                                                                                                  | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | 了解详细信息                                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 本地服务和 Active Directory 或 M365                                                                                           |  Surface Hub 使用称为设备帐户 (的 Active Directory 或 Azure AD **帐户) 访问** Exchange 和 Teams (或 Skype for Business) 服务。 Surface Hub 必须能够连接到 Active Directory 域控制器或 Azure AD 租户，才可以验证设备帐户的凭据以及访问诸如设备帐户的显示名称、别名、Exchange Server 和会话初始协议 (SIP) 地址等信息。  <br><br>**注意：Surface Hub 适用于 Microsoft Teams、Skype for Business Server 2019、Skype for Business Server 2015 或 Skype for Business Online。 不支持早期平台，如 Lync Server 2013。 Surface Hub 在 GCC High 或 DoD 环境中不受支持。**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | [Microsoft 365 终结点](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-endpoints) <br> <br> [创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md)                                                                                                                                                    |
| Windows 更新、应用商店和诊断                                                                                                       | 若要使用操作系统功能和质量更新来维护 Surface Hub，需要访问适用于 Business 的 Windows 更新或 Windows 更新。 维护应用需要访问 Microsoft Store。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | [管理 Windows 10 企业版版本 20H2 的连接终结点](https://docs.microsoft.com/windows/privacy/manage-windows-20h2-endpoints)<br> <br>[管理 Surface Hub 上的 Windows 更新](manage-windows-updates-for-surface-hub.md) |
| 移动设备管理 (MDM) 解决方案 (Microsoft Intune、Microsoft Endpoint Configuration Manager 或受支持的第三方 MDM 提供程序)  | 如果想要远程应用设置并安装应用，以及一次性将设置应用于多台设备，必须设置 MDM 解决方案并向该解决方案注册设备。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | [Microsoft Intune 网络终结点](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)<br> <br>[使用 MDM 提供程序管理设置](manage-settings-with-mdm-for-surface-hub.md)                                  |
| Azure Monitor                                                                                                                               | Azure Monitor 可用于监视 Surface Hub 设备的运行状况。 <br><br>**注意：Surface Hub 当前不支持使用代理服务器与 Azure Monitor 利用的 Log Analytics 服务进行通信。**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | [Log Analytics 终结点](https://docs.microsoft.com/azure/azure-monitor/agents/log-analytics-agent#firewall-requirements)<br> <br> [使用 Azure Monitor 监视 Surface Hub 以跟踪其运行状况](https://docs.microsoft.com/azure/azure-monitor/insights/surface-hubs)。                                                                                                                                               |
| 网络访问                                                                                                                              |  Surface Hub 支持有线或无线连接 (有线连接是首选) 。 <br> <br>**802.1X 身份验证**<br>在 Windows 10 Team 20H2 中，尽管默认情况下已启用有线和无线连接的 802.1X 身份验证，但需要确保 Surface Hub 上也安装了 802.1x 网络配置文件和身份验证证书。 如果你使用 Intune 或其他移动设备管理解决方案管理 Surface Hub，可以使用 [ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp)传递证书。 否则， [你可以创建预配包，在](provisioning-packages-for-surface-hub.md) 首次运行设置期间或通过使用"设置"应用安装它。 应用证书后，将自动开始 802.1X 身份验证。<br> <br>**动态 IP**<br>Surface Hub 无法配置为使用静态 IP。 必须通过 DHCP 为其分配 IP 地址。<br> <br>**端口**<br>Surface Hub 需要以下打开的端口：<br><br>HTTPS：443<br>HTTP：80<br>NTP：123 | [启用 802.1x 有线身份验证](enable-8021x-wired-authentication.md)  <br><br>[创建 Surface Hub 2S 的预配程序包](surface-hub-2s-deploy.md)                                                                                 |

## <a name="device-affiliation"></a>设备附属关系

使用设备附属关系管理用户对 Surface Hub 上的"设置"应用的访问权限。 借助在 Surface Hub (上运行的 Windows 10) ，只有授权用户可以使用"设置"应用调整设置。 由于选择附属关系可能会影响功能可用性，请进行相应的规划以确保用户可以访问预期的功能。
 
 
> [!NOTE]
> 在 OOBE 设置的初始开箱即用体验期间，你 (设备) 关联。 如果需要重置设备附属关系，必须重复 OOBE 设置。
 

### <a name="no-affiliation"></a>无附属关系

无附属关系就像在每个 Surface Hub 上将 Surface Hub 放在具有不同本地管理员帐户的工作组中。 如果选择"无附属关系"，则必须将 [BitLocker 密钥本地保存到 U 盘](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)。 你仍可使用 Intune 注册设备;但是，只有本地管理员可以使用在 OOBE 期间配置的帐户凭据访问"设置"应用。 可以从"设置"应用更改管理员帐户密码。
 

### <a name="active-directory-domain-services"></a>Active Directory 域服务

如果将 Surface Hub 与本地 Active Directory 域服务关联，则需要使用域中的安全组管理对"设置"应用的访问权限。 这有助于确保所有安全组的成员都有权更改 Surface Hub 上的设置。 另请注意以下事项：当 Surface Hub 与本地 Active Directory 域服务关联时，BitLocker 密钥可以保存在 Active Directory 架构中。 有关详细信息，请参阅 [为组织准备 BitLocker：规划和策略](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。
 
你的组织的受信任根证书将推送到 Surface Hub 中的同一容器，这意味着你无需使用预配包导入它们。
 
你仍可使用 Intune 注册设备以集中管理 Surface Hub 上的设置。
 

### <a name="azure-active-directory"></a>Azure Active Directory

当你选择将 Surface Hub 与 Azure Active Directory (Azure AD) 关联时，全局管理员安全组的任何用户都可以登录到 Surface Hub 上的设置应用。 还可以配置非全局管理员帐户，以限制 Surface Hub 上"设置"应用的管理权限。 这使你能够仅作用域 Surface Hub 的管理员权限，并在整个 Azure AD 域中阻止可能不需要的管理员访问权限。

如果你为组织 [启用了 Intune](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) 自动注册，Surface Hub 将自动向 Intune 注册。 设备的 BitLocker 密钥会自动保存在 Azure AD 中。

若要了解有关使用 Azure AD 管理 Surface Hub 的信息，请参阅：

- [管理员组管理](admin-group-management-for-surface-hub.md)
- [在 Surface Hub 上配置非全局管理员帐户](surface-hub-2s-nonglobal-admin.md)

### <a name="review-and-complete-surface-hub-setup-worksheet-optional"></a>查看并填写 Surface Hub 设置工作表（可选）

在为 Surface Hub 实行首次运行计划时，需要提供一些信息。 设置工作表总结了此类信息，并提供要实行首次运行计划所需的特定于环境的信息。 有关详细信息，请参阅[设置工作表](setup-worksheet-surface-hub.md)。


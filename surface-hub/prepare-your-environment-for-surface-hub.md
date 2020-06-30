---
title: 为 Microsoft Surface Hub 准备你的环境
description: 本部分包含准备环境所需的步骤概述，以便你可以使用 Microsoft Surface Hub 的所有功能。
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: 准备环境, Surface Hub 的功能, 创建和测试设备帐户, 检查网络可用性
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/04/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0ee406df6d3022f04a80f4ce253bd76f6473f1c8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832051"
---
# 为 Microsoft Surface Hub 准备你的环境


本部分包含设置依赖关系和设置过程的概述。 查看本部分中的信息可帮助你准备环境，并收集设 Surface Hub 所需的信息。


## 查看基础结构依赖关系
查看这些依赖关系，以确保 Surface Hub 功能在你的 IT 基础结构中有效。

| 依赖关系        | 用途           |
|-------------|------------------|
| Active Directory 或 Azure Active Directory (Azure AD) | <p>Surface Hub 使用 Active Directory 或 Azure AD 帐户（称为 **设备帐户**）访问 Exchange 和 Skype for Business 服务。 Surface Hub 必须能够连接到 Active Directory 域控制器或 Azure AD 租户，才可以验证设备帐户的凭据以及访问诸如设备帐户的显示名称、别名、Exchange Server 和会话初始协议 (SIP) 地址等信息。</p>还可以将域或 Azure AD 与 Surface Hub 结合，以允许一组授权用户在 Surface Hub 上配置设置。 |
| Exchange（Exchange 2013 或更高版本，或者 Exchange Online）和 Exchange ActiveSync | <p>Exchange 用于启用邮件和日历功能，并且还允许使用该设备的用户向 Surface Hub 发送会议请求，以便支持一站式会议加入。</p>ActiveSync 用于将设备帐户的日历和邮件同步到 Surface Hub。 如果该设备不能使用 ActiveSync，则不会在欢迎屏幕上显示会议，并且不支持加入会议和通过电子邮件发送白板。 |
| Skype for Business（Lync Server 2013 或更高版本，或者 Skype for Business Online）  | Skype for Business 可用于各种会议功能，例如视频通话、即时消息和屏幕共享。|
| 移动设备管理（MDM）解决方案（Microsoft Intune、Microsoft 终结点配置管理器或受支持的第三方 MDM 提供程序） | 如果想要远程应用设置并安装应用，以及一次性将设置应用于多台设备，必须设置 MDM 解决方案并向该解决方案注册设备。 请参阅[使用 MDM 提供程序管理设置](manage-settings-with-mdm-for-surface-hub.md)了解详细信息。 |
| Microsoft Operations Management Suite (OMS)   | OMS 用于监视 Surface Hub 设备的运行状况。 请参阅[监视 Surface Hub](monitor-surface-hub.md)了解详细信息。 |
| 网络和 Internet 访问权限   | 为了能够正常工作，Surface Hub 应有权访问有线网络或无线网络。 总的来说，有线连接是首选。 有线和无线连接均支持 802.1X 身份验证。</br></br></br>**802.1X 身份验证：** 在 Windows 10 版本 1703 中，默认情况下，Surface Hub 启用了适用于有线和无线连接的 802.1X 身份验证。 如果你的组织未使用 802.1X 身份验证，则不需要进行配置并且 Surface Hub 将继续正常工作。 如果你使用 802.1X 身份验证，则必须确保 Surface Hub 上安装了身份验证证书。 你可以使用 MDM 中的 [ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp) 向 Surface Hub 提供证书，或者可以[创建预配包](provisioning-packages-for-surface-hub.md)，并在首次运行期间或通过“设置”应用来安装它。 将证书应用于 Surface Hub 后，802.1X 身份验证将自动开始工作。</br>**注意**：有关在 Surface Hub 上启用 802.1X 有线身份验证的详细信息，请参阅[启用 802.1x 有线身份验证](enable-8021x-wired-authentication.md)。</br></br>**动态 IP**：Surface Hub 无法配置为使用静态 IP。 必须使用 DHCP 才能分配 IP 地址。</br></br>**代理服务器**：如果你的拓扑需要连接到代理服务器才可以访问 Internet 服务，则可以在首次运行期间或在“设置”中对它进行配置。 代理凭据存储在 Surface Hub 会话中，只需设置一次。 |

此外，还请注意 Surface Hub 要求打开以下端口：
- HTTPS：443
- HTTP：80
- NTP：123

如果您将 Surface Hub 与 Skype for Business 配合使用，您需要打开其他端口。 请按照以下指南操作：
- 如果您使用的是 Skype for Business Online，请参阅[Office 365 IP url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)。
- 如果您使用的是 Skype for Business 服务器，请参阅[skype For Business 服务器：内部服务器的端口和协议](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols)。 
- 如果您使用的是 Skype for Business Online 和 Skype for business 服务器的混合，则需要从[Office 365 IP url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)和 skype For business 服务器中打开所有记录的端口[：内部服务器的端口和协议](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)。

Microsoft 收集诊断数据来帮助改善 Surface Hub 体验。 请将以下站点添加到允许列表：
- 诊断数据客户端终结点: `https://vortex.data.microsoft.com/`
- 诊断数据设置终结点: `https://settings.data.microsoft.com/`

### 代理配置

如果你的组织限制你网络上的计算机连接到 Internet，则需要向设备提供一组 URL 才能使用适用于企业的 Microsoft Store。 某些适用于企业的 Microsoft Store 功能使用 Microsoft Store 应用和 Microsoft Store 服务。 设备在使用适用于企业的 Microsoft Store 时，无论是获取、安装还是更新应用，都需要访问这些 URL。 如果使用代理服务器阻止流量，则你的配置需要允许这些 URL：

- login.live.com
- login.windows.net
- account.live.com
- clientconfig.passport.net
- windowsphone.com
- *.wns.windows.com
- *.microsoft.com
- www.msftncsi.com（Windows 10 版本 1607 之前的版本）
- www.msftconnecttest.com/connecttest.txt（从 Windows 10 版本 1607 开始替换 www.msftncsi.com）


## 与其他管理员合作

Surface Hub 可与某些其他产品和服务交互。 可能有多人在环境中支持不同的产品，具体取决于组织的规模。 你需要将管理 Exchange、Active Directory（或 Azure Active Directory）、移动设备管理 (MDM) 和网络资源的人员纳入 Surface Hub 部署的规划和准备工作中。 


## 创建和验证设备帐户

设备帐户是 Surface Hub 用于显示其会议日历、加入 Skype for Business 通话、发送电子邮件和验证 Exchange（可选）的 Exchange 资源帐户。 有关详细信息，请参阅[创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md)。

创建设备帐户后，若要验证是否正确设置了该帐户，请运行 Surface Hub 设备帐户验证 PowerShell 脚本。 有关详细信息，请参阅本指南后面部分的[适用于 Surface Hub 的 PowerShell 脚本](appendix-a-powershell-scripts-for-surface-hub.md)。 

 

## 准备首次运行计划 
开始[首次运行计划](first-run-program-surface-hub.md)之前，需要考虑几项内容。  

### 创建设置包（可选）
可以使用设置包添加证书、自定义设置和安装应用。 有关详细信息，请参阅[创建设置包](provisioning-packages-for-certificates-surface-hub.md)。 可以[在首次运行时安装设置包](first-run-program-surface-hub.md#first-page)。

### 设置管理员组
可使用设备上的“设置”应用在本地配置每个 Surface Hub。 若要防止未经授权的用户更改设置，“设置”应用要求使用管理员凭据打开该应用。 有关如何设置和管理管理员组的详细信息，请参阅[管理员组管理](admin-group-management-for-surface-hub.md)。 你将[在首次运行时为设备设置管理员](first-run-program-surface-hub.md#setup-admins)。

### 查看并填写 Surface Hub 设置工作表（可选）
在为 Surface Hub 实行首次运行计划时，需要提供一些信息。 设置工作表总结了此类信息，并提供要实行首次运行计划所需的特定于环境的信息。 有关详细信息，请参阅[设置工作表](setup-worksheet-surface-hub.md)。


## 本部分内容

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">主题</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="create-and-test-a-device-account-surface-hub.md" data-raw-source="[Create and test a device account](create-and-test-a-device-account-surface-hub.md)">创建和测试设备帐户</a></p></td>
<td align="left"><p>本主题介绍了如何创建和测试 Surface Hub 用于与 Skype 进行通信的设备帐户。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="provisioning-packages-for-certificates-surface-hub.md" data-raw-source="[Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md)">创建设置包</a></p></td>
<td align="left"><p>对于 Windows 10，使用注册表或内容服务平台 (CSP) 的设置可通过设置包进行配置。 也可使用预配在首次运行期间添加证书。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="admin-group-management-for-surface-hub.md" data-raw-source="[Admin group management](admin-group-management-for-surface-hub.md)">管理员组管理</a></p></td>
<td align="left"><p>通过在 Surface Hub 上打开“设置”应用，可分别配置每台设备。 但是，若要防止不是管理员的用户更改设置，“设置”应用需要管理员凭据才可以打开该应用并更改设置。</p>
<p>“设置”应用需要本地管理员凭据才可以打开该应用。</p></td>
</tr>
</tbody>
</table>

## 详细信息

- [博客文章：Surface Hub 和 Skype for Business 的受信任域列表](https://blogs.technet.microsoft.com/y0av/2017/10/25/95/)
- [博客文章：多域环境中的 Surface Hub](https://blogs.technet.microsoft.com/y0av/2017/11/08/11/)
- [博客文章：为 Surface Hub 配置代理服务器](https://blogs.technet.microsoft.com/y0av/2017/12/03/7/)

 

 






---
title: 设置工作表 (Surface Hub)
description: 当你完成预设置并已准备好为你的 Microsoft Surface Hub 启动首次设置时，请确保你拥有本部分中列出的所有信息。
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: 设置工作表, 预设置, 首次设置
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/14/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: c0bba196aa71c751d092b4e1f2f6005d653b2f69
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576712"
---
# <a name="setup-worksheet-surface-hub"></a>设置工作表 (Surface Hub)

当你完成预设置并已准备好为你的 Microsoft Surface Hub 启动首次设置时，请确保你拥有本部分中列出的所有信息。

应当为需要配置的每个 Surface Hub 都填写一个列表，尽管某些信息（如代理信息或域凭据）可用于所有 Surface Hub。 其中某些信息可能不需要，具体取决于决定配置你的设备的方式或者针对组织的基础结构配置环境的方式。

完成后，请查看下面的 [部署后](#post-deployment-checklist) 清单。

| 属性                                                          | 用途                                                                                                                                                                                                                                                                                                                                                           | 示例                                                                                                                               | 了解详细信息                                                                                                                                                                                                                                                              |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 代理信息                                                 | 如果使用代理进行网络或 Internet 访问，则必须提供脚本或服务器/端口信息。                                                                                                                                                                                                                                                                        |  代理脚本： http://contoso/proxy.pac <br><br>或者：<br><br>服务器和端口信息：10.10.10.100，端口 80                                  | [使用预配包配置代理。](surface-hub-2s-deploy.md)                                                                                                                           |
| 无线网络凭据（用户名和密码）              | 如果你的设备连接到 WLAN，并且无线网络需要用户凭据。                                                                                                                                                                                                                                                                                           | admin1@contoso.com，#MyPassw0rd                                                                                                       | [无线网络管理](wireless-network-management-for-surface-hub.md)                                                                                                                                                 |
| 设备帐户 UPN 或域\用户名以及设备帐户密码 | 这是用户主体名称 (UPN) 或域\用户名以及设备帐户的密码。 邮件、日历Microsoft Teams和Skype for Business取决于兼容的设备帐户。                                                                                                                                                                            | UPN：ConfRoom15@contoso.com，#Passw0rd1 <br><br>或者：<br><br>域和用户名：CONTOSO\ConfRoom15，#Passw0rd1                        | [创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md) |
| 邮箱属性                                                | 必须使用正确的属性配置邮箱，才能在 Surface Hub 上获得最佳会议体验。                                                                                                                                                                                                                                                                | 请参阅[Microsoft Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md) |                                                                                                                                        |
| 设备帐户邮箱的 EWS URL                              | 这是设备帐户的 Exchange Server。 邮件、日历Microsoft Teams和Skype for Business取决于兼容的设备帐户。 为了使邮件和日历正常工作，设备帐户必须具有有效的 Exchange Server。 设备将尝试自动查找此项。                                                                                               | https://outlook.office365.com/EWS/exchange.asmx                                                                                                                 | [创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md)<br><br>[Microsoft Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)      |
| 设备帐户会话初始协议 (SIP) 地址          | 这是设备帐户的 SIP 地址。 邮件、日历Microsoft Teams和Skype for Business取决于兼容的设备帐户。 若要使Skype或企业正常工作，设备帐户必须具有有效的 SIP 地址 设备将尝试自动查找此地址。                                                                                              | sip：ConfRoom15@contoso.com                                                                                                           |                                                                                                                                                                                                                                                                         |
| 设备帐户密码                                           | 为了简化管理，你可以禁用设备帐户的密码过期，或Surface Hub自动轮换设备帐户密码。 <br> <br>**注意：** 如果以域\用户名格式添加帐户，则初始设置期间将中心与本地 Active Directory 关联。 如果以自定义 username@domain.com 添加帐户，则初始设置期间Azure Active Directory中心关联。 否则，密码轮换将没有效果。                                                                                                                                                                                                                 |                                                                                                                                       | [密码管理](password-management-for-surface-hub-device-accounts.md)                                                                                                                                                 |
| ExchangeWeb 服务 (EWS)                                        | 启用 EWS。 Surface Hub EWS 同步其日历。                                                                                                                                                                                                                                                                                                                          |                                                                                                                                       | [Surface Hub 新式身份验证](surface-hub-modern-auth.md)                                                                                                                                                            |
| 多重身份验证                                        | 在设备帐户上禁用多重身份验证。 当Surface Hub登录后台Exchange用户交互时，它无法响应任何交互式提示，如多重身份验证。                                                                                                                                                                         |                                                                                                                                       |                                                                                                                                                                                                                                                                         |
| MDM 注册详细信息                                            | 如果你想要将设备手动注册到 MDM，则需要具有对 MDM 提供程序和注册 URL 有效的用户凭据。 设备将尝试自动查找注册 URL。 | manage.microsoft.com | [通过 MDM 提供商管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md) |
| 友好名称                                                     | 设备的友好名称是指用户将在尝试以无线方式连接到 Surface Hub 时看到的广播名称。 此名称将突出显示在 Surface Hub 的屏幕上。 我们建议所选的友好名称可识别且唯一，以便用户在尝试连接时可以区分不同的 Surface Hub。             | 会议室 15                                                                                                                    | [首次设置Surface Hub](surface-hub-2s-setup.md)                                                                                                                                                                   |
| 设备名称                                                       | 设备名称既是将用于域加入的名称，也是你将在设备注册到 MDM 中时在 MDM 提供程序中看到的标识。 如果你决定将设备加入域，则你选择的设备名称不得与 Active Directory 域 (中任何其他设备的名称) 。 设备无法加入没有唯一名称的域。  | confroom15                                                                                                                            | [首次设置Surface Hub](surface-hub-2s-setup.md)                                                                                                                                                                   |
| Teams 应用模式                                                    | - 模式 0 - Skype for Business安排Microsoft Teams会议提供高级功能。<br>- 模式 1 — Microsoft Teams安排Skype for Business会议提供高级功能。<br>- 模式 2 - 仅Microsoft Teams模式                                                                                                                                                         |                                                                                                                                       | [更改默认业务通信平台](manage-settings-with-mdm-for-surface-hub.md)                                                                            |

## <a name="device-affiliation"></a>设备附属关系

使用设备附属关系管理用户对 设置 应用的访问权限Surface Hub。 使用Windows 10 协同版运行 (操作系统Surface Hub) ，只有授权用户可以使用 设置 应用调整设置。 由于选择附属关系可能会影响功能可用性，请进行相应的规划以确保用户可以访问预期的功能。

> [!NOTE]
> 在 OOBE 设置的初始开箱即用体验期间，你 (设备) 关联。 如果需要重置设备附属关系，必须重复 OOBE 设置。

### <a name="if-youre-joining-azure-ad"></a>如果你要加入 Azure AD

| 属性                                                 | 用途                                                                                                                                                                                                                                                    | 示例                         | 了解详细信息                                                                                                                        |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Azure AD 租户用户凭据（用户名和密码） | 如果你决定让 azure AD Azure Active Directory (组织) 成为设备的管理员，则需要将 Surface Hub 加入 Azure AD。 若要将帐户加入 Azure AD，你将需要租户中帐户的有效凭据。                                                               | admin1@contoso.com，#MyPassw0rd | [管理员组管理](admin-group-management-for-surface-hub.md)                     |
| 非全局管理员帐户                                | 对于Surface Hub Azure AD 的设备，你可以将管理员权限限制为在 Surface Hub 上管理 设置 应用。 这使你能够仅作用域管理员Surface Hub并阻止可能不需要的管理员访问整个 Azure AD 域。 |                                 | [配置 Surface Hub 上的非全局管理员帐户](surface-hub-2s-nonglobal-admin.md) |

### <a name="if-youre-joining-a-domain"></a>如果你要加入域

| 属性                                           | 用途                                                                                                                                                                                                                        | 示例                                         |
| -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| 要加入的域                                     | 这是将要加入的域，这样所选的安全组即可成为设备的管理员。 你可能需要完全限定的域名 (FQDN)。                                                                          | contoso（短名称）或 contoso.corp.com (FQDN) |
| 域帐户凭据（用户名和密码） | 除非你提供足够的帐户凭据来加入域，否则你将无法加入域。 在提供要加入的域以及要加入该域所需的凭据后，所选的安全组可以更改设备上的设置。 | admin1，#MyPassw0rd                             |
| 管理员安全组别名                         | 这是你的 Active Directory (AD) 中的安全组；此安全组的任何成员都可以更改设备上的设置。                                                                                                                | SurfaceHubAdmins                                |

### <a name="if-youre-using-a-local-admin"></a>如果你使用的是本地管理员

| 属性                                                | 用途                                                                                   | 示例             |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------- |
| 本地管理员帐户凭据（用户名和密码） | 如果你决定不加入 AD 域或 Azure AD，你可以在设备上创建本地管理员帐户。 | admin1，#MyPassw0rd |

### <a name="if-you-need-to-install-certificates-or-apps"></a>如果你需要安装证书或应用

| 属性  | 用途                                                                                                                                                                                                                                                                                        |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| USB 驱动器 | 如果你在首次运行之前知道自己想要安装证书或通用应用，请按照[创建设置包](provisioning-packages-for-certificates-surface-hub.md)中的步骤操作。 你的设置包将在 USB 驱动器上创建。 |

## <a name="post-deployment-checklist"></a>部署后清单

| 选中                                      | 响应                                                                                                                                                                                                          |
| ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **设备帐户同步**                 | ☐是 <br><br>☐ 否                                                                                                                                                                                                |
| **Bitlocker 密钥**                          | ☐保存到文件 (没有附属关系)  <br><br>☐保存在 Active Directory (AD 附属)  <br><br>☐保存在 Azure AD (Azure AD 附属)                                                                           |
| **设备操作系统更新**                      | ☐ Completed                                                                                                                                                                                                       |
| **Windows应用商店更新**                  | ☐ 自动 <br><br>☐ 手动                                                                                                                                                                                      |
| **Microsoft Teams安排的会议**      | ☐收到确认电子邮件 <br><br>☐会议显示在"开始"屏幕上 <br><br>☐一键联接函数 <br><br>☐能够加入音频 <br><br>☐能够加入视频 <br><br>☐能够共享屏幕               |
| **Skype for Business安排的会议**   | ☐收到确认电子邮件<br>☐会议显示在"开始"屏幕上<br>☐一键联接功能正确<br>☐能够加入音频<br>☐能够加入视频<br>☐能够共享屏幕<br>☐能够发送/接收 IM |
| **已受邀时安排的会议** | ☐会议被拒绝                                                                                                                                                                                                |
| **Microsoft Teams临时会议**         | ☐邀请其他用户工作 <br><br>☐能够加入音频 <br><br>☐能够加入视频 <br><br>☐能够共享屏幕                                                                                                |
| **Microsoft Whiteboard**                   | ☐欢迎/开始"屏幕启动 <br><br>☐启动Microsoft Teams                                                                                                                                        |
| **传入Teams/Skype呼叫**              | ☐能够加入音频<br>☐能够加入视频<br>☐能够共享屏幕<br>☐仅能发送/接收 (SKYPE FOR BUSINESS IM)                                                                                      |
| **传入实时视频流**            | ☐最多 2 (Skype for Business) <br>☐最多 4 (Microsoft Teams)                                                                                                                                                  |
| **Microsoft Teams模式 0 行为**        | ☐ Skype for Business/开始"屏幕上显示磁贴<br>☐ UI 会议Skype for Business安排 (Skype会议) <br>☐ UI 会议Teams计划 (Teams会议)                                                 |
| **Microsoft Teams模式 1 行为**        | ☐ Teams/开始"屏幕上的"开始"磁贴<br>☐ UI 会议Skype for Business安排 (Skype会议) <br>☐ UI 会议Teams计划 (Teams会议)                                                              |
| **Microsoft Teams模式 2 行为**        | ☐ Teams/"开始"屏幕上的"开始"磁贴<br>☐可以加入预定Teams会议<br>☐无法加入Skype for Business会议                                                                                       |

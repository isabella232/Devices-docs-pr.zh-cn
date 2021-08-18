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
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: e82392745785f08212a112d023c40aea70f14220
ms.sourcegitcommit: 3810c4310e9f5b5b9ad7b4584eaede2789ccd946
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2021
ms.locfileid: "11902851"
---
# <a name="admin-group-management-for-surface-hub"></a>管理员组管理Surface Hub


可使用设备上的“设置”应用在本地配置每个 Surface Hub。 若要防止未经授权的用户更改设置，“设置”应用要求使用管理员凭据打开该应用。


## <a name="admin-group-management"></a>管理员组管理

可以通过以下方法设置设备的管理员帐户：

- [创建本地管理员帐户](#create-a-local-admin-account)
- [将设备加入 Active Directory 的域](#domain-join-the-device-to-active-directory)
- [Azure AD 加入设备](#azure-ad-join-the-device)
- [在加入 Azure AD 的设备上配置非全局管理员帐户 (Surface Hub 2S) ](#configure-non-global-admin-accounts-on-azure-ad-joined-devices)


### <a name="create-a-local-admin-account"></a>创建本地管理员帐户

若要创建本地管理员，[请在首次运行期间选择使用本地管理员](first-run-program-surface-hub.md)。 这将使用所选的用户名和密码在 Surface Hub 上创建一个本地管理员帐户。 使用这些凭据打开“设置”应用。 

注意：任何目录服务都不会备份本地管理员帐户信息。 我们建议你仅当设备无权访问 Active Directory (AD) 或 Azure Active Directory (Azure AD) 时，才选择本地管理员。 如果决定更改本地管理员的密码，可在“设置”中执行此操作。 但是，如果想要从使用本地管理员帐户更改为使用域或 Azure AD 租户的组，则需要[重置该设备](device-reset-surface-hub.md)，并再次完成首次计划。

### <a name="domain-join-the-device-to-active-directory"></a>将设备加入 Active Directory 的域

可将 Surface Hub 加入 AD 域，支持指定安全组的用户配置设置。 在首次运行时，选择使用[Active Directory 域服务](first-run-program-surface-hub.md#active-directory-domain-services)。 需要提供可加入所选域的凭据以及现有安全组的名称。 属于该安全组成员的任何人都可以输入其凭据并解锁“设置”。

#### <a name="what-happens-when-you-domain-join-your-surface-hub"></a>将 Surface Hub 加入域时会发生什么？
将 Surface Hub 加入域可：
- 将管理员权限授予 AD 中指定安全组的成员。
- 将设备的 BitLocker 恢复密钥存储在 AD 中的计算机对象下，备份该密钥。 有关详细信息，请参阅[保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。
- 同步系统时钟和域控制器，进行加密通信

Surface Hub不支持从域控制器应用组策略或证书。

> [!NOTE]
> 如果 Surface Hub 失去与域的信任（例如，如果在 Surface Hub 加入域后，将其从该域中删除），将无法对设备进行身份验证并打开“设置”。 当决定删除 Surface Hub 与域的信任关系时，首先要[重置设备](device-reset-surface-hub.md)。


### <a name="azure-ad-join-the-device"></a>Azure AD 加入设备

你可以Azure Active Directory (Azure AD) 加入 Surface Hub，以允许来自 Azure AD 租户的 IT 专业人员配置设置。 在首次运行时，选择使用[Microsoft Azure Active Directory](first-run-program-surface-hub.md#microsoft-azure-active-directory)。 将需要提供能够加入所选 Azure AD 租户的凭据。 成功加入 Azure AD 后，将授予相应用户该设备的管理员权限。

默认情况下，所有**全局管理员**都将授予加入 Azure AD 的 Surface Hub 的管理员权限。 凭借 **Azure AD Premium** 或 **Enterprise Mobility Suite (EMS)** 可添加其他管理员：
1.  在 [Azure 经典门户](https://manage.windowsazure.com/)中，单击“Active Directory”****，然后单击组织目录的名称。
2.  在“配置”**** 页面的“设备”**** > “Azure AD 联接设备上的其他管理员”**** 下，单击“已选定”****。
3.  单击“添加”****，选择在 Surface Hub 和其他 Azure AD 联结设备上以管理员身份希望添加的用户。
4.  结束后，单击复选标记按钮，保存更改。

#### <a name="what-happens-when-you-azure-ad-join-your-surface-hub"></a>将 Surface Hub 加入 Azure AD 时会发生什么？
Surface Hub 加入 Azure AD 可：
- 将管理员权限授予 Azure AD 租户中的相应用户。
- 将设备的 BitLocker 恢复密钥存储在加入 Azure AD 的设备帐户下，备份该密钥。 有关详细信息，请参阅[保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)。

#### <a name="automatic-enrollment-via-azure-active-directory-join"></a>通过注册加入Azure Active Directory注册

Surface Hub现在支持通过加入设备以自动注册 Intune Azure Active Directory。 

有关详细信息，请参阅启用自动[Windows 10注册](/intune/windows-enroll#enable-windows-10-automatic-enrollment)。

#### <a name="which-should-i-choose"></a>我应该选择哪一个？

如果组织使用的是 AD 或 Azure AD，我们建议选择“域加入”或“Azure AD 加入”，这主要是出于安全方面的原因。 用户将能够使用自己的凭据进行身份验证和解锁“设置”，并且可移入或移出与域相关联的安全组。

| 选项                                            | 要求                            | 哪些凭据可用于访问“设置”应用？  |
|---------------------------------------------------|-----------------------------------------|-------|
| 创建本地管理员帐户                      | 无                                    | 首次运行时指定的用户名和密码 |
| 加入 Active Directory (AD) 域              | 组织使用 AD               | 域中特定安全组的任意 AD 用户 |
| 将设备加入 Azure Active Directory (Azure AD) | 组织使用 Azure AD Basic   | 仅限全局管理员 |
| &nbsp;                                            | 组织使用 Azure AD Premium 或 Enterprise Mobility Suite (EMS) | 全局管理员和其他管理员 |


### <a name="configure-non-global-admin-accounts-on-azure-ad-joined-devices"></a>在加入 Azure AD 的设备上配置非全局管理员帐户

对于Surface Hub Azure AD 的 Surface Hub v1 和 Surface Hub 2S 设备，Windows 10 协同版 2020 更新允许你将管理员权限限制为在 Surface Hub 上管理 设置 应用。 这使你能够仅作用域管理员Surface Hub并阻止可能不需要的管理员访问整个 Azure AD 域。 若要了解更多信息，请参阅在上[配置非全局管理员Surface Hub。](surface-hub-2s-nonglobal-admin.md)
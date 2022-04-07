---
title: 首次设置Surface Hub
description: 术语\ 0034;首次运行 \ 0034;是指你在首次打开 Microsoft Surface Hub 后将完成的一系列步骤，其含义与\ 0034;全新体验 \ 0034(OOBE) 相同。 本部分将指导你完成该过程。
ms.assetid: 07C9E84C-1245-4511-B3B3-75939AD57C49
ms.reviewer: ''
manager: laurawi
keywords: 首次体验, Surface Hub, 全新体验, OOBE
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: medium
ms.openlocfilehash: 551867ccbb041fe292d9ec60f38bb89acfbc764e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472442"
---
# <a name="first-time-setup-for-surface-hub"></a>首次设置Surface Hub

首次启动Surface Hub时，设备会自动进入首次安装模式，以指导你完成帐户配置和相关设置。

> [!TIP]
> 可以使用预 [配包](#use-provisioning-packages) 自动执行整个安装过程，以确保跨多个 Surface Hub 获得一致的体验。

## <a name="get-started"></a>入门

1. 默认情况下，启用了Cortana来指导你完成此过程。 若要关闭Cortana帮助，请选择麦克风图标。

    :::image type="content" source="images/hub-setup-cortana.png" alt-text="Cortana已启用，可引导你完成此过程。":::

2. **选择你所在的区域。** 确认自动检测到的区域，然后选择 **"是**"。

    :::image type="content" source="images/hub-setup-region.png" alt-text="选择你所在的区域。":::

3. **确认键盘布局。** 选择 **"是**"。

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="确认键盘布局。":::

4. 若要添加第二个键盘，请选择 **"添加"布局**。 否则，请选择 **"跳过**"。

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="添加第二个键盘。":::

5. **连接到网络。** 如果已附加以太网电缆，Surface Hub会自动连接到网络。 或者，可以连接到无线网络。 **注意：** 无法连接到热点中的无线网络， (强制网络门户) 将登录请求重定向到提供商的网站。 选择**下一步** 。

    :::image type="content" source="images/hub-setup-network.png" alt-text="连接到网络。":::

6. **接受Windows 10许可协议。** 选择 **"接受**"。

    :::image type="content" source="images/hub-setup-license.png" alt-text="接受Windows 10许可协议。":::

7. 使用 UPN 地址 (user@contoso.com) 或下级域地址 (CONTOSO\user) **输入设备帐户信息**。 使用与环境匹配的格式并输入密码。

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="输入设备帐户信息。":::

| 环境                                              | 设备帐户的必需格式 |
| -------------------------------------------------------- | ---------------------------------- |
| 设备帐户仅联机托管                     | username@contoso.com               |
| 设备帐户仅托管在本地                | CONTOSO\user                       |
| 设备帐户在联机和本地托管 (混合)  | CONTOSO\user                       |

>[!NOTE]
>尽管可以跳过设置设备帐户，但设备不会完全集成到基础结构中。 如果你现在跳过设置帐户步骤，可在以后使用“设置”应用来添加设备帐户。

8. **输入密码** ，然后选择 **"下一步"。**

9. Surface Hub从上一步中输入的域自动检测Exchange服务器和 SIP 地址信息。 或者，如果需要，请提供Exchange服务器地址，然后选择 **"下一步**"。

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange服务器和 SIP 地址。":::

10. **将此设备命名为名称。** 输入设备的名称或使用建议的名称。 **选择"下一步**"。

    :::image type="content" source="images/hub-setup-name.png" alt-text="将此设备命名为名称。":::

- **友好名称**在 Surface Hub 2S 的左下角可见，在投影到设备时显示。
- **设备名称**标识与 Active Directory 或 Azure Active Directory 关联时以及使用Intune注册设备时的设备。

>[!IMPORTANT]
>如果打算将Surface Hub与 Active Directory 结合使用，则设备名称必须满足 [AD 中计算机名称的标准要求](/troubleshoot/windows-server/identity/naming-conventions-for-computer-domain-site-ou#computer-names)，否则安装将失败。

>[!NOTE]
>如果你想要启用[基础结构上的 Miracast](miracast-over-infrastructure.md)，则必须能够通过 DNS 发现设备名称。 通过允许 Surface Hub 通过动态 DNS 自动注册，或者通过为 Surface Hub 设备名称手动创建 A 或 AAAA 记录，你可以达到此目的。

### <a name="configure-device-admin-accounts"></a>配置设备管理员帐户

只能在第一次安装期间设置设备管理员。 有关详细信息，请参阅：

- [Surface Hub 2S 设备隶属关系](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [管理员组管理](admin-group-management-for-surface-hub.md)

1. **选择管理员帐户的类型。** 选择以下选项之一：Active Directory 域服务、Azure Active Directory或本地管理员。

    :::image type="content" source="images/hub-setup-join.png" alt-text="选择管理员帐户的类型。":::

### <a name="active-directory-domain-services"></a>Active Directory 域服务

1. 如果打算在本地环境中使用Surface Hub，则可以将 Hub 与**Active Directory 域服务**关联。  输入有权将设备加入 Active Directory 的用户的凭据。
2. 选择 Active Directory 安全组，其中包含允许在 Surface Hub 2S 上登录设置应用的成员。
3. 选择 **"完成**"。 设备将启动。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

1. 如果打算使用Microsoft Intune或 MDM 提供程序从云中管理Surface Hub，请选择**Microsoft Azure Active Directory**。
2. 选择"下一步"并使用工作或学校帐户登录。 如果重定向，请使用组织的登录页进行身份验证，并在请求时提供其他凭据。 否则，输入密码并选择 **"下一步"。**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="使用工作或学校帐户登录。":::

>[!NOTE]
>若要配置谁可以使用设置应用管理 Surface Hub，请确保在将设备加入Azure AD之前，在租户中启用自动Intune注册。 然后，Intune策略可用于在 Surface Hub 上[配置非全局管理员](surface-hub-2s-nonglobal-admin.md)。

### <a name="local-administrator-account"></a>本地管理员帐户

- 为本地管理员输入用户名和令人难忘的密码。 (如果忘记了本地管理员密码，则需要 [恢复设备](surface-hub-2s-recover-reset.md) 并重复安装过程。)   

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="为本地管理员帐户输入令人难忘的密码。":::

### <a name="choose-privacy-settings-for-your-device"></a>为设备选择隐私设置

- 从可用隐私设置中选择，然后选择 **"接受"。**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="选择隐私设置。":::

### <a name="use-provisioning-packages"></a>使用预配包

可以自定义首次设置选项，从而确保跨多个 Surface Hub 获得一致的体验。

1. 首先，请查看 ["创建预配包](provisioning-packages-for-surface-hub.md) "中的文档，并将预配包保存到 USB 拇指驱动器。
2. 在) 上方的设置步骤中看到"许可协议"页 (步骤 6 时，请将 USB 缩略图驱动器插入到其中一个 USB 端口。
3. 出现提示时，选择要使用的预配包。
4. 如果创建了多个设备 CSV 文件，则可以选择设备配置。
5. 按照说明完成首次安装。

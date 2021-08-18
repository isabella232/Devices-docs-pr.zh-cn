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
ms.openlocfilehash: 947d73febb41562b44d5ecb102511be314ad987e
ms.sourcegitcommit: 3810c4310e9f5b5b9ad7b4584eaede2789ccd946
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2021
ms.locfileid: "11902911"
---
# <a name="first-time-setup-for-surface-hub"></a>首次设置Surface Hub

首次启动 Surface Hub时，设备会自动进入首次设置模式，以指导你完成帐户配置和相关设置。

> [!TIP]
> 可以使用预配包自动执行整个设置 [过程](#use-provisioning-packages) ，以确保跨多个 Surface Hub 实现一致的体验。

## <a name="get-started"></a>入门

1. 默认情况下，Cortana可指导你完成该过程。 若要关闭Cortana帮助，请选择麦克风图标。

    :::image type="content" source="images/hub-setup-cortana.png" alt-text="Cortana可指导你完成此过程":::

2. **选择你所在的区域。** 确认自动检测区域，**然后选择是。**

    :::image type="content" source="images/hub-setup-region.png" alt-text="选择你的地区":::

3. **确认键盘布局。** 选择 **"是"。**

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="确认键盘布局":::

4. 若要添加第二个键盘，请选择"**添加布局"。** 否则 **，请选择跳过**。

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="添加第二个键盘":::

5. **连接网络。** 如果已连接以太网电缆，Surface Hub自动连接到网络。 或者，你可以连接到无线网络。 **注意：** 你无法连接到热点的无线网络 (强制门户) 将登录请求重定向到提供商的网站。 选择**下一步** 。

    :::image type="content" source="images/hub-setup-network.png" alt-text="连接到网络":::

6. **接受Windows 10许可协议。** 选择 **接受**。

    :::image type="content" source="images/hub-setup-license.png" alt-text="接受Windows 10许可协议":::

7. **使用** CONTOSO\user (user@contoso.com) UPN 地址或下层域 (输入设备帐户) 。 使用符合你的环境的格式并输入密码。

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="输入设备帐户信息":::

| 环境                                              | 设备帐户的必需格式 |
| -------------------------------------------------------- | ---------------------------------- |
| 设备帐户仅联机托管                     | username@contoso.com               |
| 设备帐户仅托管在本地                | CONTOSO\user                       |
| 设备帐户在混合部署中联机 (本地)  | CONTOSO\user                       |

>[!NOTE]
>尽管你可以跳过设置设备帐户，但设备不会完全集成到你的基础结构中。 如果你现在跳过设置帐户步骤，可在以后使用“设置”应用来添加设备帐户。

8. **输入您的密码，** 然后选择"下一 **步"。**

9. Surface Hub自动检测Exchange步骤中输入的域中的服务器和 SIP 地址信息。 或者，如果需要，提供Exchange服务器地址，然后选择"下一**步"。**

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange服务器和 SIP 地址":::

10. **为此设备命名。** 输入设备名称或使用建议的名称。 **选择"下一步"。**

    :::image type="content" source="images/hub-setup-name.png" alt-text="为此设备命名":::

- 友好**名称**显示在 2S Surface Hub左下角，在计划到设备时显示。
- 设备**名称**标识与 Active Directory 或 Azure Active Directory关联时的设备，以及向 Intune 注册设备时。

>[!NOTE]
>如果你想要启用[基础结构上的 Miracast](miracast-over-infrastructure.md)，则必须能够通过 DNS 发现设备名称。 通过允许 Surface Hub 通过动态 DNS 自动注册，或者通过为 Surface Hub 设备名称手动创建 A 或 AAAA 记录，你可以达到此目的。

### <a name="configure-device-admin-accounts"></a>配置设备管理员帐户

只能在第一次安装期间设置设备管理员。 有关详细信息，请参阅：

- [Surface Hub 2S 设备附属关系](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [管理员组管理](admin-group-management-for-surface-hub.md)

1. **选择管理员帐户的类型。** 选择下列选项之一：Active Directory 域服务、Azure Active Directory或本地管理员。

    :::image type="content" source="images/hub-setup-join.png" alt-text="选择管理员帐户类型":::

### <a name="active-directory-domain-services"></a>Active Directory 域服务

1. 如果你打算在本地环境中Surface Hub，可以将 Hub 与**Active Directory 域服务关联**。  输入有权将设备加入 Active Directory 的用户的凭据。
2. 选择 Active Directory 安全组，其中包含允许登录到 设置 2S Surface Hub应用的成员。
3. 选择"**完成"。** 设备将启动。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

1. 如果你打算使用 Surface Hub MDM 提供程序Microsoft Intune云中管理**Microsoft Azure Active Directory。**
2. 选择"下一步"，然后使用工作或学校帐户登录。 如果重定向，则使用组织的登录页进行身份验证，并提供其他凭据（如果需要）。 否则，请输入您的密码，然后选择"下一 **步"。**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="使用工作或学校帐户登录":::

>[!NOTE]
>若要配置谁可以使用 设置应用管理 Surface Hub，请确保在将设备加入 Azure AD 之前在租户中启用了自动 Intune 注册。 然后，可以使用 Intune 策略在 Surface Hub [上配置](surface-hub-2s-nonglobal-admin.md) 非全局管理员。

### <a name="local-administrator-account"></a>本地管理员帐户

- 输入本地管理员的用户名和易记密码。 (如果你忘记了本地管理员密码，则需要恢复 [设备](surface-hub-2s-recover-reset.md) 并重复设置过程。)   

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="输入本地管理员帐户的易记密码":::

### <a name="choose-privacy-settings-for-your-device"></a>选择设备的隐私设置

- 从可用的隐私设置中选择，然后选择接受 **。**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="选择隐私设置":::

### <a name="use-provisioning-packages"></a>使用预配包

你可以自定义首次设置选项，从而确保跨多个 Surface Hub 实现一致的体验。

1. 首先，请查看创建预配包 [中的文档，](provisioning-packages-for-surface-hub.md) 将预配包保存到 U 盘。
2. 在开始设置过程之前，将 U 盘插入其中一个 USB 端口。
3. 当系统提示时，选择你要使用的预配包。
4. 如果你创建了多台设备 CSV 文件，你将可以选择设备配置。
5. 按照说明完成首次安装。

---
title: 首次运行计划 (Surface Hub)
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
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: af6f6cc71a94d075341637499fe98f8206157e49
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576572"
---
# <a name="first-run-program-surface-hub"></a>首次运行计划 (Surface Hub)


术语“首次运行”是指你在首次打开 Microsoft Surface Hub 后将完成的一系列步骤，其含义与“全新体验”(OOBE) 相同。 本部分将指导你完成该过程。

现在，你应该已完成前面所有步骤：

-   [为 Surface Hub 准备你的环境](prepare-your-environment-for-surface-hub.md)
-   [以物理方式安装 Surface Hub 设备](physically-install-your-surface-hub-device.md)，并
-   [设置工作表](setup-worksheet-surface-hub.md)

假定情况的确如此，则首次运行应当既简单又快捷。
正常的过程需要完成六个步骤：

1.  [“你好”页面](#first-page)
2.  [“为你设置”页面](#set-up-for-you)
3.  [“设备帐户”页面](#device-account)
4.  [“为此设备命名”页面](#name-this-device)
5.  [“为此设备设置管理员”页面](#setup-admins)
6.  [更新 Surface Hub](#update-surface-hub)

每个部分还包含在某些内容不同时你可能需要采用的路径的相关信息。 例如，大多数 Surface Hub 将使用有线网络连接，不过其中有一些将改为以无线方式进行设置。 将在适当时介绍详细信息。

>[!NOTE]
>在开始之前，应该已设置并准备好 Surface Hub 附带的单独键盘。 有关详细信息，请参阅 Surface Hub 设置指南。

 

## <a name="hi-there-page"></a><a href="" id="first-page"></a>“你好”页面


这是你在首次打开 Surface Hub 时将看到的第一个屏幕。 这是你输入设备的本地化信息的位置。

>[!NOTE]
>这也是开始部署预配包的可选过程的位置。 如果这就是你需要执行的操作，请参阅[创建预配包](provisioning-packages-for-certificates-surface-hub.md)。

 选择语言后会显示初始设置选项。

![显示 ICD 选项清单的图像。](images/setuplocale.png)

### <a name="details"></a>详细信息

如果显示的默认值正确无误，你可以单击**下一步**继续操作。 如果有误，将需要在相应的框中输入数据。

-   **国家/地区：** 选择将使用 Surface Hub 的国家或地区。
-   **应用语言：** 应用和功能将采用此语言和语言格式进行显示。
-   **键盘布局：** 为将用于设备的屏幕键盘和物理键盘选择键盘布局。
-   **时区：** 选择将使用 Surface Hub 的国家/地区的时区。

### <a name="what-happens"></a>会发生什么情况？

>[!NOTE]
> 在此页面上输入设置后，将无法返回到此屏幕，除非你重置设备（请参阅[设备重置](device-reset-surface-hub.md)）。 确保设置已正确配置，然后再继续。

 

这些设置被接受后，设备将检查有线网络连接。 如果连接良好，它将显示 [“为你设置”页面](#set-up-for-you)。 如果有线连接存在问题，设备将显示 [“网络设置”页面](#network-setup)。

如果找不到任何有线连接，设备将尝试设置无线连接，并将显示 [“网络设置”页面](#network-setup)。

## <a name="network-setup-page"></a><a href="" id="network-setup"></a>“网络设置”页面


如果你的设备未检测到可用于连接到网络或 Internet 的有线连接，你将看到此页面。 你可以在此处连接到无线网络，也可以跳过建立网络连接步骤。

![显示“网络设置”页面的图像。](images/setupnetworksetup-1.png)

### <a name="details"></a>详细信息

仅在设备无法检测到有线网络时，才显示此屏幕。 如果你看到此屏幕，你有三个选项：

-   可以选择显示的无线网络之一。 如果网络是安全的，你将转到登录页面。 有关详细信息，请参阅 [无线网络设置](#wireless) 。
-   单击**跳过此步骤**以跳过连接到网络步骤。 你将转到[“为你设置”页面](#set-up-for-you)。
    >[!NOTE]
    >如果跳过此页面，设备将没有网络连接，并且需要网络连接的所有工作（包括系统更新以及电子邮件和日历同步）均将无法在 Surface Hub 上进行。 稍后可以使用无线网络连接到无线网络，设置 (无线网络[管理](wireless-network-management-for-surface-hub.md)) 。

     

-   可以在此屏幕可见时插入网络电缆。 设备将检测它，并将**下一步**添加到屏幕。 单击**下一步**以继续进行有线连接。

### <a name="what-happens"></a>会发生什么情况？

如果设备具有有线连接，当它启动并且可以建立网络或 Internet 连接时，将不显示此页。 如果要将设备连接到无线连接，请确保首次运行时未插入任何以太网电缆，以便可转至此屏幕。 无论你现在选择设置什么内容，你都可以稍后 [使用“设置”](wireless-network-management-for-surface-hub.md) 设置不同的连接。

如果要从此页连接到安全的无线网络，请单击所选的网络，然后提供必要信息（密码或帐户凭据）以进行连接。 请参阅 [无线网络设置](#wireless)。

## <a name="wireless-network-setup"></a><a href="" id="wireless"></a>无线网络设置


当你已选择安全的无线网络时，将显示此页面。

![显示“无线网络设置”页面的图像。](images/setupnetworksetup-3.png)

### <a name="details"></a>详细信息

-   **用户名：** 输入选定无线网络的用户名。
-   **密码：** 这是该网络的密码。

### <a name="what-happens"></a>会发生什么情况？

设备将尝试连接到指定网络。 如果成功，你将转到[“为你设置”页面](#set-up-for-you)。

## <a name="network-proxy-setup"></a><a href="" id="proxy"></a>网络代理设置


当设备检测到状态为有限连接的有线连接时，将显示此页面。 你有三个选项：

-   可以选择使用无线网络，而不是有限的有线连接。

-   可通过选择**跳过此步骤**跳过连接到网络步骤。 你将转到[“为你设置”页面](#set-up-for-you)。

    > [!NOTE]
    > 如果跳过此步骤，设备将没有网络连接，并且需要网络连接的所有工作（包括诸如电子邮件和日历同步等操作）均将无法在 Surface Hub 上进行。 稍后可以使用无线网络连接到无线网络，设置 (无线网络[管理](wireless-network-management-for-surface-hub.md)) 。

-   可以选择**输入代理设置**，这将允许你指定如何使用网络代理。 你将转到下一个屏幕。

    ![显示“网络代理”页面的图像。](images/setupnetworksetup-2.png)

    这是你将看到的屏幕（如果你在上一屏幕上单击了**输入代理设置**）。

    ![显示代理服务器设置详细信息的图像。](images/setupnetworksetup-4.png)

### <a name="details"></a>详细信息

为了进行网络连接，你将需要填写脚本名称或代理服务器和端口信息。

-   **代理脚本：** 提供代理脚本的地址。
-   **代理服务器和端口：** 可提供代理服务器地址和端口。

### <a name="what-happens"></a>会发生什么情况？

当你单击**下一步**时，设备将尝试连接到代理服务器。 如果成功，你将转到[“为你设置”页面](#set-up-for-you)。

可通过选择**跳过此步骤**跳过连接到网络步骤。 你将转到[“为你设置”页面](#set-up-for-you)。

>[!NOTE]
>如果跳过此步骤，设备将没有网络连接，并且需要网络连接的所有工作（包括诸如电子邮件和日历同步等操作）均将无法在 Surface Hub 上进行。 稍后可以使用无线网络连接到无线网络，设置 (无线网络[管理](wireless-network-management-for-surface-hub.md)) 。

 

## <a name="set-up-for-you-page"></a><a href="" id="set-up-for-you"></a>“为你设置”页面


此屏幕纯粹用于提供信息，将显示默认情况下启用的建议设置。

![显示“为你设置”页面的图像。](images/setupsetupforyou.png)

### <a name="details"></a>详细信息

你应阅读此屏幕，并留意默认情况下启用的服务。 所有这些设置都可以使用“设置”应用进行更改（如果需要），不过应注意执行此操作所产生的影响。 有关详细信息，请参阅 [Surface Hub 简介](intro-to-surface-hub.md)。

检查完设置后，单击**下一步**以继续。

### <a name="what-happens"></a>会发生什么情况？

显示在该页面上的设置均已启用，并且在完成首次运行之前无法进行更改。

## <a name="device-account-page"></a><a href="" id="device-account"></a>“设备帐户”页面


在此页面上，Surface Hub 将要求提供之前配置的设备帐户的凭据。 （请参阅[创建和测试设备帐户](create-and-test-a-device-account-surface-hub.md)。）Surface Hub 将尝试发现帐户的各种属性，并且可能会在失败时要求在其他页面上提供更多信息。

>[!NOTE]
>本部分不包括在首次运行期间可能出现的特定错误。 有关错误的详细信息，请参阅 [Surface Hub 疑难解答](troubleshoot-surface-hub.md)。


![显示“输入设备帐户信息”页面的图像。](images/setupdeviceacct.png)

### <a name="details"></a>详细信息

使用**用户主体名称 (UPN)** 或**域\\用户名**作为第一个输入字段中的帐户标识符。 使用与环境匹配的格式，并输入密码。


|                      环境                      | 设备帐户的必需格式 |
|-------------------------------------------------------|------------------------------------|
|         设备帐户仅联机托管。         |        username@domain.com         |
|        设备帐户仅本地托管。         |          域\用户名           |
| 设备帐户既可联机托管，也可本地托管（混合）。 |          域\用户名           |

单击**跳过设置设备帐户**可跳过设置设备帐户步骤。 但是，如果你不设置设备帐户，设备将不完全集成到你的基础结构中。 例如，用户将无法：

-   在欢迎屏幕上查看会议日历
-   从欢迎屏幕开始会议
-   通过 OneNote 以电子邮件形式发送白板内容
-   将 Skype for Business 用于会议

如果你现在跳过设置帐户步骤，可在以后使用“设置”应用来添加设备帐户。

如果你单击**跳过设置设备帐户**，设备将显示一个对话框，提示如果设备没有设备帐户将发生什么情况。 如果你选择**是，跳过此设置**，你将转到[“为此设备命名”页面](#name-this-device)。

![显示用于确认要跳过创建设备帐户的消息的图像。](images/setupskipdeviceacct.png)

### <a name="what-happens"></a>会发生什么情况？

设备将使用设备帐户的 UPN 或域\\用户名及密码执行以下操作：

-   检查该帐户是否存在于 Active Directory (AD) 或 Azure Active Directory (Azure AD) 中：

    -   如果已输入 UPN：设备将在 Azure AD 中查找该帐户。
    -   如果已输入域\\用户名：设备将在 AD 中查找该帐户。
-   查找帐户邮箱的 Microsoft Exchange Server。
-   查找帐户的会话初始协议 (SIP) 地址。
-   提取帐户的显示名称和别名属性。

## <a name="exchange-server-page"></a><a href="" id="exchange-server"></a>Exchange Server 页面


此页面将仅在存在问题时才显示。 通常，这意味着已在 Active Directory (AD) 或 Azure Active Directory (Azure AD) 中找到你提供的设备帐户，但未发现该帐户的 Exchange Server。

![显示 Exchange Server 页面的图像。](images/setupexchangeserver-01.png)

### <a name="details"></a>详细信息

输入托管设备帐户邮箱的 Exchange Server 的名称。

单击**跳过设置 Exchange 服务这一步**可跳过此步骤。 如果跳过，用户将无法：

-   在欢迎屏幕上查看会议日历。
-   从欢迎屏幕开始会议。
-   通过 OneNote 以电子邮件形式发送白板内容。

有关设置依赖项的详细信息，请参阅 [Surface Hub 简介](intro-to-surface-hub.md) 。

以后可通过使用“设置”应用来为设备帐户启用 Exchange 服务。

如果你单击**跳过设置 Exchange 服务这一步**，设备将显示一个对话框，提示将发生什么情况。 如果你选择**是，跳过此设置**，将不设置 Exchange 服务。

![显示当你跳过设置 Exchange 服务时显示的确认消息的图像。](images/setupexchangeserver-02.png)

### <a name="what-happens"></a>会发生什么情况？

Surface Hub 将尝试在你在此处输入的 Exchange Server 上验证设备帐户。 如果 Exchange Server 可以访问并验证，将继续首次运行。

如果你选择跳过设置 Exchange 服务步骤，Surface Hub 将停止查找 Exchange Server，而 Exchange 服务（邮件和日历）将处于禁用状态。

## <a name="exchange-policies-page"></a><a href="" id="exchange-policies"></a>Exchange 策略页面


此页面将在以下情况下显示：

-   设备帐户使用 Exchange Active Sync (EA) 策略，其中 PasswordEnabled 策略设置为 1。
-   没有到 Exchange 的连接。
-   Exchange 返回一个指示错误的状态代码。 （例如：帐户已预配给过多的设备。）
-   Exchange 支持的协议不受 Surface Hub 支持。
-   Exchange 返回错误的 XML。

![显示“Exchange 策略”页面的图像。](images/setupexchangepolicies.png)

### <a name="details"></a>详细信息

此页面纯粹用于提供信息，因此无需任何输入。 但是，有两个选项可用于继续操作：提前跳过或重试导致错误的验证。 在决定哪个选项最适合之前，请阅读下面的**会发生什么情况？** 部分。 在单击其中一个选项前，你可以解决别处的问题。

-   **若要继续使用不受支持的策略，请单击此处**：单击此项可继续首次运行。 Surface Hub 将不能使用 Exchange 服务或同步。
-   **重试**：重新检查 Exchange Server 上的策略。

### <a name="what-happens"></a>会发生什么情况？

Surface Hub 检查设备帐户的 EAS 策略是否已将 PasswordEnabled 策略设置为 0 (False)。 如果未这样做，邮件和日历将无法同步，Surface Hub 将无法使用任何 Exchange 服务。 你可以使用电脑中的 Exchange 管理工具来检查设备帐户是否已将 PasswordEnabled 策略设置为 0。 如果未这样做，可重新配置该帐户并单击此处的**重试**。

如果策略已正确配置，请检查你的设备是否已正确连接到网络或 Internet，以及是否可以访问 Exchange Server，因为在 Surface Hub 无法访问 Exchange Server 时也会显示此页面。

无法访问 Exchange 的另一个可能的原因是由于基于证书的身份验证。 你可能由于证书问题而停留在此页面上。 注意：如果设备显示错误代码 0x80072F0D 或 0X800C0019，则需要使用证书。 由于已在首次运行过程的第一个页面上完成预配，因此你必须禁用 Exchange 服务，方法是单击**单击此处以继续使用不受支持的策略**，然后通过“设置”应用安装正确的证书。

如果你选择跳过此检查，Surface Hub 将停止查找 Exchange Server 和验证 EAS 策略，而 Exchange 服务将处于禁用状态。 有关设置依赖项的详细信息，请参阅 [Surface Hub 简介](intro-to-surface-hub.md) 。

## <a name="name-this-device-page"></a><a href="" id="name-this-device"></a>“为此设备命名”页面


此页面要求你提供两个将用于标识 Surface Hub 的名称。

![显示“为此设备命名”页面的图像。](images/setupnamedevice.png)

### <a name="details"></a>详细信息

如果显示的默认值正确无误，你可以单击**下一步**继续操作。 否则，请在一个或两个文本框中输入数据。

-   **友好名称：** 这是用户在需要以无线方式连接到 Surface Hub 时将看到的名称。
-   **设备名称：** 可根据屏幕上的描述设置为任何唯一名称。

只要两个名称符合长度要求且未使用受限的字符，就可以通过单击**下一步**转到下一页面 [为此设备设置管理员](#setup-admins)。

### <a name="what-happens"></a>会发生什么情况？

Surface Hub 要求设备的两个名称，其默认为：

-   **友好名称：** 默认为设备帐户的显示名称
-   **设备名称：** 默认为设备帐户的别名

虽然可在以后更改这两个名称之一，但请记住：

-   友好名称应可识别且不相同，以便用户在尝试无线连接时可以区分不同的 Surface Hub。
-   如果你决定域加入设备，设备名称不得与帐户的 Active Directory 域上的任何其他设备同名。 如果设备使用的名称与另一台已加入域的设备名称相同，该设备将无法加入域。

>[!NOTE]
>如果你想要启用[基础结构上的 Miracast](miracast-over-infrastructure.md)，则必须能够通过 DNS 发现设备名称。 通过允许 Surface Hub 通过动态 DNS 自动注册，或者通过为 Surface Hub 设备名称手动创建 A 或 AAAA 记录，你可以达到此目的。

## <a name="set-up-admins-for-this-device-page"></a><a href="" id="setup-admins"></a>“为此设备设置管理员”页面


在此页面上，你将根据希望如何设置要本地管理你的设备的管理员帐户，从多个选项中进行选择。

由于每个 Surface Hub 可由任意数量的经过身份验证的员工使用，因此如果锁定设置，他们将无法在会话之间进行更改。 仅管理员可以在设备上和此页面上配置设置，你将选择哪种类型的管理员可拥有该权限。

>[!NOTE]
>此页面的主要用途是确定谁可以从设备的 UI 配置设备；即，实际上谁可以访问设备、登录、打开“设置”应用以及更改“设置”。

 

![显示“为此设备设置管理员”页面的图像。](images/setupsetupadmins.png)

### <a name="details"></a>详细信息

选择三个可用选项之一：

-   **使用 Microsoft Azure Active Directory**
-   **使用 Active Directory 域服务**
-   **使用本地管理员**

### <a name="what-happens"></a>会发生什么情况？

这是你选择某一选项时会发生的情况。

-   **使用 Microsoft Azure Active Directory**

    单击此选项，可将设备加入 Azure AD。 单击**下一步**后，设备将重新启动以应用某些设置，之后你将转到 [使用 Microsoft Azure Active Directory](#use-microsoft-azure) 页面，并要求你输入加入 Azure AD 所需的凭据。 已加入组织的 Azure 全局管理员角色的成员将能够使用 设置 应用。 将允许的特定人员取决于你的 Azure AD 订阅，以及你为你的 Azure AD 组织配置设置的方式。
    
    > [!IMPORTANT]
    > 若要配置谁可以使用 设置应用管理 Surface Hub，请确保在将设备加入 Azure AD 之前在租户中启用了自动[Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)注册。 然后，可以使用 Intune 策略在 Surface Hub [上配置](surface-hub-2s-nonglobal-admin.md) 非全局管理员。

-   **使用 Active Directory 域服务**

    单击此选项，可将设备加入 AD。 单击**下一步**后，你将转到 [使用 Active Directory 域服务](#use-active-directory) 页面，并要求你输入加入特定域所需的凭据。 加入后，你可以从已加入域中选取安全组，该安全组中的用户将能够使用“设置”应用。

-   **使用本地管理员**

    选择此选项将允许你创建一个本地管理员。此管理员不受任何目录服务支持，因此我们建议你仅在设备无法访问 Azure AD 或 AD 时才选择此选项。 在[使用本地管理员](#use-a-local-admin)页面上创建管理员的用户名和密码后，每当你打开“设置”应用时，都需要重新输入这些相同的凭据。

    注意：本地管理员必须具有对 Surface Hub 的物理访问权限才能登录。

>[!NOTE]
>完成此过程后，将无法更改设备的管理员选项，除非你重置设备。

 

### <a name="use-microsoft-azure-active-directory"></a><a href="" id="use-microsoft-azure"></a>使用 Microsoft Azure Active Directory

如果你已决定将 Surface Hub 加入 Azure Active Directory (Azure AD)，你将看到**接下来会发生什么情况**这一页面。 阅读它，然后单击**下一步**以转到**让我们进行登录**页面。

加入 Azure AD 主要有两项好处：

1.  你组织中的某些员工将能够以管理员身份访问设备，并且将能够启动“设置”应用和配置设备。 具有管理员权限的人员将在你的 Azure AD 订阅中进行定义。

2.  如果你的 Azure AD 已连接到移动设备管理 (MDM) 解决方案，设备将注册该 MDM 解决方案，以便你可以应用策略和配置。

    ![显示当你使 Surface Hub 加入 Azure Active Directory 时的消息的图像。](images/setupjoiningazuread-1.png)

### <a name="details"></a>详细信息

以下输入是必需的：

-   **用户的 UPN：** 可以加入 Azure AD 的帐户的用户主体名称 (UPN)。
-   **密码：** 用于加入 Azure AD 的帐户的密码。

![显示帐户登录信息的图像。](images/setupjoiningazuread-2.png)

如果你执行到此步骤，但不具有有效的 Azure AD 帐户凭据，设备将允许你通过创建一个本地管理员帐户来继续操作。 单击**改为使用本地帐户设置 Windows**。

![显示“设置管理员帐户”页面的图像。](images/setupjoiningazuread-3.png)

### <a name="what-happens"></a>会发生什么情况？

输入有效的 Azure AD 帐户凭据后，设备将尝试加入关联的 Azure AD 组织。 如果此操作成功，设备将预配该组织中的员工，以使其成为该设备上的本地管理员。 如果你的 Azure AD 租户已针对设备进行配置，设备还将在 MDM 中进行注册。

### <a name="use-active-directory-domain-services"></a><a href="" id="use-active-directory"></a>使用 Active Directory 域服务

此页面将要求提供用于加入域的凭据，以便 Surface Hub 可以预配一个安全组作为设备管理员。

设备加入域后，你必须从已加入的域指定一个安全组。 此安全组将预配为 Surface Hub 上的管理员，并且该安全组中的任何人都可以通过输入其域凭据来访问“设置”。

![显示“使用域加入设置管理员”页面的图像。](images/setupdomainjoin.png)

### <a name="details"></a>详细信息

以下输入是必需的：

-   **域：** 这是要加入的域的完全限定的域名 (FQDN)。 此域中的安全组可用于管理设备。
-   **用户名：** 具有加入指定域足够权限的帐户的用户名。 
-   **密码：** 该帐户的密码。

验证完凭据后，系统将要求你键入安全组名称。 此输入是必需的。

![显示“输入安全组”页面的图像。](images/setupsecuritygroup-1.png)

### <a name="what-happens"></a>会发生什么情况？

通过从 [“使用 Active Directory 域服务”页面](#use-active-directory) 使用提供的域和帐户凭据，并从 [“为此设备命名”](#name-this-device) 页面使用设备名称，Surface Hub 将尝试加入域。 如果加入成功，首次运行将继续，并且系统将要求你提供安全组。 如果加入失败，首次运行将暂停，并且系统将要求你更改提供的信息。

如果加入成功，你将看到**输入安全组**页面。 在此页面上单击**选择**按钮时，设备将在你的域上搜索指定安全组。 如果找到该组，将对其进行验证。 单击**完成**以完成首次运行过程。

>[!NOTE]
>如果域加入 Surface Hub，则在未重置设备的情况下无法取消加入设备。

 

### <a name="use-a-local-admin"></a>使用本地管理员

如果你决定不使用 Azure Active Directory (Azure AD) 或 Active Directory (AD) 来管理 Surface Hub，你将需要创建一个本地管理员帐户。

![显示本地管理员的“设置管理帐户”的图像。](images/setuplocaladmin.png)

### <a name="details"></a>详细信息

以下输入是必需的：

-   **用户名：** 这是将为此 Surface Hub 创建的本地管理员帐户的用户名。
-   **密码：** 这是设备帐户的密码。
-   **重新输入密码：** 验证上一个框中的密码。

### <a name="what-happens"></a>会发生什么情况？

此页面将尝试使用你在此处输入的凭据创建新的管理员帐户。 如果成功，首次运行将结束。 如果失败，系统将要求你提供其他凭据。

## <a name="update-the-surface-hub"></a><a href="" id="update-surface-hub"></a>更新 Surface Hub


>[!IMPORTANT]
>在进行更新前，请务必阅读[保存 BitLocker 密钥](save-bitlocker-key-surface-hub.md)，以确保你具有该密钥的备份。

 

若要获取最新的功能和修补程序，在完成上述所有首次运行步骤后，应立即更新 Surface Hub。

1.  确保设备可以访问更新Windows服务器。 
2.  打开“设置”，然后依次单击**更新和安全**、**Windows 更新**和**检查更新**。
3.  如果有可用的更新，将下载它们。 下载完成后，单击**立即更新**按钮即可安装更新。
4.  安装更新后，请按照屏幕上的提示操作。 你可能需要重新启动设备。

 

 






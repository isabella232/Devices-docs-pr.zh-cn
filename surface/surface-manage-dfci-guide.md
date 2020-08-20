---
title: Surface UEFI 设置的 Intune 管理
description: 本文介绍如何在 Microsoft Intune 中配置 DFCI 环境，以及如何管理目标 Surface 设备的固件设置。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 08/19/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
ms.openlocfilehash: 9d83fe9b7febf996d2cb314399505ed050a69a92
ms.sourcegitcommit: b94832cba98e01014f7d184c85d79f8339e046c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941661"
---
# Surface UEFI 设置的 Intune 管理

## 简介

管理云中的设备的功能在整个生命周期中进行了重大化。 借助 Microsoft Intune (中内置的设备配置接口 (DFCI [) ](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)) 配置文件，Surface UEFI 管理层将现代管理堆叠到 UEFI 硬件级别。 DFCI 支持零触控设置，消除 BIOS 密码，提供对安全设置的控制，包括启动选项和内置外围设备，并在未来为高级安全方案设置分页工作。 有关常见问题的解答，请参阅 [Ignite 2019：公布 Intune 的 Surface UEFI 设置远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。

### Background

与运行 Windows 10 的任何计算机类似，Surface 设备所存储在 SoC 中的代码，后续的 CPU 可将 CPU 与硬盘连接、显示设备、USB 端口以及其他设备。 存储在此只读的 () 内存中的程序称为固件 (而存放在动态媒体中时，存储在动态媒体中的程序称为软件) 。

与当市场中可用的其他 Windows 10 设备相比，Surface 使 IT 管理员可通过一组丰富的 UEFI 配置设置来配置和管理固件。 这在通过移动设备管理或 MDM) 策略、Configuration Manager 或组策略实施时，基于软件的策略管理提供基于软件 (的硬件控制。 例如，将设备部署到高度安全性信息的区域，可能无法在硬件级别删除功能，防止相机使用。 从设备角度来看，通过固件设置关闭相机以物理方式删除相机。 比较在固件级别管理的增强安全性，使其仅处理于操作系统软件设置。 例如，如果通过域环境中的策略设置禁用 Windows 音频服务，本地管理员仍然可以重新启用该服务。

### DFCI 与 SEMM

到目前为止，使用长期执行手动 IT 密集任务的开头，管理开发需要将设备注册到 Surface Enterprise 管理模式 (SEMM) 的固件。 例如，SEMM 要求 IT 人员实际访问每台电脑，以在证书管理过程中输入两位数 PIN。 SEMM 在统一的本地环境中为组织保留了不错的解决方案，但其复杂性和 IT 密集性要求将充分利用费用。

现在，借助 Microsoft Intune 中新集成的 UEFI 固件管理功能，因此锁定硬件的功能得到了简化，并且通过新功能用于在单个主机中进行配置、安全和简化更新，现在统一 [标识为 Microsoft 终结点管理器](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)。 下图显示了直接在设备中查看的 UEFI 设置 (左侧) ，以及在适当的终结点 (管理员) 。

![设备与终结点管理器 (控制) 台的 UEFI (设置) ](images/uefidfci.png)

从根本上来讲，DFCI 支持零触摸管理，不再需要 IT 管理员手动互动。 在 Intune 中使用设备配置文件功能通过 Windows Autopilot 部署 DFCI。 设备配置文件让你可以添加和配置这些设置，然后可以将其部署到组织内管理中注册的设备。 设备收到该设备配置文件后，功能和设置将自动应用。 常见设备配置文件的示例包括电子邮件、设备限制、VPN、Wi-Fi 和管理模板。 DFCI 只是一个附加设备配置文件，使你能够从云管理 UEFI 配置设置，而无需维护本地基础结构。  

## 支持的设备

以下设备支持 DFCI：

- Surface Pro 7
- Surface Pro X
- Surface 笔记本电脑 3
- Surface Book 3

> [!NOTE]
> Surface Pro X 不支持针对内置相机、音频和 Wi-Fi/Bluetooth。

## 必备条件

- 设备必须由 Microsoft 云解决方案提供商未 [面向 Windows Autopilot (CSP 或](https://partner.microsoft.com/membership/cloud-solution-provider) OEM) 分发商注册。

- 在为 Surface 配置 DFCI 之前，你应熟悉  [Microsoft Intune](https://docs.microsoft.com/intune/) 和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) 中的 Autopilot 配置 (Azure AD) 。

## 开始之前

将目标 Surface 设备添加到 Azure AD 安全组。 有关创建和管理安全组的详细信息，请参阅 [Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。

## 为 Surface 设备配置 DFCI 管理

DFCI 环境要求设置一个 DFCI 配置文件，其中包含设置和 Autopilot 配置文件，以将设置应用到已注册设备。 还建议注册状态配置文件，以确保在用户首次启动设备时，在 OOBE 设置过程中设置已被推送。 此指南介绍了如何配置 DFCI 环境和管理针对 Surface 设备的 UEFI 配置设置。

## 创建 DFCI 配置文件

在配置 DFCI 策略设置之前，请首先创建一个 DFCI 配置文件并将其分配到包含目标设备的 Azure AD 安全组。

1. 在 devicemanagement.microsoft.com。
2. 在 Microsoft 终结点管理器管理中心，选择 **">配置文件">并** 输入名称;例如 **，DFCI 配置策略。**
3. 选择 **Windows 10 和更高版本以** 获取平台类型。
4. 在配置文件类型下拉列表中， **选择"设备固件配置** 接口"以打开包含所有可用策略设置的 DFCI 蓝色。 有关 DFCI 设置的信息，请参阅此页面中的"表格 1"或 ["Intune"文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。 您可以在初始设置过程中或编辑 DFCI 配置文件，在初始设置过程中或更高版本中配置 DFCI 设置。

    ![创建 DFCI 配置文件](images/df1.png)

5. 单击" **确定** "，然后选择" **创建**"。
6. 选择 **"选择组"，** 在 **"选择组"** 下加入包含目标设备的 Azure AD 安全组，如下图所示。 单击 **“保存”**。

    ![分配安全组](images/df2a.png)

## 创建 Autopilot 配置文件

1. 在支持"配置文件devicemanagement.microsoft.com的 **终结点管理 >器，然后** 滚动到 **部署配置文件**。
2. 选择 **"创建配置** 文件"并输入名称;例如"我的 **自动化配置文件"，** 然后选择"下一 **步**"。
3. 选择以下设置：

    - 部署模式：**用户驱动。**
    - 加入类型：Azure **AD 加入**。

4. 使其余的默认设置保持不变，然后选择 **"下**一步"，如下图所示。

    ![创建 Autopilot 配置文件](images/df3b.png)

5. 在"作业"页面上，选择 **"选择要包括的组"，** 并单击 Azure AD 安全组。 选择**下一步** 。
6. 接受摘要，然后选择" **创建**"。 现已创建 Autopilot 配置文件并将其分配给组。

## "配置注册状态"页面

若要确保设备在用户登录之前在 OOBE 期间应用 DFCI 配置，您需要配置注册状态。

有关详细信息，请参 [考"设置合约状态"页面](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。


## 在 Surface 设备上配置 DFCI 设置

DFCI 包含一组简化的 UEFI 配置策略，它们通过在硬件级别锁定设备来提供额外级别的安全性。 DFCI 设计为与软件级别的移动设备管理设置配合使用。 请注意，DFCI 设置仅影响内置于 Surface 设备的硬件组件，并且不超过连接外围设备，例如 USB 摄像头。  (，您可以在 Intune 中使用设备限制策略关闭对软件级别设置的附加外围设备) 。

通过从终结点管理器编辑 DFCI 配置文件来配置 DFCI 策略设置，如下图所示。 

- 在支持的终结devicemanagement.microsoft.com"终 **结点管理器">，> >"配置文件>"DFCI 配置文件名称"> >设置**。

    ![配置 DFCI 设置](images/dfciconfig.png)

### 阻止用户访问 UEFI 设置

对于许多客户而，阻止用户更改 UEFI 设置这一功能是非常重要的，这是使用 DFCI 的主要理由。 如表 1 所示，通过设置"允许本地用户更改 **UEFI 设置"来进行管理**。 如果不编辑或配置此设置，本地用户将不能更改 Intune 未管理的任何 UEFI 设置。 因此，强烈建议禁用"允许本地用户更改 **UEFI 设置"。**
使用 DFCI 设置，你可以关闭用户对其可用的功能。 例如，如果需要在高度安全区域保护敏感信息，可禁用相机，如果不希望用户在 USB 驱动器的脚本中进行登录，也可以禁用该文件。

### 表 1.  DFCI 方案

| 设备管理目标                        | 配置步骤                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 阻止本地用户更改 UEFI 设置 | 在 **"安全性>允许本地用户更改 UEFI 设置，** 选择 **"无**"。              |
| 禁用相机                               | 在 **"硬件内置>内置"下，** 选择" **已禁用**"。                                       |
| 禁用麦克风和扬声器              | 在 **"麦克风和扬>器"** 下，选择"已 **禁用**"。                      |
| 禁用使用 WLAN 网络 (Bluetooth的无线)              | 在 **硬件（> 无波版和 Wi-) Fi (Bluetooth 等 **）下，选择" **已禁用**"。                   |
| 从 USB、 S) D 函数通过外部 (开    | 在 **"内置硬件>支持"自动 > UOot（来自 USB (SD）的) **按" **已禁用**"。 |

> [!CAUTION]
> " **禁用 wi- (Bluetooth，"Wi-Fi) " ** 设置只能在具有有线以太网连接的设备上使用。
 
> [!NOTE]
>  Intune 中的 DFCI 包含两个当前不适用于 Surface 设备的设置： (1) CPU 和 IO 虚拟化， (2) 禁用来自网络适配器的 Boot。
 
Intune 提供代理管理权限和适用性规则来管理设备类型的范围标记。 有关所有 DFCI 设置的策略管理支持和完整详细信息，请参阅 [Microsoft Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。

## 在 Autopilot 中注册设备

如上所述，DFCI 只能应用于经销商或分销商在 Windows Autopilot 中注册的设备，且仅在 Surface Pro 7、Surface Pro X 和 Surface 笔记本电脑 3 上受支持。 出于安全原因，不能将设备"自行设置"设备"连接到 Autopilot。

## 手动同步自动设备

尽管 Intune 策略设置通常几乎立即应用，但是设置可能在目标设备上生效之前 10 分钟。 在少数情况下，最多可以延迟 8 小时。 要确保尽快应用设置（ (在测试方案) ），可以手动同步目标设备。

- 在支持的 devicemanagement.microsoft.com 端点管理器中，转到 **Windows > > 注册窗口 Windows >注册** 的设备，然后选择" **同步**"。

 有关详细信息，请参阅 [手动同步 Windows 设备](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。

> [!NOTE]
> 当直接在 UEFI 中调整设置时，你需要确保设备完全重启到标准 Windows 登录。

## 验证 DFCI 托管设备上的 UEFI 设置

在测试环境中，你可以在 Surface UEFI 接口中验证设置。

1. 打开 Surface UEFI，它同时涉及同时按 **高源 +** 和 **电** 源按钮。
2. 选择 **"设备**"。 UEFI 菜单将反映已配置设置，如下图所示。

    ![Surface UEFI](images/df3.png)

    请注意方法：

      - 设置显示为"允许本地用户更改 **UEFI"** 设置是"无"。
      - 音频设置为"已关闭 **"，因为"麦克风和扬声** 器"已设置为 **"已禁用**"。

## 删除 DFCI 策略设置

创建 DFCI 配置文件时，所有已配置设置会在配置文件管理范围内的所有设备保持有效。 只能通过直接编辑 DFCI 配置文件来删除 DFCI 策略设置。

如果原始 DFCI 配置文件已被删除，可以通过创建新的配置文件，然后对其进行编辑设置来删除策略设置。

## 删除 DFCI 管理

**若要删除 DFCI 管理并将设备恢复为出版新状态，请执行以下操作：**

1. 停用 Intune 上的设备：
    1. 在管理"终结点devicemanagement.microsoft.com中，选择 **">"组**"。 选择要停用的设备，然后选择" **停用/擦除"。** 若要了解详细信息， [请参阅"删除设备"中的操作、停用设备或手动取消注册该设备](https://docs.microsoft.com/intune/remote-actions/devices-wipe)。 
2. 从 Intune 中删除 Autopilot 注册：
    1.  选择**设备注册窗口> >设备。**
    2. 在 Windows Autopilot 设备上，选择要删除的设备，然后选择" **删除**"。
3. 使用 Surface 品牌广告适配器将设备连接到有线 Internet。 重启设备并打开 UEFI 菜单 (然后按住音量按钮，同时按下和重新放) 。
4. 从 **网络>"> 中选择"配置管理器，** 然后选择 **"选择退出"。**

若要使用 Intune 管理设备，但不使用 DFCI 管理，将设备注册为 Autopilot，并将其注册到 Intune。 DFCI 将不适用于自行注册的设备。

## 了解详细信息
- [Ignite 2019：从 Intune 通知远程管理 Surface UEFI 设置](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot 和 Surface 设备](windows-autopilot-and-surface-devices.md) 
- [在 Microsoft Intune 的 Windows 设备上使用 DFCI 配置文件](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

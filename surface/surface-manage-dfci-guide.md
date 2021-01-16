---
title: Surface UEFI 设置的 Intune 管理
description: 本文介绍了如何在 Microsoft Intune 中配置 DFCI 环境并管理目标 Surface 设备的固件设置。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
ms.openlocfilehash: dde34126c726ec0ac8093a665804c4fb0f639e3e
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271566"
---
# Surface UEFI 设置的 Intune 管理

## 简介

从云管理设备的能力极大地简化了整个生命周期中的 IT 部署和预配。 借助内置于 [Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows) (DFCI) DFCI 配置文件，Surface UEFI 管理将新式管理堆栈向下扩展到 UEFI 硬件级别。 DFCI 支持零接触预配、消除 BIOS 密码、控制安全设置（包括启动选项和内置外设）并在将来为高级安全方案打下基础。 有关常见问题的解答，请参阅 [Ignite 2019：宣布从 Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)远程管理 Surface UEFI 设置。

### Background

与运行 Windows 10 的任何计算机一样，Surface 设备依赖于 SoC 中存储的代码，该代码使 CPU 能够与硬盘驱动器、显示设备、USB 端口和其他设备交互。 此只读内存中存储的程序 (ROM) 称为固件 (而存储在动态媒体中的程序称为软件) 。

与当今市场中提供的其他 Windows 10 设备不同，Surface 为 IT 管理员提供了通过一组丰富的 UEFI 配置设置配置和管理固件的能力。 这将在基于软件的策略管理的基础上提供硬件控制层，通过移动设备管理、MDM (策略、Configuration Manager 或组) 实现。 例如，在具有敏感信息的高度安全区域部署设备的组织可以通过删除硬件级别的功能来阻止使用相机。 从设备的角度来看，通过固件设置关闭相机等效于以物理方式删除相机。 将固件级别管理的新增安全性与仅依赖操作系统软件设置进行比较。 例如，如果在域环境中通过策略设置禁用 Windows 音频服务，本地管理员仍可重新启用该服务。

### DFCI 与 SEMM

以前，管理需要将设备注册到 Surface Enterprise Management Mode (SEMM) 与正在进行的手动 IT 密集型任务的开销有关。 例如，SEMM 要求 IT 人员在物理上访问每台电脑，以在证书管理过程中输入两位数的引脚。 虽然 SEMM 对于严格位于本地环境中的组织仍然是一个很好的解决方案，但它的复杂性和 IT 密集型要求使使用成本高。

 借助 Microsoft Intune 中的集成 UEFI 固件管理功能，锁定硬件的功能已简化，并且更易于与预配、安全性和简化更新的新功能一同使用，现在统一为[Microsoft Endpoint Manager。](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 下图显示了直接在设备左侧 (查看的 UEFI 设置) 在终结点管理器控制台中 (右) 。

![设备左侧和 (控制台) 的 UEFI 设置 (右) ](images/uefidfci.png)

重要的是，DFCI 支持零接触管理，无需 IT 管理员进行手动交互。 DFCI 使用 Intune 中的设备配置文件功能通过 Windows Autopilot 部署。 设备配置文件允许你添加和配置设置，这些设置随后可部署到在组织管理中注册的设备。 设备收到设备配置文件后，将自动应用功能和设置。 常见设备配置文件的示例包括电子邮件、设备限制、VPN、WLAN 和管理模板。 DFCI 只是一个额外的设备配置文件，使你能够管理云中的 UEFI 配置设置，而无需维护本地基础结构。  

## 支持的设备

以下设备支持 DFCI：

- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go

> [!NOTE]
> Surface Pro X 不支持内置相机、音频和 WI-Fi/Bluetooth。

## 必备条件

- 设备必须由 Microsoft 云解决方案提供商或 OEM ([云](https://partner.microsoft.com/membership/cloud-solution-provider) 解决方案提供商) Windows Autopilot 注册。

- 为 Surface 配置 DFCI 之前，你应该熟悉  [Microsoft Intune](https://docs.microsoft.com/intune/) 和 Azure [Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD) 。

## 开始之前

将目标 Surface 设备添加到 Azure AD 安全组。 有关创建和管理安全组的信息，请参阅 [Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。

## 为 Surface 设备配置 DFCI 管理

DFCI 环境需要设置包含设置的 DFCI 配置文件和 Autopilot 配置文件，以将设置应用于注册的设备。 还建议注册状态配置文件，以确保在用户首次启动设备时在 OOBE 安装期间将设置向下推送。 本指南介绍如何配置 DFCI 环境和管理目标 Surface 设备的 UEFI 配置设置。

## 创建 DFCI 配置文件

在配置 DFCI 策略设置之前，首先创建一个 DFCI 配置文件并将其分配给包含目标设备的 Azure AD 安全组。

1. 在租户中登录devicemanagement.microsoft.com。
2. 在 Microsoft Endpoint Manager 管理中心中，> **配置文件>设备** 并输入名称;例如 **，DFCI 配置策略。**
3. 为 **平台类型选择 Windows 10** 和更高版本。
4. 在"配置文件类型"下拉列表中，选择 **"设备固件配置接口** "以打开包含所有可用策略设置的 DFCI 边栏选项卡。 有关 DFCI 设置的信息，请参阅此页上的表 1 或 [Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。 可以在初始设置过程中或稍后通过编辑 DFCI 配置文件来配置 DFCI 设置。

    ![创建 DFCI 配置文件](images/df1.png)

5. 单击 **"** 确定"，然后选择"**创建"。**
6. 选择**分配****，在**"选择要包括的组"下选择包含目标设备的 Azure AD 安全组，如下图所示。 单击 **“保存”**。

    ![分配安全组](images/df2a.png)

## 创建 Autopilot 配置文件

1. 在终结点管理器devicemanagement.microsoft.com，> **Windows** 注册的设备，然后向下滚动到 **部署配置文件**。
2. 选择 **"创建配置文件**"并输入名称;例如，**我的 Autopilot 配置文件**，然后选择"**下一步"。**
3. 选择以下设置：

    - 部署模式： **用户驱动**。
    - 加入类型：已加入 Azure **AD。**

4. 保留其余默认设置不变，然后选择" **下**一步"，如下图所示。

    ![创建 Autopilot 配置文件](images/df3b.png)

5. 在"分配"页上， **选择"选择要包含** 的组"，然后单击 Azure AD 安全组。 选择**下一步** 。
6. 接受摘要，然后选择"创建 **"。** Autopilot 配置文件现已创建并分配给组。

## 配置注册状态页

若要确保设备在用户登录之前在 OOBE 期间应用 DFCI 配置，需要配置注册状态。

有关详细信息，请参阅" [设置注册状态"页](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。


## 在 Surface 设备上配置 DFCI 设置

DFCI 包括一组简化的 UEFI 配置策略，这些策略通过锁定硬件级别的设备来提供额外的安全级别。 DFCI 设计为与软件级别的移动设备管理设置结合使用。 请注意，DFCI 设置仅影响内置于 Surface 设备的硬件组件，不会扩展到连接的外围设备（如 USB 摄像头）。  (但是，可以使用 Intune 中的设备限制策略在软件级别关闭对已连接的外围设备) 。

通过从终结点管理器编辑 DFCI 配置文件来配置 DFCI 策略设置，如下图所示。 

- 在终结点管理器devicemanagement.microsoft.com，> **Windows > 配置文件中的>"DFCI 配置文件名称">属性>设置**。

    ![配置 DFCI 设置](images/dfciconfig.png)

### 阻止用户访问 UEFI 设置

对于许多客户来说，阻止用户更改 UEFI 设置的能力至关重要，也是使用 DFCI 的主要原因。 如表 1 所示，这是通过设置"允许本地用户更改 **UEFI 设置"进行管理的**。 如果未编辑或配置此设置，本地用户将能够更改任何未由 Intune 管理的 UEFI 设置。 因此，强烈建议禁用"允许本地用户 **更改 UEFI 设置"。**
其余 DFCI 设置使你可以关闭原本可供用户使用的功能。 例如，如果需要保护高度安全的区域中的敏感信息，可以禁用相机，如果不希望用户从 USB 驱动器启动，也可以禁用此功能。

### 表 1.  DFCI 方案

| 设备管理目标                        | 配置步骤                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 阻止本地用户更改 UEFI 设置 | 在 **"安全功能>允许本地用户更改 UEFI 设置"** 下，选择"**无"。**              |
| 禁用相机                               | 在 **"内置硬件>相机"下**，选择"**已禁用"。**                                       |
| 禁用麦克风和扬声器              | 在 **"内置硬件>麦克风和扬声器"下**，选择 **"已禁用"。**                      |
| 禁用无线 (Bluetooth、WLAN 和)              | Under **Built in Hardware > Radios (Bluetooth， Wi-Fi， etc...) ， **select **Disabled**.                   |
| 禁用从外部媒体启动 (USB、SD)     | Under **Built in Hardware > Boot Options > Boot from external media (USB， SD) ， **select **Disabled.** |

> [!CAUTION]
> **"禁用 (Bluetooth WI-Fi) **设置应仅在具有有线以太网连接的设备上使用。
 
> [!NOTE]
>  Intune 中的 DFCI 包括两个当前不适用于 Surface 设备的设置： (1) CPU 和 IO 虚拟化以及 (2) 从网络适配器禁用启动。
 
Intune 提供范围标记以委派管理权限和适用性规则来管理设备类型。 有关策略管理支持和有关所有 DFCI 设置的完整详细信息的详细信息，请参阅 [Microsoft Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。

## 在 Autopilot 中注册设备

如上所述，DFCI 只能应用于由经销商或分销商在 Windows Autopilot 中注册的设备，并且仅在 Surface Pro 7+、Surface Laptop Go、Surface Pro 7、Surface Pro X 和 Surface Laptop 3 上受支持。 出于安全考虑，无法将设备"自行预配"到 Autopilot 中。 若要了解更多信息，请参阅 Windows [Autopilot](surface-autopilot-registration-support.md)的 Surface 注册支持。 

## 手动同步 Autopilot 设备

尽管通常几乎会立即应用 Intune 策略设置，但设置在目标设备上生效之前可能有 10 分钟的延迟。 在极少数情况下，最多延迟 8 小时。 若要确保设置尽快应用， (如在测试方案中) ，可以手动同步目标设备。

- 在终结点管理器devicemanagement.microsoft.com，转到 Windows **Autopilot** > Windows 注册>设备注册>，然后选择"**同步"。**

 有关详细信息，请参阅手动同步 [Windows 设备](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。

> [!NOTE]
> 直接在 UEFI 中调整设置时，需要确保设备完全重启到标准 Windows 登录。

## 验证 DFCI 托管的设备的 UEFI 设置

在测试环境中，你可以验证 Surface UEFI 接口中的设置。

1. 打开 Surface UEFI，这涉及同时按音量 **+** 和 **电源** 按钮。
2. 选择 **设备**。 UEFI 菜单将反映配置的设置，如下图所示。

    ![Surface UEFI](images/df3.png)

    请注意如何：

      - 由于"允许本地用户更改 **UEFI"** 设置设置为"无"，因此设置灰化。
      - 音频设置为关闭， **因为麦克风和扬声器** 设置为 **禁用**。

## 删除 DFCI 策略设置

创建 DFCI 配置文件时，所有配置的设置将在配置文件的管理作用域内的所有设备中保持有效。 你仅可以通过直接编辑 DFCI 配置文件来删除 DFCI 策略设置。

如果原始 DFCI 配置文件已删除，则可以通过创建新配置文件，然后编辑相应设置来删除策略设置。

## 删除 DFCI 管理

**若要删除 DFCI 管理，将设备返回到出厂新状态：**

1. 从 Intune 停用设备：
    1. 在终结点管理器devicemanagement.microsoft.com，选择> **所有设备的组**。 选择要停用的设备，然后选择"停用 **/擦除"。** 若要了解详情，请参阅使用擦除、停用或手动注销设备来 [删除设备](https://docs.microsoft.com/intune/remote-actions/devices-wipe)。 
2. 从 Intune 中删除 Autopilot 注册：
    1.  Choose **Device enrollment > Windows enrollment > Devices.**
    2. 在 Windows Autopilot 设备下，选择要删除的设备，然后选择"删除 **"。**
3. 使用 Surface 品牌以太网适配器将设备连接到有线 Internet。 重新启动设备并打开 UEFI 菜单 (长按调高按钮，同时按下并释放电源按钮) 。
4. Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**

若要使用 Intune 继续管理设备，但不进行 DFCI 管理，请自行将设备注册到 Autopilot，然后注册到 Intune。 DFCI 不会应用于自注册设备。

## 了解详细信息
- [Ignite 2019：宣布从 Intune 远程管理 Surface UEFI 设置](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot 和 Surface 设备](windows-autopilot-and-surface-devices.md) 
- [在 Microsoft Intune 中的 Windows 设备上使用 DFCI 配置文件](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

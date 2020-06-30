---
title: Surface UEFI 设置的 Intune 管理
description: 本文介绍如何在 Microsoft Intune 中配置 DFCI 环境和管理目标 Surface 设备的固件设置。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 11/13/2019
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 0aa69bb229f0d76972620bc58f236e43e03075b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831008"
---
# Surface UEFI 设置的 Intune 管理

## 简介

从云管理设备的能力大大简化了 IT 部署和在生命周期中的预配。 使用内置于 Microsoft Intune 的设备固件配置接口（DFCI）配置文件（现在在[公共预览版](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)中可用），Surface UEFI 管理将新式管理堆栈扩展到 UEFI 硬件级别。 DFCI 支持零接触预配，消除了 BIOS 密码，提供了安全设置（包括启动选项和内置外围设备）的控制权，并为将来的高级安全方案奠定了基础。 有关常见问题的解答，请参阅[Ignite 2019：宣布从 Intune 进行 SURFACE UEFI 设置的远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。

### Background

与运行 Windows 10 的任何计算机一样，Surface 设备依赖于 SoC 中存储的代码，使 CPU 能够与硬盘驱动器、显示器设备、USB 端口和其他设备进行接口。 存储在此只读内存（ROM）中的程序称为固件（虽然存储在动态媒体中的程序称为软件）。

与目前市场上提供的其他 Windows 10 设备相比，Surface 为 IT 管理员提供通过一组丰富的 UEFI 配置设置配置和管理固件的能力。 这在基于软件的策略管理（通过移动设备管理（MDM）策略、配置管理器或组策略实现）的基础上提供了一层硬件控制。 例如，在具有敏感信息的高度安全的区域中部署设备的组织可通过在硬件级别删除功能来阻止相机使用。 从设备角度看，通过固件设置关闭摄像头相当于实际删除摄像头。 比较在固件级别管理的增加的安全性，仅依赖于操作系统软件设置。 例如，如果通过域环境中的策略设置禁用 Windows 音频服务，本地管理员仍然可以重新启用该服务。

### DFCI 与 SEMM

到目前为止，管理固件需要将设备注册到 Surface Enterprise 管理模式（SEMM），并具有持续手动 IT 密集型任务的开销。 例如，SEMM 要求 IT 员工以物理方式访问每台电脑以在证书管理过程中输入两位数的 pin 码。 尽管 SEMM 在严格的本地环境中为组织提供了良好的解决方案，但其复杂性和 IT 密集型要求使其使用成本很高。

现在，使用 Microsoft Intune 中的新集成的 UEFI 固件管理功能，锁定硬件的功能在单个控制台中预配、安全和优化更新的新功能更易于使用，现在统一为[Microsoft 终结点管理器](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)。 下图显示了在设备上直接查看的 UEFI 设置（左图），并在终结点管理器控制台中查看（右）。

![在设备（左侧）和终结点管理器控制台（右）中显示的 UEFI 设置](images/uefidfci.png)

Crucially，DFCI 支持零接触管理，消除 IT 管理员对手动交互的需要。 DFCI 通过 Windows Autopilot 使用 Intune 中的设备配置文件功能进行部署。 设备配置文件允许你添加和配置设置，然后可将这些设置部署到在你的组织中注册管理的设备。 设备收到设备配置文件后，将自动应用功能和设置。 常见设备配置文件的示例包括电子邮件、设备限制、VPN、Wi-fi 和管理模板。 DFCI 只是一个附加的设备配置文件，使你能够从云管理 UEFI 配置设置，而无需维护本地基础结构。  

## 支持的设备

目前，DFCI 在以下设备中受支持：

- Surface Pro 7
- Surface Pro X
- Surface 笔记本电脑3

> [!NOTE]
> Surface Pro X 不支持内置摄像头、音频和 Wi-fi/蓝牙的 DFCI 设置管理。

## 必备条件

- 设备必须由[Microsoft 云解决方案提供商（CSP）合作伙伴](https://partner.microsoft.com/membership/cloud-solution-provider)或 OEM 分发服务器通过 Windows Autopilot 注册。

- 在为 Surface 配置 DFCI 之前，你应该熟悉[Microsoft Intune](https://docs.microsoft.com/intune/)和[azure Active DIRECTORY](https://docs.microsoft.com/azure/active-directory/) （azure AD）中的 Autopilot 配置要求。

## 开始之前

将目标 Surface 设备添加到 Azure AD 安全组。 有关创建和管理安全组的详细信息，请参阅[Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。

## 为 Surface 设备配置 DFCI 管理

DFCI 环境需要设置包含设置和 Autopilot 配置文件的 DFCI 配置文件，以便将设置应用于已注册的设备。 还建议使用注册状态配置文件，以确保在用户第一次启动设备时，在 OOBE 设置期间将设置推送到运行状态。 本指南介绍如何配置 DFCI 环境和管理目标 Surface 设备的 UEFI 配置设置。

## 创建 DFCI 配置文件

在配置 DFCI 策略设置之前，请先创建一个 DFCI 配置文件，然后将其分配给包含你的目标设备的 Azure AD 安全组。

1. 在 devicemanagement.microsoft.com 登录到你的租户。
2. 在 Microsoft 终结点管理器管理中心，选择 "**设备" > 配置文件 > "创建配置文件**"，然后输入名称;例如， **DFCI 配置策略。**
3. 为 "平台类型" 选择**Windows 10 和更高版本**。
4. 在 "配置文件类型" 下拉列表中，选择 "**设备固件配置" 界面**以打开包含所有可用策略设置的 DFCI 刀片。 有关 DFCI 设置的信息，请参阅此页面上的表1或[Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。 你可以在初始设置过程中或在稍后通过编辑 DFCI 配置文件来配置 DFCI 设置。

    ![创建 DFCI 配置文件](images/df1.png)

5. 单击 **"确定"** ，然后选择 "**创建**"。
6. 选择 "**作业**"，然后在 "**选择要包括的组**" 下，选择包含目标设备的 Azure AD 安全组，如下图所示。 单击 **“保存”**。

    ![分配安全组](images/df2a.png)

## 创建 Autopilot 配置文件

1. 在 devicemanagement.microsoft.com 的终结点管理器中，选择 "**设备" > Windows 注册**并向下滚动到 "**部署配置文件**"。
2. 选择 "**创建配置文件**"，然后输入名称;例如， **"我的 Autopilot" 配置文件**，然后选择 "**下一步**"。
3. 选择以下设置：

    - 部署模式：**用户驱动**的。
    - 加入类型： Azure **AD 已加入**。

4. 保留其余默认设置不变，然后选择 "**下一步**"，如下图所示。

    ![创建 Autopilot 配置文件](images/df3b.png)

5. 在 "作业" 页面上，选择 "**选择要包含的组**"，然后单击您的 Azure AD 安全组。 选择**下一步** 。
6. 接受摘要，然后选择 "**创建**"。 此时将创建 Autopilot 配置文件，并将其分配给该组。

## "配置注册状态" 页面

若要确保设备在用户登录之前在 OOBE 期间应用 DFCI 配置，你需要配置注册状态。

有关详细信息，请参阅[设置注册状态页面](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。


## 在 Surface 设备上配置 DFCI 设置

DFCI 包括一组简化的 UEFI 配置策略，可通过在硬件级别锁定设备来提供额外的安全级别。 DFCI 设计为与软件级别的移动设备管理设置结合使用。 请注意，DFCI 设置仅影响内置于 Surface 设备中的硬件组件，并且不会扩展到连接的外围设备（如 USB 网络摄像头）。 （但是，你可以使用 Intune 中的设备限制策略关闭对连接到软件级别的外围设备的访问。

通过从终结点管理器编辑 DFCI 配置文件来配置 DFCI 策略设置，如下图所示。 

- 在 devicemanagement.microsoft.com 的终结点管理器中，选择 **"设备" > Windows > 配置文件 > "DFCI 配置文件名称" > 属性 > 设置**。

    ![配置 DFCI 设置](images/dfciconfig.png)

### 阻止用户访问 UEFI 设置

对于许多客户，阻止用户更改 UEFI 设置的功能至关重要，并且是使用 DFCI 的主要原因。 如表1所示，通过设置进行管理，**允许本地用户更改 UEFI 设置**。 如果不编辑或配置此设置，本地用户将能够更改不由 Intune 管理的任何 UEFI 设置。 因此，强烈建议禁用 "**允许本地用户更改 UEFI 设置"。**
其余的 DFCI 设置使你能够关闭其他用户可以使用的功能。 例如，如果您需要保护高度安全的区域中的敏感信息，则可以禁用摄像头，如果不希望用户从 USB 驱动器启动，也可以将其禁用。

### 表 1.  DFCI 方案

| 设备管理目标                        | 配置步骤                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 阻止本地用户更改 UEFI 设置 | 在 "**安全功能" 下 > 允许本地用户更改 UEFI 设置**"下，选择"**无**"。              |
| 禁用相机                               | 在 "**内置硬件 > 照相机**" 下，选择 "**已禁用**"。                                       |
| 禁用麦克风和扬声器              | 在 "**内置硬件 > 麦克风和扬声器**" 下，选择 "**已禁用**"。                      |
| 禁用无线电收发器（蓝牙、Wi-fi）             | 在 "**内置硬件 > 无线收发器（蓝牙、wi-fi 等）**" 下，选择 "**已禁用**"。                   |
| 禁止从外部媒体（USB、SD）启动    | 在 "**内置硬件 > 启动选项" 下 > 从外部媒体（USB、SD）启动**"，选择"**已禁用**"。 |

> [!CAUTION]
> 仅应在具有有线以太网连接的设备上使用 "**禁用无线收发器（蓝牙、wi-fi）** " 设置。
 
> [!NOTE]
>  Intune 中的 DFCI 包括两个目前不适用于 Surface 设备的设置：（1） CPU 和 IO 虚拟化，（2）禁用从网络适配器启动。
 
Intune 提供用于委派管理权限和适用规则以管理设备类型的作用域标记。 有关策略管理支持的详细信息以及所有 DFCI 设置的完整详细信息，请参阅[Microsoft Intune 文档](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。

## 在 Autopilot 中注册设备

如上所述，DFCI 只能应用于经销商或分销商在 Windows Autopilot 中注册的设备，此时仅支持 Surface Pro 7、Surface Pro X 和 Surface 笔记本电脑3。 出于安全考虑，不能将设备 "自设置" 到 Autopilot。

## 手动同步 Autopilot 设备

尽管 Intune 策略设置通常几乎会立即应用，但可能会有10分钟的延迟，然后设置才会在目标设备上生效。 在极少数情况下，可能需要最多8小时的延迟。 若要确保尽快应用 "设置" （例如在测试方案中），可以手动同步目标设备。

- 在 devicemanagement.microsoft.com 的终结点管理器中，转到 "设备" **> 设备注册 > windows 注册 > Windows Autopilot 设备**，然后选择 "**同步**"。

 有关详细信息，请参阅[手动同步你的 Windows 设备](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。

> [!NOTE]
> 当直接在 UEFI 中调整设置时，你需要确保设备完全重启到标准 Windows 登录。

## 在 DFCI 托管设备上验证 UEFI 设置

在测试环境中，可以验证 Surface UEFI 界面中的设置。

1. 打开 Surface UEFI，其中包括同时按下 "**音量 +** " 和 "**电源**" 按钮。
2. 选择 "**设备**"。 UEFI 菜单将反映已配置的设置，如下图所示。

    ![Surface UEFI](images/df3.png)

    注意操作方法：

      - 设置将灰显，因为 "**允许本地用户更改 UEFI" 设置**将设置为 "无"。
      - 将音频设置为 "关闭" **，因为麦克风和扬声器**设置为 "**已禁用**"。

## 删除 DFCI 策略设置

创建 DFCI 配置文件时，所有配置的设置将在配置文件的管理范围内的所有设备上保持有效。 仅可通过直接编辑 DFCI 配置文件来删除 DFCI 策略设置。

如果已删除原始 DFCI 配置文件，则可以通过创建新的配置文件，然后根据需要编辑设置来删除策略设置。

## 删除 DFCI 管理

**要删除 DFCI 管理并将设备返回到出厂新状态，请执行以下操作：**

1. 从 Intune 中停用设备：
    1. 在 devicemanagement.microsoft.com 的终结点管理器中，选择 "**组 > 所有设备**"。 选择要停用的设备，然后选择 "**停用/擦除"。** 若要了解详细信息，请参阅[使用擦除、停用或手动通过设备删除设备](https://docs.microsoft.com/intune/remote-actions/devices-wipe)。 
2. 从 Intune 中删除 Autopilot 注册：
    1.  选择 "**设备注册" > Windows 注册 > 设备**"。
    2. 在 "Windows Autopilot 设备" 下，选择要删除的设备，然后选择 "**删除**"。
3. 将设备连接到带 Surface 品牌以太网适配器的有线互联网。 重启设备并打开 UEFI 菜单（按住音量键，同时按下并释放电源按钮）。
4. 选择 "**管理 > 配置" 从网络 > 刷新**"，然后选择"**退出 "。**

若要继续通过 Intune 管理设备，但没有 DFCI 管理，请自行注册设备以 Autopilot 并将其注册到 Intune。 DFCI 将不会应用于自注册设备。

## 了解详细信息
- [Ignite 2019：宣布从 Intune 进行 SURFACE UEFI 设置的远程管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot 和 Surface 设备](windows-autopilot-and-surface-devices.md) 
- [在 Microsoft Intune 中的 Windows 设备上使用 DFCI 配置文件](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

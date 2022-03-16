---
title: 在 Surface 设备上管理 DFCI
description: 本文介绍如何在设备上配置 DFCI Microsoft Intune并管理目标 Surface 设备的固件设置。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/01/2021
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: c4a39c094c0621ed491ab04148f0c8338771a6a6
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448595"
---
# <a name="manage-dfci-on-surface-devices"></a>在 Surface 设备上管理 DFCI

## <a name="introduction"></a>简介

从云管理设备的能力极大地简化了整个生命周期中的 IT 部署和预配。 借助内置在 Microsoft Intune 中的 (DFCI) 配置文件的设备固件配置接口，Surface UEFI 管理[](/intune/configuration/device-firmware-configuration-interface-windows)将新式管理堆栈向下扩展到 UEFI 硬件级别。 DFCI 支持零接触预配、消除 BIOS 密码、控制安全设置（包括启动选项和内置外设）并在将来为高级安全方案打下基础。 有关常见问题的解答，请参阅 [Ignite 2019：宣布从 Intune 远程管理 Surface UEFI 设置](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。

### <a name="background"></a>Background

与运行 Windows 10 或 Windows 11 的任何计算机一样，Surface 设备依赖于 SoC 中存储的代码，该代码使 CPU 能够与硬盘驱动器、显示设备、USB 端口和其他设备交互。 此只读内存中存储的程序 ROM () 称为固件 (而存储在动态媒体中的程序称为软件) 。

与当今市场中Windows设备不同，Surface 为 IT 管理员提供了通过一组丰富的 UEFI 配置设置配置和管理固件的能力。 这将在基于软件的策略管理的基础上提供一层硬件控制，通过移动设备管理、MDM (策略、配置管理器) 组策略实现。 例如，在具有敏感信息的高度安全区域部署设备的组织可以通过删除硬件级别的功能来阻止使用相机。 从设备的角度来看，通过固件设置关闭相机等效于以物理方式移除相机。 将固件级别的管理新增的安全性与仅依赖操作系统软件设置进行比较。 例如，如果通过域Windows策略设置禁用音频服务，本地管理员仍可以重新启用该服务。

### <a name="dfci-versus-semm"></a>DFCI 与 SEMM

以前，管理固件需要将设备注册到 Surface Enterprise 管理模式 (SEMM) 与正在进行的手动 IT 密集型任务的开销有关。 例如，SEMM 要求 IT 员工以物理方式访问每台电脑，以在证书管理过程中输入一个两位数的引脚。 虽然 SEMM 仍是严格位于本地环境中组织的良好解决方案，但它的复杂性和 IT 密集型要求使使用成本昂贵。

借助 Microsoft Intune 中的集成 UEFI 固件管理功能，锁定硬件的功能已简化，并且更易于与新功能一同使用，从而在单个控制台中预配、安全性和简化更新，现在统一为 [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)。 下图显示了直接在设备上查看的 UEFI 设置 (左侧) 右侧Endpoint Manager控制台 (查看) 。

:::image type="content" alt-text="设备左侧 (和) 控制台Endpoint Manager显示的 UEFI (右) 。" source="images/uefidfci.png" lightbox="images/uefidfci.png":::

重要的是，DFCI 支持零触摸管理，无需 IT 管理员进行手动交互。 使用 Intune 中的设备配置文件Windows Autopilot 部署 DFCI。 设备配置文件允许你添加和配置设置，这些设置随后可部署到在组织中管理中注册的设备。 设备收到设备配置文件后，将自动应用功能和设置。 常见设备配置文件的示例包括电子邮件、设备限制、VPN、WI-Fi 和管理模板。 DFCI 只是一个额外的设备配置文件，使你无需维护本地基础结构即可从云管理 UEFI 配置设置。  

## <a name="supported-devices"></a>支持的设备

以下设备支持 DFCI：

- Surface Laptop 标准版
- Surface Laptop Studio (商业 SKUs) 
- Surface Pro 8 (商业 SKUs) 
- Surface Go 3 (商业 SKUs) 
- Surface Pro 7+ (商业 SKUs) 
- Surface Pro 7 (SKUs) 
- Surface Pro X (所有 SKUs) 
- Surface Laptop 4 (商业 SKUs) 
- Surface Laptop 3 (Intel 处理器) 
- Surface Book 3
- Surface Laptop Go


>[!TIP]
> 商业 SKUS (，Surface 商用版) 运行 Windows 10 专业版/Enterprise 或 Windows 11 专业版/Enterprise;消费者 SUS Windows 10/Windows 11 家庭版。 若要了解详细信息，请参阅 [查看系统信息](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00)。 

> [!NOTE]
> Surface Pro X 不支持内置相机、音频和 WI-Fi/蓝牙 的 DFCI 设置管理。

## <a name="prerequisites"></a>系统必备

- 设备必须由云解决方案提供商Windows或 OEM Microsoft 云解决方案提供商 (向) [Autopilot](https://partner.microsoft.com/membership/cloud-solution-provider) 注册。

- 在配置 Surface 的 DFCI 之前，你应该熟悉 Microsoft Intune 和 Azure Active Directory (Azure AD) 中的 [](/intune/) Autopilot [配置要求](/azure/active-directory/)。

## <a name="before-you-begin"></a>在开始之前

将目标 Surface 设备添加到安全Azure AD组。 有关创建和管理安全组的信息，请参阅 [Intune 文档](/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。

## <a name="configure-dfci-management-for-surface-devices"></a>为 Surface 设备配置 DFCI 管理

DFCI 环境需要设置包含设置的 DFCI 配置文件和 Autopilot 配置文件，以将设置应用到注册的设备。 还建议使用注册状态配置文件，以确保在用户首次启动设备时在 OOBE 设置期间将设置向下推送。 本指南介绍如何配置 DFCI 环境和管理目标 Surface 设备的 UEFI 配置设置。

## <a name="create-dfci-profile"></a>创建 DFCI 配置文件

在配置 DFCI 策略设置之前，首先创建一个 DFCI 配置文件并将其分配给Azure AD设备的安全组。

1. 在租户中登录 devicemanagement.microsoft.com。

2. 在"Microsoft Endpoint Manager中心"中，选择">**** 配置文件">"配置文件"，然后输入名称;例如 **，DFCI 配置策略。**

3. 选择**Windows 10类型选择**"Windows 10及更高版本"。

4. 在配置文件类型下拉列表中，选择 **设备固件配置接口** 以打开包含所有可用策略设置的 DFCI 边栏选项卡。 有关 DFCI 设置的信息，请参阅此页面上的表 1 或 [Intune 文档](/intune/configuration/device-firmware-configuration-interface-windows)。 可以在初始设置过程中或稍后通过编辑 DFCI 配置文件来配置 DFCI 设置。

   :::image type="content" alt-text="创建 DFCI 配置文件。" source="images/df1.png":::

5. 单击 **"确定** "，然后选择" **创建"**。

6. 选择 **"分配**"，在"选择要**包含**Azure AD组"下选择包含目标设备的安全组，如下图所示。 单击 **“保存”**。

   :::image type="content" alt-text="分配安全组。" source="images/df2a.png":::

## <a name="create-autopilot-profile"></a>创建 Autopilot 配置文件

1. In Endpoint Manager at devicemanagement.microsoft.com， select **devices > Windows enrollment** and scroll down to **Deployment profiles**.

2. 选择 **"创建配置文件** "并输入名称;例如，" **我的 Autopilot 配置文件"**，然后选择"下一 **步"**。

3. 选择以下设置：

    - 部署模式： **用户驱动**。
    - 加入类型：已加入 Azure **AD**。

4. 保留其余默认设置不变，然后选择"下一步 **"，如下**图所示。

   :::image type="content" alt-text="创建 Autopilot 配置文件。" source="images/df3b.png" lightbox="images/df3b.png":::

5. 在"分配"页上，**选择"选择要包含的组"**，然后单击Azure AD安全组"。 选择**下一步** 。

6. 接受摘要，然后选择"创建 **"**。 Autopilot 配置文件现已创建并分配给组。

## <a name="configure-enrollment-status-page"></a>配置注册状态页

若要确保设备在用户登录之前在 OOBE 期间应用 DFCI 配置，你需要配置注册状态。

有关详细信息，请参阅设置 [注册状态页面](/intune/enrollment/windows-enrollment-status)。


## <a name="configure-dfci-settings-on-surface-devices"></a>在 Surface 设备上配置 DFCI 设置

DFCI 包括一组简化的 UEFI 配置策略，这些策略通过锁定硬件级别的设备来提供额外的安全级别。 DFCI 旨在与软件级别的移动设备管理设置结合使用。 请注意，DFCI 设置仅影响内置于 Surface 设备的硬件组件，不会扩展到连接的外围设备（如 USB 摄像头）。  (但是，可以使用 Intune 中的设备限制策略在软件级别关闭对已连接的外围设备) 。

通过编辑 DFCI 配置文件从 Endpoint Manager配置 DFCI 策略设置，如下图所示。 

- In Endpoint Manager at devicemanagement.microsoft.com， select **Devices > Windows > Configuration Profiles > "DFCI profile name" > Properties > 设置**.

  :::image type="content" alt-text="配置 DFCI 设置。" source="images/dfciconfig.png" lightbox="images/dfciconfig.png":::

### <a name="block-user-access-to-uefi-settings"></a>阻止用户访问 UEFI 设置

对于许多客户来说，阻止用户更改 UEFI 设置的能力非常重要，也是使用 DFCI 的主要原因。 如表 1 所示，这是通过"允许本地用户更改 **UEFI 设置"设置进行管理的**。 如果未编辑或配置此设置，本地用户将能够更改任何未由 Intune 管理的 UEFI 设置。 因此，强烈建议禁用允许本地 **用户更改 UEFI 设置。**
其余 DFCI 设置让你能够关闭原本可供用户使用的功能。 例如，如果你需要保护高度安全的区域中的敏感信息，可以禁用相机，并且如果你不希望用户从 USB 驱动器启动，也可以禁用此功能。

### <a name="table-1-dfci-scenarios"></a>表 1. DFCI 方案

| 设备管理目标                        | 配置步骤                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 阻止本地用户更改 UEFI 设置 | 在 **"安全功能>允许本地用户更改 UEFI 设置"** 下，选择"无 **"**。              |
| 禁用相机                               | 在 **"内置硬件>相机"下，** 选择" **已禁用"**。                                       |
| 禁用麦克风和扬声器              | 在 **"内置硬件>麦克风和扬声器"下，** 选择" **已禁用"**。                      |
| 禁用无线 (蓝牙、WI-Fi)              | 在 **"内置硬件>无线电 (蓝牙、WI-Fi 等...) **，选择"已**禁用"**。                   |
| 禁用从外部媒体启动 (USB、SD)     | 在 **"内置硬件>启动选项> USB、SD (从外部媒体 **启动) ，选择"已 **禁用"**。 |

> [!CAUTION]
> "**禁用无线 (蓝牙、WI-Fi) **设置应仅在具有有线以太网连接的设备上使用。
 
> [!NOTE]
>  Intune 中的 DFCI 包括两个当前不适用于 Surface 设备的设置： (1) CPU 和 IO 虚拟化以及 (2) 禁用从网络适配器启动。
 
Intune 提供 Scope 标记以委派管理权限和适用性规则来管理设备类型。 有关策略管理支持和有关所有 DFCI 设置的完整详细信息的详细信息，请参阅Microsoft Intune[文档](/intune/configuration/device-firmware-configuration-interface-windows)。

## <a name="register-devices-in-autopilot"></a>在 Autopilot 中注册设备

如上所述，DFCI 只能应用于经销商或分销商在 Windows Autopilot 中注册的设备，并且受 Surface Pro 8、Surface Laptop Studio、Surface Go 3、Surface Pro 7+、Surface Laptop Go、Surface Pro 7 支持，Surface Pro X，Surface Laptop 3。 出于安全考虑，无法将你的设备"自行预配"到 Autopilot 中。 若要了解更多信息，请参阅 Surface [Registration Support for Windows Autopilot](surface-autopilot-registration-support.md)。 

## <a name="manually-sync-autopilot-devices"></a>手动同步 Autopilot 设备

尽管通常几乎会立即应用 Intune 策略设置，但设置在目标设备上生效之前可能有 10 分钟的延迟。 在极少数情况下，最多可能会延迟 8 小时。 若要确保设置尽快应用， (如在测试) ，你可以手动同步目标设备。

- In Endpoint Manager at devicemanagement.microsoft.com， go to **Devices > Device enrollment > Windows Autopilot devices> Windows** and select **Sync**.

 有关详细信息，请参阅手动[同步Windows设备](/intune-user-help/sync-your-device-manually-windows)。

> [!NOTE]
> 当直接在 UEFI 中调整设置时，你需要确保设备完全重启到标准登录Windows登录。

## <a name="verifying-uefi-settings-on-dfci-managed-devices"></a>验证 DFCI 托管的设备的 UEFI 设置

在测试环境中，你可以验证 Surface UEFI 接口中的设置。

1. 打开 Surface UEFI，这涉及同时按下 **音量 +** **和电源** 按钮。

2. 选择 **"设备"**。 UEFI 菜单将反映配置的设置，如下图所示。

   :::image type="content" alt-text="Surface UEFI。" source="images/df3.png":::

   请注意如何：

   - 设置显示为灰色，因为 **"允许本地用户更改 UEFI"设置** 设置为"无"。
   - 音频设置为关闭， **因为麦克风和扬声器** 设置为 **已禁用**。

## <a name="removing-dfci-policy-settings"></a>删除 DFCI 策略设置

创建 DFCI 配置文件时，所有配置的设置将在配置文件的管理作用域内的所有设备中保持有效。 你仅可以通过直接编辑 DFCI 配置文件来删除 DFCI 策略设置。

如果原始 DFCI 配置文件已删除，则可以通过创建新配置文件然后编辑设置（如果适当）来删除策略设置。

## <a name="removing-dfci-management"></a>删除 DFCI 管理

**若要删除 DFCI 管理，将设备返回到出厂新状态：**

1. 从 Intune 停用设备：
    1. In Endpoint Manager at devicemanagement.microsoft.com， choose **Groups > All Devices**. 选择要停用的设备，然后选择" **停用/擦除"。** 若要了解详情，请参阅使用擦除、停用或手动 [注销设备来删除设备](/intune/remote-actions/devices-wipe)。 
2. 从 Intune 中删除 Autopilot 注册：
    1.  选择**设备注册> Windows注册>设备"**。
    2. 在Windows Autopilot 设备"下，选择要删除的设备，然后选择"删除 **"**。
3. 连接 Surface 品牌以太网适配器连接 Internet。 重新启动设备并打开 UEFI 菜单 (长按调高音量按钮，同时按下并释放电源按钮) 。
4. 选择 **"管理>配置>"从网络刷新"** ，然后选择" **选择退出"。**

若要使用 Intune 继续管理设备，但不进行 DFCI 管理，请自行将设备注册到 Autopilot，然后注册到 Intune。 DFCI 不会应用于自行注册的设备。

## <a name="learn-more"></a>了解详细信息
- [Ignite 2019：宣布从 Intune 远程管理 Surface UEFI 设置](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot 和 Surface 设备](windows-autopilot-and-surface-devices.md) 
- [在 Microsoft Intune 的设备Windows DFCI 配置文件](/intune/configuration/device-firmware-configuration-interface-windows)

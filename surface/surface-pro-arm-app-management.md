---
title: 部署、管理和维护 Surface Pro X
description: 本文概述了部署、管理和维护 Surface Pro X 的主要注意事项。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/01/2020
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 758cde12ea79e42630dad55b06eb50d0ab9dda12
ms.sourcegitcommit: f996a95af741e54536b1f3eb94d0f13f681f5d5d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093125"
---
# 部署、管理和维护 Surface Pro X

## 简介

Surface Pro X 专为满足高性能商业要求而构建，集成了在 ARM 设备上发布的功能强大的处理器（即 Microsoft SQ1 ARM 芯片集），实现了新的突破。

Surface Pro X 由 3 GHz CPU 和 2.1 万亿次浮点运算 GPU 提供支持，可提供完整的 Windows 体验。 其具有 13 小时的电池使用时间并内置 4G LTE，非常适合金融、法律和医疗领域的移动一线工作人员和专业人员，或者需要更长的电池使用时间和连续连接能力的任何角色。

Surface Pro X 几乎专为围绕 Microsoft 365、Intune 和 Windows Autopilot 且基于云的现代环境而设计。 本文重点介绍了 Surface Pro X 的外观，并概述了部署、管理和维护 Surface Pro X 的主要注意事项。

## 部署 Surface Pro X

为了获得出色体验，请使用 Windows Autopilot 部署 Surface Pro X，可以依靠 Microsoft 云解决方案提供商的帮助，也可以使用 Autopilot 部署配置文件和相关功能自行设置。 有关详细信息，请参阅：

- [Windows Autopilot 和 Surface 设备](windows-autopilot-and-surface-devices.md)
- [Windows Autopilot 概述](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)

Autopilot 部署具有以下几个优点：为你提供出厂设置好的操作系统，针对零接触部署进行了优化，并预安装 Office 专业增强版。

已经在使用现代管理、安全和工作效率解决方案的组织可充分利用 Surface Pro X 中独特的性能功能。使用现代化业务线应用、Microsoft Store (UWP) 应用或远程桌面解决方案的客户也可从中受益。

## 基于映像的部署注意事项

Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager（以前称为 System Center Configuration Manager）当前不支持 Surface Pro X 的操作系统部署。 依赖基于映像的部署的客户在评估过渡到云的正确时间时，应考虑采用 Surface Pro 7。

## 管理 Surface Pro X 设备

### Intune

作为 Microsoft 企业移动性 + 安全性的一个组成部分，Intune 与 Azure Active Directory 相集成，可实现身份和访问控制，并提供对已注册 Surface Pro X 设备的精细管理。 与旧的本地工具（如 Windows 组策略）相比，Intune 移动设备管理 (MDM) 策略具有许多优点。 其中包括设备登录时间缩短，策略目录更为简化，因此支持在云端进行全面设备管理。 例如，你可以使用 eSIM 配置文件管理 LTE，以配置流量套餐并将激活代码部署到多台设备。<br> 

有关使用 Intune 的详细信息，请参阅 [Intune 文档](https://docs.microsoft.com/intune/)。

### 联合管理

在 Autopilot 中部署 Surface Pro X 设备后，你可以将其加入到 Azure AD 或 Active Directory（混合 Azure AD 联接），通过此服务你将能够使用 Intune 管理设备，或使用 Endpoint Configuration Manager 对设备进行联合管理（将会安装 32 位 x86 ConfigMgr 客户端）。

### 第三方 MDM 解决方案

你可以使用第三方 MDM 工具管理 Surface Pro X 设备。 有关详细信息，请联系 MDM 提供商。

### 防病毒软件

在 Windows 10 设备受支持的生命周期内，Windows Defender 将保护基于 ARM 的电脑上的 Windows 10。 

某些第三方防病毒软件无法安装到采用 ARM 处理器的 Windows 10 电脑。 与第三方防病毒软件提供商的协作仍在继续，以确保 AV 应用在基于 ARM 的电脑上的就绪度。 请联系你的防病毒软件提供商，了解其应用何时可用。

## 维护 Surface Pro X

Surface Pro X 支持 Windows 10 版本 1903 和更高版本。 作为一台基于 ARM 的设备，它对于保持最新的驱动程序和固件有着特定要求。 

Surface Pro X 可使用 Windows 更新来简化将驱动程序和固件保持最新的过程，这对家庭用户和小型企业用户均适用。 使用默认设置接收自动更新。  如需进行验证，请执行以下步骤：

1. 转到**开始** > **设置 > 更新和安全 > Windows 更新** > **高级选项**。
2. 在**选择安装更新的方式**下，选择**自动(建议)**。

### 针对商业客户的建议

- 使用 Windows 更新或适用于企业的 Windows 更新来维护最新的驱动程序和固件。 有关详细信息，请参阅[使用适用于企业的 Windows 更新部署更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)。
- 如果此过程需要使用 Windows Installer .msi 文件，请联系[商用 Surface 支持](https://support.microsoft.com/help/4037645)。 
- 有关部署和管理 Surface 设备更新的更多信息，参见“[管理和部署 Surface 驱动程序和固件更新](manage-surface-driver-and-firmware-updates.md)”。
- 请注意，Windows Server Update Services (WSUS) 不支持向 Surface Pro X 提供驱动程序和固件。

## 在 Surface Pro X 上运行应用

大多数应用在基于 ARM 的 Windows 10 电脑上运行，少数应用除外。

### 支持的应用

- 大多数 x86 Win32 应用都能在 Surface Pro X 上运行。
- 本机 ARM64 和 Microsoft Store UWP 应用充分发挥了基于 ARM 的处理器的本机速度，同时优化了电池使用时间，从而提供了出色的用户体验。
- 使用专为采用 ARM 处理器的 Windows 10 电脑设计的驱动程序的应用。

> [!NOTE]
> 通过 Windows 预览体验计划即将在预览版中提供 64 位仿真功能，你将能够在 Surface Pro X 上运行 64 位 (x64) 应用程序。

有关在 Surface Pro X 上运行应用的详细信息，请参阅：

- [基于 ARM 的 Windows 10 电脑支持常见问题解答](https://support.microsoft.com/help/4521606)
- [基于 ARM 的 Windows 10 文档](https://docs.microsoft.com/windows/arm)

## 虚拟桌面 (VDI)

Windows 虚拟桌面允许从任何位置访问 Windows 桌面、应用程序和任何计算设备或平台上的数据。 如需了解详细信息，请参阅 [Windows 虚拟桌面站点](https://aka.ms/wvd)。 

## 使用 Surface Pro X 浏览

很多热门浏览器在 Surface Pro X 上运行：

- 设备自带的 Edge、Firefox、Chrome 和 Internet Explorer 均可在 Surface Pro X 上运行。
- 设备自带的 Edge 和 Firefox 均在本机运行，因此在采用 ARM 处理器的 Windows 10 电脑上性能有所增强。

## 安装和使用 Microsoft Office

- 在采用 ARM 处理器的 Windows 10 电脑上，使用 Office 365 获得出色体验。
- Office 365“即点即用”安装了 Outlook、Word、Excel 和 PowerPoint，这些程序已进行优化，可在采用 ARM 处理器的 Windows 10 电脑上运行。
- Microsoft Teams 在 Surface Pro X 上的运行效果出色。
- 对于 Office 的“永久版本”（例如 Office 2019），请安装 32 位版本。

## VPN

如需确认特定的第三方 VPN 是否支持采用 ARM 处理器的 Windows 10 电脑，请联系 VPN 提供商。

## 主要功能比较

下表展示了所选关键功能在 Surface Pro X（采用基于 ARM 的 Windows 10 系统）与 Surface Pro 7（采用 Intel 处理器）上的可用性。

| 部署                              | Surface Pro 7 | Surface Pro X | 注释                                                                                                                           |
| --------------------------------------- | ------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                       | 是           | 是           |                                                                                                                                 |
| 支持网络启动 (PXE)          | 是           | 否           |                                                                                                                                 |
| Windows 配置设计器          | 是           | 否            | 不建议用于 Surface Pro X。                                                                                              |
| WinPE                                   | 是           | 是           | 不建议用于 Surface Pro X。Microsoft 不提供 Surface Pro X 支持 WinPE 所需的 .ISO 和驱动程序。 |
| Endpoint Configuration Manager：操作系统部署 (OSD) | 是           | 否            | 在 Surface Pro X 上不支持。                                                                                              |
| MDT                                     | 是           | 否            | 在 Surface Pro X 上不支持。                                                                                              |


| 管理                                    | Surface Pro 7       | Surface Pro X | 注释                                                                                 |
| --------------------------------------------- | ------------------- | ------------- | ------------------------------------------------------------------------------------- |
| Intune                                        | 是                 | 是           | 使用 eSIM 配置文件管理 LTE。                                                        |
| Windows Autopilot                             | 是                 | 是           |                                                                                       |
| Azure AD（联合管理）                      | 是                 | 是           | 将 Surface Pro X 加入到 Azure AD 或 Active Directory（混合 Azure AD 联接）的功能。 |
| Endpoint Configuration Manager                                          | 是               | 是           |                                                                                       |
| 当 AC 恢复时开机                      | 是                 | 是           |                                                                                   |
| 适用于企业的 Surface 诊断工具包 (SDT) | 是                 | 是           |                                                                                   |
| Surface Dock 固件更新                  | 是                 | 否           |                                                                                   |
| 资产标记实用工具                             | 是                 | 是           |                                                                                   |
| Surface 企业管理模式 (SEMM)     | 是 | 部分       | 不支持在固件级别禁用 Surface Pro X 上的硬件。                 |
| Surface UEFI 配置器                     | 是 |   否            | 不支持在固件级别 禁用 Surface Pro X 上的硬件。                |
| Surface UEFI 管理器                          | 是 | 部分       | 不支持在固件级别禁用 Surface Pro X 上的硬件。                 |


| 安全性                          | Surface Pro 7 | Surface Pro X | 注释                                                                                                                                                                                                                                                                                                                                                |
| --------------------------------- | ------------- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BitLocker                         | 是           | 是           |                                                                                                                                                                                                                                                                                                                                                      |
| Windows Defender                  | 是           | 是           |                                                                                                                                                                                                                                                                                                                                                      |
| 支持第三方防病毒程序 | 是           | 查看说明      |某些第三方防病毒软件无法安装到采用 ARM 处理器的 Windows 10 电脑。 与第三方防病毒软件提供商的协作仍在继续，以确保 AV 应用在基于 ARM 的电脑上的就绪度。 请联系你的防病毒软件提供商，了解其应用何时可用。 |
| 条件访问                | 是           | 是           |                                                                                                                                                                                                                                                                                                                                                      |
| 安全启动                       | 是           | 是           |                                                                                                                                                                                                                                                                                                                                                      |
| Windows 信息保护    | 是           | 是           |                                                                                                                                                                                                                                                                                                                                                      |
| Surface Data Eraser (SDE)         | 是           | 是           |                                                                                                                                                                                                                                                                                                                                                     
## 常见问题

### 我能否使用 MDT 或 Endpoint Configuration Manager 部署 Surface Pro X？

Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager 当前不支持 Surface Pro X 的操作系统部署。依赖基于映像的部署的客户在评估过渡到云的正确时间时，应考虑采用 Surface Pro 7。

### 我可以如何部署 Surface Pro X？

使用 Windows Autopilot 部署 Surface Pro X。

### BMR 是否可用？

是。

### 是否必须使用 Intune 来管理 Surface Pro X？

建议使用 Intune，但并非强制要求。 在 Autopilot 中部署 Surface Pro X 设备后，你可以将其加入到 Azure AD 或 Active Directory（混合 Azure AD 联接），通过此服务你将能够使用 Intune 管理设备，或使用 Endpoint Configuration Manager 对设备进行联合管理（将会安装 32 位 x86 ConfigMgr 客户端）。

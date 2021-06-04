---
title: Windows Autopilot 和 Surface 设备
ms.reviewer: ''
manager: laurawi
description: 了解适用于 Surface 设备的 Windows Autopilot 部署选项。
keywords: autopilot， windows 10， 图面， 部署
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 9/14/2020
ms.openlocfilehash: 31f11db8c3ab12d1af754267022d9060d3a8c026
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271098"
---
# Windows Autopilot 和 Surface 设备

Windows Autopilot 是 Windows 10 中的一种基于云的部署技术。 你可以立即使用 Windows Autopilot 在零接触进程中远程部署和配置设备。

从传统来看，IT 专业人员花费大量时间构建和自定义映像，这些映像稍后将部署到已经安装了良好操作系统的设备。 Windows Autopilot 引入了一种新的零接触部署方法，该方法使用一组技术来设置和配置 Windows 设备。 这使 IT 部门能够配置/自定义映像，几乎无需管理基础结构，且过程简单明了。 从用户的角度来看，只需几个简单的步骤，Surface 就进入高效状态。 实际上，最终用户所需的唯一交互是连接到网络并验证其凭据。 之后的所有内容都完全自动化。

Windows Autopilot 允许你：

- 自动将设备加入 Azure Active Directory (Azure AD) 。
- 将设备自动注册到 MDM 服务（如 Microsoft Intune (）需要 Azure AD Premium 订阅) 。
- 限制管理员帐户的创建。 Autopilot 是让第一个登录 Windows 的人以标准用户输入的唯一方法。
- 根据设备配置文件创建设备并将其自动分配给配置组。
- 自定义 OOBE (全新体验) 内容和品牌，以满足组织要求。
- 使用 Intune 启用完整的设备配置。
- 远程重置或重新启动设备。

##  <a name="how-it-works"></a>工作原理

Windows Autopilot 注册的设备在首次启动时通过称为硬件哈希的唯一设备签名通过 Internet *进行标识*。 通过使用现代管理解决方案（如 Azure Active Directory (Azure AD) 移动设备管理）自动注册和配置它们。

你可以从为 Windows Autopilot 启用的 Surface 合作伙伴购买时注册 Surface 设备。 这些合作伙伴可以直接将新设备发货给用户。 设备将在首次打开时自动注册和配置。 此过程在部署过程中消除了重新映像，从而允许你实现新的敏捷的设备管理和分发方法。

##  <a name="modern-management"></a>现代管理

Autopilot 是 Surface 设备（包括 Surface Pro 7+、Surface Laptop 3、Surface Pro 7 和 Surface Pro X）的推荐部署选项，专用于通过 Autopilot 进行部署。

 最好在 Microsoft 云解决方案提供商的帮助下注册 Surface 设备。 此步骤允许你直接从 Intune 管理 Surface 上的 UEFI 固件设置。 它无需以物理方式触摸设备进行证书管理。 有关详细信息 [，请参阅 Surface UEFI 设置的 Intune](surface-manage-dfci-guide.md) 管理。

##  <a name="windows-version-considerations"></a>Windows 版本注意事项

通过 Windows Autopilot 广泛部署 Surface 设备（包括在购买时由 Surface 合作伙伴注册）需要 Windows 10 版本 1709 (Fall Creators Update) 或更高版本。

这些 Windows 版本支持 4，000 字节 (4k) 哈希值，它唯一标识 Windows Autopilot 的设备，这是大规模部署所必需的。 所有新的 Surface 设备（包括 Surface Pro 7+、Surface Pro X 和 Surface Laptop 3）随 Windows 10 版本 1903 或更高版本一起提供。

##  <a name="exchange-experience-on-surface-devices-in-need-of-repair-or-replacement"></a>需要修复或更换的 Surface 设备的 Exchange 体验

Microsoft 会自动检查每个 Surface 的 Autopilot 注册，并取消客户租户中的设备注册。  Microsoft 确保在将替换设备交付回客户后注册到 Windows Autopilot。 此服务可在所有设备直接与 Microsoft 交换服务订单上提供。

> [!NOTE]
> 当客户使用合作伙伴返回设备时，合作伙伴负责管理交换过程，包括注销设备以及将设备注册到 Windows Autopilot。

##  <a name="microsoft-support-registration"></a>Microsoft 支持注册

客户和 Microsoft 云解决方案提供商 (服务提供商) 通过向 Microsoft 支持提交请求来注册 Surface 设备。 若要了解更多信息，请参阅 [Windows Autopilot](surface-autopilot-registration-support.md)的 Surface 注册支持。

##  <a name="surface-partners-enabled-for-windows-autopilot"></a>为 Windows Autopilot 启用的 Surface 合作伙伴

选择 Surface 合作伙伴可在购买时在 Windows Autopilot 中注册 Surface 设备。 他们还可以将已注册的设备直接发货给用户。 可以使用 Windows Autopilot、Azure AD 和移动设备管理，通过零接触过程完全配置设备。

为 Windows Autopilot 启用的 Surface 合作伙伴包括：

| 美国合作伙伴 | 全球合作伙伴 | 美国分销商 |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [Also](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [连接](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [见解](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [一名](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [受保护的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

##  <a name="learn-more"></a>了解详细信息

有关 Windows Autopilot 详细信息，请参阅：
- [Windows Autopilot 概述](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Windows Autopilot 要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [适用于 Windows Autopilot 的 Surface 注册支持](surface-autopilot-registration-support.md)
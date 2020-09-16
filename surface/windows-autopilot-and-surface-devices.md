---
title: Windows Autopilot 和 Surface 设备
ms.reviewer: ''
manager: laurawi
description: 了解有关面向 Surface 设备的 Windows Autopilot 部署选项的信息。
keywords: autopilot、windows 10、surface、部署
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
ms.openlocfilehash: d2a948d236ffa286192937cc5ca71099b6eeeafb
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016421"
---
# Windows Autopilot 和 Surface 设备

Windows Autopilot 是 Windows 10 中基于云的部署技术。 你可以使用 Windows Autopilot 远程部署和配置设备，只需要一个零接触过程即可。

传统上，IT 专业人员花费大量时间构建和自定义映像，这些映像稍后将部署到已安装好良好操作系统的设备。 Windows Autopilot 使用用于设置和配置 Windows 设备的技术集合引入了新的零接触部署方法。 这使 IT 部门能够配置/自定义图像，几乎不需要管理基础结构，而且简单明了。 从用户的角度来看，只需执行几个简单的步骤即可获取生产状态的图面。 实际上，最终用户所需的唯一交互是连接到网络并验证其凭据。 所有内容将完全自动化。

Windows Autopilot 允许你：

- 将设备自动加入到 Azure Active Directory (Azure AD) 。
- 将设备自动注册到 MDM 服务（如 Microsoft Intune (需要 Azure AD Premium 订阅) 。
- 限制管理员帐户的创建。 Autopilot 是让登录 Windows 的第一个用户输入标准用户的唯一方法。
- 根据设备配置文件创建设备并自动将其分配到配置组。
- 自定义 OOBE (现成的体验) 内容和品牌，以满足组织的要求。
- 使用 Intune 启用完整设备配置。
- 远程重置或重启设备。

## 工作原理

Windows Autopilot 注册的设备将在首次启动时通过 Internet 标识，该设备签名是一个称为 *硬件哈希*的唯一设备签名。 它们通过使用新式管理解决方案（如 Azure Active Directory (Azure AD) 和移动设备管理）自动注册和配置。

您可以在从支持 Windows Autopilot 的 Surface 合作伙伴处购买时注册 Surface 设备。 这些合作伙伴可以将新设备直接发送给你的用户。 这些设备将在首次打开时自动注册和配置。 此过程消除了部署期间的映像，使你可以实现设备管理和分发的全新敏捷方法。

## 现代管理

Autopilot 是适用于 Surface 设备的推荐部署选项，包括 Surface Pro 7、Surface 笔记本3和 Surface Pro X，后者专为通过 Autopilot 进行部署而设计。

 最好使用 Microsoft 云解决方案提供商的帮助注册 Surface 设备。 此步骤允许你直接从 Intune 管理 Surface 固件设置。 它消除了针对证书管理的物理触控设备的需要。 有关详细信息，请参阅 [SURFACE UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md) 。

## Windows 版本注意事项

通过 Windows Autopilot 广泛部署 Surface 设备（包括购买时 Surface 合作伙伴的注册）需要 Windows 10 版本 1709 (秋季创建者更新) 或更高版本。

这些 Windows 版本支持4000字节 (4k) 哈希值，该哈希值唯一地标识 Windows Autopilot 的设备，这对于部署规模很有必要。 所有新的 Surface 设备（包括 Surface Pro 7、Surface Pro X 和 Surface 笔记本3）随 Windows 10 版本1903或更高版本一起提供。

## 需要维修或更换的 Surface 设备上的 Exchange 体验

Microsoft 会自动检查每个 Surface 的 Autopilot 注册，并将该设备从客户的租户中注销。  Microsoft 可确保一旦向客户推出更换设备，即可将替换设备注册到 Windows Autopilot。 此服务在所有设备 exchange 服务订单上通过 Microsoft 直接提供。

> [!NOTE]
> 当客户使用合作伙伴返回设备时，合作伙伴负责管理 exchange 流程，包括将设备注销和注册到 Windows Autopilot。

## Microsoft 支持注册

 (Csp) 的客户和 Microsoft 云解决方案提供商可以通过向 Microsoft 支持人员提交请求来选择注册 Surface 设备。 若要了解详细信息，请参阅 [Windows Autopilot 的 Surface Registration 支持](surface-autopilot-registration-support.md)。

## 为 Windows Autopilot 启用的 Surface 合作伙伴

选择 "Surface 合作伙伴" 可在购买时为您在 Windows Autopilot 中注册 Surface 设备。 他们还可以直接将注册的设备发运给你的用户。 通过使用 Windows Autopilot、Azure AD 和移动设备管理，可以完全通过零接触过程来配置设备。

为 Windows Autopilot 启用的 Surface 合作伙伴包括：

| 美国合作伙伴 | 全球合作伙伴 | 美国分销商 |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [而且](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [知识](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [SHI](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI 连接](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [了解](https://www.functiononeit.com/#empower)  |   |  |
| * [受保护的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## 了解详细信息

有关 Windows Autopilot 的详细信息，请参阅：
- [Windows Autopilot 概述](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Windows Autopilot 要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [适用于 Windows 的 Surface 注册支持 Autopilot](surface-autopilot-registration-support.md)
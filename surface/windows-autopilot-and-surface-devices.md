---
title: Windows Autopilot 和 Surface 设备
ms.reviewer: ''
manager: laurawi
description: 了解 Surface Windows的 Autopilot 部署选项。
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
ms.openlocfilehash: 6cf2996ab9348bcc778a4b334d82e52b2eebdcde
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676596"
---
# <a name="windows-autopilot-and-surface-devices"></a>Windows Autopilot 和 Surface 设备

WindowsAutopilot 是一种基于云的部署技术，Windows 10。 你可以立即Windows Autopilot 在零接触进程中远程部署和配置设备。

从传统来看，IT 专业人员花费大量时间生成和自定义映像，这些映像稍后将部署到已安装好操作系统的设备。 WindowsAutopilot 引入了一种新的零接触部署方法，该方法使用一组技术来设置和配置Windows设备。 这使 IT 部门能够配置/自定义映像，几乎无需管理基础结构，且过程简单明了。 从用户的角度来看，使 Surface 进入高效状态只需几个简单步骤。 实际上，最终用户所需的唯一交互是连接到网络并验证其凭据。 之后的所有操作都完全自动化。

WindowsAutopilot 允许你：

- 自动将设备加入 Azure Active Directory (Azure AD) 。
- 将设备自动注册到 MDM 服务（如Microsoft Intune (）需要Azure AD Premium订阅) 。
- 限制管理员帐户的创建。 Autopilot 是让第一个以标准用户Windows登录的唯一方式。
- 基于设备配置文件创建设备并将其自动分配给配置组。
- 自定义 OOBE (全新体验) 内容和品牌，以满足组织要求。
- 使用 Intune 启用完整的设备配置。
- 远程重置或重新启动设备。

## <a name="how-it-works"></a>工作原理

WindowsAutopilot 注册的设备在首次启动时通过称为硬件哈希的唯一设备签名通过 Internet*进行标识*。 通过使用现代管理解决方案（如 Azure AD Azure Active Directory (和移动设备管理) 自动注册和配置它们。

从启用了 Autopilot 的 Surface 合作伙伴购买时，你可以注册 surface Windows设备。 这些合作伙伴可以直接将新设备发货给用户。 设备将在首次打开时自动注册和配置。 此过程在部署期间消除了重映像，从而允许你实现设备管理和分发的新的敏捷方法。

## <a name="modern-management"></a>现代管理

Autopilot 是 Surface 设备的推荐部署选项，包括 Surface Pro 7+、Surface Laptop 3、Surface Pro 7 和 Surface Pro X，专用于通过 Autopilot 进行部署。

 最好在 Surface 设备注册时，使用 Microsoft 云解决方案提供商。 此步骤允许你直接从 Intune 管理 Surface 上的 UEFI 固件设置。 无需在物理上触摸设备进行证书管理。 有关详细信息 [，请参阅 Surface UEFI 设置的 Intune](surface-manage-dfci-guide.md) 管理。

## <a name="windows-version-considerations"></a>Windows版本注意事项

通过 Windows Autopilot 广泛部署 Surface 设备（包括在购买时由 Surface 合作伙伴注册）需要 Windows 10 版本 1709 (Fall Creators Update) 或更高版本。

这些 Windows 版本支持 4，000 字节 (4k) 哈希值，该值唯一标识 Windows Autopilot 的设备，这是大规模部署所必需的。 所有新的 Surface 设备（包括 Surface Pro 7+、Surface Pro X 和 Surface Laptop 3）都Windows 10版本 1903 或更高版本。

## <a name="exchange-experience-on-surface-devices-in-need-of-repair-or-replacement"></a>Exchange需要修复或更换的 Surface 设备上提供的体验

Microsoft 会自动检查每个 Surface 的 Autopilot 注册情况，并取消客户租户中的设备注册。  Microsoft 确保在将替换产品发回客户Windows替换设备注册到 Autopilot 中。 此服务可直接在 Microsoft 的所有设备交换服务订单上提供。

> [!NOTE]
> 当客户使用合作伙伴返回设备时，合作伙伴负责管理 Exchange 过程，包括注销设备以及将设备注册到 Autopilot Windows注册。

## <a name="microsoft-support-registration"></a>Microsoft 支持注册

客户和 Microsoft 云解决方案提供商 (云解决方案提供商) 向 Microsoft 支持人员提交请求，以注册 Surface 设备。 若要了解更多信息，请参阅[Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md)。

## <a name="surface-partners-enabled-for-windows-autopilot"></a>Surface 合作伙伴已启用 Windows Autopilot

选择 Surface 合作伙伴可以在购买时Windows在 Autopilot 中注册 Surface 设备。 他们还可以将已注册的设备直接发货给用户。 通过使用 Autopilot、Azure AD 和移动设备管理，可通过零接触Windows配置设备。

启用了 Autopilot 的 Surface 合作伙伴Windows包括：

| 美国合作伙伴 | 全球合作伙伴 | 美国分销商 |
|--------------|---------------|-------------------|
|  [CDW](https://www.cdw.com/) |  [Also](https://www.also.com/ec/cms5/da_2800/2800-msportal/products-and-solutions/surface/surface-is-more/surface-and-wa/index.jsp) |  [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
|  [左侧的“连接”](https://www.connection.com/brand/microsoft/microsoft-surface)   |  [ATEA](https://www.atea.com/) |  [Techdata](https://www.techdata.com/)  |
|  [见解](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  |  [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) |  [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
|  [SHI](https://www.shi.com/Surface) |  [Cancom](https://www.cancom.de/) |    |
|  [LDI 连接](https://www.myldi.com/managed-it/)  |  [Computacenter](https://www.computacenter.com/uk) |    |
|  [F1](https://www.functiononeit.com/#empower)  |   |  |
|  [受保护的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | |

## <a name="learn-more"></a>了解详细信息

有关 Autopilot Windows，请参阅：

- [Windows Autopilot 概述](/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Windows Autopilot 要求](/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [适用于 Windows Autopilot 的 Surface 注册支持](surface-autopilot-registration-support.md)

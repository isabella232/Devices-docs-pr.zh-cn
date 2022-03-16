---
title: 管理和部署 Surface 驱动程序和固件更新
description: 本文提供指向包含 Surface 设备的驱动程序和固件更新的可下载程序包的链接，并说明可用的管理和部署解决方案。
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface， Surface Pro 8， Surface Go， Surface Laptop， Surface Studio， Surface Pro 3， 固件， 更新， 设备， 管理， 部署， 驱动程序， USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 12/14/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: f914678f2317ce4e08554d27b74bac4e33e3c641
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449635"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>管理和部署 Surface 驱动程序和固件更新

管理 Surface 驱动程序和固件更新可能有所不同，具体取决于你的环境和组织要求。 在大型组织中，IT 管理员通常在内部部署阶段，并分配时间以测试升级，然后再将其部署到用户设备。

> [!NOTE]
> 本文适用于 IT 专业人员和技术支持代理，仅适用于 Surface 设备。 如果你正在寻找在家庭设备上安装 Surface 更新或固件的帮助，请参阅 [下载 Surface 的驱动程序和固件](https://support.microsoft.com/help/4023505)。

企业级软件分发解决方案不断发展，集中管理更新的业务原理保持不变：维护 Surface 设备的安全性，并使它们通过最新的操作系统和改进功能进行更新。 对于维持稳定的生产环境并确保不会阻止用户提高工作效率至关重要。

## <a name="whats-in-surface-driver-and-firmware-updates"></a>Surface 驱动程序和固件更新中的功能

Windows Installer .msi 文件包含 Surface 设备所需的所有累积驱动程序和固件更新。 更新程序包可能包括以下部分或所有组件：

- Wi-Fi 和 LTE
- 视频
- 固态硬盘
- 系统聚合器模块 (SAM) 
- 电池
- 键盘控制器
- 嵌入式控制器 (EC) 
- 管理引擎 (ME) 
- 统一可扩展固件接口 (UEFI) 

## <a name="download-msi-files"></a>下载.msi文件

本部分提供指向包含 Surface 设备的驱动程序和固件更新的可下载程序包的直接链接。 

1. 选择Windows 10或Windows 11选项。 
2. 对于具有多个 .msi 文件的设备，.msi Surface 型号和组织中部署版本匹配的 Windows 文件名。  


| Surface 设备                                                                                                                                        | 可下载.msi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Pro**                                                                                                                                       | - [Surface Pro 8](https://www.microsoft.com/en-us/download/details.aspx?id=103503)<br>- [Surface Pro 7+ 和 Surface Pro 7+ (LTE) ](https://www.microsoft.com/en-us/download/details.aspx?id=102633)<br>- [Surface Pro 7](https://www.microsoft.com/download/details.aspx?id=100419)<br>- [Surface Pro 6](https://www.microsoft.com/download/details.aspx?id=57514)<br>- [Surface Pro 5 (LTE) ](https://www.microsoft.com/download/details.aspx?id=56278)<br>- [Surface Pro 5 (WLAN) ](https://www.microsoft.com/download/details.aspx?id=55484)<br>- [Surface Pro 4](https://www.microsoft.com/download/details.aspx?id=49498)<br>- [Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826)<br>- [Surface Pro 2](https://www.microsoft.com/download/details.aspx?id=49042)<br>- [Surface Pro](https://www.microsoft.com/download/details.aspx?id=49038) |
| **Surface Laptop**                                                                                                                                    | - [Surface Laptop Go](https://www.microsoft.com/download/details.aspx?id=102261)<br>- [Surface Laptop 4 与 Intel 处理器](https://www.microsoft.com/download/details.aspx?id=102924)<br>- [Surface Laptop AMD 处理器安装 4](https://www.microsoft.com/download/details.aspx?id=102923)<br>- [Surface Laptop 3 与 Intel 处理器](https://www.microsoft.com/download/details.aspx?id=100429)<br>- [Surface Laptop AMD 处理器的 Surface Laptop 3](https://www.microsoft.com/download/details.aspx?id=100428)<br>- [Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)<br>- [Surface Laptop](https://www.microsoft.com/en-us/download/details.aspx?id=55489)                                                                                                                                                                                    |
| **Surface Laptop Studio**                                                                                                                             | - [Surface Laptop Studio](https://www.microsoft.com/en-us/download/details.aspx?id=103505)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Surface Book**                                                                                                                                      | - [Surface Book 3](https://www.microsoft.com/download/details.aspx?id=101315)<br>- [Surface Book 2](https://www.microsoft.com/download/details.aspx?id=56261)<br>- [Surface Book](https://www.microsoft.com/download/details.aspx?id=49497)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Surface Go**                                                                                                                                        | - [Surface Go 3](https://www.microsoft.com/en-us/download/details.aspx?id=103504)<br>- [Surface Go 2](https://www.microsoft.com/download/details.aspx?id=101304)<br>- [Surface Go (WLAN) ](https://www.microsoft.com/download/details.aspx?id=57439)<br>- [Surface Go (LTE) ](https://www.microsoft.com/download/details.aspx?id=57601)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Surface Studio**                                                                                                                                    | - [Surface Studio 2](https://www.microsoft.com/download/details.aspx?id=57593)<br>- [Surface Studio](https://www.microsoft.com/download/details.aspx?id=54311)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Surface 3**                                                                                                                                         | - [Surface 3 (WLAN) ](https://www.microsoft.com/download/details.aspx?id=49040)<br>- [Surface 3 (LTE) - ATT](https://www.microsoft.com/download/details.aspx?id=49039)<br>- [Surface 3 (LTE) - Verizon](https://www.microsoft.com/download/details.aspx?id=49920)<br>- [Surface 3 (LTE) - 北美运营商解锁](https://www.microsoft.com/download/details.aspx?id=49037)<br>- [Surface 3 (LTE) - 北美以外，日本为 Y！mobile](https://www.microsoft.com/download/details.aspx?id=49041)                                                                                                                                                                                                                                                                                                                                                   |
| **Surface Hub运行**[**Windows 10 专业版或Windows 10 企业版**](/surface-hub/surface-hub-2s-migrate-os)   | - [Windows 10 专业版 2 Enterprise上的 Surface Hub 操作系统](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Surface Hub 2020 Windows 10 Teams 2020 更新**                                                                                                  | - 请参阅[管理Windows更新Surface Hub](/surface-hub/manage-windows-updates-for-surface-hub)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Surface 扩展坞 2**                                                                                                                                    | - [Surface 扩展坞 2](https://www.microsoft.com/download/details.aspx?id=101317)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

 

> [!TIP]
> 对于包含不同版本不同版本Windows文件较早的设备，.msi Surface 型号和版本匹配的 Windows。 the .msi file name includes the minimum supported Windows build number that's required to install the drivers and firmware. 例如，若要更新Surface Book版本 18362 的 Windows 10 2，请选择"SurfaceBook2_Win10_18362_19.101.13994.msi ** "。** 对于Surface Book版本 16299 的 Windows 10 2，请选择"SurfaceBook2_Win10_16299_1803509_3.msi** "**。

## <a name="central-update-management-in-commercial-environments"></a>商业环境中的中央更新管理

用于管理设备的工具（包括驱动程序和固件更新）包含在[Microsoft Endpoint Manager](https://devicemanagement.microsoft.com/)。 

### <a name="manage-updates-with-configuration-manager-and-intune"></a>使用 Configuration Manager 和 Intune 管理更新

Microsoft Endpoint Configuration Manager允许你与 Configuration Manager 客户端同步和部署 Surface 固件和驱动程序更新。 与 Microsoft Intune集成后，可以在一个地方查看所有托管、共同管理和合作伙伴管理的设备。 这是建议大型组织管理 Surface 更新的解决方案。

有关详细步骤，请参阅以下资源：

- [管理 Configuration Manager 中的 Surface 驱动程序更新](manage-surface-driver-updates-configuration-manager.md)
- [使用 Configuration Manager 部署应用程序](/configmgr/apps/deploy-use/deploy-applications)
- [Endpoint Configuration Manager 文档](/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>使用 Microsoft Deployment Toolkit

Microsoft Deployment Toolkit (MDT) 包含在 Endpoint Configuration Manager 中。 根据您的环境，它包含您可能需要使用的可选部署工具。  其中包括 Windows 评估和部署工具包 (Windows ADK) 、Windows 系统映像管理器 (Windows SIM) 、部署映像服务和管理 (DISM) 以及用户状态迁移工具 (USMT) 。 你可以从 Microsoft Deployment Toolkit[下载最新版本的 MDT](https://www.microsoft.com/download/details.aspx?id=54259)。

有关详细步骤，请参阅以下资源：

- [Microsoft 部署Toolkit文档](/configmgr/mdt/)
- [准备使用 MDT 部署](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)

有关如何使用 Endpoint Configuration Manager 部署更新的说明，请参阅 [使用 Configuration Manager 部署应用程序](/configmgr/apps/deploy-use/deploy-applications)。 有关如何使用 MDT 部署更新的说明，请参阅[使用 MDT Windows 10部署映像](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)。

**WindowsPE 和 Surface 固件和驱动程序**

终结点配置管理器和 MDT 在部署过程中Windows WindowsPE (windowsPE) 预安装环境。 WindowsPE 仅支持一组有限的基本驱动程序，如网络适配器和存储控制器。 非 WindowsPE Windows的组件驱动程序可能会产生错误。 最佳做法是，可以通过将部署过程配置为在 WindowsPE 阶段仅使用所需驱动程序来防止此类错误。

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

从 Endpoint Configuration Manager 开始，可以使用 Configuration Manager 客户端同步和部署 Microsoft Surface 固件和驱动程序更新。 有关其他信息，请参阅 KB 4098906， [在 Configuration Manager 中管理 Surface 驱动程序更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)。

## <a name="supported-devices"></a>支持的设备

可.msi文件适用于 Surface Pro 2 和更高版本的设备 (，Surface Pro X Windows 10运行ARM) 。

## <a name="managing-firmware-with-dfci"></a>使用 DFCI 管理固件

通过将设备固件配置接口 (内置在 [Intune](/intune/configuration/device-firmware-configuration-interface-windows)) DFCI 配置文件中，Surface UEFI 管理将新式管理堆栈向下扩展到 UEFI 硬件级别。 DFCI 支持零接触预配、消除 BIOS 密码、控制安全设置 (包括启动选项和内置外设) ，并在将来为高级安全方案打下基础。 有关详细信息，请参阅以下内容：

- [在 Surface 设备上管理 DFCI](surface-manage-dfci-guide.md)
- [Ignite 2019：宣布从 Intune 远程管理 Surface UEFI 设置](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。

## <a name="best-practices-for-update-deployment-processes"></a>更新部署过程最佳做法

若要维护稳定环境，我们强烈建议您保持与最新版本的 Windows 10。  有关最佳实践建议，请参阅[准备客户端](/windows/deployment/update/waas-deployment-rings-windows-10-updates)更新Windows策略。

### <a name="surface-msi-naming-convention"></a>Surface .msi命名约定

自 2019 年 8 .msi，多个文件都使用下列命名约定：

- *Product* _*Windows release*_ *Windows build numberVersion*_**_ *numberRevision of version numberrevision of version number (typically zero) *.

**示例**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

此文件名提供以下信息：

- **产品：** SurfacePro6
- **Windows版本：** Win10
- **内部版本：** 18362
- **版本：** 19.073.44195 – 显示文件的创建日期和时间，如下所示：
  - **年份：** 2019 年 1 (19) 
  - **月份和周：** 073 (年 7 月的第三周) 
  - **一个月的分钟数：** 44195
- **版本修订：** 0 (此版本的第一个版本) 

### <a name="legacy-surface-msi-naming-convention"></a>旧版 Surface .msi命名约定

旧.msi文件 (2019 年 8 月之前构建) 整体命名公式，但使用不同的方法来派生版本号。

**示例**

- SurfacePro6_Win10_16299_1900307_0.msi

此文件名提供以下信息：

- **产品：** SurfacePro6
- **Windows版本：** Win10
- **内部版本：** 16299
- **版本：** 1900307 – 显示文件的创建日期及其在发布序列中的位置，如下所示：
  - **年份：** 2019 年 1 (19) 
  - **发布数量：** 003 (年第三版) 
  - **产品版本号：** 07 (Surface Pro 6 正式是第七版 Surface Pro) 
- **版本修订：** 0 (此版本的第一个版本) 

## <a name="learn-more"></a>了解详细信息

- [准备 Windows 客户端更新的维护策略](/windows/deployment/update/waas-deployment-rings-windows-10-updates)
- [管理 Configuration Manager 中的 Surface 驱动程序更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [使用 Configuration Manager 部署应用程序](/configmgr/apps/deploy-use/deploy-applications)
- [Endpoint Configuration Manager 文档](/configmgr/)
- [Microsoft 部署Toolkit文档](/configmgr/mdt/)
- [准备使用 MDT 部署](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [在 Surface 设备上管理 DFCI](surface-manage-dfci-guide.md)
- [Ignite 2019：宣布从 Intune 远程管理 Surface UEFI 设置](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。


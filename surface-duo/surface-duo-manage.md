---
title: Surface Duo 管理概述
description: 本文重点介绍了在商业环境中管理 Surface Duo 的选项。
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/23/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 19ef3f5d20b22997aa339a462a34b84da27fb922
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326123"
---
# Surface Duo 管理概述

商业客户可以使用各种企业移动性管理 (EMM) 解决方案来管理 Surface Duo，每种解决方案都提供一组一致的基于云的设备管理功能，无论是管理员工设备还是公司拥有的设备。

可以通过使用统一控制台（Microsoft Endpoint Manager）和可扩展组件（如 Microsoft Intune）的 [Microsoft EMM](https://androidenterprisepartners.withgoogle.com/provider/#!/75) 管理 Duo。 或者，您可以使用 Google Android 生态系统中的任意 EMM 提供程序。 在某些情况下，第三方 EMM 解决方案提供额外支持，以满足可能根据您的环境有用的特定方案。

 若要比较 EMM 解决方案，请参阅 [Android 企业版解决方案目录](https://androidenterprisepartners.withgoogle.com/emm/)。
使用 Intune 的 Endpoint Manager，可以使用最新的移动设备管理策略以及早期技术（如 Exchange ActiveSync）管理 Duo。 如果你已使用Exchange ActiveSync设置来管理移动设备，可以使用电子邮件设备配置配置文件将这些设置应用于 Intune 中的 Duo 设备。  有关详细信息，请参阅使用 [Intune 将电子邮件设置添加到设备](https://docs.microsoft.com/mem/intune/configuration/email-settings-configure)。

在 Intune 中管理设备的主要方式是，配置文件提供默认设置，你可以自定义这些设置以满足组织的需求。 

##  <a name="managing-personally-owned-surface-duo-devices"></a>管理个人拥有的 Surface Duo 设备
| 解决方案                                          | 功能                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | 了解详细信息                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 无需设备注册的应用保护策略 | 允许您在应用程序中管理和保护组织的数据。<br>部署应用保护策略，这是一种轻型管理解决方案，无需设备注册。<br>现在，可以使用应用保护策略（包括 Microsoft Office 和第三方应用（如 Adobe Acrobat、Service Now 和 Zoom）管理越来越多的应用。 有关完整列表，请参阅 [Microsoft Intune 保护的应用](https://docs.microsoft.com/mem/intune/apps/apps-supported-intune-apps)。 | - [应用保护策略概述](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)<br>- [Microsoft Intune 中的 Android 应用保护策略设置](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)。<br>- [使用 Intune 应用包装工具为应用](https://docs.microsoft.com/mem/intune/developer/app-wrapper-prepare-android)保护策略准备 Android 应用。 |
| Android 企业版工作配置文件                   | 工作配置文件面向 BYOD 部署，在 Duo 上为工作应用和数据提供了单独的空间，使组织可以完全控制其数据、应用和安全策略，而不会限制用户将设备用于个人应用和数据。                                                                                                                                                                                                                                                  | - [为 Surface Duo 配置 Android 企业版工作配置文件](surface-duo-config-work-profile.md)。                                                                                                                                                                                                                                                                                                               |


##  <a name="managing-corporate-owned-surface-duo-devices"></a>管理企业拥有的 Surface Duo 设备

| 解决方案                                  | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | 了解详细信息                                                                                                                                                                                                                                                                                                      |
| ----------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 具有工作配置文件的企业拥有的设备 | 面向希望在他们为工作提供的企业拥有的单用户设备上启用个人用途的组织。 它旨在向组织提供比使用工作配置文件管理更精细的控制，但不希望使用完整设备管理或专用设备管理完全锁定设备。<br>工作和个人配置文件应用数据由 Android 操作系统隔离，但通过为管理员提供更多的设备级控制来不同于 Android 企业版工作配置文件。<br>IT 管理员可以在工作配置文件中查看、控制和配置工作帐户、应用程序和数据，同时保证最终用户不会查看个人配置文件中的数据和应用程序。 | - [Intune 宣布推出具有工作配置文件的 Android 企业所有设备的公共预览版](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-announcing-public-preview-for-android-enterprise/ba-p/1524325)                                                                    |
| Android 企业版完全托管          | 为与单个用户关联的公司拥有的设备提供全面的设备和应用管理功能，并专门用于工作而不是个人用途。<br> <br>完整的设备管理使 IT 可以完全控制设备数据和安全性，并可以访问 Android 的完整应用管理功能套件。 例如：<br><br>- 你可以设置设备上的最低密码要求<br>- 远程擦除和锁定设备<br>- 设置应用程序权限请求的默认响应。<br>- 使用 Microsoft 启动器自定义最终用户体验<br><br>还可以完全控制设备上的应用，包括远程安装和删除应用。                                 | - [设置 Android 企业版完全托管设备的 Intune 注册](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-enroll)。 |
| 专用设备管理               | 此企业部署方案面向部署到特定用例（如后勤、交通和工厂楼层）的设备。 用于需要限制使用一个或两个应用并禁止用户更改任何设置的锁定体验。                                                                                                                                                                                                                                                                                                                                                                                                                                                           | - [设置 Android 企业版专用设备的 Intune 注册](https://docs.microsoft.com/mem/intune/enrollment/android-kiosk-enroll)                                                                                                                                                               |

 
##  <a name="learn-more"></a>了解详细信息
- [Ignite 会话：使用企业中的 Surface Duo 部署、管理和启用工作效率](https://youtu.be/DOsBMNFmdfw)
- [使用 Microsoft Intune 管理设备](https://docs.microsoft.com/mem/intune/remote-actions/device-management)
- [Intune 部署规划、设计和实现指南](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [使用 Intune 注册 Android 设备](https://docs.microsoft.com/mem/intune/enrollment/android-enroll)

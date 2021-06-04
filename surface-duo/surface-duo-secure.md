---
title: Surface Duo 安全性概述
description: 本文重点介绍 Surface Duo 如何在移动设备上通过 Android OS 和 Microsoft 设计的 UEFI 提供企业级安全性。
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/12/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 91eb893dbdc6dae93cf402a602b64a83309388e8
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326120"
---
# Surface Duo 安全性概述

Surface Duo 在具有深入集成的硬件、固件和软件的每一层内置保护，以保持设备、标识和数据的安全。 作为 Android 10 设备，Surface Duo 在操作系统级别和 Google 服务层利用 Android 安全功能。 Android 操作系统利用传统操作系统安全控件来保护用户数据和系统资源，保护设备完整性免受恶意软件的攻击，并提供应用程序隔离。 此外，Google 还提供一些分层在操作系统顶部的服务，这些服务与 Android 操作系统安全性结合使用时，有助于持续保护 Android 用户。

- **自定义工程 UEFI。** Surface Duo 在 Android 设备中的独特之处是 Microsoft 自定义设计的统一可扩展固件接口 (UEFI) ，可完全控制固件组件。 Microsoft 通过编写或审阅内部的每一行固件代码，为 Surface Duo 提供企业级安全性，从而使 Microsoft 能够直接敏捷地响应潜在固件威胁，并降低供应链安全风险。
- **已验证启动。** 从登录后的硬件级别开始，验证启动努力确保执行的代码仅来自受信任的源。 它建立一个完整的信任链 - 从受硬件保护的信任根到启动加载程序、启动分区和其他已验证分区。 当 Surface Duo 启动时，每个阶段将验证下一阶段的完整性和真实性，然后再进行执行。
- **应用分离。** 应用程序沙盒隔离并保护 Android 应用，防止恶意应用访问私人信息。 强制且始终启用的加密和密钥处理有助于保护传输中和静态的数据 ，即使设备落入错误之手。 加密使用密钥存储密钥进行保护，密钥存储密钥将加密密钥存储在容器中，从而使得从设备中提取变得更加困难。
- **Google Play Protect。** 在软件层，Surface Duo 使用 Google Play 保护威胁检测来扫描所有应用程序，包括 Google Play 中的公共应用、Microsoft 和运营商更新的系统应用以及旁加载的应用。
- **Microsoft Defender ATP。** 适用于 Window 10 的企业级防病毒和恶意软件保护软件现在可用于从 Intune 管理的 Android 设备。 若要了解更多信息，请参阅[适用于 Android 的 Microsoft defender ATP。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-android) 


##  <a name="mobile-device-management-security"></a>移动设备管理安全性

Surface Duo 在企业环境中使用企业移动性管理 (EMM) 解决方案进行保护，该解决方案提供一组一致的保护工具、技术和最佳做法，你可以根据组织和合规性要求进行定制。 广泛的管理 API 为 IT 部门提供了各种工具，以帮助防止数据泄露，并强制在多种方案中实现合规性。 多配置文件支持和设备管理选项支持分离工作和个人数据，帮助确保公司数据安全。

MDM 安全性基于一组扩展的配置技术构建，使用户能够在一起高效工作，同时保护关键企业知识产权。 这包括应用保护策略、设备限制策略和相关技术，旨在使您能够根据环境实现特定目标 - 业务包括提供餐厅外线订单、管理办公场所的 IT 服务或处理敏感的国家/地区安全信息。 

例如，你可能希望通过要求用户输入 6 位字母数字引脚和 2 因素身份验证来加强设备身份验证。  你可能希望限制用户可以注册的设备，以帮助确保你遵守许可限制，或者避免授予对"越狱"电话或其他不受支持的设备类型的访问权限。
Intune 和其他 EMM 为组织提供了根据其需求管理设备的灵活性。

##  <a name="app-protection-policies"></a>应用保护策略

APP (策略) 是可确保组织数据保持安全或包含在托管应用中的规则。 策略可以是在用户尝试访问或移动"公司"数据时强制执行的规则，或者是在用户位于应用内时禁止或监视的一组操作。 托管应用是应用了应用保护策略的应用，并且可以通过 Intune 进行管理。

应用保护策略允许你在应用程序中管理和保护组织的数据。 许多生产力应用（如Microsoft Office应用）都可以由 Intune MAM 管理。 请参阅可供公共使用的 [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-supported-intune-apps) 保护的应用的官方列表。

##  <a name="security-considerations-for-managing-surface-duo"></a>管理 Surface Duo 的安全注意事项

移动设备管理解决方案中可用的策略设置数量不断增加，使组织能够调整保护级别以满足其特定需求。 为了帮助组织确定 Surface Duo (或任何其他 Android 设备) 的安全设置的优先级，Intune 引入了其组织到多个不同配置方案的 [Android 企业](https://docs.microsoft.com/mem/intune/enrollment/android-configuration-framework) 版安全配置框架，为工作配置文件和完全管理的方案提供指导。
 

| 安全级别                                                                                                       | 面向                                                                                                                                                                      | 摘要                                                                                                                                                                                     | 设置信息                                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 工作配置文件基本安全性 - 级别 1                                                                                | 有权访问工作或学校数据的个人设备。                                                                                                                             | 引入密码要求、分隔工作和个人数据，并验证 Android 设备证明。                                                                               | [工作配置文件级别 1 设置](https://microsoft.sharepoint.com/teams/EpsilonAdminGuide/Shared%20Documents/General/•%09https:/docs.microsoft.com/mem/intune/enrollment/android-work-profile-security-settings#work-profile-basic-security) |
| 工作配置文件高安全性 - 级别 3<br> (由于框架约定，这是级别 1.) <br> ** | 由具有独特高风险的用户或组使用的设备。 例如，处理高度敏感数据的用户在未经授权的情况下导致大量材料损失。 | 引入了移动威胁防护或 Microsoft Defender ATP，将最低 Android 版本设置为 8.0，引入了更强大的密码策略，并进一步限制工作和个人分离。 | [工作配置文件级别 3 设置](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-security-settings#work-profile-high-security)                                                                                         |
| 完全托管的基本安全性 -级别 1                                                                                | 企业设备的最低安全性配置，适用于访问工作或学校数据大多数移动用户。                                                          | 引入了密码要求，将最低 Android 版本设置为 8.0，并规定了某些设备限制。                                                                          | [完全托管级别 1 设置](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-basic-security)                                                                                     |
| 完全托管的增强安全级别 2                                                                              | 用户访问敏感信息或机密信息的设备。                                                                                                                | 增强密码策略并禁用用户/帐户功能。                                                                                                                   | [完全托管级别 2 设置](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-enhanced-security)                                                                                   |
| 完全托管的高安全级别 3                                                                                  | 由具有独特高风险的用户或组使用的设备。 例如，处理高度敏感数据的用户在未经授权的情况下导致大量材料损失。 | 将最低 Android 版本增加至 10.0，引入移动威胁防护或 Microsoft Defender ATP，并强制执行其他设备限制。                                     | [完全托管级别 3 设置](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-high-security)                                                                                      |
 
与任何框架一样，可能需要根据组织的需求调整相应级别的设置，因为安全必须评估威胁环境、风险防范以及可用性影响。
 
 
**了解详细信息**


- [Android 企业版安全配置框架](https://docs.microsoft.com/mem/intune/enrollment/android-configuration-framework)
- [应用保护策略概述](https://docs.microsoft.com/mem/intune/apps/app-protection-policy)
- [Microsoft Intune 中的 Android 应用保护策略设置](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)
- [设置注册限制](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set)
- [Android 企业安全白皮书](https://static.googleusercontent.com/media/www.android.com/en//static/2016/pdfs/enterprise/Android_Enterprise_Security_White_Paper_2019.pdf)
 
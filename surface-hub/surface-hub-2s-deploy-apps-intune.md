---
title: 使用 Intune 将应用部署到 Surface Hub 2S
description: 了解如何使用 Intune 将应用部署到 Surface Hub 2。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831571"
---
# 使用 Intune 将应用部署到 Surface Hub 2S

你可以安装其他应用以满足你的团队或组织的需求。

##  <a name="developer-guidelines"></a>开发人员指南

- Surface Hub 仅运行[通用 Windows 平台 (UWP) 应用](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)。 无法在 Surface Hub 上运行使用 [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) 创建的应用。
- 应用必须面向[通用设备系列](https://msdn.microsoft.com/library/windows/apps/dn894631)或 Windows 团队设备系列。
- Surface Hub 仅支持[Microsoft Store For Business](https://businessstore.microsoft.com/store)中的[脱机许可应用](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)。
- 默认情况下，应用必须经过应用商店签名才能安装。 在测试和开发时，还可以选择运行开发人员签名的 UWP 应用，使设备进入开发人员模式即可。
- 在向 Microsoft Store 开发应用和提交应用时，请设置设备系列可用性和组织授权选项以确保应用可以在 Surface Hub 上运行。
- 需要管理员凭据才能在 Surface Hub 上安装应用。 为了在会议室和其他共享空间中使用，Surface Hub 阻止常规用户访问 Microsoft Store 以下载和安装应用。

##  <a name="deployment-guidelines"></a>部署指南

你可以使用 Intune 将通用 Windows 平台（UWP）应用部署到 Surface Hub 2，从而使应用部署更易于使用设备。

1. 若要部署应用，请为你的组织启用 MDM。 在 Intune 门户中，选择 " **Intune** " 作为你的 MDM 机构（推荐）。 <br>

    ![选择 "MDM 机构"](images/sh2-set-intune5.png)

2. 在 Intune 中启用 Microsoft Store for Business。 打开 Intune，选择 "**客户端应用**  >  **Microsoft Store for Business"。** <br>

    ![启用企业应用商店](images/sh2-deploy-apps-sync.png)

3. 在 Intune 中打开**Microsoft Store for Business** ，然后选择 "**设置**  >  **分发**  >  **管理工具**"。 选择 " **Microsoft Intune**作为你的管理工具"。 <br>

    ![将 Intune 添加为你的管理工具](images/sh2-set-intune8.png)

4. 在 Microsoft Store for Business 中，选择 "**设置**  >  **车间**  >  **购物体验**"，然后选择 "**显示脱机应用**"。 脱机应用指可同步到 Intune 并集中部署到设备的应用。
5. 启用脱机购物后，你可以为可同步到 Intune 并部署为设备授权的应用获取脱机许可证。
6. 在**Intune**  >  **客户端应用**  >  **Microsoft Store for Business**中，选择 "**同步**"。
7. 在 "客户端应用" 页面中，在 "应用" 列表中搜索应用。 将应用分配到所需的设备组。 选择 "**作业**  >  **添加组**"。 <br>

![* 将应用分配给组 *](images/sh2-assign-group.png) <br>

8. 在 "作业类型" 下，选择 "**必需**"。 <br>

![* 将应用分配给组 *](images/sh2-add-group.png) <br>

9. 对于选定的组，请选择 "**设备授权**"，然后选择 **"确定"** 并保存作业。 <br>
 
![* 将应用分配给组 *](images/sh2-apps-assign.png)

---
title: 创建 Surface Hub 2S 的预配程序包
description: 本页介绍如何使用预配包和其他工具部署 Surface Hub 2。
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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832187"
---
# 创建 Surface Hub 2S 的预配程序包

你可以使用 Windows 配置设计器（WCD）创建预配程序包，以自动执行 Surface Hub 2 的部署过程。 使用预配程序包添加证书、配置代理、设置设备管理员和设备帐户。 你还可以使用预配包和配置文件来部署具有单个 USB 拇指驱动器的多个 Surface Hub。

### 安装 Windows 配置设计器

从 windows 10 的 Windows 评估和部署工具包（ADK）安装 Windows 配置设计器。 下载并安装[适用于 Windows 10 版本1703的 ADK](https://go.microsoft.com/fwlink/p/?LinkId=845542)。 有关详细信息，请参阅[下载并安装 WINDOWS ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)。

### 添加证书

您可以将证书颁发机构证书导入到 Surface Hub 2。
若要向 Surface Hub 2 添加证书，你需要将每个证书的副本作为 x.509 格式。 不能导入 .crt、.pfx 或其他容器格式。 必须将证书导入 Windows 配置设计器并按层次结构排列：

 ![添加证书](images/sh2-wcd.png)

### 在 OOBE 期间配置代理

在 Windows 配置设计器中，转到 "配置代理服务器设置" 选项卡，然后输入相应的设置，如下所示。

 ![配置代理设置](images/sh2-proxy.png) 

> [!NOTE]
> 配置代理服务器设置时，如果打算使用安装脚本或代理服务器，请关闭 "**自动检测设置**"。 你可以使用设置脚本*或*代理服务器，而不是同时使用这两者。

### Azure Active Directory 的关联 Surface Hub 2

你可以使用预配包将 Surface Hub 2 与 Azure Active Directory 关联：作为 Azure Active Directory 全局管理员，你可以使用批量令牌将大量新的 Windows 设备加入到 Azure Active Directory 和 Intune。

若要创建批量令牌，请为其指定一个友好名称，配置过期日期（最多30天），并使用管理员凭据获取令牌，如下所示：

 ![设置设备管理员](images/sh2-token.png) <br><br>
 ![设置设备管理员](images/sh2-token2.png) <br><br>
 ![设置设备管理员](images/sh2-token3.png) <br><br>

### 预配多个设备（.csv 文件）

除了预配包之外，你还可以使用 Surface Hub 配置文件，以便更轻松地设置你的设备。 Surface Hub 配置文件包含设备帐户列表和用于无线投影的友好名称。 首次运行时，你可以从配置文件获取选择设备帐户和友好名称的选项。

### 创建 Surface Hub 配置文件

1. 使用 Microsoft Excel 或其他 CSV 编辑器，创建名为： **SurfaceHubConfiguration.csv**的 CSV 文件
2. 按以下格式输入设备帐户和友好名称的列表：

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. 将文件保存到您复制了 PPKG 文件的 USB 拇指驱动器的根。

    ![配置文件示例](images/sh2-config-file.png)

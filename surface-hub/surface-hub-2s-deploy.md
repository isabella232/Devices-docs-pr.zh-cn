---
title: 创建 Surface Hub 2S 的预配程序包
description: 此页面介绍如何使用预配包Surface Hub部署 2S。
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
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576862"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a>创建 Surface Hub 2S 的预配程序包

可以使用配置设计器Windows WCD (WCD) 创建预配包，以自动部署 Surface Hub 2S。 使用预配包添加证书、配置代理、设置设备管理员和设备帐户。 还可以将预配包与配置文件一起用于部署具有单个 U 盘的多个 Surface Hub。

### <a name="install-windows-configuration-designer"></a>安装 Windows 配置设计器

从Windows ADK Windows部署工具包 (配置) 配置Windows 10。 下载并安装适用于 Windows 10[版本 1703 的 ADK。](https://go.microsoft.com/fwlink/p/?LinkId=845542) 有关详细信息，请参阅“[下载并安装 Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)”。

### <a name="add-certificates"></a>添加证书

可以将证书颁发机构证书导入 Surface Hub 2S。
若要将证书添加到 Surface Hub 2S，您需要每个证书的副本为 X.509，格式为 .cer。 不能导入 .crt、.pfx 或其他容器格式。 证书必须导入到Windows设计器中，并按层次结构排列：

> [!div class="mx-imgBorder"]
> ![添加证书](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a>在 OOBE 期间配置代理

In Windows Configuration Designer， go to the Configure proxy settings tab and enter the appropriate settings as shown below.

> [!div class="mx-imgBorder"]
> ![配置代理设置](images/sh2-proxy.png) 

> [!NOTE]
> 配置代理设置时，如果您打算使用**** 安装脚本或代理服务器，请关闭"自动检测设置"。 您可以使用安装程序 *脚本或代理服务器* ，而不是同时使用这两者。

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a>关联Surface Hub 2S 与 Azure Active Directory

可以使用预配包将 Surface Hub 2S 与 Azure Active Directory 关联：作为 Azure Active Directory 全局管理员，可以使用批量令牌将大量新的 Windows 设备加入 Azure Active Directory 和 Intune。

若要创建批量令牌，请为它指定一个友好名称，将到期日期配置为 (最长 30 天) 并使用管理员凭据获取令牌，如下所示：

> [!div class="mx-imgBorder"]
> ![设置设备管理员示例 1](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![设置设备管理员示例 2](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![设置设备管理员示例 3](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a>预配多个设备 (.csv文件) 

除了预配包之外，您还可以使用 Surface Hub 配置文件，以便更轻松地设置设备。 一Surface Hub配置文件包含无线投影的设备帐户和友好名称的列表。 首次运行时，你可以选择从配置文件中选择设备帐户和友好名称。

### <a name="to-create-a-surface-hub-configuration-file"></a>创建Surface Hub配置文件

1. 使用Microsoft Excel或其他 CSV 编辑器，创建**名为：SurfaceHubConfiguration.csv**

2. 按此格式输入设备帐户和友好名称列表：

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. 将文件保存到你复制 PPKG 文件的 U 盘的根目录。

    > [!div class="mx-imgBorder"]
    > ![配置文件示例](images/sh2-config-file.png)

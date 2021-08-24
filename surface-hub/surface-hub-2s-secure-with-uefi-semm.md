---
title: 使用 SEMM Surface Hub和管理 2S
description: 详细了解如何通过 SEMM Surface Hub 2S 安全。
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
ms.openlocfilehash: b22bfc39c07facb84ca57438ec16038492f85d15
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911037"
---
# <a name="secure-and-manage-surface-hub-2s-with-semm-and-uefi"></a>使用 SEMM 和 UEFI 保护 Surface Hub 2S 的安全并进行管理

这是 Surface Hub 2S 中的新增功能，可以使用 SEMM 管理设备的 UEFI 设置。
使用 Microsoft Surface UEFI 配置器控制以下组件：

- 有线局域网
- 相机
- 蓝牙
- WLAN
- 占用传感器

使用 Microsoft Surface UEFI 配置器打开或关闭以下 UEFI 设置：

- 靴子

    - 用于 PXE 启动的 IPv6
    - 备用启动
    - 启动顺序锁
    - USB 启动
- UEFI 首页

    - 设备
    - 靴子
    - 日期/时间

## <a name="create-uefi-configuration-image"></a>创建 UEFI 配置映像

与其他 Surface 设备不同，你无法使用 MSI 文件或 Win PE 映像在 2S Surface Hub这些设置。 相反，你需要创建 USB 映像以加载到设备中。 若要创建 Surface Hub 2S UEFI 配置映像，请从 Microsoft 下载中心的[Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)页面下载并安装最新版本的 Microsoft Surface UEFI 配置器。 有关使用 UEFI 和 SEMM 的信息，请参阅[Microsoft Surface Enterprise管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。

## <a name="to-configure-uefi-on-surface-hub-2s"></a>在 2S Surface Hub UEFI

1. 启动 UEFI 配置器，然后第一个屏幕上，选择配置 **包**。<br><br>
![* 启动 UEFI 配置程序，然后选择配置包*。](images/sh2-uefi1.png) <br> <br>
2. 若要将证书添加到程序包中，你必须具有一个有效的证书，该证书具有 .pfx 文件格式的私钥，以对程序包进行签名和保护。 选择 **+ 证书保护。** <br>
![* 选择 + 证书保护 *。](images/sh2-uefi2.png) <br><br>
3. 输入证书的私钥密码。<br>
![* 输入证书的私钥密码 *。](images/sh2-uefi3.png) <br><br>
4. 导入私钥后，继续创建包。<br>
![* 继续创建程序包 *。](images/sh2-uefi4.png) <br><br>
5. 选择**中心**Surface Hub **2S**作为 UEFI 配置包的目标。<br>
![* 选择中心Surface Hub 2S 作为 UEFI 配置包 *的目标。](images/sh2-uefi5.png) <br><br>
6. 选择要在 2S 上激活或停用的组件Surface Hub设置。<br>
![* 选择要激活或停用的组件和设置 *。](images/sh2-uefi6.png) <br><br>
7. 使用 USB 选项导出文件。<br>
![* 使用 USB 选项导出文件 *。](images/sh2-uefi8.png) <br><br>
8. 插入并选择要用于此程序包的 USB 驱动器。 USB 驱动器将进行格式化，并且你丢失了它上拥有的任何信息。<br>
![* 插入并选择程序包的 USB 驱动器 *。](images/sh2-uefi9.png) <br><br>
9. 成功创建包后，Configurator 将显示证书指纹的最后两个字符。 在导入到 2S 的配置时，需要Surface Hub字符。<br>
![* 成功配置程序包 *。](images/sh2-uefi10.png) <br>

## <a name="to-boot-into-uefi"></a>启动到 UEFI

关闭Surface Hub 2S。 长按 **"调高音量"** 按钮，然后按 **电源** 按钮。 继续按住"调高音量"按钮，直到 UEFI 菜单显示。

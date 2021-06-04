---
title: 通过 SEMM 保护和管理 Surface Hub 2
description: 了解有关通过 SEMM 保护 Surface Hub 的详细信息。
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
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830930"
---
# 使用 SEMM 和 UEFI 保护 Surface Hub 2S 的安全并进行管理

新的 Surface Hub 2，您可以使用 SEMM 管理设备的 UEFI 设置。
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
- UEFI 前页

    - 设备
    - 靴子
    - 日期/时间

##  <a name="create-uefi-configuration-image"></a>创建 UEFI 配置图像

与其他 Surface 设备不同，您不能使用 MSI 文件或 Win PE 映像在 Surface Hub 2 秒上应用这些设置。 相反，你需要创建一个 USB 图像以加载到设备中。 若要创建 Surface Hub 2 UEFI 配置映像，请从 Microsoft 下载中心的 " [Surface Tools FOR IT](https://www.microsoft.com/download/details.aspx?id=46703) " 页面下载并安装最新版本的 MICROSOFT Surface UEFI 配置器。 有关使用 UEFI 和 SEMM 的详细信息，请参阅[Microsoft Surface 企业管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。

##  <a name="to-configure-uefi-on-surface-hub-2s"></a>在 Surface Hub 2 上配置 UEFI

1. 启动 UEFI 配置器，在第一个屏幕上，选择 "**配置包**"。<br><br>
![* 启动 UEFI 配置器并选择 "配置包" *](images/sh2-uefi1.png) <br> <br>
2. 若要将证书添加到你的程序包，你必须拥有一个 .pfx 文件格式的私钥的有效证书，才能对包进行签名和保护。 选择 " **+ 证书保护"。** <br>
![* 选择 + 证书保护 *](images/sh2-uefi2.png) <br><br>
3. 输入证书的专用密钥密码。<br>
![* 输入证书的专用密钥的密码 *](images/sh2-uefi3.png) <br><br>
4. 导入私钥后，继续创建程序包。<br>
![* 继续创建程序包 *](images/sh2-uefi4.png) <br><br>
5. 选择 "**中心**" 和 " **Surface hub** 2" 作为 UEFI 配置包的目标。<br>
![* 选择 "中心" 和 "Surface Hub 2" 作为 UEFI 配置包的目标 *](images/sh2-uefi5.png) <br><br>
6. 选择要在 Surface Hub 2 秒上激活或停用的组件和设置。<br>
![* 选择要激活或停用的组件和设置 *](images/sh2-uefi6.png) <br><br>
7. 使用 USB 选项导出文件。<br>
![* 使用 USB 选项导出文件 *](images/sh2-uefi8.png) <br><br>
8. 插入并选择要用于此程序包的 USB 驱动器。 将设置 USB 驱动器的格式，并丢失您所拥有的任何信息。<br>
![* 插入并选择软件包的 USB 驱动器 *](images/sh2-uefi9.png) <br><br>
9. 成功创建程序包后，配置器将显示你的证书指纹的最后两个字符。 当你将配置导入到 Surface Hub 2 的配置时，你需要这些字符。<br>
![* 程序包的成功配置 *](images/sh2-uefi10.png) <br>

##  <a name="to-boot-into-uefi"></a>启动到 UEFI

关闭 Surface Hub 2。 长按**音量**按钮并按**电源**按钮。 一直按住音量按钮，直到 UEFI 菜单出现。

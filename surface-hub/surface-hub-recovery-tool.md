---
title: 使用 Surface Hub 恢复工具
description: 如何使用 Surface Hub 恢复工具重新镜像 SSD。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832168"
---
# 使用 Surface Hub 恢复工具

[Microsoft Surface Hub 恢复工具](https://www.microsoft.com/download/details.aspx?id=52210)可帮助你使用 Windows 10 桌面设备重新镜像 Surface Hub 固态驱动器（SSD），而无需调用支持或更换 SSD。 使用此工具，你可以重置具有未知管理员密码、启动错误、无法完成云恢复的 SSD，或者重置具有较早版本的操作系统的设备的映像。 该工具不会修复物理损坏的 SSDs。

要使用恢复工具重新镜像 Surface Hub SSD，你需要从 Surface Hub 中删除 SSD，将驱动器连接到 USB 至 SATA 电缆，然后将电缆连接到安装了恢复工具的桌面电脑。 有关如何从 Surface Hub 中删除现有驱动器的详细信息，请参阅[Surface HUB SSD 替换](surface-hub-ssd-replacement.md)。

> [!IMPORTANT]
> 不要让设备进入睡眠状态或中断图像文件的下载。

如果该工具在重新映像驱动器中未成功，请联系[Surface Hub 支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。

## 必备条件

### Mandatory

- 运行64位版本的 Windows 10、版本1607或更高版本的主机电脑。
- Internet 访问权限
- 打开 USB 2.0 或更高端口
- USB 至 SATA 电缆
- 主计算机上有 10 GB 的可用磁盘空间
- SSDs 附带 Surface Hub 或 SSD 提供的支持作为替代。 不支持 Microsoft 提供的 SSDs。

### 推荐

- 高速互联网连接
- 打开 USB 3.0 端口
- USB 3.0 或更高版本的 USB 至 SATA 电缆
- 已通过以下电缆和型号对图像处理工具进行了测试：
    - Startech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## 下载 Surface Hub 恢复工具

Surface Hub 恢复工具可从[Surface Hub 工具](https://www.microsoft.com/download/details.aspx?id=52210)下载，在文件名**SurfaceHub_Recovery_v1.14.137.0.msi**下。

若要开始下载，请单击 "**下载**"，从列表中选择 " **SurfaceHub_Recovery_v1.14.137.0.msi** "，然后单击 "**下一步**"。 从弹出窗口中，选择下列操作之一：

- 单击 "**运行**" 立即开始安装。
- 单击 "**保存**" 将下载内容复制到计算机以供以后安装。

在主机 PC 上安装 Surface Hub 恢复工具。

## 运行 Surface Hub 恢复工具

1. 在主机 PC 上，选择 "**开始**" 按钮，滚动到左侧的 "按字母顺序" 列表，然后选择 "恢复工具" 快捷方式。

    ![Microsoft Surface Hub 恢复工具快捷方式](images/shrt-shortcut.png)

2. 单击**开始**。

    ![恢复工具 "开始" 按钮](images/shrt-start.png)

3. 在 "**指南**" 窗口中，单击 "**下一步**"。

    ![不要让计算机转到睡眠指南](images/shrt-guidance.png)

4. 单击 **"是"** 下载图像。 下载恢复映像的时间取决于互联网连接速度。 在一般的企业连接中，下载8GB 图像文件最多可能需要一个小时。

    ![下载图像？](images/shrt-download.png)

5. 下载完成后，该工具指示你连接 SSD 驱动器。 如果该工具无法找到连接的驱动器，则很有可能是使用电缆时不报告 SSD 的名称到 Windows。  图像处理工具必须找到驱动器的名称，就像 "LITEON L CH-128V2S USB 设备"，然后它才能继续。  有关如何从 Surface Hub 中删除现有驱动器的详细信息，请参阅[Surface HUB SSD 替换](surface-hub-ssd-replacement.md)。

    ![连接 SSD](images/shrt-drive.png)

6. 识别驱动器时，单击 "**开始**" 以开始重新映像过程。 当出现有关将擦除驱动器上的所有数据的警告时，单击 **"确定"**。

    ![开始重新映像 SSD](images/shrt-drive-start.png)

    在将系统映像应用到驱动器之前，将对 SSD 进行重新分区和格式化。 复制系统二进制文件大约需要30分钟，但可能需要较长时间，具体取决于 USB 总线的速度、所使用的电缆或系统上安装的防病毒软件。

    ![复制完成](images/shrt-done.png)

    ![映像完成](images/shrt-complete.png)

## 疑难解答和常见问题

问题 | 注释
--- | ---
该工具无法映像 SSD | 确保使用工厂提供的 SSD 和已测试的电缆之一。
映像进程显示已暂停/已冻结 | 可安全关闭并重新启动 Surface Hub 恢复工具，对 SSD 不产生任何影响。
该工具无法识别该驱动器 | 验证 Surface Hub SSD 是否被枚举为一个精简的驱动器，"LITEON L CH-128V2S USB 设备"。  如果驱动器被识别为另一个已命名的设备，则当前电缆不兼容。 尝试其他电缆或上面列出的已测试电缆之一。
错误：-2147024809 | 打开磁盘管理器并删除 Surface Hub 驱动器上的分区。  断开连接并将驱动器重新连接到主计算机。 重新启动图像处理工具。

如果该工具在重新映像驱动器中未成功，请联系[Surface Hub 支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。

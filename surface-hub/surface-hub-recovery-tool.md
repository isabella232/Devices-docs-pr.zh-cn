---
title: 使用 Surface Hub 恢复工具
description: 如何使用 Surface Hub 恢复工具对 SSD 进行重新映像。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: f472d42bba9270b117cfa8cb9b54eaeb020aefc4
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910977"
---
# <a name="using-the-surface-hub-recovery-tool"></a>使用 Surface Hub 恢复工具

Microsoft Surface Hub[恢复](https://www.microsoft.com/download/details.aspx?id=52210)工具可帮助你使用 Windows 10 桌面设备重新映像 Surface Hub 固态硬盘 (SSD) ，而无需调用支持或更换 SSD。 使用此工具，你可以为具有未知管理员密码、启动错误、无法完成云恢复的 SSD 或具有较旧版本操作系统的设备重置映像。 该工具不会修复物理损坏的 SSD。

若要使用恢复工具重新映像 Surface Hub SSD，需要从 Surface Hub 中删除 SSD，将驱动器连接到 USB 到 SATA 电缆，然后将电缆连接到安装了恢复工具的台式电脑。 若要详细了解如何从驱动器中删除现有驱动器Surface Hub，请参阅Surface Hub [SSD 替换](surface-hub-ssd-replacement.md)。

> [!IMPORTANT]
> 请勿让设备进入睡眠状态或中断映像文件的下载。

If the tool is unsuccessful in reimaging your drive， please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## <a name="prerequisites"></a>系统必备

### <a name="mandatory"></a>Mandatory

- 运行 64 位版本 Windows 10版本 1607 或更高版本的主机电脑。
- Internet 访问权限
- 打开 USB 2.0 或更大端口
- USB 到 SATA 电缆
- 主计算机上 10 GB 的可用磁盘空间
- 由支持提供Surface Hub或 SSD 作为替代提供的 SSD 附带的 SSD。 不支持 Microsoft 未提供的 SSD。

### <a name="recommended"></a>推荐

- 高速 Internet 连接
- 打开 USB 3.0 端口
- USB 3.0 或更高版本 USB 到 SATA 电缆
- 已使用以下电缆型号和型号测试了映像工具：
    - Startech USB312SAT3CB
    - ））Will RCUC16001
    - Ugreen 20231

## <a name="download-surface-hub-recovery-tool"></a>下载 Surface Hub 恢复工具

Surface Hub恢复工具可从 it Surface Hub[工具](https://www.microsoft.com/download/details.aspx?id=52210)的文件名**下下载**SurfaceHub_Recovery_v2.7.139.0.msi。

> [!IMPORTANT]
> 此版本于 2021 年 2 月 11 日发布，取代了不再正常工作的早期版本。 如果之前已下载此工具，请将其卸载并安装当前版本。

若要开始下载，请单击"**下载**"，**从SurfaceHub_Recovery_v2.7.139.0.msi**选择"下载"，然后单击"下一**步"。** 从弹出窗口中，选择下列选项之一：

- 单击 **"运行** "以立即开始安装。
- 单击 **"** 保存"将下载复制到计算机，以稍后安装。

在Surface Hub计算机上安装恢复工具。

## <a name="run-surface-hub-recovery-tool"></a>运行 Surface Hub 恢复工具

1. 在主机电脑上 **，选择"** 开始"按钮，滚动左侧按字母顺序排列的列表，然后选择恢复工具快捷方式。

    ![Microsoft Surface Hub恢复工具快捷方式。](images/shrt-shortcut.png)

2. 单击**开始**。

    ![恢复工具"开始"按钮。](images/shrt-start.png)


3. 在"指南 **"窗口中**，单击"下一**步"。**

    ![不要让你的计算机转到睡眠指南。](images/shrt-guidance.png)

4. 在"选择图像"窗口中，单击**RS2**或后续**20H2，****选择"继续**"，然后选择"**下载图像"。**

     ![恢复工具 选择映像。](images/shrt-select-image.png)
    ![恢复工具下载映像。](images/shrt-download-image.png)

5. 下载恢复映像的时间取决于 Internet 连接速度。 在一般的公司连接中，可能需要一小时才能下载 8GB 图像文件。

    ![正在下载图像。](images/shrt-download.png)



5. 下载完成后，该工具会指示你连接 SSD 驱动器。 如果该工具无法找到连接的驱动器，则很有可能所使用的电缆未向系统报告 SSD Windows。  映像工具必须找到驱动器名称"LITEON L CH-128V2S USB 设备"，然后才能继续。  若要详细了解如何从驱动器中删除现有驱动器Surface Hub，请参阅Surface Hub [SSD 替换](surface-hub-ssd-replacement.md)。

    ![连接SSD。](images/shrt-drive.png)

6. 识别驱动器后，单击" **开始** "开始重新映像处理。 On the warning that all data on the drive will be erased， click **OK**.



    在将系统映像应用到驱动器之前，将重新分区 SSD 并设置其格式。 复制系统二进制文件大约需要 30 分钟，但可能需要更长时间，具体取决于 USB 总线的速度、使用的电缆或系统上安装的防病毒软件。



## <a name="troubleshooting-and-common-problems"></a>疑难解答和常见问题

问题 | 注释
--- | ---
该工具无法映像 SSD | 确保使用的是出厂提供的 SSD 和一条经过测试的电缆。
重新映像处理似乎已停止/冻结 | 安全地关闭并重新启动 Surface Hub 恢复工具，对 SSD 没有不良影响。
工具无法识别驱动器 | 确认将 Surface Hub SSD 枚举为Lite-On驱动器"LITEON L CH-128V2S USB 设备"。  如果驱动器被识别为另一个命名设备，则当前电缆不兼容。 请尝试其他电缆或上面列出的测试电缆之一。
错误：-2147024809 | 打开磁盘管理器并删除磁盘驱动器上的Surface Hub分区。  断开驱动器连接，并重新连接到主机。 再次重新启动映像工具。

If the tool is unsuccessful in reimaging your drive， please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## <a name="version-history"></a>版本历史记录


### <a name="version-v271390"></a>版本 v2.7.139.0

*发布日期：2021 年 2 月 11 日*<br>
此版本的 Surface Hub 恢复工具增加了对以下内容的支持：

- 安全更新


### <a name="version-v201390"></a>版本 v2.0.139.0

> [!IMPORTANT]
> 此版本不再可用。 请下载上面列出的当前版本。 

*发布日期：2020 年 12 月 18 日*<br>
此版本的 Surface Hub 恢复工具增加了对以下内容的支持：
- 更新以支持 Windows 10 协同版 2020 Update (20H2) 
- 用户体验改进
- 体系结构更改
- 遥测新增功能


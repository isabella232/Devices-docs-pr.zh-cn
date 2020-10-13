---
title: Microsoft Surface Data Eraser (Surface)
description: 了解 Microsoft Surface Data Eraser 工具如何帮助你安全擦除 Surface 设备中的数据。
ms.assetid: 8DD3F9FE-5458-4467-BE26-E9200341CF10
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: 工具, USB, 数据, 擦除
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
audience: itpro
ms.date: 10/12/2020
ms.openlocfilehash: 8b201ce45533c28740a7c6bdfcb56688ada25718
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114700"
---
# Microsoft Surface Data Eraser


了解 Microsoft Surface Data Eraser 工具如何帮助你安全擦除 Surface 设备中的数据。

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) 是一种从 U 盘启动的工具，支持安全擦除可兼容 Surface 设备中的全部数据。 Microsoft Surface Data Eraser U 盘只需具备从 USB 启动的功能即可。 该 USB 盘可通过使用提供的向导（即 Microsoft Surface Data Eraser 包装器）轻松创建，并且易于与简单的图形界面结合使用，无需任何命令行。 若要了解有关 Surface 服务流程中 Microsoft 使用的数据擦除功能和做法的详细信息，请参阅[将 Surface 送修时保护你的数据](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy)。

>[!IMPORTANT]
>Microsoft Surface Data Eraser 使用 NVM Express (NVMe) 格式命令擦除数据，如 [NIST 特别出版物 800-88 修订版 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) 中所授权。 

兼容的 Surface 设备包括：

- Surface Book (所有版本) 
- 表面转 (所有版本) 
- Surface Pro X (所有版本) 
- Surface 膝上型电脑 (所有版本) 
- Surface 膝上型电脑 Go
- Surface Studio (所有版本) 
- Surface Pro 2 及更高版本
- Surface Hub 2 上的 Windows 10 专业版和企业版

Microsoft Surface Data Eraser 在以下情况中可能有所帮助：

-   准备要进行送修的 Surface 设备

-   停止使用企业或组织不再使用的 Surface 设备

-   使 Surface 设备供新部门或新用户使用

-   对使用敏感数据的设备执行重置映像时的标准做法

>[!NOTE]
>第三方设备、运行 Windows RT 的 Surface 设备（包括 Surface 和 Surface 2）和 Surface Pro 与 Microsoft Surface Data Eraser 不兼容。

>[!NOTE]
>由于运行 Microsoft Surface Data Eraser 需要能够启动到 USB，因此，如果设备未配置为从 USB 启动，或者设备无法成功启动或 POST，Microsoft Surface Data Eraser 工具将不起作用。

>[!NOTE]
>Surface Studio 和 Surface 2 上的 surface Data 橡皮擦最多可能需要6分钟的时间来启动到 WinPE，然后才能进行磁盘擦除。


## 如何创建 Microsoft Surface Data Eraser U 盘


若要创建 Microsoft Surface Data Eraser U 盘，首先要安装 Microsoft Surface Data Eraser 安装程序工具（可使用本文开头提供的链接，从 Microsoft 下载中心获取该工具）。 *创建* U 盘不需要使用 Surface 设备。 在将安装文件下载到计算机后，请按照以下步骤来安装 Microsoft Surface Data Eraser 创建工具：

1.  运行从 [Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=46703)下载的 DataEraserSetup.msi 安装文件。

2.  选中指示接受许可协议条款的复选框，然后单击**安装**。

3.  单击**完成**关闭 Microsoft Surface Data Eraser 安装程序窗口。

在创建工具安装完成后，请按照以下步骤创建 Microsoft Surface Data Eraser U 盘。 在开始这些步骤之前，请确保已将 U 盘 3.0（至少 4 GB）连接到计算机。

1. 从“开始”菜单或“开始”屏幕启动 Microsoft Surface Data Eraser。

2. 单击**生成**，开始 Microsoft Surface Data Eraser USB 创建过程。 

3. 单击**开始**，确认你已连接 U 盘（至少 4 GB），如图 1 所示。

   ![启动 Microsoft Surface Data Eraser 工具](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *图 1. 启动 Microsoft Surface Data Eraser 工具*
4.  从 "**体系结构选择**" 页面中为 Surface Pro X 的大多数 surface 设备或**ARM64**选择 " **x64** "，如图2所示。 选择**继续**。

    ![体系结构选择](images/dataeraser-arch.png "Architecture Selection")<br>
       *图 2. 选择设备体系结构*
    

4. 从 " **Usb 拇指驱动器选择** " 页面中选择所选的 usb 驱动器（如图3所示），然后单击 " **开始** " 以开始 usb 创建过程。 所选的驱动器会进行格式化，此驱动器上的任何现有数据都将丢失。

   >[!NOTE]
   >如果禁用了“开始”按钮，请检查可移动驱动器的总容量是否至少有 4 GB。
  
   ![U 盘选择](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *图 3. U 盘选择*

5. 创建过程完成后，U 盘已进行格式化，并且所有二进制文件都会复制到该 U 盘中。 单击**成功**。

6. 当**恭喜**屏幕显示时，即可弹出并移除该 U 盘。 该 U 盘现在随时可以插入一台 Surface 设备中、从中进行启动，然后擦除该设备上的所有数据。 单击 " **完成** " 以完成 USB 创建过程，如图4所示。

   ![Surface Data Eraser USB 创建过程](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *图 4. 完成 Microsoft Surface Data Eraser USB 创建过程*

7. 单击 **X** 关闭 Microsoft Surface Data Eraser。

## 如何使用 Microsoft Surface Data Eraser U 盘


创建 Microsoft Surface Data Eraser U 盘后，你可以按照以下过程从该 U 盘启动受支持的 Surface 设备：

1. 将可启动 Microsoft Surface Data Eraser U 盘插入受支持的 Surface 设备。

2. 从 Microsoft Surface Data Eraser U 盘启动 Surface 设备。 若要从 U 盘启动设备，请按照以下步骤执行：

   a. 关闭 Surface 设备。

   b. 长按**调低音量**按钮。

   c. 按下并释放**电源**按钮。

   d. 释放**调低音量**按钮。
    
   >[!NOTE]
   >如果设备使用这些步骤未能启动到 USB，则可能需要在 Surface UEFI 中打开 **Enable Alternate Boot Sequence**。 可以在[管理 Surface UEFI 设置](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)中阅读有关 Surface UEFI 启动配置的详细信息。

3. 当 Surface 设备启动时，将显示一个 **SoftwareLicenseTerms** 文本文件，如图5所示。

   ![启动 Microsoft Surface Data Eraser U 盘](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *图 5. 启动 Microsoft Surface Data Eraser U 盘*

4. 请阅读软件许可条款，然后关闭该记事本文件。

5. 通过输入**接受**或**拒绝**，可接受或拒绝该软件许可条款。 必须接受该许可条款才能继续。

6. Microsoft Surface Data Eraser 脚本会检测 Surface 设备中存在的存储设备，并显示本机存储设备的详细信息。 若要继续操作，请按 **Y**（此操作运行 Microsoft Surface Data Eraser 并从存储设备中删除所有数据），或按 **N**（此操作关闭设备而不删除数据）。

   >[!NOTE]
   >Microsoft Surface Data Eraser 工具会以安全且无法恢复的方式删除所有数据（包括启动设备所需的 Windows 操作系统文件）。 若要启动已使用 Microsoft Surface Data Eraser 擦除的 Surface 设备，首先需要重新安装 Windows 操作系统。 若要从 Surface 设备中删除数据而不删除 Windows 操作系统，可以使用**初始化电脑**功能。 但是，这不会阻止使用取证或数据恢复功能恢复数据。 有关详细信息，请参阅 [Windows 10 中的恢复选项](https://support.microsoft.com/help/12415/windows-10-recovery-options)。

   ![显示要擦除的分区](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *图 6. Microsoft Surface Data Eraser 中显示了要擦除的分区*

7. 如果你在步骤 6 中按了**Y**，由于数据擦除过程的破坏性，会显示另一个对话框供你确认选择。

8. 单击**是**按钮以继续擦除 Surface 设备上的数据。

   >[!NOTE]
   >在 Surface Data Eraser U 盘上运行 Surface Data Eraser 时，**SurfaceDataEraserLogs** 文件夹内会生成日志文件。

## 更改和更新

Microsoft 会定期更新 Microsoft Surface Data Eraser。 有关每个新版本中提供的更改的信息，请参阅以下各项：

### 3.33.139
*发布日期：2020年9月9日*

此版本的 Surface Data 橡皮擦包括错误修复和添加对以下内容的支持： 

- 体系结构重新设计，以减少更新新产品版本的需要
- 适用于新工具更新的通知
- 遥测添加
- Surface Hub 2 上的 Windows 10 专业版和企业版


### 3.30.139
*发布日期：11月11日2020*

此版本的 Surface Data 橡皮擦添加了对以下内容的支持： 
- Surface Book 3
- Surface Go 2
- 新的 SSD Surface Go

### 3.28.137
*发布日期：11月11日 2019* 此版本的 Surface Data 橡皮擦：

- 包括 bug 修复

### 版本3.21.137
*发布日期：2019年10月 21* 日此版本的 Surface Data 橡皮擦是针对 x86 编译的，并添加了对以下设备的支持：

- 支持 Surface Pro 7、Surface Pro X 和 Surface 笔记本电脑3

### 版本3.2.78。0
*发布日期：2018年12月4日*

此版本的 Surface Data 橡皮擦：

- 包括 bug 修复


### 版本3.2.75。0
*发布日期：2018年11月12日*

此版本的 Surface Data 橡皮擦：

- 将支持添加到 Surface Studio 2
- 修复了 SD 卡的问题

### 版本3.2.69。0
*发布日期：2018年10月12日*

此版本的 Surface Data 橡皮擦添加了对以下项的支持：

- Surface Pro 6
- Surface Laptop 2

### 版本3.2.68。0
此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- Surface Go


### 版本3.2.58。0
此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- 适用于 Surface Pro 和 Surface 笔记本电脑设备 (驱动器) 的其他存储设备


### 版本 3.2.46.0
此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- 带有 LTE Advanced 的 Surface Pro


### 版本 3.2.45.0

此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- Surface Book 2

- Surface Pro 1TB

   >[!NOTE]
   >Surface Data Eraser v3.2.45.0 及更高版本可以用来在以下情况下恢复带有 1TB 存储选项的 Surface Pro 或 Surface Laptop 设备：设备在尝试部署或安装 Windows 10 时显示两个独立的 512GB 卷或遇到错误。 请参阅 [Surface Pro 型号 1796 和 Surface Laptop 1TB 显示两个驱动器](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives)了解详细信息。


### 版本 3.2.36.0

此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- Surface Pro

- Surface Laptop

>[!NOTE]
>Microsoft Surface Data Eraser U 盘创建工具无法在 Windows 10 S 上运行。若要擦除运行 Windows 10 S 的 Surface Laptop，必须首先在具有 Windows 10 专业版或 Windows 10 企业版的另一台计算机上创建 Microsoft Surface Data Eraser U 盘。

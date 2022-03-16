---
title: Microsoft Surface Data Eraser (Surface)
description: Microsoft Surface Data Eraser 工具允许你安全地擦除 Surface 设备的数据。
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
ms.date: 10/06/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e40c967003fc6dd40725e5015c01497eb3fa141a
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449645"
---
# <a name="microsoft-surface-data-eraser"></a>Microsoft Surface Data Eraser

了解 Microsoft Surface Data Eraser 工具如何帮助你安全擦除 Surface 设备中的数据。

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) 是一种从 U 盘启动的工具，支持安全擦除可兼容 Surface 设备中的全部数据。 Microsoft Surface Data Eraser U 盘只需具备从 USB 启动的功能即可。 若要了解有关 Surface 服务流程中 Microsoft 使用的数据擦除功能和做法的详细信息，请参阅[将 Surface 送修时保护你的数据](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy)。

>[!IMPORTANT]
>Microsoft Surface Data Eraser 使用 NVM Express (NVMe) 格式命令擦除数据，如 [NIST 特别出版物 800-88 修订版 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) 中所授权。

兼容的 Surface 设备包括：

- Surface Laptop Studio
- Surface Book (所有版本) 
- Surface Go (所有版本) 
- Surface Pro X (所有版本) 
- Surface Laptop (所有版本) 
- Surface Laptop Go
- Surface Studio (所有版本) 
- Surface Pro 2 及更高版本
- Surface 3
- Windows 10 专业版 2 Enterprise上的 Surface Hub 和

Microsoft Surface Data Eraser 在以下情况中可能有所帮助：

- 准备要发送进行修复的 Surface 设备。
- 停用公司或组织使用的 Surface 设备。
- 将 Surface 设备重新用于新用户。
- 为包含敏感数据的设备重新映像。

## <a name="how-to-create-a-microsoft-surface-data-eraser-usb-stick"></a>如何创建 Microsoft Surface Data Eraser U 盘

在创建工具安装完成后，请按照以下步骤创建 Microsoft Surface Data Eraser U 盘。 在开始这些步骤之前，请确保已将 U 盘 3.0（至少 4 GB）连接到计算机。

1. 运行DataEraserSetup.msi从 Microsoft 下载中心下载的安装 [文件](https://www.microsoft.com/download/details.aspx?id=46703)。

2. 选择 **"生成** "开始 Microsoft Surface Data Eraser USB 创建过程，如图 1 所示。

   :::image type="content" source="images/microsoft-surface-data-eraser/fig1-build.png" alt-text="图 1. 开始 Microsoft Surface Data Eraser 工具":::<br>
  *图 1. 开始 Microsoft Surface Data Eraser 工具*

3. 选择 **"** 继续"确认你已连接至少 4GB 的 U 盘，如图 2 所示。
   
   :::image type="content" source="images/microsoft-surface-data-eraser/fig2-continue.png" alt-text="图 2. 确认已连接至少 4GB 的 USB 驱动器":::<br>
   *图 2. 确认已连接至少 4GB 的 USB 驱动器*

4. 对于 **2021 (设备仅选择 x64 (**（对于 2021 或更高版本的设备) 请选择 **"x64**"，从"体系结构选择"页面选择"适用于 2020 和较旧的设备的 **x64**"或"适用于 Surface Pro X 的 ARM64"，如图 3 所示。**** 选择**继续**。

   :::image type="content" source="images/microsoft-surface-data-eraser/fig3-select.png" alt-text="图 3. 选择设备体系结构":::

5. 从"USB U 盘选择"页中选择**** 你选择的 U 盘，如图 4 所示，然后选择"开始"开始 USB **** 创建过程。 所选的驱动器会进行格式化，此驱动器上的任何现有数据都将丢失。

   :::image type="content" source="images/microsoft-surface-data-eraser/fig4-start.png" alt-text="图 4. U 盘选择>":::<br>
   *图 4. U 盘选择*

  >[!TIP]
   >如果禁用了“开始”按钮，请检查可移动驱动器的总容量是否至少有 4 GB。

6. 创建过程完成后，U 盘已进行格式化，并且所有二进制文件都会复制到该 U 盘中。 选择 **"成功"**。

7. 当**恭喜**屏幕显示时，即可弹出并移除该 U 盘。 该 U 盘现在随时可以插入一台 Surface 设备中、从中进行启动，然后擦除该设备上的所有数据。 选择 **"** 完成"以完成 USB 创建过程，如图 5 所示。

   :::image type="content" source="images/microsoft-surface-data-eraser/fig5-complete.png" alt-text="完成 Microsoft Surface Data Eraser 工具":::<br>
   *图 5. 完成 Microsoft Surface Data Eraser USB 创建过程*

8. 选择 **X** 关闭 Microsoft Surface Data Eraser。

## <a name="how-to-use-a-microsoft-surface-data-eraser-usb-stick"></a>如何使用 Microsoft Surface Data Eraser U 盘

创建 Microsoft Surface Data Eraser U 盘后，你可以按照以下过程从该 U 盘启动受支持的 Surface 设备：

>[!NOTE]
>surface Data Eraser on Surface Studio and Surface Studio 2 can take up to 6 minutes to boot into WinPE before disk erases occur.

1. 将可启动 Microsoft Surface Data Eraser U 盘插入受支持的 Surface 设备。

2. 从 Microsoft Surface Data Eraser U 盘启动 Surface 设备。 若要从 U 盘启动设备，请按照以下步骤执行：

   a. 关闭 Surface 设备。
   b. 长按**调低音量**按钮。
   c. 按下并释放**电源**按钮。
   d. 释放**调低音量**按钮。

   >[!TIP]
   >如果设备使用这些步骤未能启动到 USB，则可能需要在 Surface UEFI 中打开 **Enable Alternate Boot Sequence**。 可以在[管理 Surface UEFI 设置](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)中阅读有关 Surface UEFI 启动配置的详细信息。

3. 当 Surface 设备启动时， **将显示 SoftwareLicenseTerms** 文本文件，如图 5 所示。

   ![启动 Microsoft Surface Data Eraser U 盘。](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *图 5. 启动 Microsoft Surface Data Eraser U 盘*

4. 请阅读软件许可条款，然后关闭该记事本文件。

5. 通过输入**接受**或**拒绝**，可接受或拒绝该软件许可条款。 必须接受该许可条款才能继续。

6. Microsoft Surface Data Eraser 脚本会检测 Surface 设备中存在的存储设备，并显示本机存储设备的详细信息。 若要继续操作，请按 **Y**（此操作运行 Microsoft Surface Data Eraser 并从存储设备中删除所有数据），或按 **N**（此操作关闭设备而不删除数据）。

   >[!CAUTION]
   >Microsoft Surface Data Eraser 工具会以安全且无法恢复的方式删除所有数据（包括启动设备所需的 Windows 操作系统文件）。 若要启动已使用 Microsoft Surface Data Eraser 擦除的 Surface 设备，首先需要重新安装 Windows 操作系统。 若要从 Surface 设备中删除数据而不删除 Windows 操作系统，可以使用**初始化电脑**功能。 但是，这不会阻止使用取证或数据恢复功能恢复数据。 有关详细信息，请参阅 [Windows 10 中的恢复选项](https://support.microsoft.com/help/12415/windows-10-recovery-options)。

   ![将显示要擦除的分区。](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *图 6. Microsoft Surface Data Eraser 中显示了要擦除的分区*

7. 如果你在步骤 6 中按了**Y**，由于数据擦除过程的破坏性，会显示另一个对话框供你确认选择。

8. 选择 **"** 是"以在 Surface 设备上继续擦除数据。

   >[!TIP]
   >在 Surface Data Eraser U 盘上运行 Surface Data Eraser 时，**SurfaceDataEraserLogs** 文件夹内会生成日志文件。

## <a name="changes-and-updates"></a>更改和更新

Microsoft 会定期更新 Microsoft Surface Data Eraser。 有关每个新版本中提供的更改的信息，请参阅以下各项：

### <a name="3421390"></a>3.42.139.0

*发布日期：2021 年 10 月 5 日*

此版本的 Surface Data Eraser 包括：

- 适用于 2021 的单独选项和支持较新的设备，包括 Surface Laptop Studio、Surface Pro 8 和 Surface Go 3。

### <a name="3391390"></a>3.39.139.0

*发布日期：2021 年 4 月 13 日*

此版本的 Surface Data Eraser 包括：

- 支持 Surface Laptop 4

### <a name="2341390"></a>2.34.139.0

*发布日期：2021 年 1 月 15 日*

此版本的 Surface Data Eraser：

- 包括 Bug 修复

### <a name="333139"></a>3.33.139

*发布日期：2020 年 9 月 9 日*

此版本的 Surface Data Eraser 包含 Bug 修复，并添加了对以下功能的支持：

- 体系结构重新设计，以减少使用新产品版本更新需求
- 可用于新工具更新的通知
- 遥测新增功能
- Windows 10 专业版 2 Enterprise上的 Surface Hub 和

### <a name="330139"></a>3.30.139

*发布日期：2020 年 5 月 11 日*

此版本的 Surface Data Eraser 增加了对以下功能的支持：

- Surface Book 3
- Surface Go 2
- Surface Go 中的新 SSD

### <a name="328137"></a>3.28.137

*发布日期：2019 年 11 月 11 日*

此版本的 Surface Data Eraser：

- 包括 Bug 修复

### <a name="version-321137"></a>版本 3.21.137

*发布日期：2019 年 10 月 21 日*

此版本的 Surface Data Eraser 针对 x86 编译，并添加了对以下设备的支持：

- Surface Pro 7、Surface Pro X 和 Surface Laptop 3

### <a name="version-32780"></a>版本 3.2.78.0

*发布日期：2018 年 12 月 4 日*

此版本的 Surface Data Eraser：

- 包括 Bug 修复

### <a name="version-32750"></a>版本 3.2.75.0

*发布日期：2018 年 11 月 12 日*

此版本的 Surface Data Eraser：

- 向 Surface Studio 2 添加支持
- 修复了 SD 卡的问题

### <a name="version-32690"></a>版本 3.2.69.0

*发布日期：2018 年 10 月 12 日*

此版本的 Surface Data Eraser 增加了对以下内容的支持：

- Surface Pro 6
- Surface Laptop 2

### <a name="version-32680"></a>版本 3.2.68.0

此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- Surface Go

### <a name="version-32580"></a>版本 3.2.58.0

此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- 其他存储设备 (驱动器) Surface Pro Surface Laptop设备

### <a name="version-32460"></a>版本 3.2.46.0

此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- 带有 LTE Advanced 的 Surface Pro

### <a name="version-32450"></a>版本 3.2.45.0

此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- Surface Book 2
- Surface Pro 1TB

   >[!NOTE]
   >Surface Data Eraser v3.2.45.0 及更高版本可以用来在以下情况下恢复带有 1TB 存储选项的 Surface Pro 或 Surface Laptop 设备：设备在尝试部署或安装 Windows 10 时显示两个独立的 512GB 卷或遇到错误。 请参阅 [Surface Pro 型号 1796 和 Surface Laptop 1TB 显示两个驱动器](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives)了解详细信息。

### <a name="version-32360"></a>版本 3.2.36.0

此版本的 Microsoft Surface Data Eraser 添加了以下支持：

- Surface Pro
- Surface Laptop

>[!NOTE]
>Microsoft Surface Data Eraser USB 驱动器创建工具无法在 S Windows 10运行。若要擦除Surface Laptop S Windows 10，必须先在具有 Windows 10/11 Pro 或 Windows 10/11 Enterprise 的另一计算机上创建 Microsoft Surface Data Eraser U 盘。

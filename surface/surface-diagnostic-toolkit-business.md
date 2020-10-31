---
title: 部署适用于企业的 Surface 诊断工具包
description: 本主题介绍了如何使用面向企业的 Surface 诊断工具包。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 97d0a3d76cf9286ca946e08be9f605084084b2ba
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145957"
---
# 部署适用于企业的 Surface 诊断工具包

适用于 Business (SDT) 的 Microsoft Surface 诊断工具包使 IT 管理员能够快速调查和解决与 Surface 设备有关的硬件、软件和固件问题。 除了获取设备运行状况见解和解决问题的指南之外，还可以运行一系列诊断测试和软件修复。 

特别是，SDT for Business 使你能够：

- [自定义程序包。](#preparing-the-sdt-package-for-distribution)
- [使用命令运行应用。](surface-diagnostic-toolkit-command-line.md)
- [运行多个硬件测试以解决问题。](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [生成用于分析问题的日志。](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [获取与最佳配置比较设备和最佳配置的详细报告。](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## 主要方案和下载资源 

若要运行 SDT for Business，请下载下表中列出的组件。


模式 |  主要方案 | 下载 | 了解详细信息
--- | --- | --- | ---
桌面模式 |  帮助用户在其 Surface 设备上运行 SDT 以解决问题。<br>创建要在一个或多个 Surface 设备上部署的自定义程序包，以允许用户选择要收集和分析的特定日志。 | SDT 可分发 MSI 程序包：<br>适用于企业版安装程序的 Microsoft Surface 诊断工具包<br>[适合 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703) | [在桌面模式下使用 Surface 诊断工具包](surface-diagnostic-toolkit-desktop-mode.md)
命令行 |  使用标准工具（如配置管理器）无需用户交互即可直接对 Surface 设备进行故障排除。 它包括以下命令：<br>`-DataCollector` 收集所有日志文件<br>`-bpa` 使用最佳做法分析器运行运行状况诊断。<br>`-windowsupdate` 检查 Windows 更新中是否缺少固件或驱动程序更新。<br>`-warranty` 检查保修信息。 <br><br>| SDT 控制台应用：<br>Microsoft Surface 诊断应用程序控制台<br>[适合 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703) | [使用命令运行 Surface 诊断工具包](surface-diagnostic-toolkit-command-line.md)

## 支持的设备 

在 Surface 3 及更高版本的设备上支持 SDT for Business，包括：

- Surface 膝上型电脑 Go
- Surface Book 3
- Surface Go 2
- Surface Pro X
- Surface Pro 7
- Surface 笔记本电脑3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- 带有 LTE 的 Surface Go
- Surface Book 2
- 带有 LTE Advanced 的 Surface Pro（型号 1807）
- Surface Pro（型号 1796）
- Surface Laptop
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3

## 安装面向企业的 Surface 诊断工具包

若要创建可分发给组织中的用户的 SDT 程序包，请执行以下操作：

1. 使用管理员帐户登录 Surface 设备。
2. 从 " [Surface Tools FOR IT 下载" 页面](https://www.microsoft.com/download/details.aspx?id=46703) 下载 SDT Windows Installer 程序包 ( .msi) 并将其复制到 surface 设备（如桌面）上的首选位置。
3. 将显示 "SDT 设置" 向导，如图1所示。 单击“下一步”****。 

    >[!NOTE]
    >如果未显示 "设置向导"，请确保您已登录到您的计算机上的管理员帐户。 

    ![欢迎使用 Surface 诊断工具包设置向导](images/sdt-1.png)

    *图 1. 图面诊断工具包设置向导*

4. 当 "SDT 设置向导" 出现时，单击 " **下一步**"，接受《最终用户许可协议》 (EULA) 

5. 在 "安装选项" 屏幕上，根据需要更改默认安装位置。 
6. 在 "安装类型" 下，选择 " **高级**"。 

    >[!NOTE]
    >标准选项允许用户在其 Surface 设备上直接运行诊断工具，前提是他们已使用管理员帐户登录到其设备。 
    
     ![安装选项：高级](images/sdt-install.png)

7. 单击 " **下一步** "，然后单击 " **安装**"。 

## 使用命令行安装
如果需要，您可以在命令提示符处安装 SDT 并设置自定义标志以在管理员模式下安装该工具。 SDT 包含以下安装选项标志：

- `SENDTELEMETRY` 将遥测数据发送到 Microsoft。 标志接受 " `0` 已禁用" 或 " `1` 已启用"。 默认值是 `1` 发送遥测。
- `ADMINMODE` 配置要在管理员模式下安装的工具。 标志接受 `0` 客户端模式或 `1` IT 管理员模式。 默认值为 `0`。

### 要从命令行安装 SDT，请执行以下操作：

1. 打开命令提示符并输入：

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **示例：**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## 在 Surface 设备上找到 SDT

将安装 "SDT" 和 "SDT" 应用控制台 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 。

除了 .exe 文件之外，SDT 还会安装 JSON 文件和 admin.dll 文件 ( # A1) ，如图2所示。

![文件资源管理器中的 SDT 已安装文件的列表](images/sdt-2.png)

*图 2. 由 SDT 安装的文件*

## 准备用于分发的 SDT 程序包

创建自定义程序包使你可以将工具定位到特定的已知问题。

1. 单击 " **开始 > 运行**"，输入 " **表面** "，然后单击 " **面向企业的 surface 诊断工具包**"。 
2. 当工具打开时，单击 " **创建自定义程序包**"，如图3所示。

    ![创建自定义程序包选项](images/sdt-3.png)

    *图 3. 创建自定义程序包*

### 语言和遥测设置

  创建程序包时，你可以选择语言设置或选择不向 Microsoft 发送遥测信息。 默认情况下，SDT 会将遥测发送到用于根据 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)改进应用程序的 microsoft。 如果想要拒绝，请清除创建自定义程序包时的复选框，如下所示。 或清除 "**安装选项**" 页面上的 "将**遥测发送到 Microsoft** " 复选框（在 SDT 设置期间）。 

>[!NOTE]
>此设置不会影响运行需要 Internet 连接（如 Windows 更新和软件修复）或使用应用工具栏中的笑脸或 Frown 按钮提供反馈的测试和修复时，自动存储在 Microsoft 服务器上的最小遥测。 


![选择语言和遥测设置](images/sdt-4.png)

*图 4. 选择语言和遥测设置*


### Windows 更新页面

选择适用于你的组织的选项。 大多数具有多个用户的组织通常会选择通过 Windows Server Update Services (WSUS) 接收更新，如图5所示。 如果使用本地 Windows 更新程序包或 WSUS，请根据需要输入路径。 

![选择 "Windows 更新" 选项](images/sdt-5.png)

*图 5. Windows 更新选项*

### 软件修复页面

这允许你选择或删除运行软件修复更新的选项。 

![选择软件修复选项](images/sdt-6.png)

*图 6. 软件修复选项*

### 收集日志和保存程序包页面

你可以选择在应用程序、驱动程序、硬件和操作系统上运行各种日志。 单击相应的区域，然后从可用日志的菜单中进行选择。 然后，你可以将程序包保存到用户可以访问的软件分发点或等效位置。 

![选择日志选项](images/sdt-7.png)

*图 7. 日志选项和保存程序包*

## 后续步骤

- [在桌面模式下使用适用于企业的 Surface 诊断工具包](surface-diagnostic-toolkit-desktop-mode.md)
- [使用命令的面向企业的表面诊断工具包](surface-diagnostic-toolkit-command-line.md)

## 更改和更新

### 版本2.124.139。0

此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：

- 无缝集成支持
- 保存所有测试结果
- 检查图像是否已创建自定义
- 包括来自设备管理器的警告
- 插接固件版本
- 将驱动器标记为存储测试中的潜在故障
- 删除存储链接 

### 版本2.121.139
*发布日期： 31 2020 年7月*<br>
此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：

- 无缝支持体验
- Bug 修复

### 版本2.94.139。0
*发布日期： 2020 5 月11日*<br>
此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：

- 能够跳过 Windows 更新以执行硬件检查。
- 能够接收有关最新版本更新的通知
- Surface Go 2
- Surface Book 3
- 显示进度指示器


### 版本2.43.139。0
*发布日期：2019年10月21日*<br>
此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：

- Surface Pro 7
- Surface 笔记本电脑3

### 版本2.42.139。0
*发布日期：2019年9月24日*<br>
此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持： 
- 下载硬件报告的能力。
- 直接从工具联系 Microsoft 支持的能力。 <br>

### 版本2.41.139。0
*发布日期：2019年6月24日*<br>
此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持： 
- 日志和报告中包含的驱动程序版本信息。
- 提供有关应用的反馈的能力。<br>


### 版本2.36.139。0
*发布日期：2019年4月26日*<br>
此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持： 
- "高级设置" 选项，通过安装程序 UI 解锁管理员功能，无需命令行配置。
- 辅助功能改进。
- 日志中包含 Surface 亮度控制设置。
- 报表生成器中的外部监视器兼容性支持链接。

---
title: 部署适用于企业的 Surface 诊断工具包
description: 本主题介绍如何使用 Surface Diagnostic Toolkit for Business。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271576"
---
# 部署适用于企业的 Surface 诊断工具包

Microsoft Surface Diagnostic Toolkit for Business (SDT) 使 IT 管理员能够快速调查、排查并解决 Surface 设备的硬件、软件和固件问题。 除了获取设备运行状况见解和解决问题的指导外，还可以运行一系列诊断测试和软件修复。 

具体来说，SDT for Business 使您能够：

- [自定义程序包。](#preparing-the-sdt-package-for-distribution)
- [使用命令运行应用。](surface-diagnostic-toolkit-command-line.md)
- [运行多个硬件测试以解决问题。](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [生成用于分析问题的日志。](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [获取比较设备与最佳配置的详细报告。](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## 主要方案和下载资源 

若要运行 SDT for Business，请下载下表中列出的组件。


模式 |  主要方案 | 下载 | 了解详细信息
--- | --- | --- | ---
桌面模式 |  帮助用户在 Surface 设备上运行 SDT 以解决问题。<br>创建要部署在一个或多个 Surface 设备的自定义程序包，允许用户选择要收集和分析的特定日志。 | SDT 可分发的 MSI 程序包：<br>Microsoft Surface Diagnostic Toolkit for Business Installer<br>[适合 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703) | [在桌面Toolkit Surface Diagnostic Toolkit](surface-diagnostic-toolkit-desktop-mode.md)
命令行 |  使用标准工具（如 Configuration Manager）直接远程解决 Surface 设备问题，而无需用户交互。 它包含以下命令：<br>`-DataCollector` 收集所有日志文件<br>`-bpa` 使用最佳做法分析器运行运行状况诊断。<br>`-windowsupdate` 检查 Windows 更新中缺少固件或驱动程序更新。<br>`-warranty` 检查担保信息。 <br><br>| SDT 控制台应用：<br>Microsoft Surface Diagnostics 应用控制台<br>[适合 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703) | [使用命令运行 Surface 诊断Toolkit](surface-diagnostic-toolkit-command-line.md)

##  <a name="supported-devices"></a>支持的设备 

SDT for Business 在 Surface 3 和更高版本设备上受支持，包括：

- Surface Book - 所有代
- Surface Go - 所有代
- Surface Laptop - 所有代
- Surface Pro 3 及更高版本
- Surface Pro X - 所有代
- Surface Studio - 所有代
- Surface 3 LTE
- Surface 3


## 安装 Surface Diagnostic Toolkit for Business

若要创建可分发给组织中用户的 SDT 包：

1. 使用管理员帐户登录到 Surface 设备。
2. 从 Surface Tools for [IT](https://www.microsoft.com/download/details.aspx?id=46703) (.msi) 下载页面下载 SDT Windows Installer 程序包，并复制到 Surface 设备上的首选位置，如桌面。
3. 将显示 SDT 安装向导，如图 1 所示。 单击“下一步”****。 

    >[!NOTE]
    >如果未显示安装向导，请确保已登录到您计算机的管理员帐户。 

    ![欢迎使用 Surface Diagnostic Toolkit设置向导](images/sdt-1.png)

    *图 1. Surface 诊断Toolkit设置向导*

4. 当 SDT 安装向导出现时****，单击"下一步"，接受 EULA (最终用户许可协议) 

5. 如果需要，在"安装选项"屏幕上更改默认安装位置。 
6. 在"安装类型"下，选择 **"高级"。** 

    >[!NOTE]
    >标准选项允许用户直接在 Surface 设备上运行诊断工具，只要他们使用管理员帐户登录设备。 
    
     ![安装选项：高级](images/sdt-install.png)

7. 单击 **"** 下一步"，然后单击"**安装"。** 

## 使用命令行安装
如果需要，可以在命令提示符下安装 SDT，并设置自定义标志以在管理模式下安装该工具。 SDT 包含以下安装选项标志：

- `SENDTELEMETRY` 将遥测数据发送到 Microsoft。 标志接受 `0` 禁用或 `1` 启用。 默认值是 `1` 发送遥测。
- `ADMINMODE` 配置要以管理模式安装的工具。 该标志接受 `0` 客户端模式或 `1` IT 管理员模式。 默认值为 `0`。

### 若要从命令行安装 SDT：

1. 打开命令提示符并输入：

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **示例：**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## 在 Surface 设备上定位 SDT

SDT 和 SDT 应用控制台都安装在 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 。

除了 .exe 文件，SDT 还安装了 JSON 文件和 admin.dll 文件 (modules\admin.dll) ，如图 2 所示。

![文件资源管理器中已安装 SDT 文件的列表](images/sdt-2.png)

*图 2. 由 SDT 安装的文件*

## 准备 SDT 包进行分发

通过创建自定义程序包，你可以将工具定向到特定的已知问题。

1. Click **Start > Run，** enter **Surface** and then click Surface Diagnostic Toolkit **for Business.** 
2. 工具打开后，单击 **"创建自定义程序包**"，如图 3 所示。

    ![创建自定义程序包选项](images/sdt-3.png)

    *图 3. 创建自定义程序包*

### 语言和遥测设置

  创建程序包时，可以选择语言设置或选择不向 Microsoft 发送遥测信息。 默认情况下，SDT 根据 Microsoft 隐私声明向 Microsoft 发送用于改进应用程序的 [遥测](https://privacy.microsoft.com/privacystatement)。 如果希望拒绝，请在创建自定义程序包时清除该复选框，如下所示。 或者，在 SDT 安装期间清除"**** 安装选项"页上的"将遥测发送到**Microsoft"** 复选框。 

>[!NOTE]
>当运行需要 Internet 连接的测试和修复（如 Windows 更新和软件修复）时，或者使用应用工具栏中的"笑脸"或"小脸"按钮提供反馈时，此设置不会影响 Microsoft 服务器上自动存储的最少遥测。 


![选择语言和遥测设置](images/sdt-4.png)

*图 4. 选择语言和遥测设置*


### Windows 更新页

选择适合贵组织的选项。 具有多个用户的大多数组织通常会选择通过 Windows Server Update Services (WSUS) 接收更新，如图 5 所示。 如果使用本地 Windows 更新程序包或 WSUS，请根据情况输入路径。 

![选择 Windows 更新选项](images/sdt-5.png)

*图 5. Windows 更新选项*

### 软件修复页

这允许你选择或删除运行软件修复更新的选项。 

![选择软件修复选项](images/sdt-6.png)

*图 6. 软件修复选项*

### 收集日志并保存程序包页面

可以选择跨应用程序、驱动程序、硬件和操作系统运行各种日志。 单击相应的区域，然后从可用日志的菜单中选择。 然后，您可以将程序包保存到软件分发点或用户可以访问的等效位置。 

![选择日志选项](images/sdt-7.png)

*图 7. 日志选项和保存程序包*

##  <a name="next-steps"></a>后续步骤

- [在桌面模式下使用适用于企业的 Surface 诊断工具包](surface-diagnostic-toolkit-desktop-mode.md)
- [使用适用于Toolkit Surface Diagnostic Toolkit For Business](surface-diagnostic-toolkit-command-line.md)

##  <a name="changes-and-updates"></a>更改和更新

### 版本 2.131.139.0

此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：

- 支持 Surface Pro 7+
- Surface Pro X 上的无缝支持体验
- 安全改进
- 非独占用户体验改进

### 版本 2.124.139.0

此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：

- 无缝集成支持
- 保存所有测试结果
- 检查映像是否创建自定义
- 包括来自设备管理器的警告
- 扩展坞固件版本
- 将驱动器标为存储测试中的潜在故障
- 删除存储链接 

### 版本 2.121.139
*发布日期：2020 年 7 月 31 日*<br>
此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：

- 无缝支持体验
- Bug 修复

### 版本 2.94.139.0
*发布日期：2020 年 5 月 11 日*<br>
此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：

- 跳过 Windows 更新以执行硬件检查的能力。
- 能够接收有关最新版本更新的通知
- Surface Go 2
- Surface Book 3
- 显示进度指示器


### 版本 2.43.139.0
*发布日期：2019 年 10 月 21 日*<br>
此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：

- Surface Pro 7
- Surface Laptop 3

### 版本 2.42.139.0
*发布日期：2019 年 9 月 24 日*<br>
此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持： 
- 下载硬件报告的能力。
- 可以直接通过该工具联系 Microsoft 支持人员。 <br>

### 版本 2.41.139.0
*发布日期：2019 年 6 月 24 日*<br>
此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持： 
- 日志和报告中包含的驱动程序版本信息。
- 提供有关应用的反馈的能力。<br>


### 版本 2.36.139.0
*发布日期：2019 年 4 月 26 日*<br>
此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持： 
- 高级安装程序选项，用于通过安装程序 UI 解锁管理功能，而无需命令行配置。
- 辅助功能改进。
- 日志中包含的图面亮度控制设置。
- 报告生成器中的外部监视器兼容性支持链接。

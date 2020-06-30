---
title: Microsoft Surface Dock 固件更新-IT 管理员的技术信息
description: 本文介绍了如何使用 Microsoft Surface Dock 固件更新来更新 Surface Dock 固件。 当安装在 Surface 设备上时，它将更新连接到 Surface 设备的任何 Surface Dock。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: aab4c67a6a262b11cd5982ebe145afbddfeaa1c9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830770"
---
# Microsoft Surface Dock 固件更新：面向 IT 管理员的技术信息

> [!IMPORTANT]
> 本文包含适用于 IT 管理员的技术说明。 如果您是家庭用户，请参阅如何在 Microsoft 支持网站上[更新 Surface Dock 固件](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   。 支持网站上的说明与下面的常规安装步骤相同，但本文提供了有关监视、验证和将更新部署到网络上的多个设备的其他信息。

本文介绍了如何使用 Microsoft Surface Dock 固件更新来更新 Surface Dock 固件。 当安装在 Surface 设备上时，它将更新连接到 Surface 设备的任何 Surface Dock。 

此工具取代了以前的 Microsoft Surface Dock 更新工具，以前可将其作为 Surface 工具的一部分进行下载。 以前的工具被命名为 "Surface_Dock_Updater_vx.xx.xxx.x.msi" （其中 x 指示版本号），不再可供下载，不应使用。

## 安装 Surface Dock 固件更新

本部分介绍如何手动安装固件更新。

> [!NOTE]
> Microsoft 定期发布 Surface Dock 固件更新的新版本。 MSI 文件不是自我更新。 如果你已将 MSI 部署到 Surface 设备，并且新版本的固件已发布，你将需要部署新版本。

1. 下载并安装[Microsoft Surface Dock 固件更新](https://www.microsoft.com/download/details.aspx?id=46703)。
    - 更新需要运行 Windows 10 版本1803或更高版本的 Surface 设备。
    - 安装 MSI 文件可能会提示你重启 Surface。 但是，执行更新不需要重新启动。

2. 将 Surface 设备与 Surface Dock 断开连接（使用 power adapter），等待约5秒钟，然后重新连接。 Surface Dock 固件更新将在后台静默地更新坞站。 该过程可能需要几分钟才能完成，即使中断，也会继续。 

## 监视 Surface Dock 固件更新

本部分是可选的，概述了如何监视固件更新的安装。 

要监视更新，请执行以下操作：

1. 打开事件查看器，浏览到**Windows 日志 > 应用程序**，然后在右侧窗格中的 "**操作**" 下单击 "**筛选当前日志**"，在 "**事件源**" 旁边输入 " **SurfaceDockFwUpdate** "，然后单击 **"确定"**。

2. 在提升的命令提示符处键入以下命令：

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. 按照本文[下一节](#install-the-surface-dock-firmware-update)中的说明安装更新。
4. 事件2007和以下文本表示更新成功：**固件更新已完成。 hr = 0 DriverTelementry EventCode = 2007**。 
    - 如果更新不成功，则事件 ID 2007 将显示为**错误**事件，而不是**信息**。 此外，Windows 注册表中报告的版本将不是最新版本。
5. 更新完成后，Windows 注册表中将显示已更新的 DWORD 值，这些值对应于该工具的当前版本。 有关详细信息，请参阅本文中的[版本参考](#versions-reference)部分。 例如：
    - Component10CurrentFwVersion 0x04ac3970 （78395760）
    - Component20CurrentFwVersion 0x04915a70 （76634736）

>[!TIP]
>如果在事件文本中看到 "无法找到源 SurfaceDockFwUpdate 的事件 ID xxxx 的说明"，则这是预期的，可以忽略。

另请参阅本文中的以下部分： 
  - [如何验证固件更新已完成](#how-to-verify-completion-of-the-firmware-update)
  - [事件日志记录](#event-logging)
  - [疑难解答提示](#troubleshooting-tips)
  - [版本参考](#versions-reference)

## 网络部署

你可以使用 Windows Installer 命令（Msiexec.exe）将 Surface Dock 固件更新部署到网络上的多个设备。 使用 Microsoft 终结点配置管理器或其他部署工具时，请输入以下语法以确保安装静默：

- **Msiexec.exe/i \<path to msi file\> /quiet/norestart** 

  例如：
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > 默认情况下不创建日志文件。 为了创建日志文件，你需要追加 "/l*v [path]"。例如： Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI "

  有关详细信息，请参阅[命令行选项](https://docs.microsoft.com/windows/win32/msi/command-line-options)文档。

> [!IMPORTANT]
> 如果你想要使用任何其他方法更新 Surface Dock，请参阅[更新 Surface dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)以了解详细信息。

## Intune 部署

你可以使用 Intune 将 Surface Dock 固件更新分发到你的设备。 首先，你需要将 MSI 文件转换为 intunewin 格式，如以下文档中所述： [Intune 独立-Win32 应用管理](https://docs.microsoft.com/intune/apps/apps-win32-app-management)。

使用以下命令：
  - **msiexec/i \<path to msi file\> /quiet/q**

## 如何验证固件更新的完成

Surface dock 固件包含两个组件：

- **Component10：** 微型控制器单元（MCU）固件
- **Component20：** 显示端口（DP）固件。

成功完成 Surface Dock 固件更新会导致这些固件组件的新注册表项值。

**要验证更新，请执行以下操作：**

1. 打开注册表编辑器，然后导航到以下注册表路径：

    - **HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. 查找注册表项： **Component10CurrentFwVersion 和 Component20CurrentFwVersion**，它指的是当前在设备上的固件。

   ![Surface Dock 固件更新安装过程](images/regeditDock.png)

3. 验证新的注册表项值是否与本文档末尾的版本参考中列出的更新的注册表项值相匹配。 如果值匹配，则固件已成功更新。

4. 如果无法验证，请查看下一节中的事件日志记录和疑难解答提示。

## 事件日志记录

**表 1.  Surface Dock 固件更新的日志文件**

| Log                              | 位置                               | 注释                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Dock 固件更新日志 | 需要指定路径（请参阅注意） | 此工具的早期版本将事件写入应用程序和服务 Logs\Microsoft Surface Dock 更新。                                                                                                  |
| Windows 设备安装日志       | %windir%\inf\setupapi.dev.log           | 有关使用设备安装日志的详细信息，请参阅[SetupAPI 日志记录](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-)文档。 |


**表 2.  Surface Dock 固件更新的事件日志 Id**<br>
在应用程序事件日志中记录事件。  注意：此工具的早期版本向应用程序和服务 Logs\Microsoft Surface Dock 更新程序写入了事件。

| 事件 ID | 事件类型                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | 已开始插接固件更新。                                    |
| 2002     | 已跳过插接固件更新，因为插接已被认为是最新的。 |
| 2003     | 插接固件更新无法获取固件版本。                 |
| 2004     | 查询固件版本。                                       |
| 2005     | Dock 固件无法开始更新。                                |
| 2006     | 无法发送优惠/负载对。                                  |
| 2007     | 固件更新已完成。                                            |
| 2008     | 开始停靠遥测。                                                |
| 2011     | 结束停靠遥测。                                                  |

## 疑难解答提示

- 完全断开 Surface dock 与交流电源的连接，以重置 Surface Dock。
- 断开除 Surface Dock 之外的所有外围设备。
- 卸载任何当前 Surface Dock 固件更新，然后安装最新版本。
- 确保 Surface Dock 已断开连接，然后通过 Dock 的以太网端口中的 LED 使更新时间有足够的时间完成更新。 等待 LED 停止闪烁，然后再从 power 中拔出 Surface Dock。
- 将 Surface Dock 连接到其他设备，查看它是否能够更新坞站。

## 版本参考

>[!NOTE]
>安装文件以以下命名格式发布： **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** （例如： Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi），默认情况下安装到 C:\Program Files\SurfaceUpdate。

### 版本1.42.139 
*发布日期： 18 2019 年9月*

此版本（包含在 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI 中）会在后台更新固件。 
**已更新注册表项值：**<br>

- Component10CurrentFwVersion 更新为**4ac3970**。
- Component20CurrentFwVersion 更新为**4a1d570**。

它添加了对 Surface Pro 7 和 Surface 笔记本电脑3的支持。

## 旧版本

### 版本2.23.139。0
*发布日期：2018年10月10日*

此版本的 Surface Dock Updater 添加了以下支持：

- 添加对 Surface Pro 6 的支持
- 添加对 Surface 笔记本电脑的支持2


### 版本2.22.139。0
*发布日期：2018年7月26日*

此版本的 Surface Dock Updater 添加了以下支持：

- 提高更新可靠性
- 添加对 Surface Go 的支持

### 版本 2.12.136.0
*发布日期：2018 年 1 月 29 日*

此版本的 Surface Dock Updater 添加了以下支持：
* Surface 扩展坞主芯片集固件更新
* Surface 扩展坞 DisplayPort 固件更新
* 改进了使用 Surface Book 或 Surface Book 2 时外部显示器的显示稳定性。

此外，在 Surface Book 设备上安装的此版本 Surface Dock Updater 包括：
* Surface Book 底座固件更新
* 增加了 Surface 扩展坞固件更新支持，针对 Surface Book 设备做出了改进


### 版本 2.9.136.0
*发布日期：2017 年 11 月 3 日*

此版本的 Surface Dock Updater 添加了以下支持：

* Surface 扩展坞 DisplayPort 固件更新
* 通过无源显示端口适配器解决音频问题

### 版本 2.1.15.0
*发布日期：2017 年 6 月 19 日*

此版本的 Surface Dock Updater 添加了以下支持：

* Surface Laptop
* Surface Pro

### 版本 2.1.6.0
*发布日期：2017 年 4 月 7 日*

此版本的 Surface Dock Updater 添加了以下支持：

* Surface 扩展坞 DisplayPort 固件更新
* 要求使用 Windows 10

### 版本 2.0.22.0
*发布日期：2016 年 10 月 21 日*

此版本的 Surface Dock Updater 添加了以下支持：

* Surface 扩展坞 USB 固件更新
* 提升了以太网、音频和 USB 端口的可靠性

### 版本 1.0.8.0
*发布日期：2016 年 4 月 26 日*

此版本的 Surface Dock Updater 添加了以下支持：

* Surface 扩展坞主芯片集固件更新
* Surface 扩展坞 DisplayPort 固件更新


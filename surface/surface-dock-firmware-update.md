---
title: Microsoft Surface Dock 1 固件更新
description: 本文介绍了如何使用 Microsoft Surface 扩展坞固件更新在原始 Surface 扩展坞 1 上安装和管理固件。 在 Surface 设备上安装时，它将更新连接到 Surface 设备的 Surface 扩展坞 1 设备。
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
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319206"
---
# Microsoft Surface 扩展坞固件更新

> [!IMPORTANT]
> 本文包含适用于 IT 管理员的技术说明。 如果你是家庭用户，请参阅如何在 Microsoft 支持站点上更新[Surface 扩展](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   坞固件。 支持站点上的说明与下面的一般安装步骤相同，但本文提供了用于监视、验证更新以及将更新部署到网络上多台设备的其他信息。

本文介绍了如何使用 Microsoft Surface 扩展坞固件更新在原始 Surface 扩展坞 1 上安装和管理固件。 在 Surface 设备上安装时，它将更新连接到 Surface 设备的 Surface 扩展坞 1 设备。

> [!NOTE]
> 本文不适用于 Surface Dock 2，它通过 Windows 更新或 Microsoft Endpoint Configuration Manager 或其他 MSI 部署工具自动接收更新。 若要了解更多信息，请参阅 Surface 扩展 [坞中的新增功能](surface-dock-whats-new.md)。

此工具取代以前作为适用于 IT 的 Surface Tools 的一部分可供下载的早期的 Microsoft Surface Dock Updater 工具。 之前的工具名为 Surface_Dock_Updater_vx.xx.xxx.x.msi (其中 x 指示版本号) 且不再可供下载，因此不应使用。

## 安装 Surface 扩展坞固件更新

本节介绍如何手动安装固件更新。

> [!NOTE]
> Microsoft 会定期发布新版本的 Surface 扩展坞固件更新。 MSI 文件不是自行更新的。 如果你已经将 MSI 部署到 Surface 设备并发布了新版本的固件，则需要部署新版本。

1. 下载并安装 [Microsoft Surface 扩展坞固件更新](https://www.microsoft.com/download/details.aspx?id=46703)。
    - 更新需要运行 Windows 10 版本 1803 或更高版本的 Surface 设备。
    - 安装 MSI 文件可能会提示你重新启动 Surface。 但是，执行更新不需要重新启动。

2. 断开 Surface 设备与 Surface 扩展坞连接，等待约 5 秒，然后重新连接。 Surface 扩展坞固件更新将在后台以静默方式更新扩展坞。 此过程可能需要几分钟才能完成，即使中断，也会继续。 

## 监视 Surface 扩展坞固件更新

此部分是可选的，概述了如何监视固件更新的安装。 

若要监视更新，请执行以下操作：

1. 打开事件查看器，浏览到 Windows**日志 > 应用程序**，然后在右侧**** 窗格中的操作下单击"筛选当前日志****"，输入事件源旁边的**SurfaceDockFwUpdate，** 然后单击"**确定**"。 ****

2. 在提升的命令提示符下键入以下命令：

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. 安装更新，如本文下 [一节](#install-the-surface-dock-firmware-update) 中所述。

4. 具有以下文本的事件 2007 表示成功更新：固件**更新已完成。hr=0 DriverTelementry EventCode = 2007。** 

   如果更新不成功，则事件 ID 2007 将显示为 **错误** 事件而不是 **信息**。 此外，Windows 注册表中报告的版本不是最新的。
   
5. 更新完成后，更新后的 DWORD 值将显示在 Windows 注册表中，与该工具的当前版本相对应。 有关详细信息 [，请参阅](#versions-reference) 本文中的版本参考部分。 例如：

    - Component10CurrentFwVersion 0x04ac3970 (78395760) 
    - Component20CurrentFwVersion 0x04915a70 (76634736) 

>[!TIP]
>如果在事件文本中看到"找不到源 SurfaceDockFwUpdate 中的事件 ID xxxx 的说明"，这是预期且可以忽略的。

另请参阅本文中的以下部分： 
  - [如何验证固件更新的完成情况](#how-to-verify-completion-of-the-firmware-update)
  - [事件日志记录](#event-logging)
  - [疑难解答提示](#troubleshooting-tips)
  - [版本参考](#versions-reference)

## 网络部署

可以使用 Windows Installer (Msiexec.exe) 将 Surface 扩展坞固件更新部署到整个网络的多个设备。 使用 Microsoft Endpoint Configuration Manager 或其他部署工具时，输入以下语法以确保安装是无提示的：

- **Msiexec.exe /i \<path to msi file\> /quiet /norestart** 

例如：

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> 默认情况下日志文件创建一个数据库。 若要创建一个日志文件，您需要追加"/l*v [path]"。例如：Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"

有关详细信息，请参阅 [命令行选项](https://docs.microsoft.com/windows/win32/msi/command-line-options) 文档。

> [!IMPORTANT]
> 如果你想要使用任何其他方法更新 Surface 扩展坞，请参阅更新 Surface [扩展](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) 坞了解详细信息。

## Intune 部署

可以使用 Intune 将 Surface 扩展坞固件更新分发到设备。 首先，你需要将 MSI 文件转换为 .intunewin 格式，如以下文档所述 [：Intune Standalone - Win32 应用管理](https://docs.microsoft.com/intune/apps/apps-win32-app-management)。

使用以下命令：
  - **msiexec /i \<path to msi file\> /quiet /q**

## 如何验证固件更新的完成情况

Surface 扩展坞固件由两个组件组成：

- **Component10：** MCU 控制器固件 (控制器) 单元
- **Component20：** 显示 DP (固件) 端口。

成功完成 Surface 扩展坞固件更新会导致这些固件组件获得新的注册表项值。

**验证更新：**

1. 打开 Regedit 并导航到以下注册表路径：

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. 查找注册表项 **：Component10CurrentFwVersion 和 Component20CurrentFwVersion，** 它引用当前位于设备的固件。

   ![Surface 扩展坞固件更新安装过程](images/regeditDock.png)

3. 验证新的注册表项值是否与本文档末尾的 Versions 参考中列出的更新的注册表项值匹配。 如果值匹配，则固件已成功更新。

4. 如果无法验证，请查看下一节中的事件日志记录和疑难解答提示。

## 事件日志记录

**表 1.  Surface 扩展坞固件更新的日志文件**

| Log                              | 位置                               | 注释                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface 扩展坞固件更新日志 | 需要指定路径， (注释)  | 此工具的早期版本将事件写到应用程序和服务日志\Microsoft Surface Dock Updater。                                                                                                  |
| Windows 设备安装日志       | %windir%\inf\setupapi.dev.log           | 有关使用设备安装日志的信息，请参阅 [SetupAPI 日志记录](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) 文档。 |


**表 2.  Surface 扩展坞固件更新的事件日志 ID**<br>
事件记录在应用程序事件日志中。  注意：此工具的早期版本将事件写到 Applications and Services Logs\Microsoft Surface Dock Updater。

| 事件 ID | 事件类型                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | 扩展坞固件更新已启动。                                    |
| 2002     | 扩展坞固件更新已跳过，因为扩展坞已知是最新的。 |
| 2003     | 扩展坞固件更新无法获取固件版本。                 |
| 2004     | 查询固件版本。                                       |
| 2005     | 扩展坞固件无法启动更新。                                |
| 2006     | 无法发送产品/有效负载对。                                  |
| 2007     | 固件更新已完成。                                            |
| 2008     | BEGIN 扩展坞遥测。                                                |
| 2011     | END 扩展坞遥测。                                                  |

## 疑难解答提示

- Surface 扩展坞与交流电源完全断开连接以重置 Surface 扩展坞。
- 断开除 Surface 扩展坞之外的所有外围设备。
- 卸载任何当前 Surface 扩展坞固件更新，然后安装最新版本。
- 确保 Surface 扩展坞已断开连接，然后留出足够的时间，以便更新完成（通过扩展坞的以太网端口中的 LED 进行监视）。 等待 LED 停止闪烁，然后拔下 Surface 扩展坞电源。
- 将 Surface 扩展坞连接到其他设备，以查看其能否更新扩展坞。

## 版本参考

>[!NOTE]
>安装文件以以下命名格式 ** 发布：Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI(** 例如：Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) 并默认安装到 C：\Program Files\SurfaceUpdate。

### 版本 1.53.139.0
*发布日期：2020 年 8 月 4 日*

此版本的 Surface 扩展坞固件更新包括 Bug 修复和支持：
- 使用 Surface Pro X 更新 Surface 扩展坞 1。 
   > [!NOTE]
   > 如果你运行的是 Surface Pro X，请下载 。ARM64 内部版本。 对于所有其他设备，请使用 AMD64 版本。 

#### 注册表项值

指示固件更新状态的注册表值与此工具的早期版本相同： 

- Component10CurrentFwVersion 更新为 **4ac3970**。
- Component20CurrentFwVersion 更新为 **4a1d570**。
 
### 版本 1.42.139 
*发布日期：2019 年 9 月 18 日*

此版本包含在 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI，可更新后台固件。 

####  <a name="update"></a>更新了注册表项值

- Component10CurrentFwVersion 更新为 **4ac3970**。
- Component20CurrentFwVersion 更新为 **4a1d570**。

它增加了对 Surface Pro 7 和 Surface Laptop 3 的支持。

## 旧版本

### 版本 2.23.139.0
*发布日期：2018 年 10 月 10 日*

此版本的 Surface Dock Updater 添加了以下支持：

- 添加对 Surface Pro 6 的支持
- 添加对 Surface Laptop 2 的支持


### 版本 2.22.139.0
*发布日期：2018 年 7 月 26 日*

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


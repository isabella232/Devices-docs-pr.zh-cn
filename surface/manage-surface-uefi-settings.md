---
title: 管理 Surface UEFI 设置
description: 使用 Surface UEFI 设置启用或者禁用设备或组件、配置安全设置以及调整 Surface 设备启动设置。
keywords: 固件, 安全, 功能, 配置, 硬件
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831655"
---
# 管理 Surface UEFI 设置

所有当前和未来的 Surface 设备代都使用专为这些设备设计的独特的统一可扩展固件接口（UEFI）。 Surface UEFI 设置提供启用或禁用内置设备和组件、保护 UEFI 设置不被更改以及调整 Surface 设备启动设置的功能。 

## 支持基于云的管理

使用内置于 Microsoft Intune 的设备固件配置接口（DFCI）配置文件（现在在公共预览版中可用），Surface UEFI 管理将新式管理堆栈扩展到 UEFI 硬件级别。 DFCI 支持零接触预配，消除了 BIOS 密码，提供了安全设置（包括启动选项和内置外围设备）的控制权，并为将来的高级安全方案奠定了基础。 DFCI 当前可用于 Surface Pro 7、Surface Pro X 和 Surface 笔记本电脑3。 有关详细信息，请参阅[SURFACE UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。

## 打开 Surface UEFI 菜单

要在系统启动期间调整 UEFI 设置，请执行以下操作：

1. 关闭你的 Surface，等待大约10秒钟，确保它处于关闭状态。
2. 同时按住**调高音量**按钮，同时按下并松开**电源按钮。**
3. 由于 Microsoft 或 Surface 徽标显示在你的屏幕上，因此继续保持**音量向上**键，直到出现 UEFI 屏幕。

## UEFI 电脑信息页面

PC 信息页面包括有关 Surface 设备的详细信息： 

- **模型**-你的 surface 设备模型将在此处显示，如 surface Book 2 或 surface Pro 7。 不会显示设备的具体配置（例如处理器、磁盘大小或内存大小）。 
- **UUID** - 此通用唯一标识号特定于设备，用于在部署或管理期间标识设备。 

- **序列号** - 此编号用于标识资源标记和支持场景的特定 Surface 设备。
- **资源标记** - 资源标记通过[资源标记工具](https://docs.microsoft.com/surface/assettag)分配到 Surface 设备。 

还可以找到关于 Surface 设备固件的详细信息。 Surface 设备具有多个内部组件，每个组件运行不同版本的固件。 以下所有设备的固件版本显示在**电脑信息**页上（如图 1 所示）： 

- 系统 UEFI 

- SAM 控制器 

- Intel 管理引擎 

- 系统嵌入式控制器 

- 触摸固件 

![系统信息和固件版本信息](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*图 1. 系统信息和固件版本信息*

在设备的 [Surface 更新历史记录](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)中可以找到有关 Surface 设备最新固件版本的最新信息。 

## UEFI 安全页面 

![配置 Surface UEFI 安全设置](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*图 2. 配置 Surface UEFI 安全设置*

"安全" 页面允许您设置密码以保护 UEFI 设置。 在将 Surface 设备启动到 UEFI 时，必须输入此密码。 密码可以包含以下字符（如图3所示）： 

- 大写字母：A-Z 

- 小写字母：a-z 

- 数字：1-0 

- 特殊字符：！ @ # $% ^& * （）？ <>{} [] – _ = + |;，;： "'" 

密码必须最少为 6 个字符，并且区分大小写。 

![添加保护 Surface UEFI 设置的密码](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*图 3. 添加保护 Surface UEFI 设置的密码*

在安全页上，还可以更改 Surface 设备的安全启动配置。 安全启动技术可阻止未经授权的启动代码启动 Surface 设备，这可防御 bootkit 和 rootkit 类型的恶意软件感染。 可以禁用安全启动，从而允许 Surface 设备启动第三方操作系统或可启动媒体。 您还可以配置 "安全启动" 以处理第三方证书，如图4所示。 在 TechNet 库中阅读有关[安全启动](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)的详细信息。

![配置安全启动](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*图 4. 配置安全启动*

根据你的设备，你还可以查看你的 TPM 是否已启用或已禁用。 如果看不到 "**启用 TPM** " 设置，请在 Windows 中打开 "services.msc" 以检查状态，如图5所示。 TPM 用于与 BitLocker 一起验证设备数据的加密情况。 若要了解详细信息，请参阅[BitLocker 概述](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。 

![TPM 控制台](images/manage-surface-uefi-fig5-a.png "TPM console")

*图 5. TPM 控制台*


## UEFI 菜单：设备 

"设备" 页面允许你启用或禁用特定设备和组件，包括：

- 扩展坞和 USB 端口 

- MicroSD 或 SD 卡槽 

- 后置摄像头 

- 前置摄像头 

- 红外 (IR) 相机 

- WLAN 和蓝牙 

- 板载音频（扬声器和麦克风） 

列出的每个设备带有一个滑块按钮，您可以将该按钮移动到 **"打开"** （已启用）或 "**关闭**" （禁用）位置，如图6所示。 

![启用和禁用特定设备](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*图 6. 启用和禁用特定设备*

## UEFI 菜单：启动配置 

"启动配置" 页面允许你更改启动设备的顺序以及启用或禁用以下设备的启动： 

- Windows 启动管理器 

- USB 存储 

- PXE 网络 

- 内部存储 

可以立即启动特定设备，或使用触摸屏在列表中向左滑动该设备项。 还可以在关闭 Surface 设备电源时，同时按**调低音量**按钮和**电源**按钮，立即启动到 USB 设备或 USB 以太网适配器。 

为使指定的启动顺序生效，必须将 "**启用备用启动序列**" 选项设置为 **"打开**"，如图7所示。 

![配置 Surface 设备的启动顺序](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*图 7. 配置 Surface 设备的启动顺序* 

在使用 PXE 服务器仅为 IPv4 配置的 PXE 部署 Windows 时，还可以使用**启用用于 PXE 网络启动的 IPv6** 选项来打开和关闭对 PXE 的 IPv6 支持。  

## UEFI 菜单：管理
通过 "管理" 页面，你可以在符合条件的设备（包括 Surface Pro 7、Surface Pro X 和 Surface 笔记本3）上管理零接触 UEFI 管理和其他功能的使用。  

![管理对零接触 UEFI 管理和其他功能的访问 ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *图8。管理对零接触 UEFI 管理和其他功能的访问* 


零接触 UEFI 管理允许你通过使用名为 "设备固件配置" 界面（DFCI）的 Intune 内的设备配置文件来远程管理 UEFI 设置。 如果不配置此设置，将具有 DFCI 的符合条件的设备的功能设置为 "**就绪**"。 若要防止 DFCI，**请选择 "选择退出**"。 

> [!NOTE]
> 只有 Surface Pro 7、Surface Pro X 和 Surface 笔记本电脑3提供了 UEFI 管理设置页面和使用 DFCI。  

有关详细信息，请参阅[SURFACE UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。

## UEFI 菜单：退出 

使用 "**退出**" 页面上的 "**立即重启**" 按钮退出 UEFI 设置，如图9所示。 

![退出 Surface UEFI，并重启设备](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*图 9. 单击“立即重启”退出 Surface UEFI，并重启设备*

## Surface UEFI 启动屏幕

当你通过 Windows 更新或手动安装更新 Surface 设备固件时，更新不会立即适用于设备，而是在下个重新启动周期应用。 你可以在[管理 Surface 驱动程序和固件更新](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)中了解有关 Surface 固件更新过程的详细信息。 固件更新的进度会在屏幕上显示为具有不同颜色的进度栏，以指示每个组件的固件。 每个组件的进度条都显示在第9和第18图中。

![带有蓝色进度栏的 Surface UEFI 固件更新](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*图 10. Surface UEFI 固件更新显示蓝色进度栏*

![带有绿色进度栏的系统嵌入式控制器固件](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*图 11. 系统嵌入式控制器固件更新显示绿色进度栏*

![带有橙色进度栏的 SAM 控制器固件更新](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*图 12. SAM 控制器固件更新显示橙色进度栏*

![带有红色进度栏的 Intel 管理引擎固件](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*图 13. Intel 管理引擎固件更新显示红色进度栏*

![带有灰色进度栏的 Surface 触摸固件](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*图 14. Surface 触摸固件更新显示灰色进度栏*

![带有浅绿色进度栏的 Surface KIP 固件](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*图 15. Surface KIP 固件更新显示浅绿色进度栏*

![具有粉红色进度栏的 Surface ISH 固件](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*图 16 Surface ISH 固件更新显示浅粉色进度条*

![具有灰色进度栏的 Surface 触控板固件](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*图 17. Surface 触控板固件更新显示粉红色进度条*

![具有浅灰色进度栏的 Surface TCON 固件](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*图 18. Surface TCON 固件更新显示浅灰色进度栏*


![具有浅紫色进度栏的 Surface TPM 固件](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*图 19. Surface TPM 固件更新显示紫色进度栏*


>[!NOTE]
>将显示一个指示安全启动已禁用的其他警告消息，如图19所示。

![指示安全启动已禁用的 Surface 启动屏幕](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*图 20. 指示安全启动已在 Surface UEFI 设置中禁用的安全启动屏幕*

## 相关主题

- [Surface UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)

-  [Surface 企业管理模式](surface-enterprise-management-mode.md)

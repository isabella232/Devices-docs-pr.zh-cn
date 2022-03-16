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
ms.reviewer: hachidan
manager: laurawi
ms.date: 01/18/2022
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 7da3a2908acc654abd86406af36eba4929bf4760
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449655"
---
# <a name="manage-surface-uefi-settings"></a>管理 Surface UEFI 设置

 Surface PC 设备旨在利用 Microsoft 专门为这些设备 (UEFI) 唯一的统一可扩展固件接口。 Surface UEFI 设置提供启用或禁用内置设备和组件、防止更改 UEFI 设置以及调整 Surface 设备启动设置的能力。

## <a name="supported-products"></a>支持的产品

以下各项支持 UEFI 管理：

- Surface Pro 4、Surface Pro (第五代) 、Surface Pro 6、Surface Pro 7、Surface Pro 7+ (商业 SK 仅) 、Surface Pro 8 (商业 SK) 、Surface Pro X
- Surface Laptop (第一代) 、Surface Laptop 2、Surface Laptop 3 (Intel 处理器仅) 、Surface Laptop Go、Surface Laptop 4 (商业 SK) Surface Laptop 标准版
- Surface Studio (第一代) ，Surface Studio 2 号
- Surface Book (所有代) 
- Surface Laptop Studio (商业 SKUs) 
- Surface Go、Surface Go [21<sup></sup>](#references)、Surface Go 3 (商业 SK 仅) 

>[!TIP]
> 商业 SKUS (，Surface 商用版) 运行 Windows 10 专业版/Enterprise 或 Windows 11 专业版/Enterprise;消费者 SUS Windows 10/Windows 11 家庭版。 若要了解详细信息，请参阅 [查看系统信息](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00)。 


## <a name="support-for-cloud-based-management"></a>支持基于云的管理

通过内置于 Microsoft Intune (中的设备固件配置接口 (DFCI) 配置文件现在可用于公共预览版) ，Surface UEFI 管理将新式管理堆栈向下扩展到 UEFI 硬件级别。 DFCI 支持零接触预配、消除 BIOS 密码、控制安全设置（包括启动选项和内置外设）并在将来为高级安全方案打下基础。 DFCI 目前可用于 Surface Laptop 标准版、Surface Laptop Studio、Surface Pro 8、Surface Go 3、Surface Laptop 4、Surface Laptop Go、Surface Book 3、Surface Laptop 3，Surface Pro 7+、Surface Pro 7 和 Surface Pro X。  有关详细信息，请参阅 [Surface UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。

## <a name="open-surface-uefi-menu"></a>打开 Surface UEFI 菜单

在系统启动期间调整 UEFI 设置：

1. 关闭 Surface 并等待大约 10 秒以确保其关闭。
2. 长按 **"调高音量"** 按钮，同时按下并释放 **电源按钮。**
3. 当 Microsoft 或 Surface 徽标显示在屏幕上时，请继续按住"调高**** 音量"按钮，直到出现 UEFI 屏幕。

## <a name="uefi-pc-information-page"></a>UEFI 电脑信息页

电脑信息页面包含有关 Surface 设备的详细信息：

- **型号** – Surface 设备型号将在此处显示，如 Surface Book 2 或 Surface Pro 7。 不会显示设备的具体配置（例如处理器、磁盘大小或内存大小）。
- **UUID** - 此通用唯一标识号特定于设备，用于在部署或管理期间标识设备。

- **序列号** - 此编号用于标识资源标记和支持场景的特定 Surface 设备。
- **资源标记** - 资源标记通过[资源标记工具](assettag.md)分配到 Surface 设备。

还可以找到关于 Surface 设备固件的详细信息。 Surface 设备具有多个内部组件，每个组件运行不同版本的固件。 以下所有设备的固件版本显示在**电脑信息**页上（如图 1 所示）：

- 系统 UEFI

- SAM 控制器

- Intel 管理引擎

- 系统嵌入式控制器

- 触摸固件

:::image type="content" alt-text="系统信息和固件版本信息。" source="images/manage-surface-uefi-figure-1.png":::

*图 1. 系统信息和固件版本信息*

在设备的 [Surface 更新历史记录](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)中可以找到有关 Surface 设备最新固件版本的最新信息。

## <a name="uefi-security-page"></a>UEFI 安全页

:::image type="content" alt-text="配置 Surface UEFI 安全设置。" source="images/manage-surface-uefi-fig4.png":::

*图 2. 配置 Surface UEFI 安全设置*

The Security page allows you to set a password to protect UEFI settings. 在将 Surface 设备启动到 UEFI 时，必须输入此密码。 密码可以包含以下字符 (如图 ) 3 所示：

- 大写字母：A-Z

- 小写字母：a-z

- 数字：1-0

- 特殊字符：！@#$%^&* () ？<>{}[]-_=+|.，;：''"

密码必须至少为六个字符，并且区分大小写。

![添加密码以保护 Surface UEFI 设置。](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*图 3. 添加保护 Surface UEFI 设置的密码*

在安全页上，还可以更改 Surface 设备的安全启动配置。 安全启动技术可阻止未经授权的启动代码启动 Surface 设备，这可防御 bootkit 和 rootkit 类型的恶意软件感染。 可以禁用安全启动，从而允许 Surface 设备启动第三方操作系统或可启动媒体。 还可以配置安全启动以使用第三方证书，如图 4 所示。 若要了解更多信息，请参阅 [安全启动](/windows-hardware/design/device-experiences/oem-secure-boot)。

![配置安全启动。](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*图 4. 配置安全启动*

根据你的设备，你可能还能够查看你的 TPM 是已启用还是已禁用。 如果看不到"启用 **TPM**"设置，请在"Windows打开 tpm.msc 以检查状态，如图 5 所示。 TPM 用于与 BitLocker 一起验证设备数据的加密情况。 若要了解更多信息，请参阅 [BitLocker 概述](/windows/security/information-protection/bitlocker/bitlocker-overview)。

![TPM 控制台。](images/manage-surface-uefi-fig5-a.png "TPM console")

*图 5. TPM 控制台*

## <a name="uefi-menu-devices"></a>UEFI 菜单：设备

"设备"页允许你启用或禁用特定设备和组件，包括：

- 扩展 USB 端口

- MicroSD 或 SD 卡槽

- 后置摄像头

- 前置摄像头

- 红外 (IR) 相机

- WLAN 和蓝牙

- 板载音频（扬声器和麦克风）

每个设备都列出了一个滑块按钮，你可以将其移动到"**** 开" (") " (禁用) 位置****"，如图 6 所示。

:::image type="content" alt-text="启用和禁用特定设备。" source="images/manage-surface-uefi-fig5a.png":::

*图 6. 启用和禁用特定设备*

## <a name="uefi-menu-boot-configuration"></a>UEFI 菜单：启动配置

"启动配置"页允许你更改启动设备的顺序，以及启用或禁用以下设备的启动：

- Windows 启动管理器

- USB 存储

- PXE 网络

- 内部存储

可以立即启动特定设备，或使用触摸屏在列表中向左滑动该设备项。 还可以在关闭 Surface 设备电源时，同时按**调低音量**按钮和**电源**按钮，立即启动到 USB 设备或 USB 以太网适配器。

为了使指定的启动顺序生效，必须将"启用备用启动序列"**** 选项设置为 **"打开**"，如图 7 所示。

:::image type="content" alt-text="配置 Surface 设备的启动顺序。" source="images/manage-surface-uefi-fig6.png":::

*图 7. 配置 Surface 设备的启动顺序*

在使用 PXE 服务器仅为 IPv4 配置的 PXE 部署 Windows 时，还可以使用**启用用于 PXE 网络启动的 IPv6** 选项来打开和关闭对 PXE 的 IPv6 支持。  

## <a name="uefi-menu-management"></a>UEFI 菜单："管理"

"管理"页允许你在符合条件的设备上管理零接触 UEFI 管理和其他功能的使用，包括 Surface Pro 8、Surface Go 3、Surface Laptop Studio、Surface Pro 7+、Surface Pro 7、Surface Pro X、Surface Laptop 4、Surface Laptop 3、Surface Laptop 标准版 和 Surface Book 3。 

:::image type="content" alt-text="管理对零接触 UEFI 管理和其他功能的访问权限。" source="images/manage-surface-uefi-fig7a.png":::

*图 8. 管理对零接触 UEFI 管理和其他功能的访问权限*

借助零接触 UEFI 管理，可以使用 Intune 中的设备配置文件（称为设备固件配置接口和 DFCI (）远程管理 UEFI) 。 如果未配置此设置，则使用 DFCI 管理符合条件的设备的能力将设置为 **"就绪"**。 若要阻止 DFCI，请选择 **"选择退出"**。

> [!NOTE]
> UEFI 管理设置页和 DFCI 的使用目前适用于 Surface Laptop 标准版、Surface Laptop Studio、Surface Pro 8、Surface Go 3、Surface Laptop 4、Surface Laptop Go、Surface Book 3、Surface Laptop 3、Surface Pro 7+、Surface Pro 7 和 Surface Pro X。 若要了解更多信息，请参阅 [Surface UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)。

## <a name="uefi-menu-exit"></a>UEFI 菜单：退出

使用"**退出"****页上的"** 立即重启"按钮退出 UEFI 设置，如图 9 所示。

:::image type="content" alt-text="退出 Surface UEFI 并重启设备。" source="images/manage-surface-uefi-fig7.png":::

*图 9. 单击“立即重启”退出 Surface UEFI，并重启设备*

## <a name="surface-uefi-boot-screens"></a>Surface UEFI 启动屏幕

当你通过 Windows 更新或手动安装更新 Surface 设备固件时，更新不会立即适用于设备，而是在下个重新启动周期应用。 可以在管理和部署 Surface 驱动程序和固件更新中了解有关 Surface 固件更新 [过程的信息](manage-surface-driver-and-firmware-updates.md)。 固件更新的进度会在屏幕上显示为具有不同颜色的进度栏，以指示每个组件的固件。 图 9 至 18 显示了每个组件的进度栏。

![使用蓝色进度栏进行 Surface UEFI 固件更新。](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*图 10. Surface UEFI 固件更新显示蓝色进度栏*

![带绿色进度栏的系统嵌入式控制器固件。](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*图 11. 系统嵌入式控制器固件更新显示绿色进度栏*

![使用橙色进度栏更新 SAM 控制器固件。](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*图 12. SAM 控制器固件更新显示橙色进度栏*

![带红色进度栏的 Intel 管理引擎固件。](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*图 13. Intel 管理引擎固件更新显示红色进度栏*

![带灰色进度条的 Surface 触摸固件。](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*图 14. Surface 触摸固件更新显示灰色进度栏*

![使用浅绿色进度栏的 Surface KIP 固件。](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*图 15. Surface KIP 固件更新显示浅绿色进度栏*

![带粉色进度栏的 Surface ISH 固件。](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*图 16 Surface ISH 固件更新显示浅粉色进度栏*

![带灰色进度栏的 Surface Trackpad 固件。](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*图 17. Surface Trackpad 固件更新显示粉色进度栏*

![具有浅灰色进度条的 Surface TCON 固件。](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*图 18. Surface TCON 固件更新显示浅灰色进度栏*

![带淡紫色进度条的 Surface TPM 固件。](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*图 19. Surface TPM 固件更新显示紫色的进度栏*

>[!NOTE]
>将显示其他指示安全启动已禁用的警告消息，如图 19 所示。

![指示安全启动已禁用的 Surface 启动屏幕。](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*图 20. 指示安全启动已在 Surface UEFI 设置中禁用的安全启动屏幕*

## <a name="references"></a>参考

1. Surface Go 和 Surface Go 2 使用第三方 UEFI，不支持 DFCI。 DFCI 目前可用于 Surface Laptop 标准版、Surface Laptop Studio、Surface Pro 8、Surface Go 3、Surface Laptop 4、Surface Laptop Go、Surface Book 3、Surface Laptop 3，Surface Pro 7+、Surface Pro 7 和 Surface Pro X。

## <a name="related-topics"></a>相关主题

- [Surface UEFI 设置的 Intune 管理](surface-manage-dfci-guide.md)

- [Surface 企业管理模式](surface-enterprise-management-mode.md)

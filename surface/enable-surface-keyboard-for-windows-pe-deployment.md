---
title: 如何在 MDT Surface Laptop启用键盘
description: 当你使用 MDT 将 Windows 10 Surface 笔记本电脑时，你需要导入键盘驱动程序以在 Windows PE 环境中使用。
keywords: windows 10 surface， 自动化， 自定义， mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 01/05/2022
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
- Surface Laptop 4
- Surface Laptop Studio
- Surface Pro 8
- Windows 10
- Windows 11
ms.openlocfilehash: 8707d022ae5e3d3f34c59fab88328b5720896898
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449185"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>如何在 MDT Surface Laptop启用键盘

本文介绍使用 Microsoft Deployment Toolkit (MDT) 。 您还可以将此信息应用于其他部署方法。 在大多数类型的 Surface 设备上，键盘应在 Lite Touch 安装期间运行 (LTI) 。 但是，Surface Laptop需要其他一些驱动程序才能启用键盘。 对于 Surface Laptop (第一代) 和 Surface Laptop 2 设备，必须准备文件夹结构和选择配置文件，以允许你指定在 LTI 的 Windows 预安装环境 (Windows PE) 阶段使用的键盘驱动程序。 有关此文件夹结构详细信息，请参阅使用 MDT 部署Windows 10映像[：步骤 5：准备驱动程序存储库](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。

> [!TIP]
> 在同一 Windows PE 启动实例中将 Surface Laptop 2 和 Surface Laptop 3 的键盘驱动程序用于时，如果键盘或触摸板在 Windows PE 中不起作用，可能需要手动重置固件：
>
> - 长按电源按钮 30 秒。 如果连接到电源设备 (PSU) ，请长按电源按钮，直到看到 PSU 电缆末端的灯在重新打开之前短暂关闭。

> [!IMPORTANT]
> 如果要将 Windows 10 映像部署到在 S 模式下预安装 Windows 10 的 Surface Laptop，请参阅 KB 4032347，在 S 模式下将 Windows 部署到具有预安装 Windows 10 的 [Surface 设备时](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)出现问题。

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>将键盘驱动程序添加到选择配置文件

1. 从适当Surface Laptop .msi下载最新更新文件：
    - [Surface Laptop (第一代) 驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 和 Intel 处理器驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 和 Intel 处理器驱动程序和固件](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 与 AMD 处理器驱动程序和固件](https://www.microsoft.com/download/102923)
    - [Surface Laptop Studio 驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 个驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=103503)

2. 将 Surface Laptop .msi 文件的内容解压缩到一个文件夹，您可以轻松地找到 (例如 c：\surface_laptop_drivers) 。 若要提取内容，请打开提升的命令提示符窗口并从以下示例运行命令：

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. 打开部署工作台，展开部署 **共享** 节点和部署共享，然后导航到 **WindowsPEX64** 文件夹。
4. 右键单击 **WindowsPEX64** 文件夹，然后选择 **导入驱动程序**。
5. 按照导入驱动程序向导中的说明将驱动程序文件夹导入到 WindowsPEX64 文件夹中。

 > [!NOTE]
 > 检查下载.msi包以确定格式和目录结构。  目录结构从 SurfacePlatformInstaller (较旧的 .msi 文件) 或 SurfaceUpdate (.msi 文件) 具体取决于 .msi 文件的发布时间。

## <a name="import-drivers-for-surface-devices"></a>导入 Surface 设备的驱动程序

根据你的设备需要导入Surface Laptop文件夹。  

| 设备                                | 导入文件夹                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | 更多信息                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Laptop Studio                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol | 不适用 |
| Surface Pro 8                         | heci<br>ialpss2_gpio2_tgl<br>ialpss2_i2c_tgl<br>ialpss2_spi_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>msux64w10<br>netwtw08<br>surfacebattery<br>surfacehidminidriver<br>surfaceintegrationdriver<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>tbthostcontroller<br>tbthostcontrollercioacomponent<br> |不适用 |
| Surface Laptop 4 与 Intel 处理器 | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          |不适用                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 4 与 AMD 处理器   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient |不适用                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 3 和 Intel 处理器 | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | 导入以下文件夹将在 PE 中启用完整的键盘、跟踪板和触摸功能：<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>itouch<br>芯片集<br>芯片集LPS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| Surface Laptop 2                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | 对于以.msi SurfaceUpdate"开头的较新文件，请使用：<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                                    |
| Surface Laptop (第一代)               | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | 对于以.msi SurfaceUpdate"开头的较新文件，请使用：<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                |

  > [!TIP]
  > 检查下载.msi包以确定格式和目录结构。  目录结构从 SurfacePlatformInstaller (较旧的 .msi 文件) 或 SurfaceUpdate (Newer .msi 文件) 具体取决于 .msi 何时发布。

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>验证导入的驱动程序&配置Windows PE 属性

1. 验证 WindowsPEX64 文件夹现在是否包含导入的驱动程序，如下图所示：

   ![显示部署工作台的 WindowsPEX64 文件夹中新导入的驱动程序的图像。](./images/surface-laptop-keyboard-2.png)
1. 配置使用 WindowsPEX64 文件夹的选择配置文件，如下图所示：

   ![显示选择配置文件的一部分选择的 WindowsPEX64 文件夹的图像。](./images/surface-laptop-keyboard-3.png)
1. 配置Windows MDT 部署共享的新 PE 属性以使用新的选择配置文件，如下所示：
    - 对于 **"平台**"，选择 **"x64"**。
    - 对于 **"选择配置文件**"，选择新配置文件。
    - 从 **选择配置文件中选择包括所有驱动程序**。

    ![显示 MDT Windows Share 的 PE 属性的图像。](./images/surface-laptop-keyboard-4.png)
4. 使用选择配置文件或 **DriverGroup001** 变量Surface Laptop剩余驱动程序。
    - 对于Surface Laptop (一代) ，**模型Surface Laptop。** 其余Surface Laptop驱动程序应位于 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 文件夹中，如下图所示。
    - 对于 Surface Laptop 2，模型为 **Surface Laptop 2**。 其余的Surface Laptop驱动程序应位于 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 文件夹中。
    - 对于Surface Laptop 3 处理器，型号为 Surface Laptop 3。 其余的Surface Laptop位于 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 文件夹中。

    ![显示部署工作台的 Surface Laptop (文件夹中) 第一代Surface Laptop驱动程序的图像。](./images/surface-laptop-keyboard-5.png)

将 MDT 部署共享配置为使用新的选择配置文件和相关设置后，继续部署过程，如使用 [MDT 部署 Windows 10 映像：步骤 6：创建部署任务序列](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)中所述。

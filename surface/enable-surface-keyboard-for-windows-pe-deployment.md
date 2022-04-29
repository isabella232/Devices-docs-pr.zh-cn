---
title: 如何在 MDT 部署期间启用Surface Laptop键盘
description: 使用 MDT 将Windows 10部署到 Surface 笔记本电脑时，需要导入要在 Windows PE 环境中使用的键盘驱动程序。
keywords: windows 10 surface， automate， customize， mdt
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
ms.openlocfilehash: d207d0843e23f68713597c12a529ab5574fa695e
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497915"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>如何在 MDT 部署期间启用Surface Laptop键盘

本文介绍使用 Microsoft 部署Toolkit (MDT) 的部署方法。 还可以将此信息应用于其他部署方法。 在大多数类型的 Surface 设备上，键盘应在 Lite Touch 安装 (LTI) 期间正常工作。 但是，Surface Laptop需要一些额外的驱动程序来启用键盘。 对于Surface Laptop (第一代) 和Surface Laptop 2 台设备，必须准备文件夹结构和选择配置文件，以便在 LTI 的Windows预安装环境 (Windows PE) 阶段指定要使用的键盘驱动程序。 有关此文件夹结构的详细信息，请参阅[使用 MDT 部署Windows 10映像：步骤 5：准备驱动程序存储库](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。

> [!TIP]
> 在同一Windows PE 启动实例中使用Surface Laptop 2 和 Surface Laptop 3 的键盘驱动程序时，如果键盘或触摸板在 WINDOWS PE 中不起作用，可能需要手动重置固件：
>
> - 按住 Power 按钮 30 秒。 如果连接到电源单元 (PSU) ，请按住电源按钮，直到看到 PSU 电源线末尾的灯短暂关闭，然后再重新打开。

> [!IMPORTANT]
> 如果要将Windows 10映像部署到已在 S 模式下预安装Windows 10的Surface Laptop，请参阅 KB [4032347，在 S 模式下使用预安装的Windows 10将Windows部署到 Surface 设备时出现问题](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)。

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>将键盘驱动程序添加到选择配置文件

1. 从相应位置下载最新的Surface Laptop .msi文件：
    - [Surface Laptop (第一代) 驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=57515)
    - [使用 Intel 处理器驱动程序和固件Surface Laptop 3](https://www.microsoft.com/download/details.aspx?id=100429)
    - [使用 Intel 处理器驱动程序和固件Surface Laptop 4](https://www.microsoft.com/download/102924)
    - [使用 AMD 处理器驱动程序和固件Surface Laptop 4](https://www.microsoft.com/download/102923)
    - [Surface Laptop Studio 驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=103503)

2. 将Surface Laptop .msi文件的内容提取到可轻松找到 (（例如 c：\surface_laptop_drivers) ）的文件夹。 若要提取内容，请打开提升的命令提示符窗口，并运行以下示例中的命令：

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. 打开 Deployment Workbench 并展开 **部署共享** 节点和部署共享，然后导航到 **WindowsPEX64** 文件夹。
4. 右键单击 **WindowsPEX64** 文件夹，然后选择 **“导入驱动程序**”。
5. 按照导入驱动程序向导中的说明将驱动程序文件夹导入 WindowsPEX64 文件夹。

 > [!NOTE]
 > 检查下载的.msi包以确定格式和目录结构。  目录结构将从 SurfacePlatformInstaller (较旧的.msi文件开始，) 或 SurfaceUpdate (较新的.msi文件) 取决于.msi文件的发布时间。

## <a name="import-drivers-for-surface-devices"></a>导入 Surface 设备的驱动程序

根据Surface Laptop设备导入以下文件夹。

| 设备                                    | 导入文件夹                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | 更多信息                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Laptop Studio**                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol                                                                                                                                                                                                                                                 | 不适用                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Pro 8**                         | intelthcbase<br>ManagementEngine<br>surfaceacpiplatformextension<br>SurfaceBattery<br>SurfaceCoverClick<br>SurfaceEthernetAdapter<br>SurfaceHidMini<br>SurfaceHotPlug<br>surfaceintegrationdriver<br>SurfaceSar<br>SurfaceSerialHub<br>surfacetimealarmacpifilter<br>surfacetypecoverv7fprude<br>SurfaceUcmUcsiHidClient<br>surfacevirtualfunctionenum<br>tbtslimhostcontroller<br>TglChipset<br>TglSerial                                                                                                                                                                     | 不适用                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **使用 Intel 处理器Surface Laptop 4** | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          | 不适用                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **使用 AMD 处理器Surface Laptop 4**   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient | 不适用                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **使用 Intel 处理器Surface Laptop 3** | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | 导入以下文件夹可在 PE 中启用完整的键盘、触控板和触摸功能：<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>itouch<br>芯片组<br>ChipsetLPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| **Surface Laptop 2**                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | 对于以“SurfaceUpdate”开头的较新.msi文件，请使用：<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                               |
| **Surface Laptop (第一代) **              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | 对于以 **“SurfaceUpdate”** 开头的较新.msi文件，请使用：<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                       |

  > [!TIP]
  > 检查下载的.msi包以确定格式和目录结构。  目录结构将从 SurfacePlatformInstaller (旧.msi文件) 或 SurfaceUpdate (Newer .msi 文件) 开头，具体取决于.msi的发布时间。

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>验证导入的驱动程序&配置 Windows PE 属性

1. 验证 WindowsPEX64 文件夹现在是否包含导入的驱动程序，如下图所示：

   ![显示部署 Workbench 的 WindowsPEX64 文件夹中新导入的驱动程序的图像。](./images/surface-laptop-keyboard-2.png)
1. 配置使用 WindowsPEX64 文件夹的选择配置文件，如下图所示：

   ![显示作为选择配置文件的一部分选择的 WindowsPEX64 文件夹的图像。](./images/surface-laptop-keyboard-3.png)
1. 将 MDT 部署共享的 Windows PE 属性配置为使用新的选择配置文件，如下所示：
    - 对于 **平台**，请选择 **x64**。
    - 对于 **“选择”配置文件**，请选择新配置文件。
    - 从 **选择配置文件中选择“包括所有驱动程序**”。

    ![显示 MDT 部署共享的 Windows PE 属性的图像。](./images/surface-laptop-keyboard-4.png)
4. 使用选择配置文件或 **DriverGroup001** 变量验证是否已配置剩余Surface Laptop驱动程序。
    - 对于Surface Laptop (第一代) ，模型**Surface Laptop**。 其余Surface Laptop驱动程序应位于 \MDT Deployment Share\Out-Box Drivers\Windows10\X64\Surface Laptop 文件夹中，如下图所示。
    - 对于Surface Laptop 2，模型**Surface Laptop 2**。 其余Surface Laptop驱动程序应位于 \MDT Deployment Share\Out-Box Drivers\Windows10\X64\Surface Laptop 2 文件夹中。
    - 对于使用 Intel 处理器的 Surface Laptop 3，模型Surface Laptop 3。 其余Surface Laptop驱动程序位于 \MDT Deployment Share\Out-Box Drivers\Windows10\X64\Surface Laptop 3 文件夹中。

    ![显示 Deployment Workbench Surface Laptop 文件夹中第一代) 驱动程序的常规Surface Laptop (图像。](./images/surface-laptop-keyboard-5.png)

将 MDT 部署共享配置为使用新的选择配置文件和相关设置后，继续执行部署过程，如[使用 MDT 部署Windows 10映像中所述：步骤 6：创建部署任务序列](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)。

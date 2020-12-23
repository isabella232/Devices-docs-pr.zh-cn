---
title: 如何在 MDT 部署期间启用 Surface Laptop 键盘
description: 当你使用 MDT 将 Windows 10 部署到 Surface 笔记本电脑时，你需要导入键盘驱动程序以在 Windows PE 环境中使用。
keywords: windows 10 surface， 自动化， 自定义， mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247304"
---
# 如何在 MDT 部署期间启用 Surface Laptop 键盘

本文介绍使用 Microsoft Deployment Toolkit (MDT) 。 您还可以将此信息应用于其他部署方法。 在大多数类型的 Surface 设备上，键盘应在 Lite Touch Installation (LTI) 。 但是，Surface Laptop 需要一些额外的驱动程序才能启用键盘。 对于 Surface Laptop (第一代) 和 Surface Laptop 2 设备，必须准备文件夹结构和选择配置文件，以允许你指定在 LTI 的 Windows 预安装环境 (Windows PE) 阶段使用的键盘驱动程序。 有关此文件夹结构的信息，请参阅使用 [MDT 部署 Windows 10 映像：步骤 5：准备驱动程序存储库](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。


> [!IMPORTANT]
> 如果要将 Windows 10 映像部署到已预安装 S 模式下的 Windows 10 的 Surface Laptop，请参阅 KB [4032347，](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)将 Windows 部署到在 S 模式下预安装 Windows 10 的 Surface 设备时出现问题。

若要将键盘驱动程序添加到选择配置文件，请按照以下步骤操作：

1. 从相应位置下载最新的 Surface Laptop MSI 文件：
    - [Surface Laptop (第一代) 驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=57515)
    - [带 Intel 处理器驱动程序和固件的 Surface Laptop 3](https://www.microsoft.com/download/details.aspx?id=100429)

2. 将 Surface Laptop MSI 文件的内容解压缩到一个文件夹， (例如 c：\surface_laptop_drivers) 。 若要提取内容，请打开提升的命令提示符窗口并运行以下示例中的命令：

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. 打开部署工作台，展开"部署共享****"节点和部署共享，然后导航到**WindowsPEX64**文件夹。

   ![显示 WindowsPEX64 文件夹在部署工作台中的位置的图像](./images/surface-laptop-keyboard-1.png)

4. 右键单击**WindowsPEX64**文件夹，然后选择 **"导入驱动程序"。**
5. 按照导入驱动程序向导中的说明将驱动程序文件夹导入到 WindowsPEX64 文件夹中。  

> [!NOTE]
>  检查下载的 MSI 程序包以确定格式和目录结构。  目录结构将首先使用 SurfacePlatformInstaller (较旧的 MSI 文件) 或 SurfaceUpdate (较新的 MSI 文件) 具体取决于 MSI 的发布时间。 

若要支持 Surface Laptop (第一代) ，请导入以下文件夹：

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\SurfaceHidMiniDriver
- SurfaceUpdate\SurfaceSerialHubDriver
- SurfaceUpdate\Itouch

若要支持 Surface Laptop 2，请导入以下文件夹：

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\I2C
 - SurfacePlatformInstaller\Drivers\System\SPI
 - SurfacePlatformInstaller\Drivers\System\UART
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
若要使用 Intel 处理器支持 Surface Laptop 3，请导入以下文件夹：

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

导入以下文件夹将在 PE 中为 Surface Laptop 3 启用完整的键盘、触控板和触摸功能。

- IclSerialIOGPIO
- IclSerialIOI2C
- IclSerialIOSPI
- IclSerialIOUART
- itouch
- IclChipset
- IclChipsetLPSS
- IclChipsetNorthpeak
- ManagementEngine
- SurfaceAcpiNotify
- SurfaceBattery
- SurfaceDockIntegration
- SurfaceHidMini
- SurfaceHotPlug
- SurfaceIntegration
- SurfaceSerialHub
- SurfaceService
- SurfaceStorageFwUpdate


    > [!NOTE]
    >  检查下载的 MSI 程序包以确定格式和目录结构。  目录结构将首先使用 SurfacePlatformInstaller (较旧的 MSI 文件) 或 SurfaceUpdate (较新的 MSI 文件) 具体取决于 MSI 的发布时间。 

    若要支持 Surface Laptop (第一代) ，请导入以下文件夹：

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    若要支持 Surface Laptop 2，请导入以下文件夹：

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    或者对于以"SurfaceUpdate"开头的较新的 MSI 文件，请使用：

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    若要使用 Intel 处理器支持 Surface Laptop 3，请导入以下文件夹：

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > 对于带 Intel 处理器的 Surface Laptop 3，型号为 Surface Laptop 3。 其余的 Surface Laptop 驱动程序位于 \MDT 部署共享\开箱即用驱动程序\Windows10\X64\Surface Laptop 3 文件夹中。

6. 验证 WindowsPEX64 文件夹现在是否包含导入的驱动程序。 该文件夹应类似于以下内容：  

   ![显示部署工作台的 WindowsPEX64 文件夹中新导入的驱动程序的图像](./images/surface-laptop-keyboard-2.png)

7. 配置使用 WindowsPEX64 文件夹的选择配置文件。 选择配置文件应类似于以下内容：  

   ![显示选择配置文件的一部分选择的 WindowsPEX64 文件夹的图像](./images/surface-laptop-keyboard-3.png)

8. 配置 MDT 部署共享 Windows PE 属性以使用新的选择配置文件，如下所示：  

   - 对于 **平台**，选择 **x64**。
   - 对于 **"选择"** 配置文件，选择新配置文件。
   - Select **Include all drivers from the selection profile.**
   
   ![显示 MDT 部署共享 Windows PE 属性的图像](./images/surface-laptop-keyboard-4.png)

9. 使用选择配置文件或 **DriverGroup001** 变量验证是否配置了其余的 Surface Laptop 驱动程序。  
   - 对于 Surface Laptop (第一代) ，型号为**Surface Laptop。** 其余的 Surface Laptop 驱动程序应位于 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 文件夹中，如此列表后图所示。
   - 对于 Surface Laptop 2，型号为**Surface Laptop 2。** 其余的 Surface Laptop 驱动程序应位于 \MDT 部署共享\开箱即用驱动程序\Windows10\X64\Surface Laptop 2 文件夹中。 
   - 对于带 Intel 处理器的 Surface Laptop 3，型号为 Surface Laptop 3。 其余的 Surface Laptop 驱动程序位于 \MDT 部署共享\开箱即用驱动程序\Windows10\X64\Surface Laptop 3 文件夹中。

   ![显示部署工作台的 Surface Laptop 文件夹中的常规 Surface Laptop (第一代) 驱动程序的图像](./images/surface-laptop-keyboard-5.png)

将 MDT 部署共享配置为使用新的选择配置文件和相关设置后，继续部署过程，如使用 MDT 部署 Windows 10 映像中所述：步骤 [6：创建部署任务序列](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)。

---
title: 如何在 MDT 部署期间启用 Surface 笔记本电脑键盘
description: 使用 MDT 将 Windows 10 部署到 Surface 笔记本电脑时，需要导入键盘驱动程序以在 Windows PE 环境中使用。
keywords: windows 10 surface，自动化，自定义，mdt
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
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830791"
---
# 如何在 MDT 部署期间启用 Surface 笔记本电脑键盘

本文讨论使用 Microsoft 部署工具包（MDT）的部署方法。 你还可以将此信息应用到其他部署方法。 在大多数类型的 Surface 设备上，键盘应在 "精简触控安装（LTI）" 期间工作。 但是，Surface 膝上型电脑需要其他一些驱动程序才能启用键盘。 对于 Surface 笔记本电脑（第1代）和 Surface 膝上型电脑2设备，你必须准备文件夹结构和选择配置文件，以便你可以指定在 LTI 的 Windows 预安装环境（Windows PE）阶段使用的键盘驱动程序。 有关此文件夹结构的详细信息，请参阅[使用 MDT 部署 Windows 10 映像：步骤5：准备驱动程序存储库](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。

> [!NOTE]
> 由于驱动程序冲突，当前不支持在同一 Windows PE 启动实例中添加 Surface 笔记本2和 Surface 笔记本3键盘驱动程序。请改用单独的实例。

> [!IMPORTANT]
> 如果你要将 Windows 10 映像部署到具有预装了 Windows 10 的 S 模式的 Surface 笔记本电脑，请参阅 KB [4032347，使用预安装的 windows 10 s 模式将 windows 部署到 surface 设备时遇到问题](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)。

若要将键盘驱动程序添加到选择配置文件，请按照下列步骤操作：

1. 从相应的位置下载最新的 Surface 笔记本电脑 MSI 文件：
    - [Surface 笔记本电脑（第1代）驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface 膝上型电脑2驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=57515)
    - [带有英特尔处理器驱动程序和固件的 Surface 笔记本电脑3](https://www.microsoft.com/download/details.aspx?id=100429)

2. 将 Surface 膝上型电脑 MSI 文件的内容提取到您可以轻松找到的文件夹（例如，c：\ surface_laptop_drivers）。 若要提取内容，请打开提升的命令提示符窗口，然后运行以下示例中的命令：

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. 打开部署工作台并展开 "**部署共享**" 节点和部署共享，然后导航到 " **WindowsPEX64** " 文件夹。

   ![显示部署工作台中 WindowsPEX64 文件夹位置的图像](./images/surface-laptop-keyboard-1.png)

4. 右键单击 " **WindowsPEX64** " 文件夹，然后选择 "**导入驱动程序**"。
5. 按照导入驱动程序向导中的说明将驱动程序文件夹导入 WindowsPEX64 文件夹。  

> [!NOTE]
>  检查下载的 MSI 程序包以确定格式和目录结构。  目录结构将从 SurfacePlatformInstaller （较旧的 MSI 文件）或 SurfaceUpdate （较新的 MSI 文件）开始，具体取决于发布 MSI 的时间。 

若要支持 Surface 笔记本电脑（第一代），请导入以下文件夹：

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

或者对于以 "SurfaceUpdate" 开头的较新 MSI 文件，请使用：

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\SurfaceHidMiniDriver
- SurfaceUpdate\SurfaceSerialHubDriver
- SurfaceUpdate\Itouch

若要支持 Surface 膝上型电脑2，请导入以下文件夹：

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\I2C
 - SurfacePlatformInstaller\Drivers\System\SPI
 - SurfacePlatformInstaller\Drivers\System\UART
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

或者对于以 "SurfaceUpdate" 开头的较新 MSI 文件，请使用：

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
若要通过英特尔处理器支持 Surface 笔记本电脑3，请导入以下文件夹：

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

导入以下文件夹将在 Surface 笔记本电脑3的 PE 中启用全键盘、触控板和触摸功能。

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
    >  检查下载的 MSI 程序包以确定格式和目录结构。  目录结构将从 SurfacePlatformInstaller （较旧的 MSI 文件）或 SurfaceUpdate （较新的 MSI 文件）开始，具体取决于发布 MSI 的时间。 

    若要支持 Surface 笔记本电脑（第一代），请导入以下文件夹：

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    或者对于以 "SurfaceUpdate" 开头的较新 MSI 文件，请使用：

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    若要支持 Surface 膝上型电脑2，请导入以下文件夹：

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    或者对于以 "SurfaceUpdate" 开头的较新 MSI 文件，请使用：

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    若要通过英特尔处理器支持 Surface 笔记本电脑3，请导入以下文件夹：

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > 对于带有英特尔处理器的 Surface 笔记本电脑3，型号是 Surface 笔记本电脑3。 剩余 Surface 笔记本电脑驱动程序位于 "\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 笔记本 3" 文件夹中。

6. 验证 WindowsPEX64 文件夹现在是否包含导入的驱动程序。 该文件夹应如下所示：  

   ![显示部署工作台的 WindowsPEX64 文件夹中新导入的驱动程序的图像](./images/surface-laptop-keyboard-2.png)

7. 配置使用 WindowsPEX64 文件夹的选择配置文件。 选择配置文件应类似于以下内容：  

   ![显示选定为选择配置文件一部分的 WindowsPEX64 文件夹的图像](./images/surface-laptop-keyboard-3.png)

8. 将 MDT 部署共享的 Windows PE 属性配置为使用新的选择配置文件，如下所示：  

   - 对于 "**平台**"，选择 " **x64**"。
   - 对于 "**选择配置文件**"，选择新的配置文件。
   - **从选择配置文件中选择 "包括所有驱动程序"**。
   
   ![显示 MDT 部署共享的 Windows PE 属性的图像](./images/surface-laptop-keyboard-4.png)

9. 通过使用选择配置文件或**DriverGroup001**变量，验证是否已配置了剩余 Surface 笔记本电脑驱动程序。  
   - 对于 Surface 笔记本电脑（第1代），模型为**Surface 膝上型电脑**。 剩余 Surface 笔记本电脑驱动程序应位于 \MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型电脑文件夹中，如下图所示。
   - 对于 Surface 笔记本电脑2，型号是**Surface 膝上型电脑 2**。 剩余 Surface 笔记本电脑驱动程序应位于 "\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 笔记本 2" 文件夹中。 
   - 对于带有英特尔处理器的 Surface 笔记本电脑3，型号是 Surface 笔记本电脑3。 剩余 Surface 笔记本电脑驱动程序位于 "\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 笔记本 3" 文件夹中。

   ![显示部署工作台的 "Surface 笔记本" 文件夹中的常规 Surface 笔记本电脑（第1代）驱动程序的图像](./images/surface-laptop-keyboard-5.png)

将 MDT 部署共享配置为使用新的选择配置文件和相关设置后，请按照使用 MDT 部署 Windows 10 映像中的说明继续执行部署过程[：步骤6：创建部署任务序列](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)。

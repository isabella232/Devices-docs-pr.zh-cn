---
title: 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 在 Surface Hub 2 上迁移并安装 Windows 10 专业版或企业版。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/01/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 7198fd3f18a160a0a50f46d270997e4fb4c03b3c
ms.sourcegitcommit: a828853f227b2eda75f904792f7763dc581e9931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10991023"
---
# 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版

## 简介

Surface Hub 2 是预安装的 Windows 10 团队，它是 Windows 10 的自定义版本，旨在促进会议室环境轻松协作。 现在，你可以选择运行 Windows 10 专业版或企业版来使用 Surface Hub 2，与任何其他电脑非常相似。 

从 Windows 10 团队开始迁移，使用单独的 PC 和可下载的工具 **SURFACE UEFI 配置** 器-创建包含应用于 Surface Hub 2 的新 UEFI 设置的包。  Surface UEFI 配置器充当 Surface Enterprise 管理模式 (SEMM) 的接口，旨在促进对公司环境中 Surface 设备上的固件设置的集中管理。 若要了解有关 SEMM 的详细信息，请参阅 [Microsoft Surface 企业管理模式文档](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。
 

## 解决方案组件
- 运行 Windows 10 协同操作系统的 Surface Hub 2 版设备
- 运行 Windows 10 的单独设备
- Surface UEFI 配置工具
- Windows 10 专业版或企业版操作系统映像版本1903或更高版本
- 具有存储空间、FAT32 格式的两个 USB 驱动器
- 适用于 Surface Hub 2、Windows Installer 的 Windows 10 专业版和企业版的驱动程序和固件。MSI 文件
- Internet 连接
- 图像处理解决方案 (可选) 

 
## 迁移工作流摘要

| 步骤  | 操作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| raid-1 | [验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | 确保 UEFI 版本为694.2938.768.0 或更高版本。                                                                                                                                                                                                                                                                                                                                                      |
| ppls-2 | [下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 从 Surface Tools 下载 [SURFACE UEFI 配置](https://www.microsoft.com/download/details.aspx?id=46703) 器，并在单独的 PC 上安装它。 下载 [适用于 Surface Hub 2 上的 Windows 10 专业版和企业版的驱动程序和固件。MSI 文件](https://www.microsoft.com/download/details.aspx?id=101974) 并将其保存，以便在步骤5中使用。 |
| 三维空间 | [准备 SEMM 证书](#prepare-semm-certificate)                                                                          | 准备运行 Surface UEFI 配置器所需的证书或使用您的当前证书。                                                                                                                                                                                                                                                                                                      |
| 第 | [创建 SEMM 程序包](#create-semm-package)                                                                               | 启动 Surface UEFI 配置器在 USB 驱动器上创建 SEMM 程序包，其中将包含 Surface Hub 2 上应用的必需配置文件。 将这些 SEMM 软件包文件复制到电脑上的某个文件夹中。                                                                                                                                                                                          |
| 级 | [准备 USB 闪存驱动器，其中包含适用于 windows 10 的 Windows 10 映像、SEMM 程序包以及适用于 Surface Hub 2 的 Windows 10 专业版和企业版的驱动程序和固件](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 在此示例中创建一个 (名为 **BOOTME** 的单个 USB 驱动器，) 包含 Windows 10 图像。 将 Windows 10 专业版和企业版的驱动程序和固件添加到 Surface Hub 2 (步骤 2) 和 SEMM 软件包文件 (步骤 4) 到 **BOOTME** 驱动器。                                                                                                                                                                                                  |
| 型 | [更新 Surface Hub 2 的 UEFI 以启用操作系统迁移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用 **BOOTME** 驱动器将 Surface Hub 2 启动到 UEFI 菜单并安装 SEMM 程序包。|
| 7 | [安装 Windows 10 专业版或企业版1903或更高版本](#install-windows-10-pro-or-enterprise)                                        | 使用 **BOOTME** 驱动器安装 **Windows 10 专业版或企业** 版1903或更高版本。                                                                                                                                                                                                                                                                                 |
| 个 | [为 Surface Hub 2 上的 Windows 10 专业版和企业版安装驱动程序和固件](#install-surface-hub-2-drivers-and-firmware)                                        | 为确保你的设备具有所有最新的更新和驱动程序，请安装 [Surface Hub 2 上的 Windows 10 专业版和企业版的驱动程序和固件。MSI 文件 ( https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                  |[
## 验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求

将 Surface Hub 从 Windows 10 团队迁移到 Windows 10 桌面之前所需的最低 UEFI 版本是 **694.2938.768.0**。
 
**要验证系统上的当前 UEFI 版本，请执行以下操作：**

1. 在 Surface Hub 2 主屏幕上，选择 "**开始**"，然后打开 " **SurfaceApp** (**所有应用**  >  **Surface** ") 。
2. 选择 **你的图面** 以显示 surface Hub 的相关信息，包括设备上的当前版本。 如果 UEFI 版本为 **694.2938.768.0** 或更高版本，如下所示，则 UEFI 有资格创建 SEMM 程序包以启用操作系统迁移。<br><br>
 ![打开 Surface App & 选择你的 Surface](images/shm-fig1.png)<br><br>
1. 如果 UEFI 版本早于版本694.2938.768.0，你将需要使用 Windows 更新获取当前版本。

**要从 Windows 更新更新 UEFI，请执行以下操作：**
1. 在 Surface Hub 2，以**管理员**身份登录，转到 "**所有应用**  >  **设置**" >  **更新和安全**  >  **Windows 更新**并安装所有更新，然后重新启动设备。 使用 Surface App 验证 UEFI 版本。 注意：如果您不知道您的用户名或管理员密码，您将需要重置设备。 若要了解详细信息，请参阅 [重置和恢复 Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)2。
2. 重复这些步骤，直到 UEFI 版本为 **694.2938.768.0** 或更高版本。
3. 如果在多次尝试后仍然看不到已更新的 UEFI，请检查 " **更新历史记录** " 并查找任何失败的固件安装实例。 你可能需要重置设备 (**设置**  >  **更新 & 安全**  >  **重置设备**) 。

### 下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件

在单独的 PC 上：

- 从 "Surface 工具" 下载并安装 Microsoft [SURFACE UEFI 配置](https://www.microsoft.com/download/details.aspx?id=46703) 器。 Surface UEFI 配置程序不能在 Surface Hub 2-2 上运行，而是安装了 Windows 10 团队。
- 下载 [Surface Hub 2 驱动程序和固件 Windows 安装程序。](https://www.microsoft.com/download/details.aspx?id=101974) 安装新操作系统时要应用的 MSI 文件。

### 准备 SEMM 证书

如果这是你第一次使用 Surface UEFI 配置器，你将需要准备证书。 此证书确保在 SEMM 中注册设备后，只能使用使用已批准的证书创建的程序包来修改 UEFI 设置。 获取证书的方式可能会有所不同，具体取决于组织的规模或复杂程度：

- 大型企业组织通常会保留自己的证书基础结构，以基于标准安全做法生成证书。
- 中型企业和其他人可以选择从第三方提供商处获取证书。 对于没有足够 IT 专业知识或专门 IT 安全团队的组织，推荐使用此选项。
- 或者，你可以使用以下文档的 PowerShell 脚本生成自签名证书： [Surface Enterprise 管理模式证书要求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。 或使用 PowerShell 创建你自己的证书，每个文档： [new-selfsignedcertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps)。

必须使用证书对 SEMM 程序包进行保护，才能验证配置文件的签名，然后才能应用 UEFI 设置。 若要了解详细信息，请参阅 [Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 文档。
 
 
### 创建 SEMM 程序包

1. 打开 **SURFACE UEFI 配置** 器，然后选择 " **开始**"。<br><br>
 ![开放式 Surface UEFI 配置器](images/shm-fig2.png)<br><br>
2. 选择 " **Surface 设备** "，然后选择 " **下一步**"。 <br><br>
  ![选择 Surface 设备](images/shm-fig3.png)<br><br>
  
3. 选择 " **配置包**"。<br><br>
 ![选择配置包](images/shm-fig4.png)<br><br> 
  
4. 选择 " **证书保护**"。<br><br>
  ![选择证书保护](images/shm-fig5.png)<br><br>

5. 系统将提示您添加证书 .pfx 文件。 <br><br> 
  ![系统将提示您添加证书](images/shm-fig6.png)<br><br>
6. 输入您的 **证书密码** ，然后选择 **"确定"**。<br><br> 
  ![输入你的证书密码，然后选择 "确定"](images/shm-fig7.png)<br><br>

7. 选择 " **密码保护** " 以将密码添加到 Surface UEFI。 当您启动到 UEFI 时，将需要此密码。 **强烈建议**设置你将在 Surface Hub 2 秒使用的 UEFI 密码。<br><br>   
![单击 "密码保护"](images/shm-fig8.png)<br><br>
8. 设置 **UEFI 密码** ，然后选择 **"确定"**。<br><br> 
 ![输入你的 UEFI 密码](images/shm-fig9.png)<br><br>

> [!IMPORTANT]
> 记下您的密码。 如果忘记或丢失密码，则不会恢复过程。 


9. 选择 **Surface Hub** 2-2，然后选择 " **下一步**"。<br><br>
 ![选择 Surface Hub 2](images/shm-fig10.png)<br><br>
10. 选择**下一步** 。<br><br>
 ![选择 "下一步"](images/shm-fig10a.png)<br><br>
11. 若要允许安装 Windows 10 专业版或企业版，请选择 " **EnableOsMigration"。**<br><br>
 ![选择 "启用 OS 迁移"](images/shm-fig11.png)<br><br>
12. 将 **EnableOSMigration** 设置为 **"打开"** 并选择 " **下一步**"。<br><br>
 ![将 "启用 OS 迁移" 设置为 "开"](images/shm-fig12.png)<br><br>

> [!NOTE]
> 应用 SEMM 程序包后，所有 UEFI 设置将显示为灰色 (在设备上的 UEFI 菜单中已锁定) 。 这包括其他设置（如用于 PXE 启动的 IPv6）的默认值。 若要修改 UEFI 设置，你将需要应用另一个 SEMM 程序包或从 SEMM 取消注册设备。

#### 将 SEMM 软件包保存到 USB 驱动器

1. 将 USB 驱动器连接到电脑。 选择 " **中心** 2"，然后选择 " **下一步**"。 <br><br>
![选择 "USB](images/shm-fig13.png)<br><br>
2. 选择 " **生成"。**<br><br>
![选择 "生成"](images/shm-fig14.png)<br><br>
3. 捕获此页面的屏幕截图，然后选择 " **结束**"。 你的 SEMM 程序包现已准备就绪，包含 SEMM 程序包 **DfciUpdate. dfi** 和 SEMM 指纹的文本文件 (证书的指纹) 的最后两个字符。<br><br>
 ![选择结束](images/shm-fig15.png)<br><br>
 4. 保存证书指纹的最后2个字符，当你在 Surface Hub 2 上应用包时，激活 SEMM 需要该字符。

### 准备包含 Windows 10 映像、SEMM 程序包和 Surface Hub 2 驱动程序和固件的 USB 闪存驱动器

你可以使用以下选项之一 (版本1903或更高版本) 安装 Windows 10 专业版或企业版映像：

- 当前的图像处理解决方案。
- [Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) 允许创建可启动的 windows 10 映像，其中包括所有当前 Windows 10 更新、Office、你选择的其他应用以及所需的驱动程序和固件。 
- 带有 Windows 10 专业版或企业版映像的 USB 闪存驱动器，然后安装了  [适用于 Surface Hub 2 的 windows 10 专业版和企业版的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。
 

此过程介绍如何从安装媒体创建一个 USB 闪存驱动器，然后添加 SEMM 软件包文件和适用于 Surface Hub 2 的 Windows 10 专业版和企业版的驱动程序和固件。MSI 文件。 如果你使用的是其他部署方法，请转到以下部分： [更新 Surface Hub 2 上的 UEFI 以启用操作系统迁移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)。

> [!NOTE]
> 安装后，你将需要适用于 Windows 10 专业版或 Windows 10 企业版的有效许可证。

1. 若要创建 Windows 10 专业版安装，请按照 [下载 windows 10](https://www.microsoft.com/software-download/windows10) 页面上的说明使用 **媒体创建** 工具。 若要下载 Windows 10 企业版，请转到 [Microsoft 批量许可服务中心。](https://www.microsoft.com/licensing/servicecenter/default.aspx)
2. 插入新的 **USB 存储** 驱动器。 启动 " **媒体创建** " 工具，选择 " **创建安装媒体** "，然后选择 " **下一步**"。<br><br>
 ![创建安装媒体](images/shm-fig16.png)<br><br>
3. 选择 "语言"、"Windows 10" 和 "64 (x64") 然后选择 " **下一步**"。<br><br>
 ![选择 "语言"、"Windows 10" 和 "64 位 & 选择" 下一步 "](images/shm-fig17.png)<br><br>
4. 选择 " **USB 闪存驱动器** "，然后选择 " **下一步**"。<br><br>
 ![选择 "USB 闪存驱动器"，然后选择 "下一步"](images/shm-fig18.png)<br><br>
5. 下载完成后，选择 " **完成**"。<br><br>
 ![选择 "完成"](images/shm-fig19.png)<br><br>
6. 在 Surface Hub 2 上复制 Windows 10 专业版和企业版的 SEMM 软件包文件和驱动程序和固件。MSI 到 USB 闪存驱动器 (**BOOTME**) 包含你的 Windows 10 映像：
    - DfciUpdate.dfi
    - 带有 SEMM 指纹的文本文件。 此示例中的 (： SurfaceUEFI_2020Aug25_1058.txt) 
    - Surface Hub 2 上的 Windows 10 专业版和企业版的驱动程序和固件 ( # A0) 

### 更新 Surface Hub 2 的 UEFI 以启用操作系统迁移

使用 **BOOTME** 驱动器安装 SEMM 程序包文件并更新 UEFI，从而使 Surface Hub 能够运行 Windows 10 专业版或企业版。 然后从 **BOOTME** 驱动器启动以安装 Windows 10。

1. 插入 **BOOTME** 驱动器，其中包含适用于 Surface Hub 2 上的 Windows 10 专业版和企业版的 SEMM 程序包文件、驱动程序和固件。MSI 和 Windows 10 在 Surface Hub 2 的 USB 端口上安装文件。  
2. 要启动到 UEFI，请执行以下操作：
    1. 第一次关闭) Surface Hub 2 (关闭的电源。
    2. 按住 " **音量 +** "，然后按下并松开 " **电源** " 按钮。
    3. 继续保持 **音量 +** ，直到 UEFI 菜单出现。<br><br>
     ![保留 holdling 的音量 +，直到 UEFI 菜单出现](images/shm-fig20.png)<br><br>
3. 重新启动设备时，输入你之前创建的 UEFI 密码（如果适用 (强烈建议) ）。<br><br>
 ![当设备重新启动时，请输入 UEFI paassword](images/shm-fig22.png)<br><br>
4. 在 UEFI 菜单中，选择**Management**"  >  **从 USB 安装**管理"。<br><br>
 ![选择 "管理 & 从 USB 安装"](images/shm-fig21.png)<br><br>
5. 选择 " **立即重启**"，如下所示。 设备将关闭。<br><br>
 ![选择 "立即重启"](images/shm-fig25.png)<br><br>
6. 按下并释放 "电源" 按钮，将显示一个红色屏幕，提示你激活 Surface Enterprise 管理模式。 
7. 输入你的两个字符的 **证书指纹**，你的 **UEFI 设置密码** ，然后选择 **"确定"**。<br><br>
 ![输入2个字符的证书指纹](images/shm-fig23.png)<br><br>  
8. 设备将重新启动，在屏幕中间显示白色4方块，然后再次关闭。

### 安装 Windows 10 专业版或企业版

1. 如果可启动的 Windows 10 专业版或企业版驱动器尚未插入 Surface Hub 2 USB-A 端口，请立即插入，然后按下并释放电源按钮。
2. 设备将启动，你将在屏幕的中间看到白色的4方块，然后你将在白色的四个方形徽标下方看到旋转圆
3. 如果设备不会自动启动到 USB 驱动器，请关闭设备 (拔出电源线，然后再将其插入) 中，按下并释放 "电源" 按钮，然后按住 "音量" 按钮，直到看到位于白色四个正方形徽标下方的旋转圆圈。 <br><br>
 ![从 USB 启动到 Windows 10](images/shm-fig26.png)<br><br>
4. 当 (OOBE) 安装程序启动时，请按照说明安装 Windows 10 专业版或企业版 (版本1903或更高版本) 。

### 安装 Surface Hub 2 驱动程序和固件

1.  为确保你的设备具有所有最新的更新和驱动程序，请安装 [适用于 Surface Hub 2 的 Windows 10 专业版和企业版的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。
 
### 后续步骤

若要优化 Surface Hub 2 的使用作为个人生产力设备，请参阅 [安装了 Surface hub 2 安装后配置的 Windows 10](surface-hub-2-post-install.md)。
> [!NOTE]
>如果按照本文档中概述的步骤将设备迁移到 Windows 10 Pro 或 Enterprise for Surface Hub 2，请联系 [Surface Hub 支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。


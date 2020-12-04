---
title: 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文介绍如何从 Surface Hub 2 上的 Windows 10 团队迁移到 Windows 10 Pro 或 Windows 10 企业版。
keywords: Surface Hub 桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/03/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 01c5c8a5c6b9f7ed657829fe792fc9eecd1facb5
ms.sourcegitcommit: 5d02cca9ca8c0a252798c2fc0a89dbda81911c44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195397"
---
# 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版

Surface Hub 2 预装了 Windows 10 团队。 此自定义版本的 Windows 10 旨在促进会议室环境中的协作。 现在，你可以选择运行 Windows 10 专业版或企业版来使用 Surface Hub 2，与任何其他电脑非常相似。 

> [!IMPORTANT]
>与典型升级或迁移不同，此过程要求你遵循说明性过程，如本文中所述。 继续之前，请查看 [解决方案组件](#solution-components) 和 [迁移和安装工作流](#migration-and-installation-workflow-summary) 。


> [!NOTE]
> 安装 Windows 10 专业版或企业版时，你需要与现有 Windows 10 团队许可证分开的新许可证。 


通过使用单独的 PC 和可下载的工具 *SURFACE UEFI 配置*器开始从 Windows 10 团队迁移。 使用该工具创建一个程序包，其中包含应用于 Surface Hub 2 的新 UEFI 设置。  

Surface UEFI 配置器在 (SEMM) 的情况下用作 Surface Enterprise 管理模式的接口。 它旨在促进企业环境中 Surface 设备上的固件设置的集中管理。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> MICROSOFT SEMM 文档</a>
 

## 解决方案组件

- 运行 Windows 10 团队操作系统的 Surface Hub 2 设备
- 运行 Windows 10 的单独设备
- 用于创建 SEMM 程序包的 Surface UEFI 配置器工具
- Windows 10 专业版或企业版 OS 映像、版本1903或更高版本
- 具有 16 GB 存储空间的两个 USB 驱动器，FAT32 格式
- Surface Hub 2 Microsoft Windows Installer (MSI) 文件的 Windows 10 专业版和企业版 OS 的驱动程序和固件
- Internet 连接
- 图像处理解决方案 (可选) 

 
## 迁移和安装工作流摘要

| 步骤  | 操作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| raid-1 | [验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求。](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | 确保 UEFI 版本为694.2938.768.0 或更高版本。                                                                                                                                                                                                                                                                                                                                                      |
| ppls-2 | [下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件。](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 在 " <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **Surface TOOLS for IT** " 页面上 </a> ，选择 "**下载**"。 然后选择并下载 **SURFACE UEFI 配置器。MSI 文件** 并将其安装在单独的 PC 上。 下载 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 MSI 文件上的 Windows 10 专业版和企业版操作系统的驱动程序和固件。</a> 将其保存为在步骤5中使用。 |
| 三维空间 | [准备 SEMM 证书。](#prepare-the-semm-certificate)                                                                          | 准备运行 Surface UEFI 配置器所需的证书。 或使用您当前的证书。                                                                                                                                                                                                                                                                                                      |
| 第 | [创建 SEMM 程序包。](#create-a-semm-package)                                                                               | Start Surface UEFI 配置器在 USB 驱动器上创建 SEMM 程序包，它将包含你需要在 Surface Hub 2 上应用的配置文件。 将这些 SEMM 软件包文件复制到电脑上的某个文件夹中。                                                                                                                                                                                          |
| 级 | [准备 USB 闪存驱动器，其中包含适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的 Windows 10 映像、SEMM 软件包和驱动程序和固件。](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 创建包含 Windows 10 映像的单个 USB 驱动器。 在此示例中，驱动器名为 *BOOTME*。 将 Windows 10 专业版和企业操作系统的驱动程序和固件添加到 Surface Hub 2 (步骤 2) 和 SEMM 软件包文件 (步骤 4) 到 *BOOTME* 驱动器。                                                                                                                                                                                                  |
| 型 | [更新 Surface Hub 2 的 UEFI 以启用操作系统迁移。](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用 *BOOTME* 驱动器将 Surface Hub 2 启动到 UEFI 菜单并安装 SEMM 程序包。|
| 7 | [安装 Windows 10 专业版或企业版1903或更高版本。](#install-windows-10-pro-or-enterprise)                                        | 使用 *BOOTME* 驱动器安装 Windows 10 专业版或企业版1903或更高版本。                                                                                                                                                                                                                                                                                 |
| 个 | [为 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统安装驱动程序和固件。](#install-surface-hub-2-drivers-and-firmware)                                        | 为确保你的设备具有所有最新的更新和驱动程序，请 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 MSI 文件上安装 Windows 10 专业版和企业版操作系统的驱动程序和固件。</a>                                                                                                                                                                                                                                                                                  |
| db-9 | [将 Surface Hub 2 完全配置为个人工作效率设备。](#configure-recommended-settings)                                        |  启用推荐的设置和应用程序以优化 Surface Hub 2 作为个人工作效率设备。                                                                                                                                                                                                                                                                    |

### 验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求

在将 Surface Hub 从 Windows 10 团队迁移到 Windows 10 桌面版之前，你需要一个至少 *694.2938.768.0*的 UEFI 版本。
 
**要在系统上验证 UEFI 版本，请执行以下操作：**

1. 在 "Surface Hub 2" 主页上，选择 "**开始**"，然后在 "**所有应用**"  >  **图面**) 中打开 Surface app (。

2. 选择 **你的图面** 以显示 surface Hub 的相关信息，包括设备上的当前 UEFI 版本。 
   - 如果 UEFI 版本为 *694.2938.768.0* 或更高版本，如下图所示，你可以创建 SEMM 程序包以启用 OS 迁移。

       ![显示 Surface 应用中的 Surface 页面的屏幕截图。](images/shm-fig1.png)
 
   - 如果 UEFI 版本早于版本694.2938.768.0，你将需要获取最新版本，方法是安装 Window 10 Team 2020 更新裸机恢复 (BMR) 映像或使用 Windows 更新。
   
**要通过 Windows 更新更新 UEFI，请执行以下操作：**

1. 在 Surface Hub 2 秒内，以 **管理员身份**登录。 
    >[!Note]
    > 如果您不知道您的用户名或管理员密码，则需要重置设备。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> 重置和恢复 Surface Hub 2。</a>

1. 转到 "**所有应用**  >  **设置**  >  "**更新和安全**  >  **Windows 更新**，然后安装所有更新。 
1. 重新启动设备。 
1. 使用 Surface app 验证 UEFI 版本。 
1. 此时，如果 UEFI 版本尚未版本694.2938.768.0 或更高版本，则可以重复上述步骤，也可以通过安装 Windows 10 Team 2020 更新裸机恢复 (BMR) 映像来获取最新的 UEFI。

**若要通过裸机恢复更新 UEFI (BMR) 映像，请执行以下操作：**

1.  转到 " [surface recovery" 网站](https://support.microsoft.com/surfacerecoveryimage)，然后选择 " **surface Hub** 2"
3.  输入集线器序列号 (位于集线器背面的电源连接旁边。 ) 
4.  通过安装 Windows 10 Team 2020 更新，按照说明将图像下载到格式化的 USB 驱动器上。
5.  更新完成后，设备首次进入 "OOBE" 设置时，不需要完成 OOBE，将更新 UEFI 版本。 请改为关闭设备，方法是按住电源按钮，直到屏幕关闭。 

### 下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件

在单独的 PC 上：

1. 在 " <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools FOR IT" 页面上 </a> ，选择 " **下载**"。  
1. 选择并下载 Surface UEFI 配置器 MSI 文件，并将其安装在单独的电脑上。 安装 Windows 10 团队版时，不能在 Surface Hub 2 上运行 Surface UEFI 配置器工具。

1. 下载 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 驱动程序和固件 Windows INSTALLER MSI 文件 </a> 。 安装新操作系统时，您将使用此文件。

### 准备 SEMM 证书

如果你之前未使用 Surface UEFI 配置器，则需要准备证书。 此证书确保在 SEMM 中注册设备后，只能使用使用已批准的证书创建的程序包修改 UEFI 设置。 

证书的获取方式取决于组织的规模或复杂程度：

- 企业组织通常会保留自己的基础结构，以便根据标准安全做法生成证书。

- 中型企业和其他人可以选择从合作伙伴提供商处获取证书。 对于没有足够 IT 专业知识或专门 IT 安全团队的组织，建议使用此选项。

- 或者，你可以使用 PowerShell 脚本生成自签名证书。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> Surface Enterprise 管理模式证书要求 </a> 。 或者，你可以使用 PowerShell 创建你自己的证书。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> new-selfsignedcertificate </a> 文档。

Surface UEFI 配置器创建的 SEMM 程序包必须使用证书进行保护。 证书验证配置文件的签名，然后才能应用 UEFI 设置。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 文档 </a> 。
 
 
### 创建 SEMM 程序包

1. 在单独的电脑上，安装之前下载的 Surface UEFI 配置工具。 

2. 打开 Surface UEFI 配置器，然后选择 " **开始**"。

   ![开放式 Surface UEFI 配置器。](images/shm-fig2.png)
   
3. 选择 " **Surface 设备**"，然后选择 " **下一步**"。

   ![选择 "Surface 设备"。](images/shm-fig3.png)
  
4. 选择 " **配置包**"。

   ![选择 "配置包"。](images/shm-fig4.png)
  
5. 选择 " **证书保护**"。

   ![选择 "证书保护"。](images/shm-fig5.png)

   系统将提示您添加证书 .pfx 文件。

   ![添加您的证书。](images/shm-fig6.png)
   
7. 输入你的证书密码，然后选择 **"确定"**。

   ![输入您的证书密码，然后选择 "确定"。](images/shm-fig7.png)

8. 选择 " **密码保护** " 以将密码添加到 Surface UEFI。 当您启动到 UEFI 时，您将需要此密码。 *强烈建议*你设置你将在 Surface Hub 2 上使用的 UEFI 密码。

   ![选择 "密码保护"。](images/shm-fig8.png)
   
9. 设置 UEFI 密码，然后选择 **"确定"**。

   > [!IMPORTANT]
   > 将密码保存到管理 Surface Hub 的 IT 管理员可以访问的安全位置。 如果密码丢失，则无法恢复。 

   ![输入 UEFI 密码。](images/shm-fig9.png)

10. 选择 " **Surface Hub**2"，然后选择 " **下一步**"。

    ![选择 Surface Hub 2。](images/shm-fig10.png)
   
11. 选择**下一步** 。

    ![选择下一步 。](images/shm-fig10a.png)

12. 若要允许安装 Windows 10 专业版或企业版，请打开 **EnableOsMigration**，然后选择 " **下一步**"。

    ![选择 "启用 O S 迁移"。](images/shm-fig11.png)
    
    ![将 "启用 OS 迁移" 设置为 "开"。](images/shm-fig12.png)

### 管理 SEMM 注册

将设备注册到 SEMM 会影响你管理未来的设备的方式。 例如，在应用 SEMM 程序包后，在设备的 UEFI 菜单中，所有 UEFI 设置均不可用 ("已锁定") 。 其他设置（如用于 **PXE 启动的 IPv6** ）的默认值也不可用。 

若要在完成迁移后更改 UEFI 设置，请应用另一个 SEMM 程序包或从 SEMM 取消注册设备。 如果你应用另一个 SEMM 程序包以更改 UEFI 设置，则在生成新的 SEMM 程序包时必须使用原始证书。 使用 UEFI 配置器工具，将 **EnableOSMigration** 关闭 (not on，如原始迁移步骤) 所示。

#### 与合作伙伴合作

如果您的公司将迁移迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版，您可能希望让合作伙伴将 SEMM 证书、SEMM 包和 UEFI 密码转让给您。  或者，在迁移中心后，您可以立即取消注册 SEMM，这将允许本地管理 UEFI 并将设备传输到另一方。 但是，强烈建议使用 UEFI 密码，该密码可在迁移后进行配置。 若要了解详细信息，请参阅 [管理 SURFACE UEFI 设置](https://docs.microsoft.com/surface/manage-surface-uefi-settings)。 

#### 回滚到 Windows 10 团队

如果迁移后选择将设备还原到 Windows 10 团队（如下 [所述](#roll-back-to-windows-10-team)），建议首先取消 SEMM 中的集线器注册。 若要了解详细信息，请参阅 [从 SEMM 中取消注册 Surface 设备](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。


#### 将 SEMM 程序包保存到 USB 驱动器

1. 将 USB 驱动器连接到电脑。 
1. 选择 " **中心2秒**"，然后选择 " **下一步**"。

   ![选择 "USB](images/shm-fig13.png)

   > [!WARNING]
   > 当构建 SEMM 软件包时，将擦除 USB 驱动器上的所有现有数据。 在生成 SEMM 程序包之前，请从要保存的 USB 驱动器中删除所有文件。
   
2. 选择“构建”****。

   ![选择“构建”。](images/shm-fig14.png)

3. 捕获此页面的屏幕截图，然后选择 " **结束**"。 您的 SEMM 程序包现已准备就绪。 它包含 SEMM 程序包 *DfciUpdate dfi* 和包含 SEMM 指纹的文本文件 (证书的指纹) 的最后两个字符。

   ![选择 "结束"。](images/shm-fig15.png)
   
4. 保存证书指纹的最后两个字符。 当你在 Surface Hub 2 上应用包时，你将需要以下字符来激活 SEMM。

### 准备一个包含 Windows 10 映像、SEMM 软件包和 Surface Hub 2 驱动程序和固件的 USB 闪存驱动器

你可以使用以下选项之一，将 Windows 10 专业版或企业版映像安装 (版本1903或更高版本) ：

- 当前的图像处理解决方案。

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Surface 部署加速器 </a> 。 使用此工具创建可启动的 Windows 10 映像。 该映像可以包括所有当前 Windows 10 更新、Office、你选择的其他应用以及所需的驱动程序和固件。 

- 包含 Windows 10 专业版或企业版映像的 USB 闪存驱动器。 然后 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 上安装 Windows 10 专业版和企业版操作系统的驱动程序和固件 </a> 。
 
以下过程介绍了如何从安装媒体创建 USB 闪存驱动器，然后在 Surface Hub 2 MSI 文件上添加 Windows 10 专业版和企业操作系统的 SEMM 软件包文件和驱动程序和固件。 如果您使用的是其他部署方法，请转到 [Surface Hub 2 上的更新 UEFI 以启用](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 本文中的操作系统迁移部分。

> [!NOTE]
> 完成安装后，你需要与现有 Windows 10 团队许可证分开的 Windows 10 专业版或 Windows 10 企业版的有效许可证。

1. 若要创建 Windows 10 专业版安装，请在 " <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> 下载 windows 10" </a> 页面上，按照说明下载媒体创建工具。 若要下载 Windows 10 企业版，请转到 <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft 批量许可服务中心 </a> 。

2. 插入新的 USB 存储驱动器。 
1. 打开媒体创建工具，选择 " **创建安装媒体**"，然后选择 " **下一步**"。

   ![创建安装媒体。](images/shm-fig16.png)
   
3. 选择一种语言，然后选择 " **Windows 10** 和 **64 位 (x64) **"。 然后选择 " **下一步**"。

   ![选择 "语言"，然后选择 "Windows 10 和64位"。 然后选择 "下一步"。](images/shm-fig17.png)
   
4. 选择 " **USB 闪存驱动器**"，然后选择 " **下一步**"。

   ![选择 "U S B 闪存驱动器"，然后选择 "下一步"。](images/shm-fig18.png)
   
5. 下载完成后，选择 " **完成**"。

   ![选择“完成”。](images/shm-fig19.png)
   
6. 将 SEMM 软件包文件和 Windows 10 专业版的驱动程序和固件复制到 Surface Hub 2 上的 (MSI 文件) 到包含 Windows 10 映像的 USB 闪存驱动器 (*BOOTME*) 的根。 BOOTME USB 驱动器包含：

    - Windows 10 可启动映像。
    
    - SEMM 软件包文件 (复制到 USB 驱动器) 的根目录。
    
      - *DfciUpdate dfi*。
      - 包含 SEMM 指纹的文本文件。  (在此示例中，文件 *SurfaceUEFI_2020Aug25_1058.txt*。 ) 自动生成的日期时间戳对应于使用 Surface UEFI 配置器创建文件的日期。

   - Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件 ( # A0) 。 将此文件复制到 USB 驱动器的根目录。

### 更新 Surface Hub 2 的 UEFI 以启用操作系统迁移

1. 将 BOOTME 驱动器插入到 Surface Hub 2 上的 USB 端口。 有关所需文件的列表，请参阅上一节。

2. 要启动到 UEFI，请执行以下操作：

   1. 关闭 Surface Hub 2) 的 (关机。
   1. 按住 " **音量 +**"，然后按下并松开 "电源" 按钮。
   1. 继续保持 **音量 +** ，直到 UEFI 菜单出现。
   
      ![按住调高音量按钮，直到 UEFI 菜单出现。](images/shm-fig20.png)
      
3. 重新启动设备时，输入你之前创建的 UEFI 密码（如果适用 (强烈建议) ）。

   ![输入 UEFI 密码。](images/shm-fig22.png)
   
4. 在 UEFI 菜单中，选择**Management**"  >  **从 USB 安装**管理"。

   ![选择 "管理"，从 U S B 安装。](images/shm-fig21.png)
   
5. 选择 " **立即重启**"，如下图所示。 设备将重新启动。 它将在窗口中间显示白色 Microsoft 徽标，然后关闭。

   ![选择 "立即重启"。](images/shm-fig25.png)
   
6. 按下并释放 "电源" 按钮。 在出现的红色窗口中，激活 Surface Enterprise 管理模式。 

7. 输入两个字符的证书指纹和 UEFI 设置密码。 然后选择 **"确定"**。

   ![输入两个字符的证书指纹和 UEFI 设置密码。](images/shm-fig23.png)
 
   > [!NOTE]
   > 在设备上激活 SEMM 后，将应用新的 UEFI 设置 **EnableOSMigration** 。 您将不能再访问 Windows 10 团队。 而是必须继续下一步，并安装 Windows 10 专业版或 Windows 10 企业版。 

   设备将重新启动。 它显示屏幕中间的白色徽标，然后再次关闭。

### 安装 Windows 10 专业版或企业版

1. 如果可启动的 Windows 10 专业版或企业版驱动器尚不在 Surface Hub 2 USB-A 端口中，请立即插入。 然后按下并释放 "电源" 按钮。 

    当设备启动时，将在屏幕的中间看到白色徽标。 然后，你将在白色徽标下方看到一个旋转圆。

3. 如果设备不会自动启动到 USB 驱动器，请关闭设备 (拔出电源线，然后将其重新插入) 。 再次插入电源线后，设备将在几秒钟后启动。 然后，你将在屏幕中间看到白色徽标。 

    如果设备未打开，请按下并释放 "电源" 按钮。 在屏幕中间看到徽标后，按住 "音量" 按钮，直到看到白色徽标下方的旋转圆圈。
 
   ![从 U S 驱动器启动到 Windows 10。](images/shm-fig26.png)
   
4. 当 (OOBE) 安装程序启动时，请按照说明安装 Windows 10 专业版或企业版 (版本1903或更高版本) 。

### 安装 Surface Hub 2 驱动程序和固件

为确保你的设备具有所有最新的更新和驱动程序，请安装 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件 </a> 。
 
## 配置推荐的设置

若要将 Surface Hub 2 完全配置为个人生产力设备，请参阅 <a href="surface-hub-2-post-install.md" target="_blank"> 在 Surface hub 2 上配置 Windows 10 专业版或企业版 </a> 。

> [!NOTE]
>如果本文中概述的步骤未成功将设备迁移到 Windows 10 Pro 或 Surface Hub 2 的企业版，请联系 <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub 支持 </a> 。

## 回退到 Windows 10 团队

如果你想要将设备还原到 Windows 10 团队，请参阅 <a href="surface-hub-2s-recover-reset.md" target="_blank"> 重置和恢复 Surface Hub 2 </a> 。

> [!NOTE]
> 在回滚到 Windows 10 团队之前，建议首先取消 SEMM 中的集线器注册。 若要了解详细信息，请参阅 [从 SEMM 中取消注册 Surface 设备](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。

## 版本历史记录

下表总结了本文的更改。

| 版本 | 日期               | 描述                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| 视听. 1.3  | 2020年12月3日 | 已更新有关管理 SEMM 注册的指南                                                        |
| 视听. 1.2  | 2020年9月29日 | 解决可用性反馈的各种更新。                                                        |
| 视听. 1.1  | 2020年9月15日 | 在介绍中放置了说明安装新操作系统的许可要求的其他说明。 |
| 视听. 1.0  | 2020年9月1日  | 新文章。                                                                                           |

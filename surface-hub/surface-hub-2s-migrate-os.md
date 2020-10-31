---
title: 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文介绍从 Surface Hub 2 上的 Windows 10 团队迁移到 Windows 10 Pro 或 Windows 10 企业版的过程。
keywords: Surface Hub 桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 12742cc887ba495f8f7cbded8bd84dc4fd63b6f6
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145967"
---
# 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版

## 简介

Surface Hub 2 是预安装的 Windows 10 团队，它是 Windows 10 的自定义版本，旨在促进会议室环境轻松协作。 现在，你可以选择运行 Windows 10 专业版或企业版来使用 Surface Hub 2，与任何其他电脑非常相似。 

> [!IMPORTANT]
>与典型升级或迁移不同，此过程需要遵循说明性过程，如本页所述。 继续之前，请先查看 [解决方案组件](#solution-components) 和 [迁移和安装工作流](#migration-and-installation-workflow-summary) 。


> [!NOTE]
> 安装 Windows 10 专业版或企业版时，你将需要与现有 Windows 10 团队许可证分开的新许可证。 


从 Windows 10 团队开始迁移，使用单独的 PC 和可下载的工具 **SURFACE UEFI 配置** 器-创建包含应用于 Surface Hub 2 的新 UEFI 设置的包。  Surface UEFI 配置器充当 Surface Enterprise 管理模式 (SEMM) 的接口，旨在促进对公司环境中 Surface 设备上的固件设置的集中管理。 若要了解有关 SEMM 的详细信息，请参阅 [Microsoft Surface 企业管理模式文档](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。
 

## 解决方案组件

- 运行 Windows 10 协同操作系统的 Surface Hub 2 版设备。
- 运行 Windows 10 的单独设备。
- 用于创建 SEMM 程序包的 Surface UEFI 配置器工具。
- Windows 10 专业版或企业版操作系统映像版本1903或更高版本。
- 两个 USB 驱动器，其存储空间为 FAT32 格式。
- Surface Hub 2、Windows 安装程序上的 Windows 10 专业版和企业版操作系统的驱动程序和固件。MSI 文件。
- 互联网连接。
- 图像处理解决方案 (可选) 。

 
## 迁移和安装工作流摘要

| 步骤  | 操作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| raid-1 | [验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | 确保 UEFI 版本为 **694.2938.768.0** 或更高版本。                                                                                                                                                                                                                                                                                                                                                      |
| ppls-2 | [下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 选择 " [Surface Tools FOR IT](https://www.microsoft.com/download/details.aspx?id=46703) " 页面上的 "下载" 按钮，选择并下载 **Surface UEFI 配置器。MSI 文件** 并将其安装在单独的 PC 上。 下载 [适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件。MSI 文件](https://www.microsoft.com/download/details.aspx?id=101974) 并将其保存，以便在步骤5中使用。 |
| 三维空间 | [准备 SEMM 证书](#prepare-semm-certificate)                                                                          | 准备运行 Surface UEFI 配置器所需的证书或使用您的当前证书。                                                                                                                                                                                                                                                                                                      |
| 第 | [创建 SEMM 程序包](#create-semm-package)                                                                               | 启动 Surface UEFI 配置器在 USB 驱动器上创建 SEMM 程序包，它将包含要应用于 Surface Hub 2 的必需配置文件。 将这些 SEMM 软件包文件复制到电脑上的某个文件夹中。                                                                                                                                                                                          |
| 级 | [准备 USB 闪存驱动器，其中包含适用于 windows 10 的 Windows 10 映像、SEMM 程序包以及适用于 Surface Hub 2 的 Windows 10 专业版和企业操作系统的驱动程序和固件](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 在此示例中创建一个 (名为 **BOOTME** 的单个 USB 驱动器，) 包含 Windows 10 图像。 将 Windows 10 专业版和企业操作系统的驱动程序和固件添加到 Surface Hub 2 (步骤 2) 和 SEMM 软件包文件 (步骤 4) 到 **BOOTME** 驱动器。                                                                                                                                                                                                  |
| 型 | [更新 Surface Hub 2 的 UEFI 以启用操作系统迁移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用 **BOOTME** 驱动器将 Surface Hub 2 启动到 UEFI 菜单并安装 SEMM 程序包。|
| 7 | [安装 Windows 10 专业版或企业版1903或更高版本](#install-windows-10-pro-or-enterprise)                                        | 使用 **BOOTME** 驱动器安装 **Windows 10 专业版或企业** 版1903或更高版本。                                                                                                                                                                                                                                                                                 |
| 个 | [为 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统安装驱动程序和固件](#install-surface-hub-2-drivers-and-firmware)                                        | 为确保你的设备具有所有最新的更新和驱动程序，请安装 [适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件。MSI 文件](https://www.microsoft.com/download/details.aspx?id=101974)。                                                                                                                                                                                                                                                                                  |
| db-9 | [将 Surface Hub 2 完全配置为个人生产力设备](#next-steps)                                        |  启用推荐的设置和应用程序，优化将 Surface Hub 2 作为个人生产力设备使用。                                                                                                                                                                                                                                                                    |

### 验证 Surface Hub 2 上的 UEFI 版本是否满足最低要求

将 Surface Hub 从 Windows 10 团队迁移到 Windows 10 桌面之前所需的最低 UEFI 版本是 **694.2938.768.0**。
 
**要验证系统上的当前 UEFI 版本，请执行以下操作：**

1. 在 Surface Hub 2 主屏幕上，选择 "**开始**"，然后打开 " **SurfaceApp** (**所有应用**  >  **Surface** ") 。

2. 选择 **你的图面** 以显示 surface Hub 的相关信息，包括设备上的当前 UEFI 版本。 如果 UEFI 版本为 **694.2938.768.0** 或更高版本，如下所示，则 UEFI 有资格创建 SEMM 程序包以启用操作系统迁移。

    ![打开 Surface App & 选择你的 Surface](images/shm-fig1.png)
 
3. 如果 UEFI 版本早于版本 **694.2938.768.0**，你将需要使用 Windows 更新获取当前版本。

**要从 Windows 更新更新 UEFI，请执行以下操作：**

1. 在 Surface Hub 2，以**管理员**身份登录，转到 "**所有应用**  >  **设置**"  >  **更新和安全**  >  **Windows 更新**并安装所有更新，然后重新启动设备。 使用 Surface App 验证 UEFI 版本。 **注意：** 如果您不知道您的用户名或管理员密码，将需要重置设备。 若要了解详细信息，请参阅 [重置和恢复 Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)2。

2. 重复这些步骤，直到 UEFI 版本为 **694.2938.768.0** 或更高版本。

3. 如果在多次尝试后仍然看不到已更新的 UEFI，请检查 " **更新历史记录** " 并查找任何失败的固件安装实例。 你可能需要重置设备 (**设置**  >  **更新 & 安全**  >  **重置设备**) 。

### 下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件

在单独的 PC 上：

- 选择 " [Surface Tools FOR IT" 页面](https://www.microsoft.com/download/details.aspx?id=46703)上的 "下载" 按钮，选择并下载 Surface UEFI 配置器。MSI 文件并将其安装在单独的 PC 上。 安装 Windows 10 团队版时，不能在 Surface Hub 2 上运行 Surface UEFI 配置器工具。

- 下载 [Surface Hub 2 驱动程序和固件 Windows 安装程序。](https://www.microsoft.com/download/details.aspx?id=101974) 安装新操作系统时要应用的 MSI 文件。

### 准备 SEMM 证书

如果这是你第一次使用 Surface UEFI 配置器，你将需要准备证书。 此证书确保在 SEMM 中注册设备后，只能使用使用已批准的证书创建的程序包来修改 UEFI 设置。 获取证书的方式可能会有所不同，具体取决于组织的规模或复杂程度：

- 大型企业组织通常会保留自己的证书基础结构，以基于标准安全做法生成证书。

- 中型企业和其他人可以选择从第三方提供商处获取证书。 对于没有足够 IT 专业知识或专门 IT 安全团队的组织，推荐使用此选项。

- 或者，你可以使用以下文档的 PowerShell 脚本生成自签名证书： [Surface Enterprise 管理模式证书要求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。 或使用 PowerShell 创建你自己的证书，每个文档： [new-selfsignedcertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)。

使用 Surface UEFI 配置工具创建的 SEMM 包必须通过证书进行保护，才能验证配置文件的签名，然后才能应用 UEFI 设置。 若要了解详细信息，请参阅 [Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 文档。
 
 
### 创建 SEMM 程序包

1. 将 **SURFACE UEFI 配置** 器工具（如前面已下载的）安装到单独的 PC。 

2. 打开 **SURFACE UEFI 配置** 器，然后选择 " **开始**"。

   ![开放式 Surface UEFI 配置器](images/shm-fig2.png)
   
3. 选择 " **Surface 设备** "，然后选择 " **下一步**"。

   ![选择 Surface 设备](images/shm-fig3.png)
  
4. 选择 " **配置包**"。

   ![选择配置包](images/shm-fig4.png)
  
5. 选择 " **证书保护**"。

   ![选择证书保护](images/shm-fig5.png)

6. 系统将提示您添加证书 .pfx 文件。

   ![系统将提示您添加证书](images/shm-fig6.png)
   
7. 输入您的 **证书密码** ，然后选择 **"确定"**。

   ![输入你的证书密码，然后选择 "确定"](images/shm-fig7.png)

8. 选择 " **密码保护** " 以将密码添加到 Surface UEFI。 当您启动到 UEFI 时，将需要此密码。 **强烈建议**设置你将在 Surface Hub 2 秒使用的 UEFI 密码。

   ![单击 "密码保护"](images/shm-fig8.png)
   
9. 设置 **UEFI 密码** ，然后选择 **"确定"**。

   > [!IMPORTANT]
   > 将密码保存在你的组织中负责管理 Surface Hub 的 IT 管理员可访问的安全位置。 如果密码丢失，则不会恢复过程。 

   ![输入你的 UEFI 密码](images/shm-fig9.png)

10. 选择 **Surface Hub** 2-2，然后选择 " **下一步**"。

    ![选择 Surface Hub 2](images/shm-fig10.png)
   
11. 选择**下一步** 。

    ![选择 "下一步"](images/shm-fig10a.png)

12. 若要允许安装 Windows 10 专业版或企业版，请选择 " **EnableOsMigration"。**

    ![选择 "启用 OS 迁移"](images/shm-fig11.png)
    
13. 将 **EnableOSMigration** 设置为 **"打开"** 并选择 " **下一步**"。

    ![将 "启用 OS 迁移" 设置为 "开"](images/shm-fig12.png)

> [!NOTE]
> 应用 SEMM 程序包后，所有 UEFI 设置将显示为灰色 (在设备上的 UEFI 菜单中已锁定) 。 这包括其他设置（如用于 PXE 启动的 IPv6）的默认值。 若要在完成迁移后修改 UEFI 设置，你需要应用另一个 SEMM 程序包或从 SEMM 取消注册设备。 如果你应用另一个 SEMM 包来修改 UEFI 设置，则必须使用 UEFI 配置器工具生成新的 SEMM 程序包时使用原始证书，并将 "EnableOSMigration" 关闭 (而不是 "on"，如原始迁移步骤) 所示。

#### 将 SEMM 软件包保存到 USB 驱动器

1. 将 USB 驱动器连接到电脑。 选择 " **中心** 2"，然后选择 " **下一步**"。

   ![选择 "USB](images/shm-fig13.png)

> [!WARNING]
> 生成 SEMM 程序包时，将擦除 USB 驱动器上的所有现有数据。 在生成 SEMM 程序包之前，请从要保存的 USB 驱动器中删除所有文件。
   
2. 选择“构建”****。

   ![选择 "生成"](images/shm-fig14.png)

3. 捕获此页面的屏幕截图，然后选择 " **结束**"。 你的 SEMM 程序包现已准备就绪，包含 SEMM 程序包 **DfciUpdate. dfi** 和 SEMM 指纹的文本文件 (证书的指纹) 的最后两个字符。

   ![选择结束](images/shm-fig15.png)
   
4. 保存证书指纹的最后2个字符，当你在 Surface Hub 2 上应用包时，激活 SEMM 需要该字符。

### 准备包含 Windows 10 映像、SEMM 程序包和 Surface Hub 2 驱动程序和固件的 USB 闪存驱动器

你可以使用以下选项之一 (版本1903或更高版本) 安装 Windows 10 专业版或企业版映像：

- 当前的图像处理解决方案。

- [Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) 允许你创建可启动的 Windows 10 映像，其中包括所有当前 Windows 10 更新、Office、你选择的其他应用以及所需的驱动程序和固件。 

- 带有 Windows 10 专业版或企业版映像的 USB 闪存驱动器，然后安装了  [适用于 Surface Hub 2 上的 windows 10 专业版和企业版操作系统的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。
 
此过程介绍如何从安装媒体创建一个 USB 闪存驱动器，然后添加 SEMM 程序包文件和适用于 Surface Hub 2 上的 Windows 10 Pro 和企业操作系统的驱动程序和固件。MSI 文件。 如果你使用的是其他部署方法，请转到 [Surface Hub 2 的更新 UEFI 部分以启用操作系统迁移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)。

> [!NOTE]
> 安装后，你将需要与现有 Windows 10 团队许可证分开的 Windows 10 专业版或 Windows 10 企业版有效许可证。

1. 若要创建 Windows 10 专业版安装，请按照 [下载 windows 10](https://www.microsoft.com/software-download/windows10) 页面上的说明使用 **媒体创建** 工具。 若要下载 Windows 10 企业版，请转到 [Microsoft 批量许可服务中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。

2. 插入新的 **USB 存储** 驱动器。 启动 " **媒体创建** " 工具，选择 " **创建安装媒体** "，然后选择 " **下一步**"。

   ![创建安装媒体](images/shm-fig16.png)
   
3. 选择 "语言"、"Windows 10" 和 "64 (x64") 然后选择 " **下一步**"。

   ![选择 "语言"、"Windows 10" 和 "64 位 & 选择" 下一步 "](images/shm-fig17.png)
   
4. 选择 " **USB 闪存驱动器** "，然后选择 " **下一步**"。

   ![选择 "USB 闪存驱动器"，然后选择 "下一步"](images/shm-fig18.png)
   
5. 下载完成后，选择 " **完成**"。

   ![选择 "完成"](images/shm-fig19.png)
   
6. 在 Surface Hub 2 ( 上复制 Windows 10 专业版和企业版操作系统的 SEMM 软件包文件和驱动程序和固件。MSI 文件) 到包含 Windows 10 映像的 USB 闪存驱动器 (**BOOTME**) 的根。 BOOTME USB 驱动器包含：

    - Windows 10 可启动映像。
    
    - SEMM 软件包文件 (复制到 USB 驱动器的根目录) 
    
      - DfciUpdate.dfi.
      - 带有 SEMM 指纹的文本文件。 此示例中的 (： SurfaceUEFI_2020Aug25_1058.txt。 ) 自动生成的日期时间戳对应于使用 Surface UEFI 配置器创建文件的日期。

   - Surface Hub 2 上的 Windows 10 专业版和企业操作系统的驱动程序和固件 ( # A0) ，也复制到 USB 驱动器的根目录。

### 更新 Surface Hub 2 的 UEFI 以启用操作系统迁移

1. 将 **BOOTME** 驱动器插入到 Surface Hub 2 上的 USB 端口。  (请参阅上一节，了解所需文件的列表。 ) 

2. 要启动到 UEFI，请执行以下操作：

   1. 关闭 Surface Hub 2) 的 (关闭电源。
   1. 按住 " **音量 +** "，然后按下并松开 " **电源** " 按钮。
   1. 继续保持 **音量 +** ，直到 UEFI 菜单出现。
   
      ![保留 holdling 的音量 +，直到 UEFI 菜单出现](images/shm-fig20.png)
      
3. 重新启动设备时，输入你之前创建的 UEFI 密码（如果适用 (强烈建议) ）。

   ![当设备重新启动时，请输入 UEFI paassword](images/shm-fig22.png)
   
4. 在 UEFI 菜单中，选择**Management**"  >  **从 USB 安装**管理"。

   ![选择 "管理 & 从 USB 安装"](images/shm-fig21.png)
   
5. 选择 " **立即重启**"，如下所示。 设备将重新启动并在屏幕中间显示 "4 平方" 徽标，然后关闭。

   ![选择 "立即重启"](images/shm-fig25.png)
   
6. 按下并释放 "电源" 按钮，将显示一个红色屏幕，提示你激活 Surface Enterprise 管理模式。 

7. 输入你的两个字符的 **证书指纹**，你的 **UEFI 设置密码** ，然后选择 **"确定"**。

   ![输入2个字符的证书指纹](images/shm-fig23.png)
 
   > [!NOTE]
   > 在设备上激活 SEMM 后，将应用新的 UEFI 设置 **EnableOSMigration** 。 你将无法再访问 Windows 10 团队，并且必须继续下一步，并安装 Windows 10 专业版或 Windows 10 企业版。 

8. 设备将重新启动，显示屏幕中间的白色4方形徽标，然后将再次关闭。

### 安装 Windows 10 专业版或企业版

1. 如果可启动的 Windows 10 专业版或企业版驱动器尚未插入 Surface Hub 2 USB-A 端口，请立即插入，然后按下并释放电源按钮。

2. 设备将启动，你将在屏幕中间看到白色的4方块，然后你将在白色四个方形的徽标下方看到旋转的圆圈。

3. 如果设备不会自动启动到 USB 驱动器，请关闭设备 (拔出电源线，然后再将其插入) 。 重新插入电源线后，设备将在几秒钟后启动到屏幕中间的白色4方形徽标，或者按下并释放电源按钮以重新打开设备。 在屏幕中间看到4个方形的徽标后，按住音量按钮，直到看到位于白色四个方形徽标下方的旋转圆圈。
 
   ![从 USB 启动到 Windows 10](images/shm-fig26.png)
   
4. 当 (OOBE) 安装程序启动时，请按照说明安装 Windows 10 专业版或企业版 (版本1903或更高版本) 。

### 安装 Surface Hub 2 驱动程序和固件

 - 为确保你的设备具有所有最新的更新和驱动程序，请安装 [适用于 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。
 
### 后续步骤

若要将 Surface Hub 2 完全配置为个人生产力设备，请参阅 [在 Surface hub 2 上配置 Windows 10 专业版或企业版](surface-hub-2-post-install.md)。

> [!NOTE]
>如果按照本文档中概述的步骤将设备迁移到 Windows 10 Pro 或 Enterprise for Surface Hub 2，请联系 [Surface Hub 支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。

### 回滚到 Windows 10 团队

如果你想要将设备还原到 Windows 10 团队，请参阅 [重置和恢复 Surface Hub](surface-hub-2s-recover-reset.md)2。

## 版本历史记录

| 版本 | 日期               | 描述                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| 视听. 1.2  | 2020年9月29日 | 每种可用性反馈的各种更新。                                                        |
| 视听. 1.1  | 2020年9月15日 | 在介绍介绍安装新操作系统的许可要求中放置了其他笔记。 |
| 视听. 1.0  | 2020年9月1日  | 新文章。                                                                                           |

---
title: 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文介绍了如何从 Surface Hub 2 上的 Windows 10 团队迁移到 Windows 10 专业版或 Windows 10 企业版。
keywords: Surface Hub 桌面、Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c2851505b3595ea768217de443676b45cc01a9ae
ms.sourcegitcommit: efc38524f81238e0c36371f462eb57123e46d09b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "11228553"
---
# 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版

- [文章版本历史记录](#version-history)

Surface Hub 2S 预安装有 Windows 10 团队。 此自定义版本的 Windows 10 旨在促进在会议室环境中进行协作。 现在，你可以选择运行 Windows 10 专业版或企业版以使用 Surface Hub 2S，这非常像任何其他电脑。 

> [!IMPORTANT]
>与典型的升级或迁移不同，此过程要求您遵循一个说明性过程，如本文中所述。 在继续[之前，](#solution-components)[请查看解决方案组件以及迁移](#migration-and-installation-workflow-summary)和安装工作流。


> [!NOTE]
> 安装 Windows 10 专业版或企业版时，需要一个独立于现有 Windows 10 团队版许可证的新许可证。 


使用单独的电脑和可下载的工具 *Surface UEFI Configurator*开始从 Windows 10 团队迁移。 使用该工具创建包含适用于 Surface Hub 2S 的新 UEFI 设置的程序包。  

Surface UEFI 配置器用作 SEMM (Surface 企业管理模式的) 。 它旨在便于在企业环境中集中管理 Surface 设备的固件设置。 有关详细信息，请参阅 Microsoft <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 文档</a>
 

## 解决方案组件

- 运行 Windows 10 团队操作系统的 Surface Hub 2S 设备
- 运行 Windows 10 的单独设备
- 用于创建 SEMM 程序包的 Surface UEFI 配置器工具
- Windows 10 专业版或企业版操作系统映像版本 1903 或更高版本
- 两个存储为 16 GB 的 USB 驱动器，FAT32 格式
- Surface Hub 2 上适用于 Windows 10 专业版和企业操作系统的驱动程序和固件Microsoft Windows Installer (MSI) 文件
- Internet 连接
- 映像解决方案 (可选) 

 
## 迁移和安装工作流摘要

| 步骤  | 操作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [验证 Surface Hub 2S 上的 UEFI 版本是否满足最低要求。](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | 确保 UEFI 版本为 694.2938.768.0 或更高版本。                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件。](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 在 <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **Surface Tools for IT**页面上 </a> ，选择"**下载"。** 然后选择并下载 **Surface UEFI 配置器。MSI 文件** ，并安装在单独的电脑上。 在 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 MSI 文件上下载适用于 Windows 10 专业版和企业操作系统的驱动程序和固件。</a> 保存它以在步骤 5 中使用。 |
| 3 | [准备 SEMM 证书。](#prepare-the-semm-certificate)                                                                          | 准备运行 Surface UEFI 配置程序所需的证书。 或使用当前证书。                                                                                                                                                                                                                                                                                                      |
| 4 | [创建 SEMM 程序包。](#create-a-semm-package)                                                                               | 启动 Surface UEFI 配置器以在 USB 驱动器上创建 SEMM 程序包，其中包含在 Surface Hub 2S 上应用所需的配置文件。 将这些 SEMM 程序包文件复制到电脑上的文件夹中。                                                                                                                                                                                          |
| 5 | [为 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统准备包含 Windows 10 映像、SEMM 程序包以及驱动程序和固件的 U 盘。](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 创建一个包含 Windows 10 映像的 USB 驱动器。 本示例中，驱动器名为*BOOTME。* 将 Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件 (步骤 2) ，将 SEMM 程序包文件 (步骤 4) *BOOTME* 驱动器。                                                                                                                                                                                                  |
| 6 | [更新 Surface Hub 2S 上的 UEFI 以启用操作系统迁移。](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用 *BOOTME* 驱动器将 Surface Hub 2S 启动到 UEFI 菜单并安装 SEMM 程序包。|
| 7 | [安装 Windows 10 专业版或企业版 1903 或更高版本。](#install-windows-10-pro-or-enterprise)                                        | 使用 *BOOTME* 驱动器安装 Windows 10 专业版或企业版 1903 或更高版本。                                                                                                                                                                                                                                                                                 |
| 8 | [在 Surface Hub 2 上安装适用于 Windows 10 专业版和企业版操作系统的驱动程序和固件。](#install-surface-hub-2-drivers-and-firmware)                                        | 若要确保你的设备具有所有最新的更新和驱动程序，请为 Surface Hub 2 MSI 文件安装适用于 Windows 10 专业版和企业操作系统的驱动程序 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 和固件。</a>                                                                                                                                                                                                                                                                                  |
| 9 | [将 Surface Hub 2S 完全配置为个人生产力设备。](#configure-recommended-settings)                                        |  启用推荐的设置和应用程序以将 Surface Hub 2S 优化为个人生产力设备。                                                                                                                                                                                                                                                                    |

### 验证 Surface Hub 2S 上的 UEFI 版本是否满足最低要求

在将 Surface Hub 从 Windows 10 团队迁移到 Windows 10 桌面版之前，你需要至少为 *694.2938.768.0*的 UEFI 版本。
 
**验证系统上的 UEFI 版本：**

1. 在 Surface Hub 2S 主页**** 上，选择"开始"，然后打开 Surface 应用 (**所有应用**  >  **Surface**) 。

2. 选择 Surface 以显示 **有关** Surface Hub 的信息，包括设备上当前的 UEFI 版本。 
   - 如果 UEFI 版本为 *694.2938.768.0* 或更高版本，如下图所示，您可以创建 SEMM 程序包以启用操作系统迁移。

       ![显示 Surface 应用中的 Surface 页面的屏幕截图。](images/shm-fig1.png)
 
   - 如果 UEFI 版本早于版本 694.2938.768.0，则需要通过安装 Window 10 Team 2020 Update Bare Metal Recovery (BMR) 映像或通过使用 Windows 更新来获取当前版本。
   
**若要通过 Windows 更新更新 UEFI，**

1. 在 Surface Hub 2S 上，以管理员角色 **登录**。 
    >[!Note]
    > 如果不知道用户名或管理员密码，则需要重置设备。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Surface Hub 2S 的重置和恢复。</a>

1. 转到 **"所有应用**  >  **设置**  >  **更新和安全**  >  **Windows 更新**"，然后安装所有更新。 
1. 重新启动设备。 
1. 使用 Surface 应用验证 UEFI 版本。 
1. 此时，如果 UEFI 版本尚不为版本 694.2938.768.0 或更高版本，可以重复上述步骤，或者可以通过安装 Windows 10 Team 2020 Update 裸机恢复 (BMR) 映像获取最新的 UEFI。

**若要通过裸机恢复更新 UEFI (BMR) 映像：**

1.  转到 [Surface 恢复站点并选择](https://support.microsoft.com/surfacerecoveryimage) **Surface Hub 2S**
3.  输入位于集线器 (电源连接旁的集线器序列号。) 
4.  按照说明通过安装 Windows 10 Team 2020 Update 将映像下载到格式化的 USB 驱动器上。
5.  更新完成后，设备首次进入 OOBE 设置后，无需完成 OOBE，UEFI 版本将更新。 而是按住电源按钮关闭设备，直到屏幕关闭。 

### 下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件

在单独的电脑上：

1. 在 <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT 页面上 </a> ，选择"**下载"。**  
1. 选择并下载 Surface UEFI 配置器 MSI 文件，将其安装在单独的电脑上。 安装 Windows 10 团队版时，Surface UEFI 配置器工具无法运行在 Surface Hub 2S 上。

1. 下载 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 驱动程序和固件 Windows Installer MSI 文件 </a> 。 安装新操作系统时，将使用此文件。

### 准备 SEMM 证书

如果你之前没有使用过 Surface UEFI 配置器，则需要准备证书。 此证书可确保在 SEMM 中注册设备后，只能使用使用已批准证书创建的程序包修改 UEFI 设置。 

获取证书的方式取决于组织的规模或复杂性：

- 企业组织通常维护自己的基础结构，以根据标准安全做法生成证书。

- 中型企业和其他企业可能会选择从合作伙伴提供商获取证书。 对于没有足够的 IT 专业知识或专门的 IT 安全团队的组织，建议使用此选项。

- 或者，您可以使用 PowerShell 脚本生成自签名证书。 有关详细信息，请参阅 Surface <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> Enterprise 管理模式证书要求 </a> 。 或者，您可以使用 PowerShell 创建自己的证书。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate </a> 文档。

Surface UEFI 配置器创建的 SEMM 程序包必须使用证书进行保护。 证书先验证配置文件的签名，然后才能应用 UEFI 设置。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 文档 </a> 。
 
 
### 创建 SEMM 程序包

1. 在单独的电脑上，安装之前下载的 Surface UEFI 配置器工具。 

2. 打开 Surface UEFI 配置器，然后选择"**开始"。**

   ![打开 Surface UEFI 配置器。](images/shm-fig2.png)
   
3. 选择**Surface 设备**，然后选择"下一**步"。**

   ![选择 Surface 设备。](images/shm-fig3.png)
  
4. 选择 **配置包**。

   ![选择配置包。](images/shm-fig4.png)
  
5. 选择 **证书保护**。

   ![选择"证书保护"。](images/shm-fig5.png)

   系统将提示你添加证书 .pfx 文件。

   ![添加证书。](images/shm-fig6.png)
   
7. 输入你的证书密码，然后选择"**确定"。**

   ![输入证书密码，然后选择"确定"。](images/shm-fig7.png)

8. 选择 **密码保护** 以将密码添加到 Surface UEFI。 每次启动到 UEFI 时，都需要此密码。 *我们强烈建议*你设置在 Surface Hub 2S 上使用的 UEFI 密码。

   ![选择"密码保护"。](images/shm-fig8.png)
   
9. 设置 UEFI 密码，然后选择"**确定"。**

   > [!IMPORTANT]
   > 将密码保存在可供管理 Surface Hub 的 IT 管理员访问的安全位置。 如果密码丢失，则不能恢复。 

   ![输入 UEFI 密码。](images/shm-fig9.png)

10. 选择**Surface Hub 2S，** 然后选择"下**一步"。**

    ![选择 Surface Hub 2S。](images/shm-fig10.png)
   
11. 选择**下一步** 。

    ![选择下一步 。](images/shm-fig10a.png)

12. 若要允许安装 Windows 10 专业版或企业版，请打开**EnableOsMigration，** 然后选择"下一**步"。**

    ![选择"启用 OS 迁移"。](images/shm-fig11.png)
    
    ![将"启用操作系统迁移"设置为"打开"。](images/shm-fig12.png)

### 管理 SEMM 注册

将设备注册到 SEMM 会影响你可以如何管理设备。 例如，应用 SEMM 程序包后，在设备的 UEFI 菜单中，所有 UEFI 设置在锁定 (不可用) 。 其他设置（如 **用于 PXE 启动的 IPv6）的** 默认值也不可用。 

若要在迁移完成后更改 UEFI 设置，请应用另一个 SEMM 程序包，或者从 SEMM 注销设备。 如果应用另一个 SEMM 程序包来更改 UEFI 设置，则必须在生成新的 SEMM 程序包时使用原始证书。 使用 UEFI 配置器工具，将 **EnableOSMigration** (保持关闭状态，如原始迁移步骤) 。

#### 与合作伙伴合作

如果你的公司将迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版外包，你可能希望让合作伙伴将 SEMM 证书、SEMM 程序包和 UEFI 密码传输给你。  或者，在迁移中心后，你可以立即从 SEMM 取消注册它，这将允许本地管理 UEFI 以及将设备转移到另一方。 但是，仍强烈建议使用可在迁移后配置的 UEFI 密码。 若要了解更多信息，请参阅["管理 Surface UEFI 设置"。](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### 回滚到 Windows 10 团队

如果在迁移后选择将设备还原到 Windows 10 团队，[](#roll-back-to-windows-10-team)如下所述，建议先从 SEMM 注销 Hub。 若要了解更多信息，请参阅 [从 SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)注销 Surface 设备。


#### 将 SEMM 程序包保存到 U 盘

1. 将 U 盘连接到电脑。 
1. 选择**中心 2S，** 然后选择"下**一步"。**

   ![选择 USB](images/shm-fig13.png)

   > [!WARNING]
   > 生成 SEMM 程序包时，将擦除 USB 驱动器上的所有现有数据。 生成 SEMM 程序包之前，请从要保存的 USB 驱动器中删除所有文件。
   
2. 选择“构建”****。

   ![选择“构建”。](images/shm-fig14.png)

3. 捕获此页面的屏幕截图，然后选择"结束 **"。** SEMM 程序包现已准备就绪。 它包含 SEMM 程序包 *DfciUpdate.dfi* 和一个文本文件，其中包含 SEMM 指纹 (证书指纹证书的最后两个字符) 。

   ![选择"结束"。](images/shm-fig15.png)
   
4. 保存证书指纹的最后两个字符。 当你在 Surface Hub 2S 上应用程序包时，你将需要这些字符来激活 SEMM。

### 准备包含 Windows 10 映像、SEMM 程序包和 Surface Hub 2 驱动程序和固件的 U 盘

可以使用以下选项之一 (版本 1903 或) 安装 Windows 10 专业版或企业版映像：

- 当前的映像解决方案。

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Surface Deployment Accelerator </a> . 使用此工具创建可启动的 Windows 10 映像。 该映像可以包括所有当前的 Windows 10 更新、Office、你选择的其他应用以及所需的驱动程序和固件。 

- 包含 Windows 10 专业版或企业版映像的 U 盘。 然后在 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 上安装适用于 Windows 10 专业版和企业操作系统的驱动程序和固件 </a> 。
 
以下过程介绍如何从安装媒体创建 U 盘，然后在 Surface Hub 2 MSI 文件上添加 SEMM 程序包文件和适用于 Windows 10 专业版和企业操作系统的驱动程序和固件。 如果你使用的是其他部署方法，请转到 Surface Hub [2S 上的更新 UEFI](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 以启用本文中的操作系统迁移部分。

> [!NOTE]
> 完成安装后，你将需要一个有效的 Windows 10 专业版或 Windows 10 企业版许可证，该许可证独立于现有的 Windows 10 团队版许可证。

1. 若要创建 Windows 10 专业版安装，请按照说明在"下载 <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> Windows 10"页上 </a> 下载媒体创建工具。 若要下载 Windows 10 企业版，请转到 <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft 批量许可服务中心 </a> 。

2. 插入新的 USB 存储驱动器。 
1. 打开媒体创建工具，选择 **"创建安装媒体**"，然后选择"下**一步"。**

   ![创建安装媒体。](images/shm-fig16.png)
   
3. 选择一种语言，然后选择**Windows 10**和 64 位 (**x64) 。 ** 然后选择"**下一步"。**

   ![选择语言，然后选择 Windows 10 和 64 位。 然后选择"下一步"。](images/shm-fig17.png)
   
4. 选择**U 盘**，然后选择"下一**步"。**

   ![选择 U S 闪存驱动器，然后选择"下一步"。](images/shm-fig18.png)
   
5. 下载完成后，选择"完成 **"。**

   ![选择“完成”。](images/shm-fig19.png)
   
6. 将 SURFACE Hub 2 上的 Windows 10 专业版和企业版操作系统的 SEMM 程序包文件和驱动程序和固件 (MSI 文件) 复制到包含 Windows 10 映像的 U 盘 (*BOOTME*) 的根目录。 BOOTME USB 驱动器包含：

    - Windows 10 可启动映像。
    
    - SEMM 包 (复制到 USB 驱动器驱动器的根) 。
    
      - *DfciUpdate.dfi*。
      - 包含 SEMM 指纹的文本文件。  (此示例中，该文件为 *SurfaceUEFI_2020Aug25_1058.txt*.) 自动生成的日期时间戳对应于使用 Surface UEFI 配置器创建文件的日期。

   - Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi) 。 将此文件复制到 USB 驱动器的根目录。

### 在 Surface Hub 2S 上更新 UEFI 以启用操作系统迁移

1. 将 BOOTME 驱动器插入 Surface Hub 2S 上的 USB-A 端口。 有关所需文件的列表，请参阅上一节。

2. 若要启动到 UEFI：

   1. 关闭 (Surface Hub 2S) 关闭。
   1. 长按 **音量 +**，然后按下并释放电源按钮。
   1. 保持音量 **+** ，直到 UEFI 菜单出现。
   
      ![长按调高音量按钮，直到 UEFI 菜单出现。](images/shm-fig20.png)
      
3. 当设备重新启动时，输入之前创建的 UEFI 密码（如果适用 (强烈建议) 。

   ![输入 UEFI 密码。](images/shm-fig22.png)
   
4. 在 UEFI 菜单中，选择 **"从**  >  **USB 安装管理"。**

   ![Select Management and Install from U S B.](images/shm-fig21.png)
   
5. 选择 **"立即重启**"，如下图所示。 设备重新启动。 它在窗口中间显示一个白色 Microsoft 徽标，然后关闭。

   ![选择"立即重启"。](images/shm-fig25.png)
   
6. 按下并释放电源按钮。 在出现的红色窗口中，激活 Surface Enterprise 管理模式。 

7. 输入双字符证书指纹和 UEFI 设置密码。 然后选择 **"确定"。**

   ![输入双字符证书指纹和 UEFI 设置密码。](images/shm-fig23.png)
 
   > [!NOTE]
   > 在设备上激活 SEMM 后，将应用新的 UEFI 设置**EnableOSMigration。** 你将无法再访问 Windows 10 团队。 相反，你必须继续执行下一步并安装 Windows 10 专业版或 Windows 10 企业版。 

   设备重新启动。 它在屏幕中间显示白色徽标，然后再次关闭。

### 安装 Windows 10 专业版或企业版

1. 如果你的可启动 Windows 10 专业版或企业版驱动器尚未在 Surface Hub 2 USB-A 端口中，则现在插入它。 然后按下并释放电源按钮。 

    设备启动时，你将在屏幕中间看到白色徽标。 然后，你将在白色徽标下方看到一个旋转圆圈。

3. 如果设备未自动启动到 USB 驱动器，请关闭设备电源 (拔下电源线，然后将其插回) 。 再次插入电缆后，设备应在几秒钟后启动。 然后，你将在屏幕中间看到白色徽标。 

    如果设备未打开，请按并释放电源按钮。 在屏幕中间看到徽标后，立即长按音量按钮，直到看到白色徽标下方的旋转圆圈。
 
   ![从美国 B 驱动器启动到 Windows 10。](images/shm-fig26.png)
   
4. 当 OOBE (OOBE) 安装启动时，请按照说明安装 Windows 10 专业版或企业版 (版本 1903 或更高版本) 。

### 安装 Surface Hub 2 驱动程序和固件

若要确保你的设备具有所有最新的更新和驱动程序，请为 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 上的 Windows 10 专业版和企业版操作系统安装驱动程序和固件 </a> 。 安装驱动程序和固件 MSI 后，重启设备。 然后，重新打开集线器电源后，将电脑电源保持打开状态一小时，然后重新启动设备。 系统不会提示您进行第二次重启。 根据迁移到 Windows 10 专业版或企业版之前计算机的状态，可能需要执行第二步以确保已更新所有固件。
 
## 配置建议设置

若要将 Surface Hub 2S 完全配置为个人生产力设备，请参阅在 Surface Hub 2 上配置 <a href="surface-hub-2-post-install.md" target="_blank"> Windows 10 专业版或企业版 </a> 。

> [!NOTE]
>如果本文中概述的步骤无法成功将设备迁移到适用于 Surface Hub 2 的 Windows 10 专业版或企业版，请联系 <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub 支持 </a> 人员。

## 回退到 Windows 10 团队

如果你想要将设备还原到 Windows 10 团队，请参阅 <a href="surface-hub-2s-recover-reset.md" target="_blank"> Surface Hub 2S 的重置和恢复 </a> 。

> [!NOTE]
> 在回滚到 Windows 10 团队之前，建议先从 SEMM 注销 Hub。 若要了解更多信息，请参阅 [从 SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)注销 Surface 设备。

## 版本历史记录

下表汇总了对本文所做的更改。

| 版本 | 日期               | 描述                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 2020 年 12 月 14 日 | 提供有关[](#install-surface-hub-2-drivers-and-firmware)为"Surface Hub 2 上的 Windows 10 专业版和企业版操作系统的驱动程序和固件"安装 MSI 文件的进一步信息，提示可能需要根据系统状态进行第二次重启。                                                          |
| v. 1.3  | 2020 年 12 月 3 日 | 更新了有关管理 [SEMM 注册的指南](#managing-semm-enrollment)。                                                       |
| v. 1.2  | 2020 年 9 月 29 日 | 处理可用性反馈的杂项更新。                                                        |
| v. 1.1  | 2020 年 9 月 15 日 | 在介绍中附加了一条说明，阐明了安装新操作系统的许可要求。 |
| v. 1.0  | 2020 年 9 月 1 日  | 新文章。                                                                                           |

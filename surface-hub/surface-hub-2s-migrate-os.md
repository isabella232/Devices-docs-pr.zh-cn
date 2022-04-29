---
title: 在 Surface Hub 2 上迁移到Windows 10/11 Pro或Enterprise
description: 如何从 Surface Hub 2 上的Windows 10 协同版迁移到Windows 10 专业版或Windows 10 企业版。
keywords: Surface Hub桌面、Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S
- Windows 10
- Windows 11
ms.openlocfilehash: 7b221b6f8b4a7753a10dd974da47ce58af41d006
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497755"
---
# <a name="migrate-to-windows-1011-pro-or-enterprise-on-surface-hub-2"></a>在 Surface Hub 2 上迁移到Windows 10/11 Pro或Enterprise

- [文章版本历史记录](#version-history)

Surface Hub 2S 随附Windows 10 协同版安装。 此自定义版本的Windows 10有助于在会议室环境中进行协作。 现在可以改为运行Windows 10/11 Pro或Enterprise，以像任何其他电脑一样使用Surface Hub 2S。

> [!IMPORTANT]
> 此迁移过程要求遵循本文中所述的特定过程。 在继续之前，请阅读 [解决方案组件](#solution-components) 以及 [迁移和安装工作流](#migration-and-installation-workflow-summary)。

> [!NOTE]
> 在 Surface Hub 2S 上安装Windows 10/11 Pro或Enterprise时，需要一个与设备提供的现有Windows 10 协同版许可证不同的新许可证。

使用单独的电脑和可下载的 *Surface UEFI 配置器*工具从Windows 10 协同版开始迁移。 该工具创建一个包，其中包含应用于 Surface Hub 2S 的新 UEFI 设置。  

Surface UEFI 配置器充当 Surface Enterprise 管理模式 (SEMM) 中的接口。 它允许在公司环境中集中管理 Surface 设备上的固件设置。 有关详细信息，请参阅 [Microsoft Surface Enterprise管理模式](/surface/surface-enterprise-management-mode)。

## <a name="solution-components"></a>解决方案组件

- Surface Hub运行Windows 10 协同版的 2S 设备
- 单独运行Windows 10设备
- 用于创建 SEMM 包的 Surface UEFI 配置器工具
- Windows 10/11 Pro或Enterprise OS 映像版本 20H2 或更高版本
- 具有 16 GB 存储的两个 USB 驱动器，FAT32 格式
- Surface Hub 2 Microsoft Windows安装程序 (MSI) 文件中Windows 10 专业版和Enterprise的驱动程序和固件
- Internet 连接
- 成像解决方案 (可选) 

## <a name="migration-and-installation-workflow-summary"></a>迁移和安装工作流摘要

| 步骤  | 操作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [验证 Surface Hub 2S 上的 UEFI 版本](#verify-the-uefi-version-on-surface-hub-2s)。                                  | UEFI 版本必须是 *版本 694.2938.768.0* 或更高版本。                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [下载 Surface UEFI 配置器和Surface Hub 2 个驱动程序和固件。](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 在 **[Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)** 页面</a>上，选择 **“下载**”。 然后选择并下载 **Surface UEFI 配置器 MSI 文件**，并将其安装在单独的电脑上。 此外，在 [Surface Hub 2 MSI 文件上下载 Windows 10 专业版 和 Enterprise OS 的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</a> 保存此包以在步骤 5 中使用。 |
| 3 | [准备 SEMM 证书。](#prepare-the-semm-certificate)                                                                          | 准备运行 Surface UEFI 配置器或使用当前证书所需的证书。                                                                                                                                                                                                                                                                                                      |
| 4 | [创建 SEMM 包。](#create-a-semm-package)                                                                               | 启动 Surface UEFI 配置器，以便在 USB 驱动器上创建 SEMM 包。 此包将包含在 Surface Hub 2S 上应用所需的配置文件。 将这些 SEMM 包文件复制到电脑上的文件夹。                                                                                                                                                                                          |
| 5 | [使用Windows 10映像、SEMM 包以及驱动程序和固件加载 USB 闪存驱动器。](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 创建包含Windows 10映像的 USB 驱动器。 在此示例中，驱动器名为 *BOOTME*。 在步骤 2) 的Surface Hub 2 (上添加Windows 10 专业版和 Enterprise OS 的驱动程序和固件，并将从步骤 4)  (的 SEMM 包文件添加到 *BOOTME* 驱动器。                                                                                                                                                                                                  |
| 6 | [更新 Surface Hub 2S 上的 UEFI 以启用 OS 迁移。](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用 *BOOTME* 驱动器将Surface Hub 2S 启动到 UEFI 菜单并安装 SEMM 包。|
| 7 | [安装Windows 10 专业版或Enterprise。](#install-windows-1011-pro-or-enterprise)                                        | 使用 *BOOTME* 驱动器安装Windows 10 专业版或Enterprise*版本 20H2* 或更高版本。                                                                                                                                                                                                                                                                                 |
| 8 | [安装用于Windows 10 专业版和Enterprise的驱动程序和固件。](#install-surface-hub-2-drivers-and-firmware)                                        | 若要确保设备具有所有最新的更新和驱动程序，请在 Surface Hub 2 MSI 文件上安装 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Windows 10 专业版 和 Enterprise OS 的驱动程序和固件。</a>                                                                                                                                                                                                                                                                                  |
| 9 | [将 Surface Hub 2S 配置为个人生产力设备。](#configure-recommended-settings)                                        |  启用建议的设置和应用程序，以优化个人工作效率设备Surface Hub 2S。                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a>验证 Surface Hub 2S 上的 UEFI 版本

在将Surface Hub从Windows 10 协同版迁移到Windows 10桌面之前，需要 UEFI *版本 694.2938.768.0* 或更高版本。

**验证系统上的 UEFI 版本：**

1. 在 Surface Hub 2S 主页上，选择 **“开始**”，然后打开 Surface 应用 (**所有** **AppsSurface** > ) 。

2. 选择 **Surface** 以显示有关Surface Hub的信息，包括设备上的当前 UEFI 版本。
   - 如果 UEFI 版本为 *694.2938.768.0* 或更高版本，如下图所示，可以创建 SEMM 包以启用 OS 迁移。

    ![屏幕截图显示了 Surface 应用中的“Surface”页。](images/shm-fig1.png)

   - 如果 UEFI 版本早于 *版本 694.2938.768.0*，请使用以下方法之一获取较新的版本

#### <a name="update-uefi-via-windows-update"></a>通过Windows 更新更新 UEFI

1. 在Surface Hub 2S 上，以**管理员**身份登录。

    >[!Note]
    > 如果不知道用户名或管理员密码，则需要重置设备。 有关详细信息，请参阅 [Surface Hub 2S 的重置和恢复](/surface-hub/surface-hub-2s-recover-reset)。

1. 转到**所有应用** > **设置** > **Update 和安全** > **性Windows 更新**，并安装所有更新。
1. 重启设备。
1. 使用 Surface 应用验证 UEFI 版本。 如果 UEFI 版本不是 *版本 694.2938.768.0* 或更高版本，请重复这些步骤，或使用以下过程获取最新的 UEFI 版本。

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a>通过裸机恢复 (BMR) 映像更新 UEFI

1. 转到 [Surface 恢复站点](https://support.microsoft.com/surfacerecoveryimage)并选择**Surface Hub 2S**。
3. 输入中心序列号。 它位于电源连接旁边的中心后面。
4. 按照说明，通过安装 Windows 10 协同版 2020 更新，将映像下载到格式化的 USB 驱动器上。
5. 更新后，设备 (OOBE) 设置中输入现) 体验。 无需完成设置。 UEFI 版本已更新。 而是按住电源按钮关闭设备，直到屏幕关闭。

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a>下载 Surface UEFI 配置器并Surface Hub 2 个驱动程序和固件

在单独的电脑上，执行以下步骤：

1. <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">在 Surface Tools for IT 页面</a>上，选择 **“下载**”。  
1. 选择并下载 Surface UEFI 配置器 MSI 文件，并将其安装在单独的电脑上。 安装 Windows 10 协同版 版本时，Surface UEFI 配置器工具不能在 Surface Hub 2S 上运行。

1. [下载 Surface Hub 2 个驱动程序和固件Windows安装程序 MSI 文件](https://www.microsoft.com/download/details.aspx?id=101974)。 安装新操作系统时，将使用此文件。

### <a name="prepare-the-semm-certificate"></a>准备 SEMM 证书

如果以前未使用 Surface UEFI 配置器，则需要准备证书。 此证书可确保在 SEMM 中注册设备后，只能使用使用已批准证书创建的包来修改 UEFI 设置。

获取证书的方式取决于组织的规模或复杂性：

- Enterprise组织通常维护自己的基础结构，以便根据标准安全做法生成证书。

- 中型企业和其他企业通常选择从合作伙伴提供商处获取证书。 对于没有 IT 专业知识或缺乏专用 IT 安全团队的组织，建议使用此选项。

- 或者，可以使用 PowerShell 脚本生成自签名证书。 有关详细信息，请参阅 [Surface Enterprise管理模式证书要求](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。 也可以使用 PowerShell 创建自己的证书。 有关详细信息，请参阅 [自签名证书](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) 文档。

Surface UEFI 配置器创建的 SEMM 包必须使用证书进行保护。 证书在应用 UEFI 设置之前验证配置文件的签名。 有关详细信息，请参阅 [SEMM](/surface/surface-enterprise-management-mode) 文档。

### <a name="create-a-semm-package"></a>创建 SEMM 包

1. 在单独的电脑上，安装之前下载的 Surface UEFI 配置器工具。

1. 打开 Surface UEFI 配置器，然后选择 **“开始**”。

   ![Surface UEFI 配置器启动屏幕。](images/shm-fig2.png)

1. 选择 **Surface 设备**，然后选择 **“下一步**”。

   ![屏幕截图显示了所选的 Surface Devices 选项。](images/shm-fig3.png)
  
1. 选择 **配置包**。

   ![屏幕截图显示已选择“选择配置包”。](images/shm-fig4.png)
  
1. 选择 **“证书保护**”。

   ![屏幕截图显示选择“选择证书保护”。](images/shm-fig5.png)

   系统会提示你添加证书 .pfx 文件。

   ![屏幕截图显示了在何处添加证书文件。](images/shm-fig6.png)

1. 输入证书密码，然后选择 **“确定**”。

   ![屏幕截图显示了要输入和确认证书密码的字段。](images/shm-fig7.png)

1. 选择 **“密码保护** ”以向 Surface UEFI 添加密码。 每次启动到 UEFI 时都需要此密码。 *强烈建议设置将在 Surface Hub 2S 上使用的 UEFI 密码。*

   ![屏幕截图显示选择密码保护的位置。](images/shm-fig8.png)

1. 设置 UEFI 密码，然后选择 **“确定**”。

   > [!IMPORTANT]
   > 将密码保存在管理Surface Hub的 IT 管理员可访问的安全位置。 *如果此密码丢失，则无法恢复。*

   ![屏幕截图显示了设置 UEFI 密码的位置。](images/shm-fig9.png)

1. 选择**Surface Hub 2S**，然后选择 **“下一步**”。

    ![屏幕截图显示了选择Surface Hub 2S 的位置。](images/shm-fig10.png)

1. 再次选择 **“下一步** ”。

    ![屏幕截图显示在“选择哪些组件”下选择“下一步”。](images/shm-fig10a.png)

1. 若要允许安装Windows 10/11 Pro或Enterprise，请打开 **EnableOsMigration**，然后选择 **“下一步**”。

    ![屏幕截图显示了选择“启用 O S 迁移”的位置。](images/shm-fig11.png)

    ![屏幕截图显示将启用 OS 迁移设置为打开的位置。](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a>管理 SEMM 注册

将设备注册到 SEMM 会影响管理设备的方式。 例如，应用 SEMM 包后，所有 UEFI 设置都不可用， (设备的 UEFI 菜单中锁定) 。 其他设置（例如 **IPv6 for PXE Boot）** 的默认值也不可用。

若要在完成迁移后更改 UEFI 设置，请应用另一个 SEMM 包或从 SEMM 取消注册设备。 如果应用另一个 SEMM 包来更改 UEFI 设置，则在生成新的 SEMM 包时必须使用原始证书。 使用 UEFI 配置器工具，将 **EnableOSMigration** *关闭* (不会像原始迁移步骤) 中那样 *继续* 。

#### <a name="if-you-work-with-partners"></a>如果你与合作伙伴合作

如果公司将 Surface Hub 2 迁移外包到 Windows 10/11 Pro或Enterprise，则可能需要让合作伙伴将 SEMM 证书、SEMM 包和 UEFI 密码传输给你。 或者，迁移中心后，可以立即从 SEMM 取消注册它。 此步骤允许对 UEFI 进行本地管理，并将设备传输到另一方。 但我们仍然强烈建议使用 UEFI 密码，该密码可以在迁移后进行配置。 若要了解详细信息，请参阅 [“管理 Surface UEFI 设置](/surface/manage-surface-uefi-settings)”。

#### <a name="to-roll-back-to-windows-10-team"></a>回滚到Windows 10 协同版

如果选择在迁移后将设备还原为Windows 10 协同版[，](#to-roll-back-to-windows-10-team)我们建议首先从 SEMM 取消注册中心。 若要了解详细信息，请参阅 [SEMM 中的取消注册 Surface 设备](/surface/unenroll-surface-devices-from-semm)。

>[!WARNING]
>若要从 SEMM 中取消注册设备并还原 Surface UEFI 设置的用户控制，必须具有用于在 SEMM 中注册设备的 SEMM 证书。 如果此证书丢失或损坏，则无法从 SEMM 取消注册。 相应地备份和保护 SEMM 证书。

#### <a name="save-the-semm-package-to-a-usb-drive"></a>将 SEMM 包保存到 USB 驱动器

1. 连接到电脑的 USB 驱动器。
1. 选择 **中心 2S**，然后选择 **“下一步**”。

   ![屏幕截图显示选择中心 2S 的位置。](images/shm-fig13.png)

   > [!WARNING]
   > 生成 SEMM 包时，USB 驱动器上的所有现有数据都将被擦除。 在生成 SEMM 包之前，请从 USB 驱动器中删除所需的任何文件。

1. 选择“构建”****。

   ![屏幕截图显示选择“生成”的位置。](images/shm-fig14.png)

1. 捕获此页面的屏幕截图，然后选择 **“结束**”。 SEMM 包现已准备就绪。 它包含 SEMM 包 *DfciUpdate.dfi* 和包含 SEMM *指纹*的文本文件，这是证书指纹的最后两个字符。

   ![屏幕截图显示了选择 End 的位置。](images/shm-fig15.png)

4. 保存证书指纹的最后两个字符。 在 Surface Hub 2S 上应用包时，需要这些字符来激活 SEMM。

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a>使用Windows 10映像、SEMM 包和 Surface Hub 2 个驱动程序和固件加载 USB 闪存驱动器

可以使用以下选项之一安装Windows 10/11 Pro或Enterprise映像 (*版本 20H2* 或更高版本) ：

- 当前的成像解决方案。

- [Surface Deployment Accelerator](/surface/microsoft-surface-deployment-accelerator)。 使用此工具创建可启动的Windows 10映像。 映像可以包括所有当前Windows 10更新、Microsoft Office、其他应用以及所需的驱动程序和固件。

- 包含Windows 10/11 Pro或Enterprise图像的 USB 闪存驱动器。 此选项在安装 OOBE)  (后才可用Wi-Fi。 安装完成后，在设备上安装所需的[Surface Hub 2 个驱动程序和固件，用于Windows 10 专业版和Enterprise](https://www.microsoft.com/download/details.aspx?id=101974)。

以下步骤演示如何从安装介质创建 USB 闪存驱动器，然后在 Surface Hub 2 MSI 文件上添加 SEMM 包文件以及Windows 10 专业版和Enterprise OS 的驱动程序和固件。 如果使用其他部署方法，请转到 [Surface Hub 2S 上的 Update UEFI 以启用本文的 OS 迁移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)部分。

> [!NOTE]
> 完成安装后，需要一个与现有Windows 10 协同版许可证分开的Windows 10 专业版或Windows 10 企业版的有效许可证。

1. 若要创建Windows 10 专业版安装，请按照说明下载[下载Windows 10](https://www.microsoft.com/software-download/windows10)中的媒体创建工具。 若要下载Windows 10 企业版，请转到 [Microsoft 批量许可服务中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。

1. 插入新的 USB 存储驱动器。
1. 打开媒体创建工具，选择 **“创建安装媒体**”，然后选择 **“下一步**”。

   ![屏幕截图显示了创建安装媒体的选项。](images/shm-fig16.png)

3. 选择语言，然后选择**Windows 10**和 **64 位 (x64) **。 然后选择 **“下一步**”。

   ![屏幕截图显示了选择语言、O S 版和体系结构类型的位置。](images/shm-fig17.png)

4. 选择 **USB 闪存驱动器**，然后选择 **“下一步**”。

   ![屏幕截图显示了在何处选择 U S B 闪存驱动器。](images/shm-fig18.png)

5. 下载完成后，选择 **“完成**”。

   ![屏幕报告 U S B 驱动器已准备就绪，并包含“完成”按钮。](images/shm-fig19.png)

6. 将 SURFACE HUB 2 上用于Windows 10 专业版和Enterprise OS 的 SEMM 包文件和驱动程序和固件 (MSI 文件) 复制到包含Windows 10映像的 USB 闪存驱动器 (*BOOTME*) 的根目录。 BOOTME USB 驱动器将包含：

    - Windows 10可启动映像。

    - 复制到 USB 驱动器根目录的 SEMM 包文件：

      - *DfciUpdate.dfi*.
      - 包含 SEMM 指纹的文本文件。  (在此示例中，文件 *SurfaceUEFI_2020Aug25_1058.txt*.) 自动生成的日期时间戳对应于使用 Surface UEFI 配置器创建文件的日期。

   - Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi) 上Windows 10 专业版和Enterprise OS 的驱动程序和固件。 将此文件复制到 USB 驱动器的根目录。

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a>更新 Surface Hub 2S 上的 UEFI 以启用 OS 迁移

1. 将 BOOTME 驱动器插入到 Surface Hub 2S 上的 USB-A 端口。 有关其所需内容的列表，请参阅上一部分。

1. 若要启动到 UEFI，请执行以下操作：

   1. 关闭 (Surface Hub 2S) 关闭。
   1. 按住 **Volume +**，然后按下并释放电源按钮。 一直保留 **Volume +** ，直到 UEFI 菜单出现。

      ![绘图显示卷和电源按钮。](images/shm-fig20.png)

3. 当设备重新启动时，输入之前创建的 UEFI 密码（如果适用 (建议) ）。

   ![系统密码屏幕。](images/shm-fig22.png)

4. 在 UEFI 菜单中，选择 **“管理**”。 然后  **从 USB 中选择“安装**”。

   ![屏幕截图显示了在何处选择“管理”，然后选择“从 U S B 安装”。](images/shm-fig21.png)

5. **立即选择“重启**”，如下图所示。 设备将启动。 它将在窗口中间显示一个白色的 Microsoft 徽标，然后关闭。

   ![屏幕截图显示提示重启的消息。](images/shm-fig25.png)

6. 按下并释放电源按钮。 在出现的红色对话框中，选择激活 Surface Enterprise 管理模式。

7. 输入双字符证书指纹和 UEFI 设置密码。 然后选择 **“确定**”。

   ![屏幕截图显示“确认激活”对话框，其中输入了双字符证书指纹和 UEFI 设置密码。](images/shm-fig23.png)

   > [!NOTE]
   > 在设备上激活 SEMM 后，将应用新的 UEFI 设置 **EnableOSMigration** 。 无法再访问Windows 10 协同版。 相反，必须继续执行下一步，并安装Windows 10 专业版或Windows 10 企业版。

   设备重新启动。 它在屏幕中间显示白色徽标，然后再次关闭。

### <a name="install-windows-1011-pro-or-enterprise"></a>安装Windows 10/11 Pro或Enterprise

1. 如果可启动Windows 10/11 Pro或Enterprise驱动器尚未在 Surface Hub 2 USB-A 端口中，请立即插入它。 然后按下并释放电源按钮。

    设备启动时，屏幕中间会显示白色徽标。 然后，白色徽标下方会显示一个旋转的圆圈。

3. 如果 Surface 设备未自动启动到 USB 驱动器，则关闭设备 (拔下电源线，然后将其插入) 。 再次插入电源线后，设备应在几秒钟后启动。 然后，屏幕中间会显示白色徽标。

    如果设备未打开，请按下并释放电源按钮。 在屏幕中间看到徽标后，立即按住“卷”按钮，直到看到白色徽标下方的旋转圆圈。

   ![卷和电源按钮的图片。](images/shm-fig26.png)

4.  (OOBE) 安装程序启动时，请按照说明安装Windows 10/11 Pro或Enterprise (*版本 20H2* 或更高版本) 。

### <a name="install-surface-hub-2-drivers-and-firmware"></a>安装Surface Hub 2 个驱动程序和固件

若要确保Surface Hub 2 是最新的，请安装[用于Windows 10 专业版和Enterprise的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。 然后重新启动设备。 使 Surface 打开一小时，然后重新启动它。 不会提示你进行第二次重启。 此暂停和额外重启可确保固件已完全更新。

## <a name="configure-recommended-settings"></a>配置建议的设置

若要将 Surface Hub 2S 配置为个人工作效率设备，请参阅[在 Surface Hub 2 上配置 Windows 10/11 Pro或Enterprise](surface-hub-2-post-install.md)。

> [!NOTE]
>如果无法按照本文中所述的步骤将设备成功迁移到Windows 10/11 Pro或Enterprise Surface Hub 2，[请联系Surface Hub支持](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)部门。

## <a name="to-roll-back-to-windows-10-team"></a>回滚到Windows 10 协同版

若要将设备还原到Windows 10 协同版，请参阅 [Surface Hub 2S 的重置和恢复](surface-hub-2s-recover-reset.md)。

> [!NOTE]
> 回滚到Windows 10 协同版之前，建议先从 SEMM 取消注册Surface Hub。 若要了解详细信息，请参阅 [SEMM 中的取消注册 Surface 设备](/surface/unenroll-surface-devices-from-semm)。

## <a name="version-history"></a>版本历史记录

下表总结了对本文所做的更改。

| 版本 | 日期               | 描述                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| V。 1.5  | 2021 年 12 月 1 日  | 已更新以显示对Windows 11的支持
| V。 1.4  | 2020 年 12 月 14 日 | 提供有关为“Surface Hub 2 上为 Windows 10 专业版 和 Enterprise OS 安装驱动程序和固件”的 MSI 文件的[更多信息](#install-surface-hub-2-drivers-and-firmware)，建议根据系统的状态进行第二次重启。                                                          |
| V。 1.3  | 2020 年 12 月 3 日 | 更新了有关 [管理 SEMM 注册](#manage-semm-enrollment)的指南。                                                       |
| V。 1.2  | 2020 年 9 月 29 日 | 用于解决可用性反馈的杂项更新。                                                        |
| V。 1.1  | 2020 年 9 月 15 日 | 在简介中添加了一个说明，其中阐明了安装新 OS 的许可要求。 |
| V。 1.0  | 2020 年 9 月 1 日  | 新文章。                                                                                           |

---
title: 在 2 Windows 10迁移到 Windows 11 专业版/Enterprise Surface Hub 服务器
description: 如何从 Windows 10 协同版 2 Surface Hub迁移到 Windows 10 专业版 或 Windows 10 企业版。
keywords: Surface Hub桌面Surface Hub
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
ms.openlocfilehash: afcdb0b8089343b8703bcbfa28994ef46377aeb3
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448365"
---
# <a name="migrate-to-windows-10-or-windows-11-proenterprise-on-surface-hub-2"></a>在 2 Windows 10迁移到 Windows 11 专业版/Enterprise Surface Hub 服务器

- [文章版本历史记录](#version-history)

Surface Hub 2S 附带Windows 10 协同版软件。 此自定义版本的Windows 10促进在会议室环境中进行协作。 你现在可以运行 Windows 10 或 Windows 11 专业版/Enterprise 来使用你的 Surface Hub 2S，这非常像任何其他电脑。

> [!IMPORTANT]
> 此迁移过程需要您遵循本文中描述的特定过程。 在继续之前，请阅读 [解决方案组件](#solution-components) 和 [迁移和安装工作流](#migration-and-installation-workflow-summary)。

> [!NOTE]
> 在 Surface Hub 2S Windows 10或 Windows 11 专业版/Enterprise 时，需要与设备提供的现有 Windows 10 协同版 许可证不同的新许可证。

通过使用单独的电脑Windows 10 协同版可下载*的 Surface UEFI 配置*器工具，从服务器开始迁移。 该工具将创建一个程序包，其中包含应用于 2S Surface Hub UEFI 设置。  

Surface UEFI 配置器用作 Surface Enterprise 管理模式 (SEMM) 。 它支持在企业环境中集中管理 Surface 设备的固件设置。 有关详细信息，请参阅 [Microsoft Surface Enterprise管理模式](/surface/surface-enterprise-management-mode)。

## <a name="solution-components"></a>解决方案组件

- Surface Hub 2S 设备运行Windows 10 协同版
- 单独的设备运行Windows 10
- 用于创建 SEMM 程序包的 Surface UEFI 配置器工具
- Windows 10或Windows 11 专业版/Enterprise操作系统映像版本 1909 或更高版本
- 两个存储为 16 GB、FAT32 格式的 USB 驱动器
- Windows 10 专业版 2 Microsoft Windows Enterprise Surface Hub Installer 2 Microsoft Windows Installer (MSI) 中的驱动程序和固件
- Internet 连接
- 映像解决方案 (可选) 

## <a name="migration-and-installation-workflow-summary"></a>迁移和安装工作流摘要

| 步骤  | 操作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [在 2S 版上验证 Surface Hub UEFI 版本](#verify-the-uefi-version-on-surface-hub-2s)。                                  | UEFI 版本必须为 *版本 694.2938.768.0* 或更高版本。                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [下载 Surface UEFI 配置器和 Surface Hub 2 驱动程序和固件。](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 在" **[适用于 IT 的 Surface 工具"页上](https://www.microsoft.com/download/details.aspx?id=46703)** ，</a>选择"下载 **"**。 然后选择并下载 **Surface UEFI 配置器 MSI 文件**，然后在单独的电脑上安装该文件。 此外，请下载 Windows 10 专业版 [2 MSI Enterprise上的 Surface Hub 操作系统的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</a> 保存此程序包以在步骤 5 中使用。 |
| 3 | [准备 SEMM 证书。](#prepare-the-semm-certificate)                                                                          | 准备运行 Surface UEFI 配置程序所需的证书，或使用你的当前证书。                                                                                                                                                                                                                                                                                                      |
| 4 | [创建 SEMM 程序包。](#create-a-semm-package)                                                                               | 启动 Surface UEFI 配置器以在 USB 驱动器上创建 SEMM 程序包。 此程序包将包含需要在 2S Surface Hub配置文件。 将这些 SEMM 程序包文件复制到电脑上的文件夹中。                                                                                                                                                                                          |
| 5 | [使用 U 盘映像Windows 10 SEMM 程序包以及驱动程序和固件加载 U 盘。](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 创建包含 U 盘的 U 盘Windows 10映像。 此示例中，驱动器名为 *BOOTME*。 从步骤 2) 向 Surface Hub 2 (上的 Windows 10 专业版 和 Enterprise 操作系统添加驱动程序和固件，将步骤 4) 中的 SEMM 程序包文件 (添加到 *BOOTME* 驱动器。                                                                                                                                                                                                  |
| 6 | [更新 Surface Hub 2S 上的 UEFI 以启用操作系统迁移。](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用 *BOOTME* 驱动器将 Surface Hub 2S 启动到 UEFI 菜单并安装 SEMM 程序包。|
| 7 | [安装Windows 10 专业版或Enterprise。](#install-windows-10-or-windows-11-proenterprise)                                        | 使用 *BOOTME* 驱动器安装Windows 10 专业版或Enterprise版本 1909 或更高版本。                                                                                                                                                                                                                                                                                 |
| 8 | [安装用于客户端和Windows 10 专业版Enterprise。](#install-surface-hub-2-drivers-and-firmware)                                        | 若要确保你的设备具有所有最新的更新和驱动程序，请安装 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Windows 10 专业版 和 Enterprise OS 的驱动程序和固件Surface Hub 2 MSI 文件。</a>                                                                                                                                                                                                                                                                                  |
| 9 | [将 Surface Hub 2S 配置为个人生产力设备。](#configure-recommended-settings)                                        |  启用推荐的设置和应用程序以将 Surface Hub 2S 优化为个人工作效率设备。                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a>在 2S 上验证 UEFI Surface Hub版本

在将 Surface Hub 迁移到 Windows 10 协同版 Windows 10 Desktop 之前，你需要 UEFI 版本 *694.2938.768.0* 或更高版本。

**若要在系统上验证 UEFI 版本，请运行以下代码：**

1. 在 Surface Hub 2S 主页上，选择"开始"，**** 然后在"所有 **AppsSurface****** > " (Surface) 。

2. 选择 **Surface** 以显示有关Surface Hub的信息，包括设备上当前的 UEFI 版本。
   - 如果 UEFI 版本是 *694.2938.768.0* 或更高版本，如下图所示，你可以创建 SEMM 程序包以启用操作系统迁移。

    ![Screenshot shows the "Your Surface" page in the Surface app.](images/shm-fig1.png)

   - 如果 UEFI 版本低于 *版本 694.2938.768.0*，请使用以下方法之一获取较新版本

#### <a name="update-uefi-via-windows-update"></a>通过更新更新 UEFI Windows UEFI

1. 在 Surface Hub 2S 上，以管理员角色**登录**。

    >[!Note]
    > 如果不知道用户名或管理员密码，则需要重置设备。 有关详细信息，请参阅重置[和恢复 Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset)。

1. 转到所有**应用设置** > **** > **更新** > 和安全**Windows更新**，然后安装所有更新。
1. 重启设备。
1. 使用 Surface 应用验证 UEFI 版本。 如果 UEFI 版本不是 *版本 694.2938.768.0* 或更高版本，请重复这些步骤，或使用以下过程获取最新的 UEFI 版本。

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a>通过 BMR 映像中的裸机恢复 (UEFI) UEFI

1. 转到 Surface 恢复[站点并选择](https://support.microsoft.com/surfacerecoveryimage)"**Surface Hub 2S"**。
3. 输入你的中心序列号。 它位于电源连接旁边的 Hub 的后面。
4. 按照说明安装 2020 年更新程序，将映像下载到格式化的 U 盘Windows 10 协同版 U 盘。
5. 更新后，设备在 OOBE (进入) 体验。 无需完成设置。 UEFI 版本已更新。 而是按住电源按钮关闭设备，直到屏幕关闭。

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a>下载 Surface UEFI 配置器和 Surface Hub 2 个驱动程序和固件

在单独的电脑上，按照以下步骤操作：

1. 在" <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> 适用于 IT 的 Surface 工具"页上，</a>选择"下载 **"**。  
1. 选择并下载 Surface UEFI 配置器 MSI 文件，然后将其安装在单独的电脑上。 Surface UEFI 配置器工具无法运行在 Surface Hub 2S Windows 10 协同版安装时。

1. 下载 [Surface Hub 2 驱动程序和固件Windows Installer MSI 文件](https://www.microsoft.com/download/details.aspx?id=101974)。 安装新操作系统时，将使用此文件。

### <a name="prepare-the-semm-certificate"></a>准备 SEMM 证书

如果你之前没有使用过 Surface UEFI 配置器，则需要准备证书。 此证书可确保在 SEMM 中注册设备后，只能使用使用已批准证书创建的程序包修改 UEFI 设置。

如何获取证书取决于组织的规模或复杂性：

- Enterprise组织通常维护自己的基础结构，以根据标准安全做法生成证书。

- 中型企业和其他企业通常选择从合作伙伴提供商获取证书。 对于没有太多 IT 专业知识或缺乏专门的 IT 安全团队的组织，建议使用此选项。

- 或者，您可以使用 PowerShell 脚本生成自签名证书。 有关详细信息，请参阅 [Surface Enterprise管理模式证书要求](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。 或者，您可以使用 PowerShell 创建自己的证书。 有关详细信息，请参阅自 [签名证书](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) 文档。

Surface UEFI 配置器创建的 SEMM 程序包必须使用证书进行保护。 证书先验证配置文件的签名，然后才能应用 UEFI 设置。 有关详细信息，请参阅 [SEMM](/surface/surface-enterprise-management-mode) 文档。

### <a name="create-a-semm-package"></a>创建 SEMM 程序包

1. 在单独的电脑上，安装之前下载的 Surface UEFI 配置器工具。

1. 打开 Surface UEFI 配置器，然后选择"开始 **"**。

   ![Surface UEFI 配置器开始屏幕。](images/shm-fig2.png)

1. 选择 **"Surface 设备"**，然后选择"下一 **步"**。

   ![Screenshot shows the Surface Devices option selected.](images/shm-fig3.png)
  
1. 选择 **配置包**。

   ![Screenshot shows "Select Configuration Package" selected.](images/shm-fig4.png)
  
1. 选择 **"证书保护"**。

   ![屏幕截图显示是选择"选择证书保护"。](images/shm-fig5.png)

   系统将提示你添加证书 .pfx 文件。

   ![Screenshot shows where to add your certificate file.](images/shm-fig6.png)

1. 输入证书密码，然后选择"确定 **"**。

   ![Screenshot shows fields to enter and confirm your certificate password.](images/shm-fig7.png)

1. 选择 **密码保护** 以将密码添加到 Surface UEFI。 每次启动到 UEFI 时，你都需要此密码。 *我们强烈建议你设置用于 2S 的 UEFI Surface Hub密码。*

   ![Screenshot shows where to select Password Protection.](images/shm-fig8.png)

1. 设置 UEFI 密码，然后选择"确定 **"**。

   > [!IMPORTANT]
   > 将密码保存在可供管理密码的 IT 管理员访问的安全Surface Hub。 *如果此密码丢失，则不能恢复。*

   ![Screenshot shows where you set the UEFI password.](images/shm-fig9.png)

1. 选择**Surface Hub 2S"**，然后选择"下一**步"**。

    ![Screenshot shows where to select Surface Hub 2S.](images/shm-fig10.png)

1. 再次 **选择"下一步** "。

    ![Screenshot shows to select Next under "Choose which components".](images/shm-fig10a.png)

1. 若要允许安装 Windows 10 或 Windows 11 专业版/Enterprise，请打开 **EnableOsMigration**，然后选择"下一步 **"**。

    ![Screenshot shows where to select Enable O S Migration.](images/shm-fig11.png)

    ![Screenshot shows where to set Enable OS Migration to on.](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a>管理 SEMM 注册

将设备注册到 SEMM 会影响管理设备。 例如，应用 SEMM 程序包后，所有 UEFI 设置 (UEFI) UEFI 菜单中锁定。 其他设置（如 **用于 PXE 启动的 IPv6）的** 默认值也不可用。

若要在迁移完成后更改 UEFI 设置，请应用另一个 SEMM 程序包，或者从 SEMM 注销设备。 如果应用另一个 SEMM 程序包来更改 UEFI 设置，则必须在生成新的 SEMM 程序包时使用原始证书。 使用 UEFI 配置器工具，将 **EnableOSMigration** ** (保持打开状态，而不是像** 原始迁移步骤) 。

#### <a name="if-you-work-with-partners"></a>如果与合作伙伴合作

如果你的公司将 Surface Hub 2 迁移外包到 Windows 10 或 Windows 11 专业版/Enterprise，你可能希望合作伙伴将 SEMM 证书、SEMM 程序包和 UEFI 密码转移给你。 或者，迁移中心后，你可以立即从 SEMM 取消注册它。 此步骤启用 UEFI 的本地管理和将设备传输给另一方。 但是，我们强烈建议你使用 UEFI 密码，可以在迁移后配置该密码。 若要了解更多信息，请参阅 [管理 Surface UEFI 设置](/surface/manage-surface-uefi-settings)。

#### <a name="to-roll-back-to-windows-10-team"></a>回滚到Windows 10 协同版

如果你选择在迁移后将设备还原Windows 10 协同版，如本文稍后所述，[](#to-roll-back-to-windows-10-team)我们建议你先从 SEMM 注销 Hub。 若要了解更多信息，请参阅 [从 SEMM 注销 Surface 设备](/surface/unenroll-surface-devices-from-semm)。

#### <a name="save-the-semm-package-to-a-usb-drive"></a>将 SEMM 程序包保存到 USB 驱动器

1. 连接 U 盘连接到电脑。
1. 选择 **"中心 2S"**，然后选择"下一 **步"**。

   ![Screenshot shows where to select Hub 2S.](images/shm-fig13.png)

   > [!WARNING]
   > 生成 SEMM 程序包时，将擦除 USB 驱动器上的所有现有数据。 在生成 SEMM 程序包之前，请从 USB 驱动器中删除所需的任何文件。

1. 选择“构建”****。

   ![Screenshot shows where to select Build.](images/shm-fig14.png)

1. 捕获此页面的屏幕截图，然后选择"结束 **"**。 SEMM 程序包现已准备就绪。 它包含 SEMM 程序包 *DfciUpdate.dfi* 和一个包含 *SEMM 指纹*的文本文件，它是证书指纹的最后两个字符。

   ![Screenshot shows where to select End.](images/shm-fig15.png)

4. 保存证书指纹的最后两个字符。 当你在 2S 上应用程序包时，你将需要这些字符Surface Hub SEMM。

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a>使用 2 个驱动程序和固件Windows 10 U 盘、SEMM 程序包Surface Hub U 盘

可以使用以下选项Windows 10 *1909 Enterprise版本 1909* (安装) 或 Windows 11 专业版/) 映像：

- 当前的映像解决方案。

- [Surface Deployment Accelerator](/surface/microsoft-surface-deployment-accelerator)。 使用此工具创建可启动Windows 10映像。 该映像可以包含所有当前Windows 10更新Microsoft Office应用、其他应用以及所需的驱动程序和固件。

- 包含 U 盘或Windows 10/Windows 11 专业版/Enterprise U 盘。 在安装 OOBE Wi-Fi后，此选项才可用 (OOBE) 可用。 设置完成后，在设备上安装Surface Hub 2 个驱动程序和固件[Windows 10 专业版Enterprise](https://www.microsoft.com/download/details.aspx?id=101974)和固件。

以下步骤显示如何从安装媒体创建 U 盘，然后在 Windows 10 专业版 2 MSI 文件上为 Windows 10 专业版 和 Enterprise Surface Hub 操作系统添加 SEMM 程序包文件和驱动程序和固件。 如果使用其他部署方法，请转到本文的 Surface Hub [2S 上的更新 UEFI](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 以启用操作系统迁移部分。

> [!NOTE]
> 完成安装后，您需要一个有效的许可证Windows 10 专业版或Windows 10 企业版许可证与现有的 Windows 10 协同版 许可证分开。

1. 若要创建Windows 10 专业版，请按照说明下载媒体创建工具（位于下载[Windows 10）。](https://www.microsoft.com/software-download/windows10) 若要下载Windows 10 企业版，请转到 [Microsoft 批量许可服务中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。

1. 插入新的 USB 存储驱动器。
1. 打开媒体创建工具，选择" **创建安装媒体"**，然后选择"下一 **步"**。

   ![Screenshot shows the option to create installation media.](images/shm-fig16.png)

3. 选择一种语言，然后选择"**Windows 10****和 64 位 (x64) "**。 然后选择"下一 **步"**。

   ![Screenshot shows where you select the language， O S edition， and architecture type.](images/shm-fig17.png)

4. 选择 **U 盘，** 然后选择"下一 **步"**。

   ![Screenshot shows where to select U S B flash drive.](images/shm-fig18.png)

5. 下载完成后，选择"完成 **"**。

   ![屏幕报告 U S B 驱动器已准备就绪，并包含"完成"按钮。](images/shm-fig19.png)

6. 将 MSI 文件) 上的 Surface Hub Windows 10 专业版 2 (上的 Windows 10 专业版 和 Enterprise 操作系统的 SEMM 程序包文件和驱动程序和固件复制到包含 Windows 10 映像的 U 盘 (*BOOTME*) 的根目录。 BOOTME USB 驱动器将包含：

    - 你的Windows 10可启动映像。

    - 复制到 USB 驱动器根目录的 SEMM 程序包文件：

      - *DfciUpdate.dfi*。
      - 包含 SEMM 指纹的文本文件。  (此示例中，该文件为 *SurfaceUEFI_2020Aug25_1058.txt*.) 自动生成的日期时间戳对应于使用 Surface UEFI 配置器创建文件的日期。

   - Windows 10 专业版 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi Enterprise上的 Surface Hub 操作系统的驱动程序和) 。 将此文件复制到 USB 驱动器的根目录。

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a>在 2S Surface Hub UEFI 以启用操作系统迁移

1. 将 BOOTME 驱动器插入 Surface Hub 2S 上的 USB-A 端口。 有关所需内容的列表，请参阅上一节。

1. 若要启动到 UEFI：

   1. 关闭 (2S) 关闭Surface Hub。
   1. 长按 **音量 +**，然后按下并释放电源按钮。 保持音量 **+** ，直到 UEFI 菜单显示。

      ![绘图显示音量和电源按钮。](images/shm-fig20.png)

3. 当设备重新启动时，输入你之前创建的 UEFI 密码（如果适用 (推荐) 。

   ![系统密码屏幕。](images/shm-fig22.png)

4. 从 UEFI 菜单中，**选择管理。** 然后选择"  **从 USB 安装"**。

   ![Screenshot shows where to select Management and then "Install from U S B".](images/shm-fig21.png)

5. 选择 **"立即重新启动**"，如下图所示。 设备将启动。 它将在窗口中间显示一个白色 Microsoft 徽标，然后关闭。

   ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)

6. 按下并释放电源按钮。 在出现的红色对话框中，选择激活 Surface Enterprise管理模式。

7. 输入双字符证书指纹和 UEFI 设置密码。 然后选择" **确定"**。

   ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)

   > [!NOTE]
   > 在设备上激活 SEMM 后，将应用新的 UEFI 设置 **EnableOSMigration** 。 你无法再访问Windows 10 协同版。 相反，您必须继续执行下一步，并安装 Windows 10 专业版 或 Windows 10 企业版。

   设备重新启动。 它在屏幕中间显示白色徽标，然后再次关闭。

### <a name="install-windows-10-or-windows-11-proenterprise"></a>安装Windows 10或Windows 11 专业版/Enterprise

1. 如果你的可启动Windows 10 Windows 11 专业版/Enterprise驱动器尚未在 Surface Hub 2 USB-A 端口中，则现在插入它。 然后按下并释放电源按钮。

    设备启动时，你将在屏幕中间看到白色徽标。 然后，白色徽标下方出现一个旋转圆圈。

3. 如果 Surface 设备没有自动启动到 U 盘，请拔下 (线，然后将其插回电源) 。 再次插入电缆后，设备应在几秒钟后启动。 然后，你将在屏幕中间看到白色徽标。

    如果设备未打开，请按并释放电源按钮。 在看到屏幕中间的徽标后，立即长按"音量降低"按钮，直到看到白色徽标下方的旋转圆圈。

   ![音量和电源按钮的图片。](images/shm-fig26.png)

4. 当 OOBE (OOBE) 安装启动时，请按照说明安装 Windows 10 或 Windows 11 专业版/Enterprise (版本 1909 或更高版本) 。

### <a name="install-surface-hub-2-drivers-and-firmware"></a>安装 Surface Hub 2 个驱动程序和固件

若要确保你的 Surface Hub 2 是最新的，请安装适用于 Windows 10 专业版 [和 Enterprise 的驱动程序和固件](https://www.microsoft.com/download/details.aspx?id=101974)。 然后重新启动设备。 将 Surface 保持打开状态一小时，然后重新启动它。 系统不会提示你进行第二次重启。 此暂停和额外重启可确保固件已完全更新。

## <a name="configure-recommended-settings"></a>配置建议设置

若要将 Surface Hub 2S 配置为个人工作效率设备，请参阅 Windows 10 [2 Windows 11 专业版/Enterprise 2 Surface Hub配置](surface-hub-2-post-install.md)。

> [!NOTE]
>如果无法按照本文中概述的步骤将设备成功迁移到 Windows 10 或 Windows 11 专业版/Enterprise for Surface Hub 2，请联系 Surface Hub [Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。

## <a name="to-roll-back-to-windows-10-team"></a>回滚到Windows 10 协同版

如果你想要将设备还原到 Windows 10 协同版，请参阅重置和恢复 Surface Hub [2S](surface-hub-2s-recover-reset.md)。

> [!NOTE]
> 在回滚到Windows 10 协同版，我们建议你先从 SEMM 注销Surface Hub注册。 若要了解更多信息，请参阅 [从 SEMM 注销 Surface 设备](/surface/unenroll-surface-devices-from-semm)。

## <a name="version-history"></a>版本历史记录

下表汇总了对本文所做的更改。

| 版本 | 日期               | 说明                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 2020 年 12 月 14 日 | 提供有关[](#install-surface-hub-2-drivers-and-firmware)为"Surface Hub 2 上的 Windows 10 专业版 和 Enterprise 操作系统的驱动程序和固件"安装 MSI 文件的进一步信息，提示可能需要根据系统状态再次重新启动。                                                          |
| v. 1.3  | 2020 年 12 月 3 日 | 使用有关管理 [SEMM 注册的指南进行了更新](#manage-semm-enrollment)。                                                       |
| v. 1.2  | 2020 年 9 月 29 日 | 处理可用性反馈的杂项更新。                                                        |
| v. 1.1  | 2020 年 9 月 15 日 | 简介中新增了一条说明，阐明了安装新操作系统的许可要求。 |
| v. 1.0  | 2020 年 9 月 1 日  | 新文章。                                                                                           |

---
title: 使用 SEMM (Surface) 注册和配置 Surface 设备
description: 了解如何创建 Surface UEFI 配置包来控制 Surface UEFI 的设置，以及如何在 SEMM 中注册 Surface 设备。
keywords: surface Enterprise Management
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: hachinda
manager: laurawi
ms.date: 1/15/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 6df11e1c6e0b28616cb4d365e159f134195c0ecb
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472353"
---
# <a name="enroll-and-configure-surface-devices-with-semm"></a>使用 SEMM 注册并配置 Surface 设备

使用 Microsoft Surface Enterprise管理模式 (SEMM) ，可以在 Surface 设备上安全配置 Surface UEFI 的设置，并在组织中的 Surface 设备上管理这些设置。 当 Surface 设备由 SEMM 管理时，该设备被视为 *已注册* (有时称为已激活) 。 本文介绍如何创建 Surface UEFI 配置包，该包将控制 Surface UEFI 的设置并在 SEMM 中注册 Surface 设备。

有关 SEMM 的更高级概述，请参阅 [Microsoft Surface Enterprise管理模式](surface-enterprise-management-mode.md)。

作为 SEMM 的替代方法，较新的 Surface 设备支持通过Microsoft Intune远程管理固件设置的子集。 有关详细信息，请参阅 [Surface UEFI 设置的Intune管理](surface-manage-dfci-guide.md)。

> [!NOTE]
> 仅通过 UEFI 管理器在 Surface Pro X 上支持 SEMM。 有关详细信息，请参阅[部署、管理和服务Surface Pro X](surface-pro-arm-app-management.md)。

#### <a name="download-and-install-microsoft-surface-uefi-configurator"></a>下载并安装 Microsoft Surface UEFI 配置器

用于创建 SEMM 包的工具是 Microsoft Surface UEFI 配置器。 可以从 Microsoft 下载中心的 [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) 页面下载 Microsoft Surface UEFI 配置器。
运行 Microsoft Surface UEFI 配置器Windows安装程序 (.msi) 文件以开始安装该工具。 安装程序完成后，在"开始"菜单的"所有应用"部分中找到 Microsoft Surface UEFI 配置器。

>[!NOTE]
>仅Windows 10和Windows 11支持 Microsoft Surface UEFI 配置器。

## <a name="create-a-surface-uefi-configuration-package"></a>创建 Surface UEFI 配置包

Surface UEFI 配置包执行将 Surface UEFI 设置的新配置应用到使用 SEMM 管理的 Surface 设备的角色，以及在 SEMM 中注册 Surface 设备的角色。 创建配置包需要具有与 SEMM 一起使用的签名证书，以确保在每个 Surface 设备上配置 UEFI 设置。 有关 SEMM 证书要求的详细信息，请参阅 [Microsoft Surface Enterprise管理模式](surface-enterprise-management-mode.md)。

若要创建 Surface UEFI 配置包，请执行以下步骤：

1. 从"开始"菜单打开 Microsoft Surface UEFI 配置器。

2. 单击**开始**。

3. 单击 **"配置包**"，如图 1 所示。

   ![创建用于 SEMM 注册的包。](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *图 1. 选择配置包以创建用于 SEMM 注册和配置的包*

4. 单击 **"证书保护** "以使用私钥 (.pfx) 添加导出的证书文件，如图 2 所示。 浏览到证书文件的位置，选择该文件，然后单击 **"确定**"。

   ![将 SEM 证书和 Surface UEFI 密码添加到配置包。](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to the configuration package")

   *图 2. 将 SEMM 证书和 Surface UEFI 密码添加到 Surface UEFI 配置包*

5. 当系统提示确认证书密码时，输入并确认证书文件的密码，然后单击 **"确定**"。

6. 单击 **"密码保护** "将密码添加到 Surface UEFI。 每次启动到 UEFI 时都需要此密码。 如果未输入此密码，则将仅显示**电脑信息**"**关于****"、"Enterprise管理**"和 **"退出**"页。 此步骤可选。

7. 出现提示时，输入并确认所选的 Surface UEFI 密码，然后单击 **"确定**"。 如果要清除现有的 Surface UEFI 密码，请将密码字段留空。

8. 如果不希望 Surface UEFI 包应用于特定设备，请在 **"选择要面向哪个 Surface 类型** "页上，单击相应设备下方的滑块，使其处于 **"关闭** "位置，如图 3 所示。
   > [!TIP] 
   > 必须选择设备，因为默认情况下未选择任何设备。 向右滚动以查看所有可用设备。

   ![为包兼容性选择设备，然后向右滚动以查看所有可用设备](images/surface-semm-enroll-fig3.png "Choose devices for package compatibility")

   ![为包兼容性选择设备。](images/surface-semm-enroll-fig3a.png "Choose devices for package compatibility")


   *图 3. 为包兼容性选择设备*

9. 单击“下一步”****。

10. 如果要停用托管 Surface 设备上的组件，请在 **"选择要激活或停用哪些组件** "页上，单击要停用的任何设备或设备组旁边的滑块，使滑块处于 **"关闭** "位置。  (图 4.) 每个设备的默认配置处于 **打开状态**。 单击 **"重置** "按钮可将所有滑块返回到默认位置。

    ![禁用或启用 Surface 组件。](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *图 4. 禁用或启用单个 Surface 组件*

11. 单击“下一步”****。

12. 若要在 Surface UEFI 中启用或禁用高级选项或显示 Surface UEFI 页面，请在 **"选择设备的高级设置** "页上，单击所需设置旁边的滑块，将该选项配置为" **打开** "或 **"关闭** " (图 5) 中所示。 在 **UEFI"头版** "部分中，可以使用 **"安全**"、" **设备**"和 **"启动** "的滑块来控制启动到 Surface UEFI 的用户可用的页面。  (有关 Surface UEFI 设置的详细信息，请参阅 ["管理 Surface UEFI 设置](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)"。) 在选择完用于生成和保存包的选项后，单击" **生成**"。 

    ![控制高级 Surface UEFI 设置和 Surface UEFI 页面。](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *图 5. 使用 SEMM 控制高级 Surface UEFI 设置和 Surface UEFI 页面*

13. 在 **"另存为** "对话框中，指定 Surface UEFI 配置包名称，浏览到要保存文件的位置，然后单击 **"保存**"。

14. 创建并保存包时，将显示 **"成功** "页。

    >[!NOTE]
    >记录此页上显示的证书指纹字符，如图 6 所示。 你需要这些字符来确认 SEMM 中新 Surface 设备的注册。 单击 **"结束** "完成包创建并关闭 Microsoft Surface UEFI 配置器。
    
    ![显示证书指纹字符。](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")
    
    *图 6. 证书指纹的最后两个字符显示在"成功"页上*

创建 Surface UEFI 配置包后，可以注册或配置 Surface 设备。

>[!NOTE]
>创建 Surface UEFI 配置包时，桌面上会显示一个日志文件，其中包含配置包设置和选项的详细信息。

## <a name="enroll-a-surface-device-in-semm"></a>在 SEMM 中注册 Surface 设备
执行 Surface UEFI 配置包时，SEMM 证书和 Surface UEFI 配置文件将暂存在 Surface 设备的固件存储中。 当 Surface 设备重新启动时，Surface UEFI 将处理这些文件，并开始应用 Surface UEFI 配置或在 SEMM 中注册 Surface 设备的过程，如图 7 所示。

![用于配置 Surface UEFI 或注册的 SEMM 过程。](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*图 7. 用于配置 Surface UEFI 或注册 Surface 设备的 SEMM 过程*

在 SEMM 中注册 Surface 设备之前，请确保手头有证书指纹的最后两个字符。 需要这些字符来确认设备的注册 (请参阅图 6) 。

若要使用 Surface UEFI 配置包在 SEMM 中注册 Surface 设备，请执行以下步骤：

1. 在要在 SEMM 中注册的 Surface 设备上运行 Surface UEFI 配置包.msi文件。 这将在设备固件中预配 Surface UEFI 配置文件。
2. 选择 **"我接受许可协议"** 复选框中的条款以接受最终用户许可协议 (EULA) ，然后单击 **"安装** "以开始安装过程。
3. 单击 **"完成** "以完成 Surface UEFI 配置包安装，并在系统提示时重启 Surface 设备。
4. Surface UEFI 将加载配置文件，并确定设备上未启用 SEMM。 然后，Surface UEFI 将开始 SEMM 注册过程，如下所示：
   * Surface UEFI 将验证 SEMM 配置文件是否包含 SEMM 证书。
   * Surface UEFI 将提示输入证书指纹的最后两个字符，以确认 SEMM 中 Surface 设备的注册，如图 8 所示。

      ![SEMM 注册需要证书指纹的最后两个字符。](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *图 8. SEMM 注册需要证书指纹的最后两个字符*

   * Surface UEFI 将 SEMM 证书存储在固件中，并应用 Surface UEFI 配置文件中指定的配置设置。
   
5. Surface 设备现已在 SEMM 中注册，将启动到Windows。

可以通过查找"**程序和功能**"中的 **Microsoft Surface 配置包**（如图 9) 中所示 (或存储在 **Microsoft Surface UEFI 配置器**日志中的事件（在事件查看器 (中的**应用程序和服务日志**下找到的事件）来验证 Surface 设备是否已成功注册，如图 10) 中所示。

:::image type="content" alt-text="在&quot;程序和功能&quot;中验证 SEMM 中 Surface 设备的注册。" source="images/surface-semm-enroll-fig9.png":::

*图 9. 在"程序和功能"中验证 SEMM 中 Surface 设备的注册*

:::image type="content" alt-text="在 事件查看器 中验证 SEMM 中的 Surface 设备注册。" source="images/surface-semm-enroll-fig10.png":::

*图 10. 在 事件查看器 中验证 SEMM 中 Surface 设备的注册*

还可以验证设备是否已在 Surface UEFI 中的 SEMM 中注册 - 注册设备时，Surface UEFI 将包含**Enterprise管理**页 (如图 11) 所示。

:::image type="content" alt-text="Surface UEFI Enterprise管理页。" source="images/surface-semm-enroll-fig11.png":::

*图 11. Surface UEFI Enterprise管理页*


## <a name="configure-surface-uefi-settings-with-semm"></a>使用 SEMM 配置 Surface UEFI 设置

在 SEMM 中注册设备后，可以运行使用相同 SEMM 证书签名的 Surface UEFI 配置包来应用新的 Surface UEFI 设置。 下次设备启动时会自动应用这些设置，而不会与用户进行任何交互。 可以使用应用程序部署解决方案（如Microsoft Endpoint Configuration Manager）将 Surface UEFI 配置包部署到 Surface 设备，以更改或管理 Surface UEFI 中的设置。

有关如何使用Configuration Manager部署Windows安装程序 (.msi) 文件的详细信息，请参阅[使用Microsoft Endpoint Configuration Manager部署和管理应用程序](/mem/configmgr/apps/deploy-use/deploy-applications)。

假设已使用密码保护 Surface UEFI。 在这种情况下，没有密码尝试启动到 Surface UEFI 的用户将仅向其显示**电脑信息**"**关于**"、"**Enterprise管理**"和 **"退出**"页。

如果未使用密码保护 Surface UEFI 或用户正确输入密码，则使用 SEMM 配置的设置将变暗 (不可用) 指示  **某些设置由组织管理**，如图 12 所示。

:::image type="content" alt-text="由 SEMM 管理的设置在 Surface UEFI 中处于禁用状态。" source="images/surface-semm-enroll-fig12.png":::

*图 12. 由 SEMM 管理的设置将在 Surface UEFI 中禁用*

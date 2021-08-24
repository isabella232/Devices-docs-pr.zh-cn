---
title: '使用 SEMM 注册和配置 Surface (Surface) '
description: 了解如何创建 Surface UEFI 配置包以控制 Surface UEFI 的设置，以及如何在 SEMM 中注册 Surface 设备。
keywords: 图面企业管理
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
ms.openlocfilehash: b7edb07fdd14d3940358a667f81513dd453769c6
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911007"
---
# <a name="enroll-and-configure-surface-devices-with-semm"></a>使用 SEMM 注册并配置 Surface 设备

借助 Microsoft Surface Enterprise Management Mode (SEMM) ，你可以安全地在 Surface 设备上配置 Surface UEFI 的设置，并管理组织中 Surface 设备的这些设置。 当 Surface 设备由 SEMM 管理时，该设备被视为已** 注册 (有时称为已激活) 。 本文介绍了如何创建 Surface UEFI 配置包，该配置包不仅控制 Surface UEFI 的设置，还将在 SEMM 中注册 Surface 设备。

有关 SEMM 的更高级概述，请参阅[Microsoft Surface Enterprise 管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

作为 SEMM 的替代方法，较新的 Surface 设备支持通过远程管理固件设置的子集Microsoft Intune。 有关详细信息，请参阅 Surface [UEFI](surface-manage-dfci-guide.md)设置的 Intune 管理。

> [!NOTE]
> 仅通过 UEFI Surface Pro X 支持 SEMM。 有关详细信息，请参阅部署[、管理和维护 Surface Pro X。](surface-pro-arm-app-management.md)

#### <a name="download-and-install-microsoft-surface-uefi-configurator"></a>下载并安装 Microsoft Surface UEFI 配置器

用于创建 SEMM 程序包的工具是 Microsoft Surface UEFI 配置器。 你可以从 Microsoft 下载中心的 Surface Tools [for IT 页面](https://www.microsoft.com/download/details.aspx?id=46703) 下载 Microsoft Surface UEFI 配置器。
运行 Microsoft Surface UEFI Configurator Windows Installer (.msi) 文件以开始安装该工具。 安装程序完成后，在应用的"所有应用"部分查找 Microsoft Surface UEFI "开始"菜单。

>[!NOTE]
>Microsoft Surface UEFI 配置器仅在 Windows 10。

## <a name="create-a-surface-uefi-configuration-package"></a>创建 Surface UEFI 配置包

Surface UEFI 配置包同时执行将 Surface UEFI 设置的新配置应用到使用 SEMM 管理的 Surface 设备的角色和在 SEMM 中注册 Surface 设备的角色。 创建配置包需要具有签名证书以与 SEMM 一起使用，以确保在每个 Surface 设备上配置 UEFI 设置。 有关 SEMM 证书的要求详细信息，请参阅 Microsoft [Surface Enterprise管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

若要创建 Surface UEFI 配置包，请按照以下步骤操作：

1. 从应用打开 Microsoft Surface UEFI "开始"菜单。
2. 单击**开始**。
3. 单击 **"配置包**"，如图 1 所示。

   ![创建用于 SEMM 注册的程序包。](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *图 1. 选择配置包以创建用于 SEMM 注册和配置的程序包*

4. 单击 **"证书** 保护"以使用私钥 (.pfx) 导出的证书文件，如图 2 所示。 浏览到证书文件的位置，选择该文件，**然后单击确定。**

   ![将 SEM 证书和 Surface UEFI 密码添加到配置包。](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *图 2. 将 SEMM 证书和 Surface UEFI 密码添加到 Surface UEFI 配置包*

5. 当系统提示您确认证书密码时，请输入并确认证书文件的密码，然后单击"确定 **"。**
6. 单击 **"密码保护** "将密码添加到 Surface UEFI。 每次启动到 UEFI 时，都需要此密码。 如果未输入此密码，则只显示**电脑**信息、关于**** Enterprise**管理**"和"退出"页面。 **** 此步骤可选。
7. 出现提示时，输入并确认为 Surface UEFI 选择的密码，然后单击"确定 **"。** 如果你想要清除现有的 Surface UEFI 密码，将密码字段留空。
8. 如果你不希望 Surface UEFI 程序包应用于特定设备，请在"选择要面向的**Surface**类型"页上，单击相应的 Surface Book 或 Surface Pro 4 图像下方的滑块，以便它处于**关闭位置。**  (如图 3.) 
   > [!NOTE] 
   > 你必须选择设备，因为默认情况下未选择任何设备。

   ![选择设备进行程序包兼容性。](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *图 3. 选择设备进行程序包兼容性*

9. 单击“下一步”****。
10. 如果要在托管 Surface 设备上停用组件，请在"选择要激活或停用**** 的组件"页上，单击要停用的任何设备或设备组旁边的滑块，以便滑块处于"关闭 **"** 位置。  (图 4.) 设备的默认配置是 **"打开"。** 如果要 **将所有** 滑块返回到默认位置，请单击"重置"按钮。

    ![禁用或启用 Surface 组件。](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *图 4. 禁用或启用单个 Surface 组件*

11. 单击“下一步”****。
12. 若要在 Surface UEFI 中启用或禁用高级选项或显示 Surface UEFI 页面，请在"选择设备的高级设置"页上，单击所需设置旁边的滑块，将该选项配置为"**** 开"**** 或"关" (如图 5) 所示。 **** 在**UEFI**首页部分中，可以使用安全、设备和启动的滑块来控制哪些**** 页面可供启动到**** Surface UEFI 的用户使用。 ****  (有关 Surface UEFI 设置的详细信息，请参阅管理[Surface UEFI](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)设置 。) **** 完成选择用于生成和保存程序包的选项后单击生成。

    ![控制高级 Surface UEFI 设置和 Surface UEFI 页面。](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *图 5. 使用 SEMM 控制高级 Surface UEFI 设置和 Surface UEFI 页面*

13. 在 **"另存为**"对话框中，指定 Surface UEFI 配置包的名称，浏览到要保存文件的位置，然后单击"保存 **"。**
14. 创建并保存程序包时，将显示 **"成功"** 页。

>[!NOTE]
>记录此页上显示的证书指纹字符，如图 6 所示。 你将需要这些字符来确认在 SEMM 中注册新的 Surface 设备。 单击 **"结束** "完成程序包创建并关闭 Microsoft Surface UEFI 配置器。

![证书指纹字符的显示。](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*图 6. 证书指纹的最后两个字符显示在"成功"页上*

现在，你已创建 Surface UEFI 配置程序包，你可以注册或配置 Surface 设备。

>[!NOTE]
>创建 Surface UEFI 配置包时，日志文件在桌面上创建一个配置包设置和选项的详细信息。

## <a name="enroll-a-surface-device-in-semm"></a>在 SEMM 中注册 Surface 设备
执行 Surface UEFI 配置包时，SEMM 证书和 Surface UEFI 配置文件将存储在 Surface 设备的固件存储中。 当 Surface 设备重新启动时，Surface UEFI 将处理这些文件并开始应用 Surface UEFI 配置或在 SEMM 中注册 Surface 设备的过程，如图 7 所示。

![Surface UEFI 或注册配置的 SEMM 流程。](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*图 7. Surface UEFI 配置或 Surface 设备的注册的 SEMM 过程*

在开始在 SEMM 中注册 Surface 设备的过程之前，请确保你已拥有证书指纹的最后两个字符。 你将需要这些字符来确认设备的注册 (参见图 6) 。

若要使用 Surface UEFI 配置包在 SEMM 中注册 Surface 设备，请按照以下步骤操作：

1. 在你想要在 SEMM .msi Surface 设备上运行 Surface UEFI 配置包文件。 这将在设备的固件中预配 Surface UEFI 配置文件。
2. 选中 **"我接受许可协议中的**条款"复选框以接受最终用户许可协议 (EULA) ，然后单击"安装"开始安装过程。 ****
3. 单击 **完成** 以完成 Surface UEFI 配置包安装，当系统提示你这样做时，重新启动 Surface 设备。
4. Surface UEFI 将加载配置文件并确定设备上未启用 SEMM。 Surface UEFI 将开始 SEMM 注册过程，如下所示：
   * Surface UEFI 将验证 SEMM 配置文件是否包含 SEMM 证书。
   * Surface UEFI 将提示你输入证书指纹的最后两个字符以确认 Surface 设备在 SEMM 中注册，如图 8 所示。

      ![SEMM 注册需要证书指纹的最后两个字符。](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *图 8. 在 SEMM 中注册需要证书指纹的最后两个字符*

   * Surface UEFI 将 SEMM 证书存储在固件中，并应用在 Surface UEFI 配置文件中指定的配置设置。
   
5. Surface 设备现已在 SEMM 中注册，将启动到Windows。

通过查找"程序和功能 ("中的 Microsoft **Surface 配置**包（如图 9) **** 所示）或在**存储在 Microsoft Surface UEFI**配置器日志中的事件（在事件查看器 (中的应用程序和服务日志下找到，如图 10 ****) 所示）中，可以验证 Surface 设备已成功注册 SEMM。

![在"程序和功能"中验证 Surface 设备在 SEMM 中的注册情况。](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*图 9. 在"程序和功能"中验证 Surface 设备在 SEMM 中的注册*

![在事件查看器中验证 Surface 设备在 SEMM 中的注册。](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*图 10. 在事件查看器中验证 Surface 设备在 SEMM 中的注册*

还可以验证设备是否注册到 Surface UEFI 的 SEMM 中 - 当设备注册时，Surface UEFI 将包含**Enterprise**管理页面 (如图 11) 所示。

![Surface UEFI Enterprise管理页面。](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*图 11. Surface UEFI Enterprise管理页面*


## <a name="configure-surface-uefi-settings-with-semm"></a>使用 SEMM 配置 Surface UEFI 设置

在 SEMM 中注册设备后，你可以运行使用相同 SEMM 证书签名的 Surface UEFI 配置包，以应用新的 Surface UEFI 设置。 这些设置将在设备下次启动时自动应用，无需用户的任何交互。 可以使用应用程序部署解决方案（如 Microsoft Endpoint Configuration Manager）将 Surface UEFI 配置包部署到 Surface 设备，以更改或管理 Surface UEFI 中的设置。

有关如何使用 Configuration Manager 部署 Windows Installer (.msi) 文件，请参阅使用 Microsoft Endpoint Configuration Manager 部署[和管理应用程序](https://technet.microsoft.com/library/mt627959)。

如果你已使用密码保护 Surface UEFI，没有密码的用户尝试启动到 Surface UEFI 将只显示电脑信息****、关于、Enterprise**** 管理和退出页面。 **** ****

如果没有使用密码保护 Surface UEFI，或者用户正确输入密码，则使用 SEMM 配置的设置将灰显 (不可用) 并且文本"某些设置由组织管理"将显示在页面顶部，如图 12 所示。

![设置在 Surface UEFI 中禁用的 SEMM 管理。](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*图 12. 设置在 Surface UEFI 中禁用由 SEMM 管理*

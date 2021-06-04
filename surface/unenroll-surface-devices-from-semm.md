---
title: 来自 SEMM （Surface）的取消注册 Surface 设备
description: 了解如何使用 Surface UEFI reset 程序包或恢复请求选项从 SEMM 取消注册设备。
keywords: surface 企业管理
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: aa24ff1ac8a93ebc8078490c5e0c8fa34c940a25
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830764"
---
# 从 SEMM 取消注册 Surface 设备

当 Surface 设备注册到 Surface Enterprise 管理模式（SEMM）时，证书将存储在该设备的固件中。 当设备注册在 SEMM 中时，该证书和 SEMM 中的注册将阻止对 Surface UEFI 设置或选项进行任何未经授权的更改。 若要将 Surface UEFI 设置的控制权还原到用户，Surface 设备必须是从 SEMM 中 unenrolled 的过程，有时会将其描述为重置或恢复。 可使用两种方法从 SEMM 取消注册设备： Surface UEFI 重置包和恢复请求。

>[!WARNING]
>若要从 SEMM 取消注册设备并还原用户对 Surface UEFI 设置的控制，您必须拥有用于在 SEMM 中注册设备的 SEMM 证书。 如果此证书已丢失或损坏，则不能取消注册 SEMM。 相应地备份和保护您的 SEMM 证书。

有关 SEMM 的详细信息，请参阅[Microsoft Surface 企业管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

##  <a name="unenroll-a-surface-device-from-semm-with-a-surface-uefi-reset-package"></a>使用 Surface UEFI reset 程序包取消注册 SEMM 中的 Surface 设备

Surface UEFI 重置程序包是用于从 SEMM 取消注册 Surface 设备的主要方法。 与 Surface UEFI 配置包一样，reset 程序包是在设备上配置 SEMM 的 Windows Installer （.msi）文件。 与配置包不同，重置程序包会将 Surface 设备上的 Surface UEFI 配置重置为其默认设置，删除 SEMM 证书，然后从 SEMM 取消注册该设备。

重置程序包专为单个 Surface 设备创建。 若要开始创建重置程序包的过程，你将需要要取消注册的设备的序列号，以及用于注册设备的 SEMM 证书。 你可以在 Surface UEFI 的**PC 信息**页面上找到 surface 设备的序列号，如图1所示。 即使 Surface UEFI 受密码保护，输入的密码不正确，也会显示此页面。

![显示 Surface 设备序列号](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*图 1. Surface 设备的序列号显示在 "Surface UEFI 电脑信息" 页面上*

>[!NOTE]
>若要启动到 Surface UEFI，请在设备关闭时同时按**成交量**和**电源**。 保持**音量**，直到显示 Surface 徽标，并且设备开始启动。

若要创建 Surface UEFI 重置程序包，请执行以下步骤：

1. 从 "开始" 菜单打开 Microsoft Surface UEFI 配置器。
2. 单击**开始**。
3. 单击 "**重置程序包**"，如图2所示。

   ![选择 "重置包" 以创建从 SEMM 的取消注册 Surface 设备的程序包](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *图 2. 单击 "重置包" 以创建程序包以从 SEMM 取消注册 Surface 设备*

4. 单击 "**证书保护**" 以添加带有私钥（.pfx）的 SEMM 证书文件，如图3所示。 通过浏览找到您的证书文件的位置，选择该文件，然后单击 **"确定"**。

   ![将 SEMM 证书添加到 Surface UEFI 重置程序包](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *图 3. 将 SEMM 证书添加到 Surface UEFI 重置程序包*

5. 单击“下一步”****。
6. 键入要从 SEMM 取消注册的设备的序列号（如图4所示），然后单击 "**生成**" 以生成 Surface UEFI reset 程序包。

   ![使用 Surface 设备序列号创建 Surface UEFI 重置包](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *图 4. 使用 Surface 设备的序列号创建 Surface UEFI 重置包*

7. 在 "**另存为**" 对话框中，指定 Surface UEFI 重置程序包的名称，浏览到要保存文件的位置，然后单击 "**保存**"。
8. 程序包生成完成后，将显示**成功**的页面。 单击 "**结束**" 以完成程序包创建并关闭 MICROSOFT Surface UEFI 配置器。

在 Surface 设备上运行 Surface UEFI 重置程序包 Windows Installer （.msi）文件，从 SEMM 取消注册设备。 重置程序包将需要重新启动才能执行取消注册操作。 在设备 unenrolled 后，您可以通过确保 "**程序和功能**" （如图5所示）中的**Microsoft Surface Configuration 程序包**项目不再存在来验证是否成功删除。

![屏幕显示设备已注册 SEMM](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*图 5. "程序和功能" 中的 Microsoft Surface 配置包项目的存在表示设备已注册 SEMM*

##  <a name="unenroll-a-surface-device-from-semm-with-a-recovery-request"></a>使用恢复请求取消注册 Surface 设备 SEMM

在某些情况下，Surface UEFI 重置程序包可能无法用于取消注册 SEMM 中的 Surface 设备（例如，Windows 变得不可用）。 在这些方案中，你可以使用从 Surface UEFI 内部生成的恢复请求取消注册设备。 即使在没有 Surface UEFI 密码的设备上，也可以启动恢复请求进程。

恢复请求进程从 surface 设备上的 Surface UEFI 启动，在另一台计算机上通过 Microsoft Surface UEFI 配置器批准，然后在 Surface UEFI 中完成。 与重置程序包一样，使用 Microsoft Surface UEFI 配置器批准恢复请求需要访问用于注册 Surface 设备的 SEMM 证书。

若要启动恢复请求，请按照下列步骤操作：

1. 引导要从 SEMM unenrolled 到 Surface UEFI 的 Surface 设备。
2. 如果出现提示，请键入 Surface UEFI 密码。
3. 单击 "**企业管理**" 页面，如图6所示。

   ![企业管理页面](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *图 6. 在 SEMM 中注册的设备上，企业管理页面显示在 Surface UEFI 中*

4. 单击或按 "**开始**"。
5. 单击或按 "**下一步**" 以开始恢复请求过程。
   >[!NOTE]
   >恢复请求在创建后将在两个小时内过期。 如果此时未完成恢复请求，则必须重新启动恢复请求进程。
6. 从 "**选择 SEMM 重置密钥**" 页面上显示的证书列表中选择 " **SEMM 证书**" （如图7所示），然后单击或按 "**下一步**"。

   ![为你的恢复请求选择 SEMM 证书](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *图 7. 为你的恢复请求选择 SEMM 证书（重置请求）*

7. 在 "**输入 SEMM 重置验证代码**" 页面上，你可以单击**QR 代码**或**文本**按钮以显示你的恢复请求（重置请求）（如图8所示）或**Usb**按钮以将你的恢复请求（重置请求）另存为 USB 驱动器的文件，如图9所示。

   ![作为 QR 码显示的恢复请求](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *图 8. 作为 QR 代码显示的恢复请求（重置请求）*

   ![将恢复请求保存到 USB 驱动器](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *图 9. 将恢复请求（重置请求）保存到 USB 驱动器*

   * 若要使用 QR 代码恢复请求（重置请求），请使用移动设备上的 QR 读取器应用读取代码。 QR 读取器应用会将 QR 代码转换为字母数字字符串。 然后，你可以通过电子邮件或消息将该字符串发送到将通过 Microsoft Surface UEFI 配置器生成重置验证代码的管理员。
   * 若要使用以文件形式保存到 USB 驱动器的恢复请求（重置请求），请使用 USB 驱动器将文件传输到 Microsoft Surface UEFI 配置器将用于生成重置验证代码的计算机。 也可以从另一台设备上的 USB 驱动器复制文件，以便通过网络通过网络发送或传输。
   * 若要将恢复请求（重置请求）用作文本，只需直接在 Microsoft Surface UEFI 配置器中键入文本。

8. 从另一台计算机上的 "开始" 菜单打开 Microsoft Surface UEFI 配置器。
    >[!NOTE]
    >Microsoft Surface UEFI 配置程序必须在能够对 SEMM 证书的证书链进行身份验证的环境中运行。
9. 单击**开始**。
10. 单击 "**恢复请求**"，如图10所示。

    ![启动流程以批准恢复请求](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *图 10. 单击 "恢复请求" 开始批准恢复请求的过程*

11. 单击 "**证书保护**" 以通过 SEMM 证书对恢复请求进行身份验证。
12. 通过浏览找到并选择 SEMM 证书文件，然后单击 **"确定"**。
13. 当系统提示您输入证书密码（如图11所示）时，请键入并确认证书文件的密码，然后单击 **"确定"**。

    ![键入 SEMM 证书的密码](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *图 11. 键入 SEMM 证书的密码*

14. 单击“下一步”****。
15. 输入恢复请求（重置请求），然后单击 "**生成**" 以创建重置验证代码（如图12所示）。

    ![输入恢复请求](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *图 12. 输入恢复请求（重置请求）*

    * 如果在要重置的 Surface 设备上将恢复请求（重置请求）显示为文本，请使用键盘在所提供的字段中键入恢复请求（重置请求）。
    * 如果你将恢复请求（重置请求）显示为 QR 代码，然后使用消息或电子邮件应用程序通过 Microsoft Surface UEFI 配置程序将代码发送到计算机，请将该代码复制并粘贴到所提供的字段中。
    * 如果将恢复请求（重置请求）另存为 USB 驱动器的文件，请单击 "**导入**" 按钮，通过浏览找到并选择恢复请求（重置请求）文件，然后单击 **"确定"**。

16. 重置验证代码显示在 Microsoft Surface UEFI 配置器中，如图13所示。

    ![显示重置验证码](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *图 13. Microsoft Surface UEFI 配置器中显示的重置验证代码*

    * 单击 "**共享**" 按钮以通过电子邮件发送重置验证码。

17. 在 Surface 设备上提供的字段中输入重置验证码（如图8所示），然后单击或按 "**验证**" 以重置设备并从 SEMM 取消注册设备。
18. 在**SEMM 重置成功**页面上单击或按 "**立即重启**" 以完成来自 SEMM 的取消注册，如图14所示。

    ![从 SEMM 成功取消注册的示例显示](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *图 14. 成功取消注册 SEMM*

19. 单击 Microsoft Surface UEFI 配置器中的 "**结束**" 以完成恢复请求（重置请求）进程并关闭 MICROSOFT Surface UEFI 配置器。



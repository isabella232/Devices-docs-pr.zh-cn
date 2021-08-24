---
title: '从 SEMM 或 Surface (注销 Surface) '
description: 了解如何使用 Surface UEFI 重置程序包或恢复请求选项从 SEMM 注销设备。
keywords: 图面企业管理
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
ms.openlocfilehash: 8584ae4ade7d7a043438206230cb24d146b586cb
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911667"
---
# <a name="unenroll-surface-devices-from-semm"></a>从 SEMM 取消注册 Surface 设备

当 Surface 设备在 SEMM Enterprise管理模式下 (时) 证书存储在该设备的固件中。 在 SEMM 中注册设备时，存在该证书并注册 SEMM 可防止对 Surface UEFI 设置或选项进行未经授权的更改。 若要将 Surface UEFI 设置控制还原到用户，Surface 设备必须从 SEMM 注销，此过程有时称为重置或恢复。 有两种方法可用于从 SEMM 注销设备：Surface UEFI 重置程序包和恢复请求。

>[!WARNING]
>若要从 SEMM 注销设备并恢复用户对 Surface UEFI 设置的控制，你必须拥有用于在 SEMM 中注册设备的 SEMM 证书。 如果此证书丢失或损坏，则不能从 SEMM 注销。 相应地备份和保护 SEMM 证书。

有关 SEMM 详细信息，请参阅[Microsoft Surface Enterprise管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

## <a name="unenroll-a-surface-device-from-semm-with-a-surface-uefi-reset-package"></a>使用 Surface UEFI 重置程序包从 SEMM 注销 Surface 设备

Surface UEFI 重置程序包是你将用于从 SEMM 注销 Surface 设备的主要方法。 与 Surface UEFI 配置包一样，重置程序包是一个Windows安装程序 (.msi) 文件，用于配置设备上 SEMM。 与配置包不同，重置程序包将 Surface 设备上 Surface UEFI 配置重置为默认设置，删除 SEMM 证书，并从 SEMM 取消注册设备。

重置程序包专为单个 Surface 设备创建。 要开始创建重置程序包的过程，你需要要注销的设备序列号，以及用于注册设备的 SEMM 证书。 可以在 Surface UEFI 的电脑信息页面上找到**** Surface 设备的序列号，如图 1 所示。 即使 Surface UEFI 受密码保护且输入了不正确的密码，也将显示此页面。

![将显示 Surface 设备的序列号。](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*图 1. Surface 设备的序列号显示在 Surface UEFI 电脑信息页面上*

>[!NOTE]
>若要启动到 Surface UEFI，请同时按 **"调高音量** "和" **电源** "，同时关闭设备。 调 **高音量** ，直到显示 Surface 徽标并且设备开始启动。

若要创建 Surface UEFI 重置程序包，请按照以下步骤操作：

1. 从应用打开 Microsoft Surface UEFI "开始"菜单。
2. 单击**开始**。
3. 单击 **"重置程序包**"，如图 2 所示。

   ![选择"重置程序包"以创建从 SEMM 注销 Surface 设备的程序包。](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *图 2. 单击重置程序包以创建从 SEMM 注销 Surface 设备的程序包*

4. 单击 **证书保护** 以使用私钥 (.pfx) 添加 SEMM 证书文件，如图 3 所示。 浏览到证书文件的位置，选择该文件，**然后单击确定。**

   ![将 SEMM 证书添加到 Surface UEFI 重置程序包。](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *图 3. 将 SEMM 证书添加到 Surface UEFI 重置程序包*

5. 单击“下一步”****。
6. 键入你想要从 SEMM (注销的设备的序列号，如图 4) 中所示，然后单击生成以生成 Surface UEFI**** 重置程序包。

   ![创建序列号为 Surface 设备的 Surface UEFI 重置程序包。](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *图 4. 使用 Surface 设备的序列号创建 Surface UEFI 重置程序包*

7. 在 **"另存为**"对话框中，指定 Surface UEFI 重置程序包的名称，浏览到要保存文件的位置，然后单击"保存 **"。**
8. 包生成完成后，将显示 **"成功"** 页。 单击 **"结束** "以完成程序包创建并关闭 Microsoft Surface UEFI 配置器。

在 Surface 设备上运行 Surface UEFI 重置Windows安装程序 (.msi) 文件以从 SEMM 注销该设备。 重置程序包将需要重新启动才能执行注销操作。 注销设备后，可以通过确保"程序和功能" (中显示的 **"Microsoft Surface 配置**包"项不再存在) 验证是否**** 成功删除。

![显示设备在 SEMM 中注册的屏幕。](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*图 5. "程序和功能"中是否存在"Microsoft Surface 配置包"项指示设备已注册 SEMM*

## <a name="unenroll-a-surface-device-from-semm-with-a-recovery-request"></a>使用恢复请求从 SEMM 注销 Surface 设备

在某些情况下，Surface UEFI 重置程序包可能不是从 SEMM (注销 Surface 设备的可行选项，例如，Windows已) 。 在这些情况下，可以使用从 Surface UEFI 中生成的恢复请求注销设备。 即使在没有 Surface UEFI 密码的设备上也可以启动恢复请求过程。

恢复请求过程从 Surface 设备的 Surface UEFI 启动，在另一计算机上通过 Microsoft Surface UEFI 配置程序批准，然后在 Surface UEFI 中完成。 与重置程序包一样，使用 Microsoft Surface UEFI 配置程序批准恢复请求需要访问用于注册 Surface 设备的 SEMM 证书。

若要启动恢复请求，请按照以下步骤操作：

1. 将要从 SEMM 注销的 Surface 设备启动到 Surface UEFI。
2. 如果系统提示你这样做，请键入 Surface UEFI 密码。
3. 单击 **"Enterprise**管理"页，如图 6 所示。

   ![Enterprise"管理"页。](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *图 6. "Enterprise管理"页显示在在 SEMM 中注册的设备的 Surface UEFI 中*

4. 单击或按**入门。**
5. 单击或按 **"下一步** "开始恢复请求过程。
   >[!NOTE]
   >恢复请求将在创建后的两小时后过期。 如果此时未完成恢复请求，您必须重新启动恢复请求进程。
6. Select **SEMM Certificate** from the list of certificates displayed on the **Choose a SEMM reset key** page (shown in Figure 7) ， and then click or press **Next**.

   ![为恢复请求选择 SEMM 证书。](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *图 7. 为恢复请求选择 SEMM 证书 (重置请求) *

7. 在"输入**SEMM**重置验证码"页上，可以单击 **"QR**代码"或"文本"按钮显示恢复请求 (重置请求) （如图 8 所示）或**USB**按钮将恢复请求 (重置请求) 另存为文件保存到 USB 驱动器，如图 9 所示。 ****

   ![恢复请求显示为 QR 代码。](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *图 8. 重置请求 (重置) 显示为 QR 代码*

   ![将恢复请求保存到 USB 驱动器。](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *图 9. 将恢复请求 (重置) U 盘*

   * 若要使用 QR 代码恢复 (重置) ，请使用移动设备上的 QR 阅读器应用来阅读代码。 QR 阅读器应用将 QR 代码转换为字母数字字符串。 然后，你可以向管理员发送该字符串的电子邮件或消息，以使用 Microsoft Surface UEFI 配置器生成重置验证代码。
   * 若要使用以文件 (U 盘保存的恢复请求 (重置请求) ，请使用 USB 驱动器将文件传输至 Microsoft Surface UEFI 配置器将用于生成重置验证代码的计算机。 还可从另一台设备上的 USB 驱动器复制该文件，以通过电子邮件或网络传输该文件。
   * 若要将恢复请求 (重置) 文本，只需将文本直接键入到 Microsoft Surface UEFI 配置器中。

8. 从另一台计算机的 "开始"菜单打开 Microsoft Surface UEFI 配置器。
    >[!NOTE]
    >Microsoft Surface UEFI 配置器必须在能够对 SEMM 证书的证书链进行身份验证的环境中运行。
9. 单击**开始**。
10. 单击 **"恢复请求**"，如图 10 所示。

    ![启动审批恢复请求的过程。](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *图 10. 单击"恢复请求"开始审批恢复请求的过程*

11. 单击 **"证书保护** "以使用 SEMM 证书对恢复请求进行身份验证。
12. 浏览到并选择 SEMM 证书文件，然后单击"确定 **"。**
13. 当系统提示您输入证书密码（如图 11 所示）时，键入并确认证书文件的密码，然后单击"确定 **"。**

    ![键入 SEMM 证书的密码。](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *图 11. 键入 SEMM 证书的密码*

14. 单击“下一步”****。
15. 输入"恢复 (重置) "，然后单击"生成"以创建重置验证 (如**** 图 12) 所示。

    ![输入恢复请求。](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *图 12. 输入"恢复请求 (重置请求) *

    * 如果在要重置的 Surface 设备上将恢复请求 (重置请求) 显示为文本，请使用键盘在提供的字段中键入恢复请求 (重置请求) 。
    * 如果将恢复请求 (重置请求) 显示为 QR 代码，然后使用消息或电子邮件应用程序通过 Microsoft Surface UEFI 配置器将代码发送到计算机，请将代码复制并粘贴到提供的字段中。
    * 如果将恢复请求 (重置请求) 另存为 U 盘的文件，请单击"导入"**** 按钮，浏览到并选择恢复请求 (重置请求) 文件，然后单击 **"确定**"。

16. 重置验证代码显示在 Microsoft Surface UEFI 配置器中，如图 13 所示。

    ![显示重置验证代码。](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *图 13. Microsoft Surface UEFI 配置器中显示的重置验证代码*

    * 单击" **共享** "按钮以通过电子邮件发送重置验证码。

17. 在 Surface 设备上提供的字段中输入重置验证码 (如图 8) 中所示，然后单击或按 **"** 验证"重置设备，然后从 SEMM 取消注册设备。
18. 单击**或按****SEMM**重置成功页面上的立即重启以完成从 SEMM 注销，如图 14 所示。

    ![从 SEMM 成功注销的示例显示。](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *图 14. 从 SEMM 成功注销*

19. 单击 **"** 在 Microsoft Surface UEFI 配置器中结束"以完成"恢复 (重置请求) 并关闭 Microsoft Surface UEFI 配置器。



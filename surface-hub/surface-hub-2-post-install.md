---
title: 在 Surface Hub 2 上配置Windows 10/11 Pro或Enterprise
description: 本文包含一些建议，以确保在使用个性化的大屏幕触摸和笔计算机时获得最佳体验。
keywords: Surface Hub、Windows 10、桌面、安装、配置
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
- Windows 10
- Windows 11
ms.openlocfilehash: 2b645ef580eda85a91bf282c8772c42c09cbb67d
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497765"
---
# <a name="configure-windows-1011-pro-or-enterprise-on-surface-hub-2"></a>在 Surface Hub 2 上配置Windows 10/11 Pro或Enterprise

迁移到 Windows 10/11 Pro或Enterprise后，可以配置应用和设置，以确保使用这种个性化的大屏幕触摸和笔计算机的最佳体验。

执行这些步骤时，你可能会发现使用有线键盘或无线键盘和鼠标会很有帮助。

## <a name="configure-system-settings"></a>配置系统设置

1. 使用设备上具有本地管理员权限的帐户登录。  

    - 在已加入Azure AD设备上执行Azure AD联接的用户会自动添加到本地管理员组。  Azure AD全局管理员和Azure AD设备管理员<a href="/azure/active-directory/devices/assign-local-admin" target="_blank">也是本地管理员</a>。 

    - 可以在命令提示符下键入 **净本地组管理员** ，以列出具有本地管理员权限的帐户。
    
2. 使用友好名称重命名设备，例如 **username-SHub-Desktop**。

3. 选择 **“开始** > **设置** > **”设置“并** > 关闭 **”同步“设置**。**** 

    - 此处使用的设置旨在实现最佳的大屏幕触摸体验，因此你可能不想同步其他设备。
    
4. 重启设备。

## <a name="enable-the-touch-keyboard-and-touchpad"></a>启用触摸键盘和触摸板

1. 选择 **“开始** > **设置** > **DevicesTyping** > ，**在不处于平板电脑模式且没有附加键盘的情况下打开”显示触摸键盘**”。****

2. 点击并按住或右键单击任务栏，然后选择 **“显示触摸键盘”按钮** 和 **“显示触摸板”按钮**。 

    - 触摸键盘有助于直接用户输入，虚拟触摸板有助于精确选择、将屏幕提示悬停在一起，或者作为右键点击和按住的替代方法。 
    
    - 请参阅以下示例。

      ![触摸设置。](images/touch.png)

3. 将触摸键盘配置为 QWERTY 并浮动。

    1. 选择任务栏上的 **键盘** 图标以显示触摸键盘。
    
    1. 在触摸键盘上，选择左上角的键盘图标以打开键盘设置。
    
    1. 选择顶部行上最后一个键盘类型以启用 QWERTY，并选择第二行上的最后一个选项以启用浮动，这在此大屏幕上很有用。 请参阅以下示例。

       ![键盘设置。](images/kbd.png)
 
4. 配置软键盘设置。

    1. 在触摸键盘上选择**设置**图标，或搜索并打开**键入设置**。
    
       ![软键盘设置。](images/sh2-softkeyboard.png)

    1. 在拼写、键入和触摸键盘下启用所有选项。


下面的示例演示了用于导航和选择选项的触控板。 屏幕键盘用于搜索Microsoft Store：

![使用触控板。](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>配置蓝牙键盘和鼠标 (可选) 

如果将设备用作主Windows设备，或者经常将其用于键入或精确工作，则连接键盘和鼠标。

如果Surface Hub设备靠近电脑，则可以使用<a href="https://aka.ms/mm" target="_blank">无边框</a>鼠标在Surface Hub和电脑之间无缝移动。 有关详细信息，请参阅 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft 从“车库：无边框鼠标”下载。 </a>

## <a name="example-of-taskbar-layout"></a>任务栏布局示例

完成以下步骤，为Windows 10/11 Pro或Enterprise设置/配置Surface Hub 2 后，建议使用将最常用的应用程序固定到 Taskbar，以便快速启动每个应用程序。 下面是任务栏的外观示例：

 ![任务栏布局。](images/taskblyt.png)
### <a name="update-installed-apps"></a>更新已安装的应用

若要更新所有已安装的应用商店应用，请执行以下操作：

1. 打开Microsoft Store应用，然后选择右上角的 **“查看更多**省略号”。
2. 选择 **“下载”和“更新”。**
3. 选择 **“获取更新”**

### <a name="scan-for-and-install-all-windows-updates"></a>扫描并安装所有Windows更新

迁移后，可能会有服务和功能更新可供你安装。 

- 转到 **设置** > **Update &安全**>，然后选择 **“检查更新**”。
- 如果有任何更新，请安装它们，重新启动，然后重复此过程，直到看到以下通知：

> [!div class="mx-imgBorder"]
> ![Windows 更新“你是最新的”通知。](images/wustatus.png)


## <a name="onedrive-for-business"></a>OneDrive for Business

使用<a href="/onedrive/onedrive" target="_blank">OneDrive for Business</a>在所有工作设备之间轻松共享工具、日志和其他文件。

- OneDrive使你可以在笔记本电脑、Surface Hub桌面和Intune托管的移动设备之间共享工作文件。 可以在任何设备上编辑文件，并且所有已连接网络的设备都将随更改一起更新。

- 考虑到 Surface Hub SSD (128GB) 的大小，如果在Surface Hub桌面设备上配置OneDrive，请确保默认配置是使文件保持联机状态，并在使用文件时下载文件。

若要将OneDrive配置为仅在需要时下载文件，请将 **“按需文件**”设置设置设置为 **“节省空间”，并在使用文件时下载文件**。 有关详细信息，请参阅<a href="/onedrive/files-on-demand-windows" target="_blank">查询并在Windows</a>中设置文件按需状态。

![OneDrive设置。](images/onedrive.png)

> [!NOTE]
> 还可以重复这些步骤来配置个人OneDrive但请务必节省驱动器空间，并且仅根据需要下载文件。

## <a name="sharepoint-and-teams"></a>SharePoint和Teams

SharePoint和Teams通道文件还可以使用OneDrive 同步引擎在本地同步到桌面设备，如笔记本电脑和 Surface Hub。

若要将内部公司文件同步到本地驱动器，请使用OneDrive 同步应用：

1. 转到SharePoint站点，导航到要从本地设备查看或编辑的文件的顶级文档目录。

2. 在SharePoint功能区顶部的 **“同步**”按钮上选择。

3. 在弹出窗口的 **“打开**”上选择**此网站正在尝试打开Microsoft OneDrive**。

4. 通过选择任务栏右下角的OneDrive图标，验证SharePoint文件是否正在同步到本地驱动器。

5. 验证配置是否设置为使文件保持联机状态，并仅在使用文件时下载文件：

    1. 打开文件资源管理器。
    
    2. 导航到并右键单击SharePoint名称;例如 **Contoso \ \<SharePoint Document Folder Name\>**。
    
    3. 选择 **“释放空间**”。
    
    4. “状态”列将显示文件和文件夹的状态。 有关详细信息，请参阅<a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank">与OneDrive 同步客户</a>端同步SharePoint文件。
    
6. Teams频道文件存储在SharePoint站点中，具有相同的SharePoint文档功能，包括版本历史记录和同步到本地桌面设备。 同步Teams通道文件：

    1. 导航到感兴趣的Teams通道，然后选择顶部的 **“文件”** 选项卡。 然后选择 **“同步**”。文件将开始同步，并在**桌面 \ Contoso \ \<name of the Teams Channel\>** 的文件资源管理器中可见。
    
    2. 使用用于同步SharePoint站点的相同过程将文件保留在云中，并且仅在使用它们时下载它们，方法是点击并按住或右键单击Teams通道名称上的文件资源管理器，然后选择 **“释放空间**”。

## <a name="surface-hub-pen-settings"></a>Surface Hub笔设置

**将蓝牙 Surface Hub笔配对**

将笔配对以使笔固件保持最新，设置笔快捷方式，并在蓝牙设备设置页或 Surface 应用中获取电池电量信息：

1. 选择 **“开始** > **设置** > **Devices**。

2. 选择 **“添加蓝牙或其他设备**。

3. 选择**蓝牙**。

4. 删除笔尾按钮并摇动以断开电池连接。

5. 重新打开帽子，按住帽子，直到配对 LED 闪烁。

6. 在Surface Hub 蓝牙设置中，选择**Surface Hub 2 笔**。

7. 完成配对操作。 

8. 如果配对不成功，请尝试再次配对笔。 如果这不起作用，可以通过验证白板应用程序中的笔是否正常工作来测试电池是否已充电。 如果没有，请更换电池，然后尝试再次配对笔。  如有必要，请重启设备，然后重试。

**设置笔快捷方式**Surface Hub笔有一个快捷按钮，有时称为“尾部单击”。 配置快捷方式需要先将笔配对，如前面所述。

1. 搜索 Pen 并选择 **Pen & Windows Ink 设置**。

2. 在页面底部附近，选择打开对话框的 Pen 快捷方式，如下所示：

   ![笔快捷方式。](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>相机配置

可以将相机装载到设备顶部或任意一侧。 如果将中心与桌面支架（而不是购物车）配合使用，或者位于中心附近，则将相机装载到可优化相机角度的位置。 相机不会自动旋转，因此你需要有一个 2 毫米十六进制键才能手动旋转相机。 

有关如何手动旁装相机和旋转相机的详细信息，请参阅 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S 相机镜头方向</a>。

## <a name="windows-hello-configuration"></a>Windows Hello配置

Surface Hub运行 Windows 10/11 Pro或Enterprise的 2S 允许提供完整的 Win32 桌面应用程序套件以及生物识别Windows Hello选项。 Surface Hub 2 指纹读取器配件可以插入设备上的任何 USB-C 端口。 

若要订购Surface Hub 2 指纹读取器或查看技术规格，请参阅 (surface-hub-2-essential-add-ons.md“target=”_blank“>Surface Hub 2 </a>上Windows 10 专业版和Enterprise的基本加载项。 

插入指纹读取器后，选择 **“开始** > **设置** > **AccountsSign-in** > **选项** > **Windows Hello指纹**以注册指纹。

使用Windows Hello认证设备进行人脸识别。 Surface Hub 2S 相机不支持人脸识别Windows Hello。

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>在任务栏上启用锁屏界面快捷方式图标

若要向任务栏添加一个图标，以便启用类似于 Windows-L 键盘快捷方式的单触摸屏锁： 

1.  点击并按住或右键单击桌面，选择 **** NewShortcutBrowseDesktopOKNext**** > 。**************** >  >  >  > 

1.  为快捷方式提供名称，例如 **锁定电脑**，然后选择 **“完成**”。

1.  右键单击或点击并按住桌面上新建的快捷方式，然后选择 **“属性**”。 在 **“快捷方式** ”选项卡上，在 **“目标** ”字段中输入以下内容： **Rundll32.exe User32.dll、LockWorkStation**

1.  选择 **“更改图标** ”按钮并浏览以 **C:\Windows\System32\imageres.dll** 并选择要使用的图标。 

    请参阅以下示例：

    ![选择一个图标。](images/lock.png)
    
1.  选择 **“确定** ”以保存快捷方式。

1.  右键单击或点击并按住快捷方式，然后选择 **“固定到任务栏**”。

1. 将锁快捷方式固定到任务栏后，可以将其从桌面中删除。

## <a name="applications"></a>应用程序


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

若要安装Microsoft Whiteboard：

 - 选择任务栏右下角的**Windows Ink 工作区**图标并下载 **Whiteboard**。
 
   ![墨迹工作区。](images/ink.png) 

或者，可以从Microsoft Store安装 Whiteboard：

1. 打开Microsoft Store应用并搜索 **Whiteboard**。

2. 若要登录并跨设备使用，请选择 **“否** ”。

3. 将白板固定到任务栏。

### <a name="surface-app"></a>Surface 应用

1. 在Microsoft Store中，搜索 **Surface**。

2. 将 **“在筛选器上可用** ”设置为 **“所有设备**”。

3. 安装 **Surface** 应用。 这应该是列出的第一个应用。 可能需要将 MSA 关联到应用商店才能安装应用。

4. 将 **Surface** 应用固定到任务栏。

### <a name="snip--sketch"></a>截图和草图

1. 打开 **Snip & Sketch** 应用并将其固定到任务栏。

2. 选择右上角的省略号，然后选择**设置**。

3. 在**设置**中，打开**自动复制到剪贴板**、**保存代码**和**多个窗口** (可选) 。

### <a name="microsoft-office"></a>Microsoft Office

1. <a href="https://portal.office.com/account#installs" target="_blank"> 打开Office门户</a>并安装所需的应用程序。

2. 将所需的Office应用程序固定到任务栏。

3. 如果安装了Outlook，请务必将OUTLOOK OST 设置为仅保存过去两周的缓存。 这将大大减少磁盘的使用和设置时间。

    - 选择 **FileAccount** **** >  设置并选择帐户。
    
    - 选择 **“更改**”，并将 **“使用缓存Exchange模式**”的滑块设置为 14 天。

### <a name="microsoft-teams"></a>Microsoft Teams

1. 下载并安装<a href="https://teams.microsoft.com/downloads" target="_blank">Microsoft Teams</a>。

2. 将设置配置为自动启动应用程序 (可选) 。

3. 将Teams固定到任务栏。

4. 请考虑减少设备上的Teams通知，以避免干扰 (可选) 。

   ![Teams通知。](images/teams.png)

### <a name="connect-app"></a>连接应用

> [!IMPORTANT]
> 在 Windows 10 版本 2004 及更高版本中，使用Miracast进行无线投影的连接应用默认未安装，但可作为可选功能使用。 如果已安装 (或已更新到) Windows 版本 2004 或更高版本，则可能会在“投影到此电脑”屏幕上看到以下设置：

![Project到此电脑。](images/sh2-project.png) 


1. 若要从“投影到此电脑”设置页安装应用，请选择 **“可选功能** > **”功能，** 然后安装 **无线显示** 应用。

2. 在**某些Windows和 Android 设备可以投影到此电脑时，你说它是确定的**，选择：

    - 如果设备不在公司网络上，则**可随时随地使用**。
    - 否则，请在 **安全网络上选择“随时随地可用**”。
    
3. 在 **“请求投影到此电脑**”下， **仅选择“第一次**”。

4. 在 **“需要 PIN 进行配对**”下，选择 **“从不**”。

5. 若要启动应用并将其固定到任务栏，请搜索**连接**。

6. 打开应用。 打开应用时，右键单击任务栏上的连接应用图标，然后选择**固定到任务栏**。

7. 然后关闭连接应用。 **此电脑Project**可能不起作用，除非应用已运行至少一次。

建议在不在公司网络上时进行配置：

![设置在家。](images/project1.png)

企业网络上的建议配置：

![设置工作。](images/project2.png)

### <a name="your-phone"></a>你的手机

你的**电话**应用默认安装在Windows 10上。 如果不存在，也可以从 Windows Store 安装它。

有关设置应用的信息，请参阅<a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank">如何在电脑和手机</a>之间设置Windows 10和同步数据的电话。 另请参阅<a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank">如何在Windows 10上解决电话应用的</a>常见问题。

###  <a name="fancy-zones"></a>花式区域


**花式区域**是GitHub上名为<a href="https://github.com/microsoft/PowerToys/releases" target="_blank">PowerToys</a>的工具集合的一部分。 这是利用Surface Hub 2 上的屏幕房地产的绝佳方式，它使你能够在显示 (“区域”) 上定义固定布局，然后选择将在每个区域中运行的应用。 


[PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) 提供有关如何使用和自定义每个工具（包括 [FancyZones）的](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)说明。 在高级别 - 安装PowerToys后，可以选择或创建自定义布局，然后按住班次键，拖动或使用键盘键将正在运行的应用移动到特定区域。 使用蓝牙或 USB 键盘和鼠标将对此有所帮助，也可以使用屏幕触摸键盘和触摸板。

**电源玩具提示**
- 若要在GitHub上接收PowerToys发布更新的电子邮件通知，请单击[页面](https://github.com/microsoft/PowerToys/releases)顶部的“注册”按钮。
- 安装PowerToys后，可以通过配置PowerToys设置**自动下载更新**来接收Windows通知和/或下载和安装最新更新。
- 若要转到PowerToys设置，请选择任务栏上**运行应用**的向上大篷车，然后右键单击或按住PowerToys图标，直到出现菜单。 选择“设置”。
- 在“PowerToys设置”页底部，**自动打开“下载”更新**。
- 发布更新后，将显示Windows通知，让你可以选择何时安装更新。


### <a name="edge-chromium-browser"></a>Edge Chromium浏览器

下载并安装新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium浏览器</a>。


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub硬件诊断工具

<a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub硬件诊断工具</a>可供Microsoft Store免费使用。 该工具旨在帮助你确保Surface Hub性能最佳。 它包含测试，用于确定固件是否为最新且配置正确。 通过交互式测试，可以确认基本功能是否按预期工作。 如果遇到问题，可保存结果并与 Surface Hub 支持团队共享。 单击链接从Microsoft Store安装它，然后将应用程序固定到任务栏。

## <a name="additional-settings"></a>其他设置

### <a name="pen-tail-select-to-launch-whiteboard"></a>笔尾选择启动白板

1. 搜索 **Pen** 并选择 **Pen & Windows Ink 设置**。

2. 在页面底部附近，**在“笔”快捷方式**下，**将“选择”** 设置为**Microsoft Whiteboard**一次。 

### <a name="power-management"></a>电源管理

有多个电源设置可用于在 Surface Hub 2 上使用Windows 10/11 Pro或Enterprise获得最佳体验。 这包括屏幕和电脑超时，以及它们如何与内置的人工状态检测 (Doppler) 、屏幕保护程序和密码保护进行交互，以及如何通过适用于笔记本电脑/桌面用户的分组策略电源设置。

Surface Hub 2 上的Windows 10/11 Pro或Enterprise可防止屏幕通过触摸、鼠标和键盘操作以及内置的人工占用情况检测 (Doppler) 进入睡眠状态。 默认情况下启用了人工占用检测，但如果需要，可以通过在 Surface UEFI 配置器工具中切换设备选项（作为初始迁移的一部分，或通过生成和应用更高版本的 UEFI 配置包）在 UEFI 中禁用它。 

**电源管理：屏幕和电脑睡眠设置**

1. 选择 **“开始** > **设置** > **SystemPower** > **&睡眠**。

2. 将电源模式滑块设置为 **最佳性能**。

3. 将屏幕和睡眠值配置为首选项，同时考虑在检测到移动时唤醒设备的 Doppler 状态检测。 因此，作为最佳做法，建议将屏幕设置为 **在 2 小时后关闭** ，电脑在 **4 小时后关闭。**

**电源管理：屏幕保护程序**

1. 搜索 **锁屏** 和打开 **锁屏设置**。

2. 将 **屏幕超时设置** 和 **屏幕保护设置** 配置为首选项。 建议的默认值为：

   - 用于 (无) 或所选屏幕保护程序的屏幕保护程序。
   - 等待时间到 15 分钟。
   - 在简历上，显示登录屏幕。


**电源管理：组策略**

在执行以下过程之前，请咨询 IT 部门以获得批准，以从全局电源管理策略中排除Surface Hub 2S 设备。 某些电源管理设置可以禁用状态检测函数。

1. 搜索 **软件中心** 并将其打开。

2. 选择 **选项**。

3. 展开 **电源管理**  ，然后选择 **“不要将 IT 部门中的电源设置应用到此计算机**”。

   ![软件设置。](images/soft-cntr.png)

### <a name="storage-sense"></a>存储感知

Surface Hub 2 具有用于本地存储的 128GB SSD，因此在正常使用期间需要考虑使用存储保存措施。  若要配置 存储 Sense：

1.  搜索在**系统**设置下找到**的存储设置**。

2.  在**设置**下，选择 **“打开存储感**”打开**存储**设置页。

3.  将存储感启**用**。

4.  选择 **“配置存储感知”或立即运行它**，并配置设置以使文件尽可能保持联机 (，因为驱动器空间) 有限。

建议的设置：

- 运行存储 Sense = 每天。
- 删除应用未使用的临时文件 = 每 14 天 (至少) 。
- 如果文件已存在超过 = 30 天，请删除“下载”文件夹中的文件。
- OneDrive：如果打开时间不超过 = 30 天，内容将仅联机。

### <a name="tablet-mode"></a>平板电脑模式

如果需要辅助功能，请启用 Tablet 模式。


### <a name="sound-settings"></a>声音设置

1. 搜索 **“声音”设置** 并打开此页面。

2. 选择右侧**的“声音控制面板**”，然后选择 **“声音”** 选项卡。

3. 在 **“程序事件**”下，将**设备连接**和**设备断开连接**设置为 **“无**”。

### <a name="silence-notifications"></a>静音通知

1. 搜索 **“焦点帮助** ”并打开此页面。

2. **仅选择“警报**”。 这将避免常量通知浮出控件。

### <a name="disk-cleanup"></a>磁盘清理

1. 搜索 **磁盘清理** 并打开此应用。

2. 在 **要删除的文件**下，选择要删除的文件。 

3. 另请选择 **“清理系统文件**”。

## <a name="complete-and-verify"></a>完成并验证

1. 扫描并安装所有Windows更新。

2. 更新组策略。

   1. 在提升的命令提示符下，输入 **gpupdate /force /boot /wait：0**。
   
3. 重启设备。

4. 验证任务栏应用。

   - 连接应用
   - 锁定图标
   - 截图和草图
   - Teams (（如果适用）) 
   - Office应用 (（如果适用）) 
   - Surface App
   - 白板
    
5. 验证状态检测。

   - 状态检测将是系统托盘中的绿色图标。
    
6. 使用连接应用验证是否启用了对此电脑的投影。 将**Project配置到此电脑**设置后，至少运行一次连接应用。  (随后，无需运行连接应用即可投影到Surface Hub.) 

7. 验证电源和睡眠设置。

    - 屏幕保护程序：15 分钟，设置为 (无) 、Mystify 或 Blank;确保选中了要求密码的复选框。
    - 屏幕： **2 小时后关闭**。
    - 电脑：  **4 小时后关闭**。
    
8. 验证Windows Hello是否正常工作。

9. 验证是否已禁用同步设置。

10. 验证启动应用。

> [!TIP]
> 安装和配置Windows 10后，可以像管理任何其他Windows 10或Windows 11设备一样管理Surface Hub 2S。

## <a name="related-topics"></a>相关主题

<a href="surface-hub-2s-migrate-os.md" target="_blank"> 在 Surface Hub 2 上迁移到Windows 10/11 Pro或Enterprise</a>

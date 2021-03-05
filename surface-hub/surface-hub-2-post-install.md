---
title: 配置 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文包含一些建议，以确保在使用个性化大屏幕触摸和笔计算机时获得最佳体验。
keywords: Surface Hub， Windows 10， 桌面， 安装， 配置
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
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393594"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a>配置 Surface Hub 2 上的 Windows 10 专业版或企业版

完成迁移到 Windows 10 专业版或企业版安装过程后，可以执行以下步骤在 Surface Hub 2 上配置应用和设置。 建议执行这些步骤以确保使用此个性化大屏幕触摸和笔计算机时获得最佳体验。

执行这些步骤时，你可能会发现使用有线或无线键盘和鼠标非常有用。

## <a name="configure-system-settings"></a>配置系统设置

1. 使用在设备上具有本地管理员权限的帐户登录。  

    - 在加入 Azure AD 的设备上，执行 Azure AD 加入的用户将自动添加到本地管理员组。 Azure AD 全局管理员和 Azure AD 设备管理员 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 也是本地管理员 </a> 。 
    
    - 您可以在命令 **提示符下** 键入 net localgroup 管理员，以列出具有本地管理员权限的帐户。
    
2. 使用友好名称重命名设备，例如 **：username-SHub-Desktop**。

3. 选择 **"**  >  **开始**  >  **设置**  >  **帐户同步设置"并**关闭 **"同步设置**"。 

    - 此处使用的设置旨在实现最佳的大屏幕触摸体验，因此你可能不希望同步其他设备。
    
4. 重新启动设备。

## <a name="enable-the-touch-keyboard-and-touchpad"></a>启用触摸键盘和触摸板

1. 选择 **"** 开始  >  ****  >  **设置**设备  >  **键入"，** 当**** 未在平板电脑模式下且没有连接键盘时，打开"显示触摸键盘"。

2. 点击并按住或右键单击任务栏，然后选择" **显示触摸键盘按钮** "和" **显示触摸板"按钮**。 

    - 触摸键盘有助于直接用户输入，虚拟触摸板有助于精确选择、悬停屏幕提示，或者作为点击并按住进行右键单击的替代方法。 
    
    - 请参阅以下示例。

      ![触摸设置](images/touch.png)

3. 将触摸键盘配置为 QWERTY 和浮动。

    1. 选择 **任务栏** 上的键盘图标以显示触摸键盘。
    
    1. 在触摸键盘上，选择左上角的键盘图标以打开键盘设置。
    
    1. 选择首行上的最后一个键盘类型以启用 QWERTY，选择第二行的最后一个选项以启用浮动，这在此大屏幕上非常有用。 请参阅以下示例。

       ![键盘设置](images/kbd.png)
 
4. 配置软键盘设置。

    1. 选择**触摸**键盘上的"设置"图标或搜索并打开 **"键入设置"。**
    
       ![软键盘设置](images/sh2-softkeyboard.png)

    1. 启用拼写、键入和触摸键盘下的所有选项。


以下示例显示跟踪板，它可用于导航和选择选项。 屏幕键盘用于搜索 Microsoft Store：

![使用跟踪板](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>配置Bluetooth键盘和鼠标 (可选) 

如果你将设备用作主 Windows 设备，或者你经常使用它进行键入或精确工作，请连接键盘和鼠标。

如果你的 Surface Hub 设备靠近电脑，可以使用不带边框的鼠标在 Surface Hub 和电脑之间无缝 <a href="https://aka.ms/mm" target="_blank"> </a> 移动。 有关详细信息，请参阅 Microsoft 从 Garage <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> 下载：没有边框的鼠标。 </a>

## <a name="example-of-taskbar-layout"></a>任务栏布局示例

完成以下步骤以设置/配置适用于 Windows 10 专业版或企业版 Surface Hub 2 后，我们建议你利用将最常用的应用程序固定到任务栏，以便快速一键启动每个应用程序。 下面是任务栏外观的示例：

 ![任务栏布局](images/taskblyt.png)
### <a name="update-installed-apps"></a>更新已安装的应用

更新所有已安装的应用商店应用：

1. 打开 Microsoft Store 应用 **，然后选择右上角** 的"查看更多省略号"。
2. 选择 **"下载和更新"。**
3. 选择 **"获取更新"**

### <a name="scan-for-and-install-all-windows-updates"></a>扫描并安装所有 Windows 更新
迁移到 Windows 10 专业版或 Windows 10 企业版后，可能有可供你安装的维护和功能更新。 

- 转到 **"设置**  >  **更新&安全**>，然后选择 **"检查更新"。**
- 如果存在任何更新，请安装它们，重新启动，然后重复此过程，直到看到以下通知：

> [!div class="mx-imgBorder"]
> ![Windows 更新"你已更新"通知](images/wustatus.png)


## <a name="onedrive-for-business"></a>OneDrive for Business

使用 OneDrive for Business 在所有工作设备之间轻松共享工具、日志 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> 和其他文件。

- OneDrive 使你能够在笔记本电脑、Surface Hub 桌面和 Intune 托管的移动设备之间共享工作文件。 可以在任何设备上编辑文件，并且所有网络连接的设备都将随更改一起更新。

- 考虑 Surface Hub SSD (128GB) 的大小，如果在 Surface Hub 桌面版设备上配置 OneDrive，请确保默认配置是使文件保持联机并下载使用的文件。

若要将 OneDrive 配置为仅根据需要下载文件，请**** 设置"按需文件"设置以节省空间，并下载使用**时的文件**。 有关详细信息，请参阅 Windows 中的查询和 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> 设置文件按需状态 </a> 。

![OneDrive 设置](images/onedrive.png)

> [!NOTE]
> 还可以重复这些步骤来配置个人 OneDrive，但请务必节省驱动器空间，并仅根据需要下载文件。

## <a name="sharepoint-and-teams"></a>SharePoint 和 Teams

SharePoint 和 Teams 频道文件还可使用 OneDrive 同步引擎本地同步到桌面设备，如笔记本电脑和 Surface Hub。

若要使用 OneDrive 同步应用将内部公司文件同步到本地驱动器：

1. 转到 SharePoint 网站，并导航到顶级文档目录，了解您在本地设备中查看或编辑的文件。

2. 在 SharePoint 功能 **区** 顶部的"同步"按钮上选择。

3. 在弹出窗口**中选择**"打开"**此网站正在尝试打开 Microsoft OneDrive。**

4. 通过选择任务栏右下角的 OneDrive 图标，验证 SharePoint 文件是否正在同步到本地驱动器。

5. 验证配置是否设置为保持文件联机，并仅在使用文件时下载这些文件：

    1. 打开文件资源管理器。
    
    2. 导航到 SharePoint 名称并右键单击您的 SharePoint 名称;例如 **，Contoso \ \<SharePoint Document Folder Name\> **。
    
    3. 选择 **"释放空间"。**
    
    4. "状态"列将显示文件和文件夹的状态。 有关详细信息，请参阅将 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> SharePoint 文件与 OneDrive 同步客户端同步 </a> 。
    
6. Teams 频道文件存储在 SharePoint 网站中，具有所有相同的 SharePoint 文档功能，包括版本历史记录和同步到本地桌面设备。 同步 Teams 频道文件：

    1. 导航到感兴趣的 Teams 频道， **然后选择顶部的"** 文件"选项卡。 然后选择"**同步"。** 文件将开始同步，并且将在桌面**\ Contoso \<name of the Teams Channel\> \**文件资源管理器中可见。
    
    2. 使用用于同步 SharePoint 网站的过程将文件保留到云中，并且仅在使用这些文件时下载这些文件，方法为点击并按住或右键单击 Teams 频道名称上的文件资源管理器，然后选择"释放空间 **"。**

## <a name="surface-hub-pen-settings"></a>Surface Hub 笔设置

**将 Bluetooth Surface Hub 触控笔配对**

配对笔，使笔固件保持最新，设置笔快捷方式，并获取"Bluetooth设置"页面或 Surface 应用中的电池充电信息：

1. 选择 **"**  >  **开始设置**  >  **设备"。**

2. 选择 **"添加Bluetooth或其他设备**。

3. 选择 **Bluetooth**。

4. 删除笔尾按钮并摇动以断开电池连接。

5. 将顶帽重新打开并按住该顶帽，直到配对的 LED 闪烁。

6. 在 Surface Hub Bluetooth设置上，选择 **Surface Hub 2 触控笔**。

7. 完成配对操作。 

8. 如果配对失败，可以再次尝试配对笔。 如果不起作用，可以通过验证笔在白板应用程序中是否正常工作来测试电池是否充电。 如果没有，请更换电池，然后再次尝试配对笔。 如有必要，请重新启动设备，然后重试。

**设置笔快捷方式** Surface Hub 笔有一个快捷按钮，有时称为"尾部单击"。 配置快捷方式需要你先配对笔，如前面所述。

1. 搜索笔并选择"笔 **& Windows Ink 设置**。

2. 在页面底部附近，选择打开对话框的笔快捷方式，如下所示：

   ![笔快捷方式](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>相机配置

你可以将相机安装在设备顶部或两侧。 如果你将 Hub 与桌面台而不是购物车一同使用，或者靠近中心，则将相机装载到一个位置以优化相机角度。 相机不自动旋转，因此你需要有一个 2mm 的十六进制密钥来手动旋转相机。 

若要详细了解如何手动旁装载相机并旋转相机，请参阅 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S 相机镜头方向 </a> 。

## <a name="windows-hello-configuration"></a>Windows Hello 配置

运行 Windows 10 企业版 Surface Hub 2S 允许整套 Win32 桌面应用程序以及生物识别 Windows Hello 选项。 Surface Hub 2 指纹读取器附件可以插入设备上的任何 USB-C 端口。 

若要订购 Surface Hub 2 指纹读取器或查看技术规范，请参阅 (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a> . 

插入指纹读取器后，选择"**开始**  >  **设置**帐户  >  ****  >  **登录选项**  >  **"Windows Hello 指纹**以注册指纹。

使用 Windows Hello 认证的设备进行人脸识别。 Surface Hub 2S 相机不支持 Windows Hello 人脸识别。

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>在任务栏上启用锁屏界面快捷方式图标

若要将图标添加到启用一键式屏幕锁定的任务栏，类似于 Windows-L 键盘快捷方式： 

1.  点击并按住或右键单击桌面，选择 **"新建**  >  **快捷方式**  >  **浏览**  >  **桌面**  >  **确定**  >  **下一步"。**

1.  提供快捷方式的名称，如 **"锁定我的电脑**"，然后选择"完成 **"。**

1.  右键单击或点击并按住桌面上新建的快捷方式，然后选择"**属性"。** 在 **"快捷方式**"选项卡上，在"目标****"字段中输入以下内容 **：Rundll32.exe User32.dll、LockWorkStation**

1.  选择 **"更改** 图标"按钮并浏览 **C:\Windows\System32\imageres.dll并选择要使用 ** 图标。 

    请参见以下示例：

    ![选择图标](images/lock.png)
    
1.  选择 **"确定** "保存快捷方式。

1.  右键单击或点击并按住快捷方式，然后选择 **"固定到任务栏"。**

1. 将锁定快捷方式固定到任务栏后，可以从桌面中删除它。

## <a name="applications"></a>应用程序


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

若要安装 Microsoft Whiteboard：

 - 选择任务栏右下角的 **Windows Ink 工作区** 图标并下载 **白板**。
 
   ![墨迹工作区](images/ink.png) 

或者，你可以从 Microsoft Store 安装白板：

1. 打开 Microsoft Store 应用并搜索 **白板**。

2. 选择 **"否"，** 以感谢登录并跨设备使用。

3. 将白板固定到任务栏。

### <a name="surface-app"></a>Surface 应用

1. 在 Microsoft Store 中，搜索 **Surface**。

2. 将**筛选器上的"可用**"设置为 **"所有设备"。**

3. 安装 **Surface** 应用。 这应该是列出的第一个应用。 你可能需要将 MSA 与应用商店关联才能安装应用。

4. 将 **Surface** 应用固定到任务栏。

### <a name="snip--sketch"></a>截图和草图

1. 打开 **"Snip &草图** "应用，将其固定到任务栏。

2. 选择右上角的省略号，然后选择"**设置"。**

3. 在 **"设置****"中**，打开"自动复制到剪**** 贴板"、"保存剪贴"和"多个**窗口 (** 可选) 。

### <a name="microsoft-office"></a>Microsoft Office

1. 打开 <a href="https://portal.office.com/account#installs" target="_blank"> Office 门户 </a> 并安装所需的应用程序。

2. 将所需的 Office 应用程序固定到任务栏。

3. 如果安装了 Outlook，请确保将 Outlook OST 设置为仅保存最近两周缓存。 这将大大减少磁盘使用率和设置时间。

    - 选择****  >  **"文件帐户设置**"，然后选择您的帐户。
    
    - 选择 **"更改** "，将" **使用缓存 Exchange 模式"** 的滑块设置为 14 天。

### <a name="microsoft-teams"></a>Microsoft Teams

1. 下载并安装 <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft </a> Teams。

2. 将设置配置为自动启动应用程序 (可选) 。

3. 将 Teams 固定到任务栏。

4. 请考虑减少设备上 Teams 通知，以避免干扰 (可选) 。

   ![Teams 通知](images/teams.png)

### <a name="connect-app"></a>连接应用

> [!IMPORTANT]
> 在 Windows 10 版本 2004 及更高版本中，默认情况下不会安装使用 Miracast 的用于无线投影的 Connect 应用，但作为可选功能提供。 如果你已安装 (或更新到) Windows 版本 2004 或更高版本，你可能会在"正在计划到此电脑"屏幕的设置中看到以下内容：

![Project to this PC](images/sh2-project.png) 


1. 若要从"计划到此电脑"设置页安装应用，请选择"可选**功能**添加功能"，然后  >  **** 安装**无线显示**应用。

2. 在 **"一些 Windows 和 Android 设备可以在**你说出'确定'时计划到此电脑"下，选择：

    - **如果设备** 不在企业网络上，则可在任何位置使用。
    - 否则，在**安全网络上选择"可用"。**
    
3. 在 **"询问到此电脑"下**，选择 **"仅首次"。**

4. 在 **"需要 PIN 进行配对"下**，选择"**从不"。**

5. 若要启动应用，将其固定到任务栏，请搜索**Connect。**

6. 打开应用。 当应用打开时，右键单击任务栏上的 Connect 应用图标，然后选择 **固定到任务栏**。

7. 然后关闭 Connect 应用。 **除非应用** 至少运行一次，否则此电脑的项目可能无法运行。

当不在企业网络上时，建议配置：

![家庭设置](images/project1.png)

企业网络上建议的配置：

![工作中的设置](images/project2.png)

### <a name="your-phone"></a>你的手机

默认情况下 **，你的手机** 应用安装在 Windows 10 上。 如果不存在，还可以从 Windows 应用商店安装它。

有关设置应用的信息，请参阅如何在 Windows 10 上设置你的手机，以及如何在电脑和手机之间同步 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 数据 </a> 。 另请参阅 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 如何修复 Windows 10 上你的手机应用的常见问题 </a> 。

###  <a name="fancy-zones"></a>奇特区域


**奇特** 区域是 GitHub 上名为 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> 的工具集合的一部分。 这是利用 Surface Hub 2 上的屏幕空间的一种好方法，它让你能够在显示器上定义固定布局 ("区域") ，然后选择将在每个区域中运行的应用。 


[PowerToys Wiki](https://github.com/microsoft/PowerToys/wiki)提供了如何使用和自定义每个工具的说明，包括[奇特Zones。](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview) 在高级别 – 安装 PowerToys 后，可以选择或创建自定义布局，然后按住 Shift 键，然后拖动或使用键盘键将正在运行的应用移动到特定区域。 使用Bluetooth或 USB 键盘和鼠标将对此有所帮助，或者可以使用屏幕触摸键盘和触摸板。

**Power toys 提示**
- 若要在 GitHub 上接收 PowerToys 发布更新的电子邮件通知，请单击页面顶部的"注册" [按钮](https://github.com/microsoft/PowerToys/releases)。
- 安装 PowerToys 后，可以通过配置 PowerToys 设置自动下载更新来接收 Windows 通知和/或下载**** 并安装最新更新。
- 若要访问 PowerToys 设置，请在任务栏上选择**** 运行应用，然后右键单击或长按 PowerToys 图标，直到菜单显示。 选择"设置"。
- 在 PowerToys 设置页的底部，将 **下载更新自动打开** 。
- 发布更新后，将显示 Windows 通知，提供安装更新时间的选项。


### <a name="edge-chromium-browser"></a>Edge Chromium 浏览器

下载并安装新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium 浏览器 </a> 。


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub 硬件诊断工具

可从 Microsoft Store 免费获得 <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub </a> 硬件诊断工具。 该工具旨在帮助你确保 Surface Hub 性能最佳。 它包含用于确定固件是否为最新且配置正确的测试。 交互式测试允许你确认基本功能是否正常工作。 如果遇到问题，可保存结果并与 Surface Hub 支持团队共享。 单击链接以从 Microsoft Store 安装它，然后将应用程序固定到任务栏。

## <a name="additional-settings"></a>其他设置

### <a name="pen-tail-select-to-launch-whiteboard"></a>笔尾选择以启动白板

1. 搜索笔**并选择****"笔& Windows Ink 设置**。

2. 在页面底部附近，在**笔快捷方式**下将 **"选择**一次"设置为 **"Microsoft Whiteboard"。** 

### <a name="power-management"></a>电源管理

有几种电源设置可用于在 Surface Hub 2 上使用 Windows 10 专业版或企业版获得最佳体验。 这包括屏幕和电脑超时，以及它们如何与内置的人机状态检测 (Doppler) 、屏幕保护程序以及密码保护进行交互，然后在适当时如何传递适用于笔记本电脑/台式机用户的组策略电源设置。

Surface Hub 2 上的 Windows 10 专业版或企业版阻止屏幕通过触摸、鼠标和键盘操作以及内置的人体空间检测 (Doppler) 进入睡眠状态。 默认情况下会启用人工占用检测，但如果需要，可以通过切换 Surface UEFI 配置器工具中的设备选项（作为初始迁移的一部分）或在 UEFI 配置包中生成和应用更高版本的 UEFI 配置包，在 UEFI 中禁用它。 

**电源管理：屏幕和电脑睡眠设置**

1. 选择 **"**  >  **启动设置**  >  **系统**  >  **电源&睡眠。**

2. 将电源模式滑块设置为 **最佳性能**。

3. 根据你的偏好配置屏幕和睡眠值，同时还负责在检测到移动时唤醒设备的 Doppler 状态检测。 因此，作为最佳实践，建议将"屏幕"设置为 **在 2** 小时后关闭，将电脑设置为 **在 4 小时后关闭。**

**电源管理：屏幕保护程序**

1. 搜索**锁屏界面并****打开锁屏界面设置**。

2. 根据 **你的偏好配置** 屏幕超时 **设置和** 屏幕保护程序设置。 建议的默认值为：

   - 屏幕保护 (选择) 选择的任何屏幕保护程序或屏幕保护程序。
   - 等待时间到 15 分钟。
   - 恢复时，显示登录屏幕。


**电源管理：组策略**

在执行以下过程之前，请咨询 IT 部门进行审批，以从全局电源管理策略中排除 Surface Hub 2S 设备。 某些电源管理设置可能会禁用状态检测功能。

1. 搜索 **软件中心并** 打开它。

2. 选择 **选项**。

3. 展开 **"电源管理"，** 然后选择 **"不将我的 IT 部门的电源设置应用到此计算机"。**

   ![软件设置](images/soft-cntr.png)

### <a name="storage-sense"></a>存储感知

Surface Hub 2 具有 128GB SSD 用于本地存储，因此必须考虑在正常使用期间使用存储保存措施。  配置存储感知：

1.  搜索 **"系统设置**"下的存储 **设置**。

2.  在 **"** 设置"下， **选择"打开存储感知** "以打开 **"存储设置"** 页。

3.  将存储感知功能 **打开**。

4.  选择 **"配置存储** 感知"或现在运行它，并配置设置以尽可能使文件保持联机状态 (由于驱动器空间有限) 。

推荐设置：

- 运行存储感知 = 每天。
- 删除我的应用未使用的临时文件 = 至少每 14 天 (一次) 。
- 删除"下载"文件夹中的文件（如果这些文件已保留超过 30 天）。
- OneDrive：如果超过 30 天未打开内容，内容将变为仅联机状态。

### <a name="tablet-mode"></a>平板电脑模式

如果需要辅助功能需求，请打开平板电脑模式。


### <a name="sound-settings"></a>声音设置

1. 搜索 **"声音"设置** 并打开此页面。

2. 选择 **右侧的声音** 控制面板，然后选择" **声音"** 选项卡。

3. 在 **"程序事件"下****，将"设备连接**和设备**断开连接"****设置为"无"。**

### <a name="silence-notifications"></a>静默通知

1. 搜索 **焦点协助并** 打开此页面。

2. 选择 **"仅闹钟"。** 这将避免常量通知飞出。

### <a name="disk-cleanup"></a>磁盘清理

1. 搜索磁盘 **清理并** 打开此应用程序。

2. 在 **"要删除的文件"下**，选择要删除的文件。 

3. 此外，**选择"清理系统文件"。**

## <a name="complete-and-verify"></a>完成并验证

1. 扫描并安装所有 Windows 更新。

2. 更新组策略。

   1. 在提升的命令提示符下，输入 **gpupdate /force /boot /wait：0**。
   
3. 重新启动设备。

4. 验证任务栏应用。

   - 连接应用
   - 锁定图标
   - 截图和草图
   - Teams (（如果适用) 
   - Office Apps (（如果适用) 
   - Surface App
   - 白板
    
5. 验证状态检测。

   - 状态检测将是系统托盘中的绿色图标。
    
6. 使用 Connect 应用验证是否已启用对此电脑进行项目规划。 将  **Project 配置为此电脑** 设置后，至少运行一次 Connect App。  (，连接应用无需运行，就无需在 Surface Hub.) 

7. 验证电源和睡眠设置。

    - 屏幕保护程序：15 分钟，设置为 (、) 或空白;确保选中了要求密码的复选框。
    - 屏幕 **：2 小时后关闭**。
    - 电脑  **：4 小时后关闭**。
    
8. 验证 Windows Hello 是否正常工作。

9. 验证已禁用同步设置。

10. 验证启动应用。

> [!TIP]
> 安装和配置 Windows 10 后，可以像管理任何其他 Windows 10 设备一样管理 Surface Hub 2S。

## <a name="related-topics"></a>相关主题

<a href="surface-hub-2s-migrate-os.md" target="_blank"> 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版</a>

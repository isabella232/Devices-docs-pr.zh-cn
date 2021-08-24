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
ms.openlocfilehash: 5bb207823abb462179faf72810354885050dc25f
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911227"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a>配置 Surface Hub 2 上的 Windows 10 专业版或企业版

完成迁移到 Windows 10 专业版 或 Enterprise 的安装过程后，可以执行以下步骤在 Surface Hub 2 上配置应用和设置。 建议使用这些步骤来确保使用此个性化的大屏幕触摸和笔计算机时获得最佳体验。

执行这些步骤时，你可能会发现使用有线或无线键盘和鼠标非常有用。

## <a name="configure-system-settings"></a>配置系统设置

1. 使用在设备上具有本地管理员权限的帐户登录。  

    - 在加入 Azure AD 的设备上，执行 Azure AD 加入的用户将自动添加到本地管理员组。 Azure AD 全局管理员和 Azure AD 设备管理员 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 也是本地管理员 </a> 。 
    
    - 您可以在命令提示符下键入 net **localgroup administrators，** 以列出具有本地管理员权限的帐户。
    
2. 使用友好名称重命名设备，例如 **：username-SHub-Desktop**。

3. 选择 **"**  >  **开始设置**  >  ****  >  **帐户 同步设置"，** 然后**关闭"同步设置**"。 

    - 此处使用的设置旨在实现最佳的大屏幕触摸体验，因此你可能不希望同步其他设备。
    
4. 重新启动设备。

## <a name="enable-the-touch-keyboard-and-touchpad"></a>启用触摸键盘和触摸板

1. 选择 **"设置**设备键入"，然后打开"在不在平板电脑模式下且未连接键盘时显示触摸  >  ****  >  ****  >  ******键盘**"。

2. 点击并按住或右键单击任务栏，然后选择"**显示触摸键盘**按钮"和"**显示触摸板按钮"。** 

    - 触摸键盘有助于直接用户输入，虚拟触摸板有助于精确选择、悬停屏幕提示，或作为点击并按住右键单击的替代方法。 
    
    - 请参阅以下示例。

      ![触摸设置。](images/touch.png)

3. 将触摸键盘配置为 QWERTY 和浮动。

    1. 选择 **任务栏** 上的键盘图标以显示触摸键盘。
    
    1. 在触摸键盘上，选择左上角的键盘图标以打开键盘设置。
    
    1. 选择顶部行上的下一个键盘类型以启用 QWERTY，选择第二行的最后一个选项以启用浮动，这在此大型屏幕上非常有用。 请参阅以下示例。

       ![键盘设置。](images/kbd.png)
 
4. 配置软键盘设置。

    1. 选择设置**键盘**上的"键入"图标，或搜索并打开 **"键入设置"。**
    
       ![软键盘设置。](images/sh2-softkeyboard.png)

    1. 启用拼写、键入和触摸键盘下的所有选项。


以下示例显示跟踪板，它可用于导航和选择选项。 屏幕键盘用于搜索Microsoft Store：

![使用触控板。](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>配置蓝牙键盘和鼠标 (可选) 

连接设备作为主要设备，或者经常使用该设备进行键入或精确Windows使用键盘和鼠标。

如果你Surface Hub靠近电脑，可以使用不带边框的鼠标在电脑 <a href="https://aka.ms/mm" target="_blank"> </a> 和电脑Surface Hub无缝移动。 有关详细信息，请参阅 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft 从 Garage 下载：没有边框的鼠标。 </a>

## <a name="example-of-taskbar-layout"></a>任务栏布局示例

完成以下步骤以设置/配置 Windows 10 Professional 或 Enterprise 的 Surface Hub 2 后，我们建议你利用将最常用的应用程序固定到任务栏，以便每个应用程序的一键式快速启动。 下面是任务栏外观的示例：

 ![任务栏布局。](images/taskblyt.png)
### <a name="update-installed-apps"></a>更新已安装的应用

更新所有已安装的应用商店应用：

1. 打开Microsoft Store应用 **，然后选择右上角**的"查看更多省略号"。
2. 选择 **下载和更新。**
3. 选择 **"获取更新"**

### <a name="scan-for-and-install-all-windows-updates"></a>扫描并安装所有 Windows 更新
迁移到 Windows 10 Professional 或 Windows 10 企业版 后，可能有服务更新和功能更新可供你安装。 

- 转到****  >  **"设置"&安全**>，然后选择"**检查更新"。**
- 如果存在任何更新，请安装它们，重新启动，然后重复此过程，直到看到以下通知：

> [!div class="mx-imgBorder"]
> ![Windows更新"你最新的"通知。](images/wustatus.png)


## <a name="onedrive-for-business"></a>OneDrive for Business

使用OneDrive for Business，在所有工作设备之间轻松共享工具、日志 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> 和其他文件。

- OneDrive，可以在笔记本电脑、桌面设备Surface Hub Intune 托管的移动设备之间共享工作文件。 可以在任何设备上编辑文件，并且所有网络连接的设备都将随更改一起更新。

- 考虑 Surface Hub SSD (128GB) 的大小，如果在 Surface Hub 桌面设备上配置 OneDrive，请确保默认配置是使文件保持联机并下载使用时的文件。

若要将OneDrive配置为仅根据需要下载文件，请设置"文件按需"**** 设置以节省空间，并下载**使用时的文件**。 有关详细信息，请参阅 Query <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> and set Files On-Demand states in Windows </a> 。

![OneDrive设置。](images/onedrive.png)

> [!NOTE]
> 还可以重复这些步骤来配置个人OneDrive但请确保节省驱动器空间，并仅根据需要下载文件。

## <a name="sharepoint-and-teams"></a>SharePoint 和 Teams

SharePoint和 Teams Channel 文件也可使用桌面引擎本地同步到桌面设备，如笔记本电脑和 Surface Hub OneDrive 同步同步。

若要使用应用程序将内部公司文件同步到本地OneDrive 同步驱动器：

1. 转到SharePoint网站，并导航到顶级文档目录，找到您有兴趣从本地设备查看或编辑的文件。

2. 在功能**区**顶部的"同步"按钮SharePoint选择。

3. 在弹出**式**菜单上的"打开"上选择此**网站正在尝试打开Microsoft OneDrive。**

4. 通过选择SharePoint右下角的"OneDrive图标，验证文件是否正在同步到本地驱动器。

5. 验证配置是否设置为使文件保持联机，并仅在使用文件时下载这些文件：

    1. 打开文件资源管理器。
    
    2. 导航到 并右键单击SharePoint名称;例如 **，Contoso \ \<SharePoint Document Folder Name\> **。
    
    3. 选择 **"释放空间"。**
    
    4. "状态"列将显示文件和文件夹的状态。 有关详细信息，请参阅 Sync <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> SharePoint files with the OneDrive 同步 client </a> 。
    
6. Teams频道文件存储在SharePoint网站中，具有所有相同的 SharePoint 文档功能，包括版本历史记录和同步到本地桌面设备。 若要同步Teams频道文件：

    1. 导航到Teams感兴趣的频道，**然后选择顶部的"** 文件"选项卡。 然后选择"**同步"。** 文件将开始同步，并且将在桌面**\ Contoso \ 的文件资源管理器中可见 \<name of the Teams Channel\> **。
    
    2. 使用用于同步 SharePoint 网站的相同过程将文件保留于云中，仅在使用这些文件时下载这些文件，只需在 Teams 频道名称上的"文件资源管理器"中点击并按住或右键单击，然后选择"**释放**空间"。

## <a name="surface-hub-pen-settings"></a>Surface Hub笔设置

**成对蓝牙 Surface Hub笔**

配对笔使笔固件保持最新，设置笔快捷方式，并获取 蓝牙 设备设置页面或 Surface 应用中的电池充电信息：

1. 选择****  >  **"设置**  >  **设备"。**

2. 选择 **"添加蓝牙或其他设备"。**

3. 选择 **"蓝牙"。**

4. 删除笔尾按钮并摇动以断开电池连接。

5. 将大头灯重新打开并按住该顶帽，直到配对 LED 闪烁。

6. On the Surface Hub 蓝牙 settings， choose **Surface Hub 2 Pen**.

7. 完成配对操作。 

8. 如果配对未成功，可以尝试再次配对笔。 如果不起作用，可以通过验证笔在白板应用程序中是否正常工作来测试电池是否充电。 如果没有，请更换电池，然后再次尝试配对笔。 如有必要，请重新启动设备，然后重试。

**设置笔快捷方式**the Surface Hub pen has a shortcut button sometimes referred to as a "tail click". 配置快捷方式需要你先配对笔，如前面所述。

1. 搜索"笔"，然后选择"**笔& Windows Ink设置"。**

2. 在页面底部附近，选择可打开对话框的笔快捷方式，如下所示：

   ![笔快捷方式。](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>相机配置

你可以将相机安装在设备顶部或两侧。 将相机装载到一个位置，以优化相机角度（如果你将 Hub 与桌面台而不是购物车一同使用，或者与 Hub 邻近）。 相机不自动旋转，因此你需要有一个 2mm 的十六进制密钥来手动旋转相机。 

若要详细了解如何旁装载相机并手动旋转相机，请参阅Surface Hub <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> 2S 相机镜头方向 </a> 。

## <a name="windows-hello-configuration"></a>Windows Hello配置

Surface Hub运行 Windows 10 企业版 的 2S 支持整套 Win32 桌面应用程序以及生物识别Windows Hello选项。 可Surface Hub 2 指纹读取器附件插入设备上的任何 USB-C 端口。 

若要订购 Surface Hub 2 指纹读取器或查看技术规格，请参阅 (surface-hub-2-essential-add-ons.md"target="_blank">Essential add-ons for Windows 10 专业版 and Enterprise on Surface Hub </a> 2。 

插入指纹读取器后，选择"开始**** 设置帐户登录选项  >  ****  >  ****  >  ****  >  **"Windows Hello指纹**"注册指纹。

使用经Windows Hello设备进行人脸识别。 2S Surface Hub 2S 相机不支持Windows Hello识别。

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>在任务栏上启用锁屏界面快捷方式图标

若要将图标添加到启用单一触摸屏锁的任务栏，Windows-L 键盘快捷方式： 

1.  点击并按住或右键单击桌面，选择"**新建**  >  **快捷方式**  >  **浏览**  >  **桌面**  >  **确定下一**  >  **步"。**

1.  提供快捷方式的名称，如**锁定我的电脑**，**然后选择完成。**

1.  右键单击或点击并按住桌面上新创建的快捷方式， **然后选择属性**。 在"**快捷方式**"选项卡上的"目标"字段中**** 输入以下内容 **：Rundll32.exe User32.dll，LockWorkStation**

1.  选择" **更改图标** "按钮并浏览 **C:\Windows\System32\imageres.dll** 并选择一个图标以使用。 

    请参见以下示例：

    ![选择图标。](images/lock.png)
    
1.  选择 **"** 确定"保存快捷方式。

1.  右键单击或点击并按住快捷方式，然后选择 **固定到任务栏**。

1. 将锁定快捷方式固定到任务栏后，可以从桌面中删除它。

## <a name="applications"></a>应用程序


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

若要安装Microsoft Whiteboard：

 - 选择**Windows Ink 工作区**右下角的"下载"图标，然后下载 **"白板"。**
 
   ![墨迹工作区。](images/ink.png) 

或者，也可以从以下操作系统安装白板Microsoft Store：

1. 打开Microsoft Store应用，然后搜索**白板**。

2. 选择 **"否，** 感谢登录并跨设备使用"。

3. 将白板固定到任务栏。

### <a name="surface-app"></a>Surface 应用

1. 在Microsoft Store中，搜索**Surface**。

2. 将"**在筛选器上**可用"**设置为"所有设备"。**

3. 安装 **Surface** 应用。 这应该是列出的第一个应用。 你可能需要将 MSA 与应用商店关联才能安装应用。

4. 将 **Surface 应用** 固定到任务栏。

### <a name="snip--sketch"></a>截图和草图

1. 打开 **"Snip & Sketch"** 应用，将其固定到任务栏。

2. 选择右上角的省略号，然后选择 **"设置"。**

3. 在**设置**中，打开自动复制到**剪**贴板、保存剪贴**** 和多个**窗口** (可选) 。

### <a name="microsoft-office"></a>Microsoft Office

1. 打开Office <a href="https://portal.office.com/account#installs" target="_blank"> </a> 门户并安装所需的应用程序。

2. 将所需的Office固定到任务栏。

3. 如果Outlook，请确保将 OUTLOOK OST 设置为仅保存最近两周缓存。 这将大大减少磁盘使用率和设置时间。

    - 选择 **"**  >  **文件设置**帐户"，然后选择您的帐户。
    
    - 选择 **"更改**"，将"使用缓存模式Exchange**滑块设置为**14 天。

### <a name="microsoft-teams"></a>Microsoft Teams

1. 下载并安装 <a href="https://teams.microsoft.com/downloads" target="_blank"> </a> Microsoft Teams。

2. 将设置配置为"自动启动应用程序" (可选) 。

3. 将Teams固定到任务栏。

4. 请考虑减少Teams通知，以避免在可选设备上 (干扰) 。

   ![Teams通知。](images/teams.png)

### <a name="connect-app"></a>连接应用

> [!IMPORTANT]
> 在 Windows 10 版本 2004 及更高版本中，使用 Miracast 的 连接 无线投影应用未默认安装，但作为可选功能提供。 如果你已安装 (或更新到) Windows 2004 或更高版本，你可能会在设置中的"计划到此电脑"屏幕上看到以下内容：

![Project此电脑。](images/sh2-project.png) 


1. 若要从"计划到此电脑"设置页安装应用，请选择"可选功能****""添加功能"，  >  **** 然后安装**无线显示**应用。

2. 在 **"Windows和 Android 设备可以计划到此电脑（当你说**它正常时）"下，选择：

    - **如果设备不在** 企业网络上，则可在任何位置使用。
    - 否则，请选择 **"在安全网络上任何地方可用"。**
    
3. 在 **"要求向此电脑进行项目"下**，选择"**仅首次"。**

4. 在 **"需要 PIN 进行配对"下，** 选择"从不 **"。**

5. 若要启动应用，将其固定到任务栏，**请搜索**连接。

6. 打开应用。 当应用打开时，右键单击任务栏连接应用图标，然后选择**固定到任务栏**。

7. 然后关闭连接应用。 **Project运行**该应用至少一次，否则无法连接到此电脑。

当不在企业网络上时，推荐配置：

![设置家。](images/project1.png)

企业网络上的推荐配置：

![设置工作。](images/project2.png)

### <a name="your-phone&quot;></a>你的手机

默认情况下**你的手机**应用程序安装在 Windows 10。 如果不存在，还可以从应用商店Windows安装。

有关设置应用的信息，请参阅如何在你的手机上设置Windows 10，以及如何在 <a href=&quot;https://www.windowscentral.com/how-set-your-phone-windows-10&quot; target=&quot;_blank&quot;> 电脑和手机之间同步数据 </a> 。 另请参阅 <a href=&quot;https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10&quot; target=&quot;_blank&quot;> 如何修复有关 你的手机 应用的 </a> Windows 10。

###  <a name=&quot;fancy-zones&quot;></a>奇特区域


**奇特**区域是名为 PowerToys 对象GitHub <a href=&quot;https://github.com/microsoft/PowerToys/releases&quot; target=&quot;_blank&quot;> </a> 集合的一部分。 这是在 Surface Hub 2 上利用屏幕空间的一种很好的方法，它让你能够在屏幕 (&quot;区域") 上定义固定布局，然后选择将在每个区域中运行的应用。 


Wiki [PowerToys提供了](https://github.com/microsoft/PowerToys/wiki)如何使用和自定义每个工具的说明，包括["奇特区域"。](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview) 在高级别 – 在安装PowerToys后，可以选择或创建自定义布局，然后按住 Shift 键并拖动或使用键盘键将正在运行的应用移动到特定区域。 使用蓝牙 USB 键盘和鼠标将对此有所帮助，或者可以使用屏幕触摸键盘和触摸板。

**Power toys tips**
- 若要接收有关PowerToys发布更新GitHub，请单击页面顶部的"注册"[按钮](https://github.com/microsoft/PowerToys/releases)。
- 安装PowerToys后，你可以接收Windows通知和/或下载并安装最新更新，方式为配置 PowerToys 设置 将更新**自动**下载到打开。
- To get to the PowerToys settings， select the up up **running apps** on the taskbar， and then right click or press and hold the PowerToys icon until the menu appears. 选择"设置"。
- 在"设置"PowerToys，将"**下载更新"自动**打开。
- 发布更新后，将显示Windows通知，为您提供安装更新时间的选项。


### <a name="edge-chromium-browser"></a>Edge Chromium 浏览器

下载并安装新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium浏览器 </a> 。


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub硬件诊断工具

the <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool available from the </a> Microsoft Store. 该工具旨在帮助你确保你的Surface Hub效果最佳。 它包含用于确定固件是否为最新且配置正确的测试。 交互式测试允许你确认基本功能是否正常工作。 如果遇到问题，可保存结果并与 Surface Hub 支持团队共享。 单击链接以从任务栏Microsoft Store，然后将应用程序固定到任务栏。

## <a name="additional-settings"></a>其他设置

### <a name="pen-tail-select-to-launch-whiteboard"></a>笔尾选择以启动白板

1. 搜索"**笔"，** 然后选择"笔 **& Windows Ink设置"。**

2. 在页面底部附近，在 **"笔快捷方式**"下设置"**选择一**次以**Microsoft Whiteboard"。** 

### <a name="power-management"></a>电源管理

在 2 号上，可以使用多种电源Windows 10 专业版Enterprise Surface Hub体验。 这包括屏幕和电脑超时，以及它们如何与内置的人机状态检测 (Doppler) 、屏幕保存和密码保护进行交互，以及在适当时如何传递适用于笔记本电脑/台式机用户的组策略电源设置。

Windows 10 专业版或 Enterprise 2 上的 Surface Hub 2 阻止屏幕通过触摸、鼠标和键盘操作以及内置的人类行为检测 (Doppler) 进入睡眠状态。 默认情况下会启用人为迁移检测，但如果需要，可以通过切换 Surface UEFI 配置器工具中的设备选项（作为初始迁移的一部分，或者通过生成和应用更高版本的 UEFI 配置包）在 UEFI 中禁用它。 

**电源管理：屏幕和电脑睡眠设置**

1. 选择 **"启动**  >  **设置**  >  **系统**  >  **电源&睡眠"。**

2. 将电源模式滑块设置为 **"最佳性能"。**

3. 根据你的偏好配置屏幕和睡眠值，同时还负责在检测到移动时唤醒设备的 Doppler 状态检测。 因此，作为最佳实践，建议将"屏幕"设置为 **"2** 小时后关闭"，将电脑设置为 **"4 小时后关闭"。**

**电源管理：屏幕保护程序**

1. 搜索 **锁屏界面并** 打开 **锁屏界面设置**。

2. 根据**你的偏好配置****屏幕超时设置和**屏幕保护程序设置。 建议的默认值为：

   - 屏幕保护 (选择) "无"屏幕保护程序或屏幕保护程序。
   - 等待 15 分钟。
   - 在恢复时，显示登录屏幕。


**电源管理：组策略**

在执行以下过程之前，请咨询 IT 部门进行审批，以将 Surface Hub 2S 设备从全局电源管理策略中排除。 某些电源管理设置可以禁用状态检测功能。

1. 搜索软件 **中心并** 打开它。

2. 选择 **选项**。

3. 展开 **"电源管理"，****然后选择"不将我的 IT 部门中的电源设置应用到此计算机"。**

   ![软件设置。](images/soft-cntr.png)

### <a name="storage-sense"></a>存储感知

由于 Surface Hub 2 具有 128GB SSD 用于本地存储，因此有必要考虑在正常使用期间使用存储保存措施。  若要配置存储感知：

1.  搜索"**系统设置"** 下的"存储**设置"。**

2.  在**设置"** 下，选择 **"打开存储感知**"**以打开存储**设置"页面。

3.  将存储感知"**打开**。

4.  选择 **"存储**感知"或现在运行它，然后配置设置以尽可能使文件保持联机状态 (驱动器空间有限) 。

推荐设置：

- 运行存储感知 = 每天。
- 删除我的应用程序未使用的临时文件 = 每 14 天 (至少一次) 。
- 删除"我的下载"文件夹中的文件（如果这些文件存在时间超过 = 30 天）。
- OneDrive：如果打开时间不超过 = 30 天，内容将仅联机。

### <a name="tablet-mode"></a>平板电脑模式

如果需要辅助功能需求，请打开平板电脑模式。


### <a name="sound-settings"></a>声音设置

1. 搜索" **声音"设置** 并打开此页面。

2. 在 **右侧选择"** 声音控制面板"，然后选择"声音 **"** 选项卡。

3. 在 **"程序事件"下****，连接****设备断开连接"和**"无 **"。**

### <a name="silence-notifications"></a>静默通知

1. 搜索焦点 **协助并** 打开此页面。

2. 选择 **"仅闹钟"。** 这将避免常量通知飞出。

### <a name="disk-cleanup"></a>磁盘清理

1. 搜索" **磁盘清理"** 并打开此应用程序。

2. 在 **"要删除的文件"** 下，选择要删除的文件。 

3. 此外， **选择清理系统文件**。

## <a name="complete-and-verify"></a>完成并验证

1. 扫描并安装所有 Windows 更新。

2. 更新组策略。

   1. 在提升的命令提示符下，输入 **gpupdate /force /boot /wait：0**。
   
3. 重新启动设备。

4. 验证任务栏应用。

   - 连接应用
   - 锁定图标
   - 截图和草图
   - Teams (适用时) 
   - Office应用 (应用（如果适用) 
   - Surface 应用
   - 白板
    
5. 验证状态检测。

   - 状态检测将是系统托盘中的绿色图标。
    
6. 验证是否已启用向此电脑连接应用。 配置Project**电脑设置**后，至少连接运行一次应用。  (之后，连接应用无需运行，就无需进行项目Surface Hub.) 

7. 验证电源和睡眠设置。

    - 屏幕保护程序：15 分钟，设置为无 (、) Mystify 或空白;确保选中"需要密码"复选框。
    - 屏幕： **在 2 小时后关闭**。
    - 电脑  **：4 小时后关闭**。
    
8. 验证Windows Hello是否正常工作。

9. 验证是否禁用了同步设置。

10. 验证启动应用。

> [!TIP]
> 安装和配置 Windows 10 后，Surface Hub 2S 可以像管理任何其他 Windows 10一样进行管理。

## <a name="related-topics"></a>相关主题

<a href="surface-hub-2s-migrate-os.md" target="_blank"> 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版</a>

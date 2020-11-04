---
title: 配置 Surface Hub 2 上的 Windows 10 专业版或企业版
description: 本文包含的建议可确保使用个性化的大屏幕触摸和手写笔计算机时获得最佳体验。
keywords: Surface Hub，Windows 10，桌面，安装，配置
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
ms.date: 11/03/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: b86776b56e892c34ea8b5abbc55d5c48723a5f9e
ms.sourcegitcommit: 3ca1d1bc77452acca914d0af03e252ee260ebf1a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154124"
---
# 配置 Surface Hub 2 上的 Windows 10 专业版或企业版

完成迁移到 Windows 10 专业版或企业版的安装过程后，您可以执行以下步骤来配置 Surface Hub 2 上的应用和设置。 建议执行这些步骤，以确保使用此个性化的大屏幕触摸和笔电脑时获得最佳体验。

执行这些步骤时，您可能会发现使用有线键盘或无线键盘和鼠标非常有用。

## 配置系统设置

1. 使用对设备具有本地管理员权限的帐户登录。  

    - 在 Azure AD 已加入设备上，执行 Azure AD 联接的用户将自动添加到本地管理员组。 Azure AD 全局管理员和 Azure AD 设备管理员 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 也是本地管理员 </a> 。 
    
    - 您可以在命令提示符下键入 **net localgroup 管理员** ，以列出具有本地管理员权限的帐户。
    
2. 使用友好名称重命名设备，例如： **username-SHub-Desktop**。

3. 选择 "**启动**  >  **设置**  >  **帐户**"  >  **同步你的设置**，并关闭**同步设置**。 

    - 此处使用的设置旨在启用最佳的屏幕触摸体验，因此你可能不希望同步其他设备。
    
4. 重新启动设备。

## 启用触摸键盘和触摸板

1. 点击并按住或右键单击任务栏，然后选择 " **显示触摸键盘按钮** " 和 " **显示触摸板" 按钮**。 

    - 触摸键盘对直接用户输入很有帮助，虚拟触摸板可帮助精确选择、悬停屏幕提示，或者作为点击并按住右键单击的替代方法。 
    
    - 请参阅以下示例。

      ![触摸设置](images/touch.png)

2. 将触摸键盘配置为 "标准" 和 "浮动"。

    1. 选择任务栏上的 **键盘** 图标以显示触摸键盘。
    
    2. 在触摸键盘上，选择左上角的键盘图标以打开 "键盘设置"。
    
    3. 选择顶部行上的 "最后一次键盘类型" 以启用标准，第二行中的最后一个选项启用浮动，这在大屏幕上非常有用。 请参阅以下示例。

       ![键盘设置](images/kbd.png)
 
3. 配置软键盘设置。

    1. 选择触摸键盘上的 " **设置** " 图标，或搜索并打开 **键入设置**。
    
       ![软键盘设置](images/sh2-softkeyboard.png)

    1. 启用 "拼写检查"、"键入" 和 "触摸键盘" 下的所有选项。


以下示例显示了触控板，这对导航和选择选项很有用。 屏幕键盘用于搜索 Microsoft Store：

![使用触控板](images/store.png)

## 配置蓝牙键盘和鼠标 (可选) 

如果将设备用作主 Windows 设备，则连接键盘和鼠标，或者经常将其用于键入或精度工作。

如果 Surface Hub 设备靠近 PC，则可以使用 <a href="https://aka.ms/mm" target="_blank"> 没有边框的鼠标在 </a> Surface HUB 和 PC 之间无缝移动。 有关详细信息，请参阅 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft 从车库下载：不带边框的鼠标。 </a>

## OneDrive for Business

使用 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive For business 在 </a> 所有工作设备之间轻松共享工具、日志和其他文件。

- OneDrive 使你能够在笔记本电脑、Surface Hub 桌面和你的 Intune 管理的移动设备之间共享你的工作文件。 可以在任何设备上编辑文件，并且所有连接网络的设备都将更新为所做的更改。

- 考虑 Surface Hub SSD 的大小 (128GB) ，如果在 Surface Hub 桌面设备上配置 OneDrive，请确保默认配置是在使用文件时保持联机文件和下载文件。

若要将 OneDrive 配置为仅在需要时下载文件，请设置 **文件的按需** 设置以在 **使用时节省空间和下载文件**。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> 在 Windows 中查询和设置文件的按需状态 </a> 。

![OneDrive 设置](images/onedrive.png)

> [!NOTE]
> 您也可以重复这些步骤来配置个人 OneDrive，但请确保保留驱动器空间，并且仅在需要时下载文件。

## SharePoint 和团队

SharePoint 和团队频道文件也可以使用 OneDrive 同步引擎在本地与桌面设备（如便携式计算机和 Surface Hub）同步。

若要将内部公司文件与 OneDrive 同步应用同步到本地驱动器，请执行以下操作：

1. 转到 SharePoint 网站，然后导航到要从本地设备查看或编辑的文件的顶级文档目录。

2. 选择 SharePoint 功能区顶部的 " **同步** " 按钮。

3. 在弹出菜单上选择 " **打开** "。 **此网站将尝试打开 Microsoft OneDrive**。

4. 通过选择任务栏右下角的 OneDrive 图标，验证 SharePoint 文件是否同步到本地驱动器。

5. 验证配置是否已设置为保持联机文件，并仅在使用时下载文件：

    1. 打开文件资源管理器。
    
    2. 导航到并右键单击您的 SharePoint 名称;例如， **Contoso \ \<SharePoint Document Folder Name\> **。
    
    3. 选择 " **释放空间**"。
    
    4. "状态" 列将显示文件和文件夹的状态。 有关详细信息，请参阅 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> 与 OneDrive 同步客户端同步 SharePoint 文件 </a> 。
    
6. 团队频道文件存储在 SharePoint 网站中，具有所有相同的 SharePoint 文档功能，包括版本历史记录和同步到本地桌面设备。 要同步团队频道文件，请执行以下操作：

    1. 导航到感兴趣的团队频道，然后选择顶部的 " **文件** " 选项卡。 然后选择 "**同步**"。文件将开始同步，并且将在**桌面 \ Contoso \ \<name of the Teams Channel\> **的文件资源管理器中可见。
    
    2. 使用您用于同步 SharePoint 网站的相同过程将文件保存在云中，并仅在使用它们时下载它们，方法是在 "文件资源管理器" 的 "团队频道名称" 中点击并按住或右键单击，然后选择 " **释放空间**"。

## Surface Hub 笔设置

**配对蓝牙 Surface Hub 笔**

对笔进行配对以使笔固件保持最新状态，并在 "蓝牙设备设置" 页面或 Surface 应用中获取电池充电信息：

1. 选择 "**开始**  >  **设置**  >  **设备**"。

2. 选择 " **添加蓝牙" 或 "其他设备**"。

3. 选择 " **蓝牙**"。

4. 卸下笔尾按钮，然后晃动以断开电池连接。

5. 将 cap 放回原位并按住 cap，直到配对指示灯闪烁。

6. 在 Surface Hub 蓝牙设置中，选择 " **Surface hub 2 笔**"。

7. 完成配对操作。 

8. 如果配对不成功，你可以尝试再次配对笔。 如果这不起作用，则可以通过验证笔在白板应用程序中的工作来查看电池是否有电。 如果不是，则更换电池，然后再次尝试配对笔。 如有必要，请重启设备，然后重试。

**设置笔快捷方式** Surface Hub 笔具有一个快捷方式按钮，有时称为 "箭尾单击"。 配置快捷方式要求首先对笔进行配对，如前文所述。

1. 搜索笔并选择 " **笔" & Windows Ink 设置**。

2. 在页面底部，选择打开该对话框的笔快捷方式，如下所示：

   ![笔快捷方式](images/sh2-pen-shortcuts.png)

## 照相机配置

可以在设备顶部或任意一侧安装相机。 如果您使用的是桌面支架而不是 cart，或者在与集线器紧密邻近的位置使用集线器，请将相机装入位置以优化相机角度。 摄像头不会自动旋转，因此你需要具有2mm 十六进制密钥才能手动旋转相机。 

有关如何安装相机以及手动旋转相机的详细信息，请参阅 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2 相机镜头方向 </a> 。

## Windows Hello 配置

运行 Windows 10 企业版的 Surface Hub 2 支持完整的 Win32 桌面应用程序和生物识别 Windows Hello 选项。 Surface Hub 2 指纹读取器附件可以插入到设备上的任何 USB 端口。 

要订购 Surface Hub 2 指纹读取器或查看技术规范，请参阅 (surface-hub-2-essential-add-ons.md "target =" _blank ">Surface Hub 2 上的 Windows 10 专业版和企业版的基本加载项 </a> 。 

插入指纹读取器后，选择 "**开始**  >  **设置**  >  **帐户**"  >  **登录选项**  >  **Windows Hello 指纹**以注册指纹。

使用 Windows Hello 认证设备进行面对面认可。 Surface Hub 2 摄像头不支持 Windows Hello 人脸识别。

## 在任务栏上启用锁定屏幕快捷方式图标

若要将图标添加到任务栏以启用与 Windows-L 键盘快捷方式类似的触摸屏幕锁定，请执行以下操作： 

1.  点击并按住或右键单击桌面，选择 "**新建**  >  **快捷方式**  >  **Browse**  >  **Desktop**  >  **"**  >  **下一步**"浏览桌面确定"。

1.  为快捷方式提供一个名称，例如 **锁定我的 PC**，然后选择 " **完成**"。

1.  右键单击或点击并按住桌面上新创建的快捷方式，然后选择 " **属性**"。 在 " **快捷方式** " 选项卡上，在 " **目标** " 字段中输入以下内容： **Rundll32.exe User32.dll，LockWorkStation**

1.  选择 " **更改图标** " 按钮，浏览到 **C:\Windows\System32\imageres.dll** 并选择要使用的图标。 

    请参见以下示例：

    ![选择图标](images/lock.png)
    
1.  选择 **"确定"** 保存快捷方式。

1.  右键单击或点击并按住快捷方式，然后选择 " **固定到任务栏**"。

1. 将锁定快捷方式固定到任务栏后，可以将其从桌面中删除。

## 应用程序

### 更新已安装的应用

若要更新安装的所有应用商店应用：

1. 打开 Microsoft Store 应用，然后在右上角选择 " **查看更多** 省略号"。

2. 选择 **下载和更新**。

2. 选择**获取更新**。

### Microsoft Whiteboard

要安装 Microsoft 白板，请执行以下操作：

 - 选择任务栏右下角的 **Windows Ink 工作区** 图标，然后下载 **白板**。
 
   ![墨迹工作区](images/ink.png) 

或者，您可以从 Microsoft Store 安装白板：

1. 打开 Microsoft Store 应用并搜索 **白板**。

2. 选择 "无"， **谢谢** 通过设备登录和使用。

3. 将白板固定到任务栏。

### Surface 应用

1. 在 Microsoft Store 中，搜索 **Surface**。

2. 将 " **在筛选器中可用** " 设置为 " **所有设备**"。

3. 安装 **Surface** app。 这应该是列出的第一个应用。 你可能需要将你的 MSA 与应用商店相关联才能安装该应用。

4. 将 **Surface** app 固定到任务栏。

### 截图和草图

1. 打开 **截图 & "草拟** " 应用，并将其固定到任务栏。

2. 选择右上角的省略号，然后选择 " **设置**"。

3. 在 " **设置**" 中，打开 " **自动复制到剪贴板**"、" **保存截图**" 和 " **多个窗口** " (可选) 。

### Microsoft Office

1. 打开 <a href="https://portal.office.com/account#installs" target="_blank"> Office 门户 </a> 并安装所需的应用程序。

2. 将所需的 Office 应用程序固定到任务栏。

3. 如果已安装 Outlook，请确保将 Outlook OST 设置为仅保存最近两周的缓存。 这将大大减少磁盘使用量和设置时间。

    - 选择 "**文件**  >  **帐户设置**"，然后选择您的帐户。
    
    - 选择 " **更改** "，将 " **使用缓存 Exchange 模式** " 滑块设置为14天。

### Microsoft Teams

1. 下载并安装 <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft 团队 </a> 。

2. 将设置配置为自动启动应用程序 (可选) 。

3. 将团队固定到任务栏。

4. 请考虑减少设备上的团队通知，避免干扰 (可选) 。

   ![团队通知](images/teams.png)

### Connect 应用

> [!IMPORTANT]
> 在 Windows 10 版本2004及更高版本中，默认情况下不会安装使用 Miracast 的无线投影的 Connect 应用，但可用作可选功能。 如果已安装 (或更新为) Windows 版本2004或更高版本，则在 "设置" 中的 "投影到此电脑" 屏幕上，你可能会看到以下情况：

![投影到这台电脑](images/sh2-project.png) 


1. 若要从 "投影到这台电脑" 设置页面安装应用，请选择 "**可选功能**"  >  **添加功能**，然后安装**无线显示器**应用。

2. 在 **某些 Windows 和 Android 设备下，如果你认为是 "确定"，可以将其投影到这台电脑**，请选择：

    - 如果设备不在公司网络上，则**可以在任何位置使用**。
    - 否则，请选择 **"安全网络上的所有位置均可用"**。
    
3. 在 " **要求在这台电脑上投影**" 下，选择 " **仅首次**"。

4. 在 " **需要 PIN 才能进行配对**" 下，选择 " **从不**"。

5. 若要启动应用并将其固定到任务栏，请搜索 " **连接**"。

6. 打开应用。 当应用处于打开状态时，右键单击任务栏上的 "连接" 应用图标，然后选择 " **固定到任务栏**"。

7. 然后关闭 "连接" 应用。 **对此电脑的项目** 可能无法正常工作，除非该应用至少已运行一次。

不在公司网络上时的推荐配置：

![家庭设置](images/project1.png)

公司网络上的推荐配置：

![工作中的设置](images/project2.png)

### 你的手机

默认情况下， **您的手机** 应用安装在 Windows 10 上。 如果不存在，还可以从 Windows 应用商店安装它。

有关设置应用的信息，请参阅 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 如何在 Windows 10 上设置你的电话和在电脑和手机之间同步数据 </a> 。 另请参阅 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 如何修复 Windows 10 上的手机应用常见问题 </a> 。

### 超级别致区域

**Super 别致的区域** 可帮助用户排列窗口以最大化屏幕房地产。 它现已包含在 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> GitHub 上的 PowerToys 中 </a> 。

### Edge Chromium 浏览器

下载并安装新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium 浏览器 </a> 。


### Surface Hub 硬件诊断工具

<a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> </a> 从 Microsoft Store 免费获取 Surface Hub 硬件诊断工具。 该工具旨在帮助你确保 Surface Hub 的性能最佳。 它包含用于确定你的固件是否为最新且配置正确的测试。 交互式测试允许你确认基本功能是否按预期工作。 如果遇到问题，可保存结果并与 Surface Hub 支持团队共享。 单击链接以从 Microsoft Store 安装它，然后将应用程序固定到任务栏。

## 其他设置

### 选择 "笔尾" 以启动白板

1. 搜索 **笔** 并选择 " **笔" & Windows Ink 设置**。

2. 在页面底部的 " **笔快捷方式** " 下，将 " **选择一次** " 设置为 " **Microsoft 白板**"。 

### 电源管理

有多个电源设置可用来获得使用 Surface Hub 2 上的 Windows 10 专业版或企业版的最佳体验。 这包括屏幕和 pc 超时以及它们如何与内置的人即签入检测 (Doppler) 、屏幕保护程序和密码保护，然后，如果需要如何向便携式/桌面用户传递组策略电源设置。

Surface Hub 2 上的 Windows 10 专业版或企业版通过触摸、鼠标和键盘操作使屏幕进入睡眠状态， (Doppler) 。 默认情况下启用 "人员使用情况检测"，但如果需要，可以通过在 Surface UEFI 配置程序工具中切换设备选项（作为初始迁移的一部分）或通过构建和应用更高的 UEFI 配置包来禁用它。 

**电源管理：屏幕和 PC 睡眠设置**

1. 选择 "**开始**  >  **设置**  >  **系统**  >  **Power & 睡眠**"。

2. 将 "电源模式" 滑块设置为 " **最佳性能**"。

3. 将屏幕和睡眠值配置为你的首选项，同时还可以对检测到移动时唤醒设备的 Doppler 状态检测进行评估。 因此，最佳做法是，建议在 **2 小时后** 将屏幕设置为关闭，并在 **4 小时后关闭电脑。**

**电源管理：屏幕保护程序**

1. 搜索 **锁屏界面** 和打开 **锁定屏幕设置**。

2. 将 **屏幕超时设置** 和 **屏幕保护程序设置** 配置为你的首选项。 推荐的默认值为：

   - 屏幕保护程序 ("无") 或您选择的屏幕保护程序。
   - 等待15分钟的时间。
   - 在恢复时，显示 "登录" 屏幕。


**电源管理：组策略**

在执行以下过程之前，请与 IT 部门联系以批准从全局电源管理策略中排除 Surface Hub 2 设备。 某些电源管理设置可以禁用状态检测功能。

1. 搜索 **软件中心** 并将其打开。

2. 选择 " **选项**"。

3. 展开 " **电源管理**  "，然后选择 **"不将 IT 部门的电源设置应用到此计算机"**。

   ![软件设置](images/soft-cntr.png)

### 存储感知

Surface Hub 2 具有用于本地存储的 128GB SSD，因此在正常使用期间，有必要考虑使用存储保存措施。  要配置存储感知，请执行以下操作：

1.  搜索在 "**系统设置**" 下找到的**存储设置**。

2.  在 " **设置**" 下，选择 " **打开存储感知** " 以打开 " **存储** 设置" 页面。

3.  将 "存储感知 **" 转到 "开"**。

4.  选择 " **配置存储感知" 或 "立即运行** "，并配置设置以尽可能多地使文件联机， (因) 的驱动器空间有限。

推荐设置：

- 每日运行的存储感知。
- 删除我的应用未使用的临时文件 = 每隔14天 (至少) 。
- 如果超过30天，则删除 "我的下载" 文件夹中的文件。
- OneDrive：如果未打开超过 = 30 天，内容将转为联机状态。

### 平板电脑模式

如果需要，请打开平板电脑模式以获得辅助功能需求。


### 声音设置

1. 搜索 " **声音设置** " 并打开此页面。

2. 选择右侧的 **"声音控制面板** "，然后选择 " **声音** " 选项卡。

3. 在 " **程序事件** " 下，将 **设备连接** 和 **设备断开** 连接到 " **无**"。

### 静音通知

1. 搜索 " **聚焦助手** "，然后打开此页面。

2. 选择 " **仅闹钟**"。 这将避免持续通知浮出控件。

### 磁盘清理

1. 搜索 " **磁盘清理** " 并打开此应用。

2. 在 " **要删除的文件**" 下，选择要删除的文件。 

3. 同时选择 " **清理系统文件**"。

## 完成并验证

1. 扫描并安装所有 Windows 更新。

2. 更新组策略

   1. 在提升的命令提示符处，输入 **gpupdate/force/boot/wait： 0**。
   
3. 重新启动设备。

4. 验证任务栏应用。

   - Connect 应用
   - 锁定图标
   - 截图和草图
   - 团队 (（如果适用）) 
   - Office 应用 (（如果适用）) 
   - Surface 应用
   - 白板
    
5. 验证状态检测。

   - 状态检测将在系统托盘中显示为绿色图标。
    
6. 验证在 Connect 应用中是否已启用投影到此电脑。 **将 Project 配置为此电脑**设置后，至少运行一次 Connect 应用。  (随后，连接应用无需运行即可投影到 Surface Hub。 ) 

7. 验证电源和睡眠设置。

    - 屏幕保护程序：15分钟，设置为 (none) ，Mystify 或空白;确保选中 "需要密码的复选框"。
    - 屏幕： **2 小时后关闭**。
    - PC：  **4 小时后关闭**。
    
8. 验证 Windows Hello 是否正常工作。

9. 验证同步您的设置已禁用。

10. 验证启动应用。

> [!TIP]
> 安装和配置 Windows 10 之后，Surface Hub 2 可以像管理任何其他 Windows 10 设备一样进行管理。

## 相关主题

<a href="surface-hub-2s-migrate-os.md" target="_blank"> 迁移到 Surface Hub 2 上的 Windows 10 专业版或企业版</a>

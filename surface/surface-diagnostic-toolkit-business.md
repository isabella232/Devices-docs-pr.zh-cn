---
title: 部署适用于企业的 Surface 诊断工具包
description: 本主题介绍如何使用 Surface Diagnostic Toolkit for Business。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271576"
---
# <span data-ttu-id="6baff-103">部署适用于企业的 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="6baff-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="6baff-104">Microsoft Surface Diagnostic Toolkit for Business (SDT) 使 IT 管理员能够快速调查、排查并解决 Surface 设备的硬件、软件和固件问题。</span><span class="sxs-lookup"><span data-stu-id="6baff-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="6baff-105">除了获取设备运行状况见解和解决问题的指导外，还可以运行一系列诊断测试和软件修复。</span><span class="sxs-lookup"><span data-stu-id="6baff-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="6baff-106">具体来说，SDT for Business 使您能够：</span><span class="sxs-lookup"><span data-stu-id="6baff-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="6baff-107">自定义程序包。</span><span class="sxs-lookup"><span data-stu-id="6baff-107">Customize the package.</span></span>](#preparing-the-sdt-package-for-distribution)
- [<span data-ttu-id="6baff-108">使用命令运行应用。</span><span class="sxs-lookup"><span data-stu-id="6baff-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="6baff-109">运行多个硬件测试以解决问题。</span><span class="sxs-lookup"><span data-stu-id="6baff-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="6baff-110">生成用于分析问题的日志。</span><span class="sxs-lookup"><span data-stu-id="6baff-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="6baff-111">获取比较设备与最佳配置的详细报告。</span><span class="sxs-lookup"><span data-stu-id="6baff-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <a name="primary-scenarios-and-download-resources"></a><span data-ttu-id="6baff-112">主要方案和下载资源</span><span class="sxs-lookup"><span data-stu-id="6baff-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="6baff-113">若要运行 SDT for Business，请下载下表中列出的组件。</span><span class="sxs-lookup"><span data-stu-id="6baff-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="6baff-114">模式</span><span class="sxs-lookup"><span data-stu-id="6baff-114">Mode</span></span> |  <span data-ttu-id="6baff-115">主要方案</span><span class="sxs-lookup"><span data-stu-id="6baff-115">Primary scenarios</span></span> | <span data-ttu-id="6baff-116">下载</span><span class="sxs-lookup"><span data-stu-id="6baff-116">Download</span></span> | <span data-ttu-id="6baff-117">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="6baff-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="6baff-118">桌面模式</span><span class="sxs-lookup"><span data-stu-id="6baff-118">Desktop mode</span></span> |  <span data-ttu-id="6baff-119">帮助用户在 Surface 设备上运行 SDT 以解决问题。</span><span class="sxs-lookup"><span data-stu-id="6baff-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="6baff-120">创建要部署在一个或多个 Surface 设备的自定义程序包，允许用户选择要收集和分析的特定日志。</span><span class="sxs-lookup"><span data-stu-id="6baff-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="6baff-121">SDT 可分发的 MSI 程序包：</span><span class="sxs-lookup"><span data-stu-id="6baff-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="6baff-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span><span class="sxs-lookup"><span data-stu-id="6baff-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="6baff-123">适合 IT 的 Surface 工具</span><span class="sxs-lookup"><span data-stu-id="6baff-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="6baff-124">在桌面Toolkit Surface Diagnostic Toolkit</span><span class="sxs-lookup"><span data-stu-id="6baff-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="6baff-125">命令行</span><span class="sxs-lookup"><span data-stu-id="6baff-125">Command line</span></span> |  <span data-ttu-id="6baff-126">使用标准工具（如 Configuration Manager）直接远程解决 Surface 设备问题，而无需用户交互。</span><span class="sxs-lookup"><span data-stu-id="6baff-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="6baff-127">它包含以下命令：</span><span class="sxs-lookup"><span data-stu-id="6baff-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="6baff-128">收集所有日志文件</span><span class="sxs-lookup"><span data-stu-id="6baff-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="6baff-129">使用最佳做法分析器运行运行状况诊断。</span><span class="sxs-lookup"><span data-stu-id="6baff-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="6baff-130">检查 Windows 更新中缺少固件或驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="6baff-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="6baff-131">检查担保信息。</span><span class="sxs-lookup"><span data-stu-id="6baff-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="6baff-132">SDT 控制台应用：</span><span class="sxs-lookup"><span data-stu-id="6baff-132">SDT console app:</span></span><br><span data-ttu-id="6baff-133">Microsoft Surface Diagnostics 应用控制台</span><span class="sxs-lookup"><span data-stu-id="6baff-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="6baff-134">适合 IT 的 Surface 工具</span><span class="sxs-lookup"><span data-stu-id="6baff-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="6baff-135">使用命令运行 Surface 诊断Toolkit</span><span class="sxs-lookup"><span data-stu-id="6baff-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <a name="supported-devices-"></a><span data-ttu-id="6baff-136">支持的设备</span><span class="sxs-lookup"><span data-stu-id="6baff-136">Supported devices</span></span> 

<span data-ttu-id="6baff-137">SDT for Business 在 Surface 3 和更高版本设备上受支持，包括：</span><span class="sxs-lookup"><span data-stu-id="6baff-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="6baff-138">Surface Book - 所有代</span><span class="sxs-lookup"><span data-stu-id="6baff-138">Surface Book - all generations</span></span>
- <span data-ttu-id="6baff-139">Surface Go - 所有代</span><span class="sxs-lookup"><span data-stu-id="6baff-139">Surface Go - all generations</span></span>
- <span data-ttu-id="6baff-140">Surface Laptop - 所有代</span><span class="sxs-lookup"><span data-stu-id="6baff-140">Surface Laptop - all generations</span></span>
- <span data-ttu-id="6baff-141">Surface Pro 3 及更高版本</span><span class="sxs-lookup"><span data-stu-id="6baff-141">Surface Pro 3 and later</span></span>
- <span data-ttu-id="6baff-142">Surface Pro X - 所有代</span><span class="sxs-lookup"><span data-stu-id="6baff-142">Surface Pro X - all generations</span></span>
- <span data-ttu-id="6baff-143">Surface Studio - 所有代</span><span class="sxs-lookup"><span data-stu-id="6baff-143">Surface Studio - all generations</span></span>
- <span data-ttu-id="6baff-144">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="6baff-144">Surface 3 LTE</span></span>
- <span data-ttu-id="6baff-145">Surface 3</span><span class="sxs-lookup"><span data-stu-id="6baff-145">Surface 3</span></span>


## <a name="installing-surface-diagnostic-toolkit-for-business"></a><span data-ttu-id="6baff-146">安装 Surface Diagnostic Toolkit for Business</span><span class="sxs-lookup"><span data-stu-id="6baff-146">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="6baff-147">若要创建可分发给组织中用户的 SDT 包：</span><span class="sxs-lookup"><span data-stu-id="6baff-147">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="6baff-148">使用管理员帐户登录到 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="6baff-148">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="6baff-149">从 Surface Tools for [IT](https://www.microsoft.com/download/details.aspx?id=46703) (.msi) 下载页面下载 SDT Windows Installer 程序包，并复制到 Surface 设备上的首选位置，如桌面。</span><span class="sxs-lookup"><span data-stu-id="6baff-149">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="6baff-150">将显示 SDT 安装向导，如图 1 所示。</span><span class="sxs-lookup"><span data-stu-id="6baff-150">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="6baff-151">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6baff-151">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="6baff-152">如果未显示安装向导，请确保已登录到您计算机的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="6baff-152">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![欢迎使用 Surface Diagnostic Toolkit设置向导](images/sdt-1.png)

    *<span data-ttu-id="6baff-154">图 1.</span><span class="sxs-lookup"><span data-stu-id="6baff-154">Figure 1.</span></span> <span data-ttu-id="6baff-155">Surface 诊断Toolkit设置向导</span><span class="sxs-lookup"><span data-stu-id="6baff-155">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="6baff-156">当 SDT 安装向导出现时\*\*\*\*，单击"下一步"，接受 EULA (最终用户许可协议) </span><span class="sxs-lookup"><span data-stu-id="6baff-156">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="6baff-157">如果需要，在"安装选项"屏幕上更改默认安装位置。</span><span class="sxs-lookup"><span data-stu-id="6baff-157">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="6baff-158">在"安装类型"下，选择 **"高级"。**</span><span class="sxs-lookup"><span data-stu-id="6baff-158">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="6baff-159">标准选项允许用户直接在 Surface 设备上运行诊断工具，只要他们使用管理员帐户登录设备。</span><span class="sxs-lookup"><span data-stu-id="6baff-159">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![安装选项：高级](images/sdt-install.png)

7. <span data-ttu-id="6baff-161">单击 **"** 下一步"，然后单击"**安装"。**</span><span class="sxs-lookup"><span data-stu-id="6baff-161">Click **Next** and then click **Install**.</span></span> 

## <a name="installing-using-the-command-line"></a><span data-ttu-id="6baff-162">使用命令行安装</span><span class="sxs-lookup"><span data-stu-id="6baff-162">Installing using the command line</span></span>
<span data-ttu-id="6baff-163">如果需要，可以在命令提示符下安装 SDT，并设置自定义标志以在管理模式下安装该工具。</span><span class="sxs-lookup"><span data-stu-id="6baff-163">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="6baff-164">SDT 包含以下安装选项标志：</span><span class="sxs-lookup"><span data-stu-id="6baff-164">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="6baff-165">将遥测数据发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="6baff-165">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="6baff-166">标志接受 `0` 禁用或 `1` 启用。</span><span class="sxs-lookup"><span data-stu-id="6baff-166">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="6baff-167">默认值是 `1` 发送遥测。</span><span class="sxs-lookup"><span data-stu-id="6baff-167">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="6baff-168">配置要以管理模式安装的工具。</span><span class="sxs-lookup"><span data-stu-id="6baff-168">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="6baff-169">该标志接受 `0` 客户端模式或 `1` IT 管理员模式。</span><span class="sxs-lookup"><span data-stu-id="6baff-169">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="6baff-170">默认值为 `0`。</span><span class="sxs-lookup"><span data-stu-id="6baff-170">The default value is `0`.</span></span>

### <a name="to-install-sdt-from-the-command-line"></a><span data-ttu-id="6baff-171">若要从命令行安装 SDT：</span><span class="sxs-lookup"><span data-stu-id="6baff-171">To install SDT from the command line:</span></span>

1. <span data-ttu-id="6baff-172">打开命令提示符并输入：</span><span class="sxs-lookup"><span data-stu-id="6baff-172">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="6baff-173">示例：</span><span class="sxs-lookup"><span data-stu-id="6baff-173">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <a name="locating-sdt-on-your-surface-device"></a><span data-ttu-id="6baff-174">在 Surface 设备上定位 SDT</span><span class="sxs-lookup"><span data-stu-id="6baff-174">Locating SDT on your Surface device</span></span>

<span data-ttu-id="6baff-175">SDT 和 SDT 应用控制台都安装在 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 。</span><span class="sxs-lookup"><span data-stu-id="6baff-175">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="6baff-176">除了 .exe 文件，SDT 还安装了 JSON 文件和 admin.dll 文件 (modules\admin.dll) ，如图 2 所示。</span><span class="sxs-lookup"><span data-stu-id="6baff-176">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![文件资源管理器中已安装 SDT 文件的列表](images/sdt-2.png)

*<span data-ttu-id="6baff-178">图 2.</span><span class="sxs-lookup"><span data-stu-id="6baff-178">Figure 2.</span></span> <span data-ttu-id="6baff-179">由 SDT 安装的文件</span><span class="sxs-lookup"><span data-stu-id="6baff-179">Files installed by SDT</span></span>*

## <a name="preparing-the-sdt-package-for-distribution"></a><span data-ttu-id="6baff-180">准备 SDT 包进行分发</span><span class="sxs-lookup"><span data-stu-id="6baff-180">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="6baff-181">通过创建自定义程序包，你可以将工具定向到特定的已知问题。</span><span class="sxs-lookup"><span data-stu-id="6baff-181">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="6baff-182">Click **Start > Run，** enter **Surface** and then click Surface Diagnostic Toolkit **for Business.**</span><span class="sxs-lookup"><span data-stu-id="6baff-182">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="6baff-183">工具打开后，单击 **"创建自定义程序包**"，如图 3 所示。</span><span class="sxs-lookup"><span data-stu-id="6baff-183">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![创建自定义程序包选项](images/sdt-3.png)

    *<span data-ttu-id="6baff-185">图 3.</span><span class="sxs-lookup"><span data-stu-id="6baff-185">Figure 3.</span></span> <span data-ttu-id="6baff-186">创建自定义程序包</span><span class="sxs-lookup"><span data-stu-id="6baff-186">Create custom package</span></span>*

### <a name="language-and-telemetry-settings"></a><span data-ttu-id="6baff-187">语言和遥测设置</span><span class="sxs-lookup"><span data-stu-id="6baff-187">Language and telemetry settings</span></span>

  <span data-ttu-id="6baff-188">创建程序包时，可以选择语言设置或选择不向 Microsoft 发送遥测信息。</span><span class="sxs-lookup"><span data-stu-id="6baff-188">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="6baff-189">默认情况下，SDT 根据 Microsoft 隐私声明向 Microsoft 发送用于改进应用程序的 [遥测](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="6baff-189">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="6baff-190">如果希望拒绝，请在创建自定义程序包时清除该复选框，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6baff-190">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="6baff-191">或者，在 SDT 安装期间清除"\*\*\*\* 安装选项"页上的"将遥测发送到**Microsoft"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="6baff-191">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="6baff-192">当运行需要 Internet 连接的测试和修复（如 Windows 更新和软件修复）时，或者使用应用工具栏中的"笑脸"或"小脸"按钮提供反馈时，此设置不会影响 Microsoft 服务器上自动存储的最少遥测。</span><span class="sxs-lookup"><span data-stu-id="6baff-192">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![选择语言和遥测设置](images/sdt-4.png)

*<span data-ttu-id="6baff-194">图 4.</span><span class="sxs-lookup"><span data-stu-id="6baff-194">Figure 4.</span></span> <span data-ttu-id="6baff-195">选择语言和遥测设置</span><span class="sxs-lookup"><span data-stu-id="6baff-195">Select language and telemetry settings</span></span>*


### <a name="windows-update-page"></a><span data-ttu-id="6baff-196">Windows 更新页</span><span class="sxs-lookup"><span data-stu-id="6baff-196">Windows Update page</span></span>

<span data-ttu-id="6baff-197">选择适合贵组织的选项。</span><span class="sxs-lookup"><span data-stu-id="6baff-197">Select the option appropriate for your organization.</span></span> <span data-ttu-id="6baff-198">具有多个用户的大多数组织通常会选择通过 Windows Server Update Services (WSUS) 接收更新，如图 5 所示。</span><span class="sxs-lookup"><span data-stu-id="6baff-198">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="6baff-199">如果使用本地 Windows 更新程序包或 WSUS，请根据情况输入路径。</span><span class="sxs-lookup"><span data-stu-id="6baff-199">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![选择 Windows 更新选项](images/sdt-5.png)

*<span data-ttu-id="6baff-201">图 5.</span><span class="sxs-lookup"><span data-stu-id="6baff-201">Figure 5.</span></span> <span data-ttu-id="6baff-202">Windows 更新选项</span><span class="sxs-lookup"><span data-stu-id="6baff-202">Windows Update option</span></span>*

### <a name="software-repair-page"></a><span data-ttu-id="6baff-203">软件修复页</span><span class="sxs-lookup"><span data-stu-id="6baff-203">Software repair page</span></span>

<span data-ttu-id="6baff-204">这允许你选择或删除运行软件修复更新的选项。</span><span class="sxs-lookup"><span data-stu-id="6baff-204">This allows you to select or remove the option to run software repair updates.</span></span> 

![选择软件修复选项](images/sdt-6.png)

*<span data-ttu-id="6baff-206">图 6.</span><span class="sxs-lookup"><span data-stu-id="6baff-206">Figure 6.</span></span> <span data-ttu-id="6baff-207">软件修复选项</span><span class="sxs-lookup"><span data-stu-id="6baff-207">Software repair option</span></span>*

### <a name="collecting-logs-and-saving-package-page"></a><span data-ttu-id="6baff-208">收集日志并保存程序包页面</span><span class="sxs-lookup"><span data-stu-id="6baff-208">Collecting logs and saving package page</span></span>

<span data-ttu-id="6baff-209">可以选择跨应用程序、驱动程序、硬件和操作系统运行各种日志。</span><span class="sxs-lookup"><span data-stu-id="6baff-209">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="6baff-210">单击相应的区域，然后从可用日志的菜单中选择。</span><span class="sxs-lookup"><span data-stu-id="6baff-210">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="6baff-211">然后，您可以将程序包保存到软件分发点或用户可以访问的等效位置。</span><span class="sxs-lookup"><span data-stu-id="6baff-211">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![选择日志选项](images/sdt-7.png)

*<span data-ttu-id="6baff-213">图 7.</span><span class="sxs-lookup"><span data-stu-id="6baff-213">Figure 7.</span></span> <span data-ttu-id="6baff-214">日志选项和保存程序包</span><span class="sxs-lookup"><span data-stu-id="6baff-214">Log option and save package</span></span>*

## <a name="next-steps"></a><span data-ttu-id="6baff-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6baff-215">Next steps</span></span>

- [<span data-ttu-id="6baff-216">在桌面模式下使用适用于企业的 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="6baff-216">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="6baff-217">使用适用于Toolkit Surface Diagnostic Toolkit For Business</span><span class="sxs-lookup"><span data-stu-id="6baff-217">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <a name="changes-and-updates"></a><span data-ttu-id="6baff-218">更改和更新</span><span class="sxs-lookup"><span data-stu-id="6baff-218">Changes and updates</span></span>

### <a name="version-2.131.139.0"></a><span data-ttu-id="6baff-219">版本 2.131.139.0</span><span class="sxs-lookup"><span data-stu-id="6baff-219">Version 2.131.139.0</span></span>

<span data-ttu-id="6baff-220">此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="6baff-220">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="6baff-221">支持 Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="6baff-221">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="6baff-222">Surface Pro X 上的无缝支持体验</span><span class="sxs-lookup"><span data-stu-id="6baff-222">Seamless support experience on Surface Pro X</span></span>
- <span data-ttu-id="6baff-223">安全改进</span><span class="sxs-lookup"><span data-stu-id="6baff-223">Security improvements</span></span>
- <span data-ttu-id="6baff-224">非独占用户体验改进</span><span class="sxs-lookup"><span data-stu-id="6baff-224">Inclusive user experience improvements</span></span>

### <a name="version-2.124.139.0"></a><span data-ttu-id="6baff-225">版本 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="6baff-225">Version 2.124.139.0</span></span>

<span data-ttu-id="6baff-226">此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="6baff-226">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="6baff-227">无缝集成支持</span><span class="sxs-lookup"><span data-stu-id="6baff-227">Seamless integrated support</span></span>
- <span data-ttu-id="6baff-228">保存所有测试结果</span><span class="sxs-lookup"><span data-stu-id="6baff-228">Save all test results</span></span>
- <span data-ttu-id="6baff-229">检查映像是否创建自定义</span><span class="sxs-lookup"><span data-stu-id="6baff-229">Check if the image is custom created</span></span>
- <span data-ttu-id="6baff-230">包括来自设备管理器的警告</span><span class="sxs-lookup"><span data-stu-id="6baff-230">Include warnings from device manager</span></span>
- <span data-ttu-id="6baff-231">扩展坞固件版本</span><span class="sxs-lookup"><span data-stu-id="6baff-231">Dock firmware version</span></span>
- <span data-ttu-id="6baff-232">将驱动器标为存储测试中的潜在故障</span><span class="sxs-lookup"><span data-stu-id="6baff-232">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="6baff-233">删除存储链接</span><span class="sxs-lookup"><span data-stu-id="6baff-233">Remove store link</span></span> 

### <a name="version-2.121.139"></a><span data-ttu-id="6baff-234">版本 2.121.139</span><span class="sxs-lookup"><span data-stu-id="6baff-234">Version 2.121.139</span></span>
*<span data-ttu-id="6baff-235">发布日期：2020 年 7 月 31 日</span><span class="sxs-lookup"><span data-stu-id="6baff-235">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="6baff-236">此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="6baff-236">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="6baff-237">无缝支持体验</span><span class="sxs-lookup"><span data-stu-id="6baff-237">Seamless support experience</span></span>
- <span data-ttu-id="6baff-238">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="6baff-238">Bug fixes</span></span>

### <a name="version-2.94.139.0"></a><span data-ttu-id="6baff-239">版本 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="6baff-239">Version 2.94.139.0</span></span>
*<span data-ttu-id="6baff-240">发布日期：2020 年 5 月 11 日</span><span class="sxs-lookup"><span data-stu-id="6baff-240">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="6baff-241">此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="6baff-241">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="6baff-242">跳过 Windows 更新以执行硬件检查的能力。</span><span class="sxs-lookup"><span data-stu-id="6baff-242">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="6baff-243">能够接收有关最新版本更新的通知</span><span class="sxs-lookup"><span data-stu-id="6baff-243">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="6baff-244">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="6baff-244">Surface Go 2</span></span>
- <span data-ttu-id="6baff-245">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="6baff-245">Surface Book 3</span></span>
- <span data-ttu-id="6baff-246">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="6baff-246">Show progress indicator</span></span>


### <a name="version-2.43.139.0"></a><span data-ttu-id="6baff-247">版本 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="6baff-247">Version 2.43.139.0</span></span>
*<span data-ttu-id="6baff-248">发布日期：2019 年 10 月 21 日</span><span class="sxs-lookup"><span data-stu-id="6baff-248">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="6baff-249">此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="6baff-249">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="6baff-250">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="6baff-250">Surface Pro 7</span></span>
- <span data-ttu-id="6baff-251">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="6baff-251">Surface Laptop 3</span></span>

### <a name="version-2.42.139.0"></a><span data-ttu-id="6baff-252">版本 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="6baff-252">Version 2.42.139.0</span></span>
*<span data-ttu-id="6baff-253">发布日期：2019 年 9 月 24 日</span><span class="sxs-lookup"><span data-stu-id="6baff-253">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="6baff-254">此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="6baff-254">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="6baff-255">下载硬件报告的能力。</span><span class="sxs-lookup"><span data-stu-id="6baff-255">Ability to download hardware reports.</span></span>
- <span data-ttu-id="6baff-256">可以直接通过该工具联系 Microsoft 支持人员。</span><span class="sxs-lookup"><span data-stu-id="6baff-256">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <a name="version-2.41.139.0"></a><span data-ttu-id="6baff-257">版本 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="6baff-257">Version 2.41.139.0</span></span>
*<span data-ttu-id="6baff-258">发布日期：2019 年 6 月 24 日</span><span class="sxs-lookup"><span data-stu-id="6baff-258">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="6baff-259">此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="6baff-259">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="6baff-260">日志和报告中包含的驱动程序版本信息。</span><span class="sxs-lookup"><span data-stu-id="6baff-260">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="6baff-261">提供有关应用的反馈的能力。</span><span class="sxs-lookup"><span data-stu-id="6baff-261">Ability to provide feedback about the app.</span></span><br>


### <a name="version-2.36.139.0"></a><span data-ttu-id="6baff-262">版本 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="6baff-262">Version 2.36.139.0</span></span>
*<span data-ttu-id="6baff-263">发布日期：2019 年 4 月 26 日</span><span class="sxs-lookup"><span data-stu-id="6baff-263">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="6baff-264">此版本的 Surface Diagnostic Toolkit for Business 增加了对以下内容的支持：</span><span class="sxs-lookup"><span data-stu-id="6baff-264">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="6baff-265">高级安装程序选项，用于通过安装程序 UI 解锁管理功能，而无需命令行配置。</span><span class="sxs-lookup"><span data-stu-id="6baff-265">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="6baff-266">辅助功能改进。</span><span class="sxs-lookup"><span data-stu-id="6baff-266">Accessibility improvements.</span></span>
- <span data-ttu-id="6baff-267">日志中包含的图面亮度控制设置。</span><span class="sxs-lookup"><span data-stu-id="6baff-267">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="6baff-268">报告生成器中的外部监视器兼容性支持链接。</span><span class="sxs-lookup"><span data-stu-id="6baff-268">External monitor compatibility support link in report generator.</span></span>

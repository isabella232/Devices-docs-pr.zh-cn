---
title: 部署适用于企业的 Surface 诊断工具包
description: 本主题介绍了如何使用面向企业的 Surface 诊断工具包。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 1f2661811516507abd432dba602cf8ce81e6dbb3
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114660"
---
# <span data-ttu-id="f9364-103">部署适用于企业的 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="f9364-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="f9364-104">适用于 Business (SDT) 的 Microsoft Surface 诊断工具包使 IT 管理员能够快速调查和解决与 Surface 设备有关的硬件、软件和固件问题。</span><span class="sxs-lookup"><span data-stu-id="f9364-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="f9364-105">除了获取设备运行状况见解和解决问题的指南之外，还可以运行一系列诊断测试和软件修复。</span><span class="sxs-lookup"><span data-stu-id="f9364-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="f9364-106">特别是，SDT for Business 使你能够：</span><span class="sxs-lookup"><span data-stu-id="f9364-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="f9364-107">自定义程序包。</span><span class="sxs-lookup"><span data-stu-id="f9364-107">Customize the package.</span></span>](#create-custom-sdt)
- [<span data-ttu-id="f9364-108">使用命令运行应用。</span><span class="sxs-lookup"><span data-stu-id="f9364-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="f9364-109">运行多个硬件测试以解决问题。</span><span class="sxs-lookup"><span data-stu-id="f9364-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="f9364-110">生成用于分析问题的日志。</span><span class="sxs-lookup"><span data-stu-id="f9364-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="f9364-111">获取与最佳配置比较设备和最佳配置的详细报告。</span><span class="sxs-lookup"><span data-stu-id="f9364-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="f9364-112">主要方案和下载资源</span><span class="sxs-lookup"><span data-stu-id="f9364-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="f9364-113">若要运行 SDT for Business，请下载下表中列出的组件。</span><span class="sxs-lookup"><span data-stu-id="f9364-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="f9364-114">模式</span><span class="sxs-lookup"><span data-stu-id="f9364-114">Mode</span></span> |  <span data-ttu-id="f9364-115">主要方案</span><span class="sxs-lookup"><span data-stu-id="f9364-115">Primary scenarios</span></span> | <span data-ttu-id="f9364-116">下载</span><span class="sxs-lookup"><span data-stu-id="f9364-116">Download</span></span> | <span data-ttu-id="f9364-117">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="f9364-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="f9364-118">桌面模式</span><span class="sxs-lookup"><span data-stu-id="f9364-118">Desktop mode</span></span> |  <span data-ttu-id="f9364-119">帮助用户在其 Surface 设备上运行 SDT 以解决问题。</span><span class="sxs-lookup"><span data-stu-id="f9364-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="f9364-120">创建要在一个或多个 Surface 设备上部署的自定义程序包，以允许用户选择要收集和分析的特定日志。</span><span class="sxs-lookup"><span data-stu-id="f9364-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="f9364-121">SDT 可分发 MSI 程序包：</span><span class="sxs-lookup"><span data-stu-id="f9364-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="f9364-122">适用于企业版安装程序的 Microsoft Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="f9364-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="f9364-123">适合 IT 的 Surface 工具</span><span class="sxs-lookup"><span data-stu-id="f9364-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="f9364-124">在桌面模式下使用 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="f9364-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="f9364-125">命令行</span><span class="sxs-lookup"><span data-stu-id="f9364-125">Command line</span></span> |  <span data-ttu-id="f9364-126">使用标准工具（如配置管理器）无需用户交互即可直接对 Surface 设备进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="f9364-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="f9364-127">它包括以下命令：</span><span class="sxs-lookup"><span data-stu-id="f9364-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="f9364-128">收集所有日志文件</span><span class="sxs-lookup"><span data-stu-id="f9364-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="f9364-129">使用最佳做法分析器运行运行状况诊断。</span><span class="sxs-lookup"><span data-stu-id="f9364-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="f9364-130">检查 Windows 更新中是否缺少固件或驱动程序更新。</span><span class="sxs-lookup"><span data-stu-id="f9364-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="f9364-131">检查保修信息。</span><span class="sxs-lookup"><span data-stu-id="f9364-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="f9364-132">SDT 控制台应用：</span><span class="sxs-lookup"><span data-stu-id="f9364-132">SDT console app:</span></span><br><span data-ttu-id="f9364-133">Microsoft Surface 诊断应用程序控制台</span><span class="sxs-lookup"><span data-stu-id="f9364-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="f9364-134">适合 IT 的 Surface 工具</span><span class="sxs-lookup"><span data-stu-id="f9364-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="f9364-135">使用命令运行 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="f9364-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="f9364-136">支持的设备</span><span class="sxs-lookup"><span data-stu-id="f9364-136">Supported devices</span></span> 

<span data-ttu-id="f9364-137">在 Surface 3 及更高版本的设备上支持 SDT for Business，包括：</span><span class="sxs-lookup"><span data-stu-id="f9364-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="f9364-138">Surface 膝上型电脑 Go</span><span class="sxs-lookup"><span data-stu-id="f9364-138">Surface Laptop Go</span></span>
- <span data-ttu-id="f9364-139">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="f9364-139">Surface Book 3</span></span>
- <span data-ttu-id="f9364-140">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="f9364-140">Surface Go 2</span></span>
- <span data-ttu-id="f9364-141">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="f9364-141">Surface Pro X</span></span>
- <span data-ttu-id="f9364-142">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="f9364-142">Surface Pro 7</span></span>
- <span data-ttu-id="f9364-143">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="f9364-143">Surface Laptop 3</span></span>
- <span data-ttu-id="f9364-144">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="f9364-144">Surface Pro 6</span></span>
- <span data-ttu-id="f9364-145">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="f9364-145">Surface Laptop 2</span></span>
- <span data-ttu-id="f9364-146">Surface Go</span><span class="sxs-lookup"><span data-stu-id="f9364-146">Surface Go</span></span>
- <span data-ttu-id="f9364-147">带有 LTE 的 Surface Go</span><span class="sxs-lookup"><span data-stu-id="f9364-147">Surface Go with LTE</span></span>
- <span data-ttu-id="f9364-148">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="f9364-148">Surface Book 2</span></span>
- <span data-ttu-id="f9364-149">带有 LTE Advanced 的 Surface Pro（型号 1807）</span><span class="sxs-lookup"><span data-stu-id="f9364-149">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="f9364-150">Surface Pro（型号 1796）</span><span class="sxs-lookup"><span data-stu-id="f9364-150">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="f9364-151">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="f9364-151">Surface Laptop</span></span>
- <span data-ttu-id="f9364-152">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="f9364-152">Surface Studio</span></span>
- <span data-ttu-id="f9364-153">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="f9364-153">Surface Studio 2</span></span>
- <span data-ttu-id="f9364-154">Surface Book</span><span class="sxs-lookup"><span data-stu-id="f9364-154">Surface Book</span></span>
- <span data-ttu-id="f9364-155">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="f9364-155">Surface Pro 4</span></span>
- <span data-ttu-id="f9364-156">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="f9364-156">Surface 3 LTE</span></span>
- <span data-ttu-id="f9364-157">Surface 3</span><span class="sxs-lookup"><span data-stu-id="f9364-157">Surface 3</span></span>
- <span data-ttu-id="f9364-158">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="f9364-158">Surface Pro 3</span></span>

## <span data-ttu-id="f9364-159">安装面向企业的 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="f9364-159">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="f9364-160">若要创建可分发给组织中的用户的 SDT 程序包，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f9364-160">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="f9364-161">使用管理员帐户登录 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="f9364-161">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="f9364-162">从 " [Surface Tools FOR IT 下载" 页面](https://www.microsoft.com/download/details.aspx?id=46703) 下载 SDT Windows Installer 程序包 ( .msi) 并将其复制到 surface 设备（如桌面）上的首选位置。</span><span class="sxs-lookup"><span data-stu-id="f9364-162">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="f9364-163">将显示 "SDT 设置" 向导，如图1所示。</span><span class="sxs-lookup"><span data-stu-id="f9364-163">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="f9364-164">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9364-164">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="f9364-165">如果未显示 "设置向导"，请确保您已登录到您的计算机上的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="f9364-165">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![欢迎使用 Surface 诊断工具包设置向导](images/sdt-1.png)

    *<span data-ttu-id="f9364-167">图 1.</span><span class="sxs-lookup"><span data-stu-id="f9364-167">Figure 1.</span></span> <span data-ttu-id="f9364-168">图面诊断工具包设置向导</span><span class="sxs-lookup"><span data-stu-id="f9364-168">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="f9364-169">当 "SDT 设置向导" 出现时，单击 " **下一步**"，接受《最终用户许可协议》 (EULA) </span><span class="sxs-lookup"><span data-stu-id="f9364-169">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="f9364-170">在 "安装选项" 屏幕上，根据需要更改默认安装位置。</span><span class="sxs-lookup"><span data-stu-id="f9364-170">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="f9364-171">在 "安装类型" 下，选择 " **高级**"。</span><span class="sxs-lookup"><span data-stu-id="f9364-171">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="f9364-172">标准选项允许用户在其 Surface 设备上直接运行诊断工具，前提是他们已使用管理员帐户登录到其设备。</span><span class="sxs-lookup"><span data-stu-id="f9364-172">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![安装选项：高级](images/sdt-install.png)

7. <span data-ttu-id="f9364-174">单击 " **下一步** "，然后单击 " **安装**"。</span><span class="sxs-lookup"><span data-stu-id="f9364-174">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="f9364-175">使用命令行安装</span><span class="sxs-lookup"><span data-stu-id="f9364-175">Installing using the command line</span></span>
<span data-ttu-id="f9364-176">如果需要，您可以在命令提示符处安装 SDT 并设置自定义标志以在管理员模式下安装该工具。</span><span class="sxs-lookup"><span data-stu-id="f9364-176">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="f9364-177">SDT 包含以下安装选项标志：</span><span class="sxs-lookup"><span data-stu-id="f9364-177">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="f9364-178">将遥测数据发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="f9364-178">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="f9364-179">标志接受 " `0` 已禁用" 或 " `1` 已启用"。</span><span class="sxs-lookup"><span data-stu-id="f9364-179">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="f9364-180">默认值是 `1` 发送遥测。</span><span class="sxs-lookup"><span data-stu-id="f9364-180">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="f9364-181">配置要在管理员模式下安装的工具。</span><span class="sxs-lookup"><span data-stu-id="f9364-181">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="f9364-182">标志接受 `0` 客户端模式或 `1` IT 管理员模式。</span><span class="sxs-lookup"><span data-stu-id="f9364-182">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="f9364-183">默认值为 `0`。</span><span class="sxs-lookup"><span data-stu-id="f9364-183">The default value is `0`.</span></span>

### <span data-ttu-id="f9364-184">要从命令行安装 SDT，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f9364-184">To install SDT from the command line:</span></span>

1. <span data-ttu-id="f9364-185">打开命令提示符并输入：</span><span class="sxs-lookup"><span data-stu-id="f9364-185">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="f9364-186">示例：</span><span class="sxs-lookup"><span data-stu-id="f9364-186">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="f9364-187">在 Surface 设备上找到 SDT</span><span class="sxs-lookup"><span data-stu-id="f9364-187">Locating SDT on your Surface device</span></span>

<span data-ttu-id="f9364-188">将安装 "SDT" 和 "SDT" 应用控制台 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 。</span><span class="sxs-lookup"><span data-stu-id="f9364-188">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="f9364-189">除了 .exe 文件之外，SDT 还会安装 JSON 文件和 admin.dll 文件 ( # A1) ，如图2所示。</span><span class="sxs-lookup"><span data-stu-id="f9364-189">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![文件资源管理器中的 SDT 已安装文件的列表](images/sdt-2.png)

*<span data-ttu-id="f9364-191">图 2.</span><span class="sxs-lookup"><span data-stu-id="f9364-191">Figure 2.</span></span> <span data-ttu-id="f9364-192">由 SDT 安装的文件</span><span class="sxs-lookup"><span data-stu-id="f9364-192">Files installed by SDT</span></span>*

<span id="create-custom-sdt" />

## <span data-ttu-id="f9364-193">准备用于分发的 SDT 程序包</span><span class="sxs-lookup"><span data-stu-id="f9364-193">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="f9364-194">创建自定义程序包使你可以将工具定位到特定的已知问题。</span><span class="sxs-lookup"><span data-stu-id="f9364-194">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="f9364-195">单击 " **开始 > 运行**"，输入 " **表面** "，然后单击 " **面向企业的 surface 诊断工具包**"。</span><span class="sxs-lookup"><span data-stu-id="f9364-195">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="f9364-196">当工具打开时，单击 " **创建自定义程序包**"，如图3所示。</span><span class="sxs-lookup"><span data-stu-id="f9364-196">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![创建自定义程序包选项](images/sdt-3.png)

    *<span data-ttu-id="f9364-198">图 3.</span><span class="sxs-lookup"><span data-stu-id="f9364-198">Figure 3.</span></span> <span data-ttu-id="f9364-199">创建自定义程序包</span><span class="sxs-lookup"><span data-stu-id="f9364-199">Create custom package</span></span>*

### <span data-ttu-id="f9364-200">语言和遥测设置</span><span class="sxs-lookup"><span data-stu-id="f9364-200">Language and telemetry settings</span></span>

  <span data-ttu-id="f9364-201">创建程序包时，你可以选择语言设置或选择不向 Microsoft 发送遥测信息。</span><span class="sxs-lookup"><span data-stu-id="f9364-201">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="f9364-202">默认情况下，SDT 会将遥测发送到用于根据 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)改进应用程序的 microsoft。</span><span class="sxs-lookup"><span data-stu-id="f9364-202">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="f9364-203">如果想要拒绝，请清除创建自定义程序包时的复选框，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f9364-203">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="f9364-204">或清除 "**安装选项**" 页面上的 "将**遥测发送到 Microsoft** " 复选框（在 SDT 设置期间）。</span><span class="sxs-lookup"><span data-stu-id="f9364-204">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="f9364-205">此设置不会影响运行需要 Internet 连接（如 Windows 更新和软件修复）或使用应用工具栏中的笑脸或 Frown 按钮提供反馈的测试和修复时，自动存储在 Microsoft 服务器上的最小遥测。</span><span class="sxs-lookup"><span data-stu-id="f9364-205">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![选择语言和遥测设置](images/sdt-4.png)

*<span data-ttu-id="f9364-207">图 4.</span><span class="sxs-lookup"><span data-stu-id="f9364-207">Figure 4.</span></span> <span data-ttu-id="f9364-208">选择语言和遥测设置</span><span class="sxs-lookup"><span data-stu-id="f9364-208">Select language and telemetry settings</span></span>*


### <span data-ttu-id="f9364-209">Windows 更新页面</span><span class="sxs-lookup"><span data-stu-id="f9364-209">Windows Update page</span></span>

<span data-ttu-id="f9364-210">选择适用于你的组织的选项。</span><span class="sxs-lookup"><span data-stu-id="f9364-210">Select the option appropriate for your organization.</span></span> <span data-ttu-id="f9364-211">大多数具有多个用户的组织通常会选择通过 Windows Server Update Services (WSUS) 接收更新，如图5所示。</span><span class="sxs-lookup"><span data-stu-id="f9364-211">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="f9364-212">如果使用本地 Windows 更新程序包或 WSUS，请根据需要输入路径。</span><span class="sxs-lookup"><span data-stu-id="f9364-212">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![选择 "Windows 更新" 选项](images/sdt-5.png)

*<span data-ttu-id="f9364-214">图 5.</span><span class="sxs-lookup"><span data-stu-id="f9364-214">Figure 5.</span></span> <span data-ttu-id="f9364-215">Windows 更新选项</span><span class="sxs-lookup"><span data-stu-id="f9364-215">Windows Update option</span></span>*

### <span data-ttu-id="f9364-216">软件修复页面</span><span class="sxs-lookup"><span data-stu-id="f9364-216">Software repair page</span></span>

<span data-ttu-id="f9364-217">这允许你选择或删除运行软件修复更新的选项。</span><span class="sxs-lookup"><span data-stu-id="f9364-217">This allows you to select or remove the option to run software repair updates.</span></span> 

![选择软件修复选项](images/sdt-6.png)

*<span data-ttu-id="f9364-219">图 6.</span><span class="sxs-lookup"><span data-stu-id="f9364-219">Figure 6.</span></span> <span data-ttu-id="f9364-220">软件修复选项</span><span class="sxs-lookup"><span data-stu-id="f9364-220">Software repair option</span></span>*

### <span data-ttu-id="f9364-221">收集日志和保存程序包页面</span><span class="sxs-lookup"><span data-stu-id="f9364-221">Collecting logs and saving package page</span></span>

<span data-ttu-id="f9364-222">你可以选择在应用程序、驱动程序、硬件和操作系统上运行各种日志。</span><span class="sxs-lookup"><span data-stu-id="f9364-222">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="f9364-223">单击相应的区域，然后从可用日志的菜单中进行选择。</span><span class="sxs-lookup"><span data-stu-id="f9364-223">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="f9364-224">然后，你可以将程序包保存到用户可以访问的软件分发点或等效位置。</span><span class="sxs-lookup"><span data-stu-id="f9364-224">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![选择日志选项](images/sdt-7.png)

*<span data-ttu-id="f9364-226">图 7.</span><span class="sxs-lookup"><span data-stu-id="f9364-226">Figure 7.</span></span> <span data-ttu-id="f9364-227">日志选项和保存程序包</span><span class="sxs-lookup"><span data-stu-id="f9364-227">Log option and save package</span></span>*

## <span data-ttu-id="f9364-228">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f9364-228">Next steps</span></span>

- [<span data-ttu-id="f9364-229">在桌面模式下使用适用于企业的 Surface 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="f9364-229">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="f9364-230">使用命令的面向企业的表面诊断工具包</span><span class="sxs-lookup"><span data-stu-id="f9364-230">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="f9364-231">更改和更新</span><span class="sxs-lookup"><span data-stu-id="f9364-231">Changes and updates</span></span>

### <span data-ttu-id="f9364-232">版本2.124.139。0</span><span class="sxs-lookup"><span data-stu-id="f9364-232">Version 2.124.139.0</span></span>

<span data-ttu-id="f9364-233">此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：</span><span class="sxs-lookup"><span data-stu-id="f9364-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="f9364-234">无缝集成支持</span><span class="sxs-lookup"><span data-stu-id="f9364-234">Seamless integrated support</span></span>
- <span data-ttu-id="f9364-235">保存所有测试结果</span><span class="sxs-lookup"><span data-stu-id="f9364-235">Save all test results</span></span>
- <span data-ttu-id="f9364-236">检查图像是否已创建自定义</span><span class="sxs-lookup"><span data-stu-id="f9364-236">Check if the image is custom created</span></span>
- <span data-ttu-id="f9364-237">包括来自设备管理器的警告</span><span class="sxs-lookup"><span data-stu-id="f9364-237">Include warnings from device manager</span></span>
- <span data-ttu-id="f9364-238">插接固件版本</span><span class="sxs-lookup"><span data-stu-id="f9364-238">Dock firmware version</span></span>
- <span data-ttu-id="f9364-239">将驱动器标记为存储测试中的潜在故障</span><span class="sxs-lookup"><span data-stu-id="f9364-239">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="f9364-240">删除存储链接</span><span class="sxs-lookup"><span data-stu-id="f9364-240">Remove store link</span></span> 

### <span data-ttu-id="f9364-241">版本2.121.139</span><span class="sxs-lookup"><span data-stu-id="f9364-241">Version 2.121.139</span></span>
*<span data-ttu-id="f9364-242">发布日期： 31 2020 年7月</span><span class="sxs-lookup"><span data-stu-id="f9364-242">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="f9364-243">此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：</span><span class="sxs-lookup"><span data-stu-id="f9364-243">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="f9364-244">无缝支持体验</span><span class="sxs-lookup"><span data-stu-id="f9364-244">Seamless support experience</span></span>
- <span data-ttu-id="f9364-245">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="f9364-245">Bug fixes</span></span>

### <span data-ttu-id="f9364-246">版本2.94.139。0</span><span class="sxs-lookup"><span data-stu-id="f9364-246">Version 2.94.139.0</span></span>
*<span data-ttu-id="f9364-247">发布日期： 2020 5 月11日</span><span class="sxs-lookup"><span data-stu-id="f9364-247">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="f9364-248">此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：</span><span class="sxs-lookup"><span data-stu-id="f9364-248">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="f9364-249">能够跳过 Windows 更新以执行硬件检查。</span><span class="sxs-lookup"><span data-stu-id="f9364-249">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="f9364-250">能够接收有关最新版本更新的通知</span><span class="sxs-lookup"><span data-stu-id="f9364-250">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="f9364-251">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="f9364-251">Surface Go 2</span></span>
- <span data-ttu-id="f9364-252">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="f9364-252">Surface Book 3</span></span>
- <span data-ttu-id="f9364-253">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="f9364-253">Show progress indicator</span></span>


### <span data-ttu-id="f9364-254">版本2.43.139。0</span><span class="sxs-lookup"><span data-stu-id="f9364-254">Version 2.43.139.0</span></span>
*<span data-ttu-id="f9364-255">发布日期：2019年10月21日</span><span class="sxs-lookup"><span data-stu-id="f9364-255">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="f9364-256">此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：</span><span class="sxs-lookup"><span data-stu-id="f9364-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="f9364-257">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="f9364-257">Surface Pro 7</span></span>
- <span data-ttu-id="f9364-258">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="f9364-258">Surface Laptop 3</span></span>

### <span data-ttu-id="f9364-259">版本2.42.139。0</span><span class="sxs-lookup"><span data-stu-id="f9364-259">Version 2.42.139.0</span></span>
*<span data-ttu-id="f9364-260">发布日期：2019年9月24日</span><span class="sxs-lookup"><span data-stu-id="f9364-260">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="f9364-261">此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：</span><span class="sxs-lookup"><span data-stu-id="f9364-261">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="f9364-262">下载硬件报告的能力。</span><span class="sxs-lookup"><span data-stu-id="f9364-262">Ability to download hardware reports.</span></span>
- <span data-ttu-id="f9364-263">直接从工具联系 Microsoft 支持的能力。</span><span class="sxs-lookup"><span data-stu-id="f9364-263">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="f9364-264">版本2.41.139。0</span><span class="sxs-lookup"><span data-stu-id="f9364-264">Version 2.41.139.0</span></span>
*<span data-ttu-id="f9364-265">发布日期：2019年6月24日</span><span class="sxs-lookup"><span data-stu-id="f9364-265">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="f9364-266">此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：</span><span class="sxs-lookup"><span data-stu-id="f9364-266">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="f9364-267">日志和报告中包含的驱动程序版本信息。</span><span class="sxs-lookup"><span data-stu-id="f9364-267">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="f9364-268">提供有关应用的反馈的能力。</span><span class="sxs-lookup"><span data-stu-id="f9364-268">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="f9364-269">版本2.36.139。0</span><span class="sxs-lookup"><span data-stu-id="f9364-269">Version 2.36.139.0</span></span>
*<span data-ttu-id="f9364-270">发布日期：2019年4月26日</span><span class="sxs-lookup"><span data-stu-id="f9364-270">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="f9364-271">此面向企业的 Surface 诊断工具包的版本增加了对以下各项的支持：</span><span class="sxs-lookup"><span data-stu-id="f9364-271">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="f9364-272">"高级设置" 选项，通过安装程序 UI 解锁管理员功能，无需命令行配置。</span><span class="sxs-lookup"><span data-stu-id="f9364-272">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="f9364-273">辅助功能改进。</span><span class="sxs-lookup"><span data-stu-id="f9364-273">Accessibility improvements.</span></span>
- <span data-ttu-id="f9364-274">日志中包含 Surface 亮度控制设置。</span><span class="sxs-lookup"><span data-stu-id="f9364-274">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="f9364-275">报表生成器中的外部监视器兼容性支持链接。</span><span class="sxs-lookup"><span data-stu-id="f9364-275">External monitor compatibility support link in report generator.</span></span>

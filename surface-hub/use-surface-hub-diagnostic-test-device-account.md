---
title: 使用 Surface Hub 硬件诊断工具测试设备帐户
description: 使用 Surface Hub 硬件诊断工具测试设备帐户
ms.assetid: a87b7d41-d0a7-4acc-bfa6-b9070f99bc9c
keywords: 辅助功能设置, “设置”应用, 轻松使用
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 6661f2347d2f411ed11fe6057ede8ca2bab07c33
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406665"
---
# <a name="using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-account"></a><span data-ttu-id="57cd6-104">使用 Surface Hub 硬件诊断工具测试设备帐户</span><span class="sxs-lookup"><span data-stu-id="57cd6-104">Using the Surface Hub Hardware Diagnostic Tool to test a device account</span></span>

## <a name="introduction"></a><span data-ttu-id="57cd6-105">简介</span><span class="sxs-lookup"><span data-stu-id="57cd6-105">Introduction</span></span>

> [!NOTE]
> <span data-ttu-id="57cd6-106">Surface Hub 硬件诊断工具的"帐户设置"部分不会收集任何信息。</span><span class="sxs-lookup"><span data-stu-id="57cd6-106">The "Account Settings" section of the Surface Hub Hardware Diagnostic tool doesn’t collect any information.</span></span> <span data-ttu-id="57cd6-107">作为输入输入输入的电子邮件和密码仅在环境中直接使用，不会收集或传输到任何人。</span><span class="sxs-lookup"><span data-stu-id="57cd6-107">The email and password that are entered as input are used only directly on your environment and not collected or transferred to anyone.</span></span> <span data-ttu-id="57cd6-108">登录信息仅在应用程序关闭或结束 Surface Hub 上的当前会话之前保留。</span><span class="sxs-lookup"><span data-stu-id="57cd6-108">The login information persists only until the application is closed or you end the current session on the Surface Hub.</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="57cd6-109">运行此应用程序不需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="57cd6-109">Administrator privileges are not required to run this application.</span></span>
> * <span data-ttu-id="57cd6-110">在向 Microsoft 打开服务调用之前，应该与本地管理员讨论诊断结果。</span><span class="sxs-lookup"><span data-stu-id="57cd6-110">The results of the diagnostic should be discussed with your local administrator before you open a service call with Microsoft.</span></span>

### <a name="surface-hub-hardware-diagnostic"></a><span data-ttu-id="57cd6-111">Surface Hub 硬件诊断</span><span class="sxs-lookup"><span data-stu-id="57cd6-111">Surface Hub Hardware Diagnostic</span></span>

<span data-ttu-id="57cd6-112">默认情况下 [，Surface Hub 硬件](https://www.microsoft.com/store/apps/9nblggh51f2g) 诊断应用程序未安装在 Surface Hub 系统的早期版本中。</span><span class="sxs-lookup"><span data-stu-id="57cd6-112">By default, the [Surface Hub Hardware Diagnostic](https://www.microsoft.com/store/apps/9nblggh51f2g) application isn’t installed in earlier versions of the Surface Hub system.</span></span> <span data-ttu-id="57cd6-113">应用程序可从 Microsoft Store 免费获得。</span><span class="sxs-lookup"><span data-stu-id="57cd6-113">The application is available for free from the Microsoft Store.</span></span> <span data-ttu-id="57cd6-114">安装应用程序需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="57cd6-114">Administrator privileges are required to install the application.</span></span>

   ![硬件诊断的屏幕截图](images/01-diagnostic.png)

## <a name="about-the-surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="57cd6-116">关于 Surface Hub 硬件诊断工具</span><span class="sxs-lookup"><span data-stu-id="57cd6-116">About the Surface Hub Hardware Diagnostic Tool</span></span>

<span data-ttu-id="57cd6-117">Surface Hub 硬件诊断工具是一种易于导航的工具，允许用户测试 Surface Hub 设备中的许多硬件组件。</span><span class="sxs-lookup"><span data-stu-id="57cd6-117">The Surface Hub Hardware Diagnostic tool is an easy-to-navigate tool that lets the user test many of the hardware components within the Surface Hub device.</span></span> <span data-ttu-id="57cd6-118">此工具还可以测试和验证 Surface Hub 设备帐户。</span><span class="sxs-lookup"><span data-stu-id="57cd6-118">This tool can also test and verify a Surface Hub device account.</span></span> <span data-ttu-id="57cd6-119">本文介绍了如何在 Surface Hub 硬件诊断工具内使用帐户设置测试。</span><span class="sxs-lookup"><span data-stu-id="57cd6-119">This article describes how to use the Account Settings test within the Surface Hub Hardware Diagnostic tool.</span></span>

> [!NOTE]
> <span data-ttu-id="57cd6-120">Surface Hub 的设备帐户应在完成任何测试之前创建。</span><span class="sxs-lookup"><span data-stu-id="57cd6-120">The device account for the Surface Hub should be created before any testing is done.</span></span> <span data-ttu-id="57cd6-121">Surface Hub 管理员指南提供了说明和 PowerShell 脚本，可帮助你创建本地、联机 (Office365) 或混合设备帐户。</span><span class="sxs-lookup"><span data-stu-id="57cd6-121">The Surface Hub Administrator Guide provides instructions and PowerShell scripts to help you create on-premises, online (Office365), or hybrid device accounts.</span></span> <span data-ttu-id="57cd6-122">有关详细信息，请转到指南中的创建和测试 Surface Hub ([设备 ](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub)) 主题。</span><span class="sxs-lookup"><span data-stu-id="57cd6-122">For more information, go to the [Create and test a device account (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) topic in the guide.</span></span>

### <a name="device-account-testing-process"></a><span data-ttu-id="57cd6-123">设备帐户测试过程</span><span class="sxs-lookup"><span data-stu-id="57cd6-123">Device account testing process</span></span>

1. <span data-ttu-id="57cd6-124">导航到 **"所有应用"，** 然后找到 Surface Hub 硬件诊断应用程序。</span><span class="sxs-lookup"><span data-stu-id="57cd6-124">Navigate to **All Apps**, and then locate the Surface Hub Hardware Diagnostic application.</span></span>

    ![所有应用的屏幕截图](images/02-all-apps.png)

1. <span data-ttu-id="57cd6-126">应用程序启动时，欢迎页面提供\*\*\*\* 一个文本窗口，用于记录测试 Hub 的原因。</span><span class="sxs-lookup"><span data-stu-id="57cd6-126">When the application starts, the **Welcome** page provides a text window to document the reason why you are testing the Hub.</span></span> <span data-ttu-id="57cd6-127">在测试结束时，可以将此笔记与诊断结果一起保存到 USB。</span><span class="sxs-lookup"><span data-stu-id="57cd6-127">This note can be saved to USB together with the diagnostic results at the conclusion of testing.</span></span> <span data-ttu-id="57cd6-128">输入便笺后，选择"继续 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="57cd6-128">After you finish entering a note, select the **Continue** button.</span></span>

    >[!NOTE]
    ><span data-ttu-id="57cd6-129">保存诊断结果时，不要更改默认路径或选择子目录。</span><span class="sxs-lookup"><span data-stu-id="57cd6-129">When saving diagnostic results, do not change the default path or select a subdirectory.</span></span> <span data-ttu-id="57cd6-130">稍后可通过文件资源管理器应用复制这些文件。</span><span class="sxs-lookup"><span data-stu-id="57cd6-130">The files can be copied later via the File Explorer app.</span></span>

    ![欢迎屏幕截图](images/03-welcome.png)

1. <span data-ttu-id="57cd6-132">下一个屏幕提供测试所有或部分 Surface Hub 组件的选项。</span><span class="sxs-lookup"><span data-stu-id="57cd6-132">The next screen provides you the option to test all or some of the Surface Hub components.</span></span> <span data-ttu-id="57cd6-133">若要开始测试设备帐户， **请选择测试结果图标** 。</span><span class="sxs-lookup"><span data-stu-id="57cd6-133">To begin testing the device account, select the **Test Results** icon.</span></span>

    ![测试选项的屏幕截图](images/04-test-results-1.png)

    ![测试结果的屏幕截图](images/05-test-results-2.png)

1. <span data-ttu-id="57cd6-136">选择 **帐户设置**。</span><span class="sxs-lookup"><span data-stu-id="57cd6-136">Select **Account Settings**.</span></span>  

    ![帐户设置的屏幕截图](images/06-account-settings.png)

    <span data-ttu-id="57cd6-138">"帐户设置"屏幕用于测试设备帐户。</span><span class="sxs-lookup"><span data-stu-id="57cd6-138">The Account Settings screen is used to test your device account.</span></span>

    ![帐户设置详细信息的屏幕截图](images/07-account-settings-details.png)

1. <span data-ttu-id="57cd6-140">输入设备帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="57cd6-140">Enter the email address of your device account.</span></span> <span data-ttu-id="57cd6-141">密码是可选的，但建议这样做。</span><span class="sxs-lookup"><span data-stu-id="57cd6-141">The password is optional but is recommended.</span></span> <span data-ttu-id="57cd6-142">准备好 **继续时** ，选择"测试帐户"按钮。</span><span class="sxs-lookup"><span data-stu-id="57cd6-142">Select the **Test Account** button when you are ready to continue.</span></span>

    ![测试帐户的屏幕截图](images/08-test-account.png)

1. <span data-ttu-id="57cd6-144">测试完成后，查看四个测试区域的结果。</span><span class="sxs-lookup"><span data-stu-id="57cd6-144">After testing is finished, review the results for the four areas of testing.</span></span> <span data-ttu-id="57cd6-145">通过选择每个主题旁边的加号或减号，可以展开或折叠每个部分。</span><span class="sxs-lookup"><span data-stu-id="57cd6-145">Each section can be expanded or collapsed by selecting the Plus or Minus sign next to each topic.</span></span>

    **<span data-ttu-id="57cd6-146">网络</span><span class="sxs-lookup"><span data-stu-id="57cd6-146">Network</span></span>**

    ![网络屏幕截图](images/09-network.png)

    **<span data-ttu-id="57cd6-148">环境</span><span class="sxs-lookup"><span data-stu-id="57cd6-148">Environment</span></span>**

    ![环境的屏幕截图](images/10-environment.png)

    **<span data-ttu-id="57cd6-150">证书</span><span class="sxs-lookup"><span data-stu-id="57cd6-150">Certificates</span></span>**

    ![证书屏幕截图](images/11-certificates.png)

    **<span data-ttu-id="57cd6-152">信任模型</span><span class="sxs-lookup"><span data-stu-id="57cd6-152">Trust Model</span></span>**

    ![信任模型的屏幕截图](images/12-trust-model.png)

## <a name="appendix"></a><span data-ttu-id="57cd6-154">附录</span><span class="sxs-lookup"><span data-stu-id="57cd6-154">Appendix</span></span>

### <a name="field-messages-and-resolution"></a><span data-ttu-id="57cd6-155">字段消息和解析</span><span class="sxs-lookup"><span data-stu-id="57cd6-155">Field messages and resolution</span></span>

#### <a name="network"></a><span data-ttu-id="57cd6-156">网络</span><span class="sxs-lookup"><span data-stu-id="57cd6-156">Network</span></span>

<span data-ttu-id="57cd6-157">字段</span><span class="sxs-lookup"><span data-stu-id="57cd6-157">Field</span></span> |<span data-ttu-id="57cd6-158">成功</span><span class="sxs-lookup"><span data-stu-id="57cd6-158">Success</span></span> |<span data-ttu-id="57cd6-159">失败</span><span class="sxs-lookup"><span data-stu-id="57cd6-159">Failure</span></span> |<span data-ttu-id="57cd6-160">评论</span><span class="sxs-lookup"><span data-stu-id="57cd6-160">Comment</span></span> |<span data-ttu-id="57cd6-161">参考</span><span class="sxs-lookup"><span data-stu-id="57cd6-161">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="57cd6-162">Internet 连接</span><span class="sxs-lookup"><span data-stu-id="57cd6-162">Internet Connectivity</span></span> |<span data-ttu-id="57cd6-163">设备确实具有 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="57cd6-163">Device does have Internet connectivity</span></span> |<span data-ttu-id="57cd6-164">设备没有 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="57cd6-164">Device does not have Internet connectivity</span></span> |<span data-ttu-id="57cd6-165">验证 Internet 连接，包括代理连接</span><span class="sxs-lookup"><span data-stu-id="57cd6-165">Verifies internet connectivity, including proxy connection</span></span> |
<span data-ttu-id="57cd6-166">HTTP 版本</span><span class="sxs-lookup"><span data-stu-id="57cd6-166">HTTP Version</span></span> |<span data-ttu-id="57cd6-167">1.1</span><span class="sxs-lookup"><span data-stu-id="57cd6-167">1.1</span></span> |<span data-ttu-id="57cd6-168">1.0</span><span class="sxs-lookup"><span data-stu-id="57cd6-168">1.0</span></span> |<span data-ttu-id="57cd6-169">如果找到 HTTP 1.0，则会导致 WU 和 Store 出问题</span><span class="sxs-lookup"><span data-stu-id="57cd6-169">If HTTP 1.0 found, it will cause issue with WU and Store</span></span> |
<span data-ttu-id="57cd6-170">直接 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="57cd6-170">Direct Internet Connectivity</span></span> |<span data-ttu-id="57cd6-171">设备已配置代理 设备未配置代理</span><span class="sxs-lookup"><span data-stu-id="57cd6-171">Device has a Proxy configured Device has no Proxy configured</span></span> |<span data-ttu-id="57cd6-172">不适用</span><span class="sxs-lookup"><span data-stu-id="57cd6-172">N/A</span></span> |<span data-ttu-id="57cd6-173">信息性。</span><span class="sxs-lookup"><span data-stu-id="57cd6-173">Informational.</span></span> <span data-ttu-id="57cd6-174">你的设备是否位于代理后面？</span><span class="sxs-lookup"><span data-stu-id="57cd6-174">Is your device behind a proxy?</span></span> |
<span data-ttu-id="57cd6-175">代理地址</span><span class="sxs-lookup"><span data-stu-id="57cd6-175">Proxy Address</span></span> | | |<span data-ttu-id="57cd6-176">如果配置，则返回代理地址。</span><span class="sxs-lookup"><span data-stu-id="57cd6-176">If configured, returns proxy address.</span></span> |
<span data-ttu-id="57cd6-177">代理身份验证</span><span class="sxs-lookup"><span data-stu-id="57cd6-177">Proxy Authentication</span></span> |<span data-ttu-id="57cd6-178">代理不需要身份验证</span><span class="sxs-lookup"><span data-stu-id="57cd6-178">Proxy does not require Authentication</span></span> |<span data-ttu-id="57cd6-179">代理需要代理身份验证</span><span class="sxs-lookup"><span data-stu-id="57cd6-179">Proxy requires Proxy Auth</span></span> |<span data-ttu-id="57cd6-180">如果用户已在 Edge 中具有打开的会话并且已通过代理身份验证，则结果可能是误报。</span><span class="sxs-lookup"><span data-stu-id="57cd6-180">Result may be a false positive if a user already has an open session in Edge and has authenticated through the proxy.</span></span> |
<span data-ttu-id="57cd6-181">代理身份验证类型</span><span class="sxs-lookup"><span data-stu-id="57cd6-181">Proxy Auth Types</span></span> | | |<span data-ttu-id="57cd6-182">如果使用代理身份验证，则返回代理播发的 Authentication 方法。</span><span class="sxs-lookup"><span data-stu-id="57cd6-182">If proxy authentication is used, return the Authentication methods advertised by the proxy.</span></span>  |

#### <a name="environment"></a><span data-ttu-id="57cd6-183">环境</span><span class="sxs-lookup"><span data-stu-id="57cd6-183">Environment</span></span>

<span data-ttu-id="57cd6-184">字段</span><span class="sxs-lookup"><span data-stu-id="57cd6-184">Field</span></span> |<span data-ttu-id="57cd6-185">成功</span><span class="sxs-lookup"><span data-stu-id="57cd6-185">Success</span></span> |<span data-ttu-id="57cd6-186">失败</span><span class="sxs-lookup"><span data-stu-id="57cd6-186">Failure</span></span> |<span data-ttu-id="57cd6-187">评论</span><span class="sxs-lookup"><span data-stu-id="57cd6-187">Comment</span></span> |<span data-ttu-id="57cd6-188">参考</span><span class="sxs-lookup"><span data-stu-id="57cd6-188">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="57cd6-189">SIP 域</span><span class="sxs-lookup"><span data-stu-id="57cd6-189">SIP Domain</span></span> | | |<span data-ttu-id="57cd6-190">信息性。</span><span class="sxs-lookup"><span data-stu-id="57cd6-190">Informational.</span></span>  |
<span data-ttu-id="57cd6-191">Skype 环境</span><span class="sxs-lookup"><span data-stu-id="57cd6-191">Skype Environment</span></span> |<span data-ttu-id="57cd6-192">Skype for Business Online、Skype for Business OnPrem、Skype for Business 混合</span><span class="sxs-lookup"><span data-stu-id="57cd6-192">Skype for Business Online, Skype for Business OnPrem, Skype for Business Hybrid</span></span> |<span data-ttu-id="57cd6-193">信息性。</span><span class="sxs-lookup"><span data-stu-id="57cd6-193">Informational.</span></span> |<span data-ttu-id="57cd6-194">检测到的环境类型。</span><span class="sxs-lookup"><span data-stu-id="57cd6-194">What type of environment was detected.</span></span> <span data-ttu-id="57cd6-195">注意：只有在输入密码后才能检测到混合。</span><span class="sxs-lookup"><span data-stu-id="57cd6-195">Note: Hybrid can only be detected if the password is entered.</span></span>
<span data-ttu-id="57cd6-196">LyncDiscover FQDN</span><span class="sxs-lookup"><span data-stu-id="57cd6-196">LyncDiscover FQDN</span></span> | | |<span data-ttu-id="57cd6-197">信息性。</span><span class="sxs-lookup"><span data-stu-id="57cd6-197">Informational.</span></span> <span data-ttu-id="57cd6-198">显示 LyncDiscover DNS 结果</span><span class="sxs-lookup"><span data-stu-id="57cd6-198">Displays the LyncDiscover DNS result</span></span> |
<span data-ttu-id="57cd6-199">LyncDiscover URI</span><span class="sxs-lookup"><span data-stu-id="57cd6-199">LyncDiscover URI</span></span> | | |<span data-ttu-id="57cd6-200">信息性。</span><span class="sxs-lookup"><span data-stu-id="57cd6-200">Informational.</span></span> <span data-ttu-id="57cd6-201">显示用于在环境中执行 LyncDiscover 的 URL。</span><span class="sxs-lookup"><span data-stu-id="57cd6-201">Displays the URL used to perform a LyncDiscover on your environment.</span></span>|
<span data-ttu-id="57cd6-202">LyncDiscover</span><span class="sxs-lookup"><span data-stu-id="57cd6-202">LyncDiscover</span></span> |<span data-ttu-id="57cd6-203">连接成功</span><span class="sxs-lookup"><span data-stu-id="57cd6-203">Connection Successful</span></span> |<span data-ttu-id="57cd6-204">连接失败</span><span class="sxs-lookup"><span data-stu-id="57cd6-204">Connection Failed</span></span> |<span data-ttu-id="57cd6-205">来自 LyncDiscover Web 服务的响应。</span><span class="sxs-lookup"><span data-stu-id="57cd6-205">Response from LyncDiscover web service.</span></span> |
<span data-ttu-id="57cd6-206">SIP 池主机名</span><span class="sxs-lookup"><span data-stu-id="57cd6-206">SIP Pool Hostname</span></span> | | |<span data-ttu-id="57cd6-207">信息性。</span><span class="sxs-lookup"><span data-stu-id="57cd6-207">Informational.</span></span> <span data-ttu-id="57cd6-208">显示从 LyncDiscover 发现的 SIP 池名称</span><span class="sxs-lookup"><span data-stu-id="57cd6-208">Display the SIP pool name discovered from LyncDiscover</span></span> |

#### <a name="certificates-in-premises-hybrid-only"></a><span data-ttu-id="57cd6-209">证书 (本地混合环境) </span><span class="sxs-lookup"><span data-stu-id="57cd6-209">Certificates (in-premises hybrid only)</span></span>

<span data-ttu-id="57cd6-210">LyncDiscover 证书</span><span class="sxs-lookup"><span data-stu-id="57cd6-210">LyncDiscover Certificate</span></span>

<span data-ttu-id="57cd6-211">字段</span><span class="sxs-lookup"><span data-stu-id="57cd6-211">Field</span></span> |<span data-ttu-id="57cd6-212">成功</span><span class="sxs-lookup"><span data-stu-id="57cd6-212">Success</span></span> |<span data-ttu-id="57cd6-213">失败</span><span class="sxs-lookup"><span data-stu-id="57cd6-213">Failure</span></span> |<span data-ttu-id="57cd6-214">评论</span><span class="sxs-lookup"><span data-stu-id="57cd6-214">Comment</span></span> |<span data-ttu-id="57cd6-215">参考</span><span class="sxs-lookup"><span data-stu-id="57cd6-215">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="57cd6-216">LyncDiscover Cert CN</span><span class="sxs-lookup"><span data-stu-id="57cd6-216">LyncDiscover Cert CN</span></span> | | |<span data-ttu-id="57cd6-217">信息性。</span><span class="sxs-lookup"><span data-stu-id="57cd6-217">Informational.</span></span> <span data-ttu-id="57cd6-218">显示 LD 证书公用名</span><span class="sxs-lookup"><span data-stu-id="57cd6-218">Displays the LD cert Common name</span></span> |
<span data-ttu-id="57cd6-219">LyncDiscover Cert CA</span><span class="sxs-lookup"><span data-stu-id="57cd6-219">LyncDiscover Cert CA</span></span> | | |<span data-ttu-id="57cd6-220">信息性。</span><span class="sxs-lookup"><span data-stu-id="57cd6-220">Informational.</span></span> <span data-ttu-id="57cd6-221">显示 LD Cert CA</span><span class="sxs-lookup"><span data-stu-id="57cd6-221">Displays the LD Cert CA</span></span> |
<span data-ttu-id="57cd6-222">LyncDiscover 证书根 CA</span><span class="sxs-lookup"><span data-stu-id="57cd6-222">LyncDiscover Cert Root CA</span></span> | | |<span data-ttu-id="57cd6-223">信息性。</span><span class="sxs-lookup"><span data-stu-id="57cd6-223">Informational.</span></span> <span data-ttu-id="57cd6-224">显示 LD 证书根 CA（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="57cd6-224">Displays the LD Cert Root CA, if available.</span></span> |
<span data-ttu-id="57cd6-225">LD 信任状态</span><span class="sxs-lookup"><span data-stu-id="57cd6-225">LD Trust Status</span></span> |<span data-ttu-id="57cd6-226">证书为受信任证书。</span><span class="sxs-lookup"><span data-stu-id="57cd6-226">Certificate is Trusted.</span></span> |<span data-ttu-id="57cd6-227">证书不可信，请添加根 CA。</span><span class="sxs-lookup"><span data-stu-id="57cd6-227">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="57cd6-228">针对本地证书存储验证证书。</span><span class="sxs-lookup"><span data-stu-id="57cd6-228">Verify the certificate against the local cert store.</span></span> <span data-ttu-id="57cd6-229">如果计算机信任证书，则返回正数。</span><span class="sxs-lookup"><span data-stu-id="57cd6-229">Returns positive if the machine trusts the certificate.</span></span>|<span data-ttu-id="57cd6-230">[使用 PowerShell 下载和部署 Skype for Business 证书](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) /[Surface Hub 预配包支持的项目](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="57cd6-230">[Download and deploy Skype for Business certificates using PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/)/[Supported items for Surface Hub provisioning packages](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span></span>

<span data-ttu-id="57cd6-231">SIP 池认证</span><span class="sxs-lookup"><span data-stu-id="57cd6-231">SIP Pool Certification</span></span>

<span data-ttu-id="57cd6-232">字段</span><span class="sxs-lookup"><span data-stu-id="57cd6-232">Field</span></span> |<span data-ttu-id="57cd6-233">成功</span><span class="sxs-lookup"><span data-stu-id="57cd6-233">Success</span></span> |<span data-ttu-id="57cd6-234">失败</span><span class="sxs-lookup"><span data-stu-id="57cd6-234">Failure</span></span> |<span data-ttu-id="57cd6-235">评论</span><span class="sxs-lookup"><span data-stu-id="57cd6-235">Comment</span></span> |<span data-ttu-id="57cd6-236">参考</span><span class="sxs-lookup"><span data-stu-id="57cd6-236">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="57cd6-237">SIP 池证书 CN</span><span class="sxs-lookup"><span data-stu-id="57cd6-237">SIP Pool Cert CN</span></span> | | |<span data-ttu-id="57cd6-238"> (内容) </span><span class="sxs-lookup"><span data-stu-id="57cd6-238">(CONTENTS)</span></span> |
<span data-ttu-id="57cd6-239">SIP 池证书 CA</span><span class="sxs-lookup"><span data-stu-id="57cd6-239">SIP Pool Cert CA</span></span> | | |<span data-ttu-id="57cd6-240"> (内容) </span><span class="sxs-lookup"><span data-stu-id="57cd6-240">(CONTENTS)</span></span> |
<span data-ttu-id="57cd6-241">SIP 池信任状态</span><span class="sxs-lookup"><span data-stu-id="57cd6-241">SIP Pool Trust Status</span></span> |<span data-ttu-id="57cd6-242">证书为受信任证书。</span><span class="sxs-lookup"><span data-stu-id="57cd6-242">Certificate is Trusted.</span></span> |<span data-ttu-id="57cd6-243">证书不可信，请添加根 CA。</span><span class="sxs-lookup"><span data-stu-id="57cd6-243">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="57cd6-244">针对本地证书存储验证证书，如果设备信任证书，则返回正数。</span><span class="sxs-lookup"><span data-stu-id="57cd6-244">Verify the certificate against the local cert store and return a positive if the devices trusts the certificate.</span></span> |
<span data-ttu-id="57cd6-245">SIP 池证书根 CA</span><span class="sxs-lookup"><span data-stu-id="57cd6-245">SIP Pool Cert Root CA</span></span> | | |<span data-ttu-id="57cd6-246">信息。</span><span class="sxs-lookup"><span data-stu-id="57cd6-246">Information.</span></span> <span data-ttu-id="57cd6-247">显示 SIP 池证书根 CA（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="57cd6-247">Display the SIP Pool Cert Root CA, if available.</span></span> |

#### <a name="trust-model-on-premises-hybrid-only"></a><span data-ttu-id="57cd6-248">信任模型 (本地混合环境) </span><span class="sxs-lookup"><span data-stu-id="57cd6-248">Trust Model (on-premises hybrid only)</span></span>

<span data-ttu-id="57cd6-249">字段</span><span class="sxs-lookup"><span data-stu-id="57cd6-249">Field</span></span> |<span data-ttu-id="57cd6-250">成功</span><span class="sxs-lookup"><span data-stu-id="57cd6-250">Success</span></span> |<span data-ttu-id="57cd6-251">失败</span><span class="sxs-lookup"><span data-stu-id="57cd6-251">Failure</span></span> |<span data-ttu-id="57cd6-252">评论</span><span class="sxs-lookup"><span data-stu-id="57cd6-252">Comment</span></span> |<span data-ttu-id="57cd6-253">参考</span><span class="sxs-lookup"><span data-stu-id="57cd6-253">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="57cd6-254">信任模型状态</span><span class="sxs-lookup"><span data-stu-id="57cd6-254">Trust Model Status</span></span> |<span data-ttu-id="57cd6-255">未检测到信任模型问题。</span><span class="sxs-lookup"><span data-stu-id="57cd6-255">No Trust Model Issue Detected.</span></span> |<span data-ttu-id="57cd6-256">SIP 域和服务器域不同，请添加以下域。</span><span class="sxs-lookup"><span data-stu-id="57cd6-256">SIP Domain and server domain are different please add the following domains.</span></span> |<span data-ttu-id="57cd6-257">检查 LD FQDN/ LD 服务器名称/池服务器名称，了解信任模型问题。</span><span class="sxs-lookup"><span data-stu-id="57cd6-257">Check the LD FQDN/ LD Server Name/ Pool Server name for Trust model issue.</span></span> 
<span data-ttu-id="57cd6-258">域名 (域名) </span><span class="sxs-lookup"><span data-stu-id="57cd6-258">Domain Name(s)</span></span> | | |<span data-ttu-id="57cd6-259">返回应该为 SFB 进行连接的域列表。</span><span class="sxs-lookup"><span data-stu-id="57cd6-259">Return the list of domains that should be added for SFB to connect.</span></span> |

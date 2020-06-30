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
ms.openlocfilehash: 127be0a5f320418d8a1086aec3de62e3ef54e42a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830833"
---
# <span data-ttu-id="fc386-104">使用 Surface Hub 硬件诊断工具测试设备帐户</span><span class="sxs-lookup"><span data-stu-id="fc386-104">Using the Surface Hub Hardware Diagnostic Tool to test a device account</span></span>

## <span data-ttu-id="fc386-105">简介</span><span class="sxs-lookup"><span data-stu-id="fc386-105">Introduction</span></span>

> [!NOTE]
> <span data-ttu-id="fc386-106">Surface Hub 硬件诊断工具的 "帐户设置" 部分不会收集任何信息。</span><span class="sxs-lookup"><span data-stu-id="fc386-106">The "Account Settings" section of the Surface Hub Hardware Diagnostic tool doesn’t collect any information.</span></span> <span data-ttu-id="fc386-107">输入的电子邮件和密码仅直接在你的环境中使用，不会收集或转移给任何人。</span><span class="sxs-lookup"><span data-stu-id="fc386-107">The email and password that are entered as input are used only directly on your environment and not collected or transferred to anyone.</span></span> <span data-ttu-id="fc386-108">只有在关闭应用程序或结束 Surface Hub 上的当前会话之前，登录信息才会保持。</span><span class="sxs-lookup"><span data-stu-id="fc386-108">The login information persists only until the application is closed or you end the current session on the Surface Hub.</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="fc386-109">运行此应用程序不需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="fc386-109">Administrator privileges are not required to run this application.</span></span>
> * <span data-ttu-id="fc386-110">在使用 Microsoft 打开服务呼叫之前，应与本地管理员讨论诊断结果。</span><span class="sxs-lookup"><span data-stu-id="fc386-110">The results of the diagnostic should be discussed with your local administrator before you open a service call with Microsoft.</span></span>

### <span data-ttu-id="fc386-111">Surface Hub 硬件诊断</span><span class="sxs-lookup"><span data-stu-id="fc386-111">Surface Hub Hardware Diagnostic</span></span>

<span data-ttu-id="fc386-112">默认情况下，Surface hub 系统的早期版本中不会安装[Surface Hub 硬件诊断](https://www.microsoft.com/store/apps/9nblggh51f2g)应用程序。</span><span class="sxs-lookup"><span data-stu-id="fc386-112">By default, the [Surface Hub Hardware Diagnostic](https://www.microsoft.com/store/apps/9nblggh51f2g) application isn’t installed in earlier versions of the Surface Hub system.</span></span> <span data-ttu-id="fc386-113">可从 Microsoft Store 免费获取该应用程序。</span><span class="sxs-lookup"><span data-stu-id="fc386-113">The application is available for free from the Microsoft Store.</span></span> <span data-ttu-id="fc386-114">安装应用程序需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="fc386-114">Administrator privileges are required to install the application.</span></span>

   ![硬件诊断的屏幕截图](images/01-diagnostic.png)

## <span data-ttu-id="fc386-116">关于 Surface Hub 硬件诊断工具</span><span class="sxs-lookup"><span data-stu-id="fc386-116">About the Surface Hub Hardware Diagnostic Tool</span></span>

<span data-ttu-id="fc386-117">Surface Hub 硬件诊断工具是一种易于导航的工具，可让用户在 Surface Hub 设备中测试许多硬件组件。</span><span class="sxs-lookup"><span data-stu-id="fc386-117">The Surface Hub Hardware Diagnostic tool is an easy-to-navigate tool that lets the user test many of the hardware components within the Surface Hub device.</span></span> <span data-ttu-id="fc386-118">此工具还可测试和验证 Surface Hub 设备帐户。</span><span class="sxs-lookup"><span data-stu-id="fc386-118">This tool can also test and verify a Surface Hub device account.</span></span> <span data-ttu-id="fc386-119">本文介绍如何使用 Surface Hub 硬件诊断工具中的 "帐户设置" 测试。</span><span class="sxs-lookup"><span data-stu-id="fc386-119">This article describes how to use the Account Settings test within the Surface Hub Hardware Diagnostic tool.</span></span>

> [!NOTE]
> <span data-ttu-id="fc386-120">在完成任何测试之前，应创建 Surface Hub 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="fc386-120">The device account for the Surface Hub should be created before any testing is done.</span></span> <span data-ttu-id="fc386-121">Surface Hub 管理员指南提供说明和 PowerShell 脚本，可帮助你创建本地、联机（Office365）或混合设备帐户。</span><span class="sxs-lookup"><span data-stu-id="fc386-121">The Surface Hub Administrator Guide provides instructions and PowerShell scripts to help you create on-premises, online (Office365), or hybrid device accounts.</span></span> <span data-ttu-id="fc386-122">有关详细信息，请转到指南中的 "[创建和测试设备帐户（Surface Hub）](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) " 主题。</span><span class="sxs-lookup"><span data-stu-id="fc386-122">For more information, go to the [Create and test a device account (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) topic in the guide.</span></span>

### <span data-ttu-id="fc386-123">设备帐户测试过程</span><span class="sxs-lookup"><span data-stu-id="fc386-123">Device account testing process</span></span>

1. <span data-ttu-id="fc386-124">导航到 "**所有应用**"，然后找到 Surface Hub 硬件诊断应用程序。</span><span class="sxs-lookup"><span data-stu-id="fc386-124">Navigate to **All Apps**, and then locate the Surface Hub Hardware Diagnostic application.</span></span>

    ![所有应用的屏幕截图](images/02-all-apps.png)

1. <span data-ttu-id="fc386-126">当应用程序启动时，"**欢迎**" 页面提供一个文本窗口，用于记录测试中心的原因。</span><span class="sxs-lookup"><span data-stu-id="fc386-126">When the application starts, the **Welcome** page provides a text window to document the reason why you are testing the Hub.</span></span> <span data-ttu-id="fc386-127">在测试结束时，可以将此笔记与诊断结果一起保存到 USB。</span><span class="sxs-lookup"><span data-stu-id="fc386-127">This note can be saved to USB together with the diagnostic results at the conclusion of testing.</span></span> <span data-ttu-id="fc386-128">完成笔记的输入后，选择 "**继续**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="fc386-128">After you finish entering a note, select the **Continue** button.</span></span>

    ![欢迎屏幕截图](images/03-welcome.png)

1. <span data-ttu-id="fc386-130">下一个屏幕提供了测试所有或部分 Surface Hub 组件的选项。</span><span class="sxs-lookup"><span data-stu-id="fc386-130">The next screen provides you the option to test all or some of the Surface Hub components.</span></span> <span data-ttu-id="fc386-131">若要开始测试设备帐户，请选择 "**测试结果**" 图标。</span><span class="sxs-lookup"><span data-stu-id="fc386-131">To begin testing the device account, select the **Test Results** icon.</span></span>

    ![测试结果的屏幕截图](images/04-test-results-1.png)

    ![测试结果的屏幕截图](images/05-test-results-2.png)

1. <span data-ttu-id="fc386-134">选择 "**帐户设置**"。</span><span class="sxs-lookup"><span data-stu-id="fc386-134">Select **Account Settings**.</span></span>  

    ![帐户设置的屏幕截图](images/06-account-settings.png)

    <span data-ttu-id="fc386-136">"帐户设置" 屏幕用于测试你的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="fc386-136">The Account Settings screen is used to test your device account.</span></span>

    ![帐户设置详细信息的屏幕截图](images/07-account-settings-details.png)

1. <span data-ttu-id="fc386-138">输入设备帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fc386-138">Enter the email address of your device account.</span></span> <span data-ttu-id="fc386-139">密码是可选的，但建议使用。</span><span class="sxs-lookup"><span data-stu-id="fc386-139">The password is optional but is recommended.</span></span> <span data-ttu-id="fc386-140">准备好继续时，请选择 "**测试帐户**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="fc386-140">Select the **Test Account** button when you are ready to continue.</span></span>

    ![测试帐户的屏幕截图](images/08-test-account.png)

1. <span data-ttu-id="fc386-142">测试完成后，请查看四个测试区域的结果。</span><span class="sxs-lookup"><span data-stu-id="fc386-142">After testing is finished, review the results for the four areas of testing.</span></span> <span data-ttu-id="fc386-143">每个部分都可以通过选择每个主题旁边的加号或减号来展开或折叠。</span><span class="sxs-lookup"><span data-stu-id="fc386-143">Each section can be expanded or collapsed by selecting the Plus or Minus sign next to each topic.</span></span>

    **<span data-ttu-id="fc386-144">Network</span><span class="sxs-lookup"><span data-stu-id="fc386-144">Network</span></span>**

    ![网络的屏幕截图](images/09-network.png)

    **<span data-ttu-id="fc386-146">环境</span><span class="sxs-lookup"><span data-stu-id="fc386-146">Environment</span></span>**

    ![环境的屏幕截图](images/10-environment.png)

    **<span data-ttu-id="fc386-148">证书</span><span class="sxs-lookup"><span data-stu-id="fc386-148">Certificates</span></span>**

    ![证书的屏幕截图](images/11-certificates.png)

    **<span data-ttu-id="fc386-150">信任模型</span><span class="sxs-lookup"><span data-stu-id="fc386-150">Trust Model</span></span>**

    ![信任模型的屏幕截图](images/12-trust-model.png)

## <span data-ttu-id="fc386-152">附录</span><span class="sxs-lookup"><span data-stu-id="fc386-152">Appendix</span></span>

### <span data-ttu-id="fc386-153">域消息和解决方案</span><span class="sxs-lookup"><span data-stu-id="fc386-153">Field messages and resolution</span></span>

#### <span data-ttu-id="fc386-154">Network</span><span class="sxs-lookup"><span data-stu-id="fc386-154">Network</span></span>

<span data-ttu-id="fc386-155">字段</span><span class="sxs-lookup"><span data-stu-id="fc386-155">Field</span></span> |<span data-ttu-id="fc386-156">成功</span><span class="sxs-lookup"><span data-stu-id="fc386-156">Success</span></span> |<span data-ttu-id="fc386-157">失败</span><span class="sxs-lookup"><span data-stu-id="fc386-157">Failure</span></span> |<span data-ttu-id="fc386-158">评论</span><span class="sxs-lookup"><span data-stu-id="fc386-158">Comment</span></span> |<span data-ttu-id="fc386-159">参考</span><span class="sxs-lookup"><span data-stu-id="fc386-159">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="fc386-160">互联网连接</span><span class="sxs-lookup"><span data-stu-id="fc386-160">Internet Connectivity</span></span> |<span data-ttu-id="fc386-161">设备有互联网连接</span><span class="sxs-lookup"><span data-stu-id="fc386-161">Device does have Internet connectivity</span></span> |<span data-ttu-id="fc386-162">设备没有互联网连接</span><span class="sxs-lookup"><span data-stu-id="fc386-162">Device does not have Internet connectivity</span></span> |<span data-ttu-id="fc386-163">验证 internet 连接，包括代理连接</span><span class="sxs-lookup"><span data-stu-id="fc386-163">Verifies internet connectivity, including proxy connection</span></span> |
<span data-ttu-id="fc386-164">HTTP 版本</span><span class="sxs-lookup"><span data-stu-id="fc386-164">HTTP Version</span></span> |<span data-ttu-id="fc386-165">1.1</span><span class="sxs-lookup"><span data-stu-id="fc386-165">1.1</span></span> |<span data-ttu-id="fc386-166">1.0</span><span class="sxs-lookup"><span data-stu-id="fc386-166">1.0</span></span> |<span data-ttu-id="fc386-167">如果发现 HTTP 1.0，将导致 WU 和应用商店出现问题</span><span class="sxs-lookup"><span data-stu-id="fc386-167">If HTTP 1.0 found, it will cause issue with WU and Store</span></span> |
<span data-ttu-id="fc386-168">直接互联网连接</span><span class="sxs-lookup"><span data-stu-id="fc386-168">Direct Internet Connectivity</span></span> |<span data-ttu-id="fc386-169">设备配置的代理设备没有配置代理</span><span class="sxs-lookup"><span data-stu-id="fc386-169">Device has a Proxy configured Device has no Proxy configured</span></span> |<span data-ttu-id="fc386-170">不适用</span><span class="sxs-lookup"><span data-stu-id="fc386-170">N/A</span></span> |<span data-ttu-id="fc386-171">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-171">Informational.</span></span> <span data-ttu-id="fc386-172">您的设备是否位于代理后？</span><span class="sxs-lookup"><span data-stu-id="fc386-172">Is your device behind a proxy?</span></span> |
<span data-ttu-id="fc386-173">代理地址</span><span class="sxs-lookup"><span data-stu-id="fc386-173">Proxy Address</span></span> | | |<span data-ttu-id="fc386-174">如果已配置，则返回代理地址。</span><span class="sxs-lookup"><span data-stu-id="fc386-174">If configured, returns proxy address.</span></span> |
<span data-ttu-id="fc386-175">代理身份验证</span><span class="sxs-lookup"><span data-stu-id="fc386-175">Proxy Authentication</span></span> |<span data-ttu-id="fc386-176">代理不需要身份验证</span><span class="sxs-lookup"><span data-stu-id="fc386-176">Proxy does not require Authentication</span></span> |<span data-ttu-id="fc386-177">代理服务器需要代理身份验证</span><span class="sxs-lookup"><span data-stu-id="fc386-177">Proxy requires Proxy Auth</span></span> |<span data-ttu-id="fc386-178">如果用户已在 Edge 中打开了一个会话，并且通过代理进行了身份验证，则结果可能为假正值。</span><span class="sxs-lookup"><span data-stu-id="fc386-178">Result may be a false positive if a user already has an open session in Edge and has authenticated through the proxy.</span></span> |
<span data-ttu-id="fc386-179">代理身份验证类型</span><span class="sxs-lookup"><span data-stu-id="fc386-179">Proxy Auth Types</span></span> | | |<span data-ttu-id="fc386-180">如果使用代理身份验证，则返回由代理播发的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="fc386-180">If proxy authentication is used, return the Authentication methods advertised by the proxy.</span></span>  |

#### <span data-ttu-id="fc386-181">环境</span><span class="sxs-lookup"><span data-stu-id="fc386-181">Environment</span></span>

<span data-ttu-id="fc386-182">字段</span><span class="sxs-lookup"><span data-stu-id="fc386-182">Field</span></span> |<span data-ttu-id="fc386-183">成功</span><span class="sxs-lookup"><span data-stu-id="fc386-183">Success</span></span> |<span data-ttu-id="fc386-184">失败</span><span class="sxs-lookup"><span data-stu-id="fc386-184">Failure</span></span> |<span data-ttu-id="fc386-185">评论</span><span class="sxs-lookup"><span data-stu-id="fc386-185">Comment</span></span> |<span data-ttu-id="fc386-186">参考</span><span class="sxs-lookup"><span data-stu-id="fc386-186">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="fc386-187">SIP 域</span><span class="sxs-lookup"><span data-stu-id="fc386-187">SIP Domain</span></span> | | |<span data-ttu-id="fc386-188">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-188">Informational.</span></span>  |
<span data-ttu-id="fc386-189">Skype 环境</span><span class="sxs-lookup"><span data-stu-id="fc386-189">Skype Environment</span></span> |<span data-ttu-id="fc386-190">Skype for business Online，Skype for business 本地，Skype for business 混合</span><span class="sxs-lookup"><span data-stu-id="fc386-190">Skype for Business Online, Skype for Business OnPrem, Skype for Business Hybrid</span></span> |<span data-ttu-id="fc386-191">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-191">Informational.</span></span> |<span data-ttu-id="fc386-192">检测到何种类型的环境。</span><span class="sxs-lookup"><span data-stu-id="fc386-192">What type of environment was detected.</span></span> <span data-ttu-id="fc386-193">注意：只有在输入密码时才能检测混合。</span><span class="sxs-lookup"><span data-stu-id="fc386-193">Note: Hybrid can only be detected if the password is entered.</span></span>
<span data-ttu-id="fc386-194">LyncDiscover FQDN</span><span class="sxs-lookup"><span data-stu-id="fc386-194">LyncDiscover FQDN</span></span> | | |<span data-ttu-id="fc386-195">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-195">Informational.</span></span> <span data-ttu-id="fc386-196">显示 LyncDiscover DNS 结果</span><span class="sxs-lookup"><span data-stu-id="fc386-196">Displays the LyncDiscover DNS result</span></span> |
<span data-ttu-id="fc386-197">LyncDiscover URI</span><span class="sxs-lookup"><span data-stu-id="fc386-197">LyncDiscover URI</span></span> | | |<span data-ttu-id="fc386-198">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-198">Informational.</span></span> <span data-ttu-id="fc386-199">显示用于在你的环境上执行 LyncDiscover 的 URL。</span><span class="sxs-lookup"><span data-stu-id="fc386-199">Displays the URL used to perform a LyncDiscover on your environment.</span></span>|
<span data-ttu-id="fc386-200">LyncDiscover</span><span class="sxs-lookup"><span data-stu-id="fc386-200">LyncDiscover</span></span> |<span data-ttu-id="fc386-201">连接成功</span><span class="sxs-lookup"><span data-stu-id="fc386-201">Connection Successful</span></span> |<span data-ttu-id="fc386-202">连接失败</span><span class="sxs-lookup"><span data-stu-id="fc386-202">Connection Failed</span></span> |<span data-ttu-id="fc386-203">来自 LyncDiscover web 服务的响应。</span><span class="sxs-lookup"><span data-stu-id="fc386-203">Response from LyncDiscover web service.</span></span> |
<span data-ttu-id="fc386-204">SIP 池主机名</span><span class="sxs-lookup"><span data-stu-id="fc386-204">SIP Pool Hostname</span></span> | | |<span data-ttu-id="fc386-205">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-205">Informational.</span></span> <span data-ttu-id="fc386-206">显示从 LyncDiscover 发现的 SIP 池名称</span><span class="sxs-lookup"><span data-stu-id="fc386-206">Display the SIP pool name discovered from LyncDiscover</span></span> |

#### <span data-ttu-id="fc386-207">证书（仅限本地混合）</span><span class="sxs-lookup"><span data-stu-id="fc386-207">Certificates (in-premises hybrid only)</span></span>

<span data-ttu-id="fc386-208">LyncDiscover 证书</span><span class="sxs-lookup"><span data-stu-id="fc386-208">LyncDiscover Certificate</span></span>

<span data-ttu-id="fc386-209">字段</span><span class="sxs-lookup"><span data-stu-id="fc386-209">Field</span></span> |<span data-ttu-id="fc386-210">成功</span><span class="sxs-lookup"><span data-stu-id="fc386-210">Success</span></span> |<span data-ttu-id="fc386-211">失败</span><span class="sxs-lookup"><span data-stu-id="fc386-211">Failure</span></span> |<span data-ttu-id="fc386-212">评论</span><span class="sxs-lookup"><span data-stu-id="fc386-212">Comment</span></span> |<span data-ttu-id="fc386-213">参考</span><span class="sxs-lookup"><span data-stu-id="fc386-213">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="fc386-214">LyncDiscover Cert CN</span><span class="sxs-lookup"><span data-stu-id="fc386-214">LyncDiscover Cert CN</span></span> | | |<span data-ttu-id="fc386-215">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-215">Informational.</span></span> <span data-ttu-id="fc386-216">显示 LD 证书公用名</span><span class="sxs-lookup"><span data-stu-id="fc386-216">Displays the LD cert Common name</span></span> |
<span data-ttu-id="fc386-217">LyncDiscover Cert CA</span><span class="sxs-lookup"><span data-stu-id="fc386-217">LyncDiscover Cert CA</span></span> | | |<span data-ttu-id="fc386-218">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-218">Informational.</span></span> <span data-ttu-id="fc386-219">显示 LD 证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="fc386-219">Displays the LD Cert CA</span></span> |
<span data-ttu-id="fc386-220">LyncDiscover 证书根 CA</span><span class="sxs-lookup"><span data-stu-id="fc386-220">LyncDiscover Cert Root CA</span></span> | | |<span data-ttu-id="fc386-221">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-221">Informational.</span></span> <span data-ttu-id="fc386-222">显示 LD 证书根 CA （如果可用）。</span><span class="sxs-lookup"><span data-stu-id="fc386-222">Displays the LD Cert Root CA, if available.</span></span> |
<span data-ttu-id="fc386-223">LD 信任状态</span><span class="sxs-lookup"><span data-stu-id="fc386-223">LD Trust Status</span></span> |<span data-ttu-id="fc386-224">证书受信任。</span><span class="sxs-lookup"><span data-stu-id="fc386-224">Certificate is Trusted.</span></span> |<span data-ttu-id="fc386-225">证书不受信任，请添加根 CA。</span><span class="sxs-lookup"><span data-stu-id="fc386-225">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="fc386-226">根据本地证书存储验证证书。</span><span class="sxs-lookup"><span data-stu-id="fc386-226">Verify the certificate against the local cert store.</span></span> <span data-ttu-id="fc386-227">如果计算机信任证书，则返回正值。</span><span class="sxs-lookup"><span data-stu-id="fc386-227">Returns positive if the machine trusts the certificate.</span></span>|<span data-ttu-id="fc386-228">[使用 PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / 下载和部署 Skype for business 证书[Surface Hub 预配程序包支持的项目](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="fc386-228">[Download and deploy Skype for Business certificates using PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/)/[Supported items for Surface Hub provisioning packages](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span></span>

<span data-ttu-id="fc386-229">SIP 池认证</span><span class="sxs-lookup"><span data-stu-id="fc386-229">SIP Pool Certification</span></span>

<span data-ttu-id="fc386-230">字段</span><span class="sxs-lookup"><span data-stu-id="fc386-230">Field</span></span> |<span data-ttu-id="fc386-231">成功</span><span class="sxs-lookup"><span data-stu-id="fc386-231">Success</span></span> |<span data-ttu-id="fc386-232">失败</span><span class="sxs-lookup"><span data-stu-id="fc386-232">Failure</span></span> |<span data-ttu-id="fc386-233">评论</span><span class="sxs-lookup"><span data-stu-id="fc386-233">Comment</span></span> |<span data-ttu-id="fc386-234">参考</span><span class="sxs-lookup"><span data-stu-id="fc386-234">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="fc386-235">SIP 池证书 CN</span><span class="sxs-lookup"><span data-stu-id="fc386-235">SIP Pool Cert CN</span></span> | | |<span data-ttu-id="fc386-236">内容</span><span class="sxs-lookup"><span data-stu-id="fc386-236">(CONTENTS)</span></span> |
<span data-ttu-id="fc386-237">SIP 池证书 CA</span><span class="sxs-lookup"><span data-stu-id="fc386-237">SIP Pool Cert CA</span></span> | | |<span data-ttu-id="fc386-238">内容</span><span class="sxs-lookup"><span data-stu-id="fc386-238">(CONTENTS)</span></span> |
<span data-ttu-id="fc386-239">SIP 池信任状态</span><span class="sxs-lookup"><span data-stu-id="fc386-239">SIP Pool Trust Status</span></span> |<span data-ttu-id="fc386-240">证书受信任。</span><span class="sxs-lookup"><span data-stu-id="fc386-240">Certificate is Trusted.</span></span> |<span data-ttu-id="fc386-241">证书不受信任，请添加根 CA。</span><span class="sxs-lookup"><span data-stu-id="fc386-241">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="fc386-242">验证证书是否针对本地证书存储，如果设备信任证书，则返回正值。</span><span class="sxs-lookup"><span data-stu-id="fc386-242">Verify the certificate against the local cert store and return a positive if the devices trusts the certificate.</span></span> |
<span data-ttu-id="fc386-243">SIP 池证书根 CA</span><span class="sxs-lookup"><span data-stu-id="fc386-243">SIP Pool Cert Root CA</span></span> | | |<span data-ttu-id="fc386-244">信息.</span><span class="sxs-lookup"><span data-stu-id="fc386-244">Information.</span></span> <span data-ttu-id="fc386-245">显示 SIP 池证书根 CA （如果可用）。</span><span class="sxs-lookup"><span data-stu-id="fc386-245">Display the SIP Pool Cert Root CA, if available.</span></span> |

#### <span data-ttu-id="fc386-246">信任模型（仅限本地混合）</span><span class="sxs-lookup"><span data-stu-id="fc386-246">Trust Model (on-premises hybrid only)</span></span>

<span data-ttu-id="fc386-247">字段</span><span class="sxs-lookup"><span data-stu-id="fc386-247">Field</span></span> |<span data-ttu-id="fc386-248">成功</span><span class="sxs-lookup"><span data-stu-id="fc386-248">Success</span></span> |<span data-ttu-id="fc386-249">失败</span><span class="sxs-lookup"><span data-stu-id="fc386-249">Failure</span></span> |<span data-ttu-id="fc386-250">评论</span><span class="sxs-lookup"><span data-stu-id="fc386-250">Comment</span></span> |<span data-ttu-id="fc386-251">参考</span><span class="sxs-lookup"><span data-stu-id="fc386-251">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="fc386-252">信任模型状态</span><span class="sxs-lookup"><span data-stu-id="fc386-252">Trust Model Status</span></span> |<span data-ttu-id="fc386-253">未检测到信任模型问题。</span><span class="sxs-lookup"><span data-stu-id="fc386-253">No Trust Model Issue Detected.</span></span> |<span data-ttu-id="fc386-254">SIP 域和服务器域不同请添加以下域。</span><span class="sxs-lookup"><span data-stu-id="fc386-254">SIP Domain and server domain are different please add the following domains.</span></span> |<span data-ttu-id="fc386-255">检查 "LD FQDN/LD 服务器名称/池服务器名称是否有信任模型问题。</span><span class="sxs-lookup"><span data-stu-id="fc386-255">Check the LD FQDN/ LD Server Name/ Pool Server name for Trust model issue.</span></span> 
<span data-ttu-id="fc386-256">域名</span><span class="sxs-lookup"><span data-stu-id="fc386-256">Domain Name(s)</span></span> | | |<span data-ttu-id="fc386-257">返回应添加到 SFB 的域的列表以进行连接。</span><span class="sxs-lookup"><span data-stu-id="fc386-257">Return the list of domains that should be added for SFB to connect.</span></span> |

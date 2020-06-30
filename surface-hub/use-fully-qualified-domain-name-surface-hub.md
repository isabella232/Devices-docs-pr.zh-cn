---
title: 将完全限定的域名用于 Surface Hub
description: 常见问题疑难解答，包括设置问题和 Exchange ActiveSync 错误。
keywords:
- 常见问题疑难解答
- 设置问题
- Exchange ActiveSync 错误
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830825"
---
# <span data-ttu-id="1c62b-106">为 Skype for Business 配置域名</span><span class="sxs-lookup"><span data-stu-id="1c62b-106">Configure domain name for Skype for Business</span></span>

<span data-ttu-id="1c62b-107">在以下方案中需要指定 Skype for Business 服务器的域名：</span><span class="sxs-lookup"><span data-stu-id="1c62b-107">There are a few scenarios where you need to specify the domain name of your Skype for Business server:</span></span>
- <span data-ttu-id="1c62b-108">**多个 DNS 后缀** - 当 Skype for Business 基础结构具有非连续命名空间时，会使得一个或多个服务器具有与 Skype for Business (SIP) 登录地址后缀不匹配的 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="1c62b-108">**Multiple DNS suffixes** - When your Skype for Business infrastructure has disjointed namespaces such that one or more servers have a DNS suffix that doesn't match the suffix of the sign-in address (SIP) for Skype for Business.</span></span>  
- <span data-ttu-id="1c62b-109">**Skype for Business 和 Exchange 后缀不同** - 当 Skype for Business 登录地址的后缀与用于设备帐户的 Exchange 地址后缀不同时。</span><span class="sxs-lookup"><span data-stu-id="1c62b-109">**Skype for Business and Exchange suffixes are different** - When the suffix of the sign-in address for Skype for Business differs from the suffix of the Exchange address used for the device account.</span></span>
- <span data-ttu-id="1c62b-110">使用**证书**-具有本地 Skype for business 服务器的大型组织通常会将证书与自己的根证书颁发机构（CA）结合使用。</span><span class="sxs-lookup"><span data-stu-id="1c62b-110">**Working with certificates** - Large organizations with on-premises Skype for Business servers commonly use certificates with their own root certificate authority (CA).</span></span> <span data-ttu-id="1c62b-111">CA 域不同于 Skype for Business 服务器的域很常见，这会导致证书不受信任以及登录失败。</span><span class="sxs-lookup"><span data-stu-id="1c62b-111">It is common for the CA domain to be different than the domain of the Skype for Business server which causes the certificate to not be trusted, and sign-in fails.</span></span>  <span data-ttu-id="1c62b-112">Skype 需要了解证书的域名，以便建立信任关系。</span><span class="sxs-lookup"><span data-stu-id="1c62b-112">Skype needs to know the domain name of the certificate in order to set up a trust relationship.</span></span> <span data-ttu-id="1c62b-113">企业通常使用组策略来将其推送至 Skype 桌面，但组策略在 Surface Hub 上不受支持。</span><span class="sxs-lookup"><span data-stu-id="1c62b-113">Enterprises typically use Group Policy to push this out to Skype desktop, but Group Policy is not supported on Surface Hub.</span></span>

**<span data-ttu-id="1c62b-114">为 Skype for Business Server 配置域名</span><span class="sxs-lookup"><span data-stu-id="1c62b-114">To configure the domain name for your Skype for Business server</span></span>**</br>
1. <span data-ttu-id="1c62b-115">在 Surface Hub 上，打开**设置**。</span><span class="sxs-lookup"><span data-stu-id="1c62b-115">On Surface Hub, open **Settings**.</span></span>
2. <span data-ttu-id="1c62b-116">依次单击 **Surface Hub**、**通话和音频**。</span><span class="sxs-lookup"><span data-stu-id="1c62b-116">Click **Surface Hub**, and then click **Calling & Audio**.</span></span> 
3. <span data-ttu-id="1c62b-117">在 **Skype for Business 配置**下，单击**配置域名**。</span><span class="sxs-lookup"><span data-stu-id="1c62b-117">Under **Skype for Business configuration**, click **Configure domain name**.</span></span> 
4. <span data-ttu-id="1c62b-118">为 Skype for Business 服务器键入域名，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1c62b-118">Type the domain name for your Skype for Business server, and then click **Ok**.</span></span> 
   > [!TIP]
   > <span data-ttu-id="1c62b-119">可键入多个域名，用逗号分开。</span><span class="sxs-lookup"><span data-stu-id="1c62b-119">You can type multiple domain names, separated by commas.</span></span> <br> <span data-ttu-id="1c62b-120">例如：lync.com、outlook.com、lync.glbdns.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1c62b-120">For example: lync.com, outlook.com, lync.glbdns.microsoft.com</span></span>

    ![将 Skype for Business FQDN 添加到设置](images/system-settings-add-fqdn.png)

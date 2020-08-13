---
title: 已知问题和有关 Microsoft Surface Hub 的其他信息
description: 概括介绍 Microsoft Surface Hub 的已知问题。
ms.assetid: aee90a0c-fb05-466e-a2b1-92de89d0f2b7
keywords: surface、hub、问题
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: v-todmc
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: f9b658daa4b398fda442976b7bce2f560a1b39f6
ms.sourcegitcommit: 16845b3289a035b4e6ab5e7536307ef66651db28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926264"
---
# <span data-ttu-id="96eca-104">已知问题和有关 Microsoft Surface Hub 的其他信息</span><span class="sxs-lookup"><span data-stu-id="96eca-104">Known issues and additional information about Microsoft Surface Hub</span></span>

<span data-ttu-id="96eca-105">我们正在倾听。</span><span class="sxs-lookup"><span data-stu-id="96eca-105">We're listening.</span></span> <span data-ttu-id="96eca-106">质量是头等大事，我们希望及时了解影响客户的问题。</span><span class="sxs-lookup"><span data-stu-id="96eca-106">Quality is a top priority, and we want to keep you informed about issues impacting customers.</span></span> <span data-ttu-id="96eca-107">以下是 Microsoft Surface Hub 的一些已知问题：</span><span class="sxs-lookup"><span data-stu-id="96eca-107">The following are some known issues of Microsoft Surface Hub:</span></span>

- **<span data-ttu-id="96eca-108">Skype for Business 未将用于媒体流量的代理与 RS2 配合使用</span><span class="sxs-lookup"><span data-stu-id="96eca-108">Skype for Business isn't using proxy for media traffic with RS2</span></span>**
<br/><span data-ttu-id="96eca-109">对于位于代理后面的某些 Surface Hub 用户，Skype for Business 不会使用代理服务器进行媒体。</span><span class="sxs-lookup"><span data-stu-id="96eca-109">For some Surface Hub users who are behind a proxy, Skype for Business won't use the proxy server for media.</span></span> <span data-ttu-id="96eca-110">但是，Surface Hub 将能够登录到该帐户。</span><span class="sxs-lookup"><span data-stu-id="96eca-110">However, the Surface Hub will be able to sign in to the account.</span></span> <span data-ttu-id="96eca-111">我们收到您的反馈意见，并注意使用代理时的媒体流量问题。</span><span class="sxs-lookup"><span data-stu-id="96eca-111">We received your feedback and are aware of the media traffic issue when you are using proxy.</span></span> <span data-ttu-id="96eca-112">我们正在积极调查此问题，一旦发现并测试了解决方案，将立即发布修补程序。</span><span class="sxs-lookup"><span data-stu-id="96eca-112">We're actively investigating this issue and will release fixes as soon as a solution is identified and tested.</span></span> 

- **<span data-ttu-id="96eca-113">对于 AAD 加入的设备，当用户尝试登录到 "我的会议 & 文件" 时，Surface Hub 报告没有 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="96eca-113">For AAD joined devices, when a user tries to sign in to "My meetings & files", Surface Hub reports that there is no Internet connection</span></span>**
<br/><span data-ttu-id="96eca-114">我们将注意到一组影响 Surface Hub 上的登录和文档访问的问题。</span><span class="sxs-lookup"><span data-stu-id="96eca-114">We’re aware of a set of issues that affect sign-in and document access on Surface Hub.</span></span> <span data-ttu-id="96eca-115">我们正在积极调查这些问题。</span><span class="sxs-lookup"><span data-stu-id="96eca-115">We're actively investigating these issues.</span></span> <span data-ttu-id="96eca-116">作为解决方法，客户可以重置其设备并将其中心设置为使用本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="96eca-116">As a workaround until a resolution is released, customers can reset their devices and set up their Hub to use a local admin account.</span></span> <span data-ttu-id="96eca-117">重新配置以使用本地管理员帐户后，"我的会议和文件" 将按预期工作。</span><span class="sxs-lookup"><span data-stu-id="96eca-117">After reconfiguring to use the local admin account, "My meetings and files" will work as expected.</span></span>
- **<span data-ttu-id="96eca-118">Azure AD 加入时的单一登录</span><span class="sxs-lookup"><span data-stu-id="96eca-118">Single sign-in when Azure AD joined</span></span>**
<br/><span data-ttu-id="96eca-119">Surface Hub 设计用于群体空间，这会影响用户凭据的存储方式。</span><span class="sxs-lookup"><span data-stu-id="96eca-119">Surface Hub was designed for communal spaces, which impacts the way user credentials are stored.</span></span> <span data-ttu-id="96eca-120">因此，在设备已加入 Azure AD 时，单一登录的工作方式目前有一些限制。</span><span class="sxs-lookup"><span data-stu-id="96eca-120">Because of this, there are currently limitations in how single sign-in works when devices are Azure AD joined.</span></span> <span data-ttu-id="96eca-121">Microsoft 已注意到这种限制，正在积极调查解决方案的选项。</span><span class="sxs-lookup"><span data-stu-id="96eca-121">Microsoft is aware of this limitation and is actively investigating options for a resolution.</span></span>
- **<span data-ttu-id="96eca-122">如果 Surface Hub 在 "友好名称" 中有一个点字符 ( ) ，则通过基础结构投影到 Surface Hub 的 Miracast 将失败。</span><span class="sxs-lookup"><span data-stu-id="96eca-122">Miracast over Infrastructure projection to Surface Hub fails if the Surface Hub has a dot character (.) in the friendly name</span></span>**
<br/><span data-ttu-id="96eca-123">如果友好名称在 )  ( 名称中包含句点或点（如 "Room42"），Surface Hub 用户可能会遇到对其设备进行投影的问题。</span><span class="sxs-lookup"><span data-stu-id="96eca-123">Surface Hub users may experience issues projecting to their device if the Friendly Name includes a period or dot in the name (.) -- for example, "Conf.Room42".</span></span> <span data-ttu-id="96eca-124">若要解决此问题，请在 "**设置**Surface Hub" 中更改中心的友好名称  >  **Surface Hub**  >  **About**，然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="96eca-124">To work around the issue, change the Friendly Name of the Hub in **Settings** > **Surface Hub** > **About**, and then restart the device.</span></span> <span data-ttu-id="96eca-125">Microsoft 正在处理此问题的解决方案。</span><span class="sxs-lookup"><span data-stu-id="96eca-125">Microsoft is working on a solution to this issue.</span></span>
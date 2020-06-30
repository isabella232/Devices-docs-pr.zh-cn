---
title: 已知问题和有关 Microsoft Surface Hub 的其他信息
description: 概括介绍 Microsoft Surface Hub 的已知问题。
ms.assetid: aee90a0c-fb05-466e-a2b1-92de89d0f2b7
keywords: surface、hub、问题
ms.prod: surface-hub
ms.sitesec: library
author: todmccoy
ms.author: v-todmc
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: ec6746098203b5e91e2aaf3b044d21b81c31c897
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830970"
---
# 已知问题和有关 Microsoft Surface Hub 的其他信息

我们正在倾听。 质量是头等大事，我们希望及时了解影响客户的问题。 以下是 Microsoft Surface Hub 的一些已知问题：

- **Skype for Business 未将用于媒体流量的代理与 RS2 配合使用**
<br/>对于位于代理后面的某些 Surface Hub 用户，Skype for Business 不会使用代理服务器进行媒体。 但是，Surface Hub 将能够登录到该帐户。 我们收到您的反馈意见，并注意使用代理时的媒体流量问题。 我们正在积极调查此问题，一旦发现并测试了解决方案，将立即发布修补程序。 

- **对于 AAD 加入的设备，当用户尝试登录到 "我的会议 & 文件" 时，Surface Hub 报告没有 Internet 连接**
<br/>我们将注意到一组影响 Surface Hub 上的登录和文档访问的问题。 我们正在积极调查这些问题。 作为解决方法，客户可以重置其设备并将其中心设置为使用本地管理员帐户。 重新配置以使用本地管理员帐户后，"我的会议和文件" 将按预期工作。
- **Azure AD 加入时的单一登录**
<br/>Surface Hub 设计用于群体空间，这会影响用户凭据的存储方式。 因此，在设备已加入 Azure AD 时，单一登录的工作方式目前有一些限制。 Microsoft 已注意到这种限制，正在积极调查解决方案的选项。
- **如果 Surface Hub 在友好名称中有一个点字符（.），则将基础结构投影与 Surface Hub 进行的 Miracast 将失败**
<br/>如果友好名称包括名称（.）中的句点或点（例如，"Room42"），Surface Hub 用户可能会遇到问题。 若要解决此问题，请在 "**设置**Surface Hub" 中更改中心的友好名称  >  **Surface Hub**  >  **About**，然后重新启动设备。 Microsoft 正在处理此问题的解决方案。
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
# 为 Skype for Business 配置域名

在以下方案中需要指定 Skype for Business 服务器的域名：
- **多个 DNS 后缀** - 当 Skype for Business 基础结构具有非连续命名空间时，会使得一个或多个服务器具有与 Skype for Business (SIP) 登录地址后缀不匹配的 DNS 后缀。  
- **Skype for Business 和 Exchange 后缀不同** - 当 Skype for Business 登录地址的后缀与用于设备帐户的 Exchange 地址后缀不同时。
- 使用**证书**-具有本地 Skype for business 服务器的大型组织通常会将证书与自己的根证书颁发机构（CA）结合使用。 CA 域不同于 Skype for Business 服务器的域很常见，这会导致证书不受信任以及登录失败。  Skype 需要了解证书的域名，以便建立信任关系。 企业通常使用组策略来将其推送至 Skype 桌面，但组策略在 Surface Hub 上不受支持。

**为 Skype for Business Server 配置域名**</br>
1. 在 Surface Hub 上，打开**设置**。
2. 依次单击 **Surface Hub**、**通话和音频**。 
3. 在 **Skype for Business 配置**下，单击**配置域名**。 
4. 为 Skype for Business 服务器键入域名，然后单击**确定**。 
   > [!TIP]
   > 可键入多个域名，用逗号分开。 <br> 例如：lync.com、outlook.com、lync.glbdns.microsoft.com

    ![将 Skype for Business FQDN 添加到设置](images/system-settings-add-fqdn.png)

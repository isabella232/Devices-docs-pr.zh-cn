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
ms.openlocfilehash: c9617ec9c77d0f0c0333a156448ca24c18aec1db
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911757"
---
# <a name="configure-domain-name-for-skype-for-business"></a>为 Skype for Business 配置域名

在以下方案中需要指定 Skype for Business 服务器的域名：
- **多个 DNS 后缀** - 当 Skype for Business 基础结构具有非连续命名空间时，会使得一个或多个服务器具有与 Skype for Business (SIP) 登录地址后缀不匹配的 DNS 后缀。  
- **Skype for Business 和 Exchange 后缀不同** - 当 Skype for Business 登录地址的后缀与用于设备帐户的 Exchange 地址后缀不同时。
- **使用证书**- 具有本地证书服务器的大型Skype for Business通常使用具有其自己的根证书颁发机构或 CA (证书) 。 CA 域不同于 Skype for Business 服务器的域很常见，这会导致证书不受信任以及登录失败。  Skype 需要了解证书的域名，以便建立信任关系。 企业通常使用组策略来将其推送至 Skype 桌面，但组策略在 Surface Hub 上不受支持。

**为 Skype for Business Server 配置域名**</br>
1. 在 Surface Hub 上，打开**设置**。
2. 依次单击 **Surface Hub**、**通话和音频**。 
3. 在 **Skype for Business 配置**下，单击**配置域名**。 
4. 为 Skype for Business 服务器键入域名，然后单击**确定**。 
   > [!TIP]
   > 可键入多个域名，用逗号分开。 <br> 例如：lync.com、outlook.com、lync.glbdns.microsoft.com

    ![将Skype for Business FQDN 添加到设置。](images/system-settings-add-fqdn.png)

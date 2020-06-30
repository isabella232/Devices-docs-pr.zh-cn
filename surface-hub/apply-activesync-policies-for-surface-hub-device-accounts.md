---
title: 将 ActiveSync 策略应用到设备帐户 (Surface Hub)
description: Microsoft Surface Hub 的设备帐户使用 ActiveSync 同步邮件和日历。 这将允许用户通过 Surface Hub 加入并启动安排的会议，并允许他们以电子邮件形式发送会议期间所做的任何白板内容。
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, ActiveSync 策略
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 6e93069c2d90bdc4c2f505bc28ba0ec1a4f08076
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831627"
---
# 将 ActiveSync 策略应用到设备帐户 (Surface Hub)


Microsoft Surface Hub 的设备帐户使用 ActiveSync 同步邮件和日历。 这将允许用户通过 Surface Hub 加入并启动安排的会议，并允许他们以电子邮件形式发送会议期间所做的任何白板内容。

若要使这些功能正常运行，必须将你的组织的 ActiveSync 策略配置为如下内容：

-   不能存在阻止 Surface Hub 设备帐户正在使用的资源邮箱同步的任何全局策略。 如果存在此类阻止策略，则需要将 Surface Hub 添加为允许的设备。
-   必须设置一个移动设备邮箱策略，其中 **PasswordEnabled** 设置已设为 False。 其他移动设备邮箱策略设置与 Surface Hub 不兼容。

## 允许 DeviceID


你的组织可能有一个会阻止 Surface Hub 上预配的设备帐户同步的全局策略。 若要配置此属性，请参阅 [ActiveSync 的允许设备 ID](appendix-a-powershell-scripts-for-surface-hub.md#whitelisting-device-ids-cmdlet)。

## 设置 PasswordEnabled


设备帐户必须具有一个 ActiveSync 策略，其中 **PasswordEnabled** 属性已设为 False 或 0。 若要配置此属性，请参阅 [创建 Surface Hub 兼容的 Microsoft Exchange ActiveSync 策略](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy)。

 

 






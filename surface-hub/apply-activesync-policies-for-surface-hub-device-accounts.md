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
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: fa393eca697897ee620732b543ebb6889aa035d1
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472571"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a>将 ActiveSync 策略应用到设备帐户 (Surface Hub)

Windows 10 协同版 1703 及更早版本的 Surface Hub 使用 ActiveSync 同步日历&邮件。

组织中 ActiveSync 策略的Surface Hub要求如下所示：

-   不能有任何全局策略阻止Surface Hub设备帐户使用的资源邮箱同步。 如果存在这样的阻止策略，则需要将Surface Hub添加为允许的设备。
-   必须设置一个移动设备邮箱策略，其中 **PasswordEnabled** 设置已设为 False。 其他移动设备邮箱策略设置与 Surface Hub 不兼容。

## <a name="allowing-the-deviceid"></a>允许 DeviceID

你的组织可能有一个会阻止 Surface Hub 上预配的设备帐户同步的全局策略。 若要配置此属性，请参阅 [ActiveSync 的允许设备 ID](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync)。

## <a name="setting-passwordenabled"></a>设置 PasswordEnabled

设备帐户必须具有一个 ActiveSync 策略，其中 **PasswordEnabled** 属性已设为 False 或 0。 若要配置此属性，请参阅 [创建 Surface Hub 兼容的 Microsoft Exchange ActiveSync 策略](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy)。

 

 






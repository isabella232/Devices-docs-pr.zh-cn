---
title: 保存 BitLocker 密钥 (Surface Hub)
description: 使用 BitLocker 驱动器加密软件自动设置每台 Microsoft Surface Hub。 Microsoft 强烈建议你确保备份 BitLocker 恢复密钥。
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, BitLocker 恢复密钥
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831959"
---
# 保存 BitLocker 密钥 (Surface Hub)


使用 BitLocker 驱动器加密软件自动设置每台 Microsoft Surface Hub。 Microsoft 强烈建议你确保备份 BitLocker 恢复密钥。

可使用几种方法在 Surface Hub 上管理 BitLocker 密钥。

1.  如果已将 Surface Hub 加入域，该设备会备份域中的密钥并将其存储在计算机对象下。

    如果在将该设备加入域后找不到 BitLocker 密钥，可能是因为你的 Active Directory 架构不支持 BitLocker 密钥备份。 如果不想更改架构，可以通过转到“设置”，然后按照使用本地管理员帐户（将在本列表中的后面进行详细说明）的过程来保存 BitLocker 密钥。

2.  如果已将 Surface Hub 加入 Azure Active Directory (Azure AD)，BitLocker 密钥将会存储在用于加入该设备的帐户下。

3.  如果你使用本地管理员帐户管理设备，你可以通过转到 "**设置**" 应用并导航到 "**更新 & 安全**恢复" 来保存 BitLocker 密钥 &gt; **Recovery**。 插入 USB 驱动器，然后选择用于保存 BitLocker 密钥的选项。 该密钥将保存到 USB 驱动器上的文本文件中。


##  <a name="related-topics"></a>相关主题

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)

 

 






---
title: 管理设备帐户密码轮换
description: 了解如何通过 PowerShell 配置本地帐户的 Surface Hub 2
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: ea445588fe2242e3200284a39fdb4a3a8473f94a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832047"
---
# <span data-ttu-id="3f708-104">管理设备帐户密码轮换</span><span class="sxs-lookup"><span data-stu-id="3f708-104">Manage device account password rotation</span></span>

<span data-ttu-id="3f708-105">你可以将 Surface Hub 2 配置为自动更改设备帐户密码，而无需手动更新设备帐户信息。</span><span class="sxs-lookup"><span data-stu-id="3f708-105">You can configure Surface Hub 2S to automatically change a device account password without requiring you to manually update the device account information.</span></span>

<span data-ttu-id="3f708-106">如果启用密码旋转，Surface Hub 2 每隔7天更改一次密码。</span><span class="sxs-lookup"><span data-stu-id="3f708-106">If you turn on Password Rotation, Surface Hub 2S changes the password every 7 days.</span></span> <span data-ttu-id="3f708-107">自动生成的密码包含15-32 个字符，包括大小写字母、数字和特殊字符的组合。</span><span class="sxs-lookup"><span data-stu-id="3f708-107">The automatically generated passwords contain 15-32 characters including  a combination of uppercase and lowercase letters, numbers, and special characters.</span></span>

<span data-ttu-id="3f708-108">在会议期间密码不会更改。</span><span class="sxs-lookup"><span data-stu-id="3f708-108">Passwords do not change during a meeting.</span></span> <span data-ttu-id="3f708-109">如果 Surface Hub 2 的关闭，它会在打开或每隔10分钟后立即尝试更改密码，直到成功。</span><span class="sxs-lookup"><span data-stu-id="3f708-109">If Surface Hub 2S is turned off, it attempts to change the password immediately when turned on or every 10 minutes until successful.</span></span>

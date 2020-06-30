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
# <span data-ttu-id="debfa-105">保存 BitLocker 密钥 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="debfa-105">Save your BitLocker key (Surface Hub)</span></span>


<span data-ttu-id="debfa-106">使用 BitLocker 驱动器加密软件自动设置每台 Microsoft Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="debfa-106">Every Microsoft Surface Hub is automatically set up with BitLocker drive encryption software.</span></span> <span data-ttu-id="debfa-107">Microsoft 强烈建议你确保备份 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="debfa-107">Microsoft strongly recommends that you make sure you back up your BitLocker recovery keys.</span></span>

<span data-ttu-id="debfa-108">可使用几种方法在 Surface Hub 上管理 BitLocker 密钥。</span><span class="sxs-lookup"><span data-stu-id="debfa-108">There are several ways to manage your BitLocker key on the Surface Hub.</span></span>

1.  <span data-ttu-id="debfa-109">如果已将 Surface Hub 加入域，该设备会备份域中的密钥并将其存储在计算机对象下。</span><span class="sxs-lookup"><span data-stu-id="debfa-109">If you’ve joined the Surface Hub to a domain, the device will back up the key on the domain and store it under the computer object.</span></span>

    <span data-ttu-id="debfa-110">如果在将该设备加入域后找不到 BitLocker 密钥，可能是因为你的 Active Directory 架构不支持 BitLocker 密钥备份。</span><span class="sxs-lookup"><span data-stu-id="debfa-110">If you can’t find the BitLocker key after joining the device to a domain, it’s likely that your Active Directory schema doesn’t support BitLocker key backup.</span></span> <span data-ttu-id="debfa-111">如果不想更改架构，可以通过转到“设置”，然后按照使用本地管理员帐户（将在本列表中的后面进行详细说明）的过程来保存 BitLocker 密钥。</span><span class="sxs-lookup"><span data-stu-id="debfa-111">If you don’t want to change the schema, you can save the BitLocker key by going to Settings and following the procedure for using a local admin account, which is detailed later in this list.</span></span>

2.  <span data-ttu-id="debfa-112">如果已将 Surface Hub 加入 Azure Active Directory (Azure AD)，BitLocker 密钥将会存储在用于加入该设备的帐户下。</span><span class="sxs-lookup"><span data-stu-id="debfa-112">If you’ve joined the Surface Hub to Azure Active Directory (Azure AD), the BitLocker key will be stored under the account that was used to join the device.</span></span>

3.  <span data-ttu-id="debfa-113">如果你使用本地管理员帐户管理设备，你可以通过转到 "**设置**" 应用并导航到 "**更新 & 安全**恢复" 来保存 BitLocker 密钥 &gt; **Recovery**。</span><span class="sxs-lookup"><span data-stu-id="debfa-113">If you’re using a local admin account to manage the device, you can save the BitLocker key by going to the **Settings** app and navigating to **Update & security** &gt; **Recovery**.</span></span> <span data-ttu-id="debfa-114">插入 USB 驱动器，然后选择用于保存 BitLocker 密钥的选项。</span><span class="sxs-lookup"><span data-stu-id="debfa-114">Insert a USB drive and select the option to save the BitLocker key.</span></span> <span data-ttu-id="debfa-115">该密钥将保存到 USB 驱动器上的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="debfa-115">The key will be saved to a text file on the USB drive.</span></span>


## <span data-ttu-id="debfa-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="debfa-116">Related topics</span></span>

[<span data-ttu-id="debfa-117">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="debfa-117">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="debfa-118">Microsoft Surface Hub 管理员指南</span><span class="sxs-lookup"><span data-stu-id="debfa-118">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 






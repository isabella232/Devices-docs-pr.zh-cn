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
ms.openlocfilehash: 7ead08e49d3eee2d616ac9fcf06b85dd82e136dc
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474729"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a><span data-ttu-id="2026e-105">将 ActiveSync 策略应用到设备帐户 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="2026e-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="2026e-106">使用 Active Directory 设备帐户的 Surface Hub (在 Hub 上以 \**域\** 用户名格式) 和本地 Exchange 服务使用 ActiveSync 同步邮件和日历。</span><span class="sxs-lookup"><span data-stu-id="2026e-106">Surface Hubs using Active Directory device accounts (provisioned on the Hub in **domain\username** format) and on-premises Exchange services make use of ActiveSync to sync mail and calendar.</span></span> <span data-ttu-id="2026e-107">这将允许用户通过 Surface Hub 加入并启动安排的会议，并允许他们以电子邮件形式发送会议期间所做的任何白板内容。</span><span class="sxs-lookup"><span data-stu-id="2026e-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="2026e-108">若要使这些功能正常运行，必须将你的组织的 ActiveSync 策略配置为如下内容：</span><span class="sxs-lookup"><span data-stu-id="2026e-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="2026e-109">不能存在阻止 Surface Hub 设备帐户正在使用的资源邮箱同步的任何全局策略。</span><span class="sxs-lookup"><span data-stu-id="2026e-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="2026e-110">如果存在此类阻止策略，你需要将 Surface Hub 添加为允许的设备。</span><span class="sxs-lookup"><span data-stu-id="2026e-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="2026e-111">必须设置一个移动设备邮箱策略，其中 **PasswordEnabled** 设置已设为 False。</span><span class="sxs-lookup"><span data-stu-id="2026e-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="2026e-112">其他移动设备邮箱策略设置与 Surface Hub 不兼容。</span><span class="sxs-lookup"><span data-stu-id="2026e-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <a name="allowing-the-deviceid"></a><span data-ttu-id="2026e-113">允许 DeviceID</span><span class="sxs-lookup"><span data-stu-id="2026e-113">Allowing the DeviceID</span></span>

<span data-ttu-id="2026e-114">你的组织可能有一个会阻止 Surface Hub 上预配的设备帐户同步的全局策略。</span><span class="sxs-lookup"><span data-stu-id="2026e-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="2026e-115">若要配置此属性，请参阅 [ActiveSync 的允许设备 ID](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync)。</span><span class="sxs-lookup"><span data-stu-id="2026e-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span></span>

## <a name="setting-passwordenabled"></a><span data-ttu-id="2026e-116">设置 PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="2026e-116">Setting PasswordEnabled</span></span>

<span data-ttu-id="2026e-117">设备帐户必须具有一个 ActiveSync 策略，其中 **PasswordEnabled** 属性已设为 False 或 0。</span><span class="sxs-lookup"><span data-stu-id="2026e-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="2026e-118">若要配置此属性，请参阅 [创建 Surface Hub 兼容的 Microsoft Exchange ActiveSync 策略](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy)。</span><span class="sxs-lookup"><span data-stu-id="2026e-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 






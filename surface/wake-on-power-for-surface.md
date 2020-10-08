---
title: 如何启用 Surface Power on Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: 介绍如何启用和禁用 Surface 设备的唤醒功能。
keywords: 更新、部署、驱动程序、wol、lan 唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 272c19baedb295abac08e90012246e453b88f42f
ms.sourcegitcommit: 6fd7008992503db9ae1f56654aa80110348924d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903391"
---
# <span data-ttu-id="1add0-104">Surface 设备通电唤醒</span><span class="sxs-lookup"><span data-stu-id="1add0-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="1add0-105">当您离开桌面时，可以关闭 Surface 设备，或设置为休眠模式以节省电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="1add0-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="1add0-106">为了提高这些设备的可管理性，Power on Power 启用兼容的 Surface 设备，以便在它们重新连接到电源时自动启动。</span><span class="sxs-lookup"><span data-stu-id="1add0-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="1add0-107">若要配置 Power on Power，可以通过 Surface UEFI 配置器或 UEFI 管理器使用 Surface Enterprise 管理模式（SEMM）。</span><span class="sxs-lookup"><span data-stu-id="1add0-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="1add0-108">以下设备上提供了 Power on Power 功能：</span><span class="sxs-lookup"><span data-stu-id="1add0-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="1add0-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="1add0-109">Surface Book 3</span></span>
- <span data-ttu-id="1add0-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="1add0-110">Surface Pro 7</span></span>
- <span data-ttu-id="1add0-111">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="1add0-111">Surface Laptop 3</span></span>
- <span data-ttu-id="1add0-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="1add0-112">Surface Pro X</span></span> 

## <span data-ttu-id="1add0-113">概述和先决条件</span><span class="sxs-lookup"><span data-stu-id="1add0-113">Overview and prerequisites</span></span>

<span data-ttu-id="1add0-114">Surface UEFI 配置器允许你将单个 UEFI 设置保存在 Windows Installer 的 .msi 程序包中，以便分发到目标设备。</span><span class="sxs-lookup"><span data-stu-id="1add0-114">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="1add0-115">本文假定你知道如何使用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="1add0-115">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="1add0-116">有关详细信息，请参阅[Surface Enterprise 管理模式（SEMM）](surface-enterprise-management-mode.md)文档。</span><span class="sxs-lookup"><span data-stu-id="1add0-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="1add0-117">启用 Power 唤醒</span><span class="sxs-lookup"><span data-stu-id="1add0-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="1add0-118">下载最新版本的[SURFACE UEFI 配置](https://www.microsoft.com/download/confirmation.aspx?id=46703)器。</span><span class="sxs-lookup"><span data-stu-id="1add0-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="1add0-119">以管理员身份登录 Surface 设备，打开**SURFACE UEFI 配置**器，选择 " **Surface 设备**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1add0-119">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。":::
3.  <span data-ttu-id="1add0-121">选择 "**开始**"，然后选择 "**配置程序包**" 下的 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="1add0-121">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。":::
4.  <span data-ttu-id="1add0-123">选择 "**证书保护**"，然后添加证书 .pfx 文件。</span><span class="sxs-lookup"><span data-stu-id="1add0-123">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="1add0-124">输入您的密码，选择 "**下一步**，根据需要添加**密码保护**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1add0-124">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="1add0-125">在 "**选择要作为目标的图面类型**" 页面上，根据需要选择目标设备。</span><span class="sxs-lookup"><span data-stu-id="1add0-125">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="1add0-126">例如，选择**Surface Pro 7**。</span><span class="sxs-lookup"><span data-stu-id="1add0-126">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="1add0-127">在 "**高级功能**" 页面上，选择 " **Power on Power**"，将功能设置为 **"打开**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1add0-127">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。"::: 
8.  <span data-ttu-id="1add0-129">在 "**成功**" 页面上，选择 "**结束**"。</span><span class="sxs-lookup"><span data-stu-id="1add0-129">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1add0-130">如果这是你第一次向设备提供设置，系统将提示你还提供证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="1add0-130">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="1add0-131">保存 .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="1add0-131">Save the .msi package.</span></span> 

## <span data-ttu-id="1add0-132">应用 MSI 程序包</span><span class="sxs-lookup"><span data-stu-id="1add0-132">Apply the MSI package</span></span> 

<span data-ttu-id="1add0-133">通过使用软件分发工具（如 Microsoft 终结点配置管理器），可以将 MSI 程序包应用到网络上的设备。</span><span class="sxs-lookup"><span data-stu-id="1add0-133">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="1add0-134">此过程包括在本地计算机上安装程序包的步骤。</span><span class="sxs-lookup"><span data-stu-id="1add0-134">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="1add0-135">在提升的命令提示符处，输入 .msi 文件的完整路径以运行 .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="1add0-135">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="1add0-136">在 "**警告**" 对话框中，根据需要选择 **"确定" 或 "** 禁用 BitLocker"。</span><span class="sxs-lookup"><span data-stu-id="1add0-136">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。":::
3.  <span data-ttu-id="1add0-138">在 "欢迎" 页面上，选择 "**下一步**" 以运行程序包并应用新配置的 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="1add0-138">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="选择 &quot;Surface 设备&quot;，然后选择 &quot;下一步&quot;。":::
4.  <span data-ttu-id="1add0-140">重启您的设备。</span><span class="sxs-lookup"><span data-stu-id="1add0-140">Restart your device.</span></span> 

<span data-ttu-id="1add0-141">现已配置 Power on Power。</span><span class="sxs-lookup"><span data-stu-id="1add0-141">Wake on Power is now configured.</span></span> <span data-ttu-id="1add0-142">要测试设置，请关闭您的设备，断开电源，然后重新连接电源。</span><span class="sxs-lookup"><span data-stu-id="1add0-142">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="1add0-143">设备应自动启动。</span><span class="sxs-lookup"><span data-stu-id="1add0-143">The device should start automatically.</span></span> 

## <span data-ttu-id="1add0-144">参考</span><span class="sxs-lookup"><span data-stu-id="1add0-144">References</span></span>

<span data-ttu-id="1add0-145">有关详细信息，请参阅以下文章。</span><span class="sxs-lookup"><span data-stu-id="1add0-145">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="1add0-146">Surface 企业管理模式</span><span class="sxs-lookup"><span data-stu-id="1add0-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="1add0-147">面向 Surface 设备的 LAN 唤醒</span><span class="sxs-lookup"><span data-stu-id="1add0-147">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="1add0-148">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="1add0-148">Still need help?</span></span> <span data-ttu-id="1add0-149">转到[Microsoft 社区](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="1add0-149">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
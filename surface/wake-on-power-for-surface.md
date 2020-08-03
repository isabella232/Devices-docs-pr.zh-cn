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
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902995"
---
# <span data-ttu-id="8805c-104">对 Surface 设备供电的唤醒</span><span class="sxs-lookup"><span data-stu-id="8805c-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="8805c-105">可以在离开桌面时关闭 Surface 设备，也可以设置为休眠模式以节省电池。</span><span class="sxs-lookup"><span data-stu-id="8805c-105">Surface devices can be powered off while away from the desk or set to hibernate mode to save battery.</span></span> <span data-ttu-id="8805c-106">为了提高这些设备的可管理性，Power on Power 可使兼容的 Surface 设备在重新连接到 Power 时自动启动。</span><span class="sxs-lookup"><span data-stu-id="8805c-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when reconnected to power.</span></span> <span data-ttu-id="8805c-107">配置 "在 Power 唤醒" 时，需要通过 Surface UEFI 配置器或 UEFI 管理器使用 Surface Enterprise 管理模式（SEMM）。</span><span class="sxs-lookup"><span data-stu-id="8805c-107">Configuring Wake on Power requires using Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="8805c-108">在以下设备上可以使用 "Power on" 功能：</span><span class="sxs-lookup"><span data-stu-id="8805c-108">Wake on Power is a feature available on the following devices:</span></span>

- <span data-ttu-id="8805c-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="8805c-109">Surface Book 3</span></span>
- <span data-ttu-id="8805c-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="8805c-110">Surface Pro 7</span></span>
- <span data-ttu-id="8805c-111">Surface 笔记本电脑3</span><span class="sxs-lookup"><span data-stu-id="8805c-111">Surface Laptop 3</span></span>
- <span data-ttu-id="8805c-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="8805c-112">Surface Pro X</span></span> 

## <span data-ttu-id="8805c-113">概述和先决条件</span><span class="sxs-lookup"><span data-stu-id="8805c-113">Overview and prerequisites</span></span>

<span data-ttu-id="8805c-114">你可以使用 Surface UEFI 配置器配置单独的 UEFI 设置，这些设置保存在 Windows 安装程序 .msi 程序包中，以便分发到目标设备。</span><span class="sxs-lookup"><span data-stu-id="8805c-114">You can use the Surface UEFI Configurator to configure individual UEFI settings that are saved in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="8805c-115">本文假定你熟悉 SEMM 的使用。</span><span class="sxs-lookup"><span data-stu-id="8805c-115">This article assumes that you are familiar with using SEMM.</span></span> <span data-ttu-id="8805c-116">有关详细信息，请参阅[Surface Enterprise 管理模式（SEMM）](surface-enterprise-management-mode.md)文档。</span><span class="sxs-lookup"><span data-stu-id="8805c-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="8805c-117">启用 Power 唤醒</span><span class="sxs-lookup"><span data-stu-id="8805c-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="8805c-118">下载最新版本的[SURFACE UEFI 配置](https://www.microsoft.com/download/confirmation.aspx?id=46703)器。</span><span class="sxs-lookup"><span data-stu-id="8805c-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="8805c-119">以管理员身份登录 Surface 设备，打开**SURFACE UEFI 配置**器，选择 " **Surface 设备**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8805c-119">Sign into your Surface device as an Administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="选择 "Surface 设备"，然后选择 "下一步"。":::
3.  <span data-ttu-id="8805c-121">选择 "**开始**"，然后在 "**配置包**" 下选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="8805c-121">Select **Start** and then under **Configuration Package** select **Create**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="选择 "创建配置包"。":::
4.  <span data-ttu-id="8805c-123">选择 "**证书保护**" 并添加证书 .pfx 文件。</span><span class="sxs-lookup"><span data-stu-id="8805c-123">Select **Certificate Protection** and add your certificate .pfx file.</span></span> <span data-ttu-id="8805c-124">输入密码后，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8805c-124">After entering your password, select **Next**.</span></span> <span data-ttu-id="8805c-125">根据需要添加**密码保护**，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8805c-125">Add **Password Protection**, as appropriate, and then select **Next**.</span></span>
5.  <span data-ttu-id="8805c-126">在 "**选择要作为目标的图面类型**" 页面上，根据需要选择目标设备。</span><span class="sxs-lookup"><span data-stu-id="8805c-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="8805c-127">例如， **Surface Pro 7**。</span><span class="sxs-lookup"><span data-stu-id="8805c-127">For example, **Surface Pro 7**.</span></span>
6.  <span data-ttu-id="8805c-128">在 "**高级功能**" 页面上，选择 **"接通电源"** 并设置为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="8805c-128">On the **Advanced Features** page, select **Wake on Power** and set to **On**.</span></span> <span data-ttu-id="8805c-129">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="8805c-129">Select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="选择 "接通电源时唤醒"，并设置为 "开"。"::: 
7.  <span data-ttu-id="8805c-131">在 "**成功**" 页面上，选择 "**结束**"。</span><span class="sxs-lookup"><span data-stu-id="8805c-131">On the **Successful** page, select **End**.</span></span> <span data-ttu-id="8805c-132">如果你是第一次向设备提供设置，系统将提示你提供证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="8805c-132">If this is your first time providing settings to your device, you will be prompted to provide the last two characters of the certificate thumbprint.</span></span> 
8.  <span data-ttu-id="8805c-133">保存 .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="8805c-133">Save the .msi package.</span></span> 

## <span data-ttu-id="8805c-134">应用 MSI 程序包</span><span class="sxs-lookup"><span data-stu-id="8805c-134">Apply the MSI package</span></span> 

<span data-ttu-id="8805c-135">你可以使用软件分发工具（如 Microsoft 终结点配置管理器）将 MSI 程序包应用到网络上的设备。</span><span class="sxs-lookup"><span data-stu-id="8805c-135">You can apply the MSI package to devices across your network using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="8805c-136">此过程包括在本地计算机上安装程序包的步骤。</span><span class="sxs-lookup"><span data-stu-id="8805c-136">This procedure includes steps for installing the package on your local machine.</span></span> 

1.  <span data-ttu-id="8805c-137">打开提升的命令提示符，输入 .msi 文件的完整路径以运行 .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="8805c-137">Open an elevated command prompt and enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="8805c-138">在 "**警告**" 对话框中，根据需要选择 **"确定" 或 "** 禁用 Bitlocker"。</span><span class="sxs-lookup"><span data-stu-id="8805c-138">On the **Warning** dialog box, select **OK** or disable Bitlocker as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="根据需要选择 "确定" 或 "禁用 Bitlocker"。":::
3.  <span data-ttu-id="8805c-140">在 "欢迎" 页面上，选择 "**下一步**" 以运行程序包并应用新配置的 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="8805c-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="一个欢迎页面，选择 "下一步"。":::
4.  <span data-ttu-id="8805c-142">重启您的设备。</span><span class="sxs-lookup"><span data-stu-id="8805c-142">Restart your device.</span></span> 

<span data-ttu-id="8805c-143">现已配置 Power on Power。</span><span class="sxs-lookup"><span data-stu-id="8805c-143">Wake on Power is now configured.</span></span> <span data-ttu-id="8805c-144">要测试设置，请关闭您的设备，断开电源，然后重新连接电源。</span><span class="sxs-lookup"><span data-stu-id="8805c-144">To test the setting, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="8805c-145">设备将自动启动。</span><span class="sxs-lookup"><span data-stu-id="8805c-145">The device will start automatically.</span></span> 

## <span data-ttu-id="8805c-146">详细信息</span><span class="sxs-lookup"><span data-stu-id="8805c-146">More information</span></span>

<span data-ttu-id="8805c-147">有关详细信息，请参阅以下文章。</span><span class="sxs-lookup"><span data-stu-id="8805c-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="8805c-148">Surface 企业管理模式</span><span class="sxs-lookup"><span data-stu-id="8805c-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="8805c-149">面向 Surface 设备的 LAN 唤醒</span><span class="sxs-lookup"><span data-stu-id="8805c-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="8805c-150">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="8805c-150">Still need help?</span></span> <span data-ttu-id="8805c-151">转到[Microsoft 社区](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="8805c-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
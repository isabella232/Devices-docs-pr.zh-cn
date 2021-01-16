---
title: 如何为 Surface 启用电源唤醒
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: 介绍如何为 Surface 设备启用和禁用电源唤醒。
keywords: 更新， 部署， 驱动程序， wol， lan 唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271556"
---
# <span data-ttu-id="8e3c7-104">Surface 设备通电唤醒</span><span class="sxs-lookup"><span data-stu-id="8e3c7-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="8e3c7-105">当你离开桌面时，Surface 设备可以关闭电源，或者设置为休眠模式以节省电池使用时间。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="8e3c7-106">为了改进这些设备的可管理性，电源唤醒使兼容的 Surface 设备能够在重新连接到电源时自动启动。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="8e3c7-107">若要配置电源唤醒，可以通过 Surface UEFI (UEFI) 或 UEFI 管理器使用 Surface Enterprise Management Mode) SEMM 模式。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="8e3c7-108">电源唤醒功能在下列设备上可用：</span><span class="sxs-lookup"><span data-stu-id="8e3c7-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="8e3c7-109">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="8e3c7-109">Surface Pro 7+</span></span>
- <span data-ttu-id="8e3c7-110">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="8e3c7-110">Surface Book 3</span></span>
- <span data-ttu-id="8e3c7-111">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="8e3c7-111">Surface Pro 7</span></span>
- <span data-ttu-id="8e3c7-112">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="8e3c7-112">Surface Laptop 3</span></span>
- <span data-ttu-id="8e3c7-113">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="8e3c7-113">Surface Laptop Go</span></span>
- <span data-ttu-id="8e3c7-114">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="8e3c7-114">Surface Pro X</span></span> 


## <span data-ttu-id="8e3c7-115">概述和先决条件</span><span class="sxs-lookup"><span data-stu-id="8e3c7-115">Overview and prerequisites</span></span>

<span data-ttu-id="8e3c7-116">Surface UEFI 配置器允许你将单个 UEFI 设置保存在 Windows Installer .msi 程序包中，以分发到目标设备。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-116">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="8e3c7-117">本文假定你了解如何使用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-117">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="8e3c7-118">有关详细信息，请参阅 [SURFACE Enterprise Management Mode (SEMM) ](surface-enterprise-management-mode.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-118">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="8e3c7-119">启用电源唤醒</span><span class="sxs-lookup"><span data-stu-id="8e3c7-119">To enable Wake on Power</span></span>

1.  <span data-ttu-id="8e3c7-120">下载最新版本的[Surface UEFI Configurator。](https://www.microsoft.com/download/confirmation.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="8e3c7-120">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="8e3c7-121">以管理员角色登录 Surface 设备，打开**Surface UEFI 配置**器，选择**Surface 设备**，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="8e3c7-121">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="选择 Surface 设备并选择"下一步"。":::
3.  <span data-ttu-id="8e3c7-123">选择 **"** 开始"，然后选择 **"配置包\*\*\*\*"下的"创建"。**</span><span class="sxs-lookup"><span data-stu-id="8e3c7-123">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="选择"创建配置包"。":::
4.  <span data-ttu-id="8e3c7-125">选择 **证书保护**，并添加证书 .pfx 文件。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-125">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="8e3c7-126">输入您的密码，选择 **"下**一步\*\*\*\*"，根据需要添加密码保护，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="8e3c7-126">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="8e3c7-127">在 **"选择要面向的 Surface 类型"** 页上，选择相应的目标设备。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-127">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="8e3c7-128">例如，选择**Surface Pro 7。**</span><span class="sxs-lookup"><span data-stu-id="8e3c7-128">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="8e3c7-129">在"**高级功能**"页上，选择 **"电源**唤醒"，将功能设置为 **"打开**"，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="8e3c7-129">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="选择"电源唤醒"并设置为"打开"。"::: 
8.  <span data-ttu-id="8e3c7-131">在"**成功"** 页上，选择"**结束"。**</span><span class="sxs-lookup"><span data-stu-id="8e3c7-131">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8e3c7-132">如果这是第一次向设备提供设置，系统将提示你提供证书指纹的最后两个字符。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-132">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="8e3c7-133">保存 .msi 包。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-133">Save the .msi package.</span></span> 

## <span data-ttu-id="8e3c7-134">应用 MSI 程序包</span><span class="sxs-lookup"><span data-stu-id="8e3c7-134">Apply the MSI package</span></span> 

<span data-ttu-id="8e3c7-135">可以使用软件分发工具（如 Microsoft Endpoint Configuration Manager）将 MSI 程序包应用到整个网络的设备。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-135">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="8e3c7-136">此过程包括在本地计算机上安装程序包的步骤。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-136">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="8e3c7-137">在提升的命令提示符下，输入 .msi 文件的完整路径以运行 .msi 包。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-137">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="8e3c7-138">在 **"警告** "对话框中，选择 **"确定** "或禁用 BitLocker（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-138">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="选择"确定"或在适当时禁用 BitLocker。":::
3.  <span data-ttu-id="8e3c7-140">在"欢迎"页上，选择 **"下** 一步"运行程序包并应用新配置的 UEFI 设置。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="在欢迎页面之一，选择"下一步"。":::
4.  <span data-ttu-id="8e3c7-142">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-142">Restart your device.</span></span> 

<span data-ttu-id="8e3c7-143">现在配置了"电源唤醒"。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-143">Wake on Power is now configured.</span></span> <span data-ttu-id="8e3c7-144">若要测试设置，请关闭设备，断开电源连接，然后重新连接电源。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-144">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="8e3c7-145">设备应自动启动。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-145">The device should start automatically.</span></span> 

## <span data-ttu-id="8e3c7-146">参考</span><span class="sxs-lookup"><span data-stu-id="8e3c7-146">References</span></span>

<span data-ttu-id="8e3c7-147">有关详细信息，请参阅以下文章。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="8e3c7-148">Surface 企业管理模式</span><span class="sxs-lookup"><span data-stu-id="8e3c7-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="8e3c7-149">在 LAN 上唤醒 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="8e3c7-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="8e3c7-150">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="8e3c7-150">Still need help?</span></span> <span data-ttu-id="8e3c7-151">转到 [Microsoft 社区](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="8e3c7-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
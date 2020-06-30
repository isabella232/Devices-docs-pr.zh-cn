---
title: 来自 SEMM （Surface）的取消注册 Surface 设备
description: 了解如何使用 Surface UEFI reset 程序包或恢复请求选项从 SEMM 取消注册设备。
keywords: surface 企业管理
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: aa24ff1ac8a93ebc8078490c5e0c8fa34c940a25
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830764"
---
# <span data-ttu-id="76686-104">从 SEMM 取消注册 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="76686-104">Unenroll Surface devices from SEMM</span></span>

<span data-ttu-id="76686-105">当 Surface 设备注册到 Surface Enterprise 管理模式（SEMM）时，证书将存储在该设备的固件中。</span><span class="sxs-lookup"><span data-stu-id="76686-105">When a Surface device is enrolled in Surface Enterprise Management Mode (SEMM), a certificate is stored in the firmware of that device.</span></span> <span data-ttu-id="76686-106">当设备注册在 SEMM 中时，该证书和 SEMM 中的注册将阻止对 Surface UEFI 设置或选项进行任何未经授权的更改。</span><span class="sxs-lookup"><span data-stu-id="76686-106">The presence of that certificate and the enrollment in SEMM prevent any unauthorized changes to Surface UEFI settings or options while the device is enrolled in SEMM.</span></span> <span data-ttu-id="76686-107">若要将 Surface UEFI 设置的控制权还原到用户，Surface 设备必须是从 SEMM 中 unenrolled 的过程，有时会将其描述为重置或恢复。</span><span class="sxs-lookup"><span data-stu-id="76686-107">To restore control of Surface UEFI settings to the user, the Surface device must be unenrolled from SEMM, a process sometimes described as reset or recovery.</span></span> <span data-ttu-id="76686-108">可使用两种方法从 SEMM 取消注册设备： Surface UEFI 重置包和恢复请求。</span><span class="sxs-lookup"><span data-stu-id="76686-108">There are two methods you can use to unenroll a device from SEMM—a Surface UEFI reset package and a Recovery Request.</span></span>

>[!WARNING]
><span data-ttu-id="76686-109">若要从 SEMM 取消注册设备并还原用户对 Surface UEFI 设置的控制，您必须拥有用于在 SEMM 中注册设备的 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="76686-109">To unenroll a device from SEMM and restore user control of Surface UEFI settings, you must have the SEMM certificate that was used to enroll the device in SEMM.</span></span> <span data-ttu-id="76686-110">如果此证书已丢失或损坏，则不能取消注册 SEMM。</span><span class="sxs-lookup"><span data-stu-id="76686-110">If this certificate becomes lost or corrupted, it is not possible to unenroll from SEMM.</span></span> <span data-ttu-id="76686-111">相应地备份和保护您的 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="76686-111">Back up and protect your SEMM certificate accordingly.</span></span>

<span data-ttu-id="76686-112">有关 SEMM 的详细信息，请参阅[Microsoft Surface 企业管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="76686-112">For more information about SEMM, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="76686-113">使用 Surface UEFI reset 程序包取消注册 SEMM 中的 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="76686-113">Unenroll a Surface device from SEMM with a Surface UEFI reset package</span></span>

<span data-ttu-id="76686-114">Surface UEFI 重置程序包是用于从 SEMM 取消注册 Surface 设备的主要方法。</span><span class="sxs-lookup"><span data-stu-id="76686-114">The Surface UEFI reset package is the primary method you use to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="76686-115">与 Surface UEFI 配置包一样，reset 程序包是在设备上配置 SEMM 的 Windows Installer （.msi）文件。</span><span class="sxs-lookup"><span data-stu-id="76686-115">Like a Surface UEFI configuration package, the reset package is a Windows Installer (.msi) file that configures SEMM on the device.</span></span> <span data-ttu-id="76686-116">与配置包不同，重置程序包会将 Surface 设备上的 Surface UEFI 配置重置为其默认设置，删除 SEMM 证书，然后从 SEMM 取消注册该设备。</span><span class="sxs-lookup"><span data-stu-id="76686-116">Unlike the configuration package, the reset package will reset the Surface UEFI configuration on a Surface device to its default settings, remove the SEMM certificate, and unenroll the device from SEMM.</span></span>

<span data-ttu-id="76686-117">重置程序包专为单个 Surface 设备创建。</span><span class="sxs-lookup"><span data-stu-id="76686-117">Reset packages are created specifically for an individual Surface device.</span></span> <span data-ttu-id="76686-118">若要开始创建重置程序包的过程，你将需要要取消注册的设备的序列号，以及用于注册设备的 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="76686-118">To begin the process of creating a reset package, you will need the serial number of the device you want to unenroll, as well as the SEMM certificate used to enroll the device.</span></span> <span data-ttu-id="76686-119">你可以在 Surface UEFI 的**PC 信息**页面上找到 surface 设备的序列号，如图1所示。</span><span class="sxs-lookup"><span data-stu-id="76686-119">You can find the serial number of your Surface device on the **PC information** page of Surface UEFI, as shown in Figure 1.</span></span> <span data-ttu-id="76686-120">即使 Surface UEFI 受密码保护，输入的密码不正确，也会显示此页面。</span><span class="sxs-lookup"><span data-stu-id="76686-120">This page is displayed even if Surface UEFI is password protected and the incorrect password is entered.</span></span>

![显示 Surface 设备序列号](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*<span data-ttu-id="76686-122">图 1.</span><span class="sxs-lookup"><span data-stu-id="76686-122">Figure 1.</span></span> <span data-ttu-id="76686-123">Surface 设备的序列号显示在 "Surface UEFI 电脑信息" 页面上</span><span class="sxs-lookup"><span data-stu-id="76686-123">The serial number of the Surface device is displayed on the Surface UEFI PC information page</span></span>*

>[!NOTE]
><span data-ttu-id="76686-124">若要启动到 Surface UEFI，请在设备关闭时同时按**成交量**和**电源**。</span><span class="sxs-lookup"><span data-stu-id="76686-124">To boot to Surface UEFI, press **Volume Up** and **Power** simultaneously while the device is off.</span></span> <span data-ttu-id="76686-125">保持**音量**，直到显示 Surface 徽标，并且设备开始启动。</span><span class="sxs-lookup"><span data-stu-id="76686-125">Hold **Volume Up** until the Surface logo is displayed and the device begins to boot.</span></span>

<span data-ttu-id="76686-126">若要创建 Surface UEFI 重置程序包，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="76686-126">To create a Surface UEFI reset package, follow these steps:</span></span>

1. <span data-ttu-id="76686-127">从 "开始" 菜单打开 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="76686-127">Open Microsoft Surface UEFI Configurator from the Start menu.</span></span>
2. <span data-ttu-id="76686-128">单击**开始**。</span><span class="sxs-lookup"><span data-stu-id="76686-128">Click **Start**.</span></span>
3. <span data-ttu-id="76686-129">单击 "**重置程序包**"，如图2所示。</span><span class="sxs-lookup"><span data-stu-id="76686-129">Click **Reset Package**, as shown in Figure 2.</span></span>

   ![选择 "重置包" 以创建从 SEMM 的取消注册 Surface 设备的程序包](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *<span data-ttu-id="76686-131">图 2.</span><span class="sxs-lookup"><span data-stu-id="76686-131">Figure 2.</span></span> <span data-ttu-id="76686-132">单击 "重置包" 以创建程序包以从 SEMM 取消注册 Surface 设备</span><span class="sxs-lookup"><span data-stu-id="76686-132">Click Reset Package to create a package to unenroll a Surface device from SEMM</span></span>*

4. <span data-ttu-id="76686-133">单击 "**证书保护**" 以添加带有私钥（.pfx）的 SEMM 证书文件，如图3所示。</span><span class="sxs-lookup"><span data-stu-id="76686-133">Click **Certificate Protection** to add your SEMM certificate file with private key (.pfx), as shown in Figure 3.</span></span> <span data-ttu-id="76686-134">通过浏览找到您的证书文件的位置，选择该文件，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="76686-134">Browse to the location of your certificate file, select the file, and then click **OK**.</span></span>

   ![将 SEMM 证书添加到 Surface UEFI 重置程序包](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *<span data-ttu-id="76686-136">图 3.</span><span class="sxs-lookup"><span data-stu-id="76686-136">Figure 3.</span></span> <span data-ttu-id="76686-137">将 SEMM 证书添加到 Surface UEFI 重置程序包</span><span class="sxs-lookup"><span data-stu-id="76686-137">Add the SEMM certificate to a Surface UEFI reset package</span></span>*

5. <span data-ttu-id="76686-138">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76686-138">Click **Next**.</span></span>
6. <span data-ttu-id="76686-139">键入要从 SEMM 取消注册的设备的序列号（如图4所示），然后单击 "**生成**" 以生成 Surface UEFI reset 程序包。</span><span class="sxs-lookup"><span data-stu-id="76686-139">Type the serial number of the device you want to unenroll from SEMM (as shown in Figure 4), and then click **Build** to generate the Surface UEFI reset package.</span></span>

   ![使用 Surface 设备序列号创建 Surface UEFI 重置包](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *<span data-ttu-id="76686-141">图 4.</span><span class="sxs-lookup"><span data-stu-id="76686-141">Figure 4.</span></span> <span data-ttu-id="76686-142">使用 Surface 设备的序列号创建 Surface UEFI 重置包</span><span class="sxs-lookup"><span data-stu-id="76686-142">Use the serial number of your Surface device to create a Surface UEFI reset package</span></span>*

7. <span data-ttu-id="76686-143">在 "**另存为**" 对话框中，指定 Surface UEFI 重置程序包的名称，浏览到要保存文件的位置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="76686-143">In the **Save As** dialog box, specify a name for the Surface UEFI reset package, browse to the location where you would like to save the file, and then click **Save**.</span></span>
8. <span data-ttu-id="76686-144">程序包生成完成后，将显示**成功**的页面。</span><span class="sxs-lookup"><span data-stu-id="76686-144">When the package generation has completed, the **Successful** page is displayed.</span></span> <span data-ttu-id="76686-145">单击 "**结束**" 以完成程序包创建并关闭 MICROSOFT Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="76686-145">Click **End** to complete package creation and close Microsoft Surface UEFI Configurator.</span></span>

<span data-ttu-id="76686-146">在 Surface 设备上运行 Surface UEFI 重置程序包 Windows Installer （.msi）文件，从 SEMM 取消注册设备。</span><span class="sxs-lookup"><span data-stu-id="76686-146">Run the Surface UEFI reset package Windows Installer (.msi) file on the Surface device to unenroll the device from SEMM.</span></span> <span data-ttu-id="76686-147">重置程序包将需要重新启动才能执行取消注册操作。</span><span class="sxs-lookup"><span data-stu-id="76686-147">The reset package will require a reboot to perform the unenroll operation.</span></span> <span data-ttu-id="76686-148">在设备 unenrolled 后，您可以通过确保 "**程序和功能**" （如图5所示）中的**Microsoft Surface Configuration 程序包**项目不再存在来验证是否成功删除。</span><span class="sxs-lookup"><span data-stu-id="76686-148">After the device has been unenrolled, you can verify the successful removal by ensuring that the **Microsoft Surface Configuration Package** item in **Programs and Features** (shown in Figure 5) is no longer present.</span></span>

![屏幕显示设备已注册 SEMM](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*<span data-ttu-id="76686-150">图 5.</span><span class="sxs-lookup"><span data-stu-id="76686-150">Figure 5.</span></span> <span data-ttu-id="76686-151">"程序和功能" 中的 Microsoft Surface 配置包项目的存在表示设备已注册 SEMM</span><span class="sxs-lookup"><span data-stu-id="76686-151">The presence of the Microsoft Surface Configuration Package item in Programs and Features indicates that the device is enrolled in SEMM</span></span>*

## <span data-ttu-id="76686-152">使用恢复请求取消注册 Surface 设备 SEMM</span><span class="sxs-lookup"><span data-stu-id="76686-152">Unenroll a Surface device from SEMM with a Recovery Request</span></span>

<span data-ttu-id="76686-153">在某些情况下，Surface UEFI 重置程序包可能无法用于取消注册 SEMM 中的 Surface 设备（例如，Windows 变得不可用）。</span><span class="sxs-lookup"><span data-stu-id="76686-153">In some scenarios, a Surface UEFI reset package may not be a viable option to unenroll a Surface device from SEMM (for example, where Windows has become unusable).</span></span> <span data-ttu-id="76686-154">在这些方案中，你可以使用从 Surface UEFI 内部生成的恢复请求取消注册设备。</span><span class="sxs-lookup"><span data-stu-id="76686-154">In these scenarios you can unenroll the device by using a Recovery Request generated from within Surface UEFI.</span></span> <span data-ttu-id="76686-155">即使在没有 Surface UEFI 密码的设备上，也可以启动恢复请求进程。</span><span class="sxs-lookup"><span data-stu-id="76686-155">The Recovery Request process can be initiated even on devices where you do not have the Surface UEFI password.</span></span>

<span data-ttu-id="76686-156">恢复请求进程从 surface 设备上的 Surface UEFI 启动，在另一台计算机上通过 Microsoft Surface UEFI 配置器批准，然后在 Surface UEFI 中完成。</span><span class="sxs-lookup"><span data-stu-id="76686-156">The Recovery Request process is initiated from Surface UEFI on the Surface device, approved with Microsoft Surface UEFI Configurator on another computer, and then completed in Surface UEFI.</span></span> <span data-ttu-id="76686-157">与重置程序包一样，使用 Microsoft Surface UEFI 配置器批准恢复请求需要访问用于注册 Surface 设备的 SEMM 证书。</span><span class="sxs-lookup"><span data-stu-id="76686-157">Like the reset package, approving a Recovery Request with Microsoft Surface UEFI Configurator requires access to the SEMM certificate that was used to enroll the Surface device.</span></span>

<span data-ttu-id="76686-158">若要启动恢复请求，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="76686-158">To initiate a Recovery Request, follow these steps:</span></span>

1. <span data-ttu-id="76686-159">引导要从 SEMM unenrolled 到 Surface UEFI 的 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="76686-159">Boot the Surface device that is to be unenrolled from SEMM to Surface UEFI.</span></span>
2. <span data-ttu-id="76686-160">如果出现提示，请键入 Surface UEFI 密码。</span><span class="sxs-lookup"><span data-stu-id="76686-160">Type the Surface UEFI password if you are prompted to do so.</span></span>
3. <span data-ttu-id="76686-161">单击 "**企业管理**" 页面，如图6所示。</span><span class="sxs-lookup"><span data-stu-id="76686-161">Click the **Enterprise management** page, as shown in Figure 6.</span></span>

   ![企业管理页面](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *<span data-ttu-id="76686-163">图 6.</span><span class="sxs-lookup"><span data-stu-id="76686-163">Figure 6.</span></span> <span data-ttu-id="76686-164">在 SEMM 中注册的设备上，企业管理页面显示在 Surface UEFI 中</span><span class="sxs-lookup"><span data-stu-id="76686-164">The Enterprise management page is displayed in Surface UEFI on devices enrolled in SEMM</span></span>*

4. <span data-ttu-id="76686-165">单击或按 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="76686-165">Click or press **Get Started**.</span></span>
5. <span data-ttu-id="76686-166">单击或按 "**下一步**" 以开始恢复请求过程。</span><span class="sxs-lookup"><span data-stu-id="76686-166">Click or press **Next** to begin the Recovery Request process.</span></span>
   >[!NOTE]
   ><span data-ttu-id="76686-167">恢复请求在创建后将在两个小时内过期。</span><span class="sxs-lookup"><span data-stu-id="76686-167">A Recovery Request expires two hours after it is created.</span></span> <span data-ttu-id="76686-168">如果此时未完成恢复请求，则必须重新启动恢复请求进程。</span><span class="sxs-lookup"><span data-stu-id="76686-168">If a Recovery Request is not completed in this time, you will have to restart the Recovery Request process.</span></span>
6. <span data-ttu-id="76686-169">从 "**选择 SEMM 重置密钥**" 页面上显示的证书列表中选择 " **SEMM 证书**" （如图7所示），然后单击或按 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="76686-169">Select **SEMM Certificate** from the list of certificates displayed on the **Choose a SEMM reset key** page (shown in Figure 7), and then click or press **Next**.</span></span>

   ![为你的恢复请求选择 SEMM 证书](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *<span data-ttu-id="76686-171">图 7.</span><span class="sxs-lookup"><span data-stu-id="76686-171">Figure 7.</span></span> <span data-ttu-id="76686-172">为你的恢复请求选择 SEMM 证书（重置请求）</span><span class="sxs-lookup"><span data-stu-id="76686-172">Choose SEMM Certificate for your Recovery Request (Reset Request)</span></span>*

7. <span data-ttu-id="76686-173">在 "**输入 SEMM 重置验证代码**" 页面上，你可以单击**QR 代码**或**文本**按钮以显示你的恢复请求（重置请求）（如图8所示）或**Usb**按钮以将你的恢复请求（重置请求）另存为 USB 驱动器的文件，如图9所示。</span><span class="sxs-lookup"><span data-stu-id="76686-173">On the **Enter SEMM reset verification code** page you can click the **QR Code** or **Text** buttons to display your Recovery Request (Reset Request) as shown in Figure 8, or the **USB** button to save your Recovery Request (Reset Request) as a file to a USB drive, as shown in Figure 9.</span></span>

   ![作为 QR 码显示的恢复请求](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *<span data-ttu-id="76686-175">图 8.</span><span class="sxs-lookup"><span data-stu-id="76686-175">Figure 8.</span></span> <span data-ttu-id="76686-176">作为 QR 代码显示的恢复请求（重置请求）</span><span class="sxs-lookup"><span data-stu-id="76686-176">A Recovery Request (Reset Request) displayed as a QR Code</span></span>*

   ![将恢复请求保存到 USB 驱动器](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *<span data-ttu-id="76686-178">图 9.</span><span class="sxs-lookup"><span data-stu-id="76686-178">Figure 9.</span></span> <span data-ttu-id="76686-179">将恢复请求（重置请求）保存到 USB 驱动器</span><span class="sxs-lookup"><span data-stu-id="76686-179">Save a Recovery Request (Reset Request) to a USB drive</span></span>*

   * <span data-ttu-id="76686-180">若要使用 QR 代码恢复请求（重置请求），请使用移动设备上的 QR 读取器应用读取代码。</span><span class="sxs-lookup"><span data-stu-id="76686-180">To use a QR Code Recovery Request (Reset Request), use a QR reader app on a mobile device to read the code.</span></span> <span data-ttu-id="76686-181">QR 读取器应用会将 QR 代码转换为字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="76686-181">The QR reader app will translate the QR code into an alphanumeric string.</span></span> <span data-ttu-id="76686-182">然后，你可以通过电子邮件或消息将该字符串发送到将通过 Microsoft Surface UEFI 配置器生成重置验证代码的管理员。</span><span class="sxs-lookup"><span data-stu-id="76686-182">You can then email or message that string to the administrator that will produce the reset verification code with Microsoft Surface UEFI Configurator.</span></span>
   * <span data-ttu-id="76686-183">若要使用以文件形式保存到 USB 驱动器的恢复请求（重置请求），请使用 USB 驱动器将文件传输到 Microsoft Surface UEFI 配置器将用于生成重置验证代码的计算机。</span><span class="sxs-lookup"><span data-stu-id="76686-183">To use a Recovery Request (Reset Request) saved to a USB drive as a file, use the USB drive to transfer the file to the computer where Microsoft Surface UEFI Configurator will be used to produce the Reset Verification Code.</span></span> <span data-ttu-id="76686-184">也可以从另一台设备上的 USB 驱动器复制文件，以便通过网络通过网络发送或传输。</span><span class="sxs-lookup"><span data-stu-id="76686-184">The file can also be copied from the USB drive on another device to be emailed or transferred over the network.</span></span>
   * <span data-ttu-id="76686-185">若要将恢复请求（重置请求）用作文本，只需直接在 Microsoft Surface UEFI 配置器中键入文本。</span><span class="sxs-lookup"><span data-stu-id="76686-185">To use the Recovery Request (Reset Request) as text, simply type the text directly into Microsoft Surface UEFI Configurator.</span></span>

8. <span data-ttu-id="76686-186">从另一台计算机上的 "开始" 菜单打开 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="76686-186">Open Microsoft Surface UEFI Configurator from the Start menu on another computer.</span></span>
    >[!NOTE]
    ><span data-ttu-id="76686-187">Microsoft Surface UEFI 配置程序必须在能够对 SEMM 证书的证书链进行身份验证的环境中运行。</span><span class="sxs-lookup"><span data-stu-id="76686-187">Microsoft Surface UEFI Configurator must run in an environment that is able to authenticate the certificate chain for the SEMM certificate.</span></span>
9. <span data-ttu-id="76686-188">单击**开始**。</span><span class="sxs-lookup"><span data-stu-id="76686-188">Click **Start**.</span></span>
10. <span data-ttu-id="76686-189">单击 "**恢复请求**"，如图10所示。</span><span class="sxs-lookup"><span data-stu-id="76686-189">Click **Recovery Request**, as shown in Figure 10.</span></span>

    ![启动流程以批准恢复请求](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *<span data-ttu-id="76686-191">图 10.</span><span class="sxs-lookup"><span data-stu-id="76686-191">Figure 10.</span></span> <span data-ttu-id="76686-192">单击 "恢复请求" 开始批准恢复请求的过程</span><span class="sxs-lookup"><span data-stu-id="76686-192">Click Recovery Request to begin the process to approve a Recovery Request</span></span>*

11. <span data-ttu-id="76686-193">单击 "**证书保护**" 以通过 SEMM 证书对恢复请求进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="76686-193">Click **Certificate Protection** to authenticate the Recovery Request with the SEMM certificate.</span></span>
12. <span data-ttu-id="76686-194">通过浏览找到并选择 SEMM 证书文件，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="76686-194">Browse to and select your SEMM certificate file, and then click **OK**.</span></span>
13. <span data-ttu-id="76686-195">当系统提示您输入证书密码（如图11所示）时，请键入并确认证书文件的密码，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="76686-195">When you are prompted to enter the certificate password as shown in Figure 11, type and confirm the password for the certificate file, and then click **OK**.</span></span>

    ![键入 SEMM 证书的密码](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *<span data-ttu-id="76686-197">图 11.</span><span class="sxs-lookup"><span data-stu-id="76686-197">Figure 11.</span></span> <span data-ttu-id="76686-198">键入 SEMM 证书的密码</span><span class="sxs-lookup"><span data-stu-id="76686-198">Type the password for the SEMM certificate</span></span>*

14. <span data-ttu-id="76686-199">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76686-199">Click **Next**.</span></span>
15. <span data-ttu-id="76686-200">输入恢复请求（重置请求），然后单击 "**生成**" 以创建重置验证代码（如图12所示）。</span><span class="sxs-lookup"><span data-stu-id="76686-200">Enter the Recovery Request (Reset Request), and then click **Generate** to create a reset verification code (as shown in Figure 12).</span></span>

    ![输入恢复请求](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *<span data-ttu-id="76686-202">图 12.</span><span class="sxs-lookup"><span data-stu-id="76686-202">Figure 12.</span></span> <span data-ttu-id="76686-203">输入恢复请求（重置请求）</span><span class="sxs-lookup"><span data-stu-id="76686-203">Enter the Recovery Request (Reset Request)</span></span>*

    * <span data-ttu-id="76686-204">如果在要重置的 Surface 设备上将恢复请求（重置请求）显示为文本，请使用键盘在所提供的字段中键入恢复请求（重置请求）。</span><span class="sxs-lookup"><span data-stu-id="76686-204">If you displayed the Recovery Request (Reset Request) as text on the Surface device being reset, use the keyboard to type the Recovery Request (Reset Request)  in the provided field.</span></span>
    * <span data-ttu-id="76686-205">如果你将恢复请求（重置请求）显示为 QR 代码，然后使用消息或电子邮件应用程序通过 Microsoft Surface UEFI 配置程序将代码发送到计算机，请将该代码复制并粘贴到所提供的字段中。</span><span class="sxs-lookup"><span data-stu-id="76686-205">If you displayed the Recovery Request (Reset Request) as a QR Code and then used a messaging or email application to send the code to the computer with Microsoft Surface UEFI Configurator, copy and paste the code into the provided field.</span></span>
    * <span data-ttu-id="76686-206">如果将恢复请求（重置请求）另存为 USB 驱动器的文件，请单击 "**导入**" 按钮，通过浏览找到并选择恢复请求（重置请求）文件，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="76686-206">If you saved the Recovery Request (Reset Request) as a file to a USB drive, click the **Import** button, browse to and select the Recovery Request (Reset Request) file, and then click **OK**.</span></span>

16. <span data-ttu-id="76686-207">重置验证代码显示在 Microsoft Surface UEFI 配置器中，如图13所示。</span><span class="sxs-lookup"><span data-stu-id="76686-207">The reset verification code is displayed in Microsoft Surface UEFI Configurator, as shown in Figure 13.</span></span>

    ![显示重置验证码](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *<span data-ttu-id="76686-209">图 13.</span><span class="sxs-lookup"><span data-stu-id="76686-209">Figure 13.</span></span> <span data-ttu-id="76686-210">Microsoft Surface UEFI 配置器中显示的重置验证代码</span><span class="sxs-lookup"><span data-stu-id="76686-210">The reset verification code displayed in Microsoft Surface UEFI Configurator</span></span>*

    * <span data-ttu-id="76686-211">单击 "**共享**" 按钮以通过电子邮件发送重置验证码。</span><span class="sxs-lookup"><span data-stu-id="76686-211">Click the **Share** button to send the reset verification code by email.</span></span>

17. <span data-ttu-id="76686-212">在 Surface 设备上提供的字段中输入重置验证码（如图8所示），然后单击或按 "**验证**" 以重置设备并从 SEMM 取消注册设备。</span><span class="sxs-lookup"><span data-stu-id="76686-212">Enter the reset verification code in the provided field on the Surface device (shown in Figure 8), and then click or press **Verify** to reset the device and unenroll the device from SEMM.</span></span>
18. <span data-ttu-id="76686-213">在**SEMM 重置成功**页面上单击或按 "**立即重启**" 以完成来自 SEMM 的取消注册，如图14所示。</span><span class="sxs-lookup"><span data-stu-id="76686-213">Click or press **Restart now** on the **SEMM reset successful** page to complete the unenrollment from SEMM, as shown in Figure 14.</span></span>

    ![从 SEMM 成功取消注册的示例显示](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *<span data-ttu-id="76686-215">图 14.</span><span class="sxs-lookup"><span data-stu-id="76686-215">Figure 14.</span></span> <span data-ttu-id="76686-216">成功取消注册 SEMM</span><span class="sxs-lookup"><span data-stu-id="76686-216">Successful unenrollment from SEMM</span></span>*

19. <span data-ttu-id="76686-217">单击 Microsoft Surface UEFI 配置器中的 "**结束**" 以完成恢复请求（重置请求）进程并关闭 MICROSOFT Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="76686-217">Click **End** in Microsoft Surface UEFI Configurator to complete the Recovery Request (Reset Request) process and close Microsoft Surface UEFI Configurator.</span></span>



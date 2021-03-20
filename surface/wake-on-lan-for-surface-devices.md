---
title: Surface 设备的 LAN 唤醒
description: 了解如何使用 LAN 唤醒远程唤醒设备以自动执行管理任务。
keywords: 更新， 部署， 驱动程序， wol， lan 上唤醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 3/19/2021
ms.openlocfilehash: 1fbbf899876d154469d48fa75a179196697205c1
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442152"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="2109a-104">Surface 设备的 LAN 唤醒</span><span class="sxs-lookup"><span data-stu-id="2109a-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="2109a-105">使用 Surface 以太网适配器连接到有线网络的 Surface 设备可以利用连接待机LAN 唤醒 (WOL) 连接。</span><span class="sxs-lookup"><span data-stu-id="2109a-105">Surface devices that use a Surface Ethernet adapter to connect to a wired network can take advantage of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="2109a-106">借助 WOL，你可以远程唤醒设备，并自动使用管理解决方案（如 Microsoft Endpoint Manager/Microsoft Intune）执行管理任务。</span><span class="sxs-lookup"><span data-stu-id="2109a-106">With WOL, you can remotely wake up devices and automatically perform management tasks using management solutions such as Microsoft Endpoint Manager/Microsoft Intune.</span></span>

## <a name="wol-supported-devices"></a><span data-ttu-id="2109a-107">支持 WOL 的设备</span><span class="sxs-lookup"><span data-stu-id="2109a-107">WOL-supported devices</span></span>

- <span data-ttu-id="2109a-108">Surface 以太网适配器</span><span class="sxs-lookup"><span data-stu-id="2109a-108">Surface Ethernet adapter</span></span>
- <span data-ttu-id="2109a-109">Surface USB-C 到以太网和 USB 适配器</span><span class="sxs-lookup"><span data-stu-id="2109a-109">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="2109a-110">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="2109a-110">Surface Dock 2</span></span>
- <span data-ttu-id="2109a-111">Surface Pro 6 及更高版本</span><span class="sxs-lookup"><span data-stu-id="2109a-111">Surface Pro 6 and later</span></span>
- <span data-ttu-id="2109a-112">Surface Book (代) </span><span class="sxs-lookup"><span data-stu-id="2109a-112">Surface Book (all generations)</span></span>
- <span data-ttu-id="2109a-113">Surface Laptop (所有代) </span><span class="sxs-lookup"><span data-stu-id="2109a-113">Surface Laptop (all generations)</span></span>
- <span data-ttu-id="2109a-114">Surface Go (代) </span><span class="sxs-lookup"><span data-stu-id="2109a-114">Surface Go (all generations)</span></span>
- <span data-ttu-id="2109a-115">Surface Studio 2 (请参阅附录) </span><span class="sxs-lookup"><span data-stu-id="2109a-115">Surface Studio 2 (see Appendix)</span></span>


## <a name="using-surface-wol"></a><span data-ttu-id="2109a-116">使用 Surface WOL</span><span class="sxs-lookup"><span data-stu-id="2109a-116">Using Surface WOL</span></span>

<span data-ttu-id="2109a-117">IT 管理员可以使用 LAN 请求唤醒 (包含目标计算机的 MAC 地址的) 数据包来触发设备。</span><span class="sxs-lookup"><span data-stu-id="2109a-117">IT admins can trigger devices using a wake on LAN request (magic packet) that contains the target computer’s MAC address.</span></span> <span data-ttu-id="2109a-118">若要发送神奇数据包，然后使用 WOL 唤醒设备，必须知道目标设备和以太网适配器的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="2109a-118">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="2109a-119">由于神奇数据包不使用 IP 网络协议，因此不可能使用设备的 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="2109a-119">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="2109a-120">许多管理解决方案（如 Microsoft Endpoint Configuration Manager 和第三方 Microsoft Store 应用）都提供对 WOL 的内置支持。</span><span class="sxs-lookup"><span data-stu-id="2109a-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="2109a-121">请注意，设备需要处于连接待机模式 (睡眠) 并连接到交流电源。</span><span class="sxs-lookup"><span data-stu-id="2109a-121">Note that devices need to be in Connected Standby (Sleep) mode and connected to AC power.</span></span> <span data-ttu-id="2109a-122">若要了解有关使用 Endpoint Configuration Manager 唤醒设备的信息，请参阅[Configure Wake on LAN - Configuration Manager。](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan)</span><span class="sxs-lookup"><span data-stu-id="2109a-122">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>


## <a name="to-check-wol-is-enabled-on-your-device"></a><span data-ttu-id="2109a-123">检查设备上是否已启用 WOL</span><span class="sxs-lookup"><span data-stu-id="2109a-123">To check WOL is enabled on your device</span></span>

1. <span data-ttu-id="2109a-124">在已连接以太网的设备上，选择网络适配器，然后选择"属性 **"。**</span><span class="sxs-lookup"><span data-stu-id="2109a-124">On your Ethernet connected device, select your network adapter, and then select **Properties**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Surface 以太网适配器](images/surface-ethernet.png)

2. <span data-ttu-id="2109a-126">选择 **"配置**  >  **高级"。**</span><span class="sxs-lookup"><span data-stu-id="2109a-126">Select **Configure** > **Advanced**.</span></span>
3. <span data-ttu-id="2109a-127">滚动到 **"新式待机 WoL 神奇数据包** "，并确保 **选中"** 已启用"。</span><span class="sxs-lookup"><span data-stu-id="2109a-127">Scroll to **Modern Standby WoL Magic Packet** and ensure **Enabled** is selected.</span></span>

     ![检查设备上是否已启用 WOL](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a><span data-ttu-id="2109a-129">附录：Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="2109a-129">Appendix: Surface Studio 2</span></span>

<span data-ttu-id="2109a-130">若要在 Surface Studio 2 上启用 WOL，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="2109a-130">To enable WOL on Surface Studio 2, use the following procedure.</span></span>

1. <span data-ttu-id="2109a-131">创建以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="2109a-131">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="2109a-132">运行以下命令</span><span class="sxs-lookup"><span data-stu-id="2109a-132">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a><span data-ttu-id="2109a-133">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="2109a-133">Learn more</span></span>

- [<span data-ttu-id="2109a-134">Microsoft Surface USB-C 到以太网和 USB 适配器</span><span class="sxs-lookup"><span data-stu-id="2109a-134">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [<span data-ttu-id="2109a-135">Surface USB 3.0 千兆位以太网适配器</span><span class="sxs-lookup"><span data-stu-id="2109a-135">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)

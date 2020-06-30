---
title: 配置 Surface Hub 的“开始”菜单
description: 使用 MDM 自定义 Surface Hub 上的“开始”菜单。
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.date: 08/15/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: c5b6a083d543649eab899d2fea36327d08f8bc29
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830741"
---
# <span data-ttu-id="782ea-103">配置 Surface Hub 的“开始”菜单</span><span class="sxs-lookup"><span data-stu-id="782ea-103">Configure Surface Hub Start menu</span></span>

<span data-ttu-id="782ea-104">[Windows 10 的 2018 年 1 月 17 更新](https://support.microsoft.com/help/4057144)(版本 15063.877)支持在 Surface Hub 设备上自定义“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="782ea-104">The [January 17, 2018 update to Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) enables customized Start menus on Surface Hub devices.</span></span> <span data-ttu-id="782ea-105">使用移动设备管理(MDM)应用自定义的开始菜单布局。</span><span class="sxs-lookup"><span data-stu-id="782ea-105">You apply the customized Start menu layout using mobile device management (MDM).</span></span>

<span data-ttu-id="782ea-106">如果将自定义的开始菜单布局应用到 Surface Hub，则用户无法从“开始”菜单固定、解锁或卸载应用。</span><span class="sxs-lookup"><span data-stu-id="782ea-106">When you apply a customized Start menu layout to Surface Hub, users cannot pin, unpin, or uninstall apps from Start.</span></span> 

## <span data-ttu-id="782ea-107">如何将自定义的“开始”菜单应用到 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="782ea-107">How to apply a customized Start menu to Surface Hub</span></span>

<span data-ttu-id="782ea-108">自定义的“开始”菜单是在开始菜单布局 XML 文件中定义的。</span><span class="sxs-lookup"><span data-stu-id="782ea-108">The customized Start menu is defined in a Start layout XML file.</span></span> <span data-ttu-id="782ea-109">有两个选项可用于创建开始菜单布局 XML 文件:</span><span class="sxs-lookup"><span data-stu-id="782ea-109">You have two options for creating your Start layout XML file:</span></span>

- <span data-ttu-id="782ea-110">编辑 [Surface Hub 默认开始菜单 XML](#default)</span><span class="sxs-lookup"><span data-stu-id="782ea-110">Edit the [default Surface Hub Start XML](#default)</span></span>

    <span data-ttu-id="782ea-111">- 或者 -</span><span class="sxs-lookup"><span data-stu-id="782ea-111">-or-</span></span>

- <span data-ttu-id="782ea-112">在桌面上配置所需的“开始”菜单(仅固定 Surface Hub 上可用的应用)，然后[导出布局](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout)。</span><span class="sxs-lookup"><span data-stu-id="782ea-112">Configure the desired Start menu on a desktop (pinning only apps that are available on Surface Hub), and then [export the layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span></span>

>[!TIP]
><span data-ttu-id="782ea-113">要将带 Web 链接的磁贴添加到桌面开始菜单，请转到 Microsoft Edge 中的链接，选择右上角的 `...`，再选择**将此页固定到开始菜单**。</span><span class="sxs-lookup"><span data-stu-id="782ea-113">To add a tile with a web link to your desktop start menu, go to the link in Microsoft Edge, select `...` in the top right corner, and select **Pin this page to Start**.</span></span> <span data-ttu-id="782ea-114">若要通过示例了解链接在 XML 中的显示方式，请参阅[包含 Microsoft Edge 链接的开始菜单布局](#edge)。</span><span class="sxs-lookup"><span data-stu-id="782ea-114">See [a Start layout that includes a Microsoft Edge link](#edge) for an example of how links will appear in the XML.</span></span>

<span data-ttu-id="782ea-115">若要编辑默认 XML 或导出的布局，请先熟悉[开始菜单布局 XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop)。</span><span class="sxs-lookup"><span data-stu-id="782ea-115">To edit the default XML or the exported layout, familiarize yourself with the [Start layout XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span></span> <span data-ttu-id="782ea-116">[桌面版和 Surface Hub 在开始菜单布局方面存在一些差异。](#differences)</span><span class="sxs-lookup"><span data-stu-id="782ea-116">There are a few [differences between Start layout on a deskop and a Surface Hub.](#differences)</span></span>

<span data-ttu-id="782ea-117">如果已在开始菜单布局 XML 中定义了“开始”菜单，请[创建 MDM 策略以应用该布局。](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span><span class="sxs-lookup"><span data-stu-id="782ea-117">When you have your Start menu defined in a Start layout XML, [create an MDM policy to apply the layout.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span></span>

<span id="differences" />
## <span data-ttu-id="782ea-118">Surface Hub 和桌面版在“开始”菜单方面的差异</span><span class="sxs-lookup"><span data-stu-id="782ea-118">Differences between Surface Hub and desktop Start menu</span></span>

<span data-ttu-id="782ea-119">Surface Hub 和 Windows 10 桌面版在“开始”菜单自定义方面存在以下一些主要差异:</span><span class="sxs-lookup"><span data-stu-id="782ea-119">There are a few key differences between Start menu customization for Surface Hub and a Windows 10 desktop:</span></span>

- <span data-ttu-id="782ea-120">无法在 " **DesktopApplicationTile**开始" https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) 布局 XML 中使用 DesktopApplicationTile，因为 Surface Hub 不支持 Windows 桌面应用程序（Win32）。</span><span class="sxs-lookup"><span data-stu-id="782ea-120">You cannot use **DesktopApplicationTile** (https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) in your Start layout XML because Windows desktop applications (Win32) are not supported on Surface Hub.</span></span>
- <span data-ttu-id="782ea-121">不可使用开始菜单布局来配置 Surface Hub 的任务栏和欢迎屏幕。</span><span class="sxs-lookup"><span data-stu-id="782ea-121">You cannot use the Start layout XML to configure the taskbar or the Welcome screen for Surface Hub.</span></span>  
- <span data-ttu-id="782ea-122">Surface Hub 最多支持 6 列(6 个 1x1 的磁贴)，但你**必须**定义 `GroupCellWidth=8` 列，即使 Surface Hub 仅显示 0-5 列的磁贴，而不显示第 6 列和 7 列。</span><span class="sxs-lookup"><span data-stu-id="782ea-122">Surface Hub supports a maximum of 6 columns (6 1x1 tiles), however, you **must** define `GroupCellWidth=8` even though Surface Hub will only display tiles in columns 0-5, not columns 6 and 7.</span></span>
- <span data-ttu-id="782ea-123">Surface Hub 最多支持 6 行(6 个 1x1 的磁贴)</span><span class="sxs-lookup"><span data-stu-id="782ea-123">Surface Hub supports a maximum 6 rows (6 1x1 tiles)</span></span>
- `SecondaryTile`<span data-ttu-id="782ea-124">这用于链接，且将在 Microsoft Edge 中打开链接。</span><span class="sxs-lookup"><span data-stu-id="782ea-124">, which is used for links, will open the link in Microsoft Edge.</span></span>


<span id="default" />
## <span data-ttu-id="782ea-125">示例: 默认的 Surface Hub 开始菜单布局</span><span class="sxs-lookup"><span data-stu-id="782ea-125">Example: Default Surface Hub Start layout</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

<span id="edge" />
## <span data-ttu-id="782ea-126">示例: 包含 Microsoft Edge 链接的开始菜单布局</span><span class="sxs-lookup"><span data-stu-id="782ea-126">Example: Start layout that includes a Microsoft Edge link</span></span>

<span data-ttu-id="782ea-127">此示例显示了两个分别指向网站和 .pdf 文件的链接。</span><span class="sxs-lookup"><span data-stu-id="782ea-127">This example shows a link to a website and a link to a .pdf file.</span></span> <span data-ttu-id="782ea-128">Microsoft Edge 的辅助磁贴使用 150 x 150 像素图标。</span><span class="sxs-lookup"><span data-stu-id="782ea-128">The secondary tile for Microsoft Edge uses a 150 x 150 pixel icon.</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
    <start:Tile
              AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
              Size="2x2"
              Row="0"
              Column="0"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
              Size="2x2"
              Row="0"
              Column="2"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
              Size="2x2"
              Row="0"
              Column="4"/>
    <start:Tile
              AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
              Size="2x2"
              Row="2"
              Column="0"/>
    <start:Tile
              AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
              Size="2x2" 
             Row="2"
             Column="2"/>   
  <start:SecondaryTile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
           TileID="2678823080"
           DisplayName="Bing"
           Arguments="https://www.bing.com/"
           Square150x150LogoUri="ms-appx:///"
           Wide310x150LogoUri="ms-appx:///"
           ShowNameOnSquare150x150Logo="true"
           ShowNameOnWide310x150Logo="false"
           BackgroundColor="#ffe9e7e7"
           ForegroundText="dark"
           Size="2x2"
           Column="4"
           Row="2"  />
    <start:Tile
              AppUserModelID="Microsoft.Windows.Photos_8wekyb3d8bbwe!App"
              Size="2x2"
              Row="4"
              Column="0"/>
    <start:SecondaryTile
             AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
             TileID="6153963000"
             DisplayName="cstrtqbiology.pdf"
             Arguments="-contentTile -formatVersion 0x00000003 -pinnedTimeLow 0x45b7376e -pinnedTimeHigh 0x01d2356c -securityFlags 0x00000000 -tileType 0x00000000 -url 0x0000003a https://www.ada.gov/regs2010/2010ADAStandards/Guidance_2010ADAStandards.pdf"
             Square150x150LogoUri="ms-appx:///Assets/MicrosoftEdgeSquare150x150.png"
             Wide310x150LogoUri="ms-appx:///" 
             ShowNameOnSquare150x150Logo="true"
             ShowNameOnWide310x150Logo="false"
             BackgroundColor="#ff4e4248"
             Size="4x2" 
             Row="4"
             Column="2"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

>[!NOTE]
><span data-ttu-id="782ea-129">的默认值为 `ForegroundText` 浅色; 你无需包含 `ForegroundText` 在 XML 中，除非你将值更改为深色。</span><span class="sxs-lookup"><span data-stu-id="782ea-129">The default value for `ForegroundText` is light; you don't need to include `ForegroundText` in your XML unless you're changing the value to dark.</span></span>

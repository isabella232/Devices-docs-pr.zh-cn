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
ms.openlocfilehash: ff08b8ab6e59af77761fb365980af261c47030a9
ms.sourcegitcommit: 09a47921ec2e565a92ba2baa61e181d218706ad9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2021
ms.locfileid: "11921821"
---
# <a name="configure-surface-hub-start-menu"></a>配置 Surface Hub 的“开始”菜单

[Windows 10 的 2018 年 1 月 17 更新](https://support.microsoft.com/help/4057144)(版本 15063.877)支持在 Surface Hub 设备上自定义“开始”菜单。 使用移动设备管理(MDM)应用自定义的开始菜单布局。

如果将自定义的开始菜单布局应用到 Surface Hub，则用户无法从“开始”菜单固定、解锁或卸载应用。 

## <a name="how-to-apply-a-customized-start-menu-to-surface-hub"></a>如何将自定义的“开始”菜单应用到 Surface Hub

自定义的“开始”菜单是在开始菜单布局 XML 文件中定义的。 有两个选项可用于创建开始菜单布局 XML 文件:

- 编辑 [Surface Hub 默认开始菜单 XML](#default)

    - 或者 -

- 在桌面上配置所需的“开始”菜单(仅固定 Surface Hub 上可用的应用)，然后[导出布局](/windows/configuration/customize-and-export-start-layout#export-the-start-layout)。

>[!TIP]
>要将带 Web 链接的磁贴添加到桌面开始菜单，请转到 Microsoft Edge 中的链接，选择右上角的 `...`，再选择**将此页固定到开始菜单**。 若要通过示例了解链接在 XML 中的显示方式，请参阅[包含 Microsoft Edge 链接的开始菜单布局](#edge)。

若要编辑默认 XML 或导出的布局，请先熟悉[开始菜单布局 XML](/windows/configuration/start-layout-xml-desktop)。 [桌面版和 Surface Hub 在开始菜单布局方面存在一些差异。](#differences)

如果已在开始菜单布局 XML 中定义了“开始”菜单，请[创建 MDM 策略以应用该布局。](/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)

<span id="differences" />

## <a name="differences-between-surface-hub-and-desktop-start-menu"></a>Surface Hub 和桌面版在“开始”菜单方面的差异

Surface Hub 和 Windows 10 桌面版在“开始”菜单自定义方面存在以下一些主要差异:

- 不能在"开始"屏幕布局 XML 中使用**[DesktopApplicationTile，Windows](/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile)** Win32 (不支持) 桌面应用程序Surface Hub。
- 不可使用开始菜单布局来配置 Surface Hub 的任务栏和欢迎屏幕。  
- "开始"屏幕布局策略应仅分配给设备，而非用户。
- 策略中要使用的 OMA-URI 设置是 `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- Surface Hub 最多支持 6 列(6 个 1x1 的磁贴)，但你**必须**定义 `GroupCellWidth=8` 列，即使 Surface Hub 仅显示 0-5 列的磁贴，而不显示第 6 列和 7 列。
- Surface Hub 最多支持 6 行(6 个 1x1 的磁贴)
- `SecondaryTile`这用于链接，且将在 Microsoft Edge 中打开链接。


<span id="default" />

## <a name="example-default-surface-hub-start-layout"></a>示例: 默认的 Surface Hub 开始菜单布局

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:DesktopApplicationTile
            DesktopApplicationID="MSEdge"
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

## <a name="example-start-layout-that-includes-a-microsoft-edge-link"></a>示例: 包含 Microsoft Edge 链接的开始菜单布局

此示例显示了两个分别指向网站和 .pdf 文件的链接。 用户辅助磁贴Microsoft Edge 150 x 150 像素图标。

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
          <start:DesktopApplicationTile
              DesktopApplicationID="MSEdge"
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
>的默认值为 light;除非将该值更改为深色，否则不需要包括在 `ForegroundText` `ForegroundText` XML 中。

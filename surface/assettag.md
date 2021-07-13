---
title: Surface 资源标记工具
description: 本主题介绍如何使用 Surface 资源标记工具。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.date: 06/29/2021
manager: laurawi
ms.openlocfilehash: b130f6b0bf52dc1c3a28231a2330cae51a5ef44a
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643828"
---
# <a name="surface-asset-tag-tool"></a>Surface 资源标记工具

Surface Asset Tag 是 CLI (的) 接口，可用于查看、分配和修改 Surface 设备的已分配资源标记值。 它适用于 Surface Pro 3 以及所有较新的 Surface 设备。

## <a name="system-requirements"></a>系统要求

- Surface Pro 3 或更高版本

- UEFI 固件版本 3.9.150.0 或更高版本

## <a name="using-surface-asset-tag"></a>使用 Surface 资源标记

若要运行 Surface Asset Tag：

1. 在 Surface 设备上，从[Microsoft](https://www.microsoft.com/download/details.aspx?id=46703)下载中心Tag.zipSurface **Asset** Tag.zip，提取 zip 文件，将 AssetTag.exe 保存在所需的文件夹 (中，本示例中为 C：\\assets) 。

    > [!NOTE]
    > 对于Surface Pro X，请使用 ZIP **AssetTag_x86**名为 AssetTag_x86 的应用程序。

2. 以管理员角色打开命令控制台，AssetTag.exe输入该工具的完整路径。

3. 重新启动 Surface。

    > [!NOTE]
    > 设置资源标记后，需要再次重新启动，然后才能在 WMI 中显示。

### <a name="asset-tag-tool-commands"></a>资产标记工具命令

在下面的示例中，AssetTag.exe C：\assets 文件保存在本地 (的) 。

若要获取建议的资产标记，请运行**AssetTag -g：**

```console
C:\assets\AssetTag.exe -g
```

若要清除建议的资产标记，请运行 **AssetTag -s**：

```console
C:\assets\AssetTag.exe -s
```

若要设置建议的资产标记，请运行 **AssetTag -s testassettag12**：

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>资源标记值必须包含 1 到 36 个字符。 有效字符包括 A-Z、a-z、0-9、period (.) 和连 (-) 。

## <a name="managing-asset-tags"></a>管理资产标记

可以在"设备信息" (控制面板"下查看 UEFI 设置中的现有资产标记 **>>高级**启动>立即重启) 

下图显示了在 Surface Go 上运行资产标记工具的结果。

![在 Surface Go 上运行 Surface 资源标记工具的结果。](images/assettag-fig1.png)

> **图 1.** 在 Surface Go 上运行 Surface 资源标记工具的结果

或者，可以使用 WMI 查询设备上现有的资源标记：

 (Get-WmiObject -query "Select * from Win32_SystemEnclosure") 

### <a name="example"></a>示例

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a>使用 PowerShell

您可以使用下面的脚本作为获取建议值并解释任何错误的方法。

```powershell
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim("\`r\`n")

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output ("Good Tag = " + $asset\_tag)  
} else {  
Write-Output (  
"Failure: Code = " + $asset\_tag\_return\_code +  
"Tag = " + $asset\_tag +  
"Message = " + $error\_message)

}
```

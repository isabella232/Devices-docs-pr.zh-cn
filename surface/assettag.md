---
title: Surface 资产标签工具
description: 本主题介绍了如何使用 Surface 资产标签工具。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.openlocfilehash: ca6a71a6b864692953fcd96eb687c2752527c9f5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830799"
---
# Surface 资产标签工具

Surface 资产标记是一个命令行界面（CLI）实用工具，允许你查看、分配和修改 Surface 设备的已分配资产标记值。 它适用于 Surface Pro 3 和所有较新的 Surface 设备。

##  <a name="system-requirements"></a>系统要求

- Surface Pro 3 或更高版本

- UEFI 固件版本3.9.150.0 或更高版本

##  <a name="using-surface-asset-tag-"></a>使用 Surface 资产标签 

要运行 Surface 资产标签，请执行以下操作：

1.  在 Surface 设备上，从[Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=46703)下载**Surface 资产 Tag.zip** ，提取 zip 文件，然后将 AssetTag.exe 保存在所需的文件夹中（在此示例中，C:\\assets）。

    > [!NOTE]
    > 对于 Surface Pro X，在 ZIP 文件中使用名为**AssetTag_x86**的应用程序。 

2.  以管理员身份打开命令控制台并运行 AssetTag.exe，输入工具的完整路径。

3.  重启图面。

###  <a name="asset-tag-tool-commands"></a>资产标签工具命令   
在以下示例中，AssetTag.exe 保存在本地计算机（C:\assets）的目录中。 

若要获取建议的资产标签，请运行 AssetTag-g。

**示例**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 若要清除建议的资产标签，请运行 AssetTag-s。
 
 **示例**
 
   ```
C:\assets\AssetTag.exe -s
  ```
若要设置建议的资产标签，请运行 AssetTag-s testassettag12。

**示例**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>资产标签值必须包含1到36个字符。 有效字符包括 A-z、A-z、0-9、句号（.）和连字符（-）。


##  <a name="managing-asset-tags"></a>管理资产标签

你可以在 "设备信息" （**控制面板 > 恢复 > 高级启动 > "立即重启**"）下的 "UEFI 设置" 中查看现有资产标记。

下图显示了在 Surface Go 上运行资产标签工具的结果。

![图面资产标签工具在图面上的运行结果。
](images/assettag-fig1.png)

> **图 1.** 图面资产标签工具在 Surface Go 上的运行结果

或者，您可以使用 WMI 查询设备上的现有资产标记：

（WmiObject-query "Select * from Win32_SystemEnclosure"）

**示例**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
###  <a name="using-powershell"></a>使用 PowerShell

你可以使用下面的脚本作为获取建议值和解释任何错误的方法。

 ```
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim(“\`r\`n”)

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output (“Good Tag = ” + $asset\_tag)  
} else {  
Write-Output (  
“Failure: Code = ” + $asset\_tag\_return\_code +  
“Tag = ” + $asset\_tag +  
“Message = ” + $error\_message)

}
 ```

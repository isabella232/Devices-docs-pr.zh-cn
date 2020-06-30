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
# <span data-ttu-id="a5f2c-103">Surface 资产标签工具</span><span class="sxs-lookup"><span data-stu-id="a5f2c-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="a5f2c-104">Surface 资产标记是一个命令行界面（CLI）实用工具，允许你查看、分配和修改 Surface 设备的已分配资产标记值。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="a5f2c-105">它适用于 Surface Pro 3 和所有较新的 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <span data-ttu-id="a5f2c-106">系统要求</span><span class="sxs-lookup"><span data-stu-id="a5f2c-106">System requirements</span></span>

- <span data-ttu-id="a5f2c-107">Surface Pro 3 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a5f2c-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="a5f2c-108">UEFI 固件版本3.9.150.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a5f2c-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <span data-ttu-id="a5f2c-109">使用 Surface 资产标签</span><span class="sxs-lookup"><span data-stu-id="a5f2c-109">Using Surface Asset Tag</span></span> 

<span data-ttu-id="a5f2c-110">要运行 Surface 资产标签，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a5f2c-110">To run Surface Asset Tag:</span></span>

1.  <span data-ttu-id="a5f2c-111">在 Surface 设备上，从[Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=46703)下载**Surface 资产 Tag.zip** ，提取 zip 文件，然后将 AssetTag.exe 保存在所需的文件夹中（在此示例中，C:\\assets）。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703), extract the zip file, and save AssetTag.exe in desired folder (in this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a5f2c-112">对于 Surface Pro X，在 ZIP 文件中使用名为**AssetTag_x86**的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span> 

2.  <span data-ttu-id="a5f2c-113">以管理员身份打开命令控制台并运行 AssetTag.exe，输入工具的完整路径。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3.  <span data-ttu-id="a5f2c-114">重启图面。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-114">Restart Surface.</span></span>

### <span data-ttu-id="a5f2c-115">资产标签工具命令</span><span class="sxs-lookup"><span data-stu-id="a5f2c-115">Asset Tag tool commands</span></span>   
<span data-ttu-id="a5f2c-116">在以下示例中，AssetTag.exe 保存在本地计算机（C:\assets）的目录中。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-116">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span> 

<span data-ttu-id="a5f2c-117">若要获取建议的资产标签，请运行 AssetTag-g。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-117">To get the proposed asset tag, run AssetTag -g.</span></span>

**<span data-ttu-id="a5f2c-118">示例</span><span class="sxs-lookup"><span data-stu-id="a5f2c-118">Example</span></span>**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 <span data-ttu-id="a5f2c-119">若要清除建议的资产标签，请运行 AssetTag-s。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-119">To clear the proposed asset tag, run AssetTag -s.</span></span>
 
 **<span data-ttu-id="a5f2c-120">示例</span><span class="sxs-lookup"><span data-stu-id="a5f2c-120">Example</span></span>**
 
   ```
C:\assets\AssetTag.exe -s
  ```
<span data-ttu-id="a5f2c-121">若要设置建议的资产标签，请运行 AssetTag-s testassettag12。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-121">To set the proposed asset tag, run AssetTag -s testassettag12.</span></span>

**<span data-ttu-id="a5f2c-122">示例</span><span class="sxs-lookup"><span data-stu-id="a5f2c-122">Example</span></span>**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="a5f2c-123">资产标签值必须包含1到36个字符。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-123">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="a5f2c-124">有效字符包括 A-z、A-z、0-9、句号（.）和连字符（-）。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-124">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>


## <span data-ttu-id="a5f2c-125">管理资产标签</span><span class="sxs-lookup"><span data-stu-id="a5f2c-125">Managing asset tags</span></span>

<span data-ttu-id="a5f2c-126">你可以在 "设备信息" （**控制面板 > 恢复 > 高级启动 > "立即重启**"）下的 "UEFI 设置" 中查看现有资产标记。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-126">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="a5f2c-127">下图显示了在 Surface Go 上运行资产标签工具的结果。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-127">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![<span data-ttu-id="a5f2c-128">图面资产标签工具在图面上的运行结果。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-128">Results of running Surface Asset Tag tool on Surface Go.</span></span>
](images/assettag-fig1.png)

> **<span data-ttu-id="a5f2c-129">图 1.</span><span class="sxs-lookup"><span data-stu-id="a5f2c-129">Figure 1.</span></span>** <span data-ttu-id="a5f2c-130">图面资产标签工具在 Surface Go 上的运行结果</span><span class="sxs-lookup"><span data-stu-id="a5f2c-130">Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id="a5f2c-131">或者，您可以使用 WMI 查询设备上的现有资产标记：</span><span class="sxs-lookup"><span data-stu-id="a5f2c-131">Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id="a5f2c-132">（WmiObject-query "Select \* from Win32_SystemEnclosure"）</span><span class="sxs-lookup"><span data-stu-id="a5f2c-132">(Get-WmiObject -query “Select \* from Win32_SystemEnclosure”)</span></span>

**<span data-ttu-id="a5f2c-133">示例</span><span class="sxs-lookup"><span data-stu-id="a5f2c-133">Example</span></span>**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### <span data-ttu-id="a5f2c-134">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5f2c-134">Using PowerShell</span></span>

<span data-ttu-id="a5f2c-135">你可以使用下面的脚本作为获取建议值和解释任何错误的方法。</span><span class="sxs-lookup"><span data-stu-id="a5f2c-135">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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

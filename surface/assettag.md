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
# <a name="surface-asset-tag-tool"></a><span data-ttu-id="163f2-103">Surface 资源标记工具</span><span class="sxs-lookup"><span data-stu-id="163f2-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="163f2-104">Surface Asset Tag 是 CLI (的) 接口，可用于查看、分配和修改 Surface 设备的已分配资源标记值。</span><span class="sxs-lookup"><span data-stu-id="163f2-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="163f2-105">它适用于 Surface Pro 3 以及所有较新的 Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="163f2-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="163f2-106">系统要求</span><span class="sxs-lookup"><span data-stu-id="163f2-106">System requirements</span></span>

- <span data-ttu-id="163f2-107">Surface Pro 3 或更高版本</span><span class="sxs-lookup"><span data-stu-id="163f2-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="163f2-108">UEFI 固件版本 3.9.150.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="163f2-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <a name="using-surface-asset-tag"></a><span data-ttu-id="163f2-109">使用 Surface 资源标记</span><span class="sxs-lookup"><span data-stu-id="163f2-109">Using Surface Asset Tag</span></span>

<span data-ttu-id="163f2-110">若要运行 Surface Asset Tag：</span><span class="sxs-lookup"><span data-stu-id="163f2-110">To run Surface Asset Tag:</span></span>

1. <span data-ttu-id="163f2-111">在 Surface 设备上，从[Microsoft](https://www.microsoft.com/download/details.aspx?id=46703)下载中心Tag.zipSurface **Asset** Tag.zip，提取 zip 文件，将 AssetTag.exe 保存在所需的文件夹 (中，本示例中为 C：\\assets) 。</span><span class="sxs-lookup"><span data-stu-id="163f2-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download  Center](https://www.microsoft.com/download/details.aspx?id=46703),  extract the zip file, and save AssetTag.exe in desired folder (in  this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="163f2-112">对于Surface Pro X，请使用 ZIP **AssetTag_x86**名为 AssetTag_x86 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="163f2-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span>

2. <span data-ttu-id="163f2-113">以管理员角色打开命令控制台，AssetTag.exe输入该工具的完整路径。</span><span class="sxs-lookup"><span data-stu-id="163f2-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3. <span data-ttu-id="163f2-114">重新启动 Surface。</span><span class="sxs-lookup"><span data-stu-id="163f2-114">Restart Surface.</span></span>

    > [!NOTE]
    > <span data-ttu-id="163f2-115">设置资源标记后，需要再次重新启动，然后才能在 WMI 中显示。</span><span class="sxs-lookup"><span data-stu-id="163f2-115">After setting the asset tag, a second reboot is required before it appears in WMI.</span></span>

### <a name="asset-tag-tool-commands"></a><span data-ttu-id="163f2-116">资产标记工具命令</span><span class="sxs-lookup"><span data-stu-id="163f2-116">Asset Tag tool commands</span></span>

<span data-ttu-id="163f2-117">在下面的示例中，AssetTag.exe C：\assets 文件保存在本地 (的) 。</span><span class="sxs-lookup"><span data-stu-id="163f2-117">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span>

<span data-ttu-id="163f2-118">若要获取建议的资产标记，请运行**AssetTag -g：**</span><span class="sxs-lookup"><span data-stu-id="163f2-118">To get the proposed asset tag, run **AssetTag -g**:</span></span>

```console
C:\assets\AssetTag.exe -g
```

<span data-ttu-id="163f2-119">若要清除建议的资产标记，请运行 **AssetTag -s**：</span><span class="sxs-lookup"><span data-stu-id="163f2-119">To clear the proposed asset tag, run **AssetTag -s**:</span></span>

```console
C:\assets\AssetTag.exe -s
```

<span data-ttu-id="163f2-120">若要设置建议的资产标记，请运行 **AssetTag -s testassettag12**：</span><span class="sxs-lookup"><span data-stu-id="163f2-120">To set the proposed asset tag, run **AssetTag -s testassettag12**:</span></span>

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="163f2-121">资源标记值必须包含 1 到 36 个字符。</span><span class="sxs-lookup"><span data-stu-id="163f2-121">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="163f2-122">有效字符包括 A-Z、a-z、0-9、period (.) 和连 (-) 。</span><span class="sxs-lookup"><span data-stu-id="163f2-122">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>

## <a name="managing-asset-tags"></a><span data-ttu-id="163f2-123">管理资产标记</span><span class="sxs-lookup"><span data-stu-id="163f2-123">Managing asset tags</span></span>

<span data-ttu-id="163f2-124">可以在"设备信息" (控制面板"下查看 UEFI 设置中的现有资产标记 **>>高级**启动>立即重启) </span><span class="sxs-lookup"><span data-stu-id="163f2-124">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="163f2-125">下图显示了在 Surface Go 上运行资产标记工具的结果。</span><span class="sxs-lookup"><span data-stu-id="163f2-125">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![在 Surface Go 上运行 Surface 资源标记工具的结果。](images/assettag-fig1.png)

> **<span data-ttu-id="163f2-127&quot;>图 1.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;163f2-127&quot;>Figure 1.</span></span>** <span data-ttu-id=&quot;163f2-128&quot;>在 Surface Go 上运行 Surface 资源标记工具的结果</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;163f2-128&quot;>Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id=&quot;163f2-129&quot;>或者，可以使用 WMI 查询设备上现有的资源标记：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;163f2-129&quot;>Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id=&quot;163f2-130&quot;> (Get-WmiObject -query &quot;Select\ * from Win32_SystemEnclosure") </span><span class="sxs-lookup"><span data-stu-id="163f2-130">(Get-WmiObject -query "Select \* from Win32_SystemEnclosure")</span></span>

### <a name="example"></a><span data-ttu-id="163f2-131">示例</span><span class="sxs-lookup"><span data-stu-id="163f2-131">Example</span></span>

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a><span data-ttu-id="163f2-132">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="163f2-132">Using PowerShell</span></span>

<span data-ttu-id="163f2-133">您可以使用下面的脚本作为获取建议值并解释任何错误的方法。</span><span class="sxs-lookup"><span data-stu-id="163f2-133">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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

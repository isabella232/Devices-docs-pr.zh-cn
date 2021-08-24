---
title: 使用 Microsoft Endpoint Configuration Manager 通过 SEMM 管理设备
description: 了解如何使用 Endpoint Configuration Manager 在 SEMM Enterprise管理 (Microsoft Surface) 管理模式。
keywords: 注册， 更新， 脚本， 设置
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 3a70f08ded5ad19b8bc2dc8a7e4fe6d85d972c43
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911617"
---
# <a name="use-microsoft-endpoint-configuration-manager-to-manage-devices-with-semm"></a>使用 Microsoft Endpoint Configuration Manager 通过 SEMM 管理设备

Microsoft Surface Enterprise 管理模式 (Surface UEFI) SEMM 管理模式功能使管理员能够管理和帮助保护 Surface UEFI 设置的配置。 对于大多数组织来说，此过程是通过使用 Microsoft Surface UEFI Windows工具 (.msi) 安装程序程序包完成的。 然后，运行这些程序包或将其部署到客户端 Surface 设备，以在 SEMM 中注册设备并更新 Surface UEFI 设置配置。

对于具有Microsoft Endpoint Configuration Manager组织，有一个替代方法，可以按照使用 Microsoft Surface UEFI 配置.msi部署和管理 SEMM 的过程。 Microsoft Surface UEFI 管理器是轻型安装程序，可在设备上使用 SEMM 管理所需的程序集。 通过使用 Microsoft Surface UEFI 管理器在托管客户端上安装这些程序集，SEMM 可以通过 Configuration Manager 通过 PowerShell 脚本进行管理，并部署为应用程序。 通过此过程，SEMM 管理在 Configuration Manager 内执行，这样就无需使用外部 Microsoft Surface UEFI 配置器工具。

> [!Note]
> 尽管本文中介绍的过程可能用于早期版本的 Endpoint Configuration Manager 或其他第三方管理解决方案，但只有 Endpoint Configuration Manager 的 Current Branch 才支持使用 Microsoft Surface UEFI 管理器和 PowerShell 管理 SEMM。

#### <a name="prerequisites"></a>系统必备

在开始本文中概述的过程之前，请熟悉以下技术和工具：

* [Surface UEFI](manage-surface-uefi-settings.md)
* [Surface 企业管理模式 (SEMM)](surface-enterprise-management-mode.md)
* [PowerShell 脚本](/powershell)
* [使用 Configuration Manager 部署应用程序](/mem/configmgr/apps/deploy-use/deploy-applications)


> [!Note]
> 你还需要访问打算用于保护 SEMM 的证书。 有关此证书的要求的详细信息，请参阅 Surface [Enterprise 管理模式证书要求](surface-enterprise-management-mode.md#surface-enterprise-management-mode-certificate-requirements)。
> 
> 此证书应保留在安全的位置并正确备份，这一点非常重要。 如果此证书丢失或不可用，则不能重置 Surface UEFI、更改托管的 Surface UEFI 设置，或者从已注册的 Surface 设备中删除 SEMM。

#### <a name="download-microsoft-surface-uefi-manager"></a>下载 Microsoft Surface UEFI 管理器

使用 Configuration Manager 管理 SEMM 需要在每台客户端 Surface 设备上安装 Microsoft Surface UEFI 管理器。 你可以从 Microsoft 下载中心的 Surface Tools for [IT](https://www.microsoft.com/download/details.aspx?id=46703) (SurfaceUEFIManager.msi) 下载 Microsoft Surface UEFI 管理器。

#### <a name="download-semm-scripts-for-configuration-manager"></a>下载 Configuration Manager 的 SEMM 脚本

在客户端 Surface 设备上安装 Microsoft Surface UEFI 管理器后，可以使用 PowerShell 脚本部署和管理 SEMM。 通过从适用于 IT 的 Surface Tools SEMM_PowerShell.zip获取 [SEMM](https://www.microsoft.com/download/details.aspx?id=46703) 管理脚本示例。

## <a name="deploy-microsoft-surface-uefi-manager"></a>部署 Microsoft Surface UEFI 管理器

部署 Microsoft Surface UEFI 管理器是典型的应用程序部署。 Microsoft Surface UEFI 管理器安装程序文件是标准 Windows安装程序文件，可以使用标准[安静选项进行安装](https://msdn.microsoft.com/library/windows/desktop/aa367988)。

安装 Microsoft Surface UEFI 管理器的命令如下所示。

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

用于卸载 Microsoft Surface UEFI 管理器的命令如下所示。

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

若要创建新应用程序并部署到包含 Surface 设备的集合，请执行以下步骤：

1. 从"开始"屏幕或 **"** 开始" **菜单打开** Configuration Manager 控制台。
2. 选择 **窗口** 左下角的软件库。
3. 展开"**软件库"** 的"应用程序管理"节点，然后选择"应用程序 **"。**
4. 选择 **窗口顶部的** "主页 **"** 选项卡下的"创建应用程序"按钮。 这将启动"创建应用程序向导"。
5. "创建应用程序向导"提供了一系列步骤：

   * **常规** - **默认情况下选择"从安装** 文件自动检测此应用程序的信息"选项。 在"**类型**"字段中 **，Windows安装程序 (.msi文件**) 也默认选中。 选择 **"浏览**"导航到**并选择**"SurfaceUEFIManagerSetup.msi"，然后选择"下一**步"。**
   
      > [!Note]
      > 文件SurfaceUEFIManagerSetup.msi位于网络共享上，且位于不包含其他文件的文件夹中。 不能使用本地文件位置。

   * **导入信息**– 创建应用程序向导将分析.msi文件并读取**应用程序名称和****产品代码**。 SurfaceUEFIManagerSetup.msi应列为"内容文件"行下的唯一文件，如图**** 1 所示。 选择 **"下一** 步"继续。

      ![Surface UEFI 管理器设置中的信息会自动进行分析。](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *图 1. 自动分析来自 Microsoft Surface UEFI 管理器设置的信息*

   * **常规** 信息 – 可以修改应用程序名称和有关发布者和版本的信息，或在此页面上添加注释。 Microsoft Surface UEFI 管理器的安装命令显示在"安装程序"字段中。 为系统安装的默认安装行为将允许 Microsoft Surface UEFI 管理器安装 SEMM 所需的程序集，即使用户未登录到 Surface 设备。 选择 **"下一** 步"继续。
   * **摘要**- "导入信息"步骤中分析**** 的信息以及"常规信息"步骤中的选择**** 将显示在此页面上。 选择 **"** 下一步"以确认您的选择并创建应用程序。
   * **进度** – 在导入应用程序并添加到软件库时显示进度栏和状态。
   * **完成** – 应用程序创建过程完成后，将显示应用程序创建成功确认。 选择 **"** 关闭"以完成"创建应用程序向导"。

在 Configuration Manager 中创建应用程序后，你可以将其分发到分发点，并将其部署到集合（包括 Surface 设备）。 此应用程序不会在 Surface 设备上安装或启用 SEMM。 它仅提供使用 PowerShell 脚本启用 SEMM 所需的程序集。

如果不想在不会使用 SEMM 管理的设备上安装 Microsoft Surface UEFI 管理器程序集，可以将 Microsoft Surface UEFI 管理器配置为 SEMM Configuration Manager 脚本的依赖项。 本文稍后的部署 [SEMM Configuration Manager 脚本](#deploy-semm-configuration-manager-scripts) 一节将介绍此方案。

## <a name="create-or-modify-the-semm-configuration-manager-scripts"></a>创建或修改 SEMM Configuration Manager 脚本

在设备上安装所需程序集后，在 SEMM 中注册设备并配置 Surface UEFI 的过程通过 PowerShell 脚本完成，并部署为具有 Configuration Manager 的脚本应用程序。 可以修改这些脚本以满足组织和环境的需求。 例如，你可以为不同部门或角色中的托管 Surface 设备创建多个配置。 可以从本文开头的先决条件部分的链接下载 SEMM 和 Configuration Manager 脚本[](#prerequisites)的示例。

需要两个主要脚本才能使用 Configuration Manager 执行 SEMM 部署：

* **ConfigureSEMM.ps1** – 使用此脚本为具有所需 Surface UEFI 设置的 Surface 设备创建配置包，以将指定的设置应用于 Surface 设备、在 SEMM 中注册设备，以及设置用于标识在 SEMM 中注册设备的注册表项。
* **ResetSEMM.ps1** – 使用此脚本在 Surface 设备上重置 SEMM，这会从 SEMM 取消注册它并删除对 Surface UEFI 设置的控制。

示例脚本包括如何设置 Surface UEFI 设置以及如何控制这些设置的权限的示例。 可修改这些设置以确保 Surface UEFI 安全，并可根据你的环境需求设置 Surface UEFI 设置。 本文的以下各节将ConfigureSEMM.ps1脚本，并探索您需要对脚本所做的修改以满足您的要求。

> [!NOTE]
> 在将 SEMM Configuration Manager 脚本和导出的 SEMM 证书文件 (.pfx) 添加到 Configuration Manager 之前，它们应放在没有其他文件的同一文件夹中。

### <a name="specify-certificate-and-package-names"></a>指定证书和程序包名称

需要修改的脚本的第一个区域是指定和加载 SEMM 证书的部分，同时还指示 SurfaceUEFIManager 版本以及 SEMM 配置包和 SEMM 重置程序包的名称。 证书名称和 SurfaceUEFIManager 版本在脚本第 56 至 73 行ConfigureSEMM.ps1指定。

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

将 $certName 变量的**FabrikamSEMMSample.pfx**值替换为第 58 行的 SEMM 证书文件的名称。 **** 脚本将在脚本所在的文件夹中 (一个名为 Config) 的工作目录，然后将证书文件复制到此工作目录。

所有者程序包和重置程序包也将在 Config 目录中创建，并保留由脚本生成的 Surface UEFI 设置和权限的配置。

在行 73 中，将****$password 的值从**1234**替换为证书文件的密码。 如果不需要密码，请删除 **1234** 文本。

> [!Note]
> 在 SEMM 中注册设备需要证书指纹的最后两个字符。 此脚本会向用户显示这些数字，这允许用户或技术人员在系统重新启动之前记录这些数字以在 SEMM 中注册设备。 脚本使用第 150-155 行找到的以下代码来完成此操作。

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

有权访问证书文件 (.pfx) 可通过在 CertMgr 中打开 .pfx 文件来随时读取指纹。 若要使用 CertMgr 查看指纹，请按照以下过程操作：

1. 右键单击 .pfx 文件，然后选择"打开 **"。**
2. 展开导航窗格中的文件夹。
3. 选择 **"证书"。**
4. 右键单击主窗格中的证书，然后选择"打开 **"。**
5. 选择" **详细信息"** 选项卡。
6. **必须在** " **显示"** 下拉菜单中选择"全部"或 **"仅属性** "。
7. 选择字段 **Thumbprint**。

> [!NOTE]
> 还必须在 ResetSEMM.ps1 脚本的这一部分中输入 SEMM 证书名称和密码，以便 Configuration Manager 通过卸载操作从设备中删除 SEMM。

### <a name="configure-permissions"></a>配置权限

要指定 Surface UEFI 配置的脚本的第一个区域是 **"配置权限"** 区域。 此区域从示例脚本的第 210 行开始，注释为 **"** 配置权限"，然后继续到第 247 行。 以下代码片段首先设置所有 Surface UEFI 设置的权限，以便仅由 SEMM 修改这些设置，然后添加显式权限以允许本地用户修改 Surface UEFI 密码、TPM 以及前置和后置摄像头。

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

每个 **$uefiV 2** 变量通过设置名称或 ID 来标识 Surface UEFI 设置，然后将权限配置为下列值之一：

* **$ownerOnly** - 仅向 SEMM 授予修改此设置的权限。
* **$ownerAndLocalUser** – 修改此设置的权限授予本地用户启动到 Surface UEFI 以及 SEMM。

有关 Surface UEFI 的可用设置名称和设置[名称和 ID 部分](#settings-names-and-ids)的信息。

### <a name="configure-settings"></a>配置设置

将在其中指定 Surface UEFI 配置的脚本的第二个区域是 ConfigureSEMM.ps1 脚本的 Configure**设置**区域，用于配置是启用还是禁用每个设置。 示例脚本包含用于将所有设置设置为其默认值的说明。 然后，该脚本会提供明确说明，以禁用 IPv6 进行 PXE 启动，并保留 Surface UEFI 管理员密码不变。 您可以在示例脚本的第 291**行至第**335 行找到以 # Configure 设置 注释开头的区域。 区域如下所示。

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

与脚本的"配置权限"**** 部分中设置的权限类似，每个 Surface UEFI 设置的配置通过定义 **$uefiV 2**变量执行。 对于定义 **$uefiV 2** 变量的每一行，Surface UEFI 设置都通过设置名称或 ID 进行标识，并且配置的值设置为 **Enabled** 或 **Disabled**。

如果不希望更改 Surface UEFI 设置的配置，例如，为了确保不会通过将所有 Surface UEFI 设置重置为默认值的操作来清除 Surface UEFI 管理员密码，可以使用 **ClearConfiguredValue () ** 强制不更改此设置。 在示例脚本中，这用于第 323 行以防止清除 Surface UEFI 管理员密码，该密码在示例脚本中通过设置 ID **501 标识**。

有关 Surface UEFI 的可用设置名称和 ID 的信息，请参阅本文设置[名称和 ID 部分](#settings-names-and-ids)。

### <a name="settings-registry-key"></a>设置注册表项

为了标识 Configuration Manager 的已注册系统，ConfigureSEMM.ps1脚本会写入注册表项，这些注册表项可用于将已注册的系统标识为已经与 SEMM 配置脚本一起安装。 可以在以下位置找到这些键。

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

以下代码片段（位于第 380-477 行）用于编写这些注册表项。

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <a name="settings-names-and-ids"></a>设置名称和 ID

若要为 Surface UEFI 设置配置 Surface UEFI 设置或权限，必须通过设置名称或设置 ID 来引用每个设置。 每次更新 Surface UEFI 时，可能会添加新设置。 在适用于 IT ShowSettingsOptions.ps1 (运行SEMM_Powershell.zip脚本脚本) [提供了](https://www.microsoft.com/download/details.aspx?id=46703) 可用设置的详细信息。 运行 ShowSettingsOptions.ps1 的计算机必须安装 Microsoft Surface UEFI 管理器，但脚本不需要 Surface 设备。


## <a name="deploy-semm-configuration-manager-scripts"></a>部署 SEMM Configuration Manager 脚本

准备好在客户端设备上配置和启用 SEMM 后，下一步是在 Configuration Manager 中将这些脚本添加为应用程序。 在打开 Configuration Manager 之前，请确保以下文件在不包含其他文件的共享文件夹中：

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* 例如，SEMM 证书 (例如 SEMMCertificate.pfx) 

SEMM Configuration Manager 脚本将作为脚本应用程序添加到 Configuration Manager。 用于安装 SEMM 的命令ConfigureSEMM.ps1如下所示。

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

用于卸载 SEMM 的命令ResetSEMM.ps1如下所示。

`Powershell.exe -file ".\ResetSEMM.ps1"`

若要将 SEMM Configuration Manager 脚本作为应用程序添加到 Configuration Manager，请使用以下过程：

1. 使用本文前面部署 [Microsoft Surface UEFI 管理器](#deploy-microsoft-surface-uefi-manager) 部分的步骤 1 到步骤 5 启动创建应用程序向导。

2. 继续执行"创建应用程序向导"，如下所示：

   - **常规**–**选择"手动指定应用程序信息"，** 然后选择"下一**步"。**

   - **常规信息** – 输入应用程序名称 (例如 SEMM) ，以及你需要的其他任何信息，例如此页面上的发布者、版本或注释。 选择 **"下一** 步"继续。

   - **应用程序** 目录 – 此页上的字段可以留有默认值。 选择**下一步** 。

   - **部署类型** – 选择 **"添加** "以启动"创建部署类型向导"。

   - 继续执行创建部署类型向导的步骤，如下所示：

     * **常规** – 从 **"类型"** 下拉菜单 **中选择** "脚本安装程序"。 将自动 **选择"手动指定部署类型** 信息"选项。 选择 **"下一** 步"继续。
     * **常规信息**– 输入部署类型的名称 (例如 SEMM Configuration Scripts) ，然后选择"下一步 **"继续。**
     * **内容**–**选择"** 内容**** 位置"字段旁边的"浏览"，然后选择 SEMM Configuration Manager 脚本所在的文件夹。 在 **"安装程序"** 字段中，键入 [本文前面](#deploy-semm-configuration-manager-scripts) 介绍的安装命令。 在"**卸载程序**"字段中，输入[](#deploy-semm-configuration-manager-scripts)本文前面介绍的卸载 (如图 2 所示) 。 选择 **"下** 一步"以移到下一页。
    
     ![将 SEMM Configuration Manager 脚本设置为安装和卸载命令。](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *图 2. 将 SEMM Configuration Manager 脚本设置为安装和卸载命令*

     * **检测方法** – 选择 **"添加子句** "以添加 SEMM Configuration Manager 脚本注册表项检测规则。 将显示 **"检测** 规则"窗口，如图 3 所示。 使用以下设置：

       - 从 **"设置** 类型 **"下拉菜单中选择** "注册表"。
       - 从**HKEY_LOCAL_MACHINE****配置**单元"下拉菜单中选择"配置单元"。
       - 在 **"密钥"字段中输入 SOFTWARE\Microsoft\Surface\SEMM。** ****
       - 在 **"值"字段中输入 CertName。** ****
       - 从 **"** 数据类型 **"下拉菜单中选择** "字符串"。
       - 选择 **"此注册表设置必须满足以下规则"以指示存在此应用程序** 按钮。
       - 在"值"字段中输入在脚本的第 58 行中输入的 **证书** 的名称。
       - 选择 **"确定** "关闭 **"检测规则"** 窗口。

     ![使用注册表项标识在 SEMM 中注册的设备。](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *图 3. 使用注册表项标识在 SEMM 中注册的设备*

     * 选择 **"下** 一步"继续下一页。
     
     * **用户体验** – 从 **"安装行为"** 下拉菜单中选择"为 **系统安装** "。 如果希望用户自行记录和输入证书指纹，请保留登录要求设置为"仅在用户**登录时"。** 如果希望管理员输入用户的指纹，而用户不需要看到指纹，请从"登录要求"下拉菜单中选择"用户是否已登录"。 **** ****

     * **要求** - ConfigureSEMM.ps1脚本在尝试启用 SEMM 之前自动验证设备是 Surface 设备。 但是，如果你打算将此脚本应用程序部署到包含使用 SEMM 管理的设备外的其他设备的集合，可以在此处添加要求，以确保此应用程序仅在打算使用 SEMM 管理的 Surface 设备或设备上运行。 选择 **"下一** 步"继续。
     
     * **依赖项** – 选择 **"添加** "以打开 **"添加依赖关系"** 窗口。

       * 选择 **"添加** "以打开 **"指定所需的应用程序"** 窗口。

          - 在"依赖关系组名称"字段中输入 SEMM 依赖项的名称 (例如 *，SEMM*程序集) 。 ****

          - 从可用应用程序和 MSI 部署类型的列表中选择**** Microsoft **Surface UEFI**管理器，然后选择确定**** 以关闭"**指定所需的应用程序"** 窗口。
          
         *   如果希望 **在设备上自动** 安装 Microsoft Surface UEFI 管理器，请在尝试使用 Configuration Manager 脚本启用 SEMM 时，使"自动安装"复选框保持选中状态。 选择 **"确定** "关闭 **"添加依赖关系"** 窗口。

     * 选择 **"下一** 步"继续。
     
     * **摘要** - 在此页上显示您在整个"创建部署类型"向导中输入的信息。 选择 **"下** 一步"以确认你的选择。
     
     * **进度** - 在此页上显示为 SEMM 脚本应用程序添加部署类型时的进度栏和状态。
     
     * **完成** – 过程完成后，将显示部署类型创建确认。 选择 **"** 关闭"完成"创建部署类型向导"。

   - **摘要** - 显示您在整个"创建应用程序向导"中输入的信息。 选择 **"下** 一步"以创建应用程序。

   - **进度** – 在此页上显示应用程序添加到软件库时的进度栏和状态。

   - **完成** – 应用程序创建过程完成后，将显示应用程序创建成功确认。 选择 **"** 关闭"以完成"创建应用程序向导"。

脚本应用程序在 Configuration Manager 的软件库中可用后，可以使用为设备或集合准备的脚本分发和部署 SEMM。 如果你已配置 Microsoft Surface UEFI 管理器程序集作为将自动安装的依赖项，则可以通过一个步骤部署 SEMM。 如果尚未将程序集配置为依赖项，则必须在要管理的设备上安装这些程序集，然后才能启用 SEMM。

使用此脚本应用程序和对最终用户可见的配置部署 SEMM 时，PowerShell 脚本将启动，并且证书指纹将显示在 PowerShell 窗口。 你可以让用户记录此指纹，在设备重启后由 Surface UEFI 提示时输入它。

或者，你可以将应用程序安装配置为自动重新启动，并让用户以不公开方式安装。 在此方案中，在重新启动每台设备时，需要技术人员输入指纹。 有权访问证书文件的任何技术人员都可以通过使用 CertMgr 查看证书来读取指纹。 有关使用 CertMgr 查看指纹的说明，请参阅本文的创建或修改 [SEMM Configuration Manager](#create-or-modify-the-semm-configuration-manager-scripts) 脚本部分。

从使用这些脚本通过 Configuration Manager 部署的设备删除 SEMM 与使用 Configuration Manager 卸载应用程序一样简单。 此操作将启动ResetSEMM.ps1脚本，并正确取消注册与 SEMM 部署期间使用的证书文件相同的设备。

> [!NOTE]
> Microsoft Surface 建议你仅在需要注销设备时创建重置程序包。 这些重置程序包通常仅对一个设备有效，按其序列号标识。 但是，你可以创建通用重置程序包，该程序包适用于在此证书的 SEMM 中注册的任何设备。
> 
> 我们强烈建议你像在 SEMM 中注册设备的证书一样小心保护通用重置程序包。 请记住，与证书本身一样，此通用重置程序包可用于从 SEMM 注销组织的任何 Surface 设备。
> 
> 安装重置程序包时，LSV (支持) 值将重置为 1。 可以使用现有配置包重新注册设备。 设备将在获得所有权前提示输入证书指纹。
> 
> 因此，在 SEMM 中重新注册设备将需要在该设备中创建和安装新程序包。 由于此操作是一个新的注册，而不是已在 SEMM 中注册的设备的配置更改，因此设备将在获得所有权之前提示输入证书指纹。

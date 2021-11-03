---
title: 启用 802.1x 有线身份验证
description: 802.1x 有线身份验证 MDM 策略已在 Surface Hub 设备上启用。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: dcb2799accfcbccb41e44e09f0df3fd1ac6eb57e
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154037"
---
# <a name="enable-8021x-wired-authentication"></a>启用 802.1x 有线身份验证

[2017 年 11 月 14](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954)日更新到 Windows 10 (版本 15063.726) 在 Surface Hub 设备上启用了 802.1x 有线身份验证 MDM 策略。 该功能允许组织使用 [IEEE 802.1x 身份验证协议](http://www.ieee802.org/1/pages/802.1x-2010.html) 强制执行标准化有线网络身份验证。 这已经可用于通过 MDM 使用 [WLAN 配置文件进行无线](/mem/intune/configuration/wi-fi-settings-import-windows-8-1) 身份验证。 本主题介绍如何配置用于有线身份验证的 Surface Hub。 

可以通过 MDM [OMA-URI 定义](/mem/intune/configuration/custom-settings-windows-10) 在 Surface Hub 上强制执行和启用 802.1x 有线身份验证。 

主要配置设置为 **LanProfile** 策略。 根据所选的身份验证方法，可能需要其他策略，**EapUserData** 策略，或通过用于添加用户或计算证书的 MDM 策略（例如用户用户/设备证书的 [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) 或用于设备证书的 [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp)）。 

## <a name="lanprofile-policy-element"></a>LanProfile 策略元素

若要将 Surface Hub 配置为使用受支持的 802.1x 身份验证方法之一，请使用以下 OMA URI。 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

此 OMA-URI 节点采用 XML 文本字符串作为参数。 作为参数提供的 XML 应符合包括 [802.1X 架构](/openspecs/windows_protocols/ms-gpwl/71f2eda6-d018-4ba3-ad37-32c98b926ebb)中的元素的[有线 LAN 配置文件架构](/openspecs/windows_protocols/ms-gpwl/c88a926a-087b-405f-9a76-effaf7277bf3)。 

在大多数情况下，管理员或用户可以使用以下 NETSH 命令，从已在网络上针对 802.1X 配置的现有电脑中导出 LanProfile XML。 

```
netsh lan export profile folder=.
```

运行此命令将提供以下输出，并将标题为 **Ethernet.xml** 的文件放在当前目录中。 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <a name="eapuserdata-policy-element"></a>EapUserData 策略元素

如果所选的身份验证方法需要用户名和密码而不是证书，则可以使用 **EapUserData** 元素指定供设备用于身份验证到网络的凭据。 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

此 OMA-URI 节点采用 XML 文本字符串作为参数。 作为参数提供的 XML 应符合 [PEAP MS-CHAPv2 用户属性示例](/windows/win32/eaphost/peap-ms-chapv2-user-properties)。 在此示例中，将需要使用信息替换 *test* 和 *ias-domain*。



## <a name="adding-certificates"></a>添加证书

如果你所选的身份验证方法是基于证书的，则需要创建预配包、利用[](provisioning-packages-for-surface-hub.md) [MDM，](/windows/client-management/mdm/clientcertificateinstall-csp)或从设置 (**设置**更新和安全证书) 导入证书，以在相应的证书存储中将证书部署到  >  ****  >  **** Surface Hub 设备。 添加证书时，每个 PFX 必须只包含一个证书（一个PFX 不能具有多个证书）。


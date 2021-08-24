---
title: 为 Surface Duo 配置 Android 企业工作配置文件
description: 本文介绍了如何在 Surface Duo 上设置工作配置文件。
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 380c5fc625983119a516f5d0e2294af70e0dbd29
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911197"
---
# <a name="configure-android-enterprise-work-profile-for-surface-duo"></a>为 Surface Duo 配置 Android 企业工作配置文件

工作配置文件面向 BYOD 部署，在 Duo 上为工作应用和数据提供单独的空间，使组织可以完全控制其数据、应用和安全策略，而不会阻止员工将设备用于个人应用和数据。

### <a name="set-up-android-enterprise-work-profile"></a>设置 Android Enterprise工作配置文件

使用工作配置文件在用户拥有的 Android 设备上管理公司数据和应用。 默认情况下，将启用个人拥有的工作配置文件设备的注册，无需进一步管理员配置。  

**若要启用Enterprise工作配置文件：**

- In Endpoint Manager， select **Devices**  >  **Android**  >  **Android enrollment** and then select Personal **devices with work profile**.
<br><br>
 ![启用Enterprise工作配置文件。](images/enroll-start.png)

 
**使用 Android 工作配置文件Enterprise Surface Duo**

1. 从 Google Play 公司门户安装应用，然后使用 Microsoft 工作或学校帐户登录。<br><br>
![登录到 Surface Duo。](images/duo-wp-1.png)
 
2. 在"Access 安装程序"页上，选择"开始 **"。**<br><br>
![开始。](images/duo-wp-2.png)

3. 查看隐私页面上的信息，然后选择"继续 **"。**<br><br>
 ![继续。](images/duo-wp-3.png)
<br><br>
 ![选择"继续"。](images/duo-wp-4.png)
 
4. 工作配置文件设置完成后，选择" **继续"** 以激活和注册设备。<br><br>
 ![选择"继续"以激活和注册设备。](images/duo-wp-5.png)

5. 选择**继续**。<br><br>
 ![再次选择"继续"。](images/duo-wp-6.png)

6. 激活工作配置文件后，选择" **继续"** 以更新设备设置。 本示例中，工作配置文件应用 MDM 设置，要求使用更强大的 6 位字母数字密码。 <br><br>

     ![示例字母数字密码。](images/duo-wp-7.png)<br><br>
7. 选择 **"解析** "以输入所需的身份验证，然后选择" **继续** "以完成工作配置文件设置。 <br><br>
     ![选择"继续"完成设置。](images/duo-wp-8.png)<br><br>
     ![完成设置。](images/duo-wp-9.png)<br><br>

## <a name="learn-more"></a>了解详细信息

- [设置 Android Enterprise工作配置文件设备的注册](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)


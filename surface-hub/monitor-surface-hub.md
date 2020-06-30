---
title: 监视 Microsoft Surface Hub
description: 支持通过 Microsoft Operations Management Suite (OMS) 监视 Microsoft Surface Hub 设备。
ms.assetid: 1D2ED317-DFD9-423D-B525-B16C2B9D6942
ms.reviewer: ''
manager: laurawi
keywords: 监视 Surface Hub, Microsoft Operations Management Suite, OMS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 108f24036a0e02295cf2a5588bb6b51e517eba8d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831816"
---
# 监视 Microsoft Surface Hub

支持通过 Microsoft Operations Management Suite (OMS) 监视 Microsoft Surface Hub 设备。 [Operations Management Suite](https://go.microsoft.com/fwlink/?LinkId=718138) 是 Microsoft 的 IT 管理解决方案，可帮助你管理和保护整个 IT 基础结构，包括 Surface Hub。


Surface Hub 在 OMS 中作为 Log Analytics 解决方案提供，支持收集并查看所有 Surface Hub 上的使用情况和可靠性数据。 使用 Surface Hub 解决方案：
- 编制 Surface Hub 清单。
- 查看 Skype 会议、有线和无线投影、Surface Hub 应用的使用情况和可靠性数据快照。
- 如果 Surface Hub 可报告软件或硬件问题，请创建自定义警报，快速做出响应。

## 将 Surface Hub 添加到 Operations Management Suite

1. **登录 Operations Management Suite (OMS)**。 可使用 Microsoft 帐户或者工作或学校帐户创建工作区。 如果公司在使用 Azure Active Directory (Azure AD)，则使用工作或学校帐户登录 OMS。 使用工作或学校帐户支持使用 Azure AD 中的身份管理 OMS 权限。
2. **创建新的 OMS 工作区**。 输入工作区名称、选择工作区区域，并提供与此工作区关联的电子邮件地址。 选择**创建**。
3. **将 Azure 订阅链接到工作区**。 如果组织拥有 Azure 订阅，可将其链接到工作区。 请注意，可能需要向组织的 Azure 管理员请求访问权限。

    > [!NOTE] 
    > 如果组织没有 Azure 订阅，请创建一个订阅，或者从列表中选择默认的 OMS Azure 订阅。 工作区将打开。

4. **添加 Surface Hub 解决方案**。 在解决方案库中，选择库中的 **Surface Hub** 磁贴，然后选择解决方案详细信息页上的**添加**。 此时可在工作区看到该解决方案。

## 使用 Surface Hub 仪表板
在 OMS 工作区的**概述**页上，单击“Surface Hub”磁贴，查看 Surface Hub 仪表板。 使用该仪表板获取 Surface Hub 上使用情况和可靠性数据的快照。 单击仪表板上的每个视图，查看详细数据、根据需要修改查询，并创建警报。

> [!NOTE]
> 大部分视图显示过去 30 天的数据，但具体时间由订阅的数据保留策略而定。

**活动的 Surface Hub**

使用此视图获取所有 Surface Hub 清单。 连接到 OMS 后，每个 Surface Hub 会定期向服务器发送“检测信号”事件。 此视图显示过去 24 小时报告检测信号的 Surface Hub。

<!--
**Skype meetings**

Use this view to get usage data for Skype over the past 30 days. The graph shows the total number of Skype Meetings started across your Surface Hubs, and a breakdown between scheduled meetings, ad hoc meetings, and PSTN calls.
-->
 
**无线投影**

使用此视图获取过去 30 天无线投影的使用情况和可靠性数据。 该图显示所有 Surface Hub 上的无线连接总数，可指示组织成员是否在使用此功能。 如果数字较小，可能暗示需要提供培训，帮助组织成员学习如何无线连接到 Surface Hub。
 
另外，该图还显示成功和失败连接的细分情况。 如果看到大量失败连接，可能是设备没有正确使用 Miracast 支持无线投影。 为了获取最佳性能，Microsoft 建议设备运行 WDI WLAN 驱动程序和 WDDM 2.0 图形驱动程序。 使用详细信息视图了解特定设备是否经常发生投影问题。
 
连接失败时，如果用户使用的是 Windows 笔记本电脑或手机，还可执行以下操作：
- 在**设置** > **设备** > **连接的设备**中删除已配对设备，然后重新尝试连接。
- 重启设备。
 
**有线投影**

使用此视图获取过去 30 天有线投影的使用情况和可靠性数据。 如果该图显示大量失败连接，可能指示视听管道中出现连接问题。 例如，如果使用 HDMI 中继器或空间中心控制面板，可能需要重新启动它们。
 
**应用程序使用情况**

使用此视图获取过去 30 天 Surface Hub 应用的使用情况数据。 数据来源于在 Surface Hub 上启动的应用，不包括 Skype for Business。 此视图可帮助了解对组织最有价值的 Surface Hub 应用。 如果在环境中部署新的业务线应用，此视图还可帮助了解这些应用的使用频率。
 
**应用程序崩溃**

使用此视图获取过去 30 天 Surface Hub 应用的可靠性数据。 数据来源于 Surface Hub 上的应用崩溃数。 此视图可帮助检测并通知应用开发人员表现不如人意的内置和业务线应用。
 
**示例查询**

用以根据推荐的查询集创建自定义警报。 如果 Surface Hub 可报告软件或硬件问题，警报可有助于快速响应。 有关详细信息，请参阅[使用示例查询设置警报](#set-up-alerts-with-sample-queries)。

## 使用示例查询设置警报

如果 Surface Hub 可报告软件或硬件问题，请使用警报快速响应。 警报规则根据计划自动运行日志搜索，并在结果符合特定条件时运行一项或多项操作。 有关详细信息，请参阅 [Log Analytics 中的警报](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/)。
 
Surface Hub Log Analytics 解决方案随附示例查询集，帮助设置相应警报和了解如何解决遇到的问题。 根据这些查询集规划监视和支持策略。

此表介绍了 Surface Hub 解决方案中的示例查询：

| 警报类型 | 影响 | 建议的纠正措施 | 详细信息 |
| ---------- | ------ | ----------------------- | ------- |
| 软件   | 错误  | **重启设备**。 <br> 手动重启，或使用[重启配置服务提供程序](https://msdn.microsoft.com/library/windows/hardware/mt720802(v=vs.85).aspx)重启。 <br> 建议在会议间隙执行此操作，尽可能将对组织成员的影响降到最低。 | 触发条件： <br> - Surface Hub 操作系统中的关键过程，如 Shell、投影、或 Skype 崩溃或者没有响应。 <br> - 设备在过去 24 小时没有报告检测信号。 这可能是因为网络连接问题或与网络相关的硬件故障，或者是诊断数据报告系统出现错误。 |
| 软件   | 错误  | **查看 Exchange 服务**。 <br> 验证： <br> - 服务是否可用。 <br> - 设备帐户密码是否是最新密码 – 请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)，获取详细信息。| 同步设备日历与 Exchange 出现错误时触发。 |
| 软件   | 错误  | **查看 Skype for Business 服务**。 <br> 验证： <br> - 服务是否可用。 <br> - 设备帐户密码是否是最新密码 – 请参阅[密码管理](password-management-for-surface-hub-device-accounts.md)，获取详细信息。 <br> - Skype for Business 的域名是否配置正确 - 请参阅[配置域名](use-fully-qualified-domain-name-surface-hub.md)。 | 在 Skype 无法登录时触发。 |
| 软件   | 错误  | **重置设备**。 <br> 这需要一些时间，应使设备脱机。 <br> 有关详细信息，请参阅[设备重置](device-reset-surface-hub.md)。| 在会话结束后清理用户和应用数据出现错误时触发。 如果此操作重复失败，设备将锁定，以保护用户数据。 必须重置设备才能继续操作。 |
| 硬件   | 警告 | **无**。 表示对功能的影响微乎其微。| 在以下任何硬件组件出现错误时触发： <br> - 虚拟笔槽 <br> - NFC 驱动程序 <br> - USB 集线器驱动程序 <br> - 蓝牙驱动程序 <br> - 邻近感应传感器 <br> - 图形性能（视频卡驱动程序） <br> - 硬盘驱动器不匹配 <br> - 没有检测到键盘/鼠标 |
| 硬件   | 错误 | **联系 Microsoft 支持人员**。 <br> 指示对核心功能（例如 Skype、投影、触摸和 Internet 连接）的影响。 <br> **注意** 某些事件（包括检测信号）包含可在联系支持人员时使用的设备序列号。| 在以下任何硬件组件出现错误时触发。 <br> **影响 Skype 的组件**： <br> - 扬声器驱动程序 <br> - 麦克风驱动程序 <br> - 相机驱动程序 <br> **影响有线和无线投影的组件**： <br> - 有线 touchback 驱动程序 <br> - 有线引入驱动程序 <br> - 无线适配器驱动程序 <br> - WLAN Direct 错误 <br> **其他组件**： <br> - 触摸数字化器驱动程序 <br> - 网络适配器错误（没有向 OMS 报告）|

**设置警报**
1. 从 Surface Hub 解决方案中选择一个示例查询。
2. 根据需要修改查询。 请参阅 Log Analytics 搜索参考，了解详细信息。
3. 在页面顶部单击**警报**，打开**添加警报规则**屏幕。 有关配置警报选项的详细信息，请参阅 [Log Analytics 中的警报](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/)。
4. 单击**保存**，完成填写警报规则。 它将立即开始运行。

## 注册 Surface Hub

Surface Hub 若要连接到并注册 OMS 服务，必须访问域和 URL的端口号。 此表列出了 OMS 所需的端口。 有关详细信息，请参阅[在 Log Analytics 中配置代理和防火墙设置](https://azure.microsoft.com/documentation/articles/log-analytics-proxy-firewall/)。

>[!NOTE]
>Surface Hub 当前不支持使用代理服务器与 OMS 服务进行通信。

| 代理资源              | 端口 | 绕过 HTTPS 检查？ |
| --------------------------- | ----- | ------------------------ |
| *.ods.opinsights.azure.com  | 443   | 是 |
| *.oms.opinsights.azure.com  | 443   | 是 |
| *.blob.core.windows.net     | 443   | 是 |
| ods.systemcenteradvisor.com | 443   | 否  |

Microsoft Monitoring Agent 用于将设备连接到 OMS，它与 Surface Hub 操作系统集成，因此无需安装其他客户端即可将 Surface Hub 连接到 OMS。
 
设置 OMS 工作区后，可使用几种方法注册 Surface Hub 设备：
- [“设置”应用](#enroll-using-the-settings-app)
- [设置包](#enroll-using-a-provisioning-package)
- [MDM 提供程序](#enroll-using-a-mdm-provider)，例如 Microsoft Intune 和 Configuration Manager
 
需要工作区 ID 和 OMS 工作区的主键。 可以从 OMS 门户获取上述内容。
 
### 使用“设置”应用注册

**使用“设置”应用注册**

1. 在 Surface Hub 中，启动**设置**。
2. 请在系统提示时，输入该设备的管理员凭据。
3. 选择**此设备**，然后导航到**设备管理**。
4. 在**监视**下，选择**配置 OMS 设置**。
5. 在“OMS 设置”对话框中，选择**启用监视**。
6. 键入工作区 ID 和 OMS 工作区主键。 可以从 OMS 门户获取上述内容。
7. 单击**确定**，完成配置。
 
将显示确认对话框，告知你是否已将 OMS 配置成功应用到设备。 如果成功，该设备将开始向 OMS 发送数据。

### 使用设置包注册
可使用设置包注册 Surface Hub。 有关详细信息，请参阅[创建设置包](provisioning-packages-for-certificates-surface-hub.md)。
 
### 使用 MDM 提供程序注册
可使用 SurfaceHub 云解决方案提供商将 Surface Hub 注册到 OMS。 Intune 和 Configuration Manager 提供有助于创建用于 Surface Hub 的策略模板的内置体验。 有关详细信息，请参阅[使用 MDM 提供程序管理 Surface Hub 设置](manage-settings-with-mdm-for-surface-hub.md)。

## 相关主题

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)

 

 






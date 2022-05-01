---
title: Surface Hub 更新历史记录
description: Surface Hub 更新历史记录
ms.assetid: d66a9392-2b14-4cb2-95c3-92db0ae2de34
keywords: ''
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: dpandre
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 9d48779195702952314baf07636749b70ce000ab
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497945"
---
# <a name="surface-hub-update-history"></a>Surface Hub 更新历史记录

Windows 旨在提供服务，这意味着可通过定期软件更新自动进行完善。 通常无需执行任何操作，即可获取最新的 Windows 10 更新，因为这些更新在可用时即会下载并安装。

大多数 Windows 更新侧重于提升性能和安全性。 在下面的列表中，首先列出了具有特定 Surface Hub 改进的最新 Windows 更新。 更新是累积的，因此安装最新的可用 Windows 更新 (即使它不在下面的列表中) 也可确保你还受益于任何以前的更新中的改进。 Microsoft Store 应用可通过 Microsoft Store (由 Surface Hub 的系统管理员管理) 进行更新。 有关应用更新的详细信息基于每个应用提供。

> [!TIP]
> 当发布新更新时，将刷新此页面。 有关可能需要你关注的当前和以往版本的相关主题，请参阅 [Surface Hub 的重要信息](https://support.microsoft.com/products/surface-devices/surface-hub)页面。

## <a name="windows-10-team-2020-update-20h2"></a>Windows 10 协同版 2020 更新 (20H2)

<details>
<summary>2022 年 4 月 21 日 - 基于 KB5011831* (OS 内部版本 19042.1679) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history)中概述) 包含:

* 修复了以下问题：阻止“结束会话”触发消息“你的设备需要更新。 重新启动以完成更新...”以及某些情况下的后续重启。
* 修复了以下问题：确保 [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp#deviceaccount) 可以与以 `DOMAIN\username` 格式配置设备帐户的 SyncML 策略一起使用。
 
有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB5011831](https://support.microsoft.com/help/5011831)
</details>

<details>
<summary>2022 年 3 月 22 日 - 基于 KB5011543 的团队更新*（操作系统内部版本 19042.1620）</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history)中概述) 包含:

* 增加管理员[安装渐进式 Web 应用 ](install-pwa-surface-hub.md)(PWA) 的功能。
* 解决加入 Azure AD 或使用本地管理员帐户配置的 Surface Hub 可能无法同步其计算机时钟的问题。
* 解决通过 Authenticator 应用使用会议和文件登录建议可能会强制用户重复登录过程的问题。
 
有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB5011543](https://support.microsoft.com/help/5011543)
</details>

<details>
<summary>2022 年 2 月 15 日 — 基于 KB5010415* (OS 内部版本 19042.1566) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 [Windows 10 协同版 2020 更新 2](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-2) 中概述了 Surface Hub 的关键更新，还包括以下内容:

* 修复了允许在设备帐户设置期间禁用 Exchange 服务的修补程序。
* 提高了使用本地 Exchange 邮箱时某些设备帐户设置方案的可靠性。
* 改进了使用 SurfaceHub CSP 时某些 MDM 策略设置方案的可靠性。
* 提高使用 Skype for Business 时传入呼叫方案的可靠性。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB5010415](https://support.microsoft.com/help/5010415)
</details>

<details>
<summary>2022 年 1 月 25 日 — 基于 KB5009596* (OS 内部版本 19042.1503) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history)中概述) 包含:

* 解决了 Surface Hub 无法向其配置的 Azure Log Analytics 工作区报告数据的问题。
* 解决了从 Surface Hub 的欢迎屏幕启动 Skype for Business 会议可能导致完全最大化的 SfB 客户端无法最小化的问题。
* 解决了 Azure AD 加入的 Surface Hub 未使用会议受邀者列表预填充会议和文件登录的问题。
* 解决了在某些本地方案中无法启用设备帐户密码轮换的问题。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB5009596](https://support.microsoft.com/help/5009596)
</details>

<details>
<summary>2022 年 1 月 21 日 — Surface Hub 2S 的更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Surface UEFI 更新 - 694.3924.768.0
  * 提高系统安全性和稳定性。
* Intel(R) 管理引擎接口驱动程序 - 2120.100.0.1085
  * 提高系统安全性和稳定性。
</details>

<details>
<summary>2021 年 11 月 22 日 — 基于 KB5007253* (OS 内部版本 19042.1387) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history)中概述) 包含:

* 修复了在 Surface Hub 上使用 MDM 策略设置“友好名称”时强制执行 32 个字符限制的问题。
* 修复了将 AllowStorageCard MDM 从 0 还原到值 1 (允许存储卡) 时的策略行为。
* 更新以允许 Edge (Chromium) 浏览器访问文件资源管理器中可访问的相同文件位置，包括附加的 USB 驱动器。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB5007253](https://support.microsoft.com/help/5007253)
</details>

<details>
<summary>2021 年 9 月 30 日 — KB5004196、KB5004198 和 KB5004199</summary>

Surface Hub 的这些更新提供 Teams 会议室客户端、Teams 管理中心代理和托管会议室代理。 [Surface Hub 上的 Teams 会议室](surface-hub-teams-rooms.md) 中概述了主要功能。
 
有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
</details>

<details>
<summary>2021 年 9 月 30 日 — 基于 KB5005611* (OS 内部版本 19042.1266) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history)中概述) 包含:

* 将会议模式 1 (Teams 首选/SfB 可用) 替换为模式 2 功能 (仅限 Teams); 可以使用任一设置，但两者具有相同的效果。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB5005611](https://support.microsoft.com/help/5005611)
</details>

<details>
<summary>2021 年 9 月 1 日 — 基于 KB5005101* (OS 内部版本 19042.1202) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 [Windows 10 协同版 2020 更新 1](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-1) 中概述了 Surface Hub 的关键更新，还包括以下内容:

* 提高了使用本地 Exchange 邮箱时某些设备帐户设置方案的可靠性。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB5005101](https://support.microsoft.com/help/5005101)
</details>

<details>
<summary>2021 年 7 月 29 日 — 基于 KB5004296* (OS 内部版本 19042.1151) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history)中概述) 包含:

* 更新到“收集日志”以 csv 格式包含 Windows 诊断数据的功能。
* 修复以确保结束会话清理完全删除与 Edge Chromium 相关的所有数据。
* 改进在使用 Authenticator 应用时加入 Azure AD 的 Surface Hub 的一些个人登录方案。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB5004296](https://support.microsoft.com/help/5004296)
</details>

<details>
<summary>2021 年 6 月 10 日 — Surface Hub 2S 的更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Surface UEFI 更新 - 694.3751.768.0
  * 修复了关键安全漏洞并提高了系统稳定性。
* Surface ME 固件更新 - 11.8.86.3877
  * 修复了关键安全漏洞并提高了系统稳定性。
* Intel(R) 管理引擎接口驱动程序 - 2102.100.0.1044
  * 修复了关键安全漏洞并提高了系统稳定性。
</details>

<details>
<summary>2021 年 4 月 13 日 — 基于 KB5001330* (OS 内部版本 19042.928) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history)中概述) 包含:

* 解决了某些 Surface Hub 设备仅安装每月 Windows 安全更新而不是所有 Windows 累积更新的问题。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB5001330](https://support.microsoft.com/help/5001330)
</details>

<details>
<summary>2021 年 3 月 13 日 — Surface Hub 2S 的更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Intel(R) 蓝牙驱动程序 - 22.30.0.4
  * 提高系统安全性和稳定性。
* Intel(R) 图形驱动程序 - 27.20.100.8682
  * 提高系统安全性和稳定性。
* Intel(R) Wi-Fi 驱动程序 - 22.30.0.11
  * 提高系统安全性和稳定性。
</details>

<details>
<summary>2021 年 2 月 2 日 — 基于 KB4598291* (OS 内部版本 19042.789) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history)中概述) 包含:

* 当设备帐户的 UPN 不等于其 SMTP 时，允许与 Exchange 的日历同步的修补程序。
* 增加管理员在与 Exchange 同步日历期间[禁用新式验证](/windows/client-management/mdm/surfacehub-csp#deviceaccount-exchangemodernauthenabled)的功能。
* 确保在启用“使用设备帐户凭据”功能后，不会提示 Surface Hub 用户输入代理凭据。
* 解决了在使用需要身份验证的代理时，Windows 更新和存储更新检查永远不会完成的问题。
* 在有线引入方案期间提高连接应用的可靠性。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB4598291](https://support.microsoft.com/help/4598291)
</details>

<details>
<summary>2021 年 1 月 15 日 — Surface Hub 2S 的更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Surface SMC 固件更新 - 3.93.139.0
* Surface UEFI 更新 - 694.3473.768.0
</details>

<details>
<summary>2020 年 12 月 11 日 — Surface Hub 2S 的更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Surface SMC 固件更新 - 3.92.139.0
* Surface UEFI 更新 - 694.3447.768.0
</details>

<details>
<summary>2020 年 11 月 30 日 — 基于 KB4586853* (OS 内部版本 19042.662) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history)中概述) 包含:

* 更新到“隐私设置”页面以提供其他选项。
* 解决了已开始的会议不显示在欢迎/开始屏幕上的问题。
* 解决了非 en-US 区域设置的云恢复问题。
* Skype for Business
  * 提高定向音频性能。
  * 减低了在 Skype for Business 通话期间使用手写笔时的“笔击”声音。
* 提高注册到 Windows 预览体验计划时的可靠性。
* 提高了 Windows Team shell 的可靠性。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。 *[KB4586853](https://support.microsoft.com/help/4586853)
</details>

<details>
<summary>2020 年 11 月 24 日 — Surface Hub 2S 的更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Surface SMC 固件更新 - 3.91.139.0
  * 提高连接待机可靠性。
* Surface 触控固件更新 - 3.91.139.0
  * 改进连接待机触控响应。
* Surface USB 音频固件更新 - 3.91.139.0
* Surface 触控笔固件更新 - 3.91.139.0
</details>

<details>
<summary>2020 年 10 月 27 日 — Surface Hub 2S 的更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Surface 系统聚合器固件更新 - 4.14.139.0
* Surface UEFI 更新 - 694.3386.768.0
</details>

<details>
<summary>Windows 10 协同版 2020 Surface Hub 更新 — 常规发行说明 (OS 内部版本 19042.572)</summary>

此 Surface Hub 更新包含质量改进和安全修复。 [Windows 10 更新历史记录](https://support.microsoft.com/help/4581839/windows-10-update-history) 中尚未列出 Surface Hub 的关键更新，请在 [Windows 10 协同版 2020 更新中的新增功能](/surface-hub/surface-hub-2020-update-whats-new) 页面中记录。

更多关于按地区、分发方式和设备类型的更新可用性的信息，请参阅 [安装Windows 10 协同版 2020 更新](/surface-hub/surface-hub-2020-update) 页面。
</details>

## <a name="windows-10-team-creators-update-1703"></a>Windows 10 协同版创意者更新 (1703)

<details>
<summary>2020 年 9 月 1 日 — Surface Hub 2S 的更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Surface SMC 固件更新 - 1.177.139.0
  * 改进了字段修复方案。
* Surface SSD 固件更新 - 5.14.139.0
  * 改进了系统稳定性。
* Surface 串行中心驱动程序 - 9.40.139.0
  * 改进了系统稳定性。
</details>

<details>
<summary>2020 年 5 月 4 日 — Surface Hub 2S 更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Surface USB 音频驱动程序 - 15.3.6.0
  * 提高定向音频性能。
* Intel(R) 显示音频驱动程序 - 10.27.0.5
  * 改进屏幕共享方案。
* Intel(R) 图形驱动程序 - 26.20.100.7263
  * 改进了系统稳定性。
* Surface System 驱动程序 - 1.7.139.0
  * 改进了系统稳定性。
* Surface SMC 固件更新 - 1.176.139.0
  * 改进了系统稳定性。
</details>

<details>
<summary>2020 年 2 月 28 日 — Surface Hub 2S 的更新</summary>

此更新特定于 Surface Hub 2S，并提供下面概述的驱动程序和固件更新:

* Surface 集成驱动程序 - 13.46.139.0 
  * 改进显示亮度方案。
* Intel(R) 管理引擎接口驱动程序 - 1914.12.0.1256
  * 改进了系统稳定性。
* Surface SMC 固件更新 - 1.161.139.0
  * 提高触控笔电池性能。
* Surface UEFI 更新 - 694.2938.768.0
  * 改进了系统稳定性。
</details>

<details>
<summary>2020 年 2 月 11 日 — 基于 KB4537765* (OS 内部版本 15063.2284) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决了在 Skype for Business 通话期间其他参与者无法很好地听到 Hub 2S 的问题。
* 提高了在 Surface Hub 中某些阿拉伯语、希伯来语和其他 RTL 语言使用方案的可靠性。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4537765](https://support.microsoft.com/help/4537765)
</details>

<details>
<summary>2020 年 1 月 14 日 — 基于 KB4534296* (OS 内部版本 15063.2254) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决了 Microsoft Surface Hub 2S 的日志收集问题。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4534296](https://support.microsoft.com/help/4534296)
</details>

<details>
<summary>2019 年 9 月 24 日 — 基于 KB4516059* (OS 内部版本 15063.2078) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

 * 更新到“Surface Hub 2S 恢复设置”页面以准确反映恢复选项。
 * 更新到“Surface Hub 2S 欢迎”屏幕以提高设备的可识别性。
 * 解决了 Windows Team shell 背景显示不正确的问题。
 * 解决了使用 MDM 策略配置时“开始”菜单布局持久性的问题。
 * 修复了 Microsoft Edge 浏览某些内部网站时出现的问题。
 * 修复了 Skype for Business 中在全屏模式下演示时出现的问题。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4503289](https://support.microsoft.com/help/4503289)
</details>

<details>
<summary>2019 年 8 月 17 日 — 基于 KB4512474*  (OS 内部版本 15063.2021) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

 * 请确保 Hub 2S 上的视频输出默认为“重复”模式。
 * 提高了在 Surface Hub 中某些阿拉伯语使用方案的可靠性。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4503289](https://support.microsoft.com/help/4503289)
 </details>

<details>
<summary>2019 年 6 月 18 日 — 基于 KB4503289* (OS 内部版本 15063.1897) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决了阻止用户使用 Azure Active Directory 帐户登录到 Microsoft Surface Hub 设备的问题。 出现此问题的原因是上一个会话未成功结束。
* 增加了设备账户设置方案中对 TLS 1.2 连接到身份提供者和 Exchange 的支持。
* 为提高 Hub 2S 上的硬件诊断应用可靠性而进行的修复。 
* 为提高 Hub 2S 上首次运行安装体验一致性的修复。 

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4503289](https://support.microsoft.com/help/4503289)
</details>

<details>
<summary>2019 年 5 月 28 日 — 基于 KB4499162* (OS 内部版本 15063.1835) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 确保在启用“使用设备帐户凭据”功能后，不会提示 Surface Hub 用户输入代理凭据。
* 解决了 Skype 连接由于音频/视频未使用正确的代理而周期性失败的问题。
* 添加了对 Skype for Business 中 TLS 1.2 的支持。
* 解决 Skype 服务器禁用 TLS 1.0 或 TLS 1.1 时 Skype 客户端的 SIP 连接故障。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4499162](https://support.microsoft.com/help/4499162)
</details>

<details>
<summary>2019 年 4 月 25 日 — 基于 KB4493436* (OS 内部版本 15063.1784) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决连接到 Surface Hub 的某些 USB 设备的视频和音频同步问题。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4493436](https://support.microsoft.com/help/4493436)
</details>

<details>
<summary>2018 年 11 月 27 日 — 基于 KB4467699* (OS 内部版本 15063.1478) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决了阻止某些用户登录到“我的会议和文件”的问题。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KBKB4467699](https://support.microsoft.com/help/KB4467699)
</details>

<details>
<summary>2018 年 10 月 18 日 — 基于 KB4462939* (OS 内部版本 15063.1418) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* Skype for Business 修补程序: 
  * 解决了从睡眠状态恢复时 Skype for Business 连接的问题
  * 解决了设备连接到 Internet 时 Skype for Business 网络连接的问题
  * 解决从目录搜索用户时 Skype for Business 崩溃的问题
* 解决了在企业代理环境中 Hub 错误地报告“无 Internet 连接”的问题。
* 实现了允许客户选择加入新的白板体验的功能。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4462939](https://support.microsoft.com/help/4462939)
</details>

<details>
<summary>2018 年 8 月 31 日 — 基于 KB4343889* (OS 内部版本 15063.1292) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 添加对 Microsoft Teams 的支持
* 解决了 Intune 注册中任务管理的问题
* 使管理员能够为 Hub 禁用即时消息和电子邮件服务
* Surface Hub Skype for Business 应用的其他 bug 修复和可靠性改进

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4343889](https://support.microsoft.com/help/4343889)
</details>

<details>
<summary>2018 年 6 月 21 日 — 基于 KB4284830* (OS 内部版本 15063.1182) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* EMEA 中支持 GDPR 要求而进行的遥测更改

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4284830](https://support.microsoft.com/help/KB4284830)
</details>

<details>
<summary>2018 年 4 月 17 日 — 基于 KB4093117* (OS 内部版本 15063.1058) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决了有线投影的问题
* 为某些 MDM (移动设备管理) 策略启用批量更新
* 解决了国际呼叫的电话拨号器的问题
* 解决了 2 个 Surface Hub 加入同一会议时的图像解析度的问题
* 解决 OMS (运营管理套件) 证书处理错误的问题
* 解决了在会话结束后清理时出现的安全问题
* 解决了当 Surface Hub 指定到通道 149 到 165 时 Miracast 的问题
  * 由于区域性政府法规，频道 149 到 165 在欧洲、日本或以色列将继续无法使用

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4093117](https://support.microsoft.com/help/4093117)
</details>

<details>
<summary>2018 年 2 月 23 日 — 基于 KB4077528* (OS 内部版本 15063.907) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决了 MDM 设置未正确应用的问题
* 改进了清理过程

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4077528](https://support.microsoft.com/help/4077528)
</details>

<details>
<summary>2018 年 1 月 16 日 — 基于 KB4057144* (OS 内部版本 15063.877) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 添加了通过 MDM 管理“开始”菜单磁贴布局的功能
* 修复了密码旋转配置的 MDM Bug

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4057144](https://support.microsoft.com/help/4057144)
</details>

<details>
<summary>2017 年 12 月 12 日 — 基于 KB4053580* (OS 内部版本 15063.786) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决了 Skype for Business 通话期间摄像头视频闪烁 (画面撕裂或闪光) 的问题
* 解决了通知中心 SSD ID 问题

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4053580](https://support.microsoft.com/help/4053580)
</details>

<details>
<summary>2017 年 11 月 14 日 — 基于 KB4048954* (OS 内部版本 15063.726) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 功能更新，支持客户启用 802.1x 有线网络身份验证 (使用 MDM 策略)。
* 功能更新，可以使用户灵活选择自己想要的应用程序来打开文件。
* 安全修复，确保“结束会话”的清理操作彻底删除用户帐户与设备间的所有连接。
* 性能修复，缩短清理用时和 Miracast 连接用时。
* 引入了可用于临时会议期间的“便捷身份验证”功能。
* 安全修复，确保服务组件使用的代理与设备所配置的代理相同。
* 减少并更彻底地保护了经过设备传输的遥测，减少了带宽占用。
* 启用了可以使用户在会议结束后向 Microsoft 提供反馈的功能。

有关启用/禁用设备功能和服务的信息，请参阅 [Surface Hub 管理员指南](/surface-hub/)。
*[KB4048954](https://support.microsoft.com/help/4048954)
</details>

<details>
<summary>2017 年 10 月 10 日 — 基于 KB4041676* (OS 内部版本 15063.674) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* Skype for Business
  * 解决了从睡眠状态恢复时需要重新启动设备的问题。
  * 修复了外部联系人未能通过 Skype Online Hub 帐户解决的问题。
* PowerPoint
  * 修复了某些 PowerPoint 演示文稿不能在中心上投影的问题。
* 概要
  * 进行了相关修复，解决了系统管理员无法禁用 USB 端口的问题。

*[KB4041676](https://support.microsoft.com/help/4041676)
</details>

<details>
<summary>2017 年 9 月 12 日 — 基于 KB4038788* (OS 内部版本 15063.605) 的团队更新 </summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 安全性
  * 解决了设备从睡眠状态唤醒时 Bitlocker 存在的问题。
* 概要
  * 减少设备运行状况遥测的频率/数量，同时提高了系统性能。
  * 修复了阻止设备收集系统日志的问题。

*[KB4038788](https://support.microsoft.com/help/4038788)
</details>

<details>
<summary>2017 年 8 月 1 日 — 基于 KB4032188* (OS 内部版本 15063.498) 的团队更新</summary>

* Skype for Business 
  * 解决了需要重试或重新启动系统的 Skype for Business 登录问题。
  * 解决了 Skype for Business 会议时间显示错误的问题。
  * 进行了相关修复，提高了 Surface Hub Skype for Business 的可靠性。

*[KB4032188](https://support.microsoft.com/help/4032188)
</details>

<details>
<summary>2017 年 6 月 27 日 — 基于 KB4022716* (OS 内部版本 15063.442) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决了 NVIDIA 驱动程序崩溃的问题，从而避免可能需要关闭处于睡眠状态的 84 英寸 Surface Hub 的电源 (需要手动重启)。
* 解决了某些应用无法在 84 英寸 Surface Hub 上启动的问题。

*[KB4022716](https://support.microsoft.com/help/4022716)
</details>

<details>
<summary>2017 年 6 月 13 日 — 基于 KB4022725* (OS 内部版本 15063.413) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 概要
  * 解决了使用手写笔时笔墨滴落的问题
  * 解决了导致“清理”会议时间延长的问题

*[KB4022725](https://support.microsoft.com/help/4022725)
</details>

<details>
<summary>2017 年 5 月 24 日 — 基于 KB4021573* (OS 内部版本 15063.328) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 概要
  * 解决了更新期间保留代理设置的问题

*[KB4021573](https://support.microsoft.com/help/4021573)
</details>

<details>
<summary>2017 年 5 月 9 日 — 基于 KB4016871* (OS 内部版本 15063.296) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 概要
  * 解决了睡眠/唤醒周期问题
  * 解决了多个重置和恢复问题
  * 解决了“更新历史记录”选项卡问题
  * 解决了 Miracast 服务启动问题
* 应用
  * 修复了应用包更新错误

*[KB4016871](https://support.microsoft.com/help/4016871)
</details>

<details>
<summary>适用于 Surface Hub 的 Windows 10 协同版创意者更新 1703 - 常规发行说明 (操作系统内部版本 15063.0)</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 改善大屏幕体验 
  * 改进了“欢迎”和“开始”中的会议传送
  * 可直接从“开始”菜单加入会议和结束会话
  * 应用可在会话期间利用屏幕的更多部分
  * 简化了 Skype 控件
  * 改进了用于提供反馈的机制
* 访问我的个人内容*
  * “欢迎”或“开始”中的个人单一登录
  * 可直接从“开始”菜单加入会议和结束会话
  * 可直接从“开始”菜单通过 OneDrive for Business 访问个人文件
  * 预填充了与会者的登录信息
  * 利用“验证器”应用简化了身份验证流**
* 部署和可管理性 
  * 通过批量预配简化了 OOBE 体验
  * 基于云的设备恢复服务
  * 企业客户端证书支持
  * 改进了代理凭据支持
  * 添加和改进了 Skype 服务质量 (QoS) 配置支持
  * 添加了在“设置”中设置默认设备音量的功能
  * 改进了 MDM 对 Surface Hub [设置](/surface-hub/remote-surface-hub-management)的支持
* 增强了安全性 
  * 添加了将 U 盘仅限于 BitLocker 的功能
  * 添加了通过 MDM 禁用 USB 端口的功能
  * 添加了在超时期间禁用“恢复会话”功能的功能
  * 添加了有线 802.1x 支持
* 音频和投影
  * 杜比音频“人工扬声器”增强功能
  * 减低了在 Skype for Business 通话期间使用手写笔时的“笔击”声音
  * 添加了对 Miracast 基础结构连接的支持
* 可靠性和性能修复
  * 解决了多个重置和恢复问题
  * 解决了利用客户端证书时的 Surface Hub Exchange 身份验证问题
  * 改进了 WLAN 网络连接和凭据稳定性
  * 修复了视频播放期间的 Miracast 音频弹出和同步问题
  * 包括了用于禁用自动连接行为的设置

*单一登录功能需要使用 Office365 和 OneDrive for Business** 有关服务要求，请参阅管理员指南

</details>

## <a name="windows-10-team-anniversary-update-1607"></a>Windows 10 协同版周年更新 (1607)

<details>
<summary>2017 年 3 月 14 日 — 基于 KB4013429* (OS 内部版本 14393.953) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 概要
  * 文件资源管理器的安全修复，用于防止导航到受限的文件位置
* Skype for Business
  * 进行了相关修复，解决了远程桌面屏幕共享期间出现的延迟问题

*[KB4013429](https://support.microsoft.com/help/4013429)
</details>

<details>
<summary>2017 年 1 月 10 日 — 基于 KB4000825* (OS 内部版本 14393.693) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 支持选择将 106/109 键盘布局用于日语物理键盘

*[KB4000825](https://support.microsoft.com/help/4000825)
</details>

<details>
<summary>2016 年 12 月 13 日 — 基于 KB3206632* (OS 内部版本 14393.576) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 解决了有线连接音频失真问题

*[KB3206632](https://support.microsoft.com/help/3206632)
</details>

<details>
<summary>2016 年 11 月 4 日 — 基于 KB3200970* (OS 内部版本 14393.447) 的团队更新</summary>

此适用于 Surface Hub 的 Windows 10 协同版周年更新(版本 1607)包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* Skype for Business bug 修复，用于提高可靠性

*[KB3200970](https://support.microsoft.com/help/3200970)
</details>

<details>
<summary>2016 年 10 月 25 日 — 基于 KB3197954* (OS 内部版本 14393.351) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 支持操作系统和 BIOS 中的全新“睡眠”功能，可减少 Surface Hub 的耗电量，并提高其长期可靠性
* 概要
  * 解决了屏幕键盘有时不显示的情况
  * 解决了打开已计划会议时偶尔发生白板应用程序转向的问题
  * 解决了在重置设备后阻止管理员更改本地管理员密码的问题
  * 更改了 BIOS，可解决重置设备期间状态栏跟踪出现的问题
  * UEFI 更新，可解决电源关闭问题

*[KB3197954](https://support.microsoft.com/help/3197954)
</details>

<details>
<summary>2016 年 10 月 11 日 — 基于 KB3194496* (OS 内部版本 14393.222) 的团队更新</summary>

此更新为 Surface Hub 带来 Windows 10 协同版周年更新，并且包含质量改进和安全修复。 (安装后设备将运行 Windows 10 版本 1607。)[Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history) 中尚未概述 Surface Hub 的关键更新，包括:

* Skype for Business
  * 提高了加入会议时的性能，包括解决了使用联合帐户加入会议时出现的问题
  * 适用于 Surface Hub 的 Skype for Business 目前提供基于视频的屏幕共享 (VBSS) 支持
  * 解决了空闲时间超过 5 分钟后断开连接的问题
  * 解决了 Skype 中心到中心屏幕共享失败的问题
  * 改进了 Skype 视频，其中包括:
    * 与多个视频演示者举行会议期间丢失视频
    * 通话期间剪裁视频
    * 无法为其他参与者显示传出呼叫视频
  * 解决了出现 UPN 登录错误的问题
  * 解决了使用会话启动协议 (SIP) 呼叫期间拨号盘存在的问题
* 白板
  * 用户现在可以使用 OneDrive 联机服务 (通过共享功能) 保存和恢复白板会话
  * 改进了从扩展坞中删除手写笔时启动白板的操作
* 应用
  * 预安装了 OneDrive 应用，用于访问你的个人和工作文件
  * 预安装了 Photos 应用，用于查看照片和观看视频
  * 预安装了 PowerBI 应用，用于查看仪表板
  * Office 应用 (Word、Excel 和 PowerPoint) 都支持墨迹
  * 基于 Surface Hub 的 Edge 目前支持基于 Flash 的网站
* 概要
  * 支持选择音频设备 (适用于使用外部音频设备连接的 Surface Hub)
  * 在 DisplayPort 输出连接器上实现了对 HDCP 的支持
  * 更改了系统 UI 设置，可优化可用性 (有关其他详细信息，请参考[用户和管理员指南](https://www.microsoft.com/surface/support/surface-hub))
  * 修复了 Bug 并优化了性能，可加速 Azure Active Directory 登录流
  * 显著缩短了重置和还原 Surface Hub 所需的时间
  * Windows Defender UI 已添加在设置中
  * 改进了通过 UX 触控启动的操作
  * 在受支持设备上实现了对通过 Miracast 执行 1080p 以上无线投影的支持
  * 解决了启动时出现“没有 Internet 连接”和“约会可能已过期”的通知误报状态
  * 提升了屏幕键盘的可靠性
  * 添加了对使用 Windows 映像和配置设计器 (ICD) 创建 Surface Hub 预配程序包的支持，并改进了基于操作管理套件 (OMS) 的 Surface Hub 监控解决方案

*[KB3194496](https://support.microsoft.com/help/3194496)
</details>

## <a name="updates-for-windows-10-version-1511"></a>Windows 10 版本 1511 的更新

<details>
<summary>2016 年 11 月 4 日 — 基于 KB3198586* (OS 内部版本 10586.679) 的团队更新</summary>

此适用于 Surface Hub 的 Windows 10 协同版 (版本 1511) 的更新包含质量改进和安全修复 (在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述)。 此更新中没有 Surface Hub 的特定项目。

*[KB3198586](https://support.microsoft.com/help/3198586)
</details>

<details>
<summary>2016 年 7 月 12 日 — 基于 KB3172985* (OS 内部版本 10586.494) 的团队更新</summary>

此更新包含质量改进和安全修补。 此更新未引入任何新的操作系统功能。 特定于 Surface Hub 的关键更改 (这些更改尚未包括在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中) 包含:

* 修复了导致 Windows 系统崩溃的问题
* 修复了导致 Edge 反复崩溃的问题
* 修复了导致预关机服务崩溃的问题
* 修复了在会话后无法正确删除某应用数据的问题
* 更新了 Broadcom NFC 驱动程序，可提高 NFC 性能
* 更新了 Marvell WLAN 驱动程序，可提高 Miracast 性能
* 更新了 Nvidia 驱动程序，可修复显示器 bug，包括 84 英寸 Surface Hub 设备显示内容变暗或模糊的问题
* 修复了多个 Skype for Business 问题，其中包括: 
  * 导致了 Skype for Business 在会议期间断开连接的问题
  * 在会议组织者使用联合配置时用户无法加入会议的问题
  * 启用 Skype for Business 应用程序共享
  * 导致了 Skype 应用程序崩溃的问题
* 在“设置”中添加了提示，用于通知用户如果设备重置在完成前中断，则操作系统可能会受损

*[KB3172985](https://support.microsoft.com/help/3172985)
</details>

<details>
<summary>2016 年 6 月 14 日 — 基于 KB3163018* (OS 内部版本 10586.420) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 此更新未引入任何新的操作系统功能。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 受限的版本。 有关 Surface Hub 的特定程序包的详细信息，请参考 2016 年 7 月 12 日 - [KB3172985](https://support.microsoft.com/en-us/help/3172985) (操作系统内部版本 10586.494)

*[KB3163018](https://support.microsoft.com/help/3163018)
</details>

<details>
<summary>2016 年 5 月 10 日 — 基于 KB3156421* (OS 内部版本 10586.318) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 此更新未引入任何新的操作系统功能。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 修复了阻止安装某些 Microsoft Store 应用 (OneDrive) 的问题
* 修复了导致触控输入在应用程序中停止响应的问题

*[KB3156421](https://support.microsoft.com/help/3156421)
</details>

<details>
<summary>2016 年 4 月 12 日 — 基于 KB3147458* (OS 内部版本 10586.218) 的团队更新</summary>

此 Surface Hub 更新包含质量改进和安全修复。 此更新未引入任何新的操作系统功能。 Surface Hub 的关键更新 (尚未在 [Windows 10 更新历史记录](https://support.microsoft.com/help/4018124/windows-10-update-history)中概述) 包含:

* 修复了在会话之间未正确重置音量的问题

*[KB3147458](https://support.microsoft.com/help/3147458)
</details>

## <a name="related-topics"></a>相关主题

* [Windows 10 版本信息](https://go.microsoft.com/fwlink/p/?LinkId=724328)
* [Windows 10 的 11 月更新: 常见问题解答](https://windows.microsoft.com/windows-10/windows-update-faq)
* [Microsoft Surface 更新历史记录](https://go.microsoft.com/fwlink/p/?LinkId=724327)
* [Microsoft Lumia 更新历史记录](https://go.microsoft.com/fwlink/p/?LinkId=785968)
* [获取 Windows 10](https://go.microsoft.com/fwlink/p/?LinkId=616447)

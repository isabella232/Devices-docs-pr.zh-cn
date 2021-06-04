---
title: Surface Hub 如何解决 Wi-Fi Direct 的安全问题
description: 有关 Wi-fi 直接安全风险的指南。
keywords: 更改历史记录
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/27/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d877d9b6a4e330a74a9d79cf1150487d89c0da23
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830862"
---
# Surface Hub 如何解决 WLAN Direct 的安全问题

Microsoft Surface Hub 是一款一体式的高效率设备，团队借助它能够更好地进行集体讨论、协作和分享想法。 Surface Hub 通过 Wi-fi Direct 依靠 Miracast 进行无线投影。

本文介绍 Wi-fi 直接安全漏洞、Surface Hub 如何解决这些风险，以及管理员如何为最高级别的安全配置 Surface Hub。 此信息将帮助具有高安全性要求的客户保护其 Surface Hub 连接的网络和传输中的数据。

本文的目标读者是希望使用最佳安全设置在其企业环境中部署 Surface Hub 的 IT 和网络管理员。

##  <a name="overview"></a>概述

Surface Hub 的安全性广泛地依赖于 Wi-fi Direct/Miracast 以及关联的802.11、Wi-fi 保护访问（WPA2）和无线保护设置（WPS）标准。 由于设备仅支持 WPS （而不是 WPA2 预共享密钥 [PSK] 或 WPA2 Enterprise），因此与802.11 加密相关的问题会得到简化。

Surface Hub 与 Miracast 接收器的字段进行操作。 因此，它容易受到类似于所有基于 WPS 的无线网络设备的一组类似的攻击。 但是，WPS 的 Surface Hub 实现中内置了额外的预防措施。 此外，它的内部体系结构可帮助防止已损坏 Wi-fi Direct/Miracast 层的攻击者将超过网络接口的攻击者移到其他攻击面和连接的企业网络。

##  <a name="wi-fi-direct-background"></a>WLAN Direct 背景

Miracast 是 Wi-fi 显示标准的一部分，由 Wi-fi Direct 协议支持。 这些标准受用于屏幕共享和协作的现代移动设备的支持。

Wi-fi Direct 或 Wi-fi "对等" （P2P）是来自 "临时" 网络的 Wi-fi 联盟的标准。 受支持的设备可以直接通信，并在没有常规 Wi-fi 接入点或 Internet 连接的情况下创建网络组。

Wlan Direct 的安全性由 WPA2 在 WPS 标准下提供。 设备的身份验证机制可以是一个数字 pin （WPS-PIN）、物理或虚拟推送按钮（WPS-PBC）或带外消息，如近域通信（WPS-OOO）。 Surface Hub 同时支持引脚方法和推拉按钮方法，这是默认设置。

在 Wi-fi Direct 中，组创建为以下类型之一：
- *持久*的，可通过使用存储的密钥材料进行自动重新连接
- *暂时*的，在此情况下，设备不能重新进行身份验证而无需用户操作

Wi-fi Direct 组通过协商协议确定*组所有者*（GO），该协议模仿已建立的 wi-fi Direct 组的 "工作站" 或 "访问点" 功能。 Wi-fi Direct GO 提供身份验证（通过 "内部注册机构"），并推动上游网络连接。 对于 Surface Hub，不会发生此转协商。 网络仅以 "自治" 模式运行，Surface Hub 始终是组所有者。 最后，Surface Hub 本身不会作为客户端加入其他 Wi-fi Direct 网络。

##  <a name="how-surface-hub-addresses-wi-fi-direct-vulnerabilities"></a>Surface Hub 如何解决 Wi-fi 直接漏洞

**Wi-fi 直接邀请、广播和发现过程中的漏洞和攻击：** Wi-fi Direct/Miracast 攻击可能针对组建立、对等发现、设备广播或邀请流程中的弱点。

|Wi-fi Direct 漏洞 | Surface Hub 缓解 |
| --- | --- |
| 发现过程可能会在较长时间内保持活动状态，这样就可以在不批准设备所有者的情况下允许邀请和连接建立。 | Surface Hub 仅作为组所有者运行，这不会执行客户端发现或转到协商过程。 你可以完全禁用无线投影以关闭广播。 |
| 通过 PBC 的邀请和发现允许未经身份验证的攻击者执行重复的连接尝试，或自动接受未经身份验证的连接。 | 通过要求使用 WPS 引脚 security，管理员可以降低此类未经授权的连接或 "邀请炸弹" 的潜在可能性，在此情况下，将重复发送邀请，直到用户误接受了邀请。 |

**Wi-fi 受保护设置（WPS）按钮连接（PBC）与 PIN 输入：** 在 WPS 引脚方法设计和实施中演示了公开的弱点。 WPS-PBC 有其他漏洞，这些漏洞可能允许针对一次性使用的协议进行活动攻击。

| Wi-fi Direct 漏洞 | Surface Hub 缓解 |
| --- | --- |
| WPS-PBC 易受主动攻击者的攻击。 WPS 规范状态： "PBC" 方法的熵为零，并且仅针对被动窃听攻击提供保护。 PBC 可抵御窃听攻击，并能采取措施，防止设备加入非设备所有者选择的网络。 但是，如果没有身份验证，则意味着 PBC 不能防范活动攻击。 " 攻击者可以使用选择性无线拥塞或其他拒绝服务技术触发意外的 Wi-fi Direct GO 或连接。 此外，仅有物理邻近感应的活动攻击者可以反复地断开任何 Wi-fi Direct 组并尝试攻击，直至成功。 | 在 Surface Hub 配置中启用 WPS PIN 安全性。 Wi-fi WPS 规范状态： "仅当没有支持 PIN 的注册机构可用且 WLAN 用户愿意接受与 PBC 相关联的风险时，才应使用 PBC 方法。" |
| WPS-PIN 实现可能会受到强力攻击，其目标是 WPS 标准中的一个漏洞。 在一系列 Wi-fi 硬件制造商的过去几年中，拆分引脚验证的设计会导致多个实施漏洞。 在2011中，研究人员斯蒂芬 Viehböck 和 Craig Heffner 发布有关此漏洞的信息和工具，例如 "Reaver" 作为概念证明。 |   Surface Hub 中的 Microsoft 实现 WPS 每30秒更改一次 PIN 码。 要破译 PIN 码，攻击者必须在30秒内完成整个攻击。 鉴于此区域中的工具和研究的当前状态，通过 WPS 进行的强力 PIN 破解攻击不太可能成功。 |
| 由于较弱的初始密钥（E-S1，E S2）熵，因此可通过脱机攻击破译 WPS PIN 码。 在2014中，Dominique Bongard 介绍了一个 "Pixie 灰尘" 攻击，在此攻击中，无线设备中伪随机数字生成器（PRNG）的初始随机性不好，允许进行脱机暴力攻击。 | Surface Hub 中的 WPS 的 Microsoft 实现不容易受到此脱机 PIN 强力攻击。 WPS-PIN 针对每个连接进行了随机化。 |

**网络服务意外暴露：** 由于配置错误（如绑定到 "all"/0.0.0.0 接口），用于以太网或 WLAN 服务的网络守护程序可能会意外暴露。 其他可能的原因包括配置不当的设备防火墙或缺少防火墙规则。

| Wi-fi Direct 漏洞 | Surface Hub 缓解 |
| --- | --- |
| 错误配置会将漏洞或未经身份验证的网络服务绑定到“所有”接口，包括 WLAN Direct 接口。 这可能会暴露不应被 Wi-fi Direct 客户端访问的服务，这些服务可能会很弱，也可能会自动进行身份验证。 | 在 Surface Hub 中，默认防火墙规则仅允许所需的 TCP 和 UDP 网络端口，并且默认情况下拒绝所有入站连接。 通过启用 WPS PIN 模式配置加强身份验证。|

**桥接 Wi-fi Direct 和其他有线或无线网络：** WLAN 或以太网网络之间的网络桥接是否违反了 Wi-fi Direct 规范。 这种桥或错误配置可能会有效地降低或删除内部公司网络的无线访问控制。

| Wi-fi Direct 漏洞 | Surface Hub 缓解 |
| --- | --- |
| WLAN Direct 设备可允许对桥接的网络连接进行未经身份验证或经过不当身份验证的访问。 这可能会允许 Wi-fi Direct 网络将流量路由到内部以太网 LAN 或其他基础结构，或与现有 IT 安全协议发生冲突的企业 WLAN 网络。 | Surface Hub 无法配置为桥接无线接口或允许在不同网络之间路由。 默认防火墙规则为任何此类路由或桥路连接添加深度防护。 |

**使用 Wi-fi Direct "旧版" 模式：** 在 "旧版" 模式下操作时，可能会对意外的网络或设备造成暴露。 如果未启用 WPS-PIN，则可能会发生设备欺骗或非预期连接。

| Wi-fi Direct 漏洞 | Surface Hub 缓解 |
| --- | --- |
| 系统通过支持 WLAN Direct 和 802.11 基础结构客户端，以“旧”支持模式运行。 这可能会无限期地公开连接设置阶段，允许加入组或受邀请的设备在其预定设置阶段终止后进行连接。 |    Surface Hub 不支持 Wi-fi Direct 旧客户端。 即使启用 WPS-PIN 模式，也只能对 Surface Hub 进行 WLAN Direct 连接。 |

**连接设置期间的 Wi-fi DIRECT GO 协商：** Wi-fi Direct 中的组所有者类似于常规802.11 无线网络中的 "访问点"。 协商可能会受恶意设备操纵。

|Wi-fi Direct 漏洞 |   Surface Hub 缓解 |
| --- | --- |
| 如果组是动态建立的，或者可以使用 Wi-fi Direct 设备加入新组，则组所有者协商可以由恶意设备赢得，该设备始终指定最大组所有者 "意图" 值15。 （但如果设备配置为始终是组所有者，则连接将失败。）  | Surface Hub 利用 Wi-fi Direct "自治模式"，该模式会跳过连接设置的 "转到协商" 阶段。 并且 Surface Hub 始终是组所有者。 |

**意外或恶意的 wi-fi deauthentication：** Wi-fi deauthentication 是一种旧攻击，在此攻击中，本地攻击者可以加速连接设置过程中的信息泄漏、触发全新的四次握手、针对活动攻击的目标 Wi-fi Direct-PBC，或创建拒绝服务攻击。

| Wi-fi Direct 漏洞 | Surface Hub 缓解 |
| --- | --- |
| 未经身份验证的攻击者可以发送 Deauthentication 数据包，从而使工作站重新进行身份验证，然后嗅探结果握手。 可能会尝试对生成的握手进行加密或暴力攻击。 这些攻击的缓解措施包括为预共享密钥强制执行长度和复杂性策略，配置访问点（如果适用）检测 deauthentication 数据包的恶意级别，以及使用 WPS 自动生成强密钥。 在 PBC 模式中，用户与物理或虚拟按钮交互，以允许任意设备关联。 此过程应仅在设置时（在短窗口内）发生。 按钮自动 "推送" 后，设备将接受通过规范引脚值（全为零）关联的任何站。 解除身份验证可以强制进行重复设置过程。 |   Surface Hub 在引脚或 PBC 模式中使用 WPS。 不允许 PSK 配置。 此方法有助于强制生成强密钥。 最好为 Surface Hub 启用 WPS PIN 安全性。 |
| 除了拒绝服务攻击之外，deauthentication 数据包还可用于触发重新连接，以便针对 WPS-PBC 重新打开活动攻击的机会窗口。 |   在 Surface Hub 配置中启用 WPS PIN 安全性。 |

**基本无线信息泄漏：** 无线网络、802.11 或其他，本身就是信息泄露的危险。 虽然此信息通常是连接或设备元数据，但此问题仍然是任何802.11 网络管理员的已知风险。 通过 WPS-PIN 对设备进行身份验证的 WLAN Direct 有效显示了与 PSK 或企业 802.11 网络相同的信息。

| Wi-fi Direct 漏洞 | Surface Hub 缓解 |
| --- | --- |
| 在广播、连接设置甚至已加密连接的普通操作中，有关设备和数据包大小的基本信息均以无线方式传输。 在基本级别，无线范围内的本地攻击者可以检查相关的802.11 信息元素，以确定无线设备的名称、通信设备的 MAC 地址以及可能的其他详细信息，如无线堆栈的版本、数据包大小或配置的接入点或组所有者选项。  | Surface Hub 使用的 Wi-fi Direct 网络不能进一步保护元数据泄漏，就像802.11 企业版或 PSK 无线网络一样。 物理安全性和删除无线邻近感应的潜在威胁有助于减少潜在的信息泄漏。 |

**无线恶意攻击或欺骗攻击：** 哄骗无线名称是一种简单的已知漏洞，本地攻击者可使用该漏洞引诱不受信任或误认为用户连接的用户。

| Wi-fi Direct 漏洞 | Surface Hub 缓解 |
| --- | --- |
| 通过哄骗或克隆目标网络的无线名称或 "SSID"，攻击者可以诱使用户连接到虚假的恶意网络。 通过支持未经身份验证的自动加入 Miracast，攻击者可以捕获所需的显示资料或在连接设备上启动网络攻击。 | 虽然在加入欺骗 Surface Hub 时没有特定的保护措施，但此漏洞有两种减轻部分影响的方式。 首先，任何潜在攻击必须在物理上位于 WLAN 范围内。 第二，此攻击仅在第一次连接期间才可能。 后续连接使用永久 Wi-fi Direct 组，并且在将来的中心使用时，Windows 将记住并优先处理此之前的连接。 （注意：对于此报告，不考虑对 MAC 地址、Wi-fi 通道和 SSID 的欺骗，可能会导致 Wlan 行为不一致。）总而言之，对于任何缺少企业 WPA2 协议（如 EAP-TLS 或 EAP-PWD）的802.11 无线网络而言，此弱点是一个基本问题，这种情况下，Wi-fi Direct 不支持。 |

##  <a name="surface-hub-hardening-guidelines"></a>Surface Hub 强化指南

Surface Hub 是专为促进协作和允许用户快速高效地开始和加入会议而设计。 为此方案优化了 Surface Hub 的默认 Wi-fi 直接设置。

对于其他无线接口安全性，Surface Hub 用户应启用 WPS PIN 安全性设置。 此设置禁用 WPS-PBC 模式并提供客户端身份验证。 它通过防止与 Surface Hub 的未经授权连接来提供最强大的保护级别。

如果你仍然担心 Surface Hub 的身份验证和授权，我们建议你将设备连接到单独的网络。 你可以使用 Wi-fi （如 "来宾" Wi-fi 网络）或单独的以太网网络（最好是完全不同的物理网络）。 但 VLAN 还可以提供额外的安全性。 当然，此方法可能会妨碍与内部网络资源或服务的连接，并且可能需要其他网络配置才能重新获得访问权限。

此外，还建议：
- [安装常规系统更新](manage-windows-updates-for-surface-hub.md) 
- 更新 Miracast 设置以禁用自动显示模式

##  <a name="learn-more"></a>了解详情

- [WLAN Direct 规范](http://www.wi-fi.org/discover-wi-fi/wi-fi-direct)
- [无线保护设置 (WPS) 规范](http://www.wi-fi.org/discover-wi-fi/wi-fi-protected-setup)




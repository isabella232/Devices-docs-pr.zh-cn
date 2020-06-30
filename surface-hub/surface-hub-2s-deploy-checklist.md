---
title: Surface Hub 2 部署清单
description: 使用预部署和后期部署核对清单验证 Surface Hub 2 的部署。
keywords: 值之间以逗号分隔
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 3c30892a3ae4f534006aa32ad6d969b42a52cbf2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831911"
---
# Surface Hub 2 部署清单

## Surface Hub 2 预部署清单

|**项目**|**响应**|
|:------ |:------ |
|**设备帐户名称**| |
|**设备帐户 UPN**| |
|**ActiveSync 策略**| |
|**日历处理配置已完成**| ☐是 <br>  ☐否 |
|**设备友好名称**| |
|**设备主机名**| |
|**团体**| ☐无 <br> ☐ Active Directory 从属关系 <br> ☐ Azure Active Directory |
|**Microsoft 团队模式**| ☐模式0 <br> ☐模式1 <br> ☐模式2 |
|**设备管理**| ☐是，Microsoft Intune <br> ☐是，其他移动设备管理器 [MDM] <br> ☐无 |  
|**代理**| ☐自动配置 <br> ☐代理服务器 <br> ☐代理自动配置（PAC）文件 |
|**代理身份验证**| ☐设备帐户凭据 <br> ☐提示输入凭据 |
|**密码轮换**| ☐ <br> ☐关闭 |
|**Skype for Business 其他域名（仅限内部部署）**| |
|**会话超时时间**| |
|**会话超时操作**| ☐结束会话 <br> ☐允许简历 |
|**我的会议和文件**| ☐启用 <br> ☐禁用 |
|**锁定屏幕超时**| |
|**睡眠空闲超时**| |
|**蓝牙**| ☐ <br> ☐关闭 |
|**仅使用 BitLocker USB 驱动器**| ☐ <br> ☐关闭 |
|**安装其他证书（仅限内部部署）**| |
|**Windows 更新**| ☐适用于企业的 Windows 更新 <br> ☐ Windows Server Update Services [WSUS] |
|**Surface app 扬声器设置**| ☐滚动支架 <br> ☐墙-已安装 |
|**IP 地址**| ☐有线-DHCP <br> ☐有线-DHCP 保留 <br> ☐无线-DHCP <br> ☐无线-DHCP 保留 |

## Surface Hub 2 后期部署清单

|**选中**|**响应**|
|:------|:---------|
|**设备帐户同步**| ☐是 <br> ☐否 |
|**Bitlocker 密钥**| ☐保存到文件（无隶属关系） <br> 在 Active Directory 中保存的☐（广告从属关系） <br>在 Azure AD 中保存的☐（Azure AD 从属关系） |
|**设备操作系统更新**| ☐已完成 |
|**Windows 应用商店更新**| ☐自动 <br> ☐手册 |
|**Microsoft 团队计划会议**| 收到☐确认电子邮件 <br> "开始" 屏幕上显示☐会议 <br>  ☐一个触控联接函数 <br> ☐能够加入音频 <br> ☐能够加入视频 <br> ☐能够共享屏幕 ||
|**Skype for Business 计划会议**| 收到☐确认电子邮件 <br> "开始" 屏幕上显示☐会议 <br> ☐一条触摸联接是否正常工作 <br> ☐能够加入音频 <br> ☐能够加入视频 <br> ☐能够共享屏幕 <br> ☐能够发送/接收即时消息 |
|**已邀请的计划会议**| 拒绝☐会议 |
|**Microsoft 团队临时会议**| ☐邀请其他用户工作 <br> ☐能够加入音频 <br> ☐能够加入视频 <br> ☐能够共享屏幕 |
|**Skype for Business 计划会议**| ☐邀请其他用户工作 <br> ☐能够加入音频 <br> ☐能够加入视频 <br> ☐能够共享屏幕 <br> ☐能够发送/接收即时消息 |
|**Microsoft Whiteboard**| 从欢迎/开始屏幕☐启动 <br> ☐从 Microsoft 团队发起 | 
|**Skype/团队来电**| ☐能够加入音频<br>☐能够加入视频 <br> ☐能够共享屏幕 <br> ☐能够发送/接收即时消息（仅 Skype for business） |
|**传入的实时视频流**| ☐最大2（Skype for Business） <br> ☐最多4个（Microsoft 团队） |
|**Microsoft 团队模式0行为**| ☐欢迎/开始屏幕上的 Skype for Business 磁贴 <br> ☐可以加入计划的 Skype for Business 会议（Skype UI） <br> ☐可以加入计划的团队会议（团队 UI） |
|**Microsoft 团队模式1行为**| ☐团队在欢迎/开始屏幕上平铺 <br> ☐可以加入计划的 Skype for Business 会议（Skype UI） <br> ☐可以加入计划的团队会议（团队 UI） |
|**Microsoft 团队模式2行为**| ☐团队在欢迎/开始屏幕上平铺 <br> ☐可以加入计划的团队会议 <br> ☐无法加入 Skype for Business 会议 |

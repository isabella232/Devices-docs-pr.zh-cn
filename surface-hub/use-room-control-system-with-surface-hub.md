---
title: 使用房间控制系统 (Surface Hub)
description: 可以将房间控制系统与 Microsoft Surface Hub 结合使用。
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: 房间控制系统, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830824"
---
# 使用房间控制系统 (Surface Hub)


可以将房间控制系统与 Microsoft Surface Hub 结合使用。

将房间控制系统与 Surface Hub 结合使用包括通常通过 Surface Hub 底部的 RJ11 串行端口将房间控制硬件连接到 Surface Hub。

## 终端设置

若要连接到房间控制系统控制面板，无需在 Surface Hub 上配置任何终端设置。 如果想要将电脑或笔记本电脑连接到 Surface Hub，然后从该 Surface Hub 发送一系列命令，可以使用终端仿真器程序（如 Tera Term 或 PuTTY）。 

| 设置 | 值 |
| --- | --- |
| 波特率 | 115200 |
| 数据位 | 个 | 
| 停止位 | raid-1 |
| 奇偶校验 | 无 |
| 流控制 | 无 |
| 换行 | 每个回车 |
 

## 接线图

可以使用标准的 RJ-11 (6P6C) 连接器将 Surface Hub 串行端口连接到房间控制系统。 这是推荐的方法。 还可以使用 RJ-11 4 导线电缆，但我们不建议使用此方法。

此图显示用于 RJ-11 (6P6C) 到 DB9 电缆的正确引出线。

![显示了接线图的图像。](images/room-control-wiring-diagram.png)

## 命令集

房间控制系统使用适用于命令的常见会议室方案。 命令源自房间控制系统，通过串行连接与 Surface Hub 进行通信。 命令基于 ASCII，Surface Hub 将在状态发生更改时进行确认。

以下命令修饰符可用。 以换行符 (\n) 终止命令。 随时响应不是由管理端口命令直接触发的状态更改。

| 修饰符 | 结果 |
| --- | --- |
| + | 增加值 |
| - | 减少值 |
| = | 设置离散值 |
| ? | 查询当前值 |
 

## 电源

Surface Hub 可以处于以下一种电源状态。

| 状态 | 能源星状态| 描述 |
| --- | --- | --- |
| 0 | S5 | 关闭 |
| raid-1 | - | 通电（不确定） |
| ppls-2 | S3 | 睡眠 |
| 级 | S0 | 就绪 |


在“替换电脑”模式中，电源状态仅为“就绪”和“关闭”，并且仅更改屏幕。 管理端口无法用于接通替换电脑电源。 

| 状态 | 能源星状态| 描述 |
| --- | --- | --- |
| 0 | S5 | 关闭 |
| 级 | S0 | 就绪 |

对于控制设备，5/就绪以外的任何其他状态均视为关闭。 每个 PowerOn 命令都会产生两种状态更改和响应。 

| 命令 | 状态更改| 响应 |
| --- | --- | --- |
| PowerOn | 设备打开（屏幕 + 电脑）。</br></br>电脑服务通知 SMC 电脑已准备就绪。 |  Power=0</br></br>Power=5 |
| PowerOff | 设备转换到环境状态（电脑打开，屏幕变暗）。 |  Power=0 |
| Power? |  SMC 报告上次已知电源状态。 |  Power=<#> |



## 亮度

当前亮度级别范围从 0 到 100。

可以通过房间控制系统或其他系统发送对亮度级别的更改。

| 命令 | 状态更改 |响应 |
| --- | --- | --- |
| Brightness+ | 系统管理控制器 (SMC) 发送亮度增加命令。</br></br>房间控制系统上的电脑服务向 SMC 通知新的亮度级别。 |  Brightness = 51 |
| Brightness- |  SMC 发送亮度减弱命令。</br></br>电脑服务向 SMC 通知新的亮度级别。 | Brightness = 50 |

## 音量

当前音量级别范围从 0 到 100。

可以通过房间控制系统或其他系统发送对音量级别的更改。

>[!NOTE]
>音量命令将仅控制嵌入或替换电脑模式的音量，而不控制来自[来宾源](connect-and-display-with-surface-hub.md)的音量。

| 命令 | 状态更改 | 响应</br>（处于[替换电脑模式](connect-and-display-with-surface-hub.md#replacement-pc-mode)） |
| --- | --- | --- |
| Volume+ |  SMC 发送音量提高命令。</br></br>电脑服务向 SMC 通知新的音量级别。 |  Volume = 51 |
| Volume- |  SMC 发送音量降低命令。</br></br>电脑服务向 SMC 通知新的音量级别。 |  Volume = 50 |


 

## 音频静音

可将音频设为静音。

| 命令 | 状态更改 | 响应 |
| --- | --- | --- |
| AudioMute+ |  SMC 发送音频静音命令。</br></br>电脑服务通知 SMC 已将音频设置为静音。 |  无 |


 

## 视频源

可以使用多个显示源。

| 状态 | 描述 | 
| --- | --- |
| 0 |  板载电脑 |
| raid-1 |  DisplayPort |
| ppls-2 |  HDMI |
| 三维空间 |  VGA |


 

可以通过房间控制系统或其他系统发送对显示源的更改。

| 命令 | 状态更改 | 响应 |
| --- | --- | --- |
| Source=# |  SMC 将更改为所需源。</br></br>电脑服务通知 SMC 已切换显示源。 |  Source=&lt;#&gt; |
| Source+ |  SMC 将循环到下一个活动输入源。</br></br>电脑服务向 SMC 通知当前输入源。 |  Source=&lt;#&gt; |
| Source- | SMC 将循环到上一个活动输入源。</br></br>电脑服务向 SMC 通知当前输入源。 |  Source=&lt;#&gt; |
| Source? |  SMC 查询电脑服务以获取活动输入源。</br></br>电脑服务向 SMC 通知当前输入源。 | Source=&lt;#&gt; |

## 错误

按照此表中的格式返回错误。

| 错误 | 备注 |
| --- | --- |
| 错误：未知命令“&lt;input&gt;”。 |  该指令包含未知初始命令。 例如，&quot;VOL+&quot; 将无效并返回&quot;错误：未知命令‘VOL’&quot;。 |
| 错误：未知运算符“&lt;input&gt;”。 |  该指令包含未知运算符。 例如，&quot;Volume!&quot; 将无效并返回&quot;错误：未知运算符‘!’&quot;。 |
| 错误：未知参数“&lt;input&gt;”。 |  该指令包含未知参数。 例如，&quot;Volume=abc&quot; 将无效并返回&quot;错误：未知参数‘abc’&quot;。 |
| 错误：在处于关闭状态时命令不可用“&lt;input&gt;”。 |  当 Surface Hub 处于关闭状态时，电源以外的命令将返回此错误。 例如，&quot;Volume+&quot; 将无效并返回&quot;错误：在处于关闭状态时命令不可用‘Volume’&quot;。 |


 

##  <a name="related-topics"></a>相关主题


[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 管理员指南](surface-hub-administrators-guide.md)

 

 






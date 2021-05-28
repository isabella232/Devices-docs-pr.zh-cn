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
# <span data-ttu-id="cee14-104">使用房间控制系统 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="cee14-104">Using a room control system (Surface Hub)</span></span>


<span data-ttu-id="cee14-105">可以将房间控制系统与 Microsoft Surface Hub 结合使用。</span><span class="sxs-lookup"><span data-stu-id="cee14-105">Room control systems can be used with your Microsoft Surface Hub.</span></span>

<span data-ttu-id="cee14-106">将房间控制系统与 Surface Hub 结合使用包括通常通过 Surface Hub 底部的 RJ11 串行端口将房间控制硬件连接到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="cee14-106">Using a room control system with your Surface Hub involves connecting room control hardware to the Surface Hub, usually through the RJ11 serial port on the bottom of the Surface Hub.</span></span>

## <a name="terminal-settings"></a><span data-ttu-id="cee14-107">终端设置</span><span class="sxs-lookup"><span data-stu-id="cee14-107">Terminal settings</span></span>

<span data-ttu-id="cee14-108">若要连接到房间控制系统控制面板，无需在 Surface Hub 上配置任何终端设置。</span><span class="sxs-lookup"><span data-stu-id="cee14-108">To connect to a room control system control panel, you don't need to configure any terminal settings on the Surface Hub.</span></span> <span data-ttu-id="cee14-109">如果想要将电脑或笔记本电脑连接到 Surface Hub，然后从该 Surface Hub 发送一系列命令，可以使用终端仿真器程序（如 Tera Term 或 PuTTY）。</span><span class="sxs-lookup"><span data-stu-id="cee14-109">If you want to connect a PC or laptop to your Surface Hub and send serial commands from the Surface Hub, you can use a terminal emulator program like Tera Term or PuTTY.</span></span> 

| <span data-ttu-id="cee14-110">设置</span><span class="sxs-lookup"><span data-stu-id="cee14-110">Setting</span></span> | <span data-ttu-id="cee14-111">值</span><span class="sxs-lookup"><span data-stu-id="cee14-111">Value</span></span> |
| --- | --- |
| <span data-ttu-id="cee14-112">波特率</span><span class="sxs-lookup"><span data-stu-id="cee14-112">Baud rate</span></span> | <span data-ttu-id="cee14-113">115200</span><span class="sxs-lookup"><span data-stu-id="cee14-113">115200</span></span> |
| <span data-ttu-id="cee14-114">数据位</span><span class="sxs-lookup"><span data-stu-id="cee14-114">Data bits</span></span> | <span data-ttu-id="cee14-115">个</span><span class="sxs-lookup"><span data-stu-id="cee14-115">8</span></span> | 
| <span data-ttu-id="cee14-116">停止位</span><span class="sxs-lookup"><span data-stu-id="cee14-116">Stop bits</span></span> | <span data-ttu-id="cee14-117">raid-1</span><span class="sxs-lookup"><span data-stu-id="cee14-117">1</span></span> |
| <span data-ttu-id="cee14-118">奇偶校验</span><span class="sxs-lookup"><span data-stu-id="cee14-118">Parity</span></span> | <span data-ttu-id="cee14-119">无</span><span class="sxs-lookup"><span data-stu-id="cee14-119">none</span></span> |
| <span data-ttu-id="cee14-120">流控制</span><span class="sxs-lookup"><span data-stu-id="cee14-120">Flow control</span></span> | <span data-ttu-id="cee14-121">无</span><span class="sxs-lookup"><span data-stu-id="cee14-121">none</span></span> |
| <span data-ttu-id="cee14-122">换行</span><span class="sxs-lookup"><span data-stu-id="cee14-122">Line feed</span></span> | <span data-ttu-id="cee14-123">每个回车</span><span class="sxs-lookup"><span data-stu-id="cee14-123">every carriage return</span></span> |
 

## <a name="wiring-diagram"></a><span data-ttu-id="cee14-124">接线图</span><span class="sxs-lookup"><span data-stu-id="cee14-124">Wiring diagram</span></span>

<span data-ttu-id="cee14-125">可以使用标准的 RJ-11 (6P6C) 连接器将 Surface Hub 串行端口连接到房间控制系统。</span><span class="sxs-lookup"><span data-stu-id="cee14-125">You can use a standard RJ-11 (6P6C) connector to connect the Surface Hub serial port to a room control system.</span></span> <span data-ttu-id="cee14-126">这是推荐的方法。</span><span class="sxs-lookup"><span data-stu-id="cee14-126">This is the recommended method.</span></span> <span data-ttu-id="cee14-127">还可以使用 RJ-11 4 导线电缆，但我们不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="cee14-127">You can also use an RJ-11 4-conductor cable, but we do not recommend this method.</span></span>

<span data-ttu-id="cee14-128">此图显示用于 RJ-11 (6P6C) 到 DB9 电缆的正确引出线。</span><span class="sxs-lookup"><span data-stu-id="cee14-128">This diagram shows the correct pinout used for an RJ-11 (6P6C) to DB9 cable.</span></span>

![显示了接线图的图像。](images/room-control-wiring-diagram.png)

## <a name="command-sets"></a><span data-ttu-id="cee14-130">命令集</span><span class="sxs-lookup"><span data-stu-id="cee14-130">Command sets</span></span>

<span data-ttu-id="cee14-131">房间控制系统使用适用于命令的常见会议室方案。</span><span class="sxs-lookup"><span data-stu-id="cee14-131">Room control systems use common meeting-room scenarios for commands.</span></span> <span data-ttu-id="cee14-132">命令源自房间控制系统，通过串行连接与 Surface Hub 进行通信。</span><span class="sxs-lookup"><span data-stu-id="cee14-132">Commands originate from the room control system, and are communicated over a serial connection to a Surface Hub.</span></span> <span data-ttu-id="cee14-133">命令基于 ASCII，Surface Hub 将在状态发生更改时进行确认。</span><span class="sxs-lookup"><span data-stu-id="cee14-133">Commands are ASCII based, and the Surface Hub will acknowledge when state changes occur.</span></span>

<span data-ttu-id="cee14-134">以下命令修饰符可用。</span><span class="sxs-lookup"><span data-stu-id="cee14-134">The following command modifiers are available.</span></span> <span data-ttu-id="cee14-135">以换行符 (\n) 终止命令。</span><span class="sxs-lookup"><span data-stu-id="cee14-135">Commands terminate with a new line character (\n).</span></span> <span data-ttu-id="cee14-136">随时响应不是由管理端口命令直接触发的状态更改。</span><span class="sxs-lookup"><span data-stu-id="cee14-136">Responses can come at any time in response to state changes not triggered directly by a management port command.</span></span>

| <span data-ttu-id="cee14-137">修饰符</span><span class="sxs-lookup"><span data-stu-id="cee14-137">Modifier</span></span> | <span data-ttu-id="cee14-138">结果</span><span class="sxs-lookup"><span data-stu-id="cee14-138">Result</span></span> |
| --- | --- |
| + | <span data-ttu-id="cee14-139">增加值</span><span class="sxs-lookup"><span data-stu-id="cee14-139">Increment a value</span></span> |
| - | <span data-ttu-id="cee14-140">减少值</span><span class="sxs-lookup"><span data-stu-id="cee14-140">Decrease a value</span></span> |
| = | <span data-ttu-id="cee14-141">设置离散值</span><span class="sxs-lookup"><span data-stu-id="cee14-141">Set a discrete value</span></span> |
| <span data-ttu-id="cee14-142">?</span><span class="sxs-lookup"><span data-stu-id="cee14-142">?</span></span> | <span data-ttu-id="cee14-143">查询当前值</span><span class="sxs-lookup"><span data-stu-id="cee14-143">Queries for a current value</span></span> |
 

## <a name="power"></a><span data-ttu-id="cee14-144">电源</span><span class="sxs-lookup"><span data-stu-id="cee14-144">Power</span></span>

<span data-ttu-id="cee14-145">Surface Hub 可以处于以下一种电源状态。</span><span class="sxs-lookup"><span data-stu-id="cee14-145">Surface Hub can be in one of these power states.</span></span>

| <span data-ttu-id="cee14-146">状态</span><span class="sxs-lookup"><span data-stu-id="cee14-146">State</span></span> | <span data-ttu-id="cee14-147">能源星状态</span><span class="sxs-lookup"><span data-stu-id="cee14-147">Energy Star state</span></span>| <span data-ttu-id="cee14-148">描述</span><span class="sxs-lookup"><span data-stu-id="cee14-148">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cee14-149">0</span><span class="sxs-lookup"><span data-stu-id="cee14-149">0</span></span> | <span data-ttu-id="cee14-150">S5</span><span class="sxs-lookup"><span data-stu-id="cee14-150">S5</span></span> | <span data-ttu-id="cee14-151">关闭</span><span class="sxs-lookup"><span data-stu-id="cee14-151">Off</span></span> |
| <span data-ttu-id="cee14-152">raid-1</span><span class="sxs-lookup"><span data-stu-id="cee14-152">1</span></span> | - | <span data-ttu-id="cee14-153">通电（不确定）</span><span class="sxs-lookup"><span data-stu-id="cee14-153">Power up (indeterminate)</span></span> |
| <span data-ttu-id="cee14-154">ppls-2</span><span class="sxs-lookup"><span data-stu-id="cee14-154">2</span></span> | <span data-ttu-id="cee14-155">S3</span><span class="sxs-lookup"><span data-stu-id="cee14-155">S3</span></span> | <span data-ttu-id="cee14-156">睡眠</span><span class="sxs-lookup"><span data-stu-id="cee14-156">Sleep</span></span> |
| <span data-ttu-id="cee14-157">级</span><span class="sxs-lookup"><span data-stu-id="cee14-157">5</span></span> | <span data-ttu-id="cee14-158">S0</span><span class="sxs-lookup"><span data-stu-id="cee14-158">S0</span></span> | <span data-ttu-id="cee14-159">就绪</span><span class="sxs-lookup"><span data-stu-id="cee14-159">Ready</span></span> |


<span data-ttu-id="cee14-160">在“替换电脑”模式中，电源状态仅为“就绪”和“关闭”，并且仅更改屏幕。</span><span class="sxs-lookup"><span data-stu-id="cee14-160">In Replacement PC mode, the power states are only Ready and Off and only change the display.</span></span> <span data-ttu-id="cee14-161">管理端口无法用于接通替换电脑电源。</span><span class="sxs-lookup"><span data-stu-id="cee14-161">The management port can't be used to power on the replacement PC.</span></span> 

| <span data-ttu-id="cee14-162">状态</span><span class="sxs-lookup"><span data-stu-id="cee14-162">State</span></span> | <span data-ttu-id="cee14-163">能源星状态</span><span class="sxs-lookup"><span data-stu-id="cee14-163">Energy Star state</span></span>| <span data-ttu-id="cee14-164">描述</span><span class="sxs-lookup"><span data-stu-id="cee14-164">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cee14-165">0</span><span class="sxs-lookup"><span data-stu-id="cee14-165">0</span></span> | <span data-ttu-id="cee14-166">S5</span><span class="sxs-lookup"><span data-stu-id="cee14-166">S5</span></span> | <span data-ttu-id="cee14-167">关闭</span><span class="sxs-lookup"><span data-stu-id="cee14-167">Off</span></span> |
| <span data-ttu-id="cee14-168">级</span><span class="sxs-lookup"><span data-stu-id="cee14-168">5</span></span> | <span data-ttu-id="cee14-169">S0</span><span class="sxs-lookup"><span data-stu-id="cee14-169">S0</span></span> | <span data-ttu-id="cee14-170">就绪</span><span class="sxs-lookup"><span data-stu-id="cee14-170">Ready</span></span> |

<span data-ttu-id="cee14-171">对于控制设备，5/就绪以外的任何其他状态均视为关闭。</span><span class="sxs-lookup"><span data-stu-id="cee14-171">For a control device, anything other than 5 / Ready should be considered off.</span></span> <span data-ttu-id="cee14-172">每个 PowerOn 命令都会产生两种状态更改和响应。</span><span class="sxs-lookup"><span data-stu-id="cee14-172">Each PowerOn command results in two state changes and responses.</span></span> 

| <span data-ttu-id="cee14-173">命令</span><span class="sxs-lookup"><span data-stu-id="cee14-173">Command</span></span> | <span data-ttu-id="cee14-174">状态更改</span><span class="sxs-lookup"><span data-stu-id="cee14-174">State change</span></span>| <span data-ttu-id="cee14-175">响应</span><span class="sxs-lookup"><span data-stu-id="cee14-175">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cee14-176">PowerOn</span><span class="sxs-lookup"><span data-stu-id="cee14-176">PowerOn</span></span> | <span data-ttu-id="cee14-177">设备打开（屏幕 + 电脑）。</span><span class="sxs-lookup"><span data-stu-id="cee14-177">Device turns on (display + PC).</span></span></br></br><span data-ttu-id="cee14-178">电脑服务通知 SMC 电脑已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="cee14-178">PC service notifies SMC that the PC is ready.</span></span> |  <span data-ttu-id="cee14-179">Power=0</span><span class="sxs-lookup"><span data-stu-id="cee14-179">Power=0</span></span></br></br><span data-ttu-id="cee14-180">Power=5</span><span class="sxs-lookup"><span data-stu-id="cee14-180">Power=5</span></span> |
| <span data-ttu-id="cee14-181">PowerOff</span><span class="sxs-lookup"><span data-stu-id="cee14-181">PowerOff</span></span> | <span data-ttu-id="cee14-182">设备转换到环境状态（电脑打开，屏幕变暗）。</span><span class="sxs-lookup"><span data-stu-id="cee14-182">Device transitions to ambient state (PC on, display dim).</span></span> |  <span data-ttu-id="cee14-183">Power=0</span><span class="sxs-lookup"><span data-stu-id="cee14-183">Power=0</span></span> |
| <span data-ttu-id="cee14-184">Power?</span><span class="sxs-lookup"><span data-stu-id="cee14-184">Power?</span></span> |  <span data-ttu-id="cee14-185">SMC 报告上次已知电源状态。</span><span class="sxs-lookup"><span data-stu-id="cee14-185">SMC reports the last-known power state.</span></span> |  <span data-ttu-id="cee14-186">Power=<#></span><span class="sxs-lookup"><span data-stu-id="cee14-186">Power=<#></span></span> |



## <a name="brightness"></a><span data-ttu-id="cee14-187">亮度</span><span class="sxs-lookup"><span data-stu-id="cee14-187">Brightness</span></span>

<span data-ttu-id="cee14-188">当前亮度级别范围从 0 到 100。</span><span class="sxs-lookup"><span data-stu-id="cee14-188">The current brightness level is a range from 0 to 100.</span></span>

<span data-ttu-id="cee14-189">可以通过房间控制系统或其他系统发送对亮度级别的更改。</span><span class="sxs-lookup"><span data-stu-id="cee14-189">Changes to brightness levels can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="cee14-190">命令</span><span class="sxs-lookup"><span data-stu-id="cee14-190">Command</span></span> | <span data-ttu-id="cee14-191">状态更改</span><span class="sxs-lookup"><span data-stu-id="cee14-191">State change</span></span> |<span data-ttu-id="cee14-192">响应</span><span class="sxs-lookup"><span data-stu-id="cee14-192">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cee14-193">Brightness+</span><span class="sxs-lookup"><span data-stu-id="cee14-193">Brightness+</span></span> | <span data-ttu-id="cee14-194">系统管理控制器 (SMC) 发送亮度增加命令。</span><span class="sxs-lookup"><span data-stu-id="cee14-194">System management controller (SMC) sends the brightness up command.</span></span></br></br><span data-ttu-id="cee14-195">房间控制系统上的电脑服务向 SMC 通知新的亮度级别。</span><span class="sxs-lookup"><span data-stu-id="cee14-195">PC service on the room control system notifies SMC of new brightness level.</span></span> |  <span data-ttu-id="cee14-196">Brightness = 51</span><span class="sxs-lookup"><span data-stu-id="cee14-196">Brightness = 51</span></span> |
| <span data-ttu-id="cee14-197">Brightness-</span><span class="sxs-lookup"><span data-stu-id="cee14-197">Brightness-</span></span> |  <span data-ttu-id="cee14-198">SMC 发送亮度减弱命令。</span><span class="sxs-lookup"><span data-stu-id="cee14-198">SMC sends the brightness down command.</span></span></br></br><span data-ttu-id="cee14-199">电脑服务向 SMC 通知新的亮度级别。</span><span class="sxs-lookup"><span data-stu-id="cee14-199">PC service notifies SMC of new brightness level.</span></span> | <span data-ttu-id="cee14-200">Brightness = 50</span><span class="sxs-lookup"><span data-stu-id="cee14-200">Brightness = 50</span></span> |

## <a name="volume"></a><span data-ttu-id="cee14-201">音量</span><span class="sxs-lookup"><span data-stu-id="cee14-201">Volume</span></span>

<span data-ttu-id="cee14-202">当前音量级别范围从 0 到 100。</span><span class="sxs-lookup"><span data-stu-id="cee14-202">The current volume level is a range from 0 to 100.</span></span>

<span data-ttu-id="cee14-203">可以通过房间控制系统或其他系统发送对音量级别的更改。</span><span class="sxs-lookup"><span data-stu-id="cee14-203">Changes to volume levels can be sent by a room control system, or other system.</span></span>

>[!NOTE]
><span data-ttu-id="cee14-204">音量命令将仅控制嵌入或替换电脑模式的音量，而不控制来自[来宾源](connect-and-display-with-surface-hub.md)的音量。</span><span class="sxs-lookup"><span data-stu-id="cee14-204">The Volume command will only control the volume for embedded or Replacement PC mode, not from [Guest sources](connect-and-display-with-surface-hub.md).</span></span>

| <span data-ttu-id="cee14-205">命令</span><span class="sxs-lookup"><span data-stu-id="cee14-205">Command</span></span> | <span data-ttu-id="cee14-206">状态更改</span><span class="sxs-lookup"><span data-stu-id="cee14-206">State change</span></span> | <span data-ttu-id="cee14-207">响应</span><span class="sxs-lookup"><span data-stu-id="cee14-207">Response</span></span></br><span data-ttu-id="cee14-208">（处于[替换电脑模式](connect-and-display-with-surface-hub.md#replacement-pc-mode)）</span><span class="sxs-lookup"><span data-stu-id="cee14-208">(On in [Replacement PC mode](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cee14-209">Volume+</span><span class="sxs-lookup"><span data-stu-id="cee14-209">Volume+</span></span> |  <span data-ttu-id="cee14-210">SMC 发送音量提高命令。</span><span class="sxs-lookup"><span data-stu-id="cee14-210">SMC sends the volume up command.</span></span></br></br><span data-ttu-id="cee14-211">电脑服务向 SMC 通知新的音量级别。</span><span class="sxs-lookup"><span data-stu-id="cee14-211">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="cee14-212">Volume = 51</span><span class="sxs-lookup"><span data-stu-id="cee14-212">Volume = 51</span></span> |
| <span data-ttu-id="cee14-213">Volume-</span><span class="sxs-lookup"><span data-stu-id="cee14-213">Volume-</span></span> |  <span data-ttu-id="cee14-214">SMC 发送音量降低命令。</span><span class="sxs-lookup"><span data-stu-id="cee14-214">SMC sends the volume down command.</span></span></br></br><span data-ttu-id="cee14-215">电脑服务向 SMC 通知新的音量级别。</span><span class="sxs-lookup"><span data-stu-id="cee14-215">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="cee14-216">Volume = 50</span><span class="sxs-lookup"><span data-stu-id="cee14-216">Volume = 50</span></span> |


 

## <a name="mute-for-audio"></a><span data-ttu-id="cee14-217">音频静音</span><span class="sxs-lookup"><span data-stu-id="cee14-217">Mute for audio</span></span>

<span data-ttu-id="cee14-218">可将音频设为静音。</span><span class="sxs-lookup"><span data-stu-id="cee14-218">Audio can be muted.</span></span>

| <span data-ttu-id="cee14-219">命令</span><span class="sxs-lookup"><span data-stu-id="cee14-219">Command</span></span> | <span data-ttu-id="cee14-220">状态更改</span><span class="sxs-lookup"><span data-stu-id="cee14-220">State change</span></span> | <span data-ttu-id="cee14-221">响应</span><span class="sxs-lookup"><span data-stu-id="cee14-221">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cee14-222">AudioMute+</span><span class="sxs-lookup"><span data-stu-id="cee14-222">AudioMute+</span></span> |  <span data-ttu-id="cee14-223">SMC 发送音频静音命令。</span><span class="sxs-lookup"><span data-stu-id="cee14-223">SMC sends the audio mute command.</span></span></br></br><span data-ttu-id="cee14-224">电脑服务通知 SMC 已将音频设置为静音。</span><span class="sxs-lookup"><span data-stu-id="cee14-224">PC service notifies SMC that audio is muted.</span></span> |  <span data-ttu-id="cee14-225">无</span><span class="sxs-lookup"><span data-stu-id="cee14-225">none</span></span> |


 

## <a name="video-source"></a><span data-ttu-id="cee14-226">视频源</span><span class="sxs-lookup"><span data-stu-id="cee14-226">Video source</span></span>

<span data-ttu-id="cee14-227">可以使用多个显示源。</span><span class="sxs-lookup"><span data-stu-id="cee14-227">Several display sources can be used.</span></span>

| <span data-ttu-id="cee14-228">状态</span><span class="sxs-lookup"><span data-stu-id="cee14-228">State</span></span> | <span data-ttu-id="cee14-229">描述</span><span class="sxs-lookup"><span data-stu-id="cee14-229">Description</span></span> | 
| --- | --- |
| <span data-ttu-id="cee14-230">0</span><span class="sxs-lookup"><span data-stu-id="cee14-230">0</span></span> |  <span data-ttu-id="cee14-231">板载电脑</span><span class="sxs-lookup"><span data-stu-id="cee14-231">Onboard PC</span></span> |
| <span data-ttu-id="cee14-232">raid-1</span><span class="sxs-lookup"><span data-stu-id="cee14-232">1</span></span> |  <span data-ttu-id="cee14-233">DisplayPort</span><span class="sxs-lookup"><span data-stu-id="cee14-233">DisplayPort</span></span> |
| <span data-ttu-id="cee14-234">ppls-2</span><span class="sxs-lookup"><span data-stu-id="cee14-234">2</span></span> |  <span data-ttu-id="cee14-235">HDMI</span><span class="sxs-lookup"><span data-stu-id="cee14-235">HDMI</span></span> |
| <span data-ttu-id="cee14-236">三维空间</span><span class="sxs-lookup"><span data-stu-id="cee14-236">3</span></span> |  <span data-ttu-id="cee14-237">VGA</span><span class="sxs-lookup"><span data-stu-id="cee14-237">VGA</span></span> |


 

<span data-ttu-id="cee14-238">可以通过房间控制系统或其他系统发送对显示源的更改。</span><span class="sxs-lookup"><span data-stu-id="cee14-238">Changes to display source can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="cee14-239">命令</span><span class="sxs-lookup"><span data-stu-id="cee14-239">Command</span></span> | <span data-ttu-id="cee14-240">状态更改</span><span class="sxs-lookup"><span data-stu-id="cee14-240">State change</span></span> | <span data-ttu-id="cee14-241">响应</span><span class="sxs-lookup"><span data-stu-id="cee14-241">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cee14-242">Source=#</span><span class="sxs-lookup"><span data-stu-id="cee14-242">Source=#</span></span> |  <span data-ttu-id="cee14-243">SMC 将更改为所需源。</span><span class="sxs-lookup"><span data-stu-id="cee14-243">SMC changes to the desired source.</span></span></br></br><span data-ttu-id="cee14-244">电脑服务通知 SMC 已切换显示源。</span><span class="sxs-lookup"><span data-stu-id="cee14-244">PC service notifies SMC that the display source has switched.</span></span> |  <span data-ttu-id="cee14-245">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="cee14-245">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="cee14-246">Source+</span><span class="sxs-lookup"><span data-stu-id="cee14-246">Source+</span></span> |  <span data-ttu-id="cee14-247">SMC 将循环到下一个活动输入源。</span><span class="sxs-lookup"><span data-stu-id="cee14-247">SMC cycles to the next active input source.</span></span></br></br><span data-ttu-id="cee14-248">电脑服务向 SMC 通知当前输入源。</span><span class="sxs-lookup"><span data-stu-id="cee14-248">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="cee14-249">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="cee14-249">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="cee14-250">Source-</span><span class="sxs-lookup"><span data-stu-id="cee14-250">Source-</span></span> | <span data-ttu-id="cee14-251">SMC 将循环到上一个活动输入源。</span><span class="sxs-lookup"><span data-stu-id="cee14-251">SMC cycles to the previous active input source.</span></span></br></br><span data-ttu-id="cee14-252">电脑服务向 SMC 通知当前输入源。</span><span class="sxs-lookup"><span data-stu-id="cee14-252">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="cee14-253">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="cee14-253">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="cee14-254">Source?</span><span class="sxs-lookup"><span data-stu-id="cee14-254">Source?</span></span> |  <span data-ttu-id="cee14-255">SMC 查询电脑服务以获取活动输入源。</span><span class="sxs-lookup"><span data-stu-id="cee14-255">SMC queries PC service for the active input source.</span></span></br></br><span data-ttu-id="cee14-256">电脑服务向 SMC 通知当前输入源。</span><span class="sxs-lookup"><span data-stu-id="cee14-256">PC service notifies SMC of the current in;put source.</span></span> | <span data-ttu-id="cee14-257">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="cee14-257">Source=&lt;#&gt;</span></span> |

## <a name="errors"></a><span data-ttu-id="cee14-258">错误</span><span class="sxs-lookup"><span data-stu-id="cee14-258">Errors</span></span>

<span data-ttu-id="cee14-259">按照此表中的格式返回错误。</span><span class="sxs-lookup"><span data-stu-id="cee14-259">Errors are returned following the format in this table.</span></span>

| <span data-ttu-id="cee14-260">错误</span><span class="sxs-lookup"><span data-stu-id="cee14-260">Error</span></span> | <span data-ttu-id="cee14-261">备注</span><span class="sxs-lookup"><span data-stu-id="cee14-261">Notes</span></span> |
| --- | --- |
| <span data-ttu-id="cee14-262">错误：未知命令“&lt;input&gt;”。</span><span class="sxs-lookup"><span data-stu-id="cee14-262">Error: Unknown command '&lt;input&gt;'.</span></span> |  <span data-ttu-id="cee14-263">该指令包含未知初始命令。</span><span class="sxs-lookup"><span data-stu-id="cee14-263">The instruction contains an unknown initial command.</span></span> <span data-ttu-id="cee14-264">例如，&quot;VOL+&quot; 将无效并返回&quot;错误：未知命令‘VOL’&quot;。</span><span class="sxs-lookup"><span data-stu-id="cee14-264">For example, &quot;VOL+&quot; would be invalid and return &quot; Error: Unknown command 'VOL'&quot;.</span></span> |
| <span data-ttu-id="cee14-265">错误：未知运算符“&lt;input&gt;”。</span><span class="sxs-lookup"><span data-stu-id="cee14-265">Error: Unknown operator '&lt;input&gt;'.</span></span> |  <span data-ttu-id="cee14-266">该指令包含未知运算符。</span><span class="sxs-lookup"><span data-stu-id="cee14-266">The instruction contains an unknown operator.</span></span> <span data-ttu-id="cee14-267">例如，&quot;Volume!&quot; 将无效并返回&quot;错误：未知运算符‘!’&quot;。</span><span class="sxs-lookup"><span data-stu-id="cee14-267">For example, &quot;Volume!&quot; would be invalid and return &quot; Error: Unknown operator '!'&quot;.</span></span> |
| <span data-ttu-id="cee14-268">错误：未知参数“&lt;input&gt;”。</span><span class="sxs-lookup"><span data-stu-id="cee14-268">Error: Unknown parameter '&lt;input&gt;'.</span></span> |  <span data-ttu-id="cee14-269">该指令包含未知参数。</span><span class="sxs-lookup"><span data-stu-id="cee14-269">The instruction contains an unknown parameter.</span></span> <span data-ttu-id="cee14-270">例如，&quot;Volume=abc&quot; 将无效并返回&quot;错误：未知参数‘abc’&quot;。</span><span class="sxs-lookup"><span data-stu-id="cee14-270">For example, &quot;Volume=abc&quot; would be invalid and return &quot; Error: Unknown parameter 'abc'&quot;.</span></span> |
| <span data-ttu-id="cee14-271">错误：在处于关闭状态时命令不可用“&lt;input&gt;”。</span><span class="sxs-lookup"><span data-stu-id="cee14-271">Error: Command not available when off '&lt;input&gt;'.</span></span> |  <span data-ttu-id="cee14-272">当 Surface Hub 处于关闭状态时，电源以外的命令将返回此错误。</span><span class="sxs-lookup"><span data-stu-id="cee14-272">When the Surface Hub is off, commands other than Power return this error.</span></span> <span data-ttu-id="cee14-273">例如，&quot;Volume+&quot; 将无效并返回&quot;错误：在处于关闭状态时命令不可用‘Volume’&quot;。</span><span class="sxs-lookup"><span data-stu-id="cee14-273">For example, &quot;Volume+&quot; would be invalid and return &quot; Error: Command not available when off 'Volume'&quot;.</span></span> |


 

## <a name="related-topics"></a><span data-ttu-id="cee14-274">相关主题</span><span class="sxs-lookup"><span data-stu-id="cee14-274">Related topics</span></span>


[<span data-ttu-id="cee14-275">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="cee14-275">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="cee14-276">Microsoft Surface Hub 管理员指南</span><span class="sxs-lookup"><span data-stu-id="cee14-276">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 






---
title: 在桌面模式下使用适用于企业的 Surface 诊断工具包
description: 如何使用 SDT 来帮助贵组织的用户运行该工具，以识别和诊断 Surface 设备的问题，以及直接从该工具提交支持请求。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 7/31/2020
ms.openlocfilehash: 7d09bc70a2e0c882bde9106ee2c241568c1fc991
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154127"
---
# <a name="use-surface-diagnostic-toolkit-for-business-in-desktop-mode"></a>在桌面模式下使用适用于企业的 Surface 诊断工具包

本主题介绍如何使用 Surface Diagnostic Toolkit (SDT) 来帮助贵组织的用户运行该工具，以识别和诊断其 Surface 设备的问题，以及直接从该工具提交支持请求。 

成功运行 SDT 可以快速确定报告的问题是由硬件故障还是用户错误导致的。 有关 SDT 中受支持的 Surface 设备的列表，请参阅[D部署适用于Toolkit Surface 诊断。](surface-diagnostic-toolkit-business.md)


1. 指示用户从软件分发点或网络) 安装 [SDT](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution) 程序包。 安装后，即可指导用户完成一系列测试。 

2. 从允许用户输入问题说明的主页开始，然后单击"继续"，如图 1**** 所示。

    ![在桌面模式下启动 SDT。](images/sdt-desk-1.png)<br/>
    *图 1. 桌面模式下的 SDT*

3. 当 SDT 指示设备具有最新更新时，单击****"继续"以前进到可用测试的目录，如图 2 所示。

    ![从 SDT 选项中进行选择。](images/sdt1.png)<br/>
    *图 2. 从 SDT 选项中进行选择*

4. 你可以选择运行所有诊断测试。 或者，如果您已经怀疑存在特定问题，例如显示错误或电源问题，请单击"选择"以从**** 可用测试中选择，然后单击"运行**已**选"，如图 3 所示。 有关每个测试的详细信息，请参阅下表。 

    ![选择硬件测试。](images/sdt2.png)<br/>
    *图 3. 选择硬件测试*

    硬件测试 | 描述
    --- | ---
    电源和电池 |  检查电源运行最佳
    显示和声音   | 检查亮度、卡住或死像素、扬声器和麦克风是否正常工作
    端口和附件   | 检查附件、屏幕连接和 USB 功能
    连接性 |  检查蓝牙、无线和 LTE 连接
    安全    | 检查与安全相关的问题
    触控   | 检查触摸相关问题
    键盘和触摸 |    检查集成的键盘连接和类型覆盖
    传感器 | 检查设备中不同传感器的运行情况
    硬件 |  检查不同硬件组件（如显卡和相机）的问题

5. 完成所有测试后，该工具会要求您确认问题是否得到解决。 

    ![你的问题是否得到解决？](images/sdt3.png)<br/>
    *图 3a. 你的问题是否得到解决？*

6. 如果问题未解决或你不知道，可以通过选择"联系我们"立即获取帮助来提交**支持票证。** ****
 
    ![提交支持票证。](images/sdt4.png)<br/>
    *图 3b. 提交支持票证*

<span id="multiple" />

## <a name="running-multiple-hardware-tests-to-troubleshoot-issues"></a>运行多个硬件测试以解决问题

SDT 设计为可运行一系列测试的交互式工具。 对于每个测试，SDT 都提供了概述测试的性质以及用户期望或查找哪些内容以便测试成功的说明。 例如，为了诊断显示亮度是否正常工作，SDT 从零开始，将亮度增加至 100%，并要求用户通过回答"是"或"否****"来**** 确认亮度是否按预期工作，如图 4 所示。 

对于每个测试，如果功能未按预期工作，并且用户单击"否"，则 SDT 将生成一个报告，说明可能的原因和疑难解答方法。 **** 

![运行硬件诊断。 ](images/sdt-desk-4.png)
*图 4.运行硬件诊断*

1. 如果亮度按预期从 0- 100% 成功调整，请引导用户单击****"是"，然后单击"继续 **"。** 
2. 如果亮度无法按预期从 0- 100% 调整，请引导用户单击****"否"，然后单击"继续 **"。** 
3. 根据情况指导用户完成剩余的测试。 完成后，SDT 将自动提供报告高级摘要，包括任何硬件问题的可能原因以及解决指南。


### <a name="repairing-applications"></a>修复应用程序

SDT 使您能够诊断和修复可能导致问题的应用程序，如图 5 所示。

![运行修复。 ](images/sdt-desk-5.png)
*图 5.运行修复*
<span id="logs" />

### <a name="generating-logs-for-analyzing-issues"></a>生成用于分析问题的日志 

SDT 跨应用程序、驱动程序、硬件和操作系统问题提供广泛的启用日志的诊断支持，如图 6 所示。

![生成日志。 ](images/sdt-desk-6.png)
*图 6.生成日志*

<span id="detailed-report" />

### <a name="generating-detailed-report-comparing-device-vs-optimal-configuration"></a>生成比较设备和最佳配置的详细报告

SDT 基于日志生成基于软件和固件的问题报告，您可以将这些问题保存到首选位置。

## <a name="related-topics"></a>相关主题

- [使用适用于 Business 的 Surface Diagnostic Toolkit运行命令行应用控制台](surface-diagnostic-toolkit-command-line.md)

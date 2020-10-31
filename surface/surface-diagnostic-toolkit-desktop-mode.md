---
title: 在桌面模式下使用适用于企业的 Surface 诊断工具包
description: 如何使用 SDT 帮助你的组织中的用户运行该工具来识别和诊断 Surface 设备的问题，并直接从工具提交支持请求。
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
ms.openlocfilehash: 8b113d16f2053fe0904518b2643f1bafeaebdf64
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145937"
---
# 在桌面模式下使用适用于企业的 Surface 诊断工具包

本主题介绍了如何使用 (SDT) 的 Surface 诊断工具包，帮助你组织中的用户运行该工具来识别和诊断其 Surface 设备的问题，并直接从工具提交支持请求。 

成功运行 SDT 可以快速确定报告的问题是否由硬件故障或用户错误引起。 有关 SDT 中受支持的 Surface 设备的列表，请参阅 [部署适用于企业的 Surface 诊断工具包](surface-diagnostic-toolkit-business.md)。


1. 指导用户从软件分发点或网络共享安装 [SDT 程序包](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution)) 。 安装完成后，你可以通过一系列测试来指导用户。 

2. 从主页开始，该页面允许用户输入问题的描述，然后单击 " **继续**"，如图1所示。

    ![在桌面模式下启动 SDT ](images/sdt-desk-1.png)
 *图1。桌面模式中的 SDT*

3. 当 SDT 指示设备具有最新的更新时，请单击 " **继续** " 以转到可用测试的目录，如图2所示。

    ![从 SDT 选项中选择 ](images/sdt1.png)
 *图2。从 SDT 选项中选择*

4. 你可以选择运行所有诊断测试。 或者，如果你怀疑某个特定问题（如显示错误或电源问题），请单击 " **选择** " 以从可用测试中进行选择，然后单击 " **运行所选**"，如图3所示。 有关每个测试的详细信息，请参阅下表。 

    ![选择硬件测试 ](images/sdt2.png)
 *图3。选择硬件测试*

    硬件测试 | 描述
    --- | ---
    电源设备和电池 |  检查电源的运行速度最佳
    显示和声音   | 检查亮度、粘滞或死像素、扬声器和麦克风功能
    端口和附件   | 检查附件、屏幕连接和 USB 运行状况
    连接性 |  检查蓝牙、无线和 LTE 连接
    安全性    | 检查与安全性相关的问题
    触控   | 检查触摸相关问题
    键盘和触控 |    检查集成键盘连接和输入封面
    传感器 | 检查设备中不同传感器的运行情况
    硬件 |  检查不同硬件组件（如图形卡和照相机）的问题

5. 当所有测试完成后，该工具会要求您确认问题是否已修复。 

 ![您的问题是否已得到解决？ ](images/sdt3.png)
*图3a。您的问题是否已得到解决？*

6. 如果问题未得到解决，或者您不知道，您可以通过选择 " **与我们联系** " 来提交支持票证， **立即获取帮助。**
 
 ![提交支持票证 ](images/sdt4.png)
 *图3B。提交支持票证*

<span id="multiple" />

## 运行多个硬件测试以解决问题

SDT 设计为可运行一系列测试的交互式工具。 对于每个测试，SDT 都提供有关测试性质的说明以及用户应期望或查找的内容，以便测试成功。 例如，若要诊断显示亮度是否正常工作，SDT 将从零开始，并将亮度增加到100%，要求用户通过回答 **"是"** 或 " **否** " 来进行确认--该亮度按预期方式工作，如图4所示。 

对于每个测试，如果功能不按预期工作，并且用户单击 " **否**"，则 SDT 将生成可能的原因和解决问题的方法的报告。 

![运行硬件诊断 ](images/sdt-desk-4.png)
 *图4。运行硬件诊断*

1. 如果亮度已按预期成功地调整了0-100%，请直接在用户单击 **"是"** ，然后单击 " **继续**"。 
2. 如果亮度无法按预期调整0-100%，请指示用户单击 " **否** "，然后单击 " **继续**"。 
3. 根据需要指导用户完成剩余的测试。 完成后，SDT 将自动提供报表的高级别摘要，包括任何硬件问题的可能原因以及解决方案的指南。


### 修复应用程序

SDT 使你能够诊断和修复可能导致问题的应用程序，如图5所示。

![正在运行修复 ](images/sdt-desk-5.png)
 *图5。正在运行修复*
<span id="logs" />

### 生成用于分析问题的日志 

SDT 在应用程序、驱动程序、硬件和操作系统问题上提供丰富的支持日志的诊断支持，如图6所示。

![生成日志 ](images/sdt-desk-6.png)
 *图6。生成日志*

<span id="detailed-report" />

### 生成比较设备和最佳配置的详细报告

根据日志，SDT 将为基于软件和固件的问题生成报表，你可以将这些问题保存到首选位置。

## 相关主题

- [使用命令运行适用于企业的 Surface 诊断工具包](surface-diagnostic-toolkit-command-line.md)


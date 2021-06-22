---
title: Surface 自助服务担保和服务
description: Microsoft 365商业客户可能有资格使用 Microsoft 管理中心中的 beta Surface Self Serve 担保和服务节点来创建和管理服务订单。
ms.prod: w10
ms.mktglfcycl: support
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/07/2021
ms.reviewer: louannh
manager: laurawi
audience: itpro
ms.openlocfilehash: a6021a58c85ac6ee4c039959dcde9bab632ea1bb
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614047"
---
# <a name="surface-self-serve-warranty-and-service"></a>Surface 自助服务担保和服务

Microsoft 365商业客户可能有资格使用 Microsoft 365 管理 中心中的 Surface 自助服务担保和服务节点来创建和提供服务订单。 此新功能作为 beta 计划提供，允许全局管理员将权限指定给其公司内负责支持担保和服务声明的个人，其中包括：

- Upload需要服务的设备的序列号。
- 添加多个送货地址。
- 为一个或多个设备和类型覆盖创建单个服务订单。
- 请参阅实时服务订单状态。
- 如果设备由延长Exchange或高级产品包含在设备购买中，则到货Exchange批量接收预付产品。

## <a name="join-beta-program"></a>加入 beta 计划

请联系你的 Microsoft 客户成功客户经理或客户成功经理，了解有关体验以及如何参与 beta 计划的详细信息。

## <a name="role-based-permissions"></a>基于角色的权限

Surface Self-Serve担保和服务允许Microsoft 365全局管理员通过向用户分配角色来授予创建和管理服务订单的不同权限。

当Microsoft 365租户添加到 beta 计划时，会向以下管理员角色授予其他权限：

| 角色                  | 权限                                                                                                                         |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| 全局管理员          | 查看修复请求<br>创建/管理修复请求<br>Add/Edit/Delete Ship to Address (es) <br>创建/管理用户及其角色 |
| 服务支持管理员 | 查看修复请求<br>创建/管理修复请求                                                                               |
| 帐单管理员         | 查看修复请求<br>创建/管理修复请求<br>添加/编辑/删除发货地址 (地址)                                         |

有关用户和权限详细信息，请参阅 Microsoft [管理中心概述](/microsoft-365/admin/admin-overview/about-the-admin-center)。

## <a name="create-and-manage-a-service-order"></a>创建和管理服务订单

1. 转到 "Microsoft 365 管理 中心 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) "，然后使用相应的管理员权限登录。 若要了解更多信息，[请参阅Who我的企业中具有管理员权限？](/microsoft-365/business-video/admin-center-overview#who-has-admin-permissions-in-my-business)
2. 转到支持****  >  **Surface 设备修复，** 然后选择**创建修复请求**。  (如果未看到此修复选项，则没有访问此页面的权限。) 

    > [!div class="mx-imgBorder"]
    > ![启动自助修复请求](images/self-serve-fig1.png)

3. 你可以为一个或多个设备创建修复请求。 选择"**一次提交 1**台设备****"或"提交多个设备"以使用.csv文件上传多个序列号，然后选择"下一**步"。**

    > [!NOTE]
    > **对于多台设备：**
    >
    > - 从管理中心页面，下载示例 CSV 模板，添加所需信息并将其保存到本地驱动器。
    > - Select **Upload CSV file for bulk entries，** select the .csv file you saved to your local drive and select **Open.**
    > - 你的设备序列号将上载。 选择 **"下** 一步"继续创建修复。

4. 在 **"将替换项寄送到**"下，选择送货地址。 或选择 **"添加新地址"。**

    > [!NOTE]
    >
    > - 权限允许某些管理员将新的发货地址添加到地址。 如果您具有权限，>可以添加新地址。 输入所需信息，然后选择"保存 **"。**
    > - 该窗体将自动验证地址信息，如果本地邮政系统无法识别该地址，则可能会更正您所做的更改。 电子邮件地址用于发送修复请求的通知和通信。

    > [!div class="mx-imgBorder"]
    > ![添加新地址](images/self-serve-fig2a.png)

5. 在文本块中输入设备序列号来添加设备。 若要了解更多信息，请参阅 [设备序列号](https://support.microsoft.com/help/4036293/surface-find-the-serial-number-on-surface)。 如果序列号有效，将显示一个图像和产品信息，其中包括担保日期和型号。 如果 **信息正确** ，请选择"添加设备"。

    > [!div class="mx-imgBorder"]
    > ![“添加设备”](images/self-serve-fig2.png)

6. 重复步骤 1-2 以向 (添加最多 20) 的设备。
7. 从下拉菜单中，选择最能描述该问题的问题类型，然后选择"下一步 **"。**

    > [!div class="mx-imgBorder"]
    > ![选择问题类别](images/self-serve-fig3.png)

8. 查看订单。 如果任何信息不正确，请选择" **返回** "以更正错误。
9. 接受条件条款。
10. 如果请求摘要正确，请选择"**提交请求"。**

    > [!div class="mx-imgBorder"]
    > ![提交自助修复请求](images/self-serve-fig4.png)

当主页显示时，您可以查看摘要列表中的服务请求并接收确认电子邮件。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="why-am-i-getting-error-code-400-generic-client-service-error-401-unauthorized-service-error-or-error-403-forbidden-service-error"></a>为什么我收到错误代码 400"通用客户端服务错误"、401"未经授权服务错误"或错误 403"禁止的服务错误"？

帐户可能Microsoft 365，或者用户无权访问内容。 联系你的全局Microsoft 365寻求帮助。

### <a name="when-i-enter-my-shipping-address-and-i-get-an-error-message-that-no-shipping-offers-are-available"></a>当我输入送货地址时收到一条错误消息，指出没有可用的送货产品/服务？

Surface Self-Serve Service Beta 目前的可用性有限。 只有当地址位于以下国家/地区之一时，产品/服务才可用：

奥地利、巴林、比利时、保加利亚、克罗地亚、塞浦路斯、捷克共和国、丹麦、爱沙尼亚、芬兰、法国、德国、希腊、匈牙利、爱尔兰、意大利、科威特、拉脱维亚、立陶宛、卢森堡、马耳他、荷兰、阿曼、波兰、葡萄牙、罗马尼亚、斯洛伐克、斯洛文尼亚、南非、西班牙、瑞典和英国 (，爱尔兰) 除外。

### <a name="where-can-i-see-orders-that-i-have-placed-through-the-microsoft-365-portal"></a>在哪里可以看到我通过客户门户Microsoft 365订单？

转到[Microsoft 365 管理中心 - 服务请求](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/support/devicerepairs)，然后使用你的 Microsoft 365 凭据登录。

通过 Microsoft 客户支持创建的订单将不会显示在"Self-Serve和服务管理"模块中。

### <a name="why-am-i-unable-to-add-edit-or-delete-a-shipping-address"></a>为什么我无法添加、编辑或删除送货地址？

只能由全局管理员或帐单管理员Microsoft 365、编辑或删除送货地址。联系他们寻求帮助。  

### <a name="how-can-i-contact-microsoft-support-for-the-surface-self-serve-warranty-and-service-beta"></a>如何联系 Microsoft 支持部门获得 Surface Self-Serve Service Beta？

可以直接通过 Microsoft 管理中心中的 Surface 支持模块联系支持人员。

1. 使用你的凭据登录 Microsoft Microsoft 365中心。
2. 选择 **"**  >  **支持 Surface 设备修复>需要帮助？"** 并描述问题。
3. 如果结果没有帮助，请选择" **联系支持人员**"，然后输入问题说明。 确认你的联系人号码和电子邮件地址，选择你的首选联系人方法，然后选择"**联系我"。**

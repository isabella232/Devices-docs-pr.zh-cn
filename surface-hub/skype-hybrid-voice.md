---
title: 使用 Skype 混合语音环境的联机或混合部署 (Surface Hub)
description: 本主题介绍了如何通过云连接器版本或 Skype for Business 2015 池使用本地 PSTN 连接启用 Skype for Business 云 PBX。
keywords: 混合部署, Skype 混合语音
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831943"
---
# 使用 Skype 混合语音环境的联机或混合部署 (Surface Hub)

本主题介绍了如何通过云连接器或 Skype for Business 2015 池使用本地公用电话交换网 (PSTN) 连接启用 Skype for Business 云 PBX。 在此选项中， Skype for Business 主池和 Exchange 服务器都位于云中，并通过运行 Skype for Business 2015 或云连接版本的本地池由 PSTN 连接。 [了解有关不同的云 PBX 选项的详细信息](https://technet.microsoft.com/library/mt612869.aspx)。  

如果使用混合语音选项之一部署 Skype for Business 云 PBX，请执行以下步骤，为 Surface Hub 启用会议室帐户。 请务必先创建常规用户帐户，分配所有混合语音选项和电话号码，然后再将该帐户转换为会议室帐户。 如果未遵循此顺序，将无法分配混合电话号码。  

>[!WARNING]
>如果在配置混合语音前创建帐户（运行 Enable-CSMeetingRoom 命令），将无法配置需要的混合语音参数。 若要为之前配置的帐户配置混合语音参数或重新配置电话号码，请删除 E5 或 E3 + 云 PBX 加载项许可证，然后执行以下步骤，从步骤 3 开始。

1. 创建新的 Surface Hub 用户帐户。 此示例使用 <strong> surfacehub2@adatum.com </strong> 。 可在本地 Active Directory 中创建帐户并将其同步到云，或直接在云中创建。 

    ![新建对象 - 用户](images/new-user-hybrid-voice.png)

2. 选择**密码永不过期**。 这对于 Surface Hub 设备非常重要。

   ![密码永不过期](images/new-user-password-hybrid-voice.png)

3. 在 Office 365 中，将 **E5** 许可证或 **E3 和云 PBX** 加载项添加至针对会议室创建的用户帐户。 这是使用混合语音的必需条件。

   ![添加产品许可证](images/product-license-hybrid-voice.png)

4. 等待大约 15 分钟，直到 Skype for Business Online 中出现会议室用户帐户。

5. 在 Skype for Business Online 中创建会议室用户帐户后，通过运行下列 cmdlet 在 Skype for Business 远程 PowerShell 中对混合语音启用它：

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. 通过从 Surface Hub 拨打测试电话验证混合语音呼叫流。

7. 在电脑上启动远程 PowerShell 会话，并通过运行下列 cmdlet 连接到 Exchange。

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. 建立会话后，通过运行下列 cmdlet 修改会议室的用户帐户以将其作为 **RoomMailboxAccount** 启用。 这会允许在 Surface Hub 中对帐户进行身份验证。

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. 设置邮箱后，你将需要创建新的 Exchange ActiveSync 策略，或使用兼容的现有策略。

   Surface Hub 仅与具有 ActiveSync 策略的设备帐户（其中 **PasswordEnabled** 属性已设置为 **False**）兼容。 如果未正确设置，将无法启用 Surface Hub 上的 Exchange 服务（邮件、日历和加入会议）。
    
   如果尚未创建兼容的策略，请使用以下 cmdlet（该 cmdlet 将创建名为“Surface Hubs”的策略）。 完成创建后，你可以对其他设备帐户应用相同的策略。

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   具有兼容的策略后，你需要将该策略应用于设备帐户。 但是，仅可以将策略应用到用户帐户，而非资源邮箱。 运行下列 cmdlet 将邮箱转换为用户类型、应用策略，然后将其转换回邮箱（你可能需要重新启用此帐户并重新设置密码）。
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. 必须在设备帐户上设置各种 Exchange 属性才能改进会议体验。 可以在 [Exchange 属性](exchange-properties-for-surface-hub-device-accounts.md)中查看可以设置哪些属性。 以下 cmdlet 提供了设置 Exchange 属性的示例。

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. 在 Skype for Business Online 中将邮箱作为会议室设备启用。 运行以下支持将帐户作为会议设备的 cmdlet。 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    运行此 cmdlet 后，系统将询问用户是否在会议室中，如下图所示。 **是**会使麦克风和扬声器静音。

    ![](images/adjust-room-audio.png)


    
此时，已完全配置会议室帐户，包括混合语音。 如果使用本地 Skype，可以在本地配置如描述、位置等附加属性。 如果在 Skype Online 中创建会议室，则可以联机设置这些参数。 

在下图中，可以看到向用户显示设备的方式。


![](images/select-room-hybrid-voice.png)

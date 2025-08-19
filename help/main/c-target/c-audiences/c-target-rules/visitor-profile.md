---
keywords: 访客轮廓;Target 访客轮廓
description: 了解如何在 [!DNL Adobe Target] 中创建受众，以定位满足特定配置文件参数（如new或returning visitor、category affinity等）的访客。
title: 我是否可以定位满足特定配置文件参数的访客？
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 35%

---

# 访客轮廓

在[!DNL Adobe Target]中创建受众以定位满足特定配置文件参数的访客。

1. 在[!DNL Target]界面中，单击&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
1. 命名受众并添加可选描述。
1. 将&#x200B;**[!UICONTROL Visitor Profile]**&#x200B;拖放到受众生成器窗格中。

1. 单击&#x200B;**[!UICONTROL Select]**，然后选择以下选项之一：

   ![target_visitor_profile图像](assets/target_visitor_profile.png)

   访客配置文件参数通过 mbox（配置文件）进行传递。您可以定位新访客或回访访客，也可以包含所有用户。

   * [!UICONTROL New Visitor]
   * [!UICONTROL Returning Visitor]
   * [!UICONTROL In Other Tests]
   * [!UICONTROL Not In Other Tests]
   * [!UICONTROL First Page of Session]
   * [!UICONTROL Not First Page of Session]
   * [!UICONTROL Category Affinity]

   使用新的 `mboxPC` 为每个 mbox 调用在本地 Edge 内存中创建访客轮廓。30分钟不活动后，配置文件将保存到[!DNL Target]数据库，可从其他Edge访问。

   当网站访客在会话期间登录并获得`3rdpartyId`时，之前加载的所有与`3rdPartyId`关联的配置文件属性立即可用。

   您可以锁定自定义轮廓参数和 `user.` 参数。选择要用来定位活动的参数。如果未显示所需的参数，则该参数未由mbox触发。

1. （可选）为受众设置其他规则。
1. 单击 **[!UICONTROL Done]**。

## 培训视频：创建受众![概述徽章](/help/main/assets/overview.png)

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)

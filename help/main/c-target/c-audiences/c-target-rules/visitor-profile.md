---
keywords: 访客配置文件;Target 访客配置文件
description: 了解如何在 [!DNL Adobe Target] 以定位满足特定配置文件参数（如新访客或回访访客、类别亲和度等）的访客。
title: 我是否可以定位满足特定配置文件参数的访客？
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 46%

---

# 访客个人资料

在中创建受众 [!DNL Adobe Target] 以定位满足特定配置文件参数的访客。

1. 在 [!DNL Target] 界面中，单击&#x200B;**[!UICONTROL 受众]** > **[!UICONTROL 创建受众]**。
1. 为受众命名并添加可选描述。
1. 拖放 **[!UICONTROL 访客资料]** 进入受众生成器窗格。

1. 单击&#x200B;**[!UICONTROL 选择]**，然后选择以下选项之一：

   ![target_visitor_profile图像](assets/target_visitor_profile.png)

   访客配置文件参数通过 mbox（配置文件）进行传递。您可以定位新访客或回访访客，也可以包含所有用户。

   * [!UICONTROL 新访客]
   * [!UICONTROL 回访访客]
   * [!UICONTROL 在其他测试中]
   * [!UICONTROL 不在其他测试中]
   * [!UICONTROL 会话首页]
   * [!UICONTROL 不是会话首页]
   * [!UICONTROL 类别亲和力]

   使用新的 `mboxPC` 为每个 mbox 调用在本地 Edge 内存中创建访客配置文件。处于不活动状态30分钟后，该用户档案会保存到 [!DNL Target] 数据库，并可从其他边缘访问。

   网站访客在会话期间登录并 `3rdpartyId`，所有之前加载的与 `3rdPartyId` 将立即可用。

   您可以定位自定义配置文件参数和 `user.` 参数。选择要用来定位活动的参数。如果未显示所需的参数，则表示该参数未被mbox触发。

1. （可选）为受众设置其他规则。
1. 单击&#x200B;**[!UICONTROL 完成]**。

## 培训视频：创建受众 ![概述徽章](/help/main/assets/overview.png)

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)

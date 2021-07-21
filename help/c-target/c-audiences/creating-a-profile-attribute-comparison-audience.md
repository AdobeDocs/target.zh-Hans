---
keywords: 受众;倾向;配置文件属性;比较;对比;创建受众
description: 了解如何定义受众以比较两个配置文件属性。
title: 我是否可以比较在受众中使用的两个配置文件属性？
feature: 受众
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 61%

---

# 在 Adobe Target 中创建配置文件属性比较受众

在[!DNL Adobe Target]中定义受众，以比较[受众库](/help/c-target/c-audiences/audiences.md)或[仅限该活动的受众](/help/c-target/creating-activity-only-audience.md)中的两个配置文件属性。 使用诸如大于、小于或等于的运算符来定义受众，以动态比较两个不同配置文件属性的值。

>[!NOTE]
>
>此功能仅适用于[[!UICONTROL 访客配置文件]](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)类别。

## 概述 {#section_303CBC78194D49A2A004945D425441E1}

受众由确定在 [!DNL Target] 活动中包含或排除哪些访客的规则来定义。一个受众定义可以包含多个规则，而每个规则可以包含多个参数。如果您包含的其中一个规则使用[!UICONTROL 访客配置文件]类别，则可以根据访客配置文件属性的特定值定义规则，或将该属性的值与其他访客配置文件属性进行比较。

例如，假设您为家具公司工作，并将两个客户倾向得分上传到[!DNL Target]中：

* 在接下来的 90 天内购买餐厅家具的可能性
* 在接下来的 90 天内购买客厅家具的可能性

您可以创建一个受众，将其定义为购买餐厅家具的倾向大于购买客厅家具的倾向。[!DNL Target]然后， 将动态比较特定访客的餐厅和客厅倾向得分，以确定访客是否符合该受众的条件。

有关更多信息，请参阅[将数据导入 Target 的方法](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)。

## 在 Adobe Target 中创建配置文件属性比较受众 {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. 单击&#x200B;**[!UICONTROL 受众]** > **[!UICONTROL 创建受众]**。
1. 为受众命名并添加可选描述。
1. 将&#x200B;**[!UICONTROL 访客配置文件]**&#x200B;拖放到受众生成器窗格中。
1. 从&#x200B;**[!UICONTROL 访客配置文件]**&#x200B;下拉列表中选择一个属性：

   ![倾向得分 1](assets/propensity_score_1.png)

1. 选择您的计算器：

   ![倾向得分 2](assets/propensity_score_2.png)

1. 从&#x200B;**[!UICONTROL 选择比较类型]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 属性]**。

   “静态值”比较类型允许您将访客配置文件属性与特定值进行比较。

   ![倾向得分 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >如果您使用其中一个默认访客配置文件类别（例如，“新访客”或“回访访客”），则只能选择静态值选项。 动态比较选项不适用于默认类别。不能使用动态比较选项的其他示例包括“会话首页”、“不在其他测试中”、“不是会话首页”和“类别亲和度”。

1. 选择要与初始属性进行比较的其他属性。

   ![](assets/propensity_score_4.png)

1. 单击&#x200B;**[!UICONTROL 完成]**。

## 培训视频![概述徽章](/help/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

请观看以下视频，了解更多信息以及可使用此功能的情景：

>[!VIDEO](https://video.tv.adobe.com/v/23218/)

---
keywords: 自动个性化；选件；报表；组；报表组
description: 了解如何在Adobe中使用优惠报表组 [!DNL Target] Automated Personalization活动。 使用报表组， [!DNL Target] 为每个报表组只创建一个个性化模型。
title: 我能否在Automated Personalization活动中使用选件报表组？
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: d90e541588f51e16dd9b11ead1ece77e9ca1408b
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 62%

---

# ![PREMIUM](/help/main/assets/premium.png) 自动个性化中的选件报表组

有关在 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)活动。

报表组执行两项关键功能：

* 它们允许您查看在 AP 活动报表中分组的选件。
* 他们在 [!DNL Target] 个性化模型功能。

使用报表组时， [!DNL Target] 使用该群组中所有选件的数据，只为AP活动中的每个报表组（而不是每个选件）创建一个个性化模型。

如果您的活动设置没有足够的数据来为每个选件构建个性化模型，则报表组可以帮助降低使用自动个性化的数据要求。报表组还可以通过对相似选件进行分组来帮助解决新选件的“冷启动”问题，以便每个模型获得更多培训数据。对于定期向 AP 活动引入新选件的活动，还可使用建模组。

如果访客以相同的方式响应组中的所有选件，则此方法很有效。最佳做法是对相似访客组以相似方式进行响应的选件进行分组。换句话说，对具有相似转化率的选件进行分组。您绝不应该将所有选件都放置到一个报表组中。对具有非常不同转化率的所有选件或选件进行分组可能会降低 [!DNL Target] 个性化模型。

>[!NOTE]
>
>如果删除或替换特定建模组中的选件，则也会删除建模组中查看该特定选件的历史流量。换句话说，已删除的选件不会对用于 [!DNL Target] 个性化模型以便了解。

**设置报表组：**

1. 在 [!UICONTROL 体验] 页面，单击 **[!UICONTROL 管理内容]** 图标。

   ![](/help/main/c-reports/assets/ap_manage_content.png)

1. 单击“**[!UICONTROL 管理内容]**”对话框顶部的[!UICONTROL 选件]选项卡。
1. （视情况而定）将特定体验添加到报表组，方法是将鼠标悬停在所需的选件上，然后单击&#x200B;**[!UICONTROL 报表组]**&#x200B;文件夹图标。

   ![](/help/main/c-reports/assets/ap_manage_content_2.png)

1. （视情况而定）在报表组中批量添加体验，方法是选中相关体验的复选框，然后单击对话框右上角的&#x200B;**[!UICONTROL 报表组]**&#x200B;文件夹图标。

   ![](/help/main/c-reports/assets/ap_manage_content_3.png)

1. （视情况而定）要将选定选件分配给现有报表组，请选择 **[!UICONTROL 现有]**，从下拉列表中选择所需的报表组，然后单击 **[!UICONTROL 应用]**.

   或

   要创建新报表组以将所选选件分配到该报表组，请选择&#x200B;**[!UICONTROL 新建]**，为新报表组命名，然后单击&#x200B;**[!UICONTROL 应用]**。

   ![](/help/main/c-reports/assets/ap_reporting_groups.png)

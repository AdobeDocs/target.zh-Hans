---
description: 有关在自动个性化 (AP) 活动中使用报表组的信息。
keywords: 自动个性化;选件;报表;组
seo-description: 有关在自动个性化 (AP) 活动中使用报表组的信息。
seo-title: 自动个性化中的选件报表组
solution: Target
title: 自动个性化中的选件报表组
title-outputclass: premium
topic: 高级
uuid: 5b111a68-bd05-4ef1-8156-d064f2c7e257
badge: premium
translation-type: tm+mt
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# ![PREMIUM](/help/assets/premium.png) 自动个性化中的选件报表组{#offer-reporting-groups-in-automated-personalization}

有关在自动个性化 (AP) 活动中使用报表组的信息。

报表组执行两项关键功能：

* 它们允许您查看在 AP 活动报表中分组的选件。
* 它们在 Target 的个性化模型运作方面发挥着关键作用。

使用报表组时，Target 会使用该组中所有选件的数据，仅为 AP 活动中的每个报表组创建一个个性化模型，而不是为每个选件创建个性化模型。

如果您的活动设置没有足够的数据来为每个选件构建个性化模型，则报表组可以帮助降低使用自动个性化的数据要求。报表组还可以通过对相似选件进行分组来帮助解决新选件的“冷启动”问题，以便每个模型获得更多培训数据。对于定期向 AP 活动引入新选件的活动，还可使用建模组。

如果访客以相同的方式响应组中的所有选件，则此方法很有效。最佳做法是对相似访客组以相似方式进行响应的选件进行分组。换句话说，对具有相似转化率的选件进行分组。您绝不应该将所有选件都放置到一个报表组中。对所有选件进行分组或对具有完全不同转化率的选件进行分组，可能会降低 Target 个性化模型的有效性。

>[!NOTE]
>
>如果删除或替换特定建模组中的选件，则也会删除建模组中查看该特定选件的历史流量。换句话说，删除的选件对于 Target 的个性化模型使用哪些数据来进行学习，不会有任何影响。

**设置报表组：**

1. 在 AP 活动的“体验”页面上，单击**[!UICONTROL 管理内容]图标。**

   ![](assets/ap_manage_content.png)

1. 单击“[!UICONTROL **管理内容]”对话框顶部的**[!UICONTROL 选件]选项卡。
1. （视情况而定）将特定体验添加到报表组，方法是将鼠标悬停在所需的选件上，然后单击**[!UICONTROL 报表组]文件夹图标。**

   ![](assets/ap_manage_content_2.png)

1. （视情况而定）在报表组中批量添加体验，方法是选中相关体验的复选框，然后单击对话框右上角的**[!UICONTROL 报表组]文件夹图标。**

   ![](assets/ap_reporting_groups.png)

1. 要将所选选件分配到现有报表组，请选择**[!UICONTROL 现有]**，从下拉列表中选择所需的报表组，然后单击**[!UICONTROL 应用]**。

   或

   要创建新报表组以将所选选件分配到该报表组，请选择**[!UICONTROL 新建]**，为新报表组命名，然后单击**[!UICONTROL 应用]**。

   ![](assets/ap_manage_content_3.png)


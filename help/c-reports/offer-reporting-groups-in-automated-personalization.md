---
keywords: 自动个性化；优惠;报告；组；报告组
description: 有关在Adobe TargetAutomated Personalization(AP)活动中使用报告组的信息。
title: 优惠报告集团在Automated Personalization（美联社）活动
feature: Reports
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 63%

---


# ![PREMIUM](/help/assets/premium.png) 自动个性化中的选件报表组{#offer-reporting-groups-in-automated-personalization}

有关在[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP)活动中使用报告组的信息。

报表组执行两项关键功能：

* 它们允许您查看在 AP 活动报表中分组的选件。
* 他们在[!DNL Target]个性化模型的运行方式方面起着关键作用。

使用报告组时，[!DNL Target]仅为每个报告组创建一个个性化模型，而不是使用该组中所有优惠的数据在AP活动中创建每个优惠。

如果您的活动设置没有足够的数据来为每个选件构建个性化模型，则报表组可以帮助降低使用自动个性化的数据要求。报表组还可以通过对相似选件进行分组来帮助解决新选件的“冷启动”问题，以便每个模型获得更多培训数据。对于定期向 AP 活动引入新选件的活动，还可使用建模组。

如果访客以相同的方式响应组中的所有选件，则此方法很有效。最佳做法是对相似访客组以相似方式进行响应的选件进行分组。换句话说，对具有相似转化率的选件进行分组。您绝不应该将所有选件都放置到一个报表组中。将所有优惠分组或将具有非常不同转化率的优惠分组可能会降低[!DNL Target]个性化模型的有效性。

>[!NOTE]
>
>如果删除或替换特定建模组中的选件，则也会删除建模组中查看该特定选件的历史流量。换言之，已删除的优惠不会影响[!DNL Target]个性化模型所使用的数据。

**设置报表组：**

1. 在AP活动的[!UICONTROL 体验]页面上，单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;图标。

   ![](assets/ap_manage_content.png)

1. 单击“**[!UICONTROL 管理内容]**”对话框顶部的[!UICONTROL 选件]选项卡。
1. （视情况而定）将特定体验添加到报表组，方法是将鼠标悬停在所需的选件上，然后单击&#x200B;**[!UICONTROL 报表组]**&#x200B;文件夹图标。

   ![](assets/ap_manage_content_2.png)

1. （视情况而定）在报表组中批量添加体验，方法是选中相关体验的复选框，然后单击对话框右上角的&#x200B;**[!UICONTROL 报表组]**&#x200B;文件夹图标。

   ![](assets/ap_manage_content_3.png)

1. （视情况而定）要将选定优惠分配给现有报告组，请选择&#x200B;**[!UICONTROL 现有]**，从下拉列表中选择所需的报告组，然后单击&#x200B;**[!UICONTROL 应用]**。

   或

   要创建新报表组以将所选选件分配到该报表组，请选择&#x200B;**[!UICONTROL 新建]**，为新报表组命名，然后单击&#x200B;**[!UICONTROL 应用]**。

   ![](assets/ap_reporting_groups.png)


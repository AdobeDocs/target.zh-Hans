---
keywords: 自动个性化；选件；报表；组；报表组；ap
description: 了解如何在 [!DNL Adobe Target] [!UICONTROL Automated Personalization]活动中使用选件报表组。
title: 我能否在[!UICONTROL Automated Personalization]活动中使用选件报表组？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Reports
hide: true
hidefromtoc: true
source-git-commit: 19f70ce944e4db4aa0774da034a0d16be34a4ec8
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 15%

---

# [!UICONTROL Automated Personalization]中的选件报表组

有关在[!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)活动中使用报表组的信息。

报表组执行两项关键功能：

* 通过报表组，可查看在AP活动报表中分组的选件。
* 报表组在[!DNL Target]个性化模型的运行方式中发挥着关键作用。

当您使用报表组时，[!DNL Target]会使用来自每个报表组中的所有选件的数据，为该组创建一个个性化模型。 如果没有报表组，[!DNL Target]将为您的AP活动中的每个选件创建个性化模型。

如果您的活动设置没有足够的数据来为每个选件构建个性化模型，则报表组有助于减少使用[!UICONTROL Automated Personalization]的数据要求。 报表组还可以通过对相似选件进行分组来帮助解决新选件的“冷启动”问题，以便每个模型获得更多培训数据。建模组也可用于定期向AP活动引入新选件的活动。

如果访客以相同的方式响应组中的所有选件，则此方法很有效。最佳做法是对相似访客组以相似方式进行响应的选件进行分组。换句话说，对具有相似转化率的选件进行分组。您绝不应该将所有选件都放置到一个报表组中。对所有选件进行分组或将具有不同转化率的选件分组可能会降低[!DNL Target]个性化模型的有效性。

>[!NOTE]
>
>如果删除或替换特定建模组中的产品建议，则也会删除建模组中查看该特定产品建议的历史流量。换言之，删除的选件不影响[!DNL Target]个性化模型要学习的数据。

## 设置报表组

1. 在AP活动的&#x200B;**[!UICONTROL Experiences]**&#x200B;页面上，单击&#x200B;**[!UICONTROL Manage Content]**&#x200B;图标（ ![管理内容图标](/help/main/assets/icons/Experience.svg)）
1. 单击[!UICONTROL Manage Content]对话框顶部的&#x200B;**[!UICONTROL Offers]**&#x200B;选项卡。
1. （视情况而定）单击所需选件的[!UICONTROL More Actions]图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg) ），然后单击&#x200B;**[!UICONTROL Reporting Group]**，将特定体验添加到报表组。

1. （视情况而定）在报表组中批量添加体验，方法是选中相关体验的复选框，然后单击对话框底部的&#x200B;**[!UICONTROL Reporting Group]**。

1. 要将所选选件分配给现有报表组，请选择&#x200B;**[!UICONTROL Existing]**，从下拉列表中选择所需的报表组，然后单击&#x200B;**[!UICONTROL Confirm]**。

   或

   要创建要将选定选件分配到的报表组，请选择&#x200B;**[!UICONTROL New]**，命名新的报表组，然后单击&#x200B;**[!UICONTROL Confirm]**。

您可以使用[!UICONTROL Location]列表按位置筛选选件。 使用[!UICONTROL Report Group]列表按报表组筛选选件。 您还可以使用[!UICONTROL Report Group]列表过滤[!UICONTROL Unassigned Offers]，以便将报表组分配给当前未分配给任何报表组的选件。

有关将选件定位到特定受众的信息，请参阅[定位[!UICONTROL Automated Personalization]选件](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E)。

## 注意事项

* 请务必了解报表组会影响[!DNL Target]构建其模型的方式。 因此，[!DNL Adobe]建议，只有在您计划在活动上线时替换或添加新优惠时，才使用报表组。 如果在实时活动中引入了新选件，则通过将新选件放入具有现有相似选件的组中，计算机可以使用已为其组中的其他选件收集的数据来了解新选件。 您绝不应该将所有选件都放置到一个报表组中。

* AP活动具有位置+选件（可建模）的组合。 当[!DNL Target]在报表中记录数据时，[!DNL Target]会考虑此类组合，以便明确了解选件来自哪个事件（显示、单击等）。

  例如，一个活动可能具有多个位置和多个选件，这些位置和选件可能会重叠。 如果访客在不同位置看到多个这些选件，[!DNL Target]将仅记录这些选件的数据。 如果同一访客稍后单击某个选件，[!DNL Target]将仅记录该组合中的事件（并非所有组合均如此）。

  同样，如果点击来自其他位置（该位置存在于量度中，但不显示选件），则此事件将记录到活动下，但不记录任何选件+位置组合。 因此，此选件不会显示在选件报表组中。

  此行为是因为单击可能来自其他mbox，而不是提供选件的mbox。 因此，量度与活动相关联，但不与选件相关联。

## 在报表组中查看选件

1. 单击&#x200B;**[!UICONTROL Activities]**，从列表中单击所需的[!UICONTROL Automated Personalization]活动，然后单击&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡以显示[选件级别](/help/main/c-reports/personalization-reports/reports-ap.md)报表。

   如果您有许多活动，请单击[!UICONTROL Show Filters]（漏斗）图标，然后选中[!UICONTROL Automated Personalization]复选框以筛选列表以仅显示[!UICONTROL Automated Personalization]个活动。

1. 单击表格中的&#x200B;**[!UICONTROL Control]**&#x200B;或&#x200B;**[!UICONTROL Targeted]**&#x200B;以在报表组内显示未分组的选件和选件。

   ![优惠组：控制和目标](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

有关使用[!UICONTROL Automated Personalization]报告（包括[!UICONTROL Offer Level]报告）的信息，请参阅[Automated Personalization摘要报告](/help/main/c-reports/personalization-reports/reports-ap.md)。

---
keywords: 自动个性化；选件；报表；组；报表组；AP
description: 了解如何在Adobe中使用优惠报表组 [!DNL Target] [!UICONTROL Automated Personalization] 活动。
title: 我能否在Automated Personalization活动中使用选件报表组？
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 748051dccf4a0df49ac05e699fa14801c148d45e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png)[!UICONTROL  自动个性化中的选件报表组]

有关在 [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)活动。

报表组执行两项关键功能：

* 通过报表组，您可以查看在AP活动报表中分组的选件。
* 报表组在 [!DNL Target] 个性化模型功能。

使用报表组时， [!DNL Target] 使用该群组中所有选件的数据，为每个报表群组创建一个个性化模型。 如果没有报表组， [!DNL Target] 为AP活动中的每个选件创建一个个性化模型。

如果活动设置没有足够的数据来为每个选件构建个性化模型，则报表组可以帮助降低使用的数据要求 [!UICONTROL Automated Personalization]. 报表组还可以通过对相似选件进行分组来帮助解决新选件的“冷启动”问题，以便每个模型获得更多培训数据。建模组还可用于定期向AP活动引入新选件的活动。

如果访客以相同的方式响应组中的所有选件，则此方法很有效。最佳做法是对相似访客组以相似方式进行响应的选件进行分组。换句话说，对具有相似转化率的选件进行分组。您绝不应该将所有选件都放置到一个报表组中。对具有不同转化率的所有选件或选件进行分组可能会降低 [!DNL Target] 个性化模型。

>[!NOTE]
>
>如果删除或替换特定建模组中的选件，则也会删除建模组中查看该特定选件的历史流量。换句话说，已删除的选件不会对用于 [!DNL Target] 个性化模型以便了解。

## 设置报表组

1. 在 **[!UICONTROL 体验]** 页面，单击 **[!UICONTROL 管理内容]** 图标。

   ![“管理内容”图标](/help/main/c-reports/assets/ap_manage_content.png)

1. 单击“**[!UICONTROL 管理内容]**”对话框顶部的[!UICONTROL 选件]选项卡。
1. （视情况而定）将特定体验添加到报表组，方法是将鼠标悬停在所需的选件上，然后单击&#x200B;**[!UICONTROL 报表组]**&#x200B;文件夹图标。

   ![“报表组”图标](/help/main/c-reports/assets/ap_manage_content_2.png)

1. （视情况而定）在报表组中批量添加体验，方法是选中相关体验的复选框，然后单击 **[!UICONTROL 报表组]** 文件夹图标。

   ![“报表组”图标](/help/main/c-reports/assets/ap_manage_content_3.png)

1. 要将所选选件分配到现有报表组，请选择&#x200B;**[!UICONTROL 现有]**，从下拉列表中选择所需的报表组，然后单击&#x200B;**[!UICONTROL 应用]**。

   或

   要创建报表组以将选定选件分配到，请选择 **[!UICONTROL 新建]**，命名新报表组，然后单击 **[!UICONTROL 应用]**.

   ![用于创建新报表组的新图标](/help/main/c-reports/assets/ap_reporting_groups.png)

您可以使用 [!UICONTROL 位置] 列表按位置筛选选件。 使用[!UICONTROL 报表组]列表可按报表组筛选选件。您还可以使用“[!UICONTROL 报表组]”来筛选“[!UICONTROL 未分配选件]”，以便将某个报表组分配给当前未分配给任何报表组的选件。

有关将选件定位到特定受众的信息，请参阅 [Target AP选件](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## 注意事项

* 请务必了解报表组对 [!DNL Target] 建立模型。 因此， [!DNL Adobe] 建议仅当您计划在活动开始时替换或添加新选件时，才使用报表组。 如果在实时活动中引入了新选件，则将新选件放入具有现有类似选件的组中后，计算机将能够使用已收集到的用于其组中其他选件的数据来了解新选件。 您绝不应该将所有选件都放置到一个报表组中。

* AP活动包含位置+选件（可建模型）的组合。 When [!DNL Target] 在报表中记录数据， [!DNL Target] 考虑这些组合，以便明确选件来自哪个事件（显示、点击等）。

   例如，一个活动可能具有多个位置和多个选件，这些位置和选件可能会重叠。 如果访客在不同位置看到这些选件中的多个选件， [!DNL Target] 仅记录这些选件的数据。 如果同一访客稍后点击某个选件， [!DNL Target] 仅记录该组合中的事件（而非所有组合）。

   同样，如果点击来自其他位置（该位置位于量度中，但未显示选件），则此事件将记录在活动下，但不会记录到任何选件+位置组合。 因此，此选件不会显示在选件报表组中。

   此行为是由于点击可能来自其他mbox，而不是提供选件的mbox所致。 因此，量度与活动关联，但与选件不关联。

## 在报表组中查看选件

1. 单击 **[!UICONTROL 活动]**，请单击所需的 [!UICONTROL Automated Personalization] 活动，然后单击 **[!UICONTROL 报表]** 选项卡 [选件级别](/help/main/c-reports/personalization-reports/reports-ap.md) 报表。

   如果您有多种活动，则可以对活动列表进行筛选，方法是从“[!UICONTROL 类型]”下拉列表中选择“[!UICONTROL 自动个性化]”。

1. 单击 **[!UICONTROL 控制]** 或 **[!UICONTROL 目标]** 在表中显示报表组内未分组的选件和选件。

   ![选件组：控制和目标](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

有关使用 [!UICONTROL Automated Personalization] 报告(包括 [!UICONTROL 选件级别] 报表)，请参阅 [Automated Personalization摘要报表](/help/main/c-reports/personalization-reports/reports-ap.md).



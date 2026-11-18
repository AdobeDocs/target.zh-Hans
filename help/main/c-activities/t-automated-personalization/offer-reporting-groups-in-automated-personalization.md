---
keywords: 自动个性化；选件；报表；组；报表组；ap
description: 了解如何在[!DNL Adobe Target] [!UICONTROL Automated Personalization]活动中使用选件报表组。
title: 我能否在[!UICONTROL Automated Personalization]活动中使用选件报表组？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
TQID: 'https://experienceleague.adobe.com/VW3zVGXb3IuQMDaRyidbkjsbUrojvwFsvwP3yRVeHp4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: e8a43148-398f-56c7-9433-6564f96999c2
    internal-label: Reports
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 3%
---
# [!UICONTROL Automated Personalization]中的选件报表组 {#offer-reporting-groups}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解选件报表组如何在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中工作、如何设置以及如何在报表中查看它们。

>[!ENDSHADEBOX]

报表组允许您将[!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)活动的选件组织到组中。 报表组执行两项关键功能：

* 它们允许您查看在 AP 活动报表中分组的选件。
* 它们在[!DNL Target]个性化模型的运行方式中发挥着关键作用。

当您使用报表组时，[!DNL Target]会使用该组中所有选件的数据为每个报表组创建一个个性化模型。 如果没有报表组，[!DNL Target]将为您的AP活动中的每个选件创建个性化模型。

当活动设置没有足够的数据为每个选件构建个性化模型时，报表组还会降低使用&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;的数据要求。 它们有助于解决新选件的“冷启动”问题，这些选件与相似选件分组，以便每个模型具有更多可供培训的数据。

如果访客对组中的所有选件响应方式相同，因此组选件具有相似的转化率，则此方法非常有效。 切勿将所有选件放入单个报表组中，也不要将具有不同转化率的选件分组，因为这两种选择都可能会降低[!DNL Target]个性化模型的有效性。

>[!NOTE]
>
>如果从报表组中删除或替换了某个选件，则也会从报表组中删除查看该选件的历史流量，因此删除的选件不会增加[!DNL Target]个性化模型用于学习的数据。


## 注意事项

### 将报表组用于实时活动

报表组影响[!DNL Target]构建其模型的方式。 因此，[!DNL Adobe]建议，只有在您计划在活动上线时替换或添加优惠时，才使用报表组。 如果将新选件引入到实时活动中，则通过将新选件放入具有现有相似选件的组中，允许[!DNL Target]使用已为组中的其他选件收集的数据来了解新选件。

### 如何记录优惠和位置的数据

AP活动具有位置和选件（可建模）的组合。 当[!DNL Target]在报表中记录数据时，它会考虑这些组合，因此会清楚知道选件是来自哪个事件（显示、单击等）。

例如，一个活动可能具有多个位置和多个选件，这些位置和选件可能会重叠。 如果访客在不同位置看到多个这些选件，[!DNL Target]将仅记录这些选件的数据。 如果同一访客稍后单击某个选件，[!DNL Target]将仅记录该组合中的事件（并非所有组合均如此）。

同样，如果点击来自某个量度中存在的不同位置，但未显示选件，则事件将记录到活动下，但不记录选件和位置的任意组合。 因此，此选件不会显示在选件报表组中。 发生此行为的原因是，单击的mbox可能与提供选件的mbox不同。 在这种情况下，量度与活动关联，但与选件无关。

## 设置报表组

将选件分配给报表组将确定[!DNL Target]如何构建其个性化模型以及选件在活动报表中的显示方式。 在构建活动时设置组，如果向实时活动添加新选件，则设置后者。

1. 在AP活动的&#x200B;**[!UICONTROL 体验]**&#x200B;页面上，单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;图标（![管理内容图标](/help/main/assets/icons/Experience.svg)）。

1. 单击“**[!UICONTROL 管理内容]**”对话框顶部的&#x200B;**[!UICONTROL 选件]**&#x200B;选项卡。

   ![配置图标](../assets/ap-offers-2.png)

1. （视情况而定）选择要添加到报表组的选件。

   * 要添加单个选件，请单击选件的&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg)），然后单击&#x200B;**[!UICONTROL 报表组]**。
   * 要同时添加多个选件，请选中选件对应的复选框，然后单击对话框底部的&#x200B;**[!UICONTROL 报表组]**。

1. 将所选选件分配给报表组。

   * 要将选件分配给现有报表组，请选择&#x200B;**[!UICONTROL 现有]**，从下拉列表中选择报表组，然后单击&#x200B;**[!UICONTROL 确认]**。
   * 要为选件创建报表组，请选择&#x200B;**[!UICONTROL 新建]**，为新报表组命名，然后单击&#x200B;**[!UICONTROL 确认]**。

要缩小选件列表，请使用&#x200B;**[!UICONTROL 位置]**&#x200B;列表按位置进行筛选，或使用&#x200B;**[!UICONTROL 报表组]**&#x200B;列表按报表组进行筛选。 **[!UICONTROL 报表组]**&#x200B;列表还提供了&#x200B;**[!UICONTROL 未分配选件]**&#x200B;选项，该选项显示尚未属于任何报表组的选件，以便您可以将它们分配给一个报表组。

有关将选件定位到特定受众的信息，请参阅[定位&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;选件](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#set-up-targeting-rules)。

## 在报表组中查看选件

**[!UICONTROL 选件级别]**&#x200B;报表显示活动选件的执行情况（按报表组分组），以便您可以比较各个组以及各个选件。

1. 单击&#x200B;**[!UICONTROL 活动]**，单击列表中的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡以显示[选件级别](/help/main/c-reports/personalization-reports/reports-ap.md)报表。

   如果您有许多活动，请单击&#x200B;**[!UICONTROL 显示筛选器]** (funnel)图标，然后选中&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;复选框以仅显示&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动。

1. 单击表中的&#x200B;**[!UICONTROL 控制]**&#x200B;或&#x200B;**[!UICONTROL 目标]**&#x200B;以显示报表组内未分组的选件和选件。

   ![优惠组：控制和目标](/help/main/c-reports/assets/offer-groups.png)

有关使用&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;报告（包括&#x200B;**[!UICONTROL 选件级别]**&#x200B;报告）的信息，请参阅[Automated Personalization摘要报告](/help/main/c-reports/personalization-reports/reports-ap.md)。

---
keywords: 定位；AP报表；自动个性化报表；活动级别报表；选件级别报表；选件详细信息报表；常见问题解答
description: 了解如何在Adobe Target中解释Automated Personalization摘要报表。 您可以从此报表切换到自动化区段和重要属性报表。
title: 如何使用Automated Personalization摘要报表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 11%

---

# Automated Personalization 摘要报表

[!DNL Adobe Target]中[!UICONTROL Automated Personalization]个活动的用户可以使用专门的摘要报告。

>[!NOTE]
>
>[!UICONTROL Automated Personalization]作为[!DNL Target Premium]解决方案的一部分提供。 在没有[Target Premium许可证](/help/main/c-intro/intro.md#premium)的[!DNL Target Standard]中不包括它。

1. 单击&#x200B;**[!UICONTROL Activities]**，从列表中单击所需的[!UICONTROL Automated Personalization]活动，然后单击&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡。

   如果您有许多活动，则可以通过从[!UICONTROL Type]下拉列表中选择[!UICONTROL Automated Personalization]来筛选列表。

1. （可选）单击&#x200B;**[!UICONTROL Download]**&#x200B;图标以下载按所有可用成功量度划分的摘要视图（例如，比较控制和目标流量）。

[!UICONTROL Automated Personalization]提供了以下报告：

* 活动级别
* 选件级别
* 自动化区段
* 重要属性

## 活动级别报表 {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL Activity Level]报表将使用[!UICONTROL Automated Personalization]算法的聚合性能与随机提供的内容（控制）进行比较。

![活动级别的报表](/help/main/c-reports/assets/box_plot_ap.png)

用于解释 A/B 测试结果的标准规则仍然适用，包括提升度、置信度、趋势、持续时间等。有关解释结果的更多信息，请参阅[A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

## 选件级别报表 {#section_CAA6409879E349C6906E2BE8156D87A1}

随机林体验的[!UICONTROL Offer Level]报表将比较每个算法应用的选件与同一随机提供的选件（控制）的性能。 因此，这种观点不应将优惠相互进行比较。

单击体验算法（随机林或控制）以查看[!UICONTROL Offer Level]报表。

Adobe Target中的![选件级别报告](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>时钟图标表示仍在构建算法模型。 复选标记图标表示已建立基本算法。

选件可以显示在[报表组](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)中，并且这些报表组可以折叠和展开。 单击表格中的&#x200B;**[!UICONTROL Control]**&#x200B;或&#x200B;**[!UICONTROL Targeted]**&#x200B;以查看按报表组而不是按选件汇总的信息。

## 自动化区段

单击[!UICONTROL Automated Segments]图标。 此报表可显示不同访客对您的AP/AT活动中的选件/体验做出的不同响应。 此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的选件/体验。

![自动化区段图标](/help/main/c-reports/assets/icon-automated-sements-ap.png)

有关详细信息，请参阅[自动化区段报表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要属性

单击[!UICONTROL Important Attributes]图标。 此报表显示了在不同活动中，不同属性对模型如何决定进行个性化的重要性如何。 此报表可显示影响模型的排名靠前的属性及其相对重要性。

![重要属性图标](/help/main/c-reports/assets/icon-important-attributes-ap.png)

有关详细信息，请参阅[重要属性报表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

## 常见问题解答

### 为什么活动级别报表和选件级别报表中的数据存在差异？

**[!UICONTROL Activity Level]报表**： [!UICONTROL Activity Level]报表中记录的访问量捕获了控制体验与“目标”流量的访问次数。 目标流量包括探索流量和个性化流量的组合。

**选件级别报表**： [!UICONTROL Offer Level]报表中记录的展示次数捕获了每个选件的展示次数。 因此，在具有多个位置的活动中，所有报表组在[!UICONTROL Offer Level]报表中记录的访问总数等于[!UICONTROL Activity Level]报表中为控制流量或目标流量记录的访问次数与活动中位置总数的倍数。 在默认内容为可用选项的位置发生的默认内容展示记录在“默认内容”选件组中。 未分配给报表组的选件展示次数记录在“未分组”选件组中。

>[!NOTE]
>
>[!UICONTROL Offer Level]报表中记录的展示次数可能不是[!UICONTROL Activity Level]报表中记录的访问次数的精确整数倍。 这是由于通过Internet捕获报表数据流量时发生的细微差异（典型差异率低于5%）。 因此，当活动中的可用位置数量在激活活动后发生更改时，展示次数不会是准确的倍数。

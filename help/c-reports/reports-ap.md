---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: 自动个性化活动的用户可以使用专门的报表。
title: 自动个性化摘要报表
uuid: 959b6814-9686-4741-8a79-5957e64f6209
translation-type: tm+mt
source-git-commit: 72f1a92f299286e14211f0c8773ba7718d779198

---


# ![PREMIUM](/help/assets/premium.png) 自动个性化摘要报表{#automated-personalization-summary-reports}

自动个性化活动的用户可以使用专门的报表。

>[!NOTE]
>
>“自动个性化”作为 [!DNL Target Premium] 解决方案的一部分提供。It is not included with [!DNL Target Standard] without a [Target Premium license](/help/c-intro/intro.md#premium).

1. 单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需的[!UICONTROL 自动个性化]活动，然后单击**[!UICONTROL &#x200B;报表]**选项卡。

   如果您有多种活动，则可以对活动列表进行筛选，方法是从“[!UICONTROL 类型]”下拉列表中选择“[!UICONTROL 自动个性化]”。

1. （可选）单击“[!UICONTROL 下载]”图标，以下载按所有可用成功量度划分的摘要视图（例如，比较控制流量和目标流量）。

[!UICONTROL 自动个性化]提供了以下报表：

## Activity Level report {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活动级别]的报表可将使用[!UICONTROL 自动个性化]算法的整体性能与使用随机提供内容（控制）的整体性能进行比较。

![活动级别的报表](/help/c-reports/assets/box_plot_ap.png)

用于解释 A/B 测试结果的标准规则仍然适用，包括提升度、置信度、趋势、持续时间等。有关结果解释的更多信息，请参阅[关于转化率](../c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844)。

## Offer Level report {#section_CAA6409879E349C6906E2BE8156D87A1}

随机林体验的[!UICONTROL 选件级别]的报表可将每个应用了算法的选件与随机提供内容的同一选件（控制）进行比较。由此可见，此视图不会对选件进行相互比较。

单击体验算法（随机林或控制），可查看选件级别的报表。

![](assets/ap_OfferLevelRpt.png)

选件可以在报表组中显示，而这些报表组可以折叠或展开。在下拉列表中选择“[!UICONTROL 报表组]”，可查看按报表组（而不是选件）汇总的信息。

>[!NOTE]
>
>时钟图标指示仍在构建算法模型。复选标记图标指示已建立基础算法。

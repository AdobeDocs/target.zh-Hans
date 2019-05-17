---
description: 自动个性化活动的用户可以使用专门的报表。
keywords: 定位;AP 报表;自动个性化报表;活动级别的报表;选件级别的报表;选件详细信息报表
seo-description: 自动个性化活动的用户可以使用专门的报表。
seo-title: 自动个性化摘要报表
solution: Target
title: 自动个性化摘要报表
title-outputclass: premium
uuid: 959b6814-9686-4741-8a79-5957e64f6209
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) 自动个性化摘要报表{#automated-personalization-summary-reports}

自动个性化活动的用户可以使用专门的报表。

>[!NOTE]
>
>“自动个性化”作为 [!DNL Target Premium] 解决方案的一部分提供。在没有 [!DNL Target Premium] 许可证的情况下，不会包含在 [!DNL Target Standard] 中。

1. 单击**[!UICONTROL 活动]**，从列表中单击所需的[!UICONTROL 自动个性化]活动，然后单击**报表]选项卡。[!UICONTROL **

   如果您有多种活动，则可以对活动列表进行筛选，方法是从“[!UICONTROL 类型]”下拉列表中选择“[!UICONTROL 自动个性化]”。

1. （可选）单击“[!UICONTROL 下载]”图标，以下载按所有可用成功量度划分的摘要视图（例如，比较控制流量和目标流量）。

>[!NOTE]
>
>没有为[!UICONTROL 自动个性化]报表提供[!UICONTROL 设置]图标。

[!UICONTROL 自动个性化]提供了以下报表：

## 活动级别的报表 {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL 活动级别]的报表可将使用[!UICONTROL 自动个性化]算法的整体性能与使用随机提供内容（控制）的整体性能进行比较。

![](assets/box_plot_ap.jpg)

用于解释 A/B 测试结果的标准规则仍然适用，包括提升度、置信度、趋势、持续时间等。有关结果解释的更多信息，请参阅[关于转化率](../c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844)。

## 选件级别的报表 {#section_CAA6409879E349C6906E2BE8156D87A1}

随机林体验的[!UICONTROL 选件级别]的报表可将每个应用了算法的选件与随机提供内容的同一选件（控制）进行比较。由此可见，此视图不会对选件进行相互比较。在以下示例中可以看出，与随机提供内容（控制）的情况相比，按照算法逻辑（随机林）提供内容时选件 D 表现出 12.43% 的提升度。

单击体验算法（随机林或控制），可查看选件级别的报表。

![](assets/ap_OfferLevelRpt.png)

选件可以在报表组中显示，而这些报表组可以折叠或展开。在下拉列表中选择“[!UICONTROL 报表组]”，可查看按报表组（而不是选件）汇总的信息。

>[!NOTE]
>
>时钟图标指示仍在构建算法模型。复选标记图标指示已建立基础算法。


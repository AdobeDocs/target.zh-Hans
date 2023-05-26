---
keywords: 推荐；推荐活动；标准；算法
description: 了解如何选择要在您的Adobe中使用的标准（确定要推荐哪些产品或内容的规则） [!DNL Target] Recommendations活动。
title: 如何为Recommendations活动选择标准？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 72%

---

# 选择标准

选择 [标准](/help/main/c-recommendations/c-algorithms/algorithms.md) 用于您的 [!DNL Adobe Target Recommendations] 活动。 标准即规则，可根据预先确定的一组访客行为来确定要推荐的产品。

您可以添加多个标准，以便对多个推荐类型进行相互测试。

如果选择多个标准，则流量会平均拆分到选择的标准中。例如，如果您选择了两个标准，且您的活动设计为将默认内容显示给 20% 的活动参加者，那么 40% 的活动参加者将看到由每个标准控制的推荐。没有选项可以用来更改每个标准的百分比。

* 要搜索现有标准（例如，如果显示了许多标准卡片），请在搜索字段中键入相应内容直到显示所需标准为止，然后选择该标准，并单击&#x200B;**[!UICONTROL 完成]**。

   [!DNL Recommendations] 中提供了一些自带标准。您和您的团队也可以创建自己的自定义标准。

* 要创建新标准，请单击 **[!UICONTROL 创建标准]** > **[!UICONTROL 创建标准]**，然后填写有关新条件的信息。 有关创建新标准的信息，请参阅[创建新标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)。

**选择标准：**

1. While [创建新推荐](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)，在 **[!UICONTROL 选择标准]** 对话框中，找到并选择一个或多个标准。

   ![“选择标准”对话框](/help/main/c-recommendations/t-create-recs-activity/assets/filters.png)

   您可以使用“[!UICONTROL 行业类型]”筛选器、“[!UICONTROL 页面类型]”筛选器和“[!UICONTROL 兼容]”复选框来筛选标准列表。这些选项可帮助您找到所需的标准。

   * **行业类型：**&#x200B;行业类型用于帮助对 [!DNL Recommendations] 标准进行分类。要更改默认的垂直行业，请单击 **[!UICONTROL Recommendations]** > **[!UICONTROL 设置]** 并选择所需的默认值 **[!UICONTROL 垂直行业]** 设置。
   * **页面类型：**&#x200B;页面类型可帮助您对推荐进行分类。每种页面类型还有一些内置标准，可供您选择。
   * **兼容：**&#x200B;仅显示要求选定页面传递所需数据的标准。并非每个标准都能在每个页面上正常运行。页面或 mbox 需要传入 `entity.id` 或 `entity.categoryId`，才能兼容当前项目/当前类别推荐。一般来说，最好只显示兼容的标准。但是，如果您希望不兼容的标准也可用于活动，请清除&#x200B;**[!UICONTROL 兼容]**&#x200B;复选框。可以在设置中禁用或启用此选项： **[!UICONTROL Recommendations]** > **[!UICONTROL 设置]**.

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;以显示“[选择设计](/help/main/c-recommendations/c-design-overview/design-overview.md)”对话框。

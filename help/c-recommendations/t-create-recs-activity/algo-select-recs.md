---
description: 选择要在您的“推荐”活动中使用的标准。
keywords: 推荐;推荐活动;标准
seo-description: 选择要在您的“推荐”活动中使用的标准。
seo-title: 选择标准
solution: Target
title: 选择标准
title-outputclass: premium
topic: Premium
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
badge: premium
translation-type: tm+mt
source-git-commit: 37ddc2858eb8088f470f87c1a6c0927cd96cc48e

---


# ![PREMIUM](/help/assets/premium.png) 选择标准{#select-criteria}

选择要在您的“推荐”活动中使用的标准。

您可以添加多个标准，以便对多个推荐类型进行相互测试。

如果选择多个标准，则流量会平均拆分到选择的标准中。例如，如果您选择了两个标准，且您的活动设计为将默认内容显示给 20% 的活动参加者，那么 40% 的活动参加者将看到由每个标准控制的推荐。没有选项可以用来更改每个标准的百分比。

* 要搜索现有标准（例如，如果显示了许多标准卡片），请在搜索字段中键入相应内容直到显示所需标准为止，然后选择该标准，并单击**[!UICONTROL 完成]**。

   [!DNL Recommendations] 中提供了一些自带标准。您和您的团队也可以创建自己的自定义标准。

* 要创建新标准，请单击**[!UICONTROL 新建]**，然后填写有关新标准的信息。有关创建新标准的信息，请参阅[创建新标准](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)。

1. [创建新推荐](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)，或查找要为其设置标准的推荐，然后单击**[!UICONTROL 编辑]**。
1. 选择行业类型和页面类型。

* **行业类型：** 行业类型用于帮助分类 [!DNL Recommendations] 条件。要更改默认的垂直行业，请单击**[!UICONTROL 设置]**，然后选择所需的默认**垂直行业]设置。[!UICONTROL **
* **页面类型：**页面类型可帮助您对推荐进行分类。每种页面类型还有一些内置标准，可供您选择。
* **兼容：**仅显示要求选定页面传递所需数据的标准。并非每个标准都能在每个页面上正常运行。页面或 mbox 需要传入 `entity.id` 或 [!DNL entity.categoryId]，才能兼容当前项目/当前类别推荐。一般来说，最好只显示兼容的标准。但是，如果您希望不兼容的标准也可用于活动，请清除**[!UICONTROL 兼容]复选框。**可以在 [!DNL Target][!UICONTROL  的“首选项]”中禁用或启用此选项。

1. 单击**[!UICONTROL 添加]**。

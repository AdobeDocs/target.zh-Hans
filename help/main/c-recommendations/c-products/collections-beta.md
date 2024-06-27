---
keywords: 收藏集;定位
description: 了解如何在中使用产品或项目集合 [!DNL Target Recommendations].
title: 如何在Recommendations活动中使用收藏集？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: b6eaf89ef71ea3448584dcdadc926c45dba77504
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 29%

---

# 收藏集

收藏集是一组符合推荐标准的产品或项目。 集合的定义方式是指定作为集合一部分的项必须满足的条件。

一般情况下，收藏集是一组相似或相关的项目，例如单个产品收藏集。但是，您可以将任何项目分组到一个对您的业务有意义的类别中，例如可以将属于某个价格范围的产品分组到一个类别中，也可以将属于某个颜色的产品分组到一个类别中，或将可能在某个特定地理区域引起客户关注的项目分组到一个类别中。

使用收藏集，可将您的产品组织到逻辑分段中。例如，如果某些项目在一个区域可用，但在另一个区域不可用，您可以创建一个收藏集，以排除在访客所在区域不可用的项目。 您还可以使用收藏集来组织季节性项目，或使用任何其他对您的业务适用的组织参数。

[备用建议](/help/main/c-recommendations/c-algorithms/backup-recs.md) 为推荐中的每个标准生成的也会使用此收藏集，因此备用推荐中仅包含收藏集中的项目。 使用收藏集，您可以确保仅在某个位置显示对其有意义的产品。

每次运行各个标准时，都会重新构建或更新收藏集。

您可以将项目分组到不同的目录中，然后分别为每个收藏集创建单独的推荐。

包含标准与收藏集的功能类似，通过包含标准可以执行类似的操作，但不同的是您每次创建活动时都必须设置包含标准。收藏集允许您一次性创建一组项目，然后可以在适合时使用该收藏集，而无需再次设置。

创建或编辑 [!DNL Recommendations] 活动，收藏集名称将显示在 [!UICONTROL Criteria] 活动图上的标签。

>[!NOTE]
>
>使用时不应用收藏集 [!UICONTROL Recently Viewed Items] 推荐键。

## 创建收藏集 {#task_1256DFF6842141FCAADD9E1428EF7F08}

可创建收藏集以组织要在推荐中显示的产品或内容。

1. 单击 **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** 以显示现有收藏集的列表。

   ![收藏集列表](assets/collections-list.png)

   此 [!UICONTROL Collections] 页面显示现有收藏集的列表。 您可以通过单击 [!UICONTROL Create Collection] 按钮。 您还可以编辑、复制和删除现有收藏集，方法是单击所需收藏集旁边的省略号图标，然后单击所需选项。

   上每个收藏集报告的“项目数” [!UICONTROL Collections] list view是配置的默认Recommendations中与该收藏集的规则相匹配的产品数 [主机组](/help/main/administrating-target/hosts.md) （环境）。 请参阅 [设置](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} 更改默认主机组。

1. 单击 **[!UICONTROL Create Collection]**。

   ![创建收藏集](/help/main/c-recommendations/c-products/assets/create-collection.png)

1. 键入 **[!UICONTROL Name]** 用于收藏集。

   您还可以输入可选的 **[!UICONTROL Description]**.

1. （视情况而定）选择一个 [环境](/help/main/administrating-target/environments.md) 从 **[!UICONTROL Environment]** 在创建（或更新）收藏集时进行筛选，以预览该环境中收藏集的内容。 默认情况下，会显示默认主机组的结果。

1. 设置用于构建收藏集的规则。

   例如，您可以根据产品 ID 或类别、利润或列表中的任何其他参数来构建收藏集。

   您可以添加规则，以使用多个参数来定义收藏集。使用AND运算符连接多个规则。 必须匹配指定的所有规则，才能应用收藏集。

1. 单击 **[!UICONTROL Create]**。

## 使用以下方式创建收藏集 [!UICONTROL Advanced Search]

您还可以使用以下方式创建收藏集 [!UICONTROL Advanced Search] 在 [目录搜索](/help/main/c-recommendations/c-products/catalog-search.md#save-as) 页面([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search])。

![“另存为”对话框](/help/main/c-recommendations/c-products/assets/save-as.png)

例如，在使用“ID”>“包含”创建搜索后，您可以单击 [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>此 [!UICONTROL Advanced Search] 功能不区分大小写；但是，在交付时返回的产品基于区分大小写的搜索。 这种不匹配可能会导致产生混淆。在使用根据结果创建集合时，请确保考虑区分大小写 [!UICONTROL Advanced Search] 功能。 例如，如果您搜索“Holiday”，初始搜索会列出包含“Holiday”和“holiday”的结果。如果您随后创建一个目录，以用于返回包含“holiday”的产品，则只会返回包含“holiday”的产品，而不会返回包含“Holiday”的产品。

## 编辑、复制或删除收藏集

单击 **省略号** 图标，然后单击相应的图标：编辑、复制或删除。

![悬停图标：编辑、复制和删除](/help/main/c-recommendations/c-products/assets/hover-icons-new.png)

您可以复制现有收藏集以创建重复的收藏集，然后对其进行修改。 这样，您就可以用更少的工作量创建类似的收藏集。

请注意，收藏集可在整个帐户中使用。 确保在删除收藏集之前考虑这一点。 无法恢复已删除的收藏集。

## 在中使用收藏集 [!DNL Recommendations] 活动

1. 使用上述方法之一创建收藏集。

1. 单击 **[!UICONTROL Activities]** 和 [创建新的Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) 活动或编辑现有活动。

1. 选择标准和设计后， [!UICONTROL Options] 页面会在您选择所需收藏集的位置显示。

   ![选择收藏集选项](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. （视情况而定）要更改现有收藏集设置，请在 **[!UICONTROL Experiences]** 页面（三步引导式工作流的步骤2），单击放置推荐的位置，然后单击 **[!UICONTROL Change Collection]**，然后选择所需的收藏集。

   ![更改收藏集选项](/help/main/c-recommendations/c-products/assets/change-collection.png)

## 培训视频：在Recommendations中创建收藏集和排除项(7:05) ![教程徽章](/help/main/assets/tutorial.png)

本视频包含以下信息：

* 创建收藏集
* 创建排除项

>[!VIDEO](https://video.tv.adobe.com/v/27689)
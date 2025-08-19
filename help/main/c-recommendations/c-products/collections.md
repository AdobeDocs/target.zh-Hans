---
keywords: 收藏集;定位
description: 了解如何在 [!DNL Target Recommendations]中使用产品或项目的集合。
title: 如何在推荐活动中使用收藏集？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: be9cb6da17f125c127d64ed8f9002987188fdf3d
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 26%

---

# 收藏集

收藏集是一组符合推荐标准的产品或项目。 集合的定义方式是指定作为集合一部分的项必须满足的条件。

一般情况下，收藏集是一组相似或相关的项目，例如单个产品收藏集。但是，您可以将任何项目分组到一个对您的业务有意义的类别中，例如可以将属于某个价格范围的产品分组到一个类别中，也可以将属于某个颜色的产品分组到一个类别中，或将可能在某个特定地理区域引起客户关注的项目分组到一个类别中。

使用收藏集，可将您的产品组织到逻辑分段中。例如，如果某些项目在一个区域可用，但在另一个区域不可用，您可以创建一个收藏集，以排除在访客所在区域不可用的项目。 您还可以使用收藏集来组织季节性项目，或使用任何其他对您的业务适用的组织参数。

[为推荐中的每个标准生成的备用推荐](/help/main/c-recommendations/c-algorithms/backup-recs.md)也使用此收藏集，因此备用推荐中仅包含收藏集中的项目。 使用收藏集，您可以确保仅在某个位置显示对其有意义的产品。

每次运行各个标准时，都会重新构建或更新收藏集。

您可以将项目分组到不同的目录中，然后分别为每个收藏集创建单独的推荐。

包含标准与收藏集的功能类似，通过包含标准可以执行类似的操作，但不同的是您每次创建活动时都必须设置包含标准。收藏集允许您一次性创建一组项目，然后可以在适合时使用该收藏集，而无需再次设置。

创建或编辑[!DNL Recommendations]活动时，收藏集名称会显示在活动图上的[!UICONTROL Criteria]标签旁边。

>[!NOTE]
>
>* 收集规则适用于运行标准后生成的推荐项。 它们只影响输出中的实体推荐(ER)，而不影响键。
>
>* 使用[!UICONTROL Recently Viewed Items]推荐键时不会应用收藏集。

## 创建收藏集 {#task_1256DFF6842141FCAADD9E1428EF7F08}

可创建收藏集以组织要在推荐中显示的产品或内容。

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Collections]**&#x200B;以显示现有收藏集列表。

   [!UICONTROL Collections]页面显示现有收藏集的列表。 单击[!UICONTROL Create Collection]按钮可创建新收藏集。 您还可以编辑、复制和删除现有收藏集，方法是单击所需收藏集旁边的“更多操作”图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击所需选项。

   [!UICONTROL Collections]列表视图中为每个收藏集报告的“项目数”是指，在配置的默认“推荐”[主机组](/help/main/administrating-target/hosts.md)（环境）中与该收藏集的规则相匹配的产品数。 请参阅[设置](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}以更改默认主机组。

1. 单击 **[!UICONTROL Create Collection]**。

1. 为集合键入&#x200B;**[!UICONTROL Name]**。

   您还可以输入可选的&#x200B;**[!UICONTROL Description]**。

1. （视情况而定）在创建（或更新）收藏集时从[筛选器中选择](/help/main/administrating-target/environments.md)环境&#x200B;**[!UICONTROL Environment]**，以预览该环境中收藏集的内容。 默认情况下，会显示默认主机组的结果。

1. 设置用于构建收藏集的规则。

   例如，您可以根据产品 ID 或类别、利润或列表中的任何其他参数来构建收藏集。

   您可以添加规则，以使用多个参数来定义收藏集。使用AND运算符连接多个规则。 必须匹配指定的所有规则，才能应用收藏集。

1. 单击 **[!UICONTROL Create]**。

<!-- ## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. -->

## 编辑、复制或删除收藏集

单击列表中所需集合旁边的（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击相应的图标： [!UICONTROL Edit]、[!UICONTROL Copy]或[!DNL Delete]。

您可以复制现有收藏集以创建重复的收藏集，然后对其进行修改。 这样，您就可以用更少的工作量创建类似的收藏集。

请注意，收藏集可在整个帐户中使用。 确保在删除收藏集之前考虑这一点。 无法恢复已删除的收藏集。

## 在[!DNL Recommendations]活动中使用收藏集

1. 使用上述方法之一创建收藏集。

1. 单击&#x200B;**[!UICONTROL Activities]**&#x200B;并[创建新的推荐](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)活动或编辑现有活动。

1. 选择标准和设计后，将显示[!UICONTROL Options]页面，您可以在其中选择所需的集合。

1. （视情况而定）要更改现有的收藏集设置，请在&#x200B;**[!UICONTROL Experiences]**&#x200B;页面（三步引导式工作流的步骤1）中单击放置推荐的位置，单击&#x200B;**[!UICONTROL Change Collection]**，然后选择所需的收藏集。

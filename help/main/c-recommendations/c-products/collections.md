---
keywords: 收藏集;定位
description: 了解如何在 [!DNL Target Recommendations]中使用产品或项目的集合。
title: 如何在Recommendations活动中使用收藏集？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: c8bd2bb45ee8ef1a849fd9091554caec77effba0
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 40%

---

# 收藏集

收藏集是一组符合推荐标准的产品或项目。 集合的定义方式是指定作为集合一部分的项必须满足的条件。

一般情况下，收藏集是一组相似或相关的项目，例如单个产品收藏集。但是，您可以将任何项目分组到一个对您的业务有意义的类别中，例如可以将属于某个价格范围的产品分组到一个类别中，也可以将属于某个颜色的产品分组到一个类别中，或将可能在某个特定地理区域引起客户关注的项目分组到一个类别中。

使用收藏集，可将您的产品组织到逻辑分段中。例如，如果某些项目在一个区域可用，但在另一个区域不可用，您可以创建一个收藏集，以排除在访客所在区域不可用的项目。 您还可以使用收藏集来组织季节性项目，或使用任何其他对您的业务适用的组织参数。

为推荐中的每个标准生成的[备用推荐](/help/main/c-recommendations/c-algorithms/backup-recs.md)也使用该收藏集，因此备用推荐中仅包含收藏集中的项目。使用收藏集，您可以确保仅在某个位置显示对其有意义的产品。

每次运行各个标准时，都会重新构建或更新收藏集。

您可以将项目分组到不同的目录中，然后分别为每个收藏集创建单独的推荐。

包含标准与收藏集的功能类似，通过包含标准可以执行类似的操作，但不同的是您每次创建活动时都必须设置包含标准。而收藏集允许您一次性创建一组项目，之后不论何时需要使用这些项目，都可以直接使用，而无需再次设置。

创建或编辑[!DNL Recommendations]活动时，收藏集名称会显示在活动图上的[!UICONTROL Criteria]标签旁边。

>[!NOTE]
>
>使用[!UICONTROL Recently Viewed Items]推荐键时不会应用收藏集。

## 创建收藏集 {#task_1256DFF6842141FCAADD9E1428EF7F08}

可创建收藏集以组织要在推荐中显示的产品或内容。

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Collections]**&#x200B;以显示现有收藏集列表。

   ![收藏集列表](assets/collections_list.png)

   [!UICONTROL Collections]页面显示现有收藏集的列表。 单击[!UICONTROL Create Collection]按钮可创建新收藏集。 您还可以编辑、复制和删除现有收藏集，方法是将鼠标悬停在所需收藏集上，然后单击所需图标。

   ![悬停图标：编辑、复制和删除](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   [!UICONTROL Collections]列表视图中为每个收藏集报告的“项目数”是指，在配置的默认Recommendations [主机组](/help/main/administrating-target/hosts.md)（环境）中与该收藏集的规则相匹配的产品数。 请参阅[设置](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}以更改默认主机组。

1. 单击 **[!UICONTROL Create Collection]**。

1. （视情况而定）在创建（或更新）收藏集时从&#x200B;**[!UICONTROL Environment]**&#x200B;筛选器中选择一个环境，以预览该环境中收藏集的内容。 默认情况下，会显示默认主机组的结果。

   ![创建收藏集](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. 为集合键入&#x200B;**[!UICONTROL Name]**。

   您还可以输入可选的&#x200B;**[!UICONTROL Description]**。

1. 设置用于构建收藏集的规则。

   例如，您可以根据产品 ID 或类别、利润或列表中的任何其他参数来构建收藏集。

   您可以添加规则，以使用多个参数来定义收藏集。使用AND运算符连接多个规则。 必须匹配指定的所有规则，才能应用收藏集。

1. 单击 **[!UICONTROL Save]**。

## 使用高级搜索创建收藏集

您还可以使用[目录搜索](/help/main/c-recommendations/c-products/catalog-search.md#save-as)页面上的“高级搜索”([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search])来创建收藏集。

![另存为对话框](/help/main/c-recommendations/c-products/assets/save-as.png)

例如，在使用“ID”>“包含”创建搜索后，您可以单击[!UICONTROL Save As] > [!UICONTROL Collection]。

>[!IMPORTANT]
>
>“高级搜索”功能不区分大小写；但在进行产品交付时，会根据区分大小写的搜索来返回产品。这种不匹配可能会导致产生混淆。因此，在基于使用“高级搜索”功能搜索到的结果创建收藏集时，请务必考虑大小写问题。例如，如果您搜索“Holiday”，初始搜索会列出包含“Holiday”和“holiday”的结果。如果您随后创建一个目录，以用于返回包含“holiday”的产品，则只会返回包含“holiday”的产品，而不会返回包含“Holiday”的产品。

## 编辑、复制或删除收藏集

将鼠标悬停在列表中所需的收藏集上，然后单击相应的图标：编辑、复制或删除。

收藏集的![悬停图标](/help/main/c-recommendations/c-products/assets/hover-collections.png)

您可以复制现有收藏集以创建重复的收藏集，然后对其进行修改。 这样，您就可以用更少的工作量创建类似的排除项。

请注意，收藏集可在整个帐户中使用。 确保在删除收藏集之前考虑这一点。 无法恢复已删除的收藏集。

## 在Recommendations活动中使用收藏集

1. 使用上述方法之一创建收藏集。

1. 单击&#x200B;**[!UICONTROL Activities]**&#x200B;和[创建新的Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)活动或编辑现有活动。

1. 选择标准和设计后，在选择所需收藏集时显示[!UICONTROL Options]页面。

   ![选择收藏集选项](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. （视情况而定）要更改现有的收藏集设置，请在&#x200B;**[!UICONTROL Experiences]**&#x200B;页面（三步引导式工作流的步骤2）中单击放置推荐的位置，单击&#x200B;**[!UICONTROL Change Collection]**，然后选择所需的收藏集。

   ![更改收藏集选项](/help/main/c-recommendations/c-products/assets/change-collection.png)

## 培训视频：在Recommendations中创建收藏集和排除项(7:05) ![教程徽章](/help/main/assets/tutorial.png)

本视频包含以下信息：

* 创建收藏集
* 创建排除项

>[!VIDEO](https://video.tv.adobe.com/v/27689)

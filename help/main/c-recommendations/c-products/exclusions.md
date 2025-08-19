---
keywords: 排除项
description: 了解如何在 [!DNL Target Recommendations] 中创建排除项以防止向访客推荐产品或内容。
title: 如何在[!UICONTROL Recommendations]活动中使用排除项？
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 14%

---

# 排除项

在[!DNL Adobe Target Recommendations]中创建排除项以阻止向访客推荐产品或内容。 排除项是不向访客推荐的产品或内容的子集。

排除项可在整个帐户中使用。 与收藏集（在创建[!UICONTROL Recommendations]活动时为每个体验指定特定收藏集）不同，排除项适用于帐户中的所有活动。 在活动创建期间没有用于分配排除组的选项。

您可以使用排除项的一些次数示例包括：

* 已停产的产品。
* 秋冬目录现在是唯一应该在线显示的目录。 Summer目录中的任何项目不再可供购买。
* 可能不适宜在大多数页面或屏幕上推荐的项目（成人产品、NC-17电影等）。
* 元数据字段不完整的产品（缺少缩略图、价格或其他重要元数据）。
* 绝不应该推荐的产品(可能系统中存在某个项目的SKU，但它不是可购买的项目。 或者可能是QA团队模拟购买而不实际订购某些东西的虚假SKU，等等)。

>[!IMPORTANT]
>
>排除规则已全局应用于所有[环境](/help/main/administrating-target/environments.md)。
>
>静态和动态排除规则是可帮助您完成营销工作的强大功能。有关详细信息、示例和用例情景，请参阅[使用动态和静态包含规则](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)。

## 创建排除项

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]**&#x200B;以显示现有排除项列表。

   [!UICONTROL Exclusions]列表视图中为每个排除项报告的“项目数”是指，在配置的默认“推荐”[主机组](/help/main/administrating-target/hosts.md)（环境）中与该排除项规则相匹配的产品数。 有关如何更改默认主机组的信息，请参阅[Adobe Target开发人员指南 [!DNL Recommendations]中的](https://experienceleague.adobe.com/en/docs/target-dev/developer/recommendations){target=_blank}计划和实施&#x200B;**。

1. （视情况而定）单击&#x200B;**[!UICONTROL Show Filters]**&#x200B;图标（![显示过滤器图标](/help/main/assets/icons/Filter.svg)），然后在创建（或更新）排除项时从[下拉列表中选择所需的](/help/main/administrating-target/environments.md)环境&#x200B;**[!UICONTROL Environment]**，以预览该环境中排除项的内容。 默认情况下，会显示默认主机组的结果。

1. 单击 **[!UICONTROL Create Exclusion]**。

1. 键入排除项&#x200B;**[!UICONTROL Name]**&#x200B;并输入可选描述。

1. 使用规则生成器创建排除项。

   在[!UICONTROL Rules]列表中选择一个参数，选择一个运算符，然后输入一个或多个值以标识产品。 使用逗号分隔多个值。

1. 单击 **[!UICONTROL Create]**。

<!-- ## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded. -->

## 编辑、复制或删除排除项

单击列表中所需排除项旁边的更多操作图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击相应的图标： [!UICONTROL Edit]、[!UICONTROL Copy]或[!UICONTROL Delete]。

您可以复制现有排除项以创建重复排除项，然后对其进行修改。 利用此选项，您可以用更少的工作量创建类似的排除项。

请注意，排除项可在整个帐户中使用。 确保在删除排除项之前考虑此注意事项。 无法恢复已删除的排除项。

## 培训视频：在“推荐” (7:05) ![教程徽章](/help/main/assets/tutorial.png)中创建收藏集和排除项

本视频包含以下信息：

* 创建收藏集
* 创建排除项

>[!VIDEO](https://video.tv.adobe.com/v/27689)

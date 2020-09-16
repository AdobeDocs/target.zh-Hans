---
keywords: exclusions
description: 创建排除， [!DNL Adobe Target Recommendations] 防止向访客推荐产品或内容。
title: Adobe Target 中的排除项
feature: entities
uuid: 1970846e-37d8-4b69-a0d9-ff45bb840bef
translation-type: tm+mt
source-git-commit: 28e97c03e21df246e208588d507d4af8d3695283
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 45%

---


# 排除项{#exclusions}

在中创建排除 [!DNL Adobe Target Recommendations] 功能，防止向访客推荐产品或内容。 排除是不应推荐给访客的产品或内容的子集。

可在整个帐户中使用排除。 与在创建Recommendations活动时为每个体验指定特定集合的集合不同  ，排除将应用于帐户中的所有活动。 在创建活动时，没有指定排除组的选项。

使用排除的一些示例包括：

* 已停用的产品
* 秋季／冬季目录现在是唯一应在线提供的目录。 Summer目录中的任何物品不再可供购买。
* 在大多数页面／屏幕（成人产品、NC-17电影等）上可能不宜推荐的项目
* 元数据字段不完整（缺少缩略图、价格或其他重要元数据）的产品
* 不应推荐的产品（可能系统中存在某些物品的SKU，但它不是可购买的物品，或者QA团队模拟购买而不实际订购物品的假SKU，等等）

>[!IMPORTANT]
>
>静态和动态排除规则是可帮助您完成营销工作的强大功能。有关详细信息、示例和用例情景，请参阅[使用动态和静态包含规则](../../c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)。

## 创建排除项

1. 单击&#x200B;**[!UICONTROL 推荐]** > **[!UICONTROL 排除项]**&#x200B;以显示现有排除项列表。

   ![](assets/exclusions_list.png)

   [!UICONTROL 排除项]列表视图中为每个排除项报告的“项目数”是指，在配置的默认“推荐”[主机组](/help/administrating-target/hosts.md)（环境）中与该排除项规则相匹配的产品数。请参阅[设置](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)以更改默认主机组。

1. 单击&#x200B;**[!UICONTROL 创建排除项]**。

1. （视情况而定）在创建（或更新）排除项时从&#x200B;**[!UICONTROL 环境]**&#x200B;筛选器中选择一个环境，以预览该环境中排除项的内容。默认情况下，会显示默认主机组的结果。

   ![创建排除项](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. 键入排除项&#x200B;**[!UICONTROL 名称]**，并输入可选描述。

1. 使用规则生成器创建排除项。

   在“规则”列表中选择一个参数，选择一个运算符，然后输入一个或多个值以标识产品。使用逗号分隔多个值。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 使用高级搜索创建排除项

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![另存为对话框](/help/c-recommendations/c-products/assets/save-as.png)

例如，在使用“ID”>“包含”创建搜索后，您可以单击“[!UICONTROL 另存为]”>“[!UICONTROL 排除项]”。

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. 这种不匹配可能会导致产生混淆。因此，在基于使用“高级搜索”功能搜索到的结果创建排除项时，请务必考虑大小写问题。例如，如果您搜索“Holiday”，初始搜索会列出包含“Holiday”和“holiday”的结果。如果您随后创建一个排除项，以用于排除包含“holiday”的产品，则只会排除包含“holiday”的产品，而不会排除包含“Holiday”的产品。

## 编辑、复制或删除排除项

将指针悬停在列表中所需的排除项上，然后单击相应的图标：编辑、复制或删除。

![排除项的悬停图标](/help/c-recommendations/c-products/assets/hover-exclusions.png)

您可以复制现有排除，以创建重复排除，然后可以修改该排除。 这样，您可以更轻松地创建类似的排除。

请注意，整个帐户中都有排除项。 请确保在删除排除之前考虑这一点。 无法恢复已删除的排除。

## Training video: Create collections and exclusions in Recommendations (7:05) ![Tutorial badge](/help/assets/tutorial.png)

本视频包含以下信息：

* 创建收藏集
* 创建排除项

>[!VIDEO](https://video.tv.adobe.com/v/27689)
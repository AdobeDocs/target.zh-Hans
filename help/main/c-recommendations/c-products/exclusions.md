---
keywords: 排除项
description: 了解如何在[!DNL Target Recommendations]中创建排除项以防止向访客推荐产品或内容。
title: 如何在[!UICONTROL 推荐]活动中使用排除项？
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
TQID: 'https://experienceleague.adobe.com/6-PWkqq5eXAwyLcGGbSqSZmFdJa85yU3x7FPNEt8-2o'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%
---
# 排除项 {#exclusions}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在[!DNL Adobe Target Recommendations]中创建和管理排除项以防止向访客推荐产品或内容。

>[!ENDSHADEBOX]

排除项是不向访客推荐的产品或内容的子集。 排除项可在整个帐户中使用。 与创建[!DNL Recommendations]活动时为每个体验选择的收藏集不同，排除项适用于帐户中的所有活动，并且在活动创建期间不能分配排除组。

排除项通常用于：

* 已停产的产品。
* 目录中不再可用的项目。 例如，当只有秋季和冬季目录应在线显示时，夏季目录中的任何项目都不能购买。
* 可能不适宜在大多数页面或屏幕上推荐的项目（成人产品、NC-17电影等）。
* 元数据字段不完整的产品（缺少缩略图、价格或其他重要元数据）。
* 绝不应该推荐的产品，例如系统中存在但不是可购买项目的SKU，或QA团队用于模拟购买而不订购任何内容的虚假SKU。

>[!IMPORTANT]
>
>排除规则已全局应用于所有[环境](/help/main/administrating-target/environments.md)。
>
>有关静态和动态排除规则的详细信息、示例和用例方案，请参阅[使用动态和静态包含规则](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules)。

## 创建排除项

排除规则定义一次，然后应用于帐户中的每个[!DNL Recommendations]活动。

1. 单击&#x200B;**[!UICONTROL 推荐]** > **[!UICONTROL 排除项]**&#x200B;以显示现有排除项列表。

   >[!NOTE]
   >
   >**[!UICONTROL 排除项]**&#x200B;列表视图中为每个排除项报告的“项目数”是指，在配置的默认“推荐”[主机组](/help/main/administrating-target/hosts.md)（环境）中与该排除项规则相匹配的产品数。 有关如何更改默认主机组的信息，请参阅&#x200B;*Adobe Target开发人员指南*&#x200B;中的[计划和实施 [!DNL Recommendations]](https://experienceleague.adobe.com/zh-hans/docs/target-dev/developer/recommendations){target=_blank}。


1. 单击&#x200B;**[!UICONTROL 显示筛选器]**&#x200B;图标（![显示筛选器图标](/help/main/assets/icons/Filter.svg)），然后从&#x200B;**[!UICONTROL 环境]**&#x200B;下拉列表中选择所需的[环境](/help/main/administrating-target/environments.md)，以预览该环境中排除项的内容。 默认情况下，会显示默认主机组的结果。

   打开“筛选器”面板和“环境”列表的![排除项页面](../assets/exclusions_2.png)

1. 单击&#x200B;**[!UICONTROL 创建排除项]**。

   使用“创建排除项”按钮的![排除项页面](../assets/exclusions_1.png)

1. 键入排除项&#x200B;**[!UICONTROL 名称]**。 也可以输入可选描述。

1. 使用规则生成器定义排除项。

   在&#x200B;**[!UICONTROL 规则]**&#x200B;列表中Select参数，选择一个运算符，然后输入一个或多个值以标识产品。 使用逗号分隔多个值。

1. 单击&#x200B;**[!UICONTROL 创建]**。

1. 单击列表中所需排除项旁边的更多操作图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击相应的选项： **[!UICONTROL 编辑]**、**[!UICONTROL 复制]**&#x200B;或&#x200B;**[!UICONTROL 删除]**。

   ![排除项列表，“更多操作”菜单处于打开状态，显示“编辑”、“复制”和“删除”](../assets/exclusions_3.png)

<!--
## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded.
-->


## 培训视频：在“推荐”(7:05) ![教程徽章](/help/main/assets/tutorial.png)中创建收藏集和排除项

本视频包含以下信息：

* 创建收藏集
* 创建排除项

>[!VIDEO](https://video.tv.adobe.com/v/35356?captions=chi_hans)

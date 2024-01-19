---
keywords: 排除项
description: 了解如何在Adobe中创建排除项 [!DNL Target] Recommendations ，以防止向访客推荐产品或内容。
title: 如何在Recommendations活动中使用排除项？
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 34%

---

# 排除项

在中创建排除项 [!DNL Adobe Target Recommendations] 防止向访客推荐产品或内容。 排除项是不向访客推荐的产品或内容的子集。

排除项可在整个帐户中使用。 与收藏集不同，收藏集可在创建体验时为每个体验指定特定的收藏集 [!UICONTROL Recommendations] 活动，排除项适用于帐户中的所有活动。 在活动创建期间没有用于分配排除组的选项。

您可以使用排除项的一些次数示例包括：

* 已停产的产品
* 秋/冬目录现在是唯一应在线显示的目录。 Summer目录中的任何项目不再可供购买。
* 可能不宜在大多数页面/屏幕上推荐的项目（成人产品、NC-17电影等）
* 元数据字段不完整的产品（缺少缩略图、价格或其他重要元数据）
* 绝不应该推荐的产品（可能系统中存在某个产品的SKU，但它不是可购买的项目，或者可能它是一个假SKU，供QA团队模拟购买而不实际订购某些产品，等等）

>[!IMPORTANT]
>
>排除规则可全局应用于所有环境。
>
>静态和动态排除规则是可帮助您完成营销工作的强大功能。有关详细信息、示例和用例情景，请参阅[使用动态和静态包含规则](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)。

## 创建排除项

1. 单击 **[!UICONTROL Recommendations]** > **[!UICONTROL 排除项]** 以显示现有排除项的列表。

   ![exclusions_list图像](assets/exclusions_list.png)

   [!UICONTROL 排除项]列表视图中为每个排除项报告的“项目数”是指，在配置的默认“推荐”[主机组](/help/main/administrating-target/hosts.md)（环境）中与该排除项规则相匹配的产品数。请参阅 [设置](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} 更改默认主机组。

1. 单击 **[!UICONTROL 创建排除项]**.

1. （视情况而定）从 **[!UICONTROL 环境]** 在创建（或更新）排除项时进行筛选，以预览该环境中排除项的内容。 默认情况下，会显示默认主机组的结果。

   ![创建排除项](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. 键入排除项 **[!UICONTROL 名称]** 并输入可选说明。

1. 使用规则生成器创建排除项。

   在“规则”列表中选择一个参数，选择一个运算符，然后输入一个或多个值以标识产品。使用逗号分隔多个值。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 使用高级搜索创建排除项

您还可以使用以下方式创建排除项 [!UICONTROL 高级搜索] 在 [目录搜索](/help/main/c-recommendations/c-products/catalog-search.md#save-as) 页面( [!UICONTROL Recommendations] > [!UICONTROL 目录搜索] > [!UICONTROL 高级搜索])。

![“另存为”对话框](/help/main/c-recommendations/c-products/assets/save-as.png)

例如，在使用“ID”>“包含”创建搜索后，您可以单击“[!UICONTROL 另存为]”>“[!UICONTROL 排除项]”。

>[!IMPORTANT]
>
>此 [!UICONTROL 高级搜索] 功能不区分大小写；但是，在交付时返回的产品基于区分大小写的搜索。 这种不匹配可能会导致产生混淆。因此，在基于使用“高级搜索”功能搜索到的结果创建排除项时，请务必考虑大小写问题。例如，如果您搜索“Holiday”，初始搜索会列出包含“Holiday”和“holiday”的结果。如果您随后创建一个排除项，以用于排除包含“holiday”的产品，则只会排除包含“holiday”的产品，而不会排除包含“Holiday”的产品。

## 编辑、复制或删除排除项

将鼠标悬停在列表中所需的排除项上，然后单击相应的图标：编辑、复制或删除。

![将鼠标悬停在排除项图标上](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

您可以复制现有排除项以创建重复排除项，然后对其进行修改。 这样，您就可以用更少的工作量创建类似的排除项。

请注意，排除项可在整个帐户中使用。 确保在删除排除项之前考虑这一点。 无法恢复已删除的排除项。

## 培训视频：在Recommendations中创建收藏集和排除项(7:05) ![教程徽章](/help/main/assets/tutorial.png)

本视频包含以下信息：

* 创建收藏集
* 创建排除项

>[!VIDEO](https://video.tv.adobe.com/v/27689)

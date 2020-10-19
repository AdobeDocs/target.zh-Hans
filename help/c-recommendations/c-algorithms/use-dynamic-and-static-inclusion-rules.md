---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: 有关在Adobe TargetRecommendations创建包含规则以获取标准和促销信息，以及添加其他动态或静态过滤规则以获得更好效果的信息。
title: 在Adobe TargetRecommendations使用动态和静态包含规则
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 45%

---


# ![PREMIUM](/help/assets/premium.png) 使用动态和静态包含规则{#use-dynamic-and-static-inclusion-rules}

Information about creating inclusion rules for criteria and promotions in [!DNL Adobe Target] and adding additional dynamic or static filtering rules to achieve better results for your recommendations.

如用例和示例所述，针对标准和促销活动创建和使用包含规则的过程类似。本节将介绍标准和促销以及包含规则的使用。

## 将筛选规则添加到标准 {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[创建标准](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)时，单击&#x200B;**[!UICONTROL 包含规则]**&#x200B;下的&#x200B;**[!UICONTROL 添加筛选规则]**。

![](assets/inclusion_options_new.png)

可用选项取决于所选垂直行业和推荐键。

## 将筛选规则添加到促销活动 {#section_D59AFB62E2EE423086281CF5D18B1076}

[创建促销活动](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)时，选择&#x200B;**[!UICONTROL 按属性促销]**，然后单击&#x200B;**[!UICONTROL 添加筛选规则]**。

![](assets/inclusion_options.png)

## 筛选类型 {#section_0125F1ED10A84C0EB45325122460EBCD}

以下部分列表了标准和促销、动态筛选和按值筛选选项的类型：

### 动态筛选

动态包含规则比静态包含规则更强大，并且产生更好的结果和参与度。 请考虑以下事项：

* 动态包含规则通过匹配用户用户档案参数或mbox调用中的属性来提供推荐。

   例如，您可以创建“最受欢迎的标准”推荐，然后根据用户访问显示推荐的页面时传递的属性，实时筛选返回的推荐集中的任意推荐。

* 使用静态规则限制推荐中包含的项目（而非集合）。

* 您可以根据需要创建任意数量的动态包含规则。 包含规则使用“与”运算符进行结合。所有规则都必须得到满足，才能在推荐中包含某个项目。

以下选项可用于动态筛选：

| 动态筛选选项 | 详细信息 |
| --- | --- |
| [实体属性匹配](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | 通过将潜在推荐项目池与用户已交互的特定项目进行比较，动态筛选。<br>如果您希望显示最有可能吸引访客的推荐(如访客喜爱的品牌)，请使用“实体属性匹配”。 |
| [配置文件属性匹配](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | 通过比较项目（实体）与用户用户档案中的值来动态筛选。<br>如  果要显示与访客用户档案中存储的值（如大小或喜爱的品牌）匹配的推荐，请使用用户档案属性匹配。 |
| [参数匹配](/help/c-recommendations/c-algorithms/parameter-matching.md) | 通过比较项（实体）与请求（API或mbox）中的值来动态筛选。<br>使用参数匹配可推荐与页面参数或访客参数（如设备尺寸或地理位置）匹配的内容。 |

### 按值筛选

以下选项可用于按值筛选：

| 按值筛选选项 | 详细信息 |
| --- | --- |
| [静态滤镜](/help/c-recommendations/c-algorithms/static-value.md) | 手动输入一个或多个静态值以进行筛选。 |

## 动态标准和促销示例

动态标准和促销活动比静态标准和促销活动更强大，可产生更好的结果和参与度。

以下示例将为您提供有关如何在营销工作中使用动态促销的一般信息：

### 等于

在动态促销中使用“等于”运算符，当访客在您的网站（如产品、文章或电影）上查看项目时，您可以从以下位置提升其他项目：

* 同一品牌
* 同一类别
* 同一类别和同一厂商
* 同一商店

### 不等于

在动态促销中使用“不等于”运算符，当访客在您的网站（如产品、文章或电影）上查看项目时，您可以从以下位置提升其他项目：

* 不同的电视连续剧
* 不同的类别
* 不同的产品系列
* 不同的风格 ID

### 介于

在动态促销中使用“介于”运算符，当访客在您的网站（如产品、文章或电影）上查看项目时，您可以提升以下项目：

* 更贵
* 更便宜
* 费用高或低 30%
* 同一季的后续集数
* 一套书中之前出版的书

## Handling empty values when filtering by Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching {#section_7D30E04116DB47BEA6FF840A3424A4C8}

You can choose several options to handle empty values when filtering by [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching] for exit criteria and promotions.

以前，如果值为空，则不会返回任何结果。如果标准包含空值，则“如果 *x* 为空”下拉列表允许您选择适当的操作，如下图所示：

![](assets/empty_value.png)

要选择所需的操作，请将鼠标悬停在齿轮图标 (![](assets/icon_gear.png)) 上，然后选择所需的操作：

| 操作 | 适用选项 | 详细信息 |
|--- |--- |--- |
| 忽略此筛选规则 | 配置文件属性匹配<br>参数匹配 | 这是“配置文件属性匹配”和“参数匹配”的默认操作。<br>该选项指定忽略该规则。例如，如果有三个筛选规则，第三个规则不传递任何值，则您只需忽略具有空值的第三个规则，而不是不返回任何结果。 |
| 不提升任何项目 | 实体属性匹<br>配配置文件属<br>性匹配参数匹配 | 这是“实体属性匹配”的默认操作。<br>[!DNL Target]此操作是 在添加此选项之前处理空值的方式：不显示此标准的结果。 |
| 使用静态值 | 实体属性匹配<br>配置文件属性匹配<br>参数匹配 | 如果值为空，您可以选择使用静态值。 |

## 注意事项 {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>在运行时，不同的数据类型属性可能在动态标准或促销活动中与“等于”和“不等于”运算符不兼容。You should use [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory], and [!UICONTROL Environment] values wisely on the right hand side if the left hand side has predefined attributes or custom attributes.

![](assets/left_right.png)

下表显示了有效规则和在运行时可能不兼容的规则：

| 兼容规则 | 可能不兼容的规则 |
|--- |--- |
| value - 介于 - 当前项目的 90% 至 110% - salesValue | salesValue - 介于 - 当前项目的 90% 至 110% - value |
| value - 介于 - 当前项目的 90% 至 110% - value | clearancePrice - 介于 - 当前项目的 90% 至 110% - margin |
| margin - 介于 - 当前项目的 90% 至 110% - margin | storeInventory - 等于 - 当前项目的 - inventory |
| inventory - 等于 - 当前项目的 - inventory |  |

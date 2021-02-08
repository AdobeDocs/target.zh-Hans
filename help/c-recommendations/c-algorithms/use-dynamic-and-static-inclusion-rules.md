---
keywords: 包含规则;包含标准;推荐;新建标准;促销活动;动态筛选;动态;空值;忽略筛选规则;静态筛选器;按值筛选;实体属性匹配;配置文件属性匹配;参数匹配;按值筛选;静态筛选器
description: 了解如何在Adobe TargetRecommendations创建标准和促销的包含规则。 添加其他动态或静态过滤规则以获得更好的效果。
title: 如何在Recommendations使用动态和静态包含规则？
feature: Recommendations
mini-toc-levels: 3
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1099'
ht-degree: 41%

---


# ![PREMIUM](/help/assets/premium.png) 使用动态和静态包含规则{#use-dynamic-and-static-inclusion-rules}

有关在[!DNL Adobe Target]中为条件和促销创建包含规则以及添加其他动态或静态筛选规则以更好地实现推荐的信息。

>[!NOTE]
>
>如用例和示例所述，针对标准和促销活动创建和使用包含规则的过程类似。本节将介绍标准和促销以及包含规则的使用。

## 将筛选规则添加到标准 {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[创建标准](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)时，单击&#x200B;**[!UICONTROL 包含规则]**&#x200B;下的&#x200B;**[!UICONTROL 添加筛选规则]**。

![](assets/inclusion_options_new.png)

可用选项取决于所选垂直行业和推荐键。

## 将筛选规则添加到促销活动 {#section_D59AFB62E2EE423086281CF5D18B1076}

[创建促销活动](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)时，选择&#x200B;**[!UICONTROL 按属性促销]**，然后单击&#x200B;**[!UICONTROL 添加筛选规则]**。

![](assets/inclusion_options.png)

## 筛选类型 {#section_0125F1ED10A84C0EB45325122460EBCD}

以下各节列表了[!UICONTROL 动态筛选]和[!UICONTROL 按值筛选]的筛选选项类型，包括条件和促销：

### 动态筛选

动态包含规则比静态包含规则更强大，并且产生更好的结果和参与度。 请考虑以下事项：

* 动态包含规则通过匹配用户用户档案参数或mbox调用中的属性来提供推荐。

   例如，您可以创建“最受欢迎的标准”推荐，然后创建返回的推荐集，然后根据用户访问显示推荐的页面时通过的属性过滤出任何推荐（实时）。

* 使用静态规则限制推荐中包含的项目（而不是使用集合）。

* 您可以根据需要创建任意数量的动态包含规则。 包含规则使用“与”运算符进行结合。所有规则都必须得到满足，才能在推荐中包含某个项目。

以下选项可用于动态筛选：

| 动态筛选选项 | 详细信息 |
| --- | --- |
| [实体属性匹配](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | 通过将潜在推荐项目池与用户已交互的特定项目进行比较，动态筛选。<br>当您 [!UICONTROL 希望显] 示最有可能吸引访客(如访客喜爱的品牌)的推荐时，请使用实体属性匹配。 |
| [配置文件属性匹配](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | 通过比较项目（实体）与用户用户档案中的值来动态筛选。<br>如果 [!UICONTROL 要显] 示与用户档案用户档案中存储的值（如大小或喜爱的品牌）匹配的推荐，请使用访客属性匹配。 |
| [参数匹配](/help/c-recommendations/c-algorithms/parameter-matching.md) | 通过比较项（实体）与请求（API或mbox）中的值来动态筛选。<br>使用 [!UICONTROL 参] 数匹配可推荐与页面参数或访客的参数（如设备尺寸或地理位置）匹配的内容。 |

### 按值筛选

以下选项可用于按值筛选：

| 按值筛选选项 | 详细信息 |
| --- | --- |
| [静态滤镜](/help/c-recommendations/c-algorithms/static-value.md) | 手动输入一个或多个静态值以进行筛选。 |

## 动态标准和促销示例

动态标准和促销比静态标准和促销更加强大，并产生更好的结果和参与度。

以下示例提供了有关如何在营销工作中使用动态促销的一般思路：

| 运算符 | 示例 |
| --- | --- |
| 等于 | 在动态促销中使用“等于”运算符，当访客在您的网站（如产品、文章或电影）上查看项目时，您可以从以下位置提升其他项目：<ul><li>同一品牌</li><li>同一类别</li><li>同一类别和同一厂商</li><li>同一商店</li></ul> |
| 不等于 | 在动态促销中使用“不等于”运算符，当访客在您的网站（如产品、文章或电影）上查看项目时，您可以从以下位置提升其他项目：<ul><li>不同的电视连续剧</li><li>不同的类别</li><li>不同的产品系列</li><li>不同的风格 ID</li></ul> |
| 介于 | 在动态促销中使用“介于”运算符，当访客在您的网站（如产品、文章或电影）上查看项目时，您可以提升以下项目：<ul><li>更贵</li><li>更便宜</li><li>费用高或低 30%</li><li>同一季的后续集数</li><li>一套书中之前出版的书</li></ul> |

## 按实体属性匹配、用户档案属性匹配和参数匹配{#section_7D30E04116DB47BEA6FF840A3424A4C8}筛选时处理空值

通过[!UICONTROL 实体属性匹配]、[!UICONTROL 用户档案属性匹配]和[!UICONTROL 参数匹配]筛选退出条件和促销时，可以选择多个选项来处理空值。

以前，如果值为空，则不会返回任何结果。如果标准包含空值，则“如果 *x* 为空”下拉列表允许您选择适当的操作，如下图所示：

![](assets/empty_value.png)

要选择所需的操作，请将鼠标悬停在齿轮图标 (![](assets/icon_gear.png)) 上，然后选择所需的操作：

| 操作 | 适用选项 | 详细信息 |
|--- |--- |--- |
| [!UICONTROL 忽略此筛选规则] | [!UICONTROL 用户档案属性] [!UICONTROL 匹配与参数匹配] | 这是[!UICONTROL 用户档案属性匹配]和[!UICONTROL 参数匹配]的默认操作。<br>该选项指定忽略该规则。例如，如果有三个筛选规则，第三个规则不传递任何值，则您只需忽略具有空值的第三个规则，而不是不返回任何结果。 |
| [!UICONTROL 不显示此条件的任何结果]<br>（仅限条件） | [!UICONTROL 实体属性匹配]、 [!UICONTROL 用户档案属性匹配]、参 [!UICONTROL 数匹配] | 这是[!UICONTROL 实体属性匹配]的默认操作。<br>[!DNL Target]此操作是 在添加此选项之前处理空值的方式：不显示此标准的结果。 |
| [!UICONTROL 不提升任何项目<br>（仅限促销）] | [!UICONTROL 实体属性匹配]、 [!UICONTROL 用户档案属性匹配]、参 [!UICONTROL 数匹配] | 这是[!UICONTROL 实体属性匹配]的默认操作。<br>[!DNL Target]此操作是 在添加此选项之前处理空值的方式：不显示此标准的结果。 |
| [!UICONTROL 使用静态值] | [!UICONTROL 实体属性匹配]、 [!UICONTROL 用户档案属性匹配]、参 [!UICONTROL 数匹配] | 如果值为空，您可以选择使用静态值。 |

## 注意事项 {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>在运行时，不同的数据类型属性可能在动态标准或促销活动中与“等于”和“不等于”运算符不兼容。如果左侧具有预定义属性或自定义属性，则应在右侧明智地使用[!UICONTROL Value]、[!UICONTROL Margin]、[!UICONTROL Inventory]和[!UICONTROL 环境]值。

![](assets/left_right.png)

下表显示了有效规则和在运行时可能不兼容的规则：

| 兼容规则 | 可能不兼容的规则 |
|--- |--- |
| value - 介于 - 当前项目的 90% 至 110% - salesValue | salesValue - 介于 - 当前项目的 90% 至 110% - value |
| value - 介于 - 当前项目的 90% 至 110% - value | clearancePrice - 介于 - 当前项目的 90% 至 110% - margin |
| margin - 介于 - 当前项目的 90% 至 110% - margin | storeInventory - 等于 - 当前项目的 - inventory |
| inventory - 等于 - 当前项目的 - inventory |  |

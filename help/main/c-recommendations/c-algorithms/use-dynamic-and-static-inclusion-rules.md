---
keywords: 包含规则;包含标准;推荐;新建标准;促销活动;动态筛选;动态;空值;忽略筛选规则;静态筛选器;按值筛选;实体属性匹配;轮廓属性匹配;参数匹配;按值筛选;静态筛选器
description: 了解如何在[!DNL Target]推荐中为标准和促销创建包含规则。
title: 使用动态和静态包含规则
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
TQID: 'https://experienceleague.adobe.com/PM9h863-uQWm3wrU7OVWfmnqQgyUGmF7QFpTUaAZuCQ'
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
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '2164'
ht-degree: 7%
---
# 使用动态和静态包含规则 {#inclusion-rules}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在[!DNL Adobe Target Recommendations]中将动态和静态筛选规则添加到标准和促销活动。

>[!ENDSHADEBOX]

包含规则可缩小显示在推荐中的项目范围。 它们是在[!DNL Adobe Target]中为标准和促销活动创建的，具有动态或静态筛选规则。 标准和促销的流程、用例和示例相似，因此本页同时涵盖了标准和促销。

## 添加筛选规则 {#add-filtering-rules}

以下步骤将筛选规则添加到标准。

1. 在[创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#create-criteria)时（**[!UICONTROL 推荐]** > **[!UICONTROL 标准]** > **[!UICONTROL 创建标准]** > **[!UICONTROL 创建标准]**），单击&#x200B;**[!UICONTROL 包含规则]**&#x200B;下的&#x200B;**[!UICONTROL 添加筛选规则]**。

   ![添加筛选规则](/help/main/c-recommendations/c-algorithms/assets/add-fitering-rule.png)

1. 在“推荐应遵守哪些其他规则”框中，单击&#x200B;**[!UICONTROL 静态筛选器]**&#x200B;下拉列表，然后选择所需的选项。

   ![静态筛选器下拉列表](/help/main/c-recommendations/c-algorithms/assets/dynamic-and-static.png)

   可用选项取决于所选垂直行业和推荐键。

要将筛选规则添加到促销活动，请在[创建促销活动](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)时选择&#x200B;**[!UICONTROL 按属性促销]**，然后单击&#x200B;**[!UICONTROL 添加筛选规则]**。

## 筛选器类型 {#filter-types}

以下部分介绍了标准和促销的&#x200B;**[!UICONTROL 动态筛选]**&#x200B;和&#x200B;**[!UICONTROL 按值筛选]**&#x200B;的筛选选项。

### 动态筛选

动态包含规则适应访客或请求，而静态包含规则使用固定值。

* 动态包含规则通过匹配用户配置文件参数或mbox调用中的属性来交付推荐。

  例如，可以创建“最受欢迎的标准”推荐。 从返回的推荐集中可以（实时）根据用户访问显示推荐的页面时传递的属性过滤掉任何推荐。

* 可以创建任意数量的动态包含规则。 由于包含规则使用AND运算符进行连接，因此必须满足所有规则才能将项目包含在推荐中。

以下选项可用于动态筛选：

| 动态筛选选项 | 详细信息 |
| --- | --- |
| [**[!UICONTROL 实体属性匹配]**](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | 通过比较潜在的推荐项目池与访客与之交互的特定项目，动态进行筛选。<P>使用&#x200B;**[!UICONTROL 实体属性匹配]**&#x200B;显示最有可能吸引访客的建议，如访客最喜爱的品牌。 |
| [**[!UICONTROL 轮廓属性匹配]**](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | 通过比较项目（实体）与访客配置文件中的值来进行动态筛选。<P>使用&#x200B;**[!UICONTROL 配置文件属性匹配]**&#x200B;显示与访客配置文件中存储的值匹配的推荐，如大小或最喜爱的品牌。 |
| [**[!UICONTROL 参数匹配]**](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | 通过比较项目（实体）与请求中的值（API或mbox）来进行动态筛选。<P>使用&#x200B;**[!UICONTROL 参数匹配]**&#x200B;来推荐与页面参数或访客参数匹配的内容，如设备维度或地理位置。 |

### 按值筛选

静态规则限制推荐中包含哪些项目，而不使用收藏集。 以下选项可用于按值筛选：

| 按值过滤选项 | 详细信息 |
| --- | --- |
| [**[!UICONTROL 静态筛选]**](/help/main/c-recommendations/c-algorithms/static-value.md) | 按手动输入的一个或多个静态值筛选。 |

## 可用运算符 {#operators}

以下示例显示如何使用动态促销和排除进行营销。

>[!NOTE]
>
>“列表”运算符要求实体和配置文件属性都存储为数组。 以逗号分隔的列表不起作用。

| 运算符 | 可在 | 示例 |
|--- |--- |--- |
| **[!UICONTROL 等于任何]** | **[!UICONTROL 实体属性匹配]**，**[!UICONTROL 配置文件属性匹配]**，**[!UICONTROL 参数匹配]**&#x200B;和&#x200B;**[!UICONTROL 静态筛选器]** | 当访客查看网站上的项目时（例如产品、文章或影片），使用“等于”运算符的动态促销活动可以促销以下分类的其他项目：<ul><li>相同品牌</li><li>相同类别</li><li>同类AND来自自有品牌</li><li>同一商店</li></ul> |
| **[!UICONTROL 不等于]**&#x200B;中的任何一个 | **[!UICONTROL 实体属性匹配]**，**[!UICONTROL 配置文件属性匹配]**，**[!UICONTROL 参数匹配]**&#x200B;和&#x200B;**[!UICONTROL 静态筛选器]** | 当访客查看网站上的项目（例如产品、文章或电影）时，使用“**[!UICONTROL ”运算符的动态促销不等于]**”运算符的任何一个运算符可以促销以下分类的其他项目：<ul><li>另一部电视剧</li><li>另一种类型</li><li>其他产品系列</li><li>其他样式ID</li></ul> |
| **[!UICONTROL 大于或等于]**&#x200B;的任意一个 | **[!UICONTROL 实体属性匹配]**，**[!UICONTROL 配置文件属性匹配]**，**[!UICONTROL 参数匹配]**&#x200B;和&#x200B;**[!UICONTROL 静态筛选器]** | 当访客查看网站上的项目（例如产品）时，“**[!UICONTROL ”大于或等于]**”运算符可以促销满足以下条件的其他项目：<ul><li>成本相同或更昂贵</li></ul> |
| **[!UICONTROL 小于或等于]**&#x200B;中的任意一个 | **[!UICONTROL 实体属性匹配]**，**[!UICONTROL 配置文件属性匹配]**，**[!UICONTROL 参数匹配]**&#x200B;和&#x200B;**[!UICONTROL 静态筛选器]** | 当访客查看网站上的项目（例如产品）时，“**[!UICONTROL 小于或等于]**”运算符可以促销满足以下条件的其他项目：<ul><li>成本相同或更便宜</li></ul> |
| **[!UICONTROL 包含任何]** | **[!UICONTROL 实体属性匹配]**，**[!UICONTROL 配置文件属性匹配]**，**[!UICONTROL 参数匹配]**&#x200B;和&#x200B;**[!UICONTROL 静态筛选器]** | 当访客查看网站上的项目（例如产品）时，“**[!UICONTROL 包含任意]**”运算符可以促销以下其他项目：<ul><li>标题包含相同的品牌</li></ul> |
| **[!UICONTROL 不包含任何]** | **[!UICONTROL 实体属性匹配]**，**[!UICONTROL 配置文件属性匹配]**，**[!UICONTROL 参数匹配]**&#x200B;和&#x200B;**[!UICONTROL 静态筛选器]** | 当访客查看网站上的项目（例如产品）时，“**[!UICONTROL 不包含任何]**”运算符可以促销以下其他项目：<ul><li>标题不包含脏字</li></ul> |
| **[!UICONTROL 以任一]**&#x200B;开头 | **[!UICONTROL 实体属性匹配]**，**[!UICONTROL 配置文件属性匹配]**，**[!UICONTROL 参数匹配]**&#x200B;和&#x200B;**[!UICONTROL 静态筛选器]** | 当访客查看网站上的项目（例如产品）时，“**[!UICONTROL 以任意]**”运算符可以促销以下其他项目：<ul><li>产品名称以iPhone开头</li></ul> |
| **[!UICONTROL 以任意]**&#x200B;结尾 | **[!UICONTROL 实体属性匹配]**，**[!UICONTROL 配置文件属性匹配]**，**[!UICONTROL 参数匹配]**&#x200B;和&#x200B;**[!UICONTROL 静态筛选器]** | 当访客查看网站上的项目（例如产品）时，“**[!UICONTROL 以任意]**”运算符可以促销以下其他项目：<ul><li>内容以EN结尾，EN表示英语</li></ul> |
| **[!UICONTROL 介于]**&#x200B;之间 | **[!UICONTROL 实体属性匹配]**、**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 当访客查看网站上的项目（例如产品、文章或电影）时，使用“**[!UICONTROL ”运算符的动态促销可以促销以下其他项目：]**<ul><li>更贵</li><li>更便宜</li><li>成本加减30%</li><li>同一季的后几集</li><li>系列中以前的书籍</li></ul> |
| **[!UICONTROL 列表在]**&#x200B;中包含一个项（位于右侧的列表） | **[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 在配置文件属性匹配中，当访客查看网站上的项目（例如产品、文章或电影）时，“**[!UICONTROL 列表包含]**”运算符中的项目，该运算符可以促销以下其他项目：<ul><li>在访客所在的地理位置可用</li></ul>**示例**：推荐仅在访客的地理区域中可用的项目。<P>过滤器规则可能如下所示：<P>`availableGeographies list contains an item in user.currentGeography`<P>**注意**：使用此运算符时，应在规则的[右侧](#caveats)有一个列表。 |
| **[!UICONTROL 列表在]**&#x200B;中不包含项（右侧的列表） | **[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 在配置文件属性匹配中，当访客查看网站上的项目（例如产品、文章或电影）时，“**[!UICONTROL 列表在]**”中不包含项目，运算符可以排除以下其他项目：<ul><li>在访客查看的最近十个项目的列表中</li></ul>**示例**：访客最近查看过且对其不感兴趣的项目不会被提升。<P>筛选规则可能如下所示：<P>`id is not contained in list user.lastViewedItems`<P>**注意**：使用此运算符时，应在规则的[右侧](#caveats)有一个列表。 |
| **[!UICONTROL 列表在]**&#x200B;中包含项（两侧的列表） | **[!UICONTROL 实体属性匹配]**、**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 在配置文件属性匹配中，当访客查看网站上的项目（例如体育赛事或音乐会）时，“**[!UICONTROL 列表包含]**”中的项目，运算符可以促销以下其他项目：<ul><li>与访客最喜爱的团队之一关联</li></ul>**示例**：推荐与访客最喜爱的团队之一关联的游戏。<P>筛选规则可能如下所示：<P>`teamsPlaying list contains an item in user.favoriteTeams`<P>**注意**：使用此运算符时，需要规则的[两侧](#caveats)都有一个列表。 |
| **[!UICONTROL 列表在]**&#x200B;中不包含项（两侧的列表） | **[!UICONTROL 实体属性匹配]**、**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 在参数匹配中，当访客查看网站上的项目（例如产品、文章或电影）时，“**[!UICONTROL 列表在]**”中不包含项目，运算符可以排除以下其他项目：<ul><li>包含在禁止类型列表中</li></ul>**示例**：排除仅供成人访客使用的项目，例如烟草和酒精。<P>筛选规则可能如下所示：<P>`itemType is not contained in list mbox.prohibitedTypes`<P>**注意**：使用此运算符时，需要规则的[两侧](#caveats)都有一个列表。 |
| **[!UICONTROL 列表包含]**&#x200B;中的所有项 | **[!UICONTROL 实体属性匹配]**、**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 在配置文件属性匹配中，当访客查看网站上的项目（例如工作张贴或方法）时，“**[!UICONTROL 列表包含]**”运算符中的所有项目可以提升满足以下条件的其他项目：<ul><li>包括一组技能</li><li>包括一组所需成分</li></ul>**示例1**：访客具有一组技能（Java、C++和HTML）。 目录中的项目是具有所需技能的作业（Java和HTML）。 在将作业推荐给访客之前，访客配置文件必须包含所有必需的技能。<P>筛选规则可能如下所示：<P>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<P>**示例2**：用户有食品柜配料的列表。 食谱里有一份必要配料的清单。 在向访客推荐方法之前，访客配置文件必须包含所有必需的组成部分。<P>筛选规则可能如下所示：<P>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<P>**注意**：使用此运算符时，需要规则的[两侧](#caveats)都有一个列表。 |
| **[!UICONTROL 列表未包含]**&#x200B;中的所有项 | **[!UICONTROL 实体属性匹配]**、**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 在实体属性匹配中，当访客查看网站上的项目（例如体育赛事或音乐会）时，“**[!UICONTROL 列表不包含]**”运算符中的所有项目可以促销具有以下特性的其他项目：<ul><li>不包括团队集</li></ul>**示例**：体育赛事包括两支球队。 该访客的配置文件指示该访客不想查看这些团队的游戏，因此如果这些团队在玩游戏，则不得推荐该游戏。<P>筛选规则可能如下所示：<P>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<P>**注意**：使用此运算符时，需要规则的[两侧](#caveats)都有一个列表。 |

## 处理空值 {#empty-values}

当按&#x200B;**[!UICONTROL 实体属性匹配]**、**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]**&#x200B;进行筛选时，有多个选项可用于处理空值。

以前，如果值为空，则不会返回任何结果。 “如果&#x200B;*x*&#x200B;为空”下拉列表指定条件具有空值时要执行的操作，如下图所示：

![空值选项](/help/main/c-recommendations/c-algorithms/assets/empty_value.png)

要选择所需的操作，请将鼠标悬停在齿轮图标（ ![齿轮图标](/help/main/c-recommendations/c-algorithms/assets/icon_gear.png)）上，然后选择所需的操作：

| 操作 | 可用于 | 详细信息 |
|--- |--- |--- |
| **[!UICONTROL 忽略此筛选规则]** | **[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 此操作是&#x200B;**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]**&#x200B;的默认操作。<P>该规则将被忽略。 例如，如果有三个筛选规则，且第三个规则未传递任何值，则可以忽略具有空值的第三个规则，而不是不返回任何结果。 |
| **[!UICONTROL 不显示此条件的任何结果]**<P>（仅限标准） | **[!UICONTROL 实体属性匹配]**、**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 此操作是&#x200B;**[!UICONTROL 实体属性匹配]**&#x200B;的默认操作。<P>此操作是[!DNL Target]在添加此选项之前处理空值的方式：不显示此条件的结果。 |
| **[!UICONTROL 不促销任何项目]**<P>（仅限促销活动） | **[!UICONTROL 实体属性匹配]**、**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 此操作是&#x200B;**[!UICONTROL 实体属性匹配]**&#x200B;的默认操作。<P>此操作是[!DNL Target]在添加此选项之前处理空值的方式：不显示此促销的结果。 |
| **[!UICONTROL 使用静态值]** | **[!UICONTROL 实体属性匹配]**、**[!UICONTROL 配置文件属性匹配]**&#x200B;和&#x200B;**[!UICONTROL 参数匹配]** | 当值为空时，可以使用静态值。 |

## 注意事项 {#caveats}

>[!IMPORTANT]
>
>在运行时，不同的数据类型属性可能在动态标准或促销活动中与“等于”和“不等于”运算符不兼容。 如果左侧具有预定义的属性或自定义属性，请仔细选择右侧的&#x200B;**[!UICONTROL 值]**、**[!UICONTROL 利润]**、**[!UICONTROL 库存]**&#x200B;和&#x200B;**[!UICONTROL 环境]**&#x200B;值。

![筛选规则的左右两侧](/help/main/c-recommendations/c-algorithms/assets/left_right.png)

下表显示了兼容的规则和在运行时可能不兼容的规则：

| 兼容的规则 | 潜在不兼容的规则 |
|--- |--- |
| value - 介于 - 当前项目的 90% 至 110% - salesValue | salesValue - 介于 - 当前项目的 90% 至 110% - value |
| value - 介于 - 当前项目的 90% 至 110% - value | clearancePrice - 介于 - 当前项目的 90% 至 110% - margin |
| margin - 介于 - 当前项目的 90% 至 110% - margin | storeInventory - 等于 - 当前项目的 - 库存 |
| inventory - 等于 - 当前项目的 - 库存 |  |

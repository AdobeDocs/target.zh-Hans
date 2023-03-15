---
keywords: 包含规则;包含标准;推荐;新建标准;促销活动;动态筛选;动态;空值;忽略筛选规则;静态筛选器;按值筛选;实体属性匹配;配置文件属性匹配;参数匹配;按值筛选;静态筛选器
description: 了解如何在Adobe中创建包含规则 [!DNL Target] Recommendations ，以了解标准和促销活动。 要获得更好的结果，请添加更多动态或静态筛选规则。
title: 如何在Recommendations中使用动态和静态包含规则？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '2093'
ht-degree: 16%

---

# 使用动态和静态包含规则

有关在中为标准和促销活动创建包含规则的信息 [!DNL Adobe Target] 和添加动态或静态筛选规则，以便为推荐获得更好的结果。

如用例和示例所述，针对标准和促销活动创建和使用包含规则的过程类似。此部分涵盖标准和促销活动以及包含规则的使用。

## 将筛选规则添加到标准 {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)时，单击&#x200B;**[!UICONTROL 包含规则]**&#x200B;下的&#x200B;**[!UICONTROL 添加筛选规则]**。

![inclusion_options_new图像](assets/inclusion_options_new.png)

可用选项取决于所选垂直行业和推荐键。

## 将筛选规则添加到促销活动 {#section_D59AFB62E2EE423086281CF5D18B1076}

[创建促销活动](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)时，选择&#x200B;**[!UICONTROL 按属性促销]**，然后单击&#x200B;**[!UICONTROL 添加筛选规则]**。

![inclusion_options图像](assets/inclusion_options.png)

## 筛选类型 {#section_0125F1ED10A84C0EB45325122460EBCD}

以下部分列出了 [!UICONTROL 动态筛选] 和 [!UICONTROL 按值筛选] 对于标准和促销活动：

### 动态筛选

动态包含规则比静态包含规则更强大，并且可产生更好的结果和参与度。 请考虑以下事项：

* 动态包含规则通过匹配用户配置文件参数或mbox调用中的属性来提供推荐。

   例如，您可以创建“最受欢迎标准”推荐。 从返回的推荐集中，您可以根据用户访问显示推荐的页面时传递的属性过滤掉任何推荐（实时）。

* 使用静态规则来限制推荐中包含哪些项目（而不是使用收藏集）。

* 您可以创建所需数量的动态包含规则。 包含规则使用“与”运算符进行结合。所有规则都必须得到满足，才能在推荐中包含某个项目。

以下选项可用于动态筛选：

| 动态筛选选项 | 详细信息 |
| --- | --- |
| [实体属性匹配](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | 通过将潜在推荐项目池与用户交互的特定项目进行比较来进行动态筛选。<br>使用 [!UICONTROL 实体属性匹配] 当您希望显示最有可能吸引访客的推荐时，例如访客最喜爱的品牌。 |
| [配置文件属性匹配](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | 通过比较项目（实体）与用户配置文件中的值来进行动态筛选。<br>使用 [!UICONTROL 配置文件属性匹配] 当您想要显示与访客配置文件中存储的值（如大小或最喜爱的品牌）匹配的推荐时。 |
| [参数匹配](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | 通过比较项目（实体）与请求中的值（API或mbox）来进行动态筛选。<br>使用 [!UICONTROL 参数匹配] 推荐与页面参数或访客参数匹配的内容，如设备维度或地理位置。 |

### 按值筛选

以下选项可用于按值筛选：

| 按值筛选选项 | 详细信息 |
| --- | --- |
| [静态筛选](/help/main/c-recommendations/c-algorithms/static-value.md) | 手动输入一个或多个静态值以进行筛选。 |

## 可用的运算符 {#operators}

动态标准和促销活动比静态标准和促销活动功能强大得多，可产生更好的结果和参与度。

以下示例提供了有关如何在营销工作中使用动态促销和排除项的一般概念：

| 运算符 | 示例 |
| --- | --- |
| 等于<br>（可用于实体属性匹配、配置文件属性匹配、参数匹配和静态筛选器。） | 在动态促销活动中使用“等于”运算符时，如果访客正在查看您网站上的项目（例如产品、文章或影片），您可以向其促销以下分类的其他项目：<ul><li>同一品牌</li><li>同一类别</li><li>同一类别AND来自品牌</li><li>同一商店</li></ul> |
| 不等于<br>（可用于实体属性匹配、配置文件属性匹配、参数匹配和静态筛选器。） | 在动态促销活动中使用“不等于”运算符时，如果访客正在查看您网站上的项目（例如产品、文章或影片），您可以向其促销以下分类的其他项目：<ul><li>另一部电视剧</li><li>不同的流派</li><li>其他产品系列</li><li>其他样式ID</li></ul> |
| 不包含子字符串<br>（可用于实体属性匹配、配置文件属性匹配、参数匹配和静态筛选器。） | 使用“不包含子字符串”运算符时，如果访客正在查看您网站上的项目（例如产品），您可以促销以下其他项目：<ul><li>标题不包含粗体字</li></ul> |
| 开头<br>（可用于实体属性匹配、配置文件属性匹配、参数匹配和静态筛选器。） | 使用“开头为”运算符时，如果访客正在查看您网站上的项目（例如产品），您可以促销以下其他项目：<ul><li>产品名称以iPhone开头</li></ul> |
| 结束于<br>（可用于实体属性匹配、配置文件属性匹配、参数匹配和静态筛选器。） | 使用“结束于”运算符时，如果访客正在查看您网站上的项目（例如产品），您可以促销以下其他项目：<ul><li>内容以EN结尾，表示英语</li></ul> |
| Is Greater Than Or Equal To<br>（可用于实体属性匹配、配置文件属性匹配、参数匹配和静态筛选器。） | 使用“大于或等于”运算符，当访客查看您网站上的项目（例如产品）时，您可以促销以下其他项目：<ul><li>成本相同或更贵</li></ul> |
| Is Less Than Or Equal To<br>（可用于实体属性匹配、配置文件属性匹配、参数匹配和静态筛选器。） | 使用“小于或等于”运算符，当访客查看您网站上的项目（例如产品）时，您可以促销以下其他项目：<ul><li>成本相同或更便宜</li><li>排除成本较低的项目</li></ul> |
| 介于<br>（可用于实体属性匹配、配置文件属性匹配和参数匹配。） | 在动态促销活动中使用“介于”运算符时，如果访客正在查看您网站上的项目（例如产品、文章或影片），您可以向其促销以下其他项目：<ul><li>更贵</li><li>更便宜</li><li>成本加或减30%</li><li>同一季的后续剧集</li><li>系列中的先前书籍</li></ul> |
| 包含在列表中<br>（可用于配置文件属性匹配和参数匹配。） | 在配置文件属性匹配中使用“包含在列表中”运算符时，如果访客正在查看您网站上的项目（例如产品、文章或影片），您可以促销以下其他项目：<ul><li>在访客的地理位置中可用</li></ul>**示例**:您只想推荐访客所在地理区域中可用的项目。<br>您的过滤器规则可能如下所示：<br>`availableGeographies list contains an item in user.currentGeography`<br>**注意**:使用此运算符时， [右侧](#caveats) 规则。 |
| 未包含在列表中<br>（可用于配置文件属性匹配和参数匹配。） | 在配置文件属性匹配中使用“未包含在列表中”运算符时，如果访客正在查看您网站上的项目（例如产品、文章或影片），则可以排除以下其他项目：<ul><li>在访客最近查看的十个项目列表中</li></ul></ul>**示例**:您不希望促销访客最近查看过且不感兴趣的项目。<br>您的筛选规则可能如下所示：<br>`id is not contained in list user.lastViewedItems`<br>**注意**:使用此运算符时， [右侧](#caveats) 规则。 |
| 列表包含<br>（可用于实体属性匹配、配置文件属性匹配和参数匹配。） | 在配置文件属性匹配中使用“列表包含中的项目”运算符时，如果访客正在查看您网站上的项目（例如体育赛事或音乐会），您可以促销以下其他项目：<ul><li>与访客最喜爱的团队之一关联</li></ul>**示例**:您希望推荐与访客最喜爱的团队之一关联的游戏。<br>您的筛选规则可能如下所示：<br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**注意**:使用此运算符时， [两侧](#caveats) 规则。 |
| 列表中不包含项目<br>（可用于实体属性匹配、配置文件属性匹配和参数匹配。） | 在参数属性匹配中使用“列表中不包含项目”运算符时，如果访客正在查看您网站上的项目（例如产品、文章或影片），则可以排除以下其他项目：<ul><li>列在禁止类型清单中</li></ul>**示例**:您希望排除成年人（如烟草和酒精）的访客可用的物品。<br>您的筛选规则可能如下所示：<br>`itemType is not contained in list mbox.prohibitedTypes`<br>**注意**:使用此运算符时， [两侧](#caveats) 规则。 |
| 列表包含<br>（可用于实体属性匹配、配置文件属性匹配和参数匹配。） | 在配置文件属性匹配中使用“列表包含中的所有项目”运算符时，如果访客正在查看您网站上的项目（如职务发帖或方法），您可以促销以下其他项目：<ul><li>包括一组技能</li><li>包括一组必需的配料</li></ul>**示例1**:假设访客具有一套技能(Java、C++和HTML)。 目录中的项目是具有所需技能(Java和HTML)的工作。 在向访客推荐工作之前，您需要确保访客的配置文件包含所有必需的技能。<br>您的筛选规则可能如下所示：<br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**示例2**:假设用户有一个食品配料列表。 配方中有一份必需的配料列表。 在向访客推荐方法之前，您需要确保访客的配置文件包含所有必需的组分。<br>您的筛选规则可能如下所示：<br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**注意**:使用此运算符时， [两侧](#caveats) 规则。 |
| 列表中并不包含<br>（可用于实体属性匹配、配置文件属性匹配和参数匹配。） | 在实体属性匹配中使用“list does not contain all items in”运算符时，如果访客正在查看您网站上的项目（例如体育赛事或音乐会），您可以促销以下其他项目：<ul><li>不要包含一组团队</li></ul>**示例**:假设体育赛事包含两支球队。 访客的配置文件表示该访客不想查看这些团队的游戏。 如果这些团队正在进行比赛，您需要确保不推荐比赛。<br>您的筛选规则可能如下所示：<br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**注意**:使用此运算符时， [两侧](#caveats) 规则。 |

## 按实体属性匹配、配置文件属性匹配和参数匹配进行筛选时处理空值 {#section_7D30E04116DB47BEA6FF840A3424A4C8}

筛选时，您可以选择多个选项来处理空值 [!UICONTROL 实体属性匹配], [!UICONTROL 配置文件属性匹配]和 [!UICONTROL 参数匹配] （退出标准和促销活动）。

以前，如果值为空，则不会返回任何结果。如果标准包含空值，则“如果 *x* 为空”下拉列表允许您选择适当的操作，如下图所示：

![empty_value图像](assets/empty_value.png)

要选择所需的操作，请将鼠标悬停在齿轮图标(![icon_gear图像](assets/icon_gear.png))，然后选择所需的操作：

| 操作 | 适用选项 | 详细信息 |
|--- |--- |--- |
| [!UICONTROL 忽略此筛选规则] | [!UICONTROL 配置文件属性匹配] 和 [!UICONTROL 参数匹配] | 此操作是 [!UICONTROL 配置文件属性匹配] 和 [!UICONTROL 参数匹配].<br>该选项指定忽略该规则。例如，如果有三个筛选规则，第三个规则不传递任何值，则您只需忽略具有空值的第三个规则，而不是不返回任何结果。 |
| [!UICONTROL 不显示此标准的任何结果]<br>（仅限标准） | [!UICONTROL 实体属性匹配], [!UICONTROL 配置文件属性匹配]和 [!UICONTROL 参数匹配] | 此操作是 [!UICONTROL 实体属性匹配].<br>此操作是 [!DNL Target] 在添加此选项之前处理了空值：此标准不显示任何结果。 |
| [!UICONTROL 不促销任何项目<br>（仅限促销）] | [!UICONTROL 实体属性匹配], [!UICONTROL 配置文件属性匹配]和 [!UICONTROL 参数匹配] | 此操作是 [!UICONTROL 实体属性匹配].<br>此操作是 [!DNL Target] 在添加此选项之前处理了空值：此标准不显示任何结果。 |
| [!UICONTROL 使用静态值] | [!UICONTROL 实体属性匹配], [!UICONTROL 配置文件属性匹配]和 [!UICONTROL 参数匹配] | 如果值为空，您可以选择使用静态值。 |

## 注意事项 {#caveats}

>[!IMPORTANT]
>
>在运行时，不同的数据类型属性可能在动态标准或促销活动中与“等于”和“不等于”运算符不兼容。使用 [!UICONTROL 值], [!UICONTROL 边距], [!UICONTROL 库存]和 [!UICONTROL 环境] 如果左侧具有预定义属性或自定义属性，则在右侧的值会明智。

![left_right图像](assets/left_right.png)

下表显示了有效规则和在运行时可能不兼容的规则：

| 兼容规则 | 可能不兼容的规则 |
|--- |--- |
| value - 介于 - 当前项目的 90% 至 110% - salesValue | salesValue - 介于 - 当前项目的 90% 至 110% - value |
| value - 介于 - 当前项目的 90% 至 110% - value | clearancePrice - 介于 - 当前项目的 90% 至 110% - margin |
| margin - 介于 - 当前项目的 90% 至 110% - margin | storeInventory - 等于 - 当前项目的 - inventory |
| inventory - 等于 - 当前项目的 - inventory |  |

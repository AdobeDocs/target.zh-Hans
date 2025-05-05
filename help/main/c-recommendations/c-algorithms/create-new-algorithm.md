---
keywords: 标准；算法；垂直行业；页面类型；推荐键；推荐逻辑；数据范围；回顾窗口；行为数据源；部分设计；备用推荐；包含规则；属性权重；当前类别；自定义属性；上次购买的项目；上次查看的项目；查看次数最多的项目；最喜爱的类别；热门程度；最近查看的项目；上次购买；上次查看；最喜爱的项目；最近查看的项目；最近查看的项目；最近查看的项目
description: 了解如何创建条件来控制 [!DNL Recommendations] 活动的内容，以显示最适合您的活动的推荐。
title: 如何在 [!DNL Recommendations]中创建[!UICONTROL Criteria]？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '2554'
ht-degree: 47%

---

# 创建标准

[!UICONTROL Adobe Target] [!UICONTROL Recommendations]中的条件可控制[!UICONTROL Recommendations]活动的内容。 可创建标准以显示最适合您的活动的推荐。 这些标准使用访客的操作来确定要显示的内容或产品。

以下部分将说明如何创建新标准。

## 访问“创建新标准”屏幕

可通过多种方式访问[!UICONTROL Create New Criteria]屏幕。 某些屏幕选项会根据您访问该屏幕的方式而有所不同。

* 在&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;库屏幕上，单击&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**。 您在此处创建的标准会自动设置为可用于所有 [!DNL Recommendations] 活动。
* 使用[!UICONTROL Visual Experience Composer] (VEC)创建[!DNL Recommendations]活动时，在页面上选择一个元素并单击[!UICONTROL Replace w/ Recommendations]、[!UICONTROL Insert Recommendations Before]或[!UICONTROL Insert Recommendations After]后，您会立即转到[!UICONTROL Select Criteria]屏幕。 然后，您可以选择可用的标准，也可以单击&#x200B;**[!UICONTROL Create Criteria]**。 如果您创建新标准，则可以选择保存标准以供其他[!DNL Recommendations]活动使用。 有关详细信息，请参阅[创建Recommendations活动](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。
* 编辑[!DNL Recommendations]活动时，单击页面上的[!UICONTROL Recommendations Location]框并选择&#x200B;**[!UICONTROL Change Criteria]**。 在[!UICONTROL Select Criteria]屏幕上单击&#x200B;**[!UICONTROL Create Criteria]**。 您将可以选择保存新建的标准，以供在其他 [!DNL Recommendations] 活动中使用。

以下步骤假定您使用第一个方法访问[!UICONTROL Create New Criteria]屏幕： **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;库屏幕。

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**。

1. 单击&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**。

1. 配置以下部分中的信息。

## [!UICONTROL Basic Information] {#info}

1. 键入&#x200B;**[!UICONTROL Criteria Name]**。

   这是用于描述标准的“内部”名称。例如，您可能希望将标准命名为“利润最高的产品”，但是不希望公开显示此名称。请参阅下一步骤，以设置公开显示的标题。

1. 为使用该标准的任意推荐键入一个要在页面上公开显示的&#x200B;**[!UICONTROL Display Title]**。

   例如，使用此标准显示推荐时，您可能想要显示“查看了这个项目，也查看了那个项目的人”或“相似产品”。

1. 键入条件的简短&#x200B;**[!UICONTROL Description]**。

   描述应该有助于您识别该标准，并且可以包含有关该标准用途的信息。

1. 根据推荐活动的目标选择垂直行业。

   | 垂直行业 | 目标 |
   |--- |--- |
   | [!UICONTROL Retail/Ecommerce] | 转化促进完成购买 |
   | [!UICONTROL Lead Generation/B2B/Financial Services] | 转化但不购买 |
   | [!UICONTROL Media/Publishing] | 参与度 |

   根据您选择的垂直行业，其他标准选项会发生变化。

1. 选择&#x200B;**[!UICONTROL Page Type]**。

   您可以选择多个页面类型。

   垂直行业和页面类型可一起帮助您对保存的标准进行分类，使其更易于在其他[!DNL Recommendations]活动中重复使用。

## [!UICONTROL Recommendations Algorithm] {#rec-algo}

1. 选择&#x200B;**[!UICONTROL Algorithm Type]**&#x200B;和&#x200B;**[!UICONTROL Algorithm]**：

   ![推荐的算法部分](assets/recommended-algorithm.png)

   | 算法类型 | 何时使用/可用算法 |
   | --- | --- |
   | [!UICONTROL Cart-Based] | 根据用户的购物车内容提供推荐。 <ul><li>[!UICONTROL People Who Viewed These, Also Viewed] </li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul> |
   | [!UICONTROL Popularity-Based] | 根据项目在整个网站中的整体受欢迎程度或用户最喜爱或查看次数最多的类别、品牌、流派等中的项目受欢迎程度提供推荐。 <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
   | [!UICONTROL Item-Based] | 根据查找的用户当前正在查看或最近查看过的项目的相似项目提供推荐。 <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
   | [!UICONTROL User-Based] | 根据用户的行为提供推荐。 | <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
   | [!UICONTROL Custom Criteria] | 根据您上传的自定义文件提出推荐。 | <ul><li>自定义算法</li></ul> |

   >[!NOTE]
   >
   >如果选择&#x200B;**[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**，则可以选择设置[内容相似度规则](#similarity)。

1. 根据需要，选择要匹配的&#x200B;**项目属性**&#x200B;和&#x200B;**配置文件属性**、**推荐键**、**筛选键**&#x200B;和/或&#x200B;**Analytics量度**&#x200B;以配置算法。

其余的算法配置选项因所选算法而异。 要完成算法配置，请选择[!UICONTROL Recommendation Key]、[!UICONTROL Filtering Key]、[!UICONTROL Co-Occurrence Basis]、[!UICONTROL Analytics Metric]和/或[!UICONTROL Item Attribute]和[!UICONTROL Profile Attribute to Match]。

有关选择[!UICONTROL Recommendation Key]的详细信息，请参阅[使推荐基于推荐键](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

## [!UICONTROL Backup Content] {#content}

[!UICONTROL Backup Content]规则确定推荐项目数未填入您的[推荐设计](/help/main/c-recommendations/c-design-overview/design-overview.md)时会发生什么情况。 [!DNL Recommendations]标准可能会返回比您的设计调用更少的推荐。 例如，如果您的设计有四个项目的版块，但您的标准导致仅推荐两个项目，则可以将剩余版块留空，您可以使用备用推荐来填充额外的版块，也可以选择不显示推荐。

1. （可选）将&#x200B;**[!UICONTROL Partial Design Rendering]**&#x200B;切换开关滑动到“开”位置。

   系统会尽可能多地填充版块，但设计模板仍可包含空白空间以备放置剩余版块。 如果禁用了此选项，并且内容不足以填充所有可用的版块，则不会提供推荐，而是显示默认内容。

   如果您希望向推荐提供空白版块，请启用此选项。 如果您希望根据标准用空白版块填充推荐版块，而这些版块填充了您网站上的类似或热门内容，请使用备用推荐，如下一步中所述。

1. （可选）将&#x200B;**[!UICONTROL Show Backup Content]**&#x200B;切换开关滑动到“开”位置。

   从您的网站中随机选择查看次数最多的产品，来填满设计中剩余的空白版块。

   使用备用推荐可确保您的推荐设计填充所有可用的版块。 假设您采用4 x 1设计，如下所示：

   ![4 x 1设计](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

   假设您的标准导致只推荐两个项目。 如果启用[!UICONTROL Partial Design Rendering]选项，则前两个版块已填满，但剩余两个版块仍留空。 但是，如果启用[!UICONTROL Show Backup Recommendations]选项，则前两个版块会根据您指定的条件填充，其余两个版块会根据您的备用推荐填充。

   以下矩阵显示了使用[!UICONTROL Partial Design Rendering]和[!UICONTROL Backup Content]选项时将观察到的结果：

   | 局部设计渲染 | 备份内容 | 结果 |
   |--- |--- |--- |
   | 禁用 | 禁用 | 如果返回的推荐少于设计所需的推荐，则推荐设计将被替换为默认内容，并且不显示任何推荐。 |
   | 启用 | 禁用 | 设计会进行渲染，但如果返回的推荐少于设计所需的推荐，则可能包含空白区域。 |
   | 启用 | 启用 | 备用推荐将填满可用的设计“版块”，从而完全渲染您的设计。<br>如果将包含规则应用于备用推荐时会限制符合条件的备用推荐的数量，以致于设计无法填满，则会局部渲染设计。<br>如果标准未返回任何推荐，并且包含规则将备用推荐限制为零，则设计将被替换为默认内容。 |
   | 禁用 | 启用 | 备用推荐将填满可用的设计“版块”，从而完全渲染您的设计。<br>如果将包含规则应用于备用推荐时会限制符合条件的备用推荐的数量，以致于设计无法填满，则设计将被替换为默认内容，并且不会显示任何推荐。 |

   有关详细信息，请参阅[使用备份推荐](/help/main/c-recommendations/c-algorithms/backup-recs.md)。

1. （视情况而定）如果您在上一步中选择了&#x200B;**[!UICONTROL Show Backup Content]**，则可以启用&#x200B;**[!UICONTROL Apply inclusion rules to backup recommendations]**。

   包含规则确定推荐中包含哪些项目。 可用的选项取决于您的垂直行业。

   有关详细信息，请参阅下面的[指定包含规则](#inclusion)。

## [!UICONTROL Data Source] {#data-source}

1. 选择所需的&#x200B;**[!UICONTROL Behavioral Data Source]**： [!UICONTROL Adobe Target]或[!UICONTROL Analytics]。

   >[!NOTE]
   >
   >仅当您的实施使用[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)时，才会显示[!UICONTROL Behavioral Data Source]部分。

   ![行为数据Source部分](assets/data-source.png)

   如果您选择[!UICONTROL Analytics]，请选择所需的报表包。

   如果标准使用[!DNL Adobe Analytics]作为行为数据源，则创建标准后，其可用性的时间取决于所选报表包和回顾窗口是否已用于任何其他标准，如下所述：

   * **一次性报表包设置**：首次将报表包与给定数据范围回顾时间范围一起使用时，[!DNL Target Recommendations] 可能需要 2 到 7 天的时间才能从 [!DNL Analytics] 完全下载所选报表包的行为数据。此时间范围取决于[!DNL Analytics]系统负载。
   * **使用已经可用的报表包新建或编辑标准**：在创建新标准或编辑现有标准时，如果所选报表包已经与 [!DNL Target Recommendations] 一起使用，并且其数据范围等于或小于所选的数据范围，则数据立即可用，而无需一次性设置。在这种情况下，或者如果在未修改所选报表包或数据范围的情况下对算法的设置进行编辑，则该算法将在 12 小时内运行或者重新运行。
   * **持续的算法运行**：数据每天从 [!DNL Analytics] 流向 [!DNL Target Recommendations]。例如，对于[!UICONTROL Viewed Affinity]推荐，当用户查看产品时，产品查看跟踪调用将以近实时的方式传递到[!DNL Analytics]。 [!DNL Analytics] 数据会在第二天早些时候被推送到 [!DNL Target]，然后 [!DNL Target] 会在 12 小时内运行算法。

   有关详细信息，请参阅[将Adobe Analytics与Target Recommendations结合使用](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md)。

1. 设置&#x200B;**[!UICONTROL Lookback Window]**&#x200B;以确定在确定要显示的推荐时所使用的可用历史用户行为数据的时间范围。 此选项适用于除[!UICONTROL Items with Similar Attributes]和[!UICONTROL Custom Algorithms]之外的所有算法。

   ![回顾窗口滑块](assets/data-range.png)

   如果您的网站拥有大量流量且行为更改频繁，请选择较短的数据范围。较短的范围可使 [!DNL Recommendations] 能够更好地响应市场和业务的变化。例如，较短的范围意味着 [!DNL Recommendations] 将在访客开始季节性购物时就检测到访客行为的变化（例如返校购物季或圣诞节），并推荐适合这些购物季的项目。

   如果您没有大量数据，或访客行为不经常更改，则您可以选择较长的范围。但是，对于许多网站，较短的窗口会产生质量较高的推荐。

   可用的数据范围包括：

   | 回顾窗口选项 | 更新频率（悬停时显示） | 支持的算法 |
   | --- | --- | --- |
   | 6小时 | 算法每3-6小时运行一次， | [!UICONTROL Popularity-Based]算法（当选定的[!UICONTROL Behavioral Data Source]为[!DNL Adobe Target]时） |
   | 一天 | 算法每12-24小时运行一次 | [!UICONTROL Popularity-Based]算法 |
   | 两天 | 算法每12-24小时运行一次 | <ul><li>[!UICONTROL Popularity-Based]算法</li><li>[!UICONTROL Item-Based]算法</li><li>[!UICONTROL User-Based]算法</li><li>[!UICONTROL Cart-Based]算法</li></ul> |
   | 一周 | 算法每24-48小时运行一次 | <ul><li>[!UICONTROL Popularity-Based]算法</li><li>[!UICONTROL Item-Based]算法</li><li>[!UICONTROL User-Based]算法</li><li>[!UICONTROL Cart-Based]算法</li></ul> |
   | 两周 | 算法每24-48小时运行一次 | <ul><li>[!UICONTROL Popularity-Based]算法</li><li>[!UICONTROL Item-Based]算法</li><li>所有[!UICONTROL User-Based]算法</li><li>[!UICONTROL Cart-Based]算法</li></ul> |
   | 一个月（30天） | 算法每24-48小时运行一次 | <ul><li>[!UICONTROL Popularity-Based]算法</li><li>[!UICONTROL Item-Based]算法</li><li>[!UICONTROL User-Based]算法</li><li>[!UICONTROL Cart-Based]算法</li></ul> |
   | 两个月（61天） | 算法每24-48小时运行一次 | <ul><li>[!UICONTROL Popularity-Based]算法</li><li>[!UICONTROL Item-Based]算法</li><li>[!UICONTROL User-Based]算法</li><li>[!UICONTROL Cart-Based]算法</li></ul> |

## 内容相似度 {#similarity}

使用[!UICONTROL Content Similarity]规则根据项目或媒体属性提出建议。

>[!NOTE]
>
>如果您选择&#x200B;**[!UICONTROL Item-Based]**/**[!UICONTROL Media with Similar Attributes]**&#x200B;作为您的[!UICONTROL Algorithm Type]和[!UICONTROL Algorithm]，则可以选择设置内容相似度规则。

内容相似度会比较项目属性关键字，并根据不同项目共有的关键字数量进行推荐。基于内容相似度的推荐不需要过去的数据便可交付高效的结果。

使用内容相似度生成推荐对新项目特别有效，使用&#x200B;*查看了这个项目，也查看了*&#x200B;以及基于过去行为的其他逻辑的推荐中不太可能出现这些项目。 您还可以使用内容相似度为没有过去购买数据或其他历史数据的新访客生成有用的推荐。

选择&#x200B;**[!UICONTROL Item-Based]**/ **[!UICONTROL Media with Similar Attributes]**&#x200B;时，您可以选择创建规则以增加或减少特定项目属性在确定推荐中的重要性。 对于书籍等项目，您可能希望提升“流派”**、“作者”**、“系列”**&#x200B;等属性的重要性，以便推荐类似的书籍。

由于内容相似度使用关键字来比较项目，因此某些属性（例如“消息”**&#x200B;或“描述”**）可能会在比较中引入“干扰信息”。您可以创建规则来忽略这些属性。

默认情况下，所有属性都设置为“基准线”**。除非您要更改此设置，否则无需创建规则。

>[!NOTE]
>
>内容相似度算法可能使用随机抽样来计算项目之间的相似度。 因此，在算法运行之间，项目之间的相似性评级可能会有所不同。

## 包含规则 {#inclusion}

一些选项可帮助您缩小在推荐中显示的项目范围。您可以在创建标准或促销活动时使用包含规则。

包含规则是可选的；但是，通过设置这些详细信息，您可以更好地控制推荐中显示的项目。配置的每个详细信息都会进一步限定显示条件。

例如，您可以选择仅显示库存超过 50 双且价格在 25 美元至 45 美元之间的女鞋。您还可以对每个属性设置权重，以使对您的业务更为重要的项目最有可能显示出来。

再比如，您可以选择向仅从某些城市访问您的网站并且具有所需大学学位的访客显示职位空缺。

包含规则选项会因垂直行业而异。默认情况下，包含规则会应用于备用推荐。

>[!IMPORTANT]
>
>您应谨慎使用包含规则。在某些情况下动态属性筛选非常有用，例如您的组织设置了一些规则，要求不推荐某个品牌但显示另一品牌。但是，此功能存在机会成本。通过限制某些项目使其不显示（按活动标准通常会显示这些项目），您可能会损失一定比例的提升度。

包含规则会使用“与”连接在一起。所有规则都必须得到满足，才能在推荐中包含某个项目。

如前所述，要创建一个简单的包含规则以仅显示库存超过 50 双且价格在 25 美元至 45 美元之间的女鞋，请执行以下步骤：

1. （视情况而定）将&#x200B;**[!UICONTROL Allow recently purchased items to be recommended?]**&#x200B;切换开关滑动到“开”位置。

   此设置基于 `productPurchasedId`。默认行为是不推荐以前购买的项目。在大多数情况下，您不想促销客户最近购买的项目。如果您销售的是人们通常只买一次的物品，例如皮划艇，那么此选项很有用。如果您销售的是人们会重复再次购买的物品，例如洗发水或其他个人物品，则应该启用此选项。

1. 设置您要推荐的产品的价格范围。
1. 设置您要推荐的产品的最低库存量。
1. 将推荐配置为仅显示满足特定条件的项目。

   您可以指定仅当列表中的某个属性符合或不符合一个或多个指定的条件时才包含项目。

   可用的计算器取决于您在第一个下拉列表中选择的值。您可以列出多个项目。这些项目会使用“或”进行评估。

   多个规则会使用“与”连接在一起。

   >[!NOTE]
   >
   >此选项限制了在推荐中显示的项目数。它不影响推荐在哪些页面上显示。要限制显示推荐的位置，请在体验编辑器中选择页面。

有关详细信息，请参阅[使用动态和静态包含规则](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)。

## 属性权重 {#weighting}

您可以添加多个规则，以根据有关内容目录的重要信息或元数据“轻推”算法，以便更有可能显示某些项目。

例如，您可以对预售项目应用较高的权重，以便它们更频繁地出现在推荐中。 非促销项目不会完全排除，但它们的显示频率会降低。可以将多个加权属性应用到同一算法，并且可以在推荐中对拆分流量测试加权属性。

1. 选择一个值。

   该值会根据多个可用标准中的一个标准确定更有可能显示的项目类型。

1. 选择计算器。

1. 键入关键字以完成规则属性。

   例如，完整的规则可以是“类别包含子字符串鞋子”。

1. 选择要分配给规则的权重。

   选项介于 0 到 100 之间，增量为 25。

1. 如果需要，添加其他规则。

完成后，单击&#x200B;**[!UICONTROL Create]**。

如果您正在创建新[!UICONTROL Recommendations]活动或编辑现有活动，则默认情况下会选中&#x200B;**[!UICONTROL Save criteria for later]**&#x200B;复选框。 如果您不想在其他活动中使用该标准，请在保存前清除该复选框。

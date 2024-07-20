---
keywords: 推荐算法；模型训练；模型提供；内容交付；基于项目；基于用户；基于热门程度；基于购物车；自定义标准
description: 了解 [!DNL Target Recommendations]中使用的算法，包括模型训练和模型服务。
title: 我可以在何处了解Target的Recommendations算法背后的科学原理？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '2739'
ht-degree: 0%

---

# Target 的推荐算法背后的科学原理

对[!DNL Adobe Target Recommendations]中使用的算法的深入描述，包括模型训练的逻辑和数学细节以及模型服务的过程。

模型训练是[!DNL Adobe Target]学习算法生成推荐的过程。 模型服务是[!DNL Target]如何向网站访客提供推荐（也称为内容交付）。

[!DNL Target]在[!DNL Recommendations]中包含以下各种类型的算法：

* **基于项目的算法**：包含遵循以下逻辑的算法：“查看/购买此项目的用户也查看/购买了这些项目”。 这些算法被分组到伞形术语“项目 — 项目协同筛选”以及[!UICONTROL Items with Similar Attributes]算法下。

* **基于用户的算法**：包含[!UICONTROL Recently Viewed]和[!UICONTROL Recommended for You]算法。

* **基于热门程度的算法**：包含返回网站中查看次数最多或购买次数最多的项目，或返回按类别或项目属性查看次数最多或购买次数最多的项目的算法。

* **基于购物车的算法**：包含基于多项目的推荐，其逻辑为“已查看/购买这些项目的用户也已查看/购买这些项目”。

* **自定义标准**：包含基于上载到[!DNL Target]的自定义文件的推荐。

>[!NOTE]
>
>有关每种算法类型和各个算法的更多常规信息，请参阅[使推荐基于推荐键](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

上面列出的许多算法都基于存在一个或多个键值。 这些键用于在内容交付时（提出推荐时）检索类似项目。 客户指定的键可以包括某位访客正在查看的当前项目、上次查看或购买的项目、最常查看的项目、当前类别或该访客最喜爱的类别。 其他算法（如基于购物车或基于用户的推荐）则使用隐式键（客户无法配置）。 有关详细信息，请参阅[使推荐基于推荐键](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys)中的&#x200B;*推荐键*。 但请注意，这些键仅在模型服务时（内容交付）相关。 这些键不会影响“离线”或模型训练时间逻辑。

以下部分以与上述算法类型略有不同的方式分组算法。 下面的分组是基于模型训练逻辑的相似性。

## 项目 — 项目协同筛选

算法包括：

* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Item-Item协同过滤推荐算法基于这样一个思想，即应该使用许多用户的行为模式（因此是协作的）为给定项目提供有用的推荐（例如，筛选可能推荐项目的目录）。 虽然有许多不同的算法属于[协同过滤](https://en.wikipedia.org/wiki/Collaborative_filtering)的一般范围，但这些算法通常使用行为数据源作为输入。 在[!DNL Target Recommendations]中，这些输入是用户独特的项目查看和购买。

对于“已查看/购买此项目的用户也已查看/购买这些项目”算法，目标是计算所有项目对之间的相似度(A，B)。 对于给定的项目A，排名最前的推荐按照其相似度s(A，B)排序。

此类相似性的一个示例是项目之间的共存：购买两个项目的用户数量的简单计数。 虽然这种量度是直观的，但因为偏向于推荐热门项目，所以这种量度是天真的。 例如，如果在食品零售商大多数人都购买面包，则面包与所有物品的高共现率，但它不一定是很好的推荐。 [!DNL Target]改为使用更复杂的相似性量度，称为对数似然比(LLR)。 当两个项目A和B同时发生的概率与它们不同时发生的概率差别很大时，该数量就很大。 如需具体信息，请考虑[!UICONTROL People Who Viewed This, Bought That]算法的情况。 当购买B的概率为&#x200B;*而非*&#x200B;时，LLR相似性很大，这与某人是否查看A无关。

例如，如果

已查看/已购买算法的![公式](assets/formula.png)

则不应将项目B与项目A一起推荐。此PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)中提供了[此对数似然比相似度计算的完整详细信息。

实际算法实现的逻辑流程如下图所示：

已查看/已购买算法的![示意图](assets/diagram1.png)

这些步骤的详情如下：

* **输入数据**：行为数据，其形式为当您[实施Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}或从[Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}收集的访客的视图和购买。

* **模型训练**：

   * **数据清理和采样**：对于具有N天回溯的算法，将首先过滤行为数据以仅包括这N天的数据。 然后，应用收集规则和全局排除以删除任何不应推荐的项目。 最后，任何与1,000多个项目进行交互的访客都会将其使用数据采样到仅1,000个项目。
   * **项目相似度计算**：这是核心计算步骤：计算所有候选项目对的对数似然比相似度，并按此相似度得分对项目对进行排序。
   * **脱机筛选**：最后，应用任何其他适用的动态筛选器（例如，动态类别排除）。 执行此步骤后，预先计算的推荐将缓存在全局中以可供服务。

* **模型服务**：Recommendations内容是从[!DNL Target]的[全局“Edge”网络](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934)交付的。 向[!DNL Target]发出mbox请求并确定应将推荐内容交付到页面时，将从请求中解析或查找推荐算法的相应[项键](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys)的请求，然后用于检索在之前步骤中计算的推荐。 此时在呈现适当的[设计](/help/main/c-recommendations/c-design-overview/create-design.md)之前，将应用更多的动态筛选器。

## 内容相似度

包含的算法：

* [!UICONTROL Items with Similar Attributes]

在该类算法中，如果两个项目的名称和文本描述在语义上相似，则认为两个项目相关。 与大多数必须使用行为数据源的推荐算法不同，内容相似度算法使用产品目录中的元数据来推导项目之间的相似度。 因此，[!DNL Target]能够在所谓的“冷启动”场景中推动推荐，在这种场景中，未收集到任何行为数据（例如，在[!DNL Target]活动开始时）。

虽然[!DNL Target]的内容相似度算法的模型服务和内容交付方面与其他基于项目的算法相同，但模型训练步骤却截然不同，涉及一系列自然语言处理和预处理步骤，如下图所示。 相似度计算的核心是利用修改后的tf-idf向量余弦相似度来表示目录中的每个项目。

![显示内容相似度流程流的图表](assets/diagram2.png)

这些步骤的详情如下：

* **输入数据**：如前所述，此算法完全基于目录数据(通过[目录馈送、实体API摄取到[!DNL Target]，或来自页面更新](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}。

* **模型训练**：

   * **属性提取**：在应用常规静态筛选器、目录规则和全局排除项后，此算法将从实体架构中提取相关文本字段。 [!DNL Target]自动使用实体属性中的名称、消息和类别字段，并尝试从自定义[实体属性](/help/main/c-recommendations/c-products/entity-attributes.md)中提取任何字符串字段。 通过确保该字段的大部分值不可作为数字、日期或布尔值分析，可完成此过程。
   * **词干和停用词删除**：为了更精确的文本相似度匹配，请谨慎地删除不会显着改变项含义的非常常见的“停用词”（例如，“was”、“is”、“and”等）。 同样，词干是指将具有不同后缀的单词缩减到其根单词的过程，根单词具有相同的含义（例如，“connect”、“connecting”和“connection”都具有相同的根单词：“connect”）。 [!DNL Target]使用Snowball词干器。 [!DNL Target]首先执行自动语言检测，并且最多可以删除50种语言的停止词，并为18种语言生成词根。
   * **n-gram创建**：在前面的步骤之后，每个单词都被视为一个令牌。 将令牌的连续序列组合成单个令牌的过程称为n-gram创建。 [!DNL Target]的算法考虑的量最多为2克。
   * **tf-idf计算**：下一步涉及创建tf-idf矢量以反映项描述中令牌的相对重要性。 对于项目i中的每个令牌/术语t，使用的目录D |D| 项，首先计算项频率TF(t，i)（项出现在项i中的次数）以及文档频率DF(t，D)。 实质上，存在令牌的项目数。 则tf-idf度量为

     ![显示tf-idf度量的公式](assets/formula2.png)

     [!DNL Target]使用Apache Spark的&#x200B;*tf-idf*&#x200B;功能实现，该实现将每个令牌散列为218个令牌。 在此步骤中，还通过根据[标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)中指定的设置调整每个矢量中的词频来应用客户指定的属性升序和埋葬。

   * **项相似度计算**：最终项相似度计算使用近似余弦相似度进行。 对于包含向量tA和tB的两个项目&#x200B;*A*&#x200B;和&#x200B;*B*，余弦相似度定义为：

     ![显示项目相似度计算的公式](assets/formula3.png)

     为了避免计算所有N x N项之间相似度的巨大复杂性，*tf-idf*&#x200B;矢量被截断为仅包含其最大的500个项，然后使用此截断矢量表示计算项之间的余弦相似度。 与其他近似最近邻(ANN)算法相比，该算法对稀疏向量相似度计算具有更好的鲁棒性。

   * **模型服务**：此过程与上一节中介绍的项目项协同筛选技术相同。

## 多键建议

算法包括：

* 基于购物车的推荐
* [!UICONTROL Recommended For You]

对[!DNL Target]推荐算法套件的最新添加为[!UICONTROL Recommended For You]和一系列基于购物车的推荐算法。 这两种算法都使用协同过滤技术来形成基于项目的个人推荐。 然后，在服务时，用户的浏览历史记录（对于[!UICONTROL Recommended For You]）或用户当前购物车（对于基于购物车的推荐）中的多个项目用于检索这些基于项目的推荐，然后将这些项目合并以形成推荐的最终列表。 请注意，存在多种风格的个性化推荐算法。 多键算法的选择意味着，当访客有任何浏览历史记录后，即可立即使用推荐，并且推荐可以更新以响应最新的访客行为。

这些算法基于在基于项目的推荐部分中描述的基本协同过滤技术构建，并且还结合超参数调整来确定项目之间的最佳相似度量度。 该算法对每个用户的行为数据执行时间顺序分割，并在试图预测用户稍后查看或购买的项目时训练关于较早数据的推荐模型。 然后选择生成最佳[平均平均精度](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval))的相似性度量。

模型训练和评分步骤的逻辑如下图所示：

![显示模型训练和评分步骤逻辑的图表](assets/diagram3.png)

这些步骤的详情如下：

* **输入数据**：这与项 — 项协同筛选(CF)方法相同。 [!UICONTROL Both Recommended For You]和基于购物车的算法使用行为数据，其形式为当您[实施Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}或从[Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}中收集的用户查看和购买。

* **模型训练**：

   * **数据清理和采样**：这再次与协作过滤方法相同，后者应用回顾窗口将行为数据过滤到适当的日期范围，然后应用目录规则和全局排除。 与超过1,000个项目交互的访客仅考虑其最近的1,000个使用情况。
   * **训练测试拆分**：为每个用户执行使用情况的按时间顺序拆分，将其使用情况的前80%分配给训练数据，其余20%分配给测试数据。
   * **项目相似度模型训练**： [!UICONTROL Recommended For You]和基于Cart的算法的核心项目相似度计算在构建候选项目向量的方式上有所不同。 对于[!UICONTROL Recommended For You]，项向量具有维度NUsers，其中每个条目表示该项用户的隐式评级之和 — 为项购买赋予的权重是该项查看次数的2倍。 对于基于购物车的推荐，项目矢量具有二进制条目；如果只考虑会话内行为，则每个会话都有一个新条目。 否则，每个访客在此项目矢量中都有一个条目。

  训练步骤计算几种类型的向量相似度：这里讨论的LLR相似度([](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf))、余弦相似度（以前定义）和规范化的L2相似度(定义为：

  ![显示训练计算的公式](assets/formula4.png)

   * **项目相似度模型评估**：模型评估是通过采用上一步中生成的建议并对测试数据集进行预测来完成的。 通过按时间顺序排序测试数据集中的每个用户的项目使用情况，然后为排序的项目子集提出100个推荐，以尝试预测随后的查看和购买，来模拟在线评分阶段。 信息检索量度[平均平均精度](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval))用于评估这些推荐的质量。 此量度会考虑推荐的顺序，并有利于在推荐列表中排名较高的相关项目，这是排名系统的重要属性。
   * **模型选择**：离线评估后，选择具有最高平均精确度的模型，并为其计算所有单个项推荐。
   * **脱机筛选**：模型训练的最后阶段是应用任何适用的动态筛选器。 执行此步骤后，预先计算的推荐将缓存在全局中以可供服务。

* **模型服务**：与以前的算法不同，以前的算法服务推荐涉及为检索指定单个键，然后应用业务规则，[!UICONTROL Recommended for You]和基于Cart的算法采用更复杂的运行时过程。

   * **多键检索和合并**：对于基于购物车的推荐，最多将购物车中传递的10个项目视为检索的键，并且每个推荐的权重相等。 对于[!UICONTROL Recommended for You]，最多可以将最近五个唯一查看的项目和最近五个唯一购买的项目视为检索键，其中来自购买项目的推荐的权重是来自查看项目的推荐的两倍。 在合并推荐时，如果一个项目出现在多个推荐的单个列表中，则会添加其加权相似度分数。 此阶段的最终推荐列表是随后合并的重新加权推荐列表，按降序排列。
   * **正在筛选**：下一步，将应用筛选规则，例如删除以前查看和/或购买的项目，以及其他动态业务规则。

下图说明了这些流程，其中访客查看了项目A并购买了项目B。系统会使用每个项目标签下显示的离线相似度得分来检索各个推荐。 检索后，将推荐与加权相似度得分相加。 最后，在客户已指定必须过滤掉以前查看过的和购买过的项目的场景中，过滤步骤将从推荐列表中删除项目A和B。

![显示多键算法处理的图表](assets/diagram4.png)

## 基于热门程度

算法包括：

* [!UICONTROL Most Viewed Across the Site]
* [!UICONTROL Most Viewed by Category]
* [!UICONTROL Most Viewed by Item Attribute]
* [!UICONTROL Top Sellers Across the Site]
* [!UICONTROL Top Sellers by Category]
* [!UICONTROL Top Sellers by Item Attribute]

[!DNL Target]为网站中查看次数最多的项目以及最畅销的项目，或按项目属性或类别细分的项目提供了基于热门程度的算法。 基于热门程度的算法根据在给定时间范围内查看或购买该项目的会话数对项目进行排名。

所有这些算法都整合了聚合的行为数据，即以每小时和每日分辨率记录查看并购买项目的会话总数。 然后，各个算法会找到客户配置的回顾时间范围内查看次数最多或购买次数最多的项目。

各个算法的细微差别如下：

* [!UICONTROL Most Viewed Across the Site]和[!UICONTROL Top Sellers Across the Site]按已查看或购买项目的会话的聚合计数对项目进行排名。 输出是推荐项目的单个（无键）列表。
* 按类别/项目属性显示的“查看次数最多”/“最畅销商品”是一些推荐，其中项目按查看或购买这些项目的会话的聚合计数排序，但按项目类别或特定项目属性分组。 输出是推荐项目的列表，由类别值或项目属性值键控。

## 最近查看的项目

“最近查看的”推荐算法允许对推荐进行会话内个性化。 此算法不需要离线“模型训练”。 相反，[!DNL Target]使用唯一的[访客配置文件](/help/main/c-target/c-visitor-profile/visitor-profile.md)来维护在给定会话中查看过并且可以在推荐活动中显示这些项目的运行列表。 这样可实时更新推荐和下一页面个性化。

## 自定义标准

自定义标准允许客户[将自己的推荐 [!DNL Target]](/help/main/c-recommendations/c-algorithms/recommendations-csv.md)上传到，这提供了很大的灵活性，并允许“自带模型”功能。 自定义标准取代了[!UICONTROL Item-Based]个推荐的“离线培训”部分，但在在线内容交付阶段其行为与基于项目的推荐算法类似，即使用一个键来检索推荐，然后应用业务规则/过滤器。

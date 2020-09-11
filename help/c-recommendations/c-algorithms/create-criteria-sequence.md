---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;
description: 使用最多五个标准的序列对您的Adobe TargetRecommendations活动中显示的项目进行更大控制。
title: 创建标准序列
feature: criteria
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: 381c405e55475f2474881541698d69b87eddf6fb
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 44%

---


# ![PREMIUM](/help/assets/premium.png) 创建标准序列

可使用最多包含五个标准的序列来加强对“[!UICONTROL 推荐]”活动中显示的项目的控制。

>[!NOTE]
>
>标准序列不能用于 [!UICONTROL  2016 年 10 月版发行之前创建的]推荐[!DNL Target Premium]活动。

要创建标准序列，您必须先创建要包含到序列中的标准。请参阅[创建标准](/help/c-recommendations/c-algorithms/create-new-algorithm.md)，以了解更多信息。

在单个标准无法返回足够多的结果，从而无法填充设计的情况下，通过使用标准序列，您可以提供更多具有针对性的推荐，而不是使用更为宽泛的备用推荐。通常，条件序列将从返回较少结果的更具体定位继续到通常返回较多结果的更具体定位。

您的条件序列可能因页面类型而异，如下例所示：

| 页面类型 | 可能的序列顺序 |
| --- | --- |
| 产品页面 | <ol><li>基于当前项目，来自同一品牌</li><li>基于当前项目，来自所有品牌</li><li>基于内容相似性</li><li>基于最畅销商品</li><li>基于整个网站中查看次数最多的项目</li></ol> |
| 主页 | <ol><li>基于访客上次购买的项目 </li><li>基于访客最喜爱的项目</li><li>基于访客最喜爱的类别</li><li>基于最畅销商品</li><li>基于整个网站中查看次数最多的项目</li></ol> |

## 访问“创建条件序列”屏幕

可通过多种方式来访问“[!UICONTROL 创建标准序列]”屏幕。某些屏幕选项会根据您访问该屏幕的方式而有所不同。

* 在&#x200B;**[!UICONTROL 推荐]** > **[!UICONTROL 标准]**&#x200B;库屏幕上，单击&#x200B;**[!UICONTROL 创建标准]** > **[!UICONTROL 创建标准序列]**。您在此处创建的标准会自动设置为可用于所有“[!UICONTROL 推荐]”活动。
* 创建Recommendations [!UICONTROL 活动时] ，在“选择条件”屏幕中，单击 **[!UICONTROL “新建]** ”>“ **[!UICONTROL 创建条件序列”]**。 您将可以选择保存新建的标准序列，以供在其他“[!UICONTROL 推荐]”活动中使用。
* When you are editing a [!UICONTROL Recommendations] activity, click in a [!UICONTROL Recommendations Location] box on your page, then select **[!UICONTROL Change Criteria]**. 在“[!UICONTROL 选择标准]”屏幕上，单击&#x200B;**[!UICONTROL 新建]** > **[!UICONTROL 创建标准序列]**。您将可以选择保存新建的标准，以供在其他“[!UICONTROL 推荐]”活动中使用。

以下步骤假定您使用第 [!UICONTROL 一种方法访问] “创建条件序列”屏幕：“ **[!UICONTROL Recommendations]** > **[!UICONTROL 标准]** ”库屏幕。

1. 单击 **[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**。

1. 单击 **[!UICONTROL 创建条件]** >创 **[!UICONTROL 建条件序列]**。

   ![](assets/CreateCriteriaSequence.png)

## 填写“信息”部分

1. 键入序列的&#x200B;**[!UICONTROL 名称]**。

   这是用于描述序列的“内部”名称。您的网站访客将不会看到此名称。

   ![“创建标准序列信息”部分](/help/c-recommendations/c-algorithms/assets/criteria-sequence-info.png)

1. 如果使用序列中的多个标准来填充&#x200B;**[!UICONTROL 推荐]**&#x200B;设计，请键入要在页面上显示的[!UICONTROL 通用显示标题]。

   例如，如果设计中可能包含基于多个“[!UICONTROL 推荐]”键的项目，您可能希望将“查看了这个项目的客户也查看了...”替换为“为您推荐”。

1. 键入对标准序列的简短&#x200B;**[!UICONTROL 描述]**。

   说明应帮助您确定标准序列，并可能包含有关其用途的信息。

1. 根据推荐活动的目标选择行业垂直。

   | 垂直行业 | 目标 |
   |--- |--- |
   | 零售/电子商务 | 转化促进完成购买 |
   | 潜在客户拓展/B2B/金融服务 | 转化但不购买 |
   | 媒体/出版 | 参与度 |

   系统会自动显示默认垂直行业。

   根据您选择的垂直行业，其他标准选项将会发生相应的更改。

1. 选择&#x200B;**[!UICONTROL 页面类型]**。

   您可以选择多个页面类型。

   垂直行业和页面类型可一起用于对已保存的标准序列进行分类，从而使其更易于在其他“[!UICONTROL 推荐]”活动中重复使用。

## 创建序列 {#sequence}

顺序定义设计的填充顺序。 如果标准1没有足够的建议来填充您的设计，则其余的插槽将填充标准2等。

1. 在“标准 **[!UICONTROL 序列]** ”部分，单 **[!UICONTROL 击“添加标准”]**。

   ![添加条件](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. On the [!UICONTROL Select Criteria] screen, select a criteria.

   您可以使用搜索框和筛选器下拉菜单来查找所需的条件。

   ![选择标准](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. 单击&#x200B;**[!UICONTROL 添加]**。

1. （可选）滑动 **[!UICONTROL 限制返回的项目数]** ，切换到“开启”位置，然后指定项目数（1到50）。

   ![限制返回的项目数切换](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   为了帮助您了解“限制返回 [!UICONTROL 的项目数”选项的值] ，请考虑以下用例：

   * **用例1**:您希望在单个推荐托盘中混合使用各种不同的项目。 例如，您希望展示混搭的外套（夹克）和上衣（衬衫、T恤）。 要实现此目的，请将集合用于活动，该集合包括您设计的任何插槽中所需的所有潜在产品类型。 然后，使用静态过滤器设置您的第一个标准，该静态过滤器将标准限制为仅包括外饰；使用静态过滤器设置第二个标准，该静态过滤器将标准限制为仅包括顶部。 最后，将两个标准添加到标准序列，并将第一个标准限制为2个插槽。

      推荐托盘在您的站点上可能如下所示：

      ![特色产品推荐托盘](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **用例2**:您希望混合使用替代项目和补充项目。 设置一个条件以使用已查看／已查看的算法，并使用动态筛选器将建议的项目限制为当前项目的类别。 设置第二个条件以使用已查看／已购买的算法，并使用动态筛选器，该过滤器仅包含与当前项目类别不匹配的推荐项目。 最后，将两个条件添加到序列，并将第一个条件限制为2个插槽。

1. 继续为序列添加其他条件。 您最多可以在一个序列中添加五个标准。

## 指定备份内容

当没有足够的推荐可用于填充设计模板时，选择返回的内容。

创建标准序列时，构成序列的单个标准所具有的备用推荐和局部设计渲染设置将被忽略。要使用备用推荐和局部设计渲染，您必须为序列启用这两项功能。选择相应的切换开关。如果您选择允许使用备用推荐，则还可以选择是否要对备用推荐应用包含规则。

![备份内容设置](/help/c-recommendations/c-algorithms/assets/backup-content-settings.png)

1. （可选）将“部 **[!UICONTROL 分设计渲染]** ”切换滑至“开启”位置。

   将尽可能多地填充插槽，但设计模板可能包括剩余插槽的空白空间。

1. （可选）将备份 **[!UICONTROL Recommendations]** 切换到“打开”位置。

   从您网站中随机选择查看次数最多的产品，填充设计中剩余的空白插槽。

   有关详细信息，请参 [阅使用备份建议](/help/c-recommendations/c-algorithms/backup-recs.md)。

1. （视情况而定）如果您在上 **[!UICONTROL 一步中选]** 择了备份Recommendations **[!UICONTROL ，则可以选择将包含]**&#x200B;规则应用于备份建议。

   For more information see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

1. 单击&#x200B;**[!UICONTROL 保存]**。

   标准序列随即会显示在“标准”列表中。

   有关推荐逻辑选项的更多信息，请参阅[标准](../../c-recommendations/c-algorithms/algorithms.md)。

## 培训视频：在“推荐”中创建标准 (12:33) ![教程徽章](/help/assets/tutorial.png)

本视频包含以下信息：

* 创建标准
* 创建标准序列
* 上传自定义标准

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)

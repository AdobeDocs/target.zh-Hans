---
keywords: 标准序列；多标准；算法；标准；推荐标准；序列；返回的项目数限制；插槽级别控制；插槽
description: 了解如何设置多达五个标准的序列，以更好地控制在您的Adobe TargetRecommendations活动中显示的项目。
title: 如何在Recommendations创建标准序列？
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 34%

---


# ![PREMIUM](/help/assets/premium.png) 创建标准序列

可使用最多包含五个标准的序列来加强对“[!UICONTROL 推荐]”活动中显示的项目的控制。您还可以限制返回的项目数（有时称为“插槽级别控制”）。

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

## 创建条件序列

可从[!UICONTROL 创建条件序列]屏幕创建条件序列。

可通过多种方式来访问“[!UICONTROL 创建标准序列]”屏幕。某些屏幕选项会根据您访问该屏幕的方式而有所不同。

* 在&#x200B;**[!UICONTROL 推荐]** > **[!UICONTROL 标准]**&#x200B;库屏幕上，单击&#x200B;**[!UICONTROL 创建标准]** > **[!UICONTROL 创建标准序列]**。您在此处创建的标准会自动设置为可用于所有“[!UICONTROL 推荐]”活动。
* 创建[!UICONTROL Recommendations]活动时，从“选择标准”屏幕中，单击“新建”]**>“创建标准序列”]**。 **[!UICONTROL **[!UICONTROL &#x200B;您将可以选择保存新建的标准序列，以供在其他“[!UICONTROL 推荐]”活动中使用。
* 编辑[!UICONTROL Recommendations]活动时，单击页面上的[!UICONTROL Recommendations位置]框，然后选择&#x200B;**[!UICONTROL 更改条件]**。 在“[!UICONTROL 选择标准]”屏幕上，单击&#x200B;**[!UICONTROL 新建]** > **[!UICONTROL 创建标准序列]**。您将可以选择保存新建的标准，以供在其他“[!UICONTROL 推荐]”活动中使用。

以下步骤假定您使用第一种方法访问[!UICONTROL 创建条件序列]屏幕：**[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**&#x200B;库屏幕。

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**。

1. 单击&#x200B;**[!UICONTROL 创建条件]** > **[!UICONTROL 创建条件序列]**。

   ![](assets/CreateCriteriaSequence.png)

1. 填写[基本信息](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info)部分中的信息。

1. 在&#x200B;**[!UICONTROL 标准序列]**&#x200B;部分，单击&#x200B;**[!UICONTROL 添加标准]**。

   顺序定义设计的填充顺序。 如果标准1没有足够的建议来填充您的设计，则其余的插槽将填充标准2等。

   ![添加条件](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. 在[!UICONTROL 选择条件]屏幕上，选择一个条件，然后单击&#x200B;**[!UICONTROL 添加]**。

   您可以使用搜索框和筛选器下拉菜单来查找所需的条件。

   ![选择标准](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. （可选）滑动&#x200B;**[!UICONTROL 限制返回的项数]**&#x200B;切换到“开启”位置，然后指定项数（1到50）。

   ![限制返回的项目数切换](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   为了帮助您理解[!UICONTROL 限制返回的项数]选项（有时称为“插槽级别控制”）的值，请考虑以下用例：

   * **用例1**:您希望在单个推荐托盘中混合使用各种不同的项目。例如，您希望展示混搭的外套（夹克）和上衣（衬衫、T恤）。 要实现此目的，请将集合用于活动，该集合包括您设计的任何插槽中所需的所有潜在产品类型。 然后，使用静态过滤器设置您的第一个标准，该静态过滤器将标准限制为仅包括外饰；使用静态过滤器设置第二个标准，该静态过滤器将标准限制为仅包括顶部。 最后，将两个标准添加到标准序列，并将第一个标准限制为2个插槽。

      推荐托盘在您的站点上可能如下所示：

      ![特色产品推荐托盘](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **用例2**:您希望混合使用替代项目和补充项目。设置一个条件以使用已查看／已查看的算法，并使用动态筛选器将建议的项目限制为当前项目的类别。 设置第二个条件以使用已查看／已购买的算法，并使用动态筛选器，该过滤器仅包含与当前项目类别不匹配的推荐项目。 最后，将两个条件添加到序列，并将第一个条件限制为2个插槽。

1. 继续为序列添加其他条件。 您最多可以在一个序列中添加五个标准。

1. 启用[备份内容选项](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)。

1. 单击&#x200B;**[!UICONTROL 保存]**。

   标准序列随即会显示在“标准”列表中。

   有关推荐逻辑选项的更多信息，请参阅[标准](/help/c-recommendations/c-algorithms/algorithms.md)。

## 培训视频：在“推荐”中创建标准 (12:33)  ![教程徽章](/help/assets/tutorial.png)

本视频包含以下信息：

* 创建标准
* 创建标准序列
* 上传自定义标准

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)

---
keywords: 标准序列；多个标准；算法；标准；推荐标准；序列；限制返回的项目数；槽级控制；槽
description: 了解如何设置最多包含五个标准的序列，以便更好地控制Recommendations活动中显示的项目。
title: 如何在Recommendations中创建标准序列？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: c8b0e0414603761b1c67b13d74ffa96d745c99e3
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 18%

---

# 创建标准序列

可使用最多包含五个条件的序列来加强对[!DNL Adobe Target] [!UICONTROL Recommendations]活动中显示的项目的控制。 您还可以限制返回的项目数（有时称为“槽级控制”）。

>[!NOTE]
>
>标准序列不能用于[!DNL Target Premium]的2016年10月版之前创建的[!UICONTROL Recommendations]活动。

要创建标准序列，您必须先创建要包含到序列中的标准。有关详细信息，请参阅[创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。

在单个标准无法返回足够多的结果，从而无法填充设计的情况下，通过使用标准序列，您可以提供更多具有针对性的推荐，而不是使用更为宽泛的备用推荐。通常，标准序列会从更具体的定位（可能会返回更少的结果）到更一般的定位（通常返回更多结果）。

您的标准序列可能会因页面类型的不同而有所不同，如以下示例中所示：

| 页面类型 | 可能的序列顺序 |
| --- | --- |
| 产品页面 | <ol><li>基于当前项目，来自同一品牌</li><li>基于当前项目，来自所有品牌</li><li>基于内容相似性</li><li>基于最畅销商品</li><li>基于整个网站中查看次数最多的项目</li></ol> |
| 主页 | <ol><li>基于访客上次购买的项目 </li><li>基于访客最喜爱的项目</li><li>基于访客最喜爱的类别</li><li>基于最畅销商品</li><li>基于整个网站中查看次数最多的项目</li></ol> |

## 创建标准序列

您可以从[!UICONTROL Create Criteria Sequence]屏幕创建标准序列。

可通过多种方式访问[!UICONTROL Create Criteria Sequence]屏幕。 某些屏幕选项会根据您访问该屏幕的方式而有所不同。

* 在&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;库屏幕上，单击&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**。 您在此处创建的标准会自动设置为可用于所有 [!UICONTROL Recommendations] 活动。
* 创建[!UICONTROL Recommendations]活动时，从[!UICONTROL Select Criteria]屏幕中，单击&#x200B;**[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**。 您可以选择保存新建的标准序列，以供在其他[!UICONTROL Recommendations]活动中使用。
* 编辑[!UICONTROL Recommendations]活动时，在页面上的[!UICONTROL Recommendations Location]框中单击，然后选择&#x200B;**[!UICONTROL Change Criteria]**。 在[!UICONTROL Select Criteria]屏幕上，单击&#x200B;**[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**。 您可以选择保存新建的标准，以供在其他[!UICONTROL Recommendations]活动中使用。

以下步骤假定您使用第一个方法访问[!UICONTROL Create Criteria Sequence]屏幕： **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;库屏幕。

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**。

1. 单击&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**。

1. 在[基本信息](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)部分中填写信息。

1. 在&#x200B;**[!UICONTROL Criteria Sequence]**&#x200B;部分中，单击加号( + )以添加一个或多个标准序列。

   序列顺序定义设计填充的顺序。 如果标准1没有足够的推荐项来填充您的设计，则剩余的版块将使用标准2来填充，依此类推。

1. 在[!UICONTROL Select Criteria]屏幕上，选择一个标准，然后单击&#x200B;**[!UICONTROL Save]**。

   您可以使用[!UICONTROL Search]框和筛选器选项来查找所需的条件。

1. （可选）将&#x200B;**[!UICONTROL Limit the number of items returned]**&#x200B;切换开关滑动到“开”位置，然后指定项目数（介于1和50之间）。

   为了帮助您了解[!UICONTROL Limit the number of items returned]选项（有时称为“插槽级别控制”）的值，请考虑以下用例：

   * **用例1**：您希望在单个推荐托盘中混合使用不同种类的项目。 例如，您希望显示外套（夹克）和上衣（衬衫、T恤）的组合。 要实现此目的，请为活动使用收藏集，其中包含您希望在设计中的任何版块中使用的所有潜在产品类型。 然后，使用静态筛选器设置您的第一个标准，并将该标准限制为仅包含外套，并使用静态筛选器设置您的第二个标准，该筛选器将该标准限制为仅包含上衣。 最后，将两个标准添加到标准序列中，并将第一个标准限制为2个空位。

     在您的网站上，推荐栏可能如下所示：

     ![特色产品推荐任务栏](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **用例2**：您希望同时使用替代项和补充项。 设置一个条件以使用已查看/已查看的算法，并使用动态筛选器将推荐项目限制为当前项目的类别。 设置第二个条件以使用已查看/已购买算法，并使用仅包含与当前项目类别不匹配的推荐项目的动态筛选器。 最后，将两个标准添加到序列中，并将第一个标准限制为2个空位。

1. 继续向序列中添加其他标准。 您最多可以在一个序列中添加五个标准。

1. 启用[备份内容选项](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)。

1. 单击 **[!UICONTROL Create]**。

   条件序列显示在[!UICONTROL Criteria]列表中。

   有关推荐逻辑选项的更多信息，请参阅[标准](/help/main/c-recommendations/c-algorithms/algorithms.md)。
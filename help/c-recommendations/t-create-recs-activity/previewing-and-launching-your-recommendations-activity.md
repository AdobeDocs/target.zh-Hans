---
keywords: Recommendations;offer;preview;launch
description: '在创建包含Adobe Target·Recommendations优惠的Recommendations活动、A/B测试或体验定位(XT)后，您需要对其进行预览，以确保在启动该活动之前可以获得结果。 目标Recommendations优惠了多种预览建议的方法。 '
title: '在创建包含Adobe Target·Recommendations优惠的Recommendations活动、A/B测试或体验定位(XT)后，您需要对其进行预览，以确保在启动该活动之前可以获得结果。 目标Recommendations优惠了多种预览建议的方法。 '
feature: recs creation
subtopic: Recommendations
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 19%

---


# 预览并启动您的Recommendations活动

在创建包含 [!UICONTROL Recommendations]、A [!UICONTROL /B测]试或体验定位(XT) [](/help/c-recommendations/recommendations-as-an-offer.md)活动后，您将希望预览您的建议，以确保在启动活动之前可以获得结果。 [!DNL Target Recommendations] 优惠多种预览推荐的方式。

## 检查Recommendations算法状态

创建活动后，运 [!DNL Recommendations] 行算法以生成推荐。 这个算法可能需要几个小时才能运行。

您可以在活动概述图中检查算法 [!UICONTROL 是否已] 完成运行，其中列出了条件状态。 下图显示了活动概述页上活动图 [!DNL Recommendations] 中的 [!UICONTROL 状态] :

![Recommendations活动概述页](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

下图描述了A/B测 [!UICONTROL 试或XT活动] “概述”页 [!UICONTROL 上的状] 态：

![“A/B测试概述”页](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

状态结果包括以下内容，如下所示：

* [!UICONTROL 结果就绪]:指示算法已返回结果
* [!UICONTROL 结果未就绪]:指示算法尚未完成运行。
* [!UICONTROL 源失败]:指示无法检索自定义条件源文件。

![结果对话框](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 算法要运行多长时间？

保存包含条件的活动后， [!DNL Target] 根据所选集合、条件、设计和促销计算推荐。 此计算需要一些时间来执行，并且时间范围因所选的推荐逻辑、数据范围、目录中的项目数、客户生成的行为数据量以及所选的行为数据源而有所不同。

行为数据源对处理时间的影响最大，如下所示：

### mboxes

如果选择 mbox 作为行为数据源，则标准在创建后会立即运行。根据使用的行为数据量和目录的大小，算法可能需要长达 12 个小时才能运行。对标准配置进行更改通常会导致算法重新运行。根据所做的更改，以前计算的推荐可能只有在重新运行完成后才可用，或者对于较大的更改，只有备份或默认内容才可用，直到重新运行完成。 如果未修改算法，则 [!DNL Target] 会根据所选的数据范围，每 12 到 48 小时自动重新运行该算法一次。

### Adobe Analytics

如果标准使用 [!DNL Adobe Analytics] 作为行为数据源，则创建标准后，其可用性的时间取决于所选报表包和回顾窗口是否已用于任何其他标准。

* **一次性报表包设置**：首次将报表包与给定数据范围回顾时间范围一起使用时，[!DNL Target Recommendations] 可能需要 2 到 7 天的时间才能从 [!DNL Analytics] 完全下载所选报表包的行为数据。此时间范围取决于 [!DNL Analytics] 系统负载。
* **使用已有可用的报表包新建或已编辑的条件**:在创建新标准或编辑现有标准时，如果选定的报表包已与之一起使用，且 [!DNL Target Recommendations]数据范围等于或小于选定的数据范围，则数据将立即可用，无需进行一次性设置。 在这种情况下，或者如果在未修改所选报表包或数据范围的情况下对算法的设置进行编辑，则该算法将在 12 小时内运行或者重新运行。
* **持续的算法运行**：数据每天从 [!DNL Analytics] 流向 [!DNL Target Recommendations]。例如，对于[!UICONTROL 已查看的亲和度]推荐，当用户查看产品时，产品查看跟踪调用将以近实时的方式传递到 [!DNL Analytics]。The [!DNL Analytics] data is pushed to [!DNL Target] early the next day and [!DNL Target] runs the algorithm in fewer than 12 hours.

>[!NOTE]
>
>[!UICONTROL “最近查看的项目] ”不需要运行脱机算法，结果即时可用。 [!UICONTROL 基于mbox][!UICONTROL 数据的Top Viewed] and Top Sellers算法通常由于计算更简单而生成结果非常快。 当您要预览设计更改或确认正确收集行为数据时，这些选项可能是不错的选择。

## 使用QA链接到预览Recommendations

在算法的结果准备就绪后，您可以使用的QA链接 [功能预览这](/help/c-activities/c-activity-qa/activity-qa.md) 些结果 [!DNL Adobe Target]。 QA链接位于活动概 [!UICONTROL 述页面的] “活动QA”部分：

![“活动 QA”链接](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>默认情况下， [!DNL Target] 会自动将您添加到QA链接的所需受众。 如果此设置已关闭，且活动具有定位规则，则用户用户档案需要满足这些定位规则才能查看包含推荐的体验。

使用QA链接可以预览页面上的推荐：

![特色产品](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>目标QA模式为“粘滞”并保存在cookie中。 如果不退出QA模式，您将在整个站点中继续看到QA结果。 要退出QA模式，请使用 [书签](/help/c-activities/c-activity-qa/activity-qa-bookmark.md)。

>[!NOTE]
>
>在QA模式下，浏览网站不会影响用户档案的“最近查看 [!UICONTROL 的物品] ” [!UICONTROL 或“最近购买的物品”]。这种行为是设计为避免无意污染生产行为数据。 要预览“最近查 [!UICONTROL 看的项目] ”或“ [!UICONTROL 基于用户的Recommendations”条件的结果] ，请首先在QA模式之外浏览站点，然后使用同一会话打开QA模式链接。

## 使用CSV下载来预览推荐

在某些情况下，您可能希望审核建议的特定项目。 当使用诸如“查看此、已查 [!UICONTROL 看的人员]”等算法时，这特别有用。在这些算法中，建议根据用户当前查看的项目设置不同的项目，并且您的目录中可能有数千或数百万个不同项目。

在活动中至少显示一个算 [!UICONTROL 法的“结果就绪] ”状态之前，不能下载结果。

要下载预览结果，请单击活动概述页面右上角的菜单图标，然后单击下载 **[!UICONTROL 数据]**。

![下载数据选项](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

下载CSV文件。 打开它以查看推荐的项目：

![推荐项目CSV文件](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

从左到右是推荐项目的列表，在此例中为最常查看的项目。 建议以环境分隔，在这种情况下，只有生产环境有建议。 对于此算法，我们没有根据键值应用任何限制，因此标有星号(*)的行包含整套推荐。 对于基于键值的其他算法类型 [!UICONTROL ，如“查看此项的人员”、“查看此项的人员”]，键值（即“此项”）列在最左侧的列中，建议项（即“此项”）从左至右列在Recommendation_X列中。

>[!NOTE]
>
>结果下载不适用于包含基于用户 [!UICONTROL 的Recommendations算法的活动] 。 使用“最近查看的项目”推荐逻辑时， [!UICONTROL 结果下载不适用于条] 件条件。

## 激活您的Recommendations活动

在“活动 [!UICONTROL 概述] ”选项卡中，单击状态旁的下拉箭头，然后选择“激 **[!UICONTROL 活”]**。

![激活选项](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

请注意，状态变为“激 [!UICONTROL 活”]:

![激活](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

几秒钟到几分钟后，状态将切换为“实时 [!UICONTROL ”]:

![实时](/help/c-recommendations/t-create-recs-activity/assets/live.png)

请注意，您也可以使用相同的下拉活动取消激活或存档列表。

## 在更改Recommendations设置时避免中断

在实 [!DNL Recommendations] 时活动中更改集合、条件、促销或设计设置可能会导致算法结果无效，并且算法的状态会更改为“结果 [!UICONTROL 未就绪”]。

为避免中断实时活动，我们建议在修改实时活动时采用以下方法：

1. 重复要修改的活动和条件。
1. 更改重复的活动和标准，并等待算法生成结果。
1. 预览新的修改活动，并确认结果符合要求。
1. 激活新活动。
1. 取消激活旧活动。

如果您需要在相同的报告中保留历史活动结果，则可能采用另一种方法，这可能导致建议可用性暂时中断：

1. 重复要修改的活动和条件。
1. 更改重复的活动和标准，并等待算法生成结果。
1. 预览新的修改活动，并确认结果符合要求。
1. 暂停现有活动，并将设置／条件交换为新条件。
1. 预览现有活动，并确认结果是否符合要求。
1. 重新激活活动。

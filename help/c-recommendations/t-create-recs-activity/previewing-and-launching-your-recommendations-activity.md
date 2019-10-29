---
description: '在创建了包含Recommendations选件的Recommendations、A/B测试或体验定位(XT)活动后，您需要预览该活动，以确保在启动活动之前可以使用结果。 Target Recommendations提供了多种预览推荐的方法。 '
keywords: 推荐；选件；预览；启动
seo-description: '在创建包含Adobe Target Recommendations选件的Recommendations、A/B测试或体验定位(XT)活动后，您需要预览该活动，以确保在启动活动之前可以获得结果。 Target Recommendations提供了多种预览推荐的方法。 '
seo-title: '在创建包含Adobe Target Recommendations选件的Recommendations、A/B测试或体验定位(XT)活动后，您需要预览该活动，以确保在启动活动之前可以获得结果。 Target Recommendations提供了多种预览推荐的方法。 '
solution: Target
subtopic: 推荐
title: 预览和启动Recommendations活动
title-outputclass: premium
topic: Premium
badge: premium
translation-type: tm+mt
source-git-commit: c503992671e3582acd65c1d1d0b9836074ddf898

---


# 预览并启动Recommendations活动

在您创建包含 [!UICONTROL Recommendations的]Recommendations、 [!UICONTROL A/B测试或][](/help/c-recommendations/recommendations-as-an-offer.md)Experience Targeting(XT)活动后，您将希望预览您的推荐，以确保在启动活动之前提供可用的结果。 [!DNL Target Recommendations] 提供了多种预览推荐的方式。

## 检查推荐算法状态

创建活动后，运 [!DNL Recommendations] 行算法以生成推荐。 这个算法可能需要几个小时才能运行。


![“推荐”活动“概述”页](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

下图描述了 [!UICONTROL A/B测试或XT活动的“概述] ”页面上的 [!UICONTROL 状态] :

![“A/B测试概述”页](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

状态结果包括以下内容，如下所示：

* [!UICONTROL 结果就绪]:指示算法已返回结果
* [!UICONTROL 结果未就绪]:指示算法尚未完成运行。
* [!UICONTROL 源失败]:指示无法检索自定义条件源文件。

![结果对话框](/help/c-recommendations/t-create-recs-activity/assets/results.png)

## 该算法需要多长时间才能运行？

保存包含条件的活动后，根 [!DNL Target] 据所选集合、条件、设计和促销计算推荐。 此计算需要一些时间来执行，并且时间范围因所选的推荐逻辑、数据范围、目录中的项目数、客户生成的行为数据量以及所选的行为数据源而有所不同。

行为数据源对处理时间的影响最大，如下所示：

### mboxes

如果选择 mbox 作为行为数据源，则标准在创建后会立即运行。根据使用的行为数据量和目录的大小，算法可能需要长达 12 个小时才能运行。对标准配置进行更改通常会导致算法重新运行。根据所做的更改，在重新运行完成之前，之前计算的推荐可能不可用，对于较大的更改，只有备份或默认内容才可用，直到重新运行完成。 如果未修改算法，则 [!DNL Target] 会根据所选的数据范围，每 12 到 48 小时自动重新运行该算法一次。

## Adobe Analytics

如果标准使用 [!DNL Adobe Analytics] 作为行为数据源，则创建标准后，其可用性的时间取决于所选报表包和回顾窗口是否已用于任何其他标准。

* **一次性报表包设置**：首次将报表包与给定数据范围回顾时间范围一起使用时，[!DNL Target Recommendations] 可能需要 2 到 7 天的时间才能从 [!DNL Analytics] 完全下载所选报表包的行为数据。此时间范围取决于 [!DNL Analytics] 系统负载。
* **使用已有可用的报表包新建或编辑的条件**:在创建新标准或编辑现有标准时，如果选定的报表包已与之一起使用，且数据范围等于或小于选定的数据范围，则数据将立即可用，并且不需要一次性设置。 [!DNL Target Recommendations]在这种情况下，或者如果在未修改所选报表包或数据范围的情况下对算法的设置进行编辑，则该算法将在 12 小时内运行或者重新运行。
* **持续的算法运行**：数据每天从 [!DNL Analytics] 流向 [!DNL Target Recommendations]。例如，对于[!UICONTROL 已查看的亲和度]推荐，当用户查看产品时，产品查看跟踪调用将以近实时的方式传递到 [!DNL Analytics]。The [!DNL Analytics] data is pushed to [!DNL Target] early the next day and [!DNL Target] runs the algorithm in fewer than 12 hours.

>[!NOTE]
>
>[!UICONTROL “最近查看的项目] ”不需要运行脱机算法，结果即时可用。 [!UICONTROL 基于mbox数据的Top] Viewed和 [!UICONTROL Top Sellers] （热门查看和热门销售者）算法通常由于计算更简单而产生结果的速度非常快。 当您要预览设计更改或确认正确收集行为数据时，这些选项可能是不错的选择。

## 使用QA链接预览推荐

在算法的结果准备就绪后，您可以使用的 [QA链接功能预览这些结果](/help/c-activities/c-activity-qa/activity-qa.md)[!DNL Adobe Target]。 QA链接位于“活动”概 [!UICONTROL 述页面的“活动] QA”部分：

![“活动 QA”链接](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>默认情况下， [!DNL Target] 会自动将您添加到QA链接的所需受众。 如果此设置处于关闭状态且您的活动具有定位规则，则您的用户配置文件需要满足这些定位规则才能查看包含推荐的体验。

使用QA链接可以预览页面上的推荐：

![特色产品](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>目标QA模式为“粘性”，并保存在Cookie中。 如果不退出QA模式，您将在整个站点中不断看到QA结果。 要退出QA模式，请使用书 [签工具](/help/c-activities/c-activity-qa/activity-qa-bookmark.md)。

>[!NOTE]
>
>在QA模式下，浏览站点不会影响配置文件的“最近查看的项目 [!UICONTROL ”或“最近购买的项目]”。此行为是通过设计来避免无意污染生产行为数据的。 要预览“最近查看的项 [!UICONTROL 目”或“基于用户的推荐] ”条件的结果，请首先在QA模式之外浏览站点，然后使用同一会话打开QA模式链接。

## 使用CSV下载预览推荐

在某些情况下，您可能希望审核建议的特定项目。 当使用“查看过此项、已查看的人员 ”等算法时，这特别有用。在这些算法中，建议根据用户当前查看的项目设置不同的项目集，并且您的目录中可能有数千或数百万个不同的项目。

在活动中至少显示一个算法的“结 [!UICONTROL 果就绪] ”状态之前，不能下载结果。

要下载预览结果，请单击“活动”概述页面右上角的菜单图标，然后单击“下载 **[!UICONTROL 数据”]**。

![下载数据选项](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

下载CSV文件。 打开它可查看建议的项目：

![推荐项目CSV文件](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

从左到右是推荐项目列表，在此例中为查看频率最高的项目。 建议按环境分隔，在这种情况下，只有生产环境有建议。 对于此算法，我们没有根据键值应用任何限制，因此标有星号(*)的行包含完整的推荐集。 对于基于键值的其他算法类型，如“查看此项的人” [!UICONTROL 、“查看此项的人”]，键值（即“此项”）列在最左侧的列中，推荐项（即“此项”）在Recommendation_X列中从左至右列出。

>[!NOTE]
>
>对于包含基于用户的推荐算法的活动， [!UICONTROL 结果下载不可用] 。 使用“最近查看的项目”推荐逻辑时，结果下 [!UICONTROL 载不适用于条件] 。

## 激活您的Recommendations活动

在“活 [!UICONTROL 动概述] ”选项卡中，单击状态旁边的下拉箭头，然后选择“激 **[!UICONTROL 活”]**。

![激活选项](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

请注意，状态将变为“激 [!UICONTROL 活”]:

![激活](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

几秒钟到几分钟后，状态将切换到“实 [!UICONTROL 时”]:

![实时](/help/c-recommendations/t-create-recs-activity/assets/live.png)

请注意，您也可以使用同一下拉列表取消激活或存档活动。

## 在更改“推荐”设置时避免中断

在实 [!DNL Recommendations] 时活动中更改集合、条件、促销或设计设置可能会导致算法结果无效，并且算法的状态会更改为“结 [!UICONTROL 果未就绪”]。

为避免中断实时活动，建议在修改实时活动时采用以下方法：

1. 复制要修改的活动和标准。
1. 更改重复的活动和标准并等待算法生成结果。
1. 预览新的修改活动并确认结果是否符合要求。
1. 激活新活动。
1. 取消激活旧活动。

如果您需要在同一活动中保留历史报告结果，则可能会采用另一种方法，这可能导致建议可用性暂时中断：

1. 复制要修改的活动和标准。
1. 更改重复的活动和标准并等待算法生成结果。
1. 预览新的修改活动并确认结果是否符合要求。
1. 暂停现有活动，并将设置／条件交换为新标准。
1. 预览现有活动并确认结果是否符合要求。
1. 重新激活活动。

---
keywords: Recommendations;优惠;预览；启动；状态；标准；算法
description: '了解如何预览Adobe [!DNL Target] Recommendations活动，以确保在启动活动之前结果可用。 '
title: 如何预览和启动Recommendations活动?
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 17%

---

# 预览并启动Recommendations活动

在创建包含[Recommendations优惠](/help/c-recommendations/recommendations-as-an-offer.md)的[!UICONTROL Recommendations]、[!UICONTROL A/B测试]或[!UICONTROL 体验定位](XT)活动后，您将希望预览您的建议，以确保在启动活动之前结果可用。 [!DNL Target Recommendations] 优惠多种预览建议的方法。

## 检查Recommendations算法状态

创建活动后，[!DNL Recommendations]运行算法以生成推荐。 此算法可能需要几个小时才能运行。

您可以在[!UICONTROL 活动]概述图中检查算法是否已完成运行，其中列出了条件状态。 下图显示了[!DNL Recommendations]活动的[!UICONTROL 概述]页面的活动图中的状态：

![Recommendations 活动概述页](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

下图描述了[!UICONTROL A/B Test]或XT活动的[!UICONTROL Overview]页面上的状态：

![“A/B测试概述”页](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

状态结果包括以下内容，如下所示：

* [!UICONTROL 结果就绪]:指示算法已返回结果
* [!UICONTROL 结果未就绪]:指示算法尚未完成运行。
* [!UICONTROL 源失败]:指示无法检索自定义条件源文件。

![结果对话框](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 算法要运行多长时间？

保存包含条件的活动后，[!DNL Target]会根据所选集合、条件、设计和促销计算推荐。 此计算需要一些时间才能执行，并且时间范围会根据所选推荐逻辑、数据范围、目录中的项目数、客户生成的行为数据量以及所选的行为数据源而有所不同。

行为数据源对处理时间的影响最大，如下所示：

### mboxes

如果选择 mbox 作为行为数据源，则标准在创建后会立即运行。根据使用的行为数据量和目录的大小，算法可能需要长达 12 个小时才能运行。对标准配置进行更改通常会导致算法重新运行。根据所做的更改，在重新运行完成之前，之前计算的推荐可能不可用，对于更大的更改，只有备份或默认内容才可用，直到重新运行完成。 如果未修改算法，则 [!DNL Target] 会根据所选的数据范围，每 12 到 48 小时自动重新运行该算法一次。

### Adobe Analytics

如果标准使用 [!DNL Adobe Analytics] 作为行为数据源，则创建标准后，其可用性的时间取决于所选报表包和回顾窗口是否已用于任何其他标准。

* **一次性报表包设置**：首次将报表包与给定数据范围回顾时间范围一起使用时，[!DNL Target Recommendations] 可能需要 2 到 7 天的时间才能从 [!DNL Analytics] 完全下载所选报表包的行为数据。此时间范围取决于 [!DNL Analytics] 系统负载。
* **使用已有可用的报表包新建或编辑的条件**:在创建新标准或编辑现有标准时，如果选定的报表包已与之一起使用，且数据范围等于或小于选定 [!DNL Target Recommendations]的数据范围，则数据将立即可用，无需一次性设置。在这种情况下，或者如果在未修改所选报表包或数据范围的情况下对算法的设置进行编辑，则该算法将在 12 小时内运行或者重新运行。
* **持续的算法运行**：数据每天从 [!DNL Analytics] 流向 [!DNL Target Recommendations]。例如，对于[!UICONTROL 已查看的亲和度]推荐，当用户查看产品时，产品查看跟踪调用将以近实时的方式传递到 [!DNL Analytics]。次日初将[!DNL Analytics]数据推送到[!DNL Target]，而[!DNL Target]在不到12小时内运行算法。

>[!NOTE]
>
>[!UICONTROL “最近查] 看的项目”不需要运行脱机算法，结果即时可用。[!UICONTROL 基于] mbox [!UICONTROL 数] 据的Top Viewed和Top Sellersal算法通常由于计算更简单而生成结果非常快。当您要预览设计更改或确认正确收集行为数据时，这些选项可能是不错的选择。

## 使用指向预览 Recommendations的QA链接

算法已准备好结果后，您可以使用[!DNL Adobe Target]的[QA link](/help/c-activities/c-activity-qa/activity-qa.md)功能预览这些结果。 QA链接位于活动概述页的[!UICONTROL 活动QA]部分：

![“活动 QA”链接](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>默认情况下，[!DNL Target]会自动将您添加到QA链接所需的受众。 如果此设置已关闭，且您的活动具有定位规则，则您的用户用户档案需要满足这些定位规则才能查看包含推荐的体验。

使用QA链接可以预览页面上的推荐：

![特色产品](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* 目标QA模式是“粘滞”，并保存在Cookie中。 如果您不退出QA模式，您将在整个站点中继续看到QA结果。 要退出QA模式，请使用[书签](/help/c-activities/c-activity-qa/activity-qa-bookmark.md)。
   >
   >
* 在QA模式下，浏览站点不会影响用户档案的[!UICONTROL 最近查看的项目]或[!UICONTROL 最近购买的项目]。&quot; 这种行为是通过设计来避免无意污染生产行为数据的。 要预览来自[!UICONTROL 最近查看的项目]或[!UICONTROL 基于用户的Recommendations]条件的结果，请首先在QA模式之外浏览站点，然后使用相同的会话打开QA模式链接。


## 使用CSV下载来预览推荐

在某些情况下，您可能希望审计建议的特定项目。 当使用[!UICONTROL 查看此、已查看的人员]等算法时，这特别有用，因为根据用户当前查看的项目，建议使用不同的项目集，并且目录中可能有数千或数百万个不同项目。

在活动中至少显示一个算法的[!UICONTROL 结果就绪]状态之前，不能下载结果。

要下载预览结果，请单击活动概述页面右上角的菜单图标，然后单击&#x200B;**[!UICONTROL 下载数据]**。

![下载数据选项](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

将下载CSV文件。 打开它以查看建议的项目：

![推荐项目CSV文件](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

从左到右是推荐项目的列表，在此例中为查看频率最高的项目。 这些建议以环境分隔，在这种情况下，只有生产环境有建议。 对于此算法，我们没有根据键值应用任何限制，因此标有星号(*)的行包含整套推荐。 对于基于键值的其他算法类型，如[!UICONTROL 查看此的人员，查看的那个]，键值（即“This”项）列在最左侧的列中，建议项（即“That”项）在Recommendation_X列中从左至右列出。

>[!NOTE]
>
>对于包含[!UICONTROL 基于用户的Recommendations]算法的活动，结果下载不可用。 使用[!UICONTROL 最近查看的项目]推荐逻辑的条件不提供结果下载。

## 激活Recommendations活动

在[!UICONTROL 活动概述]选项卡中，单击状态旁边的下拉箭头，然后选择&#x200B;**[!UICONTROL 激活]**。

![激活选项](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

请注意，状态将变为[!UICONTROL 激活]:

![激活](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

几秒钟后，状态将切换到[!UICONTROL Live]:

![实时](/help/c-recommendations/t-create-recs-activity/assets/live.png)

请注意，您也可以使用相同的下拉列表取消激活或存档活动。

## 在更改Recommendations设置时避免中断

在实时活动中更改[!DNL Recommendations]集合、条件、促销或设计设置可能会导致算法结果变为无效，并且算法的状态变为[!UICONTROL 结果未就绪]。

为避免中断实时活动，建议在修改实时活动时采用以下方法：

1. 重复要修改的活动和条件。
1. 更改重复的活动和标准，并等待算法生成结果。
1. 预览新的修改活动，并确认结果是否符合要求。
1. 激活新活动。
1. 取消激活旧活动。

如果您需要保留历史报告结果，则可能采用另一种方法，这可能导致建议可用性暂时中断：

1. 重复要修改的活动和条件。
1. 更改重复的活动和标准，并等待算法生成结果。
1. 预览新的修改活动，并确认结果是否符合要求。
1. 暂停现有活动，并将设置/条件切换到新标准。
1. 预览现有活动，并确认结果是否符合要求。
1. 重新激活活动。

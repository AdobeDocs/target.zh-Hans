---
keywords: Recommendations；选件；预览；启动；状态；标准；算法
description: '了解如何预览Adobe [!DNL Target] Recommendations活动，以确保在启动活动之前可以获得结果。 '
title: 如何预览和启动Recommendations活动？
feature: 推荐
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: f4972f04906cb3476f50abedd6cec847e015daf9
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 17%

---

# 预览和启动推荐活动

在创建[!UICONTROL Recommendations]、[!UICONTROL A/B测试]或[!UICONTROL 包含[Recommendations选件](/help/c-recommendations/recommendations-as-an-offer.md)的体验定位](XT)活动后，您将需要预览推荐，以确保在启动活动之前，结果可用。 [!DNL Target Recommendations] 提供了多种预览推荐的方法。

## 检查Recommendations算法状态

创建活动后，[!DNL Recommendations]会运行算法以生成推荐。 此算法可能需要几个小时才能运行。

您可以在[!UICONTROL Activity]概述图中检查算法是否已完成运行，其中列出了标准状态。 下图显示了[!DNL Recommendations]活动[!UICONTROL 概述]页面上的活动图中的状态：

![Recommendations活动概述页面](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

下图描述了[!UICONTROL A/B测试]或XT活动的[!UICONTROL 概述]页面上的状态：

![A/B测试概述页面](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

状态结果包括以下内容，如下图所示：

* [!UICONTROL 结果就绪]:指示算法已返回结果
* [!UICONTROL 结果未准备就绪]:表示算法尚未完成运行。
* [!UICONTROL 信息源失败]:指示无法检索自定义标准信息源文件。

![“结果”对话框](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 算法需要多长时间才能运行？

保存包含标准的活动后，[!DNL Target]会根据选定的收藏集、标准、设计和促销活动来计算推荐。 此计算需要一些时间来执行，并且时间范围因所选的推荐逻辑、数据范围、目录中的项目数、客户生成的行为数据量以及所选的行为数据源而异。

行为数据源对处理时间的影响最大，如下所示：

### mboxes

如果选择 mbox 作为行为数据源，则标准在创建后会立即运行。根据使用的行为数据量和目录的大小，算法可能需要长达 12 个小时才能运行。对标准配置进行更改通常会导致算法重新运行。根据所做的更改，之前计算的推荐可能只有在重新运行完成后才可用，或者对于较大的更改，只有备份或默认内容才可用，直到重新运行完成为止。 如果未修改算法，则 [!DNL Target] 会根据所选的数据范围，每 12 到 48 小时自动重新运行该算法一次。

### Adobe Analytics

如果标准使用 [!DNL Adobe Analytics] 作为行为数据源，则创建标准后，其可用性的时间取决于所选报表包和回顾窗口是否已用于任何其他标准。

* **一次性报表包设置**：首次将报表包与给定数据范围回顾时间范围一起使用时，[!DNL Target Recommendations] 可能需要 2 到 7 天的时间才能从 [!DNL Analytics] 完全下载所选报表包的行为数据。此时间范围取决于 [!DNL Analytics] 系统负载。
* **使用已有可用的报表包新建或编辑标准**:创建新标准或编辑现有标准时，如果选定的报表包已与一起使用，且数据范围等于或小于 [!DNL Target Recommendations]选定的数据范围，则数据将立即可用，而无需一次性设置。在这种情况下，或者如果在未修改所选报表包或数据范围的情况下对算法的设置进行编辑，则该算法将在 12 小时内运行或者重新运行。
* **持续的算法运行**：数据每天从 [!DNL Analytics] 流向 [!DNL Target Recommendations]。例如，对于[!UICONTROL 已查看的亲和度]推荐，当用户查看产品时，产品查看跟踪调用将以近实时的方式传递到 [!DNL Analytics]。次日早些时候，将[!DNL Analytics]数据推送到[!DNL Target]，并且[!DNL Target]会在12小时内运行算法。

>[!NOTE]
>
>[!UICONTROL “最近查看] 的项目”不需要运行离线算法，并且结果可立即获得。[!UICONTROL 基于] mbox [!UICONTROL 数] 据的热门查看和热门自助算法通常会由于所需的计算更简单而生成结果非常迅速。当您想要预览设计更改或确认正确收集行为数据时，这些选项可能很好。

## 使用QA链接预览Recommendations

算法准备就绪后，可以使用[!DNL Adobe Target]的[QA链接](/help/c-activities/c-activity-qa/activity-qa.md)功能预览这些结果。 “活动概述”页面的[!UICONTROL 活动QA]部分中提供了QA链接：

![“活动 QA”链接](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>默认情况下，[!DNL Target]会自动将您添加到QA链接的所需受众中。 如果关闭此设置，并且您的活动具有定位规则，则您的用户配置文件需要满足这些定位规则才能查看包含推荐的体验。

使用QA链接可预览页面上的推荐：

![特色产品](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Target QA模式是“粘滞”的，并保存在Cookie中。 如果不退出QA模式，您将在整个站点中继续看到QA结果。 要退出QA模式，请使用[书签](/help/c-activities/c-activity-qa/activity-qa-bookmark.md)。
   >
   >
* 在QA模式下，浏览网站将不会影响用户档案的[!UICONTROL 最近查看的项目]或[!UICONTROL 最近购买的项目]。 这种行为是通过设计来避免生产行为数据的无意污染的。 要预览[!UICONTROL 最近查看的项目]或[!UICONTROL 基于用户的Recommendations]标准的结果，请先浏览QA模式以外的站点，然后使用同一会话打开QA模式链接。


## 使用CSV下载预览推荐

在某些情况下，您可能需要审核推荐的特定项目。 当使用[!UICONTROL 查看了这个项目，也查看了那个项目的人]等算法时，这项功能会特别有用。在这些算法中，根据用户当前正在查看的项目，建议使用一组不同的项目，并且您的目录中可能有数千或数百万个不同的项目。

在活动中至少显示了一个算法的[!UICONTROL 结果就绪]状态后，才能下载结果。

要下载预览结果，请单击“活动概述”页面右上角的菜单图标，然后单击&#x200B;**[!UICONTROL 下载数据]**。

![下载数据选项](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

将下载CSV文件。 打开它以查看推荐的项目：

![推荐项目CSV文件](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

从左到右是推荐项目的列表，在此例中，推荐项目是最常查看的项目。 推荐按环境进行分隔，在这种情况下，只有生产环境具有推荐。 对于此算法，我们未根据键值应用任何限制，因此标有星号(*)的行包含整套推荐。 对于基于键值的其他算法类型，如[!UICONTROL 查看了此项的人员、查看了该项]，键值（即“此项”项目）列在最左侧的列中，推荐项目（即“此项”项目）从左至右列在Recommendation_X列中。

>[!NOTE]
>
>结果下载不适用于包含[!UICONTROL 基于用户的Recommendations]算法的活动。 使用[!UICONTROL 最近查看的项目]推荐逻辑的标准无法下载结果。

## 激活Recommendations活动

从[!UICONTROL Activity Overview]选项卡中，单击状态旁边的下拉箭头，然后选择&#x200B;**[!UICONTROL Activate]**。

![激活选项](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

请注意，状态将变为[!UICONTROL 激活]:

![激活](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

几秒钟到几分钟后，状态将切换到[!UICONTROL Live]:

![实时](/help/c-recommendations/t-create-recs-activity/assets/live.png)

请注意，您还可以使用同一下拉列表停用或存档活动。

## 避免更改Recommendations设置时出现中断

在实时活动中更改[!DNL Recommendations]收藏集、标准、促销活动或设计设置，可能会导致算法结果无效，并且算法状态更改为[!UICONTROL 结果未就绪]。

为避免中断实时活动，我们建议在修改实时活动时采取以下方法：

1. 复制要修改的活动和标准。
1. 对复制的活动和标准进行更改，然后等待算法生成结果。
1. 预览新的已修改活动，并确认结果是否符合要求。
1. 激活新活动。
1. 停用旧活动。

如果您需要在同一活动中保留历史报表结果，则可以采用另一种方法，这可能会临时中断推荐的可用性：

1. 复制要修改的活动和标准。
1. 对复制的活动和标准进行更改，然后等待算法生成结果。
1. 预览新的已修改活动，并确认结果是否符合要求。
1. 暂停现有活动，并将设置/标准交换到新标准。
1. 预览现有活动，并确认结果是否符合要求。
1. 重新激活活动。

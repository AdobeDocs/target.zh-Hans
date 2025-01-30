---
keywords: Recommendations；选件；预览；启动项；状态；标准；算法
description: 了解如何预览Adobe [!DNL Target] Recommendations活动，以确保在启动活动之前结果可用。
title: 如何预览和启动Recommendations活动？
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 75ab3bff7064c8f7df14a42422373cb64d96150a
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 15%

---

# 预览和启动“推荐”活动

在创建包含[Recommendations选件](/help/main/c-recommendations/recommendations-as-an-offer.md)的[!UICONTROL Recommendations]、[!UICONTROL A/B Test]或[!UICONTROL Experience Targeting] (XT)活动后，您将需要预览您的推荐，以确保在启动活动之前结果可用。 [!DNL Target Recommendations]提供了多种预览推荐的方法。

## 检查Recommendations算法状态

创建活动后，[!DNL Recommendations]运行算法以生成推荐。 此算法可能需要几个小时才能运行。

您可以检查算法是否已在[!UICONTROL Activity]概述图中完成运行，其中列出了条件状态。 下图显示了[!DNL Recommendations]活动[!UICONTROL Overview]页面上的活动图中的状态：

![Recommendations活动概述页面](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

状态结果包括以下内容，如下所示：

* [!UICONTROL Results Ready]：表示算法已返回结果
* [!UICONTROL Results Not Ready]：表示算法尚未完成运行。
* [!UICONTROL Feed Failure]：表示无法检索自定义条件信息源文件。

![结果对话框](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 算法需要多久才能运行？

保存包含条件的活动后，[!DNL Target]会根据选定的收藏集、条件、设计和促销来计算推荐。 此计算需要一些时间来执行，并且时间范围因所选的推荐逻辑、数据范围、目录中的项目数、客户生成的行为数据量以及所选的行为数据源而有所不同。

行为数据源对处理时间的影响最大，如下所示：

### mboxes

如果选择 mbox 作为行为数据源，则标准在创建后会立即运行。根据使用的行为数据量和目录的大小，算法可能需要长达 12 个小时才能运行。对标准配置进行更改通常会导致算法重新运行。根据所做的更改，之前计算的推荐可能在重新运行完成之前不可用，或者对于较大的更改，在重新运行完成之前，只有备份或默认内容可用。 如果未修改算法，则 [!DNL Target] 会根据所选的数据范围，每 12 到 48 小时自动重新运行该算法一次。

### [!DNL Adobe Analytics]

如果标准使用 [!DNL Adobe Analytics] 作为行为数据源，则创建标准后，其可用性的时间取决于所选报表包和回顾窗口是否已用于任何其他标准。

* **一次性报表包设置**：首次将报表包与给定数据范围回顾时间范围一起使用时，[!DNL Target Recommendations] 可能需要 2 到 7 天的时间才能从 [!DNL Analytics] 完全下载所选报表包的行为数据。此时间范围取决于 [!DNL Analytics] 系统负载。
* **使用已经可用的报表包新建或编辑标准**：在创建新标准或编辑现有标准时，如果所选报表包已与[!DNL Target Recommendations]一起使用，并且其数据范围等于或小于所选的数据范围，则数据立即可用，而无需一次性设置。 在这种情况下，或者如果在未修改所选报表包或数据范围的情况下对算法的设置进行编辑，则该算法将在 12 小时内运行或者重新运行。
* **持续的算法运行**：数据每天从 [!DNL Analytics] 流向 [!DNL Target Recommendations]。例如，对于[!UICONTROL Viewed Affinity]推荐，当用户查看产品时，产品查看跟踪调用将以近实时的方式传递到[!DNL Analytics]。 [!DNL Analytics]数据会在第二天早些时候推送到[!DNL Target]，[!DNL Target]会在12小时内运行算法。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items]不需要运行离线算法，结果立即可用。 由于所需的计算比较简单，基于mbox数据的[!UICONTROL Top Viewed]和[!UICONTROL Top Sellers]算法通常可快速生成结果。 当您想要预览设计更改或确认行为数据正在正确收集时，这些可能是很好的选项。

## 使用QA链接预览Recommendations

在算法具有结果就绪后，您可以使用[!DNL Adobe Target]的[QA链接](/help/main/c-activities/c-activity-qa/activity-qa.md)功能预览这些结果。 QA链接在[!UICONTROL Activity]概述页面的[!UICONTROL Activity Location]部分可用：

>[!NOTE]
>
>默认情况下，[!DNL Target]会自动将您添加到QA链接所需的受众。 如果关闭此设置且您的活动具有定位规则，则您的用户配置文件需要满足这些定位规则才能查看包含推荐的体验。

使用QA链接可以预览页面上的推荐：

![特色产品](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Target QA模式为“粘性”模式，保存在Cookie中。 如果不退出QA模式，您将在整个站点中持续看到QA结果。 要退出QA模式，请使用[小书签](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md)。
>
>* 在QA模式下，浏览网站将不会影响个人资料的[!UICONTROL Recently Viewed Items]或[!UICONTROL Recently Purchased Items]。 这种行为在设计上旨在避免生产行为数据受到无意的污染。 要预览来自[!UICONTROL Recently Viewed Items]或[!UICONTROL User-Based Recommendations]标准的结果，请首先在QA模式之外浏览网站，然后使用同一会话打开QA模式链接。

## 使用CSV下载来预览推荐

在某些情况下，您可能需要审核建议的特定项目。 这在使用[!UICONTROL People Who Viewed This, Viewed That]等算法时特别有用，因为根据用户当前查看的项目，推荐一组不同的项目，并且您的目录中可能有数千个或数百万个不同的项目。

在活动中至少显示一个算法的[!UICONTROL Results Ready]状态之前，结果不可下载。

要下载结果以进行预览，请单击“活动概述”页面右上角的菜单图标，然后单击&#x200B;**[!UICONTROL Download data]**。

![下载数据选项](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

正在下载CSV文件。 打开它可查看推荐的项目：

![推荐项目CSV文件](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

从左到右是推荐项目的列表，在本例中是查看次数最多的项目。 推荐按环境进行分隔，在这种情况下，只有生产环境才有推荐。

如果一行的第一个值是星号(*)，则表示[备份项](/help/main/c-recommendations/c-algorithms/backup-recs.md)。 如果不是算法（标准）的推荐项目可以填充设计中的所有版块，则会显示备用项目。

对于基于键值的其他算法类型，如[!UICONTROL People Who Viewed This, Viewed That]，键值（即“此”项）将列在最左侧的列中，而推荐项（即“该”项）将按从左到右的顺序列在Recommendation_X列中。

>[!NOTE]
>
>包含[!UICONTROL User-Based Recommendations]算法的活动无法下载结果。 使用[!UICONTROL Recently-Viewed Items]推荐逻辑的标准无法下载结果。

## 激活您的Recommendations活动

在[!UICONTROL Activity Overview]选项卡中，单击“状态”下拉箭头，然后选择&#x200B;**[!UICONTROL Activate]**。

如果[!UICONTROL Recommendations]活动当前处于[!UICONTROL Inactive]状态，则下拉列表标记为[!UICONTROL Inactive]。

几秒钟到几分钟后，状态将切换到[!UICONTROL Live]。

您还可以使用相同的下拉列表取消激活或存档活动。

## 避免在更改Recommendations设置时发生中断

在实时活动中更改[!DNL Recommendations]收藏集、标准、促销或设计设置可能会导致算法结果无效，并将算法的状态更改为[!UICONTROL Results Not Ready]。

为了避免中断实时活动，我们建议在修改实时活动时采取以下方法：

1. 复制原始活动（活动1）以及要修改的条件以创建新活动（活动2）。
1. 更改重复的活动（活动2）和标准，并等待算法生成结果。
1. 预览已修改的新活动（活动2）并确认结果符合要求。
1. 激活新活动（活动2）。
1. 取消激活原始活动（活动1）。

如果您需要在同一活动中保留历史报表结果，则可以使用替代方法，这可能会导致临时中断推荐的可用性：

1. 复制原始活动（活动1）以及要修改的条件以创建新活动（活动2）。
1. 更改重复的活动（活动2）和标准，并等待算法生成结果。
1. 预览已修改的新活动（活动2）并确认结果符合要求。
1. 暂停新的已修改活动（活动2）并将设置/标准交换给原始活动（活动1）。
1. 预览原始活动（活动1）并确认结果符合要求。
1. 重新激活原始活动（活动1）。

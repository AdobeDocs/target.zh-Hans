---
keywords: 推荐；选件；预览；启动项；状态；标准；算法
description: 了解如何预览Adobe [!DNL Target]“推荐”活动，以确保在启动该活动之前结果可用。
title: 如何预览和启动“推荐”活动？
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
TQID: 'https://experienceleague.adobe.com/21swhpZie0QN09m0LB7VwVO-9U6GWxQ0kbthPlnns18'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 0%
---
# 预览和启动“推荐”活动 {#preview-launch-recs-activity}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何检查算法状态、预览推荐以及激活[!DNL Recommendations]活动。

>[!ENDSHADEBOX]

在启动活动之前预览推荐可确认结果可用。 这适用于包含[推荐选件](/help/main/c-recommendations/recommendations-as-an-offer.md)的[!UICONTROL 推荐]、[!UICONTROL A/B测试]和[!UICONTROL 体验定位] (XT)活动。 [!DNL Target Recommendations]提供了多种预览推荐的方法。

## 检查算法状态 {#check-status}

创建活动后，[!DNL Recommendations]运行算法以生成推荐。 此算法可能需要几个小时才能运行。

算法的状态与活动图中的条件一起在[!DNL Recommendations]活动的&#x200B;**[!UICONTROL 概述]**&#x200B;页面上列出。

![推荐活动概述页面](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

状态可以是以下任一状态：

* **[!UICONTROL 结果就绪]**：算法已返回结果。
* **[!UICONTROL 结果未就绪]**：算法尚未运行完毕。
* **[!UICONTROL 信息源失败]**：无法检索自定义条件信息源文件。

![结果对话框](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## 估计算法运行时间 {#algorithm-run-time}

保存包含标准的活动后，[!DNL Target]会根据所选的收藏集、标准、设计和促销来计算推荐。 所需时间取决于推荐逻辑、数据范围、目录中的项目数、客户生成的行为数据量以及行为数据源。 行为数据源对处理时间的影响最大。

### mboxes

当mbox是行为数据源时，标准在创建后立即运行。 根据行为数据的数量和目录的大小，算法可能需要长达12小时才能运行。

对标准配置所做的更改通常会导致算法重新运行。 根据所做的更改，之前计算的推荐可能在重新运行完成后才可用。 对于较大的更改，在重新运行完成之前，只有备份或默认内容可用。

[!DNL Target]会根据所选的数据范围，每12-48小时自动重新运行未修改的算法。

### [!DNL Adobe Analytics]

当[!DNL Adobe Analytics]为行为数据源时，标准可用之前的截止时间取决于所选报表包和回顾窗口是否已用于其他标准。 首次将报表包与给定回顾时间范围一起使用时，[!DNL Target Recommendations]可能需要2到7天的时间才能从[!DNL Analytics]下载行为数据。

有关新标准或已编辑标准以及当前算法运行的时间安排，请参阅[数据Source](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#data-source)中的&#x200B;**当Analytics是数据源**&#x200B;时标准可用性。

>[!NOTE]
>
>**[!UICONTROL 最近查看的项目]**&#x200B;不需要运行离线算法，结果立即可用。 基于mbox数据的&#x200B;**[!UICONTROL 查看次数最多]**&#x200B;和&#x200B;**[!UICONTROL 最畅销商品]**&#x200B;算法通常可快速生成结果，因为计算更简单。 这些算法是用于预览设计更改或确认行为数据正在正确收集的较好选项。

## 使用QA链接预览 {#preview-qa-link}

在算法具有结果就绪后，可以使用[!DNL Adobe Target]的[QA链接](/help/main/c-activities/c-activity-qa/activity-qa.md)功能预览结果。 QA链接在&#x200B;**[!UICONTROL 活动]**&#x200B;概述页面的&#x200B;**[!UICONTROL 活动位置]**&#x200B;部分可用，并在该页面上显示推荐。

![特色产品](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>默认情况下，[!DNL Target]会自动将用户添加到QA链接所需的受众。 如果关闭此设置且活动具有定位规则，则用户配置文件必须符合这些定位规则，才能查看包含推荐的体验。

QA模式具有以下行为：

* [!DNL Target] QA模式保存在Cookie中，并跨页面持续存在。 如果未退出QA模式，则会在整个站点中继续显示QA结果。 要退出QA模式，请使用[小书签](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md)。
* 在QA模式下，浏览网站不会影响配置文件的&#x200B;**[!UICONTROL 最近查看的项目]**&#x200B;或&#x200B;**[!UICONTROL 最近购买的项目]**。 这种行为是特意设计的，以避免生产行为数据的无意污染。 要预览来自&#x200B;**[!UICONTROL 最近查看的项目]**&#x200B;或&#x200B;**[!UICONTROL 基于用户的推荐]**&#x200B;标准的结果，请首先在QA模式之外浏览网站，然后使用同一会话打开QA模式链接。

## 通过CSV下载预览 {#preview-csv}

下载结果可审核特定的推荐项目。 这对&#x200B;**[!UICONTROL 查看了这个项目，也查看了那个项目]**&#x200B;之类的算法特别有用，因为推荐的项目取决于访客当前正在查看的项目，并且目录可以包含数千个或数百万个不同的项目。

1. 等待直到活动中至少显示一个算法的&#x200B;**[!UICONTROL 结果就绪]**&#x200B;状态。 在此之前无法下载结果。

1. 在&#x200B;**[!UICONTROL 活动]**&#x200B;概述页面上，单击右上角的菜单图标，然后单击&#x200B;**[!UICONTROL 下载数据]**。

   ![下载数据选项](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

1. 打开下载的CSV文件以查看推荐的项目。

   ![推荐项目CSV文件](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

该文件从左到右列出了推荐的项目，在本例中，这些项目是查看次数最多的。 建议按环境进行分隔。 在此示例中，只有生产环境具有推荐。

以星号(*)开头的行列出了[个备份项](/help/main/c-recommendations/c-algorithms/backup-recs.md)。 当算法（标准）的推荐项目无法填满设计的所有版块时，将显示备份项目。

对于基于键值的算法，例如&#x200B;**[!UICONTROL 查看了这个项目，也查看了那个项目]**，键值（“这个”项目）位于最左侧的列中。 推荐项（“That”项）在Recommendation_X列中按从左到右的顺序列出。

对于结果集非常大的活动，**[!UICONTROL 下载数据]**&#x200B;选项可能会失败，并出现错误`Error while fetching recommendation data file.`。当生成的CSV超过用户界面在单个下载中可以返回的响应大小时，会发生这种情况。

>[!NOTE]
>
>对于包含&#x200B;**[!UICONTROL 基于用户的推荐]**&#x200B;算法的活动，或者对于使用&#x200B;**[!UICONTROL 最近查看的项目]**&#x200B;推荐逻辑的标准，结果下载不可用。

### 用于基于热门程度和基于密钥的算法的CSV下载格式 {#format}

CSV下载文件始终反映后端标准执行后生成的结果。

* **基于热门程度的算法（不基于密钥）**：文件包括：

  * 以星号(*)为前缀的一行备份推荐
  * 根据算法设置列出推荐的单独行

* **基于密钥的算法**：文件包括：

  * 备份行（与基于热门程度的算法一样）
  * 键值格式的多行，其中第一个条目是键的产品ID，后跟代表推荐候选者的逗号分隔的产品ID

## 激活活动 {#activate-activity}

激活该活动将启动它，其状态将更改为&#x200B;**[!UICONTROL 实时]**。

在&#x200B;**[!UICONTROL 活动概述]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL 状态]**&#x200B;下拉箭头，然后选择&#x200B;**[!UICONTROL 激活]**。 如果活动当前处于&#x200B;**[!UICONTROL 非活动]**&#x200B;状态，则下拉列表标记为&#x200B;**[!UICONTROL 非活动]**。 几秒钟到几分钟后，状态将切换到&#x200B;**[!UICONTROL 实时]**。

也可以使用同一下拉列表来停用或存档活动。

## 更改设置时避免中断 {#avoid-disruptions}

在实时活动中更改[!DNL Recommendations]收藏集、标准、促销活动或设计设置可能会使算法结果无效，并将算法的状态更改为&#x200B;**[!UICONTROL 结果未就绪]**。

为了避免中断实时活动，推荐的方法是修改活动副本，然后替换原始活动：

1. 复制原始活动（活动1）和要修改的条件，以创建新活动（活动2）。
1. 更改重复的活动（活动2）及其标准，然后等待算法生成结果。
1. 预览修改后的活动（活动2）并确认结果符合要求。
1. 激活新活动（活动2）。
1. 取消激活原始活动（活动1）。

如果必须将历史报表结果保留在同一活动中，则可以使用替代方法。 此方法可能会导致临时中断推荐的可用性：

1. 复制原始活动（活动1）和要修改的条件，以创建新活动（活动2）。
1. 更改重复的活动（活动2）及其标准，然后等待算法生成结果。
1. 预览修改后的活动（活动2）并确认结果符合要求。
1. 暂停修改后的活动（活动2），然后将设置和标准交换给原始活动（活动1）。
1. 预览原始活动（活动1）并确认结果符合要求。
1. 重新激活原始活动（活动1）。

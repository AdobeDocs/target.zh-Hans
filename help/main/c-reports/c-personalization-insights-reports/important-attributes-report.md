---
keywords: 定位;AP 报表;自动个性化报表;自动定位;自动定位报表;个性化;分析;FAQ;常见问题解答;重要属性
description: 了解如何使用 [!UICONTROL 重要属性] 显示影响个性化模型的主要属性及其相对重要性的报表。
title: 重要属性报表是什么？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 74%

---

# 重要属性报表

有关 [!UICONTROL 重要属性] 报告，用户可使用的两个专门报告之一 [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL 自动定位] (AT)活动

>[!NOTE]
>
>使用时，请考虑以下事项 [!UICONTROL 个性化分析] 报告：
>
>* AP 和 AT 活动会作为 [!DNL Target Premium] 解决方案的一部分提供。在没有 [!DNL Target Premium] 许可证的情况下，它们将不会包含在 [!DNL Target Standard] 中。
>
>* [!UICONTROL 个性化分析报表仅适用于使用转化优化目标的 AP 和 AT 活动。]活动上线后将优化目标从收入更改为转化的活动也不受支持。
>
>* [!UICONTROL 个性化分析] 仅当满足以下条件时，报告才可用 [!UICONTROL 主要目标] 已从中选定 [!UICONTROL 报表量度] 下拉列表。
>
>* 仅[默认环境](/help/main/administrating-target/hosts.md)支持个性化分析报表。
>
>* [!UICONTROL 个性化分析] 仅对以下范围内的活动生成报告： [!UICONTROL 实时] 状态，并且已激活并至少接收流量15天。


在不同的活动中，不同的属性对模型如何决定进行个性化的重要性也大小不一。此报表可显示影响模型的排名靠前的属性及其相对重要性。

## 访问 [!UICONTROL 重要属性] 报告 {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. 单击 **[!UICONTROL 活动]**，然后单击所需的 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) 或 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 活动。

   如果您拥有多个活动，可以通过从[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 报表源]、[!UICONTROL 体验编辑器]、[!UICONTROL 量度类型]和[!UICONTROL 活动来源]下拉列表中选择相应选项来筛选列表。

1. 单击&#x200B;**[!UICONTROL 报表]**。

   此 [Automated Personalization摘要](/help/main/c-reports/personalization-reports/reports-ap.md) 或 [自动定位摘要](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) 此时会显示报表，其中提供有关活动性能的信息，由第一个屏幕图标表示。 两个附加图标表示这两个 [!UICONTROL 个性化分析] 报告： [!UICONTROL 自动化区段] 和 [!UICONTROL 重要属性].

   ![Automated Personalization活动的摘要报告](/help/main/c-reports/assets/summary-report-ap.png)

   请注意 [!UICONTROL 自动定位] 有一个附加的图形图标，用于 [!UICONTROL 摘要] 报告。

   ![自动定位活动的摘要报表](/help/main/c-reports/assets/personalization_insights.png)

   >[!IMPORTANT]
   >
   >[!UICONTROL 重要属性]报表只有在您激活活动至少 15 天后才能使用。在此初始阶段，您将无法访问此报表，也无法单击“[!UICONTROL 重要属性]”图标。15天过后，如果您的活动中有足够的个性化流量， [!UICONTROL 重要属性] 报告可用。

1. 激活活动15天后，单击 **[!UICONTROL 重要属性]** 图标。

   ![Adobe Target报表中的“重要属性”图标](/help/main/c-reports/assets/model_attribute_ranking.png)

1. 选择所需的日期范围。

   不像 [!UICONTROL 摘要] 报表（性能报表）， [!UICONTROL 个性化分析]，包括 [!UICONTROL 重要属性]，仅适用于固定日期范围：15天、30天和60天。

   通过这些固定日期范围，“[!UICONTROL 个性化分析]”可以使用足够多的数据来降低您从活动中的短生存期模式获取分析的可能性。您可以决定日期范围的“结束日期”和“持续时间”。您会注意到“开始”显示为灰色。开始日期会根据您选择的结束日期和持续时间自动进行更改。

   ![Adobe Target报表中的日历](/help/main/c-reports/assets/personalization_insights_calendar_1.png)

   您可以从“[!UICONTROL 选择持续时间]”下拉列表中访问可用的固定日期范围。

   ![在报表中选择“持续时间”下拉列表](/help/main/c-reports/assets/personalization_insights_calendar_2.png)

1. 查看“[!UICONTROL 重要属性]”报表数据。

   ![Adobe Target中的“重要属性”报表](/help/main/c-reports/assets/model_attribute_ranking_report.png)

1. （可选）[以 CSV 格式下载报表](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF)，以便在 Excel 和其他工具中进行分析。

   >[!NOTE]
   >
   >个性化分析 UI 报表包含选择的信息。“重要属性”报表的 CSV 下载包含其他详细信息。下载的重要属性报表包含排名靠前的 100 个属性的完整列表，而 UI 报表则仅包含排名靠前的 10 个属性。如果您要在报表中查找某个特定属性，但未找到该属性，这并不意味着该属性不会影响活动，而只是该属性没有列在排名靠前的 100 个属性中。

## 解释重要属性报表

下表说明了如何解释报表并描述了其元素：

| 元素 | 详细信息 |
|--- |--- |
| 条形图 | 屏幕顶部的多色条形图允许您查看这些相对的重要性得分，该条形图映射到表格中每个相应属性旁边的圆点颜色。您还可以将鼠标悬停在条形图中的特定颜色上，以查看它所代表的属性。排名靠前的 100 个属性的重要性得分相加之和为 100%。要详细了解如何添加 Target 的个性化模型可以使用的更多属性，请参阅[为 Target 个性化算法上传数据](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。 |
| 模型属性排名图 | 模型属性排名包括排名靠前的 10 个属性，这些属性对于 Target 的个性化模型如何决定向每个访客显示什么内容最为重要。重要性得分显示了相对于排名靠前的 100 个属性，特定属性在此活动中对 Target 的个性化模型的重要程度。 |

## 重要属性常见问题解答 {#section_740910A52FA646B4AC9452F98C2F5719}

有关使用的常见问题解答，请参阅以下常见问题解答 [!UICONTROL 重要属性] 报告。

### 我的活动还无法使用个性化分析报表。为什么？

您的活动可能还不能使用[!UICONTROL 个性化分析]报表的原因包括以下几点：

* 激活活动后不满 15 天。在您启动活动至少 15 天后，自动化区段和重要属性报表才可用。在此初始阶段，您将无法访问这些报表，也无法单击“自动化区段”和“重要属性”图标。
* 您的活动在指定的时间范围内没有足够的流量。15 天过后，如果您的活动中有[足够的个性化流量](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB)来构建个性化模型，将可以使用自动化区段和重要属性报表。
* 您的活动包含收入优化目标。目前，“[!UICONTROL 个性化分析]”仅适用于转化优化目标活动。我们将在未来的版本中添加对收入优化目标活动的支持。

### 什么是属性？

属性是关于个性化算法为了解如何个性化流量而使用的访客或其特定访问的信息。例如，属性可以是浏览器类型、位置、访问时间等。

有关 [!DNL Target] 在其个性化模型中使用的属性的更多信息，请参阅[为 Target 个性化算法收集数据](/help/main/c-activities/t-automated-personalization/ap-data.md)。有关如何将新属性上传到Target以在Target个性化模型中使用的更多信息，请参阅 [将数据导入Target的方法](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}.

### 我看到一个或多个我不希望模型用于训练的属性。我可以从训练模型中移除这些属性吗？ {#models-api}

此 [!UICONTROL 模型API]也称为阻止列表API，允许用户查看和管理机器学习模型中使用的属性（也称为功能）列表 [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL 自动定位] (AT)活动 如果要排除一个或多个属性不被模型用于AP或AT活动，可以使用模型API将这些属性添加到“阻止列表”中。

有关详细信息，请参阅 [模型API概述](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} in the *Adobe Target Developer Guide*. To use the API to block attributes, see [Models API](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api-overview.html){target=_blank}.

### [!UICONTROL 自动化区段]和[!UICONTROL 重要属性]报表中的信息与 CSV 下载中的信息相同吗？

不相同，UI 报表包含选择的信息，而以 CSV 格式下载的报表则包含其他详细信息。下载的自动化区段分析报表除了包含 UI 中所包含的排名靠前的区段之外，还包含其他自动化区段，以及这些区段对您的选件或体验的性能表现。重要属性报表包含排名靠前的 100 个访客属性及其相对重要性，而 UI 则仅包含排名靠前的 10 个访客属性。

### 我能否在自定义日期范围内查看个性化分析？

个性化分析报表（“[!UICONTROL 自动化区段]”和“[!UICONTROL 重要属性]”）仅适用于固定日期范围：15 天、30 天、45 天、60 天和 90 天。通过这些固定日期范围，“[!UICONTROL 个性化分析]”可以使用足够多的数据来降低您从活动中的短生存期模式获取分析的可能性。您可以为任何结束日期（此时活动中有足够的数据来满足持续时间）选择这些持续时间。

### 个性化分析是如何创建的？

[!UICONTROL 个性化分析是采用名为 MAGIX（与模型无关的全局可理解解释）的 Adobe 技术创建的，该技术正在申请专利。]您可以在Adobe研究团队发表的有关以下主题的论文中了解有关MAGIX的更多信息 [arXiv.org网站](https://arxiv.org/abs/1706.07160).

### 是 [!UICONTROL 个性化分析] 是否可用于基于收入的建模目标/主要目标？

目前，“[!UICONTROL 个性化分析]”仅适用于转化优化目标活动。我们将在未来的版本中添加对收入优化目标活动的支持。

### 重要属性报表中的属性重要性得分是什么？

该报表的“属性重要性排名”部分中的重要性得分为以下方面提供了依据：在算法确定如何将所有访客划分到其识别的区段时，算法用于学习的哪些变量最为重要。它为模型使用的排名靠前的 100 个属性分配了百分比得分。

### 为什么在特定自动化区段中一些转化率较低的选件/体验接收的流量比其他选件/体验多？

在自动化区段中，您可能会看到转化率较低的选件/体验获得的访问次数更多，其潜在原因有多个，具体包括：

* 对特定自动化区段的部分或全部选件/体验的查看次数较少。
* 存在容量较低的活动，在这些活动中某些选件或体验没有构建模型。
* 存在容量较低的活动，在这些活动中一些选件/体验的模型构建速度快于其他选件/体验。例如，假设附加模型是在第 22 天构建的，而您查看的是第 10 天至第 24 天的数据。
* 针对特定选件的定位规则限制了哪些访客可以查看哪些选件/体验。
* 分析报表中没有置信区间。但是，如果转化率足够接近，则模型可能会提供流量，以便提高点数，但这些数字并不具有“统计学差异”。

了解模型如何提供流量很有用。系统会根据每个人的总体配置文件为其提供流量。但是，分析报表对此行为进行了归纳，以便于人们理解。因此，区段间并不互相排斥。这会导致多个区段展示此类行为，因为同一个人可以出现在多个区段中。

### 我可以通过哪些不同的方法来利用个性化分析中的信息？

* 发现要定位的新受众：如果您发现某个特定自动化区段的性能表现极好，则可以考虑创建一个受众，以便您可以在其他报表中重复使用该区段。
* 测试您针对以下内容所做的假设：哪种类型的访客会对您的哪些体验做出响应。
* 深入了解哪些内容适用于哪类访客：哪些选件负责哪些访客的提升度。
* 确定性能不佳的内容。
* 了解哪些属性对模型的学习方式最为关键。
* 查看个性化模型中使用的属性，并了解它们的重要性。
* 确定您可以将其他数据点传递到 Target 的机会，以便为您的个性化提供更多信息。

## 已知问题

以下问题目前正由 [!DNL Target] 工程团队。

* [!DNL Adobe Experience Platform] 区段名称未显示在 [!UICONTROL Automated Personalization] (AP) 和[!UICONTROL 自动定位] (AT) 活动的[!UICONTROL 重要属性]报告中。(TOP-3813)

---
keywords: 定位;AP 报表;自动个性化报表;自动定位;自动定位报表;个性化;分析;自动化区段;常见问题解答
description: 通过查看“自动化区段”报表，了解由Adobe [!DNL Target] 个性化模型定义的各种区段如何响应活动中的选件/体验。
title: 什么是自动化区段报表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Reports
exl-id: d21517b7-770b-4618-9899-7ac4948c2a8b
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '2066'
ht-degree: 59%

---

# [!UICONTROL Automated Segments]报告

有关[!UICONTROL Automated Segments]报表的信息，该报表是[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target] (AT)活动用户可以使用的两个专用报表之一。

>[!NOTE]
>
>使用[!UICONTROL Personalization Insights]报表时，请考虑以下事项：
>
>* AP 和 AT 活动会作为 [!DNL Target Premium] 解决方案的一部分提供。在没有 [!DNL Target Premium] 许可证的情况下，它们将不会包含在 [!DNL Target Standard] 中。
>
>* [!UICONTROL Personalization Insights]报表仅适用于使用转化优化目标的AP和AT活动。 活动上线后将优化目标从收入更改为转化的活动也不受支持。
>
>* 仅当从[!UICONTROL Report Metric]下拉列表中选择[!UICONTROL Primary Goal]时，[!UICONTROL Personalization Insights]报告才可用。
>
>* 仅[默认环境](/help/main/administrating-target/hosts.md)支持[!UICONTROL Personalization Insights]报告。
>
>* 仅为处于[!UICONTROL Live]状态并且已激活且接收流量至少15天的活动生成[!UICONTROL Personalization Insights]报告。

不同的访客对您的 AP/AT 活动中的选件/体验做出的响应会有所不同。此报表可显示 Target 的个性化模型定义的不同自动化区段如何响应活动中的产品建议/体验。

## 访问自动化区段报表 {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. 单击&#x200B;**[!UICONTROL Activities]**，然后从列表中单击所需的[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)或[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)活动。

   如果您有许多活动，请单击“筛选器”（![筛选器图标](/help/main/assets/icons/Filter.svg)）图标以通过从[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]和[!UICONTROL Activity Source]下拉列表中选择选项来筛选列表。

1. 单击 **[!UICONTROL Reports]**。

   将显示[Automated Personalization摘要](/help/main/c-reports/personalization-reports/reports-ap.md)或[自动定位摘要](/help/main/c-reports/personalization-reports/auto-target-summary-report.md)报告，其中提供了有关活动性能的信息，这些信息由第一个屏幕图标表示。 另外两个图标表示两个[!UICONTROL Personalization Insights]报表： **[!UICONTROL Automated Segments]** （![自动化区段报表](/help/main/assets/icons/AutomatedSegment.svg) ）和&#x200B;**[!UICONTROL Important Attributes]** （![重要属性图标](/help/main/assets/icons/ViewList.svg) ）。 自动定位为[!UICONTROL Summary]报表的图形视图提供了一个额外的图形图标。

   >[!IMPORTANT]
   >
   >[!UICONTROL Automated Segments]报表只有在您激活活动至少15天后才能使用。 在此初始期间，您将无法访问此报表或单击[!UICONTROL Automated Segments]图标。 15天过后，如果您的活动中有足够的个性化流量，将可以使用[!UICONTROL Automated Segments]报表。

1. 激活活动15天后，您可以单击&#x200B;**[!UICONTROL Automated Segments]**&#x200B;图标。

1. 选择所需的日期范围。

   与[!UICONTROL Summary]报表（性能报表）不同，包括[!UICONTROL Automated Segments]在内的[!UICONTROL Personalization Insights]仅适用于固定日期范围：15天、30天和60天。 这些固定的日期范围允许[!UICONTROL Personalization Insights]使用足够大的数据范围，以降低您从活动中的短期模式获取见解的可能性。 您可以决定日期范围的“结束日期”和“持续时间”。您会注意到“开始”显示为灰色。 开始日期会根据您选择的结束日期和持续时间自动进行更改。

   您可以从[!UICONTROL Preset Date Range]下拉列表中访问可用的固定日期范围。

1. 查看[!UICONTROL Automated Segments]报表数据。

1. （可选）单击&#x200B;**[!UICONTROL Download]** （![下载图标](/help/main/assets/icons/Download.svg) ）图标可[以CSV格式下载报表](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF)，以便在Excel和其他工具中进行分析。

   >[!NOTE]
   >
   >个性化分析 UI 报表包含选择的信息。“自动化区段”报表的 CSV 下载包含其他详细信息。下载的自动化区段报表除了包含 UI 中所包含的排名靠前的区段之外，还包含其他自动化区段，以及这些区段对您的选件或体验的性能表现。

## 解释自动化区段报表

下表说明了如何解释报表并描述了其元素：

| 元素 | 详细信息 |
|--- |--- |
| 左侧面板 | 左侧面板列出了 Target 的个性化模型为此活动确定的 20 个最大“自动化区段”。“自动化区段”就像一个受众，但它是由 Target 的个性化模型定义的，而不是由营销人员定义。每个自动化区段由特定属性的特定值（或值范围）组成。<br>自动化区段可以重叠。 自动化区段可以由一个、两个、三个或四个属性来定义。有关更多详细信息，请参阅下面的示例。<br>要了解有关 Target 个性化模型的更多信息，请参阅[随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。要了解有关 Target 个性化模型用于创建自动化区段的属性的更多信息，请参阅[为 Target 个性化算法收集数据](/help/main/c-activities/t-automated-personalization/ap-data.md)。 |
| 中心图 | 中心图显示活动内容在突出显示的自动化区段中的执行情况。 当您单击左侧面板上的不同区段时，中心图将会相应更新。 |
| 圆形分析图 | 中心面板顶部的圆形分析图显示了自动化区段的大小，以及活动中个性化访问的总次数（例如，个性化模型提供的此活动的流量。它不包括控制流量或整个入选者模型提供的流量）。区段的大小仅基于个性化访问。<br>![饼图](/help/main/c-reports/assets/pie.png) |
| 双轴条形图 | 双轴条形图包含按该特定自动化区段的选件或体验划分的访问和转化信息。 |
| 粉色条 | 粉色条表示转化率，使用图形的底轴。您可以将鼠标悬停在该条上以获取更多信息。 |
| 蓝色条 | 蓝色条表示访问次数，使用图形的顶轴。您可以将鼠标悬停在该条上以获取更多信息。 |
| 灰色虚线 | 灰色虚线表示活动中所有个性化访问的转化率，涵盖所有选件/体验和自动化区段。 |

**自动化区段示例 1**

此自动化区段仅基于一个属性来定义。此自动化区段中包含的访客在平日正常工作时间之外或周末查看此 AP 活动。

![自动化区段报告示例1](/help/main/c-reports/assets/automated_segment_example_1.png)

**自动化区段示例 2**

此自动化区段基于两个属性来定义。此自动化区段中包含的查看此 AP 活动的访客在其当前访问中的页面查看次数少于三次，并且其地理位置位于纬度 42.57 和 47.29 之间（大约位于新罕布什尔州/俄勒冈州和华盛顿州/缅因州之间的一家美国公司）。

![自动化区段报告示例2](/help/main/c-reports/assets/automated_segment_example_2.png)

## 自动化区段常见问题解答 {#section_740910A52FA646B4AC9452F98C2F5719}

**我的活动还无法使用个性化分析报表。为什么？**

[!UICONTROL Personalization Insights]报表尚不可用于您的活动的原因有多个：

* 自您激活该活动以来，已有15天未过期。 在您启动活动至少 15 天后，自动化区段和重要属性报表才可用。在此初始阶段，您将无法访问这些报表，也无法单击“自动化区段”和“重要属性”图标。
* 您的活动在指定的时间范围内没有足够的流量。15 天过后，如果您的活动中有足够的个性化流量来构建个性化模型，将可以使用自动化区段和重要属性报表。
* 您的活动包含收入优化目标。当前，[!UICONTROL Personalization Insights]仅适用于转化优化目标活动。 Adobe将在未来版本中添加对收入优化目标活动的支持。

**什么是属性？**

属性是关于个性化算法为了解如何个性化流量而使用的访客或其特定访问的信息。例如，属性可以是浏览器类型、位置、访问时间等。

有关 [!DNL Target] 在其个性化模型中使用的属性的更多信息，请参阅[为 Target 个性化算法收集数据](/help/main/c-activities/t-automated-personalization/ap-data.md)。有关如何将新属性上传到Target以在Target的个性化模型中使用的更多信息，请参阅[将数据导入Target的方法](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=zh-Hans){target=_blank}。

**什么是自动化区段？**

“自动化区段”就像一个受众，但它是由 Target 的个性化模型定义的，而不是由营销人员定义。

一个自动化区段由特定属性的特定值（或值范围）组成。请参阅上面的步骤 5 以获取自动化区段示例。区段可以重叠。

要了解有关随机林个性化算法（Target个性化模型的基础）的更多信息，请参阅[随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。

**决定自动化区段顺序的因素是什么？**

根据每个区段的大小以及它对您的活动内容的不同性能表现，会计算每个区段的得分。这些输入内容的组合决定了自动化区段的顺序，这样在响应不同内容方面具有较大差异的较大区段将显示在更靠近区段列表顶部的位置。

**为什么我的自动化区段报表中只显示了部分选件/体验？**

AP 和 AT 活动会为每个选件构建一个模型（对于 AP），以及为每个体验构建一个模型（对于 AT）。这些活动开始提供个性化的流量，并创建您的[!UICONTROL Personalization Insights]，只需构建两个模型。 如果您未在[!UICONTROL Personalization Insights]中看到您的所有选件/体验，则可能没有为这些特定选件/体验构建模型。 您可以检查活动的[!UICONTROL Summary]报告，并查看该选件/体验旁边是否有一个时钟图标。 此图标表示尚未为该选件/体验构建模型。

**为什么在特定自动化区段中一些转化率较低的产品建议/体验接收的流量比其他产品建议/体验多？**

在自动化区段中，您可能会看到转化率较低的选件或体验获得的访问次数更多，其潜在原因有多个，具体包括：

* 对特定自动化区段的部分或全部产品建议/体验的查看次数较少。
* 活动的容量较低，其中没有为某些选件/体验构建模型，或者为一些选件/体验构建模型的时间比其他选件/体验短。
* 针对特定选件的定位规则限制了哪些访客可以查看哪些选件/体验。

**[!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]报告中的信息是否与CSV下载中的信息相同？**

不相同，UI 报表包含选择的信息，而以 CSV 格式下载的报表则包含其他详细信息。下载的自动化区段分析报表除了包含 UI 中所包含的排名靠前的区段之外，还包含其他自动化区段，以及这些区段对您的选件或体验的性能表现。重要属性报表包含排名靠前的 100 个访客属性及其相对重要性，而 UI 则仅包含排名靠前的 10 个访客属性。

**我能否在自定义日期范围内看到[!UICONTROL Personalization Insights]？**

Personalization分析报表（[!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]）仅适用于固定日期范围：15天、30天和60天。 这些固定的日期范围允许[!UICONTROL Personalization Insights]使用足够大的数据范围，以降低您从活动中的短期模式获取见解的可能性。 您可以为任何结束日期（此时活动中有足够的数据来满足持续时间）选择这些持续时间。

**如何创建[!UICONTROL Personalization Insights]？**

[!UICONTROL Personalization Insights]是使用名为MAGIX（与模型无关的全局可解释解释）的Adobe正在申请专利的技术创建的。 您可以在Adobe研究团队在[arXiv.org网站](https://arxiv.org/abs/1706.07160)上发表的论文中了解有关MAGIX的更多信息。

**为什么[!UICONTROL Automated Segments]报表中的访客流量数据总数与我的AP或AT摘要/性能报表不符？**

[!UICONTROL Personalization Insights]报表仅包括查看了Target个性化模型选择的一段内容的访客（即，不考虑控制流量或整个入选者模型提供的流量）。 此流量类型称为“个性化”流量。 AP/AT中的摘要性能报表包括控制流量与“目标”流量。 目标流量包括个性化流量、使用整个入选者模型提供的流量以及随机提供的用于继续学习的一些流量。

**自动化区段是否会相互排斥？**

不会，自动化区段之间可以重叠。

**是否[!UICONTROL Personalization Insights]可用于基于收入的建模目标/主要目标？**

此时，[!UICONTROL Personalization Insights]仅适用于转化优化目标活动。 Adobe将在未来版本中添加对收入优化目标活动的支持。

**我可以通过哪些不同的方法来利用个性化分析中的信息？**

* 发现要定位的新受众：如果看到特定自动化区段表现良好，则可考虑创建受众，以便在其他报表中重复使用该区段。
* 测试您对哪种类型的访客对哪种体验做出响应的假设。
* 深入了解哪些内容适用于哪类访客：哪些选件负责哪些访客的提升度。
* 确定性能不佳的内容。
* 了解哪些属性对模型的学习方式最为关键。
* 查看个性化模型中使用的属性，并了解它们的重要性。
* 确定您可以将其他数据点传递到 Target 的机会，以便为您的个性化提供更多信息。

**区段卡片中所显示属性的顺序是否存在任何逻辑？**

不存在，卡片的顺序只是基于上面描述的排名。卡片中属性的顺序不基于任何逻辑。

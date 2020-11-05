---
keywords: Target;reports;report settings;environment;lift;lift bound;variance;confidence;control
description: 报告包括多个数据点和可视化表示形式，它们可以帮助您了解与Adobe Target活动相关的提升界限和置信度级别，从而帮助您更准确地确定获胜者。
title: 平均提升度、提升度范围和置信区间
feature: report settings
uuid: 2899503a-d81e-4dc3-b258-a5ecafd1d1a4
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 73%

---


# 平均提升度、提升度范围和置信区间

报告包括多个数据点和可视化表示形式，它们可以帮助您了解与活动相关的提升界限和置信 [!DNL Adobe Target] 度，从而帮助您更准确地确定获胜者。

>[!NOTE]
>
>This feature is available only when viewing reports in [!UICONTROL Table] View. 此功能不可用于使用 [Analytics 作为报表源 (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) 的活动。

## 解释数据 {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

The following illustration shows [!UICONTROL Lift Bounds and Confidence Level] information:

![平均提升度和置信水平报表](/help/c-reports/c-report-settings/assets/lift-screenshot-new.png)

The lift and confidence information in the [!DNL Target] reporting UI includes:

### 提升度

大数字和箭头反映了预期的提升度值。此数值是提升度范围的中间值。在置信度超过 95% 之前，表示预期提升度值的箭头会一直显示为灰色。超过该阈值后，箭头会根据提升度值的正或负分别显示为绿色或红色。

### 提升边界

提升度范围是指提升度的 95% 置信区间。它在平均提升度下方显示为一个范围。See [Example calculation](#example) below for an example of how these lift bounds are calculated.

### 包装盒图

The boxplot graph in the [!DNL Target] interface represents the expected value and 95% confidence interval of the success metric in question. 可将其视为一种用图形查看提升度和提升度范围相关信息的方式。

There are a few key ways [!DNL Target] helps you interpret the confidence information, one of which is color. 箱形图将特定体验的置信区间与控制体验的置信区间之间的重叠区域显示为灰色，而将特定体验置信区间高出或低于控制体验置信区间的区域分别显示为绿色或红色。

箱形图条块的长度直观地反映了置信区间的大小，非常便于理解。随着您收集的活动数据不断增多，条块的位置和长度会发生改变。置信区间是从方差和样本量（访客数）派生的。方差越小，样本越大，置信区间就会越小。

### 置信度

某个体验或选件的置信度表示该体验/选件的提升度超出控制体验/选件提升度的“真实性”（而不是出于偶然）概率。一般而言，建议要达到 95% 的置信水平，因为只有达到了此置信水平，提升度才会被视为具有显著意义。

## How are lift bounds calculated? {#section_1D360781D972483693680BE0F07AEAD1}

提升度范围表示特定体验或选件（相对于控制体验或选件而言）所具有的提升度的 95% 置信区间。笼统来说，这表示真实的提升度位于此范围内的概率为 95%。

可使用下列公式计算提升度范围：

![](assets/lift_diagram.png)

还需要额外进行一些计算，才能得出计算提升度范围所需的输入值：

* **t 值：** 95% 置信水平对应的统计量临界值为 1.96。您可以在此处了解更多有关 [t 值](https://en.wikipedia.org/wiki/T-statistic)的信息。
* **提升度方差：**&#x200B;需要知道体验 N 成功量度的标准误差和控制体验成功量度的标准误差，才能确定提升度方差；可使用下列公式计算此值（下列公式中的成功量度为转化）。

   ![](assets/lift_variance.png)

* **转化率/成功量度标准误差：**&#x200B;可使用下列公式以同样的方式计算体验 N 和控制体验的标准误差（下列公式中的成功量度为转化）。您可以在此处了解更多有关[标准误差](https://en.wikipedia.org/wiki/Standard_error)的信息。

   ![](assets/standard_error.png)

   >[!NOTE]
   >
   >活动的收入成功量度的标准误差基于收入的样本方差。

## Example calculation {#example}

请考虑以下活动示例，该活动具有两个体验及以下结果：

| 体验 | 访客 | 转化 | 转化率 |
|--- |--- |--- |--- |
| 体验 A（控制） | 219,328 | 2,466 | 1.12% |
| 体验 B | 218,362 | 3,040 | 1.39% |

根据我们的公式，我们可以算出计算提升度范围所需的输入值。

**体验 A（控制）的标准误差**

![](assets/standard_error_A.png)

**体验 B 的标准误差**

![](assets/standard_error_B.png)

**体验 B 的提升度方差**

![](assets/lift_variance_B.png)

**体验 B 的提升度范围**

体验 B 的预期提升度为：

![](assets/lift_bounds_B.png)

因此，体验 B 的提升度范围为：

![](assets/lift_bounds_B2.png)

>[!NOTE]
>
>使用上述公式手动计算的值与报表中显示的数字之间预计会有微小差异。此差异可能归因于手动计算中使用的页面查看次数是四舍五入后的数字。The lift shown in the [!DNL Target] report is based on the exact numbers obtained from the total engagement and the engagement count. 参与度数字可以通过性能报表 API 获得。

## When Are lift bounds not displayed? {#section_C5622E1E94684DAD937249B51A9E42CC}

In certain cases, [!DNL Target] does not display lift bounds:

* 对于任何活动，当访问总次数或访客总数少于 30 时。
* For [!UICONTROL Auto-Allocate] activities, no lift bounds are displayed until one experience has attained 60% confidence.

---
keywords: Target;报表;报表设置;环境;提升度;提升度范围;方差;置信度;控制
description: 了解如何解释Adobe [!DNL Target] 报表，包括数据点和可视化图表，可帮助您了解活动的提升度范围和置信水平。
title: 如何查看平均提升度、提升度范围和置信区间？
feature: Reports
exl-id: 0453aec1-cca5-462c-8eed-0d40bb4cf323
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 62%

---

# 平均提升度、提升度范围和置信区间

报表包含多个数据点和可视化图表，可帮助您了解与 [!DNL Adobe Target] 活动，帮助您更准确地确定入选者。

>[!NOTE]
>
>此功能仅在 [!UICONTROL 表] 查看。 此功能不可用于使用 [Analytics 作为报表源 (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) 的活动。

## 解释数据 {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

下图显示了 [!UICONTROL 提升度范围和置信水平] 信息：

![平均提升度和置信水平报表](/help/main/c-reports/c-report-settings/assets/lift-screenshot-new.png)

中的提升度和置信度信息 [!DNL Target] 报表用户界面包括：

### 提升度

大数字和箭头反映了预期的提升度值。此数值是提升度范围的中间值。在置信度超过 95% 之前，表示预期提升度值的箭头会一直显示为灰色。超过该阈值后，箭头会根据提升度值的正或负分别显示为绿色或红色。

### 提升度范围

提升度范围是指提升度的 95% 置信区间。它在平均提升度下方显示为一个范围。请参阅 [计算示例](#example) 下方的提升度范围计算示例。

### 箱形图

中的箱形图 [!DNL Target] 界面表示相关成功量度的预期值和95%置信区间。 可将其视为一种用图形查看提升度和提升度范围相关信息的方式。

有几种关键方法 [!DNL Target] 有助于您解释置信度信息，其中一种是颜色。 箱形图将特定体验的置信区间与控制体验的置信区间之间的重叠区域显示为灰色，而将特定体验置信区间高出或低于控制体验置信区间的区域分别显示为绿色或红色。

箱形图条块的长度直观地反映了置信区间的大小，非常便于理解。随着您收集的活动数据不断增多，条块的位置和长度会发生改变。置信区间是从方差和样本量（访客数）派生的。方差越小，样本越大，置信区间就会越小。

### 置信度

显示的体验或选件的置信度是获得结果的概率（以百分比表示） _极端_ 比实际观察到的更多， _如果空假设为真_，即该体验或选件与控制体验/选件之间的转化率没有差异。 对于p值，显示的置信度为 `1 - p-value`. 更简单地说，置信度越高，表示数据与控制选件/非控制选件/体验具有相等转化率的假设不一致。

## 了解如何确定提升的置信区间 {#pdf}

下载 [提升pdf文件的置信区间](/help/main/assets/confidence_interval_lift.pdf) 以了解更多信息。

## 如何计算提升度范围？ {#section_1D360781D972483693680BE0F07AEAD1}

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

## 计算示例 {#example}

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
>使用上述公式手动计算的值与报表中显示的数字之间预计会有微小差异。此差异可能归因于手动计算中使用的页面查看次数是四舍五入后的数字。显示在 [!DNL Target] 报表基于从总参与度和参与计数中获得的确切数字。 参与度数字可以通过性能报表 API 获得。

## 何时不显示提升度范围？ {#section_C5622E1E94684DAD937249B51A9E42CC}

在某些情况下， [!DNL Target] 不显示提升度范围：

* 对于任何活动，当访问总次数或访客总数少于 30 时。
* 对于 [!UICONTROL 自动分配] 活动时，只有当一个体验达到60%的置信度时，才会显示提升度范围。
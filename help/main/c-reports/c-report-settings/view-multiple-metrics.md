---
keywords: Target；报表；报表设置；多个量度；量度；显示的量度；隐藏的量度
description: 了解如何使用Adobe Target选择要在报表中查看的多个指标。
title: 如何在报表中查看多个量度？
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 12%

---

# 在报表中查看多个量度

您可以选择在[!DNL Adobe Target]报表中查看的多个量度。

在报表中使用多个量度时，请注意以下信息：

* 仅适用于[A/B测试](/help/main/c-activities/t-test-ab/test-ab.md)、[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)和[体验定位](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活动。
* 对于使用[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活动，您无法向报表中添加超过20个量度。 您可以将活动中的任意数量指标添加到&#x200B;*不*&#x200B;使用A4T的活动报表中。
* 如果您选择了多个量度，则无法使用[下载选项](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)将报表下载为CSV。 必须仅选择单个量度才能启用[!UICONTROL Download]选项。
* 您无法查看在2015年7月[!DNL Target]版本（2015年7月30日）之前创建的活动的多个量度。

**选择要在报表中显示的多个量度：**

1. 要显示报表，请单击&#x200B;**[!UICONTROL Activities]**，从列表中单击所需的活动，然后单击&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL Report Metric]**&#x200B;下拉列表以显示[!UICONTROL Shown Metrics]和[!UICONTROL Hidden Metrics]列表。

   您可以使用[!UICONTROL Search]框快速查找要添加到[!UICONTROL Shown Metrics]列表中的可用量度。

   请注意，您可以从报表的[!UICONTROL Table View]和[!UICONTROL Graph View]模式中选择多个量度。

1. 将鼠标指针悬停在[!UICONTROL Hidden Metrics]列表中的所需量度上，然后单击&#x200B;**[!UICONTROL Select]**&#x200B;以将所需量度移到[!UICONTROL Shown Metrics]列表中。

   或

   将所需量度从[!UICONTROL Hidden Metrics]列表拖放到[!UICONTROL Shown Metrics]列表。

   [!UICONTROL Shown Metrics]列表中必须至少有一个量度。

   您可以通过将量度拖放到[!UICONTROL Shown Metrics]列表中的所需顺序来重新排列这些量度。 选定的顺序将反映在[!UICONTROL Table View]和[!UICONTROL Graph View]中。 要从[!UICONTROL Shown Metrics]列表中删除指标，请将鼠标指针悬停在该指标上，然后单击&#x200B;**X**&#x200B;图标。

1. 完成后单击&#x200B;**[!UICONTROL Save]**。
1. （视情况而定）在[!UICONTROL Table View]中查看报表时，将鼠标指针悬停在任何量度的列标题上可显示一个蓝色箭头。 单击箭头可展开该表以显示该量度的[!UICONTROL Lift]和[!UICONTROL Confidence]。

   您一次只能展开一个量度/列。再次单击该箭头可折叠列。

1. （视情况而定）在[!UICONTROL Graph View]中查看报表时，您可以从下拉列表中选择要显示的各个量度。

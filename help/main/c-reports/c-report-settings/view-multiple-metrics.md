---
keywords: Target；报表；报表设置；多个量度；量度；显示的量度；隐藏的量度
description: 了解如何使用Adobe Target选择要在报表中查看的多个指标。
title: 如何在报表中查看多个量度？
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 58%

---

# 在报表中查看多个量度

您可以选择要在其中查看的多个指标 [!DNL Adobe Target] 报告。

在报表中使用多个量度时，请注意以下信息：

* 查看多个量度的功能适用于 [A/B测试](/help/main/c-activities/t-test-ab/test-ab.md)， [自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)， [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)、和 [体验定位](/help/main/c-activities/t-experience-target/experience-target.md) (XT)仅限活动。
* 您无法为使用的活动向报表添加超过20个量度 [目标分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。 您可以将活动中的任意数量指标添加到具有相应功能的活动的报表 *非* 使用A4T。
* 如果您选择了多个量度，则将无法使用“[](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)下载”选项将报表下载到 CSV 文件中。要启用“[!UICONTROL 下载]”选项，您必须只选择一个量度。
* 您无法查看2015年7月之前创建的活动的多个量度 [!DNL Target] 版本（2015年7月30日）。

**选择要在报表中显示的多个量度：**

1. 要显示报表，请单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需的活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL 报表量度]**&#x200B;下拉列表，以显示“[!UICONTROL 显示的量度]”和“[!UICONTROL 隐藏的量度]”列表。

   ![multiple_metrics图像](assets/multiple_metrics.png)

   您可以使用“[!UICONTROL 搜索]”框快速查找可用量度，以将其添加到“[!UICONTROL 显示的量度]”列表中。

   请注意，您既可以从报表的“[!UICONTROL 表格视图]”模式，也可以从“[!UICONTROL 图形视图]”模式中选择多个量度。

1. 将鼠标指针悬停在“[!UICONTROL 隐藏的量度]”列表中的所需量度上，然后单击&#x200B;**[!UICONTROL 选择]**，以将所需量度移到“[!UICONTROL 显示的量度]”列表中。

   或

   将所需量度从“[!UICONTROL 隐藏的量度]”列表拖放到“[!UICONTROL 显示的量度]”列表中。

   “[!UICONTROL 显示的量度]”列表中必须至少有一个量度。

   您可以在“[!UICONTROL 显示的量度]”列表中按所需顺序将各个量度拖放到相应的位置，以重新排列这些量度。选定的顺序将反映在 [!UICONTROL 表格视图] 和 [!UICONTROL 图形视图]. 要从“[!UICONTROL 显示的量度]”列表中删除某个量度，请将鼠标指针悬停在该量度上，然后单击 **X** 图标。

1. 完成后单击&#x200B;**[!UICONTROL 保存]**。
1. （视情况而定）在中查看报表时 [!UICONTROL 表格视图]，将鼠标指针悬停在任何量度的列标题上会显示一个蓝色箭头。 单击该箭头可展开表格，以便显示该量度的[!UICONTROL 提升度]和[!UICONTROL 置信度]。

   ![multiple_metrics_table图像](assets/multiple_metrics_table.png)

   您一次只能展开一个量度/列。再次单击该箭头可折叠列。

1. （视情况而定）在图形视图中查看报表时，您可以从下拉列表中选择要显示的各个量度：

   ![multiple_metrics_graph图像](assets/multiple_metrics_graph.png)

---
keywords: 目标；报表；报表设置；多个量度；量度；显示量度；隐藏量度
description: 了解如何使用Adobe Target在报表中选择多个要视图的量度。
title: 如何视图报表中的多个量度？
feature: 报表
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 59%

---

# 在报表中查看多个量度

您可以在[!DNL Adobe Target]报表中选择多个要视图的量度。

在报表中使用多个量度时，请注意以下信息：

* 视图多个量度的功能仅适用于[A/B Test](/help/c-activities/t-test-ab/test-ab.md)、[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自动目标](/help/c-activities/auto-target/auto-target-to-optimize.md)和[体验定位](/help/c-activities/t-experience-target/experience-target.md)(XT)活动。
* 不能向使用[Analytics for 目标](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T)的活动的报表中添加20个以上的量度。 您可以向&#x200B;*不*&#x200B;使用A4T的活动的报表添加与活动中相同的量度。
* 如果您选择了多个量度，则将无法使用“[](/help/c-reports/downloading-data-in-csv-file.md)下载”选项将报表下载到 CSV 文件中。要启用“[!UICONTROL 下载]”选项，您必须只选择一个量度。
* 您不能视图在2015年7月[!DNL Target]版本（2015年7月30日）之前创建的活动的多个量度。

**选择要在报表中显示的多个量度：**

1. 要显示报表，请单击&#x200B;**[!UICONTROL 活动]**，从列表中单击所需的活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL 报表量度]**&#x200B;下拉列表，以显示“[!UICONTROL 显示的量度]”和“[!UICONTROL 隐藏的量度]”列表。

   ![](assets/multiple_metrics.png)

   您可以使用“[!UICONTROL 搜索]”框快速查找可用量度，以将其添加到“[!UICONTROL 显示的量度]”列表中。

   请注意，您既可以从报表的“[!UICONTROL 表格视图]”模式，也可以从“[!UICONTROL 图形视图]”模式中选择多个量度。

1. 将鼠标指针悬停在“[!UICONTROL 隐藏的量度]”列表中的所需量度上，然后单击&#x200B;**[!UICONTROL 选择]**，以将所需量度移到“[!UICONTROL 显示的量度]”列表中。

   或

   将所需量度从“[!UICONTROL 隐藏的量度]”列表拖放到“[!UICONTROL 显示的量度]”列表中。

   “[!UICONTROL 显示的量度]”列表中必须至少有一个量度。

   您可以在“[!UICONTROL 显示的量度]”列表中按所需顺序将各个量度拖放到相应的位置，以重新排列这些量度。所选顺序将反映在[!UICONTROL 表视图]和[!UICONTROL 图表视图]中。 要从“[!UICONTROL 显示的量度]”列表中删除某个量度，请将鼠标指针悬停在该量度上，然后单击 **X** 图标。

1. 完成后单击&#x200B;**[!UICONTROL 保存]**。
1. （视情况而定）在[!UICONTROL 表视图]中查看报表时，将鼠标指针悬停在任何量度的列标题上可显示蓝色箭头。 单击该箭头可展开表格，以便显示该量度的[!UICONTROL 提升度]和[!UICONTROL 置信度]。

   ![](assets/multiple_metrics_table.png)

   您一次只能展开一个量度/列。再次单击该箭头可折叠列。

1. （视情况而定）在图表视图中查看报表时，您可以从下拉列表中选择要显示的单个量度：

   ![](assets/multiple_metrics_graph.png)

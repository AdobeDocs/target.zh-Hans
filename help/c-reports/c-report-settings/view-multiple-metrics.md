---
description: 可选择要在报表中查看的多个量度。
keywords: Target;报表;报表设置;多个量度;量度
seo-description: 可选择要在报表中查看的多个量度。
seo-title: 在报表中查看多个量度
solution: Target
title: 在报表中查看多个量度
topic: Premium
uuid: f3ea7313-0f98-4b58-88aa-e2438c06e739
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 在报表中查看多个量度{#view-multiple-metrics-in-a-report}

可选择要在报表中查看的多个量度。

在报表中使用多个量度时，请注意以下信息：

* 查看多个量度的功能仅适用于 A/B 活动和体验定位 (XT) 活动。
* 对于使用了 Analytics for Target (A4T) 的活动，您在活动报表中添加的量度不能超过 20 个。对于未使用 A4T 的活动，您在活动报表中可以添加所具有的任意数量的量度。
* 如果您选择了多个量度，则将无法使用“[!UICONTROL 下载]”选项将报表下载到 CSV 文件中。要启用“[!UICONTROL 下载]”选项，您必须只选择一个量度。
* 对于在 Target 2015 年 7 月版（2015 年 7 月 30 日）之前创建的活动，您无法查看多个量度。

**选择要在报表中显示的多个量度：**

1. 要显示报表，请单击**[!UICONTROL 活动]**，从列表中单击所需的活动，然后单击**报表]选项卡。[!UICONTROL **
1. 单击**[!UICONTROL 报表量度]**下拉列表，以显示“[!UICONTROL 显示的量度]”和“[!UICONTROL 隐藏的量度]”列表。

   ![](assets/multiple_metrics.png)

   您可以使用“[!UICONTROL 搜索]”框快速查找可用量度，以将其添加到“[!UICONTROL 显示的量度]”列表中。

   请注意，您既可以从报表的“[!UICONTROL 表格视图]”模式，也可以从“[!UICONTROL 图形视图]”模式中选择多个量度。

1. 将鼠标指针悬停在“[!UICONTROL 隐藏的量度]”列表中的所需量度上，然后单击**[!UICONTROL 选择]**，以将所需量度移到“[!UICONTROL 显示的量度]”列表中。

   或

   将所需量度从“[!UICONTROL 隐藏的量度]”列表拖放到“[!UICONTROL 显示的量度]”列表中。

   “[!UICONTROL 显示的量度]”列表中必须至少有一个量度。

   您可以在“[!UICONTROL 显示的量度]”列表中按所需顺序将各个量度拖放到相应的位置，以重新排列这些量度。所选的顺序将反映在“表格视图”和“图形视图”中。要从“[!UICONTROL 显示的量度]”列表中删除某个量度，请将鼠标指针悬停在该量度上，然后单击 **X** 图标。

1. 完成后单击**[!UICONTROL 保存]。**
1. 在“表格视图”中查看报表时，将鼠标指针悬停在任意量度所在列的标题上，可显示一个蓝色箭头。单击该箭头可展开表格，以便显示该量度的[!UICONTROL 提升度]和[!UICONTROL 置信度]。

   ![](assets/multiple_metrics_table.png)

   您一次只能展开一个量度/列。再次单击该箭头可折叠列。

1. 在“图形视图”中查看报表时，您可以从下拉列表中选择要显示的各个量度：

   ![](assets/multiple_metrics_graph.png)

   同样，在“图形视图”中查看报表时，收入维度也会显示为一个下拉列表：

   ![](assets/muttiple_revenue.png)


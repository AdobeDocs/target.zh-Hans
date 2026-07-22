---
title: 报表
description: 了解如何使用Customer Journey Analytics在Flags中查看功能标记报告。
badge: label="Beta" type="Informative"
hide: true
exl-id: edddca99-f263-461b-a16f-b46ee7c15f6c
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# 报表 {#reporting}

标记通过&#x200B;**Customer Journey Analytics (CJA)**&#x200B;提供报表。 每个功能标志和功能组详细信息页面上都有&#x200B;**报告**&#x200B;选项卡。 通过它，您可以查看限定为直接嵌入页面中的特定标志或组的CJA报表。

>[!NOTE]
>
>默认情况下，报表打开时具有&#x200B;**30天**&#x200B;报告窗口。 您可以从面板标题调整范围。

## 先决条件 {#prerequisites}

在查看报表之前，请确保：

1. 已为您的应用程序设置报表 — 请参阅[为功能标志报表设置CJA](set-up-cja-reporting.md)。
1. 您的功能标志或功能组处于活动状态并具有累积数据。

## 查看报表 {#view-report}

### 打开“报表”选项卡并选择一个数据视图 {#open-report-tab}

1. 打开功能标志或功能组，然后选择&#x200B;**报表**&#x200B;选项卡。
1. 将打开&#x200B;**选择数据视图**&#x200B;对话框，其中列出了可供您使用的CJA数据视图。 默认情况下，会选择第一个选项。
1. 选择所需的数据视图，然后选择&#x200B;**查看报表**。 选择&#x200B;**取消**&#x200B;关闭对话框而不加载报告。
1. 报表在选项卡中加载，其范围限定为该标记或组的实体ID。

在功能标志的详细信息页面上![报告选项卡](assets/report-tab.png)

>[!NOTE]
>
>该对话框仅列出您在当前沙盒中有权访问的数据视图。 如果没有可用，该对话框将显示一条消息，**查看报告**&#x200B;保持禁用状态 — 检查您的数据查看权限或切换沙盒。

![选择数据视图对话框](assets/select-dataview.png)

### 查看性能报表 {#view-performance-report}

显示嵌入的&#x200B;**标记概述**&#x200B;仪表板：

* **总人数**、**按日期划分的人员参与率**&#x200B;和&#x200B;**按变量划分的人员参与率**（对照组与变量ID）
* **概述**&#x200B;表，其中列出了每个变体及其人员数和参与百分比

调整面板标题中的日期范围，以重新绘制其他窗口的图表（默认为30天）。

![标记概述性能报告](assets/performance-report.png)

### 探索实验结果 {#explore-experimentation-results}

1. 在&#x200B;**试验**&#x200B;面板中，预先选择了&#x200B;**试验**（标志或组实体ID）和&#x200B;**控制变量**。
1. 使用&#x200B;**添加量度**&#x200B;添加&#x200B;**成功量度**，并根据要绘制的图形选择&#x200B;**标准化量度** （默认&#x200B;**人员**）。
1. 可选启用&#x200B;**包括置信度上/下限**。
1. 选择&#x200B;**生成**&#x200B;以计算所选量度的每个变体&#x200B;**提升**、**置信度**&#x200B;和&#x200B;**转化率**。

![试验面板，带有试验、控制变量和量度选择器](assets/experimentation-selection.png)

有关如何计算这些量度的更多详细信息，请参阅[试验面板文档](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation)。

![按变量显示提升度、置信度和转化率的试验结果](assets/experimentation.png)

## 另请参阅 {#see-also}

* [设置CJA以生成功能标记报表](set-up-cja-reporting.md)
* [创建您的第一个功能标记](create-your-first-feature-flag.md)
* [使用功能标记进行A/B测试](a-b-testing.md)
* [创建功能组](create-a-feature-group.md)

<!-- -->

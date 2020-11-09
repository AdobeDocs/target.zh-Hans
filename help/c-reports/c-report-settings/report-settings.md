---
keywords: Target;reports;report settings;preset;target preset;metric;audience;date range;settings;download;table view;graph view;average lift;lift;lift bound;confidence interval;confidence;location contribution;running average;counting methodology
description: 帮助您设置要在Adobe Target报告中显示的元素的信息。 可保存报表设置，以供日后使用。
title: 报表设置
feature: report settings
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1891'
ht-degree: 68%

---


# 报表设置{#report-settings}

Information to help you set the elements you want to appear in your report in [!DNL Adobe Target]. 可保存报表设置，以供日后使用。

要显示报表，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 活动]**，然后在列表中单击所需的活动。
1. 单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。

   ![报表 UI](/help/c-reports/c-report-settings/assets/report_ui-new.png)

## Target 预设 {#section_51F67341465045BEB4F1A2FB638A8EB1}

根据需要配置单个活动的报表后，您最多可以保存该报表的 10 个不同预设（量度、日期范围、受众、高级设置等）。All [!DNL Target] users can display, edit, and delete the various presets, regardless of who created them.

您还可以根据需要配置单个活动的报表，然后将该配置保存为默认/收藏预设。当您以后查看该活动的报表时，便会显示此视图。

### 创建预设或默认预设

1. 根据需要配置活动的报告。

   可用设置(包括指标、日期范围、受众、高级设置等)在下面进行说明。

1. 在 **[!UICONTROL Target 预设]**&#x200B;旁边，单击三个垂直省略号图标 > **[!UICONTROL 另存为新预设]**。

   ![报表预设](/help/c-reports/c-report-settings/assets/report_preset-new.png)

   此时会显示“新建预设”对话框：

   ![“新建预设”对话框](/help/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Review the information in the **[!UICONTROL Filters]** and **[!UICONTROL Settings]** sections to ensure that the report is configured as desired, then specify the **[!UICONTROL Preset Name]** (up to 50 characters).
1. (Conditional) If you want this to be your default/favorite report view, slide the **[!UICONTROL Set as default preset]** toggle to the On position.
1. 单击&#x200B;**[!UICONTROL 保存]**。

### 选择其他预设

从 **[!UICONTROL Target 预设]**&#x200B;下拉列表中选择所需的预设。

![“预设”下拉列表](/help/c-reports/c-report-settings/assets/report_preset_drop-down-new.png)

### 编辑预设

1. 选择要编辑的预设。
1. 根据需要编辑报表的配置（量度、日期范围、受众、高级设置等）。

   在编辑报表的配置后单击“[!UICONTROL 保存]”，预设名称后面会显示一个星号 ( * )，表示预设已更改，如下所示：

   ![带有星号的报表预设](/help/c-reports/c-report-settings/assets/report_preset_asterisk-new.png)

1. 单击三个垂直省略号图标 > **[!UICONTROL 另存为新预设]**&#x200B;以创建新预设。

   或

   单击三个垂直省略号图标 > **[!UICONTROL 更新]**&#x200B;以更新当前预设。

   ![更新报表默认预设](/help/c-reports/c-report-settings/assets/report_preset_update-new.png)

### 删除预设

1. 选择要删除的预设。
1. 单击三个垂直省略号图标 > **[!UICONTROL 删除]**。

   ![删除报表默认预设](/help/c-reports/c-report-settings/assets/report_preset_delete-new.png)

1. 再次 **[!UICONTROL 单击]** “删除”以确认删除（无法恢复已删除的预设）。

### 预设错误处理

通过报表中的警报和消息，您可以知晓预设是否变为无效。警报或消息会指示您选择其他受众、量度、主机组或体验以创建有效预设。

以下列表描述了可能导致预设变为无效的一些情况：

* 已删除活动中的某个报表受众，但预设定义中仍引用该报表受众。
* 已删除一个（或多个）量度，但预设定义中仍引用该量度。例如，您可能删除了活动中的一个或多个量度，然后添加了新量度。
* 一个（或多个）主机组（环境）不存在，但预设定义中仍引用该主机组（环境）。
* 创建预设后删除了一个（或多个）体验，但预设定义中仍引用该体验。
* 预设在语义上无效，因为所引用的实体虽然仍存在，但是已通过对预设定义进行语义更改的方式进行了更新。例如，假设您最初创建了一个名为“Chrome 上的收入”的预设。稍后，您更新该活动以衡量转化量度而非收入。对活动定义的此更新从语义上使预设定义无效。

## 报表量度 {#section_894ABD7148244806B7CE556EBBA2AD62}

单击&#x200B;**[!UICONTROL 报表量度]**&#x200B;下拉列表以选择要在图表中显示的其他[成功量度](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)或多个量度。

默认情况下，主量度在创建活动时的成功量度设置中确定。如果您更改该设置并重新保存活动，则报表的主量度会随之更新。

有关选择要在报表中查看的多个量度的更多信息，请参阅[在报表中查看多个量度](/help/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7)。

## 受众 {#section_70926EB4618945D9AFF2B0564FF3717B}

单击[!UICONTROL 受众]下拉列表以更改报表中显示的受众。

有关更多信息，请参阅[受众](/help/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)。

## 日期范围 {#section_A410A768403C4E01891F95CB357E63ED}

日期范围框显示报表的当前日期范围。 单击下拉图标可显示允许您更改报表日期范围的日历。

![选项](/help/c-reports/c-report-settings/assets/date_range-new.png)

为报表选择新的&#x200B;**[!UICONTROL 开始]**&#x200B;日期和&#x200B;**[!UICONTROL 结束]**&#x200B;日期。You can also use the **[!UICONTROL From start of Activity]** and **[!UICONTROL Till end of Activity]** check boxes.

单击&#x200B;**[!UICONTROL 自定义日期]**&#x200B;可选择预定义的日期范围：“最近 7 天”、“最近 15 天”或“最近 30 天”。这些预定义的日期范围是可滚动的范围。如果从开始日期算起的天数少于所选天数，则日历将显示从开始日期起的范围，但是如果随着活动持续时间增加，从开始日期算起的天数多于所选天数，则日期范围会相应滚动。

报表具有以下日期限制：

* 报表的开始日期必须是过去两年内的日期。
* 优惠组报告自今天起仅限99天。
* 每小时报表限制在 15 天以内。

## 设置 {#section_D99CE462107D45CABE0960F820E1E972}

配置报告设置：

1. 单击齿轮图标，进行所需的更改（如下所述）。
1. 完成后单击&#x200B;**[!UICONTROL 保存]**。

下图显示了 A/B 活动的“设置”对话框：

![“设置”对话框](/help/c-reports/c-report-settings/assets/ab_settings_dialog-new.png)

根据选定的活动类型，选项会有所不同：

### 计数方法

选择所需的方法：

* 访客
* 访问次数
* 活动展示次数

### 主控

选择计算和比较电梯时要使用的控制体验。

### 环境

选择要用于报告的环境（主机组）。 有关更多信息，请参阅[主机](/help/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

### 重置报表数据

重置报告数据以删除旧数据。 当前的访客将保留在活动中。This option is available only for those with [!UICONTROL Approver] permissions.

>[!IMPORTANT]
>
>这是永久性操作，无法撤消。

### 排除极端值

The [!UICONTROL Exclude Extreme Values] toggle applies to activities with Revenue and Engagement metric types only. 有关更多信息，请参阅[排除超常订单](/help/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

## 下载 {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Click the **[!UICONTROL Download]** icon to download report data in a [!DNL .csv] format for quick import into Excel, Access, or other data analysis programs.

![下载图标](/help/c-reports/c-report-settings/assets/download-icon.png)

有关更多信息，请参阅[将数据下载到 CSV 文件](/help/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)。

## 刷新 {#section_E203729F2F314DF3856D2EE67C60B370}

Click the **[!UICONTROL Refresh]** icon to refresh a report&#39;s table and graph view without refreshing the entire page, its configuration, or its date range.

## More options {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

单击“更多选项”图标（三个垂直省略号）可访问“[!UICONTROL 编辑活动]”和“[!UICONTROL 查看体验 URL]”选项。

## 视图选项

您可以视图各种格式的报表，具体取决于活动类型。 选择所需选项。

![视图选项图标](/help/c-reports/c-report-settings/assets/view-options.png)

* **表视图**:单击“ **[!UICONTROL 表视图]** ”图标，将报表视图为表。
* **图形视图**:单击图 **[!UICONTROL 形视图]** 图标以将报表视图为图形。
* **自动细分**:(仅适用于Automated Personalization(AP)和自动目标(AT)活动。) 单击“**自动[!UICONTROL 化细分] ”图标以视图 [“自动细分”报表](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。
* **重要属性**:(仅适用于Automated Personalization(AP)和自动目标(AT)活动。) 单击“**重要[!UICONTROL 属性] ”图标以视图 [重要属性报告](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

## 平均提升度、提升度范围和置信区间 {#section_0D87615B1D3344B3858BA494EEBC16FB}

报表包含一些数据点和可视化图表，有助于了解与您的活动相关的提升度范围和置信水平。这可帮助您更准确地确定入选者。

有关更多信息，请参阅[平均提升度、提升度范围和置信区间](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md#topic_AFFDC672A8A34D028B100EF6BE5D8129)。

请考虑以下事项：

* 只有在表格视图中查看报表时才可用。
* 此功能不可用于使用 [Analytics 作为报表源 (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) 的活动。

## 位置贡献 {#section_5832F126AC114AE1ABFFF4D9B904393B}

单击&#x200B;**[!UICONTROL 位置贡献]**&#x200B;图标可将报表切换为按位置显示贡献。

## 体验 {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

（仅在图形视图中查看报表时可用）

在图表的左侧选择或取消选择体验，可在图表中显示或隐藏相应的体验。

下图的报表中仅显示了“默认”体验、“中东”体验和“总计”体验。“亚洲”体验在图形中处于隐藏状态。

![体验](/help/c-reports/c-report-settings/assets/report_experiences-new.png)

## 运行平均值 {#section_59066693158C4433B87D07402C2BC6CD}

（仅在图形视图中查看报表时可用）

“运行平均值”反映累计转换(从报告窗口的开始到图表上表示的日期)除以累计访客。

选择所需的图形视图。

* 运行平均值
* 运行平均值（提升）
* 每日
* 每日（提升）

![报表运行平均值](/help/c-reports/c-report-settings/assets/report_running_average-new.png)

此下拉列表的名称因所选视图而异，但将是上面列出的视图之一。

## 计数方法 {#section_01B0ED5665C74AE1AE97259800190C3E}

（仅在图形视图中查看报表时可用）

您可以为报表中的图形选择计数方法。Note that this is not supported for [!UICONTROL Automated Personalization] (AP) activities.

To access the [!UICONTROL Counting Methodology] option, while viewing a report in graph mode, click the **[!UICONTROL My Primary Goal]** drop-down, then select the counting methodology.

计数方法将与在“[!UICONTROL 设置]”对话框中选择的方法相同，具体如上所述。

![计数方法](/help/c-reports/c-report-settings/assets/counting_methodology_2-new.png)

默认情况下，图形会按“[!UICONTROL 每日]”模式进行绘制。

You can change the mode by clicking the [!UICONTROL Daily] drop-down list, then selecting a cumulative option.

![累积](/help/c-reports/c-report-settings/assets/counting_methodology-new.png)

>[!NOTE]
>
>此下拉列表的名称会因所选的模式而异。

自动定位活动有四种模式：“每日（控制）”、“每日（目标）”、“累计（控制）”和“累计（目标）”。

默认的图形绘制顺序如下：

* **A/B测试(包括自动分配和Automated Personalization)**:体验创建的顺序，按降序排列。
* **体验定位(XT)**:活动体验的顺序。
* **Multivariate Test(MVT)**:按体验名称字母排序。
* **Recommendations**:体验创建的顺序，按降序排列。

在使用“计数方法”选项时，请考虑以下注意事项：

* For [Auto-Target activities](/help/c-activities/auto-target/auto-target-to-optimize.md), there is no option for selecting &quot;Visitors&quot; as the counting methodology. 自动定位是唯一一种无法按访客绘制图形的活动类型。
* For activities that use [Analytics as the reporting source (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md), you cannot plot Visitor, Visit, or Impression cumulatively.

## 处理在活动中具有16个以上体验的图形

如果活动中的体验少于 16 个，则会在图形中分别用不同的颜色绘制每个体验。

如果活动中的体验多于 16 个，则会在图形中用彩色线条显示前 16 个体验。在左侧的“体验”窗格中，其余的体验会呈灰显状态，并且图形中不会显示相应的绘制线条。在给定的时间，只能显示 16 个体验的线条。

如果将鼠标悬停在任意灰显的体验上，图形中会暂时显示与该体验对应的新绘制线条，该线条为灰色。要为某个灰显体验显示彩色绘制线条，您可以单击某个以彩色线条显示的体验的名称来取消选择该体验，然后单击所需灰显体验的名称来将其选中。

下图提供了一个示例，其中显示的活动图形含有 26 个体验：

![](assets/graph_1.png)

该图形显示了前 16 个体验的线条（有些线条存在重叠，因此显示的线条不到 16 个）。左侧“体验”窗格中每个体验名称旁边的彩色圆点表示该体验的绘制线条以相应的颜色显示。

如果在“体验”窗格中向下滚动，您会看到第 17 到 26 个体验的名称都处于灰显状态，如下图所示：

![](assets/graph_2.png)

如果将鼠标悬停在某个灰显的体验上，图形中会暂时显示与该体验对应的新绘制线条，该线条为灰色。

假设您希望显示体验 R 的绘制线条，而不显示体验 P 的线条，那么可以单击体验 P 的名称来取消选择该体验，然后单击体验 R 的名称来将其选中，如下所示：

![](assets/graph_3.png)


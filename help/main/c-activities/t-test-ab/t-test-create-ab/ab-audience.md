---
keywords: 受众;选择受众;选取受众;选择器
description: 根据受众条件定义哪些网站访客加入您的Adobe [!DNL Target] 活动。
title: 如何在 [!DNL Target] A/B活动中选择受众？
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: f6845756f9d4220214b0d9131cd5f27db2ae94a9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 8%

---

# 选择受众

受众可确定哪些符合条件的访客进入了您的[!DNL Adobe Target]活动。

在[!UICONTROL Targeting]创建活动[时，三步引导式工作流的](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)步骤会显示流程图，该流程图将引导您完成以下步骤：分配受众及其流量百分比、选择流量分配方法并为活动中的每个体验指定流量分配。

![A/B 测试定位步骤](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

有关流程图中所有选项的更多信息，请参阅[创建A/B测试活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

## 选择活动的受众

1. 单击&#x200B;**[!UICONTROL All Visitors]**&#x200B;控件为该活动选择其他受众。

   [!UICONTROL All Visitors]受众设置为默认受众。 如果选择其他受众，则其名称将显示在最左侧的控件中。

   对于没有特定受众定位的A/B测试，请选择默认值[!UICONTROL All Visitors]。

   此时将显示正确的框架，您可以在其中添加或删除受众，并分配活动的访客百分比。

1. 要更改受众，请单击右框架中的&#x200B;**[!UICONTROL Replace]图标** （ ![替换图标](/help/main/assets/icons/Retweet.svg) ）。

1. 在[!UICONTROL Add Audience]对话框中，[选择所需的受众](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然后单击&#x200B;**[!UICONTROL Assign Audience]**。

   默认情况下，所有访客都是您的受众。但是，您可以更改受众。从[!UICONTROL Audience Library]中选择受众，或者您可以创建仅限该活动的受众。 [!UICONTROL Audience Library]包含以前定义的受众，包括一些作为[!DNL Target]的一部分预先构建的通用受众。

1. （视情况而定）单击&#x200B;**合并受众**&#x200B;以[创建合并多个受众的受众](/help/main/c-target/combining-multiple-audiences.md)。

1. （视情况而定）要创建不在[!UICONTROL Audience Library]中的新受众，请单击&#x200B;**创建受众**，定义受众，然后单击&#x200B;**[!UICONTROL Done]**。

   在[创建受众工作流](/help/main/c-target/c-audiences/audiences.md)期间，您可以从以下选项中进行选择：

   * **[!UICONTROL Audience Library]**：创建保存到[!UICONTROL Audience Library]的按需受众，该受众可在其他活动中重复使用。
   * **[!UICONTROL This activity only]**：创建未保存到[的](/help/main/c-target/creating-activity-only-audience.md)活动特定受众[!UICONTROL Audience Library]，该受众只能用于当前活动。

1. 单击右侧窗格中的&#x200B;**[!UICONTROL Visitor Percentage]**，然后指定要包含在活动中的符合条件的访客的百分比。

1. 如果您对受众感到满意，请单击&#x200B;**[!UICONTROL Next]**&#x200B;以进入三步引导式工作流的第三步。

>[!NOTE]
>
>打开[!UICONTROL Audience]列表时会在后台自动导入受众，导入的受众为10分钟之前的受众。

## 查看受众的信息

1. 在[!UICONTROL Add Audiences]对话框中，单击受众旁边的&#x200B;**[!UICONTROL Information]**&#x200B;图标（![信息图标](/help/main/assets/icons/InfoOutline.svg)）以查看有关该受众的详细信息，包括其源和属性。

1. 单击&#x200B;**[!UICONTROL View Full Details]**&#x200B;可查看有关受众的其他详细信息。 详细信息包括受众的属性；受众的描述、工作区、类型和源；以及引用此受众的活动列表。 您可以查看有关每个受众的信息，包括活动名称、状态、工作区、上次修改受众的时间以及修改者。

## 编辑或复制受众

您可以编辑或复制受众，方法是在[!UICONTROL More Actions]对话框中单击所需受众旁边的![图标（](/help/main/assets/icons/More.svg)更多操作图标[!UICONTROL Add Audience]），然后单击[!UICONTROL Edit]或[!UICONTROL Copy]。

如果您想要创建一个与现有受众类似的受众，则复制受众很有用。您可以制作受众的副本、进行编辑，然后将其另存为新受众。

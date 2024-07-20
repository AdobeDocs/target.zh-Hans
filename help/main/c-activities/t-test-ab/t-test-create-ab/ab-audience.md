---
keywords: 受众;选择受众;选取受众;选择器
description: 受众确定哪些网站访客进入了Adobe [!DNL Target] 活动。
title: 如何在 [!DNL Target] A/B活动中选择受众？
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: 676350453268e4ffc04df83dcda0525842ca8b07
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 66%

---

# 选择受众

受众可确定哪些网站访客进入了您的[!DNL Adobe Target]活动。

>[!NOTE]
>
>除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。有关更多信息，请参阅[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 在[!UICONTROL Audience]框中，单击&#x200B;**[!UICONTROL Edit]**&#x200B;图标（垂直省略号），然后单击&#x200B;**[!UICONTROL Replace Audience]**。

   ![“替换受众”选项](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

   默认情况下，所有访客都是您的受众。但是，您可以更改受众。您可以从受众库中选择受众，也可以创建仅限该活动的受众。受众库中包含以前定义的受众，其中包括作为[!DNL Target]的一部分预先构建的一些常用受众。

1. 选择或创建所需受众：

   * 从库中选择受众
   * [合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)
   * [创建新受众](/help/main/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1)
   * [创建仅限该活动的受众](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)。

   对于没有特定受众定位的A/B测试，请选择默认值[!UICONTROL All Visitors]。

   您还可以通过在[!UICONTROL Add Audience]对话框中将鼠标悬停在所需受众上来编辑或复制受众，如下所示。

   如果您想要创建一个与现有受众类似的受众，则复制受众很有用。您可以制作受众的副本，对其进行编辑，然后将其另存为新受众。其他类型的活动中也提供了这一鼠标悬停功能。

   ![受众悬停](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

   在创建受众时，您可以选择一个位置 (mbox) 并指定该位置的参数。在[!UICONTROL Custom Parameters]下，选择mbox，然后指定所需的参数。

   >[!NOTE]
   >
   >打开受众列表时会在后台自动导入受众，导入的受众为 10 分钟之前的受众。

1. （视情况而定）指定要包含在活动中的符合条件的访客所占的百分比。

   例如，您可以选择将所有访客中 50% 的访客包含在活动中。

   ![受众百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   您还可以选择让 Target [自动分配流量](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 在 Adobe Target 中使用受众（6 分 21 秒）![概述徽章](/help/main/assets/overview.png)

以下视频介绍了如何在 [!DNL Target Standard/Premium] 中使用受众。

* 解释术语“受众”
* 介绍使用受众进行优化的两种方式
* 在“受众”列表中查找受众
* 将活动定位到受众
* 在活动中使用受众进行被动报告

>[!VIDEO](https://video.tv.adobe.com/v/17398)

### 活动工作流 — 定位(2:14) ![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关设置受众的信息。

* 为活动分配受众
* 增加或减少流量
* 选择流量分配方法
* 在不同的体验之间分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17385)

有关详细信息，请参阅[受众](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)。

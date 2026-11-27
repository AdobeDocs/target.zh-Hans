---
keywords: 推荐;设置;名称;目标;优先级;持续时间;报表设置;其他元数据
description: 了解如何配置用于描述和控制Adobe Target中的“推荐”活动的设置。
title: 如何配置“推荐”活动设置？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
TQID: 'https://experienceleague.adobe.com/pfMAvl6MmLCtH3PZfOR4Ve-WFIc3e2iN2Bh-cIzjeC0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 13%
---
# “推荐”活动设置 {#recs-activity-settings}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解描述和控制[!DNL Adobe Target]中[!DNL Recommendations]活动的设置。

>[!ENDSHADEBOX]

活动设置标识[!DNL Recommendations]活动，控制其显示时间和位置，并定义其结果的报告方式。

## 名称

单击“更多操作”图标（ ![更多操作图标](/help/main/assets/icons/MoreSmallListVert.svg) ），然后单击&#x200B;**[!UICONTROL 重命名]**&#x200B;为活动提供一个有助于识别该活动的描述性名称。

活动名称中不允许使用以下字符： `/`、`?`、`#`、`:`、`=`、`+`、`-`和`@`。

如果[!UICONTROL Recommendations Classic]中的另一个活动已存在[!DNL Recommendations]活动的名称，则会使用新名称重新同步新活动。 新名称是附加了时间戳的原始名称，具有唯一性。 它同时显示在[!DNL Target Standard/Premium]和[!UICONTROL Recommendations Classic]中。

## 目标

（可选）描述活动的目标。

## 优先级

调整滑块以设置优先级。

将具有相同受众的多个活动分配到同一位置时，会使用优先级。 如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。

## 持续时间

设置活动的持续时间。

活动可以在激活时开始，也可以在特定的日期和时间开始。 同样，它可以在停用时或在特定的日期和时间结束。

时间选择器使用的是 24 小时制时钟，其中 00:00 表示午夜。 时区是在浏览器中配置的时区。 要使用其他时区，请将浏览器设置为该时区，然后重新启动浏览器。

## 报表设置

以下设置定义活动结果的报告方式。

* **[!UICONTROL 报告Source]：**&#x200B;指定从中收集数据的解决方案： [!DNL Adobe Target]、[!DNL Adobe Analytics]或[!DNL Adobe Customer Journey Analytics]。

  如果在[帐户设置](/help/main/administrating-target/reporting.md)中指定了报表解决方案，则会使用该解决方案，并且此设置不可见。 为保持报表的一致性，在活动启动后无法更改报表源。

  **[!DNL Adobe Analytics]**：查看[[!DNL Adobe Analytics] 作为 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的报表源，以了解报表解决方案之间的差异和各自的优势。 有关[!DNL Analytics]报表包和跟踪服务器的选择，请参阅[报告Source](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source)。

  **[!DNL Adobe Customer Journey Analytics]**：有关[!DNL Adobe Customer Journey Analytics]与[!DNL Target]之间集成的详细信息，请参阅[[!DNL Target] 在 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中报告。

* **[!UICONTROL 目标量度]：**&#x200B;选择用于确定活动是否成功的成功量度。
* **[!UICONTROL 其他度量]：**&#x200B;为报告配置其他成功度量。
* **[!UICONTROL 报表的受众]：**&#x200B;定义可用于筛选报表的受众。

## 其他元数据

输入有关活动的注释。

## 培训视频：活动设置(3:02) ![教程徽章](/help/main/assets/tutorial.png)

本视频涵盖以下活动设置：

* 输入活动的目标。
* 设置活动的优先级。
* 安排开始和结束时间。
* 添加报表受众以创建报表过滤器。
* 输入活动的注释。

>[!VIDEO](https://video.tv.adobe.com/v/3507951?captions=chi_hans)

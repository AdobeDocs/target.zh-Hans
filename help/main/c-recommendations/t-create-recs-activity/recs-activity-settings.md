---
keywords: 推荐;设置;名称;目标;优先级;持续时间;报表设置;其他元数据
description: 了解如何配置用于描述和控制Adobe Target中Recommendations活动的设置。
title: 如何配置Recommendations活动设置？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 84%

---

# “推荐”活动设置

有关可用于描述和控制的设置的信息 [!UICONTROL Recommendations] 中的活动 [!DNL Adobe Target].

![“推荐”活动目标和设置页面](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

以下部分介绍了[!UICONTROL 推荐]活动的可用设置。

## 名称

提供描述性名称，以帮助您和您的团队识别活动。

活动名称中不允许使用以下字符：

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

如果您指定的[!UICONTROL 推荐]活动名称已被 [!UICONTROL Recommendations Classic] 中的其他活动使用，则会使用新名称重新同步新活动。新名称是在原始名称后附加一个时间戳，以使其具有唯一性。此新名称会同时显示在两个中 [!DNL Target Standard/Premium] 和 [!UICONTROL Recommendations Classic].

## 目标

（可选）描述活动的目标。

## 优先级

调整滑块可确定优先级别。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。

## 持续时间

设置活动的持续时间。

活动可以在激活时开始，或者您也可以设置特定的日期和时间。同样，活动可以在停用时结束，或者您也可以设置特定的日期和时间。时间选择器使用的是 24 小时制时钟，其中 00:00 表示午夜。时区设置为在浏览器中配置的时区。要使用不同的时区，请将浏览器设置为其他时区并重新启动浏览器。

## 报表设置

* **报表源：** 选择报表源： [!DNL Adobe Target] 或 [分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md). 活动开始后，请勿更改报表源。在活动开始后更改报表源会导致报表不一致。
* **目标量度：**&#x200B;选择用于确定活动是否成功的成功量度。
* **其他量度：**&#x200B;配置要在报表中使用的其他成功量度。
* **报表的受众：**&#x200B;定义可在筛选报表时使用的受众。

## 其他元数据

输入有关活动的注释。

## 培训视频：活动设置(3:02) ![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关活动设置的信息。

* 输入活动的目的
* 设置活动的优先级
* 计划活动的开始和结束时间
* 添加报表受众以创建报表筛选器
* 输入活动的注释

>[!VIDEO](https://video.tv.adobe.com/v/17381)

---
keywords: 推荐;设置;名称;目标;优先级;持续时间;报表设置;其他元数据
description: 了解如何配置用于描述和控制Adobe Target中的Recommendations活动的设置。
title: 如何配置Recommendations活动设置？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 48%

---

# “推荐”活动设置

有关可用于描述和控制 [!UICONTROL Recommendations] 中的活动 [!DNL Adobe Target].

![“推荐”活动目标和设置页面](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

以下部分介绍了的可用设置 [!UICONTROL Recommendations] 活动。

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

如果您指定 [!UICONTROL Recommendations] 中已存在另一个活动的活动名称 [!UICONTROL Recommendations Classic]，则会使用新名称重新同步新活动。 新名称是在原始名称后附加一个时间戳，以使其具有唯一性。此新名称会同时显示在 [!DNL Target Standard/Premium] 和 [!UICONTROL Recommendations Classic] 中。

## 目标

（可选）描述活动的目标。

## 优先级

调整滑块可确定优先级别。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。

## 持续时间

设置活动的持续时间。

活动可以在激活时开始，或者您也可以设置特定的日期和时间。同样，活动可以在停用时结束，或者您也可以设置特定的日期和时间。时间选择器使用的是 24 小时制时钟，其中 00:00 表示午夜。时区设置为在浏览器中配置的时区。要使用不同的时区，请将浏览器设置为其他时区并重新启动浏览器。

## 报表设置

* **报表源：** 指定从以下来源收集解决方案数据：

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  如果您在中指定了报表解决方案，则 [帐户设置](/help/main/administrating-target/reporting.md)，则使用指定的解决方案，并且此设置不可见。

  在活动启动后，为保持报表一致，您不能更改报表源。

  **[!DNL Adobe Analytics]**：请参阅 [[!DNL Adobe Analytics] 作为的报表源 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) 了解报表解决方案之间的差异和各自的优势。

  选择时 [!DNL Analytics] 作为的报表源 [!DNL Target] (A4T)，则选择 [!DNL Analytics] 要接收的报表包 [!DNL Target] 活动数据。 要执行此操作，请先从任一 [!DNL Analytics] 您的帐户绑定的公司，然后为活动选择适当的报表包。 仅限配置为连接到的报表包 [!DNL Target] 可供选择。 如果您没有看到预期的报表包，请先尝试注销并重新登录到 [!DNL Adobe Experience Cloud] 再试一次。 如果列表中仍缺少报表包，请联系 [客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

  [!DNL Analytics for Target] (A4T)需要跟踪服务器才能正确报告结果。 默认跟踪服务器显示在 [!UICONTROL Tracking Server] 字段。 如果使用多个跟踪服务器，请确保在此字段中包含正确的跟踪服务器。 请参阅 [使用Analytics跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 以了解更多信息。

  **[!DNL Adobe Customer Journey Analytics]**：请参阅 [[!DNL Target] 报告 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) 有关集成的详细信息，请参阅 [!DNL Adobe Customer Journey Analytics] 和 [!DNL Target].

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

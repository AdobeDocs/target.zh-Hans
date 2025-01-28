---
keywords: 推荐;设置;名称;目标;优先级;持续时间;报表设置;其他元数据
description: 了解如何配置用于描述和控制Adobe Target中的Recommendations活动的设置。
title: 如何配置Recommendations活动设置？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: b7c7e8d85f7f39024ed5e57177e5c9f628460e9c
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 45%

---

# “推荐”活动设置

有关可用于描述和控制[!DNL Adobe Target]中的[!UICONTROL Recommendations]活动的设置的信息。

以下部分介绍了[!UICONTROL Recommendations]活动的可用设置。

## 名称

单击“更多操作”图标（ ![更多操作图标](/help/main/assets/icons/MoreSmallListVert.svg) ），然后单击&#x200B;**[!UICONTROL Rename]**&#x200B;以提供描述性名称，帮助您和您的团队识别该活动。

活动名称中不允许使用以下字符：

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

如果您指定的[!UICONTROL Recommendations]活动名称已被[!UICONTROL Recommendations Classic]中的其他活动使用，则会使用新名称重新同步新活动。 新名称是在原始名称后附加一个时间戳，以使其具有唯一性。此新名称会同时显示在 [!DNL Target Standard/Premium] 和 [!UICONTROL Recommendations Classic] 中。

## 目标

（可选）描述活动的目标。

## 优先级

调整滑块可确定优先级别。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。

## 持续时间

设置活动的持续时间。

活动可以在激活时开始，或者您也可以设置特定的日期和时间。同样，活动可以在停用时结束，或者您也可以设置特定的日期和时间。时间选择器使用的是 24 小时制时钟，其中 00:00 表示午夜。时区设置为在浏览器中配置的时区。要使用不同的时区，请将浏览器设置为其他时区并重新启动浏览器。

## 报表设置

* **报告Source：**&#x200B;指定从以下来源收集解决方案数据：

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  如果在[帐户设置](/help/main/administrating-target/reporting.md)中指定了报表解决方案，则会使用指定的解决方案，并且此设置不可见。

  在活动启动后，为保持报表一致，您不能更改报表源。

  **[!DNL Adobe Analytics]**：查看[[!DNL Adobe Analytics] 作为 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的报告来源，了解报告解决方案之间的差异和各自的优势。

  选择[!DNL Analytics]作为[!DNL Target] (A4T)的报表源时，请选择一个[!DNL Analytics]报表包以接收[!DNL Target]活动数据。 为此，请先从您的帐户绑定的[!DNL Analytics]家公司中选择任意，然后为活动选择合适的报表包。 只有配置为连接到[!DNL Target]的报表包才可供选择。 如果您没有看到预期的报表包，请先尝试注销并重新登录到[!DNL Adobe Experience Cloud]以重试。 如果列表中仍缺少报表包，请联系[客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

  [!DNL Analytics for Target] (A4T)需要跟踪服务器才能正确报告结果。 [!UICONTROL Tracking Server]字段中将显示默认跟踪服务器。 如果使用多个跟踪服务器，请确保在此字段中包含正确的跟踪服务器。 有关详细信息，请参阅[使用Analytics跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

  **[!DNL Adobe Customer Journey Analytics]**：有关[!DNL Adobe Customer Journey Analytics]与[!DNL Target]之间集成的详细信息，请参阅[[!DNL Target] 在 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中报告。

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

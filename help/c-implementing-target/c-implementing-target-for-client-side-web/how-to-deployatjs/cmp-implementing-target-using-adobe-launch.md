---
keywords: 实施；实施；Adobe Launch;Launch；争用；重定向；体验platform launch;platform launch；标记；Adobe Platform
description: 了解如何使用 [!DNL Adobe Experience Platform], the preferred method to implement [!DNL Target]实施 [!DNL Adobe Target] at.js库。
title: 如何使用 [!DNL Adobe Experience Platform]实施 [!DNL Target] ?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 11%

---

# 使用 [!DNL Target] 实施 [!DNL Adobe Experience Platform]

[!DNL Adobe Experience Platform]中的标记是[!DNL Adobe]中推出的下一代标记管理功能。 标记为客户提供了一种简单的方式来部署和管理用来改善相关客户体验的分析、营销和广告标记。

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] 已更名为 [!DNL Adobe Experience Platform] 中的一套数据收集技术。因此，产品文档中的术语有一些改动。有关术语更改的统一参考，请参阅以下[文档](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

下表列出了可从中获取更多信息的各种来源：

| 资源 | 详细信息 |
|--- |--- |
| [添加 [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | 本教程提供了在网站中使用[!DNL Adobe Experience Platform]中的标记实施[!DNL Target]的分步说明。 主题包括添加 at.js JavaScript 库、触发全局 mbox、添加参数，以及与其他解决方案集成。本文是向您展示如何实施[!DNL Adobe Experience Platform]和其他[!DNL Adobe Experience Cloud]解决方案的较大教程的一部分。 |
| [快速入门指南](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | 此信息介绍了如何部署和管理提升相关客户体验所必需的分析、营销和广告标签。 |
| [ [!DNL Target] Adobe扩展概述](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | 有关使用[!DNL Adobe Experience Platform]实施[!DNL Target]的信息。 |

## 使用[!DNL Target]扩展实施at.js的优势 {#section_48B3F938B6F8491DAF798E0DB54EF304}

仅当您在[!DNL Adobe Experience Platform]中使用标记来实施at.js时，以下优势才适用。 因此，[!DNL Adobe]强烈建议您在[!DNL Adobe Experience Platform]中使用标记，而不是手动实施at.js。

* **解决 [!DNL Adobe Analytics] 和争 [!DNL Target] 用情况：** 由于 [!DNL Analytics] 可以在调用之前触发 [!DNL Target] 调用，因此 [!DNL Target] 调用不会与调用 [!DNL Analytics] 拼合。此排序可能会导致数据不正确。 [!DNL Target]扩展可确保[!DNL Analytics]信标调用将等到[!DNL Target]调用完成（无论是否成功）。 在[!DNL Adobe Experience Platform]中使用标记可解决客户在手动实施时可能遇到的数据不一致问题。

   >[!NOTE]
   >
   >在[!DNL Adobe Analytics]扩展中使用[!UICONTROL Send Beacon]操作，以便[!DNL Analytics]调用会等待[!DNL Target]调用。 如果您使用自定义代码直接调用`s.t()`或`s.tl()`，则[!DNL Analytics]调用不会等到[!DNL Target]调用完成后才调用。

* **阻止错误的重定向选件处理：** 如果您在 [!DNL Target] 和 [!DNL Analytics] 页面上执行了某个重定向选件，并且该选件由 [!DNL Target] [!DNL Analytics] 执行，则您可能会遇到以下情况：跟踪器触发了不应触发的请求（因为用户将被重定向到其他URL）。如果您通过[!DNL Adobe Experience Platform]中的标记实施[!DNL Target]和[!DNL Analytics]，则不会遇到此问题。 [!DNL Adobe Experience Platform]中的[!DNL Target]使用标记会指示[!DNL Analytics]中止[!DNL Analytics]信标请求。

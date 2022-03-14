---
keywords: 实施；实施；Adobe Launch;Launch；争用；重定向；体验platform launch;platform launch；标记；Adobe Platform
description: 了解如何实施 [!DNL Adobe Target] at.js库使用 [!DNL Adobe Experience Platform]，实施的首选方法 [!DNL Target].
title: 如何实施 [!DNL Target] 使用 [!DNL Adobe Experience Platform]?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 10%

---

# 使用 [!DNL Target] 实施 [!DNL Adobe Experience Platform]

中的标记 [!DNL Adobe Experience Platform] 是 [!DNL Adobe]. 标记为客户提供了一种简单的方式来部署和管理用来改善相关客户体验的分析、营销和广告标记。

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] 已更名为 [!DNL Adobe Experience Platform] 中的一套数据收集技术。因此，产品文档中的术语有一些改动。请参阅以下内容 [文档](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) ，以获取术语更改的综合参考。

下表列出了可从中获取更多信息的各种来源：

| 资源 | 详细信息 |
|--- |--- |
| [添加 [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | 本教程提供了实施的分步说明 [!DNL Target] 网站中标记为 [!DNL Adobe Experience Platform]. 主题包括添加 at.js JavaScript 库、触发全局 mbox、添加参数，以及与其他解决方案集成。本文是向您展示如何实施的大型教程的一部分 [!DNL Adobe Experience Platform]，等等 [!DNL Adobe Experience Cloud] 解决方案。 |
| [快速入门指南](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | 此信息介绍了如何部署和管理提升相关客户体验所必需的分析、营销和广告标签。 |
| [Adobe [!DNL Target] 扩展概述](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | 有关实施的信息 [!DNL Target] 使用 [!DNL Adobe Experience Platform]. |

## 使用实施at.js的优势 [!DNL Target] 扩展 {#section_48B3F938B6F8491DAF798E0DB54EF304}

仅当您在 [!DNL Adobe Experience Platform] 来实施at.js。 因此， [!DNL Adobe] 强烈建议您在 [!DNL Adobe Experience Platform] 而不是手动实施at.js。

* **解决 [!DNL Adobe Analytics] 和 [!DNL Target] 争用条件：** 因为 [!DNL Analytics] 可在 [!DNL Target] 调用， [!DNL Target] 调用未拼合到 [!DNL Analytics] 呼叫。 此排序可能会导致数据不正确。 的 [!DNL Target] 扩展可确保 [!DNL Analytics] 信标调用会一直等到 [!DNL Target] 无论是否成功，调用都会完成。 在中使用标记 [!DNL Adobe Experience Platform] 解决了客户在手动实施时可能遇到的数据不一致问题。

   >[!NOTE]
   >
   >使用 [!UICONTROL 发送信标] 中的操作 [!DNL Adobe Analytics] 扩展，以便 [!DNL Analytics] 等待调用 [!DNL Target] 呼叫。 如果您直接调用 `s.t()` 或 `s.tl()` 使用自定义代码， [!DNL Analytics] 调用不会等待 [!DNL Target] 调用已完成。

* **阻止错误的重定向选件处理：** 如果 [!DNL Target] 和 [!DNL Analytics] ，并且会执行一个重定向选件 [!DNL Target]，您可能会遇到 [!DNL Analytics] 跟踪器在不应触发时触发请求（因为用户将被重定向到其他URL）。 如果您实施 [!DNL Target] 和 [!DNL Analytics] 通过 [!DNL Adobe Experience Platform]，则不会遇到此问题。 在中使用标记 [!DNL Adobe Experience Platform], [!DNL Target] 指示 [!DNL Analytics] 中止 [!DNL Analytics] 信标请求。

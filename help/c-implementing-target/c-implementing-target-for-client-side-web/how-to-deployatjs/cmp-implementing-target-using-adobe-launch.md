---
keywords: 实施；实施；实施；adobe启动；启动；竞赛；重定向；体验platform launch;platform launch
description: 了解如何使用Adobe Experience Platform Launch实现Adobe [!DNL Target]的首选方法Adobe [!DNL Target] at.js库。
title: 如何使用Adobe启动实现 [!DNL Target] ?
feature: 实施服务器端
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a69737f49a52cde703627f91d4b97609c1796ee6
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 6%

---

# 使用[!DNL Adobe Platform Launch]实现[!DNL Target]

[!DNL Adobe Experience Platform Launch] 是来自的新一代标签管理平 [!DNL Adobe] 台，是实现的首选方 [!DNL Adobe Target]法。[!DNL Platform Launch] 为客户提供了一种部署和管理分析、营销和广告标记的简单方式，这些标记是提升相关客户体验所必需的。

## 使用[!DNL Platform Launch] {#topic_5234DDAEB0834333BD6BA1B05892FC25}实现[!DNL Target]

下表列表了各种源，您可以从中获取有关[!DNL Platform Launch]的更多信息：

| 资源 | 详细信息 |
|--- |--- |
| [使 [!DNL Target] 用Adobe Target扩 [!UICONTROL 展教程实现]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | 本教程提供了在包含[!DNL Platform Launch]的网站中实现[!DNL Target]的分步说明。 主题包括添加 at.js JavaScript 库、触发全局 mbox、添加参数，以及与其他解决方案集成。本文是一个更大的教程的一部分，该教程向您展示如何实施[!DNL Platform Launch]和其他[!DNL Adobe Experience Cloud]解决方案。 |
| [[!DNL Adobe Platform Launch] 文档](https://experienceleague.adobe.com/docs/launch/using/get-started/quick-start.html#get-started) | 有关部署和管理支持相关客户体验所必需的分析、营销和广告标记的信息。 |
| [Adobe  [!DNL Target] Extension文档](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | 有关使用[!DNL Platform Launch]实现[!DNL Target]的信息。 |

## 使用[!DNL Target] [!DNL Platform Launch]扩展{#section_48B3F938B6F8491DAF798E0DB54EF304}实现at.js的优势

以下优势仅在使用[!DNL Platform Launch]实现at.js时适用。 因此，[!DNL Adobe]强烈建议您使用[!DNL Platform Launch]，而不是手动实现at.js。

* **解决 [!DNL Adobe Analytics] 和 [!DNL Target] 竞争条件：** 由于 [!DNL Analytics] 呼叫可以在呼叫前 [!DNL Target] 触发， [!DNL Target] 因此呼叫不会被拼接 [!DNL Analytics] 到呼叫。这种排序可能导致数据不正确。 从0.6.0开始，[!DNL Platform Launch]扩展可确保[!DNL Analytics]信标呼叫等待到[!DNL Target]呼叫完成，无论是否成功。 使用[!DNL Platform Launch]解决客户在手动实施时可能遇到的数据不一致问题。
* **防止重定向优惠** 处理不 [!DNL Target] 正确：如 [!DNL Analytics] 果您在 [!DNL Target] [!DNL Analytics] 页面上执行了重定向优惠，并且存在重定向，则您会遇到一种情况，即跟踪器在不应该触发请求时（因为用户被重定向到其他URL）。如果通过[!DNL Platform Launch]实施[!DNL Target]和[!DNL Analytics]，则不会遇到此问题。 使用[!DNL Platform Launch],[!DNL Target]指示[!DNL Analytics]中止[!DNL Analytics]信标请求。

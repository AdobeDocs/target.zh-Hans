---
keywords: 实施;at.js;javascript 库
description: 了解如何部署Adobe [!DNL Target] at.js JavaScript库使用Adobe Experience Platform中的标记，或者不使用标签管理器。
title: 如何部署at.js?
feature: Implement Server-side
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---

# 如何部署 at.js

有关如何部署 [!DNL Adobe Target] JavaScript库at.js，使用 [!DNL Adobe Experience Platform] 或者没有标签管理器。

您可以使用以下方法部署 at.js：

* **[实施 [!DNL Target] 在 [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**:中的标记 [!DNL Adobe Experience Platform] 是 [!DNL Adobe]. 标记为客户提供了一种简单的方式来部署和管理用来改善相关客户体验的分析、营销和广告标记。

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] 已更名为 [!DNL Adobe Experience Platform] 中的一套数据收集技术。因此，产品文档中的术语有一些改动。请参阅以下内容 [文档](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) ，以获取术语更改的综合参考。

* **[不通过标签管理器实施Target](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**:您无需使用标签管理器即可实施Target(例如， [!DNL Adobe Experience Platform])。
* **使用第三方标签管理器实施Target**: [中的标记 [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) is the preferred method to implement Target; however, you can also implement Target using a third-party tag manager, including Tealium, Ensighten, and Google Tag. For a list of benefits of using Launch, see [Advantages of implementing at.js using the [!DNL Adobe Target] 扩展](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   但是，如果您知道如何实施 [!DNL Target] 如果没有标签管理器，您可以使用第三方标签管理器轻松实施，而无需在网站代码中硬编码at.js。

   以下两个相关主题将帮助您实施 [!DNL Target] 使用第三方标签管理器：

   * [实施之前](/help/main/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [实施 [!DNL Target] 没有标签管理器](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   有关更多信息，请务必查看第三方标签管理器的文档。

实施 [!DNL Target] 使用单页应用程序(SPA)时，请参阅 [单页应用程序实施](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

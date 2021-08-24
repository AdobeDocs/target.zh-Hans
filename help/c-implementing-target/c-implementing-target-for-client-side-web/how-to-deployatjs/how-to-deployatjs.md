---
keywords: 实施;at.js;javascript 库
description: 了解如何在Adobe Experience Platform中或不使用标签管理器时使用标签部署Adobe [!DNL Target] at.js JavaScript库。
title: 如何部署at.js?
feature: 实施服务器端
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: eddde1bae345e2e28ca866662ba9664722dedecd
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 6%

---

# 如何部署 at.js

有关如何使用[!DNL Adobe Experience Platform]中的标记或在没有标签管理器的情况下部署[!DNL Adobe Target] JavaScript库at.js的信息。

您可以使用以下方法部署 at.js：

* **[ [!DNL Target] 在 [!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**&#x200B;中实施标记：中的标 [!DNL Adobe Experience Platform] 记是推出的新一代标签管理功能 [!DNL Adobe]。标记为客户提供了一种简单的方式来部署和管理用来改善相关客户体验的分析、营销和广告标记。

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] 已在中作为一套数据收集技术进行了重新 [!DNL Adobe Experience Platform]命名。因此，在产品文档中推出了一些术语更改。 有关术语更改的统一参考，请参阅以下[文档](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

* **[不通过标签管理器实施Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**:您无需使用标签管理器（例如中的标签）即可实施 [!DNL Adobe Experience Platform]Target。
* **使用第三方标签管理器实施Target**: [标记 [!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 是实施Target的首选方法；但是，您也可以使用第三方标签管理器（包括Tealium、Ensighten和Google标签）来实施Target。有关使用Launch的好处列表，请参阅[使用 [!DNL Adobe Target] 扩展](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304)实施at.js的优势。

   但是，如果您知道如何在不使用标签管理器的情况下实施[!DNL Target]，则可以使用第三方标签管理器轻松实施，而无需在网站代码中硬编码at.js。

   以下两个相关主题将帮助您使用第三方标签管理器实施[!DNL Target]:

   * [实施之前](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [在没有标签管理器的情况下实施 [!DNL Target] ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   有关更多信息，请务必查看第三方标签管理器的文档。

要在使用单页应用程序(SPA)时实施[!DNL Target]，请参阅[单页应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

---
keywords: implement;at.js;javascript library
description: 此信息介绍了如何在以下三种情况下部署 Adobe Target JavaScript 库 at.js：使用 Adobe Launch、不使用标签管理器，或使用 Adobe 动态标签管理 (DTM)。
title: 如何部署 at.js
feature: at.js
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 57%

---


# 如何部署 at.js{#how-to-deploy-at-js}

此信息介绍了如何在以下三种情况下部署 Adobe Target JavaScript 库 at.js：使用 Adobe Launch、不使用标签管理器，或使用 Adobe 动态标签管理 (DTM)。

您可以使用以下方法部署 at.js：

* **[使用 Adobe Launch 实施 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**：Launch 是 Adobe 的下一代标签管理平台，是实施 Adobe Target 的首选方法。Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。
* **[不通过标签管理器实施 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**：您可以在不使用标签管理器（Adobe Launch 或动态标签管理）的情况下实施 Adobe Target。
* **[使用动态标签管理实施目标](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md)**:您可以使用Adobe动态标签管理(DTM)(Adobe的传统标签管理器)来实施目标。Adobe Launch 是实施 Target 和 at.js 库的最新首选方法。对于新的 Target 实施，请使用 Launch。
* **使用第三方标签管理器实施目标**: [Adobe](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 启动是实现目标的首选方法；但是，您也可以使用第三方标签管理器来实施目标，如Tealium、Ensighten、Google标签等。有关使用Launch的列表优势，请参阅[使用目标启动扩展](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304)实施at.js的优势。

   但是，如果您知道如何在没有标签管理器的情况下实现目标，则可以使用第三方标签管理器轻松实现，而不是在站点代码中硬编码at.js。

   以下两个相关主题将帮助您通过第三方标签管理器实施目标:

   * [实施之前](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [不通过标签管理器实施 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   请务必查看第三方标签管理器的文档以了解更多信息。

要在使用单页应用程序 (SPA) 时实施 Target，请参阅[单页应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。
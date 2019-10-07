---
description: Launch 是 Adobe 的下一代标签管理平台，是实施 Adobe Target 的首选方法。Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。
keywords: 实施;Adobe Launch;Launch;争用;重定向体验平台启动
seo-description: Adobe Experience Platform Launch是Adobe的新一代标签管理平台，是实施Adobe Target的首选方法。 Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。
seo-title: 使用 Adobe Launch 实施 Target
title: 使用 Adobe Launch 实施 Target
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: c94b1a1e735810ef4119781c3e051b632d140614

---


# 使用 Adobe Launch 实施 Target{#implement-target-using-adobe-launch}

Adobe Experience Platform Launch是Adobe的新一代标签管理平台，是实施Adobe Target的首选方法。 Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。

## 使用 Adobe Launch 实施 Target {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch 是 Adobe 的下一代标签管理平台，是实施 Adobe Target 的首选方法。Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。

下表列出了可以获取有关 Launch 的更多信息的各种资源：

| 资源 | 详细信息 |
|--- |--- |
| [使用Adobe Target扩展教程实施Target](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | 本教程提供了使用 Launch 在网站中实施 Adobe Target 的分步说明。主题包括添加 at.js JavaScript 库、触发全局 mbox、添加参数，以及与其他解决方案集成。本文是一个庞大教程的一部分，该教程向您介绍了如何实施 Adobe Launch，以及与其他 Adobe Experience Cloud 解决方案集成。 |
| [Adobe Launch 文档](https://docs.adobe.com/content/help/en/launch/using/intro/get-started/quick-start.html) | 有关部署和管理为相关客户体验提供支持所需的所有分析、营销和广告标记的信息。 |
| [Adobe Target扩展文档](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | 有关使用 Launch 实施 Target 的信息。 |

## 使用 Target Launch 扩展实施 at.js 的优势 {#section_48B3F938B6F8491DAF798E0DB54EF304}

仅当您使用 Adobe Launch 实施 at.js 时，以下优势才适用。为此，我们强烈建议您使用 Adobe Launch 进行实施，而不使用 DTM 进行实施或手动实施 at.js。

* **解决了 Analytics 和 Target 争用情况：**&#x200B;由于可以在 Target 调用之前触发 Analytics 调用，因此 Target 调用不会与 Analytics 调用相拼合。这可能会导致数据不正确。从 0.6.0 开始，Target Launch 扩展可确保 Analytics 信标调用将等到 Target 调用完成（不论其成功与否）后才触发。这应该可以解决客户可能遇到的数据不一致问题。
* **阻止错误的重定向选件处理：**&#x200B;如果您在页面上同时具有 Target 和 Analytics，并且有一个重定向选件由 Target 执行，则您可能会遇到如下情况：Analytics 跟踪器触发了不应触发的请求（因为用户将被重定向到不同的 URL）。如果您通过 Launch 实施 Target 和 Analytics，则不会遇到此问题。Target 会使用 Launch 指示 Analytics 中止 Analytics 信标请求。

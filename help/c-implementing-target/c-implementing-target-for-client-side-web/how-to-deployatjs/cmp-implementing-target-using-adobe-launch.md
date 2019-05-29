---
description: Launch 是 Adobe 的下一代标签管理平台，是实施 Adobe Target 的首选方法。Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。
keywords: 实施;Adobe Launch;Launch;争用;重定向
seo-description: Launch 是 Adobe 的下一代标签管理平台，是实施 Adobe Target 的首选方法。Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。
seo-title: 使用 Adobe Launch 实施 Target
title: 使用 Adobe Launch 实施 Target
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 5417d8bcacbb734e0b852d70f482a927f382c89e

---


# 使用 Adobe Launch 实施 Target{#implement-target-using-adobe-launch}

Launch 是 Adobe 的下一代标签管理平台，是实施 Adobe Target 的首选方法。Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。

## 使用 Adobe Launch 实施 Target {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch 是 Adobe 的下一代标签管理平台，是实施 Adobe Target 的首选方法。Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。

下表列出了可以获取有关 Launch 的更多信息的各种资源：

| 资源 | 详细信息 |
|--- |--- |
| [使用Adobe Target扩展教程实施目标](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | 本教程提供了使用 Launch 在网站中实施 Adobe Target 的分步说明。主题包括添加 at.js JavaScript 库、触发全局 mbox、添加参数，以及与其他解决方案集成。本文是一个庞大教程的一部分，该教程向您介绍了如何实施 Adobe Launch，以及与其他 Adobe Experience Cloud 解决方案集成。 |
| [Adobe Launch 文档](https://docs.adobelaunch.com/getting-started) | 有关部署和管理为相关客户体验提供支持所需的所有分析、营销和广告标记的信息。 |
| [Adobe Target扩展文档](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension) | 有关使用 Launch 实施 Target 的信息。 |

## 使用 Target Launch 扩展实施 at.js 的优势 {#section_48B3F938B6F8491DAF798E0DB54EF304}

仅当您使用 Adobe Launch 实施 at.js 时，以下优势才适用。为此，我们强烈建议您使用 Adobe Launch 进行实施，而不使用 DTM 进行实施或手动实施 at.js。

* **解决Analytics和Target竞赛条件：** 由于在Target调用之前可以触发Analytics调用，Target调用不会拼接到Analytics调用中。这会导致数据不正确。从0.6.0开始，Target Launch扩展确保Analytics信标调用一直等待，直到Target调用完成，无论成功与否。这应该可以解决客户可能遇到的数据不一致问题。
* **防止不正确的重定向选件处理：** 如果页面上有Target和Analytics，并且Target执行了重定向选件，则您可能遇到一个情况，该情况导致Analytics跟踪器在不应时触发请求(因为用户被重定向到其他URL)。如果您通过Launch实施Target和Analytics，则不会遇到此问题。Target会使用Launch指示Analytics中止Analytics信标请求。
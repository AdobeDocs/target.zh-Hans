---
keywords: target 文档变更日志;文档更新;新主题;编辑;更新;更新
description: 及时了解对 [!DNL Adobe Target] 文档的重要补充和变更。
title: 可在何处查看 [!DNL Target] 的文档更新？
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: b9aebf56ea46c40ca4693e85460358f2e406bbec
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 93%

---

# 文档更改

此页面列出对 [!DNL Adobe Target] 产品文档作出的重大变更。

## [!DNL Target] Standard/Premium 24.1.1（2024 年 1 月 22 日、23 日和 25 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 2 月 28 日 | [[!DNL Target] 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了关于 [!DNL Target] Standard/Premium 24.3.1（2024年3月4日至6日）版本。 |
| 2 月 26 日 | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于即将推出的产品的信息 [!UICONTROL Adobe Target社区] 茶歇（2024年2月28日）。 |
| 2 月 23 日 | [使用的IP地址 [!DNL Recommendations] 信息源处理服务器](/help/main/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | 添加了以下重要说明和您应列入允许列表的新IP地址。<P>**重要**：和 [!DNL Target] 组当前正在更新NAT网关地址以供下载 [!DNL Recommendations] 信息源。 如果实施IP列入允许列表，请确保您允许列表以下新的AWS主机。 现有主机将于2024年6月30日停用。 为确保平稳过渡，请允许列表所有九个地址。 无需急迫删除现有地址。 |
| 2 月 8 日 | [预获取](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/prefetch.html){target=_blank} | 添加了新部分：“使用 Analytics for Target (A4T) 时通过 clickTrack 指标预获取 mbox” |
| 2 月 5 日 | [创建使用 Analytics 作为报告源的活动](/help/main/c-integrating-target-with-mac/a4t/campaign-creation.md) | 添加了文本，规定您在使用 [!UICONTROL Analytics for Target] (A4T) 作为报告源时，不得将相同的活动名称用于不同工作区的两个活动。 |
|  | [活动设置 - A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md) | 添加了文本，规定您在使用 [!UICONTROL Analytics for Target] (A4T) 作为报告源时，不得将相同的活动名称用于不同工作区的两个活动。 |
|  | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于安排在 2024 年 2 月 7 日的 Adobe Target 社区喝咖啡休息时间的信息。 |
| 1 月 24 日 | [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 添加了 at.js 版本 2.11.4 的发行说明。 |
|  | [浏览器](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | 宣布这两个新配置文件尚未可用。当这些配置文件可用时，将更新这些说明。 |
|  | [at.js 常见问题解答](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-faq.html){target=_blank} | 添加了有关 Ionic 应用程序环境中 at.js 的常见问题解答。此实施未经测试，也不作推荐。 |
| 1 月 22 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了有关从[!UICONTROL 浏览器]受众属性中弃用 iPad 和 iPhone 的重要信息，您需要在 2024 年 4 月 30 日之前作出相应的更改。 |
|  | [浏览器](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | 添加了新章节： <ul><li>从浏览器受众属性中弃用 iPad 和 iPhone（2024 年 4 月 30 日）</li></ul> |
|  | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 24.1.1 版的发行说明。 |

## [!DNL Target] Standard/Premium 23.11.1（2023 年 11 月 13 日和 14 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 1 月 18 日 | [[!DNL Target] 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了即将发布的 [!DNL Target Standard/Premium] 24.1.1 版的预发行说明。 |
| 12 月 13 日 | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了有关 [!DNL Adobe Target] 2024 年个性化成熟度网络研讨会系列的信息。 |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html){target=_blank} | 添加了两个新的可选设置： <ul><li>aepSandboxId</li><li>aepSandboxName</li></ul> |
| 12 月 4 日 | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了“机器学习和 AI 报告与分析”[!DNL Adobe Target Community] 茶歇时间讲座（2023 年 12 月 6 日星期三）的登记信息。 |
| 12 月 1 日 | [Adobe Target 配置文件更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank} | 将旧版 API 文档移至以下文章：<ul><li>[Adobe Target 配置文件 API 概述](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank}</li><li>[Adobe Target 单一配置文件更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-single-api.html){target=_blank}</li><li>[Adobe Target 批量配置文件更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-bulk-api.html?){target=_blank}</li></ul> |
| 11 月 29 日 | [批量配置文件更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html){target=_blank} | 澄清了在使用[!UICONTROL 批量配置文件更新 API] v2 版本与 v1 版本时，在为 [!DNL Target] 尚未发现的用户创建配置文件时 [!DNL Target] 处理客户属性的方式的区别。 |
| 11 月 21 日 | [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 添加了 at.js 2.11.3 的发行说明。 |
| 11 月 17 日 | [管理员首要步骤](/help/main/administrating-target/start-target.md) | 添加了以下重要注释：<ul><li>[!DNL Adobe Admin Console] 中具有[!UICONTROL 产品管理员]或[!UICONTROL 系统管理员]权限的用户可以编辑或更改 [!DNL Target] [!UICONTROL 管理]页面上的所有设置，不管其 [!DNL Target] 角色如何。[!DNL Adobe Admin Console] 中不具有[!UICONTROL 产品管理员]或[!UICONTROL 系统管理员]权限的用户必须具有特定的 [!DNL Target] 角色才能进行这些更改。</li></ul> |
|  | [限制](/help/main/r-troubleshooting-target/target-limits.md#in-mbox) | 使用有关 [!DNL Target] 如何处理 at.js 2.*x* 和 [!DNL Adobe Experience Platform Web SDK] 中的截断信息更新了此部分。 |
|  | [投放 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html){target=_blank} | 添加了对当前投放 API 文档的重定向，并弃用了旧文档 (`http://developers.adobetarget.com/api/delivery-api/`)。请根据需要更新书签。 |
| 11 月 16 日 | [批量配置文件更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html){target=_blank} | 添加了以下警告：“更新通常会在一小时内进行，但可能需要长达 24 小时才能反映出来。” |
| 11 月 13 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.11.1 版的发行说明。 |

## [!DNL Target] Standard/Premium 23.10.2（2023 年 10 月 24 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 11 月 10 日 | [Recommendations API 参考](https://developer.adobe.com/target/administer/recommendations-api/){target=_blank} | [!DNL Adobe Target] [!DNL Recommendations] API 已迁移至 [!DNL Adobe Developer] 网站。如有必要，请更新您的书签。 |
|  | [时间范围](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | 添加了 [!DNL Target] 实时受众不考虑夏令时 (DST) 变化的说明。您必须手动更新受众以说明 DST 变化。 |
| 11 月 8 日 | [[!DNL Target] 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了即将发布的 [!DNL Target Standard/Premium] 23.11.1 版的预发行说明。 |
| 10 月 28 日 | [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 添加了有关 at.js 2.11.2 版的详细信息。 |
| 10 月 25 日 | [[!DNL Target] 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了关于[!UICONTROL 活动]页面用户界面更新（2023 年 10 月 25 日）的信息 |
| 10 月 24 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.10.2 版的发行说明。 |

## [!DNL Target] Standard/Premium 23.9.1（2023 年 9 月 6 日至 11 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 10 月 17 日 | [报告常见问题](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B) | 更新了以下常见问题：“我活动的报告为何没有数据可用？” |
| 10 月 11 日 | [[!DNL Adobe Analytics] 作为  [!DNL Adobe Target] (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 的报告源 | 更新了关于 [!DNL Adobe Experience Platform Web SDK] 对 A4T 支持情况的信息。 |
| 10 月 10 日 | [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 添加了 at.js 版本 2.11.0 的发行说明。 |
| 10 月 6 日 | [响应令牌](/help/main/administrating-target/response-tokens.md) | 更新了所有代码示例。 |
|  | [在 [!DNL Analysis Workspace] 中为[!UICONTROL 自动分配]活动设置 A4T 报表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} | 更新了 *[!UICONTROL Adobe Target 教程]*&#x200B;指南中的整个教程。 |
| 10 月 4 日 | [活动](/help/main/c-activities/activities.md) | 更新了文本和图像以反映 [!DNL Target] 23.9.4 版中包含的 UI 更新。 |
|  | [信息源](/help/main/c-recommendations/c-products/feeds.md) | 更新了文本和图像以反映 [!DNL Target] 23.9.4 版中包含的 UI 更新。 |
| 10 月 2 日 | [[!DNL Target] 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.9.3 版的发行说明。 |
|  | [[!DNL Recommendations] 实施模式](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank} | 新的“使用 at.js 的 Recommendations 实施模式”**&#x200B;文章帮助您在使用 at.js JavaScript 库时了解和创建您的 [!DNL Adobe Target Recommendations] 实施。<P>有关 [!DNL Target] 模式的一般信息，请参阅“Adobe Target 开发人员指南”**&#x200B;中的[实施模式概述](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html){target=_blank}。<P>新的 Recommendations 实施模式由以下文章构成：<ul><li>[使用 at.js 的 Recommendations 实施模式概述](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank}</li><ul><li>[初始化 SDK](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html){target=_blank}</li><li>[配置数据收集](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html){target=_blank}</li><li>[渲染体验](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=zh-Hans){target=_blank}</li><li>[通知 [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=zh-Hans){target=_blank}</li></ul></ul> |
| 9 月 29 日 | [[!DNL Target] 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.9.3 版本的预发行说明。 |
|  | [初始化 Java SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html){target=_blank} | 将以下新参数添加到表：<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
| 9 月 22 日 | 与[[!UICONTROL 增强体验编辑器]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF)相关的问题疑难解答 | 将 IP 地址列表更新为了允许列表。 |
| 9 月 18 日 | [[!DNL Target] 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.9.3 版的发行说明。 |
| 9 月 15 日 | [[!DNL Target] 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.9.3 版本的预发行说明。 |
| 9 月 12 日 | [[!DNL Target] 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.9.2 版的发行说明。 |
|  | [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 添加了 at.js 版本 2.10.3 的发行说明。 |
| 9 月 11 日 | [[!DNL Target] 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.9.2 版本的预发行说明。 |
| 9 月 6 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.9.1 版的发行说明。 |

## [!DNL Target] Standard/Premium 23.8.1（2023 年 8 月 9 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 9 月 1 日 | [环境](/help/main/administrating-target/environments.md##section_4F8539B07C0C45E886E8525C344D5FB0) | 更新了“设置报告的默认环境”下的注释。 |
| 8 月 30 日 | [隐私](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/privacy.html#aep){target=_blank} | 添加了新章节：“使用 Adobe Experience Platform Web SDK 时的数据流级别 IP 模糊处理” |
|  | [活动设置 - A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md#section_9F8092BE4225442896F926540292F221) | 在以下常见问题解答中，更正了预期数据显示在报表中的时间范围：“我刚刚创建了一个活动。但是为何看不到任何数据？” |
| 8 月 29 日 | [设备上决策支持的功能](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/supported-features.html){target=_blank} | 添加了在使用设备上决策 (ODD) 客户端时，支持的定位地理属性列表。 |
|  | [设备上决策概述](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html){target=_blank} | 添加了在使用设备上决策 (ODD) 服务器端时，支持的定位地理属性列表。 |
|  | [在具有 Web 视图的本机应用程序中使用 AEP Mobile SDK 实施 Target](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/native-app.html){target=_blank} | 新文章。 |
|  | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了有关即将举行的 Adobe Target 社区咖啡时间活动（2023 年 8 月 30 日）的信息：“通过做好旺季准备为获得最大 ROI 影响制定策略”网络研讨会后续活动。 |
| 8 月 14 日 | [活动 QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | 添加了信息，阐明在 at.js 2 时，使用空值加载网站上的页面&#x200B;*不会*&#x200B;从浏览器中删除 QA cookie。*x* 已部署。 |
|  | [A/Bn 测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | 更新了“置信度”的定义。 |
|  | [选件](/help/main/c-experiences/c-manage-content/manage-content.md) | 添加了注释，解释图像优惠不属于[!UICONTROL 企业用户权限]模型。 |
| 8 月 9 日 | [Target 移动版预览](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html){target=_blank} | 为主题更新了关于 [!DNL Adobe Experience Platform Mobile SDK] 当前版本的信息。 |
| 8 月 9 日 | [Target 移动版预览](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html){target=_blank} | 为主题更新了关于 [!DNL Adobe Experience Platform Mobile SDK] 当前版本的信息。 |
|  | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于安排在 2023 年 8 月 17 日举行的以下网络研讨会的信息：*通过做好旺季准备为获得最大 ROI 影响制定策略*。 |
|  | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.8.1 版的发行说明。 |

## [!DNL Target] Standard/Premium 23.7.1（2023 年 7 月 24-26 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
|  | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于安排在 2023 年 8 月 17 日举行的以下网络研讨会的信息：*通过做好旺季准备为获得最大 ROI 影响制定策略*。 |
| 8 月 7 日 | [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 澄清了有关 at.js 支持版本的信息。 |
| 7 月 25 日 | [[!DNL Target] 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md#edge) | 添加了有关计划于 2023 年 8 月 9 日进行的边缘基础设施升级的信息。 |
|  | [将 Target 边缘节点列入允许列表](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=zh-Hans){target=_blank} | 更新了边缘部署 41-48 的 NAT 和 IP/域。 |
| 7 月 24 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 23.7.1 版的发行说明。 |

---
keywords: target documentation change log;documentation updates;new topics;edits;updates;update
description: 本页列表了对Adobe Target文档所做的重要更改（按版本排序）。
title: Adobe Target 产品文档中的文档更改。
feature: release notes
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: 9faed3d7fa8659c04059486a23bbb3957a0f5e27
workflow-type: tm+mt
source-wordcount: '1814'
ht-degree: 29%

---


# 文档更改{#documentation-changes}

This page lists important changes made to the [!DNL Adobe Target] product documentation.

## Adobe Target Standard/Premium 20.7.1（2020 年 7 月 27 日） 

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 8月14日 | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md) | 添加了有关Recommendations活动中QA的已知问题。 |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 添加了文本，表明如果您在返回 `serverState` 的 `<script>` 内容中使用和使用标记，请确保HTML内容使用 `<\/script>` 而不是 `</script>`。 |
| 8月12日 | [了解目标UI](/help/c-intro/understand-the-target-ui.md) | 新主题。 |
|  | [Adobe TargetAPI概述](/help/api/api-overview.md) | 新主题。 |
| 8月10日 | [CNAME 和 Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 添加了文本，表明使用CNAME时Cookie头的大小将增加。 |
|  | [将目标与Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) | 新主题。 |
|  | [目标公告和事件](/help/r-release-notes/target-announcements.md) | 添加了视图以下归档网络研讨会的链接：“汇丰如何利用Adobe Target和人工智能大规模快速优化和提供个性化。” |
| 8月6日 | [自动定位](/help/c-activities/auto-target-to-optimize.md#how-long) | 更新了以下常见问题解答的文本：“我应该等待多久才能建好模型？” |
|  | [分类 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-classifications.md) | 已更新目标类型的文本。 |
| 8月5日 | [删除 Target Cookie](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md) | 更新了整个主题。 |
| 8月4日 | [目标公告和事件](/help/r-release-notes/target-announcements.md) | 添加了有关“使用人工智能和Adobe Target的个性化战略”网络研讨会的注册信息。 |
|  | [在浏览器中启用混合内容](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md) | 更新了主题。 |
| 8月3日 | [成功量度](/help/c-activities/r-success-metrics/success-metrics.md) | 添加了说明，以说 [!UICONTROL 明“增量计数] ”选项对访客与访问的含义。 |
| 31 年 7 月 | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md) | 添加了新的已知问题：&quot;显示“处理”标签的图像优惠。&quot; |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | 添加了用于执行 `getoffers()` pageLoad的代码示例。 |
|  | [目标公告和事件](/help/r-release-notes/target-announcements.md) | 增加了关于即将在8月5日举行的Adobe Target社区咖啡休息会的登记信息。 |
| 28 年 7 月 | [个性化洞察报](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)告、<br>[自动细分报](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)告和<br>重 [要属性报告](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) | 更新了主题顶部注释中的文本。 |
|  | [Auto-Allocate（自动分配）](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 添加了以下常见问题解答：<ul><li>在运行自动分配活动时，是否可以使用重置报告数据选项？</li><li>“自动分配”构建模型如何与环境相关？</li></ul> |
|  | [自动定位](/help/c-activities/auto-target-to-optimize.md) | 添加了以下常见问题解答：<ul><li>在运行自动目标活动时，是否可以使用“重置报告数据”选项？</li></ul>“注意事项”部分中的更新文本。 |
|  | [Automated Personalization常见问题解答](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | 添加了以下常见问题解答：<ul><li>运行Automated Personalization活动时，我是否可以使用“重置报告数据”选项？</li><li>Automated Personalization如何打造环境模式？</li></ul> |
|  | [支持的浏览器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | 添加了有关Internet Explorer和未知元素的信息。 |
|  | [客户属性](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Updated following paragraph:<br>[!DNL Adobe] does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the [!DNL Experience Cloud] and, thus, be available for use for targeting in [!DNL Target]. 在我们当前的设计中，可能不会载入少量数据（大型生产批次中高达0.1%）。 |
| 27 年 7 月 | [管理 Target](/help/administrating-target/administrating-target.md) | 更新了此页面上所有链接主题中的文本，以反映“管理”页面的新 [!UICONTROL UI] 更改。 |
|  | [目标公告和事件](/help/r-release-notes/target-announcements.md) | 做出了以下更改： <ul><li>添加了以下网络研讨会的注册信息：“汇丰如何利用Adobe Target和人工智能大规模快速优化和提供个性化。”</li><li>添加了有关Adobe再次被评为Gartner个性化引擎魔力象限领导者的信息。</li></ul> |
|  | [Form-Based Experience Composer（基于表单的体验编辑器）](/help/c-experiences/form-experience-composer.md) | 第4步中阐明的信息：选择位置。 |
| 24 年 7 月 | <br>[at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 添加了有关 at.js 2.3.2 的信息。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：20.7.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe Target Standard/Premium 20.5.1（2020 年 6 月 17 日） 

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 17 年 7 月 | [目标公告和事件](/help/r-release-notes/target-announcements.md) | 增加了有关7月22日Adobe Target咖啡假期的信息。 |
| 15 年 7 月 | [与手动测试相比，“自动分配”功能可以提高测试结果和收入](/help/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md) | 新主题。 |
| 14 年 7 月 | [自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、自<br>[动目标](/help/c-activities/auto-target-to-optimize.md)、自<br><br>[动个性化常见问题解答](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | 添加了常见问题解答，建议您不要在活动中途更改目标指标。 |
| 7 年 7 月 | [目标公告和事件](/help/r-release-notes/target-announcements.md) | 增加了有关7月8日Adobe Target咖啡休息会的信息。 |
| 6月25日 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了有关Target Standard/Premium 20.6.1版本（2020年7月）的信息。 |
|  | [目标文档概述](/help/r-release-notes/target-documentation.md) | 详细介绍不同文档来源的新 [!DNL Target] 主题。 |
| 6月23日 | [目标公告和事件](/help/r-release-notes/target-announcements.md) | 添加了有关6月24日Adobe Target咖啡假期的信息。 |
|  | [配置文件属性](/help/c-target/c-visitor-profile/profile-parameters.md) | 添加了注意事项，不建议创建使用另一个用户档案脚本中一个用户档案脚本的结果的从属用户档案脚本。 |
|  | [at.js 的工作原理](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | 添加了以下视频：办公时间：at.js提示和概述 |
| 6月17日 | [CNAME 和 Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 更新了主题。 |
|  | [响应令牌](/help/administrating-target/response-tokens.md) | 添加了有关自动目标和Automated Personalization活动 [!UICONTROL 流量分配方法] 的响 [!UICONTROL 应令牌的信息] 。 |
|  | [活动创建](/help/c-integrating-target-with-mac/a4t/campaign-creation.md) | 添加了有关目标分析(A4T)支持自动分配活动的信息。 |
|  | [用户](/help/administrating-target/c-user-management/c-user-management/user-management.md) | 在“指定角色和权限 [!UICONTROL ”下] ，添 *加了有关新发布者角色的信息*。 |
|  | [配置企业权限](/help/administrating-target/c-user-management/property-channel/properties-overview.md) | 在第6步中添加了有 [!UICONTROL 关新] “发布者 *”角色的信息：指定角色和权限*。 |
|  | [企业用户权限](/help/administrating-target/c-user-management/property-channel/property-channel.md) | 添加了指向Office小 *时的链接：目标高级工作区会话*。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：20.5.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe Target Standard/Premium 20.4.1（2020 年 5 月 6 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 6月15日 | [Target 发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了有关at.js 1.8.2和at.js 2.3.1版本的信息。 |
|  | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 添加了有关at.js 1.8.2和at.js 2.3.1版本的信息。 |
|  | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 更新了20.5.1 [!DNL Target Standard/Premium] 版本（2020年6月17日）的说明，以包含中有关A4T支持的信息 [!DNL Analysis Workspace]。 |
| 6月12日 | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 添加了有关 `deviceIdLifetime` 设置的信息。 |
|  | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了有关at.js 1.8.2和at.js 2.3.1版本的信息。 |
| 6月8日 | [目标移动应用程序常见问题解答](/help/c-target-mobile-app/target-for-mobile-apps-faq.md) | 更新了以下常见问题解答的文本：“目标移动是否只是Adobe Target高级产品SKU的功能？” |
|  | [查看报表 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | 更新了整个主题。 |
| 6月5日 | [目标公告和事件](/help/r-release-notes/target-announcements.md) | 增加了有关6月10日Adobe Target咖啡假期的信息。 |
|  | [提升度和置信度 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md) | 更新了以下常见问题解答的文本：“为什么我看不到计算指标的提升和信心？” |
| 6月4日 | [A4T 报表](/help/c-integrating-target-with-mac/a4t/reporting.md) | 更新了“Analytics中的报告”部分。 |
| 6月1日 | [目标公告](/help/r-release-notes/target-announcements.md) | 添加了新页面以宣布即将推出的目标事件。 |
|  | [适用于响应式体验的移动设备视区](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) | 更新了Apple iPhone 11、Apple iPhone SE和Google Pixel 2 XL型号的视区尺寸和分辨率。 |
| 28 年 5 月 | [报表常见问题解答](/help/c-reports/reporting-frequently-asked-questions.md) | 添加了以下新常见问题解答： <ul><li>如何计算新访客和退回访客指标？</li></ul> |
| 27 年 5 月 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了有关目标分析(A4T)支持自动分配活动的信息。 |
| 26 年 5 月 | [配置文件属性](/help/c-target/c-visitor-profile/profile-parameters.md) | 添加了以下信息：&quot;在禁用脚本后，该参数仍保留在用户档案中。 其用户档案已包含活动受众中使用的参数的用户将符合该活动的条件。” |
| 21 年 5 月 | [允许列表目标边节点](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | 已添 `mboxedge30.tt.omtrdc.net` 加到列表。 |
| 20 年 5 月 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了有关即将发布的Target Standard/Premium 20.6.1（2020年6月10日）版本的信息。 |
|  | [主机](/help/administrating-target/hosts.md) | 在“安全最佳实践”部分添加了注释。 |
| 14 年 5 月 | [Target 发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了有关用户档案批处理状态API v2更改的信息。 |
| 13 年 5 月 | [CNAME 和 Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 添加了“已知限制”部分。 |
| 11 年 5 月 | [主机](/help/administrating-target/hosts.md) | 添加了有关在重定向和中使用ubox功能允许列表的信息。 |
|  | [使用重定向器](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | 添加了有关使用主机来避免“打开重定向漏洞”的信息。 |
|  | [将“推荐”与电子邮件集成](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | 添加了有关使用主机来避免“打开重定向漏洞”的信息。 |
|  | [电子邮件：实施 Target](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | 添加了有关使用主机来避免“打开重定向漏洞”的信息。 |
|  | [活动 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 更新了“注意事项”部分。 |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 更新了“设置”下的“overrideMboxEdgeServer”行。 |
| 6 年 5 月 | [Apple 智能防跟踪 (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | 添加了有关ITP 2.3的信息。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：20.4.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe Target Standard/Premium 20.2.1（2020 年 2 月 19 日） 

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 4 年 5 月 | [报表常见问题解答](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | 新增了常见问题解答：“为什么我的A/B或MVT活动中体验之间的流量分配不均？” |
| 29 年 4 月 | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md) | 增加了极端订单报告的已知问题。 |
| 28 年 4 月 | [配置文件和变量一览表](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | 删除了有关使用较 `user.header('x-forwarded-for')` 新的AWS边缘来检索用户IP地址的信息。 此命令现在可用于较新的AWS边缘。 |
|  | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 将Target Standard/Premium版本(20.4.1)的日期更改为5月6日。 |
| 23 年 4 月 | [CNAME 和 Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 更新了主题。 |
| 22 年 4 月 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了新部分： *用户档案批处理状态API v2更改（2020年5月4日）。* |
| 14 年 4 月 | [允许列表目标边缘主机](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | 新主题。 |
| 10 年 4 月 | [单页应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | 添加了新部分：“实施最佳实践。” |
| 7 年 4 月 | [提升度和置信度 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | 更新了“为什么我看不到计算指标的提升和信心？”的文本 |
| 2 年 4 月 | [配置文件和变量一览表](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | 添加了有关使用 `user.header('x-forwarded-for')` 较新的AWS边缘来检索用户IP地址的信息。 |
|  | [从 at.js 1.*x* 升级到 at.js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | 添加了以下注释：<ul><li>安装 ECID 库 v4.3.0+ 和 at.js 2.*x* 之后，您将能够创建跨越独特域的活动并跟踪用户。请务必注意，此功能仅在会话过期后才可用。</li></ul> |
| 3月30日 | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | 添加了影响at.js 2.2.0之前版本的at.js的已知问题。当页面元素中不存在Adobe Analytics代码时，此问题导致单击跟踪无法报告目标分析(A4T)中的转换。 |
|  | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 将以下信息添加到at.js版本2.2.0详细信息中：<ul><li>修复了当页面元素中不存在Adobe Analytics代码时，导致单击跟踪无法报告目标分析(A4T)中的转换的问题。</li></ul> |
| 3月25日 | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 添加了有关以下新版at.js的信息：<ul><li>at.js版本2.3.0</li><li>at.js版本1.8.1</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 在“设置”部分添加了以下新行：<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>添加了以下新章节：<ul><li>内容安全策略</li></ul> |
| 3月24日 | [Apple 智能防跟踪 (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | 添加了有关以下影响的信息：<ul><li>用户档案基于3rdPartyID的脚本</li><li>iOS设备中的QA/预览URL</li></ul> |
| 3月20日 | [发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 指出Target Standard/Premium 20.2.1版本将于2020年3月23日发布。 |
| 3月13日 | [限制](/help/r-troubleshooting-target/target-limits.md) | 更新了“受众、可重复使用的每个帐户”的数量。 |
| 3月12日 | [发行说明（当前版本）](/help/r-release-notes/release-notes.md#summit) | 添加了注册信息以免费访问在线数字峰会。 |
| 3月9日 | [隐私](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | 在“替换IP地址的最后八位字节”部分添加了更多信息。 |
|  | [使用多值属性](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | 在JavaScript中传 *递多值参数中更新了代码示例*。 |
|  | [自定义实体属性](/help/c-recommendations/c-products/custom-entity-attributes.md) | 在“实现多 *值属性* ”下 *的“使用API”中添加了代码示例*。 |
| 3月4日 | [配置文件属性](/help/c-target/c-visitor-profile/profile-parameters.md) | 更新了整个主题，对“最佳实践”部分进行了大量修订。 |
| 2月21日 | [发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了有关新Adobe Experience Cloud导航的信息。 |
| 2月20日 | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Updated the description for the `enabled` setting. 添加了以下设置的信息： `pageLoadEnabled` 和 `viewsEnabled`。 |
|  | [地域](/help/c-target/c-audiences/c-target-rules/geo.md) | 添加了 `mboxOverride.browserIp` 在at.js 1中支持的注意事项。*x*。 |
|  | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 明确了说明目标团队支持哪些版本的at.js的文本。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：20.2.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe Target Standard/Premium 20.1.1（2020 年 2 月 4 日） 

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 2月4日 | [发行说明](/help/r-release-notes/release-notes.md)：20.1.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

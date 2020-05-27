---
keywords: target documentation change log;documentation updates;new topics;edits;updates
description: 本页列表了对Adobe目标文档所做的重要更改（按版本排序）。
title: Adobe Target 产品文档中的文档更改。
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: 7857b9765a9338405b6705046333f11f8255b365
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 34%

---


# 文档更改{#documentation-changes}

This page lists important changes made to the [!DNL Adobe Target] product documentation.

## Adobe Target Standard/Premium 20.4.1（2020 年 5 月 6 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 27 年 5 月 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了有关目标分析(A4T)支持自动分配活动的信息。 |
| 26 年 5 月 | [配置文件属性](/help/c-target/c-visitor-profile/profile-parameters.md) | 添加了以下信息： &quot;在禁用脚本后，该参数仍保留在用户档案中。 其用户档案已包含活动受众中使用的参数的用户将符合该活动的条件。” |
| 21 年 5 月 | [白名单目标边缘节点](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | 已添 `mboxedge30.tt.omtrdc.net` 加到列表。 |
| 20 年 5 月 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了有关即将发布的目标标准版／高级版20.6.1（2020年6月10日）的信息。 |
|  | [主机](/help/administrating-target/hosts.md) | 在“安全最佳实践”部分添加了注释。 |
| 14 年 5 月 | [Target 发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了有关用户档案批处理状态API v2更改的信息。 |
| 13 年 5 月 | [CNAME 和 Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 添加了“已知限制”部分。 |
| 11 年 5 月 | [主机](/help/administrating-target/hosts.md) | 添加了有关将ubox功能用于重定向和白名单的信息。 |
|  | [使用重定向器](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | 添加了有关使用主机来避免“打开重定向漏洞”的信息。 |
|  | [将“推荐”与电子邮件集成](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | 添加了有关使用主机来避免“打开重定向漏洞”的信息。 |
|  | [电子邮件：实施 Target](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | 添加了有关使用主机来避免“打开重定向漏洞”的信息。 |
| 7 年 5 月 | [Target 发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 随着mbox.js即将于2020年8月30日弃用，Adobe目标产品经理David Son最近主持了一个开发人员聊天，讨论将mbox.js迁移到at.js的好处。 您可以通过链接观看未来30天的网络研讨会。 |
|  | [活动 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 更新了“注意事项”部分。 |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 更新了“设置”下的“overrideMboxEdgeServer”行。 |
| 6 年 5 月 | [Apple 智能防跟踪 (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | 添加了有关ITP 2.3的信息。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：20.4.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe Target Standard/Premium 20.2.1（2020 年 2 月 19 日） 

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 4 年 5 月 | [报表常见问题解答](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | 新增了常见问题解答： “为什么我的A/B或MVT活动中体验之间的流量分配不均？” |
| 29 年 4 月 | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md) | 增加了极端订单报告的已知问题。 |
| 28 年 4 月 | [配置文件和变量一览表](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | 删除了有关使用较 `user.header('x-forwarded-for')` 新的AWS边缘来检索用户IP地址的信息。 此命令现在可用于较新的AWS边缘。 |
|  | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 将目标标准版／高级版(20.4.1)的日期更改为5月6日。 |
| 23 年 4 月 | [CNAME 和 Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 更新了主题。 |
| 22 年 4 月 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了新部分： *用户档案批处理状态API v2更改（2020年5月4日）。* |
| 20 年 4 月 | [Target 发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了新部分： *Adobe目标技能构建器： 开发人员聊天，将Adobe目标的mbox.js迁移到at.js。* |
| 14 年 4 月 | [白名单目标边缘主机](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | 新主题。 |
| 10 年 4 月 | [单页应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | 添加了新部分： “实施最佳实践。” |
| 7 年 4 月 | [提升度和置信度 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | 更新了“为什么我看不到计算指标的提升和信心？”的文本 |
| 2 年 4 月 | [配置文件和变量一览表](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | 添加了有关使用 `user.header('x-forwarded-for')` 较新的AWS边缘来检索用户IP地址的信息。 |
|  | [从 at.js 1.*x* 升级到 at.js 2.*x *](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | 添加了以下注释：<ul><li>安装 ECID 库 v4.3.0+ 和 at.js 2.*x* 之后，您将能够创建跨越独特域的活动并跟踪用户。请务必注意，此功能仅在会话过期后才可用。</li></ul> |
| 3月30日 | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | 添加了影响at.js 2.2.0之前版本的at.js的已知问题。当页面元素上不存在Adobe Analytics代码时，此问题导致单击跟踪无法报告目标分析(A4T)中的转换。 |
|  | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 将以下信息添加到at.js版本2.2.0详细信息中：<ul><li>修复了当页面元素中不存在Adobe Analytics代码时，导致单击跟踪无法报告目标(A4T)中的转换的问题。</li></ul> |
| 3月25日 | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 添加了有关以下新版at.js的信息：<ul><li>at.js版本2.3.0</li><li>at.js版本1.8.1</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 在“设置”部分添加了以下新行：<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>添加了以下新章节：<ul><li>内容安全策略</li></ul> |
| 3月24日 | [Apple 智能防跟踪 (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | 添加了有关以下影响的信息：<ul><li>用户档案基于3rdPartyID的脚本</li><li>iOS设备中的QA/预览URL</li></ul> |
| 3月20日 | [发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 指出目标标准版／高级版20.2.1版本将于2020年3月23日发布。 |
| 3月13日 | [限制](/help/r-troubleshooting-target/target-limits.md) | 更新了“受众、可重复使用的每个帐户”的数量。 |
| 3月12日 | [发行说明（当前版本）](/help/r-release-notes/release-notes.md#summit) | 添加了注册信息以免费访问在线数字峰会。 |
| 3月9日 | [隐私](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | 在“替换IP地址的最后八位字节”部分添加了更多信息。 |
|  | [使用多值属性](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | 在JavaScript中传 *递多值参数中更新了代码示例*。 |
|  | [自定义实体属性](/help/c-recommendations/c-products/custom-entity-attributes.md) | 在“实现多 *值属性* ”下 *的“使用API”中添加了代码示例*。 |
| 3月4日 | [配置文件属性](/help/c-target/c-visitor-profile/profile-parameters.md) | 更新了整个主题，对“最佳实践”部分进行了大量修订。 |
| 2月21日 | [发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了有关新的Adobe Experience Cloud导航的信息。 |
| 2月20日 | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Updated the description for the `enabled` setting. 添加了以下设置的信息： `pageLoadEnabled` 和 `viewsEnabled`。 |
| 2 月 19 日 | [发行说明](/help/r-release-notes/release-notes.md) | 添加了有关mbox.js库即将弃用的信息。 |
|  | [地域](/help/c-target/c-audiences/c-target-rules/geo.md) | 添加了 `mboxOverride.browserIp` 在at.js 1中支持的注意事项。*x*。 |
|  | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 明确了说明目标团队支持哪些版本的at.js的文本。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：20.2.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe Target Standard/Premium 20.1.1（2020 年 2 月 4 日） 

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 2月4日 | [发行说明](/help/r-release-notes/release-notes.md)：20.1.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

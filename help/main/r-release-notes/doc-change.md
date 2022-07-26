---
keywords: target 文档变更日志;文档更新;新主题;编辑;更新;更新
description: 及时了解对 [!DNL Adobe Target] 文档的重要补充和变更。
title: 可在何处查看 [!DNL Target] 的文档更新？
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 7de7bb1b3bc70a559d41edece8cae2d388cb0dda
workflow-type: ht
source-wordcount: '1778'
ht-degree: 100%

---

# 文档更改

此页面列出对 [!DNL Adobe Target] 产品文档作出的重大变更。

## [!DNL Adobe Target] Standard/Premium 22.10.1（交错发布：2022 年 10 月 10 日至 13 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 12 月 14 日 | [报表设置](/help/main/c-reports/c-report-settings/report-settings.md#environment) | 在“环境”部分下添加了关于使用 [!DNL Adobe Experience Platform](AEP) 将指标数据发送到 [!DNL Target] 的注释。 |
| 11 月 29 日 | [地域](/help/main/c-target/c-audiences/c-target-rules/geo.md) | 通过添加以下段落来澄清文本：<ul><li>访问者的地理信息是根据 [!DNL Target] 位置请求（mbox 请求）的原始 IP 地址确定的。IP 到地理位置的解析是在新会话的第一次调用时完成的。这意味着，如果访问者的 IP 地址在访问期间发生变化，地理信息仍基于第一次调用的 IP 地址。</li></ul> |
| 11 月 28 日 | *Adobe Target 开发人员指南* 中的[模型（阻止列表）API 概述](https://developer.adobe.com/target/before-administer/models-api/){target=_blank}。 | 新的模型 API。<br>可以从 [!DNL Target] 机器学习算法中阻止功能，防止在任何[!UICONTROL 自动定位]或[!UICONTROL 自动个性化]模型或活动中使用它们。 |
|  | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了有关模型 API 版本（2022 年 11 月 23 日）的信息。 |
| 11 月 23 日 | [使用 at.js 实施 Analytics for Target (A4T) 之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md) | 更新了链接 [Marketing Cloud 集成设置表单](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}。 |
| 11 月 16 日 | [Adobe Target 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了以下活动的注册信息：<ul><li>[!DNL Adobe Target] 社区问答喝咖啡休息时间（11 月 29 日）</li></ul> |
| 11 月 8 日 | [A/B 测试应该持续多长时间？](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) | 添加了重要说明：要获得准确的结果，您在更改[!DNL Adobe Target][!UICONTROL 样本量计算器]中的任何参数数量之前必须重新加载页面。另外还在实际的[计算器](https://experienceleague.adobe.com/tools/calculator/testcalculator.html){target=_blank}中添加了一条说明。 |
|  | [重定向选件 — A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682) | 在表中更新了对 `adobe_mc_sdid` 参数的描述。 |
|  | [活动故障诊断](/help/main/c-activities/c-troubleshooting-activities/troubleshooting-activities.md) | 新增部分：“活动转换后，访客没有任何体验。” |
|  | [自定义参数](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | 添加了说明：您从[!UICONTROL 筛选依据]下拉列表中选择的 mbox 在创建活动时不会保存。此选项允许您根据选定的 mbox 筛选参数。 |
| 11 月 2 日 | 已知问题和已解决的问题 | 已移除页面并将相关问题重新定位到适当的页面，以便信息带有相应的上下文。 |
| 10 月 25 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 22.10.3 版的发行说明。 |
| 10 月 19 日 | [类别亲和力](/help/main/c-target/c-visitor-profile/category-affinity.md#section_8B86C7FF50294208866ABF16F07D5EB9) | 添加了一条注释，说明在单个 mbox 调用中传递多个类别时的评分。 |
| 10 月 18 日 | [创建 [!UICONTROL Automated Personalization] 活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) | 更新了文本以指示尽管可在一次 AP 测试中创建最多 30000 个体验，但在使用小于 10000 个不同的体验时算法才能发挥最佳效果。即使为活动启用了[!UICONTROL 不允许重复项]选项后，也适用同样的限制。 |
|  | [Automated Personalization 常见问题](/help/main/c-activities/t-automated-personalization/automated-personalization-faq.md) | 更新了文本以指示尽管可在一次 AP 测试中创建最多 30000 个体验，但在使用小于 10000 个不同的体验时算法才能发挥最佳效果。即使为活动启用了[!UICONTROL 不允许重复项]选项后，也适用同样的限制。 |
| 10 月 14 日 | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于 [!DNL Adobe Target] 社区问答喝咖啡休息时间（2022 年 10 月 26 日）的注册信息。 |
| 10 月 10 日 | [[!UICONTROL 可视化编辑帮助程序]扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) | 新文章。 |
|  | [排除与可视化体验编辑器相关的问题](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md) | 更新了“[VEC 中不显示我的页面（仅 VEC）](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md#does-not-load)”部分。 |
| 10 月 4 日 | [A/Bn 测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | 新主题。<br>本文中的信息取代了&#x200B;*用于 A/B 测试的 Adobe Target 计算* pdf 文件，以前可在此站点上下载。 |
|  | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 22.10.1 版的发行说明。 |

## [!DNL Adobe Target] Standard/Premium 22.9.1（交错发布：2022 年 9 月 13 日至 15 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 10 月 3 日 | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 更新了 [!DNL Target Standard/Premium] 22.10.1 版本的日期。 |
| 9 月 22 日 | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于以下活动的信息：<ul><li>[!DNL Adobe Target]社区问答茶歇时间（2022 年 9 月 28 日）</li></ul> |
| 9 月 15 日 | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于以下网络研讨会的信息：<ul><li>微调 AI 支持的个性化：[!DNL Adobe Target] 中的新增功能（2022 年 10 月 11 日）</li></ul> |
| 9 月 13 日 | [了解  [!DNL Target]  UI](/help/main/c-intro/understand-the-target-ui.md) | 添加了有关在 [!DNL Recommendations] 馈送失败时发送的通知的信息。 |
|  | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 22.9.1 版的发行说明。 |

## Adobe Target Standard/Premium 22.8.1（交错发布：2022 年 8 月 17 日至 18 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 8 月 22 日 | [[!DNL Adobe Target] 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于以下公告的信息：<ul><li>[!DNL Target] 在个性化引擎的 Gartner Magic Quadrant 方面评选佼佼者 (2022)</li></ul>添加了关于以下即将发生的事件的信息：<ul><li>[!DNL Adobe Target] 社区问答茶歇（2022 年 8 月 31 日）</li><li>厨师的收藏集：个性化食谱（2022 年 8 月 30 日）</li><li>[!DNL Adobe Target] Skill Builders – 移动体验优化（2022 年 9 月 6 日）</li><li>[!DNL Adobe Target] Skill Builders – 人工智能驱动的个性化和推荐（2022 年 9 月 15 日）</li></ul>为以下过去的网络研讨会添加了录像链接：<ul><li>Adobe: Personalization Industry Insider – 零售（2022 年 8 月 11 日）</li></ul> |
| 8 月 22 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 22.8.1 版的发行说明。 |

## Adobe Target Standard/Premium 22.6.1（交错发布：2022 年 6 月 7 日- 9 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 6 月 30 日 | [Adobe Target 开发人员指南](https://developer.adobe.com/target/){target=_blank} | 发布了 *Adobe Target 开发人员指南*，将所有[!DNL Target]开发者内容整合到一个方便的门户中。该门户包含有关实施 [!DNL Target] 和 [!DNL Recommendations]、[!DNL Target] SDK 以及 [!DNL Target] API 的信息。 |
|  | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 22.6.2 版的发行说明。 |
|  | [Target 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了以往网络研讨会会议的录像链接。 |
| 6 月 14 日 | [计划和实施 Recommendations](https://developer.adobe.com/target/implement/recommendations/){target=_blank} | 更新了以下部分中的代码示例：<ul><li>购物车添加/购物车视图/结账页面</li><li>排除访客购物车中已有的项目</li></ul> |
| 6 月 7 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了 [!DNL Target Standard/Premium] 22.6.1 版的发行说明。 |

## Adobe Target Standard/Premium 22.5.1（2022 年 5 月 11 至 13 日，交错发行）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 6 月 7 日 | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了关于 [!DNL Target Standard/Premium] 22.6.1 版的预发行信息。 |
| 5 月 31 日 | [Target 公告和活动](/help/main/r-release-notes/target-announcements.md#webinar-series) | 添加了关于即将举办的 [!DNL Adobe Target] 社区咖啡时间活动的信息（2022 年 6 月 29 日） |
| 5 月 25 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了关于 [!DNL Target] Platform 版（2022 年 5 月 25 日）和 at.js 2.9.0 版（2022 年 5 月 27 日）的信息。 |
|  | [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 添加了有关 at.js 2.9.0 版的信息。 |
|  | [用户代理和客户端提示](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank} | 新主题。 |
|  | [Target 公告和活动](/help/main/r-release-notes/target-announcements.md#webinar-series) | 添加了以下网络研讨会的录像链接：迪克的体育用品：零售业的个性化及变化（2022 年 5 月 19 日） |
| 5 月 23 日 | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了 at.js 2.9.0 版（2022 年 5 月 25 日）预发行版本说明 |
| 5 月 11 日 | [Target 公告和活动](/help/main/r-release-notes/target-announcements.md#webinar-series) | 添加了以下网络研讨会的信息和注册链接：<ul><li>迪克体育用品：个性化和零售业的变化</li><li>Adobe：个性化行业内幕 — 金融服务和保险</li><li>国民城市银行 (City National Bank)：如何在数字优化中实现前 1% 的目标</li><li>Adobe：精准个性化 — [!DNL Adobe Analytics] 和 [!DNL Target]</li><li>国民城市银行：从零到英雄 — 启动并扩展个性化计划</li><li>Adobe：发现高影响力的优化机会</li><li>Adobe：个性化行业内幕 — 零售业</li></ul>添加了以下网络研讨会的录像：<ul><li>[!DNL Adobe Target] 的实时个性化服务</li></ul> |
|  | [内容安全策略 (CSP) 指令](https://developer.adobe.com/target/before-implement/privacy/content-security-policy/){target=_blank} | 添加了常见问题解答部分。 |
|  | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了关于 [!DNL Target Standard/Premium] 22.5.1 和 Target 平台（2022 年 5 月 11 日至 13 日）发行信息。 |

## Adobe Target Standard/Premium 22.4.1（4 月 28 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 5 月 10 日 | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了关于 [!DNL Target Standard/Premium] 22.5.1 版的预发行信息。 |
| 4 月 28 日 | [企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#move-audience) | 添加了以下常见问题解答：<ul><li>我是否可以将受众从一个工作区移动到另一个工作区？</li></ul> |
|  | [[!UICONTROL 自动分配] 概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#section_0E72C1D72DE74F589F965D4B1763E5C3) | 添加了以下常见问题解答：<ul><li>[!UICONTROL 自动分配] 活动能否在测试过程中调整回看窗口，以考虑随时间变化的趋势？</li><li>如果获胜体验与访客在获得活动资格时看到的不同，那么 [!UICONTROL 自动分配] 是否向回访访客显示获胜体验？</li></ul> |
|  | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了关于 [!DNL Target Standard/Premium] 22.4.1 和 Target 平台（2022 年 4 月 27 日）发行信息。 |

## Adobe Target Standard/Premium 22.3.1（4 月 5 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 4 月 26 日 | [Target 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于以下活动的信息：<ul><li>网络研讨会：Adobe Target 实时个性化（2022 年 4 月 28 日）</li><li>[!DNL Adobe Target] 社区问答喝咖啡休息时间（2022 年 5 月 25 日）</li></ul> |
|  | [重定向选件 — A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#discrepancies) | 添加了以下常见问题解答：<ul><li>在 A4T 活动中使用重定向选件时，如何最大限度地减少流量分布的差异？</li></ul> |
|  | [AEM 体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 添加了以下部分：<ul><li>从导出到目标的体验片段中移除 ClientLib 和无关 HTML</li></ul> |
| 4 月 21 日 | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了关于 [!DNL Target] 平台计划于 2022 年 4 月 17 日发行的预发行信息。 |
| 4 月 20 日 | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了有关 [!DNL Target Standard/Premium] 22.4.1 版的预发行信息。 |
| 4 月 14 日 | [可视体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) | 向“重新排列”部分添加了解释如何使用[!UICONTROL 移动]和[!UICONTROL 重新排列]操作处理因延迟加载 DOM 元素而产生 VEC 行为不一致的信息。 |
| 4 月 13 日 | [Target 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于以下事件的信息：<ul><li>[!DNL Adobe Target] 社区问答喝咖啡休息时间（2022 年 4 月 27 日）</li></ul> |
|  | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了关于 [!DNL Target] 平台版本的发行信息。 |
| 4 月 4 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 更新了关于 [!DNL Target Standard/Premium] 22.3.1 版的信息。 |

## Adobe Target Standard/Premium 22.2.1（2022 年 2 月 1 日） 

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 3 月 30 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了关于 [!DNL Target] 平台版本的发行信息。 |
| 3 月 28 日 | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了关于 [!DNL Target] 平台版本的预发行信息。 |
| 3 月 22 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了关于 [!DNL Target Standard/Premium] 客户工程修复版本的发行信息。 |
|  | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了关于 [!DNL Target Standard/Premium] 22.3.1 的预发行信息。 |
| 3 月 17 日 | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了关于 [!DNL Target Standard/Premium] 客户工程修复版本的预发行信息。 |
|  | [mbox3rdPartyId 的实时配置文件同步](/help/main/c-target/c-visitor-profile/3rd-party-id.md) | 更新了以下有关配置文件同步的句子：“每 5-10 分钟与配置文件存储同步一次更新”。 |
| 3 月 8 日 | [Target 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于以下事件的信息：<ul><li>[!DNL Adobe Target] 社区问答喝咖啡休息时间（2022 年 3 月 30 日）</li></ul> |
| 3 月 7 日 | [创建受众](/help/main/c-target/c-audiences/audiences.md#aep) | 在“利用来自 [!DNL Adobe Experience Platform] 的受众”下添加了新的部分：<ul><li>个性化用例</li></ul> |
| 2 月 25 日 | [自动分配和自动定位活动支持 A4T](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) | 更新了以下部分：<ul><li>[自动分配和自动定位](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#both)</li><li>[自动分配](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa)</li></ul> |
|  | [解释自动分配报表](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | 添加了新的常见问题解答：<ul><li>对于使用 [!UICONTROL Analytics 作为报表源] (A4T) 的[!UICONTROL 自动分配]活动，是否有“无入选项目”、“入选项目”和“星标”徽章可用？</li></ul> |
|  | [创建仅限活动的受众](/help/main/c-target/creating-activity-only-audience.md) | 在“注意事项”部分中添加了讨论排除规则的信息。 |
| 2 月 10 日 | [可视化体验编辑器助手扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) | 添加了有关在可视化体验编辑器 (VEC) 中使用 Service Worker 加载网站的信息。 |
| 2 月 7 日 | [Target 公告和活动](/help/main/r-release-notes/target-announcements.md) | 添加了关于以下事件的信息：<ul><li>[!DNL Adobe Target] 社区问答喝咖啡休息时间（2022 年 2 月 23 日）</li></ul> |
| 2 月 3 日 | [创建受众](/help/main/c-target/c-audiences/audiences.md#RTCDP) | 添加了新的部分和视频：“视频：利用 Real-time CDP 和 [!DNL Adobe Target] 的下一次点击个性化”。 |
| 2 月 2 日 | [内容交付故障诊断](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md#escape) | 添加了新的部分：“[!DNL Target] 配置文件属性值中的转义双引号无法按预期发挥作用”。 |
| 2 月 1 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了有关 [!DNL Target Standard/Premium] 22.2.1 版本的信息。 |

## [!DNL Adobe Target Standard/Premium] 22.1.1（2022 年 1 月 12 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 1 月 31 日 | [Target 发行说明（预发行版本）](/help/main/r-release-notes/target-release-notes.md) | 添加了有关 [!DNL Target Standard/Premium] 22.2.1 版的预发行信息。 |
| 1 月 28 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了有关 at.js 2.8.1 版本的信息。 |
|  | [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 添加了有关 at.js 2.8.1 版本的信息。 |
| 1 月 27 日 | [AEM 体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 更新了主题并添加了有关 [!DNL AEM as a Cloud Service] 和 [!DNL Adobe I/0] 的信息。 |
| 1 月 26 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了有关 [!DNL Target Standard/Premium] 22.1.2 版本的信息。 |
|  | [创建受众](/help/main/c-target/c-audiences/audiences.md) | 添加了关于 [!DNL Adobe Experience Platform] 受众的信息。 |
|  | [合并多个受众](/help/main/c-target/combining-multiple-audiences.md) | 添加了关于 [!DNL Adobe Experience Platform] 受众的信息。 |
| 1 月 21 日 | [at.js 版本详细信息](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 添加了有关 at.js 1.8.3 版本的信息。 |
| 1 月 19 日 | [从 at.js 1.*x* 升级到 at.js 2.x *x*](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 添加了以下部分：“at.js 2.*x* 不支持使用 vst.* 参数创建受众” |
| 1 月 12 日 | [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md) | 添加了有关 [!DNL Target Standard/Premium] 22.1.1 版本的信息。 |
|  | [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} | 添加了指向教程的链接，其中提供有关使用 Web SDK 实施 [!DNL Adobe Experience Cloud] 的说明。 |

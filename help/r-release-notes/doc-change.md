---
keywords: target 文档变更日志;文档更新;新主题;编辑;更新;更新
description: 及时了解对 Adobe [!DNL Target] 产品文档的重要补充和变更。
title: 可在何处查看 Target 的文档更新？
feature: 发行说明
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: fb0a62ecc5609e7b8ef5f6a4fb5a94f8ba025fec
workflow-type: tm+mt
source-wordcount: '1663'
ht-degree: 74%

---

# Adobe Target 产品文档中的文档更改

此页面列出对 [!DNL Adobe Target] 产品文档作出的重大变更。

## Adobe [!DNL Target] Standard/Premium 21.5.1（2021 年 6 月 8 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 12 月 7 日 | [Target 公告和活动](/help/r-release-notes/target-announcements.md) | 添加了有关以下事件的信息：<ul><li>网络研讨会：量化集成Adobe Analytics + [!DNL Adobe Target]的显着ROI、洞察和节省时间。</li><li>[!DNL Adobe Target] 社区问答型咖啡时间定于2021年7月21日星期三上午8时举行（太平洋夏季时间，GMT-7）。</li></ul> |
|  | [“推荐”常见问题解答](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md#less-than-60) | 添加了以下常见问题解答：“如何只推荐新文章或视频？” |
|  | [限制](/help/r-troubleshooting-target/target-limits.md) | 更新了“Target API调用”部分中的文本。 |
|  | [adobe.target.getOffers() - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | 更新了`consumerId`键的描述。 |
|  | [自定义全局 mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/customize-global-mbox.md) | 更新了步骤1，以指示在您选择新的mbox后自动保存所做的更改。 |
|  | Experience Cloud 设备协作 | 已删除的主题。此功能已弃用。 |
| 6 月 29 日 | [活动 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 添加了以下章节：<ul><li>Target JavaScript库[!UICONTROL QA模式]兼容性</li><li>预览URL</li></ul> |
| 6 月 24 日 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 更新了[!DNL Target Standard/Premium] 21.6.1版本（2021年6月30日）的预发行说明。 |
| 6 月 16 日 | [[!DNL Target] 发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了有关[!DNL Adobe Target] Python SDK版本1.0.0的信息。 |
|  | [个性化分析报表](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md) | 添加了以下常见问题解答：<ul><li>[!UICONTROL Automated Personalization](AP)和[!UICONTROL 自动定位]模型的数据会保留多长时间？</li></ul> |
| 6 月 8 日 | [在使用at.js实施Analytics for Target(A4T)之前](/help/c-integrating-target-with-mac/a4t/before-implement.md) | 添加了注释，指示at.js 1.8.0或更高版本不再适用于2.5.0以前的访客API版本，无法传递[!DNL Adobe Audience Manager](AAM)参数。 |
|  | [环境](/help/administrating-target/environments.md) | 添加了注释，指示如果指定[!UICONTROL 活动和不活动活动]，则此环境中的主机也会显示不活动的活动。 |
|  | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md) | 添加了以下已知问题：<ul><li>[!DNL Adobe Experience Platform] 区段名称不会显示在重要属 [!UICONTROL 性报] 表中。</li></ul> |
| 6 月 7 日 | [发行说明](/help/r-release-notes/release-notes.md)：21.5.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe [!DNL Target] Standard/Premium 21.4.1（2021 年 4 月 19 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 6 月 3 日 | [Target 公告和活动](/help/r-release-notes/target-announcements.md) | 添加了有关将于2021年6月9日星期三上午8时举行的Adobe Target社区问答咖啡会的信息。（太平洋夏季时间，GMT-7）。 |
| 6 月 1 日 | [CNAME和 [!DNL Target]](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 添加了以下常见问题解答：<ul><li>如何结合使用包含CNAME的选择退出链接</li></ul> |
|  | [隐私](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | 更新了“选择退出链接”部分，以说明如何将选择退出链接与CNAME结合使用。 |
|  | [[!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | 添加了有关[!DNL Adobe Experience Platform Web SDK]的信息。 |
|  | [实施 [!DNL Target] Analytics](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform) | 添加了新章节：<ul><li>[!DNL Adobe Experience Platform Web SDK]实施的实施步骤</li></ul> |
|  | [重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) | 添加了有关将重定向选件与A4T和Platform Web SDK结合使用的信息。 |
|  | [响应令牌](/help/administrating-target/response-tokens.md) | 添加了有关将响应令牌与[!DNL Adobe Experience Platform Web SDK]结合使用的信息。<br>**注意**:此功能将在Platform Web SDK的未来版本中发布（日期待定）。 |
|  | [Target 发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了有关Adobe Experience Platform Web SDK 2.5.0（2021年6月1日）版本的信息。 |
| 5 月 27 日 | [限制](/help/r-troubleshooting-target/target-limits.md) | 添加了关于[!DNL Target] API调用的章节。 限制为每分钟50次呼叫。 |
| 5 月 20 日 | [设备上决策](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | 在 Adobe Tech Blog 上添加了指向以下博客帖子的链接：<ul><li>Adobe技术博客 — 第2部分：运行[!DNL Adobe Target] NodeJS SDK，在边缘平台上进行实验和个性化(AWS Lambda@Edge)</li></ul> |
|  | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md) | 添加了以下已知问题： &quot;存档[!UICONTROL 自动定位]活动可能会导致同步问题。&quot; |
| 17 月 5 日 | [Target 发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了有关 at.js 版本 2.5.0 的信息。 |
|  | [活动 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 更新了主题，以指示预览链接可用于使用at.js 2.5.0（及更高版本）的[!UICONTROL Automated Personalization](AP)活动。 |
|  | [支持的浏览器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | 指示at.js 2.5.0版本移除了对Microsoft Internet Explorer 10、Internet Explorer 11和所有旧版本的支持。 at.js 2.5.0及更高版本仍支持Microsoft Edge。 |
|  | [对与增强型体验编辑器有关的问 [!UICONTROL 题进行故障诊断]](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) | 更新了要的IP地址列允许列表表。 |
| 12 月 5 日 | [[!DNL Target] 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了以下预发行说明：<ul><li>Adobe Experience Platform Web SDK(2021年5月17日</li><li>Target Standard Premium 21.5.2</li></ul> |
| 10 月 5 日 | [[!DNL Recommendations] 常见问题解答](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | 添加了以下常见问题解答：&quot;我能否使用在[!DNL Recommendations Premium]的[!DNL Adobe Recommendations Classic]中创建的算法？&quot; |
|  | [实施 [!DNL Target] using [!DNL Dynamic Tag Manager] (DTM)](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md) | 指示不再支持[!DNL Adobe Dynamic Tag Manager]。 [!DNL Adobe]建议使用[[!DNL Adobe Experience Platform Launch]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)进行实施。 |
| 5 月 6 日 | [“推荐”常见问题解答](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | 添加了以下常见问题解答：<ul><li>对我的[!UICONTROL 推荐]活动、优惠、促销或标准设置做出的更改需要多久才能反映在我的网站上？</li><li>用户的行为（例如，单击产品 A 并购买产品 B）需要多久才能反映在&#x200B;*该*&#x200B;用户收到的推荐中？</li><li>用户的行为（例如，单击产品 A 并购买产品 B）需要多久才能反映在&#x200B;*其他*&#x200B;用户收到的推荐中？</li></ul> |
|  | [设备上决策](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | 在 Adobe Tech Blog 上添加了指向以下博客帖子的链接：<ul><li>第 1 部分：在 Edge 平台上运行 Adobe Target NodeJS SDK 以提供试验性和个性化（Akamai Edge 工作者）</li></ul> |
| 5 月 5 日 | [Target 公告和活动](/help/r-release-notes/target-announcements.md) | 添加了关于将在 2021 年 5 月 12 日星期三上午 8 点（PDT，GMT-7）举办的 Adobe Target 社区问答喝咖啡休息时间的信息。 |
| 4 月 27 日 | [Cookie 设置](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-cookies.md) | 更新了一个主题以指明 Cookie 时长（`deviceIdLifetime` 设置）可在 at.js version 2.3.1 或更高版本中覆盖。 |
|  | [Adobe Target 指南](/help/target-home.md) | 添加了关于 Adobe Summit 的信息。 |
| 4 月 26 日 | [对 at.js 的设备上决策疑难解答](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/troubleshooting-on-device-decisioning.md) | 新主题。 |
| 4 月 19 日 | [设备上决策](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) | 添加了以下新文章：<ul><li>[设备上决策](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)</li><li>对 at.js 的[设备上决策支持的功能](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)</li><li>[设备上决策规则构件](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#on-device-decisioning) | 添加了关于 `decisioningMethod` 的信息。 |
|  | [adobe.target.getOffers()- at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | 添加了以下内容：<ul><li>关于 `decisioningMethod` 键的信息。</li><li>关于“用以制定设备上决策的 getCallOffers()”的示例。</li></ul> |
|  | [at.js 自定义事件](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | 添加了以下信息：<ul><li>设备上决策构件已成功</li><li>设备上决策构件失败</li></ul> |
|  | [活动](/help/c-activities/activities.md) | 添加了关于设备上决策的信息。 |
|  | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 添加了有关 at.js 2.5.0 的信息。 |
|  | [不通过标签管理器实施 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md) | 添加了关于设备上决策的信息。 |
|  | [活动 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 为 [at.js 2.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) 添加了对 [!UICONTROL Automated Personalization] 活动的预览链接的支持。 |
|  | [使用动态和静态包含规则](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators) | 添加了关于以下新运算符的信息：<ul><li>包含在列表中</li><li> 不包含在列表中</li><li>列表中包含某个项目</li><li>列表中不包含某个项目</li><li>列表中包含所有项目</li><li>列表中不包含所有项目</li></ul> |
|  | [Adobe Target Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html??lang=zh-Hans)<br>（*Experience Cloud Services 和管理*&#x200B;指南） | 添加了关于“会话 ID”的其他信息。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：21.4.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe [!DNL Target] Standard/Premium 21.2.1（2021 年 3 月 9 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 4 月 9 日 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 为 at.js 版本 2.5.0 添加了预发行信息（2021 年 4 月 19 日） |
| 4 月 9 日 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 为 Target Standard/Premium 21.4.1 版添加了预发行信息（2021 年 4 月 19 日） |
|  | [将“推荐”与电子邮件集成](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | 添加了描述选项 1 和 2 的容量准则的注释。 |
| 3 月 29 日 | [“推荐”常见问题解答](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md#persist-across-devices) | 添加了新的常见问题解答：<ul><li>根据最近查看过的项目提供的推荐是否会保留在单个访客的多个设备中？</li></ul> |
| 3 月 23 日 | [发行说明](/help/r-release-notes/release-notes.md) | 添加了 at.js 版本 2.4.1 的发行说明。 |
|  | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 添加了 at.js 版本 2.4.1 的发行说明。 |
|  | [“推荐”常见问题解答](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | 更新了以下常见问题解答：<ul><li>对目录中项目的更新耗时多久才能反映在网站上？</li></ul> |
| 3 月 22 日 | [推荐信息源处理服务器使用的 IP 地址](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | 更新了 IP 地址列表。 |
|  | [限制](/help/r-troubleshooting-target/target-limits.md) | 更新了“实体”下的“实体数量”部分。 |
|  | [地域](/help/c-target/c-audiences/c-target-rules/geo.md) | 添加了有关 at.js 2 的信息。*x*“我如何模拟其他位置的用户身份测试活动？”下面 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：21.2.1 | 添加了以下部分： <ul><li>推荐信息源处理服务器的 IP 地址更改（2021 年 3 月 16 日）</li></ul> |
| 3 月 19 日 | [查看报表 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#deactivated) | 添加了以下常见问题解答：<ul><li>为什么我的活动被停用后，我依旧会看到更多展示？</li></ul> |
| 3 月 12 日 | [自动分配和自动定位活动支持 A4T](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md#tutorial) | 添加了以下新教程：<ul><li>如何在 Analysis Workspace 中为自动定位活动设置 A4T 报表</li></ul> |
| 3 月 9 日 | [限制](/help/r-troubleshooting-target/target-limits.md#offer-size) | <ul><li>更新了允许的选件大小限制。</li><li>更正了 categoryId 参数的字符限制。</li></ul> |
|  | [将 Target 边缘节点列入允许列表](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | 更新了 [!DNL Target] 边缘 IP 地址。 |
|  | [实体属性](/help/c-recommendations/c-products/entity-attributes.md) | 添加了文本以指示 entity.value 必须为小数格式（例如，15.99 而非 15,99）。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：21.2.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe [!DNL Target] Standard/Premium 21.1.1（2021 年 1 月 19 日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 2 月 22 日 | [查看报表 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | 更新了以下常见问题解答：<ul><li>可在 Analysis Workspace 中的何处应用区段？</li></ul> |
| 2 月 16 日 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 更新了预发行说明中选件限制大小的文本。 |
| 2 月 11 日 | [Target 的工作方式](/help/c-intro/how-target-works.md) | 更新了“机器人”部分。 |
| 2 月 10 日 | [Target 公告和活动](/help/r-release-notes/target-announcements.md) | 添加了关于 2021 年 2 月 24 日星期三 Adobe Target 社区问答喝咖啡休息时间的信息。 |
| 2 月 8 日 | [Target 移动设备预览](/help/c-target-mobile-app/target-mobile-preview.md) | 添加了应添加到 Adobe Mobile SDK 第 4 版的 AndroidManifest.xml 文件的代码段。 |
|  | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md) | 阐明了以下已知问题：<ul><li>在 Target 用户界面中看不到通过 API 创建的收藏集、排除项、标准和设计，而只能通过 API 编辑它们。类似地，如果您在 Target 界面中创建任何此类项目，然后通过 API 编辑它们，则这些更改将不反映在 Target UI 中。通过 API 编辑的项目应继续通过 API 编辑，以免丢失任何修改。</li></ul> |
| 2 月 1 日 | [自动个性化摘要报表](/help/c-reports/reports-ap.md) | 添加了新部分：“常见问题”。 |
| 1 月 27 日 | [创建重定向选件](/help/c-experiences/c-manage-content/offer-redirect.md) | 更新了主题。 |
|  | [创建远程选件](/help/c-experiences/c-manage-content/about-remote-offers.md) | 更新了主题。 |
| 1 月 26 日 | [转化率](/help/c-reports/conversion-rate.md) | 阐明了 Target 如何在学生的 t 检验中使用“平方和”。 |
| 1 月 22 日 | [转化率](/help/c-reports/conversion-rate.md#t-test) | 添加了以下部分：“为什么 Target 推荐使用学生的 t 检验？” |
| 1 月 21 日 | [Analytics 与 Target 集成 (A4T) 故障诊断](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) | 添加了新的部分：“A4T 活动报表包括具有大量‘未指定’事件的一行”。 |
|  | [查看报表 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | 更新了以下部分：“为什么在 Analytics 报表中会看到‘未指定’？它意味着什么？” |
| 1 月 20 日 | [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | 新主题。 |
| 1 月 19 日 | [Target 发行说明（当前版本）](/help/r-release-notes/release-notes.md) | 添加了有关 Target 21.1.1 版本（2021 年 1 月 19 日）的信息。 |
|  | [限制](/help/r-troubleshooting-target/target-limits.md) | 更新了 `productPurchasedID` 参数的文本。 |
|  | [已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md) | 添加了一个已知问题，在复制目前有促销的[!UICONTROL 推荐]活动时发生该问题。复制活动中的任何更改也会影响原始活动，反之亦然。包括一个临时解决方法。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：21.1.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

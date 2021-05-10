---
keywords: target 文档变更日志;文档更新;新主题;编辑;更新;更新
description: 在Adobe [!DNL Target] 产品文档中添加重要内容和更改，以保持最新。
title: 可在何处查看 Target 的文档更新？
feature: 发行说明
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
translation-type: tm+mt
source-git-commit: 5d3d284f75ee00b7fd92b0083c6009334a5db2e5
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 61%

---

# Adobe Target 产品文档中的文档更改

此页面列出对 [!DNL Adobe Target] 产品文档作出的重大变更。

## Adobe [!DNL Target] Standard/Premium 21.4.1（2021年4月19日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 5 月 10 日 | “推荐”常见问题解答 | 添加了以下常见问题解答：&quot;我是否可以使用在[!DNL Recommendations Premium]中的[!DNL Adobe Recommendations Classic]中创建的算法？&quot; |
| 5 月 6 日 | [“推荐”常见问题解答](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | 添加了以下常见问题解答：<ul><li>对我的[!UICONTROL Recommendations]活动、优惠、促销或标准设置的配置进行更改需要多长时间才能反映在我的网站上？</li><li>用户的行为（例如，单击产品A和购买产品B）需要多长时间才能反映在用户收到的推荐&#x200B;*中？*</li><li>用户的行为（例如，单击产品A和购买产品B）需要多长时间才能反映在用户收到的推荐&#x200B;*其他*&#x200B;中？</li></ul> |
|  | [设备上决策](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | 在Adobe技术博客上添加了以下博客文章的链接：<ul><li>第1部分：运行Adobe Target NodeJS SDK，在边缘平台上进行试验和个性化(Akamai Edge Worker)</li></ul> |
| 5 月 5 日 | [Target 公告和活动](/help/r-release-notes/target-announcements.md) | 增加了有关将于2021年5月12日星期三上午8时举行的Adobe Target社区问答咖啡会的信息。(PDT， GMT-7)。 |
| 4 月 27 日 | [Cookie 设置](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-cookies.md) | 已更新主题，指示at.js版本2.3.1或更高版本中的Cookie持续时间（`deviceIdLifetime`设置）可覆盖。 |
|  | [Adobe Target指南](/help/target-home.md) | 添加了有关Adobe峰会的信息。 |
| 4 月 26 日 | [对at.js的设备上决策进行疑难解答](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/troubleshooting-on-device-decisioning.md) | 新主题。 |
| 4 月 19 日 | [设备上决策](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) | 新增了以下文章：<ul><li>[设备上决策](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)</li><li>[支持的设备决策功能](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)</li><li>[设备上决策规则伪像](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#on-device-decisioning) | 添加了有关`decisioningMethod`的信息。 |
|  | [adobe.target.getOffers() - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | 添加了以下内容：<ul><li>有关`decisioningMethod`键的信息。</li><li>“getCallOffers()进行设备决策的示例。”</li></ul> |
|  | [at.js 自定义事件](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | 添加了以下信息：<ul><li>设备上决策伪像成功</li><li>设备上决策伪像失败</li></ul> |
|  | [活动](/help/c-activities/activities.md) | 添加了有关设备决策的信息。 |
|  | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 添加了有关 at.js 2.5.0 的信息。 |
|  | [不通过标签管理器实施 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md) | 添加了有关设备决策的信息。 |
|  | [活动 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 在[at.js 2.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)中添加了对[!UICONTROL Automated Personalization]活动的预览链接的支持。 |
|  | [使用动态和静态包含规则](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators) | 添加了有关以下新运算符的信息：<ul><li>包含在列表中</li><li> 未包含在列表中</li><li>列表包含</li><li>列表不包含</li><li>列表包含</li><li>列表不包含</li></ul> |
|  | [Adobe Target cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html)<br>(*Experience Cloud服务和* 管理指南) | 添加了有关“会话ID”的其他信息。 |
|  | [发行说明](/help/r-release-notes/release-notes.md):21.4.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe [!DNL Target] Standard/Premium 21.2.1（2021年3月9日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 4 月 9 日 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了at.js版本2.5.0的预发行信息（2021年4月19日） |
| 4 月 9 日 | [Target 发行说明（预发行版本）](/help/r-release-notes/target-release-notes.md) | 添加了Target Standard/Premium 21.4.1版本的预发行信息（2021年4月19日） |
|  | [将“推荐”与电子邮件集成](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | 增加了说明，说明选项1和2的容量准则。 |
| 3 月 29 日 | [“推荐”常见问题解答](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md#persist-across-devices) | 新增了常见问题解答：<ul><li>基于最近查看的项目的推荐是否会跨多个设备保留以用于单个访客?</li></ul> |
| 3 月 23 日 | [发行说明](/help/r-release-notes/release-notes.md) | 添加了 at.js 版本 2.4.1 的发行说明。 |
|  | [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 添加了 at.js 版本 2.4.1 的发行说明。 |
|  | [“推荐”常见问题解答](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | 更新了以下常见问题：<ul><li>对目录中项目的更新耗时多久才能反映在网站上？</li></ul> |
| 3 月 22 日 | [“推荐”信息源处理服务器使用的 IP 地址](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | 更新了IP地址的列表。 |
|  | [限制](/help/r-troubleshooting-target/target-limits.md) | 更新了“实体”下的“实体数”部分。 |
|  | [地域](/help/c-target/c-audiences/c-target-rules/geo.md) | 添加了有关 at.js 2 的信息。*请* 阅读“如何测试活动，好像我是来自其他位置的用户一样？” |
|  | [发行说明](/help/r-release-notes/release-notes.md)：21.2.1 | 添加了以下部分： <ul><li>Recommendations源处理服务器的IP地址更改（2021年3月16日）</li></ul> |
| 3 月 19 日 | [查看报表 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#deactivated) | 添加了以下常见问题解答：<ul><li>为什么在取消激活活动后继续查看更多印象？</li></ul> |
| 3 月 12 日 | [自动分配和自动定位活动支持 A4T](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md#tutorial) | 添加了以下新教程：<ul><li>如何在 Analysis Workspace 中为自动定位活动设置 A4T 报表</li></ul> |
| 3 月 9 日 | [限制](/help/r-troubleshooting-target/target-limits.md#offer-size) | <ul><li>更新了允许的选件大小限制。</li><li>更正了 categoryId 参数的字符限制。</li></ul> |
|  | [将 Target 边缘节点列入允许列表](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | 更新了 [!DNL Target] 边缘 IP 地址。 |
|  | [实体属性](/help/c-recommendations/c-products/entity-attributes.md) | 添加了文本以指示 entity.value 必须为小数格式（例如，15.99 而非 15,99）。 |
|  | [发行说明](/help/r-release-notes/release-notes.md)：21.2.1 | 此版本包括一些增强功能和修复。您可以阅读这些内容并从发行说明链接到相应的文档。此版本还更新了帮助中的多个文档。 |

## Adobe [!DNL Target] Standard/Premium 21.1.1（2021年1月19日）

| 日期 | 主题 | 更改 |
| --- | --- | --- |
| 2 月 22 日 | [查看报表 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | 更新了以下常见问题：<ul><li>可在 Analysis Workspace 中的何处应用区段？</li></ul> |
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

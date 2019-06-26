---
description: 这些发行说明提供了每个 Target Standard 和 Target Premium 版本的功能、增强、修复问题和已知问题等信息。
keywords: 发行说明;预发行
seo-description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
seo-title: Target 发行说明（当前版本）
solution: Target
title: Target 发行说明（当前版本）
topic: 推荐
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: de5d1a5852c7c6b59521e8d89493d48959a5b377

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。

## 公告

请注意以下重要公告：

* 2019 年 2 月 20 日，欧洲、中东和非洲、日本以及亚太地区升级了 Adobe Target 基础架构，此后将不再从使用不支持 TLS 1.1 或更高版本的旧设备或 Web 浏览器的最终用户那里收集数据。北美地区计划于 **2019 年 4 月 1 日** 进行相同的升级。迁移到 TLS 1.2 可提高安全性。请务必浏览相关具体细节，并与您的 IT 团队一起制定更改计划以实现平稳过渡。有关更多信息，请参阅 [TLS（传输层安全性）加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
* [!DNL Target] 和 [!DNL Adobe Marketing Cloud] 将从 2019 年 3 月开始停止对 Microsoft Internet Explorer 11 的支持。此更改只会影响 [!DNL Target] 创作，而不会影响体验交付。请切换到 Microsoft Edge 或其他浏览器。有关更多信息，请参阅[支持的浏览器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。

## Target Standard/Premium 19.6.1（2019 年 6 月 26 日）

此版本包括以下新增功能和增强功能：

| 功能 / 增强功能 | 描述 |
| --- | --- |
| 可视化体验编辑器 (VEC) | **新的CMS菜单选项**：单击CMS中的页面元素时，菜单会显示可用于该元素类型的选项。<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>See *Styles* in [Visual Experience Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles).<br>**单击跟踪改进**：我们改进了在CMS和单页应用程序(SPA) CMS中配置点击跟踪的过程。<ul><li>选择要在单击跟踪中使用的元素时，所有可用元素的名称都会显示在右侧的“修改”面板中，从而可以快速、轻松地选择所需元素。</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. 您可以将鼠标悬停在此数字上，查看所有选定元素的名称。(TGT-33878)</li></ul>See [Click tracking](/help/c-activities/r-success-metrics/click-tracking.md). |
| 单页应用程序 Visual Experience Composer (SPA VEC) | **引导工作流程**：新的向导式工作流程可帮助您了解页面交付规则设置如何配置为为单页应用程序成功执行和运行活动。(TGT-33718)<br> See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings).<br>**克隆修改**：您现在可以使用SPA CMS定义修改，然后克隆该修改以在单页应用程序中的其他视图中使用。(TGT-33882)<br>See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |
| 移动设备可视化体验编辑器 | **多个应用程序版本**：您现在可以为移动应用程序的多个版本创作活动。这在版本类似时节省了时间和精力，您无需显著更改应用程序的UI。(TGT-34231)<br>See &quot;Manage multiple app versions&quot; in [Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#using-the-mobile-vec). |
| ![Premium徽章](/help/assets/premium.png) 自动个性化(AP)和自动定位 | **特定体验作为控制**：您可以选择要在创建AP或自动Target活动时用作控件的体验。此功能允许您根据活动中配置的流量分配百分比，将整个控制流量路由到特定体验。然后，您可以根据控制流量来评估个性化流量的绩效报告。当前控制选项(随机提供的体验)将继续可用。(TGT-32801, TGT-26572, &amp; TGT-26571)<br>See [Select the control for your Automated Personalization or Auto-Target Activity](/help/c-activities/t-automated-personalization/experience-as-control.md). Note that there is a [current known issue](/help/r-release-notes/known-issues-resolved-issues.md) with this feature.<br>**个性化洞察报告**：当访客在特定位置看到特定内容时，针对属性的营销人员友好命名提供更有意义的信息。(TGT-33421 &amp; TGT-34957)<br>See [Data collection for the Target personalization algorithms](/help/c-activities/t-automated-personalization/ap-data.md). |
| ![高级徽章](/help/assets/premium.png) 推荐 | 在创建“最近查看的项目”逻辑时，您可以使用“推荐以前购买的项目”切换。(TGT-34030)<br>有关详细信息，请参阅 [“创建标准”](/help/c-recommendations/c-algorithms/create-new-algorithm.md#previously-purchased) 中最近查看的项目。 |
| Google Chrome SameSite Cookie策略 | Google最近宣布从Chrome76(针对2019年月30日的版本)开始，开发人员必须明确指定哪些cookie可以跨网站工作以及哪些cookie可以跟踪用户。<br>随着行业努力为消费者创建更加安全的Web，Target绝对致力于在会议期间提供个性化体验并超越访客的隐私期望。<br>请参阅 [Google Chrome SameSite Cookie策略](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md)。 |

## at. js version2.1.0(2019年月日)

我们很高兴在. js2.1.0上宣布下列激动人心的功能：

| 功能/增强 | 描述 |
| --- | --- |
| Adobe选择加入支持 | 通过 Adobe 选择加入，可轻松将 Adobe 解决方案与同意管理平台集成。<br>有关Adobe选择加入的详细信息，请参阅 [隐私和一般数据保护规定(GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)。 |
| 符合行业标准的CSP | at. js不再使用eval()执行JavaScript。 |
| 客户端分析日志记录 | 无论客户端还是服务器端，都可以完全控制如何将分析数据发送到Adobe Analytics。<br>有关详细信息，请参阅 [在实现之前](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) 登录 *客户端分析*。 |
| 发送通知 | Allows developers to send notifications when an experience is rendered by their code instead of using `applyOffer()` or `applyOffers()`.<br>有关详细信息，请参阅 [adobe. target. sendNoSearch(选项)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)。 |
| 文件大小更小 | . js的大小减小了~24%。文件大小较小，可提高页面加载性能并缩短页面上下载. js的时间。 |
| at. js文档更新 | For a full list of all articles updated due to the at.js 2.1.0 release, see the June 3, 2019 entries in [Documentation changes](/help/r-release-notes/doc-change.md). |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](../r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud发行说明](https://marketing.adobe.com/resources/help/en_US/whatsnew/)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| “Adobe 产品更新早知道”列表 | 要收到有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的高级通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将发布的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [ Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
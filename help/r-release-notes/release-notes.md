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
source-git-commit: 542366ce4c14eab4ee15e3614888f4b335b9a0df

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。

## 公告

请注意以下重要公告：

* 在2019年月20日，在EMEA、日本和APAC区域中升级了Adobe Target基础结构，不再向不支持TLS1.1或更高版本的旧设备或Web浏览器收集最终用户的数据。此相同升级计划于2019 **年月日针对北美地区**进行。迁移到 TLS 1.2 可提高安全性。务必仔细研究具体内容，并与IT团队一起进行更改，实现平稳过渡。有关详细信息，请参阅 [TLS(传输层安全)加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
* [!DNL Target] 和 [!DNL Adobe Marketing Cloud] 将从 2019 年 3 月开始停止对 Microsoft Internet Explorer 11 的支持。此更改只会影响 [!DNL Target] 创作，而不会影响体验交付。请切换到 Microsoft Edge 或其他浏览器。有关更多信息，请参阅[支持的浏览器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。

## [!DNL Target] Standard/Premium19.5.1(2019年月21日) {#tgt-19-5-1}

这个版本包括以下功能、变化和增强功能：

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

### 功能更新

| 功能/增强 | 描述 |
| --- | --- |
| 单页应用程序可视化体验编辑器(SPA CMS) | SPA VEC 包含以下增强功能，可让您更快捷、更高效地完成工作：<ul><li>单击SPA中的某个操作会突出显示要应用此操作的站点上的元素。在View下创建的每个CMS操作都有四个对应图标：信息、编辑、移动和删除。此版本中新增的“移动”功能允许您将操作移至页面加载事件或修改面板中已经存在的任何其他视图。(TGT-33746)</li><li>在 VEC 中加载页面之前，或者即使页面无法完全加载（例如，自定义代码不再可操作），您可以执行许多操。网站加载之前无法编辑的操作会在 Target UI 中禁用。（TGT-33851 和 TGT-34149）</li></ul>有关更多信息，请参阅[单页应用程序 (SPA) 可视化体验编辑器](/help/c-experiences/spa-visual-experience-composer.md)。 |

### 增强功能、修复和更改

* 当您在 VEC 中取消载入页面后，系统会正确地显示出工具栏图标。如果某些特定的操作只有在完全载入页面后才能执行，那么相关的工具栏图标将会禁用。(TGT-33811)

## Mobile App Visual Experience Composer(2019年月14日){mobile-vec}

| 功能/增强 | 描述 |
| --- | --- |
| 移动应用视觉体验书写器(CMS) | 利用移动App CMS，您无需连续的开发依赖关系和应用程序发布周期，即可在本机移动应用程序上创建活动和个性化内容。<br>有关详细信息，请参阅：<ul><li>[移动设备应用程序可视化体验编辑器](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - 设置移动设备应用程序](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - 设置移动设备应用程序](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[在移动设备 VEC 中设置点击跟踪](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[视频：移动应用视觉体验书写器](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](../r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关更多信息，请参阅 [Experience Cloud发行说明](https://marketing.adobe.com/resources/help/en_US/whatsnew/)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新列表 | 要获得有关Target和其他Adobe Experience Cloud解决方案的即将产品增强的预先通知，请注册Adobe优先产品更新：<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 即将发行的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [ Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
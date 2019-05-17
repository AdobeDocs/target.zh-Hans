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
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。

## 公告

请注意以下重要公告：

* 在2019年月20日，在EMEA、日本和APAC区域中升级了Adobe Target基础结构，不再向不支持TLS1.1或更高版本的旧设备或Web浏览器收集最终用户的数据。此相同升级计划于2019 **年月日针对北美地区**进行。迁移到 TLS 1.2 可提高安全性。务必仔细研究具体内容，并与IT团队一起进行更改，实现平稳过渡。有关详细信息，请参阅 [TLS(传输层安全)加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
* [!DNL Target] 和 [!DNL Adobe Marketing Cloud] 将从 2019 年 3 月开始停止对 Microsoft Internet Explorer 11 的支持。此更改只会影响 [!DNL Target] 创作，而不会影响体验交付。请切换到 Microsoft Edge 或其他浏览器。有关更多信息，请参阅[支持的浏览器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。

## Mobile App Visual Experience Composer(2019年月14日){mobile-vec}

| 功能/增强 | 描述 |
| --- | --- |
| 移动应用视觉体验书写器(CMS) | 利用移动App CMS，您无需连续的开发依赖关系和应用程序发布周期，即可在本机移动应用程序上创建活动和个性化内容。<br>有关详细信息，请参阅：<ul><li>[移动设备应用程序可视化体验编辑器](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - 设置移动设备应用程序](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - 设置移动设备应用程序](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[在移动设备 VEC 中设置点击跟踪](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li></ul> |

## [!DNL Target] Standard/Premium19.4.2(2019年月30日) {#release-19-4-2}

此版本包括以下功能、更改和增强功能：

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

### 功能更新

| 功能/增强 | 描述 |
| --- | --- |
| [!UICONTROL 可视化体验编辑器] | [!UICONTROL Visual Experience Composer] (CMS)包含以下增强功能，使您的工作更快速、高效：<ul><li>现在，在设置单击跟踪时，DOM路径功能可用。<br>有关详细信息，请参阅 [单击跟踪](/help/c-activities/r-success-metrics/click-tracking.md#considerations)。</li><li>使用样式面板可查看或编辑选定元素的现有样式的值。您还可以添加其他样式。<br>要访问“样式”面板，请在CMS中单击页面元素，然后单击 [!UICONTROL “编辑] ”&gt; [!UICONTROL “样式]”。<br>样式面板显示在CMS的右侧。该面板包含允许您编辑或添加到选定元素的样式列表。实时CSS编辑器可让您查看更改并添加样式(如果您习惯使用层叠样式表(CSS))或从开发人员收到代码。<br>有关更多信息，请参阅 [视觉体验书写器选项](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles) 中 *的样式*。</li><li>富文本编辑器现在支持嵌套HTML元素。<br>HTML规范允许嵌套标签的新组合。富文本编辑器的早期版本不支持HTML规范所允许的新标记嵌套。因此，在CMS中选择的任何嵌套元素都无法正确处理，从而导致不需要的HTML更改。(TGT-33618)<br>有关详细信息，请参阅 [](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#edit-text-html)*“视觉体验书写器”选项中的编辑文本/HTML*。</li> |

### 增强功能、修复和更改

* 我们改进了您在使用 VEC 删除资产时的工作流程。删除的资产现在从 [!UICONTROL 选件库] 中删除，并且从中 [!DNL Scene7] 删除(如果适用)。已删除的资产将不会继续出现在搜索结果中。(TGT-31981)
* 现在，即使资产文件夹包含图像(非空文件夹)，您也可以删除资产文件夹。(TGT-33265)

   以前，您无法从Target图像选件库中删除非空文件夹([!UICONTROL “选件”] &gt; [!UICONTROL “图像选件”])。您会收到“文件夹不是空！”通知。通过此功能，我们将添加允许您执行文件夹删除的功能，以删除包含任意数量的资产和子文件夹的整个文件夹。此功能在目标UI中也可用于Adobe Experience Cloud Assets UI。

   * 可删除图像选件库中的非空文件夹。如果在任何活动中都未引用该文件夹中的所有图像，则会删除整个文件夹及其内容。如果在任何活动中引用该文件夹中的某些图像，则会删除所有未引用的图像，但保留包含这些图像的引用图像和文件夹。
   * 图像资产选取器中的图像提供渲染速度更快、效率更高。
   有关详细信息，请参阅 [使用库中的内容](/help/c-experiences/c-manage-content/assets-working.md)。(TGT-32897)

* 我们改进了“资产”选取器中图像选件的呈现方式。现在可以更加快捷、高效地显示和选择图像选件。(TGT-32897)
* 我们改进了当您在 VEC 中取消载入页面时，对 URL 重定向的处理。(TGT-33815)
* 从Collections选取器中选择 [!UICONTROL Recommendations] 集合后，您现在必须单击 [!UICONTROL “保存] ”按钮。此工作流与内其他工作流一致 [!DNL Target]。(TGT-33205)
* 修复了一个问题，该问题导致一组Insights报告可返回0%的转化率，而不是实际的转化率。(TNT-32125)

## [!DNL Target] Standard/Premium19.4.1(2019年月15日) {#release-19-4-1}

这个版本属于维护版本，它包括以下变更：

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

* 更新 [!DNL Adobe Experience Cloud] 了UI以反映品牌和产品更改。（TGT-33546、TGT-33272 和 TGT-33331）

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
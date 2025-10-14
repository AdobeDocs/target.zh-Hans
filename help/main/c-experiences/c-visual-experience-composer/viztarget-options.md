---
keywords: 可视化体验编辑器选项；体验编辑器选项；体验选项；编辑文本；编辑html；编辑文本/html；编辑背景颜色；背景颜色；插入元素；编辑链接；链接；可视化体验编辑器链接；编辑css类；css类；交换选件；选件交换；交换图像；图像交换；移除项；项移除；隐藏项；项隐藏；重新排列；移动元素；元素移动；调整元素大小；元素大小；扩展选择；导航到此链接；链接导航；链接；链接；撤消；重做；撤消/重做；自定义事件；Web组件；选件决策；选件决策
description: 浏览 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)中可用的选项。
title: 如何使用[!UICONTROL Visual Experience Composer] (VEC)选项？
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: c8cbf4998c304910a63e31acc3ec93a04ac652ae
workflow-type: tm+mt
source-wordcount: '2047'
ht-degree: 8%

---

# [!UICONTROL Visual Experience Composer]选项

[!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文介绍了已更新的UI及其选项。

>[!TIP]
>
>要了解更新的VEC与旧版VEC有何不同，请参阅[可视化体验编辑器更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)。

>[!IMPORTANT]
>
>更新的[!UICONTROL Visual Editing Composer]需要[!DNL Adobe Experience Cloud]上可用的[[!UICONTROL Visual Editing Helper] &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)扩展[!DNL Chrome Web Store]。

创建或编辑现有活动时将显示VEC。

![可视化体验编辑器 (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## VEC UI概述

以下部分说明更新后的VEC中为[!UICONTROL A/B Test]活动提供的选项。 选项因活动类型而异。

### [!UICONTROL Experiences]边栏

[!UICONTROL Experiences]边栏显示在VEC的左边栏中。

![体验边栏](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

您可以使用[!UICONTROL Experiences]边栏查看、创建、重命名或删除体验。

[!UICONTROL Experiences]边栏中有以下选项：

* **查看体验**：要查看体验，请单击所需的体验以在[!UICONTROL Design]画布中显示它。
* **添加体验**：单击&#x200B;**[!UICONTROL Add]**&#x200B;图标（![添加图标](/help/main/assets/icons/Add.svg)）以添加新体验。 根据需要配置新体验。
* **重命名体验**：单击&#x200B;**[!UICONTROL Rename]**&#x200B;图标（![重命名图标](/help/main/assets/icons/Rename.svg)）以显示[!UICONTROL Rename Experience]对话框。 指定新名称，然后单击&#x200B;**[!UICONTROL Save]**。
* **复制、删除或重新定向体验**：单击&#x200B;**[!UICONTROL More Actions]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg)），然后选择&#x200B;**[!UICONTROL Duplicate]**、**[!UICONTROL Delete]**&#x200B;或&#x200B;**[!UICONTROL Redirect to URL]**。

### 活动设置/配置 {#settings}

单击[!UICONTROL Configure]画布顶部显示的![图标（](/help/main/assets/icons/Setting.svg)配置图标[!UICONTROL Design]）以显示活动属性菜单。

![活动配置选项](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

以下选项可供选择：

* **[!UICONTROL Properties]**：将属性分配给活动或从活动中删除属性。 [!UICONTROL Properties]是([[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)功能。 有关更多信息，请参阅[企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。
* **[!UICONTROL Page Delivery]**：在您的网站上类似页面上包含相同体验。 使用页面模板为您的页面提供结构，或者如果页面包含类似的元素，则使用类似的结构化页面元素或跨整个域测试变体。 有关详细信息，请参阅[在相似页面上包含相同体验](/help/main/c-experiences/c-visual-experience-composer/temtest.md)。
* **[!UICONTROL Site Preferences]**：配置您的站点首选项以指定[!DNL Target]生成CSS选择器的方式。 有关详细信息，请参阅&#x200B;_配置_&#x200B;中的[CSS选择器[!UICONTROL Visual Experience Composer]](/help/main/administrating-target/visual-experience-composer-set-up.md)。
* **添加其他页面**：将其他页面添加到活动以创建多页面活动，该活动允许您使用特定于每个页面的设计跨多个页面创建故事。 有关详细信息，请参阅[多页面活动](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md)。
* **单个受众**：对该活动使用单个受众。
* **多个受众**：为活动分配多个受众。 单击“添加受众”图标（![添加图标](/help/main/assets/icons/Add.svg)），然后从列表中选择一个或多个受众。 您也可以[合并受众](/help/main/c-target/combining-multiple-audiences.md)或从[对话框](/help/main/c-target/c-audiences/create-audience.md)创建新的受众[!UICONTROL Add Audiences]。

### [!UICONTROL Design]/[!UICONTROL Browse]模式

使用设计画布顶部显示的[!UICONTROL Design]/[!UICONTROL Browse]切换功能，在设计模式和浏览模式之间切换。

![设计和浏览切换](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

使用[!UICONTROL Browse]模式浏览您的网站并选择您要更新的视图或页面。 切换回[!UICONTROL Design]模式以添加或编辑更改。

### [!UICONTROL Undo]/[!UICONTROL Redo]

您可以通过单击[!UICONTROL Undo]图标（![撤消图标](/help/main/assets/icons/Undo.svg) ）来撤消所做的更改。

VEC中的![撤消图标](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

要重做某项操作，请展开撤消/[!UICONTROL Redo]按钮组并选择[!UICONTROL Redo]。

### [!UICONTROL Components]边栏

您可以将多个组件添加到网页中，并根据需要使用新的[!UICONTROL Components]边栏编辑它们。

![组件边栏](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

>[!NOTE]
>
>如果您在此区域中看到[!UICONTROL Modifications]边栏而不是[!UICONTROL Components]边栏，请单击&#x200B;**[!UICONTROL Show Components]**&#x200B;图标（![显示组件图标](/help/main/assets/icons/Add.svg)）。 [!UICONTROL Show Components]图标（![显示组件图标](/help/main/assets/icons/Add.svg)）和[!UICONTROL Show Modifications]图标（![显示修改边栏](/help/main/assets/icons/History.svg)）用作显示相应选项的切换。
>
>要折叠[!UICONTROL Components]边栏并放大[!UICONTROL Design]画布，请在[!UICONTROL Components]边栏打开时单击（![显示组件图标](/help/main/assets/icons/Add.svg) ）图标。

要向体验添加新组件，请执行以下操作：

1. 单击要添加以高亮显示的所需组件。

   可用的组件将分组为逻辑容器：

   * [!UICONTROL Basic]
      * [!UICONTROL Divider]
      * [!UICONTROL HTML]
      * [!UICONTROL Image]
   * [!UICONTROL Text]
      * [!UICONTROL Heading]
      * [!UICONTROL Paragraph]
      * [!UICONTROL Link]
   * [!UICONTROL Dynamic]
      * [[!UICONTROL Recommendation]](/help/main/c-recommendations/recommendations-as-an-offer.md)
      * [[!UICONTROL Experience Fragment]](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)
      * [[!UICONTROL HTML Offer]](/help/main/c-experiences/c-manage-content/manage-content.md)

1. 将组件拖动到[!UICONTROL Design]画布中的现有页面元素上。
1. 选择以替换所选元素，或将组件插入到所选元素的前面。

### [!UICONTROL Modifications]边栏

要打开[!UICONTROL Modifications]边栏，请单击[!UICONTROL Show Modifications]边栏中的![图标（](/help/main/assets/icons/History.svg)显示修改边栏[!UICONTROL Components]）。

![修改边栏](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>[!UICONTROL Show Components]图标（![显示组件图标](/help/main/assets/icons/Add.svg)）和[!UICONTROL Show Modifications]图标（![显示修改边栏](/help/main/assets/icons/History.svg)）用作显示相应选项的切换。
>
>要在[!UICONTROL Modifications]边栏打开时折叠[!UICONTROL Design]边栏并放大[!UICONTROL Modifications]画布，请单击[!UICONTROL Show Modifications]图标（![显示修改边栏](/help/main/assets/icons/History.svg) ）图标。

[!UICONTROL Modifications]边栏显示对[!UICONTROL Visual Experience Composer] (VEC)中的页面所做的所有更改，并允许进行其他更改（如CSS选择器、Mbox和自定义代码）。

单击边栏标题中的&#x200B;**[!UICONTROL More Options]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg) ）以添加修改、删除所有修改或删除所有无效修改。 单击[!UICONTROL Select]以执行批量操作： [!UICONTROL Apply to All Pages]或[!UICONTROL Delete]。

单击每个修改旁边的&#x200B;**[!UICONTROL More Options]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg) ）以查看其信息、删除修改或将修改应用于更多视图。

### [!UICONTROL Design]画布

[!UICONTROL Design]画布允许您选择视区，包括适合屏幕、[!UICONTROL Desktop]、[!UICONTROL Tablet]、[!UICONTROL Mobile Landscape]和[!UICONTROL Mobile Portrait]。 默认情况下，画布将页面与[管理](/help/main/administrating-target/visual-experience-composer-set-up.md)部分中定义的视区一起适合屏幕。

![视区选项](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

您还可以通过单击相应的图标（![放大图标](/help/main/assets/icons/ZoomIn.svg)或![缩小图标](/help/main/assets/icons/ZoomOut.svg) ）进行放大或缩小。

单击[!UICONTROL Design]画布中的某个页面元素时，会显示一个菜单，其中提供了可用于该元素类型的选项。 此外，页面底部会显示一个 DOM 路径，可让您轻松浏览页面结构。

各种[!UICONTROL Visual Experience Composer] (VEC)操作将分组到相应的菜单选项中，以使您的工作更快捷、更有效：

![VEC 选项菜单](/help/main/c-experiences/c-visual-experience-composer/assets/vec-options.png)

>[!NOTE]
>
>可用选项取决于要创建或编辑的活动类型和元素。 有关在[!UICONTROL A/B Test]活动中编辑图像和选件的更多信息，请参阅下面的[使用画布[!UICONTROL Design]编辑元素](#design)。

### [!UICONTROL Properties]边栏

通过[!UICONTROL Properties]边栏可以更改页面上选定元素的属性，无论这些元素是HTML元素还是特定于[!DNL Target]的对象，例如推荐或选件。

![属性边栏](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

单击边栏顶部的图标可编辑HTML代码或者删除、复制或隐藏元素。 更改显示在[!UICONTROL Modifications]边栏中。

[!UICONTROL Properties]边栏可在右边栏中折叠，以允许您隐藏设计画布并放大设计画布。 单击边栏右侧的[!UICONTROL Show/Hide Properties]图标（![属性图标](/help/main/assets/icons/Propertie.svg)）以折叠或显示[!UICONTROL Properties]边栏。

## 使用[!UICONTROL Design]画布编辑元素 {#design}

以下部分将向您展示如何在[!UICONTROL Design]画布中编辑图像和文本。 “设计”画布以及“组件”、“修改”和“属性”边栏为您提供了强大的工具，让您能够轻松创建活动的体验。

### 图像选项

如果单击[!UICONTROL A/B Test]活动中的图像，则VEC将与下图类似：

已选择图像的![VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-image.png)

从左侧的[!UICONTROL Components]框架中选择组件以插入以下元素：

* 基本(分隔条、HTML、图像)。
* 文本（标题、段落、链接）。
* 动态([推荐](/help/main/c-recommendations/recommendations-as-an-offer.md)，[体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)， HTML选件)。

利用图像顶部的菜单，您可以执行以下操作：

* 插入链接（![插入链接图标](/help/main/assets/icons/Link.svg) ）。
* 更改图像（![选择图像图标](/help/main/assets/icons/Images.svg) ）。
* 添加个性化( ![添加Personalization图标](/help/main/assets/icons/PersonalizationField.svg) )。
* 删除图像（ ![删除图标](/help/main/assets/icons/Delete.svg) ）。

通过右侧的[!UICONTROL Properties]窗格，可以进一步配置图像的属性。

通过框架顶部的图标，您可以执行以下操作：

* 编辑HTML (![插入HTML图标](/help/main/assets/icons/Code.svg) )。 有关详细信息，请参阅下面的[编辑HTML](#html)。
* 复制图像（ ![复制图标](/help/main/assets/icons/Code.svg) ）。
* 删除图像（ ![删除图标](/help/main/assets/icons/Delete.svg) ）。
* 隐藏图像（ ![隐藏图标](/help/main/assets/icons/VisibilityOff.svg) ）。

利用右框架中的选项，您可以执行以下操作：

* 编辑CSS类。
* 配置图像的属性（源、标题、替换文本）。
* 编辑链接URL。
* 配置图像的大小（高度和宽度）。 单击[!UICONTROL Show Advanced Options]可配置图像的最小和最大大小、宽度、高度、溢出和对象大小。
* 配置图像在页面上的位置（绝对、固定、相对、静态或粘性）。
* 配置元素的间距，包括边距和边距。
* 配置元素的效果（不透明度）。 单击[!UICONTROL Show Advanced Options]可配置图像的棕褐色、灰度、对比度、亮度和模糊值。 也可以反转或旋转图像。
* 配置图像的内联样式。

### 文本选项

如果您单击[!UICONTROL A/B Test]活动中的文本，则VEC将与下图类似：

已选择文本的![VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-text.png)

从左侧的[!UICONTROL Components]框架中选择组件以插入以下元素：

* 基本(分隔条、HTML、图像)。
* 文本（标题、段落、链接）。
* 动态([推荐](/help/main/c-recommendations/recommendations-as-an-offer.md)，[体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)， HTML选件)。

单击[!UICONTROL Show Modifications]图标（![显示修改图标](/help/main/assets/icons/History.svg)）以显示对体验的修改。

通过文本元素顶部的菜单，您可以执行以下操作：

* 配置文本的属性（标题级别、段落、块引号或等宽）
* 选择文本的颜色（ ![文本颜色图标](/help/main/assets/icons/TextColor.svg) ）
* 配置文本的属性（粗体、斜体、下划线或删除线）（ ![选择文本属性图标](/help/main/assets/icons/Text.svg) ）。
* 配置文本的对齐方式（左、中、右、两端对齐）（ ![文本对齐方式图标](/help/main/assets/icons/TextAlignCenter.svg) ）。
* 插入链接（![插入链接图标](/help/main/assets/icons/Link.svg) ）。
* 将内容替换为HTML选件、[体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)或[推荐](/help/main/c-recommendations/recommendations-as-an-offer.md)。
* 编辑HTML (![插入HTML图标](/help/main/assets/icons/Code.svg) )。
* 添加个性化( ![添加Personalization图标](/help/main/assets/icons/PersonalizationField.svg) )。
* 删除图像（ ![删除图标](/help/main/assets/icons/Delete.svg) ）。

通过右侧的[!UICONTROL Properties]边栏，可进一步配置文本的属性。

通过框架顶部的图标，您可以执行以下操作：

* 编辑HTML (![插入HTML图标](/help/main/assets/icons/Code.svg) )。 有关详细信息，请参阅下面的[编辑HTML](#html)。
* 复制文本（ ![复制图标](/help/main/assets/icons/Code.svg) ）。
* 删除文本（ ![删除图标](/help/main/assets/icons/Delete.svg) ）。
* 隐藏文本（ ![隐藏图标](/help/main/assets/icons/VisibilityOff.svg) ）。

利用右框架中的选项，您可以执行以下操作：

* 编辑CSS类。
* 配置文本的背景颜色和图像。
* 配置文本的排版规则(标题样式、字体大小、字体粗细、行高、对齐方式、文本颜色、文本样式（粗体、斜体、下划线或点进）)。
* 配置列表，包括项目符号、编号或A、B、C。
* 选择边框颜色。
* 配置文本框的大小（高度和宽度）。 单击[!UICONTROL Show Advanced Options]可配置文本框的最小和最大大小、宽度、高度、溢出和对象大小。
* 配置文本框在页面上的位置（绝对、固定、相对、静态或粘性），并设置从上、右、下和左的像素数。
* 配置元素的间距，包括边距和边距。
* 配置元素的效果（不透明度）。 单击[!UICONTROL Show Advanced Options]可配置图像的棕褐色、灰度、对比度、亮度和模糊值。 也可以反转或旋转文本。
* 配置内联样式。

## 编辑HTML

除了 HTML 代码外，您还可以编辑和插入自定义 JavaScript。

编辑[!UICONTROL A/B]和[!UICONTROL Experience Targeting]活动的文本和HTML时，可以使用多种富文本格式选项。 您可以选择字体、选择字体样式、更改文本对齐方式以及使用其他标准文本格式设置选项。修改HTML时，您可以在HTML的代码视图和富编辑视图之间切换。

可以嵌套以下 HTML5 标记：

| 标记 | 允许的嵌套标记 |
| --- | --- |
| `<a>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>`、`<div>`、`<figure>`、`<figcaption>` |
| `<ins>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>` |
| `<del>` | `<ul>`、`<ol>`、`<menu>`、`<h1-h6>`、`<p>` |
| `<label>` | `<p>` |

## 使用DOM路径浏览元素 {#dom-path}

单击页面上的某个元素时，将显示 VEC 选项菜单。此外，单击某个元素时，相应的 DOM 路径将显示在页面底部。

![DOM 路径](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path-refresh.png)

如果未看到DOM路径，请单击[!UICONTROL Show DOM]图标（ ![显示DOM图标](/help/main/assets/icons/LayersBringToFront.svg) ）。

您可以使用 DOM 路径快速查看有关所选元素（类型、ID 和类）的信息，并向上或向下移动 DOM 路径以选择所需的元素。

<!--When you hover over the DOM path, a blue box highlights the corresponding element in the VEC. When you click the element, an orange box highlights the element and the VEC options menu displays, as explained above.-->

您可以使用 DOM 路径轻松导航到 VEC 中的任何父元素、同级元素或子元素。

设置[点击跟踪](/help/main/c-activities/r-success-metrics/click-tracking.md)时，还可使用 DOM 路径功能。

## 有关更新的UI的更多信息

* [[!DNL Target Standard/Premium] 25.2.1（2025年2月17日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!DNL Target]中[!UICONTROL Activities]、[!UICONTROL Recommendations]和[!UICONTROL Visual Experience Composer] (VEC)的关键UI更改的摘要。

* [[!DNL Target Standard/Premium] 25.1.1（2025年1月9日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!DNL Target]在[!UICONTROL Offers Library]中关键UI更改的摘要。

* [了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供简要概述以帮助您熟悉[!DNL Target]，并提供更深入的信息和分步说明的链接。

* [[!UICONTROL Visual Experience Composer]更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文介绍VEC旧版本与更新版本之间的差异。

* [[!UICONTROL Visual Experience Composer]选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文介绍更新的VEC UI及其选项。

* [[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)：此常见问题解答关于新[!DNL Target] UI和[!UICONTROL Visual Experience Composer] (VEC)的常见问题，包括导航更改、功能位置以及弃用临时UI版本切换。 无论您是营销人员、开发人员还是管理员，此常见问题解答都可以帮助您顺利过渡并充分利用更新后的UI。

<!--## [!UICONTROL Edit]

The following options are available:

### [!UICONTROL Text/HTML] {#edit-text-html}

Change the HTML code for the element, such as the text for a text area, button, or link.

In addition to HTML code, you can edit and inject custom JavaScript.

Several rich text formatting options are available when editing text and HTML for [!UICONTROL A/B] and [!UICONTROL Experience Targeting] activities. You can choose a font, select a font style, change text alignment, and other standard text formatting options. When modifying HTML, you can toggle between the code view and rich-editing view of the HTML.

The following HTML5 tags can be nested:

|Tag|Allowed Nested Tags|
| --- | --- |
|`<a>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>`|
|`<ins>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`|
|`<del>`|`<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>`|
|`<label>`|`<p>`|

### [!UICONTROL Background Color]

Use the color picker to select or configure a background color. You can select a color swatch, and adjust it using RGB values or color hex codes. The red x in the color picker makes the background transparent.

**Note:** This option is not available for an element where a background image is set. 

### [!UICONTROL Styles] {#styles}

Use the [!UICONTROL Styles] panel to view or edit the value of existing styles for the selected element. You can also add additional styling.

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

The [!UICONTROL Styles] panel displays on the right side of the VEC. The panel contains a list of styles that lets you edit or add to the selected element. A real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

![Styles panel](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

As you apply different styles, you can always revert your changes by clicking the [!UICONTROL Revert] icon that displays at the top-right corner of the [!UICONTROL Styles] panel after you change any section. Clicking the [!UICONTROL Revert] icon reverts all changes on the current section's panel.

Expand each section to edit or add styles, as explained below. To save your changes, click the [!UICONTROL Back] icon at the top of the panel to return to the panel's main display, then click **[!UICONTROL Save]**. 

Blue dots on the main panel and next to each option on the various section panels indicate that you have changed the corresponding styles. This visual indicator makes it easy for you to review your changes before clicking [!UICONTROL Save].

>[!NOTE]
>
>Quick actions for layout changes, background color, resizing, and move are also available as separate actions in the VEC menu. These options can be used as separate actions or you can use the Styles menu, as explained here.

* **[!UICONTROL Background]**

  Change the background color and image.

  * Color (specify the color code or use the color picker)
  * Image (select an image from the image picker)
  * Image source (specify an external URL)
  * Attachment
    * Click the top drop-down list to select scroll, fixed, or local
    * Click the bottom drop-down list to select repeat, repeat-x, repeat-y, no-repeat, space, or round
  * Clip
    * Click the top drop-down list to select border-box, padding-box, content-box, or text
    * Click the bottom drop-down list to select auto audio or audio

* **[!UICONTROL Typography]**

  Change the typography of an element. Typography edits are quick and easy. 

  Although the rich text editor (Edit Text/HTML) is available for fine tuning, quick actions to change the entire element is available via this option. If you want to apply typography changes to only a part of the text (not to the full text), use the [rich text editor](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md). 

  You can edit the following typography styles:

  * [!UICONTROL Font size]
  * [!UICONTROL Font weight]
  * [!UICONTROL Font style]
  * [!UICONTROL Color] (specify the color code or use the color picker)
  * [!UICONTROL Word spacing]
  * [!UICONTROL Line height]
  * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  Change the margin for the selected element. You can change the left, right, bottom, and top margins.

  Click the drop-down icon for each margin to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to set the margin or specify the number of pixels for each margin)

  Margin supports positive and negative values.

  Target also supports other size units, such as rem, pc, em. For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

  Change the padding for the selected element. You can change the left, right, bottom, and top padding.

  Drag the slider to set the padding or specify the number of pixels for padding.

  Padding supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Border]**

  Click the border icons at the top of the panel to change the selected element's border.

  You can edit the following styles for each border (top, right, bottom, and left):

  * [!UICONTROL Border style] (none, hidden, dotted, dashed, solid, or double)
  * [!UICONTROL Border color] (specify the color code or use the color picker)
  * [!UICONTROL Border width] (drag the slider to select a border width or specify the width in pixels)

  Border supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Position]**

  Move the selected element from its current position. You can change the element's top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

  Click the [!UICONTROL Static] drop-down list to choose from the following position options:

  * [!UICONTROL Static]
  * [!UICONTROL Relative]
  * [!UICONTROL Absolute]
  * [!UICONTROL Sticky]
  * [!UICONTROL Fixed]

  Click the drop-down icon for each position to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to position the element or specify the number of pixels you want to move the element)

  Position supports positive and negative values.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Size]**

  Change the selected element's width and height.

  Click the drop-down icon next to [!UICONTROL Width] and [!UICONTROL Height] to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to size the element or specify the number of pixels for each dimension)

* **[!UICONTROL Filter]**

  Drag the slider for each filter option or specify the desired percentage:

  * [!UICONTROL Sepia]
  * [!UICONTROL Contrast]
  * [!UICONTROL Brightness]
  * [!UICONTROL GrayScale]
  * [!UICONTROL Blur]
  * [!UICONTROL Opacity]
  * [!UICONTROL Invert]
  *[!UICONTROL  Hue-rotate]
  * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  The real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

  The CSS Editor displays any changes that you make in the Styles panel. As shown in the illustration below, the font size, top border, and image size have been changed:

  ![CSS editor with changes](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Notice the blue dots next to the [!UICONTROL Typography], [!UICONTROL Border], and [!UICONTROL Size] options in the preceding illustration. These dots indicate that you have changed these sections. If you open these section panels, blue dots display next to the specific options that you changed.

  You can type your own code if your desired style is not available by default in the [!UICONTROL Styles].

  The CSS Editor shows details for the current session only. If you save changes and then reopen the editor, details about your previous change do not display in the editor, even if you select the same element again.

  >[!IMPORTANT]
  >
  >You can apply a background image using the CSS Editor, but it might cause flicker. Test your changes before deployment.

### [!UICONTROL CSS Class]

Specify the predefined CSS class used for the element. If more than one element is selected, separate multiple CSS classes with a space.

Available for [!UICONTROL A/B], [!UICONTROL Automated Personalization], and [!UICONTROL Multivariate Test] activities.

### [!UICONTROL Link]

Change the URL in the link.

Use Edit Link to update the selector to point to the same image element. However, linking to a different image element is not supported. To link to a different image element, delete the original action from the code editor and use the [!UICONTROL Visual Experience Composer] to apply the action on the other image element.

## [!UICONTROL Insert Before]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=zh-Hans){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert Before] and choose whether you want to insert an image, HTML, or text. The inserted element appears before the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert Before] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=zh-Hans){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert After] and choose whether you want to insert an image, HTML, or text. The inserted element appears after the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert After] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=zh-Hans){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Select a different image from the Content Library. The images available for swapping include the images uploaded to the Experience Cloud assets folder or uploaded in the Content Library in Target.

During initial activity creation, the URL displayed is not the URL used for delivery. Upon activity synching, that URL is updated to a production Scene7 URL.

For example, the initial URL might look like the following example:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

After activity syncing, the delivery URL might look like the following example:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations supports Replace With in DIV, SECTION, and ARTICLE tags.

**Note:** Swapping images requires an Adobe Scene7 Publishing System Account.

### [!UICONTROL HTML Offer]

Select a different offer from the [!UICONTROL Content Library].

**Note:** HTML Offers are stored on [!DNL Target] servers.

An HTML offer can be up to 256 KB.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

The following options are available:

### [!UICONTROL Rearrange]

Drag the element to another location inside the same parent element or DIV. Other elements shift location to make space for the rearranged element.

**Note**: Click-tracking does not work on rearranged items.

Currently, certain VEC actions, such as [!UICONTROL Rearrange] and [!UICONTROL Move], assume that the sibling elements of the source and destination parent elements are completely loaded. If lazy loading occurs under the parent DOM elements (source or destination), these VEC actions can cause inconsistent behavior. We are working on a more reliable approach to make VEC actions work in lazy-loaded DOM elements. As a temporary workaround, you can use [!UICONTROL Custom Code] in these scenarios to render your experiences.

### [!UICONTROL Resize]

Resize an element on your page. When you select [!UICONTROL Resize], a handle appears in the bottom-right corner of the element that lets you drag that corner to resize. Hold the Shift key to retain the same aspect ratio.

**Note:** Inline elements cannot be resized.

### [!UICONTROL Move] {#move}

Move elements on your page. Unlike the [!UICONTROL Rearrange] option, [!UICONTROL Move] does not shift other elements to make room for the element being moved. Use the arrow keys to fine tune the move. (Planned enhancement: support to ensure moved elements are not hidden behind other elements.)

In certain situations, such as when a CSS restriction requires an element to remain inside its parent element, you cannot move the element outside its parent. An element cannot be moved outside of a container that has following CSS property: `overflow: hidden`.

See [!UICONTROL Rearrange] above for more information about inconsistent behavior with the [!UICONTROL Move] and [!UICONTROL Rearrange] actions due to lazy loading of DOM elements.

### [!UICONTROL Hide]

Hide the element. The white space remains, but the content is removed.

### [!UICONTROL Remove]

Remove the element. The white space behind the image is removed and the space where the element was is collapsed.

**Note:** Items within a "classic" mbox (an mbox created within a Target Classic campaign) cannot be removed using this option.

## [!UICONTROL Expand Section]

Select the parent element in addition to the originally selected element. When you select any parent element, all children of that element are automatically selected. You can expand the selection multiple times.

## [!UICONTROL Navigate to Link]

Open the destination of the link.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Undo changes you make to your activities during an editing session. You can also redo changes that have been previously undone.

## Considerations {#considerations}

* If an offer contains HTML content, see "How at.js renders offers with HTML content" in [How at.js works](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=zh-Hans){target=_blank} for more information.

## Custom element support {#custom}

The VEC supports [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) to let you create and test personalized experiences and offers on custom elements and on elements inside custom elements. This functionality is available in the VEC for all [!DNL Target] activity types.

>[!NOTE]
>
>VEC support for custom elements is supported in [at.js version](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} 2.7.0 (or later){target=_blank}. Ensure that your website has the required version deployed. If you are using the [Visual Experience Composer helper extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), it must also have the required version of at.js deployed. The VEC options described above are not visible and available for use with non-supported versions of at.js.
>
>VEC support for custom elements is currently not supported with the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

Most VEC actions are supported on custom events and inside custom events, with the following exceptions: 

The following actions are not available on custom elements:

* [!UICONTROL Edit]
  * [!UICONTROL Text/HTML]
  * [!UICONTROL Link]
  * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

The following action is not available inside custom elements:

* [!UICONTROL Layout]
  * [!UICONTROL Rearrange]-->

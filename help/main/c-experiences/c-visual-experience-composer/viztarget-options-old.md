---
keywords: 可视化体验编辑器选项；体验编辑器选项；体验选项；编辑文本；编辑html；编辑文本/html；编辑背景颜色；背景颜色；插入元素；编辑链接；链接；可视化体验编辑器链接；编辑css类；css类；交换选件；选件交换；交换图像；图像交换；移除项；项移除；隐藏项；项隐藏；重新排列；移动元素；元素移动；调整元素大小；元素大小；扩展选择；导航到此链接；链接导航；链接；撤消；重做；撤消/重做；自定义事件；Web组件；选件决策；offer decisioning
description: 浏览 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)中可用的选项。
title: 如何使用[!UICONTROL Visual Experience Composer] (VEC)选项？
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '2667'
ht-degree: 55%

---

# 可视化体验编辑器选项

单击[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)中的某个页面元素时，会显示一个菜单，其中提供了可用于该元素类型的选项。 此外，页面底部会显示一个 DOM 路径，可让您轻松浏览页面结构。

各种[!UICONTROL Visual Experience Composer] (VEC)操作将分组到相应的菜单选项中，以使您的工作更快捷、更有效：

![VEC 选项菜单](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>可用的选项取决于您创建或编辑的活动类型。

## [!UICONTROL Edit]

以下选项可供选择：

### [!UICONTROL Text/HTML] {#edit-text-html}

更改元素的 HTML 代码，例如文本区域、按钮或链接的文本。

除了 HTML 代码外，您还可以编辑和插入自定义 JavaScript。

编辑[!UICONTROL A/B]和[!UICONTROL Experience Targeting]活动的文本和HTML时，可以使用多种富文本格式选项。 您可以选择字体、选择字体样式、更改文本对齐方式以及使用其他标准文本格式设置选项。修改 HTML 时，您可以在 HTML 的代码视图和富编辑视图之间切换。

可以嵌套以下 HTML5 标记：

| 标记 | 允许的嵌套标记 |
| --- | --- |
| `<a>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>`、`<div>`、`<figure>`、`<figcaption>` |
| `<ins>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>` |
| `<del>` | `<ul>`、`<ol>`、`<menu>`、`<h1-h6>`、`<p>` |
| `<label>` | `<p>` |

### [!UICONTROL Background Color]

使用拾色器选择或配置背景颜色。您可以选择一个色样，并使用 RGB 值或十六进制颜色代码对其进行调整。拾色器中的红色 x 可使背景透明。

**注意：**&#x200B;此选项不适用于已设置背景图像的元素。

### [!UICONTROL Styles] {#styles}

使用[!UICONTROL Styles]面板查看或编辑所选元素的现有样式的值。 您还可以添加其他样式。

要访问[!UICONTROL Styles]面板，请单击VEC中的某个页面元素，然后单击&#x200B;**[!UICONTROL Edit]** > **[!UICONTROL Styles]**。

[!UICONTROL Styles]面板将显示在VEC的右侧。 该面板包含一个样式列表，允许您编辑样式或将其添加到所选元素。如果您习惯使用层叠样式表 (CSS)，或者从开发人员那里接收代码，则可以使用实时 CSS 编辑器查看更改并添加样式。

![“样式”面板](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

应用不同的样式时，您始终可以在更改任何部分后通过单击[!UICONTROL Styles]面板右上角显示的[!UICONTROL Revert]图标还原更改。 单击[!UICONTROL Revert]图标将还原在当前部分的面板上所做的所有更改。

展开每个部分以编辑或添加样式，具体如下文中所述。要保存更改，请单击面板顶部的[!UICONTROL Back]图标以返回到面板的主显示屏，然后单击&#x200B;**[!UICONTROL Save]**。

主面板上以及各个部分面板上每个选项旁边的蓝色圆点表示您已更改了相应的样式。 此视觉指示器可让您在单击[!UICONTROL Save]之前轻松查看更改。

>[!NOTE]
>
>布局更改、背景颜色、调整大小和移动的快速操作也可在 VEC 菜单中作为单独的操作使用。这些选项可用作单独的操作，您也可以使用“样式”菜单，如此处所述。

* **[!UICONTROL Background]**

  更改背景颜色和图像。

   * 颜色（指定颜色代码或使用拾色器）
   * 图像（从图像选择器中选择图像）
   * 图像源（指定外部 URL）
   * 附件
      * 单击顶部的下拉列表以选择 scroll、fixed 或 local
      * 单击底部的下拉列表以选择 repeat、repeat-x、repeat-y、no-repeat、space 或 round
   * 剪辑
      * 单击顶部的下拉列表以选择 border-box、padding-box、content-box 或 text
      * 单击底部的下拉列表以选择自动音频或音频

* **[!UICONTROL Typography]**

  更改元素的排版规则。排版规则编辑既快速又简便。

  尽管可以使用富文本编辑器(编辑文本/HTML)进行微调，但可通过此选项快速执行更改整个元素的操作。 如果要仅对部分文本（而非全文）应用排版规则更改，请使用[富文本编辑器](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)。

  您可以编辑以下排版样式：

   * [!UICONTROL Font size]
   * [!UICONTROL Font weight]
   * [!UICONTROL Font style]
   * [!UICONTROL Color] （指定颜色代码或使用拾色器）
   * [!UICONTROL Word spacing]
   * [!UICONTROL Line height]
   * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  更改所选元素的边距。您可以更改左边距、右边距、下边距和上边距。

  单击每个边距的下拉图标，从以下选项中进行选择：

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （拖动滑块以设置边距或指定每个边距的像素数）

  边距支持正值和负值。

  Target还支持其他大小单位，例如rem、pc、em。 有关这些单位的更多信息，请参阅[网页样式表CSS提示和技巧](https://www.w3.org/Style/Examples/007/units.en.html)。

* **[!UICONTROL Padding]**

  更改所选元素的内边距。您可以更改左内边距、右内边距、下内边距和上内边距。

  拖动滑块以设置内边距或指定每个内边距的像素数。

  内边距支持的宽度范围从 0 开始。

  Target还支持[其他大小单位](https://www.w3.org/Style/Examples/007/units.en.html)，例如rem、pc、em。

* **[!UICONTROL Border]**

  单击面板顶部的边框图标可更改所选元素的边框。

  您可以编辑每个边框的以下样式（上边框、右边框、下边框和左边框）：

   * [!UICONTROL Border style] （无、隐藏、点线、虚线、实线或双线）
   * [!UICONTROL Border color] （指定颜色代码或使用拾色器）
   * [!UICONTROL Border width] （拖动滑块以选择边框宽度或以像素为单位指定宽度）

  边框支持的宽度范围从 0 开始。

  Target还支持[其他大小单位](https://www.w3.org/Style/Examples/007/units.en.html)，例如rem、pc、em。

* **[!UICONTROL Position]**

  将所选元素从当前位置移动。您可以更改元素的顶部、底部、左侧、右侧和[Z索引](https://www.w3schools.com/cssref/pr_pos_z-index.asp)位置。

  单击[!UICONTROL Static]下拉列表以从以下位置选项中进行选择：

   * [!UICONTROL Static]
   * [!UICONTROL Relative]
   * [!UICONTROL Absolute]
   * [!UICONTROL Sticky]
   * [!UICONTROL Fixed]

  单击每个位置的下拉图标，从以下选项中进行选择：

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （拖动滑块以定位元素或指定要移动元素的像素数）

  位置支持正值和负值。

  Target还支持[其他大小单位](https://www.w3.org/Style/Examples/007/units.en.html)，例如rem、pc、em。

* **[!UICONTROL Size]**

  更改所选元素的宽度和高度。

  单击[!UICONTROL Width]和[!UICONTROL Height]旁边的下拉图标，从以下选项中进行选择：

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （拖动滑块以调整元素的大小或指定每个维度的像素数）

* **[!UICONTROL Filter]**

  拖动每个筛选器选项的滑块或指定所需的百分比：

   * [!UICONTROL Sepia]
   * [!UICONTROL Contrast]
   * [!UICONTROL Brightness]
   * [!UICONTROL GrayScale]
   * [!UICONTROL Blur]
   * [!UICONTROL Opacity]
   * [!UICONTROL Invert]
*[!UICONTROL &#x200B; Hue-rotate]
   * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  如果您习惯使用层叠样式表 (CSS)，或者从开发人员那里接收代码，则可以使用实时 CSS 编辑器查看更改并添加样式。

  CSS 编辑器将显示您在“样式”面板中所做的任何更改。如下图所示，字体大小、顶部边框和图像大小已被更改：

  ![包含更改的 CSS 编辑器](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  请注意上图中[!UICONTROL Typography]、[!UICONTROL Border]和[!UICONTROL Size]选项旁边的蓝点。 这些圆点表示您已更改这些部分。 如果打开这些部分的面板，则蓝色圆点将显示在您更改的特定选项旁边。

  如果您所需的样式在[!UICONTROL Styles]中默认不可用，则可以键入自己的代码。

  CSS编辑器仅显示当前会话的详细信息。 如果保存更改后重新打开编辑器，那么即使再次选择相同的元素，编辑器中也不会显示有关先前更改的详细信息。

  >[!IMPORTANT]
  >
  >您可以使用 CSS 编辑器来应用背景图像，但可能会导致闪烁。请在部署之前测试您的更改。

### [!UICONTROL CSS Class]

指定用于元素的预定义 CSS 类。如果选择多个元素，请用空格分隔多个 CSS 类。

可用于[!UICONTROL A/B]、[!UICONTROL Automated Personalization]和[!UICONTROL Multivariate Test]活动。

### [!UICONTROL Link]

更改链接中的 URL。

使用编辑链接来更新选择器，以指向相同的图像元素。但是，不支持链接到不同的图像元素。要链接到其他图像元素，请从代码编辑器中删除原始操作，并使用[!UICONTROL Visual Experience Composer]将操作应用于其他图像元素。

## [!UICONTROL Insert Before]

以下选项可供选择：

### [!UICONTROL Offer Decision]

添加在 [!DNL Adobe Journey Optimizer][&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank}中创建的选件，以便使用offer decisioning向客户提供最佳选件和体验。

**注意：**&#x200B;此选项仅在编辑或创建[手动[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)或[[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活动时可用。 此选项不适用于其他活动类型。

有关详细信息，请参阅[使用优惠决策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

### [!UICONTROL Image]、[!UICONTROL HTML]和[!UICONTROL Text]

除了修改现有的内容之外，还可以向页面添加任何类型的元素。可添加文本、代码、列表等，以创建完全不同的体验来进行测试。

在页面上选择一个元素，然后单击[!UICONTROL Insert Before]并选择想要插入图像、HTML还是文本。 插入元素显示在所选元素的前面。

插入元素的行为取决于页面的结构、CSS 和其他页面配置选项。需要有效的 HTML 才能正确显示页面。始终在插入项目后测试您的页面，以确保该页面可以按预期显示。

[!UICONTROL Recommendations]支持[!UICONTROL Insert Before] DIV、SECTION和ARTICLE标记的内容。

**注意：**&#x200B;插入图像需要启用 [!DNL Adobe Scene7 Publishing System]，以便您可以访问图像库。

### 推荐

将推荐包含到 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中。有关更多信息，请参阅[将推荐作为产品建议](/help/main/c-recommendations/recommendations-as-an-offer.md)。

### [!UICONTROL Experience Fragment]

将在 [!DNL Adobe Experience Manager] (AEM) 中创建的体验片段插入 [!DNL Target] 活动，以协助优化或进行个性化处理。有关更多信息，请参阅 [AEM 体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

## [!UICONTROL Insert After]

以下选项可供选择：

### [!UICONTROL Offer Decision]

添加在 [!DNL Adobe Journey Optimizer][&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank}中创建的选件，以便使用offer decisioning向客户提供最佳选件和体验。

**注意：**&#x200B;此选项仅在编辑或创建[手动[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)或[[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活动时可用。 此选项不适用于其他活动类型。

有关详细信息，请参阅[使用优惠决策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

### [!UICONTROL Image]、[!UICONTROL HTML]和[!UICONTROL Text]

除了修改现有的内容之外，还可以向页面添加任何类型的元素。可添加文本、代码、列表等，以创建完全不同的体验来进行测试。

在页面上选择一个元素，然后单击[!UICONTROL Insert After]并选择想要插入图像、HTML还是文本。 插入元素显示在所选元素的后面。

插入元素的行为取决于页面的结构、CSS 和其他页面配置选项。需要有效的 HTML 才能正确显示页面。始终在插入项目后测试您的页面，以确保该页面可以按预期显示。

[!UICONTROL Recommendations]支持[!UICONTROL Insert After] DIV、SECTION和ARTICLE标记的内容。

**注意：**&#x200B;插入图像需要启用 [!DNL Adobe Scene7 Publishing System]，以便您可以访问图像库。

### 推荐

将推荐包含到 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中。有关更多信息，请参阅[将推荐作为产品建议](/help/main/c-recommendations/recommendations-as-an-offer.md)。

### [!UICONTROL Experience Fragment]

将在 [!DNL Adobe Experience Manager] (AEM) 中创建的体验片段插入 [!DNL Target] 活动，以协助优化或进行个性化处理。有关更多信息，请参阅 [AEM 体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

## [!UICONTROL Replace Content]

以下选项可供选择：

### [!UICONTROL Offer Decision]

添加在 [!DNL Adobe Journey Optimizer][&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank}中创建的选件，以便使用offer decisioning向客户提供最佳选件和体验。

**注意：**&#x200B;此选项仅在编辑或创建[手动[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)或[[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活动时可用。 此选项不适用于其他活动类型。

有关详细信息，请参阅[使用优惠决策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

### [!UICONTROL Image]

从内容库中选择一个不同的图像。可用于交换的图像包括上传到 Experience Cloud 资产文件夹和上传到 Target 内容库的图像。

在初始活动创建期间显示的 URL 并不是用于交付的 URL。活动同步后，该 URL 将更新为生产 Scene7 URL。

例如，初始的 URL 可能如下例所示：

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

活动同步后，交付 URL 可能如下所示：

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

推荐支持 DIV、SECTION 和 ARTICLE 标记中的“替换为”。

**注意：**&#x200B;交换图像要求使用 Adobe Scene7 Publishing System 帐户。

### [!UICONTROL HTML Offer]

从[!UICONTROL Content Library]中选择其他选件。

**注意：**&#x200B;[!DNL Target]HTML 产品建议存储在 服务器上。

HTML选件最长可达256 KB。

### 推荐

将推荐包含到 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中。有关更多信息，请参阅[将推荐作为产品建议](/help/main/c-recommendations/recommendations-as-an-offer.md)。

### [!UICONTROL Experience Fragment]

将在 [!DNL Adobe Experience Manager] (AEM) 中创建的体验片段插入 [!DNL Target] 活动，以协助优化或进行个性化处理。有关更多信息，请参阅 [AEM 体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

## [!UICONTROL Layout]

以下选项可供选择：

### [!UICONTROL Rearrange]

在元素拖放到同一父元素或 DIV 内的其他位置。需要移动其他元素的位置以为重新排列的元素腾出空间。

**注意**：点击跟踪对重新排列的项无效。

当前，某些VEC操作（如[!UICONTROL Rearrange]和[!UICONTROL Move]）假定源父元素和目标父元素的同级元素已完全加载。 如果在父DOM元素（源或目标）下发生延迟加载，则这些VEC操作可能会导致不一致行为。 我们正在寻找一种更可靠的方法，以使VEC操作在延迟加载的DOM元素中正常工作。 作为临时解决方法，您可以在这些场景中使用[!UICONTROL Custom Code]来呈现您的体验。

### [!UICONTROL Resize]

调整页面上的元素大小。选择[!UICONTROL Resize]后，元素右下角会出现一个句柄，允许您拖动该角调整大小。 按住 Shift 键保持相同的宽高比。

**注意：**&#x200B;无法调整内联元素的大小。

### [!UICONTROL Move] {#move}

移动页面上的元素。与[!UICONTROL Rearrange]选项不同，[!UICONTROL Move]不移动其他元素以便为要移动的元素腾出空间。 可使用箭头键来微调移动。（计划的增强功能：支持确保移动的元素不会隐藏在其他元素后面。）

在某些情况下，如CSS限制要求将元素保留在其父元素内时，您不能将该元素移到其父元素之外。 无法将元素移动到具有以下 CSS 属性的容器之外：`overflow: hidden`。

有关由于延迟加载DOM元素而导致[!UICONTROL Move]和[!UICONTROL Rearrange]操作出现不一致行为的详细信息，请参阅上面的[!UICONTROL Rearrange]。

### [!UICONTROL Hide]

隐藏元素。保留空格但会删除内容。

### [!UICONTROL Remove]

删除元素。删除图像后面的空格，并且折叠元素所在的空间。

**注意：**&#x200B;使用此选项无法删除“classic”mbox（Target Classic 促销活动中创建的一个 mbox）中的项目。

## [!UICONTROL Expand Section]

除了最初选定的元素外，还需要选择父元素。选择任意父元素时，该元素的所有子元素均会自动选定。您可以多次展开选定内容。

## [!UICONTROL Navigate to Link]

打开链接的目标。

## [!UICONTROL Undo]/[!UICONTROL Redo]

在编辑会话期间撤消对活动所做的更改。您也可以重做先前已撤消的更改。

## 注意事项 {#considerations}

* 如果选件包含HTML内容，请参阅[at.js的工作方式](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank}中的“at.js如何渲染包含HTML内容的选件”以了解更多信息。

## 自定义元素支持 {#custom}

VEC支持[Web组件](https://developer.mozilla.org/en-US/docs/Web/Web_Components)，允许您在自定义元素和自定义元素内部的元素上创建和测试个性化体验和选件。 此功能在VEC中可用于所有[!DNL Target]活动类型。

>[!NOTE]
>
>[at.js版本](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} 2.7.0（或更高版本）{target=_blank}支持自定义元素的VEC支持。 确保您的网站已部署所需的版本。 如果您使用的是[可视化体验编辑器助手扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)，则还必须部署所需的at.js版本。 上述VEC选项不可见，并且无法与不受支持的at.js版本一起使用。
>
>[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}当前不支持自定义元素的VEC支持。

自定义事件和自定义事件内支持大多数VEC操作，但以下除外：

以下操作在自定义元素中不可用：

* [!UICONTROL Edit]
   * [!UICONTROL Text/HTML]
   * [!UICONTROL Link]
   * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

以下操作在自定义元素中不可用：

* [!UICONTROL Layout]
   * [!UICONTROL Rearrange]

## 使用DOM路径浏览元素 {#dom-path}

单击页面上的某个元素时，将显示 VEC 选项菜单。此外，单击某个元素时，相应的 DOM 路径将显示在页面底部。

![DOM 路径](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

您可以使用 DOM 路径快速查看有关所选元素（类型、ID 和类）的信息，并向上或向下移动 DOM 路径以选择所需的元素。

将鼠标悬停在 DOM 路径上方时，将显示一个蓝色方框，其会高亮显示 VEC 中的相应元素。单击某个元素时，橙色方框将高亮显示该元素，并显示 VEC 选项菜单，具体如上文中所述。

您可以使用 DOM 路径轻松导航到 VEC 中的任何父元素、同级元素或子元素。

设置[点击跟踪](/help/main/c-activities/r-success-metrics/click-tracking.md)时，还可使用 DOM 路径功能。

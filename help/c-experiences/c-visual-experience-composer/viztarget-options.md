---
description: 单击可视化体验编辑器 (VEC) 中某个页面元素时，会显示一个菜单，其中提供了可用于该元素类型的选项。
keywords: 可视化体验编辑器选项;体验编辑器选项;体验选项;编辑文本;编辑 html;编辑文本/html;编辑背景颜色;背景颜色;插入元素;编辑链接;链接;可视化体验编辑器链接;编辑 css 类;css 类;交换选件;选件交换;交换图像;图像交换;删除项目;项目删除;隐藏项目;项目隐藏;重新排列;移动元素;元素移动;调整元素大小;元素大小调整;元素;展开选定内容;导航到此链接;导航链接;链接导航;导航;撤消;重做;撤消/重做
seo-description: 单击 Adobe Target 可视化体验编辑器 (VEC) 中某个页面元素时，会显示一个菜单，其中提供了可用于该元素类型的选项。
seo-title: Adobe Target 可视化体验编辑器 (VEC) 选项
solution: Target
title: 可视化体验编辑器选项
topic: Standard
uuid: efd672ae-c684-455f-8ec1-0efcfe1e9534
translation-type: tm+mt
source-git-commit: d21838bdf17327b394f6e3106ea5ce4bc72605e6

---


# 可视化体验编辑器选项{#visual-experience-composer-options}

单击可视化体验编辑器 (VEC) 中某个页面元素时，会显示一个菜单，其中提供了可用于该元素类型的选项。此外，页面底部会显示一个 DOM 路径，可让您轻松浏览页面结构。

## VEC 选项

各种可视化体验编辑器 (VEC) 操作被分组为相应的菜单选项，可让您更快速、更高效地工作。

![VEC 选项菜单](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>可用选项取决于所编辑的活动类型。

### 编辑

以下选项可供选择：

#### 文本/HTML {#edit-text-html}

更改元素的 HTML 代码，例如文本区域、按钮或链接的文本。

除了 HTML 代码外，您还可以编辑和插入自定义 JavaScript。

编辑 A/B 和体验定位活动的文本和 HTML 时，可以使用多种富文本格式选项。您可以选择字体、选择字体样式、更改文本对齐方式以及使用其他标准文本格式设置选项。修改 HTML 时，您可以在 HTML 的代码视图和富编辑视图之间切换。

可以嵌套以下 HTML5 标记：

| 标记 | 允许的嵌套标记 |
| --- | --- |
| `<a>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>`、`<div>`、`<figure>`、`<figcaption>` |
| `<ins>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>` |
| `<del>` | `<ul>`、`<ol>`、`<menu>`、`<h1-h6>`、`<p>` |
| `<label>` | `<p>` |

#### 背景颜色

使用拾色器选择或配置背景颜色。您可以选择一个色样，并使用 RGB 值或十六进制颜色代码对其进行调整。拾色器中的红色 x 可使背景透明。

**注意：**&#x200B;此选项不适用于已设置背景图像的元素。

#### 样式 {#styles}

使用[!UICONTROL 样式]面板可查看或编辑所选元素现有样式的值。您还可以添加其他样式。

要访问[!UICONTROL 样式]面板，请单击 VEC 中的某个页面元素，然后单击&#x200B;**[!UICONTROL 编辑]** &gt; **[!UICONTROL 样式]**。

[!UICONTROL 样式]面板将显示在 VEC 的右侧。该面板包括一个样式列表，允许您编辑样式或将其添加到所选元素。如果您习惯使用层叠样式表 (CSS)，或者从开发人员那里接收代码，则可以使用实时 CSS 编辑器查看更改并添加样式。

![“样式”面板](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

应用不同的样式时，您始终可以在对任意部分进行更改后，通过单击[!UICONTROL 样式]面板右上角显示的[!UICONTROL 还原]图标还原您所做的更改。请注意，单击[!UICONTROL 还原]图标将还原在当前部分的面板上所做的所有更改。

展开每个部分以编辑或添加样式，具体如下文中所述。要保存更改，请单击面板顶部的“返回”图标以返回到面板的主显示屏，然后单击&#x200B;**[!UICONTROL 保存]**。

请注意，主面板上以及各个部分面板上每个选项旁边的蓝色圆点所表示的意思是，您已经对相应的样式进行了更改。这样，您就可以在单击[!UICONTROL 保存]之前轻松查看更改。

>[!NOTE]
>
>布局更改、背景颜色、调整大小和移动的快速操作也可在 VEC 菜单中作为单独的操作使用。这些选项可以作为单独的操作使用，您也可以使用“样式”菜单，具体如下文中所述。

* **背景**

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

* **排版规则**

   更改元素的排版规则。排版规则编辑既快速又简便。

   尽管可以使用富文本编辑器（编辑文本/HTML）进行微调，但可通过此选项快速执行对整个元素进行更改的操作。如果要仅对部分文本（而非全文）应用排版规则更改，请使用[富文本编辑器](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)。

   您可以编辑以下排版样式：

   * 字体大小
   * 字体粗细
   * 字体样式
   * 颜色（指定颜色代码或使用拾色器）
   * 字间距
   * 行高
   * 文本对齐方式

* **边距**

   更改所选元素的边距。您可以更改左边距、右边距、下边距和上边距。

   单击每个边距的下拉图标，从以下选项中进行选择：

   * 自动
   * 值（拖动滑块以设置边距或指定每个边距的像素数）
   边距支持正值和负值。

   Target 还支持其他大小单位，例如 rem、pc、em 等。For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **内边距**

   更改所选元素的内边距。您可以更改左内边距、右内边距、下内边距和上内边距。

   拖动滑块以设置内边距或指定每个内边距的像素数。

   内边距支持的宽度范围从 0 开始。

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **边框**

   单击面板顶部的边框图标可更改所选元素的边框。

   您可以编辑每个边框的以下样式（上边框、右边框、下边框和左边框）：

   * 边框样式（无、隐藏、点线、虚线、实线或双线）
   * 边框颜色（指定颜色代码或使用拾色器）
   * 边框宽度（拖动滑块以选择边框宽度或以像素为单位指定宽度）
   边框支持的宽度范围从 0 开始。

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **位置**

   将所选元素从当前位置移动。You can change the element's top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

   单击[!UICONTROL 静态]下拉列表，从以下位置选项中进行选择：

   * 静态
   * 相对
   * 绝对
   * 置顶
   * 固定
   单击每个位置的下拉图标，从以下选项中进行选择：

   * 自动
   * 值（拖动滑块以定位元素或指定要移动元素的像素数）
   位置支持正值和负值。

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **大小**

   更改所选元素的宽度和高度。

   单击[!UICONTROL 宽度]和[!UICONTROL 高度]旁边的下拉图标，从以下选项中进行选择：

   * 自动
   * 值（拖动滑块以调整元素的大小或指定每个维度的像素数）

* **过滤器**

   拖动每个筛选器选项的滑块或指定所需的百分比：

   * 棕褐色
   * 对比度
   * 亮度
   * 灰度
   * 模糊
   * 不透明度
   * 反转
   * 色相旋转
   * 饱和度

* **CSS 编辑器**

   如果您习惯使用层叠样式表 (CSS)，或者从开发人员那里接收代码，则可以使用实时 CSS 编辑器查看更改并添加样式。

   CSS 编辑器将显示您在“样式”面板中所做的任何更改。如下图所示，字体大小、顶部边框和图像大小已被更改：

   ![包含更改的 CSS 编辑器](/help/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   请注意上图中[!UICONTROL 排版规则]、[!UICONTROL 边框]和 [!UICONTROL 大小]选项旁边的蓝色圆点。这些圆点表示您已对这些部分进行了更改。如果打开这些部分的面板，则蓝色圆点将显示在您更改的特定选项旁边。

   如果[!UICONTROL 样式]中默认未提供所需的样式，则可以键入自己的代码。

   请注意，CSS 编辑器仅显示当前会话的详细信息。如果保存更改后重新打开编辑器，那么即使再次选择相同的元素，编辑器中也不会显示有关先前更改的详细信息。

   >[!I重要信息]
   >
   >您可以使用 CSS 编辑器来应用背景图像，但可能会导致闪烁。请在部署之前测试您的更改。

#### CSS 类

指定用于元素的预定义 CSS 类。如果选择多个元素，请用空格分隔多个 CSS 类。

其可用于 [!UICONTROL A/B]、[!UICONTROL 自动个性化]和[!UICONTROL 多变量测试]活动。

#### 链接

更改链接中的 URL。

使用编辑链接来更新选择器，以指向相同的图像元素。但是，不支持链接到不同的图像元素。要链接到不同的图像元素，请从代码编辑器中删除原始操作，并使用[!UICONTROL 可视化体验编辑器]将该操作应用于其他图像元素。

### 此项前插入

以下选项可供选择：

#### 图像、HTML 和文本

除了修改现有的内容之外，还可以向页面添加任何类型的元素。可添加文本、代码、列表等，以创建完全不同的体验来进行测试。

在页面上选择一个元素，然后单击[!UICONTROL 此项前插入]并选择想要插入图像、HTML，还是文本。插入元素显示在所选元素的前面。

插入元素的行为取决于页面的结构、CSS 和其他页面配置选项。需要有效的 HTML 才能正确显示页面。始终在插入项目后测试您的页面，以确保该页面可以按预期显示。

[!UICONTROL 推荐]支持[!UICONTROL 此项前插入] DIV、SECTION 和 ARTICLE 标记的内容。

**注意：**&#x200B;插入图像需要启用 [!DNL Adobe Scene7 Publishing System]，以便您可以访问图像库。

#### 推荐

将推荐包含到 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中。有关更多信息，请参阅[将推荐作为选件](/help/c-recommendations/recommendations-as-an-offer.md)。

#### 体验片段

将在 [!DNL Adobe Experience Manager] (AEM) 中创建的体验片段插入 [!DNL Target] 活动，以协助优化或进行个性化处理。有关更多信息，请参阅 [AEM 体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)。

### 此项后插入

以下选项可供选择：

#### 图像、HTML 和文本

除了修改现有的内容之外，还可以向页面添加任何类型的元素。可添加文本、代码、列表等，以创建完全不同的体验来进行测试。

在页面上选择一个元素，然后单击[!UICONTROL 此项后插入]并选择想要插入图像、HTML，还是文本。插入元素显示在所选元素的后面。

插入元素的行为取决于页面的结构、CSS 和其他页面配置选项。需要有效的 HTML 才能正确显示页面。始终在插入项目后测试您的页面，以确保该页面可以按预期显示。

[!UICONTROL 推荐]支持[!UICONTROL 此项后插入] DIV、SECTION 和 ARTICLE 标记的内容。

**注意：**&#x200B;插入图像需要启用 [!DNL Adobe Scene7 Publishing System]，以便您可以访问图像库。

#### 推荐

将推荐包含到 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中。有关更多信息，请参阅[将推荐作为选件](/help/c-recommendations/recommendations-as-an-offer.md)。

#### 体验片段

将在 [!DNL Adobe Experience Manager] (AEM) 中创建的体验片段插入 [!DNL Target] 活动，以协助优化或进行个性化处理。有关更多信息，请参阅 [AEM 体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)。

### 替换为

以下选项可供选择：

#### 图像

从内容库中选择一个不同的图像。可用于交换的图像包括上传到 Experience Cloud 资产文件夹和上传到 Target 内容库的图像。

在初始活动创建期间显示的 URL 并不是用于交付的 URL。活动同步后，该 URL 将更新为生产 Scene7 URL。

例如，初始的 URL 可能如下例所示：

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

活动同步后，交付 URL 可能如下所示：

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

推荐支持 DIV、SECTION 和 ARTICLE 标记中的“替换为”。

**注意：**&#x200B;交换图像要求使用 Adobe Scene7 Publishing System 帐户。

#### HTML 选件

从[!UICONTROL 内容库]中选择一个不同的选件。

**注意：**[!DNL Target]HTML 选件存储在 服务器上。

HTML 选件的大小最多可达 256KB。

#### 推荐

将推荐包含到 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中。有关更多信息，请参阅[将推荐作为选件](/help/c-recommendations/recommendations-as-an-offer.md)。

#### 体验片段

将在 [!DNL Adobe Experience Manager] (AEM) 中创建的体验片段插入 [!DNL Target] 活动，以协助优化或进行个性化处理。有关更多信息，请参阅 [AEM 体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)。

### 版式

以下选项可供选择：

#### 重新排列

在元素拖放到同一父元素或 DIV 内的其他位置。需要移动其他元素的位置以为重新排列的元素腾出空间。

**注意：**&#x200B;点击跟踪对重新排列的元素无效。

#### 调整大小

调整页面上的元素大小。当您选择[!UICONTROL 调整大小]时，在元素的右下角会显示一个控柄，可通过它来拖动该角以进行大小调整。按住 Shift 键保持相同的宽高比。

**注意：**&#x200B;无法调整内联元素的大小。

#### 移动 {#move}

移动页面上的元素。与“[!UICONTROL 重新排列]”选项不同，“[!UICONTROL 移动]”选项不会移动其他元素来为正在移动的元素腾出空间。可使用箭头键来微调移动。（计划的增强功能：提供相关支持以确保所移动的元素不会隐藏在其他元素后面。）

在某些情况下，如 CSS 限制要求将元素保留在其父元素内时，您不能将该元素移到其父元素之外。元素不能移到具有以下CSS属性的容器之外： `overflow: hidden`.

#### 隐藏

隐藏元素。保留空格但会删除内容。

#### 删除

删除元素。删除图像后面的空格，并且折叠元素所在的空间。

**注意：**&#x200B;使用此选项无法删除“classic”mbox（Target Classic 促销活动中创建的一个 mbox）中的项目。

### 展开选定内容

除了最初选定的元素外，还需要选择父元素。选择任意父元素时，该元素的所有子元素均会自动选定。您可以多次展开选定内容。

### 导航到链接

打开链接的目标。

### 撤消/重做

在编辑会话期间撤消对活动所做的更改。您也可以重做先前已撤消的更改。

## 注意事项 {#considerations}

* 如果选件包含HTML内容，请参阅 [How at.js works中的“How at.js renders offers with HTML content”(如何使用HTML内容呈现选件](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render) )以了解更多信息。

## 使用 DOM 路径浏览元素 {#dom-path}

单击页面上的某个元素时，将显示 VEC 选项菜单。此外，单击某个元素时，相应的 DOM 路径将显示在页面底部。

![DOM 路径](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

您可以使用 DOM 路径快速查看有关所选元素（类型、ID 和类）的信息，并向上或向下移动 DOM 路径以选择所需的元素。

将鼠标悬停在 DOM 路径上方时，将显示一个蓝色方框，其会高亮显示 VEC 中的相应元素。单击某个元素时，橙色方框将高亮显示该元素，并显示 VEC 选项菜单，具体如上文中所述。

您可以使用 DOM 路径轻松导航到 VEC 中的任何父元素、同级元素或子元素。

设置[点击跟踪](/help/c-activities/r-success-metrics/click-tracking.md)时，还可使用 DOM 路径功能。
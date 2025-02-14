---
keywords: 可视化体验编辑器；vec；wysiwyg
description: 了解Adobe Target 25.2.1版本（2025年2月17日）中可视化体验编辑器(VEC)中引入的更改。
title: 新可视化体验编辑器(VEC)中引入哪些更改？
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 3aeac3344c2bbc2a44da80b5a359e55c9419b59b
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer]个更改

[!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文介绍VEC的先前版本与更新版本之间的差异。

>[!IMPORTANT]
>
>更新的[!UICONTROL Visual Editing Composer]需要Chrome Web Store上提供的[!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper]扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

创建或编辑现有活动时将显示VEC。

![可视化体验编辑器 (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## VEC的重大更改

以下部分将说明更新后的VEC与先前版本相比所发生的重大更改。

### [!UICONTROL Experiences]面板

与以前的版本一样，[!UICONTROL Experiences]面板保留在VEC的左侧。 无法折叠[!UICONTROL Experiences]面板。

![体验面板](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

您可以使用[!UICONTROL Experiences]面板创建、重命名或删除体验。 单击&#x200B;**[!UICONTROL Add]**&#x200B;图标（![添加图标](/help/main/assets/icons/Add.svg)）以添加新体验。 单击[!UICONTROL More Actions]图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg) ）以复制、删除或重新定向体验。

### [!UICONTROL Components]面板（新）

您可以向网页添加许多组件，并使用新的[!UICONTROL Components]面板根据需要对其进行编辑。

![组件面板](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

要添加新组件，请从要插入到“设计”画布中的现有页面元素之上的“组件”面板中拖动该组件。 然后选择将组件插入到选定元素的前面，也就是之后。

与以前的VEC版本相比，您不能将选定的元素替换为组件。

### [!UICONTROL Modifications]面板

要打开[!UICONTROL Modifications]面板，请单击[!UICONTROL Components]面板中的[!UICONTROL Show Modifications]图标（![显示修改面板](/help/main/assets/icons/History.svg)）。 [!UICONTROL Modifications]面板将编辑画布的位置从右侧更改为左侧。

![“修改”面板](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

[!UICONTROL Modifications]面板显示在[!UICONTROL Visual Experience Composer] (VEC)中对页面所做的所有更改，并允许进行其他更改（如CSS选择器、Mbox和自定义代码）。

单击[!UICONTROL More Options]图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg) ）以添加修改、删除所有修改或删除所有无效修改。 单击[!UICONTROL Select]以执行批量操作： [!UICONTROL Apply to All Pages]或[!UICONTROL Delete]。

### [!UICONTROL Properties]面板（新）

新的[!UICONTROL Properties]面板允许您更改页面上选定元素的属性，无论这些元素是HTML元素还是特定于[!DNL Target]的对象，例如推荐或选件。

![属性面板](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

单击面板顶部的图标以编辑HTML代码或删除、复制或隐藏元素。 更改显示在[!UICONTROL Modifications]面板中。

[!UICONTROL Properties]面板可在右边栏中折叠。 单击面板右侧的[!UICONTROL Show/Hide Properties]图标（![属性图标](/help/main/assets/icons/Propertie.svg) ）以折叠或显示[!UICONTROL Properties]面板。

### 活动设置/配置

单击设计画布顶部显示的[!UICONTROL Configure]图标（![配置图标](/help/main/assets/icons/Setting.svg)）以显示活动属性菜单。

![活动配置选项](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

通过不同的选项，您可以启用或禁用多页面或多个受众活动、分配属性（[[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)功能）或编辑页面交付规则。

其位置和功能与以前的VEC UI类似。

### [!UICONTROL Design]/[!UICONTROL Browse]模式

使用设计画布顶部显示的[!UICONTROL Design]/[!UICONTROL Browse]切换功能，在设计模式和浏览模式之间切换。

![设计和浏览切换](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

使用[!UICONTROL Browse]模式浏览您的网站并选择您要更新的视图或页面。 切换回[!UICONTROL Design]模式以添加或编辑更改。

### [!UICONTROL Undo]/[!UICONTROL Redo]

您可以通过单击[!UICONTROL Undo]图标（![撤消图标](/help/main/assets/icons/Undo.svg) ）来撤消所做的更改。

VEC中的![撤消图标](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

要重做某项操作，请展开撤消/[!UICONTROL Redo]按钮组并选择[!UICONTROL Redo]。

### [!UICONTROL Design]画布

[!UICONTROL Design]画布允许您选择视区，包括适合屏幕、[!UICONTROL Desktop]、[!UICONTROL Tablet]、[!UICONTROL Mobile Landscape]和[!UICONTROL Mobile Portrait]。 默认情况下，画布将页面与[管理](/help/main/administrating-target/visual-experience-composer-set-up.md)部分中定义的视区一起适合屏幕。

![视区选项](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

更新的VEC还允许您通过单击相应的图标（![放大图标](/help/main/assets/icons/ZoomIn.svg)或![缩小图标](/help/main/assets/icons/ZoomOut.svg) ）进行放大或缩小。

## 显示UI更改的可视化插图

下图显示了对更新后的VEC所做的高级UI更改。 插图顶部显示更新的VEC UI，底部显示之前的UI。 箭头显示各种元素移动的位置。

（单击图像可将其展开到浏览器的整个宽度。）

![VEC比较 — 与以前的UI新比较](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}

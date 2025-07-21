---
keywords: 可视化体验编辑器；vec；wysiwyg
description: 了解Adobe Target 25.2.1版本（2025年2月17日）中可视化体验编辑器(VEC)中引入的更改。
title: 新可视化体验编辑器(VEC)中引入哪些更改？
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: c8cbf4998c304910a63e31acc3ec93a04ac652ae
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer]个更改

[!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文介绍VEC的先前版本与更新版本之间的差异。

>[!IMPORTANT]
>
>更新的[!UICONTROL Visual Editing Composer]需要[!DNL Adobe Experience Cloud]中可用的[[!UICONTROL Visual Editing Helper] ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)扩展[!DNL Chrome Web Store]。

创建或编辑现有活动时将显示VEC。

![可视化体验编辑器 (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## VEC的重大更改

以下部分将说明更新后的VEC与先前版本相比所发生的重大更改。

### [!UICONTROL Experiences]边栏

与以前的版本一样，[!UICONTROL Experiences]边栏保留在VEC的左侧。 无法折叠[!UICONTROL Experiences]边栏。

![体验边栏](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

您可以使用[!UICONTROL Experiences]边栏创建、重命名或删除体验。 单击&#x200B;**[!UICONTROL Add]**&#x200B;图标（![添加图标](/help/main/assets/icons/Add.svg)）以添加新体验。 单击[!UICONTROL More Actions]图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg) ）以复制、删除或重新定向体验。

### [!UICONTROL Components]边栏（新）

您可以将多个组件添加到网页中，并根据需要使用新的[!UICONTROL Components]边栏编辑它们。

![组件边栏](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

要添加新组件，请将组件从要插入的[!UICONTROL Components]边栏拖动到[!UICONTROL Design]画布中的现有页面元素上。 然后选择将组件插入到选定元素的前面，也就是之后。

>[!NOTE]
>
>如果您在此区域中看到[!UICONTROL Modifications]边栏而不是[!UICONTROL Components]边栏，请单击&#x200B;**[!UICONTROL Show Components]**&#x200B;图标（![显示组件图标](/help/main/assets/icons/Add.svg)）。 [!UICONTROL Show Components]图标（![显示组件图标](/help/main/assets/icons/Add.svg)）和[!UICONTROL Show Modifications]图标（![显示修改边栏](/help/main/assets/icons/History.svg)）用作显示相应选项的切换。
>
>要折叠[!UICONTROL Components]边栏并放大[!UICONTROL Design]画布，请在[!UICONTROL Components]边栏打开时单击（![显示组件图标](/help/main/assets/icons/Add.svg) ）图标。

### [!UICONTROL Modifications]边栏

要打开[!UICONTROL Modifications]边栏，请单击[!UICONTROL Show Modifications]边栏中的![图标（](/help/main/assets/icons/History.svg)显示修改边栏[!UICONTROL Components]）。 [!UICONTROL Modifications]边栏从编辑画布的右侧更改为左侧。

![修改边栏](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>[!UICONTROL Show Components]图标（![显示组件图标](/help/main/assets/icons/Add.svg)）和[!UICONTROL Show Modifications]图标（![显示修改边栏](/help/main/assets/icons/History.svg)）用作显示相应选项的切换。
>
>要在[!UICONTROL Modifications]边栏打开时折叠[!UICONTROL Design]边栏并放大[!UICONTROL Modifications]画布，请单击[!UICONTROL Show Modifications]图标（![显示修改边栏](/help/main/assets/icons/History.svg) ）图标。

[!UICONTROL Modifications]边栏显示对VEC中的页面所做的所有更改，并允许您进行其他更改（如CSS选择器、Mbox和自定义代码）。

单击[!UICONTROL More Options]图标（![更多操作图标](/help/main/assets/icons/MoreSmall.svg) ）以添加修改、删除所有修改或删除所有无效修改。 单击[!UICONTROL Select]以执行批量操作： [!UICONTROL Apply to All Pages]或[!UICONTROL Delete]。

要再次显示[!UICONTROL Modifications]边栏，请单击[!UICONTROL Hide Modifications]边栏中的![图标（](/help/main/assets/icons/History.svg)显示修改边栏[!UICONTROL Modifications]）。

### [!UICONTROL Properties]边栏（新）

通过[!UICONTROL Properties]边栏可以更改页面上选定元素的属性，无论这些元素是HTML元素还是特定于[!DNL Target]的对象，例如推荐或选件。

![属性边栏](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

单击边栏顶部的图标可编辑HTML代码或者删除、复制或隐藏元素。 更改显示在[!UICONTROL Modifications]边栏中。

![属性图标](/help/main/c-experiences/c-visual-experience-composer/assets/options-icons.png)

[!UICONTROL Properties]边栏可在右边栏中折叠。 单击边栏右侧的[!UICONTROL Show/Hide Properties]图标（![属性图标](/help/main/assets/icons/Propertie.svg)）以折叠或显示[!UICONTROL Properties]边栏。

### 活动设置/配置

单击设计画布顶部显示的[!UICONTROL Configure]图标（![配置图标](/help/main/assets/icons/Setting.svg)）以显示活动属性菜单。

![活动配置选项](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

通过不同的选项，您可以分配属性、编辑页面交付规则、指定网站首选项、添加其他页面以及启用或禁用多页面或多个受众活动。 分配[!UICONTROL Properties]是[[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)功能。

其位置和功能与以前的VEC UI类似。

### [!UICONTROL Design]/[!UICONTROL Browse]模式

使用[!UICONTROL Design]边栏顶部显示的[!UICONTROL Browse]/[!UICONTROL Properties]切换功能，在设计模式和浏览模式之间切换。

![设计和浏览切换](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

使用[!UICONTROL Browse]模式浏览您的网站并选择您要更新的视图或页面。 切换回[!UICONTROL Design]模式以添加或编辑更改。

### [!UICONTROL Undo]/[!UICONTROL Redo]

您可以通过单击[!UICONTROL Undo]图标（![撤消图标](/help/main/assets/icons/Undo.svg) ）来撤消所做的更改。

VEC中的![撤消图标](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

要重做某项操作，请展开撤消/[!UICONTROL Redo]按钮组并选择[!UICONTROL Redo]。

### [!UICONTROL Design]画布

[!UICONTROL Design]画布允许您选择视区，包括适合屏幕、[!UICONTROL Desktop]、[!UICONTROL Tablet]、[!UICONTROL Mobile Landscape]和[!UICONTROL Mobile Portrait]。

![视区选项](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

更新的VEC还允许您通过单击相应的图标（![放大图标](/help/main/assets/icons/ZoomIn.svg)或![缩小图标](/help/main/assets/icons/ZoomOut.svg) ）进行放大或缩小。

## 显示UI更改的可视化插图

下图显示了对更新后的VEC所做的高级UI更改。 插图顶部显示更新的VEC UI，底部显示之前的UI。 箭头显示各种元素移动的位置。

（单击图像可将其展开到浏览器的整个宽度。）

![VEC比较 — 与以前的UI新比较](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}

## 有关更新的UI的更多信息

* [[!DNL Target Standard/Premium] 25.2.1（2025年2月17日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!DNL Target]中[!UICONTROL Activities]、[!UICONTROL Recommendations]和[!UICONTROL Visual Experience Composer] (VEC)的关键UI更改的摘要。

* [[!DNL Target Standard/Premium] 25.1.1（2025年1月9日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!DNL Target]在[!UICONTROL Offers Library]中关键UI更改的摘要。

* [了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供简要概述以帮助您熟悉[!DNL Target]，并提供更深入的信息和分步说明的链接。

* [[!UICONTROL Visual Experience Composer]更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文介绍VEC旧版本与更新版本之间的差异。

* [[!UICONTROL Visual Experience Composer]选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文介绍更新的VEC UI及其选项。

* [[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)：此常见问题解答关于新[!DNL Target] UI和[!UICONTROL Visual Experience Composer] (VEC)的常见问题，包括导航更改、功能位置以及弃用临时UI版本切换。 无论您是营销人员、开发人员还是管理员，此常见问题解答都可以帮助您顺利过渡并充分利用更新后的UI。
---
keywords: 体验定位;登陆页面测试
description: 元素选择器是可以标识一个或多个元素的CSS表达式。 了解如何在Adobe [!DNL Target]可视化体验编辑器(VEC)中使用元素选择器。
title: 我可以在可视化体验编辑器(VEC)中使用元素选择器吗？
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
TQID: 'https://experienceleague.adobe.com/sqvUyLFddt7HPHH62jwpOZmwTIMSg-hyLIUr8w-x7vg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 4%
---
# 在[!UICONTROL 可视化体验编辑器]中使用的元素选择器 {#vec-selectors}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解元素选择器在[!UICONTROL 可视化体验编辑器] (VEC)中的工作方式、如何选择使用的选择器以及[!DNL Target]如何为元素生成选择器。

>[!ENDSHADEBOX]

元素选择器是可以标识一个或多个元素的CSS表达式。 有关CSS选择器的基本信息可在&#x200B;*[!DNL Mozilla Developer Network]* (MDN)上的[选择器](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)文档中找到。

无论使用元素类还是元素ID，均在帐户首选项中进行设置。 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**，然后选择首选的CSS选择器：

* **[!UICONTROL 使用元素ID]**：如果同一ID用于多个元素，或者元素ID在页面加载时可能发生更改，则禁用。
* **[!UICONTROL 使用元素类]**：如果页面上的元素类可能发生更改，则禁用。
* **[!UICONTROL 使用首选选择器]**：启用可在VEC中使用唯一选择器来识别网站的关键区域。

>[!NOTE]
>
>元素类在&#x200B;**[!UICONTROL A/B测试]**、**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 多变量测试]**&#x200B;活动中可用作选择器。

有关何时使用CSS选择器以及何时使用唯一ID的信息，请参阅[可视化体验编辑器最佳实践和限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#vec-best-practices)。

## [!DNL Target]如何为元素生成选择器 {#generate-selector}

[!DNL Target]使用简单的算法创建一个选择器。 生成逻辑如下：

1. 如果某个元素的ID为，例如`id="container"`，则该元素的选择器为`#container`。

   例如：

   ```html
   <div class="wrapper">
     <div id="container"> <!-- Selector is computed for this element -->
       <ul class="navigation">
         <li class="item active"> Home </li>
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

1. 如果元素包含类特性，则[!DNL Target]尝试使用元素上存在的任何类的第一个类。

   [!DNL Target]尝试解析该父元素，直到找到`<HTML>`元素或具有ID的元素。 每当元素包含ID并且选择器计算为其子代子项时，此元素的ID即会为选择器贡献内容。

   例如：

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li class="item active"> Home </li> <!-- Selector is computed for this element -->
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

   在此示例中，选择器是`#container` > `ul.navigation:eq(0)` > `li.item:eq(0)` （“>”表示直接子项）。

   `eq`提供具有“tagName=UL”和第一个类`navigation`的元素的索引。 因此，`index` 为 0。 有关更多信息，请参阅 MDN 中的[选择器](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)文章。

1. 如果元素不包含类，[!DNL Target]将对该元素使用`tagName`，并遍历父元素，直到找到`<HTML>`元素或具有ID的元素。

   例如：

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li> Home </li>
         <li> Men </li>
         <li class="active"> Women </li>
         <li> Kids </li><!-- Selector is computed for this element -->
       </ul>
     </div>
   </div>
   ```

   选择器是`#container` > `ul.navigation:eq(0)` > `li:nth-of-type(4)`。

在此过程中：

* 可使用任何CSS选择器，只要它唯一标识DOM中的元素即可。
* 以上方法是[!DNL Target]使用的方法。 [!DNL Target]不强制采用此方法。 可以添加任何选择器，只要它唯一标识元素即可。
* 可以在选择器中使用任何属性。 本文仅使用类名作为示例。

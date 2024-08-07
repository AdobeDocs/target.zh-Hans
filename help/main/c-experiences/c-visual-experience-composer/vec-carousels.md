---
keywords: 可视化体验编辑器;VEC;轮播
description: 了解如何创建可以在Adobe [!DNL Target] 可视化体验编辑器(VEC)中编辑的轮播效果。
title: 如何在可视化体验编辑器中创建轮播效果？
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 58%

---

# 创建可以在可视化体验编辑器中工作的轮播效果

此主题显示如何创建可以在[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)中编辑的轮播。

执行以下步骤时，[!DNL Target] 始终知道选定的幻灯片具有“选择器”，可选出正确的幻灯片，即使几秒钟后可视化体验编辑器中的幻灯片发生更改也是如此。

1. 创建静态 HTML 占位符。

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. 添加 CSS 以设计外观。

   请勿在设计时使用 JavaScript。

   >[!NOTE]
   >
   >如果[!UICONTROL Render Using JavaScript]选项与自定义代码一起在可视化体验编辑器中使用，则当前不支持该选项。

1. 仅更新 classNames 以隐藏其他幻灯片，并使用计时器/动画显示下一张幻灯片。

   请勿使用 JavaScript 更新 DOM 结构。

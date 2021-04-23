---
keywords: 可视化体验编辑器;VEC;轮播
description: 了解如何创建可在Adobe [!DNL Target] Visual Experience Composer(VEC)中编辑的传送。
title: 如何在Visual Experience Composer中创建轮盘？
feature: 可视化体验编辑器 (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 71%

---

# 创建可以在可视化体验编辑器中工作的轮播效果

本主题说明如何创建可在[!DNL Adobe Target] [!UICONTROL  Visual Experience Composer](VEC)中编辑的传送。

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
   >当前，不支持在可视化体验编辑器中将“[!UICONTROL 使用 JavaScript 渲染]”选项与自定义代码一起使用。

1. 仅更新 classNames 以隐藏其他幻灯片，并使用计时器/动画显示下一张幻灯片。

   请勿使用 JavaScript 更新 DOM 结构。

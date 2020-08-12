---
keywords: Visual Experience Composer;VEC;carousel
description: 本主题显示了如何创建可以在可视化体验编辑器 (VEC) 中编辑的轮播效果。
title: 创建可以在可视化体验编辑器中工作的轮播效果
feature: null
subtopic: Multivariate Test
topic: Standard
uuid: 19538f6e-445c-49ca-9f0d-b49fc330b721
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 100%

---


# 创建可以在可视化体验编辑器中工作的轮播效果{#creating-carousels-that-work-in-the-visual-experience-composer}

本主题显示了如何创建可以在可视化体验编辑器 (VEC) 中编辑的轮播效果。

执行以下步骤时，[!DNL Target] 始终知道选定的幻灯片具有“选择器”，可选出正确的幻灯片，即使几秒钟后可视化体验编辑器中的幻灯片发生更改也是如此。

1. 创建静态 HTML 占位符。

   ```
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
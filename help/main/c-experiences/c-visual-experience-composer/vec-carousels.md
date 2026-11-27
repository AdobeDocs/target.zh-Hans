---
keywords: 可视化体验编辑器;VEC;轮播
description: 了解如何创建可以在Adobe [!DNL Target]可视化体验编辑器(VEC)中编辑的轮播效果。
title: 如何在可视化体验编辑器中创建轮播效果？
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
TQID: 'https://experienceleague.adobe.com/RN04MJgC49BI2-h2e-i-kgSRTejpLHzKACm-hOv2VCE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 2%
---
# 创建可在[!UICONTROL 可视化体验编辑器]中工作的轮播效果 {#vec-carousels}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何构建可以在&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)中编辑的轮播。

>[!ENDSHADEBOX]

可以在[!DNL Adobe Target] **[!UICONTROL 可视化体验编辑器]** (VEC)中编辑使用以下结构构建的轮播。 此结构使每个幻灯片的选择器保持有效，因此[!DNL Target]始终标识正确的幻灯片，即使显示的幻灯片在VEC中加载页面后几秒内发生更改也是如此。

1. 将幻灯片创建为静态HTML占位符，其中一张幻灯片可见，而其他幻灯片按类隐藏。

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. 仅使用CSS设计外观。 请勿对此使用JavaScript。

   >[!NOTE]
   >
   >在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中将&#x200B;**[!UICONTROL 使用JavaScript渲染]**&#x200B;选项与自定义代码一起使用时，当前不支持该选项。

1. 通过仅更新类名显示下一张幻灯片：隐藏其他幻灯片，并使用计时器或动画显示下一张幻灯片。 切勿使用JavaScript更新DOM结构。

---
keywords: 响应式；移动视区；视区；设备；移动；响应式Web设计；rwd
description: 移动视区可帮助您了解Adobe [!DNL Target] 活动在各种尺寸的屏幕上的显示情况。 查找一列表流行的设备视口大小和分辨率。
title: 如何使用移动视区实现响应式体验？
feature: 可视化体验编辑器 (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
translation-type: tm+mt
source-git-commit: cb42be6b0791711d3a9ddf5680cf6d6e32045579
workflow-type: tm+mt
source-wordcount: '1165'
ht-degree: 35%

---

# 移动视区，提供响应式体验

移动视区允许您在各种尺寸的屏幕上预览[!DNL Adobe Target]活动。

移动视区预览功能专为响应式站点而设计，这些站点可以在各种设备、窗口和屏幕大小上完美呈现。 响应式网站会自动调整和适应任何屏幕大小，包括台式机、笔记本电脑、平板电脑或手机。

>[!NOTE]
>
> * 如果您的网站是响应式网站，而且桌面页面与移动设备页面中使用的元素相同，只是配置不同，则可以使用移动设备视区。如果您有一个具有单独结构（如`m.mysite.com`）的单独移动站点，请改用[多页活动](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48)。
   >
   >
* 如果与重定向选件叠加发生了重叠，则移动设备视区将不可用。


视区通过网页在屏幕上所填充的矩形大小来定义。视口是浏览器窗口的大小，减去滚动条和工具栏。 浏览器使用“CSS 像素”。很多设备（例如使用 Retina 显示屏的设备）的视区小于其宣称的设备分辨率。

以下是常用设备的视口和分辨率。 请记住在[!DNL Target]中使用视口大小。

>[!NOTE]
>
>多个网站列出了常用设备的视区大小。例如，请参阅[https://viewportsizer.com/devices/](https://viewportsizer.com/devices/)。 有关最准确、最新的信息，请查阅设备制造商的网站。

| 设备 | 视区大小 （宽x高） | 设备分辨率（宽x高） |
|---|---|---|
| iPhone12 | 390 x 844 | 1170 x 2532 |
| iPhone 12 Mini | 360 x 780 | 1080 x 2340 |
| iPhone 12 Pro | 390 x 844 | 1170 x 2532 |
| iPhone 12 Pro Max | 428 x 926 | 1248 x 2778 |
| iPhone SE | 214 x 379 | 640 x 1136 |
| iPhone 11 Pro Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 Xs Max | 414 x 896 | 1242 x 2688 |
| iPhone11 | 414 x 896 | 828 x 1792 |
| iPhone 11 Xr | 414 x 896 | 828 x 1792 |
| iPhone 11 Pro | 375 x 812 | 1125 x 2436 |
| iPhone 11 X | 375 x 812 | 1125 x 2436 |
| iPhone 11 Xs | 375 x 812 | 1125 x 2436 |
| iPhone X | 375 x 812 | 1125 x 2436 |
| iPhone 8 Plus | 414 x 736 | 1080 x 1920 |
| iPhone8 | 375 x 667 | 750 x 1334 |
| iPhone 7 Plus | 414 x 736 | 1080 x 1920 |
| iPhone7 | 375 x 667 | 750 x 1334 |
| iPhone 6s Plus | 414 x 736 | 1080 x 1920 |
| iPhone6s | 375 x 667 | 750 x 1334 |
| iPhone 6 Plus | 414 x 736 | 1080 x 1920 |
| iPhone6 | 375 x 667 | 750 x 1334 |
| iPad Pro | 1024 x 1366 | 2048 x 2732 |
| iPad 第三代和第四代 | 768 x 1024 | 1536 x 2048 |
| iPad Air 1 和 2 | 768 x 1024 | 1536 x 2048 |
| iPad Mini | 768 x 1024 | 768 x 1024 |
| iPad Mini 2 和 3 | 768 x 1024 | 1536 x 2048 |
| Nexus 6P | 411 x 731 | 1440 x 2560 |
| Nexus 5X | 411 x 731 | 1080 x 1920 |
| Google Pixel | 411 x 731 | 1080 x 1920 |
| Google Pixel XL | 411 x 731 | 1440 x 2560 |
| Google Pixel 2 | 411 x 731 | 1080 x 1920 |
| Google Pixel 2 XL | 411 x 823 | 1440 x 2880 |
| Samsung Galaxy Note 5 | 480 x 853 | 1440 x 2560 |
| LG G5 | 360瓦x 640 | 1440 x 2560 |
| LG G4 | 360瓦x 640 | 1440 x 2560 |
| LG G3 | 360瓦x 640 | 1440 x 2560 |
| One Plus 3 | 480 x 853 | 1080 x 1920 |
| Samsung Galaxy S9 | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S9+ | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S8 | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S8+ | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S7 | 360 x 640 | 1440 x 2560 |
| Samsung Galaxy S7 Edge | 360 x 640 | 1440 x 2560 |
| Nexus 7 (2013) | 600 x 960 | 1200 x 1920 |
| Nexus 9 | 768 x 1024 | 1536 x 2048 |
| Samsung Galaxy Tab 10 | 800 x 1280 | 800 x 1280 |
| Chromebook Pixel | 1280 x 850 | 2560 x 1700 |

要向特定设备上的访客传送活动，请在活动图中为该设备选择适当的受众。 使用移动设备 Web 编辑器可在该设备上编辑活动页面。要在整个数字体验中运行活动，以确保在所有设备上都能正常显示，请不要应用定位。 而应使用移动视口预览每个屏幕大小的活动。

对于响应式网站，通常您的网站设计为当由屏幕尺寸特定的设备访问时以不同视图打开。 这些可触发新视图的屏幕大小称为“CSS 断点”。CSS断点是指网站内容根据设备宽度做出响应的点，可向访客显示最佳布局。 CSS断点也称为[媒体查询](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)。

将CSS断点保存在[!DNL Target]中，这样您就可以为定义的每个视图预览体验。 这些体验中的每个都显示在[!DNL Target]接口的移动视口中。 单击显示屏顶部的相应视区，即可打开每个屏幕大小所对应的视图。

如果您的站点没有响应，则如果您的活动针对特定设备，请使用Mobile Web Composer视图站点。

>[!IMPORTANT]
>
>您可以从移动视区中编辑体验。 但是，这些更改适用于所有视口和设备，而不仅仅适用于您正在使用的视口。 同样，在常规桌面视图中编辑体验时，所有屏幕大小的页面均会发生相应的更改，而不仅仅是桌面视图中的页面。当前，[!DNL Target]不支持特定于视图的页面更改。

## 移动视口配置{#task_B4B161499DC0470584ED922A4D20FCAB}

配置要在创建体验时提供的移动视区。

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视体验书写器]**。
1. 在&#x200B;**[!UICONTROL 移动视区配置]**&#x200B;部分，单击&#x200B;**[!UICONTROL 添加]**。

   ![添加视口](/help/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   或

   要更改现有移动视口的配置，请选择该视口，然后单击[!UICONTROL 编辑]（铅笔）图标。

1. 键入移动设备视区的名称。

   为移动设备视区键入一个便于识别的描述性名称。名称最长可包含 36 个字符。

1. 指定移动设备的屏幕大小，包括宽度和高度。

   宽度可以是150到968像素。 高度可以是150到1280像素。

1. （可选）选择设备的操作系统。

   选项：

   * Android
   * iOS
   * Windows
   * Symbian
   * Blackberry

   如果您使用[增强型体验编辑器](/help/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D)，并选择了一种操作系统，则 会在您查看页面时模拟该设备。[!DNL Target]例如，如果Android与响应式站点上的iOS的外观不同，则[!DNL Target]会模拟该行为。

1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>
>如果尝试删除正在使用的移动视口，将显示以下消息：&quot;此视口当前与一个或多个活动关联。 您需要先从这些活动中删除视口，然后才能删除它。”

## 创建响应式体验{#task_D6332438B5EE48CCA8AF199270F1CAEF}

将移动视区添加到您的[!DNL Target]活动，为移动屏幕创建响应式体验。

1. 创建所需的[活动](/help/c-activities/activities.md)。
1. 在[!UICONTROL Visual Experience Composer](VEC)中，单击&#x200B;**[!UICONTROL Settings]**&#x200B;齿轮图标，然后选择&#x200B;**[!UICONTROL 添加Mobile Viewports]**。

   ![“添加移动视区”选项](/help/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. 单击&#x200B;**[!UICONTROL 设备]**&#x200B;图标，然后启用每个应具有移动设备视区的设备。

   ![启用移动视口](/help/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   移动设备视区将按宽度以从小到大的顺序排列。

1. 根据需要编辑移动设备视区。

   您对体验所做的任何更改将应用于所有设备上的体验。 例如，您更改标题中的文本。

   将鼠标悬停在视区名称上，以查看视区大小。

   ![iPhone 11 Pro Max响应式体验](/help/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. 如果需要，可通过单击所需的方向图标在纵向和横向模式之间切换。

   ![方向选项](/help/c-experiences/c-visual-experience-composer/assets/orientation.png)

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 可视化体验编辑器（第 2 个，共 2 个）(7:29)  ![概述徽章](/help/assets/overview.png)

以下演示视频包含有关通过可视化体验编辑器使用移动设备视区的信息：

* 重命名和复制体验
* 创建重定向体验
* 将活动定位到单个 URL 或一组 URL
* 创建多页面活动
* 预览和构建响应式网站的体验
* 使用叠加高亮显示元素类型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Adobe Target ![概述徽章](/help/assets/overview.png)中的帐户首选项

此视频包含有关设置移动视口的信息，从4:40开始。

>[!VIDEO](https://video.tv.adobe.com/v/17379)

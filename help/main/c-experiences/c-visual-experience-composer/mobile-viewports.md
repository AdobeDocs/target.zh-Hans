---
keywords: 响应式;移动视区;视区;设备;移动;响应式网页设计;rwd
description: 移动视区可帮助您了解 Adobe  [!DNL Target]  活动在各种大小的屏幕上的观感。查找常用设备视区大小和分辨率的列表。
title: 如何将移动视区用于响应式体验？
feature: Visual Experience Composer (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1154'
ht-degree: 99%

---

# 移动视区用于响应式体验

通过移动视区，可预览您的 [!DNL Adobe Target] 活动在各种大小的屏幕上的效果。

移动视区预览功能专为可在各种设备、窗口和屏幕大小上呈现出良好效果的响应式网站设计而成。响应式网站自动调整和适应任意屏幕大小，包括台式机、笔记本电脑、平板电脑或手机。

>[!NOTE]
>
> * 如果您的网站为响应式，并在移动设备页面上以不同的配置使用桌面页面中的相同元素，则可使用移动视区。如果您有单独的移动网站采用单独的架构，例如 `m.mysite.com`，请改为使用[多页面活动](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48)。
>
>* 如果与重定向选件叠加发生了重叠，则移动设备视区将不可用。


按网页在屏幕上填充的矩形大小定义视区。视区是浏览器窗口减去滚动条和工具栏的大小。浏览器使用“CSS 像素”。很多设备（例如使用 Retina 显示屏的设备）的视区小于其宣称的设备分辨率。

常用设备的视区和分辨率如下。切记在 [!DNL Target] 中使用视区大小。

>[!NOTE]
>
>许多网站列出常用设备的视区大小。例如，请参阅 `https://viewportsizer.com/devices/`。有关最准确和最新的信息，请参考设备制造商的网站。

| 设备 | 视区大小（宽度x高度） | 设备分辨率（宽度 x 高度） |
|---|---|---|
| iPhone 12 | 390 x 844 | 1170 x 2532 |
| iPhone 12 Mini | 360 x 780 | 1080 x 2340 |
| iPhone 12 Pro | 390 x 844 | 1170 x 2532 |
| iPhone 12 Pro Max | 428 x 926 | 1248 x 2778 |
| iPhone SE | 214 x 379 | 640 x 1136 |
| iPhone 11 Pro Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 Xs Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 | 414 x 896 | 828 x 1792 |
| iPhone 11 Xr | 414 x 896 | 828 x 1792 |
| iPhone 11 Pro | 375 x 812 | 1125 x 2436 |
| iPhone 11 X | 375 x 812 | 1125 x 2436 |
| iPhone 11 Xs | 375 x 812 | 1125 x 2436 |
| iPhone X | 375 x 812 | 1125 x 2436 |
| iPhone 8 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 8 | 375 x 667 | 750 x 1334 |
| iPhone 7 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 7 | 375 x 667 | 750 x 1334 |
| iPhone 6s Plus | 414 x 736 | 1080 x 1920 |
| iPhone 6s | 375 x 667 | 750 x 1334 |
| iPhone 6 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 6 | 375 x 667 | 750 x 1334 |
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
| LG G5 | 360w x 640 | 1440 x 2560 |
| LG G4 | 360w x 640 | 1440 x 2560 |
| LG G3 | 360w x 640 | 1440 x 2560 |
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

要向特定设备上的访客投放活动，请在活动示中选择适合该设备的受众。使用移动 Web 编辑器在该设备上编辑活动中的页面。要在您的整个数字体验中运行某项活动以确保在所有设备上均可正常显示该活动，请勿应用定位。请改用移动视区在每种屏幕大小上预览该活动。

对于响应式网站，一般将您的网站设计为在受到特定屏幕大小的设备访问时以不同的视图打开。那些触发新视图的屏幕大小称为“CSS 断点”。CSS 断点是网站内容根据设备宽度作出响应以向访客显示最优布局的那些点。CSS 断点也称为[媒体查询](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)。

请将 CSS 断点保存在 [!DNL Target] 中，以使您可预览自己对所定义的每个视图拥有的体验。其中每个体验都显示在 [!DNL Target] 界面中的某个移动视区中。通过沿显示屏的顶部单击该视区，打开每个屏幕大小的视图。

如果您的网站并非响应式，并且您的活动以特定设备为目标，则使用移动 Web 编辑器查看网站。

>[!IMPORTANT]
>
>可从移动视区中编辑体验。但是，这些更改适用于所有视区和设备，而非仅适用于您所在的视区。同样，在普通桌面视图中编辑体验将更改所有屏幕大小的页面，而非仅更改桌面视图的页面。目前，[!DNL Target] 不支持特定于视区的页面更改。

## 移动视区配置 {#task_B4B161499DC0470584ED922A4D20FCAB}

配置要在创建体验时提供的移动视区。

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视体验编辑器]**。
1. 在&#x200B;**[!UICONTROL 移动视区配置]**&#x200B;部分中，单击&#x200B;**[!UICONTROL 添加]**。

   ![添加视区](/help/main/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   或

   要更改现有移动视区的配置，请选择该视区，然后单击[!UICONTROL 编辑]（铅笔）图标。

1. 键入移动设备视区的名称。

   为移动设备视区键入一个便于识别的描述性名称。名称最长可包含 36 个字符。

1. 指定移动设备的屏幕大小，包括宽度和高度。

   宽度可以在 150 到 968 像素之间。高度可以在 150 到 1280 像素之间。

1. （可选）选择设备的操作系统。

   选项：

   * Android
   * iOS
   * Windows
   * Symbian
   * Blackberry

   如果您使用[增强型体验编辑器](/help/main/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D)并选择某个操作系统，则 [!DNL Target] 在您查看页面时模拟该设备。例如，如果在您的响应式网站上对于 Android 与 iOS 显示的外观不同，则 [!DNL Target] 模仿该行为。

1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>
>如果尝试删除正在使用的移动视区，则显示以下消息：“此视区当前关联到一个或多个活动。需要从这些活动中去除此视区后才能删除它。”

## 创建响应式体验 {#task_D6332438B5EE48CCA8AF199270F1CAEF}

将移动视区添加到您的 [!DNL Target] 活动以创建用于移动设备的响应式体验。

1. 创建[所需活动](/help/main/c-activities/activities.md)。
1. 在[!UICONTROL 可视体验编辑器] (VEC) 中，单击&#x200B;**[!UICONTROL 设置]**&#x200B;齿轮图标，然后选择&#x200B;**[!UICONTROL 添加移动视区]**。

   ![添加移动视区选项](/help/main/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. 单击&#x200B;**[!UICONTROL 设备]**&#x200B;图标，然后启用每个应有移动视区的设备。

   ![启用移动视区](/help/main/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   移动设备视区将按宽度以从小到大的顺序排列。

1. 根据需要编辑移动设备视区。

   您对体验作出的任何更改都应用于所有设备上的体验。例如，您可以更改标题中的文本。

   将鼠标悬停在视区的名称上以查看该视区的大小。

   ![iPhone 11 Pro Max 响应式体验](/help/main/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. 如果需要，可通过单击所需的方向图标，在纵向和横向模式之间切换。

   ![方向选项](/help/main/c-experiences/c-visual-experience-composer/assets/orientation.png)

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 可视化体验编辑器（第 2 个，共 2 个）(7:29) ![“概述”标记](/help/main/assets/overview.png)

以下演示视频包含有关通过可视化体验编辑器使用移动设备视区的信息：

* 重命名和复制体验
* 创建重定向体验
* 将活动定位到单个 URL 或一组 URL
* 创建多页面活动
* 预览和构建响应式网站的体验
* 使用叠加高亮显示元素类型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Adobe Target 中的帐户首选项 ![“概述”标记](/help/main/assets/overview.png)

本视频从 4:40 开始介绍设置移动视区。

>[!VIDEO](https://video.tv.adobe.com/v/17379)

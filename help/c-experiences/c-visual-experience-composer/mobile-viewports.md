---
keywords: responsive;mobile viewports;viewport;devices;mobile;responsive web design;rwd
description: 移动视区可帮助您预览Adobe Target活动在各种尺寸屏幕上的显示方式。
title: 移动视图端口，提供响应式体验
uuid: 86a74584-4a4d-428b-9d29-f7ebdf0cef2a
translation-type: tm+mt
source-git-commit: 292c6a5f2a49e6de88778c944099f4971d8a10af
workflow-type: tm+mt
source-wordcount: '1413'
ht-degree: 65%

---


# Mobile Viewports for responsive experiences{#mobile-viewports-for-responsive-experiences}

Mobile viewports help you preview how your [!DNL Target] activities appear on screens of various sizes.

移动视区预览功能专为响应式站点而设计，这些站点可以在各种设备、窗口或屏幕大小上呈现良好效果。 响应式网站会自动调整和适应任何屏幕大小，包括台式机、笔记本电脑、平板电脑或手机。

>[!NOTE]
>
> * 如果您的网站是响应式网站，而且桌面页面与移动设备页面中使用的元素相同，只是配置不同，则可以使用移动设备视区。If you have a separate mobile site with a separate structure, such as `m.mysite.com`, use a [multipage activity](../../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) instead.
   >
   >
* 如果与重定向选件叠加发生了重叠，则移动设备视区将不可用。


视区通过网页在屏幕上所填充的矩形大小来定义。视区是指浏览器窗口减去滚动条和工具栏后的大小。浏览器使用“CSS 像素”。很多设备（例如使用 Retina 显示屏的设备）的视区小于其宣称的设备分辨率。

下面是一些常用设备的视区和分辨率。Remember to use the viewport size in [!DNL Target]. 多个网站列出了常用设备的视区大小。例如，请参 [阅](https://viewportsizer.com/devices/) https://viewportsizer.com/devices/或查阅设备制造商的网站。

| 设备 | 视区大小 | 设备分辨率 |
|---|---|---|
| iPhone SE | 375 宽 x 667 高 | 750 宽 x 1334 高 |
| iPhone 11 Pro Max | 414 宽 x 896 高 | 1242 宽 x 2688 高 |
| iPhone 11 Xs Max | 414 宽 x 896 高 | 1242 宽 x 2688 高 |
| iPhone11 | 414 宽 x 896 高 | 828 宽 x 1792 高 |
| iPhone 11 Xr | 414 宽 x 896 高 | 828 宽 x 1792 高 |
| iPhone 11 Pro | 375 宽 x 812 高 | 1125 宽 x 2436 高 |
| iPhone 11 X | 375 宽 x 812 高 | 1125 宽 x 2436 高 |
| iPhone 11 Xs | 375 宽 x 812 高 | 1125 宽 x 2436 高 |
| iPhone X | 375 宽 x 812 高 | 1125 宽 x 2436 高 |
| iPhone 8 Plus | 414 宽 x 736 高 | 1080 宽 x 1920 高 |
| iPhone8 | 375 宽 x 667 高 | 750 宽 x 1334 高 |
| iPhone 7 Plus | 414 宽 x 736 高 | 1080 宽 x 1920 高 |
| iPhone7 | 375 宽 x 667 高 | 750 宽 x 1334 高 |
| iPhone6s 加号 | 414 宽 x 736 高 | 1080 宽 x 1920 高 |
| iPhone6s | 375 宽 x 667 高 | 750 宽 x 1334 高 |
| iPhone 6 Plus | 414 宽 x 736 高 | 1080 宽 x 1920 高 |
| iPhone6 | 375 宽 x 667 高 | 750 宽 x 1334 高 |
| iPad Pro | 1024 宽 x 1366 高 | 2048 宽 x 2732 高 |
| iPad 第三代和第四代 | 768 宽 x 1024 高 | 1536 宽 x 2048 高 |
| iPad Air 1 和 2 | 768 宽 x 1024 高 | 1536 宽 x 2048 高 |
| iPad Mini | 768 宽 x 1024 高 | 768 宽 x 1024 高 |
| iPad Mini 2 和 3 | 768 宽 x 1024 高 | 1536 宽 x 2048 高 |
| Nexus 6P | 411 宽 x 731 高 | 1440 宽 x 2560 高 |
| Nexus 5X | 411 宽 x 731 高 | 1080 宽 x 1920 高 |
| Google Pixel | 411 宽 x 731 高 | 1080 宽 x 1920 高 |
| Google Pixel XL | 411 宽 x 731 高 | 1440 宽 x 2560 高 |
| Google Pixel 2 | 411 宽 x 731 高 | 1080 宽 x 1920 高 |
| Google Pixel 2 XL | 411 宽 x 823 高 | 1440 宽 x 2880 高 |
| Samsung Galaxy Note 5 | 480 宽 x 853 高 | 1440 宽 x 2560 高 |
| LG G5 | 480 宽 x 853 高 | 1440 宽 x 2560 高 |
| One Plus 3 | 480 宽 x 853 高 | 1080 宽 x 1920 高 |
| Samsung Galaxy S9 | 360 宽 x 740 高 | 1440 宽 x 2960 高 |
| Samsung Galaxy S9+ | 360 宽 x 740 高 | 1440 宽 x 2960 高 |
| Samsung Galaxy S8 | 360 宽 x 740 高 | 1440 宽 x 2960 高 |
| Samsung Galaxy S8+ | 360 宽 x 740 高 | 1440 宽 x 2960 高 |
| Samsung Galaxy S7 | 360 宽 x 640 高 | 1440 宽 x 2560 高 |
| Samsung Galaxy S7 Edge | 360 宽 x 640 高 | 1440 宽 x 2560 高 |
| Nexus 7 (2013) | 600 宽 x 960 高 | 1200 宽 x 1920 高 |
| Nexus 9 | 768 宽 x 1024 高 | 1536 宽 x 2048 高 |
| Samsung Galaxy Tab 10 | 800 宽 x 1280 高 | 800 宽 x 1280 高 |
| Chromebook Pixel | 1280 宽 x 850 高 | 2560 宽 x 1700 高 |

如果您想要将活动交付到某一特定设备上的用户，请在活动图中选择适合该设备的受众。使用移动设备 Web 编辑器可在该设备上编辑活动页面。如果您想要在整个数字体验中运行某个活动，并确保该活动在所有设备上都展现良好的外观，请不要应用定位，而是使用移动设备视区按各种屏幕大小预览该活动。

如果您有一个响应式网站，您的网站通常会设计为当使用具有特定屏幕大小的设备访问时以不同的视图打开。这些可触发新视图的屏幕大小称为“CSS 断点”。CSS断点是网站内容根据设备宽度做出响应的点，可向访客显示最佳布局。 CSS断点也称为媒 [体查询](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)。

Save your CSS breakpoints in [!DNL Target] so you can preview your experiences for each view you define. Each of these experiences is displayed in a mobile viewport in the [!DNL Target] interface. 单击显示屏顶部的相应视区，即可打开每个屏幕大小所对应的视图。

如果您的网站不是响应式网站，您仍然可以使用移动设备 Web 编辑器查看网站，但前提是您的活动已定位到某个特定设备。

>[!IMPORTANT]
>
>虽然可以从移动视区中编辑体验，但这些更改适用于所有视区和设备，而不仅适用于您正在使用的视区。 同样，在常规桌面视图中编辑体验时，所有屏幕大小的页面均会发生相应的更改，而不仅仅是桌面视图中的页面。当前，我们尚不支持进行特定于视区的页面更改。

## Mobile viewport configuration {#task_B4B161499DC0470584ED922A4D20FCAB}

可配置您希望在创建体验时可供使用的任何移动设备视区。

1. 单击 **[!UICONTROL “管理]** ”> **[!UICONTROL “可视体验书写器]**”。
1. 要添加新的移动视区，请在“移动视 **[!UICONTROL 区”配置部分]** ，单击“ **[!UICONTROL 添加”]**。

   ![添加视区](/help/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   To change the configuration of an existing mobile viewport, select that viewport, then click the [!UICONTROL Edit] (pencil) icon.

1. 键入移动设备视区的名称。

   为移动设备视区键入一个便于识别的描述性名称。名称最长可包含 36 个字符。

1. 输入移动设备的屏幕大小，包括宽度和高度。

   宽度可以介于 150 到 968 像素之间。高度可以介于 150 到 1280 像素之间。

1. （可选）选择设备的操作系统。

   选项：

   * Android
   * iOS
   * Windows
   * Symbian
   * Blackberry

   如果您使用[增强型体验编辑器](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D)，并选择了一种操作系统，则 会在您查看页面时模拟该设备。[!DNL Target]If, for example, there is a different look and feel for Android than iOS on your responsive site, [!DNL Target] mimics that behavior.

1. 单击&#x200B;**[!UICONTROL 保存]**。

## Create a responsive experience {#task_D6332438B5EE48CCA8AF199270F1CAEF}

Add mobile viewports to your [!DNL Target] activities to create responsive experiences for mobile screens.

1. 创建所 [需活动](/help/c-activities/activities.md)。
1. 在可视化体验编辑器中，单击&#x200B;**[!UICONTROL 设置]**&#x200B;齿轮图标，然后选择&#x200B;**[!UICONTROL 添加移动设备视区]**。

   ![添加Mobile Viewports选项](/help/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. 单击&#x200B;**[!UICONTROL 设备]**&#x200B;图标，然后启用每个应具有移动设备视区的设备。

   ![启用移动视区](/help/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   移动设备视区将按宽度以从小到大的顺序排列。

1. 根据需要编辑移动设备视区。

   对体验做出的任何更改（例如，如果您更改了标题中的文本）会应用到所有设备上的体验。

   将鼠标悬停在视区名称上，以查看视区大小。

   ![iPhone 11 Pro Max响应式体验](/help/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. 如果需要，可通过单击所需的方向图标在纵向和横向模式之间切换。

   ![方向选项](/help/c-experiences/c-visual-experience-composer/assets/orientation.png)

## Use Case: Target two iPhone versions {#task_CC3144BF5BA54034996E1D3DB0BC1A35}

此用例说明如何为两个iPhone版本配置体验：iPhone 11 Pro Max和iPhone SE。

1. 在目标中，单击 **[!UICONTROL 管理]**。
1. 在“移 **[!UICONTROL 动视图端口配置]** ”部分，为iPhone 11 Pro Max和iPhone SE创建移动视图端口。

   对每个视区使用以下设置：

   | 名称 | 宽度 | 高度 | 操作系统 |
   |---|---|---|---|
   | iPhone 11 Pro Max | 414 | 896 | iOS |
   | iPhone SE | 375 | 667 | iOS |

   ![](assets/iphoneviewportconfig.png)

1. 创建具有您想要活动的体验的目标。
1. 选择您要目标给从iPhone 11 Pro Max或iPhone SE访问您网站的访客的体验。
1. 选择目标后，单击&#x200B;**[!UICONTROL 创建受众]**，然后配置受众（如下图所示）：

   ![](assets/iphoneaudiences.png)

   由于手机可以旋转到横向，要求高度和宽度同时大于320，因此，在与iPhone设备型号结合使用时，只有iPhone 11 Pro Max和iPhone SE才能满足这一条件。
1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 按常规方式继续设置活动。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 可视化体验编辑器（第 2 个，共 2 个）(7:29) ![概述徽章](/help/assets/overview.png)

以下演示视频包含有关通过可视化体验编辑器使用移动设备视区的信息：

* 重命名和复制体验
* 创建重定向体验
* 将活动定位到单个 URL 或一组 URL
* 创建多页面活动
* 预览和构建响应式网站的体验
* 使用叠加高亮显示元素类型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Adobe Target概述徽章中的 ![帐户首选项](/help/assets/overview.png)

此视频包含有关设置移动视口的信息，从视频的4:40开始。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
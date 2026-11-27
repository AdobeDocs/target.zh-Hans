---
keywords: 响应式;移动视区;视区;设备;移动;响应式网页设计;rwd
description: 移动视区可帮助您了解Adobe [!DNL Target]活动在各种大小的Screens上的观感。 查找常用设备视区大小和分辨率的列表。
title: 如何将移动视区用于响应式体验？
feature: Visual Experience Composer (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
TQID: 'https://experienceleague.adobe.com/uBJtaoaCh28mRGwc-SlK-XhU6sOIK3RaT58-ZXxSsHw'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 19%
---
# 移动视区用于响应式体验 {#mobile-viewports}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何配置移动视区，并使用它们预览和构建各种大小屏幕的体验。

>[!ENDSHADEBOX]

移动设备视区以各种设备的屏幕大小显示[!DNL Adobe Target]活动。 它们专为响应式网站而设计，可自动适应台式机、笔记本电脑、平板电脑和手机，并可以检查体验是否在每个网站上都呈现良好。

>[!NOTE]
>
> * 当网站为响应式，且移动设备页面以不同的布局重用桌面页面元素时，可使用移动设备视区。 如果移动设备网站是独立的，并且有自己的结构（如`m.mysite.com`），请改用[多页面活动](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#multipage-activity)。
>
>* 当重定向选件叠加与移动视区重叠时，移动视区将不可用。

## 视区和CSS断点

视区是网页填充的屏幕区域：浏览器窗口的大小减去滚动条和工具栏。 浏览器以CSS像素来测量视区，因此在许多设备（例如那些带有视网膜屏幕的设备）上，视区小于广告的设备分辨率。 始终使用[!DNL Target]中的视区大小。 下表列出了常用设备的这两个值。

+++ 常用设备的视区和分辨率

>[!NOTE]
>
>许多网站列出常用设备的视区大小。 例如，请参阅 `https://viewportsizer.com/devices/`。 有关最准确和最新的信息，请参考设备制造商的网站。
>
>标记为“est”的视区大小。 是估计值。

| 设备 | 视区大小（宽度x高度） | 设备分辨率（宽度 x 高度） |
|---|---|---|
| iPhone 18 Pro Max | 440 x 956 | 1320 x 2868 |
| iPhone 18 Pro | 402 x 874 | 1206 x 2622 |
| iPhone 17 Pro Max | 440 x 956 | 1320 x 2868 |
| iPhone 17 Pro | 402 x 874 | 1206 x 2622 |
| iPhone航空 | 420 x 912 | 1260 x 2736 |
| iPhone 17 | 402 x 874 | 1206 x 2622 |
| iPhone 16e | 390 x 844 | 1170 x 2532 |
| iPad (A16) | 820 x 1180 | 1640 x 2360 |
| iPad mini (A17 Pro) | 744 x 1133 | 1488 x 2266 |
| iPad航空11英寸(M3/M4) | 820 x 1180 | 1640 x 2360 |
| iPad Pro 11英寸(M5) | 834 x 1210 | 1668 x 2420 |
| Google Pixel 11 | 412 x 924 （东部标准时间） | 1080 x 2424 |
| Google Pixel 11 Pro | 410 x 914（东部标准时间） | 1280 x 2856 |
| Google Pixel 11 Pro XL | 448 x 997（东部标准时间） | 1344 x 2992 |
| Google Pixel 10 | 412 x 924 | 1080 x 2424 |
| Google Pixel 10 Pro | 410 x 914（东部标准时间） | 1280 x 2856 |
| Google Pixel 10 Pro XL | 448 x 997（东部标准时间） | 1344 x 2992 |
| Samsung Galaxy S26 | 360 x 780 | 1080 x 2340 |
| Samsung Galaxy S26 Ultra | 412 x 891 | 1440 x 3120 |
| iPhone Duo（已展开） | 890 x 626（东部标准时间） | 2670 x 1878 |
| iPhone Duo（折叠） | 466 x 678 （东部标准时间） | 1398 x 2034 |
| Samsung Galaxy Z Fold 7（折叠） | 412 x 960（东部标准时间） | 1080 x 2520 |
| Samsung Galaxy Z Flip 8 | 360 x 840（东部标准时间） | 1080 x 2520 |
| Google Pixel 11 Pro Fold（展开） | 791 x 820（东部标准时间） | 2076 x 2152 |

+++

响应式网站以特定屏幕大小切换到不同的布局。 这些大小称为CSS断点或[媒体查询](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)。 将站点的CSS断点保存在[!DNL Target]中可以预览每个视图，单击显示顶部的视区将打开相应屏幕大小的视图。

要将活动交付给特定设备，请在活动图中选择该设备的受众，然后在移动Web编辑器中编辑该设备的页面。 当活动定位到特定设备时，同一工具可用于查看无响应的网站。 要在所有设备上运行活动，请应用“无定位”并使用移动视区预览每个屏幕大小的活动。

>[!IMPORTANT]
>
>可以从移动设备视区中编辑体验，但所做更改会应用到所有视区和设备，而不仅仅应用到正在使用的视区。 同样，在桌面视图中编辑体验会更改所有屏幕大小的页面。 [!DNL Target]当前不支持特定于视区的页面更改。

## 移动视区配置 {#task_B4B161499DC0470584ED922A4D20FCAB}

定义创建体验时可用的移动设备视区。

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**。
1. 在&#x200B;**[!UICONTROL 移动设备视区配置]**&#x200B;部分中，单击&#x200B;**[!UICONTROL 添加]**。

   ![添加视区](/help/main/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   或

   要更改现有移动设备视区的配置，请选择该视区，然后单击&#x200B;**[!UICONTROL 编辑]**（铅笔）图标。

1. 键入移动设备视区的描述性名称。 名称最长可包含 36 个字符。
1. 输入移动设备的屏幕大小。 宽度可以在150到968像素之间，高度可以在150到1280像素之间。
1. （可选）选择设备的操作系统。

   选项：

   * Android
   * iOS
   * Windows
   * Symbian
   * Blackberry

   如果启用了[增强型体验编辑器](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#enable-eec)并且选择了操作系统，则[!DNL Target]在查看页面时模拟该设备。 例如，如果响应式网站对于Android的外观与iOS的外观不同，则[!DNL Target]模拟该行为。

1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>
>尝试删除正在使用的移动设备视区会显示以下消息：“此视区当前关联到一个或多个活动。 需要从这些活动中去除此视区后才能删除它。”

## 创建响应式体验 {#task_D6332438B5EE48CCA8AF199270F1CAEF}

将移动视区添加到[!DNL Target]活动以创建用于移动设备的响应式体验。

1. 创建[所需活动](/help/main/c-activities/activities.md)。
1. 在&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)中，单击&#x200B;**[!UICONTROL 设置]**&#x200B;齿轮图标，然后选择&#x200B;**[!UICONTROL 添加移动设备视区]**。

   ![添加移动视区选项](/help/main/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. 单击&#x200B;**[!UICONTROL 设备]**&#x200B;图标，然后启用每个应有移动视区的设备。

   ![启用移动视区](/help/main/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   移动设备视区将按宽度以从小到大的顺序排列。

1. 根据需要编辑移动视区中的体验。 任何更改都适用于所有设备上的体验，例如更改标题的文本。 将鼠标悬停在视区的名称上可查看该视区的大小。

   ![iPhone 11 Pro Max 响应式体验](/help/main/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. （可选）通过单击方向图标，在纵向和横向模式之间切换。

   ![方向选项](/help/main/c-experiences/c-visual-experience-composer/assets/orientation.png)

## 培训视频

以下视频包含有关移动设备视区的更多信息。

### 可视化体验编辑器（第2个，共2个）(7:29) ![概述徽章](/help/main/assets/overview.png)

以下演示视频包含有关如何使用可视化体验编辑器处理移动视区的信息：

* 重命名和复制体验
* 创建重定向体验
* 将活动定位到单个 URL 或一组 URL
* 创建多页面活动
* 预览和构建响应式网站的体验
* 使用叠加高亮显示元素类型

>[!VIDEO](https://video.tv.adobe.com/v/30330?captions=chi_hans)

### Adobe Target 中的帐户首选项 ![“概述”标记](/help/main/assets/overview.png)

本视频从4:40开始介绍设置移动视区。

>[!VIDEO](https://video.tv.adobe.com/v/3507633?captions=chi_hans)

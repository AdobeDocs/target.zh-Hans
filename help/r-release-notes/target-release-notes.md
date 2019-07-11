---
description: 这些发行说明提供有关最新或即将推出的[！DNL Adobe Target]版本。
keywords: 发行说明
seo-description: 这些发行说明提供有关最新或即将推出的[！DNL Adobe Target]版本。
seo-title: Adobe Target发行说明(预发行版)
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 7cdff6e1beca45a4900090bc91a38be7e000f289

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新日期：2019 年 7 月 11 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发行日期、功能和其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1（2019 年 7 月 23 日）{#tgt-19-7-1}

此版本包括以下新增功能和增强功能：

| 功能 / 增强功能 | 描述 |
| --- | --- |
| 可视化体验编辑器 (VEC) | When you click an image then click [!UICONTROL Replace With], two new options display:<ul><li>**HTML**：您可以使用HTML替换图像，以使您完全控制元素，而无需选择父元素来访问HTML选项。</li><li>**体验片段**：您可以使用Adobe Experience Manager(AEM) [体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md) 替换图像，以便快速插入AEM中在Target活动中创建的元素。</li></ul>(TGT-34097) |
| 移动设备应用程序可视化体验编辑器 | 移动App CMS中会显示一个新的修改面板，它显示您设置的用于单击跟踪的元素。(TGT-31741) |
| ![Premium BadgereComments](/help/assets/premium.png)<br>A/B测试和体验定位(XT)活动 | 推荐选项(算法)状态显示在包含Recommendations选件的A/B Test和XT活动的概述页面上。状态包括：结果就绪、结果未准备好和源失败。(TGT-33649) |
| 通过Experience Cloud ID(ECID)库对. js2.0+进行跨域跟踪支持 | 以前，在. js中不支持跨域跟踪。*x* 目前不支持选择加入支持。在此版本中，使用. js2.0或更高版本的客户现在可以通过ECID库使用跨域跟踪。必须将ECID库与at. js2.0或更高版本一起安装在页面上，以便跨域跟踪工作。[必须使用Experience Cloud ID库4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 。 |
| 通过Experience Cloud ID(ECID)库4.3针对Apple的ITP2.1和ITP2.2提供支持 | 如今，Target客户可以通过利用Adobe的CNAME认证计划减轻Apple的ITP2.1和ITP2.2。With this release, Target introduces a seamless integration with the ECID library 4.3, which leverages a server-side cookie to mitigate ITP 2.1 and ITP 2.2. It is highly recommended that Target customers deploy [ECID library 4.3+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) in conjunction with Target’s JavaScript library to mitigate any future ITP releases. EID库将继续推出增强功能，为浏览器引入的不断变化的cookie策略提供强大的解决方案。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要收到有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的高级通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

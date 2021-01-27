---
keywords: content;assets;manage content;offers;manage assets;enter selection mode;selection mode
description: 如何管理代码和图像优惠?
title: 选件
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 70547a05155aa2909b0e66a1f26b0fd2cc730dd9
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 40%

---


# 选件

使用[!DNL Adobe Target]中的[!UICONTROL 优惠]库管理代码优惠和图像优惠内容。

1. 单击&#x200B;**[!UICONTROL 选件]**&#x200B;可打开选件库。

   选件库中包含通过 [!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS) 及 API 设置的选件。在 [!DNL Target Classic] 或其他解决方案中创建的选件可以在 [!DNL Target Standard/Premium] 中进行编辑。

   [!UICONTROL 优惠]页面右侧有两个选项卡：[!UICONTROL 代码优惠]和[!UICONTROL 图像优惠]，可让您按类型视图优惠。

   ![优惠页，显示代码优惠和图像优惠选项卡](/help/c-experiences/c-manage-content/assets/offers-page.png)

1. （可选）单击&#x200B;**[!UICONTROL Type]**&#x200B;下拉列表按类型筛选优惠(HTML优惠、[体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)、[重定向优惠](/help/c-experiences/c-manage-content/offer-redirect.md)、[远程优惠](/help/c-experiences/c-manage-content/about-remote-offers.md)、[JSON优惠](/help/c-experiences/c-manage-content/create-json-offer.md)和&lt;json>a10/>文件夹](/help/c-experiences/c-manage-content/create-content-folder.md))。[

   ![](assets/offers_filter.png)

1. （可选）单击&#x200B;**[!UICONTROL 源]**&#x200B;下拉列表，按源(Adobe Target、Adobe Target经典和Adobe Experience Manager)筛选优惠。

1. （可选）将指针悬停在[!UICONTROL 代码任务]选项卡上所需优惠或文件夹上，然后单击所需图标，即可执行其他优惠。

   ![代码选件选项](assets/offer-picker-large.png)

   选项包括：

   * 视图(有关详细信息，请参阅下面的[查看优惠定义](#section_6B059DD121434E6292CAB393507D010E)。)
   * 编辑
   * 复制
   * 移动（例如，要将一个或多个项目移入文件夹，请单击所需项目的&#x200B;**[!UICONTROL 移动]**&#x200B;图标，单击所需文件夹，然后单击&#x200B;**[!UICONTROL 拖放]**。）
   * 删除

   根据您的权限，您可能看不到所有选项的图标。 例如，具有[!UICONTROL Observer]权限的用户无权使用[!UICONTROL Copy]选项。

1. （可选）将鼠标悬停在[!UICONTROL 图像任务]选项卡上所需的图像优惠或文件夹上，然后单击所需的图标，可执行其他优惠。

   ![图像选件选项](/help/c-experiences/c-manage-content/assets/image-offers-icons.png)

   选项包括：

   * 选择
   * 下载
   * 查看属性
   * 编辑
   * 注释
   * 复制

## 查看优惠定义{#section_6B059DD121434E6292CAB393507D010E}

您可以视图[!UICONTROL 优惠]库中弹出卡上的优惠定义详细信息，而无需打开优惠。

例如，将鼠标悬停在[!UICONTROL Content]优惠上的优惠上，然后单击信息图标，可访问HTML优惠的以下列表定义卡：

![](assets/offer-card-html.png)

其中提供了以下信息：

* 名称
* 来源
* 类型
* 选件 ID
* 选件路径
* 上次修改时间

在每个选件的定义弹出卡片中单击“[!UICONTROL 选件使用情况]”选项卡，可查看引用了代码选件的活动。此功能不适用于图像选件。利用此功能，您可以避免在编辑选件时对其他活动造成影响。信息包括[!UICONTROL 活动活动]和[!UICONTROL 非活动活动]。

![](assets/offer-card-usage.png)

下面是一个重定向选件的定义卡片：

![](assets/offer-card-redirect.png)

其中提供了以下信息：

* 名称
* 来源
* 类型
* 选件 ID
* 选件路径
* 上次修改时间
* 重定向 URL
* 包括所有URL参数（开或关）
* 传递mbox会话ID（开或关）

下面是一个远程选件的定义卡片：

![](assets/offer-card-remote.png)

其中提供了以下信息：

* 名称
* 来源
* 类型
* 选件 ID
* 选件路径
* 上次修改时间
* 重定向 URL 类型
* 绝对或相对 URL

## 培训视频：内容存储库  ![概述徽章](/help/assets/overview.png)

以下视频包含有关管理选件的信息。

* [Experience Cloud 资产库](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html)与 Target 内容库之间的关联
* 自定义 HTML 选件
* 可视化体验编辑器中的自定义 HTML 选件

>[!VIDEO](https://video.tv.adobe.com/v/17387)
---
keywords: 内容;资产;管理内容;选件;管理资产;进入选择模式;选择模式
description: 了解如何使用Adobe Target中的选件库来管理代码和图像选件。
title: 如何管理代码和图像选件？
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: be59e8ccbf12f7b3cc42becc36a8b3c7474f2f9e
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 36%

---

# 选件

使用 [!UICONTROL 选件] 库位于 [!DNL Adobe Target] 以管理代码选件和图像选件内容。

1. 单击&#x200B;**[!UICONTROL 选件]**&#x200B;可打开选件库。

   选件库中包含通过 [!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS) 及 API 设置的选件。在 [!DNL Target Classic] 或其他解决方案中创建的选件可以在 [!DNL Target Standard/Premium] 中进行编辑。

   此 [!UICONTROL 选件] 页面右侧有两个选项卡： [!UICONTROL 代码选件] 和 [!UICONTROL 图像选件] 允许您按类型查看选件。

   ![“选件”页面显示“代码选件”和“图像选件”选项卡](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. （可选）单击 **[!UICONTROL 类型]** 下拉列表，可按类型过滤选件(HTML选件， [体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)， [重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)， [远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)， [json选件](/help/main/c-experiences/c-manage-content/create-json-offer.md)、和 [文件夹](/help/main/c-experiences/c-manage-content/create-content-folder.md))。

   ![offers_filter图像](assets/offers_filter.png)

1. （可选）单击 **[!UICONTROL 来源]** 下拉列表，可按源(Adobe Target、Adobe Target Classic和Adobe Experience Manager)过滤选件。

1. （可选）将鼠标悬停在 [!UICONTROL 代码选件] 选项卡，然后单击所需的图标。

   ![代码选件选项](assets/offer-picker-large.png)

   选项包括：

   * 查看(有关更多信息，请参阅 [查看选件定义](#section_6B059DD121434E6292CAB393507D010E) 下。)
   * 编辑
   * 复制
   * 移动(例如，要将一个或多个项目移动到文件夹中，请单击 **[!UICONTROL 移动]** 图标，单击所需的文件夹，然后单击 **[!UICONTROL 放置]**.)
   * 删除

   根据您的权限，您可能不会看到所有选项的图标。 例如，用户具有 [!UICONTROL 观察者] 权限无权使用 [!UICONTROL 复制] 选项。

   有关可对选件和文件夹执行的任务的详细信息，请参阅 [处理资产库中的内容](/help/main/c-experiences/c-manage-content/assets-working.md).

1. （可选）将鼠标悬停在页面上所需的图像选件或文件夹上，以执行其他任务。 [!UICONTROL 图像选件] 选项卡，然后单击所需的图标。

   ![图像选件选项](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   选项包括：

   * 选择
   * 下载
   * 查看属性
   * 编辑
   * 注释
   * 复制

   有关可对选件和文件夹执行的任务的详细信息，请参阅 [处理资产库中的内容](/help/main/c-experiences/c-manage-content/assets-working.md).

   >[!NOTE]
   >
   >图像选件不属于 [企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 模型。


## 查看选件定义 {#section_6B059DD121434E6292CAB393507D010E}

您可以在中的弹出卡片上查看优惠定义详细信息 [!UICONTROL 选件] 库，而不打开选件。

例如，通过将鼠标悬停在上的选件上，访问HTML选件的以下选件定义卡 [!UICONTROL 内容] 列表，然后单击信息图标：

![offer-card-html图像](assets/offer-card-html.png)

其中提供了以下信息：

* 名称
* 来源
* 类型
* 选件 ID
* 选件路径
* 上次修改时间

在每个选件的定义弹出卡片中单击“[!UICONTROL 选件使用情况]”选项卡，可查看引用了代码选件的活动。此功能不适用于图像选件。利用此功能，您可以避免在编辑选件时对其他活动造成影响。信息包括 [!UICONTROL 实时活动] 和 [!UICONTROL 不活跃的活动].

![优惠卡使用情况图像](assets/offer-card-usage.png)

下面是一个重定向选件的定义卡片：

![offer-card-redirect图像](assets/offer-card-redirect.png)

其中提供了以下信息：

* 名称
* 来源
* 类型
* 选件 ID
* 选件路径
* 上次修改时间
* 重定向 URL
* 包含所有URL参数（打开或关闭）
* 传递mbox会话ID（打开或关闭）

下面是一个远程选件的定义卡片：

![优惠卡远程图像](assets/offer-card-remote.png)

其中提供了以下信息：

* 名称
* 来源
* 类型
* 选件 ID
* 选件路径
* 上次修改时间
* 重定向 URL 类型
* 绝对或相对 URL

## 培训视频：内容存储库 ![“概述”标记](/help/main/assets/overview.png)

以下视频包含有关管理选件的信息。

* [Experience Cloud 资产库](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html)与 Target 内容库之间的关联
* 自定义 HTML 选件
* 可视化体验编辑器中的自定义 HTML 选件

>[!VIDEO](https://video.tv.adobe.com/v/17387)

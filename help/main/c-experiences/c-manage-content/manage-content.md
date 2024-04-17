---
keywords: 内容;资产;管理内容;选件;管理资产;进入选择模式;选择模式
description: 了解如何使用Adobe Target中的选件库来管理代码和图像选件。
title: 如何管理代码和图像选件？
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f93e33e91fb7be9c0d1772a2014864b46c1dfe47
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# 选件

使用 [!UICONTROL Offers] 库位于 [!DNL Adobe Target] 以管理代码选件和图像选件内容。

1. 单击 **[!UICONTROL Offers]** 以打开库。

   选件库中包含通过 [!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS) 及 API 设置的选件。在 [!DNL Target Classic] 或其他解决方案中创建的选件可以在 [!DNL Target Standard/Premium] 中进行编辑。

   此 [!UICONTROL Offers] 页面右侧有两个选项卡： [!UICONTROL Code Offers] 和 [!UICONTROL Image Offers] 允许您按类型查看选件。

   ![“选件”页面显示“代码选件”和“图像选件”选项卡](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. （可选）单击 **[!UICONTROL Type]** 下拉列表，可按类型过滤选件(HTML选件， [体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)， [重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)， [远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)， [json选件](/help/main/c-experiences/c-manage-content/create-json-offer.md)、和 [文件夹](/help/main/c-experiences/c-manage-content/create-content-folder.md))。

   ![offers_filter图像](assets/offers_filter.png)

1. （可选）单击 **[!UICONTROL Source]** 下拉列表，可按源(Adobe Target、Adobe Target Classic和Adobe Experience Manager)过滤选件。

1. （可选）将鼠标悬停在 [!UICONTROL Code Offers] 选项卡，然后单击所需的图标。

   ![代码选件选项](assets/offer-picker-large.png)

   选项包括：

   * 查看(有关更多信息，请参阅 [查看选件定义](#section_6B059DD121434E6292CAB393507D010E) 下。)
   * 编辑
   * 复制
   * 移动(例如，要将一个或多个项目移动到文件夹中，请单击 **[!UICONTROL Move]** 图标，单击所需的文件夹，然后单击 **[!UICONTROL Drop]**.)
   * 删除

   根据您的权限，您可能不会看到所有选项的图标。 例如，用户具有 [!UICONTROL Observer] 权限无权使用 [!UICONTROL Copy] 选项。

   有关可对选件和文件夹执行的任务的详细信息，请参阅 [处理资产库中的内容](/help/main/c-experiences/c-manage-content/assets-working.md).

1. （可选）将鼠标悬停在页面上所需的图像选件或文件夹上，以执行其他任务。 [!UICONTROL Image Offers] 选项卡，然后单击所需的图标。

   ![“图像选件”选项](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

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

您可以在中的弹出卡片上查看优惠定义详细信息 [!UICONTROL Offers] 库，而不打开选件。

例如，通过单击信息图标，可访问HTML选件的以下选件定义卡片：

![offer-card-html图像](assets/offer-card-html-new.png)

其中提供了以下信息：

* 名称
* 选件 ID
* 类型
* 上次修改时间

单击 [!UICONTROL View Full Details] 查看选件内容和引用代码选件的活动的链接。 利用此功能，您可以避免在编辑选件时对其他活动造成影响。信息包括 [!UICONTROL Live Activities] 和 [!UICONTROL Inactive Activities].

每个卡上的可用信息因选件类型而异：HTML选件， [体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)， [重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)， [远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)，或 [json选件](/help/main/c-experiences/c-manage-content/create-json-offer.md).

优惠详细信息功能不适用于图像优惠。

<!--

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the [!UICONTROL Visual Experience Composer]

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->

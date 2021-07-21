---
keywords: 受众;受众规则;创建受众;定位受众;报表受众;区段;自定义配置文件参数;受众定义;受众列表
description: 了解如何使用 [!DNL Adobe Target]中的[!UICONTROL Audiences]列表。
title: 如何使用受众列表？
feature: 受众
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: f7d73de376c2345b628e3ebadb1d4ab4dc598693
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 31%

---

# 创建受众

[!DNL Adobe Target]中的受众可确定在目标活动中看到内容和体验的受众。

不论在何处，只要可以使用定位，便会用到受众。定位活动时，您可以选择以下选项：

* 从[!UICONTROL 受众]列表中选择可重复使用的受众
* [创建特定于活动的受](/help/c-target/creating-activity-only-audience.md) 众并将其定位
* [合并多](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) 个受众以创建临时受众

您还可以使用由[!DNL Adobe Analytics]收集的受众数据在[!DNL Target]和其他[!DNL Adobe Experience Cloud]应用程序中进行实时定位和个性化。 请参阅&#x200B;*Experience Cloud中心界面组件*&#x200B;指南中的[Experience Cloud受众](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html??lang=zh-Hans)。

[!DNL Target]中有两种类型的受众：

* **定位受众：** 用于向不同类型的访客交付不同的内容。
* **报表受众：** 用于确定不同类型的访客对同一内容有何响应，以便您能够分析测试结果。

   在 [!DNL Target] 中，仅当使用 [!DNL Target] 作为报表源时，才能配置报表受众。如果您使用 [ Adobe Analytics 作为报表源](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，则必须在 [!DNL Analytics] 中配置报表受众。

## 使用[!UICONTROL Audiences]列表

要访问“[!UICONTROL 受众]”列表，请单击顶部菜单栏中的&#x200B;**[!UICONTROL 受众]**：

![“受众”列表](assets/audiences_list.png)

[!UICONTROL 受众]列表包含可在活动中使用的受众。 使用[!UICONTROL 受众]列表可创建、编辑、复制、复制或合并受众。 该列表还显示创建受众的源：

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform]源位于测试版测试程序中，但可供使用[Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)的所有[!DNL Target]客户使用。 [!DNL Adobe Experience Platform]中可用的受众可以按原样使用，也可以与现有受众](/help/c-target/combining-multiple-audiences.md)组合使用[。

无法重命名预定义受众，如“[!UICONTROL 新访客]”和“[!UICONTROL 旧访客]”。

使用最初在[!DNL Experience Cloud]或[!DNL Adobe Experience Platform]中创建的受众时，如果您在[!DNL Target]活动中引用了稍后在[!DNL Experience Cloud]或[!DNL Adobe Experience Platform]中删除的受众，则会向您发出警报。[!DNL Target]

* 如果在[!DNL Experience Cloud]或[!DNL Adobe Experience Platform]中删除了受众，则[!UICONTROL 受众]列表和受众选取器中都会显示警告图标。 [!DNL Target] UI中的工具提示还指示受众已在[!DNL Experience Cloud]或[!DNL Adobe Experience Platform]中删除。
* 如果您尝试将多个受众与已删除的受众合并，或者您想保存引用了已删除受众的活动，则会显示一条警告消息。

您还可以定位自定义配置文件参数和 `user.` 参数。创建受众时，将要用于定位活动的属性拖到受众生成器窗口中。 如果未显示所需的属性，则表示该属性未被mbox触发。 “[!UICONTROL 自定义参数]”下拉列表中提供了其他自定义 mbox 参数。

使用[!UICONTROL Filters]按钮按源筛选[!UICONTROL Audiences]列表：[!DNL Adobe Target]、[!DNL Adobe Target Classic]、[!DNL Experience Cloud]和[!DNL Adobe Experience Platform]。

![受众列表中的过滤器  选项](assets/filters.png)

使用[!UICONTROL 搜索受众]框可搜索[!UICONTROL 受众]列表。 您可以搜索受众名称的任意部分，或将特定字符串用引号引住。

您可以按受众名称或上次修改日期对“[!UICONTROL 受众]”列表进行排序。要按名称或上次修改日期进行排序，请单击列标头，然后选择受众显示的顺序（升序或降序）。

## 查看受众定义 {#section_11B9C4A777E14D36BA1E925021945780}

您可以在[!DNL Target] UI中的各个位置通过弹出卡片查看受众定义详细信息，而无需打开受众。 此功能适用于在[!DNL Target Standard/Premium]中创建的受众，以及从[!DNL Target Classic]导入或通过API创建的受众。

例如，通过单击所需受众的[!UICONTROL 查看详细信息]图标，可访问以下受众定义卡片：

![活动 > 受众定义](assets/audience_definition_list.png)

单击活动[!UICONTROL 概述]页面上的[!UICONTROL 查看详细信息]图标，可访问以下受众定义卡片：

![活动 > 受众定义](assets/view-details-activity-overview.png)

受众定义卡片显示了受众的类型、来源和属性。 单击&#x200B;**[!UICONTROL 查看完整详细信息]**，以查看引用该受众的其他活动（如果适用）。 如果您要从活动的[!UICONTROL 概述]页面中查看受众定义卡片，请单击&#x200B;**[!UICONTROL 受众使用情况]**。

受众使用信息可帮助您避免在编辑受众时对其他活动造成意外影响。 该信息包括[!UICONTROL 实时活动]、[!UICONTROL 不活动活动]、[!UICONTROL 已存档活动]和[!UICONTROL 正在同步活动]。 此功能适用于所有受众（库受众和[仅限该活动的受众](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)）。

如果某个受众与其他受众[组合，并且该组合受众用于创建活动，则这两个受众的使用信息会列出新创建的活动。](/help/c-target/combining-multiple-audiences.md)

![](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## 培训视频：使用受众![教程徽章](/help/assets/tutorial.png)

以下视频包含有关使用受众的信息。

* 解释术语“受众”
* 介绍使用受众进行优化的两种方式
* 在“受众”列表中查找受众
* 将活动定位到受众
* 在活动中使用受众进行被动报告

>[!VIDEO](https://video.tv.adobe.com/v/17398)

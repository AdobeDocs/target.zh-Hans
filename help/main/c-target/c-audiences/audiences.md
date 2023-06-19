---
keywords: 受众;受众规则;创建受众;定位受众;报表受众;区段;自定义配置文件参数;受众定义;受众列表
description: 了解如何在中使用受众 [!DNL Adobe Target].
title: 如何使用受众列表？
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 351ed1e51b0a253476c6cda456781351333e8da5
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 32%

---

# 创建受众

中的受众 [!DNL Adobe Target] 确定可在定向活动中看到内容和体验的用户。

不论在何处，只要可以使用定位，便会用到受众。在定位活动时，您具有以下选项：

* 从中选择可重复使用的受众 [!UICONTROL 受众] 列表
* [创建特定于活动的受众](/help/main/c-target/creating-activity-only-audience.md) 并将其定位
* [合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) 创建临时受众

您还可以使用收集的受众数据 [!DNL Adobe Analytics] 在中实现实时定位和个性化 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 应用程序。 参见 [Experience Cloud受众](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html??lang=zh-Hans) 在 *Experience Cloud中央界面组件* 指南。

中有两种类型的受众 [!DNL Target]：

* **定位受众：** 用于向不同类型的访客交付不同的内容。
* **报表受众：** 用于确定不同类型的访客对同一内容有何响应，以便您分析测试结果。

  在 [!DNL Target] 中，仅当使用 [!DNL Target] 作为报表源时，才能配置报表受众。如果您使用 [ Adobe Analytics 作为报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，则必须在 [!DNL Analytics] 中配置报表受众。

## 使用 [!UICONTROL 受众] 列表 {#use-list}

要访问“[!UICONTROL 受众]”列表，请单击顶部菜单栏中的&#x200B;**[!UICONTROL 受众]**：

![“受众”列表](assets/audiences_list.png)

此 [!UICONTROL 受众] 列表包含您可以在活动中使用的受众。 使用 [!UICONTROL 受众] 列表以创建、编辑、复制、复制或组合受众。 该列表还会显示创建受众的源位置：

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

  >[!NOTE]
  >
  >此 [!DNL Adobe Experience Platform] 源可供所有人使用 [!DNL Target] 客户使用 [Adobe Experience Platform Web SDK](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}. 受众可从 [!DNL Adobe Experience Platform] 可以按原样使用或 [与现有受众相结合](/help/main/c-target/combining-multiple-audiences.md).
  >
  >用户必须具有 [!UICONTROL 审批者] 或高于以下项中的状态 [!DNL Target] 配置 [!DNL Target] [!UICONTROL 目标] AEP/RTCDP中的卡([!DNL Real-time Customer Data Platform])。
  >
  >有关详细信息，请参阅 [使用来自Adobe Experience Platform的受众](#aep).

预定义受众，如&quot;[!UICONTROL 新访客]“ ”和“ ”[!UICONTROL 旧访客]不能重命名“ ”。

使用最初在中创建的受众时 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform]， [!DNL Target] 如果您在中引用受众，则会向您发出警报 [!DNL Target] 稍后在中删除的活动 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform].

* 如果受众删除于 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform]，中都会显示一个警告图标 [!UICONTROL Audience] 列表和受众选取器随即显示。 中的工具提示 [!DNL Target] UI还指示受众已删除于 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform].
* 如果您尝试将多个受众与已删除的受众合并，或者您想保存引用了已删除受众的活动，则会显示一条警告消息。

您还可以定位自定义配置文件参数和 `user.` 参数。创建受众时，请将要用于定位活动的属性拖到受众生成器窗口中。 如果未显示所需的属性，则该属性尚未被mbox触发。 “[!UICONTROL 自定义参数]”下拉列表中提供了其他自定义 mbox 参数。

使用 [!UICONTROL 筛选器] 按钮以筛选 [!UICONTROL 受众] 按源列出： [!DNL Adobe Target]， [!DNL Adobe Target Classic]， [!DNL Experience Cloud]、和 [!DNL Adobe Experience Platform].

![中的筛选器选项 [!UICONTROL 受众] 列表](assets/filters.png)

使用 [!UICONTROL 搜索受众] 框以搜索您的 [!UICONTROL 受众] 列表。 您可以搜索受众名称的任意部分，或将特定字符串用引号引住。

您可以按受众名称或上次修改日期对“[!UICONTROL 受众]”列表进行排序。要按名称或上次修改日期进行排序，请单击列标头，然后选择受众显示的顺序（升序或降序）。

## 查看受众定义 {#section_11B9C4A777E14D36BA1E925021945780}

您可以在中的各个位置通过弹出卡查看受众定义详细信息。 [!DNL Target] 不打开受众的UI。 此功能适用于在中创建的受众 [!DNL Target Standard/Premium] 和受众导入自 [!DNL Target Classic] 或通过API创建。

例如，通过单击 [!UICONTROL 查看详细信息] 图标来显示所需受众：

![活动 > 受众定义](assets/audience_definition_list.png)

通过单击 [!UICONTROL 查看详细信息] 活动图标 [!UICONTROL 概述] 页面：

![活动 > 受众定义](assets/view-details-activity-overview.png)

受众定义卡片可显示受众的类型、源和属性。 单击 **[!UICONTROL 查看完整详细信息]** 查看引用该受众的其他活动（如果适用）。 如果您查看的是活动中的受众定义卡片 [!UICONTROL 概述] 页面，单击 **[!UICONTROL 受众使用情况]**.

受众使用情况信息可帮助您在编辑受众时避免意外影响其他活动。 信息包括 [!UICONTROL 实时活动]， [!UICONTROL 不活跃的活动]， [!UICONTROL 已存档的活动]、和 [!UICONTROL 正在同步活动]. 此功能适用于所有受众(库受众和 [仅限该活动的受众](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483))。

如果受众为 [与其他受众相结合](/help/main/c-target/combining-multiple-audiences.md) 和组合受众用于创建活动，这两个受众的使用情况信息都列出了新创建的活动。

![audience_definition_list_usage图像](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/main/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/main/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/main/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/main/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## 使用来自 [!DNL Adobe Experience Platform] 的受众 {#aep}

使用在 [!DNL Adobe Experience Platform] 中创建的受众可提供更丰富的客户数据，从而带来更强大的个性化功能。 

有关更多信息，请参阅 [使用来自的受众 [!DNL Adobe Experience Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#aep).

## 培训视频：使用受众 ![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关使用受众的信息。

* 解释术语“受众”
* 介绍使用受众进行优化的两种方式
* 在“受众”列表中查找受众
* 将活动定位到受众
* 在活动中使用受众进行被动报告

>[!VIDEO](https://video.tv.adobe.com/v/17398)

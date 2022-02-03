---
keywords: 受众;受众规则;创建受众;定位受众;报表受众;区段;自定义配置文件参数;受众定义;受众列表
description: 了解如何在中使用受众 [!DNL Adobe Target].
title: 如何使用受众列表？
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 5d3e5a15a262d29bd1d95af71baae52ed288b33e
workflow-type: tm+mt
source-wordcount: '1203'
ht-degree: 24%

---

# 创建受众

受众 [!DNL Adobe Target] 确定在定位活动中看到内容和体验的人员。

不论在何处，只要可以使用定位，便会用到受众。定位活动时，您可以选择以下选项：

* 从 [!UICONTROL 受众] 列表
* [创建特定于活动的受众](/help/c-target/creating-activity-only-audience.md) 瞄准
* [合并多个受众](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) 创建临时受众

您还可以使用 [!DNL Adobe Analytics] ，以便在 [!DNL Target] 其他 [!DNL Adobe Experience Cloud] 应用程序。 请参阅 [Experience Cloud受众](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html??lang=zh-Hans) 在 *Experience Cloud中心界面组件* 的双曲余切值。

中有两种类型的受众 [!DNL Target]:

* **定位受众：** 用于向不同类型的访客交付不同的内容。
* **报表受众：** 用于确定不同类型的访客对同一内容有何响应，以便您分析测试结果。

   在 [!DNL Target] 中，仅当使用 [!DNL Target] 作为报表源时，才能配置报表受众。如果您使用 [ Adobe Analytics 作为报表源](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，则必须在 [!DNL Analytics] 中配置报表受众。

## 使用 [!UICONTROL 受众] 列表 {#use-list}

要访问“[!UICONTROL 受众]”列表，请单击顶部菜单栏中的&#x200B;**[!UICONTROL 受众]**：

![“受众”列表](assets/audiences_list.png)

的 [!UICONTROL 受众] 列表中包含可在活动中使用的受众。 使用 [!UICONTROL 受众] 列表创建、编辑、复制、复制或合并受众。 该列表还显示创建受众的源：

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >的 [!DNL Adobe Experience Platform] 源可供所有人使用 [!DNL Target] 使用 [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). 受众 [!DNL Adobe Experience Platform] 可以按原样使用，或 [与现有受众组合](/help/c-target/combining-multiple-audiences.md).
   >
   >用户必须 [!UICONTROL 审批者] 或 [!DNL Target] 配置 [!DNL Target] [!UICONTROL 目标] AEP/RTCDP中的信息卡([!DNL Real-time Customer Data Platform])。
   >
   >有关详细信息，请参阅 [使用来自Adobe Experience Platform的受众](#aep).

预定义受众，例如“[!UICONTROL 新访客]&quot;和&quot;[!UICONTROL 回访访客]，无法重命名。

使用最初在 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform], [!DNL Target] 如果您在 [!DNL Target] 之后在 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform].

* 如果受众已在 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform]，在 [!UICONTROL 受众] 列表中，此时会显示受众选取器。 工具提示 [!DNL Target] UI还指示受众已在 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform].
* 如果您尝试将多个受众与已删除的受众合并，或者您想保存引用了已删除受众的活动，则会显示一条警告消息。

您还可以定位自定义配置文件参数和 `user.` 参数。创建受众时，将要用于定位活动的属性拖到受众生成器窗口中。 如果未显示所需的属性，则表示该属性未被mbox触发。 “[!UICONTROL 自定义参数]”下拉列表中提供了其他自定义 mbox 参数。

使用 [!UICONTROL 过滤器] 按钮来筛选 [!UICONTROL 受众] 按源列表： [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud]和 [!DNL Adobe Experience Platform].

![过滤器选项 [!UICONTROL 受众] 列表](assets/filters.png)

使用 [!UICONTROL 搜索受众] 框 [!UICONTROL 受众] 列表。 您可以搜索受众名称的任意部分，或将特定字符串用引号引住。

您可以按受众名称或上次修改日期对“[!UICONTROL 受众]”列表进行排序。要按名称或上次修改日期进行排序，请单击列标头，然后选择受众显示的顺序（升序或降序）。

## 查看受众定义 {#section_11B9C4A777E14D36BA1E925021945780}

您可以在 [!DNL Target] UI，而不打开受众。 此功能适用于在中创建的受众 [!DNL Target Standard/Premium] 从导入的受众 [!DNL Target Classic] 或通过API创建。

例如，通过单击 [!UICONTROL 查看详细信息] 图标：

![活动 > 受众定义](assets/audience_definition_list.png)

单击 [!UICONTROL 查看详细信息] 图标 [!UICONTROL 概述] 页面：

![活动 > 受众定义](assets/view-details-activity-overview.png)

受众定义卡片显示了受众的类型、来源和属性。 单击 **[!UICONTROL 查看完整详细信息]** ，以查看引用该受众的其他活动（如果适用）。 如果您查看的是活动中的受众定义卡片 [!UICONTROL 概述] 页面，单击 **[!UICONTROL 受众使用情况]**.

受众使用信息可帮助您避免在编辑受众时对其他活动造成意外影响。 信息包括 [!UICONTROL 实时活动], [!UICONTROL 不活动的活动], [!UICONTROL 已存档的活动]和 [!UICONTROL 正在同步活动]. 此功能适用于所有受众(库受众和 [仅限该活动的受众](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483))。

如果受众为 [与其他受众结合使用](/help/c-target/combining-multiple-audiences.md) 组合受众用于创建活动，则两个受众的使用情况信息会列出新创建的活动。

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

## 使用受众 [!DNL Adobe Experience Platform] {#aep}

利用在 [!DNL Adobe Experience Platform] 中创建的受众可提供更丰富的客户数据，从而带来更强大的个性化功能。的 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hans){target=_blank}(RTCDP)，内置于 [!DNL Adobe Experience Platform]，可帮助公司将来自多个企业来源的已知和匿名数据汇集在一起。 通过此流程，您可以创建客户配置文件，以便用于在所有渠道和设备中实时提供个性化的客户体验。

通过连接 [!DNL Target] 到 [!DNL Real-time Customer Data Platform]，客户可以通过解锁之前可能无法访问的新区段来扩充其Web个性化 [!DNL Target] 用于在客户的Web访问首页上实时进行毫秒个性化。 使用在中创建的受众 [!DNL Adobe Experience Platform] 允许您扩展可用的数据点，以便进行更丰富的个性化。

此集成可通过RTCDP解锁关键用例：

* 同页/下次点击个性化
* 首次/未知用户个性化

主要功能包括：

* 直接Target与RTCDP集成/[!DNL Adobe Experience Platform] 在边缘上(删除对 [!DNL Audience Core services] - AAM)
* [!UICONTROL Target边缘目标卡] 实施治理
* 使用统一配置文件进行边缘分割和边缘配置文件

有关更多信息，请参阅以下主题：

* [目标发行说明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} *Adobe Experience Platform发行说明*
* [为同一页面和下一页面个性化配置个性化目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} *目标概述* 的双曲余切值。
* [自定义个性化连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} *目标概述* 指南
* [Adobe Target连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} *目标概述* 指南
* [为同一页面和下一页个性化用例配置个性化目标](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} *目标概述* 指南

### 其他信息

下表显示了来自不同实施方案的事件的区段评估时间：

| 情景 | 边缘区段（毫秒评估） | 流区段（分钟评估） | 批量区段评估 |
| --- | --- | --- | --- |
| 来自Adobe Experience Platform SDK的事件/数据 | 是 | 是 | 不适用 |
| at.js中的事件 | 否 | 是 | 不适用 |
| Target Mobile SDK中的事件 | 否 | 是 | 不适用 |
| 批量上传事件 | 否 | 否 | 是 |
| 离线数据（流）中的事件 | 否 | 是 | 是 |

### 视频：使用实时CDP实现下一次点击的个性化，以及 [!DNL Adobe Target]{#RTCDP}

了解如何在下次点击时使用进行个性化设置 [!DNL Real-time Customer Data Platform] 和 [!DNL Adobe Target]. 的 [!DNL Adobe Target] 目标 [!DNL Real-time CDP] 允许您使用 [!DNL Experience Platform] 区段 [!DNL Adobe Target] 具有管理和隐私支持的同一页面和下一页个性化。

有关更多信息，请参阅 [使用实时CDP和Adobe Target实现下一次点击的个性化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} *平台Tutorials* 的双曲余切值。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Adobe Target博客和视频：

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

## 培训视频：使用受众 ![教程徽章](/help/assets/tutorial.png)

以下视频包含有关使用受众的信息。

* 解释术语“受众”
* 介绍使用受众进行优化的两种方式
* 在“受众”列表中查找受众
* 将活动定位到受众
* 在活动中使用受众进行被动报告

>[!VIDEO](https://video.tv.adobe.com/v/17398)

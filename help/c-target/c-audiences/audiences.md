---
keywords: 受众;受众规则;创建受众;定位受众;报表受众;区段;自定义配置文件参数;受众定义;受众列表
description: 了解如何使用Adobe [!DNL Target] 中的[!UICONTROL 受众]列表，以及如何查看包含受众详细信息和使用信息的受众定义卡片。
title: 如何使用受众列表？
feature: 受众
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 06a5fda72a649c4037cb78d3e670747cd297a64d
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 58%

---

# 创建受众

[!DNL Adobe Target]中的受众可确定在目标活动中看到内容和体验的受众。

不论在何处，只要可以使用定位，便会用到受众。对活动进行定位时，您可以选择以下选项：

* 从[!UICONTROL 受众]列表中选择可重复使用的受众
* [创建特定于活动的受](/help/c-target/creating-activity-only-audience.md) 众并将其定位
* [合并多](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) 个受众以创建临时受众

您还可以使用由[!DNL Adobe Analytics]收集的受众数据在[!DNL Target]和其他[!DNL Adobe Experience Cloud]应用程序中进行实时定位和个性化。 请参阅&#x200B;*Experience Cloud中心界面组件*&#x200B;指南中的[Experience Cloud受众](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html??lang=zh-Hans)。

[!DNL Target] 定义了以下两种类型的受众：

* **定位受众：**&#x200B;用于向不同类型的访客交付不同的内容。
* **报表受众：**&#x200B;用于确定不同类型的访客对同一内容有何响应，以便于您分析测试结果。

   在 [!DNL Target] 中，仅当使用 [!DNL Target] 作为报表源时，才能配置报表受众。如果您使用 [ Adobe Analytics 作为报表源](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，则必须在 [!DNL Analytics] 中配置报表受众。

## 使用[!UICONTROL Audiences]列表

要访问“[!UICONTROL 受众]”列表，请单击顶部菜单栏中的&#x200B;**[!UICONTROL 受众]**：

![“受众”列表](/help/c-target/c-audiences/assets/audiences_list.png)

“[!UICONTROL 受众]”列表包含所有可在活动中使用的受众。使用“[!UICONTROL 受众]”列表可创建、编辑、删除、复制或合并受众。该列表还显示创建受众的源位置（[!DNL Target]、[!DNL Target Classic]和[!DNL Experience Cloud]）。 无法重命名预定义受众，如“[!UICONTROL 新访客]”和“[!UICONTROL 旧访客]”。

使用最初在[!DNL Experience Cloud]中创建的受众时，如果您在[!DNL Target]活动中引用了稍后在[!DNL Experience Cloud]中删除的受众，Target会向您发出警报。

* 如果在[!DNL Experience Cloud]中删除了受众，则[!UICONTROL Audience]列表和受众选取器中都会显示警告图标。 UI中的工具提示还指示受众已在[!DNL Experience Cloud]中删除。
* 如果您尝试将多个受众与已删除的受众合并，或者您想保存引用了已删除受众的活动，则会显示一条警告消息。

您还可以定位自定义配置文件参数和 `user.` 参数。添加受众时，单击要用于定位活动的属性。 如果未显示所需的属性，则表示该属性未被mbox触发。 “[!UICONTROL 自定义参数]”下拉列表中提供了其他自定义 mbox 参数。

使用[!UICONTROL Filters]按钮按源筛选[!UICONTROL Audiences]列表：[!DNL Adobe Target]、[!DNL Adobe Target Classic]和[!DNL Experience Cloud]。

![受众列表中的过滤器  选项](/help/c-target/c-audiences/assets/filters.png)

使用[!UICONTROL 搜索受众]框可搜索[!UICONTROL 受众]列表。 您可以搜索受众名称的任意部分，或将特定字符串用引号引住。

您可以按受众名称或上次修改日期对“[!UICONTROL 受众]”列表进行排序。要按名称或上次修改日期进行排序，请单击列标头，然后选择受众显示的顺序（升序或降序）。

## 查看受众定义 {#section_11B9C4A777E14D36BA1E925021945780}

在 Target UI 中的多个位置，您无需打开受众，即可在弹出卡片中查看受众定义详细信息。此功能适用于在[!DNL Target Standard/Premium]中创建的受众，以及从[!DNL Target Classic]导入或通过API创建的受众。

例如，通过单击所需受众的[!UICONTROL 查看详细信息]图标，可访问以下受众定义卡片：

![活动 > 受众定义](assets/audience_definition_list.png)

单击活动[!UICONTROL 概述]页面上的[!UICONTROL 查看详细信息]图标，可访问以下受众定义卡片：

![活动 > 受众定义](/help/c-target/c-audiences/assets/view-details-activity-overview.png)

受众定义卡片显示了受众的类型、来源和属性。 单击&#x200B;**[!UICONTROL 查看完整详细信息]**，以查看引用该受众的其他活动（如果适用）。 如果您要从活动的[!UICONTROL 概述]页面中查看受众定义卡片，请单击&#x200B;**[!UICONTROL 受众使用情况]**。

受众使用信息可帮助您避免在编辑受众时对其他活动造成意外影响。 该信息包含“实时活动”、“不活跃的活动”、“已存档的活动”和“正在同步的活动”。此功能适用于所有受众（库受众和[仅限该活动的受众](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)）。

如果某个受众与其他受众组合在一起，并且该组合受众用于创建活动，则这两个受众的使用信息会列出该新创建的活动。

![](assets/audience_definition_list_usage.png)

下面是从 Adobe Experience Cloud 中导入的一个受众所具有的受众定义卡片。在本例中，受众是从 Adobe Audience Manager (AAM) 中导入的。

![“受众定义”卡片上的“使用情况”选项卡](assets/audience_definition_mc.png)

以下类型的导入受众具有下列详细信息：

| 受众类型 | 详细信息 |
|--- |--- |
| 移动设备受众 | 设备营销名称、供应商和型号。<br>将显示 `matches | does not match` 运算符，而不是`equals | does not equal`<br>![导入的移动设备受众](/help/c-target/c-audiences/assets/imported_mobile_audience.png)。 |
| 访客行为受众 | **user.categoryAffinity：**&#x200B;带有 `FAVORITE` 参数的 `categoryAffinity`。<br>![导入的类别亲和度&#x200B;](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**监控：**&#x200B;监控服务等于 true。<br>**无监控服务：**&#x200B;监控服务等于 false。<br>![导入的监控](/help/c-target/c-audiences/assets/imported_monitoring.png) |
| 使用 NOT 运算符的受众 | **单一规则：** Target 以 `[All Visitor AND [NOT [rule]` 格式显示受众。单个 NOT 规则会与 AND 及 `AllVisitor` 受众一同显示。<br>![导入的使用 NOT 运算符的受众](/help/c-target/c-audiences/assets/imported_not_audience.png) |

使用导入的受众时，请牢记以下几点信息：

* Target Standard/Premium 不再支持使用定位表达式受众。
* Target Standard/Premium 不支持某些已弃用的受众，或改进了运算符以便于使用。因此，导入的受众虽然根据定义可以使用，但这并不意味着可以在 Standard/Premium 界面中创建该受众。例如，虽然社交受众及其规则是可见的，但 Target Standard/Premium 不允许创建社交受众。

## 培训视频：使用受众 ![教程徽章](/help/assets/tutorial.png)

以下视频包含有关使用受众的信息。

* 解释术语“受众”
* 介绍使用受众进行优化的两种方式
* 在“受众”列表中查找受众
* 将活动定位到受众
* 在活动中使用受众进行被动报告

>[!VIDEO](https://video.tv.adobe.com/v/17398)

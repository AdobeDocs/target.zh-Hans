---
keywords: cja4t；customer journey analytics；customer journey analytics for target；customer journey analytics报告源；customer journey analytics作为target报告源
description: 使用 [!DNL Adobe Customer Journey Analytics] for [!DNL Target] (A4T) 根据 [!DNL Customer Journey Analytics] 转化指标和受众区段创建活动，并使用 [!DNL Customer Journey Analytics] 报表检查结果。
title: 什么是 [!DNL Adobe Customer Journey Analytics] 对象 [!DNL Target] (CJA4T)？
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 13c899b656d9f15e7368d981ac25540c46caccb2
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 12%

---

# [!DNL Adobe Customer Journey Analytics] 作为的报表源 [!DNL Adobe Target] (CJA4T)

此 [!DNL Customer Journey Analytics for Target] (CJA4T)集成介于 [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html){target=_blank} 和 [!DNL Target] 为您的优化项目提供功能强大的分析和省时的工具。

使用的主要优势 [!DNL Customer Journey Analytics] 数据输入 [!DNL Target] 为：

* 营销人员可以动态应用 [!DNL Customer Journey Analytics] 成功量度 [!DNL Target] 随时报告活动。 在运行活动之前不需要指定各项内容。
* 单个数据源可最大限度地减少在两个单独系统中收集数据时发生的差异。

## 注意事项

在使用CJA4T集成之前，请考虑以下信息：

* 要使用 [!DNL Customer Journey Analytics] 作为 [!DNL Target] 的报表源，您和您的公司必须均可以访问 [!DNL Customer Journey Analytics] 和 [!DNL Target]。如果您需要访问任一解决方案，请联系贵组织的管理员或帐户代表。
* 创建 [!DNL Target] 活动 [!DNL Customer Journey Analytics] 报表，您必须具有“[!UICONTROL 审批者]”或&#39;[!UICONTROL 编辑者]中的“ ”角色 [!DNL Target].
   * 如果您拥有 [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) 帐户，请参阅 [指定角色和权限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) 在 *用户*.
   * 如果您拥有 [Target Premium](/help/main/c-intro/intro.md#premium) 帐户，请参阅 [角色和权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) 在 *企业用户权限*.

* 根据您的设置，可以按活动或组织级别更改报告。 请参阅 [报表云解决方案](/help/main/administrating-target/reporting.md#solution) 在 *在Target中配置报表*.
* 使用一个报表源或另一个。您无法收集单个活动的数据到多个报表源。
* 当您设置 [!DNL Customer Journey Analytics] 作为报表源，系统会提示您为报表指定沙盒。 在配置过程中，您只会看到您有权访问的沙盒。
* 任何现有 [!DNL Target] 活动继续使用 [!DNL Target] 数据收集不受启用CJA4T的影响。
* CJA4T仅在以下情况下可用： [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}. 支持 [!DNL Analytics Data Connector] 已规划为未来使用。
* 有关时间的任何问题，请参见 [延迟注意事项](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#latency){target=_blank} 在 *常见问题解答* 在 *AdobeCustomer Analytics指南*.

## 支持的活动类型 {#supported-activities}

使用时，支持以下活动类型 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} JavaScript库：

| 活动类型 | 是否与CJA4T兼容？ |
|--- |--- |
| [使用手动流量拆分的 A/B 活动](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |
| [使用自动分配的 A/B 活动](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [使用自动定位的 A/B 活动](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 否 |
| [体验定位 (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | 是 |
| [多变量测试 (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 是 |
| [Automated Personalization (AP) 活动](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | 否 |
| [Recommendations 活动](/help/main/c-recommendations/recommendations.md) | 是 |

## 创建使用 [!DNL Customer Journey Analytics] 作为报表源

创建 [!DNL Target] 使用的活动 [!DNL Customer Journey Analytics] 因为报表源类似于设置常规 [!DNL Target] 活动。

1. 从 **[!UICONTROL 活动]** 列表，单击 **[!UICONTROL 创建活动]**，然后选择活动类型(根据 [上图支持的活动图](#supported-activities))，并开始设置活动。
1. 当您到达 **[!UICONTROL 目标和设置]** 在三步活动创建工作流的页面中，选择 **[!DNL Customer Journey Analytics]** 作为报表源。

   ![“Customer Journey Analytics为报表源”选项](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >在更改报表源之后， [!DNL Target] 活动上线。

1. 选择一个沙盒.

   在此下拉列表中，您只能看到您有权访问的沙盒。 如果列表中缺少您有权访问的一个或多个沙盒，请验证您有权访问沙盒。 联系人 [客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 如果您仍然看到问题。

   ![选择沙盒选项](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. 指定活动目标。

   选择一个成功量度以用作每个活动的目标。 您可以选择以下选项之一 [!DNL Target] 转化量度或使用 [!DNL Customer Journey Analytics] 量度。

   ![使用“目标指标”下的“Customer Journey Analytics指标”选项](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. 单击&#x200B;**[!UICONTROL 保存并关闭]**。

## 设置 [!DNL Customer Journey Analytics] 连接

之后 [!DNL Target] 活动已创建，您必须在中创建连接 [!DNL Customer Journey Analytics]. 如果已设置连接，则可以使用现有连接并跳至下面的步骤4。 连接允许 [!DNL Customer Journey Analytics] 以开始从数据集中提取数据以便进行报告。

1. 在 [!DNL Customer Journey Analytics]，位于 **[!UICONTROL 连接]** 页面，单击 **[!UICONTROL 创建新连接]**.

   ![在Customer Journey Analytics中创建新连接链接](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. 配置您的 [连接和数据设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html){target=_blank} 提供正确的信息。
1. 添加配置数据流时使用的事件数据集。
1. 添加 **[!UICONTROL Adobe Target分类事件]** 查找数据集，然后单击 **[!UICONTROL 下一个]**.

   ![Customer Journey Analytics中的“添加数据集”对话框](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. 配置事件数据集。

   有关更多信息，请参阅 [添加和配置数据集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#add-dataset){target=_blank} 在 *创建连接* 在 *Adobe Customer Journey Analytics指南*.

1. 使用配置查找数据集 [!UICONTROL 键] 字段作为“key”，匹配键字段具有以下路径：

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics中的“Adobe Target分类事件”对话框](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. 单击 **[!UICONTROL 添加数据集]**，然后单击 **[!UICONTROL 保存]** ，以完成连接。

## 设置数据视图

在中设置数据视图 [!DNL Customer Journey Analytics]. 数据视图可确保正确使用来自连接的数据。

1. 设置数据视图，并确保它指向您在前面创建的连接。

   有关更多信息，请参阅 [创建或编辑数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html){target=_blank} 在 *Adobe Customer Journey Analytics指南*.

1. 要正确查看 [!DNL Target] 数据输入 [!DNL Customer Journey Analytics]中，您必须从查找数据集中添加以下字段作为维度：

   * 体验名称
   * 体验 ID
   * 活动名称
   * 活动 ID

   ![Customer Journey Analytics中的名称和ID选项](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. 完成设置任何其他字段，然后单击 **[!UICONTROL 保存并继续]** 完成时。

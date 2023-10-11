---
keywords: cja4t；customer journey analytics；customer journey analytics for target；customer journey analytics 报表源；customer journey analytics 作为 target 的报表源
description: 使用 [!DNL Adobe Customer Journey Analytics] for [!DNL Target] (A4T) 根据 [!DNL Customer Journey Analytics] 转化量度和受众区段创建活动，并使用 [!DNL Customer Journey Analytics] 报表检查结果。
title: ' [!DNL Adobe Customer Journey Analytics] for [!DNL Target] (CJA4T) 是什么？'
feature: Integrations
hide: true
hidefromtoc: true
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 2480578b3e26cfbb5881700c2a09b5b6e2dabba2
workflow-type: ht
source-wordcount: '1020'
ht-degree: 100%

---

# [!DNL Adobe Customer Journey Analytics] 作为 [!DNL Adobe Target] 的报表源 (CJA4T)

[!DNL Customer Journey Analytics for Target] (CJA4T) 与 [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html){target=_blank} 和 [!DNL Target] 进行集成，为优化项目提供强大而又节省时间的分析工具。

将 [!DNL Customer Journey Analytics] 用作 [!DNL Target] 的报告源主要有以下好处：

* 营销人员可以随时将 [!DNL Customer Journey Analytics] 成功量度动态应用到 [!DNL Target] 活动报表。在运行活动之前什么都不需要指定。
* 利用如[“试验”面板](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html){target=_blank}等 [!DNL Customer Journey Analytics] 功能进一步分析您的网站个性化情况。
* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/cja-ajo.html){target=_blank} 和 [!DNL Target] 只需一个报告源。可将这两种个性化产品都连接到 [!DNL Customer Journey Analytics] 以更全面地了解您的 Web 个性化情况。

## 注意事项

在使用 CJA4T 集成之前，请考虑以下信息：

* 要使用 [!DNL Customer Journey Analytics] 作为 [!DNL Target] 的报表源，您和您的公司必须均可以访问 [!DNL Customer Journey Analytics] 和 [!DNL Target]。如果您需要任一解决方案的访问权限，请联系组织的管理员或客户代表。
* 使用 [!DNL Customer Journey Analytics] 报表创建 [!DNL Target] 活动时，您必须具有 [!DNL Target] 中的“[!UICONTROL 审批者]”或“[!UICONTROL 编辑者]”角色。
   * 如果您有一个 [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) 帐户，请参阅&#x200B;*用户*&#x200B;中的[指定角色和权限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。
   * 如果您有一个 [Target Premium](/help/main/c-intro/intro.md#premium) 帐户，请参阅&#x200B;*企业用户权限*&#x200B;中的[角色和权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions)。

* 您必须是 [!DNL Adobe Experience Platform] 中角色的一部分才能设置以 [!DNL Customer Journey Analytics] 作为报告源的 [!DNL Target] 活动。有关更多信息，请参阅&#x200B;*数据架构师和工程师教程*&#x200B;的&#x200B;*配置权限*&#x200B;中的[在  [!DNL Adobe Experience Platform] 中添加角色](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions.html){target=_blank}。
* 根据您的设置，可以根据活动或组织级别更改报表。请参阅&#x200B;*在 Target 中配置报表*&#x200B;中的[报表云解决方案](/help/main/administrating-target/reporting.md#solution)。
* 使用一个报表源或另一个。您无法将单个活动的数据收集到多个报表源中。
* 在设置 [!DNL Customer Journey Analytics] 作为您的报表源时，系统会提示您指定用于报表的沙盒。在配置期间，您只能看到您有权访问的沙盒。
* 任何现有 [!DNL Target] 活动继续使用 [!DNL Target] 数据收集，不受启用 CJA4T 的影响。
* 要使用 CJA4T，首选的实施方法是{target=_blank} and [!DNL Target] implemented through the [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html)。如果您当前未实施 [!DNL Adobe Experience Platform Web SDK]，则还可创建 [[!DNL Adobe Analytics] 源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)以将数据引入到 [!DNL Adobe Experience Platform] 中。
* 有关计时如有任何疑问，请参阅 *[!DNL Adobe Customer Analytics]指南*&#x200B;中的“常见问题解答”**&#x200B;中的[延迟注意事项](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#latency){target=_blank}。

## 支持的活动类型 {#supported-activities}

使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} JavaScript 库时，支持以下活动类型：

| 活动类型 | 是否兼容 CJA4T？ |
|--- |--- |
| [使用手动流量拆分的 A/B 活动](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |
| [使用自动分配的 A/B 活动](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [使用自动定位的 A/B 活动](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 否 |
| [体验定位 (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | 是 |
| [多变量测试 (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 是 |
| [Automated Personalization (AP) 活动](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | 否 |
| [Recommendations 活动](/help/main/c-recommendations/recommendations.md) | 是 |

## 创建使用 [!DNL Customer Journey Analytics] 作为报表源的活动

创建将 [!DNL Customer Journey Analytics] 用作报表源的 [!DNL Target] 活动的过程与设置常规 [!DNL Target] 活动大体类似。

1. 在&#x200B;**[!UICONTROL 活动]**&#x200B;列表中，单击&#x200B;**[!UICONTROL 创建活动]**，然后选择活动类型（根据[上述支持的活动图表](#supported-activities)）并开始设置活动。
1. 当您在分为三个部分的活动创建工作流中转到&#x200B;**[!UICONTROL 目标与设置]**&#x200B;页面时，请选择 **[!DNL Customer Journey Analytics]** 作为报表源。

   ![“Customer Journey Analytics 作为报表源”选项](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >[!DNL Target] 活动开始后，将无法更改报表源。

1. 选择一个沙盒。

   在此下拉列表中，您只能看到您有权访问的沙盒。如果列表中缺少您有权访问的一个或多个沙盒，请验证您是否有权访问该沙盒。如果问题继续出现，请联系[客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

   ![选择沙盒选项](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. 指定活动目标。

   选择一个成功量度作为各个活动的目标。您可以选择 [!DNL Target] 转化量度之一，或者使用 [!DNL Customer Journey Analytics] 量度。

   ![使用“目标量度”下的 Customer Journey Analytics 量度选项](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. 单击&#x200B;**[!UICONTROL “保存并关闭”。]**

## 设置 [!DNL Customer Journey Analytics] 连接

在创建了 [!DNL Target] 活动之后，您必须在 [!DNL Customer Journey Analytics] 中创建连接。如果您已设置连接，则可以使用现有连接并跳至下面的步骤 4。该连接允许 [!DNL Customer Journey Analytics] 开始从数据集内提取数据用于报表。

1. 在 [!DNL Customer Journey Analytics] 的&#x200B;**[!UICONTROL 连接]**&#x200B;页面上，单击&#x200B;**[!UICONTROL “创建新连接”。]**

   ![Customer Journey Analytics 中的“创建新连接”链接](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. 使用正确的信息配置[连接和数据设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html){target=_blank}。
1. 添加您在配置数据流时使用的事件数据集。
1. 添加 **[!UICONTROL Adobe Target 分类事件]**&#x200B;查询数据集，然后单击&#x200B;**[!UICONTROL 下一步]**。

   ![Customer Journey Analytics 中的“添加数据集”对话框](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. 配置事件数据集。

   有关更多信息，请参阅 *Adobe Customer Journey Analytics 指南*&#x200B;的&#x200B;*创建连接*&#x200B;中的[添加和配置数据集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans#add-dataset){target=_blank}。

1. 使用[!UICONTROL 键]字段作为“键”配置您的查询数据集，并使用以下路径配置“匹配键”字段：

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics 中的“Adobe Target 分类事件”对话框](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. 单击&#x200B;**[!UICONTROL “添加数据集”]**，然后在下一个屏幕上单击&#x200B;**[!UICONTROL “保存”]**&#x200B;以完成连接。

## 设置数据视图

在 [!DNL Customer Journey Analytics] 中设置数据视图。数据视图确保可以正确使用您的连接中的数据。

1. 设置数据视图并确保视图指向您在上文中创建的连接。

   有关更多信息，请参阅 *Adobe Customer Journey Analytics 指南*&#x200B;中的[创建或编辑数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html){target=_blank}。

1. 为了正确查看 [!DNL Customer Journey Analytics] 中的 [!DNL Target] 数据，您必须从查询数据集内添加以下字段作为维度：

   * 体验名称
   * 体验 ID
   * 活动名称
   * 活动 ID

   ![Customer Journey Analytics 中的名称和 ID 选项](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. 完成其他所有字段的设置，在完成后，单击&#x200B;**[!UICONTROL “保存并继续”。]**

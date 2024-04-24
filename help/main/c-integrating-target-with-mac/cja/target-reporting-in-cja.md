---
keywords: customer journey analytics；customer journey analytics for target；customer journey analytics报告源；customer journey analytics作为target的报告源；cja中的目标报告；Customer Journey Analytics中的目标报告
description: 使用 [!DNL Target] 报告 [!DNL Adobe Customer Journey Analytics] 创建活动依据 [!DNL Customer Journey Analytics] 转化量度和受众区段及其用法 [!DNL Customer Journey Analytics] 报告以检查结果。
title: 什么是 [!DNL Target] 报告 [!DNL Adobe Customer Journey Analytics]？
feature: Integrations
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
hide: true
hidefromtoc: true
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 8475365099315f3f8f2a47bfca9dd9f245b16720
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 58%

---

# [!DNL Target] 报告 [!DNL Adobe Customer Journey Analytics]

之间的集成 [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} 和 [!DNL Target] 为您的优化项目提供功能强大的分析和省时的工具。

将 [!DNL Customer Journey Analytics] 用作 [!DNL Target] 的报告源主要有以下好处：

* 营销人员可以随时将 [!DNL Customer Journey Analytics] 成功量度动态应用到 [!DNL Target] 活动报表。在运行活动之前什么都不需要指定。
* 营销人员可以利用 [!DNL Customer Journey Analytics] 功能，例如 [“试验”面板](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}，以进一步分析其网站个性化。
* 营销人员可以拥有针对以下项的单个报表源： [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} 和 [!DNL Target]. 可将这两种个性化产品都连接到 [!DNL Customer Journey Analytics] 以更全面地了解您的 Web 个性化情况。

## 注意事项

在使用之前，请考虑以下信息 [!DNL Customer Journey Analytics] 和 [!DNL Target] 集成：

>[!IMPORTANT]
>
>此集成与不同 [[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。 实施与支持的活动类型不同。 在将此集成用于您的之前，请确保仔细阅读本文 [!DNL Target] 活动。

* 要使用 [!DNL Customer Journey Analytics] 作为 [!DNL Target] 的报表源，您和您的公司必须均可以访问 [!DNL Customer Journey Analytics] 和 [!DNL Target]。如果您需要任一解决方案的访问权限，请联系组织的管理员或客户代表。
* 创建 [!DNL Target] 活动 [!DNL Customer Journey Analytics] 报表，您必须具有“[!UICONTROL Approver]”或&#39;[!UICONTROL Editor]中的“ ”角色 [!DNL Target].
   * 如果您有一个 [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) 帐户，请参阅&#x200B;*用户*&#x200B;中的[指定角色和权限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。
   * 如果您有一个 [Target Premium](/help/main/c-intro/intro.md#premium) 帐户，请参阅&#x200B;*企业用户权限*&#x200B;中的[角色和权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions)。

* 您必须是 [!DNL Adobe Experience Platform] 中角色的一部分才能设置以 [!DNL Customer Journey Analytics] 作为报告源的 [!DNL Target] 活动。有关更多信息，请参阅&#x200B;*数据架构师和工程师教程*&#x200B;的&#x200B;*配置权限*&#x200B;中的[在  [!DNL Adobe Experience Platform] 中添加角色](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank}。
* 根据您的设置，可以根据活动或组织级别更改报表。请参阅&#x200B;*在 Target 中配置报表*&#x200B;中的[报表云解决方案](/help/main/administrating-target/reporting.md#solution)。
* 使用一个报表源或另一个。您无法将单个活动的数据收集到多个报表源中。
* 在设置 [!DNL Customer Journey Analytics] 作为您的报表源时，系统会提示您指定用于报表的沙盒。在配置期间，您只能看到您有权访问的沙盒。
* 任何现有 [!DNL Target] 活动继续使用 [!DNL Target] 数据收集不受启用此集成的影响。
* 要使用此集成，首选的实施方法是 [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank} and [!DNL Target] implemented through the [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  如果您当前没有 [!DNL Adobe Experience Platform Web SDK] 实施，您还可以创建 [[!DNL Adobe Analytics] 源连接](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) 将数据导入 [!DNL Adobe Experience Platform]. 如果您计划使用此方法，则必须选择 [!DNL Analytics] 报表包以及 [!DNL Adobe Experience Platform] 您使用的沙盒 [!DNL Customer Journey Analytics].

  ![“报告设置”对话框中的“沙盒”选项](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >如果您使用 [!DNL Adobe Analytics] 源连接中，您将同时具有两个报告 [!DNL Adobe Analytics] 和 [!DNL Customer Journey Analytics]. 但是，由于这两种解决方案之间的算法不同，因此结果不太可能匹配。

* 有关计时如有任何疑问，请参阅 *[!DNL Adobe Customer Analytics]指南*&#x200B;中的“常见问题解答”**&#x200B;中的[延迟注意事项](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank}。

## 支持的活动类型 {#supported-activities}

使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} or the [at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank} JavaScript 库时，支持以下活动类型：

| 活动类型 | 受支持? |
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

1. 从 **[!UICONTROL Activities]** 列表，单击 **[!UICONTROL Create Activity]**，然后选择活动类型(根据 [上图支持的活动图](#supported-activities))，并开始设置活动。
1. 当您到达 **[!UICONTROL Goals & Settings]** 在三步活动创建工作流的页面中，选择 **[!DNL Customer Journey Analytics]** 作为报表源。

   ![“Customer Journey Analytics 作为报表源”选项](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >[!DNL Target] 活动开始后，将无法更改报表源。

1. 选择一个沙盒。

   在此下拉列表中，您只会看到您有权访问的沙盒。 如果列表中缺少您有权访问的一个或多个沙盒，请验证您是否有权访问该沙盒。如果问题继续出现，请联系[客户关怀团队](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

   ![选择沙盒选项](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. 指定活动目标。

   选择一个成功量度作为各个活动的目标。您可以选择 [!DNL Target] 转化量度之一，或者使用 [!DNL Customer Journey Analytics] 量度。

   ![使用“目标量度”下的 Customer Journey Analytics 量度选项](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. 单击 **[!UICONTROL Save & Close]**。

## 设置 [!DNL Customer Journey Analytics] 连接

在创建了 [!DNL Target] 活动之后，您必须在 [!DNL Customer Journey Analytics] 中创建连接。如果您已设置连接，则可以使用现有连接并跳至下面的步骤 4。该连接允许 [!DNL Customer Journey Analytics] 开始从数据集内提取数据用于报表。

1. 在 [!DNL Customer Journey Analytics]，位于 **[!UICONTROL Connections]** 页面，单击 **[!UICONTROL Create a new connection]**.

   ![在中创建新连接链接 [!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)

1. 使用正确的信息配置[连接和数据设置](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank}。
1. 添加您在配置数据流时使用的事件数据集。
1. 添加 **[!UICONTROL Adobe Target Classification Events]** 查找数据集，然后单击 **[!UICONTROL Next]**.

   ![Customer Journey Analytics 中的“添加数据集”对话框](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. 配置事件数据集。

   有关更多信息，请参阅 [添加和配置数据集](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank} 在 *创建连接* 在 *[!DNL Adobe Customer Journey Analytics]指南*.

1. 使用配置查找数据集 [!UICONTROL Key] 字段作为“key”，并且 [!UICONTROL Matching] 键字段，路径如下：

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics 中的“Adobe Target 分类事件”对话框](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. 单击 **[!UICONTROL Add datasets]**，然后单击 **[!UICONTROL Save]** ，以完成连接。

## 设置数据视图

在 [!DNL Customer Journey Analytics] 中设置数据视图。数据视图确保可以正确使用您的连接中的数据。

1. 设置数据视图并确保视图指向您在上文中创建的连接。

   有关更多信息，请参阅 [创建或编辑数据视图](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank} 在 *[!DNL Adobe Customer Journey Analytics]指南*.

1. 为了正确查看 [!DNL Customer Journey Analytics] 中的 [!DNL Target] 数据，您必须从查询数据集内添加以下字段作为维度：

   * [!UICONTROL Experience Name]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Activity Name]
   * [!UICONTROL Activity ID]

   ![Customer Journey Analytics 中的名称和 ID 选项](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. 使用 [!DNL Target] 中的维度 [!UICONTROL Experimentation] 面板中，设置以下上下文标签：

   * 对象 [!UICONTROL Activity Name]，请使用“试验性试验”。
   * [!UICONTROL Experience Name]，请使用“试验变体”。

   ![“试验”面板中的上下文标签](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. 完成设置任何其他字段，然后单击 **[!UICONTROL Save and continue]** 完成时。

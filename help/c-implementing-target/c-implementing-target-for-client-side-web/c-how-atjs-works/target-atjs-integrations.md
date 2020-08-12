---
keywords: at.js integration;supported integrations;unsupported integrations;third party integrations
description: 有关与 Target 的常见集成及其对 at.js 的支持状态的信息。
title: at.js 集成
feature: null
topic: Standard
uuid: 19036a1d-941c-4d31-8c7b-f50c86996b1c
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 90%

---


# at.js 集成{#at-js-integrations}

有关与 [!DNL Target] 的常见集成及其对 at.js 的支持状态的信息。

如果您迫切需要不受支持或此处未提及的集成，请联系您的客户代表或顾问。

## 受支持的集成 {#section_3B44A970D3FB42D1973701452C868B55}

| 集成 | 详细信息 |
|--- |--- |
| Analytics for Target (A4T) | 请参阅[将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)](../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)。 |
| Profiles &amp; Audiences (P&amp;A) | 请参 [阅](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) 《核心服 *务用户指南》中的受众*。 |
| Experience Cloud ID 服务 | 请参阅 [Adobe Experience Cloud ID 服务文档](https://docs.adobe.com/content/help/en/id-service/using/home.html)。 |
| Adobe Launch | Launch 是 Adobe 的下一代标签管理平台，是实施 Adobe Target 的首选方法。Launch 为客户提供了一种简单的方式来部署和管理所有用来加强相关客户体验的分析、营销和广告标签。请参阅[使用 Adobe Launch 实施 Target](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25)。 |
| 动态标签管理 (DTM) | See the [Best Practices for Implementing Target Using Dynamic Tag Management guide](https://docs.adobe.com/content/help/en/dtm/implementing/overview.html).   重要信息：[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 是实施 Target 和 at.js 库的最新首选方法。对于新的 Target 实施，请使用 Launch。以下指南适用于使用 DTM 实施的现有客户端。使用 DTM 集成时，请考虑以下事项： <ul><li>库管理：通过“自定义”主机选项来使用 at.js。当前不支持“自动”管理。 </li></ul> |
| Adobe Experience Manager (AEM) 云服务 | AEM 云服务支持在 AEM 工作流中创建 A/B 测试和体验定位活动。带有 FP-11577（或更高版本）的 Adobe Experience Manager 6.2 支持 at.js。有关更多信息，请参阅[与 Adobe Target 集成](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html)，并选择您的 AEM 版本。 |
| AEM 体验片段 | 通过在 Target 活动的 AEM 中创建的体验片段，您可以将 AEM 中这一简单易用的功能与 Target 中强大的自动化智能 (AI) 和机器学习 (ML) 功能结合使用，从而测试和个性化大量体验。AEM 可将您的所有内容和资产汇集到一个中心位置，以帮助实施您的个性化策略。通过 AEM，您能够在一个位置轻松创建适用于桌面、平板电脑和移动设备的内容，而无需编写代码。您无需为每种设备分别创建页面，因为 AEM 可以使用您的内容自动调整每个体验。请参阅[AEM 体验片段](../../../c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8)。 |

## 不受支持的集成 {#section_8EFCAED418DC42E0B07F95924819EAC2}

| 集成 | 详细信息 |
|--- |--- |
| [!DNL Legacy Target to SiteCatalyst Integration] | 该集成可通过页面调用将营销活动 ID 和方法 ID 发送到 [!DNL SiteCatalyst]，从而在 [!DNL SiteCatalyst] UI 中生成报表。此功能已被 A4T 所替代。 |
| [!DNL Legacy Target to SiteCatalyst Integration] | 该集成可发起名为 `"SiteCatalyst: Event"` 和 `"SiteCatalyst: Purchase"` 的 mbox 调用，从而根据 evar 和 prop 构建成功量度和用户配置文件。此功能已被 A4T 和 P&amp;A 所替代。 |
| [!DNL Legacy Audience Manager (AAM) to Target Integration] | 该集成可发起前端 API 调用以检索 AAM 区段，然后将检索到的区段作为页面上各个 mbox 调用中的 mbox 参数进行发送。 |

## 第三方集成 {#section_EE599839CCAD49DD97640E5EDAD9082E}

| 集成 | 详细信息 |
|--- |--- |
| 其他标签管理器 | at.js 应该可以在非 Adobe 标签管理平台中使用，但是使用由其他供应商开发的自定义集成功能时要小心谨慎。其他供应商提供的集成可能会依赖一些内部 mbox.js 函数，而 at.js 中已不再存在这些函数。 |
| 第三方数据提供程序（例如 Demandbase、Bluekai、天气 API） | 使用 at.js [数据提供程序](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)功能，可以集成许多用于补充 Target 用户分析的第三方数据提供程序. |
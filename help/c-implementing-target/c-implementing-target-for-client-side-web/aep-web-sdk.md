---
keywords: Adobe Experience Platform Web SDK;aep Web SDK;Web SDK;Adobe Experience Cloud；平台边缘网络；Adobe Experience Platform边缘网络；边缘网络；aep边缘网络
description: 了解如何使用Adobe Experience Platform Web SDK通过AEP Edge Network与Adobe Experience Cloud中的各种服务进行交互。
title: 如何使用Experience PlatformWeb SDK实施？
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: 636016be6e8a6adc8c4b7fb09af93bb89e28373a
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 5%

---

# Adobe Experience Platform Web SDK

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK)是一个客户端JavaScript库，允许客户 [!DNL Adobe Experience Cloud] 与Experience Cloud中的各种服务(包括 [!DNL Target])至 [!UICONTROL Adobe Experience Platform边缘网络]. 除了JavaScript库之外，还有 [!DNL Adobe Experience Platform] 扩展，可帮助您配置Web SDK。

有关更多信息，请参阅 *Adobe Experience Platform Web SDK* 帮助：

* 欲知全面信息： [什么是Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* 有关特定于 [!DNL Target]: [Target概述](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## 教程：使用Platform Web SDK实施Adobe Experience Cloud

了解如何 [使用Adobe Experience Platform Web SDK实施Experience Cloud应用程序](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target=_blank}。 有关特定于Target的信息，请参阅 [使用Platform Web SDK设置Target](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-target.html){target=_blank}。

## 推荐文档

除 [!DNL Platform Web SDK] 上述文档中，本指南中的主题还包含特定于 [!DNL Platform Web SDK] 如 [!DNL Target] 功能和特性。

| 功能 | 描述/链接 |
| --- | --- |
| [活动 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 在中使用QA URL [!DNL Adobe Target] 通过永不更改的预览链接、可选的受众定位以及从实时活动数据中分段的QA报表，可轻松执行端到端活动QA。 [!UICONTROL 活动QA] 允许您对 [!DNL Target] 活动之前激活它们。<br>请参阅 [Target JavaScript库QA模式兼容性](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) 和 [预览URL](/help/c-activities/c-activity-qa/activity-qa.md#preview). |
| [[!UICONTROL Analytics for Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T)是一种跨解决方案的集成，允许您根据 [!DNL Analytics] 转化量度和受众区段。 A4T集成允许您使用 [!DNL Analytics] 报告以检查结果。<br>请参阅 [支持的活动类型](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 和 [Adobe Experience Platform Web SDK实施的实施步骤](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform). |
| [受众](/help/c-target/target.md) | 受众 [!DNL Adobe Target] 确定在定位活动中看到内容和体验的人员。<br>请参阅 [使用受众列表](/help/c-target/c-audiences/audiences.md#use-list) 和 [合并多个受众](/help/c-target/combining-multiple-audiences.md). |
| [优惠决策](/help/c-integrating-target-with-mac/ajo/offer-decision.md) | 将Adobe Journey Optimizer中创建的选件决策添加到Target活动（手动A/B测试或体验定位），以确定并在Web和移动设备上为访客提供下一个最佳选件。 |
| [重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | 重定向选件会导致访客的浏览器重定向到新页面。<br>请参阅 [是否 [!DNL Adobe Experience Platform Web SDK] 是否支持A4T的重定向选件？](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [响应令牌](/help/administrating-target/response-tokens.md) | 响应令牌允许您将Target数据发送到Google Analytics和其他第三方集成。<br>请参阅 [通过Platform Web SDK向Google Analytics发送数据](/help/administrating-target/response-tokens.md#platform-web-sdk) 查看如何完成此任务的代码示例。 |
| [单页应用程序实施](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/spa-implementation.html?lang=en) 在 *平台Web SDK概述* 的双曲余切值。 | [!UICONTROL Adobe Experience Platform Web SDK] 提供了丰富的功能，使您的企业能够在下一代客户端技术(如单页应用程序(SPA))上实现个性化。 |
| [TLS（传输层安全性）加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS（传输层安全性）可帮助您保持最高的安全标准并提升客户数据的安全性。 |

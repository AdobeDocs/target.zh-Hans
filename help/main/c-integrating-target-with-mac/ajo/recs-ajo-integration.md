---
keywords: ajo；adobe journey optimizer；adobe journey optimizer target集成；推荐；target推荐；集成
description: 将 [!DNL Adobe Target Recommendations] 与 [!DNL Adobe Journey Optimizer]集成。
title: 如何在使用 [!DNL Adobe Journey Optimizer]的客户历程中使用 [!DNL Target Recommendations] ？
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
hide: true
hidefromtoc: true
exl-id: 81bbbd51-47fc-4e23-a1cb-7c18fea1c159
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 1%

---

# 集成[!DNL Adobe Target Recommendations]和[!DNL Adobe Journey Optimizer]

本文提供了将[!DNL Adobe Target Recommendations]与[!DNL Adobe Journey Optimizer]集成的使用案例和指南，使您能够提供互联、情境式和个性化的客户体验。

此集成可帮助您提高转化率，并了解包含个性化推荐的电子邮件的影响。

## 先决条件

要使用[!DNL Target Recommendations]和[!DNL Adobe Journey Optimizer]集成，您需要以下各项：

* 使用[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/zh-hans/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}实现的[[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium)。

  此功能在[!DNL Target Standard]许可证中或者使用at.js或其他[!DNL Target] SDK实施[!DNL Target]时不可用。

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target=_blank}。

## 示例用例

这些用例只是将[!DNL Target Recommendations]与[!DNL Adobe Journey Optimizer]集成的一些可能用例：

* **[!DNL Adobe Journey Optimizer]在购物车放弃后发送个性化电子邮件**：此用例基于以下情况：客户访问网站，将商品放入购物车，然后离开网站而未完成购买过程。

  例如，假设一位访客访问了一家服装公司的网站，并在购物车中置入了两件冬季外套和一件运动衫。 然后，访客分心并离开网站，或者不确定购买行为并关闭浏览器或应用程序。

  在指定的时间段（可能是几个小时或一天）之后，[!DNL Journey Optimizer]中的自定义操作会调用[!DNL Target Recommendations]，以使用基于[购物车的推荐](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)算法确定放弃的购物车的内容。 [!DNL Journey Optimizer]随后向此访客发送一封个性化电子邮件，提醒其购买流程未完成，同时还会发送指向放弃项目的图像和链接。

* **[!DNL Adobe Journey Optimizer]在网站访问后发送批量电子邮件，提醒访客查看了哪些项目**：此用例基于以下内容：访客访问网站，查看了各种项目，然后离开网站或应用程序，而不将项目放入购物车。

  在指定时段后，[!DNL Journey Optimizer]中的自定义操作会调用[!DNL Target Recommendations]，以确定每个访客使用每个访客的[!DNL Adobe Experience Cloud Identifier] (EDID)、访客的[!DNL Target]配置文件和基于用户的[算法，查看了哪些项目。 ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) [!DNL Adobe Journey Optimizer]随后向符合条件的受众的每个成员发送一封个性化电子邮件，其中包含每个访客查看项目的图像和链接，以便让访客返回并进行购买。

  在此方案中，[!UICONTROL Experience Cloud Visitor ID] (ECID)和每个访客的[!DNL Target]配置文件的内容用于根据最近查看的算法生成推荐。

  例如，假设一位访客访问了一个零售网站并查看了一些手表。 此访客的[!DNL Target]配置文件已更新，其中包含已查看监视项目的列表。 使用ECID和访客的[!DNL Target]配置文件，[!DNL Target]将推荐发送至[!DNL Journey Optimizer]。 [!DNL Journey Optimizer]然后发送一封电子邮件，其中包含该访客使用最近查看的算法查看的监视项目的图像和链接。 另一个访客会收到一封个性化电子邮件，其中包含该访客所查看项目的图像和链接。 对于每个访客，每个电子邮件都会进行个性化设置。

* **[!DNL Adobe Journey Optimizer]在网站访问后向符合条件的访客发送批量电子邮件以建议受欢迎的项目**：此用例基于访问网站的访客，但不查看任何特定项目。 电子邮件会批量发送给符合特定受众条件的所有访客，例如：

  假设访客未查看任何特定手表。 或许访客只是简单地点击了网站，并查看了类别页面或博客条目。 因此，[!DNL Target]配置文件没有有关最近查看的项目的具体信息。 在这种情况下，[!DNL Target Recommendations]使用[备用推荐](/help/main/c-recommendations/c-algorithms/backup-recs.md)，以便[!DNL Journey Optimizer]可以发送一封电子邮件，其中包含网站上的常用项目的图像和链接，以便让访客返回并可能进行购买。

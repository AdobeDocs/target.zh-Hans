---
keywords: ajo；adobe journey optimizer；adobe journey optimizer target集成；推荐；target推荐；集成
description: 集成 [!DNL Adobe Target Recommendations] 替换为 [!DNL Adobe Journey Optimizer].
title: 如何使用 [!DNL Target Recommendations] 在客户历程中使用 [!DNL Adobe Journey Optimizer]？
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
hide: true
hidefromtoc: true
source-git-commit: c79b1d40e0bf0495dc3f3d5accd196f14d18b934
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 2%

---

# 集成 [!DNL Adobe Target Recommendations] 和 [!DNL Adobe Journey Optimizer]

本文说明了用例和信息，以帮助您设置以下对象之间的集成 [!DNL Adobe Target Recommendations] 和 [!DNL Adobe Journey Optimizer] 以帮助您为客户提供互联、情境式和个性化的体验。

此集成可帮助您提高转化率，并了解包含个性化推荐的电子邮件的影响。

## 先决条件

要使用 [!DNL Target Recommendations] 和 [!DNL Adobe Journey Optimizer] 集成，您需要以下各项：

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) 使用实施 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

  该功能在 [!DNL Target Standard] 许可证或实施时 [!DNL Target] 使用at.js或其他 [!DNL Target] SDK。

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## 示例用例

以下是一些用于集成的可能用例 [!DNL Target Recommendations] 替换为 [!DNL Adobe Journey Optimizer]：

* **[!DNL A Journey Optimizer]在放弃购物车后发送个性化电子邮件**：此用例基于以下客户：访问网站，将商品放入购物车，然后离开网站而未完成购买过程。

  例如，假设一位访客访问了一家服装公司的网站，并在购物车中置入了两件冬季外套和一件运动衫。 然后，访客分心并离开网站，或者不确定购买行为并关闭浏览器或应用程序。

  在指定的时间段（可能是几个小时或一天）之后，执行中的自定义操作 [!DNL Adobe Journey Optimizer] 调用 [!DNL Target Recommendations] 使用确定放弃的购物车的内容 [基于购物车的推荐](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) 算法。 [!DNL Adobe Journey Optimizer] 然后，向此访客发送一封个性化电子邮件，提醒其购买流程未完成，并提供指向放弃项目的图像和链接。

* **[!DNL Adobe Journey Optimizer]在网站访问后发送电子邮件，提醒访客已查看哪些项目**：此用例基于以下访客：访问网站，查看各种项目，然后离开网站而不将项目放入购物车。

  经过指定时间段后，中的自定义操作 [!DNL Adobe Journey Optimizer] 调用 [!DNL Target Recommendations] 用于确定该访客查看了哪些项目，使用访客的 [!DNL Adobe Experience Cloud Identifier] (EDID)，访客的 [!DNL Target] 配置文件和 [基于用户](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) 算法。 [!DNL Adobe Journey Optimizer] 然后，向此访客发送一封个性化电子邮件，其中包含查看项目的图像和链接，以便让访客返回网站并购买。

  在此方案中， [!UICONTROL Experience Cloud访客ID] (ECID)和用户档案的内容 [!DNL Target] 用户档案用于根据最近查看的算法生成推荐。

  例如，假设一位访客访问了一个零售网站并查看了一些手表。 此访客的 [!DNL Target] 使用已查看的不同监视的列表更新配置文件。 使用ECID [!DNL Target] 个人资料， [!DNL Target] 将推荐发送至 [!DNL Adobe Journey Optimizer]. [!DNL Adobe Journey Optimizer] 然后，发送一封电子邮件，其中包含该访客使用“最近查看的项目”算法查看的监视项目的图像和链接。

* **[!DNL Adobe Journey Optimizer]在网站访问后发送电子邮件以建议受欢迎的项目**：此用例基于访客访问网站但未查看任何特定项目。

  例如，假设访客未查看任何特定观察项目。 或许访客只是简单地点击了网站各处并查看了类别页面或博客条目。 因此， [!DNL Target] 配置文件没有有关最近查看的项目的具体信息。 这种情况下 [!DNL Target Recommendations] 可以使用 [备用推荐](/help/main/c-recommendations/c-algorithms/backup-recs.md) 所以 [!DNL Adobe Journey Optimizer] 可以发送一封电子邮件，其中包含网站上的热门项目的图像和链接，以便让访客返回网站并购买。



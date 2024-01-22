---
keywords: ajo；adobe journey optimizer；adobe journey optimizer target集成；推荐；target推荐；集成
description: 集成 [!DNL Adobe Target Recommendations] 替换为 [!DNL Adobe Journey Optimizer].
title: 如何使用 [!DNL Target Recommendations] 在客户历程中使用 [!DNL Adobe Journey Optimizer]？
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
hide: true
hidefromtoc: true
source-git-commit: 1faedc44c4f8f95000b666af8eecaf1eca5bf48d
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 3%

---

# 集成 [!DNL Adobe Target Recommendations] 和 [!DNL Adobe Journey Optimizer]

本文说明了用例和信息，以帮助您设置以下对象之间的集成 [!DNL Adobe Target Recommendation] 和 [!DNL Adobe Journey Optimizer] 以帮助您为客户提供互联、情境式和个性化的体验。

## 先决条件

要使用 [!DNL Target Recommendations] 和 [!DNL Adobe Journey Optimizer] 集成，您需要以下各项：

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) 使用实施 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

  该功能在 [!DNL Target Standard] 许可证或实施时 [!DNL Target] 使用at.js或其他 [!DNL Target] SDK。

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## 示例用例

下面是集成的两个可能用例 [!DNL Target Recommendations] 替换为 [!DNL Adobe Journey Optimizer]：

* **[!DNL Customer Journey Optimizer]在放弃购物车后发送个性化电子邮件**：此用例基于以下客户：访问网站，将商品放入购物车，然后离开网站而未完成购买过程。

  例如，假设一位访客访问了一家服装公司的网站，并在购物车中置入了两件冬季外套和一件运动衫。 然后，访客分心并离开网站，或者不确定购买行为并关闭浏览器或应用程序。

  在指定的时间段（可能是几个小时或一天）之后，执行中的自定义操作 [!DNL Adobe Journey Optimizer] 调用 [!DNL Target Recommendations] 确定放弃的购物车的内容。 [!DNL Adobe Journey Optimizer] 然后，向此访客发送一封个性化电子邮件，提醒其购买流程未完成，并提供指向放弃项目的图像和链接。

* **[!DNL Customer Journey Optimizer]使用用户配置文件在网站访问后发送电子邮件**：此使用案例基于以下客户：访问网站，查看各种项目，然后离开网站而不将项目放入购物车。

  经过指定时间段后，中的自定义操作 [!DNL Adobe Journey Optimizer] 调用 [!DNL Target Recommendations] 以确定该访客使用访客的 [!DNL Adobe Experience Cloud Identifier] (EDID)。 [!DNL Adobe Journey Optimizer] 然后，向此访客发送一封个性化电子邮件，提醒其购买流程未完成，并提供指向放弃项目的图像和链接。


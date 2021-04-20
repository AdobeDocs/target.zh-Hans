---
keywords: 实施；实施；at.js;adobe experience platform web sdk;aep web sdk
description: 了解如何使用Adobe Experience Platform Web SDK(AEP Web SDK)或目标 at.js JavaScript库实施用于客户端Web的Adobe Target。
title: 如何为客户端Web实施目标
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 18%

---

# 概述：为客户端 Web 实施 Target

在 [!DNL Adobe Target] 的客户端实施中，[!DNL Target] 会将与活动相关联的体验直接交付给客户端浏览器。浏览器将决定要显示的体验，然后显示该体验。借助客户端实施，您可以使用 WYSIWYG 编辑器、[可视化体验编辑器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)，或者非可视化界面（[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)）来创建活动和个性化体验。

要实现[!DNL Adobe Target]客户端，必须使用以下JavaScript库之一：

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [目标 at.js JavaScript库](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**mbox.js终止使用**:自2021年3月31日起， [!DNL Adobe Target] 不再支持mbox.js库。2021年3月31日之后，从mbox.js发出的所有调用将轻松失败，并会通过提供默认内容来影响运行[!DNL Target]活动的页面。 我们建议所有客户在此日期前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。
>
>* **Adobe Experience Platform Web SDK**:Adobe Experience Platform  [!UICONTROL Web ] SDK允许您通过Adobe Experience Edge Network与（包括）中 [!DNL Experience Cloud] 的各种 [!DNL Target]服务进行交互。如果选择迁移到[!DNL Adobe Experience Platform Web SDK]，请参阅&#x200B;*Web SDK指南*&#x200B;中的[什么是Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。
   >
   >
* **at.js**:at.js JavaScript库比mbox.js提供许多优势。at.js可改善Web实施的页面加载时间、提高安全性并为单页应用程序提供更好的实施选项。 如果选择迁移到at.js，请参阅[At.js的工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[Adobe Target Skill Builder:开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
>
>
尽管目前支持mbox.js（2021年3月31日之前），但自2017年7月起，我们尚未对此库提供功能更新。 通过将所有客户移至[!UICONTROL Adobe Experience Platform Web SDK]或at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。

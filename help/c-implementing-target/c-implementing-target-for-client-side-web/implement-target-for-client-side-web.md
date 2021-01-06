---
keywords: implement;implementation;at.js;adobe experience platform web sdk;aep web sdk
description: 有关为客户端 Web 实施 Adobe Target 的信息。
title: 为客户端 Web 实施 Adobe Target
feature: client-side
translation-type: tm+mt
source-git-commit: 1b426e0b2004e729ba75d218a9b6ccd5195449cd
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 66%

---


# 概述：为客户端 Web 实施 Target

在 [!DNL Adobe Target] 的客户端实施中，[!DNL Target] 会将与活动相关联的体验直接交付给客户端浏览器。浏览器将决定要显示的体验，然后显示该体验。借助客户端实施，您可以使用 WYSIWYG 编辑器、[可视化体验编辑器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)，或者非可视化界面（[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)）来创建活动和个性化体验。

要实现[!DNL Adobe Target]客户端，必须使用[Adobe Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)、[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)或mbox.js库。

>[!NOTE]
>
>mbox.js 库将不再开发。所有客户都应部署[AEP Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)、[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md)或[从mbox.js迁移到at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)。

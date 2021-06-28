---
keywords: 实施；at.js;adobe experience platform web sdk;aep web sdk
description: 了解如何实施Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] at.js JavaScript库。
title: '如何为客户端Web实施 [!DNL Target] '
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 48%

---

# 概述：为客户端web实施[!DNL Target]

在 [!DNL Adobe Target] 的客户端实施中，[!DNL Target] 会将与活动相关联的体验直接交付给客户端浏览器。浏览器将决定要显示的体验，然后显示该体验。借助客户端实施，您可以使用 WYSIWYG 编辑器、[可视化体验编辑器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)，或者非可视化界面（[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)）来创建活动和个性化体验。

要实施[!DNL Adobe Target]客户端，您必须使用以下JavaScript库之一：

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Target at.js JavaScript库](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都会失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。Adobe 建议所有客户都在此日期之前迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。
>
>* **Adobe Experience Platform Web SDK**:通 [!UICONTROL 过Adobe Experience Platform ] Web SDK，您可以通过Adobe Experience Edge Network与 [!DNL Experience Cloud] 中的各种服务(包括 [!DNL Target])进行交互。如果您选择迁移到[!DNL Adobe Experience Platform Web SDK]，请参阅&#x200B;*Web SDK指南*&#x200B;中的[什么是Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。
   >
   >
* **at.js**:at.js JavaScript库可缩短Web实施的页面加载时间，增强安全性，并为单页应用程序提供更好的实施选项。如果您选择迁移到at.js，请参阅[At.js的工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[Adobe Target技能培养：开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。



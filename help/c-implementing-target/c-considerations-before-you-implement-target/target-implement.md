---
keywords: document.write;Target；实施；实施Target;DTM;at.js;mbox.js;target.js;mbox;adobe experience Platform Web SDK;Web SDK
description: 在您的网页上实施Adobe [!DNL Target] by referencing the [!DNL Target] 库（at.js或mbox.js）。
title: 了解  [!DNL Target] JavaScript 库
feature: 实施
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 24%

---


# 了解 [!DNL Target]JavaScript 库

通过在网页上引用[!DNL Adobe Target]库(Adobe Experience Platform Web SDK或at.js)来实施[!DNL Adobe Target]。

>[!NOTE]
>
>mbox.js 库将不再开发。所有客户必须在2021年3月31日之前从mbox.js迁移到at.js或[!UICONTROL Adobe Experience Platform Web SDK]。

## [!DNL Target] JavaScript库之间的差异 {#section_40117C78C2F84FECAC4F1BA40CC4F171}

下表说明了[!DNL Target] JavaScript库之间的差异：

| 库引用 | 描述 |
|--- |--- |
| Adobe Experience Platform Web SDK | 通过[!UICONTROL Adobe Experience Platform Web SDK]，您可以通过Adobe Experience Edge Network与[!DNL Experience Cloud]（包括[!DNL Target]）中的各种服务进行交互。 如果您选择迁移到[!DNL Adobe Experience Platform Web SDK]，请参阅&#x200B;*Web SDK指南*&#x200B;中的[什么是Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。 |
| at.js | at.js取代了用于[!DNL [!DNL Target]]实施的mbox.js。<br>使用 at.js 具有许多好处，包括缩短 Web 实施的页面加载时间，增强安全性，在 Google Chrome 中阻止 document.write 警告，以及为单页应用程序提供更好的实施选项，等等。 |

## at.js对页面加载时间的影响 {#section_16630CD0FF0A498EB596A51381366A5A}

许多客户和顾问都想了解[!DNL at.js]对页面加载时间的影响，特别是对于新用户与旧用户的情况。 遗憾的是，由于每位客户的实施不尽相同，因此很难评测[!DNL at.js]对页面加载时间的影响并给出具体的数字。

但是，如果页面上存在访客API，则[!DNL Target]可以更好地了解[!DNL at.js]对页面加载时间的影响情况。

>[!NOTE]
>
>仅当您使用全局mbox时，访客API和[!DNL at.js]才会对页面加载时间产生影响（因为采用了主体隐藏技术）。 区域 mbox 不受访客 API 集成的影响。

下表介绍了为新访客和旧访客执行的一系列操作：

### 新访客

1. 加载、解析并执行访客 API。
1. 加载、解析并执行at.js。
1. 如果启用了全局mbox自动创建，则[!DNL Target] JavaScript库：

   * 对访客对象实例化。
   * [!DNL Target]库尝试检索[!UICONTROL Experience Cloud访客ID]数据。
   * 对于新访客，访客API会触发对`demdex.net`的跨域请求。
   * 在检索[!UICONTROL Experience Cloud访客ID]数据后，将触发对Target的请求。

### 旧访客

1. 加载、解析并执行访客 API。
1. 加载、解析并执行at.js。
1. 如果启用了全局mbox自动创建，则[!DNL Target] JavaScript库：

   * 对访客对象实例化。
   * [!DNL Target]库尝试检索[!UICONTROL Experience Cloud访客ID]数据。
   * 访客 API 从 Cookie 中检索数据。
   * 在检索[!UICONTROL Experience Cloud访客ID]数据后，将触发对[!DNL Target]的请求。

>[!NOTE]
>
>对于新访客，当访客API存在时， [!DNL Target]会多次通过网线，以确保[!DNL Target]请求包含[!UICONTROL Experience Cloud访客ID]数据。 对于回访访客，[!DNL Target]仅通过电汇至[!DNL Target]以检索个性化内容。

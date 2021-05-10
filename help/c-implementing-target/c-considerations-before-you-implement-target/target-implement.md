---
keywords: 文档.write;目标；实现；实现目标;dtm;at.js;mbox.js;目标.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: 在网页上实施Adobe [!DNL Target] by referencing the [!DNL Target] 库（at.js或mbox.js）。
title: 了解  [!DNL Target] JavaScript 库
feature: 实施
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 24%

---


# 了解 [!DNL Target]JavaScript 库

通过在网页上引用[!DNL Adobe Target]库(Adobe Experience Platform Web SDK或at.js)来实施[!DNL Adobe Target]。

>[!NOTE]
>
>mbox.js 库将不再开发。所有客户必须在2021年3月31日之前从mbox.js迁移到at.js或[!UICONTROL Adobe Experience Platform Web SDK]。 有关详细信息，请参阅[从mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)或[Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)迁移到at.js。

## [!DNL Target] JavaScript库{#section_40117C78C2F84FECAC4F1BA40CC4F171}之间的差异

下表说明了[!DNL Target] JavaScript库之间的差异：

| 库引用 | 描述 |
|--- |--- |
| Adobe Experience Platform Web SDK | [!UICONTROL Adobe Experience Platform Web SDK]允许您通过Adobe Experience Edge Network与[!DNL Experience Cloud]（包括[!DNL Target]）中的各种服务进行交互。 如果选择迁移到[!DNL Adobe Experience Platform Web SDK]，请参阅&#x200B;*Web SDK指南*&#x200B;中的[什么是Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。 |
| at.js | at.js替换了用于[!DNL [!DNL Target]]实现的mbox.js。<br>使用 at.js 具有许多好处，包括缩短 Web 实施的页面加载时间，增强安全性，在 Google Chrome 中阻止 document.write 警告，以及为单页应用程序提供更好的实施选项，等等。<br>有关更多信息，请参阅 [at.js 实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)。 |

## at.js对页面加载时间{#section_16630CD0FF0A498EB596A51381366A5A}的影响

许多客户和顾问希望了解[!DNL at.js]对页面加载时间的影响，尤其是在新用户与回头用户的情境中。 很遗憾，由于每位客户的实施，很难衡量和给出具体数字，说明[!DNL at.js]如何影响页面加载时间。

但是，如果页面上存在访客API，[!DNL Target]可以更好地了解[!DNL at.js]如何影响页面加载时间。

>[!NOTE]
>
>仅当您使用全局mbox时，访客 API和[!DNL at.js]才会对页面加载时间产生影响（因为使用了正文隐藏技术）。 区域 mbox 不受访客 API 集成的影响。

下表介绍了为新访客和旧访客执行的一系列操作：

### 新访客

1. 加载、解析并执行访客 API。
1. 加载、分析和执行at.js。
1. 如果启用了全局mbox自动创建，则[!DNL Target] JavaScript库：

   * 对访客对象实例化。
   * [!DNL Target]库尝试检索[!UICONTROL Experience Cloud访客ID]数据。
   * 对于新访客,访客 API将向`demdex.net`触发跨域请求。
   * 检索[!UICONTROL Experience Cloud访客ID]数据后，将触发目标请求。

### 旧访客

1. 加载、解析并执行访客 API。
1. 加载、分析和执行at.js。
1. 如果启用了全局mbox自动创建，则[!DNL Target] JavaScript库：

   * 对访客对象实例化。
   * [!DNL Target]库尝试检索[!UICONTROL Experience Cloud访客ID]数据。
   * 访客 API 从 Cookie 中检索数据。
   * 在检索[!UICONTROL Experience Cloud访客ID]数据后，将触发对[!DNL Target]的请求。

>[!NOTE]
>
>对于新访客，当存在访客API时，[!DNL Target]会多次遍线以确保[!DNL Target]请求包含[!UICONTROL Experience Cloud访客ID]数据。 对于返回访客,[!DNL Target]只会通过电线到达[!DNL Target]以检索个性化内容。

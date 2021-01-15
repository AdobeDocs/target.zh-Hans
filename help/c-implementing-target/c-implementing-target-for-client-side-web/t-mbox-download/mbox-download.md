---
keywords: implementation;mbox;download mbox.js;download api;mbox.js api
description: 要使用Adobe Target标准版或目标高级版，请添加一行代码调用mbox.js。
title: mbox.js 实施
feature: null
translation-type: tm+mt
source-git-commit: bffda8c3461998767a002d66fd9340252237ae5d
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 32%

---


# mbox.js 实施

要使用[!DNL Adobe Target Standard]或[!DNL Target Premium]，请添加一行代码以调用mbox.js。

可以使用以下两个库引用之一：[!DNL Adobe Experience Platform Web SDK]或[!DNL at.js]。 [at.jsex的优](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) 点可以消除mbox.js和at.js库之间的差异。

>[!IMPORTANT]
>
>**mbox.js终止使用**:2021年3月31日 [!DNL Adobe Target] 将不再支持mbox.js库。2021年3月31日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响[!DNL Target]活动运行的页面。 我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。
>
>* **Adobe Experience PlatformWeb SDK**:Adobe Experience Platform [!UICONTROL Web ] SDK允许您通过Adobe Experience Edge Network与 [!DNL Experience Cloud] （包括）中 [!DNL Target]的各种服务进行交互。如果选择迁移到[!DNL Adobe Experience Platform Web SDK]，请参阅&#x200B;*Web SDK指南*&#x200B;中的[什么是Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。
   >
   >
* **at.js**:与mbox.js相比，at.js JavaScript库具有许多优势。at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。 如果选择迁移到at.js，请参阅[At.js工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[Adobe Target技能生成器：开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
>
>
尽管mbox.js目前受支持（2021年3月31日之前），但自2017年7月起，我们尚未对此库提供功能更新。 通过将所有客户移至[!UICONTROL Adobe Experience PlatformWeb SDK]或at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。

每个页面上的单个 [!DNL mbox.js] 引用可为所有活动提供所需的库。[!DNL mbox.js] 会从每个引用了 [!DNL mbox.js] 文件的页面中调用 [!DNL Target]。这可使 [!DNL Target] 能够执行以下任务：

* 交付 Target 活动
* 跟踪点击次数
* 跟踪大多数成功量度

>[!TIP]
>
>为简化实施过程，您可以在全局标头中引用 [!DNL mbox.js]。

您不需要为该文件维护特定于活动的不同版本。

1. 在您网站上每个页面的 `<head>` 部分中引用 [!DNL mbox.js]。

   `<script src="/ *`directory`*/ *`scripts`*/mbox.js"></script>`

   其中 ` *`directory`*/ *`scripts`*` 是下载 [!DNL mbox.js] 文件后保存该文件的目录。
如果您的页面上已经具有来自旧版实施的 mbox，则仍然可以在新界面中使用这些 mbox。更新的 [!DNL mbox.js] 文件仍然是必需的，但可以使用[!UICONTROL 可视化体验编辑器]为活动选择和编辑这些 mbox。
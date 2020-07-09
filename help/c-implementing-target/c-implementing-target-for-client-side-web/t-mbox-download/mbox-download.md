---
keywords: Implementation;Mbox;download mbox.js;download api;mbox.js api
description: 要使用 Target Standard 或 Target Premium，请添加一行代码以调用 mbox.js。
title: mbox.js 实施
subtopic: Getting Started
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
translation-type: tm+mt
source-git-commit: 322b14629d420601b763fed7597c43a8458b7dbf
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 55%

---


# mbox.js 实施{#mbox-js-implementation}

要使用 Target Standard 或 Target Premium，请添加一行代码以调用 mbox.js。

您可以使用下面两个库引用中的任何一个：[!DNL mbox.js] 或 [!DNL at.js]。[at.js 的好处](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits)阐述了这两个库之间的差异。

>[!NOTE]
>
>**mbox.js弃用**: 2020年8月30日，Adobe Target将不再支持mbox.js库。 2020年8月30日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响目标活动运行的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
>
>尽管目前支持mbox.js，但自2017年7月起，我们便未对此库提供功能更新。 较新的at.js比mbox.js具有许多优势。 at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。
>
>通过将所有客户转移到at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。

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
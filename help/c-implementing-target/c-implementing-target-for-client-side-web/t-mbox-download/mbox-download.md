---
description: 要使用 Target Standard 或 Target Premium，请添加一行代码以调用 mbox.js。
keywords: 实施;Mbox;下载 mbox.js;下载 API;mbox.js API
seo-description: 要使用 Target Standard 或 Target Premium，请添加一行代码以调用 mbox.js。
seo-title: mbox.js 实施
solution: Target
subtopic: 入门指南
title: mbox.js 实施
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# mbox.js 实施{#mbox-js-implementation}

要使用 Target Standard 或 Target Premium，请添加一行代码以调用 mbox.js。

您可以使用下面两个库引用中的任何一个：[!DNL mbox.js] 或 [!DNL at.js]。[at.js 的好处](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits)阐述了这两个库之间的差异。

>[!NOTE]
>
>虽然现在仍支持 mbox.js 库，但是以后不会再提供此库的功能更新。因此，所有客户都应迁移到 at.js。有关更多信息，请参阅[从 mbox.js 迁移到 at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)。

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
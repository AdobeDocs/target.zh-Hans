---
keywords: implementation;mbox；下载mbox.js；下载api;mbox.js api
description: 了解旧版mbox.js的Adobe Target实现。 迁移到Adobe Experience Platform Web SDK(AEP Web SDK)或at.js的最新版本。
title: 如何使用mbox.js实施目标?
feature: at.js
role: 开发人员
exl-id: 105095d7-8e29-413b-a7f4-e46e2e30e91f
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 47%

---

# mbox.js 实施

要使用[!DNL Adobe Target Standard]或[!DNL Target Premium]，请添加一行代码以调用mbox.js。

可以使用以下两个库引用之一：[!DNL Adobe Experience Platform Web SDK]或[!DNL at.js]。 [at.jsex的优](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) 点是mbox.js和at.js库之间的差异。

>[!IMPORTANT]
>
>**mbox.js终止使用**:自2021年3月31日起， [!DNL Adobe Target] 不再支持mbox.js库。2021年3月31日之后，从mbox.js发出的所有调用将轻松失败，并会通过提供默认内容来影响运行[!DNL Target]活动的页面。
>
>我们建议所有客户在此日期前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请参阅[概述：实现客户端web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)的目标。

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

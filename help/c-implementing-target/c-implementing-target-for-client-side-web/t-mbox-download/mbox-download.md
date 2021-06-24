---
keywords: 实施；mbox；下载mbox.js；下载API;mbox.js API
description: 了解旧版mbox.js的Adobe Target实施。 迁移到Adobe Experience Platform Web SDK(AEP Web SDK)或at.js的最新版本。
title: 如何使用mbox.js实施 [!DNL Target] ?
feature: at.js
role: Developer
exl-id: 105095d7-8e29-413b-a7f4-e46e2e30e91f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 65%

---

# mbox.js 实施

要使用[!DNL Adobe Target Standard]或[!DNL Target Premium]，请添加一行代码以调用mbox.js。

您可以使用以下两个库引用中的任何一个：[!DNL Adobe Experience Platform Web SDK]或[!DNL at.js]。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的网站出现任何潜在问题。 有关详细信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

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

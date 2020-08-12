---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox
description: 可通过在网页上引用 Target 库（at.js 或 mbox.js）来实施 Target。
title: 了解 Target JavaScript 库
feature: null
topic: Target
uuid: c8a254c9-afc9-4a55-be01-788c11bef7cc
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 100%

---


# 了解 [!DNL Target]JavaScript 库{#understand-the-target-javascript-libraries}

可通过在网页上引用 [!DNL Target] 库（at.js 或 mbox.js）来实施 [!DNL Target]。

>[!NOTE]
>
>mbox.js 库将不再开发。所有客户都应该从 mbox.js 迁移到 at.js。有关更多信息，请参阅[从 mbox.js 迁移到 at.js](../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)。

## 两个库之间的差异 {#section_40117C78C2F84FECAC4F1BA40CC4F171}

下表说明了这两个库之间的差异：

| 库引用 | 描述 |
|--- |--- |
| at.js | at.js 取代了用于 [!DNL Target] 实施的 mbox.js。<br>使用 at.js 具有许多好处，包括缩短 Web 实施的页面加载时间，增强安全性，在 Google Chrome 中阻止 document.write 警告，以及为单页应用程序提供更好的实施选项，等等。<br>有关更多信息，请参阅 [at.js 实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)。 |
| mbox.js | 在 [!DNL Target] 16.3.1（2016 年 3 月版）之前，[!DNL Target] 需要调用 mbox.js 来创建 [!DNL Target] 交付活动、跟踪点击和跟踪大多数成功量度所需的全局 mbox。此文件包含所有活动所需的库。您不需要为该文件维护特定于活动的不同版本。<br>如果您的页面上已经有来自旧版 [!DNL Target] 实施的封装 mbox，则在新界面中仍然能够使用这些 mbox。更新的 mbox.js 文件仍然是必需的，但可以使用可视化体验编辑器为活动选择和编辑这些 mbox。<br>[!DNL Target] Standard 和 Premium 通过引用 target.js 文件来更新和增补 mbox.js。target.js 文件由 Adobe 托管。通过 target.js 文件，您可以使用可视化体验编辑器编辑任何页面上的内容，即使页面不包含预定义的 mbox 也可编辑。您必须在网站的每个页面上都引用此文件。<br>有关更多信息，请参阅 [mbox.js 实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)。<br>**重要信息&#x200B;**：虽然现在仍支持 mbox.js 库，但是以后不会再提供此库的功能更新。因此，所有客户都应迁移到 at.js。有关更多信息，请参阅[从 mbox.js 迁移到 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br> |

## at.js 和 mbox.js 对页面加载时间的影响 {#section_16630CD0FF0A498EB596A51381366A5A}

很多客户和顾问都想了解 [!DNL at.js] 和 [!DNL mbox.js] 对页面加载时间的影响，特别是对于新用户与旧用户的情况。但遗憾的是，由于每位客户的实施不尽相同，因此很难评测 [!DNL at.js] 或 [!DNL mbox.js] 对页面加载时间的影响并给出具体的数字。

但是，如果页面上存在访客 API，我们便可以更好地了解 [!DNL at.js] 和 [!DNL mbox.js] 对页面加载时间有何影响。

>[!NOTE]
>
>仅当您使用了全局 mbox 时，访客 API 和 [!DNL at.js] 或 [!DNL mbox.js] 才会对页面加载时间造成影响（由于采用了主体隐藏技术）。区域 mbox 不受访客 API 集成的影响。

下表介绍了为新访客和旧访客执行的一系列操作：

### 新访客

1. 加载、解析并执行访客 API。
1. 加载、解析并执行 at.js/mbox.js。
1. 如果已启用全局 mbox 自动创建，则 Target JavaScript 库会执行以下操作：

   * 对访客对象实例化。
   * Target 库尝试检索 Experience Cloud 访客 ID 数据。
   * 由于是新访客，访客 API 会触发对 demdex.net 的跨域请求。
   * 检索 Experience Cloud 访客 ID 数据后，将触发对 Target 的请求。

### 旧访客

1. 加载、解析并执行访客 API。
1. 加载、解析并执行 at.js/mbox.js。
1. 如果已启用全局 mbox 自动创建，则 Target JavaScript 库会执行以下操作：

   * 对访客对象实例化。
   * Target 库尝试检索 Experience Cloud 访客 ID 数据。
   * 访客 API 从 Cookie 中检索数据。
   * 检索 Experience Cloud 访客 ID 数据后，将触发对 Target 的请求。

>[!NOTE]
>
>对于新访客，如果存在访客 API，则 Target 必须进行多次联网，以确保 Target 请求中包含 Experience Cloud 访客 ID 数据。对于旧访客，Target 只会连接到其自身来检索个性化内容。

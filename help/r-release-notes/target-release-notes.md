---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
description: 发行说明，提供有关最新或即将发布的DNL Adobe Target版本的功能、增强和修复的信息。
title: Adobe Target预发行说明
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 5042acd5b646d3debf0d2be79bf317401a98763e

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新时间：2020 年 2 月 18 日**

>[!NOTE]
>
>* 本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
   >
   >
* 括号中的问题编号供 [!DNL Adobe] 内部使用。
   >
   >
* **TLS支持更改**:从2020年3月1日开始，Target将禁用对TLS 1.1和TLS 1.0加密的支持。 传输层安全性 (TLS) 是当前使用的部署最广泛的安全协议，可用于 Web 浏览器和其他需要通过网络安全交换数据的应用程序。需要进行此更改以符合TLS 1.2或更高版本的公认安全合规标准。 检查您当前使用的TLS版本。 如果您的版本低于1.2，请在2020年3月1日之前实施所需的更改，以便继续按预期使用Target。
   >
   >   
   有关可能的影响以及更新实施时可能需要采取的步骤的详细信息，请参阅 [TLS（传输层安全）加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
   >
   >
* **mbox.js弃用**:2020年8月30日，Adobe Target将不再支持mbox.js库。 2020年8月30日之后，从mbox.js发出的所有调用都将失败，并会影响已运行Target活动的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   尽管目前支持mbox.js，但自2017年7月以来，我们尚未对此库提供功能更新。 较新的at.js比mbox.js有许多优势。 除其他优势外，at.js还缩短了Web实施的页面加载时间，提高了安全性，并为单页应用程序提供了更好的实施选项。
   >
   >   
   通过将所有客户迁移到at.js，我们的工程师和支持人员将能够为您提供新功能并为您提供Adobe所期望的支持。


## Target Standard/Premium 20.2.1（2020 年 2 月 19 日） 

>[!IMPORTANT]
>
>请参阅上述关于mbox.js弃用的信息。

此版本包含以下增强功能和修复：

* 修复了客户在执行目录搜索时无法选择集合的问题。 (TGT-36230)
* 修复了通过API创建的条件（但未由在目标UI中创建的活动引用）可能从UI中错误删除的问题。 (TGT-35917)
* 对内容安全策略(CSP)实施了安全改进。 (TGT-36190)
* 修复了在将“属性加权”百分比条滑向最左侧时，导致显示“NaN%”的问题。 (TGT-36211)
* 解决了本地化问题，以便正确显示不同语言的UI文本。

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

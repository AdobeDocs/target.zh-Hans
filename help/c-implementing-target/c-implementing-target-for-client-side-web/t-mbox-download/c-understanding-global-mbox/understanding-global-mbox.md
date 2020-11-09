---
keywords: global mbox;implement mbox.js;implement at.js
description: 有关全局mbox的信息，该名称用于指在您的Adobe Target实施的每个网页顶部进行的单个服务器调用。
title: 了解全局 mbox
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 86%

---


# 了解全局 mbox{#understand-the-global-mbox}

此信息介绍了全局 mbox，该名称用于指代在 [!DNL Adobe Target] 实施中的每个网页顶部发起的单个服务器调用。

默认情况下，全局 mbox 将名为 `target-global-mbox`。如有必要，可以为您的帐户重命名全局 mbox。

常规 mbox（非全局 mbox）和全局 mbox 之间存在以下几点差异：

| 常规 mbox | 全局 mbox |
|--- |--- |
| 常规 mbox 通常使用 `<DIV>` 标记来封装内容。 | 全局 mbox 是“空的”，并未封装任何内容。 |
| 一个常规 mbox 只能交付一个活动中的内容。 | 对全局 mbox 的一个响应可以交付多个活动中的内容。 |

如果通过全局 mbox 或多个常规 mbox 交付多个活动，则 [!DNL Target] 会[确定活动优先级](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)，并按该优先级将活动交付到网页。

使用 [!DNL Target] 函数，可以将其他页面级别数据与全局 mbox 一起发送到 `targetPageParams`。这类似于 mbox 参数功能。有关更多信息，请参阅[将参数传递到全局 Mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5)。

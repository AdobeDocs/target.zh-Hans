---
kewords: redirect;redirect url;send to different page
description: 了解当您想要将访客发送到其他页面而不是在同一页面上显示内容时，如何使用Adobe [!DNL Target] 中的“重定向到URL”选项。
title: 能否将页面重定向到其他URL？
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 80%

---

# 重定向到 URL

如果要将访客发送到其他页面而不是在同一页面上显示内容，请使用[!DNL Adobe Target]中的[!UICONTROL 重定向到URL]选项。

您可能有两个完全不同的页面来进行测试，而非只更改页面中的部分内容。 在此示例中，您的 A/B 测试要比较页面 A 与页面 B。为此，需设置一个包含两个体验的 A/B 测试营销活动：其中一个体验指向默认的页面 A，而另一个体验则重定向到页面 B。在“体验操作”菜单中（可通过单击体验所对应的字母标签找到此菜单），选择&#x200B;**[!UICONTROL 重定向到 URL]**，并指定页面 B 的 URL。该选件会配置为将访客重定向到其他页面。

重定向产品建议执行 JavaScript 代码以重定向浏览器。 由于该产品建议使用了 `window.location.replace();` 方法，因此从中对访客进行重定向的页面不会存储到浏览器历史记录中。 这允许访客仍然使用浏览器中的返回键。

重定向选件具有以下几项限制：

* 对于使用了 A4T 的活动中所包含的重定向选件，您的实施必须满足某些最低要求。 除此之外，还有一些重要信息需要您知悉。 有关更多信息，请参阅[重定向产品建议 - A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
* 使用基于表单的体验编辑器时，不应在页面所包含的 mbox 中使用重定向产品建议。 只应该从 HTML `<head>` 所包含的脚本标记中使用重定向产品建议。 您应该始终使用自动创建的全局 mbox 并为该全局 mbox 设置重定向产品建议。

>[!NOTE]
>
>如果您希望传递登陆页的引荐链接值，建议您使用 HTML 产品建议，而不是重定向产品建议。

要创建重定向产品建议，请执行以下操作：

1. 创建一个体验。
1. 在[!UICONTROL 体验]框架中，单击所需体验的&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)）。
1. 单击&#x200B;**[!UICONTROL 重定向到URL]**。
1. 在“重定向到URL”对话框中，键入URL。
1. 如有需要，选择用于包括当前查询参数的选项。

   如果选中此选项，则访客 URL 中位于 ? 后面的所有内容 都将在进行重定向时被附加到重定向 URL 中。

1. （可选）创建其他规则。

   其他规则可以基于以下任何一项：

   * URL
   * 域
   * 路径
   * 话题标签 (#) 片段
   * 查询
   * mbox 参数

   可以使用 AND 或 OR 将其他规则连接到活动 URL。 您添加的所有规则将使用 AND 进行相互评估。

## 已知问题

* at.js 实施中的重定向活动可能会导致预览 URL 进入循环（重复提供该产品建议）。 您可以改为使用 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)来执行预览和 QA。 此问题不会影响选件的实际交付。 (TGT-23019)

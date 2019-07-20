---
description: 使用 AdBox 在站外实施中交付图像。
keywords: 实施;mbox.js 非 javascript;mbox;Adbox
seo-description: 使用 AdBox 在站外实施中交付图像。
seo-title: 为图像创建 Adbox
solution: Target
subtopic: 入门指南
title: 为图像创建 Adbox
topic: Standard
uuid: 6b1763f7-08de-4bde-9e20-e79b92b02f20
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 为图像创建 Adbox{#create-an-adbox-for-an-image}

使用 AdBox 在站外实施中交付图像。

AdBox 与 mbox 类似，但它由 URL 控制而非 JavaScript。创建的 AdBox 具有特殊的 AdBox URL，此 URL 会将“广告”mbox（或 AdBox）加载到您的 Adobe 帐户中。在活动中可使用此 AdBox 替代 mbox。在电子邮件或其他非 JavaScript 实施中可使用 AdBox URL，而不使用直接图像引用。

如果要查看有关选择正确设置的帮助，请参阅[不基于 JavaScript 的实施](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)。

1. 创建 AdBox URL：

   ```
   https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/
   image?mbox=emailHeroImage123_320x200
   mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif
   ```

   * 其中，`myClientCode` 是您公司的客户端代码。您公司的客户端代码全部为小写字母，且不含任何特殊字符。

      * **at.js**：您的客户端代码在以下位置提供：[!UICONTROL  界面的]设置 &gt; 实施 &gt; 编辑 at.js 设置[!DNL Target]页面的顶部。

      * **mbox.js**：您的客户端代码在以下位置提供：[!UICONTROL 设置 &gt; 实施 &gt; 编辑 Mbox.js 设置]页面的顶部。
   * 其中，`image` 是调用类型。在此例中为图像。

   * 其中，`emailHeroImage123_320x200` 是 AdBox 的名称。

   * 其中，`http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif` 是 mbox 的默认内容。该内容必须是图像。

      这必须是进行了编码的 URL，且必须是绝对引用。You can use the [HTML URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp) to quickly encode your URLs.


1. 为每个替代图像创建[重定向选件](../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)。

   >[!NOTE] {class="- topic/note "}
   >
   >AdBox 必须和重定向选件或默认内容选件共同加载。不接受其他的选件类型。由于 AdBox 是 URL，它只能显示自身接收到的 URL，因此只有重定向选件才适用。

1. 创建活动。

   请参阅[不基于 JavaScript 的实施](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)，以了解如何正确设置来实现您的目标。
1. 完成活动 QA。

   最佳做法是，创建一个虚拟页面，并确认在所有环境中，所有体验、默认内容和报表在所有类型的浏览器上的行为均符合预期。1. 启动活动。

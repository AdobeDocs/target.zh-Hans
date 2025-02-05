---
kewords: redirect;redirect url;send to different page
description: 了解当您希望将访客发送到其他Adobe而不是在同一页上显示内容时，如何使用 [!DNL Target] 中的“重定向到URL”选项。
title: 能否将页面重定向到其他URL？
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 68%

---

# 重定向到 URL

如果要将访客发送到其他页面而不是在同一页面上显示内容，请在[!DNL Adobe Target]中使用[!UICONTROL Redirect to URL]选项。

您可能有两个完全不同的页面来进行测试，而非只更改页面中的部分内容。在本例中，您的A/B测试要比较页面A与页面B。为此，需设置一个包含两个体验的A/B测试营销活动：一个体验指向默认页面A，另一个体验重定向到页面B。在“体验操作”菜单中（可通过单击体验的字母标签找到），选择&#x200B;**[!UICONTROL Redirect to URL]**&#x200B;并指定页面B的URL。该选件会配置为将访客重定向到其他页面。

重定向产品建议执行 JavaScript 代码以重定向浏览器。由于该产品建议使用了 `window.location.replace();` 方法，因此从中对访客进行重定向的页面不会存储到浏览器历史记录中。这允许访客仍然使用浏览器中的返回键。

重定向选件具有以下几项限制：

* 对于使用了 A4T 的活动中所包含的重定向选件，您的实施必须满足某些最低要求。除此之外，还有一些重要信息需要您知悉。有关更多信息，请参阅[重定向产品建议 - A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
* 使用基于表单的体验编辑器时，不应在页面所包含的 mbox 中使用重定向产品建议。只应该从 HTML `<head>` 所包含的脚本标记中使用重定向产品建议。您应该始终使用自动创建的全局 mbox 并为该全局 mbox 设置重定向产品建议。

>[!NOTE]
>
>如果您希望传递登陆页的引荐链接值，建议您使用 HTML 产品建议，而不是重定向产品建议。

要创建重定向产品建议，请执行以下操作：

1. 创建一个体验。
1. 将鼠标悬停在鼠标体验上，然后单击“重定向到URL”图标（![icon_redirect_url图像](assets/icon_redirect_url.png)）。

   ![exp_actions图像](assets/exp_actions.png)

1. 键入 URL。
1. 如有需要，选择用于包括当前查询参数的选项。

   如果选中此选项，则访客 URL 中位于 ? 后面的所有内容都将在进行重定向时被附加到重定向 URL 中。

   默认情况下，此选项处于选中状态。
1. （可选）创建其他规则。

   其他规则可以基于以下任何一项：

   * URL
   * 域
   * 路径
   * 话题标签 (#) 片段
   * 查询
   * mbox 参数

   可以使用 AND 或 OR 将其他规则连接到活动 URL。您添加的所有规则将使用 AND 进行相互评估。

## 已知问题

* at.js 实施中的重定向活动可能会导致预览 URL 进入循环（重复提供该产品建议）。您可以改为使用 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)来执行预览和 QA。此问题不会影响选件的实际交付。(TGT-23019)

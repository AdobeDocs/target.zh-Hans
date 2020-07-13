---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: 有关 Adobe Target 中可导致浏览器重定向到新页面的重定向选件的信息。
title: 创建重定向选件
topic: Standard
uuid: 54336965-a26e-47c3-b3bc-079d3573502a
translation-type: tm+mt
source-git-commit: 32217a752574f671b790880667ac869443778f51
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 97%

---


# 创建重定向选件{#create-redirect-offers}

重定向选件会使浏览器重定向到一个新的页面。

您可能有两个完全不同的页面来进行测试，而非只更改页面中的部分内容。在这种情况下，您的 A/B 测试会比较页面 A 与页面 B。可设置包含两种体验的 A/B 测试营销活动：一种体验指向默认页面 A，另一种体验重定向至页面 B。选件被配置为将访客重定向至不同的页面。

>[!NOTE]
>
>您不能在 ajax mbox 中使用重定向选件 (`mboxUpdate`)。
>
>对于使用了 A4T 的活动中所包含的重定向选件，您的实施必须满足某些最低要求。除此之外，还有一些重要信息需要您知悉。有关更多信息，请参阅[重定向选件 - A4T 常见问题解答](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。

有关如何设置可重定向的体验的信息，请参阅[重定向到 URL](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。

重定向选件执行 JavaScript 代码以重定向浏览器。由于该选件使用了 `window.location.replace();` 方法，因此从中对访客进行重定向的页面不会存储到浏览器历史记录中。这允许访客仍然使用浏览器中的返回键。

>[!NOTE]
>
>如果您希望传递登陆页的引荐链接值，建议您使用 HTML 选件，而不是重定向选件。

**创建重定向选件：**

1. 单击&#x200B;**[!UICONTROL 选件]**，然后选择&#x200B;**[!UICONTROL 代码选件]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 重定向选件]**。
1. 键入选件名称。
1. 输入要重定向到的唯一内容或目标所对应的 URL。该 URL 必须是绝对 URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向选件会引发无限循环。您应确保用户在重定向之后不会被重复授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向选件：

* **包含所有 URL 参数：**&#x200B;如果您希望将之前页面上存在的所有 URL 参数都传播到要重定向到的页面，请选中此复选框。

   例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递 URL 中的动态参数，因为这样才能跟踪顾客是如何到达您的网站：是通过电子邮件、横幅广告、搜索广告还是自然访问。勾选此框后，当您在 URL 框中输入 [!DNL `https://www.mycompany.com/mens.html?emailId=123`] 时，[!DNL `https://www.mycompany.com/mensShirts.html?emailId=123`] 页面上的重定向选件将自动变成 [!DNL `https://www.mycompany.com/mensShirts.html`]。

* **传递 mbox 会话 ID（重定向到其他域时需要选中此选项）：**&#x200B;如果您希望在重定向中自动包含 `sessionId`，请选中此复选框。只有在测试来自于电子邮件的点击或跨域的点击时才需要此功能。`sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

   如果您使用的是第一方和第三方 Cookie 设置，则无需在跨域时传递 mbox 会话 ID。第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

>[!NOTE]
>
>请在启动这些测试前，咨询您的实施顾问。

## 培训视频： 内容存储库(4:56)概 ![述徽章](/help/assets/overview.png)

以下视频包含有关管理内容的信息。

* [Experience Cloud 资产库](https://docs.adobe.com/content/help/en/core-services/interface/assets/creative-cloud.html)与 Target 内容库之间的关联
* 自定义 HTML 选件
* 可视化体验编辑器中的自定义 HTML 选件

>[!VIDEO](https://video.tv.adobe.com/v/17387)

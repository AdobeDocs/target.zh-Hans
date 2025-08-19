---
keywords: 重定向产品建议;创建重定向产品建议;添加 HTML 产品建议;在重定向中传递所有 URL 参数;在重定向中传递 mboxSessionId（仅当要重定向到其他域时才需使用此功能）
description: 了解如何在Adobe [!DNL Target] 中创建重定向选件，以使浏览器重定向到新页面。
title: 如何创建重定向选件？
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 45%

---

# 创建重定向产品建议

[!DNL Adobe Target]中的重定向选件导致浏览器重定向到新页面。

您可能有两个完全不同的页面来进行测试，而非只更改页面中的部分内容。在本例中，您的A/B测试要比较页面A与页面B。为此，需设置一个包含两个体验的A/B测试活动：一个体验指向默认页面A，另一个体验重定向到页面B。该选件会配置为将访客重定向到其他页面。

>[!NOTE]
>
> * 可以在[!UICONTROL Offers] > [!UICONTROL Code Offers]页面或[基于Forms的体验编辑器](/help/main/c-experiences/form-experience-composer.md)中创建重定向选件。 您无法在可视化体验编辑器(VEC)中创建或应用重定向选件。 内容将插入到[!DNL Target]请求位置，因此这些位置可能不适合全局[!DNL Target]请求。
>
>* 您不能在ajax mbox (`mboxUpdate`)中使用重定向选件。
>
>* 对于使用了 A4T 的活动中所包含的重定向选件，您的实施必须满足某些最低要求。除此之外，还有一些重要信息需要您知悉。有关更多信息，请参阅[重定向产品建议 - A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
>
>* 有关如何设置可重定向的体验的信息，请参阅[重定向到 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。

重定向产品建议执行 JavaScript 代码以重定向浏览器。由于该产品建议使用了 `window.location.replace();` 方法，因此从中对访客进行重定向的页面不会存储到浏览器历史记录中。这允许访客仍然使用浏览器中的返回键。

>[!NOTE]
>
>如果您希望传递登陆页的引荐链接值，建议您使用 HTML 产品建议，而不是重定向产品建议。

## 从“代码选件”页面创建重定向选件

1. 单击&#x200B;**[!UICONTROL Offers]**，然后选择&#x200B;**[!UICONTROL Code Offers]**&#x200B;选项卡。

   ![代码选件选项卡](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 单击&#x200B;**[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**。

   ![创建重定向选件对话框](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和其他人在Assets库中快速找到选件。

1. 输入要重定向到的唯一内容或目标所对应的 URL。该 URL 必须是绝对 URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向产品建议会引发无限循环。您应确保用户在重定向之后不会被重复授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向产品建议：

   * **包含所有URL参数：**&#x200B;如果要将上一页中存在的所有URL参数都传播到重定向页面，请滑动切换开关以启用此选项。

     例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递 URL 中的动态参数，因为这样才能跟踪顾客是如何到达您的网站：是通过电子邮件、横幅广告、搜索广告还是自然访问。启用此选项后，当您在URL框中输入的是`https://www.mycompany.com/mens.html?emailId=123`时，页面`https://www.mycompany.com/mensShirts.html?emailId=123`上的重定向选件将自动变为`https://www.mycompany.com/mensShirts.html`。

   * **传递mbox会话ID：**&#x200B;需要重定向到其他域。 如果要自动将`sessionId`包含在重定向中，请滑动切换开关以启用此选项。 仅当测试来自电子邮件的点击或从一个域到另一个域的点击时才需要此功能。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

     如果您使用第一方和第三方Cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击 **[!UICONTROL Save]**。

>[!NOTE]
>
>请在启动这些测试前，咨询您的实施顾问。

## 使用基于表单的体验编辑器创建重定向选件

1. 使用基于[表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)创建活动时，请选择要显示&#x200B;**[!UICONTROL Content]**&#x200B;部分的位置。

   基于表单的体验编辑器中的![内容部分](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 单击&#x200B;**[!UICONTROL Default Content]**&#x200B;下拉列表，然后单击&#x200B;**[!UICONTROL Change Redirect Offer]**。

   ![更改重定向选件选项](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. 单击&#x200B;**[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**。

   ![创建重定向选件对话框](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和其他人在Assets库中快速找到选件。

1. 输入要重定向到的唯一内容或目标所对应的 URL。该 URL 必须是绝对 URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向产品建议会引发无限循环。您应确保用户在重定向之后不会被重复授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向产品建议：

   * **包含所有URL参数：**&#x200B;如果要将上一页中存在的所有URL参数都传播到重定向页面，请滑动切换开关以启用此选项。

     例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递 URL 中的动态参数，因为这样才能跟踪顾客是如何到达您的网站：是通过电子邮件、横幅广告、搜索广告还是自然访问。启用此选项后，当您在URL框中输入的是`https://www.mycompany.com/mens.html?emailId=123`时，页面`https://www.mycompany.com/mensShirts.html?emailId=123`上的重定向选件将自动变为`https://www.mycompany.com/mensShirts.html`。

   * **传递mbox会话ID：**&#x200B;需要重定向到其他域。 如果要自动将`sessionId`包含在重定向中，请滑动切换开关以启用此选项。 仅当测试来自电子邮件的点击或从一个域到另一个域的点击时才需要此功能。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

     如果您使用第一方和第三方Cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击 **[!UICONTROL Save]**。

>[!NOTE]
>
>请在启动这些测试前，咨询您的实施顾问。

## 在活动中使用重定向选件

您必须使用[!UICONTROL Form-Based Experience Composer]应用重定向选件。 您当前无法使用VEC应用重定向选件。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]是非可视化体验和选件创建界面，当可视化体验编辑器不可用或不实用时，它有助于创建在[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] (XT)、[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Recommendations]活动中使用的体验。 例如，您可以使用[!UICONTROL Form-Based Experience Composer]创建使用重定向选件的体验。

1. 在[!UICONTROL Form-Based Experience Composer]中创建或编辑活动。

   有关详细的分步说明，请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)。

1. 指定所需位置并根据需要添加任何受众细化。

1. 单击&#x200B;**[!UICONTROL Content]**&#x200B;部分中的下拉列表，然后单击&#x200B;**[!UICONTROL Change Redirect Offer]**。

   ![更改重定向选件选项](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 从[!UICONTROL Select Remote Offer]对话框中选择所需的重定向选件，然后单击&#x200B;**[!UICONTROL Done]**。

1. 配置完活动。

## 培训视频：基于表单的编辑器![教程徽章](/help/main/assets/tutorial.png)

本视频提供了基于表单的编辑器演示，您可以使用它创建重定向选件。

* 使用基于表单的体验编辑器创建活动
* 了解何时使用基于表单的体验编辑器，何时使用可视化体验编辑器
* 使用细化来定位位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)

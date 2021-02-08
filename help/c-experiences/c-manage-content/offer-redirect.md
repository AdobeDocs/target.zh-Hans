---
keywords: 重定向选件;创建重定向选件;添加 HTML 选件;在重定向中传递所有 URL 参数;在重定向中传递 mboxSessionId（仅当要重定向到其他域时才需使用此功能）
description: '了解如何在Adobe Target创建重定向优惠以使浏览器重定向到新页面。 '
title: 如何创建重定向优惠?
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 48%

---


# 创建重定向选件

重定向[!DNL Adobe Target]中的优惠会导致浏览器重定向到新页面。

您可能有两个完全不同的页面来进行测试，而非只更改页面中的部分内容。在这种情况下，您的A/B测试会比较页面A和页面B。设置一个包含两种体验的A/B测试活动:一个指向默认页面A，另一个指向页面B。优惠配置为将访客重定向到其他页面。

>[!NOTE]
>
> * 重定向优惠可以在[!UICONTROL 优惠] > [!UICONTROL 代码优惠]页面或在[基于Forms的体验书写器](/help/c-experiences/form-experience-composer.md)中创建。 不能在可视体验书写器(VEC)中创建或应用重定向优惠。 内容将插入到[!DNL Target]请求位置，因此这些位置很可能不适合全局[!DNL Target]请求。
   >
   >
* 您不能在 ajax mbox 中使用重定向选件 (`mboxUpdate`)。
   >
   >
* 对于使用了 A4T 的活动中所包含的重定向选件，您的实施必须满足某些最低要求。除此之外，还有一些重要信息需要您知悉。有关更多信息，请参阅[重定向选件 - A4T 常见问题解答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
   >
   >
* 有关如何设置可重定向的体验的信息，请参阅[重定向到 URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。


重定向选件执行 JavaScript 代码以重定向浏览器。由于该选件使用了 `window.location.replace();` 方法，因此从中对访客进行重定向的页面不会存储到浏览器历史记录中。这允许访客仍然使用浏览器中的返回键。

>[!NOTE]
>
>如果您希望传递登陆页的引荐链接值，建议您使用 HTML 选件，而不是重定向选件。

## 从“代码优惠”页创建重定向优惠

1. 单击&#x200B;**[!UICONTROL 选件]**，然后选择&#x200B;**[!UICONTROL 代码选件]**&#x200B;选项卡。

   ![代码优惠选项卡](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 重定向选件]**。

   ![“创建重定向优惠”对话框](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在资产库中快速找到所需的选件。

1. 输入要重定向到的唯一内容或目标所对应的 URL。该 URL 必须是绝对 URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向选件会引发无限循环。您应确保用户在重定向之后不会被重复授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向选件：

   * **包括所有URL参** 数：如果希望上一页上存在的所有URL参数传播到重定向页面，请滑动切换以启用此选项。

      例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递 URL 中的动态参数，因为这样才能跟踪顾客是如何到达您的网站：是通过电子邮件、横幅广告、搜索广告还是自然访问。通过启用此选项，当您在URL框中输入的所有内容为`https://www.mycompany.com/mensShirts.html`时，页面`https://www.mycompany.com/mens.html?emailId=123`上的重定向优惠将自动变为`https://www.mycompany.com/mensShirts.html?emailId=123`。

   * **传递mbox会话ID:** 需要重定向到其他域。如果希望将`sessionId`自动包含在重定向中，请滑动切换以启用此选项。 仅当您测试从电子邮件单击或从一个域到另一个域单击时，才需要此设置。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

      如果您使用第一方和第三方cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>
>请在启动这些测试前，咨询您的实施顾问。

## 使用基于表单的体验书写器创建重定向优惠

1. 使用[基于表单的体验书写器](/help/c-experiences/form-experience-composer.md)创建活动时，选择显示&#x200B;**[!UICONTROL 内容]**&#x200B;部分的位置。

   ![基于表单的体验书写器中的内容部分](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. 单击&#x200B;**[!UICONTROL 默认内容]**&#x200B;下拉列表，然后单击&#x200B;**[!UICONTROL 更改重定向优惠]**。

   ![更改重定向优惠选项](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 重定向选件]**。

   ![“创建重定向优惠”对话框](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在资产库中快速找到所需的选件。

1. 输入要重定向到的唯一内容或目标所对应的 URL。该 URL 必须是绝对 URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向选件会引发无限循环。您应确保用户在重定向之后不会被重复授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向选件：

   * **包括所有URL参** 数：如果希望上一页上存在的所有URL参数传播到重定向页面，请滑动切换以启用此选项。

      例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递 URL 中的动态参数，因为这样才能跟踪顾客是如何到达您的网站：是通过电子邮件、横幅广告、搜索广告还是自然访问。通过启用此选项，当您在URL框中输入的所有内容为`https://www.mycompany.com/mensShirts.html`时，页面`https://www.mycompany.com/mens.html?emailId=123`上的重定向优惠将自动变为`https://www.mycompany.com/mensShirts.html?emailId=123`。

   * **传递mbox会话ID:** 需要重定向到其他域。如果希望将`sessionId`自动包含在重定向中，请滑动切换以启用此选项。 仅当您测试从电子邮件单击或从一个域到另一个域单击时，才需要此设置。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

      如果您使用第一方和第三方cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>
>请在启动这些测试前，咨询您的实施顾问。

## 在活动中使用重定向优惠

必须使用[!UICONTROL 基于表单的体验书写器]应用重定向优惠。 当前无法使用VEC应用重定向优惠。

[!DNL Adobe Target][!UICONTROL 基于表单的体验书写器]是非可视体验和优惠创建界面，在创建用于[!UICONTROL A/B测试]、[!UICONTROL 体验定位](XT)、[!UICONTROL Automated Personalization](AP)的体验中非常有用)和[!UICONTROL Recommendations]活动。 例如，您可以使用[!UICONTROL 基于表单的体验书写器]创建使用重定向优惠的体验。

1. 在[!UICONTROL 基于表单的体验书写器]中创建或编辑活动。

   有关详细的分步说明，请参阅[基于表单的体验书写器](/help/c-experiences/form-experience-composer.md)。

1. 指定所需的位置并根据需要添加任何受众细化。

1. 单击&#x200B;**[!UICONTROL Content]**&#x200B;部分的下拉列表，然后单击&#x200B;**[!UICONTROL 更改重定向优惠]**。

   ![更改重定向优惠选项](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 从[!UICONTROL 选择远程优惠]对话框中选择所需的重定向优惠，然后单击&#x200B;**[!UICONTROL 完成]**。

1. 完成活动配置。

## 培训视频：基于表单的书写器![教程徽章](/help/assets/tutorial.png)

此视频提供了基于表单的书写器的演示，您可以使用它创建重定向优惠。

* 使用基于表单的体验编辑器创建活动
* 了解何时使用基于表单的体验编辑器，何时使用可视化体验编辑器
* 使用细化来定位位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)

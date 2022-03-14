---
keywords: 重定向选件;创建重定向选件;添加 HTML 选件;在重定向中传递所有 URL 参数;在重定向中传递 mboxSessionId（仅当要重定向到其他域时才需使用此功能）
description: '了解如何在Adobe中创建重定向选件 [!DNL Target] 以使浏览器重定向到新页面。 '
title: 如何创建重定向选件？
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 48%

---

# 创建重定向选件

中的重定向选件 [!DNL Adobe Target] 导致浏览器重定向到新页面。

您可能有两个完全不同的页面来进行测试，而非只更改页面中的部分内容。在这种情况下，您的A/B测试会比较页面A与页面B。请设置一个包含两个体验的A/B测试活动：一个选件指向默认页面A，而另一个则重定向到页面B。该选件配置为将访客重定向到其他页面。

>[!NOTE]
>
> * 可以在 [!UICONTROL 选件] > [!UICONTROL 代码选件] 页面或 [基于Forms的体验编辑器](/help/main/c-experiences/form-experience-composer.md). 无法在可视化体验编辑器(VEC)中创建或应用重定向选件。 内容将插入 [!DNL Target] 请求位置，因此这些位置很可能不适合全局 [!DNL Target] 请求。
>
>* 您不能在 ajax mbox 中使用重定向选件 (`mboxUpdate`)。
>
>* 对于使用了 A4T 的活动中所包含的重定向选件，您的实施必须满足某些最低要求。除此之外，还有一些重要信息需要您知悉。有关更多信息，请参阅[重定向选件 - A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
>
>* 有关如何设置可重定向的体验的信息，请参阅[重定向到 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。


重定向选件执行 JavaScript 代码以重定向浏览器。由于该选件使用了 `window.location.replace();` 方法，因此从中对访客进行重定向的页面不会存储到浏览器历史记录中。这允许访客仍然使用浏览器中的返回键。

>[!NOTE]
>
>如果您希望传递登陆页的引荐链接值，建议您使用 HTML 选件，而不是重定向选件。

## 从代码选件页面创建重定向选件

1. 单击&#x200B;**[!UICONTROL 选件]**，然后选择&#x200B;**[!UICONTROL 代码选件]**&#x200B;选项卡。

   ![代码选件选项卡](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 重定向选件]**。

   ![“创建重定向选件”对话框](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在资产库中快速找到所需的选件。

1. 输入要重定向到的唯一内容或目标所对应的 URL。该 URL 必须是绝对 URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向选件会引发无限循环。您应确保用户在重定向之后不会被重复授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向选件：

   * **包括所有URL参数：** 如果您希望将上一页面存在的所有URL参数都传播到重定向的页面，请滑动切换开关以启用此选项。

      例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递 URL 中的动态参数，因为这样才能跟踪顾客是如何到达您的网站：是通过电子邮件、横幅广告、搜索广告还是自然访问。启用此选项后，您的重定向选件即会显示在页面上 `https://www.mycompany.com/mens.html?emailId=123` 将自动变为 `https://www.mycompany.com/mensShirts.html?emailId=123` 当您在URL框中输入的 `https://www.mycompany.com/mensShirts.html`.

   * **传递mbox会话ID:** 重定向到其他域时需要。 如果您希望 `sessionId` 自动包含在重定向中。 仅当您测试来自电子邮件的点击量或跨域的点击量时，才需要此功能。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

      如果您使用第一方和第三方Cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>
>请在启动这些测试前，咨询您的实施顾问。

## 使用基于表单的体验编辑器创建重定向选件

1. 在使用 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，选择显示 **[!UICONTROL 内容]** 中。

   ![基于表单的体验编辑器中的“内容”部分](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 单击 **[!UICONTROL 默认内容]** 下拉列表，然后单击 **[!UICONTROL 更改重定向选件]**.

   ![更改重定向选件选项](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 重定向选件]**。

   ![“创建重定向选件”对话框](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在资产库中快速找到所需的选件。

1. 输入要重定向到的唯一内容或目标所对应的 URL。该 URL 必须是绝对 URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向选件会引发无限循环。您应确保用户在重定向之后不会被重复授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向选件：

   * **包括所有URL参数：** 如果您希望将上一页面存在的所有URL参数都传播到重定向的页面，请滑动切换开关以启用此选项。

      例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递 URL 中的动态参数，因为这样才能跟踪顾客是如何到达您的网站：是通过电子邮件、横幅广告、搜索广告还是自然访问。启用此选项后，您的重定向选件即会显示在页面上 `https://www.mycompany.com/mens.html?emailId=123` 将自动变为 `https://www.mycompany.com/mensShirts.html?emailId=123` 当您在URL框中输入的 `https://www.mycompany.com/mensShirts.html`.

   * **传递mbox会话ID:** 重定向到其他域时需要。 如果您希望 `sessionId` 自动包含在重定向中。 仅当您测试来自电子邮件的点击量或跨域的点击量时，才需要此功能。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

      如果您使用第一方和第三方Cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>
>请在启动这些测试前，咨询您的实施顾问。

## 在活动中使用重定向选件

您必须使用 [!UICONTROL 基于表单的体验编辑器]. 当前无法使用VEC应用重定向选件。

的 [!DNL Adobe Target] [!UICONTROL 基于表单的体验编辑器] 是一个非可视化体验和选件创建界面，在创建要在中使用的体验时非常有用 [!UICONTROL A/B测试], [!UICONTROL 体验定位] (XT)、 [!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL Recommendations] 活动。 例如，您可以使用 [!UICONTROL 基于表单的体验编辑器] 创建使用重定向选件的体验。

1. 在 [!UICONTROL 基于表单的体验编辑器].

   请参阅 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md) 详细的分步说明。

1. 指定所需的位置并根据需要添加任何受众细化。

1. 单击 **[!UICONTROL 内容]** ，然后单击 **[!UICONTROL 更改重定向选件]**.

   ![更改重定向选件选项](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 从 [!UICONTROL 选择远程选件] 对话框，然后单击 **[!UICONTROL 完成]**.

1. 完成活动配置。

## 培训视频：基于表单的编辑器 ![教程徽章](/help/main/assets/tutorial.png)

此视频演示了基于表单的编辑器，您可以使用该编辑器创建重定向选件。

* 使用基于表单的体验编辑器创建活动
* 了解何时使用基于表单的体验编辑器，何时使用可视化体验编辑器
* 使用细化来定位位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)

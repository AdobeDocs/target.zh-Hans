---
keywords: 重定向选件；创建重定向选件；添加html选件；在重定向中传递所有URL参数
description: 了解如何创建重定向选件以无缝地引导浏览器浏览新页面。
title: 如何创建重定向选件？
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 25%

---

# 创建重定向选件

了解如何创建重定向选件以无缝地引导浏览器浏览新页面。

您可能有两个完全不同的页面来进行测试，而非只更改页面中的部分内容。在本例中，您的A/B测试比较了页面A与页面B。为此，需设置一个包含两个体验的[!UICONTROL A/B Test]活动：一个体验指向默认页面A，另一个体验重定向到页面B。该选件会配置为将访客重定向到其他页面。

>[!NOTE]
>
> * 可以在[!UICONTROL Offers] > [!UICONTROL Code Offers]页面或[基于Forms的体验编辑器](/help/main/c-experiences/form-experience-composer.md)中创建重定向选件。 您不能在[!UICONTROL Visual Experience Composer] (VEC)中创建或应用重定向选件。 内容被插入到[!DNL Target]请求位置，因此这些位置可能不适合全局[!DNL Target]请求。
>
>* 您不能在AJAX mbox (`mboxUpdate`)中使用重定向选件。
>
>* 对于使用[[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活动中的重定向选件，您的实施必须满足某些最低要求。 除此之外，还有一些重要信息需要您知悉。请参阅[重定向选件 — A4T常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
>
>* 有关如何设置可重定向的体验的信息，请参阅[重定向到 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。

重定向选件执行 JavaScript 代码以重定向浏览器。由于该选件使用了 `window.location.replace();` 方法，因此从中对访客进行重定向的页面不会存储到浏览器历史记录中。此流程允许访客在其浏览器中使用返回按钮。

>[!NOTE]
>
>如果要传递登陆页面的反向链接值，请使用HTML选件，而不是重定向选件。

## 从[!UICONTROL Code Offers]页面创建重定向选件

1. 单击&#x200B;**[!UICONTROL Offers]**，然后选择&#x200B;**[!UICONTROL Code Offers]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**。
1. 为选件提供一个描述性名称。

   描述性名称可帮助您和其他人在[!UICONTROL Assets]库中快速找到该选件。

1. （视情况而定）如果您拥有[Target Premium帐户](/help/main/c-intro/intro.md#premium)，请选择所需的[工作区](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)。

1. 为要重定向到的唯一内容或目标指定URL。 此URL必须是绝对URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向选件会引发无限循环。确保用户在重定向后不会被重新授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向选件：

   * **[!UICONTROL Include all URL parameters]：**&#x200B;如果您希望将上一页中存在的所有URL参数都传播到重定向页面，请启用此选项。

     例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递URL中的动态参数，因为此方法可跟踪用户是通过电子邮件、横幅广告、搜索广告还是自然方式访问您的网站。 启用此选项后，当您在URL框中输入的是`https://www.mycompany.com/mensShirts.html`时，页面`https://www.mycompany.com/mens.html?emailId=123`上的重定向选件将自动变为`https://www.mycompany.com/mensShirts.html?emailId=123`。

   * **[!UICONTROL Pass mbox session ID]：**&#x200B;需要重定向到其他域。 如果要自动将`sessionId`包含在重定向中，请滑动切换开关以启用此选项。 只有在测试来自电子邮件的点击或从一个域到另一个域的点击时才需要此选项。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

     如果您使用第一方和第三方Cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击 **[!UICONTROL Create]**。

>[!IMPORTANT]
>
>请在启动这些测试之前咨询您的实施顾问。

## 使用[!UICONTROL Form-Based Experience Composer]创建重定向选件

1. 使用基于[表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)创建活动时，请选择要显示&#x200B;**[!UICONTROL Content]**&#x200B;部分的位置。
1. 单击&#x200B;**[!UICONTROL Content]**&#x200B;下拉列表，单击&#x200B;**[!UICONTROL List]**&#x200B;图标（![列表](/help/main/assets/icons/MoreSmallList.svg)），然后单击&#x200B;**[!UICONTROL Change Redirect Offer]**。
1. 单击&#x200B;**[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**。
1. 为选件提供一个描述性名称。

   描述性名称可帮助您和其他人在[!UICONTROL Assets]库中快速找到该选件。

1. 为要重定向到的唯一内容或目标指定URL。 此URL必须是绝对URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向选件会引发无限循环。确保用户在重定向后不会被重新授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向选件：

   * **[!UICONTROL Include all URL parameters]：**&#x200B;如果要将上一页中存在的所有URL参数都传播到重定向页面，请通过幻灯片切换启用此选项。

     例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递URL中的动态参数，因为此方法可跟踪用户是通过电子邮件、横幅广告、搜索广告还是自然方式访问您的网站。 启用此选项后，当您在URL框中输入的是`https://www.mycompany.com/mensShirts.html`时，页面`https://www.mycompany.com/mens.html?emailId=123`上的重定向选件将自动变为`https://www.mycompany.com/mensShirts.html?emailId=123`。

   * **[!UICONTROL Pass mbox session ID]：**&#x200B;需要重定向到其他域。 如果要自动将`sessionId`包含在重定向中，请滑动切换开关以启用此选项。 只有在测试来自电子邮件的点击或从一个域到另一个域的点击时才需要此选项。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

     如果您使用第一方和第三方Cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击 **[!UICONTROL Create]**。

>[!IMPORTANT]
>
>请在启动这些测试之前咨询您的实施顾问。

## 在活动中使用重定向选件

使用[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)应用重定向选件。 您当前无法使用[!UICONTROL Visual Experience Composer] (VEC)应用重定向选件。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]是非可视化体验和选件创建界面，当[!UICONTROL Visual Experience Composer]不可用或不实用时，它有助于创建在[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] (XT)、[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Recommendations]活动中使用的体验。 例如，您可以使用[!UICONTROL Form-Based Experience Composer]创建使用重定向选件的体验。

1. 在[!UICONTROL Form-Based Experience Composer]中创建或编辑活动。

   有关详细的分步说明，请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)。

1. 指定所需位置并根据需要添加任何受众细化。

1. 单击&#x200B;**[!UICONTROL Content]**&#x200B;下拉列表，单击&#x200B;**[!UICONTROL List]**&#x200B;图标（![列表](/help/main/assets/icons/MoreSmallList.svg)），然后单击&#x200B;**[!UICONTROL Change Redirect Offer]**。
1. 从[!UICONTROL Select Redirect Offer]对话框中选择所需的重定向选件，然后单击&#x200B;**[!UICONTROL Add]**。
1. 配置完活动。

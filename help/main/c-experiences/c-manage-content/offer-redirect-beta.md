---
keywords: 重定向选件;创建重定向选件;添加 HTML 选件;在重定向中传递所有 URL 参数;在重定向中传递 mboxSessionId（仅当要重定向到其他域时才需使用此功能）
description: 了解如何在中创建重定向选件 [!DNL Target] 以使浏览器重定向到新页面。
title: 如何创建重定向选件？
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
hide: true
hidefromtoc: true
source-git-commit: bd19686d2aa716af64f520fb0be798a300ed9fa3
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 31%

---

# 创建重定向选件

在中创建重定向选件 [!DNL Adobe Target] 以使浏览器重定向到新页面。

>[!NOTE]
>
>本文包含有关对的更新信息 [!DNL Target] 当前为测试版计划一部分的用户界面。 此 [!DNL Adobe Target] 团队经常为特定客户启用新功能以进行测试和提供反馈。 在测试期结束后，将为所有客户启用这些功能 [!DNL Target Standard/Premium] 发行版本和发行说明中宣布。

您可能有两个完全不同的页面来进行测试，而非只更改页面中的部分内容。在这种情况下，您的A/B测试会将页面A与页面B进行比较。设置 [!UICONTROL A/B Test] 活动，其中包含两个体验：一个指向默认页面A，另一个重定向到页面B。该选件会配置为将访客重定向到其他页面。

>[!NOTE]
>
> * 可于以下网址创建重定向选件： [!UICONTROL Offers] > [!UICONTROL Code Offers] 页面或中的 [基于Forms的体验编辑器](/help/main/c-experiences/form-experience-composer.md). 您无法在中创建或应用重定向选件 [!UICONTROL Visual Experience Composer] (VEC)。 内容将插入到 [!DNL Target] 请求位置，因此这些位置可能不适合全局 [!DNL Target] 请求。
>
>* 您不能在AJAX mbox中使用重定向选件(`mboxUpdate`)。
>
>* 对于使用Analytics作为报表源(A4T)的活动中的重定向选件，您的实施必须满足某些最低要求。 除此之外，还有一些重要信息需要您知悉。有关更多信息，请参阅[重定向选件 - A4T 常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
>
>* 有关如何设置可重定向的体验的信息，请参阅[重定向到 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。

重定向选件执行 JavaScript 代码以重定向浏览器。由于该选件使用了 `window.location.replace();` 方法，因此从中对访客进行重定向的页面不会存储到浏览器历史记录中。此流程允许访客在其浏览器中使用返回按钮。

>[!NOTE]
>
>如果要传递登陆页面的反向链接值，请使用HTML选件，而不是重定向选件。

## 从创建重定向选件 [!UICONTROL Code Offers] 页面

1. 单击 **[!UICONTROL Offers]**，然后选择 **[!UICONTROL Code Offers]** 选项卡。

   ![“代码选件”选项卡](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. 单击 **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.

   ![“创建重定向选件”对话框](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer-new.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和其他人在 [!UICONTROL Assets] 库。

1. （视情况而定）如果您拥有 [Target Premium帐户](/help/main/c-intro/intro.md#premium)，选择所需的 [工作区](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. 为要重定向到的唯一内容或目标指定URL。 此URL必须是绝对URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向选件会引发无限循环。确保用户在重定向后不会被重新授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向选件：

   * **包含所有URL参数：** 如果要将上一页中存在的所有URL参数都传播到重定向页面，请滑动切换开关以启用此选项。

     例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递 URL 中的动态参数，因为这样才能跟踪顾客是如何到达您的网站：是通过电子邮件、横幅广告、搜索广告还是自然访问。启用此选项后，页面上的重定向选件将会显示 `https://www.mycompany.com/mens.html?emailId=123` 自动变为 `https://www.mycompany.com/mensShirts.html?emailId=123` 当您在URL框中输入的是 `https://www.mycompany.com/mensShirts.html`.

   * **传递mbox会话ID：** 需要重定向到其他域。 滑动切换开关以启用此选项(如果您希望 `sessionId` 自动包含在重定向中。 只有在测试来自电子邮件的点击或从一个域到另一个域的点击时才需要此选项。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

     如果您使用第一方和第三方Cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击 **[!UICONTROL Create]**。

>[!NOTE]
>
>在启动这些测试之前，请咨询您的实施顾问。

## 使用创建重定向选件 [!UICONTROL Form-Based Experience Composer]

1. 在使用创建活动时 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，选择要显示的位置 **[!UICONTROL Content]** 部分。

   ![基于表单的体验编辑器中的“内容”部分](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 单击 **[!UICONTROL Default Content]** 下拉列表，然后单击 **[!UICONTROL Change Redirect Offer]**.

   ![更改重定向选件选项](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. 单击 **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![“创建重定向选件”对话框](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和其他人在 [!UICONTROL Assets] 库。

1. 为要重定向到的唯一内容或目标指定URL。 此URL必须是绝对URL。

   >[!NOTE]
   >
   >如果重定向 URL 也使用户符合同一活动的参加条件，则重定向选件会引发无限循环。确保用户在重定向后不会被重新授予该活动的资格。

1. 选择以下所需选项以自定义您的重定向选件：

   * **包含所有URL参数：** 如果要将上一页中存在的所有URL参数都传播到重定向页面，请滑动切换开关以启用此选项。

     例如，您希望将顾客直接从男士服装页面重定向到男士衬衫类别页面。您还希望传递 URL 中的动态参数，因为这样才能跟踪顾客是如何到达您的网站：是通过电子邮件、横幅广告、搜索广告还是自然访问。启用此选项后，页面上的重定向选件将会显示 `https://www.mycompany.com/mens.html?emailId=123` 自动变为 `https://www.mycompany.com/mensShirts.html?emailId=123` 当您在URL框中输入的是 `https://www.mycompany.com/mensShirts.html`.

   * **传递mbox会话ID：** 需要重定向到其他域。 滑动切换开关以启用此选项(如果您希望 `sessionId` 自动包含在重定向中。 只有在测试来自电子邮件的点击或从一个域到另一个域的点击时才需要此选项。 `sessionId` 与访客的 Cookie 相匹配，以便能够继续跟踪访客并显示相应的内容。

     如果您使用第一方和第三方Cookie设置，则跨域时无需传递mbox会话ID。 第三方 Cookie 中会一直保留此 ID，因此不必在 URL 中传递此 ID。

1. 单击 **[!UICONTROL Save]**。

>[!NOTE]
>
>在启动这些测试之前，请咨询您的实施顾问。

## 在活动中使用重定向选件

您必须使用应用重定向选件 [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md). 您当前不能使用应用重定向选件 [!UICONTROL Visual Experience Composer] (VEC)。

此 [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] 是一个非可视化体验和选件创建界面，在创建在中使用的体验时非常有用。 [!UICONTROL A/B Tests]， [!UICONTROL Experience Targeting] (XT)， [!UICONTROL Automated Personalization] (AP)，和 [!UICONTROL Recommendations] 活动当可视化体验编辑器不可用或不实用时。 例如，您可以使用 [!UICONTROL Form-Based Experience Composer] 以创建使用重定向选件的体验。

1. 在中创建或编辑活动 [!UICONTROL Form-Based Experience Composer].

   请参阅 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md) 详细的分步说明。

1. 指定所需位置并根据需要添加任何受众细化。

1. 单击 **[!UICONTROL Content]** 部分，然后单击 **[!UICONTROL Change Redirect Offer]**.

   ![更改重定向选件选项](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 从中选择所需的重定向选件 [!UICONTROL Select Remote Offer] 对话框，然后单击 **[!UICONTROL Done]**.

1. 配置完活动。

## 培训视频：基于表单的编辑器 ![教程徽章](/help/main/assets/tutorial.png)

本视频演示了 [!UICONTROL Form-Based Experience Composer]，可用于创建重定向选件。

* 使用创建活动 [!UICONTROL Form-Based Experience Composer]
* 了解何时使用 [!UICONTROL Form-Based Experience Composer] 对比 [!UICONTROL Visual Experience Composer]
* 使用细化来定位位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)
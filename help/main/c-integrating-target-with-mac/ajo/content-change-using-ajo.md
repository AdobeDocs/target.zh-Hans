---
keywords: 优化；个性化；adobe journey optimizer；ajo；用例；方案；内容更改/ab测试；配置文件属性；更改图像；交换图像
description: 在Adobe Journey Optimizer中解锁有效A/B测试内容更改的密钥
title: 通过 [!DNL Adobe Journey Optimizer]中的A/B测试更改内容
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: bbf56b2d041ea6537116d900278242a7a679dedd
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 2%

---

# 通过[!DNL Adobe Journey Optimizer]中的A/B测试更改内容

此使用案例可帮助您解锁密钥，以便在[!DNL Adobe Journey Optimizer]中有效A/B测试内容更改。

## 场景

一家服装公司通过测试各种图像并根据用户档案属性使用用户的名字对营销活动登陆页面进行个性化设置，从而提高了转化率。

## 优势和价值

* **优化内容有效性**：发现哪些内容变体和元素最能引起客户的共鸣，从而提高参与度和转化率。
* **数据驱动型决策**：利用数据在内容策略中做出明智的决策，从而确保产生最大影响。
* **个性化用户体验**：定制内容以满足所有受众区段的独特偏好和需求。

## 分步说明

执行以下步骤以通过测试各种图像并使用用户的名字个性化消息来优化网页：

1. 在[!DNL Adobe Journey Optimizer]中，单击左边栏中的&#x200B;**促销活动**&#x200B;以显示[!UICONTROL Campaigns]页面。

   ![突出显示了“营销活动”选项卡的Adobe Journey Optimizer登陆页面。](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. 单击[!UICONTROL Campaigns]页面右上角的&#x200B;**[!UICONTROL Create Campaign]**。

1. 选择&#x200B;**[!UICONTROL Scheduled - Marketing]**（默认），然后单击&#x200B;**创建**&#x200B;以显示[!UICONTROL Campaign]详细信息页面。

   Adobe Journey Optimizer中的![促销活动详细信息页面](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. 为营销活动提供描述性名称和可选描述。

1. （视情况而定）单击&#x200B;**[!UICONTROL Select Audience]**&#x200B;并选择所需的受众。

   对于此用例，我们选择为所有访客激活营销活动（默认）。

1. 从&#x200B;**[!UICONTROL Action]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Web]**，然后选择或创建新的Web配置。

   Web配置或渠道界面是由系统管理员定义的配置。 Web配置包含用于发送消息的所有技术参数，如标头参数、子域、移动应用程序等。

   有关详细信息，请参阅&#x200B;*Journey Optimizer文档*&#x200B;中的[设置渠道平面](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank}。

1. 单击&#x200B;**[!UICONTROL Edit Content]**&#x200B;以在[!DNL Journey Optimizer] Web设计器中打开您的网站。

   ![LUMA网站上的瑜伽登陆页面](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. 单击右边栏中的&#x200B;**[!UICONTROL Edit Web Page]**。

   ![在瑜伽登陆页面上编辑内容页面](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. 要更改主页图像，请单击要更改的图像，然后单击&#x200B;**[!UICONTROL Choose Image]**&#x200B;按钮。

   ![选择图像按钮](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. 浏览并选择所需的图像，然后单击&#x200B;**[!UICONTROL Use This Image]**。

   ![瑜伽页面上的新英雄图像](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. 要使用配置文件属性以用户的名字个性化邮件，请单击要个性化的文本，然后单击“**[!UICONTROL Add Personalization]**”以显示“[!UICONTROL Add Personalization]”页面。

   ![添加Personalization按钮。](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

1. 搜索并选择“名字”配置文件属性，根据需要调整文本，然后单击&#x200B;**[!UICONTROL Save]**。

   ![为名称](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)添加配置文件属性

   有关详细信息，请参阅&#x200B;*Journey Optimizer文档*&#x200B;中的[个性化编辑器入门](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank}。

1. 单击左上角的返回箭头可返回到Web设计器。

   ![后退箭头](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. 单击&#x200B;**[!UICONTROL Review to Activate]**，确保一切按预期显示，然后单击&#x200B;**激活**。

>[!MORELIKETHIS]
>
>在&#x200B;*Journey Optimizer文档*&#x200B;中[编辑Web内容](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank}
>[*Journey Optimizer文档*&#x200B;中的操作方法视频](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/web-spa#video){target=_blank}
>[在&#x200B;*Journey OptimizerTutorials*&#x200B;中创建营销活动](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank}


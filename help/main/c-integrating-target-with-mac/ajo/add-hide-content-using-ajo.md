---
keywords: 优化；个性化；adobe journey optimizer；ajo；用例；方案；添加内容；隐藏内容；添加组件；隐藏组件
description: 了解如何使用 [!DNL Adobe Journey Optimizer]在网页上添加或隐藏组件。
title: 在 [!DNL Adobe Journey Optimizer]中的网页中添加或隐藏组件
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: 8c4fba88-908e-4742-ac4b-bdf7f4c882db
source-git-commit: 52f11998149cddeb4245a0f07280562d79332a04
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 2%

---

# 向网页添加或隐藏组件

此使用案例可帮助您解锁密钥，以便在[!DNL Adobe Journey Optimizer]中有效A/B测试内容更改。

此用例演示了如何使用[而不是](/help/main/c-activities/t-test-ab/test-ab.md)执行熟悉的任务，例如对[!DNL Journey Optimizer]A/B测试活动[!DNL Adobe Target]执行A/B测试。

此使用案例旨在演示如何使用[!DNL Adobe Target]执行熟悉的任务，使用[A/B测试活动](/help/main/c-activities/t-test-ab/test-ab.md)但使用[!DNL Journey Optimizer]执行A/B测试。

## 优势和价值

* **增强用户参与度**：使用强调相关信息（如促销活动）的优化页面设计吸引用户的注意力。
* **提高可发现性**：从战略上在Web或移动应用程序上放置新组件或内容，以简化操作并增强导航。
* **增加其他接触点**：有效地引导用户了解转化事件和目标以加快业务影响。

## 可能的情况

* 一家金融服务公司计划在其主页上添加一个新图块，以便快速访问贷款计算器，减少搜索时间，并增加贷款申请。

* 一家服装公司通过在网页上添加新的call-to-action按钮来提高转化率。

## 步骤

>[!NOTE]
>
>此部分中的说明突出显示更改图像以及使用用户档案属性个性化文本消息的必要步骤。 有关[!DNL Journey Optimizer] Web设计器中可用选项的详细信息，请参阅[Journey Optimizer文档](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}中的&#x200B;*使用Web设计器*。
>
>页面底部的视频特别有用。

执行以下步骤以添加组件或隐藏网页上的组件：

1. 在[!DNL Adobe Journey Optimizer]中，单击左边栏中的&#x200B;**促销活动**&#x200B;以显示[!UICONTROL Campaigns]页面。

   ![突出显示了“营销活动”选项卡的Adobe Journey Optimizer登陆页面。](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. 单击&#x200B;**[!UICONTROL Create Campaign]**&#x200B;页面右上角的[!UICONTROL Campaigns]。

1. 选择&#x200B;**[!UICONTROL Scheduled - Marketing]**（默认），然后单击&#x200B;**创建**&#x200B;以显示[!UICONTROL Campaign]详细信息页面。

   Adobe Journey Optimizer中的![促销活动详细信息页面](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;部分中，为营销策划提供描述性名称和可选描述。

1. （视情况而定）在&#x200B;**[!UICONTROL Audience]**&#x200B;部分中，单击&#x200B;**[!UICONTROL Select Audience]**&#x200B;并选择所需的受众。

   对于此用例，您可以激活[!UICONTROL All Visitors]的营销活动（默认）。

1. 在&#x200B;**[!UICONTROL Action]**&#x200B;部分中，从&#x200B;**[!UICONTROL Web]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Action]**，然后选择或创建新的Web配置。

   Web配置或渠道界面是由系统管理员定义的配置。 Web配置包含用于发送消息的所有技术参数，如标头参数、子域、移动应用程序等。

   有关详细信息，请参阅[Journey Optimizer文档](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank}中的&#x200B;*设置渠道平面*。

1. 在&#x200B;**[!UICONTROL Action]**&#x200B;部分中，单击&#x200B;**[!UICONTROL Edit Content]**&#x200B;以在[!DNL Journey Optimizer] Web设计器中打开您的网站。

   ![LUMA网站上的瑜伽登陆页面](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. 要添加隐藏元素，请单击右边栏中的&#x200B;**[!UICONTROL Edit Web Page]**。

1. 单击要隐藏的元素，然后单击右边栏中的[!UICONTROL Hide]按钮。

   右边栏显示您可以对选定元素执行的选项。 这些选项会因所选的元素而异。

   ![隐藏元素按钮](/help/main/c-integrating-target-with-mac/ajo/assets/hide-element.png)

1. 单击左上角的返回箭头可返回到Web设计器。

   ![后退箭头](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. 单击&#x200B;**[!UICONTROL Review to Activate]**，确保一切按预期显示，然后单击&#x200B;**激活**。

## 查看报告

单击[!UICONTROL Reports]按钮，然后单击所需的报告周期：

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

有关详细信息，请参阅[Journey Optimizer文档](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank}中的&#x200B;*开始使用新的报表接口*。

>[!MORELIKETHIS]
>
>在[Journey Optimizer文档](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}中&#x200B;*使用Web设计器*
>>[在](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank}Journey Optimizer教程&#x200B;*中创建营销活动*

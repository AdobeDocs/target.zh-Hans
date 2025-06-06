---
keywords: 优化；个性化；adobe journey optimizer；ajo；用例；方案；内容更改/ab测试；配置文件属性；更改图像；交换图像
description: 在Adobe Journey Optimizer中解锁有效A/B测试内容更改的密钥
title: 通过 [!DNL Adobe Journey Optimizer]中的A/B测试更改内容
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: e5aed7cd-7701-4133-ac7c-98e528c8a763
source-git-commit: b66abe9649f8c257891c1cd8e5736b7f91501c13
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# 通过[!DNL Adobe Journey Optimizer]中的A/B测试更改内容

此使用案例可帮助您解锁密钥，以便在[!DNL Adobe Journey Optimizer]中有效A/B测试内容更改。

此用例演示了如何使用[!DNL Journey Optimizer]而不是[!DNL Adobe Target]执行熟悉的任务，例如在[!DNL Adobe Target]中对[A/B测试活动](/help/main/c-activities/t-test-ab/test-ab.md)进行A/B测试。

## 优势和价值

* **优化内容有效性**：发现哪些内容变体和元素最能引起客户的共鸣，从而提高参与度和转化率。
* **数据驱动型决策**：利用数据在内容策略中做出明智的决策，从而确保产生最大影响。
* **个性化用户体验**：定制内容以满足所有受众区段的独特偏好和需求。

## 可能的情况

* 一家服装公司通过测试各种图像并在行动号召文本中使用用户的名字个性化营销活动登陆页面，从而提高了转化率。

* 一家电子商务公司发现，通过在促销活动登陆页面上测试各种产品描述和图像，其金会员的转化率较高，从而增加了销售额。

## 步骤

>[!NOTE]
>
>此部分中的说明突出显示更改图像以及使用用户档案属性个性化文本消息的必要步骤。 有关[!DNL Journey Optimizer] Web设计器中可用选项的详细信息，请参阅&#x200B;*Journey Optimizer文档*&#x200B;中的[使用Web设计器](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}。
>
>页面底部的视频特别有用。

要通过使用用户档案脚本测试各种图像并用用户的名字个性化消息来优化网页，请执行以下操作：

1. 在[!DNL Journey Optimizer]中，单击左边栏中的&#x200B;**促销活动**&#x200B;以显示[!UICONTROL Campaigns]页面。

1. 单击[!UICONTROL Campaigns]页面右上角的&#x200B;**[!UICONTROL Create Campaign]**。

1. 选择&#x200B;**[!UICONTROL Scheduled - Marketing]**（默认），然后单击&#x200B;**创建**&#x200B;以显示[!UICONTROL Campaign]详细信息页面。

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;部分中，为营销策划提供描述性名称和可选描述。

1. （视情况而定）在&#x200B;**[!UICONTROL Audience]**&#x200B;部分中，单击&#x200B;**[!UICONTROL Select Audience]**&#x200B;并选择所需的受众。

   对于此用例，您可以激活[!UICONTROL All Visitors]的营销活动（默认）。

1. 在&#x200B;**[!UICONTROL Action]**&#x200B;部分中，从&#x200B;**[!UICONTROL Action]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Web]**，然后选择或创建新的Web配置。

   Web配置或渠道界面是由系统管理员定义的配置。 Web配置包含用于发送消息的所有技术参数，如标头参数、子域、移动应用程序等。

   有关详细信息，请参阅&#x200B;*Journey Optimizer文档*&#x200B;中的[设置渠道平面](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank}。

1. 在&#x200B;**[!UICONTROL Action]**&#x200B;部分中，单击&#x200B;**[!UICONTROL Edit Content]**&#x200B;以在[!DNL Journey Optimizer] Web设计器中打开您的网站。

   A/B测试需要两个或多个实验。 您可以使用现有主页作为第一个试验。 后续步骤将说明如何设置第二个试验。

   ![LUMA网站上的瑜伽登陆页面](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. 要创建试验以确定哪些内容表现更好，请单击&#x200B;**[!UICONTROL Create Experiment]**。

   通过内容试验，可更改消息内容、主题或发件人，以定义多种处理方式并确定适合受众的最佳组合。 有关详细信息，请参阅&#x200B;*Journey Optimizer文档*&#x200B;中的[创建内容试验](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank}。

1. 选择一个成功量度并单击操作。

   单击“帮助”图标可获取更多信息和相关文章的链接。

1. 单击&#x200B;**[!UICONTROL Add Treatment]**，然后单击&#x200B;**[!UICONTROL Create]**。

   对于此用例，可将每个试验的分布保留为50%。

1. 在[!UICONTROL Campaign]详细信息页面的&#x200B;**[!UICONTROL Action]**&#x200B;下，单击&#x200B;**[!UICONTROL Edit Content]**。

1. 单击处理B下的Web。

   对于此用例，请保持[!UICONTROL Treatment A]不变，以使用原始体验作为A/B测试中的第一个体验。

1. 单击右边栏中的&#x200B;**[!UICONTROL Edit Web Page]**。

   ![在瑜伽登陆页面上编辑内容页面](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. 要更改主页图像，请单击要更改的图像，然后单击&#x200B;**[!UICONTROL Choose Image]**&#x200B;按钮。

   ![选择图像按钮](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. 浏览并选择所需的图像，然后单击&#x200B;**[!UICONTROL Use This Image]**。

   ![瑜伽页面上的新英雄图像](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. 要使用配置文件属性以用户的名字个性化邮件，请单击要个性化的文本，然后单击“**[!UICONTROL Add Personalization]**”以显示“[!UICONTROL Add Personalization]”页面。

   ![添加Personalization按钮。](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   有关配置文件属性的更多信息，请参阅&#x200B;*Journey Optimizer文档*&#x200B;中的[个性化编辑器入门](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank}。

1. 搜索并单击加号以添加“名字”配置文件属性，根据需要调整文本，然后单击&#x200B;**[!UICONTROL Save]**。

   ![为名称](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)添加配置文件属性

   有关详细信息，请参阅&#x200B;*Journey Optimizer文档*&#x200B;中的[个性化编辑器入门](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank}。

1. 单击左上角的返回箭头可返回到Web设计器。

   ![后退箭头](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. 单击&#x200B;**[!UICONTROL Review to Activate]**，确保一切按预期显示，然后单击&#x200B;**激活**。

## 查看报表

单击[!UICONTROL Reports]按钮，然后单击所需的报告周期：

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

有关详细信息，请参阅&#x200B;*Journey Optimizer文档*&#x200B;中的[开始使用新的报表接口](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank}。

>[!MORELIKETHIS]
>
>在&#x200B;*Journey Optimizer文档*&#x200B;中[使用Web设计器](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}
>[在&#x200B;*Journey Optimizer教程*&#x200B;中创建营销活动](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank}

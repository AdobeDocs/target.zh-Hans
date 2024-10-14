---
keywords: 活动URL；URL；其他URL
description: 了解如何设置[!UICONTROL Activity URL]以定义测试页面并确保精确的测试设计。
title: A/B活动中的活动URL是什么？
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: 6e9d18b8347d8ae68be699640c4cde91bdec762c
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 40%

---

# 活动 URL

活动URL可确定测试中使用的页面，以及在使用[!DNL Adobe Target]设计测试时打开的页面。

在活动创建过程中，如果收到相应的提示，请指定活动 URL。键入完整的URL（包括`https://`），然后单击&#x200B;**[!UICONTROL Create]**。

>[!NOTE]
>
>[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `http://www.adobe.com`]和[!DNL `https://www.adobe.com`]都匹配。

## 指定其他 URL

默认情况下，[!UICONTROL Visual Experience Composer]会打开[可视化体验编辑器设置](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的页面。 在活动创建过程中，您可以指定其他页面。

1. 要在[!UICONTROL Visual Experience Composer]打开后显示其他页面，请在&#x200B;**[!UICONTROL Experiences]**&#x200B;页面上单击页面顶部的&#x200B;**[!UICONTROL Configure]**，然后选择&#x200B;**[!UICONTROL Page Delivery]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;字段中指定URL。

1. （视情况而定）单击&#x200B;**[!UICONTROL Add Rule]**&#x200B;以向活动添加更多页面或部分。

   其他规则可以基于以下任何一项：

   * URL
   * 域
   * 路径
   * 话题标签 (#) 片段
   * 查询
   * mbox 参数

   其他规则可以通过AND或OR连接到活动URL。 您添加的所有规则将使用 AND 进行相互评估。

1. 完成后单击&#x200B;**[!UICONTROL Save]**。

<!-- If you entered a URL for a site that does not include the [!DNL Target]s JavaScript code, you cannot select page elements.

By default, the [!UICONTROL Visual Experience Composer] does not allow changes to elements containing JavaScript, such as rotating banners. You can toggle off **[!UICONTROL Render using JavaScript]** if you want to be able to alter those elements using the [!UICONTROL Visual Experience Composer].-->

>[!NOTE]
>
>在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。
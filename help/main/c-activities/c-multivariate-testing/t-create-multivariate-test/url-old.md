---
keywords: 多变量测试；活动URL
description: 了解如何指定活动URL，以确定测试中使用的页面，以及在使用 [!DNL Adobe Target]设计[!UICONTROL Multivariate Test]活动时打开的页面。
title: '[!UICONTROL Multivariate Test] (MVT)活动中的活动网址是什么？'
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 34%

---

# 活动 URL

活动URL可决定[!UICONTROL Multivariate Test] (MVT)中使用的页面，以及在[!DNL Adobe Target]中设计测试时打开的页面。

在[活动创建](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)过程中，如果收到相应的提示，请指定活动 URL。键入完整的URL（包括`https://`），然后单击&#x200B;**[!UICONTROL Next]**。

>[!NOTE]
>
>[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `https://www.adobe.com`]和[!DNL `http://www.adobe.com`]都匹配。

默认情况下，[!UICONTROL Visual Experience Composer] (VEC)会打开[可视化体验编辑器设置](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的页面。 在活动创建过程中，您可以指定其他页面。

要在VEC打开后显示其他页面，请单击&#x200B;**[!UICONTROL Configure]**&#x200B;图标，选择&#x200B;**[!UICONTROL Page Delivery]**，然后指定URL。

![“页面交付”对话框](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

单击&#x200B;**[!UICONTROL Add Template Rule]**&#x200B;可向活动添加更多页面或部分。

其他规则可以基于以下任何一项：

* URL
* 域
* 路径
* 话题标签 (#) 片段
* 查询
* 参数

其他规则可以通过AND或OR连接到活动URL。 使用AND会相互评估您添加的所有规则。

完成后单击&#x200B;**[!UICONTROL Save]**。

>[!NOTE]
>
>如果您输入的URL所对应的网站不包含[!DNL Target] JavaScript代码，则您将无法选择页面元素。

默认情况下，VEC 不允许更改包含 JavaScript 的元素，如旋转横幅。如果您希望能够使用[!UICONTROL Visual Experience Composer]更改这些元素，可以关闭&#x200B;**[!UICONTROL Render using JavaScript]**。

>[!NOTE]
>
>在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。

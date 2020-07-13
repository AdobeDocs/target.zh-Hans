---
keywords: capture score;score
description: “捕获分数”参与度量根据分配给网站上访问的页面的值计算汇总分数，该值从访客第一次看到活动的第一个显示目标请求时开始。
title: 捕捉分数
subtopic: Getting Started
topic: Standard
uuid: 977454ad-da32-449a-a8c9-1f3c75220be6
translation-type: tm+mt
source-git-commit: 32217a752574f671b790880667ac869443778f51
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 51%

---


# 捕捉分数{#capture-score}

The Capture Score engagement metric calculates an aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the campaign&#39;s first display [!DNL Target] request.

下面的例子显示了在对两个体验（一个包含猫的图像，一个包含狗的图像）进行测试的营销活动中，如何计算分数参与量度。

![](assets/example_score.png)

在这个例子中，第一个访客选择了包含猫图像的体验。Assume that a global [!DNL Target] request passes in a page score based on the value of the page. If the marketer has captured page count engagement on a success metric associated with `**any Target request**`, the visit score accumulates for any request seen after the display request around the cat image.

第一个页面加 1 分，第二个页面加 0.25 分，第三个页面加 0.10 分，第四个页面加 0.10 分，总分为 1.45。可以将这个分数理解为货币或积分。在另外一次访问中，某位访客选择了包含狗图像的体验，尽管该访客查看的页面较少，但得分为 2.10，比其他访问的分数更高，因为他浏览的网页更有价值。

通过 adbox 和重定向器，您可以考虑购置成本和联属链接收入，详见下述页流程图中的描述。Notice that, in this example, both [!DNL Target] requests on the article page pass a score, possibly representing a known CPM.

![](assets/example_score2.png)

**分配网页分数**

您可以根据网页对您的价值为网站上的任何页面分配一个值。例如，烹饪网站的专题文章页面可能比体验区域获得更多广告收益。因此，专题文章页面比体验区域更具价值。网页分数可让您设计一次访问的整体“价值”，使得阅读更多专题文章的访客能够比仅仅浏览体验的访客得到更多“点数”。

分配网页分数的方法有两种：

* 在请求 [!DNL Target] 中，创建一个名为的参数 `mboxPageValue`。

   示例: `('global_mbox', 'mboxPageValue=10');`

   The specified value is added to the score every time the page with that [!DNL Target] request is viewed. 如果页面上的多个请求包含得分值，则页面的得分是所有请求值的总和。 `mboxPageValue` 是用于在目标请求中传递值以捕获参与得分的保留参数。 可以传递正值和负值。在每位访客结束访问后，将计算总和值以计算访问的总分。

* 在页面 URL 中传递 `?mboxPageValue=n` 参数。

   示例: `https://www.mydomain.com?mboxPageValue=5`

   Using this method, the specified value is added to the score for each [!DNL Target] request on the page. For example, if you pass the parameter `?mboxPageValue=10`and there are three [!DNL Target] requests on the page, the score for the page is 30.

>[!NOTE]
>
>目标请求位于活动的第一个显 [!DNL Target] 示请求之上，将不会包括在得分中。

Best practice is to assign values in the [!DNL Target] request. 这样，根据每个请求的内容，您可以精确测量值。

>[!NOTE]
>
>为便于维护，您可以在 [!DNL at.js] 或 [!DNL mbox.js] 文件中使用某些条件性 JavaScript 逻辑配置网站的页面分数值分配。这样就无需向网页添加更多代码。请联系您的客户顾问以寻求帮助。

您可以结合使用上述两种方法，但这可能导致实际分数比应得分数更高。For example, if you assign a value of 10 to each of three [!DNL Target] requests and no score to a fourth request, then pass the URL parameter `?mboxPageValue=5`, your page score will be 50, 30 for the three requests with assigned values, and then 5 for each of the four requests on the page.

计数器开始第一个显示请求，而不是输入请求。 例如，如果您在主页上输入没有显示请求的活动，然后链接到包含显示请求的目录页面，则当您移到目录页面时，计数器开始。

您还可以为某些特定网页分配负值，因为它们会增加您的成本或者不应该被访客看到。负值同样影响整体分数。这一技巧可应用在访客通过广告进入的网页上，这样您就能了解 CPC 的成本是多少。或者，它还可以应用于支持或联系页面，让您了解访客在此页面上可能需要寻求帮助。

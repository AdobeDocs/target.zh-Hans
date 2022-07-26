---
keywords: 捕捉分数;分数
description: 了解Adobe中的“捕捉分数”参与量度 [!DNL Target] 它会根据分配给网站上已访问页面的值来计算累积分数。
title: 什么是捕捉分数量度？
feature: Success Metrics
exl-id: 3446cdef-7ee0-40dd-bf17-27def56668d4
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 48%

---

# 捕捉分数

中的“捕捉分数”参与量度 [!DNL Adobe Target] 从访客第一次看到营销活动的第一个显示开始，根据网站上已访问页面的分配值计算出一个累积分数 [!DNL Target] 请求。

下面的例子显示了在对两个体验（一个包含猫的图像，一个包含狗的图像）进行测试的营销活动中，如何计算分数参与量度。

![example_score图像](assets/example_score.png)

在这个例子中，第一个访客选择了包含猫图像的体验。假设全局 [!DNL Target] 请求会根据页面的值在页面得分中传递。 如果营销人员已在与关联的成功量度上捕捉到页面计数参与度 `**any Target request**`，则对于在猫图像周围的显示请求之后看到的任何请求，都会累积访问分数。

第一个页面加 1 分，第二个页面加 0.25 分，第三个页面加 0.10 分，第四个页面加 0.10 分，总分为 1.45。可以将这个分数理解为货币或积分。在另外一次访问中，某位访客选择了包含狗图像的体验，尽管该访客查看的页面较少，但得分为 2.10，比其他访问的分数更高，因为他浏览的网页更有价值。

通过 adbox 和重定向器，您可以考虑购置成本和联属链接收入，详见下述页流程图中的描述。请注意，在本例中， [!DNL Target] 文章页面上的请求传递了一个分数，可能表示已知的CPM。

![example_score2图像](assets/example_score2.png)

## 分配页面分数

您可以根据网页对您的价值为网站上的任何页面分配一个值。例如，烹饪网站的专题文章页面可能比体验区域获得更多广告收益。因此，专题文章页面比体验区域更具价值。网页分数可让您设计一次访问的整体“价值”，使得阅读更多专题文章的访客能够比仅仅浏览体验的访客得到更多“点数”。

分配网页分数的方法有两种：

* 在 [!DNL Target] 请求，请创建名为 `mboxPageValue`.

   示例: `('global_mbox', 'mboxPageValue=10');`

   每次使用该值的页面进行分数时，指定的值都会被添加到分数中 [!DNL Target] 请求。 如果页面上的多个请求包含分数值，则页面的分数是所有请求值的总和。 `mboxPageValue` 是一个保留参数，用于在Target请求中传递值以捕捉参与度分数。 可以传递正值和负值。在每位访客结束访问后，将计算总和值以计算访问的总分。

* 在页面 URL 中传递 `?mboxPageValue=n` 参数。

   示例: `https://www.mydomain.com?mboxPageValue=5`

   使用此方法，会将指定的值添加到每个 [!DNL Target] 请求。 例如，如果传递参数 `?mboxPageValue=10`还有三个 [!DNL Target] 请求时，该页面的得分为30。

>[!NOTE]
>
>位于活动第一次显示上方的Target请求 [!DNL Target] 分数中不包含请求。

最佳做法是在 [!DNL Target] 请求。 这样，您就可以根据每个请求的内容，精确地测量所测量的值。

>[!NOTE]
>
>为便于维护，您可以在 [!DNL at.js] 文件中包含一些条件性JavaScript逻辑。 这样就无需向网页添加更多代码。请联系您的客户顾问以寻求帮助。

您可以结合使用上述两种方法，但这可能导致实际分数比应得分数更高。例如，如果为三个变量中的每个变量赋值10 [!DNL Target] 请求而不对第四个请求进行任何分数，然后传递URL参数 `?mboxPageValue=5`，则对于三个具有分配值的请求，页面分数将为50，其中30分为，对于页面上的四个请求，每个请求的分数为5。

计数器以第一个显示请求（而不是条目请求）开头。 例如，如果您在主页上输入没有显示请求的活动，然后链接到包含显示请求的目录页面，则计数器将在您移动到目录页面时开始计数。

您还可以为某些特定网页分配负值，因为它们会增加您的成本或者不应该被访客看到。负值同样影响整体分数。这一技巧可应用在访客通过广告进入的网页上，这样您就能了解 CPC 的成本是多少。或者，它还可以应用于支持或联系页面，让您了解访客在此页面上可能需要寻求帮助。
